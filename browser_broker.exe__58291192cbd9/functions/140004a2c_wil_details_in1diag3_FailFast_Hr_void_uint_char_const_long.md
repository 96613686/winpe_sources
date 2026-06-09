# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x140004a2c`
- end: `0x140004a45`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000415c`
- `0x140005110`
- `0x1400054fc`

## callees

- `0x140002258`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>((__int64)this, a2, a3, (__int64)a4, v5, retaddr, (unsigned int)a4);
}

```

## disassembly

```asm
0x140004a2c  sub     rsp, 48h
0x140004a30  mov     rax, [rsp+48h]
0x140004a35  mov     [rsp+48h+var_18], r9d
0x140004a3a  mov     [rsp+48h+var_20], rax
0x140004a3f  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
