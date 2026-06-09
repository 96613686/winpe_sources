# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180010ed4`
- end: `0x180010ef4`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e90c`
- `0x18000efec`
- `0x18000f5d4`
- `0x180010040`
- `0x180010a74`

## callees

- `0x180006c0c`

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

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    a2,
    (__int64)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x180010ed4  sub     rsp, 48h
0x180010ed8  mov     rax, [rsp+48h]
0x180010edd  mov     [rsp+48h+var_18], r9d
0x180010ee2  mov     [rsp+48h+var_20], rax
0x180010ee7  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010eee  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
