# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000fb00`
- end: `0x18000fb6b`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010044`

## callees

- `0x180003c30`
- `0x180007278`
- `0x18000fb00`

## string_xrefs

- `0x18000fb30`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

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
  int v8; // edx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v7;
}

```

## disassembly

```asm
0x18000fb00  push    rbx
0x18000fb02  sub     rsp, 60h
0x18000fb06  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000fb0d  mov     r9, rcx
0x18000fb10  test    ebx, ebx
0x18000fb12  jle     short loc_18000FB1D
0x18000fb14  movzx   ebx, bx
0x18000fb17  or      ebx, 80070000h
0x18000fb1d  mov     ecx, ebx; this
0x18000fb1f  mov     [rsp+68h+var_18], ebx
0x18000fb23  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fb28  mov     rcx, [rsp+68h+arg_28]
0x18000fb30  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000fb37  mov     [rsp+68h+var_14], eax
0x18000fb3b  lea     rax, [rsp+68h+var_18]
0x18000fb40  mov     [rsp+68h+var_30], 0
0x18000fb49  mov     [rsp+68h+var_38], rax
0x18000fb4e  mov     [rsp+68h+var_40], rcx
0x18000fb53  mov     rcx, r9
0x18000fb56  mov     [rsp+68h+var_10], 0
0x18000fb5e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fb63  mov     eax, ebx
0x18000fb65  add     rsp, 60h
0x18000fb69  pop     rbx
0x18000fb6a  retn
```
