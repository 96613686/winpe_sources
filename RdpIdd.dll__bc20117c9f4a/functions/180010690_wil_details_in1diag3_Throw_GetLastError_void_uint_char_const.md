# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x180010690`
- end: `0x1800106b0`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001086c`

## callees

- `0x18000e36c`

## string_xrefs

- `0x180010699`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    7368,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x180010690  sub     rsp, 38h
0x180010694  mov     rax, [rsp+38h]
0x180010699  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800106a0  mov     edx, 1CC8h; int
0x1800106a5  mov     [rsp+38h+var_10], rax; char *
0x1800106aa  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
