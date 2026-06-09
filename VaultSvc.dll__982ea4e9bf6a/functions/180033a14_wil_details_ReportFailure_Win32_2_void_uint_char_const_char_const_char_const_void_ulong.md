# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180033a14`
- end: `0x180033a83`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180045600`

## callees

- `0x180033a14`
- `0x180033a8c`
- `0x180041e88`

## string_xrefs

- `0x180033a6f`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  int v9; // edx
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v10,
    v9,
    (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
    0,
    v8,
    a6,
    (__int64)v12);
  return v7;
}

```

## disassembly

```asm
0x180033a14  push    rbx
0x180033a16  sub     rsp, 60h
0x180033a1a  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180033a21  xor     r8d, r8d
0x180033a24  mov     r10, rcx
0x180033a27  test    ebx, ebx
0x180033a29  jle     short loc_180033A34
0x180033a2b  movzx   ebx, bx
0x180033a2e  or      ebx, 80070000h
0x180033a34  mov     ecx, ebx; this
0x180033a36  mov     [rsp+68h+var_18], ebx
0x180033a3a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180033a3f  mov     rcx, [rsp+68h+arg_28]
0x180033a47  xor     r9d, r9d
0x180033a4a  mov     [rsp+68h+var_20], r8d
0x180033a4f  mov     [rsp+68h+var_14], eax
0x180033a53  lea     rax, [rsp+68h+var_18]
0x180033a58  mov     [rsp+68h+var_38], rax
0x180033a5d  mov     [rsp+68h+var_40], rcx
0x180033a62  mov     rcx, r10
0x180033a65  mov     [rsp+68h+var_48], r8
0x180033a6a  mov     [rsp+68h+var_10], r8d
0x180033a6f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x180033a76  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180033a7b  mov     eax, ebx
0x180033a7d  add     rsp, 60h
0x180033a81  pop     rbx
0x180033a82  retn
```
