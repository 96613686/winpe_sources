# WpW32TimeSyncNow$catch$8

- ea: `0x180011751`
- end: `0x180011787`
- name: `WpW32TimeSyncNow$catch$8`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009154`

## string_xrefs

- `0x180011762`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeSyncNow_catch_8(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x13D,
                            (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180011751  mov     [rsp+arg_8], rdx
0x180011756  push    rbp
0x180011757  sub     rsp, 30h
0x18001175b  mov     rbp, rdx
0x18001175e  mov     rcx, [rbp+68h]; this
0x180011762  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180011769  mov     edx, 13Dh; void *
0x18001176e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180011773  mov     [rbp+70h], eax
0x180011776  mov     rax, 0
0x180011780  add     rsp, 30h
0x180011784  pop     rbp
0x180011785  retn
```
