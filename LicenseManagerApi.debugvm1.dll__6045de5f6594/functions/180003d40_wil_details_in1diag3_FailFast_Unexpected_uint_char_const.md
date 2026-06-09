# wil::details::in1diag3::FailFast_Unexpected(uint,char const *)

- ea: `0x180003d40`
- end: `0x180003d68`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037a8`
- `0x180004fac`

## callees

- `0x180002c84`

## string_xrefs

- `0x180003d56`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        __int64 a2,
        const char *a3,
        int a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    a4);
}

```

## disassembly

```asm
0x180003d40  sub     rsp, 48h
0x180003d44  mov     rax, [rsp+48h]
0x180003d49  mov     [rsp+48h+var_18], 8000FFFFh
0x180003d51  mov     [rsp+48h+var_20], rax
0x180003d56  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003d5d  mov     edx, 0E01h
0x180003d62  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
