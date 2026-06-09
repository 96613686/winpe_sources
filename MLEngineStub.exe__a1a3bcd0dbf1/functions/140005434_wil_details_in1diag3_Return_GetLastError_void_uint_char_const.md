# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140005434`
- end: `0x14000544d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049c4`
- `0x140005ebc`
- `0x140008bb0`

## callees

- `0x140002de8`

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
0x140005434  sub     rsp, 38h
0x140005438  mov     rax, [rsp+38h]
0x14000543d  mov     [rsp+38h+var_10], rax
0x140005442  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140005447  nop
0x140005448  add     rsp, 38h
0x14000544c  retn
```
