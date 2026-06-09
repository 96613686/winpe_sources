# CreateCodecPackComponent(_GUID const &,bool,ushort const *,COMLESS_WINRT_DLL_DATA *,_GUID const &,void * *)

- ea: `0x18009c21c`
- end: `0x18009c8e5`
- name: `?CreateCodecPackComponent@@YAJAEBU_GUID@@_NPEBGPEAUCOMLESS_WINRT_DLL_DATA@@0PEAPEAX@Z`
- size: `1737`
- prototype: `__int64 __fastcall(const struct _GUID *, char, const unsigned __int16 *, struct COMLESS_WINRT_DLL_DATA *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c180`
- `0x1800c1c18`

## callees

- `0x180014ccc`
- `0x180098f08`
- `0x18009c21c`
- `0x1800b6eec`
- `0x1800bb784`
- `0x1800d02ac`
- `0x1800e2f90`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c8a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c8a2`
- `MFPlat!MFTEnumEx` at `0x18009c34d`
- `MFPlat!MFTEnumEx` at `0x18009c34d`
- `MFPlat!MFCreateTelemetrySession` at `0x18009c2d7`
- `MFPlat!MFCreateTelemetrySession` at `0x18009c2d7`
- `MFPlat!MFCreateWICDecoderProxy` at `0x18009c42f`
- `MFPlat!MFCreateWICDecoderProxy` at `0x18009c42f`
- `MFPlat!MFStartup` at `0x18009c291`
- `MFPlat!MFStartup` at `0x18009c291`
- `MFPlat!MFShutdown` at `0x18009c8ad`
- `MFPlat!MFShutdown` at `0x18009c8ad`

## pseudocode

```c
__int64 __fastcall CreateCodecPackComponent(
        const struct _GUID *a1,
        char a2,
        const unsigned __int16 *a3,
        struct COMLESS_WINRT_DLL_DATA *a4,
        const struct _GUID *a5,
        void **a6)
{
  GUID v8; // xmm0
  bool v11; // r14
  HRESULT v12; // eax
  int v13; // ebx
  char v14; // r15
  HRESULT v15; // eax
  const MFT_REGISTER_TYPE_INFO *v16; // r9
  GUID v17; // xmm0
  __int64 v18; // r14
  IMFActivate **v19; // rcx
  IMFActivate *v20; // rbx
  IMFActivate *v21; // rcx
  bool v22; // sf
  int v23; // eax
  bool v24; // zf
  HRESULT (__stdcall *SetUnknown)(IMFActivate *, const GUID *const, IUnknown *); // rax
  int v26; // edi
  __int64 v27; // r14
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // ecx
  int v38; // r9d
  int v39; // r10d
  void *v40; // rdx
  struct IInspectable **v41; // rax
  int v42; // r10d
  __int64 i; // rdi
  struct IInspectable **v45; // [rsp+48h] [rbp-91h]
  bool v46; // [rsp+50h] [rbp-89h] BYREF
  char v47; // [rsp+51h] [rbp-88h]
  char v48[6]; // [rsp+52h] [rbp-87h] BYREF
  struct IInspectable *v49; // [rsp+58h] [rbp-81h] BYREF
  UINT32 pnumMFTActivate; // [rsp+60h] [rbp-79h] BYREF
  __int64 v51; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v52[2]; // [rsp+70h] [rbp-69h] BYREF
  GUID v53; // [rsp+80h] [rbp-59h] BYREF
  IMFActivate **pppMFTActivate; // [rsp+90h] [rbp-49h] BYREF
  _QWORD v55[3]; // [rsp+98h] [rbp-41h] BYREF
  GUID guidCategory; // [rsp+B0h] [rbp-29h] BYREF
  _OWORD v57[2]; // [rsp+C0h] [rbp-19h] BYREF

  v57[0] = MFMediaType_Video;
  v55[0] = a5;
  v8 = *a1;
  pnumMFTActivate = 0;
  pppMFTActivate = 0;
  v57[1] = v8;
  v52[0] = 0;
  v48[0] = 0;
  v11 = 0;
  *a6 = 0;
  v12 = MFStartup(0x20070u, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v12);
    v14 = 0;
    goto LABEL_57;
  }
  v47 = 1;
  guidCategory = GUID_NULL;
  v53 = GUID_NULL;
  v15 = MFCreateTelemetrySession(&v53, &guidCategory, v52);
  v13 = v15;
  if ( v15 < 0
    || ((v16 = (const MFT_REGISTER_TYPE_INFO *)v57, !a2)
      ? (v17 = MFT_CATEGORY_VIDEO_ENCODER)
      : (v16 = 0, v17 = MFT_CATEGORY_VIDEO_DECODER),
        guidCategory = v17,
        v15 = MFTEnumEx(
                &guidCategory,
                0x441u,
                (const MFT_REGISTER_TYPE_INFO *)((unsigned __int64)v57 & -(__int64)(a2 != 0)),
                v16,
                &pppMFTActivate,
                &pnumMFTActivate),
        v13 = v15,
        v15 < 0) )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v15);
    goto LABEL_56;
  }
  v48[0] = 1;
  v46 = pnumMFTActivate != 0;
  v18 = 0;
  if ( !pnumMFTActivate )
  {
    v27 = v55[0];
LABEL_42:
    if ( a3 && a4 )
    {
      v49 = 0;
      v30 = ComlessActivateInstance(a3, a4, &v49);
      v13 = v30;
      if ( v30 >= 0 )
      {
        *(_QWORD *)&v53.Data1 = 0;
        v31 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, GUID *))v49->lpVtbl->QueryInterface)(
                v49,
                &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803,
                &v53);
        v13 = v31;
        if ( v31 < 0
          || ((*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v53.Data1 + 32LL))(*(_QWORD *)&v53.Data1, v52[0]),
              v31 = ((__int64 (__fastcall *)(struct IInspectable *, __int64, void **))v49->lpVtbl->QueryInterface)(
                      v49,
                      v27,
                      a6),
              v13 = v31,
              v31 < 0) )
        {
          if ( (_DWORD)g_doStackCaptures )
            DoStackCapture(v31);
        }
        wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v53);
      }
      else if ( (_DWORD)g_doStackCaptures )
      {
        DoStackCapture(v30);
      }
      wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
    }
    else
    {
      v13 = -2003292336;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2003292336);
    }
    goto LABEL_55;
  }
  while ( 1 )
  {
    v19 = pppMFTActivate;
    v20 = pppMFTActivate[v18];
    *(_QWORD *)&v53.Data1 = v20;
    if ( v20 )
    {
      ((void (__fastcall *)(IMFActivate *))v20->lpVtbl->AddRef)(v20);
      v19 = pppMFTActivate;
    }
    v21 = v19[v18];
    LODWORD(v51) = 0;
    v22 = ((int (__fastcall *)(IMFActivate *, __int64 *, __int64 *))v21->lpVtbl->GetUINT32)(
            v21,
            MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED,
            &v51) < 0;
    v23 = 0;
    if ( !v22 )
      v23 = v51;
    v24 = v23 == 0;
    v49 = 0;
    SetUnknown = v20->lpVtbl->SetUnknown;
    if ( v24 )
      break;
    ((void (__fastcall *)(IMFActivate *, __int64 *, _QWORD))SetUnknown)(
      v20,
      MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
      v52[0]);
    v26 = ((__int64 (__fastcall *)(IMFActivate *, GUID *, struct IInspectable **))v20->lpVtbl->ActivateObject)(
            v20,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            &v49);
    if ( v26 >= 0 )
    {
      v51 = 0;
      v28 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v49->lpVtbl->QueryInterface)(
              v49,
              &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803,
              &v51);
      v13 = v28;
      if ( v28 < 0
        || ((*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 32LL))(v51, v52[0]),
            v27 = v55[0],
            v28 = ((__int64 (__fastcall *)(struct IInspectable *, _QWORD, void **))v49->lpVtbl->QueryInterface)(
                    v49,
                    v55[0],
                    a6),
            v13 = v28,
            v28 < 0) )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v28);
        wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v51);
        wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
