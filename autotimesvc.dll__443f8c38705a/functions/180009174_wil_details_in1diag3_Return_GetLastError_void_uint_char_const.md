# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180009174`
- end: `0x18000918d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070c8`
- `0x180009f48`
- `0x18000ce84`
- `0x18000fcfc`
- `0x180010068`
- `0x180010578`
- `0x180010800`

## callees

- `0x18000418c`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180009174  sub     rsp, 38h
0x180009178  mov     rax, [rsp+38h]
0x18000917d  mov     [rsp+38h+var_10], rax
0x180009182  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180009187  nop
0x180009188  add     rsp, 38h
0x18000918c  retn
```
