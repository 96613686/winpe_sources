# OOBE::Health::details::OOBEHealthTracker::HandleEvent<12,long>(long)

- ea: `0x180058cb8`
- end: `0x180058dd8`
- name: `??$HandleEvent@$0M@J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
- size: `288`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
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
- `0x180058cb8`
- `0x180058f6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058d53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058d53`

## string_xrefs

- `0x180058ce5`: `OOBECompletedForOOBEHealth`
- `0x180058cde`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180058d41`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<12,long>(int a1)
{
  int RedirectionKeyPath; // eax
  __int64 v3; // rcx
  int pdwType; // [rsp+20h] [rbp-30h]
  int v6; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int pvData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF

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
      v6 = a1;
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)&byte_18011AF80);
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)&byte_18011AF80);
      if ( a1 < 0 )
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(v3, &dword_18011AFC4, &v6);
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
0x180058cb8  mov     [rsp-8+arg_0], rbx
0x180058cbd  push    rbp
0x180058cbe  mov     rbp, rsp
0x180058cc1  sub     rsp, 50h
0x180058cc5  mov     ebx, ecx
0x180058cc7  mov     [rbp+lpSubKey], 0
0x180058ccf  xor     edx, edx
0x180058cd1  lea     rcx, [rbp+lpSubKey]
0x180058cd5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058cda  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180058cde  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058ce5  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180058cec  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058cf1  mov     rcx, [rbp+8]; this
0x180058cf5  test    eax, eax
0x180058cf7  jns     short loc_180058D12
0x180058cf9  mov     r9d, eax; char *
0x180058cfc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058d03  mov     edx, 4D4h; void *
0x180058d08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058d0d  jmp     loc_180058DC4
0x180058d12  mov     [rbp+arg_10], 0
0x180058d19  mov     [rbp+arg_18], 4
0x180058d20  lea     rax, [rbp+arg_18]
0x180058d24  mov     [rsp+50h+pcbData], rax; pcbData
0x180058d29  lea     rax, [rbp+arg_10]
0x180058d2d  mov     [rsp+50h+pvData], rax; pvData
0x180058d32  mov     [rsp+50h+pdwType], 0; pdwType
0x180058d3b  mov     r9d, 20000010h; dwFlags
0x180058d41  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058d48  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180058d4c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058d53  call    cs:__imp_RegGetValueW
0x180058d59  cmp     [rbp+arg_10], 0
0x180058d5d  jnz     short loc_180058DC4
0x180058d5f  mov     [rbp+var_10], ebx
0x180058d62  mov     eax, ebx
0x180058d64  shr     eax, 1Fh
0x180058d67  mov     byte ptr [rbp+arg_8], al
0x180058d6a  lea     r8, [rbp+arg_8]
0x180058d6e  lea     rdx, byte_18011AF8D
0x180058d75  lea     rcx, byte_18011AF80
0x180058d7c  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180058d81  mov     eax, cs:dword_18011AFC8
0x180058d87  inc     eax
0x180058d89  mov     [rbp+arg_8], eax
0x180058d8c  lea     r8, [rbp+arg_8]
0x180058d90  lea     rdx, dword_18011AFC8
0x180058d97  lea     rcx, byte_18011AF80; struct OOBE::Health::details::HealthInfoHeader *
0x180058d9e  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180058da3  test    ebx, ebx
0x180058da5  jns     short loc_180058DB7
0x180058da7  lea     r8, [rbp+var_10]
0x180058dab  lea     rdx, dword_18011AFC4
0x180058db2  call    ??$SetHealthEventValueMember@J@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAJAEBJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(long &,long const &)
0x180058db7  lea     rcx, byte_18011AF80; this
0x180058dbe  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180058dc3  nop
0x180058dc4  lea     rcx, [rbp+lpSubKey]
0x180058dc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058dcd  mov     rbx, [rsp+50h+arg_0]
0x180058dd2  add     rsp, 50h
0x180058dd6  pop     rbp
0x180058dd7  retn
```
