# ServiceMain$catch$1

- ea: `0x18000c5f7`
- end: `0x18000c624`
- name: `ServiceMain$catch$1`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a2cc`

## pseudocode

```c
__int64 __fastcall ServiceMain_catch_1(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 40), (void *)0x39, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x18000c5f7  mov     [rsp+arg_8], rdx
0x18000c5fc  push    rbp
0x18000c5fd  sub     rsp, 20h
0x18000c601  mov     rbp, rdx
0x18000c604  mov     rcx, [rbp+28h]; this
0x18000c608  mov     edx, 39h ; '9'; void *
0x18000c60d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18000c612  nop
0x18000c613  mov     rax, 0
0x18000c61d  add     rsp, 20h
0x18000c621  pop     rbp
0x18000c622  retn
```
