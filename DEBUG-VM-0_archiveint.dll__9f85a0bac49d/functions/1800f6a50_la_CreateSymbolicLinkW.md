# la_CreateSymbolicLinkW

- ea: `0x1800f6a50`
- end: `0x1800f6b9c`
- name: `la_CreateSymbolicLinkW`
- size: `332`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x1800f6098`

## callees

- `0x1800f656c`
- `0x1800f65c4`
- `0x1800f6a50`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6a91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6a91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6b8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6b8f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f6ab6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f6ab6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6b3d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6b3d`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x1800f6a5f`

## pseudocode

```c
__int64 __fastcall la_CreateSymbolicLinkW(LPCWSTR lpFileName, __int16 *a2, int a3)
{
  __int16 *v4; // rdi
  __int64 v6; // rbx
  void *v8; // rax
  void *v9; // rsi
  unsigned int v10; // r15d
  __int16 *i; // rcx
  __int16 v12; // dx
  DWORD FileAttributesW; // eax
  unsigned __int8 v14; // al
  unsigned int v15; // ebx

  qword_180155C90 = (__int64)CreateSymbolicLinkW;
  v4 = a2;
  if ( !CreateSymbolicLinkW )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( !v6 )
  {
    *(_DWORD *)_o__errno() = 22;
    return 0;
  }
  v8 = malloc(2 * v6 + 2);
  v9 = v8;
  if ( !v8 )
    return 0;
  v10 = 0;
  for ( i = (__int16 *)v8; ; ++i )
  {
    v12 = *v4;
    if ( !*v4 )
      break;
    if ( v12 == 47 )
      v12 = 92;
    ++v4;
    *i = v12;
  }
  *i = 0;
  if ( a3 != 1
    && (a3 == 2
     || *(i - 1) == 92
     || *(i - 1) == 46 && (v6 == 1 || *(i - 2) == 92 || *(i - 2) == 46 && (v6 == 2 || *(i - 3) == 92))) )
  {
    v10 = 1;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      disk_rmdir(lpFileName);
    else
      disk_unlink(lpFileName);
  }
  v14 = ((__int64 (__fastcall *)(LPCWSTR, void *, _QWORD))qword_180155C90)(lpFileName, v9, v10 | 2);
  if ( !v14 )
    v14 = ((__int64 (__fastcall *)(LPCWSTR, void *, _QWORD))qword_180155C90)(lpFileName, v9, v10);
  v15 = v14;
  free(v9);
  return v15;
}

