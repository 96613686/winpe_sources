# WpW32TimeEnableServiceLogging$catch$6

- ea: `0x1800116a0`
- end: `0x1800116d9`
- name: `WpW32TimeEnableServiceLogging$catch$6`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009154`

## string_xrefs

- `0x1800116b4`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeEnableServiceLogging_catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 632),
                           (void *)0x23E,
                           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800116a0  mov     [rsp+arg_8], rdx
0x1800116a5  push    rbp
0x1800116a6  sub     rsp, 20h
0x1800116aa  mov     rbp, rdx
0x1800116ad  mov     rcx, [rbp+278h]; this
0x1800116b4  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800116bb  mov     edx, 23Eh; void *
0x1800116c0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800116c5  mov     [rbp+20h], eax
0x1800116c8  mov     rax, 0
0x1800116d2  add     rsp, 20h
0x1800116d6  pop     rbp
0x1800116d7  retn
```
