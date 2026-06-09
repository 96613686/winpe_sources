# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000b5b8`
- end: `0x18000b623`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018c10`

## callees

- `0x180005c30`
- `0x180007754`
- `0x18000b5b8`

## string_xrefs

- `0x18000b5e8`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

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
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    "onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp");
  return v7;
}

```

## disassembly

```asm
0x18000b5b8  push    rbx
0x18000b5ba  sub     rsp, 60h
0x18000b5be  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000b5c5  mov     r9, rcx
0x18000b5c8  test    ebx, ebx
0x18000b5ca  jle     short loc_18000B5D5
0x18000b5cc  movzx   ebx, bx
0x18000b5cf  or      ebx, 80070000h
0x18000b5d5  mov     ecx, ebx; this
0x18000b5d7  mov     [rsp+68h+var_18], ebx
0x18000b5db  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b5e0  mov     rcx, [rsp+68h+arg_28]
0x18000b5e8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000b5ef  mov     [rsp+68h+var_14], eax
0x18000b5f3  lea     rax, [rsp+68h+var_18]
0x18000b5f8  mov     [rsp+68h+var_30], 0
0x18000b601  mov     [rsp+68h+var_38], rax
0x18000b606  mov     [rsp+68h+var_40], rcx
0x18000b60b  mov     rcx, r9
0x18000b60e  mov     [rsp+68h+var_10], 0
0x18000b616  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b61b  mov     eax, ebx
0x18000b61d  add     rsp, 60h
0x18000b621  pop     rbx
0x18000b622  retn
```
