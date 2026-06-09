# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000d930`
- end: `0x18000d987`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `87`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f0bc`

## callees

- `0x180003cc8`
- `0x180007278`
- `0x18000d930`

## string_xrefs

- `0x18000d958`: `onecore\base\time\autotime\timeservice\regkey.cpp`

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
  wil::details::ReportFailure_Base<0,0>(
    v9,
    v8,
    (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\regkey.cpp",
    v9);
}

```

## disassembly

```asm
0x18000d930  sub     rsp, 68h
0x18000d934  mov     r9, rcx
0x18000d937  mov     ecx, [rsp+68h+arg_30]
0x18000d93e  test    ecx, ecx
0x18000d940  jle     short loc_18000D94B
0x18000d942  movzx   ecx, cx
0x18000d945  or      ecx, 80070000h; this
0x18000d94b  mov     [rsp+68h+var_18], ecx
0x18000d94f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d954  mov     [rsp+68h+var_14], eax
0x18000d958  lea     r8, aOnecoreBaseTim_5; "onecore\\base\\time\\autotime\\timeserv"...
0x18000d95f  lea     rax, [rsp+68h+var_18]
0x18000d964  mov     [rsp+68h+var_10], 0
0x18000d96c  mov     [rsp+68h+var_38], rax
0x18000d971  mov     rcx, r9
0x18000d974  mov     rax, [rsp+68h+arg_28]
0x18000d97c  mov     [rsp+68h+var_40], rax
0x18000d981  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
