# _Vml::TemporaryPrivilege::_TemporaryPrivilege_::_1_::catch$1

- ea: `0x1400224c6`
- end: `0x1400224e9`
- name: `_Vml::TemporaryPrivilege::_TemporaryPrivilege_::_1_::catch$1`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140009490`

## string_xrefs

- `0x1400224d7`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall __noreturn Vml::TemporaryPrivilege::_TemporaryPrivilege_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::_FailFast_Unexpected(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x1E04,
    (int)"onecore\\vm\\common\\vml\\VmSecurity.h",
    a4);
}

```

## disassembly

```asm
0x1400224c6  mov     [rsp+arg_8], rdx
0x1400224cb  push    rbp
0x1400224cc  sub     rsp, 20h
0x1400224d0  mov     rbp, rdx
0x1400224d3  mov     rcx, [rbp+28h]; this
0x1400224d7  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400224de  mov     edx, 1E04h; void *
0x1400224e3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
