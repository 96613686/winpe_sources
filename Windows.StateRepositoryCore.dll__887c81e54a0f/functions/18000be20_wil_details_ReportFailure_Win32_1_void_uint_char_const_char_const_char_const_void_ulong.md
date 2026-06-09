# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000be20`
- end: `0x18000be75`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `85`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7d0`

## callees

- `0x180002ed8`
- `0x180006d20`

## string_xrefs

- `0x18000be53`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(__int64 a1, int a2)
{
  __int64 v2; // rdx
  __int64 v3; // r9

  wil::details::HrToNtStatus((wil::details *)0x80070490LL, a2);
  wil::details::ReportFailure_Base<1,0>(
    v3,
    v2,
    "onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp");
  return 2147943568LL;
}

```

## disassembly

```asm
0x18000be20  sub     rsp, 68h
0x18000be24  mov     r9, rcx
0x18000be27  mov     [rsp+68h+var_18], 80070490h
0x18000be2f  mov     ecx, 80070490h; this
0x18000be34  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000be39  mov     r8, [rsp+68h+arg_28]
0x18000be41  lea     rcx, [rsp+68h+var_18]
0x18000be46  mov     [rsp+68h+var_38], rcx
0x18000be4b  mov     rcx, r9
0x18000be4e  mov     [rsp+68h+var_40], r8
0x18000be53  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000be5a  mov     [rsp+68h+var_14], eax
0x18000be5e  mov     [rsp+68h+var_10], 0
0x18000be66  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000be6b  mov     eax, 80070490h
0x18000be70  add     rsp, 68h
0x18000be74  retn
```
