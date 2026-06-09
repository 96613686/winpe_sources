# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$6

- ea: `0x140011ae8`
- end: `0x140011aff`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$6`
- size: `23`
- prototype: `void __fastcall __noreturn(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009f88`

## pseudocode

```c
void __fastcall __noreturn errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_6(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(a2[9], a2, a3, a4);
}

```

## disassembly

```asm
0x140011ae8  mov     [rsp+arg_8], rdx
0x140011aed  push    rbp
0x140011aee  sub     rsp, 20h
0x140011af2  mov     rbp, rdx
0x140011af5  mov     rcx, [rbp+48h]; this
0x140011af9  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
