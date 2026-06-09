# CopyFileToRandomDir(char const *,ushort *,ushort * *)

- ea: `0x407d14`
- end: `0x407ea5`
- name: `?CopyFileToRandomDir@@YGJPBDPAGPAPAG@Z`
- size: `401`
- prototype: `int __userpurge@<eax>(const WCHAR *@<edx>, const CHAR *@<ecx>, char *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x40373b`

## callees

- `0x402df9`
- `0x4066c4`
- `0x406d31`
- `0x4074cf`
- `0x407d14`
- `0x408301`
- `0x40838e`
- `0x40cb60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x407e8c`
- `KERNEL32!CloseHandle` at `0x407e8c`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x407e19`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x407e19`
- `KERNEL32!MultiByteToWideChar` at `0x407da8`
- `KERNEL32!MultiByteToWideChar` at `0x407da8`
- `KERNEL32!CreateFileW` at `0x407d5b`
- `KERNEL32!CreateFileW` at `0x407d5b`
- `KERNEL32!CopyFileW` at `0x407e3e`
- `KERNEL32!CopyFileW` at `0x407e3e`
- `ole32!CoImpersonateClient` at `0x407d3a`
- `ole32!CoImpersonateClient` at `0x407d3a`
- `ole32!CoRevertToSelf` at `0x407d63`
- `ole32!CoRevertToSelf` at `0x407d63`
- `OLEAUT32!__imp__SysAllocString@4` at `0x407e6c`
- `OLEAUT32!__imp__SysAllocString@4` at `0x407e6c`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407e5f`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407e5f`

## pseudocode

```c
int __userpurge CopyFileToRandomDir@<eax>(
        const WCHAR *a1@<edx>,
        const CHAR *a2@<ecx>,
        char *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int FileW; // esi
  int ErrorError; // edi
  DWORD FinalPathNameByHandleW; // eax
  const unsigned __int16 *v10; // [esp+0h] [ebp-640h]
  const unsigned __int16 *v11; // [esp+0h] [ebp-640h]
  int v12; // [esp+4h] [ebp-63Ch]
  unsigned __int16 *FileNameFromPath; // [esp+Ch] [ebp-634h]
  WCHAR szFilePath[268]; // [esp+14h] [ebp-62Ch] BYREF
  WCHAR WideCharStr[260]; // [esp+22Ch] [ebp-414h] BYREF
  WCHAR NewFileName[260]; // [esp+434h] [ebp-20Ch] BYREF

  FileW = -1;
  if ( CoImpersonateClient() < 0
    || (FileW = (int)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0), CoRevertToSelf(), FileW == -1)
    || !FileW
    || (FileNameFromPath = FindFileNameFromPath(v10), FileNameFromPath == a1) )
  {
    ErrorError = -2147467259;
    goto LABEL_17;
  }
  if ( !MultiByteToWideChar(0, 8u, a2, -1, WideCharStr, 260) )
    goto LABEL_6;
  ErrorError = StringCchPrintfW(NewFileName, 0x104u, (wchar_t *)L"%s\\%s.dat", WideCharStr, FileNameFromPath);
  if ( ErrorError < 0 )
    goto LABEL_17;
  ErrorError = AxiPreScanPathW(NewFileName);
  if ( ErrorError < 0 )
  {
LABEL_19:
    CloseHandle((HANDLE)FileW);
    return ErrorError;
  }
  AxiAdjustSlashToBackslashW((__int16 *)NewFileName);
  FinalPathNameByHandleW = GetFinalPathNameByHandleW((HANDLE)FileW, szFilePath, 0x10Cu, 0);
  if ( FinalPathNameByHandleW == 3 || FinalPathNameByHandleW == 8 || FinalPathNameByHandleW == 87 )
  {
    ErrorError = -2147467259;
    goto LABEL_19;
  }
  if ( CopyFileW(szFilePath, NewFileName, 1) )
  {
    ErrorError = SetFileIntegrityLevelByNameW(v11, v12);
    if ( ErrorError >= 0 )
    {
      SysFreeString(*(BSTR *)a3);
      *(_DWORD *)a3 = SysAllocString(NewFileName);
    }
    goto LABEL_19;
  }
LABEL_6:
  ErrorError = HRESULTFromLastErrorError();
LABEL_17:
  if ( FileW != -1 && FileW )
    goto LABEL_19;
  return ErrorError;
}

```

## disassembly

