# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000237c`
- end: `0x180002469`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022f4`

## callees

- `0x180002260`
- `0x1800022bc`
- `0x18000237c`
- `0x180004140`
- `0x18000b010`

## string_xrefs

- `0x1800023fb`: `admin\dm\dmapisetextimpl\desktopdll\dmapisetextimplcsp.cpp`
- `0x18000243a`: `admin\dm\dmapisetextimpl\desktopdll\dmapisetextimplcsp.cpp`

## pseudocode

```c
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
      171,
      (unsigned int)"admin\\dm\\dmapisetextimpl\\desktopdll\\dmapisetextimplcsp.cpp",
      v16);
  }
  wil::details::ReportFailure_Base<1,0>(a2, 171, "admin\\dm\\dmapisetextimpl\\desktopdll\\dmapisetextimplcsp.cpp");
  return a1;
}

```

## disassembly

```asm
0x18000237c  mov     rax, rsp
0x18000237f  mov     [rax+18h], r8d
0x180002383  push    rbx
0x180002384  push    rbp
0x180002385  push    rsi
0x180002386  push    rdi
0x180002387  sub     rsp, 68h
0x18000238b  mov     rdi, [rsp+88h+arg_38]
0x180002393  xor     ebp, ebp
0x180002395  mov     rbx, rcx
0x180002398  mov     [rax+18h], bpl
0x18000239c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800023a0  mov     rsi, rdx
0x1800023a3  inc     rcx
0x1800023a6  cmp     [rdi+rcx*2], bp
0x1800023aa  jnz     short loc_1800023A3
0x1800023ac  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800023b3  mov     [rbx], rbp
0x1800023b6  mov     dword ptr [rbx+8], 1
0x1800023bd  test    rax, rax
0x1800023c0  jz      short loc_18000242B
0x1800023c2  lea     rdx, [rdi+rcx*2]
0x1800023c6  mov     r8d, 800h
0x1800023cc  sub     r8, rcx
0x1800023cf  lea     r9, [rsp+88h+arg_10]
0x1800023d7  lea     rcx, [rsp+88h+var_38]
0x1800023dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e1  movsd   xmm0, qword ptr [rax]
0x1800023e5  mov     ecx, [rax+8]
0x1800023e8  movsd   qword ptr [rbx], xmm0
0x1800023ec  mov     [rbx+8], ecx
0x1800023ef  cmp     [rbx], ebp
0x1800023f1  jge     short loc_18000242B
0x1800023f3  mov     rax, [rsp+88h+arg_30]
0x1800023fb  lea     r8, aAdminDmDmapise; "admin\\dm\\dmapisetextimpl\\desktopdll"...
0x180002402  mov     [rsp+88h+var_50], rdi
0x180002407  mov     edx, 0ABh
0x18000240c  mov     [rsp+88h+var_58], rbx
0x180002411  mov     rcx, rsi
0x180002414  mov     [rsp+88h+var_60], rax
0x180002419  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000241e  mov     rax, rbx
0x180002421  add     rsp, 68h
0x180002425  pop     rdi
0x180002426  pop     rsi
0x180002427  pop     rbp
0x180002428  pop     rbx
0x180002429  retn
0x18000242b  mov     ecx, 8007023Eh; this
0x180002430  mov     [rbx], ecx
0x180002432  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002437  mov     [rbx+4], eax
0x18000243a  lea     r8, aAdminDmDmapise; "admin\\dm\\dmapisetextimpl\\desktopdll"...
0x180002441  mov     rax, [rsp+88h+arg_30]
0x180002449  mov     edx, 0ABh
0x18000244e  mov     [rsp+88h+var_50], rdi
0x180002453  mov     rcx, rsi
0x180002456  mov     [rsp+88h+var_58], rbx
0x18000245b  mov     [rsp+88h+var_60], rax
0x180002460  mov     [rbx+8], ebp
0x180002463  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
