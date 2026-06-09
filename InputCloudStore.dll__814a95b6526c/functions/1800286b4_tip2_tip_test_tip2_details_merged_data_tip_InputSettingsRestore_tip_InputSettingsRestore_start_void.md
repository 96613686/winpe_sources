# tip2::tip_test<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>::start(void)

- ea: `0x1800286b4`
- end: `0x180028748`
- name: `?start@?$tip_test@V?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026db4`

## callees

- `0x180007694`
- `0x180025af0`
- `0x180026c70`
- `0x180026d08`
- `0x180028180`
- `0x180028614`
- `0x1800286b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800286ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800286ef`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x1800286b4  mov     [rsp+arg_8], rbx
0x1800286b9  push    rdi
0x1800286ba  sub     rsp, 20h
0x1800286be  mov     rax, [rcx]
0x1800286c1  mov     rdi, rdx
0x1800286c4  mov     rbx, rcx
0x1800286c7  test    rax, rax
0x1800286ca  jz      short loc_1800286E4
0x1800286cc  cmp     qword ptr [rax+0F8h], 0
0x1800286d4  jnz     short loc_1800286DF
0x1800286d6  test    dword ptr [rax+48h], 100h
0x1800286dd  jz      short loc_1800286E4
0x1800286df  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>::reset(void)
0x1800286e4  cmp     qword ptr [rbx], 0
0x1800286e8  jnz     short loc_180028725
0x1800286ea  mov     ecx, 120h; cb
0x1800286ef  call    cs:__imp_CoTaskMemAlloc
0x1800286f5  test    rax, rax
0x1800286f8  jz      short loc_180028742
0x1800286fa  mov     rcx, rax
0x1800286fd  call    ??0?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>(void)
0x180028702  mov     rcx, [rbx]; pv
0x180028705  mov     [rsp+28h+arg_0], 0
0x18002870e  mov     [rbx], rax
0x180028711  test    rcx, rcx
0x180028714  jz      short loc_18002871B
0x180028716  call    ?Release@?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::Release(void)
0x18002871b  lea     rcx, [rsp+28h+arg_0]
0x180028720  call    ??1?$com_ptr_t@V?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>,wil::err_returncode_policy>(void)
0x180028725  mov     rcx, [rbx]
0x180028728  mov     rdx, rdi
0x18002872b  add     rcx, 8
0x18002872f  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180028734  mov     rbx, [rsp+28h+arg_8]
0x180028739  mov     rax, rdi
0x18002873c  add     rsp, 20h
0x180028740  pop     rdi
0x180028741  retn
0x180028742  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
