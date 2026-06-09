# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400065c4`
- end: `0x1400065de`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003700`
- `0x140005238`
- `0x140005e44`
- `0x140006e34`

## callees

- `0x1400024fc`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1400065c4  sub     rsp, 38h
0x1400065c8  mov     rax, [rsp+38h]
0x1400065cd  mov     [rsp+38h+var_10], rax
0x1400065d2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400065d7  nop
0x1400065d8  add     rsp, 38h
0x1400065dc  retn
```
