# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastUpdateInstallTime(void)

- ea: `0x18002366c`
- end: `0x180023708`
- name: `?LastUpdateInstallTime@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026380`

## callees

- `0x180022a0c`
- `0x18002366c`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x1800236bf`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastUpdateInstallTime(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  int v4; // eax
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v9);
  *((_DWORD *)a1 + 14) = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 88LL))(v9, &v8);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
      (const char *)(unsigned int)v4,
      v6);
  *a2 = v8;
  if ( v9 )
    winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18002366c  mov     [rsp+arg_8], rdx
0x180023671  mov     [rsp+arg_0], rcx
0x180023676  push    rbx
0x180023677  push    rdi
0x180023678  sub     rsp, 38h
0x18002367c  mov     rbx, rdx
0x18002367f  mov     rdi, rcx
0x180023682  lea     rdx, [rsp+48h+arg_18]
0x180023687  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x18002368c  nop
0x18002368d  mov     dword ptr [rdi+38h], 0
0x180023694  mov     [rsp+48h+arg_10], 0
0x18002369d  mov     rcx, [rsp+48h+arg_18]
0x1800236a2  mov     rax, [rcx]
0x1800236a5  lea     rdx, [rsp+48h+arg_10]
0x1800236aa  mov     rax, [rax+58h]
0x1800236ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236b3  mov     rcx, [rsp+48h]; this
0x1800236b8  test    eax, eax
0x1800236ba  jns     short loc_1800236D0
0x1800236bc  mov     r9d, eax; char *
0x1800236bf  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800236c6  mov     edx, 176h; void *
0x1800236cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800236d0  mov     ecx, dword ptr [rsp+48h+arg_10+4]
0x1800236d4  shl     rcx, 20h
0x1800236d8  mov     eax, dword ptr [rsp+48h+arg_10]
0x1800236dc  or      rcx, rax
0x1800236df  mov     [rbx], rcx
0x1800236e2  cmp     [rsp+48h+arg_18], 0
0x1800236e8  jz      short loc_1800236F4
0x1800236ea  lea     rcx, [rsp+48h+arg_18]
0x1800236ef  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x1800236f4  mov     rax, rbx
0x1800236f7  jmp     short loc_180023700
0x1800236f9  jmp     short $+2
0x1800236fb  mov     rax, [rsp+48h+arg_8]
0x180023700  add     rsp, 38h
0x180023704  pop     rdi
0x180023705  pop     rbx
0x180023706  retn
```
