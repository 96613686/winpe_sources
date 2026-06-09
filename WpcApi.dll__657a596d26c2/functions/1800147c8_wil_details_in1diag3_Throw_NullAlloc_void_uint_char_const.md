# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x1800147c8`
- end: `0x1800147f0`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f638`

## callees

- `0x18000e720`

## string_xrefs

- `0x1800147d1`: `onecore\internal\sdk\inc\wil\opensource\wil\wrl.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    63,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\wrl.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800147c8  sub     rsp, 48h
0x1800147cc  mov     rax, [rsp+48h]
0x1800147d1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800147d8  mov     [rsp+48h+var_18], 8007000Eh
0x1800147e0  mov     edx, 3Fh ; '?'
0x1800147e5  mov     [rsp+48h+var_20], rax
0x1800147ea  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
