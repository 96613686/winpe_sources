# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x1800037e4`
- end: `0x1800037f8`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001db0`
- `0x180002130`
- `0x180002670`

## callees

- `0x1800061e8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1800037e4  sub     rsp, 38h
0x1800037e8  mov     rax, [rsp+38h]
0x1800037ed  mov     [rsp+38h+var_10], rax
0x1800037f2  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
