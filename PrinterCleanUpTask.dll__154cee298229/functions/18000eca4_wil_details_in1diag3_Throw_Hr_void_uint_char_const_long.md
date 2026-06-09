# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000eca4`
- end: `0x18000ecc4`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000b11c`
- `0x18000b308`

## callees

- `0x180005c6c`

## string_xrefs

- `0x18000ecad`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

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
    (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000eca4  sub     rsp, 48h
0x18000eca8  mov     rax, [rsp+48h]
0x18000ecad  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000ecb4  mov     [rsp+48h+var_18], r9d
0x18000ecb9  mov     [rsp+48h+var_20], rax
0x18000ecbe  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
