# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x18000befc`
- end: `0x18000bf15`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `57`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c60b`
- `0x18002c659`
- `0x18002c6a7`
- `0x18002c6e3`
- `0x18002c71f`
- `0x18002c7c7`
- `0x18002c818`
- `0x18002c854`
- `0x18002ca2f`
- `0x18002ca6e`
- `0x18002cb08`
- `0x18002cb6b`
- `0x18002cbb9`
- `0x18002cbf5`
- `0x18002cc55`
- `0x18002cc94`
- `0x18002cce2`
- `0x18002cd1e`
- `0x18002cd5a`
- `0x18002cda8`
- `0x18002cee8`
- `0x18002cf5a`
- `0x18002cf99`
- `0x18002d00e`
- `0x18002d04a`
- `0x18002d0aa`
- `0x18002d0fb`
- `0x18002d149`
- `0x18002d185`
- `0x18002d1c4`
- `0x18002d227`
- `0x18002d263`
- `0x18002d29f`
- `0x18002d2db`
- `0x18002d317`
- `0x18002d356`
- `0x18002d3dd`
- `0x18002d440`
- `0x18002d491`
- `0x18002d4f4`
- `0x18002d57b`
- `0x18002d5ba`
- `0x18002d620`
- `0x18002d683`
- `0x18002d6c2`
- `0x18002d701`
- `0x18002d740`
- `0x18002d77c`
- `0x18002d7ca`
- `0x18002d81b`

## callees

- `0x180008468`

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
0x18000befc  sub     rsp, 48h
0x18000bf00  mov     rax, [rsp+48h]
0x18000bf05  mov     [rsp+48h+var_20], rax
0x18000bf0a  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000bf0f  nop
0x18000bf10  add     rsp, 48h
0x18000bf14  retn
```
