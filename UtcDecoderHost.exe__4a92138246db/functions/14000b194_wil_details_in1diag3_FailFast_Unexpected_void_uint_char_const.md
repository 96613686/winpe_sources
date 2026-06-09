# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x14000b194`
- end: `0x14000b1b0`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000aac8`
- `0x14000c11c`
- `0x14000d958`
- `0x14000fccc`
- `0x14001373c`
- `0x140015610`

## callees

- `0x14000995c`

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

  wil::details::ReportFailure_Hr<3>((__int64)this, a2, a3, (__int64)a4, v4, retaddr, 0x8000FFFF);
}

```

## disassembly

```asm
0x14000b194  sub     rsp, 48h
0x14000b198  mov     rax, [rsp+48h]
0x14000b19d  mov     [rsp+48h+var_18], 8000FFFFh
0x14000b1a5  mov     [rsp+48h+var_20], rax
0x14000b1aa  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
