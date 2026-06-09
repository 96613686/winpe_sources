# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x180024174`
- end: `0x180024199`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800043fc`

## callees

- `0x1800112a0`

## string_xrefs

- `0x18002417d`: `onecoreuap\net\mobility\radiomanagement\dll\rmcommon.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>(
    (_DWORD)this,
    271,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\rmcommon.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180024174  sub     rsp, 48h
0x180024178  mov     rax, [rsp+48h]
0x18002417d  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180024184  mov     [rsp+48h+var_18], r9d
0x180024189  mov     edx, 10Fh
0x18002418e  mov     [rsp+48h+var_20], rax
0x180024193  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
