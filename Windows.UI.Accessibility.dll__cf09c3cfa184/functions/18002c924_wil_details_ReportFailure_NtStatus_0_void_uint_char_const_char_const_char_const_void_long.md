# wil::details::ReportFailure_NtStatus<0>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18002c924`
- end: `0x18002c97f`
- name: `??$ReportFailure_NtStatus@$0A@@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `91`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002dcf4`

## callees

- `0x1800086b0`
- `0x18000ad68`

## string_xrefs

- `0x18002c94a`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<0>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  int v9; // r9d

  wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<0,0>(
    a1,
    a2,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
    v9);
}

```

## disassembly

```asm
0x18002c924  mov     [rsp+arg_0], rbx
0x18002c929  mov     [rsp+arg_8], rsi
0x18002c92e  push    rdi
0x18002c92f  sub     rsp, 60h
0x18002c933  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18002c93a  mov     rsi, rcx
0x18002c93d  mov     ecx, ebx; this
0x18002c93f  mov     edi, edx
0x18002c941  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18002c946  mov     [rsp+68h+var_18], eax
0x18002c94a  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002c951  lea     rax, [rsp+68h+var_18]
0x18002c956  mov     [rsp+68h+var_14], ebx
0x18002c95a  mov     [rsp+68h+var_38], rax
0x18002c95f  mov     edx, edi
0x18002c961  mov     rax, [rsp+68h+arg_28]
0x18002c969  mov     rcx, rsi
0x18002c96c  mov     [rsp+68h+var_40], rax
0x18002c971  mov     [rsp+68h+var_10], 1
0x18002c979  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
