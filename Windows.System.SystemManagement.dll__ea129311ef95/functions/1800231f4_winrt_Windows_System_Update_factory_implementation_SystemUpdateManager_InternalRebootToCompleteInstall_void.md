# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InternalRebootToCompleteInstall(void)

- ea: `0x1800231f4`
- end: `0x180023280`
- name: `?InternalRebootToCompleteInstall@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAXXZ`
- size: `140`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023b1c`
- `0x180023bec`

## callees

- `0x180022a0c`
- `0x1800231f4`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180023256`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InternalRebootToCompleteInstall(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  int v1; // eax
  const wil::ResultException *v2; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v5; // [rsp+68h] [rbp+10h] BYREF
  __int64 v6; // [rsp+70h] [rbp+18h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(this, &v6);
    v5 = 0;
    v1 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v6 + 160LL))(v6, 4294967283LL, 0, &v5);
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v1,
        0);
    if ( v6 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v6);
  }
  catch ( const wil::ResultException *v2 )
  {
    *((_DWORD *)this + 14) = *((_DWORD *)v2 + 8);
    throw;
  }
}

```

## disassembly

```asm
0x1800231f4  mov     [rsp+arg_0], rcx
0x1800231f9  sub     rsp, 58h
0x1800231fd  lea     rdx, [rsp+58h+arg_10]
0x180023202  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180023207  nop
0x180023208  mov     [rsp+58h+arg_8], 0
0x180023210  mov     rcx, [rsp+58h+arg_10]
0x180023215  mov     rax, [rcx]
0x180023218  xorps   xmm0, xmm0
0x18002321b  movsd   [rsp+58h+var_28], xmm0
0x180023221  mov     [rsp+58h+var_30], 1
0x180023229  mov     [rsp+58h+var_38], 0; int
0x180023231  lea     r9, [rsp+58h+arg_8]
0x180023236  xor     r8d, r8d
0x180023239  mov     edx, 0FFFFFFF3h
0x18002323e  mov     rax, [rax+0A0h]
0x180023245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002324a  mov     rcx, [rsp+58h]; this
0x18002324f  test    eax, eax
0x180023251  jns     short loc_180023268
0x180023253  mov     r9d, eax; char *
0x180023256  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002325d  mov     edx, 3B1h; void *
0x180023262  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023268  cmp     [rsp+58h+arg_10], 0
0x18002326e  jz      short loc_18002327B
0x180023270  lea     rcx, [rsp+58h+arg_10]
0x180023275  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x18002327a  nop
0x18002327b  add     rsp, 58h
0x18002327f  retn
```
