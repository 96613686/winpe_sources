# OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>(bool)

- ea: `0x180048cb8`
- end: `0x180048dba`
- name: `??$HandleEvent@$06_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `258`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049ff0`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800227ac`
- `0x18002316c`
- `0x180023c4c`
- `0x1800240f8`
- `0x180024d70`
- `0x180048cb8`
- `0x1800491bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048d50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048d50`

## string_xrefs

- `0x180048ce2`: `OOBECompletedForOOBEHealth`
- `0x180048cdb`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180048d3e`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>()
{
  int RedirectionKeyPath; // eax
  int pdwType; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int pvData; // [rsp+58h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+28h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)&Data);
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)&Data);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)&Data);
      OOBE::Health::details::DeleteRegistryValue();
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
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180048cb8  mov     byte ptr [rsp-8+arg_0], cl
0x180048cbc  push    rbp
0x180048cbd  mov     rbp, rsp
0x180048cc0  sub     rsp, 40h
0x180048cc4  mov     [rbp+lpSubKey], 0
0x180048ccc  xor     edx, edx
0x180048cce  lea     rcx, [rbp+lpSubKey]
0x180048cd2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180048cd7  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180048cdb  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180048ce2  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180048ce9  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180048cee  mov     rcx, [rbp+8]; this
0x180048cf2  test    eax, eax
0x180048cf4  jns     short loc_180048D0F
0x180048cf6  mov     r9d, eax; char *
0x180048cf9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180048d00  mov     edx, 4D4h; void *
0x180048d05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048d0a  jmp     loc_180048DAB
0x180048d0f  mov     [rbp+arg_8], 0
0x180048d16  mov     [rbp+arg_10], 4
0x180048d1d  lea     rax, [rbp+arg_10]
0x180048d21  mov     [rsp+40h+pcbData], rax; pcbData
0x180048d26  lea     rax, [rbp+arg_8]
0x180048d2a  mov     [rsp+40h+pvData], rax; pvData
0x180048d2f  mov     [rsp+40h+pdwType], 0; pdwType
0x180048d38  mov     r9d, 20000010h; dwFlags
0x180048d3e  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180048d45  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180048d49  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180048d50  call    cs:__imp_RegGetValueW
0x180048d56  cmp     [rbp+arg_8], 0
0x180048d5a  jnz     short loc_180048DAB
0x180048d5c  mov     byte ptr [rbp+arg_0], 1
0x180048d60  lea     r8, [rbp+arg_0]
0x180048d64  lea     rdx, word_18011AECA
0x180048d6b  lea     rcx, Data
0x180048d72  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180048d77  mov     eax, cs:dword_18011AEDC
0x180048d7d  inc     eax
0x180048d7f  mov     [rbp+arg_0], eax
0x180048d82  lea     r8, [rbp+arg_0]
0x180048d86  lea     rdx, dword_18011AEDC
0x180048d8d  lea     rcx, Data; struct OOBE::Health::details::HealthInfoHeader *
0x180048d94  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180048d99  lea     rcx, Data; this
0x180048da0  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180048da5  call    OOBE__Health__details__DeleteRegistryValue
0x180048daa  nop
0x180048dab  lea     rcx, [rbp+lpSubKey]
0x180048daf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180048db4  add     rsp, 40h
0x180048db8  pop     rbp
0x180048db9  retn
```
