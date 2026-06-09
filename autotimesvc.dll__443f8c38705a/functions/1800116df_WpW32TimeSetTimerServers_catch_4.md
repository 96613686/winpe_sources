# WpW32TimeSetTimerServers$catch$4

- ea: `0x1800116df`
- end: `0x180011715`
- name: `WpW32TimeSetTimerServers$catch$4`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009154`

## string_xrefs

- `0x1800116f0`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeSetTimerServers_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x218,
                           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800116df  mov     [rsp+arg_8], rdx
0x1800116e4  push    rbp
0x1800116e5  sub     rsp, 20h
0x1800116e9  mov     rbp, rdx
0x1800116ec  mov     rcx, [rbp+38h]; this
0x1800116f0  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800116f7  mov     edx, 218h; void *
0x1800116fc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180011701  mov     [rbp+48h], eax
0x180011704  mov     rax, 0
0x18001170e  add     rsp, 20h
0x180011712  pop     rbp
0x180011713  retn
```
