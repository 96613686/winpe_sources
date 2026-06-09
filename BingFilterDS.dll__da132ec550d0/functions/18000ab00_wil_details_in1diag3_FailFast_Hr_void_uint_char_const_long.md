# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18000ab00`
- end: `0x18000ab25`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008974`
- `0x180009250`

## callees

- `0x1800031bc`

## string_xrefs

- `0x18000ab13`: `onecore\internal\sdk\inc\wil\opensource\wil\safecast.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    271,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\safecast.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000ab00  sub     rsp, 48h
0x18000ab04  mov     rax, [rsp+48h]
0x18000ab09  mov     [rsp+48h+var_18], r9d
0x18000ab0e  mov     [rsp+48h+var_20], rax
0x18000ab13  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ab1a  mov     edx, 10Fh
0x18000ab1f  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
