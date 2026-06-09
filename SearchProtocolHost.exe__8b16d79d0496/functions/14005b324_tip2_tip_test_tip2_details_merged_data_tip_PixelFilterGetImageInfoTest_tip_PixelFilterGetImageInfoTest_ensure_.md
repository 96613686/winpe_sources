# tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::ensure_data(void)

- ea: `0x14005b324`
- end: `0x14005b37d`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005838c`
- `0x140058930`

## callees

- `0x140032fa0`
- `0x140058404`
- `0x1400586ac`
- `0x14005a8d8`
- `0x14005b324`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005b338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005b338`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 ImageInfo; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

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
0x14005b324  push    rbx
0x14005b326  sub     rsp, 20h
0x14005b32a  cmp     qword ptr [rcx], 0
0x14005b32e  mov     rbx, rcx
0x14005b331  jnz     short loc_14005B36E
0x14005b333  mov     ecx, 140h; cb
0x14005b338  call    cs:__imp_CoTaskMemAlloc
0x14005b33e  test    rax, rax
0x14005b341  jz      short loc_14005B377
0x14005b343  mov     rcx, rax
0x14005b346  call    ??0?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>(void)
0x14005b34b  mov     rcx, [rbx]; pv
0x14005b34e  mov     [rsp+28h+arg_0], 0
0x14005b357  mov     [rbx], rax
0x14005b35a  test    rcx, rcx
0x14005b35d  jz      short loc_14005B364
0x14005b35f  call    ?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)
0x14005b364  lea     rcx, [rsp+28h+arg_0]
0x14005b369  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x14005b36e  mov     rax, rbx
0x14005b371  add     rsp, 20h
0x14005b375  pop     rbx
0x14005b376  retn
0x14005b377  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
