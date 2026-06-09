# CAvEndpointBuilder::SyncEndpoint(IMMDevice *)

- ea: `0x18002e43c`
- end: `0x18002e93c`
- name: `?SyncEndpoint@CAvEndpointBuilder@@QEAAJPEAUIMMDevice@@@Z`
- size: `1280`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct IMMDevice *)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029ad4`
- `0x18002c798`
- `0x18002e944`
- `0x180050858`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001d560`
- `0x18001ef04`
- `0x18001f374`
- `0x180023c10`
- `0x18002d094`
- `0x18002e43c`
- `0x180034c5c`
- `0x180052ffc`
- `0x180058cac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e53b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e53b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e6b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8fe`

## string_xrefs

- `0x18002e4b5`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAvEndpointBuilder::SyncEndpoint(LPCRITICAL_SECTION lpCriticalSection, struct IMMDevice *a2)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  HRESULT Instance; // eax
  int v6; // ebx
  __int64 v7; // rdx
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  struct IPnpInterface *v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  __int64 v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  int ppv; // [rsp+20h] [rbp-39h]
  int v28; // [rsp+40h] [rbp-19h] BYREF
  struct IMMEndpointManager *v29; // [rsp+48h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-9h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1h] BYREF
  struct IPnpInterface *v32; // [rsp+60h] [rbp+7h] BYREF
  const WCHAR *v33; // [rsp+68h] [rbp+Fh] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v35; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v37; // [rsp+C8h] [rbp+6Fh] BYREF
  int v38; // [rsp+D0h] [rbp+77h] BYREF
  const WCHAR *v39; // [rsp+D8h] [rbp+7Fh] BYREF

  v38 = 3;
  v37 = 1;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  pv = 0;
  GetId = a2->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  Instance = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 4336;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_49;
  }
  v8 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v8 > 4u )
  {
    v39 = (const WCHAR *)pv;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (unsigned __int8 *)qword_1800764C0,
      v9,
      v10,
      &v39);
  }
  v29 = 0;
  Instance = CoCreateInstance(
               &GUID_06cca63e_9941_441b_b004_39f999ada412,
               0,
               0x17u,
               &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
               (LPVOID *)&v29);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 4344;
    goto LABEL_3;
  }
  v11 = v32;
  v32 = 0;
  if ( v11 )
    (*(void (__fastcall **)(struct IPnpInterface *))(*(_QWORD *)v11 + 16LL))(v11);
  v6 = CAvEndpointBuilder::SyncEndpointInternal(
         lpCriticalSection,
         a2,
         (unsigned __int16 *)pv,
         v29,
         &v32,
         (enum SyncEndpointReturnType *)&v38,
         (enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 *)&v37);
  switch ( v38 )
  {
    case 0:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      v23 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v23 > 4u )
      {
        LODWORD(v39) = v6;
        v33 = (const WCHAR *)pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v23,
          (unsigned __int8 *)byte_18007647D,
          v24,
          v25,
          &v33,
          (__int64)&v39);
      }
      goto LABEL_47;
    case 1:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      v20 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v20 > 4u )
      {
        LODWORD(v39) = v6;
        v33 = (const WCHAR *)pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v20,
          (unsigned __int8 *)&word_180076436,
          v21,
          v22,
          &v33,
          (__int64)&v39);
      }
      if ( v29 )
      {
        v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *, __int64))(*(_QWORD *)v29 + 40LL))(
               v29,
               a2,
               4);
        if ( v6 >= 0 )
          v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *, _QWORD))(*(_QWORD *)v29
                                                                                                  + 112LL))(
                 v29,
                 a2,
                 0);
      }
      break;
    case 2:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      v12 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v12 > 4u )
      {
        LODWORD(v39) = v6;
        v28 = v37;
        v33 = (const WCHAR *)pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (__int64)v12,
          (unsigned __int8 *)byte_1800763E1,
          v13,
          v14,
          &v33,
          (__int64)&v28,
          (__int64)&v39);
      }
      OpenPropertyStore = a2->lpVtbl->OpenPropertyStore;
      v16 = v31;
      v31 = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( ((int (__fastcall *)(struct IMMDevice *, __int64, __int64 *))OpenPropertyStore)(a2, 1, &v31) >= 0 )
      {
        *(_OWORD *)pvar = 0;
        v35 = 0;
        LOWORD(pvar[0]) = 19;
        LODWORD(pvar[1]) = v37;
        (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v31 + 48LL))(
          v31,
          PKEY_AudioEndpoint_MigrationReason,
          pvar);
        PropVariantClear(pvar);
      }
      (*(void (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *, __int64))(*(_QWORD *)v29 + 40LL))(
        v29,
        a2,
        4);
      CAudioDeviceManager::NotifyRemoveLocalAudioDevice((CAudioDeviceManager *)lpCriticalSection[2].LockSemaphore, a2);
      v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *, __int64))(*(_QWORD *)v29 + 56LL))(
             v29,
             a2,
             1);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
        }
        v17 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v17 > 2u )
        {
          LODWORD(v39) = v6;
          v28 = v37;
          v33 = (const WCHAR *)pv;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)v17,
            (unsigned __int8 *)&unk_180076378,
            v18,
            v19,
            &v33,
            (__int64)&v28,
            (__int64)&v39);
        }
