# ProcessNewDevicePersistenceState(IMMDevice *)

- ea: `0x1800301b8`
- end: `0x180030833`
- name: `?ProcessNewDevicePersistenceState@@YAJPEAUIMMDevice@@@Z`
- size: `1659`
- prototype: `__int64 __fastcall(struct IMMDevice *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f040`

## callees

- `0x180005400`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001707c`
- `0x18001d560`
- `0x18001ef04`
- `0x18001f374`
- `0x180024190`
- `0x180026144`
- `0x1800264a0`
- `0x18002671c`
- `0x1800301b8`
- `0x180030840`
- `0x180033578`
- `0x18003e920`
- `0x18003f780`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030669`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800302c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003065c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800302c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003065c`

## string_xrefs

- `0x1800302a6`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18003037d`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18003053c`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x1800306ba`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x1800306ff`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030744`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030786`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x1800307cd`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030806`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ProcessNewDevicePersistenceState(struct IMMDevice *a1)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  __int64 v10; // rcx
  __int64 v11; // r9
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  __int64 *v13; // rcx
  unsigned int v14; // r15d
  __int64 v15; // rax
  int v16; // eax
  struct IPart *v17; // rcx
  unsigned int v18; // r14d
  struct IPartVtbl *lpVtbl; // rax
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  CPersistedControl *v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v31; // rdx
  __int64 v32; // rdx
  int *v33; // [rsp+20h] [rbp-79h]
  LPVOID pv; // [rsp+30h] [rbp-69h] BYREF
  PVOID v35; // [rsp+38h] [rbp-61h] BYREF
  struct IPart *v36; // [rsp+40h] [rbp-59h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, struct IPart **); // [rsp+48h] [rbp-51h] BYREF
  int v38[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v41[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-31h] BYREF
  __int64 v43; // [rsp+70h] [rbp-29h] BYREF
  int v44; // [rsp+78h] [rbp-21h] BYREF
  const WCHAR *v45; // [rsp+80h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v47; // [rsp+98h] [rbp-1h]
  PVOID *v48; // [rsp+A0h] [rbp+7h]
  char v49; // [rsp+A8h] [rbp+Fh]
  struct _GUID Buf1; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v43 = 0;
  *(_QWORD *)v41 = 0;
  v40 = 0;
  *(_OWORD *)pvar = 0;
  v47 = 0;
  pv = 0;
  GetId = a1->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v3 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a1, &pv);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1031;
LABEL_9:
    v11 = (unsigned int)v3;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)v11,
      (int)v33);
    goto LABEL_11;
  }
  v6 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v6 > 4u )
  {
    *(_QWORD *)v38 = pv;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (unsigned __int8 *)byte_18007753F,
      v7,
      v8,
      (const WCHAR **)v38);
  }
  OpenPropertyStore = a1->lpVtbl->OpenPropertyStore;
  v10 = v43;
  v43 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v3 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(a1, 0, &v43);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1044;
    goto LABEL_9;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v43 + 40LL))(
         v43,
         &DEVPKEY_DeviceInterface_Enabled,
         pvar);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1045;
    goto LABEL_9;
  }
  if ( LOWORD(pvar[0]) != 11 )
  {
    v4 = -2147467259;
    v11 = 2147500037LL;
    v5 = 1046;
    goto LABEL_10;
  }
  if ( !LOWORD(pvar[1]) )
    goto LABEL_53;
  Activate = a1->lpVtbl->Activate;
  v13 = *(__int64 **)v41;
  *(_QWORD *)v41 = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  v33 = v41;
  v4 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
         a1,
         &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
         1);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x41D,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v4,
      (int)"Failed to activate device topology for device %ls",
      (const char *)pv);
    goto LABEL_11;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v41 + 40LL))(*(_QWORD *)v41, &v40);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1056;
    goto LABEL_9;
  }
  v14 = 0;
  if ( !v40 )
  {
LABEL_53:
    if ( pv )
      CoTaskMemFree(pv);
    v4 = 0;
    goto LABEL_56;
  }
  while ( 1 )
  {
    v37 = 0;
    v36 = 0;
    v39 = 0;
    v42 = 0;
    v15 = **(_QWORD **)v41;
    v37 = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v15 + 48))(*(_QWORD *)v41, v14, &v37);
    v4 = v16;
    if ( v16 < 0 )
    {
      v32 = 1065;
      goto LABEL_81;
    }
    v17 = v36;
    v36 = 0;
    if ( v17 )
      ((void (__fastcall *)(struct IPart *))v17->lpVtbl->Release)(v17);
    v16 = (**v37)(v37, &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9, &v36);
    v4 = v16;
    if ( v16 < 0 )
    {
      v32 = 1068;
      goto LABEL_81;
    }
    v16 = ((__int64 (__fastcall *)(struct IPart *, unsigned int *))v36->lpVtbl->GetLocalId)(v36, &v42);
    v4 = v16;
    if ( v16 < 0 )
    {
      v32 = 1071;
      goto LABEL_81;
    }
    v16 = ((__int64 (__fastcall *)(struct IPart *, unsigned int *))v36->lpVtbl->GetControlInterfaceCount)(v36, &v39);
    v4 = v16;
    if ( v16 < 0 )
    {
      v32 = 1074;
LABEL_81:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
        (const char *)(unsigned int)v16,
        (int)v33);
      goto LABEL_82;
    }
    v18 = 0;
    if ( !v39 )
      goto LABEL_52;
LABEL_32:
    *(_QWORD *)v38 = 0;
    Buf1 = 0;
    lpVtbl = v36->lpVtbl;
    *(_QWORD *)v38 = 0;
    v20 = ((__int64 (__fastcall *)(struct IPart *, _QWORD, int *))lpVtbl->GetControlInterface)(v36, v18, v38);
    v4 = v20;
    if ( v20 < 0 )
      break;
    v20 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**(_QWORD **)v38 + 32LL))(*(_QWORD *)v38, &Buf1);
    v4 = v20;
    if ( v20 < 0 )
    {
      v31 = 1085;
      goto LABEL_75;
    }
    v21 = 0;
    while ( memcmp_0(&Buf1, &PersistedControlFactoryList + 3 * v21, 0x10u) )
    {
      if ( ++v21 >= 7 )
        goto LABEL_51;
    }
    v35 = 0;
    v48 = &v35;
    v49 = 1;
    v22 = ((__int64 (__fastcall *)(LPVOID, _QWORD, struct IPart *, PVOID *))*(&funcs_18003052C + 3 * v21))(
            pv,
            v42,
            v36,
            &v35);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x450,
        (int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
        (const char *)(unsigned int)v22);
    v23 = (CPersistedControl *)v35;
    if ( v35 )
    {
      v24 = CPersistedControl::FinishConstruction(v35);
      v4 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x454,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v24,
          (int)v33);
        if ( v35 )
        {
          CPersistedControl::UnregisterForControlChangeCallbacks((CPersistedControl *)v35);
          if ( v35 )
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
        }
        goto LABEL_76;
      }
      v25 = CPersistedControl::RestorePersistedState((CPersistedControl *)v35, a1, v36);
      v4 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x457,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v25,
          (int)v33);
        if ( v35 )
        {
          CPersistedControl::UnregisterForControlChangeCallbacks((CPersistedControl *)v35);
          if ( v35 )
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
        }
        goto LABEL_76;
      }
      v26 = CPersistedControl::RegisterForControlChangeCallbacks((CPersistedControl *)v35, &Buf1);
      v4 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45A,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v26,
          (int)v33);
        if ( v35 )
        {
          CPersistedControl::UnregisterForControlChangeCallbacks((CPersistedControl *)v35);
          if ( v35 )
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
        }
        goto LABEL_76;
      }
      if ( !TList<CPersistedControl>::AddTail(&g_PersistedControlList, v35) )
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x463,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)0x8007000ELL,
          (int)v33);
        if ( v35 )
        {
          CPersistedControl::UnregisterForControlChangeCallbacks((CPersistedControl *)v35);
          if ( v35 )
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
        }
        goto LABEL_76;
      }
      v27 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v27 > 4u )
      {
        v44 = *((_DWORD *)v35 + 16);
        v45 = (const WCHAR *)*((_QWORD *)v35 + 9);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v27,
          (unsigned __int8 *)byte_1800774E9,
          v28,
          v29,
          &v45,
          (__int64)&v44);
      }
      v23 = 0;
      v35 = 0;
    }
    v49 = 0;
    if ( v23 )
    {
      CPersistedControl::UnregisterForControlChangeCallbacks(v23);
      if ( v35 )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v35 + 16LL))(v35);
    }
LABEL_51:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v38);
    if ( ++v18 < v39 )
      goto LABEL_32;
LABEL_52:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
    if ( ++v14 >= v40 )
      goto LABEL_53;
  }
  v31 = 1082;
LABEL_75:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v31,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
    (const char *)(unsigned int)v20,
    (int)v33);
LABEL_76:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v38);
LABEL_82:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
LABEL_11:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_56:
  PropVariantClear(pvar);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v41);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800301b8  mov     [rsp-8+arg_8], rbx
0x1800301bd  mov     [rsp-8+arg_10], rsi
0x1800301c2  push    rbp
0x1800301c3  push    r12
0x1800301c5  push    r13
0x1800301c7  push    r14
0x1800301c9  push    r15
0x1800301cb  lea     rbp, [rsp-37h]
0x1800301d0  sub     rsp, 0D0h
0x1800301d7  mov     rax, cs:__security_cookie
0x1800301de  xor     rax, rsp
0x1800301e1  mov     [rbp+57h+var_30], rax
0x1800301e5  mov     rsi, rcx
0x1800301e8  xor     r13d, r13d
0x1800301eb  mov     [rbp+57h+var_80], r13
0x1800301ef  mov     qword ptr [rbp+57h+var_90], r13
0x1800301f3  mov     [rbp+57h+var_94], r13d
0x1800301f7  xorps   xmm0, xmm0
0x1800301fa  xor     eax, eax
0x1800301fc  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180030200  mov     [rbp+57h+var_58], rax
0x180030204  mov     [rbp+57h+pv], r13
0x180030208  mov     rax, [rcx]
0x18003020b  mov     rbx, [rax+28h]
0x18003020f  xor     edx, edx
0x180030211  lea     rcx, [rbp+57h+pv]
0x180030215  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003021a  lea     rdx, [rbp+57h+pv]
0x18003021e  mov     rcx, rsi
0x180030221  mov     rax, rbx
0x180030224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030229  mov     ebx, eax
0x18003022b  test    eax, eax
0x18003022d  jns     short loc_180030236
0x18003022f  mov     edx, 407h
0x180030234  jmp     short loc_18003029F
0x180030236  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18003023b  mov     ecx, [rax]
0x18003023d  cmp     ecx, 4
0x180030240  jbe     short loc_180030262
0x180030242  mov     rcx, [rbp+57h+pv]
0x180030246  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003024a  lea     rcx, [rbp+57h+var_A0]
0x18003024e  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x180030253  lea     rdx, byte_18007753F
0x18003025a  mov     rcx, rax
0x18003025d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180030262  mov     rax, [rsi]
0x180030265  mov     rbx, [rax+20h]
0x180030269  mov     rcx, [rbp+57h+var_80]
0x18003026d  mov     [rbp+57h+var_80], r13
0x180030271  test    rcx, rcx
0x180030274  jz      short loc_180030283
0x180030276  mov     rdx, [rcx]
0x180030279  mov     rax, [rdx+10h]
0x18003027d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030282  nop
0x180030283  lea     r8, [rbp+57h+var_80]
0x180030287  xor     edx, edx
0x180030289  mov     rcx, rsi
0x18003028c  mov     rax, rbx
0x18003028f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030294  mov     ebx, eax
0x180030296  test    eax, eax
0x180030298  jns     short loc_1800302CB
0x18003029a  mov     edx, 414h; void *
0x18003029f  mov     r9d, eax; char *
0x1800302a2  mov     rcx, [rbp+5Fh]; this
0x1800302a6  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x1800302ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302b2  nop
0x1800302b3  mov     rcx, [rbp+57h+pv]; pv
0x1800302b7  test    rcx, rcx
0x1800302ba  jz      loc_180030665
0x1800302c0  call    cs:__imp_CoTaskMemFree
0x1800302c6  jmp     loc_180030665
0x1800302cb  mov     rcx, [rbp+57h+var_80]
0x1800302cf  mov     rax, [rcx]
0x1800302d2  lea     r8, [rbp+57h+pvar]
0x1800302d6  lea     rdx, DEVPKEY_DeviceInterface_Enabled
0x1800302dd  mov     rax, [rax+28h]
0x1800302e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302e6  mov     ebx, eax
0x1800302e8  test    eax, eax
0x1800302ea  jns     short loc_1800302F3
0x1800302ec  mov     edx, 415h
0x1800302f1  jmp     short loc_18003029F
0x1800302f3  mov     eax, 0Bh
0x1800302f8  cmp     ax, word ptr [rbp+57h+pvar]
0x1800302fc  jz      short loc_18003030D
0x1800302fe  mov     ebx, 80004005h
0x180030303  mov     r9d, ebx
0x180030306  mov     edx, 416h
0x18003030b  jmp     short loc_1800302A2
0x18003030d  cmp     r13w, word ptr [rbp+57h+pvar+8]
0x180030312  jz      loc_180030653
0x180030318  mov     rax, [rsi]
0x18003031b  mov     rbx, [rax+18h]
0x18003031f  mov     rcx, qword ptr [rbp+57h+var_90]
0x180030323  mov     qword ptr [rbp+57h+var_90], r13
0x180030327  test    rcx, rcx
0x18003032a  jz      short loc_180030339
0x18003032c  mov     rax, [rcx]
0x18003032f  mov     rax, [rax+10h]
0x180030333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030338  nop
0x180030339  lea     rax, [rbp+57h+var_90]
0x18003033d  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180030342  xor     r9d, r9d
0x180030345  lea     r8d, [r9+1]
0x180030349  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180030350  mov     rcx, rsi
0x180030353  mov     rax, rbx
0x180030356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003035b  mov     ebx, eax
0x18003035d  test    eax, eax
0x18003035f  jns     short loc_180030393
0x180030361  mov     rcx, [rbp+5Fh]; this
0x180030365  mov     rdx, [rbp+57h+pv]
0x180030369  mov     [rsp+0F0h+var_C8], rdx; char *
0x18003036e  lea     rax, aFailedToActiva; "Failed to activate device topology for "...
0x180030375  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18003037a  mov     r9d, ebx; char *
0x18003037d  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030384  mov     edx, 41Dh; void *
0x180030389  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003038e  jmp     loc_1800302B3
0x180030393  mov     rcx, qword ptr [rbp+57h+var_90]
0x180030397  mov     rax, [rcx]
0x18003039a  lea     rdx, [rbp+57h+var_94]
0x18003039e  mov     rax, [rax+28h]
0x1800303a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a7  mov     ebx, eax
0x1800303a9  test    eax, eax
0x1800303ab  jns     short loc_1800303B7
0x1800303ad  mov     edx, 420h
0x1800303b2  jmp     loc_18003029F
0x1800303b7  mov     r15d, r13d
0x1800303ba  cmp     [rbp+57h+var_94], r13d
0x1800303be  jbe     loc_180030653
0x1800303c4  mov     [rbp+57h+var_A8], r13
0x1800303c8  mov     [rbp+57h+var_B0], r13
0x1800303cc  mov     [rbp+57h+var_98], r13d
0x1800303d0  mov     [rbp+57h+var_88], r13d
0x1800303d4  mov     rcx, qword ptr [rbp+57h+var_90]
0x1800303d8  mov     rax, [rcx]
0x1800303db  mov     [rbp+57h+var_A8], r13
0x1800303df  lea     r8, [rbp+57h+var_A8]
0x1800303e3  mov     edx, r15d
0x1800303e6  mov     rax, [rax+30h]
0x1800303ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303ef  mov     ebx, eax
0x1800303f1  test    eax, eax
0x1800303f3  js      loc_180030801
0x1800303f9  mov     rcx, [rbp+57h+var_B0]
0x1800303fd  mov     [rbp+57h+var_B0], r13
0x180030401  test    rcx, rcx
0x180030404  jz      short loc_180030413
0x180030406  mov     rax, [rcx]
0x180030409  mov     rax, [rax+10h]
0x18003040d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030412  nop
0x180030413  mov     rcx, [rbp+57h+var_A8]
0x180030417  mov     rax, [rcx]
0x18003041a  lea     r8, [rbp+57h+var_B0]
0x18003041e  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x180030425  mov     rax, [rax]
0x180030428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003042d  mov     ebx, eax
0x18003042f  test    eax, eax
0x180030431  js      loc_1800307FA
0x180030437  mov     rcx, [rbp+57h+var_B0]
0x18003043b  mov     rax, [rcx]
0x18003043e  lea     rdx, [rbp+57h+var_88]
0x180030442  mov     rax, [rax+20h]
0x180030446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003044b  mov     ebx, eax
0x18003044d  test    eax, eax
0x18003044f  js      loc_1800307F3
0x180030455  mov     rcx, [rbp+57h+var_B0]
0x180030459  mov     rax, [rcx]
0x18003045c  lea     rdx, [rbp+57h+var_98]
0x180030460  mov     rax, [rax+40h]
0x180030464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030469  mov     ebx, eax
0x18003046b  test    eax, eax
0x18003046d  js      loc_1800307EC
0x180030473  mov     r14d, r13d
0x180030476  cmp     [rbp+57h+var_98], r13d
0x18003047a  jbe     loc_180030633
0x180030480  mov     qword ptr [rbp+57h+var_A0], r13
0x180030484  xorps   xmm0, xmm0
0x180030487  movups  [rbp+57h+Buf1], xmm0
0x18003048b  mov     rcx, [rbp+57h+var_B0]
0x18003048f  mov     rax, [rcx]
0x180030492  mov     qword ptr [rbp+57h+var_A0], r13
0x180030496  lea     r8, [rbp+57h+var_A0]
0x18003049a  mov     edx, r14d
0x18003049d  mov     rax, [rax+48h]
0x1800304a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304a6  mov     ebx, eax
0x1800304a8  test    eax, eax
0x1800304aa  js      loc_1800307C8
0x1800304b0  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800304b4  mov     rax, [rcx]
0x1800304b7  lea     rdx, [rbp+57h+Buf1]
0x1800304bb  mov     rax, [rax+20h]
0x1800304bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304c4  mov     ebx, eax
0x1800304c6  test    eax, eax
0x1800304c8  js      loc_1800307C1
0x1800304ce  mov     ebx, r13d
0x1800304d1  mov     eax, ebx
0x1800304d3  lea     r12, [rax+rax*2]
0x1800304d7  lea     rax, ?PersistedControlFactoryList@@3PAU_unnamed_type_PersistedControlFactoryList_@@A; _unnamed_type_PersistedControlFactoryList_ near * PersistedControlFactoryList
0x1800304de  lea     rdx, [rax+r12*8]; Buf2
0x1800304e2  mov     r8d, 10h; Size
0x1800304e8  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800304ec  call    memcmp_0
0x1800304f1  test    eax, eax
0x1800304f3  jz      short loc_180030501
0x1800304f5  inc     ebx
0x1800304f7  cmp     ebx, 7
0x1800304fa  jb      short loc_1800304D1
0x1800304fc  jmp     loc_18003061D
0x180030501  mov     [rbp+57h+var_B8], r13
0x180030505  lea     rax, [rbp+57h+var_B8]
0x180030509  mov     [rbp+57h+var_50], rax
0x18003050d  mov     [rbp+57h+var_48], 1
0x180030511  lea     r9, [rbp+57h+var_B8]
0x180030515  mov     r8, [rbp+57h+var_B0]; struct IPart *
0x180030519  mov     edx, [rbp+57h+var_88]; unsigned int
0x18003051c  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x180030520  lea     rax, ?PersistedControlFactoryList@@3PAU_unnamed_type_PersistedControlFactoryList_@@A; _unnamed_type_PersistedControlFactoryList_ near * PersistedControlFactoryList
0x180030527  mov     rax, (funcs_18003052C - 180085000h)[rax+r12*8]
0x18003052c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030531  mov     rcx, [rbp+5Fh]; this
0x180030535  test    eax, eax
0x180030537  jns     short loc_18003054D
0x180030539  mov     r9d, eax; char *
0x18003053c  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030543  mov     edx, 450h; void *
0x180030548  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003054d  mov     rcx, [rbp+57h+var_B8]; pv
0x180030551  test    rcx, rcx
0x180030554  jz      loc_1800305F9
0x18003055a  call    ?FinishConstruction@CPersistedControl@@QEAAJXZ; CPersistedControl::FinishConstruction(void)
0x18003055f  mov     ebx, eax
0x180030561  test    eax, eax
0x180030563  js      loc_18003077F
0x180030569  mov     r8, [rbp+57h+var_B0]; struct IPart *
0x18003056d  mov     rdx, rsi; struct IMMDevice *
0x180030570  mov     rcx, [rbp+57h+var_B8]; this
0x180030574  call    ?RestorePersistedState@CPersistedControl@@QEAAJPEAUIMMDevice@@PEAUIPart@@@Z; CPersistedControl::RestorePersistedState(IMMDevice *,IPart *)
0x180030579  mov     ebx, eax
0x18003057b  test    eax, eax
0x18003057d  js      loc_18003073D
0x180030583  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x180030587  mov     rcx, [rbp+57h+var_B8]; this
0x18003058b  call    ?RegisterForControlChangeCallbacks@CPersistedControl@@QEAAJAEAU_GUID@@@Z; CPersistedControl::RegisterForControlChangeCallbacks(_GUID &)
0x180030590  mov     ebx, eax
0x180030592  test    eax, eax
0x180030594  js      loc_1800306F8
0x18003059a  mov     rdx, [rbp+57h+var_B8]
0x18003059e  lea     rcx, ?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A; TList<CPersistedControl> g_PersistedControlList
0x1800305a5  call    ?AddTail@?$TList@VCPersistedControl@@@@QEAAPEAXPEAVCPersistedControl@@@Z; TList<CPersistedControl>::AddTail(CPersistedControl *)
0x1800305aa  test    rax, rax
0x1800305ad  jz      loc_1800306AE
0x1800305b3  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800305b8  mov     ecx, [rax]
0x1800305ba  cmp     ecx, 4
0x1800305bd  jbe     short loc_1800305F2
0x1800305bf  mov     rdx, [rbp+57h+var_B8]
0x1800305c3  mov     ecx, [rdx+40h]
0x1800305c6  mov     [rbp+57h+var_78], ecx
0x1800305c9  mov     rcx, [rdx+48h]
0x1800305cd  mov     [rbp+57h+var_70], rcx
0x1800305d1  lea     rcx, [rbp+57h+var_78]
0x1800305d5  mov     [rsp+0F0h+var_C8], rcx
0x1800305da  lea     rcx, [rbp+57h+var_70]
0x1800305de  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x1800305e3  lea     rdx, byte_1800774E9
0x1800305ea  mov     rcx, rax
0x1800305ed  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800305f2  mov     rcx, r13; this
0x1800305f5  mov     [rbp+57h+var_B8], rcx
0x1800305f9  mov     [rbp+57h+var_48], r13b
0x1800305fd  test    rcx, rcx
0x180030600  jz      short loc_18003061D
0x180030602  call    ?UnregisterForControlChangeCallbacks@CPersistedControl@@QEAAJXZ; CPersistedControl::UnregisterForControlChangeCallbacks(void)
0x180030607  mov     rcx, [rbp+57h+var_B8]
0x18003060b  test    rcx, rcx
0x18003060e  jz      short loc_18003061D
0x180030610  mov     rax, [rcx]
0x180030613  mov     rax, [rax+10h]
0x180030617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003061c  nop
0x18003061d  lea     rcx, [rbp+57h+var_A0]
0x180030621  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030626  inc     r14d
  ... truncated ...
```
