# _LogonTrigger::HandleLogOn_::_1_::catch$14

- ea: `0x1800246e2`
- end: `0x180024719`
- name: `_LogonTrigger::HandleLogOn_::_1_::catch$14`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fbe8`

## string_xrefs

- `0x1800246f6`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
__int64 __fastcall LogonTrigger::HandleLogOn_::_1_::catch_14(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0x4E,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800246e2  mov     [rsp+arg_8], rdx
0x1800246e7  push    rbp
0x1800246e8  sub     rsp, 20h
0x1800246ec  mov     rbp, rdx
0x1800246ef  mov     rcx, [rbp+1E8h]; this
0x1800246f6  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800246fd  mov     edx, 4Eh ; 'N'; void *
0x180024702  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180024707  nop
0x180024708  mov     rax, 0
0x180024712  add     rsp, 20h
0x180024716  pop     rbp
0x180024717  retn
```
