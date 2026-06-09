# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1400073c0`
- end: `0x1400073dd`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `29`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400045a0`
- `0x1400048f8`
- `0x140004cc8`
- `0x140004f10`
- `0x1400062fc`
- `0x140006f1c`
- `0x14000bb68`
- `0x14000c164`
- `0x14000e0b0`

## callees

- `0x140003978`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  char *retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x1400073c0  sub     rsp, 48h
0x1400073c4  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400073cd  mov     rax, [rsp+48h]
0x1400073d2  mov     [rsp+48h+var_20], rax
0x1400073d7  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
