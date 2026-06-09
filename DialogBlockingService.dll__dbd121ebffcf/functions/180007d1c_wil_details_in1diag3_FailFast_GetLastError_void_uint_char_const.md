# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180007d1c`
- end: `0x180007d30`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d4c`
- `0x1800046d8`
- `0x180004ae4`
- `0x1800064cc`
- `0x18000752c`
- `0x180008da8`
- `0x180009010`
- `0x1800093f0`

## callees

- `0x1800030c0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x180007d1c  sub     rsp, 38h
0x180007d20  mov     rax, [rsp+38h]
0x180007d25  mov     [rsp+38h+var_10], rax
0x180007d2a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
