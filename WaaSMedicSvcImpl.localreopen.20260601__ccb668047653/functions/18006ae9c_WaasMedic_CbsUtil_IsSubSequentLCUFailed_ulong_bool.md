# WaasMedic::CbsUtil::IsSubSequentLCUFailed(ulong,bool &)

- ea: `0x18006ae9c`
- end: `0x18006b065`
- name: `?IsSubSequentLCUFailed@CbsUtil@WaasMedic@@SAJKAEA_N@Z`
- size: `457`
- prototype: `__int64 __fastcall(unsigned int, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180061d00`

## callees

- `0x18000bbd4`
- `0x180028f10`
- `0x18002e81c`
- `0x18006ae9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aede`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006aef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006aef1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006afd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006afd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006af1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006af1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006aee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006af68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006aee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006af68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b052`

## string_xrefs

- `0x18006affd`: `Found %d LCU error package keys entries, configured subsequent error count %d.`
- `0x18006aec4`: `IsSubSequentLCUFailed: ConfiguredSubSequentFailureCount:%d`
- `0x18006af11`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrorPackageNames`
- `0x18006b031`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrorPackageNames`

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
0x18006ae9c  push    rbp
0x18006ae9e  push    rbx
0x18006ae9f  push    rsi
0x18006aea0  push    rdi
0x18006aea1  push    r14
0x18006aea3  mov     rbp, rsp
0x18006aea6  sub     rsp, 60h
0x18006aeaa  mov     r14, rdx
0x18006aead  mov     byte ptr [rdx], 0
0x18006aeb0  mov     esi, ecx
0x18006aeb2  mov     [rbp+cbMaxValueNameLen], 0
0x18006aeb9  mov     r8d, ecx
0x18006aebc  mov     [rbp+hKey], 0
0x18006aec4  lea     rdx, aIssubsequentlc; "IsSubSequentLCUFailed: ConfiguredSubSeq"...
0x18006aecb  mov     ecx, 4; unsigned __int8
0x18006aed0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006aed5  mov     rdi, [rbp+hKey]
0x18006aed9  test    rdi, rdi
0x18006aedc  jz      short loc_18006AEF7
0x18006aede  call    cs:__imp_GetLastError
0x18006aee4  mov     rcx, rdi; hKey
0x18006aee7  mov     ebx, eax
0x18006aee9  call    cs:__imp_RegCloseKey
0x18006aeef  mov     ecx, ebx; dwErrCode
0x18006aef1  call    cs:__imp_SetLastError
0x18006aef7  lea     rax, [rbp+hKey]
0x18006aefb  mov     [rbp+hKey], 0
0x18006af03  mov     r9d, 1; samDesired
0x18006af09  mov     [rsp+60h+phkResult], rax; int
0x18006af0e  xor     r8d, r8d; ulOptions
0x18006af11  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006af18  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006af1f  call    cs:__imp_RegOpenKeyExW
0x18006af25  mov     ebx, eax
0x18006af27  test    eax, eax
0x18006af29  jle     short loc_18006AF34
0x18006af2b  movzx   ebx, ax
0x18006af2e  or      ebx, 80070000h
0x18006af34  lea     eax, [rbx+7FF8FFFEh]
0x18006af3a  cmp     eax, 1
0x18006af3d  jbe     loc_18006B031
0x18006af43  test    ebx, ebx
0x18006af45  jns     short loc_18006AF75
0x18006af47  mov     rcx, [rbp+28h]; this
0x18006af4b  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006af52  mov     r9d, ebx; char *
0x18006af55  mov     edx, 14Ah; void *
0x18006af5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006af5f  mov     rcx, [rbp+hKey]; hKey
0x18006af63  test    rcx, rcx
0x18006af66  jz      short loc_18006AF6E
0x18006af68  call    cs:__imp_RegCloseKey
0x18006af6e  mov     eax, ebx
0x18006af70  jmp     loc_18006B05A
0x18006af75  mov     rcx, [rbp+hKey]; hKey
0x18006af79  lea     rax, [rbp+cbMaxValueNameLen]
0x18006af7d  mov     [rsp+60h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18006af86  xor     r9d, r9d; lpReserved
0x18006af89  mov     [rsp+60h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18006af92  xor     r8d, r8d; lpcchClass
0x18006af95  mov     [rsp+60h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18006af9e  xor     edx, edx; lpClass
0x18006afa0  mov     [rsp+60h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18006afa5  lea     rax, [rbp+cValues]
0x18006afa9  mov     [rsp+60h+lpcValues], rax; lpcValues
0x18006afae  mov     [rsp+60h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18006afb7  mov     [rsp+60h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18006afc0  mov     [rsp+60h+phkResult], 0; unsigned int
0x18006afc9  mov     [rbp+cValues], 0
0x18006afd0  call    cs:__imp_RegQueryInfoKeyW
0x18006afd6  test    eax, eax
0x18006afd8  jz      short loc_18006AFF9
0x18006afda  mov     rcx, [rbp+28h]; this
0x18006afde  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006afe5  mov     r9d, eax; char *
0x18006afe8  mov     edx, 158h; void *
0x18006afed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006aff2  mov     ebx, eax
0x18006aff4  jmp     loc_18006AF5F
0x18006aff9  mov     r8d, [rbp+cValues]
0x18006affd  lea     rdx, aFoundDLcuError_0; "Found %d LCU error package keys entries"...
0x18006b004  mov     r9d, esi
0x18006b007  mov     ecx, 4; unsigned __int8
0x18006b00c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006b011  mov     r8d, [rbp+cValues]
0x18006b015  cmp     r8d, esi
0x18006b018  jb      short loc_18006B049
0x18006b01a  lea     rdx, aConditionWasDe; "Condition was detected, found %d LCU er"...
0x18006b021  mov     byte ptr [r14], 1
0x18006b025  mov     ecx, 4; unsigned __int8
0x18006b02a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006b02f  jmp     short loc_18006B049
0x18006b031  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006b038  mov     ecx, 4; unsigned __int8
0x18006b03d  lea     rdx, aTheKeySWasNotF; "The key %s was not found, condition is "...
0x18006b044  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006b049  mov     rcx, [rbp+hKey]; hKey
0x18006b04d  test    rcx, rcx
0x18006b050  jz      short loc_18006B058
0x18006b052  call    cs:__imp_RegCloseKey
0x18006b058  xor     eax, eax
0x18006b05a  add     rsp, 60h
0x18006b05e  pop     r14
0x18006b060  pop     rdi
0x18006b061  pop     rsi
0x18006b062  pop     rbx
0x18006b063  pop     rbp
0x18006b064  retn
```
