# IParseFile

- ea: `0x1801afa7c`
- end: `0x1801afc66`
- name: `IParseFile`
- size: `490`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801afeb8`
- `0x1801b2ec0`

## callees

- `0x180003400`
- `0x180150854`
- `0x1801afa7c`
- `0x1801b4e88`
- `0x1801b5054`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1801afac4`
- `KERNEL32!GetFullPathNameW` at `0x1801afb1a`
- `KERNEL32!GetFullPathNameW` at `0x1801afac4`
- `KERNEL32!GetFullPathNameW` at `0x1801afb1a`
- `KERNEL32!HeapAlloc` at `0x1801afaef`
- `KERNEL32!HeapAlloc` at `0x1801afaef`
- `KERNEL32!LocalFree` at `0x1801afbdd`
- `KERNEL32!LocalFree` at `0x1801afbec`
- `KERNEL32!LocalFree` at `0x1801afc19`
- `KERNEL32!LocalFree` at `0x1801afc28`
- `KERNEL32!LocalFree` at `0x1801afbdd`
- `KERNEL32!LocalFree` at `0x1801afbec`
- `KERNEL32!LocalFree` at `0x1801afc19`
- `KERNEL32!LocalFree` at `0x1801afc28`

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
    v11 = *((_WORD *)qword_180229FB0 + (v15 ^ ((unsigned __int64)v11 >> 8))) ^ (v11 << 8);
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
0x1801afa7c  mov     [rsp+arg_10], rbx
0x1801afa81  mov     [rsp+arg_18], rbp
0x1801afa86  push    rsi
0x1801afa87  push    rdi
0x1801afa88  push    r14
0x1801afa8a  sub     rsp, 250h
0x1801afa91  mov     rax, cs:__security_cookie
0x1801afa98  xor     rax, rsp
0x1801afa9b  mov     [rsp+268h+var_28], rax
0x1801afaa3  mov     rbp, rdx
0x1801afaa6  mov     [rsp+268h+FilePart], 0
0x1801afaaf  mov     rdi, rcx
0x1801afab2  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x1801afab7  mov     rcx, rbp; lpFileName
0x1801afaba  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1801afabf  mov     edx, 104h; nBufferLength
0x1801afac4  call    cs:__imp_GetFullPathNameW
0x1801afacb  nop     dword ptr [rax+rax+00h]
0x1801afad0  mov     esi, eax
0x1801afad2  test    eax, eax
0x1801afad4  jz      loc_1801AFC38
0x1801afada  mov     rcx, [rdi+8]; hHeap
0x1801afade  lea     r8d, ds:2[rax*2]
0x1801afae6  add     r8, 10h; dwBytes
0x1801afaea  mov     edx, 8; dwFlags
0x1801afaef  call    cs:__imp_HeapAlloc
0x1801afaf6  nop     dword ptr [rax+rax+00h]
0x1801afafb  mov     rbx, rax
0x1801afafe  test    rax, rax
0x1801afb01  jz      loc_1801AFC38
0x1801afb07  lea     r8, [rax+10h]; lpBuffer
0x1801afb0b  mov     rcx, rbp; lpFileName
0x1801afb0e  lea     edx, [rsi+1]; nBufferLength
0x1801afb11  mov     [rax+8], r8
0x1801afb15  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x1801afb1a  call    cs:__imp_GetFullPathNameW
0x1801afb21  nop     dword ptr [rax+rax+00h]
0x1801afb26  test    eax, eax
0x1801afb28  jz      loc_1801AFC38
0x1801afb2e  cmp     eax, esi
0x1801afb30  ja      loc_1801AFC38
0x1801afb36  mov     rax, [rdi+40h]
0x1801afb3a  mov     rcx, rbp; Src
0x1801afb3d  mov     [rbx], rax
0x1801afb40  mov     [rdi+40h], rbx
0x1801afb44  call    PCreateFileObj
0x1801afb49  mov     rbx, rax
0x1801afb4c  test    rax, rax
0x1801afb4f  jz      loc_1801AFC38
0x1801afb55  movzx   edx, word ptr [rdi+20Ch]
0x1801afb5c  xor     r14d, r14d
0x1801afb5f  mov     [rdi+10h], rax
0x1801afb63  mov     r8d, [rax+28h]
0x1801afb67  mov     r9, [rax+10h]
0x1801afb6b  test    r8d, r8d
0x1801afb6e  jz      short loc_1801AFB96
0x1801afb70  movzx   eax, byte ptr [r9]
0x1801afb74  inc     r9
0x1801afb77  movzx   ecx, dx
0x1801afb7a  shr     rcx, 8
0x1801afb7e  xor     rcx, rax
0x1801afb81  shl     dx, 8
0x1801afb85  lea     rax, qword_180229FB0
0x1801afb8c  xor     dx, [rax+rcx*2]
0x1801afb90  add     r8d, 0FFFFFFFFh
0x1801afb94  jnz     short loc_1801AFB70
0x1801afb96  mov     rcx, rdi
0x1801afb99  mov     [rdi+20Ch], dx
0x1801afba0  call    IParseEntry
0x1801afba5  mov     ebp, 0FFFFFFFDh
0x1801afbaa  jmp     short loc_1801AFBC1
0x1801afbac  cmp     esi, ebp
0x1801afbae  jnz     short loc_1801AFBB5
0x1801afbb0  inc     r14d
0x1801afbb3  jmp     short loc_1801AFBB9
0x1801afbb5  test    esi, esi
0x1801afbb7  jnz     short loc_1801AFC04
0x1801afbb9  mov     rcx, rdi
0x1801afbbc  call    IParseEntry
0x1801afbc1  mov     esi, eax
0x1801afbc3  cmp     eax, 0FFFFFFFCh
0x1801afbc6  jnz     short loc_1801AFBAC
0x1801afbc8  mov     rdx, [rbx+8]
0x1801afbcc  mov     rcx, [rbx]
0x1801afbcf  call    UnmapFileFromMemory
0x1801afbd4  mov     rcx, [rbx+30h]; hMem
0x1801afbd8  test    rcx, rcx
0x1801afbdb  jz      short loc_1801AFBE9
0x1801afbdd  call    cs:__imp_LocalFree
0x1801afbe4  nop     dword ptr [rax+rax+00h]
0x1801afbe9  mov     rcx, rbx; hMem
0x1801afbec  call    cs:__imp_LocalFree
0x1801afbf3  nop     dword ptr [rax+rax+00h]
0x1801afbf8  xor     ecx, ecx
0x1801afbfa  test    r14d, r14d
0x1801afbfd  cmovle  ebp, ecx
0x1801afc00  mov     eax, ebp
0x1801afc02  jmp     short loc_1801AFC3D
0x1801afc04  mov     rdx, [rbx+8]
0x1801afc08  mov     rcx, [rbx]
0x1801afc0b  call    UnmapFileFromMemory
0x1801afc10  mov     rcx, [rbx+30h]; hMem
0x1801afc14  test    rcx, rcx
0x1801afc17  jz      short loc_1801AFC25
0x1801afc19  call    cs:__imp_LocalFree
0x1801afc20  nop     dword ptr [rax+rax+00h]
0x1801afc25  mov     rcx, rbx; hMem
0x1801afc28  call    cs:__imp_LocalFree
0x1801afc2f  nop     dword ptr [rax+rax+00h]
0x1801afc34  mov     eax, esi
0x1801afc36  jmp     short loc_1801AFC3D
0x1801afc38  mov     eax, 0FFFFFFFEh
0x1801afc3d  mov     rcx, [rsp+268h+var_28]
0x1801afc45  xor     rcx, rsp; StackCookie
0x1801afc48  call    __security_check_cookie
0x1801afc4d  lea     r11, [rsp+268h+var_18]
0x1801afc55  mov     rbx, [r11+30h]
0x1801afc59  mov     rbp, [r11+38h]
0x1801afc5d  mov     rsp, r11
0x1801afc60  pop     r14
0x1801afc62  pop     rdi
0x1801afc63  pop     rsi
0x1801afc64  retn
```
