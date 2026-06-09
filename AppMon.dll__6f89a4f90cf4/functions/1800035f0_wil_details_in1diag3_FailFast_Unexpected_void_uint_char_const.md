# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800035f0`
- end: `0x180003618`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005638`

## callees

- `0x180002abc`

## string_xrefs

- `0x180003606`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = -2147418113;
  wil::details::ReportFailure_Hr<3>(
    (int)this,
    3585,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (int)a4,
    v4,
    retaddr,
    v5);
}

```

## disassembly

```asm
0x1800035f0  sub     rsp, 48h
0x1800035f4  mov     rax, [rsp+48h]
0x1800035f9  mov     dword ptr [rsp+48h+var_18], 8000FFFFh; wil::details *
0x180003601  mov     [rsp+48h+var_20], rax; __int64
0x180003606  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000360d  mov     edx, 0E01h; int
0x180003612  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
