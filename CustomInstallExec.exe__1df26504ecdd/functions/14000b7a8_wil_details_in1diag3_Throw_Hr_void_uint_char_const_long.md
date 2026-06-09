# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x14000b7a8`
- end: `0x14000b7c8`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140009918`
- `0x14000a43c`

## callees

- `0x140007c08`

## string_xrefs

- `0x14000b7b1`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

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
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x14000b7a8  sub     rsp, 48h
0x14000b7ac  mov     rax, [rsp+48h]
0x14000b7b1  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000b7b8  mov     [rsp+48h+var_18], r9d
0x14000b7bd  mov     [rsp+48h+var_20], rax
0x14000b7c2  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
