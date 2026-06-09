# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180007898`
- end: `0x1800078b8`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005be0`
- `0x180006ad8`

## callees

- `0x180002658`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>();
}

```

## disassembly

```asm
0x180007898  sub     rsp, 48h
0x18000789c  mov     rax, [rsp+48h]
0x1800078a1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x1800078a8  mov     edx, 1435h
0x1800078ad  mov     [rsp+48h+var_20], rax
0x1800078b2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
