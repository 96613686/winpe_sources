# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000eed0`
- end: `0x18000ef31`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `97`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015518`
- `0x1800157c4`

## callees

- `0x180003d28`
- `0x180006744`
- `0x18000eed0`

## string_xrefs

- `0x18000ef1f`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Win32<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  unsigned __int64 v7; // rcx
  int v8; // edx
  int v9; // r9d

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<0,0>(v9, v8, (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp", v9);
}

```

## disassembly

```asm
0x18000eed0  sub     rsp, 68h
0x18000eed4  mov     r9, rcx
0x18000eed7  xor     r8d, r8d
0x18000eeda  mov     ecx, [rsp+68h+arg_30]
0x18000eee1  test    ecx, ecx
0x18000eee3  jle     short loc_18000EEEE
0x18000eee5  movzx   ecx, cx
0x18000eee8  or      ecx, 80070000h; this
0x18000eeee  mov     [rsp+68h+var_18], ecx
0x18000eef2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000eef7  mov     [rsp+68h+var_28], r8d
0x18000eefc  mov     rcx, r9
0x18000eeff  mov     [rsp+68h+var_30], r8
0x18000ef04  mov     [rsp+68h+var_14], eax
0x18000ef08  lea     rax, [rsp+68h+var_18]
0x18000ef0d  mov     [rsp+68h+var_38], rax
0x18000ef12  mov     rax, [rsp+68h+arg_28]
0x18000ef1a  mov     [rsp+68h+var_10], r8d
0x18000ef1f  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000ef26  mov     [rsp+68h+var_40], rax
0x18000ef2b  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
