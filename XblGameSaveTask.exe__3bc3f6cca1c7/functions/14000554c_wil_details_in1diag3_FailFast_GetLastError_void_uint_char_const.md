# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x14000554c`
- end: `0x140005560`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a8c`
- `0x140002d58`
- `0x1400030fc`
- `0x14000455c`
- `0x14000516c`

## callees

- `0x140002088`

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
0x14000554c  sub     rsp, 38h
0x140005550  mov     rax, [rsp+38h]
0x140005555  mov     [rsp+38h+var_10], rax
0x14000555a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