LABEL_32:
        wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v53);
        goto LABEL_55;
      }
      wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v51);
      wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
      goto LABEL_35;
    }
LABEL_21:
    wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
    wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v53);
    v18 = (unsigned int)(v18 + 1);
    if ( (unsigned int)v18 >= pnumMFTActivate )
    {
      v27 = v55[0];
      goto LABEL_23;
    }
  }
  ((void (__fastcall *)(IMFActivate *, __int64 *, _QWORD))SetUnknown)(
    v20,
    MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
    v52[0]);
  guidCategory = *a1;
  v26 = MFCreateWICDecoderProxy(&guidCategory, v20, &v49);
  if ( v26 < 0 )
    goto LABEL_21;
  v27 = v55[0];
  v29 = ((__int64 (__fastcall *)(struct IInspectable *, _QWORD, void **))v49->lpVtbl->QueryInterface)(v49, v55[0], a6);
  v13 = v29;
  if ( v29 < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v29);
    wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
    goto LABEL_32;
  }
  wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v49);
LABEL_35:
  wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v53);
LABEL_23:
  if ( !pnumMFTActivate )
    goto LABEL_42;
  if ( v26 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v26);
  v13 = v26;
LABEL_55:
  v11 = v46;
LABEL_56:
  v14 = v47;
