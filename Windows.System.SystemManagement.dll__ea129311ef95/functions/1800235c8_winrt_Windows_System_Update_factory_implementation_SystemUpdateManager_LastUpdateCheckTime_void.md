# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastUpdateCheckTime(void)

- ea: `0x1800235c8`
- end: `0x180023664`
- name: `?LastUpdateCheckTime@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026340`

## callees

- `0x180022a0c`
- `0x1800235c8`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x18002361b`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastUpdateCheckTime(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  int v4; // eax
  _QWORD *result; // rax
  const wil::ResultException *v6; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v12);
    *((_DWORD *)a1 + 14) = 0;
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 72LL))(v12, &v11);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v4,
        (int)v6);
    *a2 = v11;
    if ( v12 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v12);
    result = a2;
  }
  catch ( const wil::ResultException *v6 )
  {
    *((_DWORD *)a1 + 14) = *((_DWORD *)v6 + 8);
    *a2 = 0;
    return a2;
  }
  catch ( ... )
  {
    *((_DWORD *)a1 + 14) = -2147467259;
    *a2 = 0;
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x1800235c8  mov     [rsp+arg_8], rdx
0x1800235cd  mov     [rsp+arg_0], rcx
0x1800235d2  push    rbx
0x1800235d3  push    rdi
0x1800235d4  sub     rsp, 38h
0x1800235d8  mov     rbx, rdx
0x1800235db  mov     rdi, rcx
0x1800235de  lea     rdx, [rsp+48h+arg_18]
0x1800235e3  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x1800235e8  nop
0x1800235e9  mov     dword ptr [rdi+38h], 0
0x1800235f0  mov     [rsp+48h+arg_10], 0
0x1800235f9  mov     rcx, [rsp+48h+arg_18]
0x1800235fe  mov     rax, [rcx]
0x180023601  lea     rdx, [rsp+48h+arg_10]
0x180023606  mov     rax, [rax+48h]
0x18002360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002360f  mov     rcx, [rsp+48h]; this
0x180023614  test    eax, eax
0x180023616  jns     short loc_18002362C
0x180023618  mov     r9d, eax; char *
0x18002361b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180023622  mov     edx, 162h; void *
0x180023627  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002362c  mov     ecx, dword ptr [rsp+48h+arg_10+4]
0x180023630  shl     rcx, 20h
0x180023634  mov     eax, dword ptr [rsp+48h+arg_10]
0x180023638  or      rcx, rax
0x18002363b  mov     [rbx], rcx
0x18002363e  cmp     [rsp+48h+arg_18], 0
0x180023644  jz      short loc_180023650
0x180023646  lea     rcx, [rsp+48h+arg_18]
0x18002364b  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180023650  mov     rax, rbx
0x180023653  jmp     short loc_18002365C
0x180023655  jmp     short $+2
0x180023657  mov     rax, [rsp+48h+arg_8]
0x18002365c  add     rsp, 38h
0x180023660  pop     rdi
0x180023661  pop     rbx
0x180023662  retn
```
