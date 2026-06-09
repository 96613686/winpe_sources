# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003a20`
- end: `0x180003a7b`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003918`
- `0x180005270`
- `0x1800052d8`
- `0x1800059c4`
- `0x18000ce58`

## callees

- `0x180003804`
- `0x180005800`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x180003a20  sub     rsp, 68h
0x180003a24  mov     r10, rcx
0x180003a27  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180003a2e  mov     [rsp+68h+var_18], ecx
0x180003a32  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003a37  mov     [rsp+68h+var_14], eax
0x180003a3b  mov     rcx, r10
0x180003a3e  xor     eax, eax
0x180003a40  mov     [rsp+68h+var_20], eax
0x180003a44  mov     [rsp+68h+var_30], rax
0x180003a49  mov     [rsp+68h+var_10], eax
0x180003a4d  lea     rax, [rsp+68h+var_18]
0x180003a52  mov     [rsp+68h+var_38], rax
0x180003a57  mov     rax, [rsp+68h+arg_28]
0x180003a5f  mov     [rsp+68h+var_40], rax
0x180003a64  mov     rax, [rsp+68h+arg_20]
0x180003a6c  mov     [rsp+68h+var_48], rax
0x180003a71  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003a76  add     rsp, 68h
0x180003a7a  retn
```
