# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18000ce08`
- end: `0x18000ce2d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18000cad4`

## callees

- `0x180003a84`

## string_xrefs

- `0x18000ce1b`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    285,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000ce08  sub     rsp, 48h
0x18000ce0c  mov     rax, [rsp+48h]
0x18000ce11  mov     [rsp+48h+var_18], r9d
0x18000ce16  mov     [rsp+48h+var_20], rax
0x18000ce1b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ce22  mov     edx, 11Dh
0x18000ce27  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
