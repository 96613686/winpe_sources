# CCommandQueue<0>::ExecuteCommandListsImpl(uint,ID3D12CommandList * const *)

- ea: `0x180009fc0`
- end: `0x18000ab41`
- name: `?ExecuteCommandListsImpl@?$CCommandQueue@$0A@@@QEAAXIPEBQEAUID3D12CommandList@@@Z`
- size: `2945`
- prototype: `__int64 __fastcall(CCastableCommandQueue *this, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180009510`

## callees

- `0x180009fc0`
- `0x18000ab50`
- `0x18000ac4c`
- `0x18000b010`
- `0x18000b2a0`
- `0x18000b630`
- `0x18000b6a0`
- `0x18000ccfc`
- `0x180022150`
- `0x1800221bc`
- `0x180048b10`
- `0x18007c31c`
- `0x18007ccf8`
- `0x1800a09c0`
- `0x1800a6754`
- `0x1800a6af4`
- `0x1800acb34`
- `0x1800acf38`
- `0x1800b97f8`
- `0x1800b9818`
- `0x180101b90`
- `0x18011a57c`
- `0x180128200`
- `0x18012cd00`
- `0x180224e94`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18000a217`
- `msvcp_win!_Mtx_unlock` at `0x18000a221`
- `msvcp_win!_Mtx_unlock` at `0x18000a217`
- `msvcp_win!_Mtx_unlock` at `0x18000a221`

## string_xrefs

- `0x18000a179`: `Node mask mismatch between command list and command queue.`
- `0x18000a2b2`: `Command lists must be successfully closed before execution.`
- `0x18000a30c`: `Command lists must be closed before execution.`
- `0x18000a366`: `Command lists must have matching type to queue.`
- `0x18000a8e3`: `A bundle cannot be passed to ExecuteCommandLists.`
- `0x18000aa2d`: `Up to %d swapchains can be written to by a single ExecuteCommandLists call. `

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CCommandQueue<0>::ExecuteCommandListsImpl(
        CCastableCommandQueue *this,
        unsigned int a2,
        struct ID3D12CommandList *const *a3)
{
  unsigned int v3; // r15d
  struct _Mtx_internal_imp_t *v5; // r14
  _QWORD *v6; // r13
  __int64 v7; // rax
  __int64 *v8; // r12
  __int64 v9; // rax
  __int64 v10; // rax
  char v11; // di
  struct ID3D12CommandList *const *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rax
  struct ID3D12CommandList *v15; // r15
  ID3D12CommandList_vtbl *v16; // rdx
  int v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // esi
  ID3D12CommandList_vtbl *v21; // rsi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  __int64 v23; // r13
  __int64 v24; // r12
  _QWORD *v25; // rcx
  ID3D12CommandList_vtbl *v26; // rdi
  __int64 Data; // rsi
  __int64 v28; // rax
  HRESULT (__fastcall *v29)(ID3D12DeviceChild *, const _GUID *, void **); // rcx
  std::_Ref_count_base *GetDevice; // rax
  __int64 v31; // rsi
  __int64 v32; // rax
  HRESULT (__fastcall *v33)(IUnknown *, const _GUID *, void **); // rcx
  std::_Ref_count_base *v34; // rax
  __int64 v35; // rsi
  __int64 v36; // rax
  unsigned int (__fastcall *v37)(IUnknown *); // rcx
  std::_Ref_count_base *Release; // rax
  __int64 v39; // rsi
  __int64 v40; // rax
  HRESULT (__fastcall *v41)(ID3D12Object *, const _GUID *, unsigned int, const void *); // rcx
  std::_Ref_count_base *SetPrivateData; // rax
  D3D12_COMMAND_LIST_TYPE (__fastcall *GetPrivateData)(ID3D12CommandList *); // rcx
  __int64 SharedAutoDebugObjectNameW; // rax
  HRESULT (__fastcall *AddRef)(ID3D12DeviceChild *, const _GUID *, void **); // rax
  HRESULT (__fastcall *SetName)(ID3D12Object *, const _GUID *, const IUnknown *); // rax
  HRESULT (__fastcall *GetType)(ID3D12Object *, const wchar_t *); // rax
  __int64 v48; // rdi
  __int64 *v49; // rax
  __int64 *v50; // rdx
  ID3D12CommandList_vtbl *v51; // rax
  ID3D12CommandList_vtbl **v52; // rdx
  int v53; // eax
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rcx
  _QWORD *v58; // rsi
  _QWORD *v59; // r12
  _QWORD *v60; // rdi
  _QWORD *v61; // r15
  char v62; // [rsp+30h] [rbp-1B8h]
  __int64 v63; // [rsp+38h] [rbp-1B0h] BYREF
  int v64; // [rsp+40h] [rbp-1A8h]
  CCastableCommandQueue *v65; // [rsp+48h] [rbp-1A0h] BYREF
  int v66; // [rsp+50h] [rbp-198h]
  ID3D12CommandList_vtbl *v67; // [rsp+58h] [rbp-190h] BYREF
  _Mtx_t v68; // [rsp+60h] [rbp-188h]
  char v69; // [rsp+68h] [rbp-180h]
  CTrackedWorkload *v70; // [rsp+70h] [rbp-178h]
  char *v71; // [rsp+78h] [rbp-170h]
  CCastableCommandQueue *v72; // [rsp+80h] [rbp-168h]
  char v73[16]; // [rsp+88h] [rbp-160h] BYREF
  void **v74; // [rsp+98h] [rbp-150h] BYREF
  int v75; // [rsp+A0h] [rbp-148h]
  __int128 v76; // [rsp+A8h] [rbp-140h]
  void **v77; // [rsp+B8h] [rbp-130h] BYREF
  int v78; // [rsp+C0h] [rbp-128h]
  __int128 v79; // [rsp+C8h] [rbp-120h]
  void **v80; // [rsp+D8h] [rbp-110h] BYREF
  int v81; // [rsp+E0h] [rbp-108h]
  __int128 v82; // [rsp+E8h] [rbp-100h]
  void **v83; // [rsp+F8h] [rbp-F0h] BYREF
  int v84; // [rsp+100h] [rbp-E8h]
  __int128 v85; // [rsp+108h] [rbp-E0h]
  void **v86; // [rsp+118h] [rbp-D0h] BYREF
  int v87; // [rsp+120h] [rbp-C8h]
  __int128 v88; // [rsp+128h] [rbp-C0h]
  void **pExceptionObject; // [rsp+138h] [rbp-B0h] BYREF
  int v90; // [rsp+140h] [rbp-A8h]
  __int128 v91; // [rsp+148h] [rbp-A0h]
  void **v92; // [rsp+158h] [rbp-90h] BYREF
  int v93; // [rsp+160h] [rbp-88h]
  __int128 v94; // [rsp+168h] [rbp-80h]
  void **v95; // [rsp+178h] [rbp-70h] BYREF
  int v96; // [rsp+180h] [rbp-68h]
  __int128 v97; // [rsp+188h] [rbp-60h]
  char v98[80]; // [rsp+198h] [rbp-50h] BYREF
  char v101; // [rsp+208h] [rbp+20h]

  v3 = a2;
  v64 = 0;
  v5 = (CCastableCommandQueue *)((char *)this + 368);
  v71 = (char *)this + 368;
  std::_Mutex_base::lock((CCastableCommandQueue *)((char *)this + 368));
  v6 = (_QWORD *)((char *)this + 584);
  v7 = *((_QWORD *)this + 73);
  if ( v7 != *((_QWORD *)this + 74) )
    *((_QWORD *)this + 74) = v7;
  v8 = (__int64 *)((char *)this + 608);
  v9 = *((_QWORD *)this + 76);
  if ( v9 != *((_QWORD *)this + 77) )
    *((_QWORD *)this + 77) = v9;
  v10 = *((_QWORD *)this + 19);
  v68 = (_Mtx_t)(v10 + 4832);
  v69 = 0;
  if ( *(_BYTE *)(v10 + 4912) )
  {
    if ( v10 == -4832 )
      std::_Throw_system_error(1);
    std::_Mutex_base::lock((std::_Mutex_base *)(v10 + 4832));
    v69 = 1;
  }
  v11 = 0;
  v62 = 0;
  v72 = this;
  v12 = a3;
  v70 = CCastableCommandQueue::CompleteTrackedWorkloadPairs(this, v3, a3);
  v101 = 0;
  v14 = 0;
  v66 = 0;
  while ( (unsigned int)v14 < v3 )
  {
    v15 = v12[v14];
    v16 = v15[-2].__vftable;
    if ( v16 )
      v16[2].GetType = (D3D12_COMMAND_LIST_TYPE (__fastcall *)(ID3D12CommandList *))_InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 19) + 7752LL));
    if ( !LODWORD(v15[17].__vftable) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
        1131,
        0);
      v74 = &_com_error::`vftable';
      v75 = -2147024809;
      v76 = 0;
      throw (_com_error *)&v74;
    }
    v17 = (int)v15[3].__vftable;
    if ( v17 == 1 )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_BUNDLENOTSUPPORTED,
        "A bundle cannot be passed to ExecuteCommandLists.");
      v77 = &_com_error::`vftable';
      v78 = -2147024809;
      v79 = 0;
      throw (_com_error *)&v77;
    }
    if ( v17 != *((_DWORD *)this + 113) )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_COMMANDLISTMISMATCH,
        "Command lists must have matching type to queue.");
      v80 = &_com_error::`vftable';
      v81 = -2147024809;
      v82 = 0;
      throw (_com_error *)&v80;
    }
    if ( v15[19].__vftable != (ID3D12CommandList_vtbl *)-1LL )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_OPENCOMMANDLIST,
        "Command lists must be closed before execution.");
      v83 = &_com_error::`vftable';
      v84 = -2147024809;
      v85 = 0;
      throw (_com_error *)&v83;
    }
    if ( SLODWORD(v15[18].__vftable) < 0 )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_FAILEDCOMMANDLIST,
        "Command lists must be successfully closed before execution.");
      v86 = &_com_error::`vftable';
      v87 = -2147024809;
      v88 = 0;
      throw (_com_error *)&v86;
    }
    if ( *((_DWORD *)this + 116) == (*((_DWORD *)this + 116) & HIDWORD(v15[3].__vftable)) )
    {
      v64 = 0;
    }
    else
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_NODE_MASK_MISMATCH,
        "Node mask mismatch between command list and command queue.");
      ThrowFailure(-2147024809);
      v64 = -2147024809;
    }
    v18 = ((__int64 (__fastcall *)(struct ID3D12CommandList *))v15[-8].GetPrivateData)(&v15[-8]);
    if ( v18 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v90 = v18;
      v91 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v21 = v15[34].__vftable;
    QueryInterface = v21->QueryInterface;
    while ( (char *)QueryInterface != (char *)v21 )
    {
      v23 = *((_QWORD *)QueryInterface + 2);
      v63 = v23;
      v24 = *(_QWORD *)(v23 + 320);
      v25 = *(_QWORD **)(v24 + 8);
      if ( v25 )
      {
        v67 = 0;
        v65 = 0;
        if ( (*(int (__fastcall **)(_QWORD, GUID *, ID3D12CommandList_vtbl **, GUID *, CCastableCommandQueue **))(*(_QWORD *)*v25 + 40LL))(
               *v25,
               &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
               &v67,
               &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
               &v65) >= 0 )
        {
          if ( v67 != (ID3D12CommandList_vtbl *)v23 || v65 != this )
          {
            NDXGI::CDevice::RemoveDevice(*(NDXGI::CDevice **)(*((_QWORD *)this + 19) + 760LL), -2005270485);
            v95 = &_com_error::`vftable';
            v96 = -2147024809;
            v97 = 0;
            throw (_com_error *)&v95;
          }
          v53 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(v24 + 8) + 48LL))(**(_QWORD **)(v24 + 8));
          ThrowFailure(v53);
        }
        if ( v65 )
          (*(void (__fastcall **)(CCastableCommandQueue *))(*(_QWORD *)v65 + 16LL))(v65);
        if ( v67 )
          (*((void (__fastcall **)(ID3D12CommandList_vtbl *))v67->QueryInterface + 2))(v67);
      }
      if ( (*(_BYTE *)(v24 + 16) & 1) != 0 )
      {
        _mm_lfence();
        v54 = *((_QWORD *)this + 41);
        v55 = *(_QWORD *)(v54
                        + 16
                        * (*((_QWORD *)this + 44)
                         & (0x100000001B3LL
                          * (HIBYTE(v63)
                           ^ (0x100000001B3LL
                            * (BYTE6(v63)
                             ^ (0x100000001B3LL
                              * (BYTE5(v63)
                               ^ (0x100000001B3LL
                                * (BYTE4(v63)
                                 ^ (0x100000001B3LL
                                  * (BYTE3(v63)
                                   ^ (0x100000001B3LL
                                    * (BYTE2(v63)
                                     ^ (0x100000001B3LL
                                      * (BYTE1(v63) ^ (0x100000001B3LL * ((unsigned __int8)v23 ^ 0xCBF29CE484222325uLL)))))))))))))))))
                        + 8);
        if ( v55 == *((_QWORD *)this + 39) )
        {
LABEL_95:
          v55 = 0;
        }
        else
        {
          while ( v23 != *(_QWORD *)(v55 + 16) )
          {
            if ( v55 == *(_QWORD *)(v54
                                  + 16
                                  * (*((_QWORD *)this + 44)
                                   & (0x100000001B3LL
                                    * (HIBYTE(v63)
                                     ^ (0x100000001B3LL
                                      * (BYTE6(v63)
                                       ^ (0x100000001B3LL
                                        * (BYTE5(v63)
                                         ^ (0x100000001B3LL
                                          * (BYTE4(v63)
                                           ^ (0x100000001B3LL
                                            * (BYTE3(v63)
                                             ^ (0x100000001B3LL
                                              * (BYTE2(v63)
                                               ^ (0x100000001B3LL
                                                * (BYTE1(v63)
                                                 ^ (0x100000001B3LL * ((unsigned __int8)v23 ^ 0xCBF29CE484222325uLL)))))))))))))))))) )
              goto LABEL_95;
            v55 = *(_QWORD *)(v55 + 8);
          }
        }
        if ( !v55 || v55 == *((_QWORD *)this + 39) )
        {
          if ( *((_QWORD *)this + 40) >= 8u )
          {
            CDevice::ReportRetailValidationErrorF(
              (CDevice *)(*((_QWORD *)this + 19) + 288LL),
              D3D12_MESSAGE_ID_COMMAND_QUEUE_TOO_MANY_SWAPCHAIN_REFERENCES,
              "Up to %d swapchains can be written to by a single ExecuteCommandLists call. ",
              8);
            ThrowFailure(-2147024809);
          }
          if ( *(_BYTE *)(v23 + 392) == 4 )
            v56 = 0;
          else
            v56 = *(_QWORD *)(v23 + 400);
          LODWORD(v65) = *(_DWORD *)(v56 + 248);
          v57 = *((_QWORD *)this + 19);
          if ( *(_DWORD *)(v57 + 2832) )
            LODWORD(v65) = TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,88,void>,void,unsigned int,D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE>::Call<CDevice>(
                             v57,
                             v57 + 8288,
                             v23 + 416);
          std::_Hash<std::_Umap_traits<CResource *,unsigned int,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,unsigned int>>,0>>::emplace<CResource * &,unsigned int &>(
            (char *)this + 304,
            v98,
            &v63,
            &v65);
        }
      }
      QueryInterface = *(HRESULT (__fastcall **)(IUnknown *, const _GUID *, void **))QueryInterface;
      v6 = (_QWORD *)((char *)this + 584);
      v8 = (__int64 *)((char *)this + 608);
    }
    v26 = v15[-2].__vftable;
    if ( v26 )
    {
      Data = CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(v26->SetPrivateDataInterface);
      Smtx_lock_shared((_Smtx_t *)Data);
      Smtx_unlock_shared((_Smtx_t *)Data);
      v28 = *(_QWORD *)(Data + 24);
      if ( v28 )
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
      v29 = *(HRESULT (__fastcall **)(ID3D12DeviceChild *, const _GUID *, void **))(Data + 24);
      v26->SetName = *(HRESULT (__fastcall **)(ID3D12Object *, const wchar_t *))(Data + 16);
      GetDevice = (std::_Ref_count_base *)v26->GetDevice;
      v26->GetDevice = v29;
      if ( GetDevice )
        std::_Ref_count_base::_Decref(GetDevice);
      v31 = CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(v26->SetPrivateDataInterface);
      Smtx_lock_shared((_Smtx_t *)v31);
      Smtx_unlock_shared((_Smtx_t *)v31);
      v32 = *(_QWORD *)(v31 + 40);
      if ( v32 )
        _InterlockedIncrement((volatile signed __int32 *)(v32 + 8));
      v33 = *(HRESULT (__fastcall **)(IUnknown *, const _GUID *, void **))(v31 + 40);
      v26->GetType = *(D3D12_COMMAND_LIST_TYPE (__fastcall **)(ID3D12CommandList *))(v31 + 32);
      v34 = (std::_Ref_count_base *)v26[1].QueryInterface;
      v26[1].QueryInterface = v33;
      if ( v34 )
        std::_Ref_count_base::_Decref(v34);
      v35 = CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(this);
      Smtx_lock_shared((_Smtx_t *)v35);
      Smtx_unlock_shared((_Smtx_t *)v35);
      v36 = *(_QWORD *)(v35 + 24);
      if ( v36 )
        _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
      v37 = *(unsigned int (__fastcall **)(IUnknown *))(v35 + 24);
      v26[1].AddRef = *(unsigned int (__fastcall **)(IUnknown *))(v35 + 16);
      Release = (std::_Ref_count_base *)v26[1].Release;
      v26[1].Release = v37;
      if ( Release )
        std::_Ref_count_base::_Decref(Release);
      v39 = CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(this);
      Smtx_lock_shared((_Smtx_t *)v39);
      Smtx_unlock_shared((_Smtx_t *)v39);
      v40 = *(_QWORD *)(v39 + 40);
      if ( v40 )
        _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
      v41 = *(HRESULT (__fastcall **)(ID3D12Object *, const _GUID *, unsigned int, const void *))(v39 + 40);
      v26[1].GetPrivateData = *(HRESULT (__fastcall **)(ID3D12Object *, const _GUID *, unsigned int *, void *))(v39 + 32);
      SetPrivateData = (std::_Ref_count_base *)v26[1].SetPrivateData;
      v26[1].SetPrivateData = v41;
      if ( SetPrivateData )
        std::_Ref_count_base::_Decref(SetPrivateData);
      GetPrivateData = (D3D12_COMMAND_LIST_TYPE (__fastcall *)(ID3D12CommandList *))v26[1].GetPrivateData;
      if ( !GetPrivateData )
      {
        SharedAutoDebugObjectNameW = CPrivateDataImpl<ID3D12CommandQueue1>::GetSharedAutoDebugObjectNameW(this);
        std::shared_ptr<DriverStateObject>::operator=(&v26[1].GetPrivateData, SharedAutoDebugObjectNameW);
        GetPrivateData = (D3D12_COMMAND_LIST_TYPE (__fastcall *)(ID3D12CommandList *))v26[1].GetPrivateData;
      }
      v26[2].AddRef = (unsigned int (__fastcall *)(IUnknown *))*((_QWORD *)this + 20);
      AddRef = (HRESULT (__fastcall *)(ID3D12DeviceChild *, const _GUID *, void **))v26[1].AddRef;
      if ( AddRef && *((_QWORD *)AddRef + 3) > 0xFu )
        AddRef = *(HRESULT (__fastcall **)(ID3D12DeviceChild *, const _GUID *, void **))AddRef;
      v26[1].GetDevice = AddRef;
      if ( GetPrivateData && *((_QWORD *)GetPrivateData + 3) > 7u )
        GetPrivateData = *(D3D12_COMMAND_LIST_TYPE (__fastcall **)(ID3D12CommandList *))GetPrivateData;
      v26[1].GetType = GetPrivateData;
      SetName = (HRESULT (__fastcall *)(ID3D12Object *, const _GUID *, const IUnknown *))v26->SetName;
      if ( SetName && *((_QWORD *)SetName + 3) > 0xFu )
        SetName = *(HRESULT (__fastcall **)(ID3D12Object *, const _GUID *, const IUnknown *))SetName;
      v26[1].SetPrivateDataInterface = SetName;
      GetType = (HRESULT (__fastcall *)(ID3D12Object *, const wchar_t *))v26->GetType;
      if ( GetType && *((_QWORD *)GetType + 3) > 7u )
        GetType = *(HRESULT (__fastcall **)(ID3D12Object *, const wchar_t *))GetType;
      v26[1].SetName = GetType;
      v8 = (__int64 *)((char *)this + 608);
    }
    v48 = CCommandList<ID3D12GraphicsCommandList11>::CastFrom(v15);
    v49 = (__int64 *)CCommandList<ID3D12GraphicsCommandList11>::DDIHandle(v48, v73);
    v50 = (__int64 *)v6[1];
    if ( v50 == (__int64 *)v6[2] )
    {
      std::vector<IUseCounted *>::_Emplace_reallocate<IUseCounted * const &>(v6, v50, v49);
    }
    else
    {
      v13 = *v49;
      *v50 = *v49;
      v6[1] += 8LL;
    }
    v51 = v15[-12].__vftable;
    v67 = v51;
    v52 = (ID3D12CommandList_vtbl **)v8[1];
    if ( v52 == (ID3D12CommandList_vtbl **)v8[2] )
    {
      std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 &>(v8, v52, &v67);
    }
    else
    {
      *v52 = v51;
      v8[1] += 8;
    }
    if ( !LODWORD(v15[3].__vftable) )
    {
      if ( *(_BYTE *)(v48 + 1725) )
      {
        if ( !v101 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
            1209,
            0);
          v92 = &_com_error::`vftable';
          v93 = -2147024809;
          v94 = 0;
          throw (_com_error *)&v92;
        }
        v101 = 0;
      }
      if ( *(_BYTE *)(v48 + 1724) )
        v101 = 1;
    }
    v11 = LOBYTE(v15[13].__vftable) | v62;
    v62 = v11;
    v14 = (unsigned int)++v66;
    v3 = a2;
    v12 = a3;
  }
  if ( v101 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
      1210,
      0);
    ThrowFailure(-2147024809);
  }
  if ( !v11 || *(_BYTE *)(*((_QWORD *)this + 19) + 4913LL) )
  {
    if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
      McTemplateU0pqPR1_EtwEventWriteTransfer(
        v13,
        (unsigned int)EventD3D12StartExecuteCommandLists,
        *((_QWORD *)this + 20),
        (v8[1] - *((_QWORD *)this + 76)) >> 3,
        *((_QWORD *)this + 76));
    TableFunctionTraits<2>::Detail::InvokerImpl<TableFunctionTraitsImpl<2>::FunctionTraits<83,2,void>,void,void,D3D12DDI_HCOMMANDQUEUE,unsigned int,D3D12DDI_HCOMMANDLIST const *>::Call<CCommandQueue<0>>(
      this,
      (char *)this + 640,
      (__int64)(v6[1] - *v6) >> 3);
    if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
      McTemplateU0pqPR1_EtwEventWriteTransfer(
        v19,
        (unsigned int)EventD3D12StopExecuteCommandLists,
        *((_QWORD *)this + 20),
        (v8[1] - *v8) >> 3,
        *v8);
  }
  else
  {
    v58 = (_QWORD *)*v6;
    v59 = (_QWORD *)v6[1];
    v60 = (_QWORD *)((char *)this + 160);
    while ( v58 != v59 )
    {
      v61 = (_QWORD *)(*v58 - 2272LL);
      if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
      {
        McTemplateU0pp_EtwEventWriteTransfer(v13, EventD3D12StartExecuteCommandList, *v60, *v61);
        v60 = (_QWORD *)((char *)this + 160);
      }
      TableFunctionTraits<2>::Detail::InvokerImpl<TableFunctionTraitsImpl<2>::FunctionTraits<83,2,void>,void,void,D3D12DDI_HCOMMANDQUEUE,unsigned int,D3D12DDI_HCOMMANDLIST const *>::Call<CCommandQueue<0>>(
        this,
        (char *)this + 640,
        1);
      if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
        McTemplateU0pp_EtwEventWriteTransfer(v13, EventD3D12StopExecuteCommandList, *v60, *v61);
      else
        v60 = (_QWORD *)((char *)this + 160);
      ++v58;
    }
  }
  if ( v70 )
    CTrackedWorkload::SignalTrackedWorkload(v70);
  std::_Hash<std::_Umap_traits<CResource *,unsigned int,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,unsigned int>>,0>>::clear((char *)this + 304);
  if ( v69 )
    _Mtx_unlock(v68);
  _Mtx_unlock(v5);
  v20 = v64;
  if ( v64 < 0 )
  {
    if ( v64 == -2147467259 || v64 == -2147024809 )
      v20 = -2005270527;
    NDXGI::CDevice::RemoveDevice(*(NDXGI::CDevice **)(*((_QWORD *)this + 19) + 760LL), v20);
  }
}

