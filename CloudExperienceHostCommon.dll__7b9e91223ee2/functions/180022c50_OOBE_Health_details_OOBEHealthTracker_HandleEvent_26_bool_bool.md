# OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>(bool)

- ea: `0x180022c50`
- end: `0x180022d32`
- name: `??$HandleEvent@$0BK@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `226`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026848`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800227ac`
- `0x180022c50`
- `0x18002316c`
- `0x180023c4c`
- `0x1800240f8`
- `0x180024d70`
- `0x180026668`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ce5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ce5`

## string_xrefs

- `0x180022c7a`: `OOBECompletedForOOBEHealth`
- `0x180022c73`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180022cd3`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>()
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)&qword_18011ADD0);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate((OOBE::Health::details::OOBEScenarioEvents *)&qword_18011ADD0);
      OOBE::Health::details::DeleteRegistryValue();
      OOBE::Health::details::SetRegistryValue();
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
0x180022c50  mov     [rsp-8+arg_0], cl
0x180022c54  push    rbp
0x180022c55  mov     rbp, rsp
0x180022c58  sub     rsp, 40h
0x180022c5c  mov     [rbp+lpSubKey], 0
0x180022c64  xor     edx, edx
0x180022c66  lea     rcx, [rbp+lpSubKey]
0x180022c6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022c6f  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180022c73  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022c7a  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180022c81  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180022c86  mov     rcx, [rbp+8]; this
0x180022c8a  test    eax, eax
0x180022c8c  jns     short loc_180022CA4
0x180022c8e  mov     r9d, eax; char *
0x180022c91  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022c98  mov     edx, 4D4h; void *
0x180022c9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022ca2  jmp     short loc_180022D23
0x180022ca4  mov     [rbp+arg_8], 0
0x180022cab  mov     [rbp+arg_10], 4
0x180022cb2  lea     rax, [rbp+arg_10]
0x180022cb6  mov     [rsp+40h+pcbData], rax; pcbData
0x180022cbb  lea     rax, [rbp+arg_8]
0x180022cbf  mov     [rsp+40h+pvData], rax; pvData
0x180022cc4  mov     [rsp+40h+pdwType], 0; pdwType
0x180022ccd  mov     r9d, 20000010h; dwFlags
0x180022cd3  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180022cda  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180022cde  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180022ce5  call    cs:__imp_RegGetValueW
0x180022ceb  cmp     [rbp+arg_8], 0
0x180022cef  jnz     short loc_180022D23
0x180022cf1  mov     [rbp+arg_0], 1
0x180022cf5  lea     r8, [rbp+arg_0]
0x180022cf9  lea     rdx, byte_18011ADE9
0x180022d00  lea     rcx, qword_18011ADD0
0x180022d07  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180022d0c  lea     rcx, qword_18011ADD0; this
0x180022d13  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180022d18  call    OOBE__Health__details__DeleteRegistryValue
0x180022d1d  call    OOBE__Health__details__SetRegistryValue
0x180022d22  nop
0x180022d23  lea     rcx, [rbp+lpSubKey]
0x180022d27  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180022d2c  add     rsp, 40h
0x180022d30  pop     rbp
0x180022d31  retn
```
