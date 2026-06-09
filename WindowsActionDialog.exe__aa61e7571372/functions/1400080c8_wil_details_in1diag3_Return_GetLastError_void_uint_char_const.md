# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400080c8`
- end: `0x1400080ed`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `37`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008368`
- `0x140008a3c`
- `0x140009080`

## callees

- `0x1400022a8`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastErrorHr<1>((__int64)this, (unsigned int)a2, a3, 0, 0, retaddr);
}

```

## disassembly

```asm
0x1400080c8  sub     rsp, 38h
0x1400080cc  mov     rax, [rsp+38h]
0x1400080d1  mov     [rsp+38h+var_10], rax
0x1400080d6  mov     [rsp+38h+var_18], 0
0x1400080df  xor     r9d, r9d
0x1400080e2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400080e7  nop
0x1400080e8  add     rsp, 38h
0x1400080ec  retn
```
