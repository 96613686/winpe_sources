# tip2::tip_test<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::start(void)

- ea: `0x1400271cc`
- end: `0x140027260`
- name: `?start@?$tip_test@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001ae6c`

## callees

- `0x14000b524`
- `0x14001b06c`
- `0x14001bb98`
- `0x1400235f0`
- `0x140026d70`
- `0x1400270ac`
- `0x1400271cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140027207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140027207`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::start(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x1C8u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x1400271cc  mov     [rsp+arg_8], rbx
0x1400271d1  push    rdi
0x1400271d2  sub     rsp, 20h
0x1400271d6  mov     rax, [rcx]
0x1400271d9  mov     rdi, rdx
0x1400271dc  mov     rbx, rcx
0x1400271df  test    rax, rax
0x1400271e2  jz      short loc_1400271FC
0x1400271e4  cmp     qword ptr [rax+0F8h], 0
0x1400271ec  jnz     short loc_1400271F7
0x1400271ee  test    dword ptr [rax+48h], 100h
0x1400271f5  jz      short loc_1400271FC
0x1400271f7  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>::reset(void)
0x1400271fc  cmp     qword ptr [rbx], 0
0x140027200  jnz     short loc_14002723D
0x140027202  mov     ecx, 1C8h; cb
0x140027207  call    cs:__imp_CoTaskMemAlloc
0x14002720d  test    rax, rax
0x140027210  jz      short loc_14002725A
0x140027212  mov     rcx, rax
0x140027215  call    ??0?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>(void)
0x14002721a  mov     rcx, [rbx]; pv
0x14002721d  mov     [rsp+28h+arg_0], 0
0x140027226  mov     [rbx], rax
0x140027229  test    rcx, rcx
0x14002722c  jz      short loc_140027233
0x14002722e  call    ?Release@?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::Release(void)
0x140027233  lea     rcx, [rsp+28h+arg_0]
0x140027238  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>,wil::err_returncode_policy>(void)
0x14002723d  mov     rcx, [rbx]
0x140027240  mov     rdx, rdi
0x140027243  add     rcx, 8
0x140027247  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x14002724c  mov     rbx, [rsp+28h+arg_8]
0x140027251  mov     rax, rdi
0x140027254  add     rsp, 20h
0x140027258  pop     rdi
0x140027259  retn
0x14002725a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
