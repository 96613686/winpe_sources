# tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(void)

- ea: `0x180013ecc`
- end: `0x180013f16`
- name: `??1?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180102b7c`
- `0x18010313c`

## callees

- `0x180013bbc`
- `0x180013ecc`
- `0x1800149fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013efd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013efd`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x180013ecc  mov     [rsp+arg_8], rbx
0x180013ed1  push    rdi
0x180013ed2  sub     rsp, 20h
0x180013ed6  mov     rbx, [rcx+38h]
0x180013eda  mov     rdi, rcx
0x180013edd  test    rbx, rbx
0x180013ee0  jz      short loc_180013F03
0x180013ee2  or      eax, 0FFFFFFFFh
0x180013ee5  lock xadd [rbx+118h], eax
0x180013eed  cmp     eax, 1
0x180013ef0  jnz     short loc_180013F03
0x180013ef2  mov     rcx, rbx
0x180013ef5  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x180013efa  mov     rcx, rbx; pv
0x180013efd  call    cs:__imp_CoTaskMemFree
0x180013f03  lea     rcx, [rdi+8]; this
0x180013f07  mov     rbx, [rsp+28h+arg_8]
0x180013f0c  add     rsp, 20h
0x180013f10  pop     rdi
0x180013f11  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
