# tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(void)

- ea: `0x180029f7c`
- end: `0x180029fb4`
- name: `?Release@?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021be8`
- `0x18002d084`
- `0x18002d434`

## callees

- `0x180021dec`
- `0x180029f7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029fa1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 78);
  if ( !v2 )
  {
    tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::~merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180029f7c  mov     [rsp+arg_0], rbx
0x180029f81  push    rdi
0x180029f82  sub     rsp, 20h
0x180029f86  mov     rdi, rcx
0x180029f89  or      ebx, 0FFFFFFFFh
0x180029f8c  lock xadd [rcx+138h], ebx
0x180029f94  sub     ebx, 1
0x180029f97  jnz     short loc_180029FA7
0x180029f99  call    ??1?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::~merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(void)
0x180029f9e  mov     rcx, rdi; pv
0x180029fa1  call    cs:__imp_CoTaskMemFree
0x180029fa7  mov     eax, ebx
0x180029fa9  mov     rbx, [rsp+28h+arg_0]
0x180029fae  add     rsp, 20h
0x180029fb2  pop     rdi
0x180029fb3  retn
```
