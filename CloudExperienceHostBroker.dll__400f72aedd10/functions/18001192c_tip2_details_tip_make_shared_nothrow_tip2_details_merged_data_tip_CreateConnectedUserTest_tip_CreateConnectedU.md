# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,>(void)

- ea: `0x18001192c`
- end: `0x18001195f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `51`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012dc0`
- `0x180019454`

## callees

- `0x18000f178`
- `0x18001192c`
- `0x180011b0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001193a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001193a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,>(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx

  v2 = CoTaskMemAlloc(0x128u);
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *a1 = tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>(v2);
  return a1;
}

```

## disassembly

```asm
0x18001192c  push    rbx
0x18001192e  sub     rsp, 20h
0x180011932  mov     rbx, rcx
0x180011935  mov     ecx, 128h; cb
0x18001193a  call    cs:__imp_CoTaskMemAlloc
0x180011940  test    rax, rax
0x180011943  jz      short loc_180011959
0x180011945  mov     rcx, rax
0x180011948  call    ??0?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>(void)
0x18001194d  mov     [rbx], rax
0x180011950  mov     rax, rbx
0x180011953  add     rsp, 20h
0x180011957  pop     rbx
0x180011958  retn
0x180011959  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
