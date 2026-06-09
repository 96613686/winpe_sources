# __la_read

- ea: `0x18000eafc`
- end: `0x18000eba0`
- name: `__la_read`
- size: `164`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ea60`
- `0x1800c07b0`
- `0x1800c1028`
- `0x1800c3254`
- `0x1800d8b90`
- `0x1800f2aa0`
- `0x1800f2f50`
- `0x1800fa2f8`
- `0x180104fc4`
- `0x180105c30`
- `0x180107168`
- `0x1801106f4`

## callees

- `0x18000eafc`
- `0x1800149c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb6c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb6c`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18000eb38`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18000eb38`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000eb55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000eb55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb5f`

## pseudocode

```c
__int64 __fastcall _la_read(int a1, void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  DWORD LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0xFFFFFFFFLL;
  NumberOfBytesRead = 0;
  if ( a3 <= 0xFFFFFFFF )
    v3 = a3;
  if ( a1 < 0 )
  {
LABEL_4:
    *(_DWORD *)_o__errno() = 9;
    return -1;
  }
  if ( v3 )
  {
    osfhandle = (void *)_get_osfhandle(a1);
    if ( ReadFile(osfhandle, a2, v3, &NumberOfBytesRead, 0) )
      return NumberOfBytesRead;
    LastError = GetLastError();
    if ( LastError == 232 )
    {
      *(_DWORD *)_o__errno() = 11;
      return -1;
    }
    if ( LastError != 109 )
    {
      if ( LastError != 5 )
      {
        _la_dosmaperr(LastError);
        return -1;
      }
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000eafc  mov     [rsp+arg_8], rbx
0x18000eb01  push    rdi
0x18000eb02  sub     rsp, 30h
0x18000eb06  mov     ebx, 0FFFFFFFFh
0x18000eb0b  mov     [rsp+38h+NumberOfBytesRead], 0
0x18000eb13  cmp     r8, rbx
0x18000eb16  mov     rdi, rdx
0x18000eb19  cmovbe  rbx, r8
0x18000eb1d  test    ecx, ecx
0x18000eb1f  jns     short loc_18000EB33
0x18000eb21  call    cs:__imp__o__errno
0x18000eb27  mov     dword ptr [rax], 9
0x18000eb2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eb31  jmp     short loc_18000EB95
0x18000eb33  test    rbx, rbx
0x18000eb36  jz      short loc_18000EB93
0x18000eb38  call    cs:__imp__get_osfhandle
0x18000eb3e  mov     r8d, ebx; nNumberOfBytesToRead
0x18000eb41  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000eb4a  mov     rcx, rax; hFile
0x18000eb4d  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000eb52  mov     rdx, rdi; lpBuffer
0x18000eb55  call    cs:__imp_ReadFile
0x18000eb5b  test    eax, eax
0x18000eb5d  jnz     short loc_18000EB8D
0x18000eb5f  call    cs:__imp_GetLastError
0x18000eb65  cmp     eax, 0E8h
0x18000eb6a  jnz     short loc_18000EB7A
0x18000eb6c  call    cs:__imp__o__errno
0x18000eb72  mov     dword ptr [rax], 0Bh
0x18000eb78  jmp     short loc_18000EB2D
0x18000eb7a  cmp     eax, 6Dh ; 'm'
0x18000eb7d  jz      short loc_18000EB93
0x18000eb7f  cmp     eax, 5
0x18000eb82  jz      short loc_18000EB21
0x18000eb84  mov     ecx, eax
0x18000eb86  call    __la_dosmaperr
0x18000eb8b  jmp     short loc_18000EB2D
0x18000eb8d  mov     eax, [rsp+38h+NumberOfBytesRead]
0x18000eb91  jmp     short loc_18000EB95
0x18000eb93  xor     eax, eax
0x18000eb95  mov     rbx, [rsp+38h+arg_8]
0x18000eb9a  add     rsp, 30h
0x18000eb9e  pop     rdi
0x18000eb9f  retn
```
