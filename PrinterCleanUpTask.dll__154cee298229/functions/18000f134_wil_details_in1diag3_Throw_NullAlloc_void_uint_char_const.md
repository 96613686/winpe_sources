# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x18000f134`
- end: `0x18000f157`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009428`
- `0x1800094f0`

## callees

- `0x180005c6c`

## string_xrefs

- `0x18000f13d`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000f134  sub     rsp, 48h
0x18000f138  mov     rax, [rsp+48h]
0x18000f13d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f144  mov     [rsp+48h+var_18], 8007000Eh
0x18000f14c  mov     [rsp+48h+var_20], rax
0x18000f151  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
