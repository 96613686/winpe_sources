# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x18000a9b0`
- end: `0x18000a9c9`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c444`
- `0x18000c62f`
- `0x18000c667`
- `0x18000c6cf`
- `0x18000c704`

## callees

- `0x180007adc`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>((__int64)this, (unsigned int)a2);
}

```

## disassembly

```asm
0x18000a9b0  sub     rsp, 48h
0x18000a9b4  mov     rax, [rsp+48h]
0x18000a9b9  mov     [rsp+48h+var_20], rax
0x18000a9be  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000a9c3  nop
0x18000a9c4  add     rsp, 48h
0x18000a9c8  retn
```
