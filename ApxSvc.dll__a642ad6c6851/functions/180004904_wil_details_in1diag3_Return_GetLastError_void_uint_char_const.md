# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180004904`
- end: `0x18000491d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e94`
- `0x18000536c`

## callees

- `0x1800022b4`

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
0x180004904  sub     rsp, 38h
0x180004908  mov     rax, [rsp+38h]
0x18000490d  mov     [rsp+38h+var_10], rax
0x180004912  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180004917  nop
0x180004918  add     rsp, 38h
0x18000491c  retn
```
