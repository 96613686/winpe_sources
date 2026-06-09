# wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180013a00`
- end: `0x180013a25`
- name: `?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d240`

## callees

- `0x180003af4`

## string_xrefs

- `0x180013a13`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<3>(
    (int)this,
    3249,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
    (int)a4,
    v5,
    retaddr,
    v6);
}

```

## disassembly

```asm
0x180013a00  sub     rsp, 48h
0x180013a04  mov     rax, [rsp+48h]
0x180013a09  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180013a0e  mov     [rsp+48h+var_20], rax; __int64
0x180013a13  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013a1a  mov     edx, 0CB1h; int
0x180013a1f  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
