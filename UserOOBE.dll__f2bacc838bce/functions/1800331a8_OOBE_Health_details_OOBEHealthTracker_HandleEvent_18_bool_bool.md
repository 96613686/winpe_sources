# OOBE::Health::details::OOBEHealthTracker::HandleEvent<18,bool>(bool)

- ea: `0x1800331a8`
- end: `0x1800332a5`
- name: `??$HandleEvent@$0BC@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037be4`
- `0x1800395b0`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x1800225a8`
- `0x18002261c`
- `0x180023e38`
- `0x180025b8c`
- `0x1800331a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033240`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033240`

## string_xrefs

- `0x1800331d2`: `OOBECompletedForOOBEHealth`
- `0x1800331cb`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18003322e`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void OOBE::Health::details::OOBEHealthTracker::HandleEvent<18,bool>()
{
  int RedirectionKeyPath; // eax
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)qword_18006DD40);
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)qword_18006DD40);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)qword_18006DD40);
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
0x1800331a8  mov     byte ptr [rsp-8+arg_0], cl
0x1800331ac  push    rbp
0x1800331ad  mov     rbp, rsp
0x1800331b0  sub     rsp, 40h
0x1800331b4  mov     [rbp+lpSubKey], 0
0x1800331bc  xor     edx, edx
0x1800331be  lea     rcx, [rbp+lpSubKey]
0x1800331c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800331c7  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x1800331cb  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800331d2  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800331d9  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800331de  mov     rcx, [rbp+8]; this
0x1800331e2  test    eax, eax
0x1800331e4  jns     short loc_1800331FF
0x1800331e6  mov     r9d, eax; char *
0x1800331e9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800331f0  mov     edx, 4D4h; void *
0x1800331f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800331fa  jmp     loc_180033296
0x1800331ff  mov     [rbp+arg_8], 0
0x180033206  mov     [rbp+arg_10], 4
0x18003320d  lea     rax, [rbp+arg_10]
0x180033211  mov     [rsp+40h+pcbData], rax; pcbData
0x180033216  lea     rax, [rbp+arg_8]
0x18003321a  mov     [rsp+40h+pvData], rax; pvData
0x18003321f  mov     [rsp+40h+pdwType], 0; pdwType
0x180033228  mov     r9d, 20000010h; dwFlags
0x18003322e  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180033235  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180033239  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180033240  call    cs:__imp_RegGetValueW
0x180033246  cmp     [rbp+arg_8], 0
0x18003324a  jnz     short loc_180033296
0x18003324c  mov     byte ptr [rbp+arg_0], 1
0x180033250  lea     r8, [rbp+arg_0]
0x180033254  lea     rdx, byte_18006DD51
0x18003325b  lea     rcx, qword_18006DD40
0x180033262  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180033267  mov     eax, cs:dword_18006DDB8
0x18003326d  inc     eax
0x18003326f  mov     [rbp+arg_0], eax
0x180033272  lea     r8, [rbp+arg_0]
0x180033276  lea     rdx, dword_18006DDB8
0x18003327d  lea     rcx, qword_18006DD40
0x180033284  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180033289  lea     rcx, qword_18006DD40; this
0x180033290  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180033295  nop
0x180033296  lea     rcx, [rbp+lpSubKey]
0x18003329a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003329f  add     rsp, 40h
0x1800332a3  pop     rbp
0x1800332a4  retn
```
