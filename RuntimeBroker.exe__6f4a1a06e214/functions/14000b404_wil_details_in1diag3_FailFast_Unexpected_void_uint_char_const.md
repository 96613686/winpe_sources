# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x14000b404`
- end: `0x14000b424`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ad0`
- `0x140007420`

## callees

- `0x14000a4d4`

## string_xrefs

- `0x14000b40d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x14000b404  sub     rsp, 48h
0x14000b408  mov     rax, [rsp+48h]
0x14000b40d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000b414  mov     edx, 0E01h
0x14000b419  mov     [rsp+48h+var_20], rax
0x14000b41e  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
