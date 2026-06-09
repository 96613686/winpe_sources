# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180009154`
- end: `0x18000916d`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011200`
- `0x180011640`
- `0x1800116a0`
- `0x1800116df`
- `0x180011751`

## callees

- `0x180003cf4`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180009154  sub     rsp, 48h
0x180009158  mov     rax, [rsp+48h]
0x18000915d  mov     [rsp+48h+var_20], rax
0x180009162  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180009167  nop
0x180009168  add     rsp, 48h
0x18000916c  retn
```
