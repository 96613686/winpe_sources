# wil::details::ReportFailure_HrMsg<3>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)

- ea: `0x180005fd8`
- end: `0x180006047`
- name: `??$ReportFailure_HrMsg@$02@details@wil@@YAXPEAXIPEBD110J1PEAD@Z`
- size: `111`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, int, unsigned __int64, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060cc`
- `0x180006104`

## callees

- `0x180004ce8`
- `0x180006050`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_HrMsg<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int64 a8,
        char *a9)
{
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  int v12; // r10d
  int v13; // r11d
  int v14; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v9 = wil::details::ResultStatus::FromResult(v17, a7, a3, a3);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Msg<3>(v13, v12, v11, v11, v14, a6, (__int64)&v15, a8, a9);
}

```

## disassembly

```asm
0x180005fd8  sub     rsp, 78h
0x180005fdc  mov     r11, rcx
0x180005fdf  mov     r10d, edx
0x180005fe2  mov     edx, [rsp+78h+arg_30]
0x180005fe9  lea     rcx, [rsp+78h+var_18]
0x180005fee  mov     r9, r8
0x180005ff1  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180005ff6  mov     r8, r9; int
0x180005ff9  mov     edx, r10d; int
0x180005ffc  mov     rcx, r11; int
0x180005fff  movsd   xmm0, qword ptr [rax]
0x180006003  mov     eax, [rax+8]
0x180006006  mov     [rsp+78h+var_20], eax
0x18000600a  mov     rax, [rsp+78h+arg_40]
0x180006012  mov     [rsp+78h+var_38], rax; char *
0x180006017  mov     rax, [rsp+78h+arg_38]
0x18000601f  mov     [rsp+78h+var_40], rax; unsigned __int64
0x180006024  lea     rax, [rsp+78h+var_28]
0x180006029  mov     [rsp+78h+var_48], rax; __int64
0x18000602e  mov     rax, [rsp+78h+arg_28]
0x180006036  mov     [rsp+78h+var_50], rax; __int64
0x18000603b  movsd   [rsp+78h+var_28], xmm0
0x180006041  call    ??$ReportFailure_Msg@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@1PEAD@Z; wil::details::ReportFailure_Msg<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,char const *,char *)
```
