# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::StartCancelUpdates(void)

- ea: `0x180024bac`
- end: `0x180024c18`
- name: `?StartCancelUpdates@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024b80`

## callees

- `0x18001caa4`
- `0x180022a0c`
- `0x180024bac`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180024be4`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::StartCancelUpdates(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  int v2; // eax
  const wil::ResultException *v3; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(this, &v6);
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 416LL))(v6);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        (int)v3);
    winrt::event<winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable>>::operator()<std::nullptr_t,std::nullptr_t>((char *)this + 32);
    if ( v6 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v6);
  }
  catch ( const wil::ResultException *v3 )
  {
    *((_DWORD *)this + 14) = *((_DWORD *)v3 + 8);
    throw;
  }
}

```

## disassembly

```asm
0x180024bac  mov     [rsp+arg_0], rcx
0x180024bb1  push    rbx
0x180024bb2  sub     rsp, 30h
0x180024bb6  mov     rbx, rcx
0x180024bb9  lea     rdx, [rsp+38h+arg_8]
0x180024bbe  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180024bc3  nop
0x180024bc4  mov     rcx, [rsp+38h+arg_8]
0x180024bc9  mov     rax, [rcx]
0x180024bcc  mov     rax, [rax+1A0h]
0x180024bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd8  mov     rcx, [rsp+38h]; this
0x180024bdd  test    eax, eax
0x180024bdf  jns     short loc_180024BF5
0x180024be1  mov     r9d, eax; char *
0x180024be4  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024beb  mov     edx, 3CBh; void *
0x180024bf0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024bf5  lea     rcx, [rbx+20h]
0x180024bf9  call    ??$?R$$T$$T@?$event@U?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@winrt@@QEAAXAEB$$T0@Z
0x180024bfe  nop
0x180024bff  cmp     [rsp+38h+arg_8], 0
0x180024c05  jz      short loc_180024C12
0x180024c07  lea     rcx, [rsp+38h+arg_8]
0x180024c0c  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024c11  nop
0x180024c12  add     rsp, 30h
0x180024c16  pop     rbx
0x180024c17  retn
```
