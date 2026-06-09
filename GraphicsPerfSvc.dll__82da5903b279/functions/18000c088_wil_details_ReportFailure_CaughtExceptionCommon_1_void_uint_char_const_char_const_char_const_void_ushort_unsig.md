# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000c088`
- end: `0x18000c175`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bff0`

## callees

- `0x180004df8`
- `0x180004e58`
- `0x1800074c8`
- `0x18000c088`
- `0x180031010`

## string_xrefs

- `0x18000c10b`: `onecoreuap\windows\directx\dxg\gpm\service\apiprovider.cpp`
- `0x18000c148`: `onecoreuap\windows\directx\dxg\gpm\service\apiprovider.cpp`

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
    wil::details::ReportFailure_Base<3,0>(
      a2,
      a3,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\apiprovider.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, "onecoreuap\\windows\\directx\\dxg\\gpm\\service\\apiprovider.cpp");
  return a1;
}

```

## disassembly

```asm
0x18000c088  mov     rax, rsp
0x18000c08b  push    rbx
0x18000c08c  push    rbp
0x18000c08d  push    rsi
0x18000c08e  push    rdi
0x18000c08f  push    r14
0x18000c091  sub     rsp, 60h
0x18000c095  mov     rdi, [rsp+88h+arg_38]
0x18000c09d  xor     r14d, r14d
0x18000c0a0  mov     rbx, rcx
0x18000c0a3  mov     [rax+50h], r14b
0x18000c0a7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c0ab  mov     esi, r8d
0x18000c0ae  mov     rbp, rdx
0x18000c0b1  inc     rcx
0x18000c0b4  cmp     [rdi+rcx*2], r14w
0x18000c0b9  jnz     short loc_18000C0B1
0x18000c0bb  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000c0c2  mov     [rbx], r14
0x18000c0c5  mov     dword ptr [rbx+8], 1
0x18000c0cc  test    rax, rax
0x18000c0cf  jz      short loc_18000C139
0x18000c0d1  lea     rdx, [rdi+rcx*2]
0x18000c0d5  mov     r8d, 800h
0x18000c0db  sub     r8, rcx
0x18000c0de  lea     r9, [rsp+88h+arg_48]
0x18000c0e6  lea     rcx, [rsp+88h+var_38]
0x18000c0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f0  movsd   xmm0, qword ptr [rax]
0x18000c0f4  mov     ecx, [rax+8]
0x18000c0f7  movsd   qword ptr [rbx], xmm0
0x18000c0fb  mov     [rbx+8], ecx
0x18000c0fe  cmp     [rbx], r14d
0x18000c101  jge     short loc_18000C139
0x18000c103  mov     rax, [rsp+88h+arg_30]
0x18000c10b  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18000c112  mov     [rsp+88h+var_50], rdi
0x18000c117  mov     edx, esi
0x18000c119  mov     [rsp+88h+var_58], rbx
0x18000c11e  mov     rcx, rbp
0x18000c121  mov     [rsp+88h+var_60], rax
0x18000c126  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000c12b  mov     rax, rbx
0x18000c12e  add     rsp, 60h
0x18000c132  pop     r14
0x18000c134  pop     rdi
0x18000c135  pop     rsi
0x18000c136  pop     rbp
0x18000c137  pop     rbx
0x18000c138  retn
0x18000c139  mov     ecx, 8007023Eh; this
0x18000c13e  mov     [rbx], ecx
0x18000c140  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c145  mov     [rbx+4], eax
0x18000c148  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18000c14f  mov     rax, [rsp+88h+arg_30]
0x18000c157  mov     edx, esi
0x18000c159  mov     [rsp+88h+var_50], rdi
0x18000c15e  mov     rcx, rbp
0x18000c161  mov     [rsp+88h+var_58], rbx
0x18000c166  mov     [rsp+88h+var_60], rax
0x18000c16b  mov     [rbx+8], r14d
0x18000c16f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
