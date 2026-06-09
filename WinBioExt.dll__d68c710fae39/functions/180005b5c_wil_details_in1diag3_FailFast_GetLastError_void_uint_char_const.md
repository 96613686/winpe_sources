# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180005b5c`
- end: `0x180005b70`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e98`
- `0x180003168`
- `0x180003518`
- `0x180003740`
- `0x180004a4c`
- `0x18000579c`
- `0x180007290`
- `0x180007824`
- `0x1800090c0`

## callees

- `0x180002468`

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
0x180005b5c  sub     rsp, 38h
0x180005b60  mov     rax, [rsp+38h]
0x180005b65  mov     [rsp+38h+var_10], rax
0x180005b6a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
