# TpmKey20Hmac::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x180026e30`
- end: `0x18002720a`
- name: `?ImportKey@TpmKey20Hmac@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `986`
- prototype: `__int64 __usercall@<rax>(TpmKey20Hmac *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000dc90`
- `0x1800133c4`
- `0x180014830`
- `0x180014a60`
- `0x1800157c0`
- `0x180026e30`
- `0x180027670`
- `0x180029260`
- `0x180029a20`
- `0x1800768a0`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180026ea5`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180026ea5`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180026e92`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180026e92`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026e84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026e84`

## string_xrefs

- `0x180027051`: `Completed`
- `0x18002716f`: `Completed`
- `0x1800271c7`: `Completed`
- `0x18002705d`: `CompletedWithWarning`
- `0x18002717b`: `CompletedWithWarning`
- `0x1800271d6`: `CompletedWithWarning`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey20Hmac::ImportKey(
        TpmKey20Hmac *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  DWORD TickCount; // eax
  unsigned int v11; // r15d
  int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rsi
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // r12d
  void *v18; // rcx
  int v19; // r9d
  signed __int8 v20; // r8
  const char *v21; // rdx
  int KeyInTpm; // eax
  int v23; // r9d
  signed __int8 v24; // r8
  const char *v25; // rdx
  int v26; // r9d
  signed __int8 v27; // r8
  const char *v28; // rdx
  unsigned int v30; // [rsp+20h] [rbp-48h]
  void *Destination[3]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v32[32]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  int v34; // [rsp+B0h] [rbp+48h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v32, L"TpmKey20Hmac::ImportKey", 1);
  v34 = 0;
  Destination[1] = (char *)this + 56;
  Destination[2] = &v34;
  if ( !byte_180109AF0 )
  {
    TickCount = GetTickCount();
    _o_srand(TickCount);
    byte_180109AF0 = 1;
  }
  if ( rand() < 327 )
  {
    *((_QWORD *)this + 7) = "TpmKey20Hmac::ImportKey";
    *((_QWORD *)this + 8) = "Start";
    *((_QWORD *)this + 9) = GetTickCount64();
    *((_WORD *)this + 40) = 1;
  }
  v11 = a6;
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    v12 = -2144795644;
    KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "UnsupportedFlag", 255, -2144795644);
    *((_BYTE *)this + 81) = 1;
    v34 = -2144795644;
    v13 = 2150171652LL;
    v14 = 933;
    goto LABEL_34;
  }
  if ( !wcscmp_0(a3, L"OpaqueKeyBlob")
    || !wcscmp_0(a3, L"OpaqueTransport")
    || !wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
    || !wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
  {
    KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "ImportingTpmFormatKey", 0, 0);
    *((_BYTE *)this + 81) = 0;
    KeyInTpm = TpmKey20::ImportKey(this, a2, a3, a4, a5, v11);
    v12 = KeyInTpm;
    v34 = KeyInTpm;
    if ( KeyInTpm < 0 )
    {
      v14 = 947;
      goto LABEL_33;
    }
  }
  else
  {
    if ( wcscmp_0(a3, L"CipherKeyBlob") )
    {
      v12 = -2144795643;
      v34 = -2144795643;
      v13 = 2150171653LL;
      v14 = 972;
      goto LABEL_34;
    }
    KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "ImportingRawHmacKey", 0, 0);
    *((_BYTE *)this + 81) = 0;
    if ( a5 < 0x10
      || *((_DWORD *)a4 + 1) != 1380470851
      || a5 != *(_DWORD *)a4
      || (v15 = *((unsigned int *)a4 + 2), a5 < (unsigned __int64)*((unsigned int *)a4 + 3) + v15 + 16) )
    {
      v12 = -2144795645;
      v34 = -2144795645;
      v13 = 2150171651LL;
      v14 = 958;
      goto LABEL_34;
    }
    v16 = (const struct std::nothrow_t *)(a5 - (unsigned int)v15);
    v17 = (_DWORD)v16 - 16;
    *((_DWORD *)this + 164) = 0;
    operator delete(*((void **)this + 81), v16);
    *((_QWORD *)this + 81) = 0;
    wil::make_unique_nothrow<unsigned char [0]>(Destination, v17);
    v18 = Destination[0];
    if ( !Destination[0] )
    {
      if ( *((_BYTE *)this + 80) )
      {
        v19 = v34;
        if ( v34 >= 0 )
        {
          if ( v34 )
          {
            v20 = 1;
            v21 = "CompletedWithWarning";
          }
          else
          {
            v19 = 0;
            v20 = 0;
            v21 = "Completed";
          }
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v21, v20, v19);
          *((_BYTE *)this + 81) = 0;
        }
        else if ( !*((_BYTE *)this + 81) )
        {
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v34);
          *((_BYTE *)this + 81) = 1;
        }
        *((_BYTE *)this + 80) = 0;
      }
      v12 = -2147024888;
      goto LABEL_53;
    }
    *((void **)this + 81) = Destination[0];
    *((_DWORD *)this + 164) = v17;
    memcpy_s(v18, v17, &a4[v15 + 16], v17);
    KeyInTpm = TpmKey20::LoadKeyInTpm(this);
    v12 = KeyInTpm;
    v34 = KeyInTpm;
    if ( KeyInTpm < 0 )
    {
      v14 = 968;
LABEL_33:
      v13 = (unsigned int)KeyInTpm;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
        (const char *)v13,
        v30);
      if ( *((_BYTE *)this + 80) )
      {
        v23 = v34;
        if ( v34 >= 0 )
        {
          if ( v34 )
          {
            v24 = 1;
            v25 = "CompletedWithWarning";
          }
          else
          {
            v23 = 0;
            v24 = 0;
            v25 = "Completed";
          }
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v25, v24, v23);
          *((_BYTE *)this + 81) = 0;
        }
        else if ( !*((_BYTE *)this + 81) )
        {
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v34);
          *((_BYTE *)this + 81) = 1;
        }
        *((_BYTE *)this + 80) = 0;
      }
      goto LABEL_53;
    }
  }
  if ( *((_BYTE *)this + 80) )
  {
    if ( v12 >= 0 )
    {
      if ( v12 )
      {
        v26 = v12;
        v27 = 1;
        v28 = "CompletedWithWarning";
      }
      else
      {
        v26 = 0;
        v27 = 0;
        v28 = "Completed";
      }
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v28, v27, v26);
      *((_BYTE *)this + 81) = 0;
    }
    else if ( !*((_BYTE *)this + 81) )
    {
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v12);
      *((_BYTE *)this + 81) = 1;
    }
    *((_BYTE *)this + 80) = 0;
  }
  v12 = 0;
