# OOBE::Health::details::OOBEHealthTracker::HandleEvent<22,bool>(bool)

- ea: `0x1800588dc`
- end: `0x1800589d9`
- name: `??$HandleEvent@$0BG@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `253`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800593c0`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800227ac`
- `0x18002316c`
- `0x1800240f8`
- `0x180024d70`
- `0x1800491bc`
- `0x1800588dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058974`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058974`

## string_xrefs

- `0x180058906`: `OOBECompletedForOOBEHealth`
- `0x1800588ff`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180058962`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 OOBE::Health::details::OOBEHealthTracker::HandleEvent<22,bool>()
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)&byte_18011AF80);
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)&byte_18011AF80);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)&byte_18011AF80);
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
0x1800588dc  mov     byte ptr [rsp-8+arg_0], cl
0x1800588e0  push    rbp
0x1800588e1  mov     rbp, rsp
0x1800588e4  sub     rsp, 40h
0x1800588e8  mov     [rbp+lpSubKey], 0
0x1800588f0  xor     edx, edx
0x1800588f2  lea     rcx, [rbp+lpSubKey]
0x1800588f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800588fb  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x1800588ff  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058906  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x18005890d  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058912  mov     rcx, [rbp+8]; this
0x180058916  test    eax, eax
0x180058918  jns     short loc_180058933
0x18005891a  mov     r9d, eax; char *
0x18005891d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058924  mov     edx, 4D4h; void *
0x180058929  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005892e  jmp     loc_1800589CA
0x180058933  mov     [rbp+arg_8], 0
0x18005893a  mov     [rbp+arg_10], 4
0x180058941  lea     rax, [rbp+arg_10]
0x180058945  mov     [rsp+40h+pcbData], rax; pcbData
0x18005894a  lea     rax, [rbp+arg_8]
0x18005894e  mov     [rsp+40h+pvData], rax; pvData
0x180058953  mov     [rsp+40h+pdwType], 0; pdwType
0x18005895c  mov     r9d, 20000010h; dwFlags
0x180058962  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058969  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18005896d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058974  call    cs:__imp_RegGetValueW
0x18005897a  cmp     [rbp+arg_8], 0
0x18005897e  jnz     short loc_1800589CA
0x180058980  mov     byte ptr [rbp+arg_0], 1
0x180058984  lea     r8, [rbp+arg_0]
0x180058988  lea     rdx, byte_18011AF95
0x18005898f  lea     rcx, byte_18011AF80
0x180058996  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18005899b  mov     eax, cs:dword_18011B014
0x1800589a1  inc     eax
0x1800589a3  mov     [rbp+arg_0], eax
0x1800589a6  lea     r8, [rbp+arg_0]
0x1800589aa  lea     rdx, dword_18011B014
0x1800589b1  lea     rcx, byte_18011AF80; struct OOBE::Health::details::HealthInfoHeader *
0x1800589b8  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x1800589bd  lea     rcx, byte_18011AF80; this
0x1800589c4  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x1800589c9  nop
0x1800589ca  lea     rcx, [rbp+lpSubKey]
0x1800589ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800589d3  add     rsp, 40h
0x1800589d7  pop     rbp
0x1800589d8  retn
```
