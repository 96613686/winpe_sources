# tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(void)

- ea: `0x180012ea0`
- end: `0x180012ed5`
- name: `??C?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@1@XZ`
- size: `53`
- prototype: `__int64 *__fastcall(__int64, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013400`
- `0x180018b80`
- `0x18001c150`

## callees

- `0x180012ea0`
- `0x18001d208`
- `0x18001e1ac`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx

  v3 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data();
  v4 = *v3;
  *a2 = *v3;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(*a2 + 8);
  return a2;
}

```

## disassembly

```asm
0x180012ea0  push    rbx
0x180012ea2  sub     rsp, 20h
0x180012ea6  mov     rbx, rdx
0x180012ea9  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x180012eae  mov     rcx, [rax]
0x180012eb1  mov     [rbx], rcx
0x180012eb4  test    rcx, rcx
0x180012eb7  jz      short loc_180012EC0
0x180012eb9  lock inc dword ptr [rcx+118h]
0x180012ec0  mov     rcx, [rbx]
0x180012ec3  add     rcx, 8
0x180012ec7  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180012ecc  mov     rax, rbx
0x180012ecf  add     rsp, 20h
0x180012ed3  pop     rbx
0x180012ed4  retn
```
