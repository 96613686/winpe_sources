# wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)

- ea: `0x1800149a4`
- end: `0x1800149c9`
- name: `?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020270`

## callees

- `0x1800039e0`

## string_xrefs

- `0x1800149b7`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3249,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800149a4  sub     rsp, 48h
0x1800149a8  mov     rax, [rsp+48h]
0x1800149ad  mov     [rsp+48h+var_18], r9d
0x1800149b2  mov     [rsp+48h+var_20], rax
0x1800149b7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800149be  mov     edx, 0CB1h
0x1800149c3  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
