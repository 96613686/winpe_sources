# VwriteBUDFile

- ea: `0x1800728c8`
- end: `0x180072a0d`
- name: `VwriteBUDFile`
- size: `325`
- prototype: `wchar_t *__fastcall(const wchar_t *, const void *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180048148`

## callees

- `0x18000881c`
- `0x180049d00`
- `0x1800728c8`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180072935`
- `KERNEL32!DeleteFileW` at `0x1800729d1`
- `KERNEL32!DeleteFileW` at `0x180072935`
- `KERNEL32!DeleteFileW` at `0x1800729d1`
- `KERNEL32!GetFileAttributesExW` at `0x180072922`
- `KERNEL32!GetFileAttributesExW` at `0x180072922`
- `KERNEL32!WriteFile` at `0x18007299c`
- `KERNEL32!WriteFile` at `0x18007299c`
- `KERNEL32!CloseHandle` at `0x1800729be`
- `KERNEL32!CloseHandle` at `0x1800729be`
- `KERNEL32!CreateFileW` at `0x180072970`
- `KERNEL32!CreateFileW` at `0x180072970`
- `KERNEL32!LocalFree` at `0x1800729e0`
- `KERNEL32!LocalFree` at `0x1800729e0`

## pseudocode

```c
wchar_t *__fastcall VwriteBUDFile(const wchar_t *a1, const void *a2, DWORD a3)
{
  wchar_t *result; // rax
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
  result = pwstrGenerateGPDfilename(a1);
  v6 = result;
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
    return (wchar_t *)LocalFree(v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800728c8  mov     [rsp+arg_18], rbx
0x1800728cd  push    rbp
0x1800728ce  push    rsi
0x1800728cf  push    rdi
0x1800728d0  sub     rsp, 80h
0x1800728d7  mov     rax, cs:__security_cookie
0x1800728de  xor     rax, rsp
0x1800728e1  mov     [rsp+98h+var_28], rax
0x1800728e6  xorps   xmm0, xmm0
0x1800728e9  mov     [rsp+98h+NumberOfBytesWritten], 0
0x1800728f1  xor     eax, eax
0x1800728f3  mov     edi, r8d
0x1800728f6  movups  [rsp+98h+FileInformation], xmm0
0x1800728fb  mov     [rsp+98h+var_30], eax
0x1800728ff  mov     rbp, rdx
0x180072902  movups  [rsp+98h+var_40], xmm0
0x180072907  call    pwstrGenerateGPDfilename
0x18007290c  mov     rbx, rax
0x18007290f  test    rax, rax
0x180072912  jz      loc_1800729EC
0x180072918  lea     r8, [rsp+98h+FileInformation]; lpFileInformation
0x18007291d  xor     edx, edx; fInfoLevelId
0x18007291f  mov     rcx, rax; lpFileName
0x180072922  call    cs:__imp_GetFileAttributesExW
0x180072929  nop     dword ptr [rax+rax+00h]
0x18007292e  test    eax, eax
0x180072930  jz      short loc_180072949
0x180072932  mov     rcx, rbx; lpFileName
0x180072935  call    cs:__imp_DeleteFileW
0x18007293c  nop     dword ptr [rax+rax+00h]
0x180072941  test    eax, eax
0x180072943  jz      loc_1800729DD
0x180072949  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180072952  xor     r9d, r9d; lpSecurityAttributes
0x180072955  mov     [rsp+98h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x18007295d  xor     r8d, r8d; dwShareMode
0x180072960  mov     edx, 40000000h; dwDesiredAccess
0x180072965  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x18007296d  mov     rcx, rbx; lpFileName
0x180072970  call    cs:__imp_CreateFileW
0x180072977  nop     dword ptr [rax+rax+00h]
0x18007297c  mov     rsi, rax
0x18007297f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072983  jz      short loc_1800729DD
0x180072985  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007298a  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; lpOverlapped
0x180072993  mov     r8d, edi; nNumberOfBytesToWrite
0x180072996  mov     rdx, rbp; lpBuffer
0x180072999  mov     rcx, rax; hFile
0x18007299c  call    cs:__imp_WriteFile
0x1800729a3  nop     dword ptr [rax+rax+00h]
0x1800729a8  test    eax, eax
0x1800729aa  jz      short loc_1800729B9
0x1800729ac  cmp     [rsp+98h+NumberOfBytesWritten], edi
0x1800729b0  jnz     short loc_1800729B9
0x1800729b2  mov     edi, 1
0x1800729b7  jmp     short loc_1800729BB
0x1800729b9  xor     edi, edi
0x1800729bb  mov     rcx, rsi; hObject
0x1800729be  call    cs:__imp_CloseHandle
0x1800729c5  nop     dword ptr [rax+rax+00h]
0x1800729ca  test    edi, edi
0x1800729cc  jnz     short loc_1800729DD
0x1800729ce  mov     rcx, rbx; lpFileName
0x1800729d1  call    cs:__imp_DeleteFileW
0x1800729d8  nop     dword ptr [rax+rax+00h]
0x1800729dd  mov     rcx, rbx; hMem
0x1800729e0  call    cs:__imp_LocalFree
0x1800729e7  nop     dword ptr [rax+rax+00h]
0x1800729ec  mov     rcx, [rsp+98h+var_28]
0x1800729f1  xor     rcx, rsp; StackCookie
0x1800729f4  call    __security_check_cookie
0x1800729f9  mov     rbx, [rsp+98h+arg_18]
0x180072a01  add     rsp, 80h
0x180072a08  pop     rdi
0x180072a09  pop     rsi
0x180072a0a  pop     rbp
0x180072a0b  retn
```
