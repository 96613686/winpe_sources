# Windows::UI::Input::Inking::CInkStroke::Initialize(IInkStrokeDisp *,Windows::UI::Input::Inking::IInkDrawingAttributes *,unsigned __int64,unsigned __int64)

- ea: `0x180051aa0`
- end: `0x180052709`
- name: `?Initialize@CInkStroke@Inking@Input@UI@Windows@@UEAAJPEAUIInkStrokeDisp@@PEAUIInkDrawingAttributes@2345@_K2@Z`
- size: `3177`
- prototype: `__int64 __usercall@<rax>(Windows::UI::Input::Inking::CInkStroke *__hidden this@<rcx>, struct IInkStrokeDisp *@<rdx>, struct IInkDrawingAttributes *@<r8>, unsigned __int64@<r9>, unsigned __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001043c`
- `0x18001332c`
- `0x180019248`
- `0x18001bdbc`
- `0x18001bf00`
- `0x18001c1b0`
- `0x180024444`
- `0x18003d3e0`
- `0x180051aa0`
- `0x180052a00`
- `0x180054e0c`
- `0x180061ab0`
- `0x1800f85c4`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ed0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800525ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800526bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ed0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800525ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800526bd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051dbe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051efe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051dbe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526d5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052334`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052348`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052334`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052348`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051c65`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005209f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051c65`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005209f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180051c93`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005212a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180051c93`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005212a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052041`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052323`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052041`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052323`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::Initialize(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2,
        struct IInkDrawingAttributes *a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  struct IInkStrokeDisp *v6; // r15
  Windows::UI::Input::Inking::CInkStroke *v7; // rsi
  unsigned int v8; // r13d
  __int64 v9; // rdx
  int v11; // eax
  int RenderingInfoFromInkStrokeDisp; // edi
  unsigned int v13; // r12d
  float *v14; // r14
  HRESULT UBound; // ebx
  int v16; // eax
  int v17; // edi
  int v18; // r13d
  const wchar_t *v19; // rbx
  char *v20; // r9
  char *v21; // r8
  __int64 v22; // rcx
  HRESULT (__stdcall *QueryInterface)(IInkStrokeDisp *, const IID *const, void **); // rbx
  int *v24; // r14
  int v25; // r12d
  __int64 v26; // rbx
  __m128 v27; // xmm1
  __m128 v28; // xmm0
  int v29; // edi
  int v30; // eax
  signed int v31; // r12d
  signed int v32; // r8d
  int v33; // r11d
  int v34; // r9d
  _DWORD *v35; // r10
  int v36; // esi
  int v37; // r15d
  int v38; // ebx
  void *v39; // rdi
  __int64 (__fastcall *v40)(void *, _QWORD, char **); // rbx
  char *v41; // rbx
  char *v42; // rbx
  LONG v43; // ecx
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, void **); // rbx
  void *v46; // rcx
  void *v47; // rbx
  void *v48; // rbx
  __int64 v49; // rdx
  int v50; // [rsp+20h] [rbp-E0h]
  LONG plUbound; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+44h] [rbp-BCh] BYREF
  LONG v53; // [rsp+48h] [rbp-B8h] BYREF
  void *v54; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  char *v57; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  char *v59; // [rsp+78h] [rbp-88h]
  void *v60; // [rsp+80h] [rbp-80h] BYREF
  void *v61; // [rsp+88h] [rbp-78h] BYREF
  void *v62; // [rsp+90h] [rbp-70h] BYREF
  void *ppvData; // [rsp+98h] [rbp-68h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-60h] BYREF
  Windows::UI::Input::Inking::CInkStroke *v65; // [rsp+A8h] [rbp-58h]
  struct IInkStrokeDisp *v66; // [rsp+B0h] [rbp-50h]
  SAFEARRAY *psa[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-38h]
  struct IInkDrawingAttributes *v69; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v70; // [rsp+D8h] [rbp-28h]
  SAFEARRAY *v71[4]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v72[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v73[2]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v70 = a4;
  v69 = a3;
  v6 = a2;
  v66 = a2;
  v7 = this;
  v65 = this;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 280);
  v8 = 0;
  if ( !v6 )
  {
    v9 = 199;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\stroke.cpp",
      (const char *)0x80004003LL,
      v50);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v9 = 200;
    goto LABEL_5;
  }
  Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=((char *)v7 + 160, a3);
  *(_WORD *)((char *)v7 + 185) = 0;
  *((_BYTE *)v7 + 187) = 0;
  *((_QWORD *)v7 + 24) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v7 + 232);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v7 + 200);
  *((_QWORD *)v7 + 26) = 1065353216;
  *((_DWORD *)v7 + 54) = 0;
  *(_QWORD *)((char *)v7 + 220) = 1065353216;
  *((_DWORD *)v7 + 57) = 0;
  v55 = 0;
  v11 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, unsigned int *))v6->lpVtbl->get_PacketCount)(v6, &v55);
  RenderingInfoFromInkStrokeDisp = v11;
  if ( v11 >= 0 && !v55 )
  {
    RenderingInfoFromInkStrokeDisp = -2147467259;
    v60 = 0;
    v13 = 0;
LABEL_11:
    v14 = 0;
    goto LABEL_12;
  }
  v60 = 0;
  if ( v11 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    RenderingInfoFromInkStrokeDisp = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkPoint,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkPoint *>,0>>(
                                       v22,
                                       &v60);
    if ( RenderingInfoFromInkStrokeDisp >= 0 )
    {
      plUbound = 0;
      RenderingInfoFromInkStrokeDisp = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, LONG *))v6->lpVtbl->get_PacketSize)(
                                         v6,
                                         &plUbound);
      if ( RenderingInfoFromInkStrokeDisp >= 0 )
      {
        v54 = 0;
        QueryInterface = v6->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        RenderingInfoFromInkStrokeDisp = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, GUID *, void **))QueryInterface)(
                                           v6,
                                           &GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb,
                                           &v54);
        if ( RenderingInfoFromInkStrokeDisp >= 0 )
        {
          memset(v71, 0, 24);
          v24 = (int *)malloc((int)(v55 * plUbound));
          if ( v24 )
          {
            RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD, int *, SAFEARRAY **))(*(_QWORD *)v54 + 64LL))(
                                               v54,
                                               0,
                                               v55,
                                               (unsigned int)plUbound,
                                               v24,
                                               v71);
            if ( RenderingInfoFromInkStrokeDisp >= 0 )
            {
              *((_OWORD *)v7 + 13) = *(_OWORD *)v71;
              *((float *)v7 + 56) = *(float *)&v71[2] / 26.0;
              *((float *)v7 + 57) = *((float *)&v71[2] + 1) / 26.0;
              v25 = 0;
              do
              {
                if ( v25 >= (int)v55 )
                  break;
                Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkPoint,>(&v56);
                v26 = v56;
                if ( v56 )
                {
                  v27 = (__m128)COERCE_UNSIGNED_INT((float)v24[(unsigned __int64)(plUbound * v25) >> 2]);
                  v27.m128_f32[0] = v27.m128_f32[0] / 26.0;
                  v28 = (__m128)COERCE_UNSIGNED_INT((float)v24[((unsigned __int64)(plUbound * v25) >> 2) + 1]);
                  v28.m128_f32[0] = v28.m128_f32[0] / 26.0;
                  RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)(v56 + 24) + 56LL))(
                                                     v56 + 24,
                                                     _mm_unpacklo_ps(v27, v28).m128_u64[0]);
                  if ( RenderingInfoFromInkStrokeDisp >= 0 )
                    RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v60 + 104LL))(
                                                       v60,
                                                       v26);
                }
                else
                {
                  RenderingInfoFromInkStrokeDisp = -2147024882;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
                ++v25;
              }
              while ( RenderingInfoFromInkStrokeDisp >= 0 );
            }
            free(v24);
          }
          else
          {
            RenderingInfoFromInkStrokeDisp = -2147024882;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      }
    }
  }
  v13 = 0;
  if ( RenderingInfoFromInkStrokeDisp < 0 )
    goto LABEL_11;
  v14 = (float *)malloc(4LL * (int)(7 * v55));
  if ( !v14 )
  {
    RenderingInfoFromInkStrokeDisp = -2147024882;
    goto LABEL_118;
  }
  v13 = 7 * v55;
