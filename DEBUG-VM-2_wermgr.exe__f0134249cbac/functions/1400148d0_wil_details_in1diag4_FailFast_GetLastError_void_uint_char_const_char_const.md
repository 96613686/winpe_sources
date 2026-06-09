# wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)

- ea: `0x1400148d0`
- end: `0x1400148e4`
- name: `?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ff64`
- `0x140010414`
- `0x140010778`
- `0x140010b80`
- `0x140010fac`
- `0x140011210`
- `0x140013124`
- `0x140013248`
- `0x14001410c`

## callees

- `0x14000f904`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::_FailFast_GetLastError(
        wil::details::in1diag4 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5)
{
  int v5; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v5, retaddr);
}

```

## disassembly

```asm
0x1400148d0  sub     rsp, 38h
0x1400148d4  mov     rax, [rsp+38h]
0x1400148d9  mov     [rsp+38h+var_10], rax; char *
0x1400148de  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
