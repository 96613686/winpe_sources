# OOBE::Health::details::OOBEHealthTracker::HandleEvent<10,bool>(bool)

- ea: `0x18005880c`
- end: `0x1800588d6`
- name: `??$HandleEvent@$09_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `202`
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
- `0x18005880c`
- `0x180058ee8`
- `0x180059108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800588a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800588a1`

## string_xrefs

- `0x180058836`: `OOBECompletedForOOBEHealth`
- `0x18005882f`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18005888f`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<10,bool>(char a1)
{
  int RedirectionKeyPath; // eax
  __int64 v2; // rcx
  OOBE::Health::details::OOBEScenarioEvents *v3; // rcx
  int pdwType; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  char v7; // [rsp+50h] [rbp+10h] BYREF
  int pvData; // [rsp+58h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+28h] BYREF

  v7 = a1;
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
      v7 = 1;
      OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(v2, &byte_18011B03B, &v7);
      OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(v3);
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
0x18005880c  mov     [rsp-8+arg_0], cl
0x180058810  push    rbp
0x180058811  mov     rbp, rsp
0x180058814  sub     rsp, 40h
0x180058818  mov     [rbp+lpSubKey], 0
0x180058820  xor     edx, edx
0x180058822  lea     rcx, [rbp+lpSubKey]
0x180058826  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005882b  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18005882f  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058836  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x18005883d  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058842  mov     rcx, [rbp+8]; this
0x180058846  test    eax, eax
0x180058848  jns     short loc_180058860
0x18005884a  mov     r9d, eax; char *
0x18005884d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058854  mov     edx, 4D4h; void *
0x180058859  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005885e  jmp     short loc_1800588C7
0x180058860  mov     [rbp+arg_8], 0
0x180058867  mov     [rbp+arg_10], 4
0x18005886e  lea     rax, [rbp+arg_10]
0x180058872  mov     [rsp+40h+pcbData], rax; pcbData
0x180058877  lea     rax, [rbp+arg_8]
0x18005887b  mov     [rsp+40h+pvData], rax; pvData
0x180058880  mov     [rsp+40h+pdwType], 0; pdwType
0x180058889  mov     r9d, 20000010h; dwFlags
0x18005888f  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058896  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18005889a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800588a1  call    cs:__imp_RegGetValueW
0x1800588a7  cmp     [rbp+arg_8], 0
0x1800588ab  jnz     short loc_1800588C7
0x1800588ad  mov     [rbp+arg_0], 1
0x1800588b1  lea     r8, [rbp+arg_0]
0x1800588b5  lea     rdx, byte_18011B03B
0x1800588bc  call    ??$SetCensusEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(bool &,bool const &)
0x1800588c1  call    ?EvaluateCensus@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(void)
0x1800588c6  nop
0x1800588c7  lea     rcx, [rbp+lpSubKey]
0x1800588cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800588d0  add     rsp, 40h
0x1800588d4  pop     rbp
0x1800588d5  retn
```