LABEL_47:
        (*(void (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *, __int64))(*(_QWORD *)v29 + 40LL))(
          v29,
          a2,
          4);
        CAudioDeviceManager::NotifyRemoveLocalAudioDevice((CAudioDeviceManager *)lpCriticalSection[2].LockSemaphore, a2);
        if ( v29 )
          (*(void (__fastcall **)(struct IMMEndpointManager *, struct IMMDevice *))(*(_QWORD *)v29 + 32LL))(v29, a2);
        break;
      }
      if ( v32 )
        CAvEndpointBuilder::ProcessPnpInterface(
          lpCriticalSection,
          (__int64 (__fastcall ***)(struct IPnpInterface *, GUID *, __int64 *))v32);
      break;
    default:
      break;
  }
LABEL_49:
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e43c  mov     [rsp-8+arg_0], rbx
0x18002e441  push    rbp
0x18002e442  push    rdi
0x18002e443  push    r13
0x18002e445  push    r14
0x18002e447  push    r15
0x18002e449  lea     rbp, [rsp-37h]
0x18002e44e  sub     rsp, 90h
0x18002e455  mov     rdi, rdx
0x18002e458  mov     r15, rcx
0x18002e45b  mov     [rbp+57h+arg_10], 3
0x18002e462  mov     [rbp+57h+arg_8], 1
0x18002e469  mov     [rbp+57h+var_68], 0
0x18002e471  mov     [rbp+57h+var_50], 0
0x18002e479  mov     [rbp+57h+var_58], 0
0x18002e481  mov     [rbp+57h+pv], 0
0x18002e489  mov     rax, [rdx]
0x18002e48c  mov     rbx, [rax+28h]
0x18002e490  xor     edx, edx
0x18002e492  lea     rcx, [rbp+57h+pv]
0x18002e496  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e49b  lea     rdx, [rbp+57h+pv]
0x18002e49f  mov     rcx, rdi
0x18002e4a2  mov     rax, rbx
0x18002e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4aa  mov     ebx, eax
0x18002e4ac  test    eax, eax
0x18002e4ae  jns     short loc_18002E4CD
0x18002e4b0  mov     edx, 10F0h; void *
0x18002e4b5  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002e4bc  mov     r9d, eax; char *
0x18002e4bf  mov     rcx, [rbp+5Fh]; this
0x18002e4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4c8  jmp     loc_18002E8F5
0x18002e4cd  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002e4d2  mov     ecx, [rax]
0x18002e4d4  mov     r13d, 4
0x18002e4da  cmp     ecx, r13d
0x18002e4dd  jbe     short loc_18002E500
0x18002e4df  mov     rcx, [rbp+57h+pv]
0x18002e4e3  mov     [rbp+57h+arg_18], rcx
0x18002e4e7  lea     rcx, [rbp+57h+arg_18]
0x18002e4eb  mov     [rsp+0B0h+ppv], rcx
0x18002e4f0  lea     rdx, qword_1800764C0
0x18002e4f7  mov     rcx, rax
0x18002e4fa  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002e4ff  nop
0x18002e500  mov     rcx, [rbp+57h+var_68]
0x18002e504  mov     [rbp+57h+var_68], 0
0x18002e50c  test    rcx, rcx
0x18002e50f  jz      short loc_18002E51E
0x18002e511  mov     rax, [rcx]
0x18002e514  mov     rax, [rax+10h]
0x18002e518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51d  nop
0x18002e51e  lea     rax, [rbp+57h+var_68]
0x18002e522  mov     [rsp+0B0h+ppv], rax; ppv
0x18002e527  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x18002e52e  xor     edx, edx; pUnkOuter
0x18002e530  lea     r8d, [rdx+17h]; dwClsContext
0x18002e534  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x18002e53b  call    cs:__imp_CoCreateInstance
0x18002e541  mov     ebx, eax
0x18002e543  test    eax, eax
0x18002e545  jns     short loc_18002E551
0x18002e547  mov     edx, 10F8h
0x18002e54c  jmp     loc_18002E4B5
0x18002e551  mov     rcx, [rbp+57h+var_50]
0x18002e555  mov     [rbp+57h+var_50], 0
0x18002e55d  test    rcx, rcx
0x18002e560  jz      short loc_18002E56F
0x18002e562  mov     rax, [rcx]
0x18002e565  mov     rax, [rax+10h]
0x18002e569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e56e  nop
0x18002e56f  lea     rax, [rbp+57h+arg_8]
0x18002e573  mov     [rsp+0B0h+var_80], rax; enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 *
0x18002e578  lea     rax, [rbp+57h+arg_10]
0x18002e57c  mov     [rsp+0B0h+var_88], rax; enum SyncEndpointReturnType *
0x18002e581  lea     rax, [rbp+57h+var_50]
0x18002e585  mov     [rsp+0B0h+ppv], rax; struct IPnpInterface **
0x18002e58a  mov     r9, [rbp+57h+var_68]; struct IMMEndpointManager *
0x18002e58e  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x18002e592  mov     rdx, rdi; struct IMMDevice *
0x18002e595  mov     rcx, r15; this
0x18002e598  call    ?SyncEndpointInternal@CAvEndpointBuilder@@QEAAJPEAUIMMDevice@@PEBGPEAUIMMEndpointManager@@PEAPEAUIPnpInterface@@AEAW4SyncEndpointReturnType@@AEAW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009@@@Z; CAvEndpointBuilder::SyncEndpointInternal(IMMDevice *,ushort const *,IMMEndpointManager *,IPnpInterface * *,SyncEndpointReturnType &,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 &)
0x18002e59d  mov     ebx, eax
0x18002e59f  mov     eax, [rbp+57h+arg_10]
0x18002e5a2  test    eax, eax
0x18002e5a4  jz      loc_18002E84B
0x18002e5aa  sub     eax, 1
0x18002e5ad  jz      loc_18002E796
0x18002e5b3  cmp     eax, 1
0x18002e5b6  jnz     loc_18002E8F5
0x18002e5bc  lea     r14, WPP_GLOBAL_Control
0x18002e5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5ca  cmp     rcx, r14
0x18002e5cd  jz      short loc_18002E5F1
0x18002e5cf  test    dword ptr [rcx+1Ch], 80000h
0x18002e5d6  jz      short loc_18002E5F1
0x18002e5d8  cmp     [rcx+19h], r13b
0x18002e5dc  jb      short loc_18002E5F1
0x18002e5de  lea     edx, [rax+26h]
0x18002e5e1  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18002e5e8  mov     rcx, [rcx+10h]
0x18002e5ec  call    WPP_SF_
0x18002e5f1  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002e5f6  mov     ecx, [rax]
0x18002e5f8  cmp     ecx, r13d
0x18002e5fb  jbe     short loc_18002E638
0x18002e5fd  mov     dword ptr [rbp+57h+arg_18], ebx
0x18002e600  mov     ecx, [rbp+57h+arg_8]
0x18002e603  mov     [rbp+57h+var_70], ecx
0x18002e606  mov     rcx, [rbp+57h+pv]
0x18002e60a  mov     [rbp+57h+var_48], rcx
0x18002e60e  lea     rcx, [rbp+57h+arg_18]
0x18002e612  mov     [rsp+0B0h+var_80], rcx
0x18002e617  lea     rcx, [rbp+57h+var_70]
0x18002e61b  mov     [rsp+0B0h+var_88], rcx
0x18002e620  lea     rcx, [rbp+57h+var_48]
0x18002e624  mov     [rsp+0B0h+ppv], rcx
0x18002e629  lea     rdx, byte_1800763E1
0x18002e630  mov     rcx, rax
0x18002e633  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e638  mov     rax, [rdi]
0x18002e63b  mov     rbx, [rax+20h]
0x18002e63f  mov     rcx, [rbp+57h+var_58]
0x18002e643  mov     [rbp+57h+var_58], 0
0x18002e64b  test    rcx, rcx
0x18002e64e  jz      short loc_18002E65D
0x18002e650  mov     rdx, [rcx]
0x18002e653  mov     rax, [rdx+10h]
0x18002e657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e65c  nop
0x18002e65d  lea     r8, [rbp+57h+var_58]
0x18002e661  mov     edx, 1
0x18002e666  mov     rcx, rdi
0x18002e669  mov     rax, rbx
0x18002e66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e671  test    eax, eax
0x18002e673  js      short loc_18002E6B7
0x18002e675  xorps   xmm0, xmm0
0x18002e678  xor     eax, eax
0x18002e67a  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18002e67e  mov     [rbp+57h+var_30], rax
0x18002e682  mov     eax, 13h
0x18002e687  mov     word ptr [rbp+57h+pvar], ax
0x18002e68b  mov     eax, [rbp+57h+arg_8]
0x18002e68e  mov     dword ptr [rbp+57h+pvar+8], eax
0x18002e691  mov     rcx, [rbp+57h+var_58]
0x18002e695  mov     rax, [rcx]
0x18002e698  lea     r8, [rbp+57h+pvar]
0x18002e69c  lea     rdx, PKEY_AudioEndpoint_MigrationReason
0x18002e6a3  mov     rax, [rax+30h]
0x18002e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6ac  nop
0x18002e6ad  lea     rcx, [rbp+57h+pvar]; pvar
0x18002e6b1  call    cs:__imp_PropVariantClear
0x18002e6b7  mov     rcx, [rbp+57h+var_68]
0x18002e6bb  mov     rax, [rcx]
0x18002e6be  mov     r8d, r13d
0x18002e6c1  mov     rdx, rdi
0x18002e6c4  mov     rax, [rax+28h]
0x18002e6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6cd  mov     rdx, rdi; struct IMMDevice *
0x18002e6d0  mov     rcx, [r15+68h]; this
0x18002e6d4  call    ?NotifyRemoveLocalAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@@Z; CAudioDeviceManager::NotifyRemoveLocalAudioDevice(IMMDevice *)
0x18002e6d9  mov     rcx, [rbp+57h+var_68]
0x18002e6dd  mov     rax, [rcx]
0x18002e6e0  mov     r8d, 1
0x18002e6e6  mov     rdx, rdi
0x18002e6e9  mov     rax, [rax+38h]
0x18002e6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6f2  mov     ebx, eax
0x18002e6f4  test    eax, eax
0x18002e6f6  jns     loc_18002E77C
0x18002e6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e703  cmp     rcx, r14
0x18002e706  jz      short loc_18002E72C
0x18002e708  test    dword ptr [rcx+1Ch], 80000h
0x18002e70f  jz      short loc_18002E72C
0x18002e711  cmp     [rcx+19h], r13b
0x18002e715  jb      short loc_18002E72C
0x18002e717  mov     edx, 28h ; '('
0x18002e71c  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18002e723  mov     rcx, [rcx+10h]
0x18002e727  call    WPP_SF_
0x18002e72c  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002e731  mov     ecx, [rax]
0x18002e733  cmp     ecx, 2
0x18002e736  jbe     loc_18002E8BA
0x18002e73c  mov     dword ptr [rbp+57h+arg_18], ebx
0x18002e73f  mov     ecx, [rbp+57h+arg_8]
0x18002e742  mov     [rbp+57h+var_70], ecx
0x18002e745  mov     rcx, [rbp+57h+pv]
0x18002e749  mov     [rbp+57h+var_48], rcx
0x18002e74d  lea     rcx, [rbp+57h+arg_18]
0x18002e751  mov     [rsp+0B0h+var_80], rcx
0x18002e756  lea     rcx, [rbp+57h+var_70]
0x18002e75a  mov     [rsp+0B0h+var_88], rcx
0x18002e75f  lea     rcx, [rbp+57h+var_48]
0x18002e763  mov     [rsp+0B0h+ppv], rcx
0x18002e768  lea     rdx, unk_180076378
0x18002e76f  mov     rcx, rax
0x18002e772  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e777  jmp     loc_18002E8BA
0x18002e77c  mov     rdx, [rbp+57h+var_50]; struct IPnpInterface *
0x18002e780  test    rdx, rdx
0x18002e783  jz      loc_18002E8F5
0x18002e789  mov     rcx, r15; lpCriticalSection
0x18002e78c  call    ?ProcessPnpInterface@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@@Z; CAvEndpointBuilder::ProcessPnpInterface(IPnpInterface *)
0x18002e791  jmp     loc_18002E8F5
0x18002e796  lea     r14, WPP_GLOBAL_Control
0x18002e79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7a4  cmp     rcx, r14
0x18002e7a7  jz      short loc_18002E7CD
0x18002e7a9  test    dword ptr [rcx+1Ch], 80000h
0x18002e7b0  jz      short loc_18002E7CD
0x18002e7b2  cmp     [rcx+19h], r13b
0x18002e7b6  jb      short loc_18002E7CD
0x18002e7b8  mov     edx, 26h ; '&'
0x18002e7bd  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18002e7c4  mov     rcx, [rcx+10h]
0x18002e7c8  call    WPP_SF_
0x18002e7cd  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002e7d2  mov     ecx, [rax]
0x18002e7d4  cmp     ecx, r13d
0x18002e7d7  jbe     short loc_18002E805
0x18002e7d9  mov     dword ptr [rbp+57h+arg_18], ebx
0x18002e7dc  mov     rcx, [rbp+57h+pv]
0x18002e7e0  mov     [rbp+57h+var_48], rcx
0x18002e7e4  lea     rcx, [rbp+57h+arg_18]
0x18002e7e8  mov     [rsp+0B0h+var_88], rcx
0x18002e7ed  lea     rcx, [rbp+57h+var_48]
0x18002e7f1  mov     [rsp+0B0h+ppv], rcx
0x18002e7f6  lea     rdx, word_180076436
0x18002e7fd  mov     rcx, rax
0x18002e800  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002e805  mov     rcx, [rbp+57h+var_68]
0x18002e809  test    rcx, rcx
0x18002e80c  jz      loc_18002E8F5
0x18002e812  mov     rax, [rcx]
0x18002e815  mov     r8d, r13d
0x18002e818  mov     rdx, rdi
0x18002e81b  mov     rax, [rax+28h]
0x18002e81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e824  mov     ebx, eax
0x18002e826  test    eax, eax
0x18002e828  js      loc_18002E8F5
0x18002e82e  mov     rcx, [rbp+57h+var_68]
0x18002e832  mov     rax, [rcx]
0x18002e835  xor     r8d, r8d
0x18002e838  mov     rdx, rdi
0x18002e83b  mov     rax, [rax+70h]
0x18002e83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e844  mov     ebx, eax
0x18002e846  jmp     loc_18002E8F5
0x18002e84b  lea     r14, WPP_GLOBAL_Control
0x18002e852  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e859  cmp     rcx, r14
0x18002e85c  jz      short loc_18002E882
0x18002e85e  test    dword ptr [rcx+1Ch], 80000h
0x18002e865  jz      short loc_18002E882
0x18002e867  cmp     [rcx+19h], r13b
0x18002e86b  jb      short loc_18002E882
0x18002e86d  mov     edx, 25h ; '%'
0x18002e872  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18002e879  mov     rcx, [rcx+10h]
0x18002e87d  call    WPP_SF_
0x18002e882  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002e887  mov     ecx, [rax]
0x18002e889  cmp     ecx, r13d
0x18002e88c  jbe     short loc_18002E8BA
0x18002e88e  mov     dword ptr [rbp+57h+arg_18], ebx
0x18002e891  mov     rcx, [rbp+57h+pv]
0x18002e895  mov     [rbp+57h+var_48], rcx
0x18002e899  lea     rcx, [rbp+57h+arg_18]
0x18002e89d  mov     [rsp+0B0h+var_88], rcx
0x18002e8a2  lea     rcx, [rbp+57h+var_48]
0x18002e8a6  mov     [rsp+0B0h+ppv], rcx
0x18002e8ab  lea     rdx, byte_18007647D
0x18002e8b2  mov     rcx, rax
0x18002e8b5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002e8ba  mov     rcx, [rbp+57h+var_68]
0x18002e8be  mov     rax, [rcx]
0x18002e8c1  mov     r8d, r13d
0x18002e8c4  mov     rdx, rdi
0x18002e8c7  mov     rax, [rax+28h]
0x18002e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8d0  mov     rdx, rdi; struct IMMDevice *
0x18002e8d3  mov     rcx, [r15+68h]; this
0x18002e8d7  call    ?NotifyRemoveLocalAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@@Z; CAudioDeviceManager::NotifyRemoveLocalAudioDevice(IMMDevice *)
0x18002e8dc  mov     rcx, [rbp+57h+var_68]
0x18002e8e0  test    rcx, rcx
0x18002e8e3  jz      short loc_18002E8F5
0x18002e8e5  mov     rax, [rcx]
0x18002e8e8  mov     rdx, rdi
0x18002e8eb  mov     rax, [rax+20h]
0x18002e8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8f4  nop
  ... truncated ...
```
