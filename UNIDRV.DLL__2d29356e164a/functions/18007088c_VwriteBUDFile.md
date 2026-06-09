# VwriteBUDFile

- ea: `0x18007088c`
- end: `0x1800709a2`
- name: `VwriteBUDFile`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180046d30`

## callees

- `0x1800088ac`
- `0x1800487e0`
- `0x18007088c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800708f3`
- `KERNEL32!DeleteFileW` at `0x180070973`
- `KERNEL32!DeleteFileW` at `0x1800708f3`
- `KERNEL32!DeleteFileW` at `0x180070973`
- `KERNEL32!GetFileAttributesExW` at `0x1800708e6`
- `KERNEL32!GetFileAttributesExW` at `0x1800708e6`
- `KERNEL32!WriteFile` at `0x18007094a`
- `KERNEL32!WriteFile` at `0x18007094a`
- `KERNEL32!CloseHandle` at `0x180070966`
- `KERNEL32!CloseHandle` at `0x180070966`
- `KERNEL32!CreateFileW` at `0x180070924`
- `KERNEL32!CreateFileW` at `0x180070924`
- `KERNEL32!LocalFree` at `0x18007097c`
- `KERNEL32!LocalFree` at `0x18007097c`

## pseudocode

```c
const WCHAR *__fastcall VwriteBUDFile(const wchar_t *a1, const void *a2, DWORD a3)
{
  const WCHAR *result; // rax
  WCHAR *v6; // rbx
  HANDLE FileW; // rax
  void *v8; // rsi
  BOOL v9; // edi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-58h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-50h] BYREF
  int v12; // [rsp+68h] [rbp-30h]

  NumberOfBytesWritten = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v12 = 0;
  result = (const WCHAR *)pwstrGenerateGPDfilename(a1);
  v6 = (WCHAR *)result;
  if ( result )
  {
    if ( !GetFileAttributesExW(result, GetFileExInfoStandard, FileInformation) || DeleteFileW(v6) )
    {
      FileW = CreateFileW(v6, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
      v8 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v9 = WriteFile(FileW, a2, a3, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == a3;
        CloseHandle(v8);
        if ( !v9 )
          DeleteFileW(v6);
      }
    }
    return (const WCHAR *)LocalFree(v6);
  }
  return result;
}

```

## disassembly

```asm
0x18007088c  mov     [rsp+arg_18], rbx
0x180070891  push    rbp
0x180070892  push    rsi
0x180070893  push    rdi
0x180070894  sub     rsp, 80h
0x18007089b  mov     rax, cs:__security_cookie
0x1800708a2  xor     rax, rsp
0x1800708a5  mov     [rsp+98h+var_28], rax
0x1800708aa  xorps   xmm0, xmm0
0x1800708ad  mov     [rsp+98h+NumberOfBytesWritten], 0
0x1800708b5  xor     eax, eax
0x1800708b7  mov     edi, r8d
0x1800708ba  movups  [rsp+98h+FileInformation], xmm0
0x1800708bf  mov     [rsp+98h+var_30], eax
0x1800708c3  mov     rbp, rdx
0x1800708c6  movups  [rsp+98h+var_40], xmm0
0x1800708cb  call    pwstrGenerateGPDfilename
0x1800708d0  mov     rbx, rax
0x1800708d3  test    rax, rax
0x1800708d6  jz      loc_180070982
0x1800708dc  lea     r8, [rsp+98h+FileInformation]; lpFileInformation
0x1800708e1  xor     edx, edx; fInfoLevelId
0x1800708e3  mov     rcx, rax; lpFileName
0x1800708e6  call    cs:__imp_GetFileAttributesExW
0x1800708ec  test    eax, eax
0x1800708ee  jz      short loc_1800708FD
0x1800708f0  mov     rcx, rbx; lpFileName
0x1800708f3  call    cs:__imp_DeleteFileW
0x1800708f9  test    eax, eax
0x1800708fb  jz      short loc_180070979
0x1800708fd  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180070906  xor     r9d, r9d; lpSecurityAttributes
0x180070909  mov     [rsp+98h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180070911  xor     r8d, r8d; dwShareMode
0x180070914  mov     edx, 40000000h; dwDesiredAccess
0x180070919  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x180070921  mov     rcx, rbx; lpFileName
0x180070924  call    cs:__imp_CreateFileW
0x18007092a  mov     rsi, rax
0x18007092d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070931  jz      short loc_180070979
0x180070933  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180070938  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; lpOverlapped
0x180070941  mov     r8d, edi; nNumberOfBytesToWrite
0x180070944  mov     rdx, rbp; lpBuffer
0x180070947  mov     rcx, rax; hFile
0x18007094a  call    cs:__imp_WriteFile
0x180070950  test    eax, eax
0x180070952  jz      short loc_180070961
0x180070954  cmp     [rsp+98h+NumberOfBytesWritten], edi
0x180070958  jnz     short loc_180070961
0x18007095a  mov     edi, 1
0x18007095f  jmp     short loc_180070963
0x180070961  xor     edi, edi
0x180070963  mov     rcx, rsi; hObject
0x180070966  call    cs:__imp_CloseHandle
0x18007096c  test    edi, edi
0x18007096e  jnz     short loc_180070979
0x180070970  mov     rcx, rbx; lpFileName
0x180070973  call    cs:__imp_DeleteFileW
0x180070979  mov     rcx, rbx; hMem
0x18007097c  call    cs:__imp_LocalFree
0x180070982  mov     rcx, [rsp+98h+var_28]
0x180070987  xor     rcx, rsp; StackCookie
0x18007098a  call    __security_check_cookie
0x18007098f  mov     rbx, [rsp+98h+arg_18]
0x180070997  add     rsp, 80h
0x18007099e  pop     rdi
0x18007099f  pop     rsi
0x1800709a0  pop     rbp
0x1800709a1  retn
```
