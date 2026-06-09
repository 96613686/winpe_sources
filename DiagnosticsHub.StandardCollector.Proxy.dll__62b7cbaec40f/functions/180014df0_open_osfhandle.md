# _open_osfhandle

- ea: `0x180014df0`
- end: `0x180014ef0`
- name: `_open_osfhandle`
- size: `256`
- prototype: `int __cdecl(intptr_t OSFileHandle, int Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007e78`
- `0x180007ec4`
- `0x180007ee8`
- `0x180014a94`
- `0x180014b54`
- `0x180014b7c`
- `0x180014df0`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180014e32`
- `KERNEL32!GetFileType` at `0x180014e32`
- `KERNEL32!GetLastError` at `0x180014e3c`
- `KERNEL32!GetLastError` at `0x180014e3c`

## pseudocode

```c
int __cdecl open_osfhandle(intptr_t OSFileHandle, int Flags)
{
  char v3; // r8
  char v4; // bl
  DWORD FileType; // eax
  DWORD LastError; // eax
  unsigned int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rdx

  v3 = (4 * (Flags & 8)) | 0x80;
  if ( (Flags & 0x4000) == 0 )
    v3 = 4 * (Flags & 8);
  v4 = v3 | 0x10;
  if ( (Flags & 0x80u) == 0 )
    v4 = v3;
  FileType = GetFileType((HANDLE)OSFileHandle);
  switch ( FileType )
  {
    case 0u:
      LastError = GetLastError();
      _acrt_errno_map_os_error(LastError);
      return -1;
    case 2u:
      v4 |= 0x40u;
      break;
    case 3u:
      v4 |= 8u;
      break;
  }
  v8 = alloc_osfhnd();
  v9 = (int)v8;
  if ( v8 == -1 )
  {
    *errno() = 24;
    *_doserrno() = 0;
    return -1;
  }
  _acrt_lowio_set_os_handle(v8, OSFileHandle);
  v10 = 9 * (v9 & 0x3F);
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 56) = v4 | 1;
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 57) = 0;
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 61) = *(_BYTE *)(_pioinfo[v9 >> 6] + 72 * (v9 & 0x3F) + 61) & 0xFE;
  _acrt_lowio_unlock_fh((unsigned int)v9);
  return v9;
}

```

## disassembly

```asm
0x180014df0  mov     [rsp+arg_0], rbx
0x180014df5  mov     [rsp+arg_10], rsi
0x180014dfa  push    rdi
0x180014dfb  sub     rsp, 30h
0x180014dff  mov     rsi, rcx
0x180014e02  mov     al, dl
0x180014e04  and     al, 8
0x180014e06  shl     al, 2
0x180014e09  movzx   r10d, al
0x180014e0d  mov     al, r10b
0x180014e10  or      al, 80h
0x180014e12  movzx   r8d, al
0x180014e16  bt      edx, 0Eh
0x180014e1a  cmovnb  r8d, r10d
0x180014e1e  movzx   ecx, r8b
0x180014e22  mov     al, cl
0x180014e24  or      al, 10h
0x180014e26  movzx   ebx, al
0x180014e29  test    dl, 80h
0x180014e2c  cmovz   ebx, ecx
0x180014e2f  mov     rcx, rsi; hFile
0x180014e32  call    cs:__imp_GetFileType
0x180014e38  test    eax, eax
0x180014e3a  jnz     short loc_180014E5C
0x180014e3c  call    cs:__imp_GetLastError
0x180014e42  mov     ecx, eax
0x180014e44  call    __acrt_errno_map_os_error
0x180014e49  or      eax, 0FFFFFFFFh
0x180014e4c  mov     rbx, [rsp+38h+arg_0]
0x180014e51  mov     rsi, [rsp+38h+arg_10]
0x180014e56  add     rsp, 30h
0x180014e5a  pop     rdi
0x180014e5b  retn
0x180014e5c  cmp     eax, 2
0x180014e5f  jnz     short loc_180014E66
0x180014e61  or      bl, 40h
0x180014e64  jmp     short loc_180014E6E
0x180014e66  cmp     eax, 3
0x180014e69  jnz     short loc_180014E6E
0x180014e6b  or      bl, 8
0x180014e6e  call    _alloc_osfhnd
0x180014e73  movsxd  rdi, eax
0x180014e76  mov     [rsp+38h+arg_8], edi
0x180014e7a  cmp     edi, 0FFFFFFFFh
0x180014e7d  jnz     short loc_180014E94
0x180014e7f  call    _errno
0x180014e84  mov     dword ptr [rax], 18h
0x180014e8a  call    __doserrno
0x180014e8f  and     dword ptr [rax], 0
0x180014e92  jmp     short loc_180014E49
0x180014e94  mov     [rsp+38h+var_18], 0
0x180014e99  mov     rdx, rsi
0x180014e9c  mov     ecx, edi
0x180014e9e  call    __acrt_lowio_set_os_handle
0x180014ea3  or      bl, 1
0x180014ea6  mov     rax, rdi
0x180014ea9  mov     rcx, rdi
0x180014eac  sar     rcx, 6
0x180014eb0  lea     r8, __pioinfo
0x180014eb7  and     eax, 3Fh
0x180014eba  lea     rdx, [rax+rax*8]
0x180014ebe  mov     rax, [r8+rcx*8]
0x180014ec2  mov     [rax+rdx*8+38h], bl
0x180014ec6  mov     rax, [r8+rcx*8]
0x180014eca  mov     byte ptr [rax+rdx*8+39h], 0
0x180014ecf  mov     rcx, [r8+rcx*8]
0x180014ed3  mov     al, [rcx+rdx*8+3Dh]
0x180014ed7  and     al, 0FEh
0x180014ed9  mov     [rcx+rdx*8+3Dh], al
0x180014edd  mov     [rsp+38h+var_18], 1
0x180014ee2  mov     ecx, edi
0x180014ee4  call    __acrt_lowio_unlock_fh
0x180014ee9  mov     eax, edi
0x180014eeb  jmp     loc_180014E4C
0x180061542  push    rbp
0x180061544  sub     rsp, 20h
0x180061548  mov     rbp, rdx
0x18006154b  cmp     byte ptr [rbp+20h], 0
0x18006154f  jnz     short loc_180061589
0x180061551  movsxd  r9, dword ptr [rbp+48h]
0x180061555  mov     r8, r9
0x180061558  sar     r8, 6
0x18006155c  and     r9d, 3Fh
0x180061560  lea     rax, __pioinfo
0x180061567  lea     rcx, [r9+r9*8]
0x18006156b  mov     rax, [rax+r8*8]
0x18006156f  mov     dl, [rax+rcx*8+38h]
0x180061573  and     dl, 0FEh
0x180061576  lea     rax, __pioinfo
0x18006157d  lea     rcx, [r9+r9*8]
0x180061581  mov     rax, [rax+r8*8]
0x180061585  mov     [rax+rcx*8+38h], dl
0x180061589  mov     ecx, [rbp+48h]
0x18006158c  call    __acrt_lowio_unlock_fh
0x180061591  nop
0x180061592  add     rsp, 20h
0x180061596  pop     rbp
0x180061597  retn
```
