# Windows::UI::Input::Inking::CInkStrokeContainer::AddClipboardStrokes(uchar const *,unsigned __int64,Windows::Foundation::Point,Windows::Foundation::Rect *)

- ea: `0x180025940`
- end: `0x1800260cb`
- name: `?AddClipboardStrokes@CInkStrokeContainer@Inking@Input@UI@Windows@@EEAAJPEBE_KUPoint@Foundation@5@PEAURect@75@@Z`
- size: `1931`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x18001c138`
- `0x18001c2f8`
- `0x180025940`
- `0x180031e40`
- `0x1800337d0`
- `0x1800338e8`
- `0x18005f5e4`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025ff6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025ff6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025aa0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025aa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::AddClipboardStrokes(
        _QWORD **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  float v8; // xmm8_4
  float v9; // xmm9_4
  unsigned int v10; // r12d
  int v11; // ebx
  __int64 v12; // rdx
  __int64 (__fastcall *v14)(_QWORD **, __int64 *); // rbx
  int v15; // eax
  HRESULT v16; // r14d
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, __int64 *); // rbx
  unsigned int v19; // edi
  float v20; // xmm6_4
  float v21; // xmm7_4
  signed int v22; // esi
  char v23; // r13
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, _QWORD **); // rbx
  _QWORD *v26; // rdi
  __int64 (__fastcall *v27)(_QWORD *, __int64 *); // rbx
  __int64 v28; // rdi
  __int64 v29; // rbx
  _QWORD *v30; // rbx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, _QWORD, _QWORD **); // rdi
  _QWORD *v33; // rdi
  __m128 v34; // xmm3
  __m128 v35; // xmm2
  __int64 v36; // rsi
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64 *); // rdi
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 (__fastcall *v40)(_QWORD *, __int64 *); // rdi
  int v41; // edi
  unsigned int v42; // eax
  unsigned int v43; // edx
  int (__fastcall *v44)(_QWORD **, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v46; // [rsp+30h] [rbp-D0h]
  __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v48; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v50; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+54h] [rbp-ACh]
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+68h] [rbp-98h] BYREF
  int v55; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID v56; // [rsp+70h] [rbp-90h] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  _OWORD *v58; // [rsp+80h] [rbp-80h]
  SAFEARRAY *psa[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h]
  __int128 v61; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v62; // [rsp+B0h] [rbp-50h]
  __int128 v63; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v64; // [rsp+D0h] [rbp-30h]
  __int128 v65; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v66; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v8 = *(float *)&a4;
  v47 = a4;
  v9 = *((float *)&a4 + 1);
  v58 = a5;
  v10 = 0;
  v55 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*a1[30] + 56LL))(a1[30], &v55);
  if ( v11 < 0 )
  {
    v12 = 909;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    return (unsigned int)v11;
  }
  *(_OWORD *)psa = 0;
  v60 = 0;
  v11 = ((__int64 (__fastcall *)(_QWORD **, __int64, __int64, SAFEARRAY **))(*a1)[43])(a1, a2, a3, psa);
  if ( v11 < 0 )
  {
    v12 = 913;
    goto LABEL_3;
  }
  v57 = 0;
  v14 = (__int64 (__fastcall *)(_QWORD **, __int64 *))(*a1)[37];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v15 = v14(a1, &v57);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v56 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    v16 = CoCreateInstance(&rclsid, 0, 3u, &riid, &v56);
    if ( v16 >= 0 )
    {
      v65 = *(_OWORD *)psa;
      v66 = v60;
      v16 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v56 + 208LL))(v56, &v65);
      if ( v16 >= 0 )
      {
        v52 = 0;
        v17 = v56;
        v18 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v56 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v16 = v18(v17, &v52);
        if ( v16 >= 0 )
        {
          v19 = 0;
          v46 = 0;
          v65 = 0;
          v50 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 56LL))(v52, &v50);
          if ( v16 < 0 )
          {
            v43 = 0;
          }
          else
          {
            v20 = FLOAT_3_4028235e38;
            v21 = FLOAT_3_4028235e38;
            v51 = v50;
            v22 = 0;
            do
            {
              v23 = 0;
              if ( v22 >= (int)v50 )
                break;
              v48 = 0;
              v24 = v52;
              v25 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v52 + 96LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
              v16 = v25(v24, (unsigned int)v22, &v48);
              if ( v16 >= 0 )
              {
                v49 = 0;
                v26 = v48;
                v27 = *(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v48 + 72LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
                v16 = v27(v26, &v49);
                if ( v16 >= 0 )
                {
                  Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkDrawingAttributes,>(&v53);
                  v28 = v53;
                  if ( v53 )
                  {
                    v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 136LL))(v53, v49);
                    if ( v16 >= 0 )
                    {
                      Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkStroke,>(&v47);
                      v29 = v47;
                      if ( v47 )
                      {
                        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, _QWORD, _QWORD))(*(_QWORD *)v47 + 128LL))(
                                v47,
                                v48,
                                v28,
                                0,
                                0);
                        if ( v16 >= 0 )
                        {
                          v63 = 0;
                          v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v29 + 64LL))(v29, &v63);
                          if ( v16 >= 0 )
                          {
                            v20 = fminf(*(float *)&v63, v20);
                            v21 = fminf(*((float *)&v63 + 1), v21);
                            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 104LL))(v57, v29);
                          }
                        }
                      }
                      else
                      {
                        v16 = -2147024882;
                      }
                      if ( v29 )
                      {
                        v47 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                      }
                    }
                  }
                  else
                  {
                    v16 = -2147024882;
                  }
                  if ( v28 )
                  {
                    v53 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                  }
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
              ++v22;
              v23 = 0;
            }
            while ( v16 >= 0 );
            v19 = 0;
            while ( v16 >= 0 && v10 < v50 )
            {
              v48 = 0;
              v30 = 0;
              v31 = v57;
              v32 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v57 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
              v16 = v32(v31, v10, &v48);
              if ( v16 >= 0 )
              {
                v33 = v48;
                if ( v48 )
                {
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 8LL))(v48);
                  v30 = v33;
                }
                v63 = 0;
                v64 = 0;
                v16 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(v30[2] + 48LL))(v30 + 2, &v63);
                if ( v16 >= 0 )
                {
                  v34 = (__m128)(unsigned int)v64;
                  v34.m128_f32[0] = *(float *)&v64 + (float)(v8 - v20);
                  v35 = (__m128)HIDWORD(v64);
                  v35.m128_f32[0] = *((float *)&v64 + 1) + (float)(v9 - v21);
                  v61 = v63;
                  v64 = _mm_unpacklo_ps(v34, v35).m128_u64[0];
                  v62 = v64;
                  v16 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(v30[2] + 56LL))(v30 + 2, &v61);
                  if ( v16 >= 0 )
                  {
                    v63 = 0;
                    v16 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(*v48 + 64LL))(v48, &v63);
                    if ( v16 >= 0 )
                      v16 = ((__int64 (__fastcall *)(_QWORD **, __int128 *, __int128 *))(*a1)[26])(a1, &v65, &v63);
                  }
                }
              }
              v49 = 0;
              if ( v16 < 0 )
                goto LABEL_53;
              v36 = v52;
              v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 96LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              v16 = v37(v36, v10, &v49);
              if ( v16 < 0
                || (LOBYTE(v38) = 1,
                    wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::ReportUsage(
                      `wil::Feature<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::GetImpl'::`2'::impl,
                      v38),
                    v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v30 + 216LL))(v30, v49),
                    v16 < 0)
                || (LOBYTE(v39) = 1,
                    wil::details::FeatureImpl<__WilFeatureTraits_Feature_InkPointTimestamp>::ReportUsage(
                      `wil::Feature<__WilFeatureTraits_Feature_InkPointTimestamp>::GetImpl'::`2'::impl,
                      v39),
                    v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v30 + 224LL))(v30, v49),
                    v16 < 0)
                || (v16 = ((__int64 (__fastcall *)(_QWORD **, _QWORD *))(*a1)[7])(a1, v48), v16 < 0)
                || v23 )
              {
LABEL_53:
                v19 = v46;
              }
              else
              {
                LODWORD(v53) = 0;
                v47 = 0;
                v40 = *(__int64 (__fastcall **)(_QWORD *, __int64 *))(v30[2] + 64LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                v41 = v40(v30 + 2, &v47);
                if ( v41 < 0
                  || (v41 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 56LL))(v47, &v53), v41 < 0) )
                {
                  v23 = 1;
                }
                else
                {
                  v46 += v53;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                v42 = 0;
                if ( v41 >= 0 )
                  v42 = v46;
                v19 = v42;
                v46 = v42;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              if ( v30 )
                (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
              ++v10;
            }
            v43 = v51;
          }
          LogPasteFromClipboardInkStrokesInkPoints((unsigned __int64)a1[34], v43, v19);
          *v58 = v65;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      }
    }
    SafeArrayDestroy(psa[1]);
    v54 = 0;
    if ( (*(int (__fastcall **)(_QWORD *, int *))(*a1[30] + 56LL))(a1[30], &v54) >= 0 && v55 != v54 )
    {
      v47 = 0;
      v44 = (int (__fastcall *)(_QWORD **, __int64 *))(*a1)[37];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      if ( v44(a1, &v47) >= 0 )
        CInkStrokeContainerEventHelper::RaiseEvent(a1 + 14, 4, a1, v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v15,
      ppv);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180025940  mov     rax, rsp
0x180025943  push    rbp
0x180025944  push    rbx
0x180025945  push    rsi
0x180025946  push    rdi
0x180025947  push    r12
0x180025949  push    r13
0x18002594b  push    r14
0x18002594d  push    r15
0x18002594f  lea     rbp, [rsp-58h]
0x180025954  sub     rsp, 158h
0x18002595b  movaps  xmmword ptr [rax-58h], xmm6
0x18002595f  movaps  xmmword ptr [rax-68h], xmm7
0x180025963  movaps  xmmword ptr [rax-78h], xmm8
0x180025968  movaps  xmmword ptr [rax-88h], xmm9
0x180025970  mov     rax, cs:__security_cookie
0x180025977  xor     rax, rsp
0x18002597a  mov     [rbp+90h+var_90], rax
0x18002597e  mov     rsi, r8
0x180025981  mov     rdi, rdx
0x180025984  mov     r15, rcx
0x180025987  movq    xmm8, r9
0x18002598c  movsd   [rsp+190h+var_158], xmm8
0x180025993  movss   xmm9, dword ptr [rsp+190h+var_158+4]
0x18002599a  mov     rax, [rbp+90h+arg_20]
0x1800259a1  mov     [rbp+90h+var_110], rax
0x1800259a5  xor     r12d, r12d
0x1800259a8  mov     [rsp+190h+var_124], r12d
0x1800259ad  mov     rcx, [rcx+0F0h]
0x1800259b4  mov     rax, [rcx]
0x1800259b7  lea     rdx, [rsp+190h+var_124]
0x1800259bc  mov     rax, [rax+38h]
0x1800259c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c5  mov     ebx, eax
0x1800259c7  test    eax, eax
0x1800259c9  jns     short loc_1800259ED
0x1800259cb  mov     edx, 38Dh; void *
0x1800259d0  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800259d7  mov     r9d, ebx; char *
0x1800259da  mov     rcx, [rbp+98h]; this
0x1800259e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259e6  mov     eax, ebx
0x1800259e8  jmp     loc_18002608B
0x1800259ed  xorps   xmm0, xmm0
0x1800259f0  xor     eax, eax
0x1800259f2  movups  xmmword ptr [rbp+90h+psa], xmm0
0x1800259f6  mov     [rbp+90h+var_F8], rax
0x1800259fa  mov     rax, [r15]
0x1800259fd  lea     r9, [rbp+90h+psa]
0x180025a01  mov     r8, rsi
0x180025a04  mov     rdx, rdi
0x180025a07  mov     rcx, r15
0x180025a0a  mov     rax, [rax+158h]
0x180025a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a16  mov     ebx, eax
0x180025a18  test    eax, eax
0x180025a1a  jns     short loc_180025A23
0x180025a1c  mov     edx, 391h
0x180025a21  jmp     short loc_1800259D0
0x180025a23  mov     [rsp+190h+var_118], r12
0x180025a28  mov     rax, [r15]
0x180025a2b  mov     rbx, [rax+128h]
0x180025a32  lea     rcx, [rsp+190h+var_118]
0x180025a37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a3c  lea     rdx, [rsp+190h+var_118]
0x180025a41  mov     rcx, r15
0x180025a44  mov     rax, rbx
0x180025a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a4c  mov     r14d, eax
0x180025a4f  test    eax, eax
0x180025a51  jns     short loc_180025A73
0x180025a53  mov     rcx, [rbp+98h]; this
0x180025a5a  mov     r9d, eax; char *
0x180025a5d  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180025a64  mov     edx, 394h; void *
0x180025a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025a6e  jmp     loc_18002607E
0x180025a73  mov     [rsp+190h+var_120], r12
0x180025a78  lea     rcx, [rsp+190h+var_120]
0x180025a7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a82  lea     rax, [rsp+190h+var_120]
0x180025a87  mov     qword ptr [rsp+190h+ppv], rax; ppv
0x180025a8c  lea     r9, riid; riid
0x180025a93  xor     edx, edx; pUnkOuter
0x180025a95  lea     r8d, [rdx+3]; dwClsContext
0x180025a99  lea     rcx, rclsid; rclsid
0x180025aa0  call    cs:__imp_CoCreateInstance
0x180025aa6  mov     r14d, eax
0x180025aa9  test    eax, eax
0x180025aab  js      loc_180025FF2
0x180025ab1  mov     rcx, [rsp+190h+var_120]
0x180025ab6  movups  xmm0, xmmword ptr [rbp+90h+psa]
0x180025aba  movaps  [rbp+90h+var_B0], xmm0
0x180025abe  movsd   xmm1, [rbp+90h+var_F8]
0x180025ac3  movsd   [rbp+90h+var_A0], xmm1
0x180025ac8  mov     rax, [rcx]
0x180025acb  lea     rdx, [rbp+90h+var_B0]
0x180025acf  mov     rax, [rax+0D0h]
0x180025ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025adb  mov     r14d, eax
0x180025ade  test    eax, eax
0x180025ae0  js      loc_180025FF2
0x180025ae6  mov     [rsp+190h+var_138], r12
0x180025aeb  mov     rdi, [rsp+190h+var_120]
0x180025af0  mov     rax, [rdi]
0x180025af3  mov     rbx, [rax+38h]
0x180025af7  lea     rcx, [rsp+190h+var_138]
0x180025afc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025b01  lea     rdx, [rsp+190h+var_138]
0x180025b06  mov     rcx, rdi
0x180025b09  mov     rax, rbx
0x180025b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b11  mov     r14d, eax
0x180025b14  test    eax, eax
0x180025b16  js      loc_180025FE8
0x180025b1c  mov     edi, r12d
0x180025b1f  mov     [rsp+190h+var_160], r12d
0x180025b24  xorps   xmm0, xmm0
0x180025b27  movups  [rbp+90h+var_B0], xmm0
0x180025b2b  mov     [rsp+190h+var_140], r12d
0x180025b30  mov     rcx, [rsp+190h+var_138]
0x180025b35  mov     rax, [rcx]
0x180025b38  lea     rdx, [rsp+190h+var_140]
0x180025b3d  mov     rax, [rax+38h]
0x180025b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b46  mov     r14d, eax
0x180025b49  test    eax, eax
0x180025b4b  js      loc_1800260C3
0x180025b51  movss   xmm6, cs:__real@7f7fffff
0x180025b59  movaps  xmm7, xmm6
0x180025b5c  mov     eax, [rsp+190h+var_140]
0x180025b60  mov     [rsp+190h+var_13C], eax
0x180025b64  mov     esi, r12d
0x180025b67  mov     r13b, r12b
0x180025b6a  cmp     esi, [rsp+190h+var_140]
0x180025b6e  jge     loc_180025D0C
0x180025b74  mov     [rsp+190h+var_150], r12
0x180025b79  mov     rdi, [rsp+190h+var_138]
0x180025b7e  mov     rax, [rdi]
0x180025b81  mov     rbx, [rax+60h]
0x180025b85  lea     rcx, [rsp+190h+var_150]
0x180025b8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025b8f  lea     r8, [rsp+190h+var_150]
0x180025b94  mov     edx, esi
0x180025b96  mov     rcx, rdi
0x180025b99  mov     rax, rbx
0x180025b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba1  mov     r14d, eax
0x180025ba4  test    eax, eax
0x180025ba6  js      loc_180025CF4
0x180025bac  mov     [rsp+190h+var_148], r12
0x180025bb1  mov     rdi, [rsp+190h+var_150]
0x180025bb6  mov     rax, [rdi]
0x180025bb9  mov     rbx, [rax+48h]
0x180025bbd  lea     rcx, [rsp+190h+var_148]
0x180025bc2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025bc7  lea     rdx, [rsp+190h+var_148]
0x180025bcc  mov     rcx, rdi
0x180025bcf  mov     rax, rbx
0x180025bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bd7  mov     r14d, eax
0x180025bda  test    eax, eax
0x180025bdc  js      loc_180025CEA
0x180025be2  lea     rcx, [rsp+190h+var_130]
0x180025be7  call    ??$Make@VCInkDrawingAttributes@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkDrawingAttributes@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkDrawingAttributes,>(void)
0x180025bec  mov     rdi, [rsp+190h+var_130]
0x180025bf1  test    rdi, rdi
0x180025bf4  jz      loc_180025CCA
0x180025bfa  mov     rax, [rdi]
0x180025bfd  mov     rdx, [rsp+190h+var_148]
0x180025c02  mov     rcx, rdi
0x180025c05  mov     rax, [rax+88h]
0x180025c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c11  mov     r14d, eax
0x180025c14  test    eax, eax
0x180025c16  js      loc_180025CD0
0x180025c1c  lea     rcx, [rsp+190h+var_158]
0x180025c21  call    ??$Make@VCInkStroke@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkStroke@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkStroke,>(void)
0x180025c26  mov     rbx, [rsp+190h+var_158]
0x180025c2b  test    rbx, rbx
0x180025c2e  jz      short loc_180025CA8
0x180025c30  mov     rax, [rbx]
0x180025c33  mov     qword ptr [rsp+190h+ppv], r12
0x180025c38  xor     r9d, r9d
0x180025c3b  mov     r8, rdi
0x180025c3e  mov     rdx, [rsp+190h+var_150]
0x180025c43  mov     rcx, rbx
0x180025c46  mov     rax, [rax+80h]
0x180025c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c52  mov     r14d, eax
0x180025c55  test    eax, eax
0x180025c57  js      short loc_180025CAE
0x180025c59  xorps   xmm0, xmm0
0x180025c5c  movups  [rbp+90h+var_D0], xmm0
0x180025c60  mov     rax, [rbx]
0x180025c63  lea     rdx, [rbp+90h+var_D0]
0x180025c67  mov     rcx, rbx
0x180025c6a  mov     rax, [rax+40h]
0x180025c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c73  mov     r14d, eax
0x180025c76  test    eax, eax
0x180025c78  js      short loc_180025CAE
0x180025c7a  movss   xmm0, dword ptr [rbp+90h+var_D0]
0x180025c7f  minss   xmm0, xmm6
0x180025c83  movaps  xmm6, xmm0
0x180025c86  movss   xmm1, dword ptr [rbp+90h+var_D0+4]
0x180025c8b  minss   xmm1, xmm7
0x180025c8f  movaps  xmm7, xmm1
0x180025c92  mov     rcx, [rsp+190h+var_118]
0x180025c97  mov     rax, [rcx]
0x180025c9a  mov     rdx, rbx
0x180025c9d  mov     rax, [rax+68h]
0x180025ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca6  jmp     short loc_180025CAE
0x180025ca8  mov     r14d, 8007000Eh
0x180025cae  test    rbx, rbx
0x180025cb1  jz      short loc_180025CC8
0x180025cb3  mov     [rsp+190h+var_158], r12
0x180025cb8  mov     rax, [rbx]
0x180025cbb  mov     rcx, rbx
0x180025cbe  mov     rax, [rax+10h]
0x180025cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cc7  nop
0x180025cc8  jmp     short loc_180025CD0
0x180025cca  mov     r14d, 8007000Eh
0x180025cd0  test    rdi, rdi
0x180025cd3  jz      short loc_180025CEA
0x180025cd5  mov     [rsp+190h+var_130], r12
0x180025cda  mov     rax, [rdi]
0x180025cdd  mov     rcx, rdi
0x180025ce0  mov     rax, [rax+10h]
0x180025ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce9  nop
0x180025cea  lea     rcx, [rsp+190h+var_148]
0x180025cef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025cf4  lea     rcx, [rsp+190h+var_150]
0x180025cf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025cfe  inc     esi
0x180025d00  mov     r13b, r12b
0x180025d03  test    r14d, r14d
0x180025d06  jns     loc_180025B67
0x180025d0c  mov     edi, [rsp+190h+var_160]
0x180025d10  jmp     loc_180025FBD
0x180025d15  cmp     r12d, [rsp+190h+var_140]
0x180025d1a  jnb     loc_180025FC6
0x180025d20  mov     [rsp+190h+var_150], 0
0x180025d29  xor     ebx, ebx
0x180025d2b  mov     rsi, [rsp+190h+var_118]
0x180025d30  mov     rax, [rsi]
0x180025d33  mov     rdi, [rax+30h]
0x180025d37  lea     rcx, [rsp+190h+var_150]
0x180025d3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025d41  lea     r8, [rsp+190h+var_150]
0x180025d46  mov     edx, r12d
0x180025d49  mov     rcx, rsi
0x180025d4c  mov     rax, rdi
0x180025d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d54  mov     r14d, eax
0x180025d57  test    eax, eax
0x180025d59  js      loc_180025E3C
0x180025d5f  mov     rdi, [rsp+190h+var_150]
0x180025d64  test    rdi, rdi
0x180025d67  jz      short loc_180025D7C
0x180025d69  mov     rax, [rdi]
0x180025d6c  mov     rcx, rdi
0x180025d6f  mov     rax, [rax+8]
0x180025d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d78  nop
0x180025d79  mov     rbx, rdi
0x180025d7c  xorps   xmm0, xmm0
0x180025d7f  xor     eax, eax
0x180025d81  movups  [rbp+90h+var_D0], xmm0
0x180025d85  mov     [rbp+90h+var_C0], rax
0x180025d89  lea     rdi, [rbx+10h]
0x180025d8d  mov     rax, [rdi]
0x180025d90  lea     rdx, [rbp+90h+var_D0]
0x180025d94  mov     rcx, rdi
0x180025d97  mov     rax, [rax+30h]
0x180025d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025da0  mov     r14d, eax
0x180025da3  test    eax, eax
0x180025da5  js      loc_180025E3C
0x180025dab  movaps  xmm0, xmm8
0x180025daf  subss   xmm0, xmm6
0x180025db3  movss   xmm3, dword ptr [rbp+90h+var_C0]
0x180025db8  addss   xmm3, xmm0
0x180025dbc  movaps  xmm1, xmm9
0x180025dc0  subss   xmm1, xmm7
0x180025dc4  movss   xmm2, dword ptr [rbp+90h+var_C0+4]
0x180025dc9  addss   xmm2, xmm1
0x180025dcd  movups  xmm0, [rbp+90h+var_D0]
0x180025dd1  movaps  [rbp+90h+var_F0], xmm0
0x180025dd5  unpcklps xmm3, xmm2
0x180025dd8  movsd   [rbp+90h+var_C0], xmm3
0x180025ddd  movsd   [rbp+90h+var_E0], xmm3
0x180025de2  mov     rax, [rdi]
0x180025de5  lea     rdx, [rbp+90h+var_F0]
0x180025de9  mov     rcx, rdi
0x180025dec  mov     rax, [rax+38h]
0x180025df0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
