# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x140008b7c`
- end: `0x140008c76`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008ae4`

## callees

- `0x140003158`
- `0x1400031ac`
- `0x140005c30`
- `0x140008b7c`
- `0x140012010`

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
    wil::details::ReportFailure_Base<3,0>(
      a2,
      a3,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    a3,
    (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
    0,
    0,
    a7,
    a1,
    a8);
  return a1;
}

```

## disassembly

```asm
0x140008b7c  mov     rax, rsp
0x140008b7f  push    rbx
0x140008b80  push    rbp
0x140008b81  push    rsi
0x140008b82  push    rdi
0x140008b83  push    r14
0x140008b85  sub     rsp, 60h
0x140008b89  mov     rdi, [rsp+88h+arg_38]
0x140008b91  xor     r14d, r14d
0x140008b94  mov     rbx, rcx
0x140008b97  mov     [rax+50h], r14b
0x140008b9b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008b9f  mov     esi, r8d
0x140008ba2  mov     rbp, rdx
0x140008ba5  inc     rcx
0x140008ba8  cmp     [rdi+rcx*2], r14w
0x140008bad  jnz     short loc_140008BA5
0x140008baf  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140008bb6  mov     [rbx], r14
0x140008bb9  mov     dword ptr [rbx+8], 1
0x140008bc0  test    rax, rax
0x140008bc3  jz      short loc_140008C3A
0x140008bc5  lea     rdx, [rdi+rcx*2]
0x140008bc9  mov     r8d, 800h
0x140008bcf  sub     r8, rcx
0x140008bd2  lea     r9, [rsp+88h+arg_48]
0x140008bda  lea     rcx, [rsp+88h+var_38]
0x140008bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008be4  movsd   xmm0, qword ptr [rax]
0x140008be8  mov     ecx, [rax+8]
0x140008beb  movsd   qword ptr [rbx], xmm0
0x140008bef  mov     [rbx+8], ecx
0x140008bf2  cmp     [rbx], r14d
0x140008bf5  jge     short loc_140008C3A
0x140008bf7  mov     rax, [rsp+88h+arg_30]
0x140008bff  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x140008c06  mov     [rsp+88h+var_40], r14d
0x140008c0b  xor     r9d, r9d
0x140008c0e  mov     [rsp+88h+var_50], rdi
0x140008c13  mov     edx, esi
0x140008c15  mov     [rsp+88h+var_58], rbx
0x140008c1a  mov     rcx, rbp
0x140008c1d  mov     [rsp+88h+var_60], rax
0x140008c22  mov     [rsp+88h+var_68], r14
0x140008c27  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140008c2c  mov     rax, rbx
0x140008c2f  add     rsp, 60h
0x140008c33  pop     r14
0x140008c35  pop     rdi
0x140008c36  pop     rsi
0x140008c37  pop     rbp
0x140008c38  pop     rbx
0x140008c39  retn
0x140008c3a  mov     ecx, 8007023Eh; this
0x140008c3f  mov     [rbx], ecx
0x140008c41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140008c46  mov     [rbx+4], eax
0x140008c49  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x140008c50  mov     rax, [rsp+88h+arg_30]
0x140008c58  mov     edx, esi
0x140008c5a  mov     [rsp+88h+var_50], rdi
0x140008c5f  mov     rcx, rbp
0x140008c62  mov     [rsp+88h+var_58], rbx
0x140008c67  mov     [rsp+88h+var_60], rax
0x140008c6c  mov     [rbx+8], r14d
0x140008c70  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
