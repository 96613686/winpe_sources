# IParseFile

- ea: `0x1801a80e4`
- end: `0x1801a82a3`
- name: `IParseFile`
- size: `447`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801a8334`
- `0x1801ab3d0`

## callees

- `0x1800032e0`
- `0x180149ae8`
- `0x1801a80e4`
- `0x1801ad33c`
- `0x1801ad4e8`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1801a812c`
- `KERNEL32!GetFullPathNameW` at `0x1801a8176`
- `KERNEL32!GetFullPathNameW` at `0x1801a812c`
- `KERNEL32!GetFullPathNameW` at `0x1801a8176`
- `KERNEL32!HeapAlloc` at `0x1801a8151`
- `KERNEL32!HeapAlloc` at `0x1801a8151`
- `KERNEL32!LocalFree` at `0x1801a8233`
- `KERNEL32!LocalFree` at `0x1801a823c`
- `KERNEL32!LocalFree` at `0x1801a8263`
- `KERNEL32!LocalFree` at `0x1801a826c`
- `KERNEL32!LocalFree` at `0x1801a8233`
- `KERNEL32!LocalFree` at `0x1801a823c`
- `KERNEL32!LocalFree` at `0x1801a8263`
- `KERNEL32!LocalFree` at `0x1801a826c`

## pseudocode

```c
__int64 __fastcall IParseFile(__int64 a1, WCHAR *a2)
{
  DWORD FullPathNameW; // eax
  DWORD v5; // esi
  char *v6; // rax
  _QWORD *v7; // rbx
  DWORD v8; // eax
  __int64 v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  int v12; // r14d
  __int64 v13; // r8
  unsigned __int8 *v14; // r9
  __int64 v15; // rax
  bool v16; // zf
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // ebp
  unsigned int v22; // esi
  void *v23; // rcx
  void *v25; // rcx
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
  v9 = PCreateFileObj(a2);
  v10 = (_QWORD *)v9;
  if ( !v9 )
    return 4294967294LL;
  v11 = *(unsigned __int16 *)(a1 + 524);
  v12 = 0;
  *(_QWORD *)(a1 + 16) = v9;
  v13 = *(unsigned int *)(v9 + 40);
  v14 = *(unsigned __int8 **)(v9 + 16);
  if ( (_DWORD)v13 )
  {
    do
    {
      v15 = *v14++;
      LOWORD(v11) = *((_WORD *)qword_1802222E0 + (v15 ^ ((unsigned __int64)(unsigned __int16)v11 >> 8)))
                  ^ ((_WORD)v11 << 8);
      v16 = (_DWORD)v13 == 1;
      v13 = (unsigned int)(v13 - 1);
    }
    while ( !v16 );
  }
  *(_WORD *)(a1 + 524) = v11;
  v17 = IParseEntry(a1, v11, v13, v14);
  v21 = -3;
  while ( 1 )
  {
    v22 = v17;
    if ( v17 == -4 )
    {
      UnmapFileFromMemory(*v10, v10[1]);
      v23 = (void *)v10[6];
      if ( v23 )
        LocalFree(v23);
      LocalFree(v10);
      if ( v12 <= 0 )
        return 0;
      return v21;
    }
    if ( v17 == -3 )
    {
      ++v12;
      goto LABEL_12;
    }
    if ( v17 )
      break;
LABEL_12:
    v17 = IParseEntry(a1, v18, v19, v20);
  }
  UnmapFileFromMemory(*v10, v10[1]);
  v25 = (void *)v10[6];
  if ( v25 )
    LocalFree(v25);
  LocalFree(v10);
  return v22;
}

```

## disassembly

