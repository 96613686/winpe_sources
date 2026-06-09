# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18000e994`
- end: `0x18000e9b4`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000afa0`

## callees

- `0x180002590`

## string_xrefs

- `0x18000e9a7`: `onecore\windows\advcore\winrt\inputinjectionbroker\common\lib\inputinjector.cpp`

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
    (_DWORD)a2,
    (unsigned int)"onecore\\windows\\advcore\\winrt\\inputinjectionbroker\\common\\lib\\inputinjector.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000e994  sub     rsp, 48h
0x18000e998  mov     rax, [rsp+48h]
0x18000e99d  mov     [rsp+48h+var_18], r9d
0x18000e9a2  mov     [rsp+48h+var_20], rax
0x18000e9a7  lea     r8, aOnecoreWindows; "onecore\\windows\\advcore\\winrt\\input"...
0x18000e9ae  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
