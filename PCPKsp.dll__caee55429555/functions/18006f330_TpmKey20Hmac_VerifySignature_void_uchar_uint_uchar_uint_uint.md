# TpmKey20Hmac::VerifySignature(void *,uchar *,uint,uchar *,uint,uint)

- ea: `0x18006f330`
- end: `0x18006f6e9`
- name: `?VerifySignature@TpmKey20Hmac@@UEAAJPEAXPEAEI1II@Z`
- size: `953`
- prototype: `__int64 __usercall@<rax>(TpmKey20Hmac *__hidden this@<rcx>, void *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800133c4`
- `0x180014590`
- `0x180014830`
- `0x180014a60`
- `0x180014bd0`
- `0x1800157c0`
- `0x180029a20`
- `0x18004f7fc`
- `0x180052894`
- `0x18006f330`
- `0x1800768a0`
- `0x180077028`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18006f3ad`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18006f3ad`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18006f39a`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18006f39a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f3d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f3d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f38c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f38c`

## string_xrefs

- `0x18006f46a`: `Completed`
- `0x18006f59c`: `Completed`
- `0x18006f69f`: `Completed`
- `0x18006f476`: `CompletedWithWarning`
- `0x18006f5a8`: `CompletedWithWarning`
- `0x18006f6ab`: `CompletedWithWarning`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TpmKey20Hmac::VerifySignature(
        TpmKey20Hmac *this,
        void *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *Buf1,
        unsigned int a6)
{
  DWORD TickCount; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  int v13; // r9d
  signed __int8 v14; // r8
  const char *v15; // rdx
  __int64 v16; // rdx
  unsigned __int64 v17; // r9
  int v18; // eax
  unsigned int v19; // edi
  void *v20; // rsi
  int v21; // r9d
  signed __int8 v22; // r8
  const char *v23; // rdx
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  const struct std::nothrow_t *v28; // rdx
  int v29; // r9d
  signed __int8 v30; // r8
  const char *v31; // rdx
  int v33; // [rsp+20h] [rbp-61h]
  int v34; // [rsp+20h] [rbp-61h]
  struct tpm12class::TPMW8_SESSION *v35; // [rsp+40h] [rbp-41h] BYREF
  void *Buf2[3]; // [rsp+48h] [rbp-39h] BYREF
  struct tpm12class::TPMW8_SESSION **v37; // [rsp+60h] [rbp-21h] BYREF
  struct tpm12class::TPMW8_SESSION *v38; // [rsp+68h] [rbp-19h] BYREF
  char v39; // [rsp+70h] [rbp-11h]
  _BYTE v40[72]; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  int v42; // [rsp+D0h] [rbp+4Fh] BYREF
  size_t Size; // [rsp+D8h] [rbp+57h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v40, L"TpmKey20Hmac::VerifySignature", 1);
  v42 = 0;
  Buf2[1] = (char *)this + 56;
  Buf2[2] = &v42;
  if ( !byte_180109AF0 )
  {
    TickCount = GetTickCount();
    _o_srand(TickCount);
    byte_180109AF0 = 1;
  }
  if ( rand() < 327 )
  {
    *((_QWORD *)this + 7) = "TpmKey20Hmac::VerifySignature";
    *((_QWORD *)this + 8) = "Start";
    *((_QWORD *)this + 9) = GetTickCount64();
    *((_WORD *)this + 40) = 1;
  }
  if ( a2 )
  {
    v11 = -2144795645;
    v12 = 859;
LABEL_9:
    v42 = v11;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)v11,
      v33);
    goto LABEL_10;
  }
  if ( *((_DWORD *)this + 170) != 65537 )
  {
    v11 = -2144795643;
    v12 = 861;
    goto LABEL_9;
  }
  v35 = 0;
  v37 = &v35;
  v38 = 0;
  v39 = 1;
  v11 = TpmKey20Hmac::InitializeAuthSessionIfNeeded(this, &v38);
  v42 = v11;
  wil::details::out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>::~out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>(&v37);
  if ( (v11 & 0x80000000) != 0 )
  {
    v16 = 864;
LABEL_21:
    v17 = v11;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)v17,
      v33);
