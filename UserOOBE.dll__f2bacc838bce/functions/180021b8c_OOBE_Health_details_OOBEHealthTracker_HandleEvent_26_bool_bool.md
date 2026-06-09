# OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>(bool)

- ea: `0x180021b8c`
- end: `0x180021c86`
- name: `??$HandleEvent@$0BK@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026c00`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180021b8c`
- `0x18002261c`
- `0x180023b4c`
- `0x180023e38`
- `0x180025b8c`
- `0x180026ab0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021c24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021c24`

## string_xrefs

- `0x180021bb6`: `OOBECompletedForOOBEHealth`
- `0x180021c6a`: `OOBECompletedForOOBEHealth`
- `0x180021baf`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180021c63`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180021c12`: `AnyoneReadOOBECompleted`
- `0x180021c5c`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>()
{
  int RedirectionKeyPath; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  HKEY v3; // r8
  int pdwType; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int pvData; // [rsp+58h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+28h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)&lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBECompletedForOOBEHealth",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompletedForOOBEHealth",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"AnyoneReadOOBECompleted", 0x20000010u, 0, &pvData, &pcbData);
    if ( !pvData )
    {
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)byte_18006DC60);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)byte_18006DC60);
      OOBE::Health::details::DeleteRegistryValue(v2, v1, v3);
      OOBE::Health::details::SetRegistryValue(
        L"OOBECompletedForOOBEHealth",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompletedForOOBEHealth",
        L"AnyoneReadOOBECompleted");
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      pdwType);
  }
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180021b8c  mov     [rsp-8+arg_0], cl
0x180021b90  push    rbp
0x180021b91  mov     rbp, rsp
0x180021b94  sub     rsp, 40h
0x180021b98  mov     [rbp+lpSubKey], 0
0x180021ba0  xor     edx, edx
0x180021ba2  lea     rcx, [rbp+lpSubKey]
0x180021ba6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180021bab  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180021baf  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021bb6  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180021bbd  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180021bc2  mov     rcx, [rbp+8]; this
0x180021bc6  test    eax, eax
0x180021bc8  jns     short loc_180021BE3
0x180021bca  mov     r9d, eax; char *
0x180021bcd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180021bd4  mov     edx, 4D4h; void *
0x180021bd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021bde  jmp     loc_180021C77
0x180021be3  mov     [rbp+arg_8], 0
0x180021bea  mov     [rbp+arg_10], 4
0x180021bf1  lea     rax, [rbp+arg_10]
0x180021bf5  mov     [rsp+40h+pcbData], rax; pcbData
0x180021bfa  lea     rax, [rbp+arg_8]
0x180021bfe  mov     [rsp+40h+pvData], rax; pvData
0x180021c03  mov     [rsp+40h+pdwType], 0; pdwType
0x180021c0c  mov     r9d, 20000010h; dwFlags
0x180021c12  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021c19  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180021c1d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021c24  call    cs:__imp_RegGetValueW
0x180021c2a  cmp     [rbp+arg_8], 0
0x180021c2e  jnz     short loc_180021C77
0x180021c30  mov     [rbp+arg_0], 1
0x180021c34  lea     r8, [rbp+arg_0]
0x180021c38  lea     rdx, byte_18006DC79
0x180021c3f  lea     rcx, byte_18006DC60
0x180021c46  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180021c4b  lea     rcx, byte_18006DC60; this
0x180021c52  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180021c57  call    OOBE__Health__details__DeleteRegistryValue
0x180021c5c  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021c63  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021c6a  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180021c71  call    OOBE__Health__details__SetRegistryValue
0x180021c76  nop
0x180021c77  lea     rcx, [rbp+lpSubKey]
0x180021c7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021c80  add     rsp, 40h
0x180021c84  pop     rbp
0x180021c85  retn
```
