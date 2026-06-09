# tip2::tip_test<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::start(void)

- ea: `0x18003a4ec`
- end: `0x18003a580`
- name: `?start@?$tip_test@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034ca0`

## callees

- `0x180010010`
- `0x1800339b0`
- `0x18003448c`
- `0x180036eac`
- `0x18003997c`
- `0x18003a350`
- `0x18003a4ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a527`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  void *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x18003a4ec  mov     [rsp+arg_8], rbx
0x18003a4f1  push    rdi
0x18003a4f2  sub     rsp, 20h
0x18003a4f6  mov     rax, [rcx]
0x18003a4f9  mov     rdi, rdx
0x18003a4fc  mov     rbx, rcx
0x18003a4ff  test    rax, rax
0x18003a502  jz      short loc_18003A51C
0x18003a504  cmp     qword ptr [rax+0F8h], 0
0x18003a50c  jnz     short loc_18003A517
0x18003a50e  test    dword ptr [rax+48h], 100h
0x18003a515  jz      short loc_18003A51C
0x18003a517  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::reset(void)
0x18003a51c  cmp     qword ptr [rbx], 0
0x18003a520  jnz     short loc_18003A55D
0x18003a522  mov     ecx, 120h; cb
0x18003a527  call    cs:__imp_CoTaskMemAlloc
0x18003a52d  test    rax, rax
0x18003a530  jz      short loc_18003A57A
0x18003a532  mov     rcx, rax
0x18003a535  call    ??0?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>(void)
0x18003a53a  mov     rcx, [rbx]; pv
0x18003a53d  mov     [rsp+28h+arg_0], 0
0x18003a546  mov     [rbx], rax
0x18003a549  test    rcx, rcx
0x18003a54c  jz      short loc_18003A553
0x18003a54e  call    ?Release@?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::Release(void)
0x18003a553  lea     rcx, [rsp+28h+arg_0]
0x18003a558  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>(void)
0x18003a55d  mov     rcx, [rbx]
0x18003a560  mov     rdx, rdi
0x18003a563  add     rcx, 8
0x18003a567  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18003a56c  mov     rbx, [rsp+28h+arg_8]
0x18003a571  mov     rax, rdi
0x18003a574  add     rsp, 20h
0x18003a578  pop     rdi
0x18003a579  retn
0x18003a57a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
