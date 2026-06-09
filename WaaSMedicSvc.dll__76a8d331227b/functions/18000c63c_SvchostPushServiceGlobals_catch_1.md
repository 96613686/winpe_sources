# SvchostPushServiceGlobals$catch$1

- ea: `0x18000c63c`
- end: `0x18000c669`
- name: `SvchostPushServiceGlobals$catch$1`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a2cc`

## pseudocode

```c
__int64 __fastcall SvchostPushServiceGlobals_catch_1(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 40), (void *)0x40, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x18000c63c  mov     [rsp+arg_8], rdx
0x18000c641  push    rbp
0x18000c642  sub     rsp, 20h
0x18000c646  mov     rbp, rdx
0x18000c649  mov     rcx, [rbp+28h]; this
0x18000c64d  mov     edx, 40h ; '@'; void *
0x18000c652  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18000c657  nop
0x18000c658  mov     rax, 0
0x18000c662  add     rsp, 20h
0x18000c666  pop     rbp
0x18000c667  retn
```
