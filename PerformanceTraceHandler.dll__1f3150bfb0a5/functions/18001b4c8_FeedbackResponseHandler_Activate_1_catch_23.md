# _FeedbackResponseHandler::Activate_::_1_::catch$23

- ea: `0x18001b4c8`
- end: `0x18001b501`
- name: `_FeedbackResponseHandler::Activate_::_1_::catch$23`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001b4dc`: `pcshell\shell\performancetracehandler\dll\feedbackresponsehandler.cpp`

## pseudocode

```c
__int64 __fastcall FeedbackResponseHandler::Activate_::_1_::catch_23(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x78,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\feedbackresponsehandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001b4c8  mov     [rsp+arg_8], rdx
0x18001b4cd  push    rbp
0x18001b4ce  sub     rsp, 30h
0x18001b4d2  mov     rbp, rdx
0x18001b4d5  mov     rcx, [rbp+0F8h]; this
0x18001b4dc  lea     r8, aPcshellShellPe_2; "pcshell\\shell\\performancetracehandler"...
0x18001b4e3  mov     edx, 78h ; 'x'; void *
0x18001b4e8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001b4ed  mov     [rbp+40h], eax
0x18001b4f0  mov     rax, 0
0x18001b4fa  add     rsp, 30h
0x18001b4fe  pop     rbp
0x18001b4ff  retn
```
