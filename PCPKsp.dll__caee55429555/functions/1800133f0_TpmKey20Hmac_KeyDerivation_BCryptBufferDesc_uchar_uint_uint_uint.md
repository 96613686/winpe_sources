# TpmKey20Hmac::KeyDerivation(_BCryptBufferDesc *,uchar *,uint,uint *,uint)

- ea: `0x1800133f0`
- end: `0x1800138d2`
- name: `?KeyDerivation@TpmKey20Hmac@@UEAAJPEAU_BCryptBufferDesc@@PEAEIPEAII@Z`
- size: `1250`
- prototype: `__int64 __usercall@<rax>(TpmKey20Hmac *__hidden this@<rcx>, struct _BCryptBufferDesc *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800116d0`
- `0x1800133c4`
- `0x1800133f0`
- `0x180014830`
- `0x180014a60`
- `0x1800157c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180013450`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180013450`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18001381d`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18001381d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180013478`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180013478`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001380f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001380f`

## string_xrefs

- `0x180013600`: `Completed`
- `0x180013634`: `Completed`
- `0x180013653`: `Completed`
- `0x18001370c`: `Completed`
- `0x18001373c`: `Completed`
- `0x180013677`: `CompletedWithWarning`
- `0x180013680`: `CompletedWithWarning`
- `0x1800136fa`: `CompletedWithWarning`
- `0x1800137b2`: `CompletedWithWarning`
- `0x180013803`: `CompletedWithWarning`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey20Hmac::KeyDerivation(
        TpmKey20Hmac *this,
        struct _BCryptBufferDesc *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  ULONG cBuffers; // ecx
  __int64 v12; // rax
  int v13; // edx
  int v14; // edx
  int v15; // eax
  unsigned int v16; // edi
  const char *v17; // rdx
  signed __int8 v18; // r8
  unsigned __int8 *v19; // rsi
  unsigned int v20; // r12d
  unsigned __int8 *pvBuffer; // rbp
  unsigned __int16 *v22; // r8
  ULONG i; // edx
  struct _BCryptBuffer *v24; // r10
  ULONG BufferType; // r9d
  ULONG v26; // r9d
  int v27; // r9d
  signed __int8 v28; // r8
  const char *v29; // rdx
  DWORD TickCount; // eax
  unsigned int v31; // [rsp+20h] [rbp-98h]
  unsigned int v32; // [rsp+20h] [rbp-98h]
  unsigned int v33; // [rsp+38h] [rbp-80h]
  _BYTE v34[104]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v36; // [rsp+C0h] [rbp+8h]
  unsigned int cbBuffer; // [rsp+E8h] [rbp+30h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v34, L"TpmKey20Hmac::KeyDerivation", 1);
  if ( !byte_180109AF0 )
  {
    TickCount = GetTickCount();
    _o_srand(TickCount);
    byte_180109AF0 = 1;
  }
  if ( rand() < 327 )
  {
    *((_QWORD *)this + 7) = "TpmKey20Hmac::KeyDerivation";
    *((_QWORD *)this + 8) = "Start";
    *((_QWORD *)this + 9) = GetTickCount64();
    *((_WORD *)this + 40) = 1;
  }
  if ( a6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)0x80290404LL,
      v31);
    if ( *((_BYTE *)this + 80) )
    {
      if ( !*((_BYTE *)this + 81) )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, -2144795644);
        *((_BYTE *)this + 81) = 1;
      }
      *((_BYTE *)this + 80) = 0;
    }
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v34);
    return 2150171652LL;
  }
  else
  {
    cBuffers = a2->cBuffers;
    if ( !cBuffers )
      goto LABEL_7;
    v19 = 0;
    v20 = 0;
    pvBuffer = 0;
    cbBuffer = 0;
    v22 = 0;
    for ( i = 0; i < cBuffers; ++i )
    {
      v24 = &a2->pBuffers[i];
      BufferType = v24->BufferType;
      if ( BufferType )
      {
        v26 = BufferType - 13;
        if ( v26 )
        {
          if ( v26 == 1 )
          {
            pvBuffer = (unsigned __int8 *)v24->pvBuffer;
            cbBuffer = v24->cbBuffer;
          }
        }
        else
        {
          v19 = (unsigned __int8 *)v24->pvBuffer;
          v20 = v24->cbBuffer;
        }
      }
      else
      {
        v22 = (unsigned __int16 *)v24->pvBuffer;
      }
    }
    if ( !v19 || !pvBuffer || !v22 )
      goto LABEL_7;
    v12 = 0;
    do
    {
      v13 = aSha256_0[v12++];
      v14 = v13 - v22[v12 - 1];
    }
    while ( !v14 && v12 != 7 );
    if ( !v14 )
    {
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "ParametersValidated", 0, 0);
      *((_BYTE *)this + 81) = 0;
      if ( a5 )
        *a5 = a4;
      if ( !a3 )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "SizeCheckEarlyReturn", 0, 0);
        *((_BYTE *)this + 81) = 0;
        if ( *((_BYTE *)this + 80) )
        {
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "Completed", 0, 0);
          *((_BYTE *)this + 81) = 0;
          *((_BYTE *)this + 80) = 0;
        }
        goto LABEL_21;
      }
      v15 = TpmKey20Hmac::KeyDerivationSP800108_CTR_HMAC(this, v19, v20, pvBuffer, cbBuffer, a3, a4, v33);
      v16 = v15;
      v36 = v15;
      if ( v15 >= 0 )
      {
        if ( *((_BYTE *)this + 80) )
        {
          if ( v15 )
          {
            v17 = "CompletedWithWarning";
            v18 = 1;
          }
          else
          {
            v17 = "Completed";
            v18 = 0;
          }
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v17, v18, v15);
          *((_WORD *)this + 40) = 0;
        }
LABEL_21:
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v34);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A0,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
        (const char *)(unsigned int)v15,
        v32);
      if ( *((_BYTE *)this + 80) )
      {
        v27 = v36;
        if ( v36 < 0 )
        {
          if ( !*((_BYTE *)this + 81) )
          {
            KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v36);
            *((_BYTE *)this + 81) = 1;
          }
        }
        else
        {
          if ( v36 )
          {
            v28 = 1;
            v29 = "CompletedWithWarning";
          }
          else
          {
            v27 = 0;
            v28 = 0;
            v29 = "Completed";
          }
          KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v29, v28, v27);
          *((_BYTE *)this + 81) = 0;
        }
        *((_BYTE *)this + 80) = 0;
      }
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v34);
      return v16;
    }
    else
    {
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
        (const char *)0x80090027LL,
        v31);
      if ( *((_BYTE *)this + 80) )
      {
        if ( !*((_BYTE *)this + 81) )
        {
          KspFlowLogger::LogTransition(
            (TpmKey20Hmac *)((char *)this + 56),
            "FailedWithUnspecificError",
            255,
            -2146893785);
          *((_BYTE *)this + 81) = 1;
        }
        *((_BYTE *)this + 80) = 0;
      }
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v34);
      return 2148073511LL;
    }
  }
}

```

