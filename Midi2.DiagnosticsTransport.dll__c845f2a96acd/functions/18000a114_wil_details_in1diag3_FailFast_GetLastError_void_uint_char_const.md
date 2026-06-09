# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000a114`
- end: `0x18000a128`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004cfc`
- `0x180005198`
- `0x180006100`
- `0x180008da8`
- `0x180009a5c`

## callees

- `0x18000427c`

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
0x18000a114  sub     rsp, 38h
0x18000a118  mov     rax, [rsp+38h]
0x18000a11d  mov     [rsp+38h+var_10], rax
0x18000a122  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