LABEL_12:
  if ( RenderingInfoFromInkStrokeDisp >= 0 )
  {
    *(__m128i *)v71 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_OWORD *)((char *)&v71[1] + 4) = *(_OWORD *)v71;
    memset(v72, 0, 28);
    memset(v73, 0, 28);
    *(_OWORD *)psa = 0;
    v68 = 0;
    if ( ((int (__fastcall *)(struct IInkStrokeDisp *, SAFEARRAY **))v6->lpVtbl->get_PacketDescription)(v6, psa) < 0
      || LOWORD(psa[0]) != 8200 )
    {
      goto LABEL_112;
    }
    plUbound = 0;
    UBound = SafeArrayGetUBound(psa[1], 1u, &plUbound);
    v16 = ++plUbound;
    if ( UBound < 0 || v16 <= 0 || (ppvData = 0, UBound = SafeArrayAccessData(psa[1], &ppvData), UBound < 0) )
    {
LABEL_88:
      SafeArrayDestroy(psa[1]);
      if ( UBound >= 0 )
      {
        if ( v14 )
        {
          LODWORD(v56) = 0;
          RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v60 + 56LL))(
                                             v60,
                                             &v56);
          if ( (_DWORD)v56 )
          {
            do
            {
              v57 = 0;
              v39 = v60;
              v40 = *(__int64 (__fastcall **)(void *, _QWORD, char **))(*(_QWORD *)v60 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
              RenderingInfoFromInkStrokeDisp = v40(v39, v8, &v57);
              if ( RenderingInfoFromInkStrokeDisp >= 0 )
              {
                v41 = v57;
                ppvData = v57;
                if ( v57 )
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v57 + 8LL))(v57);
                v42 = v41 + 24;
                v59 = v42;
                plUbound = 7 * v8;
                (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 64LL))(v42);
                (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 72LL))(v42);
                (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 80LL))(v42);
                (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 88LL))(v42);
                v43 = plUbound;
                v66 = (struct IInkStrokeDisp *)(unsigned int)(plUbound + 4);
                if ( v14[(_QWORD)v66] > 0.0 )
                {
                  v65 = (Windows::UI::Input::Inking::CInkStroke *)(unsigned int)(plUbound + 5);
                  if ( v14[(_QWORD)v65] > 0.0 )
                  {
                    v58 = 0;
                    RenderingInfoFromInkStrokeDisp = Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkPoint>::As<Windows::UI::Input::Inking::IInkPointDrawingAttributesHost>(
                                                       &v57,
                                                       &v58);
                    v54 = 0;
                    if ( RenderingInfoFromInkStrokeDisp >= 0 )
                    {
                      v44 = v58;
                      v45 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v58 + 48LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                      RenderingInfoFromInkStrokeDisp = v45(v44, &v54);
                      if ( RenderingInfoFromInkStrokeDisp >= 0 )
                      {
                        v46 = v54;
                        if ( !v54 )
                        {
                          Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::Internal::CInkPointDrawingAttributes,>(&v61);
                          v47 = v61;
                          if ( v61 )
                          {
                            v61 = 0;
                            v62 = v47;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v62);
                            v62 = v54;
                            v54 = v47;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
                          }
                          else
                          {
                            RenderingInfoFromInkStrokeDisp = -2147024882;
                          }
                          v46 = v54;
                        }
                        if ( RenderingInfoFromInkStrokeDisp >= 0 )
                        {
                          RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)v46 + 56LL))(
                                                             v46,
                                                             _mm_unpacklo_ps(
                                                               (__m128)LODWORD(v14[(_QWORD)v66]),
                                                               (__m128)LODWORD(v14[(_QWORD)v65])).m128_u64[0]);
                          if ( RenderingInfoFromInkStrokeDisp >= 0 )
                            RenderingInfoFromInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v58 + 56LL))(
                                                               v58,
                                                               v54);
                        }
                      }
                      v42 = v59;
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
                    v43 = plUbound;
                  }
                }
                (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v42 + 96LL))(v42, SLODWORD(v14[v43 + 6]));
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvData);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
              ++v8;
            }
            while ( v8 < (unsigned int)v56 );
          }
          if ( RenderingInfoFromInkStrokeDisp < 0 )
            goto LABEL_118;
        }
        goto LABEL_113;
      }
