# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x140011084`
- end: `0x14001109d`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140017604`
- `0x140017787`
- `0x140017823`
- `0x14001785f`
- `0x1400178d1`
- `0x1400179df`

## callees

- `0x140009624`

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
0x140011084  sub     rsp, 48h
0x140011088  mov     rax, [rsp+48h]
0x14001108d  mov     [rsp+48h+var_20], rax
0x140011092  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x140011097  nop
0x140011098  add     rsp, 48h
0x14001109c  retn
```