LABEL_23:
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v35, 0);
LABEL_10:
    if ( *((_BYTE *)this + 80) )
    {
      v13 = v42;
      if ( v42 >= 0 )
      {
        if ( v42 )
        {
          v14 = 1;
          v15 = "CompletedWithWarning";
        }
        else
        {
          v13 = 0;
          v14 = 0;
          v15 = "Completed";
        }
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v15, v14, v13);
        *((_BYTE *)this + 81) = 0;
      }
      else if ( !*((_BYTE *)this + 81) )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v42);
        *((_BYTE *)this + 81) = 1;
      }
      *((_BYTE *)this + 80) = 0;
    }
    goto LABEL_57;
  }
  LODWORD(Size) = 0;
  v18 = TpmKey20Hmac::Hmac(this, v35, a3, a4, 0, 0, (unsigned int *)&Size, 0);
  v11 = v18;
  v42 = v18;
  if ( v18 < 0 )
  {
    v17 = (unsigned int)v18;
    v16 = 873;
    goto LABEL_22;
  }
  v19 = Size;
  if ( (_DWORD)Size != a6 )
  {
    v11 = -2146893818;
    v42 = -2146893818;
    v16 = 874;
    goto LABEL_21;
  }
  wil::make_unique_nothrow<unsigned char [0]>(Buf2, (unsigned int)Size);
  v20 = Buf2[0];
  if ( !Buf2[0] )
  {
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v35, 0);
    if ( *((_BYTE *)this + 80) )
    {
      v21 = v42;
      if ( v42 >= 0 )
      {
        if ( v42 )
        {
          v22 = 1;
          v23 = "CompletedWithWarning";
        }
        else
        {
          v21 = 0;
          v22 = 0;
          v23 = "Completed";
        }
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v23, v22, v21);
        *((_BYTE *)this + 81) = 0;
      }
      else if ( !*((_BYTE *)this + 81) )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v42);
        *((_BYTE *)this + 81) = 1;
      }
      *((_BYTE *)this + 80) = 0;
    }
    v11 = -2147024888;
    goto LABEL_57;
  }
  v24 = TpmKey20Hmac::Hmac(this, v35, a3, a4, (unsigned __int8 *)Buf2[0], v19, (unsigned int *)&Size, 0);
  v11 = v24;
  v42 = v24;
  if ( v24 < 0 )
  {
    v25 = (unsigned int)v24;
    v26 = 883;
    goto LABEL_41;
  }
  if ( memcmp_0(Buf1, v20, (unsigned int)Size) )
  {
    v11 = -2146893818;
    v42 = -2146893818;
    v25 = 2148073478LL;
    v26 = 886;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)v25,
      v34);
    if ( v20 )
      operator delete(v20, v27);
    goto LABEL_23;
  }
  if ( v20 )
    operator delete(v20, v28);
  wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v35, 0);
  if ( *((_BYTE *)this + 80) )
  {
    v29 = v42;
    if ( v42 >= 0 )
    {
      if ( v42 )
      {
        v30 = 1;
        v31 = "CompletedWithWarning";
      }
      else
      {
        v29 = 0;
        v30 = 0;
        v31 = "Completed";
      }
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v31, v30, v29);
      *((_BYTE *)this + 81) = 0;
    }
    else if ( !*((_BYTE *)this + 81) )
    {
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v42);
      *((_BYTE *)this + 81) = 1;
    }
    *((_BYTE *)this + 80) = 0;
  }
  v11 = 0;
LABEL_57:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v40);
  return v11;
}

