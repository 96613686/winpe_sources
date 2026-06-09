# _LogonTrigger::RuntimeClassInitialize_::_1_::catch$10

- ea: `0x180024755`
- end: `0x18002478e`
- name: `_LogonTrigger::RuntimeClassInitialize_::_1_::catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x180024769`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
__int64 __fastcall LogonTrigger::RuntimeClassInitialize_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 184),
                           (void *)0x2A,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180024755  mov     [rsp+arg_8], rdx
0x18002475a  push    rbp
0x18002475b  sub     rsp, 20h
0x18002475f  mov     rbp, rdx
0x180024762  mov     rcx, [rbp+0B8h]; this
0x180024769  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180024770  mov     edx, 2Ah ; '*'; void *
0x180024775  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002477a  mov     [rbp+20h], eax
0x18002477d  mov     rax, 0
0x180024787  add     rsp, 20h
0x18002478b  pop     rbp
0x18002478c  retn
```
