# OOBE::Health::details::OOBEHealthTracker::HandleEvent<11,long>(long)

- ea: `0x180058b90`
- end: `0x180058cb0`
- name: `??$HandleEvent@$0L@J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
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
- `0x180058b90`
- `0x180058f6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058c2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058c2b`

## string_xrefs

- `0x180058bbd`: `OOBECompletedForOOBEHealth`
- `0x180058bb6`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x180058c19`: `AnyoneReadOOBECompleted`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<11,long>(int a1)
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
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(v3, &dword_18011AFBC, &v6);
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
0x180058b90  mov     [rsp-8+arg_0], rbx
0x180058b95  push    rbp
0x180058b96  mov     rbp, rsp
0x180058b99  sub     rsp, 50h
0x180058b9d  mov     ebx, ecx
0x180058b9f  mov     [rbp+lpSubKey], 0
0x180058ba7  xor     edx, edx
0x180058ba9  lea     rcx, [rbp+lpSubKey]
0x180058bad  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058bb2  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180058bb6  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058bbd  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x180058bc4  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180058bc9  mov     rcx, [rbp+8]; this
0x180058bcd  test    eax, eax
0x180058bcf  jns     short loc_180058BEA
0x180058bd1  mov     r9d, eax; char *
0x180058bd4  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180058bdb  mov     edx, 4D4h; void *
0x180058be0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058be5  jmp     loc_180058C9C
0x180058bea  mov     [rbp+arg_10], 0
0x180058bf1  mov     [rbp+arg_18], 4
0x180058bf8  lea     rax, [rbp+arg_18]
0x180058bfc  mov     [rsp+50h+pcbData], rax; pcbData
0x180058c01  lea     rax, [rbp+arg_10]
0x180058c05  mov     [rsp+50h+pvData], rax; pvData
0x180058c0a  mov     [rsp+50h+pdwType], 0; pdwType
0x180058c13  mov     r9d, 20000010h; dwFlags
0x180058c19  lea     r8, Value; "AnyoneReadOOBECompleted"
0x180058c20  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180058c24  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058c2b  call    cs:__imp_RegGetValueW
0x180058c31  cmp     [rbp+arg_10], 0
0x180058c35  jnz     short loc_180058C9C
0x180058c37  mov     [rbp+var_10], ebx
0x180058c3a  mov     eax, ebx
0x180058c3c  shr     eax, 1Fh
0x180058c3f  mov     byte ptr [rbp+arg_8], al
0x180058c42  lea     r8, [rbp+arg_8]
0x180058c46  lea     rdx, byte_18011AF8C
0x180058c4d  lea     rcx, byte_18011AF80
0x180058c54  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x180058c59  mov     eax, cs:dword_18011AFC0
0x180058c5f  inc     eax
0x180058c61  mov     [rbp+arg_8], eax
0x180058c64  lea     r8, [rbp+arg_8]
0x180058c68  lea     rdx, dword_18011AFC0
0x180058c6f  lea     rcx, byte_18011AF80; struct OOBE::Health::details::HealthInfoHeader *
0x180058c76  call    ??$SetHealthEventValueMember@H@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAHAEBH@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<int>(int &,int const &)
0x180058c7b  test    ebx, ebx
0x180058c7d  jns     short loc_180058C8F
0x180058c7f  lea     r8, [rbp+var_10]
0x180058c83  lea     rdx, dword_18011AFBC
0x180058c8a  call    ??$SetHealthEventValueMember@J@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAJAEBJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(long &,long const &)
0x180058c8f  lea     rcx, byte_18011AF80; this
0x180058c96  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x180058c9b  nop
0x180058c9c  lea     rcx, [rbp+lpSubKey]
0x180058ca0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058ca5  mov     rbx, [rsp+50h+arg_0]
0x180058caa  add     rsp, 50h
0x180058cae  pop     rbp
0x180058caf  retn
```