```asm
0x1801a80e4  mov     [rsp+arg_10], rbx
0x1801a80e9  mov     [rsp+arg_18], rbp
0x1801a80ee  push    rsi
0x1801a80ef  push    rdi
0x1801a80f0  push    r14
0x1801a80f2  sub     rsp, 250h
0x1801a80f9  mov     rax, cs:__security_cookie
0x1801a8100  xor     rax, rsp
0x1801a8103  mov     [rsp+268h+var_28], rax
0x1801a810b  mov     rbp, rdx
0x1801a810e  mov     [rsp+268h+FilePart], 0
0x1801a8117  mov     rdi, rcx
0x1801a811a  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x1801a811f  mov     rcx, rbp; lpFileName
0x1801a8122  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1801a8127  mov     edx, 104h; nBufferLength
0x1801a812c  call    cs:__imp_GetFullPathNameW
0x1801a8132  mov     esi, eax
0x1801a8134  test    eax, eax
0x1801a8136  jz      loc_1801A8276
0x1801a813c  mov     rcx, [rdi+8]; hHeap
0x1801a8140  lea     r8d, ds:2[rax*2]
0x1801a8148  add     r8, 10h; dwBytes
0x1801a814c  mov     edx, 8; dwFlags
0x1801a8151  call    cs:__imp_HeapAlloc
0x1801a8157  mov     rbx, rax
0x1801a815a  test    rax, rax
0x1801a815d  jz      loc_1801A8276
0x1801a8163  lea     r8, [rax+10h]; lpBuffer
0x1801a8167  mov     rcx, rbp; lpFileName
0x1801a816a  lea     edx, [rsi+1]; nBufferLength
0x1801a816d  mov     [rax+8], r8
0x1801a8171  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x1801a8176  call    cs:__imp_GetFullPathNameW
0x1801a817c  test    eax, eax
0x1801a817e  jz      loc_1801A8276
0x1801a8184  cmp     eax, esi
0x1801a8186  ja      loc_1801A8276
0x1801a818c  mov     rax, [rdi+40h]
0x1801a8190  mov     rcx, rbp; Src
0x1801a8193  mov     [rbx], rax
0x1801a8196  mov     [rdi+40h], rbx
0x1801a819a  call    PCreateFileObj
0x1801a819f  mov     rbx, rax
0x1801a81a2  test    rax, rax
0x1801a81a5  jz      loc_1801A8276
0x1801a81ab  movzx   edx, word ptr [rdi+20Ch]
0x1801a81b2  xor     r14d, r14d
0x1801a81b5  mov     [rdi+10h], rax
0x1801a81b9  mov     r8d, [rax+28h]
0x1801a81bd  mov     r9, [rax+10h]
0x1801a81c1  test    r8d, r8d
0x1801a81c4  jz      short loc_1801A81EC
0x1801a81c6  movzx   eax, byte ptr [r9]
0x1801a81ca  inc     r9
0x1801a81cd  movzx   ecx, dx
0x1801a81d0  shr     rcx, 8
0x1801a81d4  xor     rcx, rax
0x1801a81d7  shl     dx, 8
0x1801a81db  lea     rax, qword_1802222E0
0x1801a81e2  xor     dx, [rax+rcx*2]
0x1801a81e6  add     r8d, 0FFFFFFFFh
0x1801a81ea  jnz     short loc_1801A81C6
0x1801a81ec  mov     rcx, rdi
0x1801a81ef  mov     [rdi+20Ch], dx
0x1801a81f6  call    IParseEntry
0x1801a81fb  mov     ebp, 0FFFFFFFDh
0x1801a8200  jmp     short loc_1801A8217
0x1801a8202  cmp     esi, ebp
0x1801a8204  jnz     short loc_1801A820B
0x1801a8206  inc     r14d
0x1801a8209  jmp     short loc_1801A820F
0x1801a820b  test    esi, esi
0x1801a820d  jnz     short loc_1801A824E
0x1801a820f  mov     rcx, rdi
0x1801a8212  call    IParseEntry
0x1801a8217  mov     esi, eax
0x1801a8219  cmp     eax, 0FFFFFFFCh
0x1801a821c  jnz     short loc_1801A8202
0x1801a821e  mov     rdx, [rbx+8]
0x1801a8222  mov     rcx, [rbx]
0x1801a8225  call    UnmapFileFromMemory
0x1801a822a  mov     rcx, [rbx+30h]; hMem
0x1801a822e  test    rcx, rcx
0x1801a8231  jz      short loc_1801A8239
0x1801a8233  call    cs:__imp_LocalFree
0x1801a8239  mov     rcx, rbx; hMem
0x1801a823c  call    cs:__imp_LocalFree
0x1801a8242  xor     ecx, ecx
0x1801a8244  test    r14d, r14d
0x1801a8247  cmovle  ebp, ecx
0x1801a824a  mov     eax, ebp
0x1801a824c  jmp     short loc_1801A827B
0x1801a824e  mov     rdx, [rbx+8]
0x1801a8252  mov     rcx, [rbx]
0x1801a8255  call    UnmapFileFromMemory
0x1801a825a  mov     rcx, [rbx+30h]; hMem
0x1801a825e  test    rcx, rcx
0x1801a8261  jz      short loc_1801A8269
0x1801a8263  call    cs:__imp_LocalFree
0x1801a8269  mov     rcx, rbx; hMem
0x1801a826c  call    cs:__imp_LocalFree
0x1801a8272  mov     eax, esi
0x1801a8274  jmp     short loc_1801A827B
0x1801a8276  mov     eax, 0FFFFFFFEh
0x1801a827b  mov     rcx, [rsp+268h+var_28]
0x1801a8283  xor     rcx, rsp; StackCookie
0x1801a8286  call    __security_check_cookie
0x1801a828b  lea     r11, [rsp+268h+var_18]
0x1801a8293  mov     rbx, [r11+30h]
0x1801a8297  mov     rbp, [r11+38h]
0x1801a829b  mov     rsp, r11
0x1801a829e  pop     r14
0x1801a82a0  pop     rdi
0x1801a82a1  pop     rsi
0x1801a82a2  retn
```
