# _ShowFeedbackToastHandler::ShowFeedbackToast_::_1_::catch$13

- ea: `0x18001b3a8`
- end: `0x18001b3e4`
- name: `_ShowFeedbackToastHandler::ShowFeedbackToast_::_1_::catch$13`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001b3bc`: `pcshell\shell\performancetracehandler\dll\showfeedbacktoasthandler.cpp`

## pseudocode

```c
__int64 __fastcall ShowFeedbackToastHandler::ShowFeedbackToast_::_1_::catch_13(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 256) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 248),
                            (void *)0xA8,
                            (int)"pcshell\\shell\\performancetracehandler\\dll\\showfeedbacktoasthandler.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18001b3a8  mov     [rsp+arg_8], rdx
0x18001b3ad  push    rbp
0x18001b3ae  sub     rsp, 60h
0x18001b3b2  mov     rbp, rdx
0x18001b3b5  mov     rcx, [rbp+0F8h]; this
0x18001b3bc  lea     r8, aPcshellShellPe_1; "pcshell\\shell\\performancetracehandler"...
0x18001b3c3  mov     edx, 0A8h; void *
0x18001b3c8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001b3cd  mov     [rbp+100h], eax
0x18001b3d3  mov     rax, 0
0x18001b3dd  add     rsp, 60h
0x18001b3e1  pop     rbp
0x18001b3e2  retn
```
