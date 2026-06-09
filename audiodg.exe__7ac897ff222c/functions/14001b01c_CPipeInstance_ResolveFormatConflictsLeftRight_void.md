# CPipeInstance::ResolveFormatConflictsLeftRight(void)

- ea: `0x14001b01c`
- end: `0x14001bfe5`
- name: `?ResolveFormatConflictsLeftRight@CPipeInstance@@AEAAJXZ`
- size: `4041`
- prototype: `__int64 __fastcall(CPipeInstance *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001af2c`

## callees

- `0x140006264`
- `0x140008124`
- `0x140008580`
- `0x140009f54`
- `0x14000a75c`
- `0x1400199d0`
- `0x14001ae80`
- `0x14001b01c`
- `0x14001c050`
- `0x14001d284`
- `0x14001ec7c`
- `0x14001ecd4`
- `0x14002c1d4`
- `0x14002ca3c`
- `0x140044d5c`
- `0x140047448`
- `0x14004dd7c`
- `0x140055de0`
- `0x14005d0e0`
- `0x14005e150`
- `0x14005e1a4`
- `0x14005f098`
- `0x140069128`
- `0x14007b324`
- `0x14007b42c`
- `0x14007b468`
- `0x14007b4a8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001b115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001b115`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b3c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b15a`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CPipeInstance::ResolveFormatConflictsLeftRight(CPipeInstance *this)
{
  CPipeInstance *v1; // r15
  __int64 v2; // rcx
  _QWORD *Head; // rax
  HRESULT Converter; // esi
  int v5; // r8d
  _QWORD *Tail; // rax
  unsigned __int16 *v7; // rsi
  __int64 v8; // r14
  WAVEFORMATEX *v9; // rax
  WAVEFORMATEX *v10; // rbx
  char *v11; // rbx
  __int64 v12; // r13
  _QWORD *v13; // r14
  unsigned int *v14; // r13
  __int64 v15; // r12
  struct IMMDevice *v16; // rdx
  unsigned int *v17; // rax
  __int64 lpVtbl_high; // r8
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r8
  struct _GUID *v22; // r12
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // r9
  int v30; // eax
  const struct tWAVEFORMATEX *v31; // rbx
  const struct tWAVEFORMATEX *v32; // rax
  __int64 v33; // rax
  __int64 v34; // r9
  int v35; // eax
  struct IAudioMediaType *v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  _QWORD *v39; // rcx
  const char *v40; // rax
  __int64 result; // rax
  HRESULT *v42; // rbx
  HRESULT *v43; // rbx
  HRESULT *v44; // rbx
  HRESULT *v45; // rbx
  HRESULT *v46; // rbx
  int ppv; // [rsp+20h] [rbp-1A8h]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v48[2]; // [rsp+28h] [rbp-1A0h]
  struct IAudioSystemEffects2 **v49; // [rsp+30h] [rbp-198h]
  char v50; // [rsp+40h] [rbp-188h]
  BOOL v51; // [rsp+44h] [rbp-184h]
  struct IAudioMediaType *v52; // [rsp+48h] [rbp-180h] BYREF
  struct IMMDevice *v53; // [rsp+50h] [rbp-178h] BYREF
  __int64 v54; // [rsp+58h] [rbp-170h] BYREF
  struct IAudioMediaType *v55; // [rsp+60h] [rbp-168h] BYREF
  __int64 v56; // [rsp+68h] [rbp-160h] BYREF
  struct _GUID *v57; // [rsp+70h] [rbp-158h]
  int v58; // [rsp+78h] [rbp-150h]
  unsigned int v59; // [rsp+7Ch] [rbp-14Ch]
  char *v60; // [rsp+80h] [rbp-148h]
  struct IAudioMediaType *v61; // [rsp+88h] [rbp-140h] BYREF
  _QWORD *v62; // [rsp+90h] [rbp-138h]
  _QWORD *v63; // [rsp+98h] [rbp-130h]
  CPipeInstance *v64; // [rsp+A0h] [rbp-128h]
  void (__fastcall ***v65)(_QWORD, __int64); // [rsp+A8h] [rbp-120h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-118h] BYREF
  unsigned int *v67; // [rsp+B8h] [rbp-110h]
  char *v68; // [rsp+C0h] [rbp-108h]
  struct _GUID v69; // [rsp+D0h] [rbp-F8h] BYREF
  struct IAudioProcessingObject **v70; // [rsp+E0h] [rbp-E8h]
  struct IMMDevice *v71; // [rsp+E8h] [rbp-E0h]
  __int64 v72; // [rsp+F0h] [rbp-D8h]
  __int64 v73; // [rsp+F8h] [rbp-D0h] BYREF
  unsigned int *v74; // [rsp+100h] [rbp-C8h]
  BOOL v75; // [rsp+108h] [rbp-C0h]
  int pExceptionObject; // [rsp+10Ch] [rbp-BCh] BYREF
  LPVOID v77; // [rsp+110h] [rbp-B8h] BYREF
  IAudioMediaType *ppIAudioMediaType; // [rsp+118h] [rbp-B0h] BYREF
  struct IMMDevice *v79; // [rsp+120h] [rbp-A8h] BYREF
  char *v80; // [rsp+128h] [rbp-A0h]
  struct IMMDevice *v81; // [rsp+130h] [rbp-98h] BYREF
  __int64 v82; // [rsp+138h] [rbp-90h]
  __int64 v83; // [rsp+140h] [rbp-88h]
  HRESULT *v84; // [rsp+148h] [rbp-80h] BYREF
  HRESULT *v85; // [rsp+150h] [rbp-78h] BYREF
  HRESULT *v86; // [rsp+158h] [rbp-70h] BYREF
  HRESULT *v87; // [rsp+160h] [rbp-68h] BYREF
  HRESULT *v88; // [rsp+168h] [rbp-60h] BYREF
  struct _GUID v89; // [rsp+170h] [rbp-58h] BYREF
  struct _GUID v90; // [rsp+180h] [rbp-48h] BYREF

  v1 = this;
  v64 = this;
  v65 = 0;
  v73 = 0;
  v89 = 0;
  v90 = 0;
  v55 = 0;
  v56 = 0;
  ppIAudioMediaType = 0;
  v77 = 0;
  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    Head = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead(v2 + 16);
    Converter = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*Head + 8LL))(*Head, &v56);
    if ( Converter < 0 )
      goto LABEL_132;
    v60 = (char *)v1 + 16;
  }
  else
  {
    v60 = (char *)v1 + 16;
    Tail = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetTail();
    Converter = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*Tail + 16LL))(*Tail, &v56);
    if ( Converter < 0 )
      goto LABEL_132;
  }
  v7 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 40LL))(v56);
  v8 = v7[8];
  v9 = (WAVEFORMATEX *)CoTaskMemAlloc(v8 + 18);
  v10 = v9;
  if ( !v9 )
  {
    Converter = -2147024882;
LABEL_132:
    v39 = WPP_GLOBAL_Control;
    goto LABEL_133;
  }
  memcpy_0(v9, v7, v8 + 18);
  ConvertPCMWfxToIEEEFloat(v10);
  Converter = CreateAudioMediaType(v10, v10->cbSize + 18, &ppIAudioMediaType);
  CoTaskMemFree(v10);
  if ( Converter < 0 )
    goto LABEL_132;
  v11 = (char *)v1 + 16;
  v12 = *((_QWORD *)v1 + 2);
  if ( !v12 )
    ATL::AtlThrowImpl(-2147467259);
  v13 = *(_QWORD **)v12;
  v14 = *(unsigned int **)(v12 + 16);
  v67 = v14;
  Converter = (*(__int64 (__fastcall **)(unsigned int *, struct IAudioMediaType **))(*(_QWORD *)v14 + 16LL))(v14, &v55);
  if ( Converter < 0 )
    goto LABEL_132;
  v58 = 0;
  v59 = 1;
  v80 = (char *)v1 + 16;
  v50 = 0;
  v68 = (char *)v1 + 16;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids, v1);
  }
  while ( 1 )
  {
    if ( !v13 )
    {
      (*(void (__fastcall **)(unsigned int *, struct IAudioMediaType *))(*(_QWORD *)v14 + 32LL))(v14, v55);
      goto LABEL_125;
    }
    v54 = 0;
    v52 = 0;
    v63 = v13;
    v15 = v13[2];
    v13 = (_QWORD *)*v13;
    v62 = v13;
    v82 = v15;
    if ( *(_DWORD *)(v15 + 40) != 2 )
    {
      v51 = 0;
      Converter = (*(__int64 (__fastcall **)(__int64, struct IAudioMediaType *, struct IAudioMediaType **, _QWORD))(*(_QWORD *)v15 + 40LL))(
                    v15,
                    v55,
                    &v52,
                    0);
      if ( Converter < 0 )
        goto LABEL_37;
      v72 = v15 + 32;
      goto LABEL_74;
    }
    v72 = v15 + 32;
    v83 = v15 + 32;
    v16 = *(struct IMMDevice **)(v15 + 32);
    v71 = v16;
    v79 = v16;
    v17 = (unsigned int *)&v16->lpVtbl + 1;
    v74 = (unsigned int *)&v16->lpVtbl + 1;
    lpVtbl_high = HIDWORD(v16->lpVtbl);
    LODWORD(v53) = lpVtbl_high;
    v51 = lpVtbl_high != 0;
    v75 = v51;
    v70 = (struct IAudioProcessingObject **)&v16[5];
    if ( v16[5].lpVtbl )
    {
      if ( !(_DWORD)lpVtbl_high )
        goto LABEL_70;
    }
    else
    {
      v19 = *((_QWORD *)v1 + 30);
      v57 = (struct _GUID *)&v16[1];
      v20 = (*(__int64 (__fastcall **)(__int64, struct IMMDevice *, __int64, _QWORD, struct IMMDeviceVtbl *, struct IMMDevice *))(*(_QWORD *)v19 + 24LL))(
              v19,
              v16 + 1,
              lpVtbl_high,
              *((_QWORD *)v1 + 24),
              v16[7].lpVtbl,
              v16 + 5);
      Converter = v20;
      if ( v20 < 0 )
      {
        if ( v20 == -2147024882 )
          goto LABEL_37;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
        {
          v22 = v57;
        }
        else
        {
          v22 = v57;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v21, v57);
        }
        ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v80, v63);
        if ( (_DWORD)v53 )
        {
          v58 = Converter;
          v59 = *v74;
          v90 = *v22;
        }
        goto LABEL_99;
      }
      if ( !(_DWORD)v53 )
      {
LABEL_70:
        Converter = (*(__int64 (__fastcall **)(__int64, struct IAudioMediaType *, struct IAudioMediaType **, _QWORD))(*(_QWORD *)v15 + 40LL))(
                      v15,
                      v55,
                      &v52,
                      0);
        if ( Converter < 0 )
          goto LABEL_37;
        goto LABEL_74;
      }
      v53 = 0;
      Converter = CoCreateInstance(
                    &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                    0,
                    0x17u,
                    &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                    &v77);
      if ( Converter < 0 )
        goto LABEL_36;
      Converter = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMMDevice **))(*(_QWORD *)v77 + 40LL))(
                    v77,
                    *((_QWORD *)v1 + 24),
                    &v53);
      if ( Converter < 0 )
        goto LABEL_36;
      v69 = *(struct _GUID *)&v71[3].lpVtbl;
      v23 = InitializeSystemEffectsInterface(
              v53,
              *v70,
              v57,
              &v69,
              ppv,
              *((enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 *)v1 + 32),
              v49);
      Converter = v23;
      if ( v23 < 0 )
      {
        if ( v23 == -2147024882 )
          goto LABEL_36;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v24, v57);
        }
        if ( (*(int (__fastcall **)(_QWORD, struct IAudioProcessingObject *))(**((_QWORD **)v1 + 30) + 32LL))(
               *((_QWORD *)v1 + 30),
               *v70) < 0 )
        {
LABEL_36:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
LABEL_37:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
          goto LABEL_125;
        }
        ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v11, v63);
        v58 = Converter;
        v59 = *v74;
        v90 = *v57;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
LABEL_99:
        if ( v51 )
        {
          v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 40LL))(v56);
          v35 = CProcessNode::CreateDummyProcessNode(v14[6], v33, &v73, v34);
          if ( v35 < 0 )
          {
            pExceptionObject = v35;
            throw (long *)&pExceptionObject;
          }
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 24LL))(v73, v56);
          Converter = 0;
          try
          {
            v13 = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertBefore(
                              v11,
                              v13,
                              &v73);
            v62 = v13;
          }
          catch ( ATL::CAtlException *v87 )
          {
            v45 = v87;
            if ( *v87 == -1073741571 )
              _o__resetstkoflw();
            Converter = *v45;
            if ( *v45 < 0 )
              goto LABEL_110;
            v14 = v67;
            v13 = v62;
            v1 = v64;
            v60 = v68;
          }
          v73 = 0;
        }
        goto LABEL_115;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
      v16 = v71;
      v17 = v74;
    }
    if ( !*v17 )
      goto LABEL_70;
    *(_QWORD *)&v69.Data1 = v16 + 6;
    if ( !LODWORD(v16[6].lpVtbl) )
      goto LABEL_70;
    Converter = (*(__int64 (__fastcall **)(__int64, struct IAudioMediaType *, struct IAudioMediaType **, __int64))(*(_QWORD *)v15 + 40LL))(
                  v15,
                  v55,
                  &v52,
                  v56);
    if ( Converter == -2005073917 )
      break;
LABEL_60:
    if ( Converter < 0 )
    {
      if ( Converter == -2147024882 )
        goto LABEL_37;
LABEL_62:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v25, &v71[1]);
      }
      if ( (*(int (__fastcall **)(_QWORD, struct IAudioProcessingObject *))(**((_QWORD **)v1 + 30) + 32LL))(
             *((_QWORD *)v1 + 30),
             *v70) < 0 )
        goto LABEL_37;
      if ( Converter != -2005073917 )
      {
        v58 = Converter;
        v59 = *v74;
        v90 = *(struct _GUID *)&v71[1].lpVtbl;
      }
      ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v11, v63);
      goto LABEL_98;
    }
LABEL_74:
    if ( Converter != 1 )
    {
      if ( Converter )
        goto LABEL_85;
      goto LABEL_81;
    }
    v30 = (*(__int64 (__fastcall **)(unsigned int *, struct IAudioMediaType *, __int64 *, _QWORD))(*(_QWORD *)v14 + 48LL))(
            v14,
            v52,
            &v54,
            0);
    Converter = v30;
    if ( v30 < 0 )
      goto LABEL_37;
    if ( !v30 )
    {
      ATL::CComPtrBase<IAudioMediaType>::Release(&v55);
      ATL::CComPtr<IAudioMediaType>::operator=(&v55, &v52);
LABEL_81:
      (*(void (__fastcall **)(__int64, struct IAudioMediaType *))(*(_QWORD *)v15 + 24LL))(v15, v55);
      (*(void (__fastcall **)(unsigned int *, struct IAudioMediaType *))(*(_QWORD *)v14 + 32LL))(v14, v55);
      if ( v51 && *(_DWORD *)(*(_QWORD *)v72 + 4LL) && *(_DWORD *)(*(_QWORD *)v72 + 48LL) )
      {
        ATL::CComPtrBase<IAudioMediaType>::Release(&v55);
        ATL::CComPtr<IAudioMediaType>::operator=(&v55, &v56);
      }
      goto LABEL_85;
    }
    if ( v30 == 1 )
    {
      ATL::CComPtrBase<IAudioMediaType>::Release(&v55);
      ATL::CComPtr<IAudioMediaType>::operator=(&v55, &v54);
      v50 = 1;
    }
LABEL_85:
    if ( v50 )
    {
      LODWORD(v53) = 0;
      Converter = CPipeInstance::FindConverter(v1, v55, v52, (int *)&v53, &v89);
      if ( Converter < 0 )
        goto LABEL_37;
      v69 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
      Converter = CAPOProcessNode::CreateAPOProcessNode(&v89, 0, 0, v14[6], (_DWORD)v53, 0, &v69, &v65);
      if ( Converter < 0 )
        goto LABEL_37;
      Converter = 0;
      try
      {
        *(_QWORD *)&v69.Data1 = v65;
        v13 = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertBefore(v11, v63, &v69);
        v62 = v13;
      }
      catch ( ATL::CAtlException *v88 )
      {
        v46 = v88;
        if ( *v88 == -1073741571 )
          _o__resetstkoflw();
        Converter = *v46;
        if ( *v46 < 0 )
          goto LABEL_110;
        v14 = v67;
        v13 = v62;
        v1 = v64;
        v60 = v68;
      }
      v65 = 0;
      v50 = 0;
    }
    else
    {
      if ( (*((_BYTE *)v1 + 140) & 8) == 0
        || (v31 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->GetAudioFormat)(ppIAudioMediaType),
            v32 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *))v55->lpVtbl->GetAudioFormat)(v55),
            !(unsigned int)CompareWaveFormat(v32, v31)) )
      {
        v14 = (unsigned int *)v15;
        v67 = (unsigned int *)v15;
        v11 = v60;
LABEL_98:
        if ( Converter >= 0 )
          goto LABEL_115;
        goto LABEL_99;
      }
      LODWORD(v53) = 0;
      v61 = 0;
      Converter = (*(__int64 (__fastcall **)(__int64, struct IAudioMediaType **))(*(_QWORD *)v15 + 8LL))(v15, &v61);
      if ( Converter < 0
        || (Converter = CPipeInstance::FindConverter(v1, v61, v61, (int *)&v53, &v89), Converter < 0)
        || (v69 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3,
            Converter = CAPOProcessNode::CreateAPOProcessNode(&v89, 0, 0, v14[6], (_DWORD)v53, 0, &v69, &v65),
            Converter < 0) )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
        goto LABEL_37;
      }
      Converter = 0;
      try
      {
        *(_QWORD *)&v69.Data1 = v65;
        v13 = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertBefore(v60, v63, &v69);
        v62 = v13;
      }
      catch ( ATL::CAtlException *v86 )
      {
        v44 = v86;
        if ( *v86 == -1073741571 )
          _o__resetstkoflw();
        Converter = *v44;
        if ( *v44 < 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
          goto LABEL_110;
        }
        v14 = v67;
        v13 = v62;
        v1 = v64;
        v60 = v68;
      }
      v65 = 0;
      v50 = 0;
      ATL::CComPtr<IAudioMediaType>::operator=(&v55, &v61);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
    }
LABEL_115:
    v36 = v52;
    if ( v52 )
    {
      v52 = 0;
      ((void (__fastcall *)(struct IAudioMediaType *))v36->lpVtbl->Release)(v36);
      v36 = v52;
    }
    v37 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v37 = v54;
      v36 = v52;
    }
    if ( v36 )
    {
      ((void (__fastcall *)(struct IAudioMediaType *))v36->lpVtbl->Release)(v36);
      v37 = v54;
    }
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v11 = v60;
  }
  v57 = (struct _GUID *)(v15 + 24);
  if ( *(_DWORD *)(v15 + 24) != 1 || !IsFixedFormatApo(*v70) )
    goto LABEL_62;
  v53 = 0;
  v66 = 0;
  Converter = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, _QWORD, struct IAudioMediaType *, __int64 *))(*v70)->lpVtbl->IsInputFormatSupported)(
                *v70,
                0,
                v55,
                &v66);
  if ( Converter < 0
    || (v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 40LL))(v66),
        Converter = CProcessNode::CreateDummyProcessNode(v57->Data1, v26, &v53, v27),
        Converter < 0) )
  {
LABEL_58:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
    if ( v53 )
      ((void (__fastcall *)(struct IMMDevice *, __int64))v53->lpVtbl->QueryInterface)(v53, 1);
    goto LABEL_60;
  }
  try
  {
    v81 = v53;
    v13 = (_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertAfter(v11, v63, &v81);
    v62 = v13;
  }
  catch ( ATL::CAtlException *v84 )
  {
    v42 = v84;
    if ( *v84 == -1073741571 )
      _o__resetstkoflw();
    Converter = *v42;
    if ( *v42 >= 0 )
    {
      v14 = v67;
      v13 = v62;
      v51 = v75;
      v1 = v64;
      v11 = v68;
      v60 = v68;
      v15 = v82;
      v72 = v83;
      v71 = v79;
      goto LABEL_53;
    }
LABEL_50:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
    if ( v53 )
      ((void (__fastcall *)(struct IMMDevice *, __int64))v53->lpVtbl->QueryInterface)(v53, 1);
LABEL_110:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    if ( v65 )
      (**v65)(v65, 1);
    v1 = v64;
LABEL_125:
    v5 = v58;
    if ( v58 >= 0 )
      goto LABEL_132;
    v48[0] = SLODWORD(FLOAT_1_0);
    v38 = TrackSystemEffectBehavior(*((_QWORD *)v1 + 24), v59, (unsigned int)v58, 0, &v90, *(_QWORD *)v48);
    if ( v38 >= 0 )
      goto LABEL_132;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids,
          (unsigned int)v38);
        goto LABEL_132;
      }
LABEL_133:
      if ( v39 != &WPP_GLOBAL_Control && (*((_DWORD *)v39 + 7) & 0x20000) != 0 && *((_BYTE *)v39 + 25) >= 4u )
      {
        v40 = "SUCCEEDED";
        if ( Converter < 0 )
          v40 = "FAILED";
        WPP_SF_qs(v39[2], 33, v5, (_DWORD)v1, (__int64)v40);
        v39 = WPP_GLOBAL_Control;
      }
    }
    if ( Converter < 0 )
    {
      if ( v39 != &WPP_GLOBAL_Control && (*((_DWORD *)v39 + 7) & 0x20000) != 0 && *((_BYTE *)v39 + 25) >= 2u )
        WPP_SF_d(v39[2], 34, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids, (unsigned int)Converter);
      AudDGTraceLoggingErrorHelper("CPipeInstance::ResolveFormatConflictsLeftRight", 0x8A1u, Converter);
    }
    if ( v77 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    if ( ppIAudioMediaType )
      ((void (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->Release)(ppIAudioMediaType);
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    if ( v55 )
      ((void (__fastcall *)(struct IAudioMediaType *))v55->lpVtbl->Release)(v55);
    result = (unsigned int)Converter;
  }
LABEL_53:
  v53 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 40LL))(v56);
  Converter = CProcessNode::CreateDummyProcessNode(v57->Data1, v28, &v53, v29);
  if ( Converter >= 0 )
  {
    Converter = 0;
    try
    {
      v79 = v53;
      ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertAfter(v11, v13, &v79);
    }
    catch ( ATL::CAtlException *v85 )
    {
      v43 = v85;
      if ( *v85 == -1073741571 )
        _o__resetstkoflw();
      Converter = *v43;
      if ( *v43 < 0 )
        goto LABEL_50;
      v14 = v67;
      v1 = v64;
      v60 = v68;
    }
    *((_DWORD *)v1 + 35) |= 6u;
    **(_DWORD **)&v69.Data1 = 0;
    v13 = v63;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
    goto LABEL_115;
  }
  goto LABEL_58;
}

```