## disassembly

```asm
0x1800133f0  push    rbx
0x1800133f2  push    rbp
0x1800133f3  push    rsi
0x1800133f4  push    rdi
0x1800133f5  push    r12
0x1800133f7  push    r13
0x1800133f9  push    r14
0x1800133fb  push    r15
0x1800133fd  sub     rsp, 78h
0x180013401  mov     r15d, r9d
0x180013404  mov     rdi, r8
0x180013407  mov     rbx, rdx
0x18001340a  mov     r13, rcx
0x18001340d  mov     r8b, 1; bool
0x180013410  lea     rdx, aTpmkey20hmacKe; "TpmKey20Hmac::KeyDerivation"
0x180013417  lea     rcx, [rsp+0B8h+var_68]; this
0x18001341c  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180013421  nop
0x180013422  mov     [rsp+0B8h+arg_0], 0
0x18001342d  lea     r14, [r13+38h]
0x180013431  mov     [rsp+0B8h+var_78], r14
0x180013436  lea     rax, [rsp+0B8h+arg_0]
0x18001343e  mov     [rsp+0B8h+var_70], rax
0x180013443  cmp     cs:byte_180109AF0, 0
0x18001344a  jz      loc_18001380F
0x180013450  call    cs:__imp_rand
0x180013457  nop     dword ptr [rax+rax+00h]
0x18001345c  cmp     eax, 147h
0x180013461  jge     short loc_18001348F
0x180013463  lea     rax, aTpmkey20hmacKe_0; "TpmKey20Hmac::KeyDerivation"
0x18001346a  mov     [r14], rax
0x18001346d  lea     rax, aStart; "Start"
0x180013474  mov     [r14+8], rax
0x180013478  call    cs:__imp_GetTickCount64
0x18001347f  nop     dword ptr [rax+rax+00h]
0x180013484  mov     [r14+10h], rax
0x180013488  mov     word ptr [r14+18h], 1
0x18001348f  cmp     [rsp+0B8h+arg_28], 0
0x180013497  jnz     loc_180013763
0x18001349d  mov     ecx, [rbx+4]
0x1800134a0  test    ecx, ecx
0x1800134a2  jnz     loc_18001368C
0x1800134a8  mov     [rsp+0B8h+arg_0], 80090027h
0x1800134b3  mov     rcx, [rsp+0B8h]; this
0x1800134bb  mov     r9d, 80090027h; char *
0x1800134c1  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800134c8  mov     edx, 48Bh; void *
0x1800134cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134d2  nop
0x1800134d3  cmp     byte ptr [r14+18h], 0
0x1800134d8  jnz     loc_180013618
0x1800134de  lea     rcx, [rsp+0B8h+var_68]; this
0x1800134e3  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800134e8  mov     eax, 80090027h
0x1800134ed  jmp     loc_1800135AD
0x1800134f2  test    rsi, rsi
0x1800134f5  jz      short loc_1800134A8
0x1800134f7  test    rbp, rbp
0x1800134fa  jz      short loc_1800134A8
0x1800134fc  test    r8, r8
0x1800134ff  jz      short loc_1800134A8
0x180013501  xor     eax, eax
0x180013503  lea     r9, aSha256_0; "SHA256"
0x18001350a  nop     word ptr [rax+rax+00h]
0x180013510  movzx   edx, word ptr [r9+rax*2]
0x180013515  inc     rax
0x180013518  movzx   ecx, word ptr [r8+rax*2-2]
0x18001351e  sub     edx, ecx
0x180013520  jnz     short loc_180013528
0x180013522  cmp     rax, 7
0x180013526  jnz     short loc_180013510
0x180013528  test    edx, edx
0x18001352a  jnz     loc_1800134A8
0x180013530  xor     r9d, r9d; int
0x180013533  xor     r8d, r8d; signed __int8
0x180013536  lea     rdx, aParametersvali; "ParametersValidated"
0x18001353d  mov     rcx, r14; this
0x180013540  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013545  mov     byte ptr [r14+19h], 0
0x18001354a  mov     rax, [rsp+0B8h+arg_20]
0x180013552  test    rax, rax
0x180013555  jz      short loc_18001355A
0x180013557  mov     [rax], r15d
0x18001355a  test    rdi, rdi
0x18001355d  jz      short loc_1800135BF
0x18001355f  mov     [rsp+0B8h+var_88], r15d; unsigned int
0x180013564  mov     [rsp+0B8h+var_90], rdi; unsigned __int8 *
0x180013569  mov     eax, [rsp+0B8h+arg_28]
0x180013570  mov     [rsp+0B8h+var_98], eax; int
0x180013574  mov     r9, rbp; unsigned __int8 *
0x180013577  mov     r8d, r12d; unsigned int
0x18001357a  mov     rdx, rsi; unsigned __int8 *
0x18001357d  mov     rcx, r13; this
0x180013580  call    ?KeyDerivationSP800108_CTR_HMAC@TpmKey20Hmac@@IEAAJPEAEI0I0II@Z; TpmKey20Hmac::KeyDerivationSP800108_CTR_HMAC(uchar *,uint,uchar *,uint,uchar *,uint,uint)
0x180013585  mov     edi, eax
0x180013587  mov     [rsp+0B8h+arg_0], eax
0x18001358e  test    eax, eax
0x180013590  js      loc_1800137BE
0x180013596  cmp     byte ptr [r14+18h], 0
0x18001359b  jnz     loc_18001364F
0x1800135a1  lea     rcx, [rsp+0B8h+var_68]; this
0x1800135a6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800135ab  xor     eax, eax
0x1800135ad  add     rsp, 78h
0x1800135b1  pop     r15
0x1800135b3  pop     r14
0x1800135b5  pop     r13
0x1800135b7  pop     r12
0x1800135b9  pop     rdi
0x1800135ba  pop     rsi
0x1800135bb  pop     rbp
0x1800135bc  pop     rbx
0x1800135bd  retn
0x1800135bf  xor     r9d, r9d; int
0x1800135c2  xor     r8d, r8d; signed __int8
0x1800135c5  lea     rdx, aSizecheckearly; "SizeCheckEarlyReturn"
0x1800135cc  mov     rcx, r14; this
0x1800135cf  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800135d4  mov     byte ptr [r14+19h], 0
0x1800135d9  cmp     byte ptr [r14+18h], 0
0x1800135de  jz      short loc_1800135A1
0x1800135e0  mov     r9d, [rsp+0B8h+arg_0]; int
0x1800135e8  test    r9d, r9d
0x1800135eb  js      loc_18001385C
0x1800135f1  mov     rcx, r14; this
0x1800135f4  jnz     loc_1800136F7
0x1800135fa  xor     r9d, r9d; int
0x1800135fd  xor     r8d, r8d; signed __int8
0x180013600  lea     rdx, aCompleted; "Completed"
0x180013607  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18001360c  mov     byte ptr [r14+19h], 0
0x180013611  mov     byte ptr [r14+18h], 0
0x180013616  jmp     short loc_1800135A1
0x180013618  mov     r9d, [rsp+0B8h+arg_0]; int
0x180013620  test    r9d, r9d
0x180013623  js      loc_1800138AA
0x180013629  mov     rcx, r14; this
0x18001362c  jnz     short loc_180013674
0x18001362e  xor     r9d, r9d; int
0x180013631  xor     r8d, r8d; signed __int8
0x180013634  lea     rdx, aCompleted; "Completed"
0x18001363b  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013640  mov     byte ptr [r14+19h], 0
0x180013645  mov     byte ptr [r14+18h], 0
0x18001364a  jmp     loc_1800134DE
0x18001364f  test    edi, edi
0x180013651  jnz     short loc_180013680
0x180013653  lea     rdx, aCompleted; "Completed"
0x18001365a  xor     r8b, r8b; signed __int8
0x18001365d  mov     r9d, edi; int
0x180013660  mov     rcx, r14; this
0x180013663  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013668  mov     word ptr [r14+18h], 0
0x18001366f  jmp     loc_1800135A1
0x180013674  mov     r8b, 1
0x180013677  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18001367e  jmp     short loc_18001363B
0x180013680  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180013687  mov     r8b, 1
0x18001368a  jmp     short loc_18001365D
0x18001368c  xor     esi, esi
0x18001368e  xor     r12d, r12d
0x180013691  xor     ebp, ebp
0x180013693  xor     eax, eax
0x180013695  mov     [rsp+0B8h+arg_28], eax
0x18001369c  xor     r8d, r8d
0x18001369f  xor     edx, edx
0x1800136a1  mov     r11, [rbx+8]
0x1800136a5  nop     word ptr [rax+rax+00000000h]
0x1800136b0  mov     r10d, edx
0x1800136b3  shl     r10, 4
0x1800136b7  add     r10, r11
0x1800136ba  mov     r9d, [r10+4]
0x1800136be  test    r9d, r9d
0x1800136c1  jz      short loc_1800136D2
0x1800136c3  sub     r9d, 0Dh
0x1800136c7  jnz     short loc_1800136E1
0x1800136c9  mov     rsi, [r10+8]
0x1800136cd  mov     r12d, [r10]
0x1800136d0  jmp     short loc_1800136D6
0x1800136d2  mov     r8, [r10+8]
0x1800136d6  inc     edx
0x1800136d8  cmp     edx, ecx
0x1800136da  jb      short loc_1800136B0
0x1800136dc  jmp     loc_1800134F2
0x1800136e1  cmp     r9d, 1
0x1800136e5  jnz     short loc_1800136D6
0x1800136e7  mov     rbp, [r10+8]
0x1800136eb  mov     eax, [r10]
0x1800136ee  mov     [rsp+0B8h+arg_28], eax
0x1800136f5  jmp     short loc_1800136D6
0x1800136f7  mov     r8b, 1
0x1800136fa  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x180013701  jmp     loc_180013607
0x180013706  xor     r9d, r9d; int
0x180013709  xor     r8d, r8d; signed __int8
0x18001370c  lea     rdx, aCompleted; "Completed"
0x180013713  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013718  mov     byte ptr [r14+19h], 0
0x18001371d  mov     byte ptr [r14+18h], 0
0x180013722  lea     rcx, [rsp+0B8h+var_68]; this
0x180013727  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001372c  mov     eax, 80290404h
0x180013731  jmp     loc_1800135AD
0x180013736  xor     r9d, r9d; int
0x180013739  xor     r8d, r8d; signed __int8
0x18001373c  lea     rdx, aCompleted; "Completed"
0x180013743  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013748  mov     byte ptr [r14+19h], 0
0x18001374d  mov     byte ptr [r14+18h], 0
0x180013752  lea     rcx, [rsp+0B8h+var_68]; this
0x180013757  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001375c  mov     eax, edi
0x18001375e  jmp     loc_1800135AD
0x180013763  mov     [rsp+0B8h+arg_0], 80290404h
0x18001376e  mov     rcx, [rsp+0B8h]; this
0x180013776  mov     r9d, 80290404h; char *
0x18001377c  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180013783  mov     edx, 46Ch; void *
0x180013788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001378d  nop
0x18001378e  cmp     byte ptr [r14+18h], 0
0x180013793  jz      short loc_180013722
0x180013795  mov     r9d, [rsp+0B8h+arg_0]; int
0x18001379d  test    r9d, r9d
0x1800137a0  js      loc_180013835
0x1800137a6  mov     rcx, r14; this
0x1800137a9  jz      loc_180013706
0x1800137af  mov     r8b, 1
0x1800137b2  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x1800137b9  jmp     loc_180013713
0x1800137be  mov     rcx, [rsp+0B8h]; this
0x1800137c6  mov     r9d, edi; char *
0x1800137c9  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800137d0  mov     edx, 4A0h; void *
0x1800137d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137da  nop
0x1800137db  cmp     byte ptr [r14+18h], 0
0x1800137e0  jz      loc_180013752
0x1800137e6  mov     r9d, [rsp+0B8h+arg_0]; int
0x1800137ee  test    r9d, r9d
0x1800137f1  js      loc_180013883
0x1800137f7  mov     rcx, r14; this
0x1800137fa  jz      loc_180013736
0x180013800  mov     r8b, 1
0x180013803  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18001380a  jmp     loc_180013743
0x18001380f  call    cs:__imp_GetTickCount
0x180013816  nop     dword ptr [rax+rax+00h]
0x18001381b  mov     ecx, eax
0x18001381d  call    cs:__imp__o_srand
0x180013824  nop     dword ptr [rax+rax+00h]
0x180013829  mov     cs:byte_180109AF0, 1
0x180013830  jmp     loc_180013450
0x180013835  cmp     byte ptr [r14+19h], 0
0x18001383a  jnz     loc_18001371D
0x180013840  mov     r8b, 0FFh; signed __int8
0x180013843  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18001384a  mov     rcx, r14; this
0x18001384d  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013852  mov     byte ptr [r14+19h], 1
0x180013857  jmp     loc_18001371D
0x18001385c  cmp     byte ptr [r14+19h], 0
0x180013861  jnz     loc_180013611
0x180013867  mov     r8b, 0FFh; signed __int8
0x18001386a  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180013871  mov     rcx, r14; this
0x180013874  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180013879  mov     byte ptr [r14+19h], 1
0x18001387e  jmp     loc_180013611
0x180013883  cmp     byte ptr [r14+19h], 0
0x180013888  jnz     loc_18001374D
0x18001388e  mov     r8b, 0FFh; signed __int8
0x180013891  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x180013898  mov     rcx, r14; this
0x18001389b  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800138a0  mov     byte ptr [r14+19h], 1
0x1800138a5  jmp     loc_18001374D
0x1800138aa  cmp     byte ptr [r14+19h], 0
0x1800138af  jnz     loc_180013645
0x1800138b5  mov     r8b, 0FFh; signed __int8
0x1800138b8  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x1800138bf  mov     rcx, r14; this
0x1800138c2  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800138c7  mov     byte ptr [r14+19h], 1
0x1800138cc  jmp     loc_180013645
```
