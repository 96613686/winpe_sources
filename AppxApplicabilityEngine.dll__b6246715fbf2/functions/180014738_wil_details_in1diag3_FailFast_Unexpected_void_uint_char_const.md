# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180014738`
- end: `0x180014761`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800160cc`

## callees

- `0x180013a98`

## string_xrefs

- `0x18001474f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x180014738  sub     rsp, 58h
0x18001473c  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180014745  mov     rax, [rsp+58h]
0x18001474a  mov     [rsp+58h+var_30], rax
0x18001474f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014756  mov     edx, 0E01h
0x18001475b  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