```

## disassembly

```asm
0x18006f330  mov     [rsp-8+arg_10], rbx
0x18006f335  push    rbp
0x18006f336  push    rsi
0x18006f337  push    rdi
0x18006f338  push    r12
0x18006f33a  push    r13
0x18006f33c  push    r14
0x18006f33e  push    r15
0x18006f340  lea     rbp, [rsp-0Fh]
0x18006f345  sub     rsp, 90h
0x18006f34c  mov     r15d, r9d
0x18006f34f  mov     r12, r8
0x18006f352  mov     rdi, rdx
0x18006f355  mov     r14, rcx
0x18006f358  mov     r8b, 1; bool
0x18006f35b  lea     rdx, aTpmkey20hmacVe_0; "TpmKey20Hmac::VerifySignature"
0x18006f362  lea     rcx, [rbp+3Fh+var_48]; this
0x18006f366  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18006f36b  nop
0x18006f36c  xor     r13d, r13d
0x18006f36f  mov     [rbp+3Fh+arg_0], r13d
0x18006f373  lea     rbx, [r14+38h]
0x18006f377  mov     [rbp+3Fh+var_70], rbx
0x18006f37b  lea     rax, [rbp+3Fh+arg_0]
0x18006f37f  mov     [rbp+3Fh+var_68], rax
0x18006f383  cmp     cs:byte_180109AF0, r13b
0x18006f38a  jnz     short loc_18006F3AD
0x18006f38c  call    cs:__imp_GetTickCount
0x18006f393  nop     dword ptr [rax+rax+00h]
0x18006f398  mov     ecx, eax
0x18006f39a  call    cs:__imp__o_srand
0x18006f3a1  nop     dword ptr [rax+rax+00h]
0x18006f3a6  mov     cs:byte_180109AF0, 1
0x18006f3ad  call    cs:__imp_rand
0x18006f3b4  nop     dword ptr [rax+rax+00h]
0x18006f3b9  cmp     eax, 147h
0x18006f3be  jge     short loc_18006F3EB
0x18006f3c0  lea     rax, aTpmkey20hmacVe; "TpmKey20Hmac::VerifySignature"
0x18006f3c7  mov     [rbx], rax
0x18006f3ca  lea     rax, aStart; "Start"
0x18006f3d1  mov     [rbx+8], rax
0x18006f3d5  call    cs:__imp_GetTickCount64
0x18006f3dc  nop     dword ptr [rax+rax+00h]
0x18006f3e1  mov     [rbx+10h], rax
0x18006f3e5  mov     word ptr [rbx+18h], 1
0x18006f3eb  test    rdi, rdi
0x18006f3ee  jz      short loc_18006F3FC
0x18006f3f0  mov     edi, 80290403h
0x18006f3f5  mov     edx, 35Bh
0x18006f3fa  jmp     short loc_18006F417
0x18006f3fc  cmp     dword ptr [r14+2A8h], 10001h
0x18006f407  jz      loc_18006F48F
0x18006f40d  mov     edi, 80290405h
0x18006f412  mov     edx, 35Dh; void *
0x18006f417  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006f41e  mov     r9d, edi; char *
0x18006f421  mov     rcx, [rbp+47h]; this
0x18006f425  mov     [rbp+3Fh+arg_0], edi
0x18006f428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f42d  nop
0x18006f42e  cmp     [rbx+18h], r13b
0x18006f432  jz      loc_18006F6C2
0x18006f438  mov     r9d, [rbp+3Fh+arg_0]; int
0x18006f43c  test    r9d, r9d
0x18006f43f  jns     short loc_18006F45F
0x18006f441  cmp     [rbx+19h], r13b
0x18006f445  jnz     short loc_18006F486
0x18006f447  mov     r8b, 0FFh; signed __int8
0x18006f44a  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18006f451  mov     rcx, rbx; this
0x18006f454  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f459  mov     byte ptr [rbx+19h], 1
0x18006f45d  jmp     short loc_18006F486
0x18006f45f  mov     rcx, rbx; this
0x18006f462  jnz     short loc_18006F473
0x18006f464  xor     r9d, r9d
0x18006f467  xor     r8d, r8d
0x18006f46a  lea     rdx, aCompleted; "Completed"
0x18006f471  jmp     short loc_18006F47D
0x18006f473  mov     r8b, 1; signed __int8
0x18006f476  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18006f47d  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f482  mov     [rbx+19h], r13b
0x18006f486  mov     [rbx+18h], r13b
0x18006f48a  jmp     loc_18006F6C2
0x18006f48f  mov     [rbp+3Fh+var_80], r13
0x18006f493  lea     rax, [rbp+3Fh+var_80]
0x18006f497  mov     [rbp+3Fh+var_60], rax
0x18006f49b  mov     [rbp+3Fh+var_58], r13
0x18006f49f  mov     [rbp+3Fh+var_50], 1
0x18006f4a3  lea     rdx, [rbp+3Fh+var_58]; struct tpm12class::TPMW8_SESSION **
0x18006f4a7  mov     rcx, r14; this
0x18006f4aa  call    ?InitializeAuthSessionIfNeeded@TpmKey20Hmac@@QEAAJPEAPEAVTPMW8_SESSION@tpm12class@@@Z; TpmKey20Hmac::InitializeAuthSessionIfNeeded(tpm12class::TPMW8_SESSION * *)
0x18006f4af  mov     edi, eax
0x18006f4b1  mov     [rbp+3Fh+arg_0], eax
0x18006f4b4  lea     rcx, [rbp+3Fh+var_60]
0x18006f4b8  call    ??1?$out_param_t@V?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>::~out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>(void)
0x18006f4bd  test    edi, edi
0x18006f4bf  jns     short loc_18006F4EA
0x18006f4c1  mov     edx, 360h; void *
0x18006f4c6  mov     r9d, edi; char *
0x18006f4c9  mov     rcx, [rbp+47h]; this
0x18006f4cd  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006f4d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f4d9  nop
0x18006f4da  xor     edx, edx
0x18006f4dc  lea     rcx, [rbp+3Fh+var_80]
0x18006f4e0  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18006f4e5  jmp     loc_18006F42E
0x18006f4ea  mov     dword ptr [rbp+3Fh+Size], r13d
0x18006f4ee  mov     [rsp+0C0h+var_88], r13d; unsigned int
0x18006f4f3  lea     rax, [rbp+3Fh+Size]
0x18006f4f7  mov     [rsp+0C0h+var_90], rax; unsigned int *
0x18006f4fc  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x18006f501  mov     [rsp+0C0h+var_A0], r13; unsigned __int8 *
0x18006f506  mov     r9d, r15d; unsigned int
0x18006f509  mov     r8, r12; unsigned __int8 *
0x18006f50c  mov     rdx, [rbp+3Fh+var_80]; struct tpm12class::TPMW8_SESSION *
0x18006f510  mov     rcx, r14; this
0x18006f513  call    ?Hmac@TpmKey20Hmac@@QEAAJPEAVTPMW8_SESSION@tpm12class@@PEAEI1IPEAII@Z; TpmKey20Hmac::Hmac(tpm12class::TPMW8_SESSION *,uchar *,uint,uchar *,uint,uint *,uint)
0x18006f518  mov     edi, eax
0x18006f51a  mov     [rbp+3Fh+arg_0], eax
0x18006f51d  test    eax, eax
0x18006f51f  jns     short loc_18006F52B
0x18006f521  mov     r9d, eax
0x18006f524  mov     edx, 369h
0x18006f529  jmp     short loc_18006F4C9
0x18006f52b  mov     edi, dword ptr [rbp+3Fh+Size]
0x18006f52e  cmp     edi, [rbp+3Fh+arg_28]
0x18006f531  jz      short loc_18006F542
0x18006f533  mov     edi, 80090006h
0x18006f538  mov     [rbp+3Fh+arg_0], edi
0x18006f53b  mov     edx, 36Ah
0x18006f540  jmp     short loc_18006F4C6
0x18006f542  mov     rdx, rdi
0x18006f545  lea     rcx, [rbp+3Fh+Buf2]
0x18006f549  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18006f54e  nop
0x18006f54f  mov     rsi, [rbp+3Fh+Buf2]
0x18006f553  test    rsi, rsi
0x18006f556  jnz     short loc_18006F5C6
0x18006f558  xor     edx, edx
0x18006f55a  lea     rcx, [rbp+3Fh+var_80]
0x18006f55e  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18006f563  nop
0x18006f564  cmp     [rbx+18h], r13b
0x18006f568  jz      short loc_18006F5BC
0x18006f56a  mov     r9d, [rbp+3Fh+arg_0]; int
0x18006f56e  test    r9d, r9d
0x18006f571  jns     short loc_18006F591
0x18006f573  cmp     [rbx+19h], r13b
0x18006f577  jnz     short loc_18006F5B8
0x18006f579  mov     r8b, 0FFh; signed __int8
0x18006f57c  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18006f583  mov     rcx, rbx; this
0x18006f586  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f58b  mov     byte ptr [rbx+19h], 1
0x18006f58f  jmp     short loc_18006F5B8
0x18006f591  mov     rcx, rbx; this
0x18006f594  jnz     short loc_18006F5A5
0x18006f596  xor     r9d, r9d
0x18006f599  xor     r8d, r8d
0x18006f59c  lea     rdx, aCompleted; "Completed"
0x18006f5a3  jmp     short loc_18006F5AF
0x18006f5a5  mov     r8b, 1; signed __int8
0x18006f5a8  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18006f5af  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f5b4  mov     [rbx+19h], r13b
0x18006f5b8  mov     [rbx+18h], r13b
0x18006f5bc  mov     edi, 80070008h
0x18006f5c1  jmp     loc_18006F6C2
0x18006f5c6  mov     [rsp+0C0h+var_88], r13d; unsigned int
0x18006f5cb  lea     rax, [rbp+3Fh+Size]
0x18006f5cf  mov     [rsp+0C0h+var_90], rax; unsigned int *
0x18006f5d4  mov     [rsp+0C0h+var_98], edi; unsigned int
0x18006f5d8  mov     [rsp+0C0h+var_A0], rsi; int
0x18006f5dd  mov     r9d, r15d; unsigned int
0x18006f5e0  mov     r8, r12; unsigned __int8 *
0x18006f5e3  mov     rdx, [rbp+3Fh+var_80]; struct tpm12class::TPMW8_SESSION *
0x18006f5e7  mov     rcx, r14; this
0x18006f5ea  call    ?Hmac@TpmKey20Hmac@@QEAAJPEAVTPMW8_SESSION@tpm12class@@PEAEI1IPEAII@Z; TpmKey20Hmac::Hmac(tpm12class::TPMW8_SESSION *,uchar *,uint,uchar *,uint,uint *,uint)
0x18006f5ef  mov     edi, eax
0x18006f5f1  mov     [rbp+3Fh+arg_0], eax
0x18006f5f4  test    eax, eax
0x18006f5f6  jns     short loc_18006F627
0x18006f5f8  mov     r9d, eax; char *
0x18006f5fb  mov     edx, 373h; void *
0x18006f600  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006f607  mov     rcx, [rbp+47h]; this
0x18006f60b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f610  nop
0x18006f611  test    rsi, rsi
0x18006f614  jz      loc_18006F4DA
0x18006f61a  mov     rcx, rsi; void *
0x18006f61d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006f622  jmp     loc_18006F4DA
0x18006f627  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x18006f62b  mov     rdx, rsi; Buf2
0x18006f62e  mov     rcx, [rbp+3Fh+Buf1]; Buf1
0x18006f632  call    memcmp_0
0x18006f637  test    eax, eax
0x18006f639  jz      short loc_18006F64D
0x18006f63b  mov     edi, 80090006h
0x18006f640  mov     [rbp+3Fh+arg_0], edi
0x18006f643  mov     r9d, edi
0x18006f646  mov     edx, 376h
0x18006f64b  jmp     short loc_18006F600
0x18006f64d  test    rsi, rsi
0x18006f650  jz      short loc_18006F65B
0x18006f652  mov     rcx, rsi; void *
0x18006f655  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006f65a  nop
0x18006f65b  xor     edx, edx
0x18006f65d  lea     rcx, [rbp+3Fh+var_80]
0x18006f661  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18006f666  nop
0x18006f667  cmp     [rbx+18h], r13b
0x18006f66b  jz      short loc_18006F6BF
0x18006f66d  mov     r9d, [rbp+3Fh+arg_0]; int
0x18006f671  test    r9d, r9d
0x18006f674  jns     short loc_18006F694
0x18006f676  cmp     [rbx+19h], r13b
0x18006f67a  jnz     short loc_18006F6BB
0x18006f67c  mov     r8b, 0FFh; signed __int8
0x18006f67f  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18006f686  mov     rcx, rbx; this
0x18006f689  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f68e  mov     byte ptr [rbx+19h], 1
0x18006f692  jmp     short loc_18006F6BB
0x18006f694  mov     rcx, rbx; this
0x18006f697  jnz     short loc_18006F6A8
0x18006f699  xor     r9d, r9d
0x18006f69c  xor     r8d, r8d
0x18006f69f  lea     rdx, aCompleted; "Completed"
0x18006f6a6  jmp     short loc_18006F6B2
0x18006f6a8  mov     r8b, 1; signed __int8
0x18006f6ab  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18006f6b2  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18006f6b7  mov     [rbx+19h], r13b
0x18006f6bb  mov     [rbx+18h], r13b
0x18006f6bf  mov     edi, r13d
0x18006f6c2  lea     rcx, [rbp+3Fh+var_48]; this
0x18006f6c6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18006f6cb  mov     eax, edi
0x18006f6cd  mov     rbx, [rsp+0C0h+arg_10]
0x18006f6d5  add     rsp, 90h
0x18006f6dc  pop     r15
0x18006f6de  pop     r14
0x18006f6e0  pop     r13
0x18006f6e2  pop     r12
0x18006f6e4  pop     rdi
0x18006f6e5  pop     rsi
0x18006f6e6  pop     rbp
0x18006f6e7  retn
```
