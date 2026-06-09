# wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)

- ea: `0x1800060cc`
- end: `0x1800060e2`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z`
- size: `22`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034e8`
- `0x1800037a8`
- `0x180003b10`
- `0x180004fac`
- `0x180005d2c`

## callees

- `0x180002a9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        __int64 a2,
        const char *a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, (void *)(unsigned int)this, (__int64)a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x1800060cc  sub     rsp, 38h
0x1800060d0  mov     rax, [rsp+38h]
0x1800060d5  mov     [rsp+38h+var_10], rax
0x1800060da  mov     edx, ecx
0x1800060dc  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
