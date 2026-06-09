# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140004704`
- end: `0x14000471d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c94`
- `0x14000516c`
- `0x1400057f8`
- `0x140005ca0`

## callees

- `0x140002100`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x140004704  sub     rsp, 38h
0x140004708  mov     rax, [rsp+38h]
0x14000470d  mov     [rsp+38h+var_10], rax
0x140004712  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140004717  nop
0x140004718  add     rsp, 38h
0x14000471c  retn
```
