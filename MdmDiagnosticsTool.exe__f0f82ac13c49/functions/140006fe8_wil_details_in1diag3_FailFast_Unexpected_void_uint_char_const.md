# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x140006fe8`
- end: `0x140007010`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e60`

## callees

- `0x1400025d0`

## string_xrefs

- `0x140006ffe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    3977,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (__int64)a4,
    v4,
    retaddr,
    0x8000FFFF);
}

```

## disassembly

```asm
0x140006fe8  sub     rsp, 48h
0x140006fec  mov     rax, [rsp+48h]
0x140006ff1  mov     [rsp+48h+var_18], 8000FFFFh
0x140006ff9  mov     [rsp+48h+var_20], rax
0x140006ffe  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140007005  mov     edx, 0F89h
0x14000700a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
