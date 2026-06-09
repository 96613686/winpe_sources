# __la_write

- ea: `0x18000fe9c`
- end: `0x18000ff1d`
- name: `__la_write`
- size: `129`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005574`
- `0x1800b00a0`
- `0x1800bcab0`
- `0x1800bcc80`
- `0x1800c3254`
- `0x1800ee7d0`
- `0x1800f2f50`
- `0x1800f8170`
- `0x180106760`
- `0x180112644`

## callees

- `0x18000fe9c`
- `0x1800149c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fec1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fec1`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18000fed3`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18000fed3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fef0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fefa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fefa`

## pseudocode

```c
__int64 __fastcall _la_write(int a1, const void *a2, unsigned __int64 a3)
{
  DWORD v3; // ebx
  void *osfhandle; // rax
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v3 = -1;
  NumberOfBytesWritten = 0;
  if ( a3 <= 0xFFFFFFFF )
    v3 = a3;
  if ( a1 < 0 )
    goto LABEL_4;
  osfhandle = (void *)_get_osfhandle(a1);
  if ( !WriteFile(osfhandle, a2, v3, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 5 )
    {
      _la_dosmaperr(LastError);
      return -1;
    }
LABEL_4:
    *(_DWORD *)_o__errno() = 9;
    return -1;
  }
  return NumberOfBytesWritten;
}

```

## disassembly

```asm
0x18000fe9c  mov     [rsp+arg_8], rbx
0x18000fea1  push    rdi
0x18000fea2  sub     rsp, 30h
0x18000fea6  mov     ebx, 0FFFFFFFFh
0x18000feab  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18000feb3  cmp     r8, rbx
0x18000feb6  mov     rdi, rdx
0x18000feb9  cmovbe  rbx, r8
0x18000febd  test    ecx, ecx
0x18000febf  jns     short loc_18000FED3
0x18000fec1  call    cs:__imp__o__errno
0x18000fec7  mov     dword ptr [rax], 9
0x18000fecd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fed1  jmp     short loc_18000FF12
0x18000fed3  call    cs:__imp__get_osfhandle
0x18000fed9  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fede  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000fee7  mov     rcx, rax; hFile
0x18000feea  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000feed  mov     rdx, rdi; lpBuffer
0x18000fef0  call    cs:__imp_WriteFile
0x18000fef6  test    eax, eax
0x18000fef8  jnz     short loc_18000FF0E
0x18000fefa  call    cs:__imp_GetLastError
0x18000ff00  cmp     eax, 5
0x18000ff03  jz      short loc_18000FEC1
0x18000ff05  mov     ecx, eax
0x18000ff07  call    __la_dosmaperr
0x18000ff0c  jmp     short loc_18000FECD
0x18000ff0e  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18000ff12  mov     rbx, [rsp+38h+arg_8]
0x18000ff17  add     rsp, 30h
0x18000ff1b  pop     rdi
0x18000ff1c  retn
```
