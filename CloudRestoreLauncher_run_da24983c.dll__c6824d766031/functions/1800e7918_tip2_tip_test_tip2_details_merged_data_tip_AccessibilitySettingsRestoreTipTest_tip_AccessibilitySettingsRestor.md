# tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::ensure_data(void)

- ea: `0x1800e7918`
- end: `0x1800e7971`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e6490`
- `0x1800e787c`

## callees

- `0x180012ab4`
- `0x1800e58ec`
- `0x1800e5c3c`
- `0x1800e6648`
- `0x1800e7918`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800e792c`
- `OLE32!CoTaskMemAlloc` at `0x1800e792c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x128u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800e7918  push    rbx
0x1800e791a  sub     rsp, 20h
0x1800e791e  cmp     qword ptr [rcx], 0
0x1800e7922  mov     rbx, rcx
0x1800e7925  jnz     short loc_1800E7962
0x1800e7927  mov     ecx, 128h; cb
0x1800e792c  call    cs:__imp_CoTaskMemAlloc
0x1800e7932  test    rax, rax
0x1800e7935  jz      short loc_1800E796B
0x1800e7937  mov     rcx, rax
0x1800e793a  call    ??0?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>(void)
0x1800e793f  mov     rcx, [rbx]; pv
0x1800e7942  mov     [rsp+28h+arg_0], 0
0x1800e794b  mov     [rbx], rax
0x1800e794e  test    rcx, rcx
0x1800e7951  jz      short loc_1800E7958
0x1800e7953  call    ?Release@?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>::Release(void)
0x1800e7958  lea     rcx, [rsp+28h+arg_0]
0x1800e795d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>,wil::err_returncode_policy>(void)
0x1800e7962  mov     rax, rbx
0x1800e7965  add     rsp, 20h
0x1800e7969  pop     rbx
0x1800e796a  retn
0x1800e796b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
