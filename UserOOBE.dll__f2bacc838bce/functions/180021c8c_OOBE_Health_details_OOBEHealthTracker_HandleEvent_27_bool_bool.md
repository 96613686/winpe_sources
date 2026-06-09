# OOBE::Health::details::OOBEHealthTracker::HandleEvent<27,bool>(bool)

- ea: `0x180021c8c`
- end: `0x180021da2`
- name: `??$HandleEvent@$0BL@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180021c8c`
- `0x180022690`
- `0x180024144`
- `0x180025b8c`
- `0x1800261ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021d20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021d20`

## string_xrefs

- `0x180021cb4`: `OOBECompletedForOOBEHealth`
- `0x180021cad`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180021d0d`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<27,bool>(char a1)
{
  int RedirectionKeyPath; // eax
  OOBE::Health::details::OOBEScenarioEvents *v2; // rcx
  WCHAR *v3; // rcx
  HKEY v4; // r8
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
    {
      OOBE::Health::details::OOBEScenarioEvents::ReadInfo(
        v2,
        (struct OOBE::Health::details::HealthInfoHeader *)&dword_18006DD0C,
        12,
        &byte_18006DD2A,
        &byte_18006DD2B,
        L"Census");
      if ( byte_18006DD14 != 1 )
      {
        byte_18006DD14 = 1;
        byte_18006DD2A = 1;
        OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(
          v3,
          (const BYTE *)&dword_18006DD0C,
          v4,
          &byte_18006DD2A,
          &byte_18006DD2B);
      }
      OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus((OOBE::Health::details::OOBEScenarioEvents *)v3);
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
0x180021c8c  mov     byte ptr [rsp+arg_0], cl
0x180021c90  push    rbx
0x180021c91  sub     rsp, 40h
0x180021c95  xor     ebx, ebx
0x180021c97  mov     [rsp+48h+lpSubKey], rbx
0x180021c9c  xor     edx, edx
0x180021c9e  lea     rcx, [rsp+48h+lpSubKey]
0x180021ca3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180021ca8  lea     r8, [rsp+48h+lpSubKey]; unsigned __int16 **
0x180021cad  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021cb4  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180021cbb  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180021cc0  mov     rcx, [rsp+48h]; this
0x180021cc5  test    eax, eax
0x180021cc7  jns     short loc_180021CE2
0x180021cc9  mov     r9d, eax; char *
0x180021ccc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180021cd3  mov     edx, 4D4h; void *
0x180021cd8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021cdd  jmp     loc_180021D92
0x180021ce2  mov     [rsp+48h+arg_0], ebx
0x180021ce6  mov     [rsp+48h+arg_8], 4
0x180021cee  lea     rax, [rsp+48h+arg_8]
0x180021cf3  mov     [rsp+48h+pcbData], rax; pcbData
0x180021cf8  lea     rax, [rsp+48h+arg_0]
0x180021cfd  mov     [rsp+48h+pvData], rax; pvData
0x180021d02  mov     [rsp+48h+pdwType], rbx; pdwType
0x180021d07  mov     r9d, 20000010h; dwFlags
0x180021d0d  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180021d14  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x180021d19  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021d20  call    cs:__imp_RegGetValueW
0x180021d26  cmp     [rsp+48h+arg_0], ebx
0x180021d2a  jnz     short loc_180021D92
0x180021d2c  lea     rax, ValueName; "Census"
0x180021d33  mov     [rsp+48h+pvData], rax; unsigned __int16 *
0x180021d38  lea     rbx, byte_18006DD2B
0x180021d3f  mov     [rsp+48h+pdwType], rbx; bool *
0x180021d44  lea     r9, byte_18006DD2A; bool *
0x180021d4b  mov     r8d, 0Ch; int
0x180021d51  lea     rdx, dword_18006DD0C; struct OOBE::Health::details::HealthInfoHeader *
0x180021d58  call    ?ReadInfo@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@234@HAEA_N1PEBG@Z; OOBE::Health::details::OOBEScenarioEvents::ReadInfo(OOBE::Health::details::HealthInfoHeader &,int,bool &,bool &,ushort const *)
0x180021d5d  cmp     cs:byte_18006DD14, 1
0x180021d64  jz      short loc_180021D8C
0x180021d66  mov     cs:byte_18006DD14, 1
0x180021d6d  mov     cs:byte_18006DD2A, 1
0x180021d74  mov     [rsp+48h+pdwType], rbx
0x180021d79  lea     r9, byte_18006DD2A
0x180021d80  lea     rdx, dword_18006DD0C
0x180021d87  call    ??$WriteInfo@UCensusTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUCensusTrackingInfo@123@AEA_N2PEBG@Z; OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::CensusTrackingInfo &,bool &,bool &,ushort const *)
0x180021d8c  call    ?EvaluateCensus@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::EvaluateCensus(void)
0x180021d91  nop
0x180021d92  lea     rcx, [rsp+48h+lpSubKey]
0x180021d97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021d9c  add     rsp, 40h
0x180021da0  pop     rbx
0x180021da1  retn
```
