# WaasMedic::CWERReporter::RegisterFilesToWERReport(void)

- ea: `0x18002c670`
- end: `0x18002c83d`
- name: `?RegisterFilesToWERReport@CWERReporter@WaasMedic@@SAJXZ`
- size: `461`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180067bb0`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000c638`
- `0x18002c670`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c768`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c77e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c768`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c6c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c6bf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c6bf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c7df`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c7df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002c819`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002c819`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c753`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c753`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x18002c7cb`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x18002c7cb`

## string_xrefs

- `0x18002c708`: `Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x`
- `0x18002c6de`: `Failed to expand log file share path %s! hr = 0x%08x`
- `0x18002c73e`: `Failed to create enumeration search filter for %s! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 WaasMedic::CWERReporter::RegisterFilesToWERReport(void)
{
  DWORD v0; // eax
  signed int LastError; // eax
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // rdx
  int v4; // eax
  HANDLE FirstFileW; // rsi
  int v6; // eax
  HRESULT v7; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR pwzFile[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v0 = ExpandEnvironmentStringsW(L"%WINDIR%\\Logs\\waasmedic", Dst, 0x104u);
  if ( !v0 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v3 = L"Failed to expand log file share path %s! hr = 0x%08x";
    goto LABEL_5;
  }
  if ( v0 > 0x104 )
  {
    v2 = -2147024774;
    v3 = L"Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x";
LABEL_5:
    LogLevelW(2u, v3, L"%WINDIR%\\Logs\\waasmedic", v2);
    return v2;
  }
  v4 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", Dst);
  v2 = v4;
  if ( v4 < 0 )
  {
    LogLevelW(2u, L"Failed to create enumeration search filter for %s! hr = 0x%08x", Dst, (unsigned int)v4);
    return v2;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  while ( 1 )
  {
    if ( !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
      || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..") )
    {
      goto LABEL_16;
    }
    v6 = StringCchPrintfW(pwzFile, 0x104u, L"%s\\%s", Dst, FindFileData.cFileName);
    v2 = v6;
    if ( v6 < 0 )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v7 = WerRegisterFile(pwzFile, WerRegFileTypeOther, 2u);
      v2 = v7;
      if ( v7 < 0 )
      {
        LogLevelW(
          2u,
          L"Failed to register files to WER report for file %s! hr = 0x%08x",
          FindFileData.cFileName,
          (unsigned int)v7);
        goto LABEL_20;
      }
    }
LABEL_16:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_20;
  }
  LogLevelW(2u, L"Failed to print format string for file %s! hr = 0x%08x", FindFileData.cFileName, (unsigned int)v6);
LABEL_20:
  if ( FirstFileW )
    FindClose(FirstFileW);
  return v2;
}

```

## disassembly

```asm
0x18002c670  push    rbp
0x18002c672  push    rbx
0x18002c673  push    rsi
0x18002c674  push    r14
0x18002c676  lea     rbp, [rsp-7C8h]
0x18002c67e  sub     rsp, 8C8h
0x18002c685  mov     rax, cs:__security_cookie
0x18002c68c  xor     rax, rsp
0x18002c68f  mov     [rbp+7E0h+var_30], rax
0x18002c696  xor     edx, edx; Val
0x18002c698  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x18002c69d  mov     r8d, 250h; Size
0x18002c6a3  call    memset_0
0x18002c6a8  mov     r14d, 104h
0x18002c6ae  lea     rdx, [rbp+7E0h+Dst]; lpDst
0x18002c6b5  mov     r8d, r14d; nSize
0x18002c6b8  lea     rcx, Src; "%WINDIR%\\Logs\\waasmedic"
0x18002c6bf  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c6c5  test    eax, eax
0x18002c6c7  jnz     short loc_18002C6FE
0x18002c6c9  call    cs:__imp_GetLastError
0x18002c6cf  mov     ebx, eax
0x18002c6d1  test    eax, eax
0x18002c6d3  jle     short loc_18002C6DE
0x18002c6d5  movzx   ebx, ax
0x18002c6d8  or      ebx, 80070000h
0x18002c6de  lea     rdx, aFailedToExpand_1; "Failed to expand log file share path %s"...
0x18002c6e5  lea     r8, Src; "%WINDIR%\\Logs\\waasmedic"
0x18002c6ec  mov     r9d, ebx
0x18002c6ef  mov     ecx, 2; unsigned __int8
0x18002c6f4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c6f9  jmp     loc_18002C81F
0x18002c6fe  cmp     eax, r14d
0x18002c701  jbe     short loc_18002C711
0x18002c703  mov     ebx, 8007007Ah
0x18002c708  lea     rdx, aFailedToExpand_2; "Failed to expand log file share path %s"...
0x18002c70f  jmp     short loc_18002C6E5
0x18002c711  lea     r9, [rbp+7E0h+Dst]
0x18002c718  mov     rdx, r14; unsigned __int64
0x18002c71b  lea     r8, aS; "%s\\*.*"
0x18002c722  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x18002c729  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c72e  mov     ebx, eax
0x18002c730  test    eax, eax
0x18002c732  jns     short loc_18002C747
0x18002c734  mov     r9d, eax
0x18002c737  lea     r8, [rbp+7E0h+Dst]
0x18002c73e  lea     rdx, aFailedToCreate_11; "Failed to create enumeration search fil"...
0x18002c745  jmp     short loc_18002C6EF
0x18002c747  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18002c74c  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x18002c753  call    cs:__imp_FindFirstFileW
0x18002c759  mov     rsi, rax
0x18002c75c  lea     rdx, asc_18008063C; "."
0x18002c763  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x18002c768  call    cs:__imp__o__wcsicmp
0x18002c76e  test    eax, eax
0x18002c770  jz      short loc_18002C7D7
0x18002c772  lea     rdx, asc_18007E6B0; ".."
0x18002c779  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x18002c77e  call    cs:__imp__o__wcsicmp
0x18002c784  test    eax, eax
0x18002c786  jz      short loc_18002C7D7
0x18002c788  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x18002c78d  mov     rdx, r14; unsigned __int64
0x18002c790  lea     r9, [rbp+7E0h+Dst]
0x18002c797  mov     [rsp+8E0h+var_8C0], rax
0x18002c79c  lea     r8, aSS; "%s\\%s"
0x18002c7a3  lea     rcx, [rbp+7E0h+pwzFile]; unsigned __int16 *
0x18002c7aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c7af  mov     ebx, eax
0x18002c7b1  test    eax, eax
0x18002c7b3  js      short loc_18002C7F8
0x18002c7b5  test    byte ptr [rsp+8E0h+FindFileData.dwFileAttributes], 10h
0x18002c7ba  jnz     short loc_18002C7D7
0x18002c7bc  mov     edx, 2; regFileType
0x18002c7c1  lea     rcx, [rbp+7E0h+pwzFile]; pwzFile
0x18002c7c8  mov     r8d, edx; dwFlags
0x18002c7cb  call    cs:__imp_WerRegisterFile
0x18002c7d1  mov     ebx, eax
0x18002c7d3  test    eax, eax
0x18002c7d5  js      short loc_18002C7EF
0x18002c7d7  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18002c7dc  mov     rcx, rsi; hFindFile
0x18002c7df  call    cs:__imp_FindNextFileW
0x18002c7e5  test    eax, eax
0x18002c7e7  jnz     loc_18002C75C
0x18002c7ed  jmp     short loc_18002C811
0x18002c7ef  lea     rdx, aFailedToRegist_3; "Failed to register files to WER report "...
0x18002c7f6  jmp     short loc_18002C7FF
0x18002c7f8  lea     rdx, aFailedToPrintF; "Failed to print format string for file "...
0x18002c7ff  mov     r9d, eax
0x18002c802  lea     r8, [rsp+8E0h+FindFileData.cFileName]
0x18002c807  mov     ecx, 2; unsigned __int8
0x18002c80c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c811  test    rsi, rsi
0x18002c814  jz      short loc_18002C81F
0x18002c816  mov     rcx, rsi; hFindFile
0x18002c819  call    cs:__imp_FindClose
0x18002c81f  mov     eax, ebx
0x18002c821  mov     rcx, [rbp+7E0h+var_30]
0x18002c828  xor     rcx, rsp; StackCookie
0x18002c82b  call    __security_check_cookie
0x18002c830  add     rsp, 8C8h
0x18002c837  pop     r14
0x18002c839  pop     rsi
0x18002c83a  pop     rbx
0x18002c83b  pop     rbp
0x18002c83c  retn
```
