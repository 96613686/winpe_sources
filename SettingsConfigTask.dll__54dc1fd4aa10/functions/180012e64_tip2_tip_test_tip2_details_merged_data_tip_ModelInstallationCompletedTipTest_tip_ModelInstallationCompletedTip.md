# tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(void)

- ea: `0x180012e64`
- end: `0x180012e99`
- name: `??C?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@1@XZ`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001871c`
- `0x1800227e8`
- `0x180022861`

## callees

- `0x180012e64`
- `0x18001d208`
- `0x18001e14c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
        void **a1,
        void **a2)
{
  void **v3; // rax
  volatile signed __int32 *v4; // rcx

  v3 = tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(a1);
  v4 = (volatile signed __int32 *)*v3;
  *a2 = *v3;
  if ( v4 )
    _InterlockedIncrement(v4 + 70);
  tip2::details::shared_data<0,0,0>::begin_update((char *)*a2 + 8);
  return a2;
}

```

## disassembly

```asm
0x180012e64  push    rbx
0x180012e66  sub     rsp, 20h
0x180012e6a  mov     rbx, rdx
0x180012e6d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(void)
0x180012e72  mov     rcx, [rax]
0x180012e75  mov     [rbx], rcx
0x180012e78  test    rcx, rcx
0x180012e7b  jz      short loc_180012E84
0x180012e7d  lock inc dword ptr [rcx+118h]
0x180012e84  mov     rcx, [rbx]
0x180012e87  add     rcx, 8
0x180012e8b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180012e90  mov     rax, rbx
0x180012e93  add     rsp, 20h
0x180012e97  pop     rbx
0x180012e98  retn
```
