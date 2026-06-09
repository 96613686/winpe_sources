# _RegisterForWNFs_::_1_::catch$3

- ea: `0x180011200`
- end: `0x180011236`
- name: `_RegisterForWNFs_::_1_::catch$3`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x180009154`

## string_xrefs

- `0x180011211`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

## pseudocode

```c
__int64 __fastcall RegisterForWNFs_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x473,
                           (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180011200  mov     [rsp+arg_8], rdx
0x180011205  push    rbp
0x180011206  sub     rsp, 20h
0x18001120a  mov     rbp, rdx
0x18001120d  mov     rcx, [rbp+28h]; this
0x180011211  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180011218  mov     edx, 473h; void *
0x18001121d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180011222  mov     [rbp+38h], eax
0x180011225  mov     rax, 0
0x18001122f  add     rsp, 20h
0x180011233  pop     rbp
0x180011234  retn
```