```asm
0x407d14  mov     edi, edi
0x407d16  push    ebp
0x407d17  mov     ebp, esp
0x407d19  sub     esp, 634h
0x407d1f  mov     eax, ___security_cookie
0x407d24  xor     eax, ebp
0x407d26  mov     [ebp+var_4], eax
0x407d29  push    ebx
0x407d2a  mov     ebx, [ebp+arg_0]
0x407d2d  push    esi; int
0x407d2e  push    edi; unsigned __int16 *
0x407d2f  mov     edi, edx
0x407d31  mov     [ebp+lpMultiByteStr], ecx
0x407d37  or      esi, 0FFFFFFFFh
0x407d3a  call    ds:__imp__CoImpersonateClient@0; CoImpersonateClient()
0x407d40  test    eax, eax
0x407d42  js      loc_407E7D
0x407d48  push    0; hTemplateFile
0x407d4a  push    80h; dwFlagsAndAttributes
0x407d4f  push    3; dwCreationDisposition
0x407d51  push    0; lpSecurityAttributes
0x407d53  push    1; dwShareMode
0x407d55  push    80000000h; dwDesiredAccess
0x407d5a  push    edi; lpFileName
0x407d5b  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x407d61  mov     esi, eax
0x407d63  call    ds:__imp__CoRevertToSelf@0; CoRevertToSelf()
0x407d69  cmp     esi, 0FFFFFFFFh
0x407d6c  jz      loc_407E7D
0x407d72  test    esi, esi
0x407d74  jz      loc_407E7D
0x407d7a  mov     ecx, edi
0x407d7c  call    ?FindFileNameFromPath@@YGPAGPBG@Z; FindFileNameFromPath(ushort const *)
0x407d81  mov     [ebp+var_634], eax
0x407d87  cmp     eax, edi
0x407d89  jz      loc_407E7D
0x407d8f  mov     edi, 104h
0x407d94  lea     eax, [ebp+WideCharStr]
0x407d9a  push    edi; cchWideChar
0x407d9b  push    eax; lpWideCharStr
0x407d9c  push    0FFFFFFFFh; cbMultiByte
0x407d9e  push    [ebp+lpMultiByteStr]; lpMultiByteStr
0x407da4  push    8; dwFlags
0x407da6  push    0; CodePage
0x407da8  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x407dae  test    eax, eax
0x407db0  jnz     short loc_407DBE
0x407db2  call    ?HRESULTFromLastErrorError@@YGJXZ; HRESULTFromLastErrorError(void)
0x407db7  mov     edi, eax
0x407db9  jmp     loc_407E82
0x407dbe  push    [ebp+var_634]
0x407dc4  lea     eax, [ebp+WideCharStr]
0x407dca  push    eax
0x407dcb  push    offset aSSDat; "%s\\%s.dat"
0x407dd0  lea     eax, [ebp+NewFileName]
0x407dd6  push    edi; unsigned int
0x407dd7  push    eax; Buffer
0x407dd8  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x407ddd  mov     edi, eax
0x407ddf  add     esp, 14h
0x407de2  test    edi, edi
0x407de4  js      loc_407E82
0x407dea  lea     ecx, [ebp+NewFileName]
0x407df0  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x407df5  mov     edi, eax
0x407df7  test    edi, edi
0x407df9  js      loc_407E8B
0x407dff  lea     ecx, [ebp+NewFileName]
0x407e05  call    ?AxiAdjustSlashToBackslashW@@YGXPAG@Z; AxiAdjustSlashToBackslashW(ushort *)
0x407e0a  push    0; dwFlags
0x407e0c  push    10Ch; cchFilePath
0x407e11  lea     eax, [ebp+szFilePath]
0x407e17  push    eax; lpszFilePath
0x407e18  push    esi; hFile
0x407e19  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x407e1f  cmp     eax, 3
0x407e22  jz      short loc_407E76
0x407e24  cmp     eax, 8
0x407e27  jz      short loc_407E76
0x407e29  cmp     eax, 57h ; 'W'
0x407e2c  jz      short loc_407E76
0x407e2e  push    1; bFailIfExists
0x407e30  lea     eax, [ebp+NewFileName]
0x407e36  push    eax; lpNewFileName
0x407e37  lea     eax, [ebp+szFilePath]
0x407e3d  push    eax; lpExistingFileName
0x407e3e  call    ds:__imp__CopyFileW@12; CopyFileW(x,x,x)
0x407e44  test    eax, eax
0x407e46  jz      loc_407DB2
0x407e4c  lea     ecx, [ebp+NewFileName]
0x407e52  call    ?SetFileIntegrityLevelByNameW@@YGJPBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x407e57  mov     edi, eax
0x407e59  test    edi, edi
0x407e5b  js      short loc_407E8B
0x407e5d  push    dword ptr [ebx]; bstrString
0x407e5f  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x407e65  lea     eax, [ebp+NewFileName]
0x407e6b  push    eax; psz
0x407e6c  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x407e72  mov     [ebx], eax
0x407e74  jmp     short loc_407E8B
0x407e76  mov     edi, 80004005h
0x407e7b  jmp     short loc_407E8B
0x407e7d  mov     edi, 80004005h
0x407e82  cmp     esi, 0FFFFFFFFh
0x407e85  jz      short loc_407E92
0x407e87  test    esi, esi
0x407e89  jz      short loc_407E92
0x407e8b  push    esi; hObject
0x407e8c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x407e92  mov     ecx, [ebp+var_4]
0x407e95  mov     eax, edi
0x407e97  pop     edi
0x407e98  pop     esi
0x407e99  xor     ecx, ebp; StackCookie
0x407e9b  pop     ebx
0x407e9c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407ea1  leave
0x407ea2  retn    4
```
