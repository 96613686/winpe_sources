# SpeechMicDiagnostic::CaptureStream::InitializeCaptureTargets(std::shared_ptr<SpeechMicDiagnostic::DiagnosticStatus> &,ushort const *)

- ea: `0x18000eb3c`
- end: `0x18000eee3`
- name: `?InitializeCaptureTargets@CaptureStream@SpeechMicDiagnostic@@AEAAJAEAV?$shared_ptr@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@PEBG@Z`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f5f0`

## callees

- `0x180002ce0`
- `0x180003260`
- `0x180003278`
- `0x180003290`
- `0x1800032f0`
- `0x180003334`
- `0x180005b28`
- `0x18000dbb8`
- `0x18000eb3c`
- `0x18000fef4`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000ec00`
- `ole32!CoCreateInstance` at `0x18000ec00`

## string_xrefs

- `0x18000ec50`: `onecoreuap\enduser\nui\onecore\speechmicdiagnostic\lib\filewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::InitializeCaptureTargets(__int64 a1, _QWORD *a2, __int64 a3)
{
  void *v6; // rbx
  LPVOID *v7; // rsi
  __int64 v8; // rdx
  HRESULT Instance; // ebx
  __int64 v11; // r14
  LPVOID v12; // rcx
  __int64 v13; // rdx
  __m128d v14; // xmm0
  SpeechMicDiagnostic::LevelMonitor *v15; // rsi
  __int64 v16; // rbx
  int v17; // esi
  __int64 v18; // rdx
  void *v19; // rcx
  unsigned int v20; // ebx
  void *v21; // rax
  unsigned __int64 v22; // rdx
  void **v23; // r14
  void *v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // rax
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rbx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  char v31; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  _QWORD *v33; // [rsp+90h] [rbp+18h]
  _QWORD *v34; // [rsp+90h] [rbp+18h]
  _BYTE *v35; // [rsp+90h] [rbp+18h]

  if ( a3 )
  {
    v33 = operator new(8u);
    *v33 = 0;
    v6 = *(void **)(a1 + 80);
    *(_QWORD *)(a1 + 80) = v33;
    if ( v6 )
    {
      Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(v6);
      operator delete(v6, 8u);
    }
    v7 = *(LPVOID **)(a1 + 80);
    if ( !v7 )
    {
      v8 = 169;
LABEL_6:
      Instance = -2147024882;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      return (unsigned int)Instance;
    }
    v11 = *(_QWORD *)(a1 + 120);
    v12 = *v7;
    if ( *v7 )
    {
      *v7 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    Instance = CoCreateInstance(&CLSID_SpStream, 0, 0x17u, &GUID_12e3cca9_7518_44c5_a5e7_ba5a79cb929e, v7);
    if ( Instance < 0 )
    {
      v13 = 24;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\filewriter.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v8 = 174;
      goto LABEL_7;
    }
    ppv = v11;
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64))(*(_QWORD *)*v7 + 136LL))(
                 *v7,
                 a3,
                 3,
                 a1 + 104);
    if ( Instance < 0 )
    {
      v13 = 27;
      goto LABEL_14;
    }
  }
  if ( *(_DWORD *)(a1 + 160) )
    goto LABEL_38;
  v34 = operator new(0x60u);
  *v34 = 0;
  v34[1] = 0;
  v34[3] = 0;
  *((_DWORD *)v34 + 16) = 0;
  v34[11] = 0;
  v34[2] = 0;
  v34[4] = 0;
  v34[5] = 0;
  v14 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0eN12;
  v14.m128d_f64[0] = sqrt(1.0e-12);
  v14.m128d_f64[0] = o_log10_0(v14.m128d_f64[0]) * 20.0;
  *((__m128d *)v34 + 3) = _mm_unpacklo_pd(v14, v14);
  *(_QWORD *)((char *)v34 + 68) = 0;
  v15 = *(SpeechMicDiagnostic::LevelMonitor **)(a1 + 88);
  *(_QWORD *)(a1 + 88) = v34;
  if ( v15 )
  {
    SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(v15);
    operator delete(v15, 0x60u);
  }
  v16 = *(_QWORD *)(a1 + 88);
  if ( !v16 )
  {
    v8 = 180;
    goto LABEL_6;
  }
  v17 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL);
  if ( !v17 )
  {
    v18 = 75;
LABEL_36:
    v20 = -2147024809;
    goto LABEL_37;
  }
  v35 = operator new(0x10u);
  *(_QWORD *)v35 = 0x3FB999999999999ALL;
  v35[8] = 0;
  v19 = *(void **)v16;
  *(_QWORD *)v16 = v35;
  if ( v19 )
    operator delete(v19, 0x10u);
  if ( !*(_QWORD *)v16 )
  {
    v20 = -2147024882;
    v18 = 78;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\levelmonitor.cpp",
      (const char *)v20,
      ppv);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)v20,
      ppva);
    return v20;
  }
  *(_DWORD *)(v16 + 76) = (unsigned int)(3 * (v17 + 85)) >> 8;
  *(_DWORD *)(v16 + 80) = (unsigned int)(v17 + 255) >> 8;
  *(_DWORD *)(v16 + 84) = (unsigned int)(7 * v17 + 255) >> 8;
  *(_DWORD *)(v16 + 88) = (unsigned int)(20 * v17 + 255) >> 8;
  *(double *)(v16 + 24) = 256.0 / (double)v17;
  v21 = operator new[](0x600u);
  v23 = (void **)(v16 + 8);
  if ( (char *)(v16 + 8) == &v31 )
  {
    if ( v21 )
    {
      v24 = v21;
LABEL_31:
      operator delete(v24, v22);
    }
  }
  else
  {
    v24 = *v23;
    *v23 = v21;
    if ( v24 )
      goto LABEL_31;
  }
  if ( !*v23 )
  {
    v20 = -2147024882;
    v18 = 89;
    goto LABEL_37;
  }
  memset_0(*v23, 0, 0x600u);
  v25 = (150 * v17 / 0x3E8u + 255) >> 8;
  *(_DWORD *)(v16 + 92) = v25;
  if ( v25 > *(_DWORD *)(v16 + 88) / 0xAu )
  {
    v18 = 98;
    goto LABEL_36;
  }
LABEL_38:
  v26 = a2[1];
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
  v27 = a2[1];
  *(_QWORD *)(a1 + 64) = *a2;
  v28 = *(volatile signed __int32 **)(a1 + 72);
  *(_QWORD *)(a1 + 72) = v27;
  if ( v28 && _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
    if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
  }
  return 0;
}

```

