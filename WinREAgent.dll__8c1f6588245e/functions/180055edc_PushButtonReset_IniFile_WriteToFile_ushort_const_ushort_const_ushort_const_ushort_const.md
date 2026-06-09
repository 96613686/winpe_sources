# PushButtonReset::IniFile::WriteToFile(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180055edc`
- end: `0x180055fea`
- name: `?WriteToFile@IniFile@PushButtonReset@@SAJPEBG000@Z`
- size: `270`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032480`

## callees

- `0x18003717c`
- `0x180037344`
- `0x180055edc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180055fbd`
- `KERNEL32!CloseHandle` at `0x180055fbd`
- `KERNEL32!GetLastError` at `0x180055efb`
- `KERNEL32!GetLastError` at `0x180055f4f`
- `KERNEL32!GetLastError` at `0x180055fc5`
- `KERNEL32!GetLastError` at `0x180055efb`
- `KERNEL32!GetLastError` at `0x180055f4f`
- `KERNEL32!GetLastError` at `0x180055fc5`
- `KERNEL32!CreateFileW` at `0x180055fa2`
- `KERNEL32!CreateFileW` at `0x180055fa2`
- `KERNEL32!WritePrivateProfileStringW` at `0x180055ef1`
- `KERNEL32!WritePrivateProfileStringW` at `0x180055f71`
- `KERNEL32!WritePrivateProfileStringW` at `0x180055ef1`
- `KERNEL32!WritePrivateProfileStringW` at `0x180055f71`
- `KERNEL32!FlushFileBuffers` at `0x180055fb4`
- `KERNEL32!FlushFileBuffers` at `0x180055fb4`

## string_xrefs

- `0x180055f12`: `Failed to write [%s].[%s]=[%s] in [%s]`
- `0x180055f2a`: `PushButtonReset::IniFile::WriteToFile`
- `0x180055fce`: `Failed to open for flush file %s. Error: 0x%08X`

## pseudocode

```c
int __fastcall PushButtonReset::IniFile::WriteToFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int v8; // eax
  int result; // eax
  HANDLE FileW; // rax
  void *v11; // rbx
  DWORD LastError; // eax

  if ( WritePrivateProfileStringW(a1, a2, a3, a4) )
  {
    WritePrivateProfileStringW(0, 0, 0, 0);
    FileW = CreateFileW(a4, 0x40000000u, 1u, 0, 4u, 0x80000000, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      PushButtonReset::Logging::Trace(1, L"Failed to open for flush file %s. Error: 0x%08X", a4, LastError);
    }
    else
    {
      FlushFileBuffers(FileW);
      CloseHandle(v11);
    }
    return 0;
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v8,
      "PushButtonReset::IniFile::WriteToFile",
      "base\\reset\\util\\src\\ini.cpp",
      233,
      L"Failed to write [%s].[%s]=[%s] in [%s]",
      a1,
      a2,
      a3,
      a4);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180055edc  push    rbx
0x180055ede  push    rbp
0x180055edf  push    rsi
0x180055ee0  push    rdi
0x180055ee1  sub     rsp, 58h
0x180055ee5  mov     rdi, r9
0x180055ee8  mov     rbx, r8
0x180055eeb  mov     rsi, rdx
0x180055eee  mov     rbp, rcx
0x180055ef1  call    cs:__imp_WritePrivateProfileStringW
0x180055ef7  test    eax, eax
0x180055ef9  jnz     short loc_180055F67
0x180055efb  call    cs:__imp_GetLastError
0x180055f01  test    eax, eax
0x180055f03  jle     short loc_180055F0D
0x180055f05  movzx   eax, ax
0x180055f08  or      eax, 80070000h
0x180055f0d  mov     [rsp+78h+var_30], rdi
0x180055f12  lea     rcx, aFailedToWriteS_2; "Failed to write [%s].[%s]=[%s] in [%s]"
0x180055f19  mov     [rsp+78h+var_38], rbx
0x180055f1e  lea     r9, aBaseResetUtilS; "base\\reset\\util\\src\\ini.cpp"
0x180055f25  mov     [rsp+78h+var_40], rsi
0x180055f2a  lea     r8, aPushbuttonrese_113; "PushButtonReset::IniFile::WriteToFile"
0x180055f31  mov     [rsp+78h+hTemplateFile], rbp
0x180055f36  mov     edx, eax
0x180055f38  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rcx
0x180055f3d  mov     ecx, 2
0x180055f42  mov     [rsp+78h+dwCreationDisposition], 0E9h
0x180055f4a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180055f4f  call    cs:__imp_GetLastError
0x180055f55  test    eax, eax
0x180055f57  jle     loc_180055FE1
0x180055f5d  movzx   eax, ax
0x180055f60  or      eax, 80070000h
0x180055f65  jmp     short loc_180055FE1
0x180055f67  xor     r9d, r9d; lpFileName
0x180055f6a  xor     r8d, r8d; lpString
0x180055f6d  xor     edx, edx; lpKeyName
0x180055f6f  xor     ecx, ecx; lpAppName
0x180055f71  call    cs:__imp_WritePrivateProfileStringW
0x180055f77  xor     r9d, r9d; lpSecurityAttributes
0x180055f7a  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180055f83  mov     [rsp+78h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x180055f8b  mov     edx, 40000000h; dwDesiredAccess
0x180055f90  mov     rcx, rdi; lpFileName
0x180055f93  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x180055f9b  lea     esi, [r9+1]
0x180055f9f  mov     r8d, esi; dwShareMode
0x180055fa2  call    cs:__imp_CreateFileW
0x180055fa8  mov     rbx, rax
0x180055fab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055faf  jz      short loc_180055FC5
0x180055fb1  mov     rcx, rax; hFile
0x180055fb4  call    cs:__imp_FlushFileBuffers
0x180055fba  mov     rcx, rbx; hObject
0x180055fbd  call    cs:__imp_CloseHandle
0x180055fc3  jmp     short loc_180055FDF
0x180055fc5  call    cs:__imp_GetLastError
0x180055fcb  mov     r8, rdi
0x180055fce  lea     rdx, aFailedToOpenFo; "Failed to open for flush file %s. Error"...
0x180055fd5  mov     r9d, eax
0x180055fd8  mov     ecx, esi
0x180055fda  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180055fdf  xor     eax, eax
0x180055fe1  add     rsp, 58h
0x180055fe5  pop     rdi
0x180055fe6  pop     rsi
0x180055fe7  pop     rbp
0x180055fe8  pop     rbx
0x180055fe9  retn
```
