# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180009fd8`
- end: `0x180009ff1`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800118ee`
- `0x180011951`
- `0x180011afe`

## callees

- `0x180007e18`

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
0x180009fd8  sub     rsp, 48h
0x180009fdc  mov     rax, [rsp+48h]
0x180009fe1  mov     [rsp+48h+var_20], rax
0x180009fe6  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180009feb  nop
0x180009fec  add     rsp, 48h
0x180009ff0  retn
```
