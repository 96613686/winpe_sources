# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800071a8`
- end: `0x1800071bc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042e8`
- `0x1800045b8`
- `0x180004988`
- `0x180004bd0`
- `0x180005fac`
- `0x180006d0c`
- `0x180008104`
- `0x1800081d8`
- `0x18000896c`
- `0x18000ba74`
- `0x18000cad4`
- `0x18000ddf8`
- `0x18000e9e8`
- `0x180010200`
- `0x1800102c0`
- `0x180010444`

## callees

- `0x180003890`

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
0x1800071a8  sub     rsp, 38h
0x1800071ac  mov     rax, [rsp+38h]
0x1800071b1  mov     [rsp+38h+var_10], rax
0x1800071b6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