LABEL_112:
      free(v14);
      v14 = 0;
LABEL_113:
      v48 = v60;
      v54 = v60;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v54);
      v54 = (void *)*((_QWORD *)v7 + 31);
      *((_QWORD *)v7 + 31) = v48;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      LOBYTE(v49) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SaveStrokeRenderingInfoInISF>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SaveStrokeRenderingInfoInISF>::GetImpl'::`2'::impl,
        v49);
      v61 = 0;
      RenderingInfoFromInkStrokeDisp = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, void **))v69->lpVtbl->put_Width)(
                                         v69,
                                         &v61);
      if ( RenderingInfoFromInkStrokeDisp >= 0 )
      {
        RenderingInfoFromInkStrokeDisp = Windows::UI::Input::Inking::CInkStroke::LoadRenderingInfoFromInkStrokeDisp(
                                           v7,
                                           v6,
                                           *(float *)&v61);
        if ( RenderingInfoFromInkStrokeDisp >= 0 )
        {
          *((_DWORD *)v7 + 30) = _InterlockedIncrement((volatile signed __int32 *)&Windows::UI::Input::Inking::CInkStroke::s_id);
          if ( v70 )
          {
            if ( a5 >= v70 )
            {
              *((_QWORD *)v7 + 17) = 10 * (a5 - v70);
              *((_BYTE *)v7 + 125) = 1;
              *((_QWORD *)v7 + 16) = InkTimestampHelper::GetCurrentDateTime() - *((_QWORD *)v7 + 17);
              *((_BYTE *)v7 + 124) = 1;
            }
          }
        }
      }
      goto LABEL_118;
    }
    v17 = 0;
    v18 = (int)v71[3];
    if ( plUbound > 0 )
    {
      LODWORD(v54) = HIDWORD(v71[2]);
      LODWORD(v62) = v71[2];
      LODWORD(v59) = HIDWORD(v71[1]);
      LODWORD(v56) = v71[1];
      LODWORD(v57) = HIDWORD(v71[0]);
      LODWORD(v58) = v71[0];
      while ( 1 )
      {
        v52 = 0;
        v53 = 0;
        v19 = (const wchar_t *)*((_QWORD *)ppvData + v17);
        if ( !wcscmp_0(v19, L"{7307502D-F9F4-4E18-B3F2-2CE1B1A3610C}") )
        {
          LODWORD(v58) = v17;
          v20 = (char *)v73;
          v21 = (char *)v72;
        }
        else if ( !wcscmp_0(v19, L"{A8D07B3A-8BF0-40B0-95A9-B80A6BB787BF}") )
        {
          LODWORD(v57) = v17;
          v20 = (char *)v73 + 4;
          v21 = (char *)v72 + 4;
        }
        else if ( !wcscmp_0(v19, L"{0E932389-1D77-43AF-AC00-5B950D6D4B2D}") )
        {
          LODWORD(v56) = v17;
          v20 = (char *)v73 + 8;
          v21 = (char *)v72 + 8;
        }
        else if ( !wcscmp_0(v19, L"{0D324960-13B2-41E4-ACE6-7AE9D43D2D3B}") )
        {
          LODWORD(v59) = v17;
          v20 = (char *)v73 + 12;
          v21 = (char *)v72 + 12;
        }
        else if ( !wcscmp_0(v19, L"{FD99FCB8-C345-448C-883C-ED308CBD93EA}") )
        {
          LODWORD(v62) = v17;
          v20 = (char *)&v73[1];
          v21 = (char *)&v72[1];
        }
        else
        {
          if ( wcscmp_0(v19, L"{DD850E16-5297-4F79-92AE-394A6F8994A1}") )
          {
            if ( !wcscmp_0(v19, L"{436510C5-FED3-45D1-8B76-71D3EA7A829D}") )
              v18 = v17;
            goto LABEL_55;
          }
          LODWORD(v54) = v17;
          v20 = (char *)&v73[1] + 4;
          v21 = (char *)&v72[1] + 4;
        }
        ((void (__fastcall *)(struct IInkStrokeDisp *, const wchar_t *, char *, char *, LONG *, int *))v6->lpVtbl->GetPacketDescriptionPropertyMetrics)(
          v6,
          v19,
          v21,
          v20,
          &v53,
          &v52);
LABEL_55:
        if ( ++v17 >= plUbound )
        {
          v29 = (int)v54;
          goto LABEL_58;
        }
      }
    }
    v29 = HIDWORD(v71[2]);
    LODWORD(v62) = v71[2];
    LODWORD(v59) = HIDWORD(v71[1]);
    LODWORD(v56) = v71[1];
    LODWORD(v57) = HIDWORD(v71[0]);
    LODWORD(v58) = v71[0];
