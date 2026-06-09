# SetUserNgcWasEnrolledRegKey(ushort const *)

- ea: `0x18005ef84`
- end: `0x18005f197`
- name: `?SetUserNgcWasEnrolledRegKey@@YAJPEBG@Z`
- size: `531`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005f3e0`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x1800325c0`
- `0x180032640`
- `0x18005d488`
- `0x18005d5a0`
- `0x18005ef84`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f06e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f0f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f16e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f06e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f0f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f16e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f127`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f127`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f0c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f0c6`

## string_xrefs

- `0x18005efe8`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005f032`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005f0da`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005f13b`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1)
{
  int v1; // eax
  const unsigned __int16 *v2; // r10
  unsigned __int64 v3; // r11
  unsigned int v4; // ebx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *(_DWORD *)Data = 1;
  hKey = 0;
  v1 = StringCchCopyW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\");
  v4 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v1,
      dwOptions);
    return v4;
  }
  v6 = StringCchCatW(SubKey, v3, v2);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v6,
      dwOptions);
    return v4;
  }
  hKey = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v7 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x85,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v7,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v8 = RegSetValueExW(hKey, L"NgcSetup", 0, 4u, Data, 4u);
  if ( v8 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x87,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v8,
           dwOptionsb);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005ef84  mov     [rsp-8+arg_8], rbx
0x18005ef89  push    rbp
0x18005ef8a  lea     rbp, [rsp-190h]
0x18005ef92  sub     rsp, 290h
0x18005ef99  mov     rax, cs:__security_cookie
0x18005efa0  xor     rax, rsp
0x18005efa3  mov     [rbp+190h+var_10], rax
0x18005efaa  mov     r10, rcx
0x18005efad  mov     dword ptr [rsp+290h+Data], 1
0x18005efb5  mov     [rsp+290h+hKey], 0
0x18005efbe  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005efc5  mov     r11d, 104h
0x18005efcb  mov     edx, r11d; unsigned __int64
0x18005efce  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18005efd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005efd8  mov     ebx, eax
0x18005efda  test    eax, eax
0x18005efdc  jns     short loc_18005F012
0x18005efde  mov     rcx, [rbp+198h]; this
0x18005efe5  mov     r9d, eax; char *
0x18005efe8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005efef  mov     edx, 81h; void *
0x18005eff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eff9  nop
0x18005effa  mov     rcx, [rsp+290h+hKey]; hKey
0x18005efff  test    rcx, rcx
0x18005f002  jz      short loc_18005F00B
0x18005f004  call    cs:__imp_RegCloseKey
0x18005f00a  nop
0x18005f00b  mov     eax, ebx
0x18005f00d  jmp     loc_18005F177
0x18005f012  mov     r8, r10; unsigned __int16 *
0x18005f015  mov     rdx, r11; unsigned __int64
0x18005f018  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18005f01d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005f022  mov     ebx, eax
0x18005f024  test    eax, eax
0x18005f026  jns     short loc_18005F057
0x18005f028  mov     rcx, [rbp+198h]; this
0x18005f02f  mov     r9d, eax; char *
0x18005f032  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005f039  mov     edx, 83h; void *
0x18005f03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f043  nop
0x18005f044  mov     rcx, [rsp+290h+hKey]; hKey
0x18005f049  test    rcx, rcx
0x18005f04c  jz      short loc_18005F055
0x18005f04e  call    cs:__imp_RegCloseKey
0x18005f054  nop
0x18005f055  jmp     short loc_18005F00B
0x18005f057  mov     rbx, [rsp+290h+hKey]
0x18005f05c  test    rbx, rbx
0x18005f05f  jz      short loc_18005F07F
0x18005f061  lea     rcx, [rsp+290h+var_230]; this
0x18005f066  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005f06b  mov     rcx, rbx; hKey
0x18005f06e  call    cs:__imp_RegCloseKey
0x18005f074  lea     rcx, [rsp+290h+var_230]; this
0x18005f079  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005f07e  nop
0x18005f07f  mov     [rsp+290h+hKey], 0
0x18005f088  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x18005f091  lea     rax, [rsp+290h+hKey]
0x18005f096  mov     [rsp+290h+phkResult], rax; phkResult
0x18005f09b  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005f0a4  mov     [rsp+290h+samDesired], 20006h; samDesired
0x18005f0ac  mov     [rsp+290h+dwOptions], 0; unsigned int
0x18005f0b4  xor     r9d, r9d; lpClass
0x18005f0b7  xor     r8d, r8d; Reserved
0x18005f0ba  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18005f0bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f0c6  call    cs:__imp_RegCreateKeyExW
0x18005f0cc  test    eax, eax
0x18005f0ce  jz      short loc_18005F103
0x18005f0d0  mov     rcx, [rbp+198h]; this
0x18005f0d7  mov     r9d, eax; char *
0x18005f0da  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005f0e1  mov     edx, 85h; void *
0x18005f0e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005f0eb  mov     ebx, eax
0x18005f0ed  mov     rcx, [rsp+290h+hKey]; hKey
0x18005f0f2  test    rcx, rcx
0x18005f0f5  jz      short loc_18005F0FE
0x18005f0f7  call    cs:__imp_RegCloseKey
0x18005f0fd  nop
0x18005f0fe  jmp     loc_18005F00B
0x18005f103  mov     r9d, 4; dwType
0x18005f109  mov     [rsp+290h+samDesired], r9d; cbData
0x18005f10e  lea     rax, [rsp+290h+Data]
0x18005f113  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x18005f118  xor     r8d, r8d; Reserved
0x18005f11b  lea     rdx, aNgcsetup; "NgcSetup"
0x18005f122  mov     rcx, [rsp+290h+hKey]; hKey
0x18005f127  call    cs:__imp_RegSetValueExW
0x18005f12d  test    eax, eax
0x18005f12f  jz      short loc_18005F164
0x18005f131  mov     rcx, [rbp+198h]; this
0x18005f138  mov     r9d, eax; char *
0x18005f13b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005f142  mov     edx, 87h; void *
0x18005f147  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005f14c  mov     ebx, eax
0x18005f14e  mov     rcx, [rsp+290h+hKey]; hKey
0x18005f153  test    rcx, rcx
0x18005f156  jz      short loc_18005F15F
0x18005f158  call    cs:__imp_RegCloseKey
0x18005f15e  nop
0x18005f15f  jmp     loc_18005F00B
0x18005f164  mov     rcx, [rsp+290h+hKey]; hKey
0x18005f169  test    rcx, rcx
0x18005f16c  jz      short loc_18005F175
0x18005f16e  call    cs:__imp_RegCloseKey
0x18005f174  nop
0x18005f175  xor     eax, eax
0x18005f177  mov     rcx, [rbp+190h+var_10]
0x18005f17e  xor     rcx, rsp; StackCookie
0x18005f181  call    __security_check_cookie
0x18005f186  mov     rbx, [rsp+290h+arg_8]
0x18005f18e  add     rsp, 290h
0x18005f195  pop     rbp
0x18005f196  retn
```
