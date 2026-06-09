# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005964`
- end: `0x18000597d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d64`
- `0x1800063ec`
- `0x1800093b0`
- `0x180009470`

## callees

- `0x18000312c`

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
0x180005964  sub     rsp, 38h
0x180005968  mov     rax, [rsp+38h]
0x18000596d  mov     [rsp+38h+var_10], rax
0x180005972  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005977  nop
0x180005978  add     rsp, 38h
0x18000597c  retn
```