LABEL_58:
    SafeArrayUnaccessData(psa[1]);
    memset(v71, 0, 24);
    UBound = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, __int64, SAFEARRAY **))v6->lpVtbl->GetPacketData)(
               v6,
               0,
               0xFFFFFFFFLL,
               v71);
    if ( UBound < 0 )
    {
LABEL_87:
      v8 = 0;
      goto LABEL_88;
    }
    if ( LOWORD(v71[0]) != 8195 )
    {
      UBound = -2147467259;
      goto LABEL_87;
    }
    v53 = 0;
    UBound = SafeArrayGetUBound(v71[1], 1u, &v53);
    v30 = ++v53;
    if ( UBound >= 0 )
    {
      if ( v30 <= 0 )
      {
LABEL_84:
        UBound = -2147467259;
        goto LABEL_85;
      }
      v52 = 0;
      UBound = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, int *))v6->lpVtbl->get_PacketSize)(v6, &v52);
      if ( UBound >= 0 )
      {
        v52 = (unsigned __int64)v52 >> 2;
        v31 = v13 / 7;
        if ( v53 == v31 * v52 )
        {
          v61 = 0;
          UBound = SafeArrayAccessData(v71[1], &v61);
          LODWORD(v54) = UBound;
          if ( UBound >= 0 )
          {
            if ( v31 > 0 )
            {
              v32 = 0;
              v33 = 0;
              v34 = v52;
              v35 = v61;
              v36 = (int)v62;
              v37 = v58;
              v38 = (int)v59;
              do
              {
                v14[v33] = 0.5;
                if ( v37 != -1 )
                  v14[v33] = (float)(v35[v37 + v34 * v32] - LODWORD(v72[0]))
                           / (float)(LODWORD(v73[0]) - LODWORD(v72[0]));
                v14[v33 + 1] = 0.0;
                if ( (_DWORD)v57 != -1 )
                  v14[v33 + 1] = (float)((float)(180 * (v35[(int)v57 + v34 * v32] - DWORD1(v72[0])))
                                       / (float)(DWORD1(v73[0]) - DWORD1(v72[0])))
                               - 90.0;
                v14[v33 + 2] = 0.0;
                if ( (_DWORD)v56 != -1 )
                  v14[v33 + 2] = (float)((float)(180 * (v35[(int)v56 + v34 * v32] - DWORD2(v72[0])))
                                       / (float)(DWORD2(v73[0]) - DWORD2(v72[0])))
                               - 90.0;
                v14[v33 + 3] = 0.0;
                if ( v38 != -1 )
                  v14[v33 + 3] = (float)(v35[v38 + v34 * v32] - HIDWORD(v72[0]))
                               / (float)(HIDWORD(v73[0]) - HIDWORD(v72[0]));
                v14[v33 + 4] = 0.0;
                if ( v36 != -1 )
                  v14[v33 + 4] = (float)(int)v35[v36 + v34 * v32] / 26.0;
                v14[v33 + 5] = 0.0;
                if ( v29 != -1 )
                  v14[v33 + 5] = (float)(int)v35[v29 + v34 * v32] / 26.0;
                v14[v33 + 6] = 0.0;
                if ( v18 != -1 )
                  v14[v33 + 6] = *(float *)&v35[v18 + v34 * v32];
                ++v32;
                v33 += 7;
              }
              while ( v32 < v31 );
              v7 = v65;
              v6 = v66;
              UBound = (int)v54;
            }
            SafeArrayUnaccessData(v71[1]);
          }
          goto LABEL_85;
        }
        goto LABEL_84;
      }
    }
