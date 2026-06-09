# WpW32TimeDisableServiceLogging$catch$4

- ea: `0x180011640`
- end: `0x180011676`
- name: `WpW32TimeDisableServiceLogging$catch$4`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009154`

## string_xrefs

- `0x180011651`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeDisableServiceLogging_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x256,
                           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180011640  mov     [rsp+arg_8], rdx
0x180011645  push    rbp
0x180011646  sub     rsp, 20h
0x18001164a  mov     rbp, rdx
0x18001164d  mov     rcx, [rbp+38h]; this
0x180011651  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180011658  mov     edx, 256h; void *
0x18001165d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180011662  mov     [rbp+40h], eax
0x180011665  mov     rax, 0
0x18001166f  add     rsp, 20h
0x180011673  pop     rbp
0x180011674  retn
```
