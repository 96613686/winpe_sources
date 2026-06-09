# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180009ad4`
- end: `0x180009ae8`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046c0`
- `0x180004b58`
- `0x180005ac0`
- `0x180008768`
- `0x18000941c`

## callees

- `0x180003c40`

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
0x180009ad4  sub     rsp, 38h
0x180009ad8  mov     rax, [rsp+38h]
0x180009add  mov     [rsp+38h+var_10], rax
0x180009ae2  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
