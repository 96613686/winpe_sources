# _LogonTrigger::HandleLogOff_::_1_::catch$12

- ea: `0x18002466f`
- end: `0x1800246a6`
- name: `_LogonTrigger::HandleLogOff_::_1_::catch$12`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fbe8`

## string_xrefs

- `0x180024683`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
__int64 __fastcall LogonTrigger::HandleLogOff_::_1_::catch_12(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0xBC,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18002466f  mov     [rsp+arg_8], rdx
0x180024674  push    rbp
0x180024675  sub     rsp, 20h
0x180024679  mov     rbp, rdx
0x18002467c  mov     rcx, [rbp+1E8h]; this
0x180024683  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002468a  mov     edx, 0BCh; void *
0x18002468f  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180024694  nop
0x180024695  mov     rax, 0
0x18002469f  add     rsp, 20h
0x1800246a3  pop     rbp
0x1800246a4  retn
```
