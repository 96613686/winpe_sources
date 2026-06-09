# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005b08`
- end: `0x180005b21`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d50`
- `0x180005f94`
- `0x18000683c`
- `0x1800087b0`
- `0x1800090dc`
- `0x18000f814`

## callees

- `0x180003698`

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
0x180005b08  sub     rsp, 38h
0x180005b0c  mov     rax, [rsp+38h]
0x180005b11  mov     [rsp+38h+var_10], rax
0x180005b16  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005b1b  add     rsp, 38h
0x180005b1f  retn
```
