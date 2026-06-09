# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180054f00`
- end: `0x180054f2e`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `46`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002aba0`
- `0x180050738`

## callees

- `0x180040b74`

## string_xrefs

- `0x180054f1c`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

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
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180054f00  sub     rsp, 58h
0x180054f04  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180054f0d  mov     rax, [rsp+58h]
0x180054f12  mov     [rsp+58h+var_28], r9d
0x180054f17  mov     [rsp+58h+var_30], rax
0x180054f1c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180054f23  mov     edx, 10Fh
0x180054f28  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
