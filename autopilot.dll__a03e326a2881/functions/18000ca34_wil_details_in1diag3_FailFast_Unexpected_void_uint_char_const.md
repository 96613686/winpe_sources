# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000ca34`
- end: `0x18000ca57`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b848`
- `0x18000bc20`
- `0x18000fda8`
- `0x18000fed0`

## callees

- `0x180009f5c`

## string_xrefs

- `0x18000ca4a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000ca34  sub     rsp, 48h
0x18000ca38  mov     rax, [rsp+48h]
0x18000ca3d  mov     [rsp+48h+var_18], 8000FFFFh
0x18000ca45  mov     [rsp+48h+var_20], rax
0x18000ca4a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ca51  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
