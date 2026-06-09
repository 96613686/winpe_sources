# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18002fecc`
- end: `0x18002fee0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180027db8`
- `0x180027e84`
- `0x180028a60`
- `0x180028e30`
- `0x180029264`
- `0x1800296f0`
- `0x18002d468`
- `0x18002d57c`
- `0x18002f1fc`

## callees

- `0x180027144`

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
0x18002fecc  sub     rsp, 38h
0x18002fed0  mov     rax, [rsp+38h]
0x18002fed5  mov     [rsp+38h+var_10], rax
0x18002feda  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
