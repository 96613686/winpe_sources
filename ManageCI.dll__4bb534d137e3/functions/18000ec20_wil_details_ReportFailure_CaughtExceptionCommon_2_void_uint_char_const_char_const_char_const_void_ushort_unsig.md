# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000ec20`
- end: `0x18000ed1a`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eb30`

## callees

- `0x180003c9c`
- `0x180003cf0`
- `0x180006744`
- `0x18000ec20`
- `0x18002c010`

## string_xrefs

- `0x18000eca3`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x18000eced`: `onecore\base\ci\management\dll\manageci.cpp`

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
    wil::details::ReportFailure_Base<3,0>(a2, a3, (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp", v18);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    a3,
    (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
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
0x18000ec20  mov     rax, rsp
0x18000ec23  push    rbx
0x18000ec24  push    rbp
0x18000ec25  push    rsi
0x18000ec26  push    rdi
0x18000ec27  push    r14
0x18000ec29  sub     rsp, 60h
0x18000ec2d  mov     rdi, [rsp+88h+arg_38]
0x18000ec35  xor     r14d, r14d
0x18000ec38  mov     rbx, rcx
0x18000ec3b  mov     [rax+50h], r14b
0x18000ec3f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ec43  mov     esi, r8d
0x18000ec46  mov     rbp, rdx
0x18000ec49  inc     rcx
0x18000ec4c  cmp     [rdi+rcx*2], r14w
0x18000ec51  jnz     short loc_18000EC49
0x18000ec53  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ec5a  mov     [rbx], r14
0x18000ec5d  mov     dword ptr [rbx+8], 1
0x18000ec64  test    rax, rax
0x18000ec67  jz      short loc_18000ECDE
0x18000ec69  lea     rdx, [rdi+rcx*2]
0x18000ec6d  mov     r8d, 800h
0x18000ec73  sub     r8, rcx
0x18000ec76  lea     r9, [rsp+88h+arg_48]
0x18000ec7e  lea     rcx, [rsp+88h+var_38]
0x18000ec83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec88  movsd   xmm0, qword ptr [rax]
0x18000ec8c  mov     ecx, [rax+8]
0x18000ec8f  movsd   qword ptr [rbx], xmm0
0x18000ec93  mov     [rbx+8], ecx
0x18000ec96  cmp     [rbx], r14d
0x18000ec99  jge     short loc_18000ECDE
0x18000ec9b  mov     rax, [rsp+88h+arg_30]
0x18000eca3  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000ecaa  mov     [rsp+88h+var_40], r14d
0x18000ecaf  xor     r9d, r9d
0x18000ecb2  mov     [rsp+88h+var_50], rdi
0x18000ecb7  mov     edx, esi
0x18000ecb9  mov     [rsp+88h+var_58], rbx
0x18000ecbe  mov     rcx, rbp
0x18000ecc1  mov     [rsp+88h+var_60], rax
0x18000ecc6  mov     [rsp+88h+var_68], r14
0x18000eccb  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000ecd0  mov     rax, rbx
0x18000ecd3  add     rsp, 60h
0x18000ecd7  pop     r14
0x18000ecd9  pop     rdi
0x18000ecda  pop     rsi
0x18000ecdb  pop     rbp
0x18000ecdc  pop     rbx
0x18000ecdd  retn
0x18000ecde  mov     ecx, 8007023Eh; this
0x18000ece3  mov     [rbx], ecx
0x18000ece5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ecea  mov     [rbx+4], eax
0x18000eced  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000ecf4  mov     rax, [rsp+88h+arg_30]
0x18000ecfc  mov     edx, esi
0x18000ecfe  mov     [rsp+88h+var_50], rdi
0x18000ed03  mov     rcx, rbp
0x18000ed06  mov     [rsp+88h+var_58], rbx
0x18000ed0b  mov     [rsp+88h+var_60], rax
0x18000ed10  mov     [rbx+8], r14d
0x18000ed14  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
