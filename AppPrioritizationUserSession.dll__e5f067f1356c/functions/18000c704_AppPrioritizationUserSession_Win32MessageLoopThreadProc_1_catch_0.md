# _AppPrioritizationUserSession::Win32MessageLoopThreadProc_::_1_::catch$0

- ea: `0x18000c704`
- end: `0x18000c736`
- name: `_AppPrioritizationUserSession::Win32MessageLoopThreadProc_::_1_::catch$0`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a9b0`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::Win32MessageLoopThreadProc_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x51,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000c704  mov     [rsp+arg_8], rdx
0x18000c709  push    rbp
0x18000c70a  sub     rsp, 30h
0x18000c70e  mov     rbp, rdx
0x18000c711  mov     rcx, [rbp+98h]; this
0x18000c718  mov     edx, 51h ; 'Q'; void *
0x18000c71d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000c722  mov     [rbp+30h], eax
0x18000c725  mov     rax, 0
0x18000c72f  add     rsp, 30h
0x18000c733  pop     rbp
0x18000c734  retn
```
