# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180008dc0`
- end: `0x180008dd9`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a40e`
- `0x18000a446`
- `0x18000a49f`
- `0x18000a4e9`
- `0x18000a554`
- `0x18000a589`
- `0x18000a642`

## callees

- `0x180006b50`

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
0x180008dc0  sub     rsp, 48h
0x180008dc4  mov     rax, [rsp+48h]
0x180008dc9  mov     [rsp+48h+var_20], rax
0x180008dce  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180008dd3  nop
0x180008dd4  add     rsp, 48h
0x180008dd8  retn
```
