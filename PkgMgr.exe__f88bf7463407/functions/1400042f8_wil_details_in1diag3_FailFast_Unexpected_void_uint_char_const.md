# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1400042f8`
- end: `0x140004321`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400062d8`

## callees

- `0x140003534`

## string_xrefs

- `0x14000430f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1400042f8  sub     rsp, 58h
0x1400042fc  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x140004305  mov     rax, [rsp+58h]
0x14000430a  mov     [rsp+58h+var_30], rax
0x14000430f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004316  mov     edx, 0E01h
0x14000431b  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
