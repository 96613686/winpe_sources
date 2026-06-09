# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180006074`
- end: `0x180006161`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005fdc`

## callees

- `0x180002d34`
- `0x180005f1c`
- `0x180005f78`
- `0x180006074`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10)
{
  __int64 v11; // rcx
  __int64 (__fastcall *v14)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v15; // rax
  int v16; // ecx
  int v18; // r9d
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v14 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v14
    || (v15 = v14(v19, a8 + 2 * v11, 2048 - v11, &a10),
        v16 = *(_DWORD *)(v15 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v15,
        *(_DWORD *)(a1 + 8) = v16,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, (unsigned int)"onecoreuap\\shell\\published\\inc\\call_as.cpp", v18);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, "onecoreuap\\shell\\published\\inc\\call_as.cpp");
  return a1;
}

```

## disassembly

```asm
0x180006074  mov     rax, rsp
0x180006077  push    rbx
0x180006078  push    rbp
0x180006079  push    rsi
0x18000607a  push    rdi
0x18000607b  push    r14
0x18000607d  sub     rsp, 60h
0x180006081  mov     rdi, [rsp+88h+arg_38]
0x180006089  xor     r14d, r14d
0x18000608c  mov     rbx, rcx
0x18000608f  mov     [rax+50h], r14b
0x180006093  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006097  mov     esi, r8d
0x18000609a  mov     rbp, rdx
0x18000609d  inc     rcx
0x1800060a0  cmp     [rdi+rcx*2], r14w
0x1800060a5  jnz     short loc_18000609D
0x1800060a7  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800060ae  mov     [rbx], r14
0x1800060b1  mov     dword ptr [rbx+8], 1
0x1800060b8  test    rax, rax
0x1800060bb  jz      short loc_180006125
0x1800060bd  lea     rdx, [rdi+rcx*2]
0x1800060c1  mov     r8d, 800h
0x1800060c7  sub     r8, rcx
0x1800060ca  lea     r9, [rsp+88h+arg_48]
0x1800060d2  lea     rcx, [rsp+88h+var_38]
0x1800060d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060dc  movsd   xmm0, qword ptr [rax]
0x1800060e0  mov     ecx, [rax+8]
0x1800060e3  movsd   qword ptr [rbx], xmm0
0x1800060e7  mov     [rbx+8], ecx
0x1800060ea  cmp     [rbx], r14d
0x1800060ed  jge     short loc_180006125
0x1800060ef  mov     rax, [rsp+88h+arg_30]
0x1800060f7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\published\\inc\\call"...
0x1800060fe  mov     [rsp+88h+var_50], rdi
0x180006103  mov     edx, esi
0x180006105  mov     [rsp+88h+var_58], rbx
0x18000610a  mov     rcx, rbp
0x18000610d  mov     [rsp+88h+var_60], rax
0x180006112  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006117  mov     rax, rbx
0x18000611a  add     rsp, 60h
0x18000611e  pop     r14
0x180006120  pop     rdi
0x180006121  pop     rsi
0x180006122  pop     rbp
0x180006123  pop     rbx
0x180006124  retn
0x180006125  mov     ecx, 8007023Eh; this
0x18000612a  mov     [rbx], ecx
0x18000612c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006131  mov     [rbx+4], eax
0x180006134  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\published\\inc\\call"...
0x18000613b  mov     rax, [rsp+88h+arg_30]
0x180006143  mov     edx, esi
0x180006145  mov     [rsp+88h+var_50], rdi
0x18000614a  mov     rcx, rbp
0x18000614d  mov     [rsp+88h+var_58], rbx
0x180006152  mov     [rsp+88h+var_60], rax
0x180006157  mov     [rbx+8], r14d
0x18000615b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
