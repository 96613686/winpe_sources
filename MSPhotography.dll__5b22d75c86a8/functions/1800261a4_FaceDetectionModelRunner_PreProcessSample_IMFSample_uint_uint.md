# FaceDetectionModelRunner::PreProcessSample(IMFSample *,uint,uint)

- ea: `0x1800261a4`
- end: `0x18002665f`
- name: `?PreProcessSample@FaceDetectionModelRunner@@AEAAJPEAUIMFSample@@II@Z`
- size: `1211`
- prototype: `__int64 __fastcall(FaceDetectionModelRunner *__hidden this, struct IMFSample *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026668`

## callees

- `0x180006014`
- `0x1800220bc`
- `0x180025514`
- `0x1800261a4`
- `0x180142010`

## string_xrefs

- `0x180026254`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x1800262ee`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x1800263d8`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x180026472`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`

## pseudocode

```c
__int64 __fastcall FaceDetectionModelRunner::PreProcessSample(
        FaceDetectionModelRunner *this,
        struct IMFSample *a2,
        unsigned int a3,
        unsigned int a4)
{
  struct IMFSampleVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v14)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 i; // r8
  __int64 result; // rax
  char *v20; // rdi
  __int64 v21; // rdx
  int v22; // eax
  __m128i si128; // xmm6
  int v24; // ecx
  __m128i v25; // xmm5
  char *v26; // rdi
  int j; // r9d
  int v28; // [rsp+30h] [rbp-88h]
  int v29; // [rsp+20h] [rbp-98h]
  _QWORD *v30; // [rsp+40h] [rbp-78h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD **); // [rsp+48h] [rbp-70h] BYREF
  __int64 v32; // [rsp+50h] [rbp-68h] BYREF
  struct IMFSample *v33; // [rsp+58h] [rbp-60h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD **); // [rsp+60h] [rbp-58h] BYREF
  int v35; // [rsp+68h] [rbp-50h]
  int v36[2]; // [rsp+70h] [rbp-48h] BYREF
  __int64 *v37; // [rsp+78h] [rbp-40h]
  _QWORD *v38; // [rsp+80h] [rbp-38h]
  char v39; // [rsp+88h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v41; // [rsp+C8h] [rbp+10h] BYREF

  try
  {
    v33 = a2;
    if ( a2 )
      ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
    v31 = 0;
    v30 = 0;
    v41 = 0;
    *(_QWORD *)v36 = 0;
    v35 = 0;
    v32 = 0;
    v37 = &v32;
    v38 = &v30;
    v39 = 1;
    lpVtbl = a2->lpVtbl;
    v31 = 0;
    v9 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **)))lpVtbl->ConvertToContiguousBuffer)(
           a2,
           &v31);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x210,
        (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
        (const char *)(unsigned int)v9,
        v29);
      if ( v32 )
        (*(void (__fastcall **)(_QWORD *))(*v30 + 32LL))(v30);
LABEL_27:
      wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v30);
      wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v31);
      wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v33);
      return v10;
    }
    if ( *((_BYTE *)this + 160) )
    {
      v34 = 0;
      v29 = *((_DWORD *)this + 15);
      v11 = NativePreProcessor::NNResizeNV12ToBGRA(v31, a3, a4, *((unsigned int *)this + 14));
      v10 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x215,
          (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
          (const char *)(unsigned int)v11,
          v29);
        wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v34);
        if ( v32 )
          (*(void (__fastcall **)(_QWORD *))(*v30 + 32LL))(v30);
        goto LABEL_27;
      }
      v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
      v31 = v34;
      if ( v34 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v34)[1])(v34);
      if ( v12 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
      wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v34);
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v14 = **v31;
    v15 = v30;
    v30 = 0;
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v15 + 16LL))(v15, *v15);
    v16 = v14(v13, &GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec, &v30);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21B,
        (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
        (const char *)(unsigned int)v16,
        v29);
      if ( v32 )
        (*(void (__fastcall **)(_QWORD *))(*v30 + 32LL))(v30);
      goto LABEL_27;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *, int *))(*v30 + 80LL))(v30, 1, &v32, &v41);
    v10 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
        (const char *)(unsigned int)v17,
        (int)v36);
      if ( v32 )
        (*(void (__fastcall **)(_QWORD *))(*v30 + 32LL))(v30);
      goto LABEL_27;
    }
    v20 = (char *)*((_QWORD *)this + 4);
    v21 = v32;
    v22 = *((_DWORD *)this + 15);
    if ( *((_BYTE *)this + 112) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v24 = 0;
      if ( v22 > 0 )
      {
        do
        {
          for ( i = 0; (int)i < 4 * *((_DWORD *)this + 14); i = (unsigned int)(i + 16) )
          {
            v25 = _mm_shuffle_epi8(_mm_loadu_si128((const __m128i *)((int)i + v21)), (__m128i)_xmm);
            _mm_maskmoveu_si128((__m128i)_mm_cvtepi32_ps(_mm_cvtepu8_epi32(v25)), si128, v20);
            v26 = v20 + 12;
            _mm_maskmoveu_si128((__m128i)_mm_cvtepi32_ps(_mm_cvtepu8_epi32(_mm_srli_si128(v25, 4))), si128, v26);
            v26 += 12;
            _mm_maskmoveu_si128((__m128i)_mm_cvtepi32_ps(_mm_cvtepu8_epi32(_mm_srli_si128(v25, 8))), si128, v26);
            v26 += 12;
            _mm_maskmoveu_si128((__m128i)_mm_cvtepi32_ps(_mm_cvtepu8_epi32(_mm_srli_si128(v25, 12))), si128, v26);
            v20 = v26 + 12;
          }
          v21 += v41;
          ++v24;
        }
        while ( v24 < *((_DWORD *)this + 15) );
      }
    }
    else
    {
      i = 0;
      if ( v22 > 0 )
      {
        do
        {
          for ( j = 0; j < 4 * *((_DWORD *)this + 14); j += 4 )
          {
            *((float *)v20 + 2) = (float)*(unsigned __int8 *)(j + v21);
            *((float *)v20 + 1) = (float)*(unsigned __int8 *)(j + v21 + 1);
            *(float *)v20 = (float)*(unsigned __int8 *)(j + v21 + 2);
            v20 += 12;
          }
          v21 += v41;
          i = (unsigned int)(i + 1);
        }
        while ( (int)i < *((_DWORD *)this + 15) );
      }
    }
    if ( v32 )
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v30 + 32LL))(v30, v21, i);
    wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v30);
    wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v33);
    result = 0;
  }
  catch ( ... )
  {
    v28 = 683;
    return (unsigned int)wil::details::in1diag3::Return_CaughtExceptionMsg(
                           retaddr,
                           (void *)0x2AB,
                           (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
                           "%hs:%hs:%d:Unexpected exception",
                           "avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
                           "FaceDetectionModelRunner::PreProcessSample",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x1800261a4  mov     rax, rsp
0x1800261a7  mov     [rax+8], rbx
0x1800261ab  mov     [rax+18h], rsi
0x1800261af  push    rdi
0x1800261b0  push    r14
0x1800261b2  push    r15
0x1800261b4  sub     rsp, 0A0h
0x1800261bb  movaps  xmmword ptr [rax-28h], xmm6
0x1800261bf  mov     esi, r9d
0x1800261c2  mov     r14d, r8d
0x1800261c5  mov     rdi, rdx
0x1800261c8  mov     rbx, rcx
0x1800261cb  mov     [rax-60h], rdx
0x1800261cf  xor     r15d, r15d
0x1800261d2  test    rdx, rdx
0x1800261d5  jz      short loc_1800261E7
0x1800261d7  mov     rax, [rdx]
0x1800261da  mov     rcx, rdx
0x1800261dd  mov     rax, [rax+8]
0x1800261e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e6  nop
0x1800261e7  mov     [rsp+0B8h+var_70], r15
0x1800261ec  mov     [rsp+0B8h+var_78], r15
0x1800261f1  mov     [rsp+0B8h+arg_8], r15d
0x1800261f9  mov     qword ptr [rsp+0B8h+var_48], r15
0x1800261fe  mov     [rsp+0B8h+var_50], r15d
0x180026203  mov     [rsp+0B8h+var_68], r15
0x180026208  lea     rax, [rsp+0B8h+var_68]
0x18002620d  mov     [rsp+0B8h+var_40], rax
0x180026212  lea     rax, [rsp+0B8h+var_78]
0x180026217  mov     [rsp+0B8h+var_38], rax
0x18002621f  mov     [rsp+0B8h+var_30], 1
0x180026227  mov     rax, [rdi]
0x18002622a  mov     [rsp+0B8h+var_70], r15
0x18002622f  lea     rdx, [rsp+0B8h+var_70]
0x180026234  mov     rcx, rdi
0x180026237  mov     rax, [rax+148h]
0x18002623e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026243  mov     edi, eax
0x180026245  test    eax, eax
0x180026247  jns     short loc_1800262A6
0x180026249  mov     rcx, [rsp+0B8h]; this
0x180026251  mov     r9d, eax; char *
0x180026254  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x18002625b  mov     edx, 210h; void *
0x180026260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026265  nop
0x180026266  cmp     [rsp+0B8h+var_68], r15
0x18002626b  jz      short loc_18002627F
0x18002626d  mov     rcx, [rsp+0B8h+var_78]
0x180026272  mov     rax, [rcx]
0x180026275  mov     rax, [rax+20h]
0x180026279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002627e  nop
0x18002627f  lea     rcx, [rsp+0B8h+var_78]
0x180026284  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026289  nop
0x18002628a  lea     rcx, [rsp+0B8h+var_70]
0x18002628f  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026294  nop
0x180026295  lea     rcx, [rsp+0B8h+var_60]
0x18002629a  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x18002629f  mov     eax, edi
0x1800262a1  jmp     loc_180026640
0x1800262a6  cmp     [rbx+0A0h], r15b
0x1800262ad  jz      loc_180026389
0x1800262b3  mov     [rsp+0B8h+var_58], r15
0x1800262b8  lea     rax, [rsp+0B8h+var_58]
0x1800262bd  mov     [rsp+0B8h+var_90], rax
0x1800262c2  mov     eax, [rbx+3Ch]
0x1800262c5  mov     [rsp+0B8h+var_98], eax; int
0x1800262c9  mov     r9d, [rbx+38h]
0x1800262cd  mov     r8d, esi
0x1800262d0  mov     edx, r14d
0x1800262d3  mov     rcx, [rsp+0B8h+var_70]
0x1800262d8  call    NativePreProcessor__NNResizeNV12ToBGRA
0x1800262dd  mov     edi, eax
0x1800262df  test    eax, eax
0x1800262e1  jns     short loc_18002634A
0x1800262e3  mov     rcx, [rsp+0B8h]; this
0x1800262eb  mov     r9d, eax; char *
0x1800262ee  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x1800262f5  mov     edx, 215h; void *
0x1800262fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262ff  lea     rcx, [rsp+0B8h+var_58]
0x180026304  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026309  nop
0x18002630a  cmp     [rsp+0B8h+var_68], r15
0x18002630f  jz      short loc_180026323
0x180026311  mov     rcx, [rsp+0B8h+var_78]
0x180026316  mov     rax, [rcx]
0x180026319  mov     rax, [rax+20h]
0x18002631d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026322  nop
0x180026323  lea     rcx, [rsp+0B8h+var_78]
0x180026328  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x18002632d  nop
0x18002632e  lea     rcx, [rsp+0B8h+var_70]
0x180026333  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026338  nop
0x180026339  lea     rcx, [rsp+0B8h+var_60]
0x18002633e  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026343  mov     eax, edi
0x180026345  jmp     loc_180026640
0x18002634a  mov     rcx, [rsp+0B8h+var_58]
0x18002634f  mov     rdi, [rsp+0B8h+var_70]
0x180026354  mov     [rsp+0B8h+var_70], rcx
0x180026359  test    rcx, rcx
0x18002635c  jz      short loc_18002636A
0x18002635e  mov     rax, [rcx]
0x180026361  mov     rax, [rax+8]
0x180026365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002636a  test    rdi, rdi
0x18002636d  jz      short loc_18002637F
0x18002636f  mov     rax, [rdi]
0x180026372  mov     rcx, rdi
0x180026375  mov     rax, [rax+10h]
0x180026379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002637e  nop
0x18002637f  lea     rcx, [rsp+0B8h+var_58]
0x180026384  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026389  mov     rdi, [rsp+0B8h+var_70]
0x18002638e  mov     rax, [rdi]
0x180026391  mov     rsi, [rax]
0x180026394  mov     rcx, [rsp+0B8h+var_78]
0x180026399  mov     [rsp+0B8h+var_78], r15
0x18002639e  test    rcx, rcx
0x1800263a1  jz      short loc_1800263B0
0x1800263a3  mov     rdx, [rcx]
0x1800263a6  mov     rax, [rdx+10h]
0x1800263aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263af  nop
0x1800263b0  lea     r8, [rsp+0B8h+var_78]
0x1800263b5  lea     rdx, _GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec
0x1800263bc  mov     rcx, rdi
0x1800263bf  mov     rax, rsi
0x1800263c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263c7  mov     edi, eax
0x1800263c9  test    eax, eax
0x1800263cb  jns     short loc_18002642A
0x1800263cd  mov     rcx, [rsp+0B8h]; this
0x1800263d5  mov     r9d, eax; char *
0x1800263d8  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x1800263df  mov     edx, 21Bh; void *
0x1800263e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263e9  nop
0x1800263ea  cmp     [rsp+0B8h+var_68], r15
0x1800263ef  jz      short loc_180026403
0x1800263f1  mov     rcx, [rsp+0B8h+var_78]
0x1800263f6  mov     rax, [rcx]
0x1800263f9  mov     rax, [rax+20h]
0x1800263fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026402  nop
0x180026403  lea     rcx, [rsp+0B8h+var_78]
0x180026408  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x18002640d  nop
0x18002640e  lea     rcx, [rsp+0B8h+var_70]
0x180026413  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026418  nop
0x180026419  lea     rcx, [rsp+0B8h+var_60]
0x18002641e  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026423  mov     eax, edi
0x180026425  jmp     loc_180026640
0x18002642a  mov     rcx, [rsp+0B8h+var_78]
0x18002642f  mov     rax, [rcx]
0x180026432  lea     rdx, [rsp+0B8h+var_50]
0x180026437  mov     [rsp+0B8h+var_90], rdx
0x18002643c  lea     rdx, [rsp+0B8h+var_48]
0x180026441  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180026446  lea     r9, [rsp+0B8h+arg_8]
0x18002644e  lea     r8, [rsp+0B8h+var_68]
0x180026453  mov     edx, 1
0x180026458  mov     rax, [rax+50h]
0x18002645c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026461  mov     edi, eax
0x180026463  test    eax, eax
0x180026465  jns     short loc_1800264C4
0x180026467  mov     rcx, [rsp+0B8h]; this
0x18002646f  mov     r9d, eax; char *
0x180026472  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180026479  mov     edx, 221h; void *
0x18002647e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026483  nop
0x180026484  cmp     [rsp+0B8h+var_68], r15
0x180026489  jz      short loc_18002649D
0x18002648b  mov     rcx, [rsp+0B8h+var_78]
0x180026490  mov     rax, [rcx]
0x180026493  mov     rax, [rax+20h]
0x180026497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002649c  nop
0x18002649d  lea     rcx, [rsp+0B8h+var_78]
0x1800264a2  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x1800264a7  nop
0x1800264a8  lea     rcx, [rsp+0B8h+var_70]
0x1800264ad  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x1800264b2  nop
0x1800264b3  lea     rcx, [rsp+0B8h+var_60]
0x1800264b8  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x1800264bd  mov     eax, edi
0x1800264bf  jmp     loc_180026640
0x1800264c4  mov     rdi, [rbx+20h]
0x1800264c8  mov     rdx, [rsp+0B8h+var_68]
0x1800264cd  mov     eax, [rbx+3Ch]
0x1800264d0  cmp     [rbx+70h], r15b
0x1800264d4  jz      loc_18002658D
0x1800264da  movdqa  xmm6, cs:__xmm@00000000808080808080808080808080
0x1800264e2  mov     ecx, r15d
0x1800264e5  test    eax, eax
0x1800264e7  jle     loc_1800265FC
0x1800264ed  mov     r8d, r15d
0x1800264f0  mov     eax, [rbx+38h]
0x1800264f3  shl     eax, 2
0x1800264f6  test    eax, eax
0x1800264f8  jle     short loc_180026575
0x1800264fa  movsxd  rax, r8d
0x1800264fd  movdqu  xmm5, xmmword ptr [rax+rdx]
0x180026502  pshufb  xmm5, cs:__xmm@0f0c0d0e0b08090a0704050603000102
0x18002650b  movdqa  xmm0, xmm5
0x18002650f  psrldq  xmm0, 4
0x180026514  pmovzxbd xmm2, xmm0
0x180026519  movdqa  xmm1, xmm5
0x18002651d  psrldq  xmm1, 8
0x180026522  pmovzxbd xmm3, xmm1
0x180026527  movdqa  xmm0, xmm5
0x18002652b  psrldq  xmm0, 0Ch
0x180026530  pmovzxbd xmm4, xmm0
0x180026535  pmovzxbd xmm0, xmm5
0x18002653a  cvtdq2ps xmm1, xmm0
0x18002653d  maskmovdqu xmm1, xmm6
0x180026541  add     rdi, 0Ch
0x180026545  cvtdq2ps xmm0, xmm2
0x180026548  maskmovdqu xmm0, xmm6
0x18002654c  add     rdi, 0Ch
0x180026550  cvtdq2ps xmm0, xmm3
0x180026553  maskmovdqu xmm0, xmm6
0x180026557  add     rdi, 0Ch
0x18002655b  cvtdq2ps xmm0, xmm4
0x18002655e  maskmovdqu xmm0, xmm6
0x180026562  add     rdi, 0Ch
0x180026566  add     r8d, 10h
0x18002656a  mov     eax, [rbx+38h]
0x18002656d  shl     eax, 2
0x180026570  cmp     r8d, eax
0x180026573  jl      short loc_1800264FA
0x180026575  movsxd  rax, [rsp+0B8h+arg_8]
0x18002657d  add     rdx, rax
0x180026580  inc     ecx
0x180026582  cmp     ecx, [rbx+3Ch]
0x180026585  jl      loc_1800264ED
0x18002658b  jmp     short loc_1800265FC
0x18002658d  mov     r8d, r15d
0x180026590  test    eax, eax
0x180026592  jle     short loc_1800265FC
0x180026594  mov     r9d, r15d
0x180026597  mov     eax, [rbx+38h]
0x18002659a  shl     eax, 2
0x18002659d  test    eax, eax
0x18002659f  jle     short loc_1800265E8
0x1800265a1  movsxd  rcx, r9d
0x1800265a4  movzx   eax, byte ptr [rcx+rdx]
0x1800265a8  movd    xmm0, eax
0x1800265ac  cvtdq2ps xmm0, xmm0
0x1800265af  movss   dword ptr [rdi+8], xmm0
0x1800265b4  movzx   eax, byte ptr [rcx+rdx+1]
0x1800265b9  movd    xmm1, eax
0x1800265bd  cvtdq2ps xmm1, xmm1
0x1800265c0  movss   dword ptr [rdi+4], xmm1
0x1800265c5  movzx   eax, byte ptr [rcx+rdx+2]
0x1800265ca  movd    xmm0, eax
0x1800265ce  cvtdq2ps xmm0, xmm0
0x1800265d1  movss   dword ptr [rdi], xmm0
0x1800265d5  add     rdi, 0Ch
0x1800265d9  add     r9d, 4
0x1800265dd  mov     eax, [rbx+38h]
0x1800265e0  shl     eax, 2
0x1800265e3  cmp     r9d, eax
0x1800265e6  jl      short loc_1800265A1
0x1800265e8  movsxd  rax, [rsp+0B8h+arg_8]
0x1800265f0  add     rdx, rax
0x1800265f3  inc     r8d
0x1800265f6  cmp     r8d, [rbx+3Ch]
0x1800265fa  jl      short loc_180026594
0x1800265fc  cmp     [rsp+0B8h+var_68], r15
0x180026601  jz      short loc_180026615
0x180026603  mov     rcx, [rsp+0B8h+var_78]
0x180026608  mov     rax, [rcx]
0x18002660b  mov     rax, [rax+20h]
0x18002660f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026614  nop
0x180026615  lea     rcx, [rsp+0B8h+var_78]
0x18002661a  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x18002661f  nop
0x180026620  lea     rcx, [rsp+0B8h+var_70]
0x180026625  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x18002662a  nop
0x18002662b  lea     rcx, [rsp+0B8h+var_60]
0x180026630  call    ??1?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(void)
0x180026635  xor     eax, eax
0x180026637  jmp     short loc_180026640
0x180026639  mov     eax, [rsp+0B8h+arg_8]
  ... truncated ...
```
