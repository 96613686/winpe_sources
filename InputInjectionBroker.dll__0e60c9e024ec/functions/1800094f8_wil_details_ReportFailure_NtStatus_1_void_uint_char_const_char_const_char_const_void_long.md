# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x1800094f8`
- end: `0x180009567`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dec0`

## callees

- `0x18000232c`
- `0x18000c984`

## string_xrefs

- `0x180009520`: `onecore\windows\advcore\winrt\inputinjectionbroker\common\lib\inputinjector.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // [rsp+50h] [rbp-18h]

  v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(
    a1,
    1635,
    "onecore\\windows\\advcore\\winrt\\inputinjectionbroker\\common\\lib\\inputinjector.cpp");
  return v9;
}

```

## disassembly

```asm
0x1800094f8  mov     [rsp+arg_0], rbx
0x1800094fd  mov     [rsp+arg_8], rsi
0x180009502  push    rdi
0x180009503  sub     rsp, 60h
0x180009507  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000950e  mov     rsi, rcx
0x180009511  mov     ecx, ebx; this
0x180009513  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009518  mov     rdx, [rsp+68h+arg_28]
0x180009520  lea     r8, aOnecoreWindows; "onecore\\windows\\advcore\\winrt\\input"...
0x180009527  mov     edi, eax
0x180009529  mov     [rsp+68h+var_18], eax
0x18000952d  lea     rax, [rsp+68h+var_18]
0x180009532  mov     [rsp+68h+var_14], ebx
0x180009536  mov     [rsp+68h+var_38], rax
0x18000953b  mov     rcx, rsi
0x18000953e  mov     [rsp+68h+var_40], rdx
0x180009543  mov     edx, 663h
0x180009548  mov     [rsp+68h+var_10], 1
0x180009550  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180009555  mov     rbx, [rsp+68h+arg_0]
0x18000955a  mov     eax, edi
0x18000955c  mov     rsi, [rsp+68h+arg_8]
0x180009561  add     rsp, 60h
0x180009565  pop     rdi
0x180009566  retn
```