LABEL_57:
  v32 = *(_QWORD *)&CLSID_WICRAWDecoder.Data1;
  v33 = *(_QWORD *)CLSID_WICJpegXLDecoder.Data4;
  v34 = *(_QWORD *)&CLSID_WICJpegXLDecoder.Data1;
  v35 = *(_QWORD *)CLSID_WICRAWDecoder.Data4;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&CLSID_WICRAWDecoder.Data1
    && *(_QWORD *)a1->Data4 == *(_QWORD *)CLSID_WICRAWDecoder.Data4
    || *(_QWORD *)&a1->Data1 == *(_QWORD *)&CLSID_WICJpegXLDecoder.Data1
    && *(_QWORD *)a1->Data4 == *(_QWORD *)CLSID_WICJpegXLDecoder.Data4 )
  {
    v36 = v52[0];
    if ( v52[0] )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64 *, _QWORD))(*(_QWORD *)v52[0] + 320LL))(
              v52[0],
              MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT,
              *(_QWORD *)&CLSID_WICJpegXLDecoder.Data1) )
      {
        v36 = v52[0];
        v35 = *(_QWORD *)CLSID_WICRAWDecoder.Data4;
        v32 = *(_QWORD *)&CLSID_WICRAWDecoder.Data1;
        v33 = *(_QWORD *)CLSID_WICJpegXLDecoder.Data4;
        v34 = *(_QWORD *)&CLSID_WICJpegXLDecoder.Data1;
        goto LABEL_64;
      }
    }
    else
    {
LABEL_64:
      if ( !v11 || v13 < 0 )
      {
        guidCategory = GUID_NULL;
        if ( v36 )
        {
          guidCategory = *(GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v36 + 280LL))(
                                    v36,
                                    v55,
                                    v34);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v52[0] + 296LL))(v52[0]);
          v32 = *(_QWORD *)&CLSID_WICRAWDecoder.Data1;
          v35 = *(_QWORD *)CLSID_WICRAWDecoder.Data4;
          v33 = *(_QWORD *)CLSID_WICJpegXLDecoder.Data4;
          v34 = *(_QWORD *)&CLSID_WICJpegXLDecoder.Data1;
        }
        if ( *(_QWORD *)&a1->Data1 == v32 && *(_QWORD *)a1->Data4 == v35 )
        {
          if ( (unsigned int)dword_180264F40 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180264F40, 0x400000000001LL) )
            goto LABEL_79;
          v40 = &unk_1802503C0;
          v55[0] = &guidCategory;
          v45 = (struct IInspectable **)&v51;
          v41 = &v49;
          LODWORD(v51) = v13;
          LODWORD(v49) = v39;
        }
        else
        {
          if ( *(_QWORD *)&a1->Data1 != v34
            || *(_QWORD *)a1->Data4 != v33
            || (unsigned int)dword_180264F08 <= 5
            || !(unsigned __int8)tlgKeywordOn(&dword_180264F08, 0x400000000001LL) )
          {
            goto LABEL_79;
          }
          v40 = &unk_180250318;
          v55[0] = &guidCategory;
          v45 = &v49;
          v41 = (struct IInspectable **)&v51;
          LODWORD(v49) = v13;
          LODWORD(v51) = v42;
        }
        v46 = v11;
        *(_QWORD *)&v53.Data1 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v37,
          (_DWORD)v40,
          v34,
          v38,
          (__int64)&v53,
          (__int64)v55,
          (__int64)v41,
          (__int64)&v46,
          (__int64)v48,
          (__int64)v45);
      }
    }
  }
