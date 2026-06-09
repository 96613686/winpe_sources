# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003158`
- end: `0x1800031b3`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003050`
- `0x180004c70`
- `0x180004cd8`
- `0x1800054b8`

## callees

- `0x180002f3c`
- `0x180005188`

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
0x180003158  sub     rsp, 68h
0x18000315c  mov     r10, rcx
0x18000315f  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180003166  mov     [rsp+68h+var_18], ecx
0x18000316a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000316f  mov     [rsp+68h+var_14], eax
0x180003173  mov     rcx, r10
0x180003176  xor     eax, eax
0x180003178  mov     [rsp+68h+var_20], eax
0x18000317c  mov     [rsp+68h+var_30], rax
0x180003181  mov     [rsp+68h+var_10], eax
0x180003185  lea     rax, [rsp+68h+var_18]
0x18000318a  mov     [rsp+68h+var_38], rax
0x18000318f  mov     rax, [rsp+68h+arg_28]
0x180003197  mov     [rsp+68h+var_40], rax
0x18000319c  mov     rax, [rsp+68h+arg_20]
0x1800031a4  mov     [rsp+68h+var_48], rax
0x1800031a9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800031ae  add     rsp, 68h
0x1800031b2  retn
```
