# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180013ce0`
- end: `0x180013dcc`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013c58`

## callees

- `0x180007bc0`
- `0x180007c1c`
- `0x18000a3e8`
- `0x180013ce0`
- `0x18002a010`

## string_xrefs

- `0x180013d5f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcupdatehelper.cpp`
- `0x180013d9d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcupdatehelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
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
      39,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
      v16);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    39,
    "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp");
  return a1;
}

```

## disassembly

```asm
0x180013ce0  mov     rax, rsp
0x180013ce3  mov     [rax+18h], r8d
0x180013ce7  push    rbx
0x180013ce8  push    rbp
0x180013ce9  push    rsi
0x180013cea  push    rdi
0x180013ceb  sub     rsp, 68h
0x180013cef  mov     rdi, [rsp+88h+arg_38]
0x180013cf7  xor     ebp, ebp
0x180013cf9  mov     rbx, rcx
0x180013cfc  mov     [rax+18h], bpl
0x180013d00  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013d04  mov     rsi, rdx
0x180013d07  inc     rcx
0x180013d0a  cmp     [rdi+rcx*2], bp
0x180013d0e  jnz     short loc_180013D07
0x180013d10  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180013d17  mov     [rbx], rbp
0x180013d1a  mov     dword ptr [rbx+8], 1
0x180013d21  test    rax, rax
0x180013d24  jz      short loc_180013D8E
0x180013d26  lea     rdx, [rdi+rcx*2]
0x180013d2a  mov     r8d, 800h
0x180013d30  sub     r8, rcx
0x180013d33  lea     r9, [rsp+88h+arg_10]
0x180013d3b  lea     rcx, [rsp+88h+var_38]
0x180013d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d45  movsd   xmm0, qword ptr [rax]
0x180013d49  mov     ecx, [rax+8]
0x180013d4c  movsd   qword ptr [rbx], xmm0
0x180013d50  mov     [rbx+8], ecx
0x180013d53  cmp     [rbx], ebp
0x180013d55  jge     short loc_180013D8E
0x180013d57  mov     rax, [rsp+88h+arg_30]
0x180013d5f  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180013d66  mov     [rsp+88h+var_50], rdi
0x180013d6b  mov     edx, 27h ; '''
0x180013d70  mov     [rsp+88h+var_58], rbx
0x180013d75  mov     rcx, rsi
0x180013d78  mov     [rsp+88h+var_60], rax
0x180013d7d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180013d82  mov     rax, rbx
0x180013d85  add     rsp, 68h
0x180013d89  pop     rdi
0x180013d8a  pop     rsi
0x180013d8b  pop     rbp
0x180013d8c  pop     rbx
0x180013d8d  retn
0x180013d8e  mov     ecx, 8007023Eh; this
0x180013d93  mov     [rbx], ecx
0x180013d95  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013d9a  mov     [rbx+4], eax
0x180013d9d  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180013da4  mov     rax, [rsp+88h+arg_30]
0x180013dac  mov     edx, 27h ; '''
0x180013db1  mov     [rsp+88h+var_50], rdi
0x180013db6  mov     rcx, rsi
0x180013db9  mov     [rsp+88h+var_58], rbx
0x180013dbe  mov     [rsp+88h+var_60], rax
0x180013dc3  mov     [rbx+8], ebp
0x180013dc6  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
