# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800057e4`
- end: `0x1800057f8`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002df4`
- `0x1800030a0`
- `0x180003470`
- `0x1800036b0`
- `0x1800048ec`
- `0x18000531c`
- `0x1800097e4`
- `0x180009ed8`
- `0x18000dbd0`

## callees

- `0x1800023b4`

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
0x1800057e4  sub     rsp, 38h
0x1800057e8  mov     rax, [rsp+38h]
0x1800057ed  mov     [rsp+38h+var_10], rax
0x1800057f2  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
