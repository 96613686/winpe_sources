# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::StartInstall(winrt::Windows::System::Update::SystemUpdateStartInstallAction const &)

- ea: `0x180024c54`
- end: `0x180024ccf`
- name: `?StartInstall@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAAXAEBW4SystemUpdateStartInstallAction@3456@@Z`
- size: `123`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this, const enum winrt::Windows::System::Update::SystemUpdateStartInstallAction *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024c20`

## callees

- `0x180022a0c`
- `0x18002486c`
- `0x180024c54`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180024ca4`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::StartInstall(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this,
        const enum winrt::Windows::System::Update::SystemUpdateStartInstallAction *a2)
{
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v3; // rcx
  int v4; // eax
  int v5; // [rsp+20h] [rbp-28h]
  const wil::ResultException *v6; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(this, &v9);
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(
      v3,
      *(_DWORD *)a2 == 1);
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v9 + 168LL))(
           v9,
           0xFFFFFFFFLL,
           0,
           L"ScanTriggerWinRtApi");
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x38F,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v4,
        v5);
    if ( v9 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v9);
  }
  catch ( const wil::ResultException *v6 )
  {
    *((_DWORD *)this + 14) = *((_DWORD *)v6 + 8);
    throw;
  }
}

```

## disassembly

```asm
0x180024c54  mov     [rsp+arg_0], rcx
0x180024c59  push    rbx
0x180024c5a  sub     rsp, 40h
0x180024c5e  mov     rbx, rdx
0x180024c61  lea     rdx, [rsp+48h+arg_10]
0x180024c66  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180024c6b  nop
0x180024c6c  cmp     dword ptr [rbx], 1
0x180024c6f  setz    dl; bool
0x180024c72  call    ?SetAutomaticReboot@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(bool)
0x180024c77  mov     rcx, [rsp+48h+arg_10]
0x180024c7c  mov     rax, [rcx]
0x180024c7f  xor     r8d, r8d
0x180024c82  or      edx, 0FFFFFFFFh
0x180024c85  lea     r9, aScantriggerwin; "ScanTriggerWinRtApi"
0x180024c8c  mov     rax, [rax+0A8h]
0x180024c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c98  mov     rcx, [rsp+48h]; this
0x180024c9d  test    eax, eax
0x180024c9f  jns     short loc_180024CB6
0x180024ca1  mov     r9d, eax; char *
0x180024ca4  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024cab  mov     edx, 38Fh; void *
0x180024cb0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024cb6  cmp     [rsp+48h+arg_10], 0
0x180024cbc  jz      short loc_180024CC9
0x180024cbe  lea     rcx, [rsp+48h+arg_10]
0x180024cc3  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024cc8  nop
0x180024cc9  add     rsp, 40h
0x180024ccd  pop     rbx
0x180024cce  retn
```
