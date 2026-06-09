# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1800047cc`
- end: `0x18000482f`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `99`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000769c`

## callees

- `0x180003c90`
- `0x180006744`

## string_xrefs

- `0x1800047fb`: `onecore\base\ci\management\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(__int64 a1, int a2)
{
  __int64 v2; // r9

  wil::details::HrToNtStatus((wil::details *)0x800700EALL, a2);
  wil::details::ReportFailure_Base<1,0>(v2, 347, "onecore\\base\\ci\\management\\dll\\dllmain.cpp");
  return 2147942634LL;
}

```

## disassembly

```asm
0x1800047cc  sub     rsp, 68h
0x1800047d0  mov     r9, rcx
0x1800047d3  mov     [rsp+68h+var_18], 800700EAh
0x1800047db  mov     ecx, 800700EAh; this
0x1800047e0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800047e5  mov     rdx, [rsp+68h+arg_28]
0x1800047ed  lea     rcx, [rsp+68h+var_18]
0x1800047f2  mov     [rsp+68h+var_30], 0
0x1800047fb  lea     r8, aOnecoreBaseCiM; "onecore\\base\\ci\\management\\dll\\dll"...
0x180004802  mov     [rsp+68h+var_38], rcx
0x180004807  mov     rcx, r9
0x18000480a  mov     [rsp+68h+var_40], rdx
0x18000480f  mov     edx, 15Bh
0x180004814  mov     [rsp+68h+var_14], eax
0x180004818  mov     [rsp+68h+var_10], 0
0x180004820  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180004825  mov     eax, 800700EAh
0x18000482a  add     rsp, 68h
0x18000482e  retn
```