```

## disassembly

```asm
0x1800f6a50  push    rbx
0x1800f6a52  push    rbp
0x1800f6a53  push    rsi
0x1800f6a54  push    rdi
0x1800f6a55  push    r12
0x1800f6a57  push    r14
0x1800f6a59  push    r15
0x1800f6a5b  sub     rsp, 20h
0x1800f6a5f  mov     rax, cs:__imp_CreateSymbolicLinkW
0x1800f6a66  xor     r12d, r12d
0x1800f6a69  mov     cs:qword_180155C90, rax
0x1800f6a70  mov     r14d, r8d
0x1800f6a73  mov     rdi, rdx
0x1800f6a76  mov     rbp, rcx
0x1800f6a79  cmp     rax, r12
0x1800f6a7c  jz      short loc_1800F6A9D
0x1800f6a7e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f6a82  inc     rbx
0x1800f6a85  cmp     [rdx+rbx*2], r12w
0x1800f6a8a  jnz     short loc_1800F6A82
0x1800f6a8c  test    rbx, rbx
0x1800f6a8f  jnz     short loc_1800F6AAE
0x1800f6a91  call    cs:__imp__o__errno
0x1800f6a97  mov     dword ptr [rax], 16h
0x1800f6a9d  xor     eax, eax
0x1800f6a9f  add     rsp, 20h
0x1800f6aa3  pop     r15
0x1800f6aa5  pop     r14
0x1800f6aa7  pop     r12
0x1800f6aa9  pop     rdi
0x1800f6aaa  pop     rsi
0x1800f6aab  pop     rbp
0x1800f6aac  pop     rbx
0x1800f6aad  retn
0x1800f6aae  lea     rcx, ds:2[rbx*2]; Size
0x1800f6ab6  call    cs:__imp_malloc
0x1800f6abc  mov     rsi, rax
0x1800f6abf  test    rax, rax
0x1800f6ac2  jz      short loc_1800F6A9D
0x1800f6ac4  mov     r15d, r12d
0x1800f6ac7  mov     rcx, rax
0x1800f6aca  mov     r8d, 5Ch ; '\'
0x1800f6ad0  jmp     short loc_1800F6AE7
0x1800f6ad2  cmp     dx, 2Fh ; '/'
0x1800f6ad6  jnz     short loc_1800F6ADC
0x1800f6ad8  movzx   edx, r8w
0x1800f6adc  add     rdi, 2
0x1800f6ae0  mov     [rcx], dx
0x1800f6ae3  add     rcx, 2
0x1800f6ae7  movzx   edx, word ptr [rdi]
0x1800f6aea  test    dx, dx
0x1800f6aed  jnz     short loc_1800F6AD2
0x1800f6aef  mov     [rcx], r12w
0x1800f6af3  cmp     r14d, 1
0x1800f6af7  jz      short loc_1800F6B34
0x1800f6af9  cmp     r14d, 2
0x1800f6afd  jz      short loc_1800F6B2E
0x1800f6aff  cmp     [rcx-2], r8w
0x1800f6b04  jz      short loc_1800F6B2E
0x1800f6b06  cmp     word ptr [rcx-2], 2Eh ; '.'
0x1800f6b0b  jnz     short loc_1800F6B34
0x1800f6b0d  cmp     rbx, 1
0x1800f6b11  jz      short loc_1800F6B2E
0x1800f6b13  cmp     [rcx-4], r8w
0x1800f6b18  jz      short loc_1800F6B2E
0x1800f6b1a  cmp     word ptr [rcx-4], 2Eh ; '.'
0x1800f6b1f  jnz     short loc_1800F6B34
0x1800f6b21  cmp     rbx, 2
0x1800f6b25  jz      short loc_1800F6B2E
0x1800f6b27  cmp     [rcx-6], r8w
0x1800f6b2c  jnz     short loc_1800F6B34
0x1800f6b2e  mov     r15d, 1
0x1800f6b34  mov     ebx, r15d
0x1800f6b37  mov     rcx, rbp; lpFileName
0x1800f6b3a  or      ebx, 2
0x1800f6b3d  call    cs:__imp_GetFileAttributesW
0x1800f6b43  cmp     eax, 0FFFFFFFFh
0x1800f6b46  jz      short loc_1800F6B5B
0x1800f6b48  mov     rcx, rbp; lpFileName
0x1800f6b4b  test    al, 10h
0x1800f6b4d  jz      short loc_1800F6B56
0x1800f6b4f  call    disk_rmdir
0x1800f6b54  jmp     short loc_1800F6B5B
0x1800f6b56  call    disk_unlink
0x1800f6b5b  mov     rax, cs:qword_180155C90
0x1800f6b62  mov     r8d, ebx
0x1800f6b65  mov     rdx, rsi
0x1800f6b68  mov     rcx, rbp
0x1800f6b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b70  test    al, al
0x1800f6b72  jnz     short loc_1800F6B89
0x1800f6b74  mov     rax, cs:qword_180155C90
0x1800f6b7b  mov     r8d, r15d
0x1800f6b7e  mov     rdx, rsi
0x1800f6b81  mov     rcx, rbp
0x1800f6b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b89  mov     rcx, rsi; Block
0x1800f6b8c  movzx   ebx, al
0x1800f6b8f  call    cs:__imp_free
0x1800f6b95  mov     eax, ebx
0x1800f6b97  jmp     loc_1800F6A9F
```
