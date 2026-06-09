# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x14000d1e4`
- end: `0x14000d204`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d6f0`

## callees

- `0x140007f74`

## string_xrefs

- `0x14000d1ed`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x14000d1e4  sub     rsp, 38h
0x14000d1e8  mov     rax, [rsp+38h]
0x14000d1ed  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000d1f4  mov     edx, 1CC8h; int
0x14000d1f9  mov     [rsp+38h+var_10], rax; char *
0x14000d1fe  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
