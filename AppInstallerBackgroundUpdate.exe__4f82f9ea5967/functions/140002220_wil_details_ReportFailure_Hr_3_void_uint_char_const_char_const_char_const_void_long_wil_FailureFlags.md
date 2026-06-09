# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140002220`
- end: `0x140002273`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `83`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033d4`
- `0x140008274`

## callees

- `0x140002018`
- `0x140003478`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // xmm0_8
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  int v13; // [rsp+58h] [rbp-20h]
  _BYTE v14[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v14, 2147549183LL);
  v7 = *(_QWORD *)v6;
  v13 = *(_DWORD *)(v6 + 8);
  v12 = v7;
  wil::details::ReportFailure_Base<3,0>(v10, v9, v8, v8, v11, a6, (__int64)&v12);
}

```

## disassembly

```asm
0x140002220  sub     rsp, 78h
0x140002224  mov     r11, rcx
0x140002227  mov     r10d, edx
0x14000222a  mov     edx, 8000FFFFh
0x14000222f  lea     rcx, [rsp+78h+var_18]
0x140002234  mov     r9, r8
0x140002237  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000223c  mov     r8, r9
0x14000223f  mov     edx, r10d
0x140002242  mov     rcx, r11
0x140002245  movsd   xmm0, qword ptr [rax]
0x140002249  mov     eax, [rax+8]
0x14000224c  mov     [rsp+78h+var_20], eax
0x140002250  lea     rax, [rsp+78h+var_28]
0x140002255  mov     [rsp+78h+var_48], rax
0x14000225a  mov     rax, [rsp+78h+arg_28]
0x140002262  mov     [rsp+78h+var_50], rax
0x140002267  movsd   [rsp+78h+var_28], xmm0
0x14000226d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
