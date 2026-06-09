# IParseFile

- ea: `0x180057d80`
- end: `0x180057f6a`
- name: `IParseFile`
- size: `490`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800581bc`
- `0x18005b210`

## callees

- `0x180001f20`
- `0x180031330`
- `0x180057d80`
- `0x18005d1d8`
- `0x18005d3a4`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180057dc8`
- `KERNEL32!GetFullPathNameW` at `0x180057e1e`
- `KERNEL32!GetFullPathNameW` at `0x180057dc8`
- `KERNEL32!GetFullPathNameW` at `0x180057e1e`
- `KERNEL32!HeapAlloc` at `0x180057df3`
- `KERNEL32!HeapAlloc` at `0x180057df3`
- `KERNEL32!LocalFree` at `0x180057ee1`
- `KERNEL32!LocalFree` at `0x180057ef0`
- `KERNEL32!LocalFree` at `0x180057f1d`
- `KERNEL32!LocalFree` at `0x180057f2c`
- `KERNEL32!LocalFree` at `0x180057ee1`
- `KERNEL32!LocalFree` at `0x180057ef0`
- `KERNEL32!LocalFree` at `0x180057f1d`
- `KERNEL32!LocalFree` at `0x180057f2c`

## pseudocode

```c
__int64 __fastcall IParseFile(__int64 a1, WCHAR *a2)
{
  DWORD FullPathNameW; // eax
  DWORD v5; // esi
  char *v6; // rax
  _QWORD *v7; // rbx
  DWORD v8; // eax
  const void **v9; // rax
  const void **v10; // rbx
  unsigned __int16 v11; // dx
  int v12; // r14d
  int v13; // r8d
  unsigned __int8 *i; // r9
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebp
  unsigned int v18; // esi
  void *v19; // rcx
  void *v21; // rcx
  LPWSTR FilePart[2]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  FilePart[0] = 0;
  FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, FilePart);
  v5 = FullPathNameW;
  if ( !FullPathNameW )
    return 4294967294LL;
  v6 = (char *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, 2 * FullPathNameW + 2 + 16LL);
  v7 = v6;
  if ( !v6 )
    return 4294967294LL;
  *((_QWORD *)v6 + 1) = v6 + 16;
  v8 = GetFullPathNameW(a2, v5 + 1, (LPWSTR)v6 + 8, FilePart);
  if ( !v8 )
    return 4294967294LL;
  if ( v8 > v5 )
    return 4294967294LL;
  *v7 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v7;
  v9 = (const void **)PCreateFileObj(a2);
  v10 = v9;
  if ( !v9 )
    return 4294967294LL;
  v11 = *(_WORD *)(a1 + 524);
  v12 = 0;
  *(_QWORD *)(a1 + 16) = v9;
  v13 = *((_DWORD *)v9 + 10);
  for ( i = (unsigned __int8 *)v9[2]; v13; --v13 )
  {
    v15 = *i++;
    v11 = *((_WORD *)qword_18006D7B0 + (v15 ^ ((unsigned __int64)v11 >> 8))) ^ (v11 << 8);
  }
  *(_WORD *)(a1 + 524) = v11;
  v16 = IParseEntry(a1);
  v17 = -3;
  while ( 1 )
  {
    v18 = v16;
    if ( v16 == -4 )
    {
      UnmapFileFromMemory(*v10, (void *)v10[1]);
      v19 = (void *)v10[6];
      if ( v19 )
        LocalFree(v19);
      LocalFree(v10);
      if ( v12 <= 0 )
        return 0;
      return v17;
    }
    if ( v16 == -3 )
    {
      ++v12;
      goto LABEL_12;
    }
    if ( v16 )
      break;
LABEL_12:
    v16 = IParseEntry(a1);
  }
  UnmapFileFromMemory(*v10, (void *)v10[1]);
  v21 = (void *)v10[6];
  if ( v21 )
    LocalFree(v21);
  LocalFree(v10);
  return v18;
}

```

## disassembly

