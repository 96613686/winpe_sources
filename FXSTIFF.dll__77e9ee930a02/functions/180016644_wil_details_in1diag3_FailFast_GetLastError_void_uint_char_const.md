# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180016644`
- end: `0x180016658`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180010db8`
- `0x180010df0`
- `0x18001133c`
- `0x180011648`
- `0x180011a14`
- `0x180011f54`
- `0x180014bc0`
- `0x180014d30`
- `0x180015dcc`
- `0x1800166b4`

## callees

- `0x1800101d4`

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
0x180016644  sub     rsp, 38h
0x180016648  mov     rax, [rsp+38h]
0x18001664d  mov     [rsp+38h+var_10], rax
0x180016652  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
