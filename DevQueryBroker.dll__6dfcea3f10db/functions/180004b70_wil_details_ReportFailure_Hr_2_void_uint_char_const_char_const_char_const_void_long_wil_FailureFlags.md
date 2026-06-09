# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180004b70`
- end: `0x180004bcc`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a80`
- `0x180006e00`
- `0x180006e68`
- `0x1800074a0`

## callees

- `0x180004984`
- `0x1800072dc`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x180004b70  sub     rsp, 68h
0x180004b74  mov     r10, rcx
0x180004b77  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180004b7e  mov     [rsp+68h+var_18], ecx
0x180004b82  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004b87  mov     [rsp+68h+var_14], eax
0x180004b8b  mov     rcx, r10
0x180004b8e  mov     [rsp+68h+var_20], 0
0x180004b96  lea     rax, [rsp+68h+var_18]
0x180004b9b  mov     [rsp+68h+var_38], rax
0x180004ba0  mov     rax, [rsp+68h+arg_28]
0x180004ba8  mov     [rsp+68h+var_40], rax
0x180004bad  mov     rax, [rsp+68h+arg_20]
0x180004bb5  mov     [rsp+68h+var_48], rax
0x180004bba  mov     [rsp+68h+var_10], 0
0x180004bc2  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180004bc7  add     rsp, 68h
0x180004bcb  retn
```
