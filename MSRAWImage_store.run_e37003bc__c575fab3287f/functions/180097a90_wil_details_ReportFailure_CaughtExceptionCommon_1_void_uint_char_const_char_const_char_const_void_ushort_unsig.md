# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180097a90`
- end: `0x180097b93`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800979ec`

## callees

- `0x180097958`
- `0x1800979b4`
- `0x180097a90`
- `0x18009bf50`
- `0x1800b4010`

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
  __int64 (__fastcall *v15)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v16; // rax
  int v17; // ecx
  int v19; // r9d
  _BYTE v20[16]; // [rsp+50h] [rbp-28h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v15 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v15
    || (v16 = v15(v20, a8 + 2 * v11, 2048 - v11, &a10),
        v17 = *(_DWORD *)(v16 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v16,
        *(_DWORD *)(a1 + 8) = v17,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v19);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4);
  return a1;
}

```

## disassembly

```asm
0x180097a90  mov     rax, rsp
0x180097a93  mov     [rax+8], rbx
0x180097a97  mov     [rax+10h], rbp
0x180097a9b  mov     [rax+18h], rsi
0x180097a9f  push    rdi
0x180097aa0  push    r14
0x180097aa2  push    r15
0x180097aa4  sub     rsp, 60h
0x180097aa8  mov     rdi, [rsp+78h+arg_38]
0x180097ab0  xor     r15d, r15d
0x180097ab3  mov     rbx, rcx
0x180097ab6  mov     [rax+50h], r15b
0x180097aba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180097abe  mov     rsi, r9
0x180097ac1  mov     ebp, r8d
0x180097ac4  mov     r14, rdx
0x180097ac7  inc     rcx
0x180097aca  cmp     [rdi+rcx*2], r15w
0x180097acf  jnz     short loc_180097AC7
0x180097ad1  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180097ad8  mov     [rbx], r15
0x180097adb  mov     dword ptr [rbx+8], 1
0x180097ae2  test    rax, rax
0x180097ae5  jz      short loc_180097B5B
0x180097ae7  lea     rdx, [rdi+rcx*2]
0x180097aeb  mov     r8d, 800h
0x180097af1  sub     r8, rcx
0x180097af4  lea     r9, [rsp+78h+arg_48]
0x180097afc  lea     rcx, [rsp+78h+var_28]
0x180097b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b06  movsd   xmm0, qword ptr [rax]
0x180097b0a  mov     ecx, [rax+8]
0x180097b0d  movsd   qword ptr [rbx], xmm0
0x180097b11  mov     [rbx+8], ecx
0x180097b14  cmp     [rbx], r15d
0x180097b17  jge     short loc_180097B5B
0x180097b19  mov     rax, [rsp+78h+arg_30]
0x180097b21  mov     r8, rsi
0x180097b24  mov     [rsp+78h+var_40], rdi
0x180097b29  mov     edx, ebp
0x180097b2b  mov     [rsp+78h+var_48], rbx
0x180097b30  mov     rcx, r14
0x180097b33  mov     [rsp+78h+var_50], rax
0x180097b38  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180097b3d  lea     r11, [rsp+78h+var_18]
0x180097b42  mov     rax, rbx
0x180097b45  mov     rbx, [r11+20h]
0x180097b49  mov     rbp, [r11+28h]
0x180097b4d  mov     rsi, [r11+30h]
0x180097b51  mov     rsp, r11
0x180097b54  pop     r15
0x180097b56  pop     r14
0x180097b58  pop     rdi
0x180097b59  retn
0x180097b5b  mov     ecx, 8007023Eh; this
0x180097b60  mov     [rbx], ecx
0x180097b62  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180097b67  mov     [rbx+4], eax
0x180097b6a  mov     r8, rsi
0x180097b6d  mov     rax, [rsp+78h+arg_30]
0x180097b75  mov     edx, ebp
0x180097b77  mov     [rsp+78h+var_40], rdi
0x180097b7c  mov     rcx, r14
0x180097b7f  mov     [rsp+78h+var_48], rbx
0x180097b84  mov     [rsp+78h+var_50], rax
0x180097b89  mov     [rbx+8], r15d
0x180097b8d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
