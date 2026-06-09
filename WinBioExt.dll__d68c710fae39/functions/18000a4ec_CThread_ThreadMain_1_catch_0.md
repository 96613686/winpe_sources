# _CThread::ThreadMain_::_1_::catch$0

- ea: `0x18000a4ec`
- end: `0x18000a503`
- name: `_CThread::ThreadMain_::_1_::catch$0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006cdc`

## pseudocode

```c
void __fastcall __noreturn CThread::ThreadMain_::_1_::catch_0(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(a2[5], a2, a3, a4);
}

```

## disassembly

```asm
0x18000a4ec  mov     [rsp+arg_8], rdx
0x18000a4f1  push    rbp
0x18000a4f2  sub     rsp, 20h
0x18000a4f6  mov     rbp, rdx
0x18000a4f9  mov     rcx, [rbp+28h]; this
0x18000a4fd  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
