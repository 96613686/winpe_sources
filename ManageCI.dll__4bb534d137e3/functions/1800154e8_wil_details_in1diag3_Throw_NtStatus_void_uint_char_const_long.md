# wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)

- ea: `0x1800154e8`
- end: `0x180015510`
- name: `?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800123e0`

## callees

- `0x180009b1c`

## string_xrefs

- `0x1800154f1`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_NtStatus(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = -1073741822;
  wil::details::ReportFailure_NtStatus<0>(
    (int)this,
    327,
    (int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
    (int)a4,
    v5,
    retaddr,
    v6);
}

```

## disassembly

```asm
0x1800154e8  sub     rsp, 48h
0x1800154ec  mov     rax, [rsp+48h]
0x1800154f1  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800154f8  mov     dword ptr [rsp+48h+var_18], 0C0000002h; wil::details *
0x180015500  mov     edx, 147h; int
0x180015505  mov     [rsp+48h+var_20], rax; __int64
0x18001550a  call    ??$ReportFailure_NtStatus@$0A@@details@wil@@YAJPEAXIPEBD110J@Z; wil::details::ReportFailure_NtStatus<0>(void *,uint,char const *,char const *,char const *,void *,long)
```
