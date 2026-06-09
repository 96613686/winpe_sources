# WindowsPerformanceRecorder::Impl::TryAccessFileS(ushort const *,ulong)

- ea: `0x1800359f4`
- end: `0x180035a6e`
- name: `?TryAccessFileS@Impl@WindowsPerformanceRecorder@@YAJPEBGK@Z`
- size: `122`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003a1f0`
- `0x18005deb0`

## callees

- `0x1800359f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035a3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035a3d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800359fd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800359fd`

## pseudocode

```c
signed int __fastcall WindowsPerformanceRecorder::Impl::TryAccessFileS(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  DWORD v4; // edx
  DWORD dwFlagsAndAttributes; // eax
  HANDLE FileW; // rax
  signed int result; // eax

  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
  {
    v4 = 1073807360;
    dwFlagsAndAttributes = 0x4000000;
  }
  else
  {
    v4 = 0x40000000;
    dwFlagsAndAttributes = 0;
  }
  FileW = CreateFileW(lpFileName, v4, 0, 0, 4u, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    CloseHandle(FileW);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800359f4  push    rbx
0x1800359f6  sub     rsp, 40h
0x1800359fa  mov     rbx, rcx
0x1800359fd  call    cs:__imp_GetFileAttributesW
0x180035a03  cmp     eax, 0FFFFFFFFh
0x180035a06  jz      short loc_180035A15
0x180035a08  test    al, 10h
0x180035a0a  jnz     short loc_180035A15
0x180035a0c  mov     edx, 40000000h
0x180035a11  xor     eax, eax
0x180035a13  jmp     short loc_180035A1F
0x180035a15  mov     edx, 40010000h; dwDesiredAccess
0x180035a1a  mov     eax, 4000000h
0x180035a1f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180035a28  xor     r9d, r9d; lpSecurityAttributes
0x180035a2b  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180035a2f  xor     r8d, r8d; dwShareMode
0x180035a32  mov     rcx, rbx; lpFileName
0x180035a35  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x180035a3d  call    cs:__imp_CreateFileW
0x180035a43  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035a47  jnz     short loc_180035A5D
0x180035a49  call    cs:__imp_GetLastError
0x180035a4f  test    eax, eax
0x180035a51  jle     short loc_180035A68
0x180035a53  movzx   eax, ax
0x180035a56  or      eax, 80070000h
0x180035a5b  jmp     short loc_180035A68
0x180035a5d  mov     rcx, rax; hObject
0x180035a60  call    cs:__imp_CloseHandle
0x180035a66  xor     eax, eax
0x180035a68  add     rsp, 40h
0x180035a6c  pop     rbx
0x180035a6d  retn
```
