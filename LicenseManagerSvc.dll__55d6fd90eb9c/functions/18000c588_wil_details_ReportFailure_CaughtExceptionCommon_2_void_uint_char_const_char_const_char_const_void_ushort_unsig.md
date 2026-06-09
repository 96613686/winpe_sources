# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000c588`
- end: `0x18000c67f`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c688`

## callees

- `0x180001c34`
- `0x180004384`
- `0x1800043d8`
- `0x18000c588`
- `0x180018010`

## string_xrefs

- `0x18000c607`: `onecoreuap\enduser\winstore\servicescommon\lib\storepolicy.cpp`
- `0x18000c650`: `onecoreuap\enduser\winstore\servicescommon\lib\storepolicy.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, int *); // rax
  __int64 v13; // rax
  int v14; // ecx
  int v16; // r9d
  _BYTE v17[56]; // [rsp+50h] [rbp-38h] BYREF
  int v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  v8 = a8;
  LOBYTE(v18) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v17, v8 + 2 * v10, 2048 - v10, &v18),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      85,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\storepolicy.cpp",
      v16);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    85,
    (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\storepolicy.cpp",
    0,
    0,
    a7,
    a1,
    v8);
  return a1;
}

```

## disassembly

```asm
0x18000c588  mov     rax, rsp
0x18000c58b  mov     [rax+18h], r8d
0x18000c58f  push    rbx
0x18000c590  push    rbp
0x18000c591  push    rsi
0x18000c592  push    rdi
0x18000c593  sub     rsp, 68h
0x18000c597  mov     rdi, [rsp+88h+arg_38]
0x18000c59f  xor     ebp, ebp
0x18000c5a1  mov     rbx, rcx
0x18000c5a4  mov     [rax+18h], bpl
0x18000c5a8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c5ac  mov     rsi, rdx
0x18000c5af  inc     rcx
0x18000c5b2  cmp     [rdi+rcx*2], bp
0x18000c5b6  jnz     short loc_18000C5AF
0x18000c5b8  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000c5bf  mov     [rbx], rbp
0x18000c5c2  mov     dword ptr [rbx+8], 1
0x18000c5c9  test    rax, rax
0x18000c5cc  jz      short loc_18000C641
0x18000c5ce  lea     rdx, [rdi+rcx*2]
0x18000c5d2  mov     r8d, 800h
0x18000c5d8  sub     r8, rcx
0x18000c5db  lea     r9, [rsp+88h+arg_10]
0x18000c5e3  lea     rcx, [rsp+88h+var_38]
0x18000c5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ed  movsd   xmm0, qword ptr [rax]
0x18000c5f1  mov     ecx, [rax+8]
0x18000c5f4  movsd   qword ptr [rbx], xmm0
0x18000c5f8  mov     [rbx+8], ecx
0x18000c5fb  cmp     [rbx], ebp
0x18000c5fd  jge     short loc_18000C641
0x18000c5ff  mov     rax, [rsp+88h+arg_30]
0x18000c607  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\services"...
0x18000c60e  mov     [rsp+88h+var_40], ebp
0x18000c612  xor     r9d, r9d
0x18000c615  mov     [rsp+88h+var_50], rdi
0x18000c61a  mov     rcx, rsi
0x18000c61d  mov     [rsp+88h+var_58], rbx
0x18000c622  mov     [rsp+88h+var_60], rax
0x18000c627  lea     edx, [r9+55h]
0x18000c62b  mov     [rsp+88h+var_68], rbp
0x18000c630  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000c635  mov     rax, rbx
0x18000c638  add     rsp, 68h
0x18000c63c  pop     rdi
0x18000c63d  pop     rsi
0x18000c63e  pop     rbp
0x18000c63f  pop     rbx
0x18000c640  retn
0x18000c641  mov     ecx, 8007023Eh; this
0x18000c646  mov     [rbx], ecx
0x18000c648  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c64d  mov     [rbx+4], eax
0x18000c650  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\services"...
0x18000c657  mov     rax, [rsp+88h+arg_30]
0x18000c65f  mov     edx, 55h ; 'U'
0x18000c664  mov     [rsp+88h+var_50], rdi
0x18000c669  mov     rcx, rsi
0x18000c66c  mov     [rsp+88h+var_58], rbx
0x18000c671  mov     [rsp+88h+var_60], rax
0x18000c676  mov     [rbx+8], ebp
0x18000c679  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
