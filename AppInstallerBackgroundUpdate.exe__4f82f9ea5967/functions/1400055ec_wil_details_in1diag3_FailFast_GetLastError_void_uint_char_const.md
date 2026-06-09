# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1400055ec`
- end: `0x140005600`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a4c`
- `0x140002d18`
- `0x1400030e8`
- `0x140003330`
- `0x14000461c`
- `0x14000521c`
- `0x140005ad0`
- `0x140006064`
- `0x140007910`

## callees

- `0x140002044`

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
0x1400055ec  sub     rsp, 38h
0x1400055f0  mov     rax, [rsp+38h]
0x1400055f5  mov     [rsp+38h+var_10], rax
0x1400055fa  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
