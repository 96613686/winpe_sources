# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x18000a848`
- end: `0x18000a861`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d5c4`
- `0x18000d600`
- `0x18000d699`
- `0x18000d6d8`
- `0x18000d7c4`
- `0x18000d827`

## callees

- `0x1800023dc`

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
0x18000a848  sub     rsp, 48h
0x18000a84c  mov     rax, [rsp+48h]
0x18000a851  mov     [rsp+48h+var_20], rax
0x18000a856  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000a85b  nop
0x18000a85c  add     rsp, 48h
0x18000a860  retn
```
