# OOBE::Health::details::OOBEHealthTracker::HandleEvent<15,long>(long)

- ea: `0x180033374`
- end: `0x180033494`
- name: `??$HandleEvent@$0P@J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f670`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x1800225a8`
- `0x18002261c`
- `0x180023e38`
- `0x180025b8c`
- `0x180033374`
- `0x180033b3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003340f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003340f`

## string_xrefs

- `0x1800333a1`: `OOBECompletedForOOBEHealth`
- `0x18003339a`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x1800333fd`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<15,long>(int a1)
{
  int RedirectionKeyPath; // eax
  __int64 v3; // rcx
  int pdwType; // [rsp+20h] [rbp-30h]
  int v5; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int pvData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF

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
      v5 = a1;
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>((struct OOBE::Health::details::HealthInfoHeader *)qword_18006DD40);
      if ( a1 < 0 )
      {
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>((struct OOBE::Health::details::HealthInfoHeader *)qword_18006DD40);
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(v3, byte_18006DDA8, &v5);
      }
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
0x180033374  mov     [rsp-8+arg_0], rbx
0x180033379  push    rbp
0x18003337a  mov     rbp, rsp
0x18003337d  sub     rsp, 50h
0x180033381  mov     ebx, ecx
0x180033383  mov     [rbp+lpSubKey], 0
0x18003338b  xor     edx, edx
0x18003338d  lea     rcx, [rbp+lpSubKey]
0x180033391  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180033396  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18003339a  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800333a1  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800333a8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800333ad  mov     rcx, [rbp+8]; this
0x1800333b1  test    eax, eax
0x1800333b3  jns     short loc_1800333CE
0x1800333b5  mov     r9d, eax; char *
0x1800333b8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800333bf  mov     edx, 4D4h; void *
0x1800333c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800333c9  jmp     loc_180033480
0x1800333ce  mov     [rbp+arg_10], 0
0x1800333d5  mov     [rbp+arg_18], 4
0x1800333dc  lea     rax, [rbp+arg_18]
0x1800333e0  mov     [rsp+50h+pcbData], rax; pcbData
0x1800333e5  lea     rax, [rbp+arg_10]
0x1800333e9  mov     [rsp+50h+pvData], rax; pvData
0x1800333ee  mov     [rsp+50h+pdwType], 0; pdwType
0x1800333f7  mov     r9d, 20000010h; dwFlags
0x1800333fd  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180033404  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180033408  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003340f  call    cs:__imp_RegGetValueW
0x180033415  cmp     [rbp+arg_10], 0
0x180033419  jnz     short loc_180033480
0x18003341b  mov     [rbp+var_10], ebx
0x18003341e  mov     eax, ebx
0x180033420  shr     eax, 1Fh
0x180033423  mov     byte ptr [rbp+arg_8], al
0x180033426  lea     r8, [rbp+arg_8]
0x18003342a  lea     rdx, byte_18006DD50
0x180033431  lea     rcx, qword_18006DD40
0x180033438  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18003343d  test    ebx, ebx
0x18003343f  jns     short loc_180033473
0x180033441  mov     eax, cs:dword_18006DDAC
0x180033447  inc     eax
0x180033449  mov     [rbp+arg_8], eax
0x18003344c  lea     r8, [rbp+arg_8]
0x180033450  lea     rdx, dword_18006DDAC
0x180033457  lea     rcx, qword_18006DD40
0x18003345e  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180033463  lea     r8, [rbp+var_10]
0x180033467  lea     rdx, byte_18006DDA8
0x18003346e  call    ??$SetHealthEventValueMember@J@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAJAEBJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(long &,long const &)
0x180033473  lea     rcx, qword_18006DD40; this
0x18003347a  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x18003347f  nop
0x180033480  lea     rcx, [rbp+lpSubKey]
0x180033484  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180033489  mov     rbx, [rsp+50h+arg_0]
0x18003348e  add     rsp, 50h
0x180033492  pop     rbp
0x180033493  retn
```
