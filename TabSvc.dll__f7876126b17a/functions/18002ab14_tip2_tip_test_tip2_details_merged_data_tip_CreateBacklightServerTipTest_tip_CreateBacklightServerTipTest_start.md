# tip2::tip_test<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::start(void)

- ea: `0x18002ab14`
- end: `0x18002aba8`
- name: `?start@?$tip_test@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800194b0`

## callees

- `0x180019314`
- `0x18001eb2c`
- `0x18001f170`
- `0x180024ed4`
- `0x180028520`
- `0x18002a1e4`
- `0x18002ab14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab4f`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 BacklightServerTip; // rax
  void *v8; // rcx
  void *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x130u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    BacklightServerTip = tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>((__int64)v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = BacklightServerTip;
    if ( v8 )
      tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x18002ab14  mov     [rsp+arg_8], rbx
0x18002ab19  push    rdi
0x18002ab1a  sub     rsp, 20h
0x18002ab1e  mov     rax, [rcx]
0x18002ab21  mov     rdi, rdx
0x18002ab24  mov     rbx, rcx
0x18002ab27  test    rax, rax
0x18002ab2a  jz      short loc_18002AB44
0x18002ab2c  cmp     qword ptr [rax+0F8h], 0
0x18002ab34  jnz     short loc_18002AB3F
0x18002ab36  test    dword ptr [rax+48h], 100h
0x18002ab3d  jz      short loc_18002AB44
0x18002ab3f  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::reset(void)
0x18002ab44  cmp     qword ptr [rbx], 0
0x18002ab48  jnz     short loc_18002AB8B
0x18002ab4a  mov     ecx, 130h; cb
0x18002ab4f  call    cs:__imp_CoTaskMemAlloc
0x18002ab55  test    rax, rax
0x18002ab58  jnz     short loc_18002AB60
0x18002ab5a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002ab60  mov     rcx, rax
0x18002ab63  call    ??0?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>(void)
0x18002ab68  mov     rcx, [rbx]; pv
0x18002ab6b  mov     [rsp+28h+arg_0], 0
0x18002ab74  mov     [rbx], rax
0x18002ab77  test    rcx, rcx
0x18002ab7a  jz      short loc_18002AB81
0x18002ab7c  call    ?Release@?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(void)
0x18002ab81  lea     rcx, [rsp+28h+arg_0]
0x18002ab86  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(void)
0x18002ab8b  mov     rcx, [rbx]
0x18002ab8e  mov     rdx, rdi
0x18002ab91  add     rcx, 8
0x18002ab95  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18002ab9a  mov     rbx, [rsp+28h+arg_8]
0x18002ab9f  mov     rax, rdi
0x18002aba2  add     rsp, 20h
0x18002aba6  pop     rdi
0x18002aba7  retn
```
