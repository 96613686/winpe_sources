# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180008b20`
- end: `0x180008b43`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e284`
- `0x1800236b4`
- `0x1800236e4`

## callees

- `0x180005f80`

## string_xrefs

- `0x180008b36`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180008b20  sub     rsp, 48h
0x180008b24  mov     rax, [rsp+48h]
0x180008b29  mov     [rsp+48h+var_18], 8000FFFFh
0x180008b31  mov     [rsp+48h+var_20], rax
0x180008b36  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008b3d  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
