# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180007214`
- end: `0x18000722e`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a44`
- `0x180007b2c`

## callees

- `0x180001fd0`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x180007214  sub     rsp, 38h
0x180007218  mov     rax, [rsp+38h]
0x18000721d  mov     [rsp+38h+var_10], rax
0x180007222  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180007227  nop
0x180007228  add     rsp, 38h
0x18000722c  retn
```
