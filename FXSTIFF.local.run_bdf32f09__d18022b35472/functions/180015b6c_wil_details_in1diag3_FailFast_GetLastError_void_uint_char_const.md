# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180015b6c`
- end: `0x180015b80`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18001053c`
- `0x180010608`
- `0x1800106b4`
- `0x1800106e8`
- `0x180010ca4`
- `0x180010f58`
- `0x180011324`
- `0x180011708`
- `0x180011930`
- `0x180014370`
- `0x180014484`
- `0x18001531c`

## callees

- `0x18000fa34`

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
0x180015b6c  sub     rsp, 38h
0x180015b70  mov     rax, [rsp+38h]
0x180015b75  mov     [rsp+38h+var_10], rax
0x180015b7a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
