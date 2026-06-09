# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180006fdc`
- end: `0x180007005`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800061c8`
- `0x180006598`
- `0x180009cf4`
- `0x180009e08`

## callees

- `0x180004be8`

## string_xrefs

- `0x180006ff3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180006fdc  sub     rsp, 58h
0x180006fe0  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180006fe9  mov     rax, [rsp+58h]
0x180006fee  mov     [rsp+58h+var_30], rax
0x180006ff3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006ffa  mov     edx, 0E01h
0x180006fff  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
