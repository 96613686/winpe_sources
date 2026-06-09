# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180003ed0`
- end: `0x180003ee4`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f20`
- `0x1800043e0`
- `0x180005680`
- `0x180005880`
- `0x180005aa0`

## callees

- `0x180003e20`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>((int)this, (int)a2, a3, (int)a4, v4, retaddr);
}

```

## disassembly

```asm
0x180003ed0  sub     rsp, 38h
0x180003ed4  mov     rax, [rsp+38h]
0x180003ed9  mov     [rsp+38h+var_10], rax; char *
0x180003ede  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
