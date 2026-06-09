# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x140004a10`
- end: `0x140004a24`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b90`
- `0x140004060`
- `0x140004f48`
- `0x140005110`
- `0x1400054fc`

## callees

- `0x1400020c0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x140004a10  sub     rsp, 38h
0x140004a14  mov     rax, [rsp+38h]
0x140004a19  mov     [rsp+38h+var_10], rax
0x140004a1e  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
