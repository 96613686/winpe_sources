# CPipeInstance::ResolveFormatConflictsRightLeft(void)

- ea: `0x14002ac14`
- end: `0x14002bc8d`
- name: `?ResolveFormatConflictsRightLeft@CPipeInstance@@AEAAJXZ`
- size: `4217`
- prototype: `__int64 __fastcall(CPipeInstance *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001af2c`

## callees

- `0x140006264`
- `0x140008124`
- `0x140009f54`
- `0x14000a75c`
- `0x14000e11c`
- `0x14000e280`
- `0x1400199d0`
- `0x14001ae80`
- `0x14001c050`
- `0x14001d284`
- `0x14001ec7c`
- `0x14001ecd4`
- `0x1400256b8`
- `0x140028a18`
- `0x14002ac14`
- `0x14002bc94`
- `0x14002c1d4`
- `0x14002ca3c`
- `0x140044d5c`
- `0x140047448`
- `0x14004dd7c`
- `0x140055de0`
- `0x14005d0e0`
- `0x14005e150`
- `0x14005f098`
- `0x140069128`
- `0x14007b324`
- `0x14007b42c`
- `0x14007b468`
- `0x14007b4a8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002acec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002acec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b086`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ad32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ad32`

## string_xrefs

- `0x14002af38`: `CreateApo`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CPipeInstance::ResolveFormatConflictsRightLeft(CPipeInstance *this)
{
  CPipeInstance *v1; // r12
  char *v2; // rdi
  __int64 v3; // rcx
  int v4; // r8d
  HRESULT Converter; // r14d
  unsigned __int16 *v6; // r14
  __int64 v7; // r15
  WAVEFORMATEX *v8; // rax
  WAVEFORMATEX *v9; // rbx
  __int64 v10; // r13
  CPipeInstance *v11; // rcx
  struct CProcessNode *v12; // r15
  struct CProcessNode **Head; // rax
  struct CProcessNode *v14; // rdi
  __int64 v15; // r14
  struct CProcessNode *v16; // rax
  struct _GUID v17; // xmm6
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  struct _GUID *v21; // rbx
  unsigned int v22; // eax
  int v23; // ecx
  struct _GUID *v24; // r14
  struct _GUID v25; // xmm6
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // r8
  struct _GUID *v28; // rbx
  HRESULT v29; // eax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // r9
  struct CProcessNode *v33; // rdi
  __int64 v34; // rax
  __int64 v35; // r9
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // rdi
  __int64 v39; // rbx
  struct IAudioMediaType *v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rbx
  _DWORD *v43; // rbx
  int v44; // eax
  const struct tWAVEFORMATEX *v45; // rbx
  const struct tWAVEFORMATEX *v46; // rax
  __int64 v47; // rcx
  struct IAudioMediaType *v48; // rdx
  int v49; // eax
  _QWORD *v50; // rcx
  const char *v51; // rax
  __int64 result; // rax
  int *v53; // rbx
  int *v54; // rbx
  int *v55; // rbx
  int *v56; // rbx
  int ppv; // [rsp+20h] [rbp-388h]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v58[2]; // [rsp+28h] [rbp-380h]
  struct IAudioSystemEffects2 **v59; // [rsp+30h] [rbp-378h]
  char v60; // [rsp+40h] [rbp-368h]
  char v61; // [rsp+41h] [rbp-367h]
  struct IAudioMediaType *v62; // [rsp+48h] [rbp-360h] BYREF
  int v63[2]; // [rsp+50h] [rbp-358h] BYREF
  struct IAudioMediaType *v64; // [rsp+58h] [rbp-350h] BYREF
  __int64 v65; // [rsp+60h] [rbp-348h] BYREF
  struct IMMDevice *v66; // [rsp+68h] [rbp-340h] BYREF
  struct _GUID *v67; // [rsp+70h] [rbp-338h] BYREF
  unsigned int v68; // [rsp+78h] [rbp-330h]
  __int64 v69; // [rsp+80h] [rbp-328h] BYREF
  struct CProcessNode *v70; // [rsp+88h] [rbp-320h]
  char *v71; // [rsp+90h] [rbp-318h]
  __int64 v72; // [rsp+98h] [rbp-310h] BYREF
  int v73; // [rsp+A0h] [rbp-308h]
  struct CProcessNode *v74; // [rsp+A8h] [rbp-300h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-2F8h]
  __int64 v76; // [rsp+B8h] [rbp-2F0h]
  struct _GUID v77; // [rsp+C0h] [rbp-2E8h] BYREF
  struct IAudioProcessingObject **v78; // [rsp+D0h] [rbp-2D8h]
  CPipeInstance *v79; // [rsp+D8h] [rbp-2D0h]
  char *v80; // [rsp+E0h] [rbp-2C8h]
  void (__fastcall ***v81)(_QWORD, __int64); // [rsp+E8h] [rbp-2C0h] BYREF
  LPVOID v82; // [rsp+F0h] [rbp-2B8h] BYREF
  IAudioMediaType *ppIAudioMediaType; // [rsp+F8h] [rbp-2B0h] BYREF
  _DWORD *v84; // [rsp+100h] [rbp-2A8h]
  struct CProcessNode *v85; // [rsp+108h] [rbp-2A0h]
  _DWORD *v86; // [rsp+110h] [rbp-298h]
  char *v87; // [rsp+118h] [rbp-290h]
  struct IMMDevice *v88; // [rsp+120h] [rbp-288h] BYREF
  struct CProcessNode *v89; // [rsp+128h] [rbp-280h]
  __int64 v90; // [rsp+130h] [rbp-278h]
  ATL::CAtlException *v91; // [rsp+138h] [rbp-270h] BYREF
  ATL::CAtlException *v92; // [rsp+140h] [rbp-268h] BYREF
  ATL::CAtlException *v93; // [rsp+148h] [rbp-260h] BYREF
  ATL::CAtlException *v94; // [rsp+150h] [rbp-258h] BYREF
  struct _GUID v95; // [rsp+158h] [rbp-250h] BYREF
  struct _GUID v96; // [rsp+168h] [rbp-240h] BYREF
  _BYTE v97[240]; // [rsp+180h] [rbp-228h] BYREF
  _BYTE v98[240]; // [rsp+270h] [rbp-138h] BYREF

  v1 = this;
  v79 = this;
  v81 = 0;
  v96 = 0;
  v95 = 0;
  v64 = 0;
  v82 = 0;
  v72 = 0;
  ppIAudioMediaType = 0;
  v2 = (char *)this + 16;
  v71 = (char *)this + 16;
  v3 = *((_QWORD *)this + 2);
  if ( !v3 )
    ATL::AtlThrowImpl(-2147467259);
  Converter = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v3 + 16) + 16LL))(*(_QWORD *)(v3 + 16), &v72);
  if ( Converter < 0 )
    goto LABEL_155;
  v6 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 40LL))(v72);
  v7 = v6[8];
  v8 = (WAVEFORMATEX *)CoTaskMemAlloc(v7 + 18);
  v9 = v8;
  if ( !v8 )
  {
    Converter = -2147024882;
LABEL_155:
    v50 = WPP_GLOBAL_Control;
    goto LABEL_156;
  }
  memcpy_0(v8, v6, v7 + 18);
  ConvertPCMWfxToIEEEFloat(v9);
  Converter = CreateAudioMediaType(v9, v9->cbSize + 18, &ppIAudioMediaType);
  CoTaskMemFree(v9);
  if ( Converter < 0 )
    goto LABEL_155;
  v10 = *((_QWORD *)v1 + 3);
  v69 = v10;
  v11 = *(CPipeInstance **)v1;
  if ( *(_QWORD *)v1 )
  {
    if ( *((_DWORD *)v1 + 30) && !*((_DWORD *)v11 + 53) )
    {
      v74 = 0;
      CPipeInstance::GetAPONodeAndConnection(v11, &GUID_d81229b1_5a43_480c_92f7_be0f7f4eab60, &v74, 0, 0);
      v12 = v74;
      v70 = v74;
      if ( v74 )
        goto LABEL_15;
      v74 = 0;
      CPipeInstance::GetAPONodeAndConnection(
        *(CPipeInstance **)v1,
        &GUID_fc7dff56_6b8d_45a9_b4ca_266f9ac21693,
        &v74,
        0,
        0);
      v12 = v74;
      v70 = v74;
      if ( v74 )
        goto LABEL_15;
      v11 = *(CPipeInstance **)v1;
    }
    Head = (struct CProcessNode **)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead((char *)v11 + 16);
  }
  else
  {
    Head = (struct CProcessNode **)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetPrev(0, &v69);
    v10 = v69;
  }
  v12 = *Head;
  v70 = *Head;
LABEL_15:
  Converter = (*(__int64 (__fastcall **)(struct CProcessNode *, struct IAudioMediaType **))(*(_QWORD *)v12 + 8LL))(
                v12,
                &v64);
  if ( Converter < 0 )
    goto LABEL_155;
  v87 = v2;
  v73 = 0;
  v68 = 1;
  v61 = 0;
  v80 = v2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids, v1);
  }
  while ( 1 )
  {
    if ( !v10 )
    {
      (*(void (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *))(*(_QWORD *)v12 + 24LL))(v12, v64);
      goto LABEL_148;
    }
    v62 = 0;
    v65 = 0;
    v76 = v10;
    v10 = *(_QWORD *)(v10 + 8);
    v69 = v10;
    v14 = *(struct CProcessNode **)(v76 + 16);
    v85 = v14;
    v89 = v14;
    v60 = 0;
    if ( *((_DWORD *)v14 + 10) == 2 )
      break;
    Converter = (*(__int64 (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *, struct IAudioMediaType **, _QWORD))(*(_QWORD *)v14 + 48LL))(
                  v14,
                  v64,
                  &v62,
                  0);
    if ( Converter < 0 )
      goto LABEL_26;
    v43 = (_DWORD *)((char *)v14 + 32);
LABEL_113:
    if ( Converter == 1 )
    {
      v44 = (*(__int64 (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *, __int64 *, _QWORD))(*(_QWORD *)v12 + 40LL))(
              v12,
              v62,
              &v65,
              0);
      Converter = v44;
      if ( v44 < 0 )
        goto LABEL_26;
      if ( v44 )
      {
        if ( v44 == 1 )
        {
          ATL::CComPtrBase<IAudioMediaType>::Release(&v64);
          ATL::CComPtr<IAudioMediaType>::operator=(&v64, &v65);
          v61 = 1;
        }
        goto LABEL_124;
      }
      ATL::CComPtrBase<IAudioMediaType>::Release(&v64);
      ATL::CComPtr<IAudioMediaType>::operator=(&v64, &v62);
LABEL_120:
      (*(void (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *))(*(_QWORD *)v12 + 24LL))(v12, v64);
      (*(void (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *))(*(_QWORD *)v14 + 32LL))(v14, v64);
      if ( v60 && *(_DWORD *)(*(_QWORD *)v43 + 4LL) && *(_DWORD *)(*(_QWORD *)v43 + 52LL) )
      {
        ATL::CComPtrBase<IAudioMediaType>::Release(&v64);
        ATL::CComPtr<IAudioMediaType>::operator=(&v64, &v72);
      }
      goto LABEL_124;
    }
    if ( !Converter )
      goto LABEL_120;
LABEL_124:
    if ( !v61 )
    {
      if ( (*((_BYTE *)v1 + 140) & 8) == 0
        || (v45 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->GetAudioFormat)(ppIAudioMediaType),
            v46 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *))v64->lpVtbl->GetAudioFormat)(v64),
            !(unsigned int)CompareWaveFormat(v46, v45)) )
      {
        v12 = v14;
        v70 = v14;
        goto LABEL_139;
      }
      if ( !v62 )
        ATL::CComPtr<IAudioMediaType>::operator=(&v62, &v72);
    }
    v63[0] = 0;
    Converter = CPipeInstance::FindConverter(v1, v64, v62, v63, &v96);
    if ( Converter < 0 )
      goto LABEL_26;
    v77 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
    Converter = CAPOProcessNode::CreateAPOProcessNode(&v96, 0, 0, *((unsigned int *)v14 + 6), v63[0], 0, &v77, &v81);
    if ( Converter < 0 )
      goto LABEL_26;
    Converter = 0;
    try
    {
      *(_QWORD *)&v77.Data1 = v81;
      v10 = ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertAfter(v71, v76, &v77);
      v69 = v10;
    }
    catch ( ATL::CAtlException *v94 )
    {
      v56 = (int *)v94;
      if ( *(_DWORD *)v94 == -1073741571 )
        _o__resetstkoflw();
      v63[0] = *v56;
      Converter = v63[0];
      if ( v63[0] < 0 )
        goto LABEL_134;
      v12 = v70;
      v10 = v69;
      v1 = v79;
      v71 = v80;
    }
    v81 = 0;
    v61 = 0;
LABEL_139:
    v47 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v47 = v65;
    }
    v48 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(struct IAudioMediaType *))v48->lpVtbl->Release)(v48);
      v48 = v62;
      v47 = v65;
    }
    if ( v47 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v48 = v62;
    }
    if ( v48 )
      ((void (__fastcall *)(struct IAudioMediaType *))v48->lpVtbl->Release)(v48);
  }
  v86 = (_DWORD *)((char *)v14 + 32);
  v15 = *((_QWORD *)v14 + 4);
  v75 = v15;
  v90 = v15;
  v78 = (struct IAudioProcessingObject **)(v15 + 40);
  if ( *(_QWORD *)(v15 + 40) )
  {
    v16 = (struct CProcessNode *)(v15 + 4);
LABEL_54:
    *(_QWORD *)v63 = v16;
    goto LABEL_55;
  }
  v67 = (struct _GUID *)(v15 + 8);
  v17 = *(struct _GUID *)(v15 + 8);
  v18 = AudioDgTelemetryProvider::Provider();
  v77 = v17;
  CPerfTracker::CPerfTracker((CPerfTracker *)v97, v18, "CreateApo", &v77);
  v19 = *((_QWORD *)v1 + 30);
  *(_QWORD *)v63 = v15 + 4;
  Converter = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, struct IAudioProcessingObject **))(*(_QWORD *)v19 + 24LL))(
                v19,
                v15 + 8,
                *(unsigned int *)(v15 + 4),
                *((_QWORD *)v1 + 24),
                *(_QWORD *)(v15 + 56),
                v78);
  CPerfTracker::~CPerfTracker((CPerfTracker *)v97);
  if ( Converter < 0 )
  {
    if ( Converter == -2147024882 )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
    {
      v21 = v67;
    }
    else
    {
      v21 = v67;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v20, v67);
    }
    ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v87, v76);
    v22 = **(_DWORD **)v63;
    if ( **(_DWORD **)v63 )
    {
      v23 = 1;
      v73 = Converter;
      v95 = *v21;
    }
    else
    {
      v23 = 0;
    }
    if ( !v23 )
      v22 = v68;
    v68 = v22;
    goto LABEL_139;
  }
  v16 = *(struct CProcessNode **)v63;
  if ( !**(_DWORD **)v63 )
  {
    v15 = v75;
    goto LABEL_54;
  }
  v66 = 0;
  Converter = CoCreateInstance(
                &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                0,
                0x17u,
                &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                &v82);
  if ( Converter < 0 )
    goto LABEL_40;
  Converter = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMMDevice **))(*(_QWORD *)v82 + 40LL))(
                v82,
                *((_QWORD *)v1 + 24),
                &v66);
  if ( Converter < 0 )
    goto LABEL_40;
  v24 = v67;
  v25 = *v67;
  v26 = AudioDgTelemetryProvider::Provider();
  v77 = v25;
  CPerfTracker::CPerfTracker((CPerfTracker *)v98, v26, "InitializeSystemEffect", &v77);
  v77 = *(struct _GUID *)(v75 + 24);
  Converter = InitializeSystemEffectsInterface(
                v66,
                *v78,
                v24,
                &v77,
                ppv,
                *((enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 *)v1 + 32),
                v59);
  CPerfTracker::~CPerfTracker((CPerfTracker *)v98);
  if ( Converter < 0 )
  {
    if ( Converter == -2147024882 )
      goto LABEL_40;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
    {
      v28 = v67;
    }
    else
    {
      v28 = v67;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v27, v67);
    }
    if ( (*(int (__fastcall **)(_QWORD, struct IAudioProcessingObject *))(**((_QWORD **)v1 + 30) + 32LL))(
           *((_QWORD *)v1 + 30),
           *v78) < 0 )
    {
LABEL_40:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
LABEL_26:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v62);
      goto LABEL_148;
    }
    ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v71, v76);
    v73 = Converter;
    v68 = **(_DWORD **)v63;
    v95 = *v28;
    if ( v66 )
      ((void (__fastcall *)(struct IMMDevice *))v66->lpVtbl->Release)(v66);
    goto LABEL_139;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
  v16 = *(struct CProcessNode **)v63;
  v15 = v75;
LABEL_55:
  v74 = v16;
  if ( !*(_DWORD *)v16 || (v84 = (_DWORD *)(v15 + 52), !*(_DWORD *)(v15 + 52)) )
  {
    Converter = (*(__int64 (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *, struct IAudioMediaType **, _QWORD))(*(_QWORD *)v14 + 48LL))(
                  v14,
                  v64,
                  &v62,
                  0);
    if ( Converter < 0 )
      goto LABEL_26;
    goto LABEL_110;
  }
  v29 = (*(__int64 (__fastcall **)(struct CProcessNode *, struct IAudioMediaType *, struct IAudioMediaType **, __int64))(*(_QWORD *)v14 + 48LL))(
          v14,
          v64,
          &v62,
          v72);
  Converter = v29;
  if ( v29 == -2005073917 )
  {
    *(_QWORD *)&v77.Data1 = (char *)v12 + 24;
    if ( *((_DWORD *)v12 + 6) != 1 || !*((_DWORD *)v1 + 78) )
    {
      v33 = *(struct CProcessNode **)v63;
      goto LABEL_101;
    }
    v67 = 0;
    Converter = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, _QWORD, struct IAudioMediaType *, struct _GUID **))(*v78)->lpVtbl->IsOutputFormatSupported)(
                  *v78,
                  0,
                  v64,
                  &v67);
    if ( Converter )
    {
      v33 = *(struct CProcessNode **)v63;
    }
    else
    {
      v66 = 0;
      v31 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&v67->Data1 + 40LL))(v67);
      Converter = CProcessNode::CreateDummyProcessNode(*((unsigned int *)v12 + 6), v31, &v66, v32);
      if ( Converter < 0 )
      {
        v33 = *(struct CProcessNode **)v63;
      }
      else
      {
        try
        {
          v88 = v66;
          v10 = ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertBefore(v71, v76, &v88);
          v69 = v10;
          v33 = *(struct CProcessNode **)v63;
        }
        catch ( ATL::CAtlException *v91 )
        {
          v53 = (int *)v91;
          if ( *(_DWORD *)v91 == -1073741571 )
            _o__resetstkoflw();
          v63[0] = *v53;
          Converter = v63[0];
          if ( v63[0] < 0 )
          {
LABEL_64:
            if ( v66 )
              ((void (__fastcall *)(struct IMMDevice *, __int64))v66->lpVtbl->QueryInterface)(v66, 1);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v67);
            goto LABEL_134;
          }
          v12 = v70;
          v10 = v69;
          v33 = v74;
          v1 = v79;
          v71 = v80;
          v85 = v89;
          v75 = v90;
        }
        v66 = 0;
        v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 40LL))(v72);
        Converter = CProcessNode::CreateDummyProcessNode(**(unsigned int **)&v77.Data1, v34, &v66, v35);
        if ( Converter >= 0 )
        {
          try
          {
            Converter = 0;
            *(_QWORD *)&v77.Data1 = v66;
            ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertBefore(v71, v10, &v77);
          }
          catch ( ATL::CAtlException *v92 )
          {
            v54 = (int *)v92;
            if ( *(_DWORD *)v92 == -1073741571 )
              _o__resetstkoflw();
            v63[0] = *v54;
            Converter = v63[0];
            if ( v63[0] < 0 )
              goto LABEL_64;
            v12 = v70;
            v1 = v79;
            v71 = v80;
          }
          *((_DWORD *)v1 + 35) |= 6u;
          *v84 = 0;
          v10 = v76;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v67);
          goto LABEL_139;
        }
      }
      if ( v66 )
        ((void (__fastcall *)(struct IMMDevice *, __int64))v66->lpVtbl->QueryInterface)(v66, 1);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v67);
    goto LABEL_98;
  }
  if ( v29 != 1 )
  {
    v33 = *(struct CProcessNode **)v63;
LABEL_98:
    if ( Converter < 0 )
      goto LABEL_86;
    goto LABEL_99;
  }
  if ( *((_DWORD *)v12 + 6) != 1 || !*((_DWORD *)v1 + 78) )
  {
LABEL_99:
    v60 = 1;
    v14 = v85;
LABEL_110:
    v43 = v86;
    goto LABEL_113;
  }
  if ( !IsFixedFormatApo(*v78) )
  {
    v38 = v72;
    v39 = ((__int64 (__fastcall *)(struct IAudioMediaType *))v64->lpVtbl->GetAudioFormat)(v64);
    if ( *(_WORD *)(v39 + 2) != *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38) + 2)
      || (v40 = v64,
          v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 40LL))(v72),
          *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))v40->lpVtbl->GetAudioFormat)(v40) + 4) != *(_DWORD *)(v41 + 4)) )
    {
      if ( (*((_BYTE *)v1 + 140) & 6) == 0 )
      {
        *v84 = 0;
        v10 = v76;
        goto LABEL_139;
      }
    }
    goto LABEL_99;
  }
  v66 = 0;
  v36 = ((__int64 (__fastcall *)(struct IAudioMediaType *))v62->lpVtbl->GetAudioFormat)(v62);
  Converter = CProcessNode::CreateDummyProcessNode(*((unsigned int *)v14 + 6), v36, &v66, v37);
  if ( Converter < 0 )
  {
    if ( v66 )
      ((void (__fastcall *)(struct IMMDevice *, __int64))v66->lpVtbl->QueryInterface)(v66, 1);
    v33 = *(struct CProcessNode **)v63;
LABEL_86:
    if ( Converter == -2147024882 )
      goto LABEL_26;
LABEL_101:
    v42 = v75;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v30, v75 + 8);
    }
    if ( (*(int (__fastcall **)(_QWORD, struct IAudioProcessingObject *))(**((_QWORD **)v1 + 30) + 32LL))(
           *((_QWORD *)v1 + 30),
           *v78) < 0 )
      goto LABEL_26;
    if ( Converter != -2005073917 )
    {
      v73 = Converter;
      v68 = *(_DWORD *)v33;
      v95 = *(struct _GUID *)(v42 + 8);
    }
    ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(v71, v76);
    goto LABEL_139;
  }
  try
  {
    Converter = 0;
    *(_QWORD *)&v77.Data1 = v66;
    v10 = ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::InsertAfter(v71, v76, &v77);
    v69 = v10;
  }
  catch ( ATL::CAtlException *v93 )
  {
    v55 = (int *)v93;
    if ( *(_DWORD *)v93 == -1073741571 )
      _o__resetstkoflw();
    v63[0] = *v55;
    Converter = v63[0];
    if ( v63[0] >= 0 )
    {
      v12 = v70;
      v10 = v69;
      v1 = v79;
      v71 = v80;
      goto LABEL_92;
    }
    if ( v66 )
      ((void (__fastcall *)(struct IMMDevice *, __int64))v66->lpVtbl->QueryInterface)(v66, 1);
LABEL_134:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v62);
    if ( v81 )
      (**v81)(v81, 1);
    v1 = v79;
LABEL_148:
    v4 = v73;
    if ( v73 >= 0 )
      goto LABEL_155;
    v58[0] = SLODWORD(FLOAT_1_0);
    v49 = TrackSystemEffectBehavior(*((_QWORD *)v1 + 24), v68, (unsigned int)v73, 0, &v95, *(_QWORD *)v58);
    if ( v49 >= 0 )
      goto LABEL_155;
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids,
          (unsigned int)v49);
        goto LABEL_155;
      }
LABEL_156:
      if ( v50 != &WPP_GLOBAL_Control && (*((_DWORD *)v50 + 7) & 0x20000) != 0 && *((_BYTE *)v50 + 25) >= 4u )
      {
        v51 = "SUCCEEDED";
        if ( Converter < 0 )
          v51 = "FAILED";
        WPP_SF_qs(v50[2], 26, v4, (_DWORD)v1, (__int64)v51);
        v50 = WPP_GLOBAL_Control;
      }
    }
    if ( Converter < 0 )
    {
      if ( v50 != &WPP_GLOBAL_Control && (*((_DWORD *)v50 + 7) & 0x20000) != 0 && *((_BYTE *)v50 + 25) >= 2u )
        WPP_SF_d(v50[2], 27, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids, (unsigned int)Converter);
      AudDGTraceLoggingErrorHelper("CPipeInstance::ResolveFormatConflictsRightLeft", 0x6ABu, Converter);
    }
    if ( ppIAudioMediaType )
      ((void (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->Release)(ppIAudioMediaType);
    if ( v72 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    if ( v82 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v82 + 16LL))(v82);
    if ( v64 )
      ((void (__fastcall *)(struct IAudioMediaType *))v64->lpVtbl->Release)(v64);
    result = (unsigned int)Converter;
  }
LABEL_92:
  *((_DWORD *)v1 + 35) |= 6u;
  goto LABEL_139;
}

```

