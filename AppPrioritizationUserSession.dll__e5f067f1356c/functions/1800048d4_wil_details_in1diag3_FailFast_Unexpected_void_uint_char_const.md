# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800048d4`
- end: `0x1800048e8`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042e8`
- `0x180005dc4`
- `0x18000ad10`

## callees

- `0x180003724`

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

  wil::details::ReportFailure_Hr<3>((__int64)this, a2, a3, (__int64)a4, v4, retaddr);
}

```

## disassembly

```asm
0x1800048d4  sub     rsp, 48h
0x1800048d8  mov     rax, [rsp+48h]
0x1800048dd  mov     [rsp+48h+var_20], rax
0x1800048e2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
