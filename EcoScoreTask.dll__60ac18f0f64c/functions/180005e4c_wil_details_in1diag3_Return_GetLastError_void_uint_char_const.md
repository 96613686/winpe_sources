# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005e4c`
- end: `0x180005e64`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a24`
- `0x180006f5c`

## callees

- `0x180002704`

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
0x180005e4c  sub     rsp, 38h
0x180005e50  mov     rax, [rsp+38h]
0x180005e55  mov     [rsp+38h+var_10], rax
0x180005e5a  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005e5f  add     rsp, 38h
0x180005e63  retn
```
