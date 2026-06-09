# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180009014`
- end: `0x180009028`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b9c`
- `0x180004038`
- `0x180004fa0`
- `0x180007c58`
- `0x18000893c`
- `0x18000d190`
- `0x18000d3e4`
- `0x18000f144`
- `0x18000f4e0`
- `0x18000f570`
- `0x180010260`
- `0x180010b10`
- `0x180010cc0`
- `0x180012b04`

## callees

- `0x18000311c`

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
0x180009014  sub     rsp, 38h
0x180009018  mov     rax, [rsp+38h]
0x18000901d  mov     [rsp+38h+var_10], rax
0x180009022  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
