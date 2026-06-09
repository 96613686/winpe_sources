# wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)

- ea: `0x1400063c4`
- end: `0x1400063e7`
- name: `?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z`
- size: `35`
- prototype: `__int64 __fastcall(wil::details::in1diag5 *__hidden this, void *, unsigned int, const char *, const char *, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004da8`
- `0x140007104`
- `0x14000759c`
- `0x140007a78`

## callees

- `0x1400022a8`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag5::Return_GetLastError(
        wil::details::in1diag5 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5)
{
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastErrorHr<1>(
           (__int64)this,
           (unsigned int)a2,
           a3,
           (__int64)a4,
           (__int64)a5,
           retaddr);
}

```

## disassembly

```asm
0x1400063c4  sub     rsp, 38h
0x1400063c8  mov     rax, [rsp+38h]
0x1400063cd  mov     [rsp+38h+var_10], rax
0x1400063d2  mov     rax, [rsp+38h+arg_20]
0x1400063d7  mov     [rsp+38h+var_18], rax
0x1400063dc  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400063e1  nop
0x1400063e2  add     rsp, 38h
0x1400063e6  retn
```