LABEL_85:
    SafeArrayDestroy(v71[1]);
    goto LABEL_87;
  }
LABEL_118:
  free(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)RenderingInfoFromInkStrokeDisp;
}

```

## disassembly

```asm
0x180051aa0  mov     rax, rsp
0x180051aa3  mov     [rax+20h], rbx
0x180051aa7  push    rbp
0x180051aa8  push    rsi
0x180051aa9  push    rdi
0x180051aaa  push    r12
0x180051aac  push    r13
0x180051aae  push    r14
0x180051ab0  push    r15
0x180051ab2  lea     rbp, [rsp-60h]
0x180051ab7  sub     rsp, 160h
0x180051abe  movaps  xmmword ptr [rax-48h], xmm6
0x180051ac2  mov     rax, cs:__security_cookie
0x180051ac9  xor     rax, rsp
0x180051acc  mov     [rbp+90h+var_50], rax
0x180051ad0  mov     [rbp+90h+var_B8], r9
0x180051ad4  mov     rbx, r8
0x180051ad7  mov     [rbp+90h+var_C0], rbx
0x180051adb  mov     r15, rdx
0x180051ade  mov     [rbp+90h+var_E0], rdx
0x180051ae2  mov     rsi, rcx
0x180051ae5  mov     [rbp+90h+var_E8], rcx
0x180051ae9  lea     rdx, [rcx+118h]
0x180051af0  lea     rcx, [rbp+90h+SRWLock]
0x180051af4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180051af9  xor     r13d, r13d
0x180051afc  test    r15, r15
0x180051aff  jnz     short loc_180051B08
0x180051b01  mov     edx, 0C7h
0x180051b06  jmp     short loc_180051B12
0x180051b08  test    rbx, rbx
0x180051b0b  jnz     short loc_180051B44
0x180051b0d  mov     edx, 0C8h; void *
0x180051b12  mov     r9d, 80004003h; char *
0x180051b18  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180051b1f  mov     rcx, [rbp+98h]; this
0x180051b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051b2b  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x180051b2f  test    rcx, rcx
0x180051b32  jz      short loc_180051B3A
0x180051b34  call    cs:__imp_ReleaseSRWLockExclusive
0x180051b3a  mov     eax, 80004003h
0x180051b3f  jmp     loc_1800526DD
0x180051b44  lea     rcx, [rsi+0A0h]
0x180051b4b  mov     rdx, rbx
0x180051b4e  call    ??4?$ComPtr@UIDispatcherQueue@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDispatcherQueue@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(Windows::System::IDispatcherQueue *)
0x180051b53  mov     [rsi+0B9h], r13w
0x180051b5b  mov     [rsi+0BBh], r13b
0x180051b62  mov     [rsi+0C0h], r13
0x180051b69  lea     rcx, [rsi+0E8h]
0x180051b70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051b75  lea     rcx, [rsi+0C8h]
0x180051b7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051b81  mov     qword ptr [rsi+0D0h], 3F800000h
0x180051b8c  mov     [rsi+0D8h], r13d
0x180051b93  mov     qword ptr [rsi+0DCh], 3F800000h
0x180051b9e  mov     [rsi+0E4h], r13d
0x180051ba5  mov     [rsp+190h+var_138], r13d
0x180051baa  mov     rax, [r15]
0x180051bad  lea     rdx, [rsp+190h+var_138]
0x180051bb2  mov     rcx, r15
0x180051bb5  mov     rax, [rax+80h]
0x180051bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bc1  mov     edi, eax
0x180051bc3  movss   xmm6, cs:__real@41d00000
0x180051bcb  test    eax, eax
0x180051bcd  js      loc_180051D21
0x180051bd3  cmp     [rsp+190h+var_138], r13d
0x180051bd8  jnz     loc_180051D21
0x180051bde  mov     edi, 80004005h
0x180051be3  mov     [rbp+90h+var_110], r13
0x180051be7  mov     r12d, r13d
0x180051bea  mov     r14, r13
0x180051bed  test    edi, edi
0x180051bef  js      loc_1800526BA
0x180051bf5  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180051bfd  movups  xmmword ptr [rbp+90h+var_B0], xmm0
0x180051c01  movups  xmmword ptr [rbp+90h+var_B0+0Ch], xmm0
0x180051c05  xorps   xmm0, xmm0
0x180051c08  xor     eax, eax
0x180051c0a  movups  [rbp+90h+var_90], xmm0
0x180051c0e  movups  [rbp+90h+var_90+0Ch], xmm0
0x180051c12  xorps   xmm1, xmm1
0x180051c15  movups  [rbp+90h+var_70], xmm1
0x180051c19  movups  [rbp+90h+var_70+0Ch], xmm1
0x180051c1d  movups  xmmword ptr [rbp+90h+psa], xmm0
0x180051c21  mov     [rbp+90h+var_C8], rax
0x180051c25  mov     rax, [r15]
0x180051c28  lea     rdx, [rbp+90h+psa]
0x180051c2c  mov     rcx, r15
0x180051c2f  mov     rax, [rax+90h]
0x180051c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c3b  test    eax, eax
0x180051c3d  js      loc_1800525E7
0x180051c43  mov     eax, 2008h
0x180051c48  cmp     ax, word ptr [rbp+90h+psa]
0x180051c4c  jnz     loc_1800525E7
0x180051c52  mov     [rsp+190h+plUbound], r13d
0x180051c57  lea     r8, [rsp+190h+plUbound]; plUbound
0x180051c5c  mov     edx, 1; nDim
0x180051c61  mov     rcx, [rbp+90h+psa+8]; psa
0x180051c65  call    cs:__imp_SafeArrayGetUBound
0x180051c6b  mov     ebx, eax
0x180051c6d  mov     eax, [rsp+190h+plUbound]
0x180051c71  inc     eax
0x180051c73  mov     [rsp+190h+plUbound], eax
0x180051c77  test    ebx, ebx
0x180051c79  js      loc_180052344
0x180051c7f  test    eax, eax
0x180051c81  jle     loc_180052344
0x180051c87  mov     [rbp+90h+ppvData], r13
0x180051c8b  lea     rdx, [rbp+90h+ppvData]; ppvData
0x180051c8f  mov     rcx, [rbp+90h+psa+8]; psa
0x180051c93  call    cs:__imp_SafeArrayAccessData
0x180051c99  mov     ebx, eax
0x180051c9b  test    eax, eax
0x180051c9d  js      loc_180052344
0x180051ca3  mov     edi, r13d
0x180051ca6  cmp     [rsp+190h+plUbound], r13d
0x180051cab  mov     r13d, [rbp+90h+var_98]
0x180051caf  jle     loc_180052018
0x180051cb5  mov     eax, dword ptr [rbp+90h+var_A0+4]
0x180051cb8  mov     dword ptr [rsp+190h+var_140], eax
0x180051cbc  mov     eax, dword ptr [rbp+90h+var_A0]
0x180051cbf  mov     dword ptr [rbp+90h+var_100], eax
0x180051cc2  mov     eax, dword ptr [rbp+90h+var_B0+0Ch]
0x180051cc5  mov     dword ptr [rsp+190h+var_118], eax
0x180051cc9  mov     eax, dword ptr [rbp+90h+var_B0+8]
0x180051ccc  mov     dword ptr [rsp+190h+var_130], eax
0x180051cd0  mov     eax, dword ptr [rbp+90h+var_B0+4]
0x180051cd3  mov     dword ptr [rsp+190h+var_128], eax
0x180051cd7  mov     eax, dword ptr [rbp+90h+var_B0]
0x180051cda  mov     dword ptr [rsp+190h+var_120], eax
0x180051cde  mov     [rsp+190h+var_14C], 0
0x180051ce6  mov     [rsp+190h+var_148], 0
0x180051cee  movsxd  rcx, edi
0x180051cf1  mov     rax, [rbp+90h+ppvData]
0x180051cf5  mov     rbx, [rax+rcx*8]
0x180051cf9  lea     rdx, a7307502dF9f44e; "{7307502D-F9F4-4E18-B3F2-2CE1B1A3610C}"
0x180051d00  mov     rcx, rbx; String1
0x180051d03  call    wcscmp_0
0x180051d08  test    eax, eax
0x180051d0a  jnz     loc_180051F21
0x180051d10  mov     dword ptr [rsp+190h+var_120], edi
0x180051d14  lea     r9, [rbp+90h+var_70]
0x180051d18  lea     r8, [rbp+90h+var_90]
0x180051d1c  jmp     loc_180051FC6
0x180051d21  mov     [rbp+90h+var_110], r13
0x180051d25  test    eax, eax
0x180051d27  js      loc_180051EE7
0x180051d2d  lea     rcx, [rbp+90h+var_110]
0x180051d31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051d36  lea     rdx, [rbp+90h+var_110]
0x180051d3a  call    ??$CreateExternalObjectVector@VInkPoint@Inking@Input@UI@Windows@@V?$AgileVector@PEAVInkPoint@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkPoint@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkPoint@Inking@Input@UI@Windows@@@7895@$0A@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVInkPoint@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkPoint@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkPoint@Inking@Input@UI@Windows@@@7895@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkPoint,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkPoint *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkPoint *>,0> * *)
0x180051d3f  mov     edi, eax
0x180051d41  test    eax, eax
0x180051d43  js      loc_180051EE7
0x180051d49  mov     [rsp+190h+plUbound], r13d
0x180051d4e  mov     rax, [r15]
0x180051d51  lea     rdx, [rsp+190h+plUbound]
0x180051d56  mov     rcx, r15
0x180051d59  mov     rax, [rax+88h]
0x180051d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d65  mov     edi, eax
0x180051d67  test    eax, eax
0x180051d69  js      loc_180051EE7
0x180051d6f  mov     [rsp+190h+var_140], r13
0x180051d74  mov     rax, [r15]
0x180051d77  mov     rbx, [rax]
0x180051d7a  lea     rcx, [rsp+190h+var_140]
0x180051d7f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051d84  lea     r8, [rsp+190h+var_140]
0x180051d89  lea     rdx, _GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb
0x180051d90  mov     rcx, r15
0x180051d93  mov     rax, rbx
0x180051d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d9b  mov     edi, eax
0x180051d9d  test    eax, eax
0x180051d9f  js      loc_180051EDD
0x180051da5  xorps   xmm0, xmm0
0x180051da8  xor     eax, eax
0x180051daa  movups  xmmword ptr [rbp+90h+var_B0], xmm0
0x180051dae  mov     [rbp+90h+var_A0], rax
0x180051db2  mov     eax, [rsp+190h+plUbound]
0x180051db6  imul    eax, [rsp+190h+var_138]
0x180051dbb  movsxd  rcx, eax; Size
0x180051dbe  call    cs:__imp_malloc
0x180051dc4  mov     r14, rax
0x180051dc7  test    rax, rax
0x180051dca  jz      loc_180051ED8
0x180051dd0  mov     rcx, [rsp+190h+var_140]
0x180051dd5  mov     rdx, [rcx]
0x180051dd8  mov     rax, [rdx+40h]
0x180051ddc  lea     rdx, [rbp+90h+var_B0]
0x180051de0  mov     [rsp+190h+var_168], rdx
0x180051de5  mov     [rsp+190h+var_170], r14
0x180051dea  mov     r9d, [rsp+190h+plUbound]
0x180051def  mov     r8d, [rsp+190h+var_138]
0x180051df4  xor     edx, edx
0x180051df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051dfb  mov     edi, eax
0x180051dfd  test    eax, eax
0x180051dff  js      loc_180051ECD
0x180051e05  movups  xmm0, xmmword ptr [rbp+90h+var_B0]
0x180051e09  movups  xmmword ptr [rsi+0D0h], xmm0
0x180051e10  movss   xmm0, dword ptr [rbp+90h+var_A0]
0x180051e15  divss   xmm0, xmm6
0x180051e19  movss   dword ptr [rsi+0E0h], xmm0
0x180051e21  movss   xmm1, dword ptr [rbp+90h+var_A0+4]
0x180051e26  divss   xmm1, xmm6
0x180051e2a  movss   dword ptr [rsi+0E4h], xmm1
0x180051e32  mov     r12d, r13d
0x180051e35  cmp     r12d, [rsp+190h+var_138]
0x180051e3a  jge     loc_180051ECD
0x180051e40  lea     rcx, [rsp+190h+var_130]
0x180051e45  call    ??$Make@VCInkPoint@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkPoint@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkPoint,>(void)
0x180051e4a  mov     rbx, [rsp+190h+var_130]
0x180051e4f  test    rbx, rbx
0x180051e52  jz      short loc_180051EB3
0x180051e54  mov     eax, r12d
0x180051e57  imul    eax, [rsp+190h+plUbound]
0x180051e5c  movsxd  rdx, eax
0x180051e5f  shr     rdx, 2
0x180051e63  lea     rcx, [rbx+18h]
0x180051e67  movd    xmm1, dword ptr [r14+rdx*4]
0x180051e6d  cvtdq2ps xmm1, xmm1
0x180051e70  divss   xmm1, xmm6
0x180051e74  movd    xmm0, dword ptr [r14+rdx*4+4]
0x180051e7b  cvtdq2ps xmm0, xmm0
0x180051e7e  divss   xmm0, xmm6
0x180051e82  mov     rax, [rcx]
0x180051e85  unpcklps xmm1, xmm0
0x180051e88  movq    rdx, xmm1
0x180051e8d  mov     rax, [rax+38h]
0x180051e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e96  mov     edi, eax
0x180051e98  test    eax, eax
0x180051e9a  js      short loc_180051EB8
0x180051e9c  mov     rcx, [rbp+90h+var_110]
0x180051ea0  mov     rax, [rcx]
0x180051ea3  mov     rdx, rbx
0x180051ea6  mov     rax, [rax+68h]
0x180051eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eaf  mov     edi, eax
0x180051eb1  jmp     short loc_180051EB8
0x180051eb3  mov     edi, 8007000Eh
0x180051eb8  lea     rcx, [rsp+190h+var_130]
0x180051ebd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051ec2  inc     r12d
0x180051ec5  test    edi, edi
0x180051ec7  jns     loc_180051E35
0x180051ecd  mov     rcx, r14; Block
0x180051ed0  call    cs:__imp_free
0x180051ed6  jmp     short loc_180051EDD
0x180051ed8  mov     edi, 8007000Eh
0x180051edd  lea     rcx, [rsp+190h+var_140]
0x180051ee2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051ee7  mov     r12d, r13d
0x180051eea  test    edi, edi
0x180051eec  js      loc_180051BEA
0x180051ef2  imul    eax, [rsp+190h+var_138], 7
0x180051ef7  movsxd  rcx, eax
0x180051efa  shl     rcx, 2; Size
0x180051efe  call    cs:__imp_malloc
0x180051f04  mov     r14, rax
0x180051f07  test    rax, rax
0x180051f0a  jz      short loc_180051F17
0x180051f0c  imul    r12d, [rsp+190h+var_138], 7
0x180051f12  jmp     loc_180051BED
0x180051f17  mov     edi, 8007000Eh
0x180051f1c  jmp     loc_1800526BA
0x180051f21  lea     rdx, aA8d07b3a8bf040; "{A8D07B3A-8BF0-40B0-95A9-B80A6BB787BF}"
0x180051f28  mov     rcx, rbx; String1
0x180051f2b  call    wcscmp_0
0x180051f30  test    eax, eax
0x180051f32  jnz     short loc_180051F45
0x180051f34  mov     dword ptr [rsp+190h+var_128], edi
0x180051f38  lea     r9, [rbp+90h+var_70+4]
0x180051f3c  lea     r8, [rbp+90h+var_90+4]
0x180051f40  jmp     loc_180051FC6
0x180051f45  lea     rdx, a0e9323891d7743; "{0E932389-1D77-43AF-AC00-5B950D6D4B2D}"
0x180051f4c  mov     rcx, rbx; String1
0x180051f4f  call    wcscmp_0
0x180051f54  test    eax, eax
0x180051f56  jnz     short loc_180051F66
0x180051f58  mov     dword ptr [rsp+190h+var_130], edi
0x180051f5c  lea     r9, [rbp+90h+var_70+8]
0x180051f60  lea     r8, [rbp+90h+var_90+8]
0x180051f64  jmp     short loc_180051FC6
0x180051f66  lea     rdx, a0d32496013b241; "{0D324960-13B2-41E4-ACE6-7AE9D43D2D3B}"
0x180051f6d  mov     rcx, rbx; String1
0x180051f70  call    wcscmp_0
0x180051f75  test    eax, eax
0x180051f77  jnz     short loc_180051F87
0x180051f79  mov     dword ptr [rsp+190h+var_118], edi
0x180051f7d  lea     r9, [rbp+90h+var_70+0Ch]
0x180051f81  lea     r8, [rbp+90h+var_90+0Ch]
0x180051f85  jmp     short loc_180051FC6
0x180051f87  lea     rdx, aFd99fcb8C34544; "{FD99FCB8-C345-448C-883C-ED308CBD93EA}"
0x180051f8e  mov     rcx, rbx; String1
  ... truncated ...
```
