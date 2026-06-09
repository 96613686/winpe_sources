# _AccountCleanupMaintenanceTaskHandler::Start_::_1_::catch$16

- ea: `0x1800243db`
- end: `0x180024414`
- name: `_AccountCleanupMaintenanceTaskHandler::Start_::_1_::catch$16`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x1800243ef`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall AccountCleanupMaintenanceTaskHandler::Start_::_1_::catch_16(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 456),
                           (void *)0x26,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaint"
                                         "enancetaskhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800243db  mov     [rsp+arg_8], rdx
0x1800243e0  push    rbp
0x1800243e1  sub     rsp, 20h
0x1800243e5  mov     rbp, rdx
0x1800243e8  mov     rcx, [rbp+1C8h]; this
0x1800243ef  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800243f6  mov     edx, 26h ; '&'; void *
0x1800243fb  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180024400  mov     [rbp+20h], eax
0x180024403  mov     rax, 0
0x18002440d  add     rsp, 20h
0x180024411  pop     rbp
0x180024412  retn
```