## disassembly

```asm
0x14001b01c  mov     r11, rsp
0x14001b01f  mov     [r11+10h], rbx
0x14001b023  mov     [r11+18h], rsi
0x14001b027  push    rdi
0x14001b028  push    r12
0x14001b02a  push    r13
0x14001b02c  push    r14
0x14001b02e  push    r15
0x14001b030  sub     rsp, 1A0h
0x14001b037  mov     rax, cs:__security_cookie
0x14001b03e  xor     rax, rsp
0x14001b041  mov     [rsp+1C8h+var_38], rax
0x14001b049  mov     r15, rcx
0x14001b04c  mov     [rsp+1C8h+var_128], rcx
0x14001b054  xor     edi, edi
0x14001b056  mov     [r11-120h], rdi
0x14001b05d  mov     [r11-0D0h], rdi
0x14001b064  xorps   xmm0, xmm0
0x14001b067  movups  xmmword ptr [r11-58h], xmm0
0x14001b06c  xorps   xmm1, xmm1
0x14001b06f  movups  xmmword ptr [r11-48h], xmm1
0x14001b074  mov     [rsp+1C8h+var_168], rdi
0x14001b079  mov     [rsp+1C8h+var_160], rdi
0x14001b07e  mov     [r11-0B0h], rdi
0x14001b085  mov     [r11-0B8h], rdi
0x14001b08c  mov     rcx, [rcx]
0x14001b08f  test    rcx, rcx
0x14001b092  jz      short loc_14001B0C9
0x14001b094  add     rcx, 10h
0x14001b098  call    ?GetHead@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@XZ; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead(void)
0x14001b09d  mov     rcx, [rax]
0x14001b0a0  mov     rax, [rcx]
0x14001b0a3  lea     rdx, [rsp+1C8h+var_160]
0x14001b0a8  mov     rax, [rax+8]
0x14001b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b0b1  mov     esi, eax
0x14001b0b3  test    eax, eax
0x14001b0b5  js      loc_14001BEBC
0x14001b0bb  lea     rcx, [r15+10h]
0x14001b0bf  mov     [rsp+1C8h+var_148], rcx
0x14001b0c7  jmp     short loc_14001B0F8
0x14001b0c9  lea     rcx, [r15+10h]
0x14001b0cd  mov     [rsp+1C8h+var_148], rcx
0x14001b0d5  call    ?GetTail@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@XZ; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetTail(void)
0x14001b0da  mov     rcx, [rax]
0x14001b0dd  mov     rax, [rcx]
0x14001b0e0  lea     rdx, [rsp+1C8h+var_160]
0x14001b0e5  mov     rax, [rax+10h]
0x14001b0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b0ee  mov     esi, eax
0x14001b0f0  test    eax, eax
0x14001b0f2  js      loc_14001BEBC
0x14001b0f8  mov     rcx, [rsp+1C8h+var_160]
0x14001b0fd  mov     rax, [rcx]
0x14001b100  mov     rax, [rax+28h]
0x14001b104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b109  mov     rsi, rax
0x14001b10c  movzx   r14d, word ptr [rax+10h]
0x14001b111  lea     rcx, [r14+12h]; cb
0x14001b115  call    cs:__imp_CoTaskMemAlloc
0x14001b11b  mov     rbx, rax
0x14001b11e  test    rax, rax
0x14001b121  jz      loc_14001BEB7
0x14001b127  lea     r8, [r14+12h]; Size
0x14001b12b  mov     rdx, rsi; Src
0x14001b12e  mov     rcx, rax; void *
0x14001b131  call    memcpy_0
0x14001b136  mov     rcx, rbx; struct tWAVEFORMATEX *
0x14001b139  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x14001b13e  movzx   edx, word ptr [rbx+10h]
0x14001b142  add     edx, 12h; cbAudioFormatSize
0x14001b145  lea     r8, [rsp+1C8h+ppIAudioMediaType]; ppIAudioMediaType
0x14001b14d  mov     rcx, rbx; pAudioFormat
0x14001b150  call    CreateAudioMediaType
0x14001b155  mov     esi, eax
0x14001b157  mov     rcx, rbx; pv
0x14001b15a  call    cs:__imp_CoTaskMemFree
0x14001b160  test    esi, esi
0x14001b162  js      loc_14001BEBC
0x14001b168  lea     rbx, [r15+10h]
0x14001b16c  mov     r13, [rbx]
0x14001b16f  test    r13, r13
0x14001b172  jnz     short loc_14001B17F
0x14001b174  mov     ecx, 80004005h; int
0x14001b179  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001b17f  mov     r14, [r13+0]
0x14001b183  mov     r13, [r13+10h]
0x14001b187  mov     [rsp+1C8h+var_110], r13
0x14001b18f  mov     rax, [r13+0]
0x14001b193  lea     rdx, [rsp+1C8h+var_168]
0x14001b198  mov     rcx, r13
0x14001b19b  mov     rax, [rax+10h]
0x14001b19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b1a4  mov     esi, eax
0x14001b1a6  test    eax, eax
0x14001b1a8  js      loc_14001BEBC
0x14001b1ae  mov     [rsp+1C8h+var_150], edi
0x14001b1b2  mov     [rsp+1C8h+var_14C], 1
0x14001b1ba  mov     [rsp+1C8h+var_A0], rbx
0x14001b1c2  mov     [rsp+1C8h+var_188], dil
0x14001b1c7  mov     [rsp+1C8h+var_108], rbx
0x14001b1cf  lea     r12, WPP_GLOBAL_Control
0x14001b1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b1dd  cmp     rcx, r12
0x14001b1e0  jz      short loc_14001B209
0x14001b1e2  test    dword ptr [rcx+1Ch], 20000h
0x14001b1e9  jz      short loc_14001B209
0x14001b1eb  cmp     byte ptr [rcx+19h], 4
0x14001b1ef  jb      short loc_14001B209
0x14001b1f1  mov     edx, 1Ch
0x14001b1f6  mov     r9, r15
0x14001b1f9  lea     r8, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids
0x14001b200  mov     rcx, [rcx+10h]
0x14001b204  call    WPP_SF_q
0x14001b209  test    r14, r14
0x14001b20c  jz      loc_14001BE2D
0x14001b212  mov     [rsp+1C8h+var_170], rdi
0x14001b217  mov     [rsp+1C8h+var_180], rdi
0x14001b21c  mov     [rsp+1C8h+var_130], r14
0x14001b224  mov     r12, [r14+10h]
0x14001b228  mov     r14, [r14]
0x14001b22b  mov     [rsp+1C8h+var_138], r14
0x14001b233  mov     [rsp+1C8h+var_90], r12
0x14001b23b  cmp     dword ptr [r12+28h], 2
0x14001b241  jnz     loc_14001B8AB
0x14001b247  lea     rax, [r12+20h]
0x14001b24c  mov     [rsp+1C8h+var_D8], rax
0x14001b254  mov     [rsp+1C8h+var_88], rax
0x14001b25c  mov     rdx, [rax]
0x14001b25f  mov     [rsp+1C8h+var_E0], rdx
0x14001b267  mov     [rsp+1C8h+var_A8], rdx
0x14001b26f  lea     rax, [rdx+4]
0x14001b273  mov     [rsp+1C8h+var_C8], rax
0x14001b27b  mov     r8d, [rax]
0x14001b27e  mov     dword ptr [rsp+1C8h+var_178], r8d
0x14001b283  mov     ecx, edi
0x14001b285  test    r8d, r8d
0x14001b288  setnz   cl
0x14001b28b  mov     [rsp+1C8h+var_184], ecx
0x14001b28f  mov     [rsp+1C8h+var_C0], ecx
0x14001b296  lea     r9, [rdx+28h]
0x14001b29a  mov     [rsp+1C8h+var_E8], r9
0x14001b2a2  cmp     [r9], rdi
0x14001b2a5  jnz     loc_14001B537
0x14001b2ab  mov     rcx, [r15+0F0h]
0x14001b2b2  lea     r10, [rdx+8]
0x14001b2b6  mov     [rsp+1C8h+var_158], r10
0x14001b2bb  mov     rax, [rcx]
0x14001b2be  mov     qword ptr [rsp+1C8h+var_1A0], r9
0x14001b2c3  mov     rdx, [rdx+38h]
0x14001b2c7  mov     [rsp+1C8h+ppv], rdx
0x14001b2cc  mov     r9, [r15+0C0h]
0x14001b2d3  mov     rdx, r10
0x14001b2d6  mov     rax, [rax+18h]
0x14001b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b2df  mov     esi, eax
0x14001b2e1  test    eax, eax
0x14001b2e3  jns     loc_14001B394
0x14001b2e9  cmp     eax, 8007000Eh
0x14001b2ee  jnz     short loc_14001B311
0x14001b2f0  lea     rcx, [rsp+1C8h+var_180]
0x14001b2f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b2fa  nop
0x14001b2fb  lea     rcx, [rsp+1C8h+var_170]
0x14001b300  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b305  lea     r12, WPP_GLOBAL_Control
0x14001b30c  jmp     loc_14001BE42
0x14001b311  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b318  lea     rax, WPP_GLOBAL_Control
0x14001b31f  cmp     rcx, rax
0x14001b322  jz      short loc_14001B34B
0x14001b324  test    dword ptr [rcx+1Ch], 20000h
0x14001b32b  jz      short loc_14001B34B
0x14001b32d  mov     r12, [rsp+1C8h+var_158]
0x14001b332  cmp     byte ptr [rcx+19h], 4
0x14001b336  jb      short loc_14001B350
0x14001b338  mov     edx, 1Dh
0x14001b33d  mov     r9, r12
0x14001b340  mov     rcx, [rcx+10h]
0x14001b344  call    WPP_SF__guid_
0x14001b349  jmp     short loc_14001B350
0x14001b34b  mov     r12, [rsp+1C8h+var_158]
0x14001b350  mov     rdx, [rsp+1C8h+var_130]
0x14001b358  mov     rcx, [rsp+1C8h+var_A0]
0x14001b360  call    ?RemoveAt@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(__POSITION *)
0x14001b365  cmp     dword ptr [rsp+1C8h+var_178], edi
0x14001b369  jz      loc_14001BB95
0x14001b36f  mov     [rsp+1C8h+var_150], esi
0x14001b373  mov     rax, [rsp+1C8h+var_C8]
0x14001b37b  mov     eax, [rax]
0x14001b37d  mov     [rsp+1C8h+var_14C], eax
0x14001b381  movups  xmm0, xmmword ptr [r12]
0x14001b386  movdqu  [rsp+1C8h+var_48], xmm0
0x14001b38f  jmp     loc_14001BB95
0x14001b394  cmp     dword ptr [rsp+1C8h+var_178], edi
0x14001b398  jz      loc_14001B883
0x14001b39e  mov     [rsp+1C8h+var_178], rdi
0x14001b3a3  lea     rax, [rsp+1C8h+var_B8]
0x14001b3ab  mov     [rsp+1C8h+ppv], rax; int
0x14001b3b0  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14001b3b7  xor     edx, edx; pUnkOuter
0x14001b3b9  lea     r8d, [rdx+17h]; dwClsContext
0x14001b3bd  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14001b3c4  call    cs:__imp_CoCreateInstance
0x14001b3ca  mov     esi, eax
0x14001b3cc  test    eax, eax
0x14001b3ce  jns     short loc_14001B3DF
0x14001b3d0  lea     rcx, [rsp+1C8h+var_178]
0x14001b3d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b3da  jmp     loc_14001B2F0
0x14001b3df  mov     rcx, [rsp+1C8h+var_B8]
0x14001b3e7  mov     rax, [rcx]
0x14001b3ea  lea     r8, [rsp+1C8h+var_178]
0x14001b3ef  mov     rdx, [r15+0C0h]
0x14001b3f6  mov     rax, [rax+28h]
0x14001b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b3ff  mov     esi, eax
0x14001b401  test    eax, eax
0x14001b403  js      short loc_14001B3D0
0x14001b405  mov     r9, [rsp+1C8h+var_E0]
0x14001b40d  movups  xmm0, xmmword ptr [r9+18h]
0x14001b412  movdqu  xmmword ptr [rsp+1C8h+var_F8.Data1], xmm0
0x14001b41b  mov     eax, [r15+80h]
0x14001b422  mov     [rsp+1C8h+var_1A0], eax; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x14001b426  lea     r9, [rsp+1C8h+var_F8]; struct _GUID
0x14001b42e  mov     r8, [rsp+1C8h+var_158]; struct _GUID *
0x14001b433  mov     rax, [rsp+1C8h+var_E8]
0x14001b43b  mov     rdx, [rax]; struct IAudioProcessingObject *
0x14001b43e  mov     rcx, [rsp+1C8h+var_178]; struct IMMDevice *
0x14001b443  call    ?InitializeSystemEffectsInterface@@YAJPEAUIMMDevice@@PEAUIAudioProcessingObject@@PEAU_GUID@@U3@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUIAudioSystemEffects2@@@Z; InitializeSystemEffectsInterface(IMMDevice *,IAudioProcessingObject *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioSystemEffects2 * *)
0x14001b448  mov     esi, eax
0x14001b44a  test    eax, eax
0x14001b44c  jns     loc_14001B51B
0x14001b452  cmp     eax, 8007000Eh
0x14001b457  jz      loc_14001B3D0
0x14001b45d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b464  lea     r12, WPP_GLOBAL_Control
0x14001b46b  cmp     rcx, r12
0x14001b46e  jz      short loc_14001B492
0x14001b470  test    dword ptr [rcx+1Ch], 20000h
0x14001b477  jz      short loc_14001B492
0x14001b479  cmp     byte ptr [rcx+19h], 4
0x14001b47d  jb      short loc_14001B492
0x14001b47f  mov     edx, 1Eh
0x14001b484  mov     r9, [rsp+1C8h+var_158]
0x14001b489  mov     rcx, [rcx+10h]
0x14001b48d  call    WPP_SF__guid_
0x14001b492  mov     rcx, [r15+0F0h]
0x14001b499  mov     rax, [rcx]
0x14001b49c  mov     rdx, [rsp+1C8h+var_E8]
0x14001b4a4  mov     rdx, [rdx]
0x14001b4a7  mov     rax, [rax+20h]
0x14001b4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4b0  test    eax, eax
0x14001b4b2  jns     short loc_14001B4D9
0x14001b4b4  lea     rcx, [rsp+1C8h+var_178]
0x14001b4b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b4be  nop
0x14001b4bf  lea     rcx, [rsp+1C8h+var_180]
0x14001b4c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b4c9  nop
0x14001b4ca  lea     rcx, [rsp+1C8h+var_170]
0x14001b4cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b4d4  jmp     loc_14001BE42
0x14001b4d9  mov     rdx, [rsp+1C8h+var_130]
0x14001b4e1  mov     rcx, rbx
0x14001b4e4  call    ?RemoveAt@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(__POSITION *)
0x14001b4e9  mov     [rsp+1C8h+var_150], esi
0x14001b4ed  mov     rax, [rsp+1C8h+var_C8]
0x14001b4f5  mov     eax, [rax]
0x14001b4f7  mov     [rsp+1C8h+var_14C], eax
0x14001b4fb  mov     rax, [rsp+1C8h+var_158]
0x14001b500  movups  xmm0, xmmword ptr [rax]
0x14001b503  movdqu  [rsp+1C8h+var_48], xmm0
0x14001b50c  lea     rcx, [rsp+1C8h+var_178]
0x14001b511  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b516  jmp     loc_14001BB95
0x14001b51b  lea     rcx, [rsp+1C8h+var_178]
0x14001b520  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b525  mov     rdx, [rsp+1C8h+var_E0]
0x14001b52d  mov     rax, [rsp+1C8h+var_C8]
0x14001b535  jmp     short loc_14001B540
0x14001b537  test    r8d, r8d
0x14001b53a  jz      loc_14001B883
0x14001b540  cmp     [rax], edi
0x14001b542  jz      loc_14001B883
0x14001b548  lea     rax, [rdx+30h]
0x14001b54c  mov     qword ptr [rsp+1C8h+var_F8.Data1], rax
0x14001b554  cmp     [rax], edi
0x14001b556  jz      loc_14001B883
0x14001b55c  mov     rax, [r12]
0x14001b560  mov     r9, [rsp+1C8h+var_160]
0x14001b565  lea     r8, [rsp+1C8h+var_180]
0x14001b56a  mov     rdx, [rsp+1C8h+var_168]
0x14001b56f  mov     rcx, r12
0x14001b572  mov     rax, [rax+28h]
0x14001b576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b57b  mov     esi, eax
0x14001b57d  cmp     eax, 887D0003h
0x14001b582  jnz     loc_14001B7C9
  ... truncated ...
```