## disassembly

```asm
0x14002ac14  mov     r11, rsp
0x14002ac17  mov     [r11+10h], rbx
0x14002ac1b  mov     [r11+18h], rsi
0x14002ac1f  push    rdi
0x14002ac20  push    r12
0x14002ac22  push    r13
0x14002ac24  push    r14
0x14002ac26  push    r15
0x14002ac28  sub     rsp, 380h
0x14002ac2f  movaps  xmmword ptr [r11-38h], xmm6
0x14002ac34  mov     rax, cs:__security_cookie
0x14002ac3b  xor     rax, rsp
0x14002ac3e  mov     [rsp+3A8h+var_48], rax
0x14002ac46  mov     r12, rcx
0x14002ac49  mov     [rsp+3A8h+var_2D0], rcx
0x14002ac51  xor     esi, esi
0x14002ac53  mov     [r11-2C0h], rsi
0x14002ac5a  xorps   xmm0, xmm0
0x14002ac5d  movups  xmmword ptr [rsp+3A8h+var_240.Data1], xmm0
0x14002ac65  xorps   xmm1, xmm1
0x14002ac68  movups  [rsp+3A8h+var_250], xmm1
0x14002ac70  mov     [rsp+3A8h+var_350], rsi
0x14002ac75  mov     [r11-2B8h], rsi
0x14002ac7c  mov     [r11-310h], rsi
0x14002ac83  mov     [r11-2B0h], rsi
0x14002ac8a  lea     rdi, [rcx+10h]
0x14002ac8e  mov     [rsp+3A8h+var_318], rdi
0x14002ac96  mov     rcx, [rdi]
0x14002ac99  test    rcx, rcx
0x14002ac9c  jnz     short loc_14002ACA9
0x14002ac9e  mov     ecx, 80004005h; int
0x14002aca3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002aca9  mov     rcx, [rcx+10h]
0x14002acad  mov     rax, [rcx]
0x14002acb0  lea     rdx, [rsp+3A8h+var_310]
0x14002acb8  mov     rax, [rax+10h]
0x14002acbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002acc1  mov     r14d, eax
0x14002acc4  test    eax, eax
0x14002acc6  js      loc_14002BB59
0x14002accc  mov     rcx, [rsp+3A8h+var_310]
0x14002acd4  mov     rax, [rcx]
0x14002acd7  mov     rax, [rax+28h]
0x14002acdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ace0  mov     r14, rax
0x14002ace3  movzx   r15d, word ptr [rax+10h]
0x14002ace8  lea     rcx, [r15+12h]; cb
0x14002acec  call    cs:__imp_CoTaskMemAlloc
0x14002acf2  mov     rbx, rax
0x14002acf5  test    rax, rax
0x14002acf8  jz      loc_14002BB53
0x14002acfe  lea     r8, [r15+12h]; Size
0x14002ad02  mov     rdx, r14; Src
0x14002ad05  mov     rcx, rax; void *
0x14002ad08  call    memcpy_0
0x14002ad0d  mov     rcx, rbx; struct tWAVEFORMATEX *
0x14002ad10  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x14002ad15  movzx   edx, word ptr [rbx+10h]
0x14002ad19  add     edx, 12h; cbAudioFormatSize
0x14002ad1c  lea     r8, [rsp+3A8h+ppIAudioMediaType]; ppIAudioMediaType
0x14002ad24  mov     rcx, rbx; pAudioFormat
0x14002ad27  call    CreateAudioMediaType
0x14002ad2c  mov     r14d, eax
0x14002ad2f  mov     rcx, rbx; pv
0x14002ad32  call    cs:__imp_CoTaskMemFree
0x14002ad38  test    r14d, r14d
0x14002ad3b  js      loc_14002BB59
0x14002ad41  mov     r13, [r12+18h]
0x14002ad46  mov     [rsp+3A8h+var_328], r13
0x14002ad4e  mov     rcx, [r12]; this
0x14002ad52  test    rcx, rcx
0x14002ad55  jz      loc_14002ADF3
0x14002ad5b  cmp     [r12+78h], esi
0x14002ad60  jz      loc_14002ADE8
0x14002ad66  cmp     [rcx+0D4h], esi
0x14002ad6c  jnz     short loc_14002ADE8
0x14002ad6e  mov     [rsp+3A8h+var_300], rsi
0x14002ad76  mov     [rsp+3A8h+ppv], rsi; struct IAudioProcessingObject **
0x14002ad7b  xor     r9d, r9d; struct CConnectionInstance **
0x14002ad7e  lea     r8, [rsp+3A8h+var_300]; struct CProcessNode **
0x14002ad86  lea     rdx, _GUID_d81229b1_5a43_480c_92f7_be0f7f4eab60; struct _GUID *
0x14002ad8d  call    ?GetAPONodeAndConnection@CPipeInstance@@AEBAXAEBU_GUID@@PEAPEBVCProcessNode@@PEAPEBVCConnectionInstance@@PEAPEAUIAudioProcessingObject@@@Z; CPipeInstance::GetAPONodeAndConnection(_GUID const &,CProcessNode const * *,CConnectionInstance const * *,IAudioProcessingObject * *)
0x14002ad92  mov     r15, [rsp+3A8h+var_300]
0x14002ad9a  mov     [rsp+3A8h+var_320], r15
0x14002ada2  test    r15, r15
0x14002ada5  jnz     short loc_14002AE13
0x14002ada7  mov     [rsp+3A8h+var_300], rsi
0x14002adaf  mov     [rsp+3A8h+ppv], rsi; struct IAudioProcessingObject **
0x14002adb4  xor     r9d, r9d; struct CConnectionInstance **
0x14002adb7  lea     r8, [rsp+3A8h+var_300]; struct CProcessNode **
0x14002adbf  lea     rdx, _GUID_fc7dff56_6b8d_45a9_b4ca_266f9ac21693; struct _GUID *
0x14002adc6  mov     rcx, [r12]; this
0x14002adca  call    ?GetAPONodeAndConnection@CPipeInstance@@AEBAXAEBU_GUID@@PEAPEBVCProcessNode@@PEAPEBVCConnectionInstance@@PEAPEAUIAudioProcessingObject@@@Z; CPipeInstance::GetAPONodeAndConnection(_GUID const &,CProcessNode const * *,CConnectionInstance const * *,IAudioProcessingObject * *)
0x14002adcf  mov     r15, [rsp+3A8h+var_300]
0x14002add7  mov     [rsp+3A8h+var_320], r15
0x14002addf  test    r15, r15
0x14002ade2  jnz     short loc_14002AE13
0x14002ade4  mov     rcx, [r12]
0x14002ade8  add     rcx, 10h
0x14002adec  call    ?GetHead@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@XZ; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead(void)
0x14002adf1  jmp     short loc_14002AE08
0x14002adf3  lea     rdx, [rsp+3A8h+var_328]
0x14002adfb  call    ?GetPrev@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetPrev(__POSITION * &)
0x14002ae00  mov     r13, [rsp+3A8h+var_328]
0x14002ae08  mov     r15, [rax]
0x14002ae0b  mov     [rsp+3A8h+var_320], r15
0x14002ae13  mov     rax, [r15]
0x14002ae16  lea     rdx, [rsp+3A8h+var_350]
0x14002ae1b  mov     rcx, r15
0x14002ae1e  mov     rax, [rax+8]
0x14002ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae27  mov     r14d, eax
0x14002ae2a  test    eax, eax
0x14002ae2c  js      loc_14002BB59
0x14002ae32  mov     [rsp+3A8h+var_290], rdi
0x14002ae3a  mov     [rsp+3A8h+var_308], esi
0x14002ae41  mov     [rsp+3A8h+var_330], 1
0x14002ae49  mov     [rsp+3A8h+var_367], sil
0x14002ae4e  mov     [rsp+3A8h+var_2C8], rdi
0x14002ae56  lea     rbx, WPP_GLOBAL_Control
0x14002ae5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae64  cmp     rcx, rbx
0x14002ae67  jz      short loc_14002AE90
0x14002ae69  test    dword ptr [rcx+1Ch], 20000h
0x14002ae70  jz      short loc_14002AE90
0x14002ae72  cmp     byte ptr [rcx+19h], 4
0x14002ae76  jb      short loc_14002AE90
0x14002ae78  mov     edx, 15h
0x14002ae7d  mov     r9, r12
0x14002ae80  lea     r8, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids
0x14002ae87  mov     rcx, [rcx+10h]
0x14002ae8b  call    WPP_SF_q
0x14002ae90  test    r13, r13
0x14002ae93  jz      loc_14002BABF
0x14002ae99  mov     [rsp+3A8h+var_360], rsi
0x14002ae9e  mov     [rsp+3A8h+var_348], rsi
0x14002aea3  mov     rax, r13
0x14002aea6  mov     [rsp+3A8h+var_2F0], rax
0x14002aeae  mov     r13, [r13+8]
0x14002aeb2  mov     [rsp+3A8h+var_328], r13
0x14002aeba  mov     rdi, [rax+10h]
0x14002aebe  mov     [rsp+3A8h+var_2A0], rdi
0x14002aec6  mov     [rsp+3A8h+var_280], rdi
0x14002aece  mov     [rsp+3A8h+var_368], sil
0x14002aed3  cmp     dword ptr [rdi+28h], 2
0x14002aed7  jnz     loc_14002B785
0x14002aedd  lea     rax, [rdi+20h]
0x14002aee1  mov     [rsp+3A8h+var_298], rax
0x14002aee9  mov     r14, [rax]
0x14002aeec  mov     [rsp+3A8h+var_2F8], r14
0x14002aef4  mov     [rsp+3A8h+var_278], r14
0x14002aefc  lea     rax, [r14+28h]
0x14002af00  mov     [rsp+3A8h+var_2D8], rax
0x14002af08  cmp     [rax], rsi
0x14002af0b  jz      short loc_14002AF16
0x14002af0d  lea     rax, [r14+4]
0x14002af11  jmp     loc_14002B238
0x14002af16  lea     rax, [r14+8]
0x14002af1a  mov     [rsp+3A8h+var_338], rax
0x14002af1f  movups  xmm6, xmmword ptr [rax]
0x14002af22  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x14002af27  movdqu  xmmword ptr [rsp+3A8h+var_2E8.Data1], xmm6
0x14002af30  lea     r9, [rsp+3A8h+var_2E8]; struct _GUID
0x14002af38  lea     r8, aCreateapo; "CreateApo"
0x14002af3f  mov     rdx, rax; struct _tlgProvider_t *
0x14002af42  lea     rcx, [rsp+3A8h+var_228]; this
0x14002af4a  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBDU_GUID@@@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,_GUID)
0x14002af4f  nop
0x14002af50  mov     rcx, [r12+0F0h]
0x14002af58  lea     r8, [r14+4]
0x14002af5c  mov     qword ptr [rsp+3A8h+var_358], r8
0x14002af61  mov     rax, [rcx]
0x14002af64  mov     rdx, [rsp+3A8h+var_2D8]
0x14002af6c  mov     qword ptr [rsp+3A8h+var_380], rdx
0x14002af71  mov     rdx, [r14+38h]
0x14002af75  mov     [rsp+3A8h+ppv], rdx
0x14002af7a  mov     r9, [r12+0C0h]
0x14002af82  mov     r8d, [r8]
0x14002af85  lea     rdx, [r14+8]
0x14002af89  mov     rax, [rax+18h]
0x14002af8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af92  mov     r14d, eax
0x14002af95  lea     rcx, [rsp+3A8h+var_228]; this
0x14002af9d  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x14002afa2  test    r14d, r14d
0x14002afa5  jns     loc_14002B053
0x14002afab  cmp     r14d, 8007000Eh
0x14002afb2  jnz     short loc_14002AFCE
0x14002afb4  lea     rcx, [rsp+3A8h+var_348]
0x14002afb9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14002afbe  nop
0x14002afbf  lea     rcx, [rsp+3A8h+var_360]
0x14002afc4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14002afc9  jmp     loc_14002BAD3
0x14002afce  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afd5  cmp     rcx, rbx
0x14002afd8  jz      short loc_14002B001
0x14002afda  test    dword ptr [rcx+1Ch], 20000h
0x14002afe1  jz      short loc_14002B001
0x14002afe3  mov     rbx, [rsp+3A8h+var_338]
0x14002afe8  cmp     byte ptr [rcx+19h], 4
0x14002afec  jb      short loc_14002B006
0x14002afee  mov     edx, 16h
0x14002aff3  mov     r9, rbx
0x14002aff6  mov     rcx, [rcx+10h]
0x14002affa  call    WPP_SF__guid_
0x14002afff  jmp     short loc_14002B006
0x14002b001  mov     rbx, [rsp+3A8h+var_338]
0x14002b006  mov     rdx, [rsp+3A8h+var_2F0]
0x14002b00e  mov     rcx, [rsp+3A8h+var_290]
0x14002b016  call    ?RemoveAt@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::RemoveAt(__POSITION *)
0x14002b01b  mov     rdi, qword ptr [rsp+3A8h+var_358]
0x14002b020  mov     eax, [rdi]
0x14002b022  test    eax, eax
0x14002b024  jz      short loc_14002B041
0x14002b026  mov     ecx, 1
0x14002b02b  mov     [rsp+3A8h+var_308], r14d
0x14002b033  movups  xmm0, xmmword ptr [rbx]
0x14002b036  movdqu  [rsp+3A8h+var_250], xmm0
0x14002b03f  jmp     short loc_14002B043
0x14002b041  mov     ecx, esi
0x14002b043  test    ecx, ecx
0x14002b045  cmovz   eax, [rsp+3A8h+var_330]
0x14002b04a  mov     [rsp+3A8h+var_330], eax
0x14002b04e  jmp     loc_14002BA40
0x14002b053  mov     rax, qword ptr [rsp+3A8h+var_358]
0x14002b058  cmp     [rax], esi
0x14002b05a  jz      loc_14002B230
0x14002b060  mov     [rsp+3A8h+var_340], rsi
0x14002b065  lea     rax, [rsp+3A8h+var_2B8]
0x14002b06d  mov     [rsp+3A8h+ppv], rax; int
0x14002b072  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14002b079  xor     edx, edx; pUnkOuter
0x14002b07b  lea     r8d, [rdx+17h]; dwClsContext
0x14002b07f  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14002b086  call    cs:__imp_CoCreateInstance
0x14002b08c  mov     r14d, eax
0x14002b08f  test    eax, eax
0x14002b091  jns     short loc_14002B0A2
0x14002b093  lea     rcx, [rsp+3A8h+var_340]
0x14002b098  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14002b09d  jmp     loc_14002AFB4
0x14002b0a2  mov     rcx, [rsp+3A8h+var_2B8]
0x14002b0aa  mov     rax, [rcx]
0x14002b0ad  lea     r8, [rsp+3A8h+var_340]
0x14002b0b2  mov     rdx, [r12+0C0h]
0x14002b0ba  mov     rax, [rax+28h]
0x14002b0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b0c3  mov     r14d, eax
0x14002b0c6  test    eax, eax
0x14002b0c8  js      short loc_14002B093
0x14002b0ca  mov     r14, [rsp+3A8h+var_338]
0x14002b0cf  movups  xmm6, xmmword ptr [r14]
0x14002b0d3  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x14002b0d8  movdqu  xmmword ptr [rsp+3A8h+var_2E8.Data1], xmm6
0x14002b0e1  lea     r9, [rsp+3A8h+var_2E8]; struct _GUID
0x14002b0e9  lea     r8, aInitializesyst; "InitializeSystemEffect"
0x14002b0f0  mov     rdx, rax; struct _tlgProvider_t *
0x14002b0f3  lea     rcx, [rsp+3A8h+var_138]; this
0x14002b0fb  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBDU_GUID@@@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,_GUID)
0x14002b100  nop
0x14002b101  mov     rax, [rsp+3A8h+var_2F8]
0x14002b109  movups  xmm0, xmmword ptr [rax+18h]
0x14002b10d  movdqu  xmmword ptr [rsp+3A8h+var_2E8.Data1], xmm0
0x14002b116  mov     eax, [r12+80h]
0x14002b11e  mov     [rsp+3A8h+var_380], eax; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x14002b122  lea     r9, [rsp+3A8h+var_2E8]; struct _GUID
0x14002b12a  mov     r8, r14; struct _GUID *
0x14002b12d  mov     rax, [rsp+3A8h+var_2D8]
0x14002b135  mov     rdx, [rax]; struct IAudioProcessingObject *
0x14002b138  mov     rcx, [rsp+3A8h+var_340]; struct IMMDevice *
0x14002b13d  call    ?InitializeSystemEffectsInterface@@YAJPEAUIMMDevice@@PEAUIAudioProcessingObject@@PEAU_GUID@@U3@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUIAudioSystemEffects2@@@Z; InitializeSystemEffectsInterface(IMMDevice *,IAudioProcessingObject *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioSystemEffects2 * *)
0x14002b142  mov     r14d, eax
0x14002b145  lea     rcx, [rsp+3A8h+var_138]; this
0x14002b14d  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x14002b152  test    r14d, r14d
0x14002b155  jns     loc_14002B217
0x14002b15b  cmp     r14d, 8007000Eh
0x14002b162  jz      loc_14002B093
0x14002b168  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b16f  cmp     rcx, rbx
0x14002b172  jz      short loc_14002B19B
0x14002b174  test    dword ptr [rcx+1Ch], 20000h
0x14002b17b  jz      short loc_14002B19B
0x14002b17d  mov     rbx, [rsp+3A8h+var_338]
0x14002b182  cmp     byte ptr [rcx+19h], 4
0x14002b186  jb      short loc_14002B1A0
0x14002b188  mov     edx, 17h
0x14002b18d  mov     r9, rbx
0x14002b190  mov     rcx, [rcx+10h]
0x14002b194  call    WPP_SF__guid_
0x14002b199  jmp     short loc_14002B1A0
0x14002b19b  mov     rbx, [rsp+3A8h+var_338]
0x14002b1a0  mov     rcx, [r12+0F0h]
0x14002b1a8  mov     rax, [rcx]
0x14002b1ab  mov     rdx, [rsp+3A8h+var_2D8]
0x14002b1b3  mov     rdx, [rdx]
0x14002b1b6  mov     rax, [rax+20h]
0x14002b1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b1bf  test    eax, eax
  ... truncated ...
```