```

## disassembly

```asm
0x180009fc0  mov     [rsp+arg_10], r8
0x180009fc5  mov     [rsp+arg_8], edx
0x180009fc9  mov     [rsp+arg_0], rcx
0x180009fce  push    rbx
0x180009fcf  push    rsi
0x180009fd0  push    rdi
0x180009fd1  push    r12
0x180009fd3  push    r13
0x180009fd5  push    r14
0x180009fd7  push    r15
0x180009fd9  sub     rsp, 1B0h
0x180009fe0  mov     r15d, edx
0x180009fe3  mov     rbx, rcx
0x180009fe6  xor     esi, esi
0x180009fe8  mov     [rsp+1E8h+var_1A8], esi
0x180009fec  lea     r14, [rcx+170h]
0x180009ff3  mov     [rsp+1E8h+var_170], r14
0x180009ff8  mov     rcx, r14; this
0x180009ffb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18000a000  nop
0x18000a001  lea     r13, [rbx+248h]
0x18000a008  mov     rax, [r13+0]
0x18000a00c  cmp     rax, [r13+8]
0x18000a010  jz      short loc_18000A016
0x18000a012  mov     [r13+8], rax
0x18000a016  lea     r12, [rbx+260h]
0x18000a01d  mov     rax, [r12]
0x18000a021  cmp     rax, [r12+8]
0x18000a026  jz      short loc_18000A02D
0x18000a028  mov     [r12+8], rax
0x18000a02d  mov     rax, [rbx+98h]
0x18000a034  lea     rsi, [rax+12E0h]
0x18000a03b  mov     [rsp+1E8h+var_188], rsi
0x18000a040  mov     [rsp+1E8h+var_180], 0
0x18000a045  cmp     byte ptr [rax+1330h], 0
0x18000a04c  jnz     loc_18000A72F
0x18000a052  xor     dil, dil
0x18000a055  mov     [rsp+1E8h+var_1B8], dil
0x18000a05a  mov     [rsp+1E8h+var_168], rbx
0x18000a062  mov     rsi, [rsp+1E8h+arg_10]
0x18000a06a  mov     r8, rsi; struct ID3D12CommandList **
0x18000a06d  mov     edx, r15d; unsigned int
0x18000a070  mov     rcx, rbx; this
0x18000a073  call    ?CompleteTrackedWorkloadPairs@CCastableCommandQueue@@IEAAPEAVCTrackedWorkload@@IPEBQEAUID3D12CommandList@@@Z; CCastableCommandQueue::CompleteTrackedWorkloadPairs(uint,ID3D12CommandList * const *)
0x18000a078  mov     [rsp+1E8h+var_178], rax
0x18000a07d  mov     byte ptr [rsp+1E8h+arg_18], dil
0x18000a085  xor     eax, eax
0x18000a087  mov     [rsp+1E8h+var_198], eax
0x18000a08b  cmp     eax, r15d
0x18000a08e  jnb     loc_18000A1A1
0x18000a094  mov     r15, [rsi+rax*8]
0x18000a098  mov     rdx, [r15-10h]
0x18000a09c  test    rdx, rdx
0x18000a09f  jz      short loc_18000A0C0
0x18000a0a1  mov     rax, [rbx+98h]
0x18000a0a8  mov     ecx, 1
0x18000a0ad  lock xadd [rax+1E48h], rcx
0x18000a0b6  inc     rcx
0x18000a0b9  mov     [rdx+0D0h], rcx
0x18000a0c0  cmp     dword ptr [r15+88h], 0
0x18000a0c8  jz      loc_18000A247
0x18000a0ce  mov     eax, [r15+18h]
0x18000a0d2  cmp     eax, 1
0x18000a0d5  jz      loc_18000A8D5
0x18000a0db  cmp     eax, [rbx+1C4h]
0x18000a0e1  jnz     loc_18000A358
0x18000a0e7  cmp     qword ptr [r15+98h], 0FFFFFFFFFFFFFFFFh
0x18000a0ef  jnz     loc_18000A2FE
0x18000a0f5  cmp     dword ptr [r15+90h], 0
0x18000a0fd  jl      loc_18000A2A4
0x18000a103  mov     ecx, [rbx+1D0h]
0x18000a109  mov     eax, [r15+1Ch]
0x18000a10d  and     eax, ecx
0x18000a10f  cmp     ecx, eax
0x18000a111  jnz     short loc_18000A16B
0x18000a113  mov     [rsp+1E8h+var_1A8], 0
0x18000a11b  lea     rcx, [r15-40h]
0x18000a11f  mov     rax, [rcx]
0x18000a122  mov     rax, [rax+18h]
0x18000a126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12b  mov     ecx, eax
0x18000a12d  test    eax, eax
0x18000a12f  jns     loc_18000A3B2
0x18000a135  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a13c  mov     [rsp+1E8h+pExceptionObject], rax
0x18000a144  mov     [rsp+1E8h+var_A8], ecx
0x18000a14b  xorps   xmm0, xmm0
0x18000a14e  movdqu  [rsp+1E8h+var_A0], xmm0
0x18000a157  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a15e  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x18000a166  call    _CxxThrowException_0
0x18000a16b  mov     rcx, [rbx+98h]
0x18000a172  add     rcx, 120h; this
0x18000a179  lea     r8, aNodeMaskMismat_5; "Node mask mismatch between command list"...
0x18000a180  mov     edx, 386h; enum D3D12_MESSAGE_ID
0x18000a185  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18000a18a  mov     ecx, 80070057h; int
0x18000a18f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18000a194  mov     [rsp+1E8h+var_1A8], 80070057h
0x18000a19c  jmp     loc_18000A11B
0x18000a1a1  cmp     byte ptr [rsp+1E8h+arg_18], 0
0x18000a1a9  jnz     loc_18000AA69
0x18000a1af  test    dil, dil
0x18000a1b2  jnz     loc_18000AA9A
0x18000a1b8  test    cs:Microsoft_Windows_Direct3D12EnableBits, 4
0x18000a1bf  jnz     loc_18000AAC2
0x18000a1c5  mov     r9, [r13+0]
0x18000a1c9  lea     rdx, [rbx+280h]
0x18000a1d0  mov     r8, [r13+8]
0x18000a1d4  sub     r8, r9
0x18000a1d7  sar     r8, 3
0x18000a1db  mov     rcx, rbx
0x18000a1de  call    ??$Call@V?$CCommandQueue@$0A@@@@?$InvokerImpl@U?$FunctionTraits@$0FD@$01X@?$TableFunctionTraitsImpl@$01@@XXUD3D12DDI_HCOMMANDQUEUE@@IPEBUD3D12DDI_HCOMMANDLIST@@@Detail@?$TableFunctionTraits@$01@@SAXPEAV?$CCommandQueue@$0A@@@UD3D12DDI_HCOMMANDQUEUE@@IPEBUD3D12DDI_HCOMMANDLIST@@@Z; TableFunctionTraits<2>::Detail::InvokerImpl<TableFunctionTraitsImpl<2>::FunctionTraits<83,2,void>,void,void,D3D12DDI_HCOMMANDQUEUE,uint,D3D12DDI_HCOMMANDLIST const *>::Call<CCommandQueue<0>>(CCommandQueue<0> *,D3D12DDI_HCOMMANDQUEUE,uint,D3D12DDI_HCOMMANDLIST const *)
0x18000a1e3  test    cs:Microsoft_Windows_Direct3D12EnableBits, 4
0x18000a1ea  jnz     loc_18000A9C2
0x18000a1f0  mov     rcx, [rsp+1E8h+var_178]; this
0x18000a1f5  test    rcx, rcx
0x18000a1f8  jnz     loc_18000AAF2
0x18000a1fe  lea     rcx, [rbx+130h]
0x18000a205  call    ?clear@?$_Hash@V?$_Umap_traits@PEAVCResource@@IV?$_Uhash_compare@PEAVCResource@@U?$hash@PEAVCResource@@@std@@U?$equal_to@PEAVCResource@@@3@@std@@V?$allocator@U?$pair@QEAVCResource@@I@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<CResource *,uint,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,uint>>,0>>::clear(void)
0x18000a20a  nop
0x18000a20b  cmp     [rsp+1E8h+var_180], 0
0x18000a210  jz      short loc_18000A21E
0x18000a212  mov     rcx, [rsp+1E8h+var_188]; _Mtx_t
0x18000a217  call    cs:__imp__Mtx_unlock
0x18000a21d  nop
0x18000a21e  mov     rcx, r14; _Mtx_t
0x18000a221  call    cs:__imp__Mtx_unlock
0x18000a227  nop
0x18000a228  mov     esi, [rsp+1E8h+var_1A8]
0x18000a22c  test    esi, esi
0x18000a22e  js      loc_18000AB10
0x18000a234  add     rsp, 1B0h
0x18000a23b  pop     r15
0x18000a23d  pop     r14
0x18000a23f  pop     r13
0x18000a241  pop     r12
0x18000a243  pop     rdi
0x18000a244  pop     rsi
0x18000a245  pop     rbx
0x18000a246  retn
0x18000a247  mov     rax, [rbx+98h]
0x18000a24e  mov     rcx, [rax+308h]
0x18000a255  mov     rax, [rcx]
0x18000a258  xor     r8d, r8d
0x18000a25b  mov     edx, 46Bh
0x18000a260  mov     rax, [rax+20h]
0x18000a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a269  nop
0x18000a26a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a271  mov     [rsp+1E8h+var_150], rax
0x18000a279  mov     [rsp+1E8h+var_148], 80070057h
0x18000a284  xorps   xmm0, xmm0
0x18000a287  movdqu  [rsp+1E8h+var_140], xmm0
0x18000a290  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a297  lea     rcx, [rsp+1E8h+var_150]; pExceptionObject
0x18000a29f  call    _CxxThrowException_0
0x18000a2a4  mov     rcx, [rbx+98h]
0x18000a2ab  add     rcx, 120h; this
0x18000a2b2  lea     r8, aCommandListsMu_1; "Command lists must be successfully clos"...
0x18000a2b9  mov     edx, 346h; enum D3D12_MESSAGE_ID
0x18000a2be  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18000a2c3  nop
0x18000a2c4  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a2cb  mov     [rsp+1E8h+var_D0], rax
0x18000a2d3  mov     [rsp+1E8h+var_C8], 80070057h
0x18000a2de  xorps   xmm0, xmm0
0x18000a2e1  movdqu  [rsp+1E8h+var_C0], xmm0
0x18000a2ea  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a2f1  lea     rcx, [rsp+1E8h+var_D0]; pExceptionObject
0x18000a2f9  call    _CxxThrowException_0
0x18000a2fe  mov     rcx, [rbx+98h]
0x18000a305  add     rcx, 120h; this
0x18000a30c  lea     r8, aCommandListsMu; "Command lists must be closed before exe"...
0x18000a313  mov     edx, 345h; enum D3D12_MESSAGE_ID
0x18000a318  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18000a31d  nop
0x18000a31e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a325  mov     [rsp+1E8h+var_F0], rax
0x18000a32d  mov     [rsp+1E8h+var_E8], 80070057h
0x18000a338  xorps   xmm0, xmm0
0x18000a33b  movdqu  [rsp+1E8h+var_E0], xmm0
0x18000a344  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a34b  lea     rcx, [rsp+1E8h+var_F0]; pExceptionObject
0x18000a353  call    _CxxThrowException_0
0x18000a358  mov     rcx, [rbx+98h]
0x18000a35f  add     rcx, 120h; this
0x18000a366  lea     r8, aCommandListsMu_0; "Command lists must have matching type t"...
0x18000a36d  mov     edx, 344h; enum D3D12_MESSAGE_ID
0x18000a372  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18000a377  nop
0x18000a378  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a37f  mov     [rsp+1E8h+var_110], rax
0x18000a387  mov     [rsp+1E8h+var_108], 80070057h
0x18000a392  xorps   xmm0, xmm0
0x18000a395  movdqu  [rsp+1E8h+var_100], xmm0
0x18000a39e  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a3a5  lea     rcx, [rsp+1E8h+var_110]; pExceptionObject
0x18000a3ad  call    _CxxThrowException_0
0x18000a3b2  mov     rsi, [r15+110h]
0x18000a3b9  mov     rdi, [rsi]
0x18000a3bc  nop     dword ptr [rax+00h]
0x18000a3c0  cmp     rdi, rsi
0x18000a3c3  jz      loc_18000A48C
0x18000a3c9  mov     r13, [rdi+10h]
0x18000a3cd  mov     [rsp+1E8h+var_1B0], r13
0x18000a3d2  mov     r12, [r13+140h]
0x18000a3d9  mov     rcx, [r12+8]
0x18000a3de  test    rcx, rcx
0x18000a3e1  jz      loc_18000A794
0x18000a3e7  mov     [rsp+1E8h+var_190], 0
0x18000a3f0  mov     [rsp+1E8h+var_1A0], 0
0x18000a3f9  mov     rcx, [rcx]
0x18000a3fc  mov     rax, [rcx]
0x18000a3ff  lea     rdx, [rsp+1E8h+var_1A0]
0x18000a404  mov     [rsp+1E8h+var_1C8], rdx
0x18000a409  lea     r9, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18000a410  lea     r8, [rsp+1E8h+var_190]
0x18000a415  lea     rdx, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18000a41c  mov     rax, [rax+28h]
0x18000a420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a425  test    eax, eax
0x18000a427  js      loc_18000A767
0x18000a42d  cmp     [rsp+1E8h+var_190], r13
0x18000a432  jz      loc_18000A930
0x18000a438  mov     rcx, [rbx+98h]
0x18000a43f  mov     edx, 887A002Bh; int
0x18000a444  mov     rcx, [rcx+2F8h]; this
0x18000a44b  call    ?RemoveDevice@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::RemoveDevice(long)
0x18000a450  nop
0x18000a451  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a458  mov     [rsp+1E8h+var_70], rax
0x18000a460  mov     [rsp+1E8h+var_68], 80070057h
0x18000a46b  xorps   xmm0, xmm0
0x18000a46e  movdqu  [rsp+1E8h+var_60], xmm0
0x18000a477  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a47e  lea     rcx, [rsp+1E8h+var_70]; pExceptionObject
0x18000a486  call    _CxxThrowException_0
0x18000a48c  mov     rdi, [r15-10h]
0x18000a490  test    rdi, rdi
0x18000a493  jz      loc_18000A63B
0x18000a499  mov     rcx, [rdi+28h]
0x18000a49d  call    ?GetOrCreateData@?$CPrivateDataImpl@UID3D12PipelineState@@@@AEAAAEAUData@1@XZ; CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(void)
0x18000a4a2  mov     rsi, rax
0x18000a4a5  mov     rcx, rax; _Smtx_t *
0x18000a4a8  call    _Smtx_lock_shared
0x18000a4ad  mov     rcx, rsi; _Smtx_t *
0x18000a4b0  call    _Smtx_unlock_shared
0x18000a4b5  mov     rax, [rsi+18h]
0x18000a4b9  test    rax, rax
0x18000a4bc  jz      short loc_18000A4C2
0x18000a4be  lock inc dword ptr [rax+8]
0x18000a4c2  mov     rcx, [rsi+18h]
0x18000a4c6  mov     rax, [rsi+10h]
0x18000a4ca  mov     [rdi+30h], rax
0x18000a4ce  mov     rax, [rdi+38h]
0x18000a4d2  mov     [rdi+38h], rcx
0x18000a4d6  test    rax, rax
0x18000a4d9  jz      short loc_18000A4E3
0x18000a4db  mov     rcx, rax; this
0x18000a4de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a4e3  mov     rcx, [rdi+28h]
0x18000a4e7  call    ?GetOrCreateData@?$CPrivateDataImpl@UID3D12PipelineState@@@@AEAAAEAUData@1@XZ; CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(void)
0x18000a4ec  mov     rsi, rax
0x18000a4ef  mov     rcx, rax; _Smtx_t *
0x18000a4f2  call    _Smtx_lock_shared
0x18000a4f7  mov     rcx, rsi; _Smtx_t *
0x18000a4fa  call    _Smtx_unlock_shared
0x18000a4ff  mov     rax, [rsi+28h]
0x18000a503  test    rax, rax
0x18000a506  jz      short loc_18000A50C
0x18000a508  lock inc dword ptr [rax+8]
0x18000a50c  mov     rcx, [rsi+28h]
0x18000a510  mov     rax, [rsi+20h]
0x18000a514  mov     [rdi+40h], rax
0x18000a518  mov     rax, [rdi+48h]
0x18000a51c  mov     [rdi+48h], rcx
0x18000a520  test    rax, rax
0x18000a523  jz      short loc_18000A52D
0x18000a525  mov     rcx, rax; this
0x18000a528  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a52d  mov     rcx, rbx
0x18000a530  call    ?GetOrCreateData@?$CPrivateDataImpl@UID3D12PipelineState@@@@AEAAAEAUData@1@XZ; CPrivateDataImpl<ID3D12PipelineState>::GetOrCreateData(void)
0x18000a535  mov     rsi, rax
0x18000a538  mov     rcx, rax; _Smtx_t *
0x18000a53b  call    _Smtx_lock_shared
0x18000a540  mov     rcx, rsi; _Smtx_t *
0x18000a543  call    _Smtx_unlock_shared
0x18000a548  mov     rax, [rsi+18h]
0x18000a54c  test    rax, rax
0x18000a54f  jz      short loc_18000A555
0x18000a551  lock inc dword ptr [rax+8]
0x18000a555  mov     rcx, [rsi+18h]
0x18000a559  mov     rax, [rsi+10h]
0x18000a55d  mov     [rdi+50h], rax
0x18000a561  mov     rax, [rdi+58h]
0x18000a565  mov     [rdi+58h], rcx
0x18000a569  test    rax, rax
0x18000a56c  jz      short loc_18000A576
0x18000a56e  mov     rcx, rax; this
  ... truncated ...
```