LABEL_79:
  for ( i = 0; (unsigned int)i < pnumMFTActivate; i = (unsigned int)(i + 1) )
    ((void (__fastcall *)(IMFActivate *, __int64, __int64))pppMFTActivate[i]->lpVtbl->Release)(
      pppMFTActivate[i],
      v33,
      v34);
  CoTaskMemFree(pppMFTActivate);
  if ( v14 )
    MFShutdown();
  wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(v52);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009c21c  mov     [rsp-8+arg_8], rbx
0x18009c221  push    rbp
0x18009c222  push    rsi
0x18009c223  push    rdi
0x18009c224  push    r12
0x18009c226  push    r13
0x18009c228  push    r14
0x18009c22a  push    r15
0x18009c22c  lea     rbp, [rsp-17h]
0x18009c231  sub     rsp, 0F0h
0x18009c238  mov     rax, cs:__security_cookie
0x18009c23f  xor     rax, rsp
0x18009c242  mov     [rbp+47h+var_40], rax
0x18009c246  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x18009c24d  mov     rax, [rbp+47h+arg_20]
0x18009c251  mov     dil, dl
0x18009c254  mov     r13, [rbp+47h+arg_28]
0x18009c258  mov     rsi, rcx
0x18009c25b  movdqu  [rbp+47h+var_60], xmm0
0x18009c260  mov     [rbp+47h+var_88], rax
0x18009c264  xor     eax, eax
0x18009c266  movups  xmm0, xmmword ptr [rcx]
0x18009c269  xor     edx, edx; dwFlags
0x18009c26b  mov     [rbp+47h+var_C0], eax
0x18009c26e  mov     ecx, 20070h; Version
0x18009c273  mov     [rbp+47h+var_90], rax
0x18009c277  movdqu  [rbp+47h+var_50], xmm0
0x18009c27c  mov     r12, r9
0x18009c27f  mov     [rbp+47h+var_B0], rax
0x18009c283  mov     r15, r8
0x18009c286  mov     [rsp+120h+var_CE], al
0x18009c28a  mov     r14b, al
0x18009c28d  mov     [r13+0], rax
0x18009c291  call    cs:__imp_MFStartup
0x18009c297  mov     ebx, eax
0x18009c299  test    eax, eax
0x18009c29b  jns     short loc_18009C2B5
0x18009c29d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c2a4  jz      short loc_18009C2AD
0x18009c2a6  mov     ecx, eax; int
0x18009c2a8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c2ad  xor     r15b, r15b
0x18009c2b0  jmp     loc_18009C66C
0x18009c2b5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009c2bc  lea     r8, [rbp+47h+var_B0]
0x18009c2c0  mov     [rsp+120h+var_CF], 1
0x18009c2c5  lea     rdx, [rbp+47h+guidCategory]
0x18009c2c9  lea     rcx, [rbp+47h+var_A0]
0x18009c2cd  movdqu  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009c2d2  movdqu  [rbp+47h+var_A0], xmm0
0x18009c2d7  call    cs:__imp_MFCreateTelemetrySession
0x18009c2dd  mov     ebx, eax
0x18009c2df  test    eax, eax
0x18009c2e1  jns     short loc_18009C2FC
0x18009c2e3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c2ea  jz      loc_18009C667
0x18009c2f0  mov     ecx, eax; int
0x18009c2f2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c2f7  jmp     loc_18009C667
0x18009c2fc  xor     eax, eax
0x18009c2fe  lea     r9, [rbp+47h+var_60]
0x18009c302  test    dil, dil
0x18009c305  cmovnz  r9, rax; pOutputType
0x18009c309  mov     al, dil
0x18009c30c  neg     al
0x18009c30e  lea     rax, [rbp+47h+var_60]
0x18009c312  sbb     r8, r8
0x18009c315  and     r8, rax; pInputType
0x18009c318  test    dil, dil
0x18009c31b  jz      short loc_18009C326
0x18009c31d  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x18009c324  jmp     short loc_18009C32D
0x18009c326  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x18009c32d  lea     rax, [rbp+47h+var_C0]
0x18009c331  movdqa  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009c336  mov     [rsp+120h+pnumMFTActivate], rax; pnumMFTActivate
0x18009c33b  lea     rcx, [rbp+47h+guidCategory]; guidCategory
0x18009c33f  lea     rax, [rbp+47h+var_90]
0x18009c343  mov     edx, 441h; Flags
0x18009c348  mov     [rsp+120h+pppMFTActivate], rax; pppMFTActivate
0x18009c34d  call    cs:__imp_MFTEnumEx
0x18009c353  mov     ebx, eax
0x18009c355  test    eax, eax
0x18009c357  js      short loc_18009C2E3
0x18009c359  mov     eax, [rbp+47h+var_C0]
0x18009c35c  test    eax, eax
0x18009c35e  mov     [rsp+120h+var_CE], 1
0x18009c363  setnz   [rsp+120h+var_D0]
0x18009c368  xor     r14d, r14d
0x18009c36b  test    eax, eax
0x18009c36d  jz      loc_18009C582
0x18009c373  mov     rcx, [rbp+47h+var_90]
0x18009c377  mov     rbx, [rcx+r14*8]
0x18009c37b  mov     qword ptr [rbp+47h+var_A0], rbx
0x18009c37f  test    rbx, rbx
0x18009c382  jz      short loc_18009C397
0x18009c384  mov     rax, [rbx]
0x18009c387  mov     rcx, rbx
0x18009c38a  mov     rax, [rax+8]
0x18009c38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c393  mov     rcx, [rbp+47h+var_90]
0x18009c397  mov     rcx, [rcx+r14*8]
0x18009c39b  lea     r8, [rbp+47h+var_B8]
0x18009c39f  xor     edi, edi
0x18009c3a1  lea     rdx, MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED
0x18009c3a8  mov     dword ptr [rbp+47h+var_B8], edi
0x18009c3ab  mov     rax, [rcx]
0x18009c3ae  mov     rax, [rax+38h]
0x18009c3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c3b7  test    eax, eax
0x18009c3b9  mov     eax, edi
0x18009c3bb  js      short loc_18009C3C0
0x18009c3bd  mov     eax, dword ptr [rbp+47h+var_B8]
0x18009c3c0  mov     r8, [rbp+47h+var_B0]
0x18009c3c4  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x18009c3cb  test    eax, eax
0x18009c3cd  mov     [rsp+120h+var_C8], rdi
0x18009c3d2  mov     rax, [rbx]
0x18009c3d5  mov     rcx, rbx
0x18009c3d8  mov     rax, [rax+0D8h]
0x18009c3df  jz      short loc_18009C416
0x18009c3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c3e6  mov     rax, [rbx]
0x18009c3e9  lea     r8, [rsp+120h+var_C8]
0x18009c3ee  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18009c3f5  mov     rcx, rbx
0x18009c3f8  mov     rax, [rax+108h]
0x18009c3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c404  mov     edi, eax
0x18009c406  test    eax, eax
0x18009c408  jns     short loc_18009C488
0x18009c40a  lea     rcx, [rsp+120h+var_C8]
0x18009c40f  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c414  jmp     short loc_18009C449
0x18009c416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c41b  movups  xmm0, xmmword ptr [rsi]
0x18009c41e  lea     r8, [rsp+120h+var_C8]
0x18009c423  mov     rdx, rbx
0x18009c426  lea     rcx, [rbp+47h+guidCategory]
0x18009c42a  movdqu  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009c42f  call    cs:__imp_MFCreateWICDecoderProxy
0x18009c435  mov     edi, eax
0x18009c437  test    eax, eax
0x18009c439  jns     loc_18009C537
0x18009c43f  lea     rcx, [rsp+120h+var_C8]
0x18009c444  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c449  lea     rcx, [rbp+47h+var_A0]
0x18009c44d  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c452  inc     r14d
0x18009c455  cmp     r14d, [rbp+47h+var_C0]
0x18009c459  jb      loc_18009C373
0x18009c45f  mov     r14, [rbp+47h+var_88]
0x18009c463  cmp     [rbp+47h+var_C0], 0
0x18009c467  jbe     loc_18009C586
0x18009c46d  test    edi, edi
0x18009c46f  jns     short loc_18009C481
0x18009c471  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c478  jz      short loc_18009C481
0x18009c47a  mov     ecx, edi; int
0x18009c47c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c481  mov     ebx, edi
0x18009c483  jmp     loc_18009C662
0x18009c488  mov     rcx, [rsp+120h+var_C8]
0x18009c48d  lea     r8, [rbp+47h+var_B8]
0x18009c491  mov     [rbp+47h+var_B8], 0
0x18009c499  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x18009c4a0  mov     rax, [rcx]
0x18009c4a3  mov     rax, [rax]
0x18009c4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c4ab  mov     ebx, eax
0x18009c4ad  test    eax, eax
0x18009c4af  jns     short loc_18009C4E2
0x18009c4b1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c4b8  jz      short loc_18009C4C1
0x18009c4ba  mov     ecx, eax; int
0x18009c4bc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c4c1  lea     rcx, [rbp+47h+var_B8]
0x18009c4c5  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c4ca  lea     rcx, [rsp+120h+var_C8]
0x18009c4cf  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c4d4  lea     rcx, [rbp+47h+var_A0]
0x18009c4d8  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c4dd  jmp     loc_18009C662
0x18009c4e2  mov     rcx, [rbp+47h+var_B8]
0x18009c4e6  mov     rdx, [rbp+47h+var_B0]
0x18009c4ea  mov     rax, [rcx]
0x18009c4ed  mov     rax, [rax+20h]
0x18009c4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c4f6  mov     rcx, [rsp+120h+var_C8]
0x18009c4fb  mov     r8, r13
0x18009c4fe  mov     r14, [rbp+47h+var_88]
0x18009c502  mov     rdx, r14
0x18009c505  mov     rax, [rcx]
0x18009c508  mov     rax, [rax]
0x18009c50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c510  mov     ebx, eax
0x18009c512  test    eax, eax
0x18009c514  js      short loc_18009C4B1
0x18009c516  lea     rcx, [rbp+47h+var_B8]
0x18009c51a  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c51f  lea     rcx, [rsp+120h+var_C8]
0x18009c524  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c529  lea     rcx, [rbp+47h+var_A0]
0x18009c52d  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c532  jmp     loc_18009C463
0x18009c537  mov     rcx, [rsp+120h+var_C8]
0x18009c53c  mov     r8, r13
0x18009c53f  mov     r14, [rbp+47h+var_88]
0x18009c543  mov     rdx, r14
0x18009c546  mov     rax, [rcx]
0x18009c549  mov     rax, [rax]
0x18009c54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c551  mov     ebx, eax
0x18009c553  test    eax, eax
0x18009c555  jns     short loc_18009C576
0x18009c557  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c55e  jz      short loc_18009C567
0x18009c560  mov     ecx, eax; int
0x18009c562  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c567  lea     rcx, [rsp+120h+var_C8]
0x18009c56c  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c571  jmp     loc_18009C4D4
0x18009c576  lea     rcx, [rsp+120h+var_C8]
0x18009c57b  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c580  jmp     short loc_18009C529
0x18009c582  mov     r14, [rbp+47h+var_88]
0x18009c586  test    r15, r15
0x18009c589  jz      loc_18009C64D
0x18009c58f  test    r12, r12
0x18009c592  jz      loc_18009C64D
0x18009c598  lea     r8, [rsp+120h+var_C8]; struct IInspectable **
0x18009c59d  mov     [rsp+120h+var_C8], 0
0x18009c5a6  mov     rdx, r12; struct COMLESS_WINRT_DLL_DATA *
0x18009c5a9  mov     rcx, r15; unsigned __int16 *
0x18009c5ac  call    ?ComlessActivateInstance@@YAJPEBGAEAUCOMLESS_WINRT_DLL_DATA@@PEAPEAUIInspectable@@@Z; ComlessActivateInstance(ushort const *,COMLESS_WINRT_DLL_DATA &,IInspectable * *)
0x18009c5b1  mov     ebx, eax
0x18009c5b3  test    eax, eax
0x18009c5b5  jns     short loc_18009C5D6
0x18009c5b7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c5be  jz      short loc_18009C5C7
0x18009c5c0  mov     ecx, eax; int
0x18009c5c2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c5c7  lea     rcx, [rsp+120h+var_C8]
0x18009c5cc  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c5d1  jmp     loc_18009C662
0x18009c5d6  mov     rcx, [rsp+120h+var_C8]
0x18009c5db  lea     r8, [rbp+47h+var_A0]
0x18009c5df  mov     qword ptr [rbp+47h+var_A0], 0
0x18009c5e7  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x18009c5ee  mov     rax, [rcx]
0x18009c5f1  mov     rax, [rax]
0x18009c5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c5f9  mov     ebx, eax
0x18009c5fb  test    eax, eax
0x18009c5fd  js      short loc_18009C62F
0x18009c5ff  mov     rcx, qword ptr [rbp+47h+var_A0]
0x18009c603  mov     rdx, [rbp+47h+var_B0]
0x18009c607  mov     rax, [rcx]
0x18009c60a  mov     rax, [rax+20h]
0x18009c60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c613  mov     rcx, [rsp+120h+var_C8]
0x18009c618  mov     r8, r13
0x18009c61b  mov     rdx, r14
0x18009c61e  mov     rax, [rcx]
0x18009c621  mov     rax, [rax]
0x18009c624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c629  mov     ebx, eax
0x18009c62b  test    eax, eax
0x18009c62d  jns     short loc_18009C63F
0x18009c62f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c636  jz      short loc_18009C63F
0x18009c638  mov     ecx, eax; int
0x18009c63a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c63f  lea     rcx, [rbp+47h+var_A0]
0x18009c643  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009c648  jmp     loc_18009C5C7
0x18009c64d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009c654  mov     ebx, 88982F50h
0x18009c659  jz      short loc_18009C662
0x18009c65b  mov     ecx, ebx; int
0x18009c65d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009c662  mov     r14b, [rsp+120h+var_D0]
0x18009c667  mov     r15b, [rsp+120h+var_CF]
0x18009c66c  mov     r9, qword ptr cs:CLSID_WICRAWDecoder.Data1
0x18009c673  mov     rdx, qword ptr cs:CLSID_WICJpegXLDecoder.Data4
0x18009c67a  mov     r8, qword ptr cs:CLSID_WICJpegXLDecoder.Data1
0x18009c681  mov     rax, qword ptr cs:CLSID_WICRAWDecoder.Data4
0x18009c688  cmp     [rsi], r9
0x18009c68b  jnz     short loc_18009C693
0x18009c68d  cmp     [rsi+8], rax
0x18009c691  jz      short loc_18009C6A6
0x18009c693  cmp     [rsi], r8
0x18009c696  jnz     loc_18009C87C
0x18009c69c  cmp     [rsi+8], rdx
0x18009c6a0  jnz     loc_18009C87C
0x18009c6a6  mov     rcx, [rbp+47h+var_B0]
0x18009c6aa  test    rcx, rcx
0x18009c6ad  jz      short loc_18009C6ED
0x18009c6af  mov     rax, [rcx]
0x18009c6b2  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
  ... truncated ...
```
