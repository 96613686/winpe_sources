# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180007164`
- end: `0x18000718c`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064a8`
- `0x180008fdc`
- `0x18000fa9c`
- `0x180011fdc`

## callees

- `0x180005220`

## string_xrefs

- `0x18000717a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180007164  sub     rsp, 48h
0x180007168  mov     rax, [rsp+48h]
0x18000716d  mov     [rsp+48h+var_18], 8000FFFFh
0x180007175  mov     [rsp+48h+var_20], rax
0x18000717a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007181  mov     edx, 0E01h
0x180007186  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