```asm
0x180057d80  mov     [rsp+arg_10], rbx
0x180057d85  mov     [rsp+arg_18], rbp
0x180057d8a  push    rsi
0x180057d8b  push    rdi
0x180057d8c  push    r14
0x180057d8e  sub     rsp, 250h
0x180057d95  mov     rax, cs:__security_cookie
0x180057d9c  xor     rax, rsp
0x180057d9f  mov     [rsp+268h+var_28], rax
0x180057da7  mov     rbp, rdx
0x180057daa  mov     [rsp+268h+FilePart], 0
0x180057db3  mov     rdi, rcx
0x180057db6  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x180057dbb  mov     rcx, rbp; lpFileName
0x180057dbe  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180057dc3  mov     edx, 104h; nBufferLength
0x180057dc8  call    cs:__imp_GetFullPathNameW
0x180057dcf  nop     dword ptr [rax+rax+00h]
0x180057dd4  mov     esi, eax
0x180057dd6  test    eax, eax
0x180057dd8  jz      loc_180057F3C
0x180057dde  mov     rcx, [rdi+8]; hHeap
0x180057de2  lea     r8d, ds:2[rax*2]
0x180057dea  add     r8, 10h; dwBytes
0x180057dee  mov     edx, 8; dwFlags
0x180057df3  call    cs:__imp_HeapAlloc
0x180057dfa  nop     dword ptr [rax+rax+00h]
0x180057dff  mov     rbx, rax
0x180057e02  test    rax, rax
0x180057e05  jz      loc_180057F3C
0x180057e0b  lea     r8, [rax+10h]; lpBuffer
0x180057e0f  mov     rcx, rbp; lpFileName
0x180057e12  lea     edx, [rsi+1]; nBufferLength
0x180057e15  mov     [rax+8], r8
0x180057e19  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x180057e1e  call    cs:__imp_GetFullPathNameW
0x180057e25  nop     dword ptr [rax+rax+00h]
0x180057e2a  test    eax, eax
0x180057e2c  jz      loc_180057F3C
0x180057e32  cmp     eax, esi
0x180057e34  ja      loc_180057F3C
0x180057e3a  mov     rax, [rdi+40h]
0x180057e3e  mov     rcx, rbp; Src
0x180057e41  mov     [rbx], rax
0x180057e44  mov     [rdi+40h], rbx
0x180057e48  call    PCreateFileObj
0x180057e4d  mov     rbx, rax
0x180057e50  test    rax, rax
0x180057e53  jz      loc_180057F3C
0x180057e59  movzx   edx, word ptr [rdi+20Ch]
0x180057e60  xor     r14d, r14d
0x180057e63  mov     [rdi+10h], rax
0x180057e67  mov     r8d, [rax+28h]
0x180057e6b  mov     r9, [rax+10h]
0x180057e6f  test    r8d, r8d
0x180057e72  jz      short loc_180057E9A
0x180057e74  movzx   eax, byte ptr [r9]
0x180057e78  inc     r9
0x180057e7b  movzx   ecx, dx
0x180057e7e  shr     rcx, 8
0x180057e82  xor     rcx, rax
0x180057e85  shl     dx, 8
0x180057e89  lea     rax, qword_18006D7B0
0x180057e90  xor     dx, [rax+rcx*2]
0x180057e94  add     r8d, 0FFFFFFFFh
0x180057e98  jnz     short loc_180057E74
0x180057e9a  mov     rcx, rdi
0x180057e9d  mov     [rdi+20Ch], dx
0x180057ea4  call    IParseEntry
0x180057ea9  mov     ebp, 0FFFFFFFDh
0x180057eae  jmp     short loc_180057EC5
0x180057eb0  cmp     esi, ebp
0x180057eb2  jnz     short loc_180057EB9
0x180057eb4  inc     r14d
0x180057eb7  jmp     short loc_180057EBD
0x180057eb9  test    esi, esi
0x180057ebb  jnz     short loc_180057F08
0x180057ebd  mov     rcx, rdi
0x180057ec0  call    IParseEntry
0x180057ec5  mov     esi, eax
0x180057ec7  cmp     eax, 0FFFFFFFCh
0x180057eca  jnz     short loc_180057EB0
0x180057ecc  mov     rdx, [rbx+8]
0x180057ed0  mov     rcx, [rbx]
0x180057ed3  call    UnmapFileFromMemory
0x180057ed8  mov     rcx, [rbx+30h]; hMem
0x180057edc  test    rcx, rcx
0x180057edf  jz      short loc_180057EED
0x180057ee1  call    cs:__imp_LocalFree
0x180057ee8  nop     dword ptr [rax+rax+00h]
0x180057eed  mov     rcx, rbx; hMem
0x180057ef0  call    cs:__imp_LocalFree
0x180057ef7  nop     dword ptr [rax+rax+00h]
0x180057efc  xor     ecx, ecx
0x180057efe  test    r14d, r14d
0x180057f01  cmovle  ebp, ecx
0x180057f04  mov     eax, ebp
0x180057f06  jmp     short loc_180057F41
0x180057f08  mov     rdx, [rbx+8]
0x180057f0c  mov     rcx, [rbx]
0x180057f0f  call    UnmapFileFromMemory
0x180057f14  mov     rcx, [rbx+30h]; hMem
0x180057f18  test    rcx, rcx
0x180057f1b  jz      short loc_180057F29
0x180057f1d  call    cs:__imp_LocalFree
0x180057f24  nop     dword ptr [rax+rax+00h]
0x180057f29  mov     rcx, rbx; hMem
0x180057f2c  call    cs:__imp_LocalFree
0x180057f33  nop     dword ptr [rax+rax+00h]
0x180057f38  mov     eax, esi
0x180057f3a  jmp     short loc_180057F41
0x180057f3c  mov     eax, 0FFFFFFFEh
0x180057f41  mov     rcx, [rsp+268h+var_28]
0x180057f49  xor     rcx, rsp; StackCookie
0x180057f4c  call    __security_check_cookie
0x180057f51  lea     r11, [rsp+268h+var_18]
0x180057f59  mov     rbx, [r11+30h]
0x180057f5d  mov     rbp, [r11+38h]
0x180057f61  mov     rsp, r11
0x180057f64  pop     r14
0x180057f66  pop     rdi
0x180057f67  pop     rsi
0x180057f68  retn
```
