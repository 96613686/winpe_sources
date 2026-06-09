# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x1800071f4`
- end: `0x18000720e`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a0dc`
- `0x18000a1e9`
- `0x18000a245`
- `0x18000a27d`
- `0x18000a70f`
- `0x18000a77d`

## callees

- `0x180001df8`

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
0x1800071f4  sub     rsp, 48h
0x1800071f8  mov     rax, [rsp+48h]
0x1800071fd  mov     [rsp+48h+var_20], rax
0x180007202  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180007207  nop
0x180007208  add     rsp, 48h
0x18000720c  retn
```
