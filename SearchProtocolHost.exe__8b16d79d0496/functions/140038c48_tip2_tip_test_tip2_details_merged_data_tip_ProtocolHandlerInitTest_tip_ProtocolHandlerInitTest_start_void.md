# tip2::tip_test<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>>::start(void)

- ea: `0x140038c48`
- end: `0x140038cdc`
- name: `?start@?$tip_test@V?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14002d100`

## callees

- `0x14000cf28`
- `0x14000eeb8`
- `0x140025150`
- `0x140032fa0`
- `0x140037c28`
- `0x1400389f8`
- `0x140038c48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038c83`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 inited; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x140u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    inited = tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = inited;
    if ( v8 )
      tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x140038c48  mov     [rsp+arg_8], rbx
0x140038c4d  push    rdi
0x140038c4e  sub     rsp, 20h
0x140038c52  mov     rax, [rcx]
0x140038c55  mov     rdi, rdx
0x140038c58  mov     rbx, rcx
0x140038c5b  test    rax, rax
0x140038c5e  jz      short loc_140038C78
0x140038c60  cmp     qword ptr [rax+0F8h], 0
0x140038c68  jnz     short loc_140038C73
0x140038c6a  test    dword ptr [rax+48h], 100h
0x140038c71  jz      short loc_140038C78
0x140038c73  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>::reset(void)
0x140038c78  cmp     qword ptr [rbx], 0
0x140038c7c  jnz     short loc_140038CB9
0x140038c7e  mov     ecx, 140h; cb
0x140038c83  call    cs:__imp_CoTaskMemAlloc
0x140038c89  test    rax, rax
0x140038c8c  jz      short loc_140038CD6
0x140038c8e  mov     rcx, rax
0x140038c91  call    ??0?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>(void)
0x140038c96  mov     rcx, [rbx]; pv
0x140038c99  mov     [rsp+28h+arg_0], 0
0x140038ca2  mov     [rbx], rax
0x140038ca5  test    rcx, rcx
0x140038ca8  jz      short loc_140038CAF
0x140038caa  call    ?Release@?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::Release(void)
0x140038caf  lea     rcx, [rsp+28h+arg_0]
0x140038cb4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>,wil::err_returncode_policy>(void)
0x140038cb9  mov     rcx, [rbx]
0x140038cbc  mov     rdx, rdi
0x140038cbf  add     rcx, 8
0x140038cc3  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x140038cc8  mov     rbx, [rsp+28h+arg_8]
0x140038ccd  mov     rax, rdi
0x140038cd0  add     rsp, 20h
0x140038cd4  pop     rdi
0x140038cd5  retn
0x140038cd6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
