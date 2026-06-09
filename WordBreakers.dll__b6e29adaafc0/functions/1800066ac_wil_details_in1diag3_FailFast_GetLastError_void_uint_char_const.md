# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800066ac`
- end: `0x1800066c0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b3c`
- `0x180003e78`
- `0x180003f90`
- `0x180004334`
- `0x180004560`
- `0x18000578c`
- `0x1800061bc`
- `0x180007830`
- `0x180007dd8`
- `0x18000a370`

## callees

- `0x1800030b0`

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
0x1800066ac  sub     rsp, 38h
0x1800066b0  mov     rax, [rsp+38h]
0x1800066b5  mov     [rsp+38h+var_10], rax
0x1800066ba  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
