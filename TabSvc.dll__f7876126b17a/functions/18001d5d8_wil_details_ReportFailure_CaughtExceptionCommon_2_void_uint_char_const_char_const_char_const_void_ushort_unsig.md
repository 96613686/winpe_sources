# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001d5d8`
- end: `0x18001d6d2`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d540`

## callees

- `0x18001b4b0`
- `0x18001d488`
- `0x18001d4dc`
- `0x18001d5d8`
- `0x180031010`

## string_xrefs

- `0x18001d65b`: `drivers\tablet\platform\pen\penservice\penservice.cpp`
- `0x18001d6a5`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

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
      (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    a3,
    (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
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
0x18001d5d8  mov     rax, rsp
0x18001d5db  push    rbx
0x18001d5dc  push    rbp
0x18001d5dd  push    rsi
0x18001d5de  push    rdi
0x18001d5df  push    r14
0x18001d5e1  sub     rsp, 60h
0x18001d5e5  mov     rdi, [rsp+88h+arg_38]
0x18001d5ed  xor     r14d, r14d
0x18001d5f0  mov     rbx, rcx
0x18001d5f3  mov     [rax+50h], r14b
0x18001d5f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001d5fb  mov     esi, r8d
0x18001d5fe  mov     rbp, rdx
0x18001d601  inc     rcx
0x18001d604  cmp     [rdi+rcx*2], r14w
0x18001d609  jnz     short loc_18001D601
0x18001d60b  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001d612  mov     [rbx], r14
0x18001d615  mov     dword ptr [rbx+8], 1
0x18001d61c  test    rax, rax
0x18001d61f  jz      short loc_18001D696
0x18001d621  lea     rdx, [rdi+rcx*2]
0x18001d625  mov     r8d, 800h
0x18001d62b  sub     r8, rcx
0x18001d62e  lea     r9, [rsp+88h+arg_48]
0x18001d636  lea     rcx, [rsp+88h+var_38]
0x18001d63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d640  movsd   xmm0, qword ptr [rax]
0x18001d644  mov     ecx, [rax+8]
0x18001d647  movsd   qword ptr [rbx], xmm0
0x18001d64b  mov     [rbx+8], ecx
0x18001d64e  cmp     [rbx], r14d
0x18001d651  jge     short loc_18001D696
0x18001d653  mov     rax, [rsp+88h+arg_30]
0x18001d65b  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18001d662  mov     [rsp+88h+var_40], r14d
0x18001d667  xor     r9d, r9d
0x18001d66a  mov     [rsp+88h+var_50], rdi
0x18001d66f  mov     edx, esi
0x18001d671  mov     [rsp+88h+var_58], rbx
0x18001d676  mov     rcx, rbp
0x18001d679  mov     [rsp+88h+var_60], rax
0x18001d67e  mov     [rsp+88h+var_68], r14
0x18001d683  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001d688  mov     rax, rbx
0x18001d68b  add     rsp, 60h
0x18001d68f  pop     r14
0x18001d691  pop     rdi
0x18001d692  pop     rsi
0x18001d693  pop     rbp
0x18001d694  pop     rbx
0x18001d695  retn
0x18001d696  mov     ecx, 8007023Eh; this
0x18001d69b  mov     [rbx], ecx
0x18001d69d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d6a2  mov     [rbx+4], eax
0x18001d6a5  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18001d6ac  mov     rax, [rsp+88h+arg_30]
0x18001d6b4  mov     edx, esi
0x18001d6b6  mov     [rsp+88h+var_50], rdi
0x18001d6bb  mov     rcx, rbp
0x18001d6be  mov     [rsp+88h+var_58], rbx
0x18001d6c3  mov     [rsp+88h+var_60], rax
0x18001d6c8  mov     [rbx+8], r14d
0x18001d6cc  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
