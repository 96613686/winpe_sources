# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800061f4`
- end: `0x18000620d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003504`
- `0x180004610`
- `0x180008010`
- `0x180008f3c`

## callees

- `0x180003dbc`

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
0x1800061f4  sub     rsp, 38h
0x1800061f8  mov     rax, [rsp+38h]
0x1800061fd  mov     [rsp+38h+var_10], rax
0x180006202  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180006207  nop
0x180006208  add     rsp, 38h
0x18000620c  retn
```
