# TpmKey20Hmac::SignHash(void *,uchar *,uint,uchar *,uint,uint *,uint)

- ea: `0x180070ca0`
- end: `0x180070f2d`
- name: `?SignHash@TpmKey20Hmac@@UEAAJPEAXPEAEI1IPEAII@Z`
- size: `653`
- prototype: `__int64 __usercall@<rax>(TpmKey20Hmac *__hidden this@<rcx>, void *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800133c4`
- `0x180014590`
- `0x180014830`
- `0x180014a60`
- `0x180014bd0`
- `0x1800157c0`
- `0x18004f7fc`
- `0x180052894`
- `0x180070ca0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180070d1d`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180070d1d`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180070d0a`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180070d0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180070d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180070d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180070cfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180070cfc`

## string_xrefs

- `0x180070dd9`: `Completed`
- `0x180070ee2`: `Completed`
- `0x180070de5`: `CompletedWithWarning`
- `0x180070eee`: `CompletedWithWarning`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TpmKey20Hmac::SignHash(
        TpmKey20Hmac *this,
        void *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int a8)
{
  DWORD TickCount; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  int v15; // r9d
  signed __int8 v16; // r8
  const char *v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  int v21; // r9d
  signed __int8 v22; // r8
  const char *v23; // rdx
  int v25; // [rsp+20h] [rbp-60h]
  struct tpm12class::TPMW8_SESSION **v26; // [rsp+50h] [rbp-30h] BYREF
  struct tpm12class::TPMW8_SESSION *v27; // [rsp+58h] [rbp-28h] BYREF
  char v28; // [rsp+60h] [rbp-20h]
  int *v29[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v31; // [rsp+B0h] [rbp+30h]
  struct tpm12class::TPMW8_SESSION *v32; // [rsp+B8h] [rbp+38h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v29, L"TpmKey20Hmac::SignHash", 1);
  if ( !byte_180109AF0 )
  {
    TickCount = GetTickCount();
    _o_srand(TickCount);
    byte_180109AF0 = 1;
  }
  if ( rand() < 327 )
  {
    *((_QWORD *)this + 7) = "TpmKey20Hmac::SignHash";
    *((_QWORD *)this + 8) = "Start";
    *((_QWORD *)this + 9) = GetTickCount64();
    *((_WORD *)this + 40) = 1;
  }
  if ( a2 )
  {
    v13 = -2144795645;
    v14 = 826;
LABEL_9:
    v31 = v13;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)v13,
      v25);
    goto LABEL_10;
  }
  if ( *((_DWORD *)this + 170) != 65537 )
  {
    v13 = -2144795643;
    v14 = 828;
    goto LABEL_9;
  }
  v32 = 0;
  v26 = &v32;
  v27 = 0;
  v28 = 1;
  v13 = TpmKey20Hmac::InitializeAuthSessionIfNeeded(this, &v27);
  v31 = v13;
  wil::details::out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>::~out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>(&v26);
  if ( (v13 & 0x80000000) != 0 )
  {
    v18 = v13;
    v19 = 831;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)v18,
      v25);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v32, 0);
LABEL_10:
    if ( *((_BYTE *)this + 80) )
    {
      v15 = v31;
      if ( v31 >= 0 )
      {
        if ( v31 )
        {
          v16 = 1;
          v17 = "CompletedWithWarning";
        }
        else
        {
          v15 = 0;
          v16 = 0;
          v17 = "Completed";
        }
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v17, v16, v15);
        *((_BYTE *)this + 81) = 0;
      }
      else if ( !*((_BYTE *)this + 81) )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v31);
        *((_BYTE *)this + 81) = 1;
      }
      *((_BYTE *)this + 80) = 0;
    }
    goto LABEL_34;
  }
  v20 = TpmKey20Hmac::Hmac(this, v32, a3, a4, a5, a6, a7, a8);
  v13 = v20;
  v31 = v20;
  if ( v20 < 0 )
  {
    v18 = (unsigned int)v20;
    v19 = 839;
    goto LABEL_21;
  }
  wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v32, 0);
  if ( *((_BYTE *)this + 80) )
  {
    v21 = v31;
    if ( v31 >= 0 )
    {
      if ( v31 )
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
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v31);
      *((_BYTE *)this + 81) = 1;
    }
    *((_BYTE *)this + 80) = 0;
  }
  v13 = 0;
LABEL_34:
  KspFunctionLogger::~KspFunctionLogger(v29);
  return v13;
}

```

## disassembly

