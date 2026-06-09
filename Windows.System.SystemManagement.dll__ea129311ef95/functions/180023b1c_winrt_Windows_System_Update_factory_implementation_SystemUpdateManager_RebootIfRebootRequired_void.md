# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::RebootIfRebootRequired(void)

- ea: `0x180023b1c`
- end: `0x180023bab`
- name: `?RebootIfRebootRequired@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAXXZ`
- size: `143`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001fbd0`

## callees

- `0x180020f4c`
- `0x180022a0c`
- `0x1800231f4`
- `0x180023b1c`
- `0x18002486c`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180023b69`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::RebootIfRebootRequired(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  int v2; // eax
  const wil::ResultException *v3; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int16 v6; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  if ( winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetAutomaticReboot(this) )
  {
    v6 = 0;
    try
    {
      winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(this, &v7);
      v2 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v7 + 112LL))(v7, &v6);
      if ( v2 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x39D,
          (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
          (const char *)(unsigned int)v2,
          (int)v3);
      if ( v6 == -1 )
      {
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(retaddr, 0);
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InternalRebootToCompleteInstall(this);
      }
      if ( v7 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v7);
    }
    catch ( const wil::ResultException *v3 )
    {
      *((_DWORD *)this + 14) = *((_DWORD *)v3 + 8);
      throw;
    }
  }
}

```

## disassembly

```asm
0x180023b1c  mov     [rsp+arg_0], rcx
0x180023b21  push    rbx
0x180023b22  sub     rsp, 30h
0x180023b26  mov     rbx, rcx
0x180023b29  call    ?GetAutomaticReboot@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetAutomaticReboot(void)
0x180023b2e  test    al, al
0x180023b30  jz      short loc_180023BA5
0x180023b32  xor     eax, eax
0x180023b34  mov     [rsp+38h+arg_8], ax
0x180023b39  lea     rdx, [rsp+38h+arg_10]
0x180023b3e  mov     rcx, rbx; this
0x180023b41  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180023b46  nop
0x180023b47  mov     rcx, [rsp+38h+arg_10]
0x180023b4c  mov     rax, [rcx]
0x180023b4f  lea     rdx, [rsp+38h+arg_8]
0x180023b54  mov     rax, [rax+70h]
0x180023b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b5d  mov     rcx, [rsp+38h]; this
0x180023b62  test    eax, eax
0x180023b64  jns     short loc_180023B7A
0x180023b66  mov     r9d, eax; char *
0x180023b69  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180023b70  mov     edx, 39Dh; void *
0x180023b75  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023b7a  cmp     [rsp+38h+arg_8], 0FFFFh
0x180023b80  jnz     short loc_180023B92
0x180023b82  xor     edx, edx; bool
0x180023b84  call    ?SetAutomaticReboot@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(bool)
0x180023b89  mov     rcx, rbx; this
0x180023b8c  call    ?InternalRebootToCompleteInstall@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAXXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InternalRebootToCompleteInstall(void)
0x180023b91  nop
0x180023b92  cmp     [rsp+38h+arg_10], 0
0x180023b98  jz      short loc_180023BA5
0x180023b9a  lea     rcx, [rsp+38h+arg_10]
0x180023b9f  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180023ba4  nop
0x180023ba5  add     rsp, 30h
0x180023ba9  pop     rbx
0x180023baa  retn
```
