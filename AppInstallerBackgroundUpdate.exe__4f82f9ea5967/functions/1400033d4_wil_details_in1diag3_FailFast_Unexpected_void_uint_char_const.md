# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1400033d4`
- end: `0x1400033f4`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d18`
- `0x14000461c`
- `0x140006064`
- `0x140007910`

## callees

- `0x140002220`

## string_xrefs

- `0x1400033e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    3585,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (__int64)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x1400033d4  sub     rsp, 48h
0x1400033d8  mov     rax, [rsp+48h]
0x1400033dd  mov     [rsp+48h+var_20], rax
0x1400033e2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400033e9  mov     edx, 0E01h
0x1400033ee  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
