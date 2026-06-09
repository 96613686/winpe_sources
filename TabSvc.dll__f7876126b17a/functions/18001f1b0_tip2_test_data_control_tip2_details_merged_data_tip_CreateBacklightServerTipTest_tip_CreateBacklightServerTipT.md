# tip2::test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(void)

- ea: `0x18001f1b0`
- end: `0x18001f1df`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800194b0`
- `0x18002fefe`

## callees

- `0x18001f170`
- `0x18001f1b0`
- `0x180028f78`
- `0x18002a1e4`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(
        void **a1)
{
  char *v2; // rcx

  v2 = (char *)*a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update(v2 + 8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::reset(a1);
  }
  return wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(a1);
}

```

## disassembly

```asm
0x18001f1b0  push    rbx
0x18001f1b2  sub     rsp, 20h
0x18001f1b6  mov     rbx, rcx
0x18001f1b9  mov     rcx, [rcx]
0x18001f1bc  test    rcx, rcx
0x18001f1bf  jz      short loc_18001F1D2
0x18001f1c1  add     rcx, 8
0x18001f1c5  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x18001f1ca  mov     rcx, rbx
0x18001f1cd  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::reset(void)
0x18001f1d2  mov     rcx, rbx
0x18001f1d5  add     rsp, 20h
0x18001f1d9  pop     rbx
0x18001f1da  jmp     ??1?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(void)
```
