# OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>(bool)

- ea: `0x18002197c`
- end: `0x180021a7e`
- name: `??$HandleEvent@$06_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
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
- `0x18002197c`
- `0x1800225a8`
- `0x18002261c`
- `0x180023b4c`
- `0x180023e38`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a14`

## string_xrefs

- `0x1800219a6`: `OOBECompletedForOOBEHealth`
- `0x18002199f`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180021a02`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>()
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
0x18002197c  mov     byte ptr [rsp-8+arg_0], cl
0x180021980  push    rbp
0x180021981  mov     rbp, rsp
0x180021984  sub     rsp, 40h
0x180021988  mov     [rbp+lpSubKey], 0
0x180021990  xor     edx, edx
0x180021992  lea     rcx, [rbp+lpSubKey]
0x180021996  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002199b  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18002199f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800219a6  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800219ad  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800219b2  mov     rcx, [rbp+8]; this
0x1800219b6  test    eax, eax
0x1800219b8  jns     short loc_1800219D3
0x1800219ba  mov     r9d, eax; char *
0x1800219bd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800219c4  mov     edx, 4D4h; void *
0x1800219c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800219ce  jmp     loc_180021A6F
0x1800219d3  mov     [rbp+arg_8], 0
0x1800219da  mov     [rbp+arg_10], 4
0x1800219e1  lea     rax, [rbp+arg_10]
0x1800219e5  mov     [rsp+40h+pcbData], rax; pcbData
0x1800219ea  lea     rax, [rbp+arg_8]
0x1800219ee  mov     [rsp+40h+pvData], rax; pvData
0x1800219f3  mov     [rsp+40h+pdwType], 0; pdwType
0x1800219fc  mov     r9d, 20000010h; dwFlags
0x180021a02  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021a09  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180021a0d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021a14  call    cs:__imp_RegGetValueW
0x180021a1a  cmp     [rbp+arg_8], 0
0x180021a1e  jnz     short loc_180021A6F
0x180021a20  mov     byte ptr [rbp+arg_0], 1
0x180021a24  lea     r8, [rbp+arg_0]
0x180021a28  lea     rdx, word_18006DC7A
0x180021a2f  lea     rcx, byte_18006DC60
0x180021a36  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180021a3b  mov     eax, cs:dword_18006DC8C
0x180021a41  inc     eax
0x180021a43  mov     [rbp+arg_0], eax
0x180021a46  lea     r8, [rbp+arg_0]
0x180021a4a  lea     rdx, dword_18006DC8C
0x180021a51  lea     rcx, byte_18006DC60
0x180021a58  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180021a5d  lea     rcx, byte_18006DC60; this
0x180021a64  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180021a69  call    OOBE__Health__details__DeleteRegistryValue
0x180021a6e  nop
0x180021a6f  lea     rcx, [rbp+lpSubKey]
0x180021a73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021a78  add     rsp, 40h
0x180021a7c  pop     rbp
0x180021a7d  retn
```
