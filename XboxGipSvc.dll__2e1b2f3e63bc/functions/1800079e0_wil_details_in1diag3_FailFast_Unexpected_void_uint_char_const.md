# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800079e0`
- end: `0x180007a03`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073b8`
- `0x18000832c`
- `0x18000c118`
- `0x18000c790`
- `0x18000c998`

## callees

- `0x180006c0c`

## string_xrefs

- `0x1800079f6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    a2,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (__int64)a4,
    v4,
    retaddr,
    0x8000FFFF);
}

```

## disassembly

```asm
0x1800079e0  sub     rsp, 48h
0x1800079e4  mov     rax, [rsp+48h]
0x1800079e9  mov     [rsp+48h+var_18], 8000FFFFh
0x1800079f1  mov     [rsp+48h+var_20], rax
0x1800079f6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800079fd  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
