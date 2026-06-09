# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180006a30`
- end: `0x180006a8b`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a3c`
- `0x180005d10`
- `0x180006084`
- `0x1800060ec`
- `0x180006ea8`
- `0x1800080c0`

## callees

- `0x1800069dc`
- `0x180007570`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        __int64 a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x180006a30  sub     rsp, 68h
0x180006a34  mov     r10, rcx
0x180006a37  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180006a3e  mov     [rsp+68h+var_18], ecx
0x180006a42  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006a47  mov     [rsp+68h+var_14], eax
0x180006a4b  mov     rcx, r10
0x180006a4e  xor     eax, eax
0x180006a50  mov     [rsp+68h+var_20], eax
0x180006a54  mov     [rsp+68h+var_30], rax
0x180006a59  mov     [rsp+68h+var_10], eax
0x180006a5d  lea     rax, [rsp+68h+var_18]
0x180006a62  mov     [rsp+68h+var_38], rax
0x180006a67  mov     rax, [rsp+68h+arg_28]
0x180006a6f  mov     [rsp+68h+var_40], rax
0x180006a74  mov     rax, [rsp+68h+arg_20]
0x180006a7c  mov     [rsp+68h+var_48], rax
0x180006a81  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006a86  add     rsp, 68h
0x180006a8a  retn
```
