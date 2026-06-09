# OOBE::Health::details::OOBEHealthTracker::HandleEvent<28,bool>(bool)

- ea: `0x1800589e0`
- end: `0x180058ab1`
- name: `??$HandleEvent@$0BM@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `209`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800593c0`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800227ac`
- `0x180024d70`
- `0x1800589e0`
- `0x180058ee8`
- `0x180059108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058a78`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058a78`

## string_xrefs

- `0x180058a0d`: `OOBECompletedForOOBEHealth`
- `0x180058a06`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180058a66`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<28,bool>(char a1)
{
  int RedirectionKeyPath; // eax
  __int64 v3; // rcx
  OOBE::Health::details::OOBEScenarioEvents *v4; // rcx
  int pdwType; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  char v9; // [rsp+68h] [rbp+18h] BYREF
  int pvData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF

  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBECompletedForOOBEHealth",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompletedForOOBEHealth",
                         (unsigned __int16 **)lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey[0], L"AnyoneReadOOBECompleted", 0x20000010u, 0, &pvData, &pcbData);
    if ( !pvData )
    {
      v9 = a1;
      OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(v3, byte_18011B035, &v9);
      OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(v4);
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
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
}

```

## disassembly

```asm
0x1800589e0  mov     [rsp-8+arg_0], rbx
0x1800589e5  push    rbp
0x1800589e6  mov     rbp, rsp
0x1800589e9  sub     rsp, 50h
0x1800589ed  mov     bl, cl
0x1800589ef  mov     [rbp+lpSubKey], 0
0x1800589f7  xor     edx, edx
0x1800589f9  lea     rcx, [rbp+lpSubKey]
0x1800589fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058a02  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180058a06  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058a0d  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180058a14  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058a19  mov     rcx, [rbp+8]; this
0x180058a1d  test    eax, eax
0x180058a1f  jns     short loc_180058A37
0x180058a21  mov     r9d, eax; char *
0x180058a24  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058a2b  mov     edx, 4D4h; void *
0x180058a30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058a35  jmp     short loc_180058A9D
0x180058a37  mov     [rbp+arg_10], 0
0x180058a3e  mov     [rbp+arg_18], 4
0x180058a45  lea     rax, [rbp+arg_18]
0x180058a49  mov     [rsp+50h+pcbData], rax; pcbData
0x180058a4e  lea     rax, [rbp+arg_10]
0x180058a52  mov     [rsp+50h+pvData], rax; pvData
0x180058a57  mov     [rsp+50h+pdwType], 0; pdwType
0x180058a60  mov     r9d, 20000010h; dwFlags
0x180058a66  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058a6d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180058a71  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058a78  call    cs:__imp_RegGetValueW
0x180058a7e  cmp     [rbp+arg_10], 0
0x180058a82  jnz     short loc_180058A9D
0x180058a84  mov     [rbp+arg_8], bl
0x180058a87  lea     r8, [rbp+arg_8]
0x180058a8b  lea     rdx, byte_18011B035
0x180058a92  call    ??$SetCensusEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(bool &,bool const &)
0x180058a97  call    ?EvaluateCensus@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(void)
0x180058a9c  nop
0x180058a9d  lea     rcx, [rbp+lpSubKey]
0x180058aa1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058aa6  mov     rbx, [rsp+50h+arg_0]
0x180058aab  add     rsp, 50h
0x180058aaf  pop     rbp
0x180058ab0  retn
```
