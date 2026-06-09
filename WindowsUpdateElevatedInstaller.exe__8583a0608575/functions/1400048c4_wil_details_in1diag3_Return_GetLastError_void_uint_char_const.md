# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400048c4`
- end: `0x1400048dd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cc4`
- `0x14000535c`

## callees

- `0x1400020b0`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x1400048c4  sub     rsp, 38h
0x1400048c8  mov     rax, [rsp+38h]
0x1400048cd  mov     [rsp+38h+var_10], rax
0x1400048d2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400048d7  nop
0x1400048d8  add     rsp, 38h
0x1400048dc  retn
```
