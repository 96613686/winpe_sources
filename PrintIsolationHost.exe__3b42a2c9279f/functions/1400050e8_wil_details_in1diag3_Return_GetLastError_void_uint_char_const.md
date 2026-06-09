# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400050e8`
- end: `0x140005100`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400041c0`
- `0x1400054ec`

## callees

- `0x14000284c`

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
0x1400050e8  sub     rsp, 38h
0x1400050ec  mov     rax, [rsp+38h]
0x1400050f1  mov     [rsp+38h+var_10], rax
0x1400050f6  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400050fb  add     rsp, 38h
0x1400050ff  retn
```
