# wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x14000b808`
- end: `0x14000b82d`
- name: `?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140008bc4`

## callees

- `0x1400080bc`

## string_xrefs

- `0x14000b811`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>(
    (_DWORD)this,
    301,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x14000b808  sub     rsp, 48h
0x14000b80c  mov     rax, [rsp+48h]
0x14000b811  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000b818  mov     [rsp+48h+var_18], r9d
0x14000b81d  mov     edx, 12Dh
0x14000b822  mov     [rsp+48h+var_20], rax
0x14000b827  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
