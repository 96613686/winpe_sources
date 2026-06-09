# OOBE::Health::details::OOBEHealthTracker::HandleEvent<29,bool>(bool)

- ea: `0x180058ab8`
- end: `0x180058b89`
- name: `??$HandleEvent@$0BN@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
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
- `0x180058ab8`
- `0x180058ee8`
- `0x180059108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058b50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058b50`

## string_xrefs

- `0x180058ae5`: `OOBECompletedForOOBEHealth`
- `0x180058ade`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180058b3e`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<29,bool>(char a1)
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
      OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(v3, byte_18011B038, &v9);
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
0x180058ab8  mov     [rsp-8+arg_0], rbx
0x180058abd  push    rbp
0x180058abe  mov     rbp, rsp
0x180058ac1  sub     rsp, 50h
0x180058ac5  mov     bl, cl
0x180058ac7  mov     [rbp+lpSubKey], 0
0x180058acf  xor     edx, edx
0x180058ad1  lea     rcx, [rbp+lpSubKey]
0x180058ad5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058ada  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180058ade  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058ae5  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180058aec  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058af1  mov     rcx, [rbp+8]; this
0x180058af5  test    eax, eax
0x180058af7  jns     short loc_180058B0F
0x180058af9  mov     r9d, eax; char *
0x180058afc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058b03  mov     edx, 4D4h; void *
0x180058b08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058b0d  jmp     short loc_180058B75
0x180058b0f  mov     [rbp+arg_10], 0
0x180058b16  mov     [rbp+arg_18], 4
0x180058b1d  lea     rax, [rbp+arg_18]
0x180058b21  mov     [rsp+50h+pcbData], rax; pcbData
0x180058b26  lea     rax, [rbp+arg_10]
0x180058b2a  mov     [rsp+50h+pvData], rax; pvData
0x180058b2f  mov     [rsp+50h+pdwType], 0; pdwType
0x180058b38  mov     r9d, 20000010h; dwFlags
0x180058b3e  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058b45  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180058b49  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058b50  call    cs:__imp_RegGetValueW
0x180058b56  cmp     [rbp+arg_10], 0
0x180058b5a  jnz     short loc_180058B75
0x180058b5c  mov     [rbp+arg_8], bl
0x180058b5f  lea     r8, [rbp+arg_8]
0x180058b63  lea     rdx, byte_18011B038
0x180058b6a  call    ??$SetCensusEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetCensusEventValueMember<bool>(bool &,bool const &)
0x180058b6f  call    ?EvaluateCensus@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(void)
0x180058b74  nop
0x180058b75  lea     rcx, [rbp+lpSubKey]
0x180058b79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058b7e  mov     rbx, [rsp+50h+arg_0]
0x180058b83  add     rsp, 50h
0x180058b87  pop     rbp
0x180058b88  retn
```
