# tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(void)

- ea: `0x18002e708`
- end: `0x18002e794`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bc5c`

## callees

- `0x180027294`
- `0x180027d0c`
- `0x18002e708`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e780`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e708  mov     [rsp+arg_10], rbx
0x18002e70d  push    rdi
0x18002e70e  sub     rsp, 20h
0x18002e712  cmp     qword ptr [rcx], 0
0x18002e716  mov     rdi, rcx
0x18002e719  jnz     short loc_18002E786
0x18002e71b  lea     rcx, [rsp+28h+pv]
0x18002e720  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>,>(void)
0x18002e725  mov     rdx, [rax]
0x18002e728  mov     qword ptr [rax], 0
0x18002e72f  mov     rbx, [rdi]
0x18002e732  mov     [rdi], rdx
0x18002e735  test    rbx, rbx
0x18002e738  jz      short loc_18002E75B
0x18002e73a  or      eax, 0FFFFFFFFh
0x18002e73d  lock xadd [rbx+118h], eax
0x18002e745  cmp     eax, 1
0x18002e748  jnz     short loc_18002E75B
0x18002e74a  mov     rcx, rbx
0x18002e74d  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x18002e752  mov     rcx, rbx; pv
0x18002e755  call    cs:__imp_CoTaskMemFree
0x18002e75b  mov     rbx, [rsp+28h+pv]
0x18002e760  test    rbx, rbx
0x18002e763  jz      short loc_18002E786
0x18002e765  or      eax, 0FFFFFFFFh
0x18002e768  lock xadd [rbx+118h], eax
0x18002e770  cmp     eax, 1
0x18002e773  jnz     short loc_18002E786
0x18002e775  mov     rcx, rbx
0x18002e778  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x18002e77d  mov     rcx, rbx; pv
0x18002e780  call    cs:__imp_CoTaskMemFree
0x18002e786  mov     rbx, [rsp+28h+arg_10]
0x18002e78b  mov     rax, rdi
0x18002e78e  add     rsp, 20h
0x18002e792  pop     rdi
0x18002e793  retn
```
