# CreateCodecPackComponent(_GUID const &,bool,ushort const *,COMLESS_WINRT_DLL_DATA *,_GUID const &,void * *)

- ea: `0x18009d760`
- end: `0x18009de52`
- name: `?CreateCodecPackComponent@@YAJAEBU_GUID@@_NPEBGPEAUCOMLESS_WINRT_DLL_DATA@@0PEAPEAX@Z`
- size: `1778`
- prototype: `int(const struct _GUID *, bool, const unsigned __int16 *, struct COMLESS_WINRT_DLL_DATA *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009d6c4`
- `0x1800c3f3c`

## callees

- `0x180014ccc`
- `0x18009a95c`
- `0x18009d760`
- `0x1800b9150`
- `0x1800bd9d4`
- `0x1800d2b8c`
- `0x1800e5e60`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009de02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009de02`
- `MFPlat!MFTEnumEx` at `0x18009d89d`
- `MFPlat!MFTEnumEx` at `0x18009d89d`
- `MFPlat!MFCreateTelemetrySession` at `0x18009d821`
- `MFPlat!MFCreateTelemetrySession` at `0x18009d821`
- `MFPlat!MFCreateWICDecoderProxy` at `0x18009d989`
- `MFPlat!MFCreateWICDecoderProxy` at `0x18009d989`
- `MFPlat!MFStartup` at `0x18009d7d5`
- `MFPlat!MFStartup` at `0x18009d7d5`
- `MFPlat!MFShutdown` at `0x18009de13`
- `MFPlat!MFShutdown` at `0x18009de13`

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
    v22 = ((int (__fastcall *)(IMFActivate *, void *, __int64 *))v21->lpVtbl->GetUINT32)(
            v21,
            &MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED,
            &v51) < 0;
    v23 = 0;
    if ( !v22 )
      v23 = v51;
    v24 = v23 == 0;
    v49 = 0;
    SetUnknown = v20->lpVtbl->SetUnknown;
    if ( v24 )
      break;
    ((void (__fastcall *)(IMFActivate *, void *, _QWORD))SetUnknown)(
      v20,
      &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
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
  ((void (__fastcall *)(IMFActivate *, void *, _QWORD))SetUnknown)(v20, &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE, v52[0]);
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
      if ( !(*(unsigned int (__fastcall **)(_QWORD, void *, _QWORD))(*(_QWORD *)v52[0] + 320LL))(
              v52[0],
              &MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT,
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
          if ( (unsigned int)dword_180268F40 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180268F40, 0x400000000001LL) )
            goto LABEL_79;
          v40 = &unk_1802542C0;
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
            || (unsigned int)dword_180268F08 <= 5
            || !(unsigned __int8)tlgKeywordOn(&dword_180268F08, 0x400000000001LL) )
          {
            goto LABEL_79;
          }
          v40 = &unk_180254218;
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
0x18009d760  mov     [rsp-8+arg_8], rbx
0x18009d765  push    rbp
0x18009d766  push    rsi
0x18009d767  push    rdi
0x18009d768  push    r12
0x18009d76a  push    r13
0x18009d76c  push    r14
0x18009d76e  push    r15
0x18009d770  lea     rbp, [rsp-17h]
0x18009d775  sub     rsp, 0F0h
0x18009d77c  mov     rax, cs:__security_cookie
0x18009d783  xor     rax, rsp
0x18009d786  mov     [rbp+47h+var_40], rax
0x18009d78a  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x18009d791  mov     rax, [rbp+47h+arg_20]
0x18009d795  mov     dil, dl
0x18009d798  mov     r13, [rbp+47h+arg_28]
0x18009d79c  mov     rsi, rcx
0x18009d79f  movdqu  [rbp+47h+var_60], xmm0
0x18009d7a4  mov     [rbp+47h+var_88], rax
0x18009d7a8  xor     eax, eax
0x18009d7aa  movups  xmm0, xmmword ptr [rcx]
0x18009d7ad  xor     edx, edx; dwFlags
0x18009d7af  mov     [rbp+47h+var_C0], eax
0x18009d7b2  mov     ecx, 20070h; Version
0x18009d7b7  mov     [rbp+47h+var_90], rax
0x18009d7bb  movdqu  [rbp+47h+var_50], xmm0
0x18009d7c0  mov     r12, r9
0x18009d7c3  mov     [rbp+47h+var_B0], rax
0x18009d7c7  mov     r15, r8
0x18009d7ca  mov     [rsp+120h+var_CE], al
0x18009d7ce  mov     r14b, al
0x18009d7d1  mov     [r13+0], rax
0x18009d7d5  call    cs:__imp_MFStartup
0x18009d7dc  nop     dword ptr [rax+rax+00h]
0x18009d7e1  mov     ebx, eax
0x18009d7e3  test    eax, eax
0x18009d7e5  jns     short loc_18009D7FF
0x18009d7e7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009d7ee  jz      short loc_18009D7F7
0x18009d7f0  mov     ecx, eax; int
0x18009d7f2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009d7f7  xor     r15b, r15b
0x18009d7fa  jmp     loc_18009DBCC
0x18009d7ff  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009d806  lea     r8, [rbp+47h+var_B0]
0x18009d80a  mov     [rsp+120h+var_CF], 1
0x18009d80f  lea     rdx, [rbp+47h+guidCategory]
0x18009d813  lea     rcx, [rbp+47h+var_A0]
0x18009d817  movdqu  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009d81c  movdqu  [rbp+47h+var_A0], xmm0
0x18009d821  call    cs:__imp_MFCreateTelemetrySession
0x18009d828  nop     dword ptr [rax+rax+00h]
0x18009d82d  mov     ebx, eax
0x18009d82f  test    eax, eax
0x18009d831  jns     short loc_18009D84C
0x18009d833  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009d83a  jz      loc_18009DBC7
0x18009d840  mov     ecx, eax; int
0x18009d842  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009d847  jmp     loc_18009DBC7
0x18009d84c  xor     eax, eax
0x18009d84e  lea     r9, [rbp+47h+var_60]
0x18009d852  test    dil, dil
0x18009d855  cmovnz  r9, rax; pOutputType
0x18009d859  mov     al, dil
0x18009d85c  neg     al
0x18009d85e  lea     rax, [rbp+47h+var_60]
0x18009d862  sbb     r8, r8
0x18009d865  and     r8, rax; pInputType
0x18009d868  test    dil, dil
0x18009d86b  jz      short loc_18009D876
0x18009d86d  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x18009d874  jmp     short loc_18009D87D
0x18009d876  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x18009d87d  lea     rax, [rbp+47h+var_C0]
0x18009d881  movdqa  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009d886  mov     [rsp+120h+pnumMFTActivate], rax; pnumMFTActivate
0x18009d88b  lea     rcx, [rbp+47h+guidCategory]; guidCategory
0x18009d88f  lea     rax, [rbp+47h+var_90]
0x18009d893  mov     edx, 441h; Flags
0x18009d898  mov     [rsp+120h+pppMFTActivate], rax; pppMFTActivate
0x18009d89d  call    cs:__imp_MFTEnumEx
0x18009d8a4  nop     dword ptr [rax+rax+00h]
0x18009d8a9  mov     ebx, eax
0x18009d8ab  test    eax, eax
0x18009d8ad  js      short loc_18009D833
0x18009d8af  mov     eax, [rbp+47h+var_C0]
0x18009d8b2  test    eax, eax
0x18009d8b4  mov     [rsp+120h+var_CE], 1
0x18009d8b9  setnz   [rsp+120h+var_D0]
0x18009d8be  xor     r14d, r14d
0x18009d8c1  test    eax, eax
0x18009d8c3  jz      loc_18009DAE2
0x18009d8c9  mov     rcx, [rbp+47h+var_90]
0x18009d8cd  mov     rbx, [rcx+r14*8]
0x18009d8d1  mov     qword ptr [rbp+47h+var_A0], rbx
0x18009d8d5  test    rbx, rbx
0x18009d8d8  jz      short loc_18009D8ED
0x18009d8da  mov     rax, [rbx]
0x18009d8dd  mov     rcx, rbx
0x18009d8e0  mov     rax, [rax+8]
0x18009d8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d8e9  mov     rcx, [rbp+47h+var_90]
0x18009d8ed  mov     rcx, [rcx+r14*8]
0x18009d8f1  lea     r8, [rbp+47h+var_B8]
0x18009d8f5  xor     edi, edi
0x18009d8f7  lea     rdx, MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED
0x18009d8fe  mov     dword ptr [rbp+47h+var_B8], edi
0x18009d901  mov     rax, [rcx]
0x18009d904  mov     rax, [rax+38h]
0x18009d908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d90d  test    eax, eax
0x18009d90f  mov     eax, edi
0x18009d911  js      short loc_18009D916
0x18009d913  mov     eax, dword ptr [rbp+47h+var_B8]
0x18009d916  mov     r8, [rbp+47h+var_B0]
0x18009d91a  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x18009d921  test    eax, eax
0x18009d923  mov     [rsp+120h+var_C8], rdi
0x18009d928  mov     rax, [rbx]
0x18009d92b  mov     rcx, rbx
0x18009d92e  mov     rax, [rax+0D8h]
0x18009d935  jz      short loc_18009D970
0x18009d937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d93c  mov     rax, [rbx]
0x18009d93f  lea     r8, [rsp+120h+var_C8]
0x18009d944  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18009d94b  mov     rcx, rbx
0x18009d94e  mov     rax, [rax+108h]
0x18009d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d95a  mov     edi, eax
0x18009d95c  test    eax, eax
0x18009d95e  jns     loc_18009D9E8
0x18009d964  lea     rcx, [rsp+120h+var_C8]
0x18009d969  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009d96e  jmp     short loc_18009D9A9
0x18009d970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d975  movups  xmm0, xmmword ptr [rsi]
0x18009d978  lea     r8, [rsp+120h+var_C8]
0x18009d97d  mov     rdx, rbx
0x18009d980  lea     rcx, [rbp+47h+guidCategory]
0x18009d984  movdqu  xmmword ptr [rbp+47h+guidCategory.Data1], xmm0
0x18009d989  call    cs:__imp_MFCreateWICDecoderProxy
0x18009d990  nop     dword ptr [rax+rax+00h]
0x18009d995  mov     edi, eax
0x18009d997  test    eax, eax
0x18009d999  jns     loc_18009DA97
0x18009d99f  lea     rcx, [rsp+120h+var_C8]
0x18009d9a4  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009d9a9  lea     rcx, [rbp+47h+var_A0]
0x18009d9ad  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009d9b2  inc     r14d
0x18009d9b5  cmp     r14d, [rbp+47h+var_C0]
0x18009d9b9  jb      loc_18009D8C9
0x18009d9bf  mov     r14, [rbp+47h+var_88]
0x18009d9c3  cmp     [rbp+47h+var_C0], 0
0x18009d9c7  jbe     loc_18009DAE6
0x18009d9cd  test    edi, edi
0x18009d9cf  jns     short loc_18009D9E1
0x18009d9d1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009d9d8  jz      short loc_18009D9E1
0x18009d9da  mov     ecx, edi; int
0x18009d9dc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009d9e1  mov     ebx, edi
0x18009d9e3  jmp     loc_18009DBC2
0x18009d9e8  mov     rcx, [rsp+120h+var_C8]
0x18009d9ed  lea     r8, [rbp+47h+var_B8]
0x18009d9f1  mov     [rbp+47h+var_B8], 0
0x18009d9f9  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x18009da00  mov     rax, [rcx]
0x18009da03  mov     rax, [rax]
0x18009da06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da0b  mov     ebx, eax
0x18009da0d  test    eax, eax
0x18009da0f  jns     short loc_18009DA42
0x18009da11  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009da18  jz      short loc_18009DA21
0x18009da1a  mov     ecx, eax; int
0x18009da1c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009da21  lea     rcx, [rbp+47h+var_B8]
0x18009da25  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da2a  lea     rcx, [rsp+120h+var_C8]
0x18009da2f  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da34  lea     rcx, [rbp+47h+var_A0]
0x18009da38  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da3d  jmp     loc_18009DBC2
0x18009da42  mov     rcx, [rbp+47h+var_B8]
0x18009da46  mov     rdx, [rbp+47h+var_B0]
0x18009da4a  mov     rax, [rcx]
0x18009da4d  mov     rax, [rax+20h]
0x18009da51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da56  mov     rcx, [rsp+120h+var_C8]
0x18009da5b  mov     r8, r13
0x18009da5e  mov     r14, [rbp+47h+var_88]
0x18009da62  mov     rdx, r14
0x18009da65  mov     rax, [rcx]
0x18009da68  mov     rax, [rax]
0x18009da6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da70  mov     ebx, eax
0x18009da72  test    eax, eax
0x18009da74  js      short loc_18009DA11
0x18009da76  lea     rcx, [rbp+47h+var_B8]
0x18009da7a  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da7f  lea     rcx, [rsp+120h+var_C8]
0x18009da84  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da89  lea     rcx, [rbp+47h+var_A0]
0x18009da8d  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009da92  jmp     loc_18009D9C3
0x18009da97  mov     rcx, [rsp+120h+var_C8]
0x18009da9c  mov     r8, r13
0x18009da9f  mov     r14, [rbp+47h+var_88]
0x18009daa3  mov     rdx, r14
0x18009daa6  mov     rax, [rcx]
0x18009daa9  mov     rax, [rax]
0x18009daac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dab1  mov     ebx, eax
0x18009dab3  test    eax, eax
0x18009dab5  jns     short loc_18009DAD6
0x18009dab7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009dabe  jz      short loc_18009DAC7
0x18009dac0  mov     ecx, eax; int
0x18009dac2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009dac7  lea     rcx, [rsp+120h+var_C8]
0x18009dacc  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009dad1  jmp     loc_18009DA34
0x18009dad6  lea     rcx, [rsp+120h+var_C8]
0x18009dadb  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009dae0  jmp     short loc_18009DA89
0x18009dae2  mov     r14, [rbp+47h+var_88]
0x18009dae6  test    r15, r15
0x18009dae9  jz      loc_18009DBAD
0x18009daef  test    r12, r12
0x18009daf2  jz      loc_18009DBAD
0x18009daf8  lea     r8, [rsp+120h+var_C8]; struct IInspectable **
0x18009dafd  mov     [rsp+120h+var_C8], 0
0x18009db06  mov     rdx, r12; struct COMLESS_WINRT_DLL_DATA *
0x18009db09  mov     rcx, r15; unsigned __int16 *
0x18009db0c  call    ?ComlessActivateInstance@@YAJPEBGAEAUCOMLESS_WINRT_DLL_DATA@@PEAPEAUIInspectable@@@Z; ComlessActivateInstance(ushort const *,COMLESS_WINRT_DLL_DATA &,IInspectable * *)
0x18009db11  mov     ebx, eax
0x18009db13  test    eax, eax
0x18009db15  jns     short loc_18009DB36
0x18009db17  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009db1e  jz      short loc_18009DB27
0x18009db20  mov     ecx, eax; int
0x18009db22  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009db27  lea     rcx, [rsp+120h+var_C8]
0x18009db2c  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009db31  jmp     loc_18009DBC2
0x18009db36  mov     rcx, [rsp+120h+var_C8]
0x18009db3b  lea     r8, [rbp+47h+var_A0]
0x18009db3f  mov     qword ptr [rbp+47h+var_A0], 0
0x18009db47  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x18009db4e  mov     rax, [rcx]
0x18009db51  mov     rax, [rax]
0x18009db54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db59  mov     ebx, eax
0x18009db5b  test    eax, eax
0x18009db5d  js      short loc_18009DB8F
0x18009db5f  mov     rcx, qword ptr [rbp+47h+var_A0]
0x18009db63  mov     rdx, [rbp+47h+var_B0]
0x18009db67  mov     rax, [rcx]
0x18009db6a  mov     rax, [rax+20h]
0x18009db6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db73  mov     rcx, [rsp+120h+var_C8]
0x18009db78  mov     r8, r13
0x18009db7b  mov     rdx, r14
0x18009db7e  mov     rax, [rcx]
0x18009db81  mov     rax, [rax]
0x18009db84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db89  mov     ebx, eax
0x18009db8b  test    eax, eax
0x18009db8d  jns     short loc_18009DB9F
0x18009db8f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009db96  jz      short loc_18009DB9F
0x18009db98  mov     ecx, eax; int
0x18009db9a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009db9f  lea     rcx, [rbp+47h+var_A0]
0x18009dba3  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x18009dba8  jmp     loc_18009DB27
0x18009dbad  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009dbb4  mov     ebx, 88982F50h
0x18009dbb9  jz      short loc_18009DBC2
0x18009dbbb  mov     ecx, ebx; int
0x18009dbbd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009dbc2  mov     r14b, [rsp+120h+var_D0]
0x18009dbc7  mov     r15b, [rsp+120h+var_CF]
0x18009dbcc  mov     r9, qword ptr cs:CLSID_WICRAWDecoder.Data1
0x18009dbd3  mov     rdx, qword ptr cs:CLSID_WICJpegXLDecoder.Data4
0x18009dbda  mov     r8, qword ptr cs:CLSID_WICJpegXLDecoder.Data1
0x18009dbe1  mov     rax, qword ptr cs:CLSID_WICRAWDecoder.Data4
0x18009dbe8  cmp     [rsi], r9
0x18009dbeb  jnz     short loc_18009DBF3
0x18009dbed  cmp     [rsi+8], rax
0x18009dbf1  jz      short loc_18009DC06
0x18009dbf3  cmp     [rsi], r8
0x18009dbf6  jnz     loc_18009DDDC
0x18009dbfc  cmp     [rsi+8], rdx
0x18009dc00  jnz     loc_18009DDDC
0x18009dc06  mov     rcx, [rbp+47h+var_B0]
  ... truncated ...
```
