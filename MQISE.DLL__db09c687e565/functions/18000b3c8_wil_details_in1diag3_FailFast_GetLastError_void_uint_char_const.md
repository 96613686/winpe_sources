# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000b3c8`
- end: `0x18000b3dc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034bc`
- `0x180003588`
- `0x1800037b0`
- `0x180003804`
- `0x180003f70`
- `0x1800044a8`
- `0x18000487c`
- `0x180005310`
- `0x180005938`
- `0x1800092b8`
- `0x1800093d8`
- `0x18000a534`

## callees

- `0x180002334`

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
0x18000b3c8  sub     rsp, 38h
0x18000b3cc  mov     rax, [rsp+38h]
0x18000b3d1  mov     [rsp+38h+var_10], rax
0x18000b3d6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
