# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x14000d2ec`
- end: `0x14000d300`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a700`
- `0x14000aac8`
- `0x14000aea4`
- `0x14000b0f0`
- `0x14000c11c`
- `0x14000cefc`
- `0x14000d86c`
- `0x14000d958`
- `0x140012e1c`
- `0x14001373c`
- `0x140015610`

## callees

- `0x140009768`

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
0x14000d2ec  sub     rsp, 38h
0x14000d2f0  mov     rax, [rsp+38h]
0x14000d2f5  mov     [rsp+38h+var_10], rax
0x14000d2fa  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
