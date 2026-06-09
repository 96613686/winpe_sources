# wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)

- ea: `0x1400076ec`
- end: `0x14000770a`
- name: `?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z`
- size: `30`
- prototype: `void __fastcall __noreturn(wil::details::in1diag5 *__hidden this, void *, unsigned int, const char *, const char *, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031f4`
- `0x1400036f0`
- `0x140003c20`
- `0x1400040e4`
- `0x14000608c`
- `0x140007104`

## callees

- `0x14000220c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag5::_FailFast_GetLastError(
        wil::details::in1diag5 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        char *a5,
        const char *a6)
{
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, a5, retaddr);
}

```

## disassembly

```asm
0x1400076ec  sub     rsp, 38h
0x1400076f0  mov     rax, [rsp+38h]
0x1400076f5  mov     [rsp+38h+var_10], rax
0x1400076fa  mov     rax, [rsp+38h+arg_20]
0x1400076ff  mov     [rsp+38h+var_18], rax
0x140007704  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
