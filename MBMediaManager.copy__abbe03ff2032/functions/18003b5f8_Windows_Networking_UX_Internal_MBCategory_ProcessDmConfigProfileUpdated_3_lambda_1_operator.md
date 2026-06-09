# _Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated_::_3_::_lambda_1_::operator()

- ea: `0x18003b5f8`
- end: `0x18003b746`
- name: `_Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated_::_3_::_lambda_1_::operator()`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180043e20`

## callees

- `0x18000867c`
- `0x180008c84`
- `0x18000a460`
- `0x18000ad20`
- `0x18001bd80`
- `0x18002cd20`
- `0x18002d8c8`
- `0x18003b5f8`
- `0x180043050`
- `0x180055dd0`

## string_xrefs

- `0x18003b683`: `Deleted. UpdateWwanProfile`
- `0x18003b68f`: `Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()`
- `0x18003b6ae`: `Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()`
- `0x18003b6d3`: `Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()`
- `0x18003b6e6`: `_ReadWwanProfileFromService failed. profileName=%ls, hr=0x%x`
- `0x18003b6f9`: `- Updated/Created. UpdateWwanProfile`
- `0x18003b6a2`: `Ignore DMConfigProfile update. profileUpdateType=%d`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated_::_3_::_lambda_1_::operator()(
        _QWORD **a1)
{
  unsigned int v2; // r9d
  int DummyWwanProfile; // eax
  int WwanProfileFromService; // eax
  int v5; // [rsp+20h] [rbp-18D8h]
  wchar_t v6[3160]; // [rsp+30h] [rbp-18C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+18F8h] [rbp+0h]

  memset_0(v6, 0, sizeof(v6));
  v2 = *((_DWORD *)a1 + 2);
  if ( v2 < 2 )
  {
    WwanProfileFromService = Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService(
                               (__int64)*a1,
                               (const wchar_t *)a1 + 6,
                               1,
                               v6);
    if ( WwanProfileFromService >= 0 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()",
        1490,
        "- Updated/Created. UpdateWwanProfile");
      Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(*a1, v6, 3, 1u, 0);
    }
    else
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()",
        0x5CDu,
        "_ReadWwanProfileFromService failed. profileName=%ls, hr=0x%x",
        (const wchar_t *)a1 + 6,
        WwanProfileFromService);
    }
  }
  else if ( v2 == 3 )
  {
    DummyWwanProfile = Windows::Networking::UX::Internal::MBCategory::_CreateDummyWwanProfile(
                         (Windows::Networking::UX::Internal::MBCategory *)*a1,
                         (const unsigned __int16 *)a1 + 6,
                         (struct WWAN_PROFILE *)v6);
    if ( DummyWwanProfile >= 0 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()",
        1471,
        "Deleted. UpdateWwanProfile");
      Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(*a1, v6, 3, 1u, 1);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x5BA,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)(unsigned int)DummyWwanProfile,
        v5);
    }
  }
  else
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBCategory::ProcessDmConfigProfileUpdated::<lambda_1>::operator ()",
      0x5D7u,
      "Ignore DMConfigProfile update. profileUpdateType=%d",
      v2);
  }
}

```

## disassembly

