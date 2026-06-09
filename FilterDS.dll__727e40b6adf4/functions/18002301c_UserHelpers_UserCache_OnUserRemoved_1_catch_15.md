# _UserHelpers::UserCache::OnUserRemoved_::_1_::catch$15

- ea: `0x18002301c`
- end: `0x180023055`
- name: `_UserHelpers::UserCache::OnUserRemoved_::_1_::catch$15`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x180023030`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
__int64 __fastcall UserHelpers::UserCache::OnUserRemoved_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x136,
                           (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002301c  mov     [rsp+arg_8], rdx
0x180023021  push    rbp
0x180023022  sub     rsp, 20h
0x180023026  mov     rbp, rdx
0x180023029  mov     rcx, [rbp+98h]; this
0x180023030  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180023037  mov     edx, 136h; void *
0x18002303c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180023041  mov     [rbp+20h], eax
0x180023044  mov     rax, 0
0x18002304e  add     rsp, 20h
0x180023052  pop     rbp
0x180023053  retn
```
