# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000a648`
- end: `0x18000a670`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009874`

## callees

- `0x1800095dc`

## string_xrefs

- `0x18000a651`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3977,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000a648  sub     rsp, 48h
0x18000a64c  mov     rax, [rsp+48h]
0x18000a651  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a658  mov     [rsp+48h+var_18], 8000FFFFh
0x18000a660  mov     edx, 0F89h
0x18000a665  mov     [rsp+48h+var_20], rax
0x18000a66a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
