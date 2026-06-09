# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x140008afc`
- end: `0x140008b10`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030ac`
- `0x140003178`
- `0x140003a78`
- `0x140003e1c`
- `0x1400041ec`
- `0x140004410`
- `0x140006ffc`
- `0x140007110`
- `0x14000823c`

## callees

- `0x1400025dc`

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
0x140008afc  sub     rsp, 38h
0x140008b00  mov     rax, [rsp+38h]
0x140008b05  mov     [rsp+38h+var_10], rax
0x140008b0a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
