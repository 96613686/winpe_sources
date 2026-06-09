# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x1800154c0`
- end: `0x1800154e0`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011c00`
- `0x180012280`
- `0x1800123e0`
- `0x180012f90`

## callees

- `0x180004120`

## string_xrefs

- `0x1800154c9`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800154c0  sub     rsp, 48h
0x1800154c4  mov     rax, [rsp+48h]
0x1800154c9  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800154d0  mov     [rsp+48h+var_18], r9d
0x1800154d5  mov     [rsp+48h+var_20], rax
0x1800154da  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
