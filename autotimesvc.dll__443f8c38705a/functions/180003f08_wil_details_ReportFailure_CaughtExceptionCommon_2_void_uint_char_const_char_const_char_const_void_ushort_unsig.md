# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180003f08`
- end: `0x180004000`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003d8c`

## callees

- `0x180003c3c`
- `0x180003c90`
- `0x180003f08`
- `0x180007278`
- `0x180012010`

## string_xrefs

- `0x180003f87`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x180003fd1`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

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
  int v17; // [rsp+20h] [rbp-68h]
  __int64 v18; // [rsp+28h] [rbp-60h]
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF
  int v20; // [rsp+A0h] [rbp+18h] BYREF

  v20 = a3;
  v8 = a8;
  LOBYTE(v20) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v19, v8 + 2 * v10, 2048 - v10, &v20),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    v18 = a7;
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      474,
      (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      v16,
      v17,
      v18,
      a1,
      v8);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    474,
    (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
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
0x180003f08  mov     rax, rsp
0x180003f0b  mov     [rax+18h], r8d
0x180003f0f  push    rbx
0x180003f10  push    rbp
0x180003f11  push    rsi
0x180003f12  push    rdi
0x180003f13  sub     rsp, 68h
0x180003f17  mov     rdi, [rsp+88h+arg_38]
0x180003f1f  xor     ebp, ebp
0x180003f21  mov     rbx, rcx
0x180003f24  mov     [rax+18h], bpl
0x180003f28  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003f2c  mov     rsi, rdx
0x180003f2f  inc     rcx
0x180003f32  cmp     [rdi+rcx*2], bp
0x180003f36  jnz     short loc_180003F2F
0x180003f38  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180003f3f  mov     [rbx], rbp
0x180003f42  mov     dword ptr [rbx+8], 1
0x180003f49  test    rax, rax
0x180003f4c  jz      short loc_180003FC2
0x180003f4e  lea     rdx, [rdi+rcx*2]
0x180003f52  mov     r8d, 800h
0x180003f58  sub     r8, rcx
0x180003f5b  lea     r9, [rsp+88h+arg_10]
0x180003f63  lea     rcx, [rsp+88h+var_38]
0x180003f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6d  movsd   xmm0, qword ptr [rax]
0x180003f71  mov     ecx, [rax+8]
0x180003f74  movsd   qword ptr [rbx], xmm0
0x180003f78  mov     [rbx+8], ecx
0x180003f7b  cmp     [rbx], ebp
0x180003f7d  jge     short loc_180003FC2
0x180003f7f  mov     rax, [rsp+88h+arg_30]
0x180003f87  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180003f8e  mov     [rsp+88h+var_40], ebp
0x180003f92  xor     r9d, r9d
0x180003f95  mov     [rsp+88h+var_50], rdi
0x180003f9a  mov     edx, 1DAh
0x180003f9f  mov     [rsp+88h+var_58], rbx
0x180003fa4  mov     rcx, rsi
0x180003fa7  mov     [rsp+88h+var_60], rax
0x180003fac  mov     [rsp+88h+var_68], rbp
0x180003fb1  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003fb6  mov     rax, rbx
0x180003fb9  add     rsp, 68h
0x180003fbd  pop     rdi
0x180003fbe  pop     rsi
0x180003fbf  pop     rbp
0x180003fc0  pop     rbx
0x180003fc1  retn
0x180003fc2  mov     ecx, 8007023Eh; this
0x180003fc7  mov     [rbx], ecx
0x180003fc9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003fce  mov     [rbx+4], eax
0x180003fd1  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180003fd8  mov     rax, [rsp+88h+arg_30]
0x180003fe0  mov     edx, 1DAh
0x180003fe5  mov     [rsp+88h+var_50], rdi
0x180003fea  mov     rcx, rsi
0x180003fed  mov     [rsp+88h+var_58], rbx
0x180003ff2  mov     [rsp+88h+var_60], rax
0x180003ff7  mov     [rbx+8], ebp
0x180003ffa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
