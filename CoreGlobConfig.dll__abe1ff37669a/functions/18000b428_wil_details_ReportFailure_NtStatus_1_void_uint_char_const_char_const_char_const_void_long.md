# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000b428`
- end: `0x18000b492`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018bec`

## callees

- `0x180005c30`
- `0x180016ab4`

## string_xrefs

- `0x18000b46f`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v10; // [rsp+50h] [rbp-38h]

  v10 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(
    a1,
    a2,
    "onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp");
  return v10;
}

```

## disassembly

```asm
0x18000b428  push    rbx
0x18000b42a  push    rbp
0x18000b42b  push    rsi
0x18000b42c  push    rdi
0x18000b42d  sub     rsp, 68h
0x18000b431  mov     ebx, dword ptr [rsp+88h+arg_30]
0x18000b438  mov     rbp, rcx
0x18000b43b  mov     ecx, ebx; this
0x18000b43d  mov     esi, edx
0x18000b43f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b444  mov     r8, [rsp+88h+arg_28]
0x18000b44c  mov     edi, eax
0x18000b44e  mov     [rsp+88h+var_38], eax
0x18000b452  mov     edx, esi
0x18000b454  lea     rax, [rsp+88h+var_38]
0x18000b459  mov     [rsp+88h+var_50], 0
0x18000b462  mov     [rsp+88h+var_58], rax
0x18000b467  mov     rcx, rbp
0x18000b46a  mov     [rsp+88h+var_60], r8
0x18000b46f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000b476  mov     [rsp+88h+var_34], ebx
0x18000b47a  mov     [rsp+88h+var_30], 1
0x18000b482  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b487  mov     eax, edi
0x18000b489  add     rsp, 68h
0x18000b48d  pop     rdi
0x18000b48e  pop     rsi
0x18000b48f  pop     rbp
0x18000b490  pop     rbx
0x18000b491  retn
```
