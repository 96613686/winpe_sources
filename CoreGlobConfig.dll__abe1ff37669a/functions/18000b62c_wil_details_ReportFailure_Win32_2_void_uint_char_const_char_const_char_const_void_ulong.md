# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000b62c`
- end: `0x18000b6a2`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `118`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001d408`

## callees

- `0x180005c3c`
- `0x180007754`
- `0x18000b62c`

## string_xrefs

- `0x18000b65e`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r10d
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, 0);
  v11[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v9,
    691,
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    0,
    v8,
    a6,
    (__int64)v11,
    v8);
  return v7;
}

```

## disassembly

```asm
0x18000b62c  push    rbx
0x18000b62e  sub     rsp, 60h
0x18000b632  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000b639  xor     edx, edx; int
0x18000b63b  mov     r10, rcx
0x18000b63e  test    ebx, ebx
0x18000b640  jle     short loc_18000B64B
0x18000b642  movzx   ebx, bx
0x18000b645  or      ebx, 80070000h
0x18000b64b  mov     ecx, ebx; this
0x18000b64d  mov     [rsp+68h+var_18], ebx
0x18000b651  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b656  mov     rcx, [rsp+68h+arg_28]
0x18000b65e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000b665  mov     [rsp+68h+var_20], edx
0x18000b669  xor     r9d, r9d
0x18000b66c  mov     [rsp+68h+var_30], rdx
0x18000b671  mov     [rsp+68h+var_14], eax
0x18000b675  lea     rax, [rsp+68h+var_18]
0x18000b67a  mov     [rsp+68h+var_38], rax
0x18000b67f  mov     [rsp+68h+var_40], rcx
0x18000b684  mov     rcx, r10
0x18000b687  mov     [rsp+68h+var_48], rdx
0x18000b68c  mov     [rsp+68h+var_10], edx
0x18000b690  mov     edx, 2B3h
0x18000b695  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b69a  mov     eax, ebx
0x18000b69c  add     rsp, 60h
0x18000b6a0  pop     rbx
0x18000b6a1  retn
```
