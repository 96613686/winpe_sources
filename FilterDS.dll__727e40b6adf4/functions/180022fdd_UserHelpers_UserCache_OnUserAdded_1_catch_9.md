# _UserHelpers::UserCache::OnUserAdded_::_1_::catch$9

- ea: `0x180022fdd`
- end: `0x180023016`
- name: `_UserHelpers::UserCache::OnUserAdded_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x180022ff1`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
__int64 __fastcall UserHelpers::UserCache::OnUserAdded_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x12D,
                           (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180022fdd  mov     [rsp+arg_8], rdx
0x180022fe2  push    rbp
0x180022fe3  sub     rsp, 20h
0x180022fe7  mov     rbp, rdx
0x180022fea  mov     rcx, [rbp+98h]; this
0x180022ff1  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180022ff8  mov     edx, 12Dh; void *
0x180022ffd  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180023002  mov     [rbp+20h], eax
0x180023005  mov     rax, 0
0x18002300f  add     rsp, 20h
0x180023013  pop     rbp
0x180023014  retn
```
