# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000f6f0`
- end: `0x18000f704`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c204`
- `0x18000c2d0`
- `0x18000c304`
- `0x18000c370`
- `0x18000c450`
- `0x18000cfac`
- `0x18000d1dc`
- `0x18000eeb8`
- `0x18000f36c`
- `0x180010da0`
- `0x1800114d8`
- `0x1800150cc`

## callees

- `0x18000b9a8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x18000f6f0  sub     rsp, 38h
0x18000f6f4  mov     rax, [rsp+38h]
0x18000f6f9  mov     [rsp+38h+var_10], rax
0x18000f6fe  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