## disassembly

```asm
0x18000eb3c  mov     [rsp+arg_0], rbx
0x18000eb41  mov     [rsp+arg_8], rbp
0x18000eb46  push    rsi
0x18000eb47  push    rdi
0x18000eb48  push    r12
0x18000eb4a  push    r14
0x18000eb4c  push    r15
0x18000eb4e  sub     rsp, 50h
0x18000eb52  mov     rbp, r8
0x18000eb55  mov     r15, rdx
0x18000eb58  mov     rdi, rcx
0x18000eb5b  xor     r12d, r12d
0x18000eb5e  test    r8, r8
0x18000eb61  jz      loc_18000EC6B
0x18000eb67  lea     esi, [r12+8]
0x18000eb6c  mov     ecx, esi; Size
0x18000eb6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eb73  mov     [rsp+78h+arg_10], rax
0x18000eb7b  mov     [rax], r12
0x18000eb7e  mov     rbx, [rdi+50h]
0x18000eb82  mov     [rdi+50h], rax
0x18000eb86  test    rbx, rbx
0x18000eb89  jz      short loc_18000EB9D
0x18000eb8b  mov     rcx, rbx
0x18000eb8e  call    ??1?$ComPtr@UIMMDevice@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(void)
0x18000eb93  mov     edx, esi; unsigned __int64
0x18000eb95  mov     rcx, rbx; void *
0x18000eb98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eb9d  mov     rsi, [rdi+50h]
0x18000eba1  test    rsi, rsi
0x18000eba4  jnz     short loc_18000EBCB
0x18000eba6  mov     edx, 0A9h; void *
0x18000ebab  mov     ebx, 8007000Eh
0x18000ebb0  mov     rcx, [rsp+78h]; this
0x18000ebb5  mov     r9d, ebx; char *
0x18000ebb8  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000ebbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebc4  mov     eax, ebx
0x18000ebc6  jmp     loc_18000EEC9
0x18000ebcb  mov     r14, [rdi+78h]
0x18000ebcf  mov     rcx, [rsi]
0x18000ebd2  test    rcx, rcx
0x18000ebd5  jz      short loc_18000EBE7
0x18000ebd7  mov     [rsi], r12
0x18000ebda  mov     rax, [rcx]
0x18000ebdd  mov     rax, [rax+10h]
0x18000ebe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe6  nop
0x18000ebe7  mov     [rsp+78h+ppv], rsi; ppv
0x18000ebec  lea     r9, _GUID_12e3cca9_7518_44c5_a5e7_ba5a79cb929e; riid
0x18000ebf3  xor     edx, edx; pUnkOuter
0x18000ebf5  lea     r8d, [rdx+17h]; dwClsContext
0x18000ebf9  lea     rcx, CLSID_SpStream; rclsid
0x18000ec00  call    cs:__imp_CoCreateInstance
0x18000ec07  nop     dword ptr [rax+rax+00h]
0x18000ec0c  mov     ebx, eax
0x18000ec0e  test    eax, eax
0x18000ec10  jns     short loc_18000EC19
0x18000ec12  mov     edx, 18h
0x18000ec17  jmp     short loc_18000EC4D
0x18000ec19  mov     rcx, [rsi]
0x18000ec1c  mov     rax, [rcx]
0x18000ec1f  lea     r9, [rdi+68h]
0x18000ec23  mov     [rsp+78h+var_50], r12
0x18000ec28  mov     [rsp+78h+ppv], r14; int
0x18000ec2d  mov     r8d, 3
0x18000ec33  mov     rdx, rbp
0x18000ec36  mov     rax, [rax+88h]
0x18000ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec42  mov     ebx, eax
0x18000ec44  test    eax, eax
0x18000ec46  jns     short loc_18000EC6B
0x18000ec48  mov     edx, 1Bh; void *
0x18000ec4d  mov     r9d, ebx; char *
0x18000ec50  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000ec57  mov     rcx, [rsp+78h]; this
0x18000ec5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec61  mov     edx, 0AEh
0x18000ec66  jmp     loc_18000EBB0
0x18000ec6b  cmp     [rdi+0A0h], r12d
0x18000ec72  jnz     loc_18000EE6C
0x18000ec78  mov     ebp, 60h ; '`'
0x18000ec7d  mov     ecx, ebp; Size
0x18000ec7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec84  mov     rbx, rax
0x18000ec87  mov     [rsp+78h+arg_10], rax
0x18000ec8f  mov     [rax], r12
0x18000ec92  mov     [rax+8], r12
0x18000ec96  mov     [rax+18h], r12
0x18000ec9a  mov     [rax+40h], r12d
0x18000ec9e  mov     [rax+58h], r12
0x18000eca2  mov     [rax+10h], r12
0x18000eca6  mov     [rax+20h], r12
0x18000ecaa  mov     [rax+28h], r12
0x18000ecae  movsd   xmm0, cs:__real@3d719799812dea11; X
0x18000ecb6  call    sqrt
0x18000ecbb  call    _o_log10_0
0x18000ecc0  mulsd   xmm0, cs:__real@4034000000000000
0x18000ecc8  unpcklpd xmm0, xmm0
0x18000eccc  movups  xmmword ptr [rbx+30h], xmm0
0x18000ecd0  mov     [rbx+44h], r12
0x18000ecd4  mov     rsi, [rdi+58h]
0x18000ecd8  mov     [rdi+58h], rbx
0x18000ecdc  test    rsi, rsi
0x18000ecdf  jz      short loc_18000ECF3
0x18000ece1  mov     rcx, rsi; this
0x18000ece4  call    ??1LevelMonitor@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(void)
0x18000ece9  mov     edx, ebp; unsigned __int64
0x18000eceb  mov     rcx, rsi; void *
0x18000ecee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ecf3  mov     rbx, [rdi+58h]
0x18000ecf7  test    rbx, rbx
0x18000ecfa  jnz     short loc_18000ED06
0x18000ecfc  mov     edx, 0B4h
0x18000ed01  jmp     loc_18000EBAB
0x18000ed06  mov     rax, [rdi+78h]
0x18000ed0a  mov     esi, [rax+4]
0x18000ed0d  test    esi, esi
0x18000ed0f  jnz     short loc_18000ED19
0x18000ed11  lea     edx, [rsi+4Bh]
0x18000ed14  jmp     loc_18000EE34
0x18000ed19  mov     ebp, 10h
0x18000ed1e  mov     ecx, ebp; Size
0x18000ed20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed25  mov     [rsp+78h+arg_10], rax
0x18000ed2d  mov     rcx, 3FB999999999999Ah
0x18000ed37  mov     [rax], rcx
0x18000ed3a  mov     [rax+8], r12b
0x18000ed3e  mov     rcx, [rbx]; void *
0x18000ed41  mov     [rbx], rax
0x18000ed44  test    rcx, rcx
0x18000ed47  jz      short loc_18000ED50
0x18000ed49  mov     edx, ebp; unsigned __int64
0x18000ed4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ed50  cmp     [rbx], r12
0x18000ed53  jnz     short loc_18000ED64
0x18000ed55  mov     ebx, 8007000Eh
0x18000ed5a  mov     edx, 4Eh ; 'N'
0x18000ed5f  jmp     loc_18000EE39
0x18000ed64  lea     eax, [rsi+55h]
0x18000ed67  lea     ecx, [rax+rax*2]
0x18000ed6a  shr     ecx, 8
0x18000ed6d  mov     [rbx+4Ch], ecx
0x18000ed70  lea     eax, [rsi+0FFh]
0x18000ed76  shr     eax, 8
0x18000ed79  mov     [rbx+50h], eax
0x18000ed7c  imul    eax, esi, 7
0x18000ed7f  mov     ebp, 0FFh
0x18000ed84  add     eax, ebp
0x18000ed86  shr     eax, 8
0x18000ed89  mov     [rbx+54h], eax
0x18000ed8c  lea     eax, [rsi+rsi*4]
0x18000ed8f  lea     eax, ds:0FFh[rax*4]
0x18000ed96  shr     eax, 8
0x18000ed99  mov     [rbx+58h], eax
0x18000ed9c  xorps   xmm0, xmm0
0x18000ed9f  cvtsi2sd xmm0, rsi
0x18000eda4  movsd   xmm1, cs:__real@4070000000000000
0x18000edac  divsd   xmm1, xmm0
0x18000edb0  movsd   qword ptr [rbx+18h], xmm1
0x18000edb5  mov     ecx, 600h; unsigned __int64
0x18000edba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000edbf  lea     r14, [rbx+8]
0x18000edc3  lea     rcx, [rsp+78h+var_38]
0x18000edc8  cmp     r14, rcx
0x18000edcb  jz      short loc_18000EDDA
0x18000edcd  mov     rcx, [r14]
0x18000edd0  mov     [r14], rax
0x18000edd3  test    rcx, rcx
0x18000edd6  jz      short loc_18000EDE7
0x18000edd8  jmp     short loc_18000EDE2
0x18000edda  test    rax, rax
0x18000eddd  jz      short loc_18000EDE7
0x18000eddf  mov     rcx, rax; void *
0x18000ede2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ede7  mov     rcx, [r14]; void *
0x18000edea  test    rcx, rcx
0x18000eded  jnz     short loc_18000EDF9
0x18000edef  mov     ebx, 8007000Eh
0x18000edf4  lea     edx, [rcx+59h]
0x18000edf7  jmp     short loc_18000EE39
0x18000edf9  xor     edx, edx; Val
0x18000edfb  mov     r8d, 600h; Size
0x18000ee01  call    memset_0
0x18000ee06  imul    ecx, esi, 96h
0x18000ee0c  mov     eax, 10624DD3h
0x18000ee11  mul     ecx
0x18000ee13  mov     ecx, edx
0x18000ee15  shr     ecx, 6
0x18000ee18  add     ecx, ebp
0x18000ee1a  shr     ecx, 8
0x18000ee1d  mov     [rbx+5Ch], ecx
0x18000ee20  mov     eax, 0CCCCCCCDh
0x18000ee25  mul     dword ptr [rbx+58h]
0x18000ee28  shr     edx, 3
0x18000ee2b  cmp     ecx, edx
0x18000ee2d  jbe     short loc_18000EE6C
0x18000ee2f  mov     edx, 62h ; 'b'; void *
0x18000ee34  mov     ebx, 80070057h
0x18000ee39  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000ee40  mov     rcx, [rsp+78h]; this
0x18000ee45  mov     edi, ebx
0x18000ee47  mov     r9d, ebx; char *
0x18000ee4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee4f  mov     rcx, [rsp+78h]; this
0x18000ee54  mov     r9d, ebx; char *
0x18000ee57  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000ee5e  mov     edx, 0B8h; void *
0x18000ee63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee68  mov     eax, ebx
0x18000ee6a  jmp     short loc_18000EEC9
0x18000ee6c  mov     rax, [r15+8]
0x18000ee70  test    rax, rax
0x18000ee73  jz      short loc_18000EE79
0x18000ee75  lock inc dword ptr [rax+8]
0x18000ee79  mov     rcx, [r15+8]
0x18000ee7d  mov     rax, [r15]
0x18000ee80  mov     [rdi+40h], rax
0x18000ee84  mov     rbx, [rdi+48h]
0x18000ee88  mov     [rdi+48h], rcx
0x18000ee8c  test    rbx, rbx
0x18000ee8f  jz      short loc_18000EEC7
0x18000ee91  or      edi, 0FFFFFFFFh
0x18000ee94  mov     eax, edi
0x18000ee96  lock xadd [rbx+8], eax
0x18000ee9b  add     eax, edi
0x18000ee9d  jnz     short loc_18000EEC7
0x18000ee9f  mov     rax, [rbx]
0x18000eea2  mov     rcx, rbx
0x18000eea5  mov     rax, [rax]
0x18000eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eead  mov     eax, edi
0x18000eeaf  lock xadd [rbx+0Ch], eax
0x18000eeb4  add     eax, edi
0x18000eeb6  jnz     short loc_18000EEC7
0x18000eeb8  mov     rax, [rbx]
0x18000eebb  mov     rcx, rbx
0x18000eebe  mov     rax, [rax+8]
0x18000eec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eec7  xor     eax, eax
0x18000eec9  lea     r11, [rsp+78h+var_28]
0x18000eece  mov     rbx, [r11+30h]
0x18000eed2  mov     rbp, [r11+38h]
0x18000eed6  mov     rsp, r11
0x18000eed9  pop     r15
0x18000eedb  pop     r14
0x18000eedd  pop     r12
0x18000eedf  pop     rdi
0x18000eee0  pop     rsi
0x18000eee1  retn
```
