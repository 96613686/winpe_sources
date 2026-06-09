# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000e814`
- end: `0x18000e828`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180005970`
- `0x180005a3c`
- `0x1800068a8`
- `0x180006c4c`
- `0x180007084`
- `0x1800074e0`
- `0x18000b3f8`
- `0x18000b50c`
- `0x18000d71c`

## callees

- `0x1800037dc`

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
0x18000e814  sub     rsp, 38h
0x18000e818  mov     rax, [rsp+38h]
0x18000e81d  mov     [rsp+38h+var_10], rax
0x18000e822  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
