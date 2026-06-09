# tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::Release(void)

- ea: `0x1800365d0`
- end: `0x180036608`
- name: `?Release@?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003601c`
- `0x18004a514`
- `0x18004a658`

## callees

- `0x180036038`
- `0x1800365d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365f5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::~merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800365d0  mov     [rsp+arg_0], rbx
0x1800365d5  push    rdi
0x1800365d6  sub     rsp, 20h
0x1800365da  mov     rdi, rcx
0x1800365dd  or      ebx, 0FFFFFFFFh
0x1800365e0  lock xadd [rcx+128h], ebx
0x1800365e8  sub     ebx, 1
0x1800365eb  jnz     short loc_1800365FB
0x1800365ed  call    ??1?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::~merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>(void)
0x1800365f2  mov     rcx, rdi; pv
0x1800365f5  call    cs:__imp_CoTaskMemFree
0x1800365fb  mov     eax, ebx
0x1800365fd  mov     rbx, [rsp+28h+arg_0]
0x180036602  add     rsp, 20h
0x180036606  pop     rdi
0x180036607  retn
```
