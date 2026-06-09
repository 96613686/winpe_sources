# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400040d8`
- end: `0x1400040f0`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035dc`
- `0x140004694`

## callees

- `0x14000212c`

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
0x1400040d8  sub     rsp, 38h
0x1400040dc  mov     rax, [rsp+38h]
0x1400040e1  mov     [rsp+38h+var_10], rax
0x1400040e6  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400040eb  add     rsp, 38h
0x1400040ef  retn
```
