# OOBE::Health::details::OOBEHealthTracker::HandleEvent<1,bool>(bool)

- ea: `0x1800218b8`
- end: `0x180021974`
- name: `??$HandleEvent@$00_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x1800218b8`
- `0x180022550`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021952`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021952`

## string_xrefs

- `0x1800218e1`: `OOBECompletedForOOBEHealth`
- `0x1800218da`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18002193f`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<1,bool>(char a1)
{
  int RedirectionKeyPath; // eax
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(pvData) = a1;
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
      OOBE::Health::details::OOBEScenarioEvents::SetEventValue<1,bool>();
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
0x1800218b8  mov     byte ptr [rsp+arg_0], cl
0x1800218bc  sub     rsp, 48h
0x1800218c0  mov     [rsp+48h+lpSubKey], 0
0x1800218c9  xor     edx, edx
0x1800218cb  lea     rcx, [rsp+48h+lpSubKey]
0x1800218d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800218d5  lea     r8, [rsp+48h+lpSubKey]; unsigned __int16 **
0x1800218da  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800218e1  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800218e8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800218ed  mov     rcx, [rsp+48h]; this
0x1800218f2  test    eax, eax
0x1800218f4  jns     short loc_18002190C
0x1800218f6  mov     r9d, eax; char *
0x1800218f9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180021900  mov     edx, 4D4h; void *
0x180021905  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002190a  jmp     short loc_180021965
0x18002190c  mov     [rsp+48h+arg_0], 0
0x180021914  mov     [rsp+48h+arg_8], 4
0x18002191c  lea     rax, [rsp+48h+arg_8]
0x180021921  mov     [rsp+48h+pcbData], rax; pcbData
0x180021926  lea     rax, [rsp+48h+arg_0]
0x18002192b  mov     [rsp+48h+pvData], rax; pvData
0x180021930  mov     [rsp+48h+pdwType], 0; pdwType
0x180021939  mov     r9d, 20000010h; dwFlags
0x18002193f  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021946  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x18002194b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021952  call    cs:__imp_RegGetValueW
0x180021958  cmp     [rsp+48h+arg_0], 0
0x18002195d  jnz     short loc_180021965
0x18002195f  call    ??$SetEventValue@$00_N@OOBEScenarioEvents@details@Health@OOBE@@QEAAX_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetEventValue<1,bool>(bool)
0x180021964  nop
0x180021965  lea     rcx, [rsp+48h+lpSubKey]
0x18002196a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002196f  add     rsp, 48h
0x180021973  retn
```
