# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1800172c8`
- end: `0x18001732a`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017b04`

## callees

- `0x18000a360`
- `0x18000a36c`
- `0x1800172c8`

## string_xrefs

- `0x1800172f8`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v9, v8, "onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp");
  return v7;
}

```

## disassembly

```asm
0x1800172c8  push    rbx
0x1800172ca  sub     rsp, 60h
0x1800172ce  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1800172d5  mov     r9, rcx
0x1800172d8  test    ebx, ebx
0x1800172da  jle     short loc_1800172E5
0x1800172dc  movzx   ebx, bx
0x1800172df  or      ebx, 80070000h
0x1800172e5  mov     ecx, ebx; this
0x1800172e7  mov     [rsp+68h+var_18], ebx
0x1800172eb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800172f0  mov     rcx, [rsp+68h+arg_28]
0x1800172f8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x1800172ff  mov     [rsp+68h+var_14], eax
0x180017303  lea     rax, [rsp+68h+var_18]
0x180017308  mov     [rsp+68h+var_38], rax
0x18001730d  mov     [rsp+68h+var_40], rcx
0x180017312  mov     rcx, r9
0x180017315  mov     [rsp+68h+var_10], 0
0x18001731d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180017322  mov     eax, ebx
0x180017324  add     rsp, 60h
0x180017328  pop     rbx
0x180017329  retn
```
