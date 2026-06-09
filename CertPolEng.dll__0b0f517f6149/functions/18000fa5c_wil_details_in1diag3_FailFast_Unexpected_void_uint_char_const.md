# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000fa5c`
- end: `0x18000fa7c`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012404`

## callees

- `0x18000efe4`

## string_xrefs

- `0x18000fa6a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000fa5c  sub     rsp, 48h
0x18000fa60  mov     rax, [rsp+48h]
0x18000fa65  mov     [rsp+48h+var_20], rax
0x18000fa6a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fa71  mov     edx, 0E01h
0x18000fa76  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