```asm
0x180070ca0  mov     [rsp-28h+arg_10], rbx
0x180070ca5  mov     [rsp-28h+arg_18], rsi
0x180070caa  push    rbp
0x180070cab  push    rdi
0x180070cac  push    r12
0x180070cae  push    r14
0x180070cb0  push    r15
0x180070cb2  mov     rbp, rsp
0x180070cb5  sub     rsp, 80h
0x180070cbc  mov     r14d, r9d
0x180070cbf  mov     r15, r8
0x180070cc2  mov     rdi, rdx
0x180070cc5  mov     rsi, rcx
0x180070cc8  mov     r8b, 1; bool
0x180070ccb  lea     rdx, aTpmkey20hmacSi; "TpmKey20Hmac::SignHash"
0x180070cd2  lea     rcx, [rbp+var_18]; this
0x180070cd6  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180070cdb  nop
0x180070cdc  xor     r12d, r12d
0x180070cdf  mov     [rbp+arg_0], r12d
0x180070ce3  lea     rbx, [rsi+38h]
0x180070ce7  mov     [rbp+var_40], rbx
0x180070ceb  lea     rax, [rbp+arg_0]
0x180070cef  mov     [rbp+var_38], rax
0x180070cf3  cmp     cs:byte_180109AF0, r12b
0x180070cfa  jnz     short loc_180070D1D
0x180070cfc  call    cs:__imp_GetTickCount
0x180070d03  nop     dword ptr [rax+rax+00h]
0x180070d08  mov     ecx, eax
0x180070d0a  call    cs:__imp__o_srand
0x180070d11  nop     dword ptr [rax+rax+00h]
0x180070d16  mov     cs:byte_180109AF0, 1
0x180070d1d  call    cs:__imp_rand
0x180070d24  nop     dword ptr [rax+rax+00h]
0x180070d29  cmp     eax, 147h
0x180070d2e  jge     short loc_180070D5B
0x180070d30  lea     rax, aTpmkey20hmacSi_0; "TpmKey20Hmac::SignHash"
0x180070d37  mov     [rbx], rax
0x180070d3a  lea     rax, aStart; "Start"
0x180070d41  mov     [rbx+8], rax
0x180070d45  call    cs:__imp_GetTickCount64
0x180070d4c  nop     dword ptr [rax+rax+00h]
0x180070d51  mov     [rbx+10h], rax
0x180070d55  mov     word ptr [rbx+18h], 1
0x180070d5b  test    rdi, rdi
0x180070d5e  jz      short loc_180070D6C
0x180070d60  mov     edi, 80290403h
0x180070d65  mov     edx, 33Ah
0x180070d6a  jmp     short loc_180070D86
0x180070d6c  cmp     dword ptr [rsi+2A8h], 10001h
0x180070d76  jz      loc_180070DFE
0x180070d7c  mov     edi, 80290405h
0x180070d81  mov     edx, 33Ch; void *
0x180070d86  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180070d8d  mov     r9d, edi; char *
0x180070d90  mov     rcx, [rbp+28h]; this
0x180070d94  mov     [rbp+arg_0], edi
0x180070d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070d9c  nop
0x180070d9d  cmp     [rbx+18h], r12b
0x180070da1  jz      loc_180070F05
0x180070da7  mov     r9d, [rbp+arg_0]; int
0x180070dab  test    r9d, r9d
0x180070dae  jns     short loc_180070DCE
0x180070db0  cmp     [rbx+19h], r12b
0x180070db4  jnz     short loc_180070DF5
0x180070db6  mov     r8b, 0FFh; signed __int8
0x180070db9  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180070dc0  mov     rcx, rbx; this
0x180070dc3  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180070dc8  mov     byte ptr [rbx+19h], 1
0x180070dcc  jmp     short loc_180070DF5
0x180070dce  mov     rcx, rbx; this
0x180070dd1  jnz     short loc_180070DE2
0x180070dd3  xor     r9d, r9d
0x180070dd6  xor     r8d, r8d
0x180070dd9  lea     rdx, aCompleted; "Completed"
0x180070de0  jmp     short loc_180070DEC
0x180070de2  mov     r8b, 1; signed __int8
0x180070de5  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180070dec  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180070df1  mov     [rbx+19h], r12b
0x180070df5  mov     [rbx+18h], r12b
0x180070df9  jmp     loc_180070F05
0x180070dfe  mov     [rbp+arg_8], r12
0x180070e02  lea     rax, [rbp+arg_8]
0x180070e06  mov     [rbp+var_30], rax
0x180070e0a  mov     [rbp+var_28], r12
0x180070e0e  mov     [rbp+var_20], 1
0x180070e12  lea     rdx, [rbp+var_28]; struct tpm12class::TPMW8_SESSION **
0x180070e16  mov     rcx, rsi; this
0x180070e19  call    ?InitializeAuthSessionIfNeeded@TpmKey20Hmac@@QEAAJPEAPEAVTPMW8_SESSION@tpm12class@@@Z; TpmKey20Hmac::InitializeAuthSessionIfNeeded(tpm12class::TPMW8_SESSION * *)
0x180070e1e  mov     edi, eax
0x180070e20  mov     [rbp+arg_0], eax
0x180070e23  lea     rcx, [rbp+var_30]
0x180070e27  call    ??1?$out_param_t@V?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>::~out_param_t<wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>>(void)
0x180070e2c  test    edi, edi
0x180070e2e  jns     short loc_180070E59
0x180070e30  mov     r9d, edi; char *
0x180070e33  mov     edx, 33Fh; void *
0x180070e38  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180070e3f  mov     rcx, [rbp+28h]; this
0x180070e43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070e48  nop
0x180070e49  xor     edx, edx
0x180070e4b  lea     rcx, [rbp+arg_8]
0x180070e4f  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180070e54  jmp     loc_180070D9D
0x180070e59  mov     eax, [rbp+arg_38]
0x180070e5c  mov     [rsp+80h+var_48], eax; unsigned int
0x180070e60  mov     rax, [rbp+arg_30]
0x180070e64  mov     [rsp+80h+var_50], rax; unsigned int *
0x180070e69  mov     eax, [rbp+arg_28]
0x180070e6c  mov     [rsp+80h+var_58], eax; unsigned int
0x180070e70  mov     rax, [rbp+arg_20]
0x180070e74  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x180070e79  mov     r9d, r14d; unsigned int
0x180070e7c  mov     r8, r15; unsigned __int8 *
0x180070e7f  mov     rdx, [rbp+arg_8]; struct tpm12class::TPMW8_SESSION *
0x180070e83  mov     rcx, rsi; this
0x180070e86  call    ?Hmac@TpmKey20Hmac@@QEAAJPEAVTPMW8_SESSION@tpm12class@@PEAEI1IPEAII@Z; TpmKey20Hmac::Hmac(tpm12class::TPMW8_SESSION *,uchar *,uint,uchar *,uint,uint *,uint)
0x180070e8b  mov     edi, eax
0x180070e8d  mov     [rbp+arg_0], eax
0x180070e90  test    eax, eax
0x180070e92  jns     short loc_180070E9E
0x180070e94  mov     r9d, eax
0x180070e97  mov     edx, 347h
0x180070e9c  jmp     short loc_180070E38
0x180070e9e  xor     edx, edx
0x180070ea0  lea     rcx, [rbp+arg_8]
0x180070ea4  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180070ea9  nop
0x180070eaa  cmp     [rbx+18h], r12b
0x180070eae  jz      short loc_180070F02
0x180070eb0  mov     r9d, [rbp+arg_0]; int
0x180070eb4  test    r9d, r9d
0x180070eb7  jns     short loc_180070ED7
0x180070eb9  cmp     [rbx+19h], r12b
0x180070ebd  jnz     short loc_180070EFE
0x180070ebf  mov     r8b, 0FFh; signed __int8
0x180070ec2  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180070ec9  mov     rcx, rbx; this
0x180070ecc  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180070ed1  mov     byte ptr [rbx+19h], 1
0x180070ed5  jmp     short loc_180070EFE
0x180070ed7  mov     rcx, rbx; this
0x180070eda  jnz     short loc_180070EEB
0x180070edc  xor     r9d, r9d
0x180070edf  xor     r8d, r8d
0x180070ee2  lea     rdx, aCompleted; "Completed"
0x180070ee9  jmp     short loc_180070EF5
0x180070eeb  mov     r8b, 1; signed __int8
0x180070eee  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180070ef5  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180070efa  mov     [rbx+19h], r12b
0x180070efe  mov     [rbx+18h], r12b
0x180070f02  mov     edi, r12d
0x180070f05  lea     rcx, [rbp+var_18]; this
0x180070f09  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180070f0e  mov     eax, edi
0x180070f10  lea     r11, [rsp+80h+var_s0]
0x180070f18  mov     rbx, [r11+40h]
0x180070f1c  mov     rsi, [r11+48h]
0x180070f20  mov     rsp, r11
0x180070f23  pop     r15
0x180070f25  pop     r14
0x180070f27  pop     r12
0x180070f29  pop     rdi
0x180070f2a  pop     rbp
0x180070f2b  retn
```
