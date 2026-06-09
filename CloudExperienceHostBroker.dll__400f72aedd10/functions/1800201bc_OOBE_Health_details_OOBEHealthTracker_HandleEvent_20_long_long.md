# OOBE::Health::details::OOBEHealthTracker::HandleEvent<20,long>(long)

- ea: `0x1800201bc`
- end: `0x18002027b`
- name: `??$HandleEvent@$0BE@J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
- size: `191`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022924`

## callees

- `0x180012408`
- `0x180018be8`
- `0x18001a980`
- `0x1800201bc`
- `0x180020cc0`
- `0x180024614`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020256`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020256`

## string_xrefs

- `0x1800201e5`: `OOBECompletedForOOBEHealth`
- `0x1800201de`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180020243`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<20,long>(unsigned int a1)
{
  int RedirectionKeyPath; // eax
  __int64 v3; // rcx
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+20h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
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
      OOBE::Health::details::OOBEScenarioEvents::SetEventValue<20,long>(v3, a1);
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
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x1800201bc  push    rbx
0x1800201be  sub     rsp, 40h
0x1800201c2  mov     ebx, ecx
0x1800201c4  mov     [rsp+48h+lpSubKey], 0
0x1800201cd  xor     edx, edx
0x1800201cf  lea     rcx, [rsp+48h+lpSubKey]
0x1800201d4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800201d9  lea     r8, [rsp+48h+lpSubKey]; unsigned __int16 **
0x1800201de  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800201e5  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800201ec  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800201f1  mov     rcx, [rsp+48h]; this
0x1800201f6  test    eax, eax
0x1800201f8  jns     short loc_180020210
0x1800201fa  mov     r9d, eax; char *
0x1800201fd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180020204  mov     edx, 4D4h; void *
0x180020209  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002020e  jmp     short loc_18002026B
0x180020210  mov     [rsp+48h+arg_8], 0
0x180020218  mov     [rsp+48h+arg_10], 4
0x180020220  lea     rax, [rsp+48h+arg_10]
0x180020225  mov     [rsp+48h+pcbData], rax; pcbData
0x18002022a  lea     rax, [rsp+48h+arg_8]
0x18002022f  mov     [rsp+48h+pvData], rax; pvData
0x180020234  mov     [rsp+48h+pdwType], 0; pdwType
0x18002023d  mov     r9d, 20000010h; dwFlags
0x180020243  lea     r8, aAnyonereadoobe; "AnyoneReadOOBECompleted"
0x18002024a  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x18002024f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180020256  call    cs:__imp_RegGetValueW
0x18002025c  cmp     [rsp+48h+arg_8], 0
0x180020261  jnz     short loc_18002026B
0x180020263  mov     edx, ebx
0x180020265  call    ??$SetEventValue@$0BE@J@OOBEScenarioEvents@details@Health@OOBE@@QEAAXJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetEventValue<20,long>(long)
0x18002026a  nop
0x18002026b  lea     rcx, [rsp+48h+lpSubKey]
0x180020270  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020275  add     rsp, 40h
0x180020279  pop     rbx
0x18002027a  retn
```
