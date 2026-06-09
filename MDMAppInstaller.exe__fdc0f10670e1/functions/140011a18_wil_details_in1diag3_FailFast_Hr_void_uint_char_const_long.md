# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x140011a18`
- end: `0x140011a3d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012c58`

## callees

- `0x140002fa4`

## string_xrefs

- `0x140011a2b`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
    488,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x140011a18  sub     rsp, 48h
0x140011a1c  mov     rax, [rsp+48h]
0x140011a21  mov     [rsp+48h+var_18], r9d
0x140011a26  mov     [rsp+48h+var_20], rax
0x140011a2b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140011a32  mov     edx, 1E8h
0x140011a37  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
