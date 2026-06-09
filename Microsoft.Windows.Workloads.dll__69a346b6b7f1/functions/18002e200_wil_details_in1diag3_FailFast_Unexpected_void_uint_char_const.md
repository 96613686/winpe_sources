# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18002e200`
- end: `0x18002e220`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800300f0`
- `0x1800302f0`

## callees

- `0x180010470`

## string_xrefs

- `0x18002e20e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3113,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18002e200  sub     rsp, 48h
0x18002e204  mov     rax, [rsp+48h]
0x18002e209  mov     [rsp+48h+var_20], rax
0x18002e20e  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002e215  mov     edx, 0C29h
0x18002e21a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
