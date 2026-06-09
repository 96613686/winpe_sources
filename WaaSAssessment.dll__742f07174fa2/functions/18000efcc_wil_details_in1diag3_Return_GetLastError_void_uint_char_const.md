# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x18000efcc`
- end: `0x18000efe4`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e900`
- `0x18000f36c`
- `0x1800138d0`
- `0x1800191c4`
- `0x180019290`
- `0x1800193b8`
- `0x1800194f4`

## callees

- `0x18000ba28`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x18000efcc  sub     rsp, 38h
0x18000efd0  mov     rax, [rsp+38h]
0x18000efd5  mov     [rsp+38h+var_10], rax
0x18000efda  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x18000efdf  add     rsp, 38h
0x18000efe3  retn
```
