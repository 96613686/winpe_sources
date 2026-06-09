# WaasMedic::CbsUtil::IsSubSequentLCUFailed(ulong,bool &)

- ea: `0x180059a50`
- end: `0x180059c19`
- name: `?IsSubSequentLCUFailed@CbsUtil@WaasMedic@@SAJKAEA_N@Z`
- size: `457`
- prototype: `__int64 __fastcall(unsigned int, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042e10`
- `0x180043f40`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x18002c284`
- `0x180059a50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059aa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059aa5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180059b84`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180059b84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059ad3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059ad3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059a9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059b1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059a9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059b1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c06`

## string_xrefs

- `0x180059a78`: `IsSubSequentLCUFailed: ConfiguredSubSequentFailureCount:%d`
- `0x180059bb1`: `Found %d LCU error package keys entries, configured subsequent error count %d.`
- `0x180059ac5`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrorPackageNames`
- `0x180059be5`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrorPackageNames`

## pseudocode

```c
__int64 __fastcall WaasMedic::CbsUtil::IsSubSequentLCUFailed(DWORD a1, bool *a2)
{
  HKEY v4; // rdi
  DWORD LastError; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int v9; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD cValues; // [rsp+98h] [rbp+38h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  cbMaxValueNameLen = 0;
  hKey = 0;
  LogLevelW(4u, L"IsSubSequentLCUFailed: ConfiguredSubSequentFailureCount:%d", a1);
  v4 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\LCUInstallErrorPackageNames",
         0,
         1u,
         &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 + 2147024894 <= 1 )
  {
    LogLevelW(
      4u,
      L"The key %s was not found, condition is not applicable.",
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\LCUInstallErrorPackageNames");
  }
  else
  {
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
        (const char *)v7,
        phkResult);
LABEL_8:
      if ( hKey )
        RegCloseKey(hKey);
      return v7;
    }
    cValues = 0;
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( v9 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x158,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
             (const char *)v9,
             phkResulta);
      goto LABEL_8;
    }
    LogLevelW(4u, L"Found %d LCU error package keys entries, configured subsequent error count %d.", cValues, a1);
    if ( cValues >= a1 )
    {
      *a2 = 1;
      LogLevelW(4u, L"Condition was detected, found %d LCU error package keys entries.");
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180059a50  push    rbp
0x180059a52  push    rbx
0x180059a53  push    rsi
0x180059a54  push    rdi
0x180059a55  push    r14
0x180059a57  mov     rbp, rsp
0x180059a5a  sub     rsp, 60h
0x180059a5e  mov     r14, rdx
0x180059a61  mov     byte ptr [rdx], 0
0x180059a64  mov     esi, ecx
0x180059a66  mov     [rbp+cbMaxValueNameLen], 0
0x180059a6d  mov     r8d, ecx
0x180059a70  mov     [rbp+hKey], 0
0x180059a78  lea     rdx, aIssubsequentlc; "IsSubSequentLCUFailed: ConfiguredSubSeq"...
0x180059a7f  mov     ecx, 4; unsigned __int8
0x180059a84  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180059a89  mov     rdi, [rbp+hKey]
0x180059a8d  test    rdi, rdi
0x180059a90  jz      short loc_180059AAB
0x180059a92  call    cs:__imp_GetLastError
0x180059a98  mov     rcx, rdi; hKey
0x180059a9b  mov     ebx, eax
0x180059a9d  call    cs:__imp_RegCloseKey
0x180059aa3  mov     ecx, ebx; dwErrCode
0x180059aa5  call    cs:__imp_SetLastError
0x180059aab  lea     rax, [rbp+hKey]
0x180059aaf  mov     [rbp+hKey], 0
0x180059ab7  mov     r9d, 1; samDesired
0x180059abd  mov     [rsp+60h+phkResult], rax; int
0x180059ac2  xor     r8d, r8d; ulOptions
0x180059ac5  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180059acc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059ad3  call    cs:__imp_RegOpenKeyExW
0x180059ad9  mov     ebx, eax
0x180059adb  test    eax, eax
0x180059add  jle     short loc_180059AE8
0x180059adf  movzx   ebx, ax
0x180059ae2  or      ebx, 80070000h
0x180059ae8  lea     eax, [rbx+7FF8FFFEh]
0x180059aee  cmp     eax, 1
0x180059af1  jbe     loc_180059BE5
0x180059af7  test    ebx, ebx
0x180059af9  jns     short loc_180059B29
0x180059afb  mov     rcx, [rbp+28h]; this
0x180059aff  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180059b06  mov     r9d, ebx; char *
0x180059b09  mov     edx, 14Ah; void *
0x180059b0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059b13  mov     rcx, [rbp+hKey]; hKey
0x180059b17  test    rcx, rcx
0x180059b1a  jz      short loc_180059B22
0x180059b1c  call    cs:__imp_RegCloseKey
0x180059b22  mov     eax, ebx
0x180059b24  jmp     loc_180059C0E
0x180059b29  mov     rcx, [rbp+hKey]; hKey
0x180059b2d  lea     rax, [rbp+cbMaxValueNameLen]
0x180059b31  mov     [rsp+60h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180059b3a  xor     r9d, r9d; lpReserved
0x180059b3d  mov     [rsp+60h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180059b46  xor     r8d, r8d; lpcchClass
0x180059b49  mov     [rsp+60h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180059b52  xor     edx, edx; lpClass
0x180059b54  mov     [rsp+60h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180059b59  lea     rax, [rbp+cValues]
0x180059b5d  mov     [rsp+60h+lpcValues], rax; lpcValues
0x180059b62  mov     [rsp+60h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180059b6b  mov     [rsp+60h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180059b74  mov     [rsp+60h+phkResult], 0; unsigned int
0x180059b7d  mov     [rbp+cValues], 0
0x180059b84  call    cs:__imp_RegQueryInfoKeyW
0x180059b8a  test    eax, eax
0x180059b8c  jz      short loc_180059BAD
0x180059b8e  mov     rcx, [rbp+28h]; this
0x180059b92  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180059b99  mov     r9d, eax; char *
0x180059b9c  mov     edx, 158h; void *
0x180059ba1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180059ba6  mov     ebx, eax
0x180059ba8  jmp     loc_180059B13
0x180059bad  mov     r8d, [rbp+cValues]
0x180059bb1  lea     rdx, aFoundDLcuError_0; "Found %d LCU error package keys entries"...
0x180059bb8  mov     r9d, esi
0x180059bbb  mov     ecx, 4; unsigned __int8
0x180059bc0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180059bc5  mov     r8d, [rbp+cValues]
0x180059bc9  cmp     r8d, esi
0x180059bcc  jb      short loc_180059BFD
0x180059bce  lea     rdx, aConditionWasDe_0; "Condition was detected, found %d LCU er"...
0x180059bd5  mov     byte ptr [r14], 1
0x180059bd9  mov     ecx, 4; unsigned __int8
0x180059bde  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180059be3  jmp     short loc_180059BFD
0x180059be5  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180059bec  mov     ecx, 4; unsigned __int8
0x180059bf1  lea     rdx, aTheKeySWasNotF; "The key %s was not found, condition is "...
0x180059bf8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180059bfd  mov     rcx, [rbp+hKey]; hKey
0x180059c01  test    rcx, rcx
0x180059c04  jz      short loc_180059C0C
0x180059c06  call    cs:__imp_RegCloseKey
0x180059c0c  xor     eax, eax
0x180059c0e  add     rsp, 60h
0x180059c12  pop     r14
0x180059c14  pop     rdi
0x180059c15  pop     rsi
0x180059c16  pop     rbx
0x180059c17  pop     rbp
0x180059c18  retn
```