```asm
0x18003b5f8  mov     [rsp+arg_8], rbx
0x18003b5fd  push    rdi
0x18003b5fe  mov     eax, 18F0h
0x18003b603  call    _alloca_probe
0x18003b608  sub     rsp, rax
0x18003b60b  mov     rax, cs:__security_cookie
0x18003b612  xor     rax, rsp
0x18003b615  mov     [rsp+18F8h+var_18], rax
0x18003b61d  mov     rbx, rcx
0x18003b620  xor     edx, edx; Val
0x18003b622  lea     rcx, [rsp+18F8h+var_18C8]; void *
0x18003b627  mov     r8d, 18B0h; Size
0x18003b62d  call    memset_0
0x18003b632  mov     r9d, [rbx+8]
0x18003b636  mov     edx, r9d
0x18003b639  test    r9d, r9d
0x18003b63c  jz      short loc_18003B6BC
0x18003b63e  sub     edx, 1
0x18003b641  jz      short loc_18003B6BC
0x18003b643  sub     edx, 1
0x18003b646  jz      short loc_18003B6A2
0x18003b648  cmp     edx, 1
0x18003b64b  jnz     short loc_18003B6A2
0x18003b64d  mov     rcx, [rbx]; this
0x18003b650  lea     rdx, [rbx+0Ch]; unsigned __int16 *
0x18003b654  lea     r8, [rsp+18F8h+var_18C8]; struct WWAN_PROFILE *
0x18003b659  call    ?_CreateDummyWwanProfile@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEBGAEAUWWAN_PROFILE@@@Z; Windows::Networking::UX::Internal::MBCategory::_CreateDummyWwanProfile(ushort const *,WWAN_PROFILE &)
0x18003b65e  test    eax, eax
0x18003b660  jns     short loc_18003B683
0x18003b662  mov     rcx, [rsp+18F8h]; this
0x18003b66a  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003b671  mov     r9d, eax; char *
0x18003b674  mov     edx, 5BAh; void *
0x18003b679  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003b67e  jmp     loc_18003B725
0x18003b683  lea     r8, aDeletedUpdatew; "Deleted. UpdateWwanProfile"
0x18003b68a  mov     edx, 5BFh; unsigned int
0x18003b68f  lea     rcx, aWindowsNetwork_164; "Windows::Networking::UX::Internal::MBCa"...
0x18003b696  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003b69b  mov     byte ptr [rsp+18F8h+var_18D8], 1
0x18003b6a0  jmp     short loc_18003B70F
0x18003b6a2  lea     r8, aIgnoreDmconfig; "Ignore DMConfigProfile update. profileU"...
0x18003b6a9  mov     edx, 5D7h; unsigned int
0x18003b6ae  lea     rcx, aWindowsNetwork_164; "Windows::Networking::UX::Internal::MBCa"...
0x18003b6b5  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18003b6ba  jmp     short loc_18003B725
0x18003b6bc  mov     rcx, [rbx]
0x18003b6bf  lea     r9, [rsp+18F8h+var_18C8]
0x18003b6c4  mov     r8d, 1
0x18003b6ca  lea     rdx, [rbx+0Ch]
0x18003b6ce  call    ?_ReadWwanProfileFromService@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEBGW4MbConnectionProfileType@345@AEAUWWAN_PROFILE@@@Z; Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService(ushort const *,Windows::Networking::UX::MbConnectionProfileType,WWAN_PROFILE &)
0x18003b6d3  lea     rcx, aWindowsNetwork_164; "Windows::Networking::UX::Internal::MBCa"...
0x18003b6da  test    eax, eax
0x18003b6dc  jns     short loc_18003B6F9
0x18003b6de  lea     r9, [rbx+0Ch]
0x18003b6e2  mov     [rsp+18F8h+var_18D8], eax
0x18003b6e6  lea     r8, aReadwwanprofil; "_ReadWwanProfileFromService failed. pro"...
0x18003b6ed  mov     edx, 5CDh; unsigned int
0x18003b6f2  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18003b6f7  jmp     short loc_18003B725
0x18003b6f9  lea     r8, aUpdatedCreated; "- Updated/Created. UpdateWwanProfile"
0x18003b700  mov     edx, 5D2h; unsigned int
0x18003b705  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003b70a  mov     byte ptr [rsp+18F8h+var_18D8], 0
0x18003b70f  mov     rcx, [rbx]
0x18003b712  lea     rdx, [rsp+18F8h+var_18C8]
0x18003b717  mov     r9b, 1
0x18003b71a  mov     r8d, 3
0x18003b720  call    ?tp_UpdateWwanProfile@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUWWAN_PROFILE@@W4_WWAN_ACTIVATION_STATE@@_N2@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(WWAN_PROFILE const &,_WWAN_ACTIVATION_STATE,bool,bool)
0x18003b725  mov     rcx, [rsp+18F8h+var_18]
0x18003b72d  xor     rcx, rsp; StackCookie
0x18003b730  call    __security_check_cookie
0x18003b735  mov     rbx, [rsp+18F8h+arg_8]
0x18003b73d  add     rsp, 18F0h
0x18003b744  pop     rdi
0x18003b745  retn
```
