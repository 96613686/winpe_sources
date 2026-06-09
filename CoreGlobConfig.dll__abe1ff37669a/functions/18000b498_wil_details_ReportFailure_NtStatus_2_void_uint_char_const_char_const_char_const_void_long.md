# wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000b498`
- end: `0x18000b51a`
- name: `??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `130`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d3e4`

## callees

- `0x180005c3c`
- `0x180016ab4`

## string_xrefs

- `0x18000b4c0`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  _DWORD v10[6]; // [rsp+50h] [rbp-18h] BYREF

  v10[0] = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v8 = v10[0];
  v10[1] = (_DWORD)a7;
  v10[2] = 1;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    843,
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    0,
    0,
    a6,
    (__int64)v10,
    0);
  return v8;
}

```

## disassembly

```asm
0x18000b498  mov     [rsp+arg_0], rbx
0x18000b49d  mov     [rsp+arg_8], rsi
0x18000b4a2  push    rdi
0x18000b4a3  sub     rsp, 60h
0x18000b4a7  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000b4ae  mov     rsi, rcx
0x18000b4b1  mov     ecx, ebx; this
0x18000b4b3  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b4b8  mov     rdx, [rsp+68h+arg_28]
0x18000b4c0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000b4c7  xor     ecx, ecx
0x18000b4c9  mov     [rsp+68h+var_18], eax
0x18000b4cd  mov     [rsp+68h+var_20], ecx
0x18000b4d1  mov     edi, eax
0x18000b4d3  mov     [rsp+68h+var_30], rcx
0x18000b4d8  lea     rax, [rsp+68h+var_18]
0x18000b4dd  mov     [rsp+68h+var_38], rax
0x18000b4e2  xor     r9d, r9d
0x18000b4e5  mov     [rsp+68h+var_40], rdx
0x18000b4ea  mov     edx, 34Bh
0x18000b4ef  mov     [rsp+68h+var_48], rcx
0x18000b4f4  mov     rcx, rsi
0x18000b4f7  mov     [rsp+68h+var_14], ebx
0x18000b4fb  mov     [rsp+68h+var_10], 1
0x18000b503  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b508  mov     rbx, [rsp+68h+arg_0]
0x18000b50d  mov     eax, edi
0x18000b50f  mov     rsi, [rsp+68h+arg_8]
0x18000b514  add     rsp, 60h
0x18000b518  pop     rdi
0x18000b519  retn
```