LABEL_53:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180026e30  push    rbp
0x180026e32  push    rbx
0x180026e33  push    rsi
0x180026e34  push    rdi
0x180026e35  push    r12
0x180026e37  push    r13
0x180026e39  push    r14
0x180026e3b  push    r15
0x180026e3d  mov     rbp, rsp
0x180026e40  sub     rsp, 68h
0x180026e44  mov     rdi, r9
0x180026e47  mov     rsi, r8
0x180026e4a  mov     r12, rdx
0x180026e4d  mov     r14, rcx
0x180026e50  mov     r8b, 1; bool
0x180026e53  lea     rdx, aTpmkey20hmacIm_0; "TpmKey20Hmac::ImportKey"
0x180026e5a  lea     rcx, [rbp+var_20]; this
0x180026e5e  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180026e63  nop
0x180026e64  xor     r13d, r13d
0x180026e67  mov     [rbp+arg_0], r13d
0x180026e6b  lea     rbx, [r14+38h]
0x180026e6f  mov     [rbp+var_30], rbx
0x180026e73  lea     rax, [rbp+arg_0]
0x180026e77  mov     [rbp+var_28], rax
0x180026e7b  cmp     cs:byte_180109AF0, r13b
0x180026e82  jnz     short loc_180026EA5
0x180026e84  call    cs:__imp_GetTickCount
0x180026e8b  nop     dword ptr [rax+rax+00h]
0x180026e90  mov     ecx, eax
0x180026e92  call    cs:__imp__o_srand
0x180026e99  nop     dword ptr [rax+rax+00h]
0x180026e9e  mov     cs:byte_180109AF0, 1
0x180026ea5  call    cs:__imp_rand
0x180026eac  nop     dword ptr [rax+rax+00h]
0x180026eb1  cmp     eax, 147h
0x180026eb6  jge     short loc_180026EE3
0x180026eb8  lea     rax, aTpmkey20hmacIm; "TpmKey20Hmac::ImportKey"
0x180026ebf  mov     [rbx], rax
0x180026ec2  lea     rax, aStart; "Start"
0x180026ec9  mov     [rbx+8], rax
0x180026ecd  call    cs:__imp_GetTickCount64
0x180026ed4  nop     dword ptr [rax+rax+00h]
0x180026ed9  mov     [rbx+10h], rax
0x180026edd  mov     word ptr [rbx+18h], 1
0x180026ee3  mov     r15d, [rbp+arg_28]
0x180026ee7  test    r15d, 0FFFFEFF7h
0x180026eee  jz      short loc_180026F1E
0x180026ef0  mov     edi, 80290404h
0x180026ef5  mov     r9d, edi; int
0x180026ef8  mov     r8b, 0FFh; signed __int8
0x180026efb  lea     rdx, aUnsupportedfla; "UnsupportedFlag"
0x180026f02  mov     rcx, rbx; this
0x180026f05  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180026f0a  mov     byte ptr [rbx+19h], 1
0x180026f0e  mov     [rbp+arg_0], edi
0x180026f11  mov     r9d, edi
0x180026f14  mov     edx, 3A5h
0x180026f19  jmp     loc_180027122
0x180026f1e  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180026f25  mov     rcx, rsi; String1
0x180026f28  call    wcscmp_0
0x180026f2d  test    eax, eax
0x180026f2f  jz      loc_1800270DB
0x180026f35  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x180026f3c  mov     rcx, rsi; String1
0x180026f3f  call    wcscmp_0
0x180026f44  test    eax, eax
0x180026f46  jz      loc_1800270DB
0x180026f4c  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x180026f53  mov     rcx, rsi; String1
0x180026f56  call    wcscmp_0
0x180026f5b  test    eax, eax
0x180026f5d  jz      loc_1800270DB
0x180026f63  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x180026f6a  mov     rcx, rsi; String1
0x180026f6d  call    wcscmp_0
0x180026f72  test    eax, eax
0x180026f74  jz      loc_1800270DB
0x180026f7a  lea     rdx, aCipherkeyblob; "CipherKeyBlob"
0x180026f81  mov     rcx, rsi; String1
0x180026f84  call    wcscmp_0
0x180026f89  test    eax, eax
0x180026f8b  jnz     loc_1800270C9
0x180026f91  xor     r9d, r9d; int
0x180026f94  xor     r8d, r8d; signed __int8
0x180026f97  lea     rdx, aImportingrawhm; "ImportingRawHmacKey"
0x180026f9e  mov     rcx, rbx; this
0x180026fa1  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180026fa6  mov     [rbx+19h], r13b
0x180026faa  mov     edx, [rbp+arg_20]
0x180026fad  cmp     edx, 10h
0x180026fb0  jb      loc_1800270B7
0x180026fb6  cmp     dword ptr [rdi+4], 52485043h
0x180026fbd  jnz     loc_1800270B7
0x180026fc3  cmp     edx, [rdi]
0x180026fc5  jnz     loc_1800270B7
0x180026fcb  mov     esi, [rdi+8]
0x180026fce  mov     eax, [rdi+0Ch]
0x180026fd1  lea     rcx, [rsi+10h]
0x180026fd5  add     rcx, rax
0x180026fd8  cmp     rdx, rcx
0x180026fdb  jb      loc_1800270B7
0x180026fe1  sub     edx, esi; struct std::nothrow_t *
0x180026fe3  lea     r12d, [rdx-10h]
0x180026fe7  mov     [r14+290h], r13d
0x180026fee  mov     rcx, [r14+288h]; void *
0x180026ff5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026ffa  mov     [r14+288h], r13
0x180027001  mov     r15d, r12d
0x180027004  mov     edx, r12d
0x180027007  lea     rcx, [rbp+Destination]
0x18002700b  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180027010  mov     rcx, [rbp+Destination]; Destination
0x180027014  test    rcx, rcx
0x180027017  jnz     short loc_18002707B
0x180027019  cmp     [rbx+18h], r13b
0x18002701d  jz      short loc_180027071
0x18002701f  mov     r9d, [rbp+arg_0]; int
0x180027023  test    r9d, r9d
0x180027026  jns     short loc_180027046
0x180027028  cmp     [rbx+19h], r13b
0x18002702c  jnz     short loc_18002706D
0x18002702e  mov     r8b, 0FFh; signed __int8
0x180027031  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180027038  mov     rcx, rbx; this
0x18002703b  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027040  mov     byte ptr [rbx+19h], 1
0x180027044  jmp     short loc_18002706D
0x180027046  mov     rcx, rbx; this
0x180027049  jnz     short loc_18002705A
0x18002704b  xor     r9d, r9d
0x18002704e  xor     r8d, r8d
0x180027051  lea     rdx, aCompleted; "Completed"
0x180027058  jmp     short loc_180027064
0x18002705a  mov     r8b, 1; signed __int8
0x18002705d  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180027064  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027069  mov     [rbx+19h], r13b
0x18002706d  mov     [rbx+18h], r13b
0x180027071  mov     edi, 80070008h
0x180027076  jmp     loc_1800271ED
0x18002707b  mov     [r14+288h], rcx
0x180027082  mov     [r14+290h], r12d
0x180027089  lea     r8, [rdi+10h]
0x18002708d  add     r8, rsi; Source
0x180027090  mov     r9, r15; SourceSize
0x180027093  mov     rdx, r15; DestinationSize
0x180027096  call    memcpy_s
0x18002709b  mov     rcx, r14; this
0x18002709e  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x1800270a3  mov     edi, eax
0x1800270a5  mov     [rbp+arg_0], eax
0x1800270a8  test    eax, eax
0x1800270aa  jns     loc_180027191
0x1800270b0  mov     edx, 3C8h
0x1800270b5  jmp     short loc_18002711F
0x1800270b7  mov     edi, 80290403h
0x1800270bc  mov     [rbp+arg_0], edi
0x1800270bf  mov     r9d, edi
0x1800270c2  mov     edx, 3BEh
0x1800270c7  jmp     short loc_180027122
0x1800270c9  mov     edi, 80290405h
0x1800270ce  mov     [rbp+arg_0], edi
0x1800270d1  mov     r9d, edi
0x1800270d4  mov     edx, 3CCh
0x1800270d9  jmp     short loc_180027122
0x1800270db  xor     r9d, r9d; int
0x1800270de  xor     r8d, r8d; signed __int8
0x1800270e1  lea     rdx, aImportingtpmfo; "ImportingTpmFormatKey"
0x1800270e8  mov     rcx, rbx; this
0x1800270eb  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800270f0  mov     [rbx+19h], r13b
0x1800270f4  mov     [rsp+68h+var_40], r15d; unsigned int
0x1800270f9  mov     eax, [rbp+arg_20]
0x1800270fc  mov     [rsp+68h+var_48], eax; int
0x180027100  mov     r9, rdi; unsigned __int8 *
0x180027103  mov     r8, rsi; unsigned __int16 *
0x180027106  mov     rdx, r12; struct TpmKey *
0x180027109  mov     rcx, r14; this
0x18002710c  call    ?ImportKey@TpmKey20@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z; TpmKey20::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)
0x180027111  mov     edi, eax
0x180027113  mov     [rbp+arg_0], eax
0x180027116  test    eax, eax
0x180027118  jns     short loc_180027191
0x18002711a  mov     edx, 3B3h; void *
0x18002711f  mov     r9d, eax; char *
0x180027122  mov     rcx, [rbp+40h]; this
0x180027126  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002712d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027132  nop
0x180027133  cmp     [rbx+18h], r13b
0x180027137  jz      loc_1800271ED
0x18002713d  mov     r9d, [rbp+arg_0]; int
0x180027141  test    r9d, r9d
0x180027144  jns     short loc_180027164
0x180027146  cmp     [rbx+19h], r13b
0x18002714a  jnz     short loc_18002718B
0x18002714c  mov     r8b, 0FFh; signed __int8
0x18002714f  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180027156  mov     rcx, rbx; this
0x180027159  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18002715e  mov     byte ptr [rbx+19h], 1
0x180027162  jmp     short loc_18002718B
0x180027164  mov     rcx, rbx; this
0x180027167  jnz     short loc_180027178
0x180027169  xor     r9d, r9d
0x18002716c  xor     r8d, r8d
0x18002716f  lea     rdx, aCompleted; "Completed"
0x180027176  jmp     short loc_180027182
0x180027178  mov     r8b, 1; signed __int8
0x18002717b  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180027182  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027187  mov     [rbx+19h], r13b
0x18002718b  mov     [rbx+18h], r13b
0x18002718f  jmp     short loc_1800271ED
0x180027191  cmp     [rbx+18h], r13b
0x180027195  jz      short loc_1800271EA
0x180027197  test    edi, edi
0x180027199  jns     short loc_1800271BC
0x18002719b  cmp     [rbx+19h], r13b
0x18002719f  jnz     short loc_1800271E6
0x1800271a1  mov     r9d, edi; int
0x1800271a4  mov     r8b, 0FFh; signed __int8
0x1800271a7  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x1800271ae  mov     rcx, rbx; this
0x1800271b1  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800271b6  mov     byte ptr [rbx+19h], 1
0x1800271ba  jmp     short loc_1800271E6
0x1800271bc  mov     rcx, rbx; this
0x1800271bf  jnz     short loc_1800271D0
0x1800271c1  xor     r9d, r9d
0x1800271c4  xor     r8d, r8d
0x1800271c7  lea     rdx, aCompleted; "Completed"
0x1800271ce  jmp     short loc_1800271DD
0x1800271d0  mov     r9d, edi; int
0x1800271d3  mov     r8b, 1; signed __int8
0x1800271d6  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x1800271dd  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800271e2  mov     [rbx+19h], r13b
0x1800271e6  mov     [rbx+18h], r13b
0x1800271ea  mov     edi, r13d
0x1800271ed  lea     rcx, [rbp+var_20]; this
0x1800271f1  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800271f6  mov     eax, edi
0x1800271f8  add     rsp, 68h
0x1800271fc  pop     r15
0x1800271fe  pop     r14
0x180027200  pop     r13
0x180027202  pop     r12
0x180027204  pop     rdi
0x180027205  pop     rsi
0x180027206  pop     rbx
0x180027207  pop     rbp
0x180027208  retn
```
