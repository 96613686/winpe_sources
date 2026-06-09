# tip2::tip_test<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>::start(void)

- ea: `0x180025c8c`
- end: `0x180025d20`
- name: `?start@?$tip_test@V?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d208`

## callees

- `0x180007694`
- `0x180019e00`
- `0x18001b14c`
- `0x180020c30`
- `0x180025130`
- `0x180025af0`
- `0x180025c8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025cc7`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>::start(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x150u);
    if ( !v5 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180025c8c  mov     [rsp+arg_8], rbx
0x180025c91  push    rdi
0x180025c92  sub     rsp, 20h
0x180025c96  mov     rax, [rcx]
0x180025c99  mov     rdi, rdx
0x180025c9c  mov     rbx, rcx
0x180025c9f  test    rax, rax
0x180025ca2  jz      short loc_180025CBC
0x180025ca4  cmp     qword ptr [rax+0F8h], 0
0x180025cac  jnz     short loc_180025CB7
0x180025cae  test    dword ptr [rax+48h], 100h
0x180025cb5  jz      short loc_180025CBC
0x180025cb7  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>::reset(void)
0x180025cbc  cmp     qword ptr [rbx], 0
0x180025cc0  jnz     short loc_180025CFD
0x180025cc2  mov     ecx, 150h; cb
0x180025cc7  call    cs:__imp_CoTaskMemAlloc
0x180025ccd  test    rax, rax
0x180025cd0  jz      short loc_180025D1A
0x180025cd2  mov     rcx, rax
0x180025cd5  call    ??0?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>(void)
0x180025cda  mov     rcx, [rbx]; pv
0x180025cdd  mov     [rsp+28h+arg_0], 0
0x180025ce6  mov     [rbx], rax
0x180025ce9  test    rcx, rcx
0x180025cec  jz      short loc_180025CF3
0x180025cee  call    ?Release@?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::Release(void)
0x180025cf3  lea     rcx, [rsp+28h+arg_0]
0x180025cf8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>,wil::err_returncode_policy>(void)
0x180025cfd  mov     rcx, [rbx]
0x180025d00  mov     rdx, rdi
0x180025d03  add     rcx, 8
0x180025d07  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180025d0c  mov     rbx, [rsp+28h+arg_8]
0x180025d11  mov     rax, rdi
0x180025d14  add     rsp, 20h
0x180025d18  pop     rdi
0x180025d19  retn
0x180025d1a  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
