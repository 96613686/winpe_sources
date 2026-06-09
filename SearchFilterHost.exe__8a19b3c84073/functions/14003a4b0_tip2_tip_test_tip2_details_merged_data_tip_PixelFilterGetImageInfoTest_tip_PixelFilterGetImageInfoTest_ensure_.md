# tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::ensure_data(void)

- ea: `0x14003a4b0`
- end: `0x14003a509`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140037af0`
- `0x14003805c`

## callees

- `0x14000b524`
- `0x140037b68`
- `0x140037db0`
- `0x140039db0`
- `0x14003a4b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003a4c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003a4c4`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 ImageInfo; // rax
  void *v5; // rcx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x140u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    ImageInfo = tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)ImageInfo;
    if ( v5 )
      tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x14003a4b0  push    rbx
0x14003a4b2  sub     rsp, 20h
0x14003a4b6  cmp     qword ptr [rcx], 0
0x14003a4ba  mov     rbx, rcx
0x14003a4bd  jnz     short loc_14003A4FA
0x14003a4bf  mov     ecx, 140h; cb
0x14003a4c4  call    cs:__imp_CoTaskMemAlloc
0x14003a4ca  test    rax, rax
0x14003a4cd  jz      short loc_14003A503
0x14003a4cf  mov     rcx, rax
0x14003a4d2  call    ??0?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>(void)
0x14003a4d7  mov     rcx, [rbx]; pv
0x14003a4da  mov     [rsp+28h+arg_0], 0
0x14003a4e3  mov     [rbx], rax
0x14003a4e6  test    rcx, rcx
0x14003a4e9  jz      short loc_14003A4F0
0x14003a4eb  call    ?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)
0x14003a4f0  lea     rcx, [rsp+28h+arg_0]
0x14003a4f5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x14003a4fa  mov     rax, rbx
0x14003a4fd  add     rsp, 20h
0x14003a501  pop     rbx
0x14003a502  retn
0x14003a503  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
