# OOBE::Health::details::OOBEHealthTracker::HandleEvent<9,bool>(bool)

- ea: `0x180021a84`
- end: `0x180021b86`
- name: `??$HandleEvent@$08_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002abbc`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180021a84`
- `0x1800225a8`
- `0x18002261c`
- `0x180023b4c`
- `0x180023e38`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021b1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021b1c`

## string_xrefs

- `0x180021aae`: `OOBECompletedForOOBEHealth`
- `0x180021aa7`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180021b0a`: `AnyoneReadOOBECompleted`

## pseudocode

```c
void OOBE::Health::details::OOBEHealthTracker::HandleEvent<9,bool>()
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)byte_18006DC60);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)byte_18006DC60);
      OOBE::Health::details::DeleteRegistryValue(v2, v1, v3);
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
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpSubKey);
}

```

## disassembly

```asm
0x180021a84  mov     byte ptr [rsp-8+arg_0], cl
0x180021a88  push    rbp
0x180021a89  mov     rbp, rsp
0x180021a8c  sub     rsp, 40h
0x180021a90  mov     [rbp+lpSubKey], 0
0x180021a98  xor     edx, edx
0x180021a9a  lea     rcx, [rbp+lpSubKey]
0x180021a9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180021aa3  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180021aa7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021aae  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180021ab5  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180021aba  mov     rcx, [rbp+8]; this
0x180021abe  test    eax, eax
0x180021ac0  jns     short loc_180021ADB
0x180021ac2  mov     r9d, eax; char *
0x180021ac5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180021acc  mov     edx, 4D4h; void *
0x180021ad1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021ad6  jmp     loc_180021B77
0x180021adb  mov     [rbp+arg_8], 0
0x180021ae2  mov     [rbp+arg_10], 4
0x180021ae9  lea     rax, [rbp+arg_10]
0x180021aed  mov     [rsp+40h+pcbData], rax; pcbData
0x180021af2  lea     rax, [rbp+arg_8]
0x180021af6  mov     [rsp+40h+pvData], rax; pvData
0x180021afb  mov     [rsp+40h+pdwType], 0; pdwType
0x180021b04  mov     r9d, 20000010h; dwFlags
0x180021b0a  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021b11  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180021b15  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021b1c  call    cs:__imp_RegGetValueW
0x180021b22  cmp     [rbp+arg_8], 0
0x180021b26  jnz     short loc_180021B77
0x180021b28  mov     byte ptr [rbp+arg_0], 1
0x180021b2c  lea     r8, [rbp+arg_0]
0x180021b30  lea     rdx, dword_18006DC7C
0x180021b37  lea     rcx, byte_18006DC60
0x180021b3e  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180021b43  mov     eax, cs:dword_18006DC94
0x180021b49  inc     eax
0x180021b4b  mov     [rbp+arg_0], eax
0x180021b4e  lea     r8, [rbp+arg_0]
0x180021b52  lea     rdx, dword_18006DC94
0x180021b59  lea     rcx, byte_18006DC60
0x180021b60  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180021b65  lea     rcx, byte_18006DC60; this
0x180021b6c  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180021b71  call    OOBE__Health__details__DeleteRegistryValue
0x180021b76  nop
0x180021b77  lea     rcx, [rbp+lpSubKey]
0x180021b7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021b80  add     rsp, 40h
0x180021b84  pop     rbp
0x180021b85  retn
```
