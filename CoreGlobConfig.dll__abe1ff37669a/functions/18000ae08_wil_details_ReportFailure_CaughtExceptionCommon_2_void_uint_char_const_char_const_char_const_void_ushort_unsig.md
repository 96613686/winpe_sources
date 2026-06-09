# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000ae08`
- end: `0x18000af2a`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ac74`
- `0x180014c5c`

## callees

- `0x180005c3c`
- `0x180005c90`
- `0x180007754`
- `0x18000ae08`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 v10; // rdi
  __int64 v12; // rcx
  __int64 (__fastcall *v16)(_BYTE *, __int64, __int64, char *); // rax
  char v17; // si
  __int64 v18; // rax
  int v19; // r9d
  int v20; // ecx
  _BYTE v22[16]; // [rsp+50h] [rbp-38h] BYREF
  char v23; // [rsp+90h] [rbp+8h] BYREF

  v10 = a8;
  v23 = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a8 + 2 * v12) );
  v16 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  v17 = 1;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v16
    || (v18 = v16(v22, v10 + 2 * v12, 2048 - v12, &v23),
        v20 = *(_DWORD *)(v18 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v18,
        *(_DWORD *)(a1 + 8) = v20,
        *(int *)a1 >= 0) )
  {
    v17 = 0;
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
  }
  if ( !a10 && !v17 )
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v19);
  wil::details::ReportFailure_Base<2,0>(a2, a3, a4, 0, 0, a7, a1, v10);
  return a1;
}

```

## disassembly

```asm
0x18000ae08  mov     rax, rsp
0x18000ae0b  mov     [rax+10h], rbx
0x18000ae0f  mov     [rax+18h], rbp
0x18000ae13  push    rsi
0x18000ae14  push    rdi
0x18000ae15  push    r12
0x18000ae17  push    r14
0x18000ae19  push    r15
0x18000ae1b  sub     rsp, 60h
0x18000ae1f  mov     rdi, [rsp+88h+arg_38]
0x18000ae27  xor     r12d, r12d
0x18000ae2a  mov     rbx, rcx
0x18000ae2d  mov     [rax+8], r12b
0x18000ae31  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae35  mov     rbp, r9
0x18000ae38  mov     r14d, r8d
0x18000ae3b  mov     r15, rdx
0x18000ae3e  inc     rcx
0x18000ae41  cmp     [rdi+rcx*2], r12w
0x18000ae46  jnz     short loc_18000AE3E
0x18000ae48  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ae4f  mov     esi, 1
0x18000ae54  mov     [rbx], r12
0x18000ae57  mov     [rbx+8], esi
0x18000ae5a  test    rax, rax
0x18000ae5d  jz      short loc_18000AE91
0x18000ae5f  lea     rdx, [rdi+rcx*2]
0x18000ae63  mov     r8d, 800h
0x18000ae69  sub     r8, rcx
0x18000ae6c  lea     r9, [rsp+88h+arg_0]
0x18000ae74  lea     rcx, [rsp+88h+var_38]
0x18000ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7e  movsd   xmm0, qword ptr [rax]
0x18000ae82  mov     ecx, [rax+8]
0x18000ae85  movsd   qword ptr [rbx], xmm0
0x18000ae89  mov     [rbx+8], ecx
0x18000ae8c  cmp     [rbx], r12d
0x18000ae8f  jl      short loc_18000AEA7
0x18000ae91  mov     ecx, 8007023Eh; this
0x18000ae96  mov     sil, r12b
0x18000ae99  mov     [rbx], ecx
0x18000ae9b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000aea0  mov     [rbx+4], eax
0x18000aea3  mov     [rbx+8], r12d
0x18000aea7  cmp     [rsp+88h+arg_48], r12d
0x18000aeaf  jnz     short loc_18000AEDC
0x18000aeb1  test    sil, sil
0x18000aeb4  jnz     short loc_18000AEDC
0x18000aeb6  mov     rax, [rsp+88h+arg_30]
0x18000aebe  mov     r8, rbp
0x18000aec1  mov     [rsp+88h+var_50], rdi
0x18000aec6  mov     edx, r14d
0x18000aec9  mov     [rsp+88h+var_58], rbx
0x18000aece  mov     rcx, r15
0x18000aed1  mov     [rsp+88h+var_60], rax
0x18000aed6  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000aedc  mov     rax, [rsp+88h+arg_30]
0x18000aee4  xor     r9d, r9d
0x18000aee7  mov     [rsp+88h+var_40], r12d
0x18000aeec  mov     r8, rbp
0x18000aeef  mov     [rsp+88h+var_50], rdi
0x18000aef4  mov     edx, r14d
0x18000aef7  mov     [rsp+88h+var_58], rbx
0x18000aefc  mov     rcx, r15
0x18000aeff  mov     [rsp+88h+var_60], rax
0x18000af04  mov     [rsp+88h+var_68], r12
0x18000af09  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000af0e  lea     r11, [rsp+88h+var_28]
0x18000af13  mov     rax, rbx
0x18000af16  mov     rbx, [r11+38h]
0x18000af1a  mov     rbp, [r11+40h]
0x18000af1e  mov     rsp, r11
0x18000af21  pop     r15
0x18000af23  pop     r14
0x18000af25  pop     r12
0x18000af27  pop     rdi
0x18000af28  pop     rsi
0x18000af29  retn
```
