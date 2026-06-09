# WindowsInternal::Shell::CDSProperties::CDSTilePropertiesBatched::GetLocalProperties(HSTRING__ *,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem * *)

- ea: `0x180019f20`
- end: `0x18001a99f`
- name: `?GetLocalProperties@CDSTilePropertiesBatched@CDSProperties@Shell@WindowsInternal@@UEAAJPEAUHSTRING__@@PEAPEAUICDSTilePropertiesItem@234@@Z`
- size: `2687`
- prototype: `int(WindowsInternal::Shell::CDSProperties::CDSTilePropertiesBatched *__hidden this, HSTRING, struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801eb430`

## callees

- `0x18000ce94`
- `0x180019f20`
- `0x18001ac50`
- `0x18001aca4`
- `0x18001acc8`
- `0x180030e28`
- `0x1800433a4`
- `0x180043470`
- `0x1800ce14c`
- `0x1800dea20`
- `0x180147be8`
- `0x18014c434`
- `0x180201e50`
- `0x18020be0c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001a3a4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001a3a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019f65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019fb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019f65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019fb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a178`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a1ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a178`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a1ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a5bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a4ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a4ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a4db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a4db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ff5`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001a242`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001a242`

## string_xrefs

- `0x18001a153`: `shellcommon\shell\datastorecache\transformers\cdsdatatransformer\lib\cdstilepropertiesbatched.cpp`
- `0x18001a50c`: `shellcommon\shell\datastorecache\transformers\cdsdatatransformer\lib\cdstilepropertiesbatched.cpp`
- `0x18001a56b`: `shellcommon\shell\datastorecache\transformers\cdsdatatransformer\lib\cdstilepropertiesbatched.cpp`
- `0x18001a61c`: `shellcommon\shell\datastorecache\transformers\cdsdatatransformer\lib\cdstilepropertiesbatched.cpp`
- `0x18001a7eb`: `shellcommon\shell\datastorecache\transformers\cdsdatatransformer\lib\cdstilepropertiesbatched.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsInternal::Shell::CDSProperties::CDSTilePropertiesBatched::GetLocalProperties(
        RTL_SRWLOCK *this,
        HSTRING a2,
        struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem **a3)
{
  HSTRING v3; // r14
  RTL_SRWLOCK *v4; // r15
  RTL_SRWLOCK *v5; // rdi
  volatile signed __int32 *Ptr; // rax
  char *v7; // rbx
  std::_Ref_count_base *v8; // r12
  __int64 v9; // rax
  IUnknown *v10; // rsi
  PCWSTR StringRawBuffer; // rax
  struct IUnknownVtbl *lpVtbl; // r13
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  const wchar_t *v14; // rcx
  size_t v15; // r14
  const wchar_t *v16; // rdx
  size_t v17; // rsi
  size_t v18; // r8
  int v19; // eax
  const wchar_t *p_AddRef; // rdx
  size_t QueryInterface; // rbx
  size_t v22; // rsi
  const wchar_t *v23; // rcx
  size_t v24; // r8
  int v25; // eax
  LPUNKNOWN v26; // rbx
  struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem **v27; // r13
  WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties *v28; // rax
  HRESULT v29; // ebx
  const char *v30; // r9
  __int64 result; // rax
  unsigned int v32; // ecx
  signed __int64 v33; // rax
  signed __int64 v34; // rtt
  struct Microsoft::WRL::Details::ModuleBase *v35; // rcx
  char *v36; // rsi
  LPUNKNOWN v37; // rbx
  HRESULT (__stdcall *v38)(IUnknown *, const IID *const, void **); // rax
  _QWORD *v39; // rcx
  LPUNKNOWN v40; // rcx
  __int64 v41; // rcx
  HRESULT v42; // ebx
  LPUNKNOWN v43; // rbx
  __int64 v44; // rcx
  LPUNKNOWN v45; // rcx
  HRESULT (__stdcall *v46)(IUnknown *, const IID *const, void **); // rcx
  HSTRING v47; // rbx
  __int64 v48; // rdx
  signed __int64 v49; // rax
  unsigned int v50; // ecx
  signed __int64 v51; // rtt
  HSTRING v52; // rax
  HSTRING v53; // rsi
  __int64 v54; // rcx
  LPUNKNOWN v55; // rbx
  __int64 v56; // rcx
  LPUNKNOWN v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rdx
  HRESULT (__stdcall *v60)(IUnknown *, const IID *const, void **); // rcx
  __int64 v61; // rcx
  signed __int64 v62; // rax
  unsigned int v63; // ecx
  signed __int64 v64; // rtt
  UINT32 length[2]; // [rsp+20h] [rbp-E8h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+28h] [rbp-E0h] BYREF
  struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem **v67; // [rsp+30h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  std::_Ref_count_base *v69; // [rsp+40h] [rbp-C8h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h]
  _QWORD v71[2]; // [rsp+50h] [rbp-B8h] BYREF
  std::_Ref_count_base *v72; // [rsp+60h] [rbp-A8h]
  IUnknown *v73; // [rsp+68h] [rbp-A0h]
  std::_Ref_count_base *v74; // [rsp+70h] [rbp-98h]
  int v75; // [rsp+84h] [rbp-84h]
  RTL_SRWLOCK *v76; // [rsp+88h] [rbp-80h]
  int v77; // [rsp+9Ch] [rbp-6Ch]
  wchar_t *S2[2]; // [rsp+A8h] [rbp-60h] BYREF
  size_t N[2]; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v67 = a3;
  v3 = a2;
  string = a2;
  v4 = this;
  *a3 = 0;
  v5 = this + 60;
  AcquireSRWLockShared(this + 60);
  try
  {
    v76 = v5;
    if ( !v4[18].Ptr )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdstilepropertiesbatched.cpp",
        (const char *)0x8007139FLL,
        length[0]);
      if ( v5 )
        ReleaseSRWLockShared(v5);
      return 2147947423LL;
    }
    Ptr = (volatile signed __int32 *)v4[19].Ptr;
    if ( Ptr )
      _InterlockedIncrement(Ptr + 2);
    v7 = (char *)v4[18].Ptr;
    v71[1] = v7;
    v8 = (std::_Ref_count_base *)v4[19].Ptr;
    v72 = v8;
    SRWLock = (PSRWLOCK)(v7 + 40);
    AcquireSRWLockShared((PSRWLOCK)v7 + 5);
    v71[0] = v7 + 40;
    v9 = *((_QWORD *)v7 + 7);
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v10 = (IUnknown *)*((_QWORD *)v7 + 6);
    ppunkMarshal = v10;
    v73 = v10;
    v69 = (std::_Ref_count_base *)*((_QWORD *)v7 + 7);
    v74 = v69;
    length[0] = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v3, length);
    *(_OWORD *)S2 = 0;
    *(_OWORD *)N = 0;
    std::wstring::_Construct<1,unsigned short const *>(S2, StringRawBuffer, length[0]);
    lpVtbl = v10->lpVtbl;
    AddRef = v10->lpVtbl->AddRef;
    v77 = 0;
    if ( !*((_BYTE *)AddRef + 25) )
    {
      while ( 1 )
      {
        v14 = (const wchar_t *)((char *)AddRef + 32);
        v15 = N[0];
        v16 = (const wchar_t *)S2;
        if ( N[1] > 7 )
          v16 = S2[0];
        v17 = *((_QWORD *)AddRef + 6);
        if ( *((_QWORD *)AddRef + 7) > 7u )
          v14 = *(const wchar_t **)v14;
        v18 = *((_QWORD *)AddRef + 6);
        if ( N[0] < v17 )
          v18 = N[0];
        v19 = wmemcmp(v14, v16, v18);
        if ( v19 )
        {
          if ( v19 < 0 )
            goto LABEL_18;
        }
        else if ( v17 < v15 )
        {
LABEL_18:
          AddRef = (ULONG (__stdcall *)(IUnknown *))((char *)AddRef + 16);
          goto LABEL_19;
        }
        lpVtbl = (struct IUnknownVtbl *)AddRef;
LABEL_19:
        AddRef = *(ULONG (__stdcall **)(IUnknown *))AddRef;
        if ( *((_BYTE *)AddRef + 25) )
        {
          v3 = string;
          break;
        }
      }
    }
    if ( !BYTE1(lpVtbl[1].QueryInterface) )
    {
      p_AddRef = (const wchar_t *)&lpVtbl[1].AddRef;
      QueryInterface = (size_t)lpVtbl[2].QueryInterface;
      if ( (char *)lpVtbl[2].AddRef > (char *)7 )
        p_AddRef = *(const wchar_t **)p_AddRef;
      v22 = N[0];
      v23 = (const wchar_t *)S2;
      if ( N[1] > 7 )
        v23 = S2[0];
      v24 = N[0];
      if ( QueryInterface < N[0] )
        v24 = (size_t)lpVtbl[2].QueryInterface;
      v25 = wmemcmp(v23, p_AddRef, v24);
      if ( v25 )
      {
        if ( v25 >= 0 )
        {
LABEL_30:
          v26 = ppunkMarshal;
LABEL_31:
          if ( N[1] > 7 )
            std::_Deallocate<16>(S2[0], 2 * N[1] + 2);
          if ( lpVtbl == v26->lpVtbl )
          {
            v27 = v67;
            *v67 = 0;
            v28 = (WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties *)operator new(
                                                                                     0xB0u,
                                                                                     (const struct std::nothrow_t *)std::nothrow);
            if ( !v28 )
            {
              v29 = -2147024882;
LABEL_36:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x131,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdstilepropertiesbatched.cpp",
                (const char *)(unsigned int)v29,
                length[0]);
              GenericCloudItemReadableData<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>::~GenericCloudItemReadableData<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(v71);
              if ( v5 )
                ReleaseSRWLockShared(v5);
              return (unsigned int)v29;
            }
            v52 = (HSTRING)WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::CDSLocalTileProperties(v28);
            v53 = v52;
            string = v52;
            v67 = 0;
            if ( v4 == (RTL_SRWLOCK *)16 )
              v4 = 0;
            *((_QWORD *)v52 + 13) = 0;
            *((_QWORD *)v52 + 14) = 0;
            *((_DWORD *)v52 + 30) = 0;
            *((_WORD *)v52 + 62) = 0;
            *((_BYTE *)v52 + 126) = 0;
            *((_BYTE *)v52 + 127) = HIBYTE(v72);
            *((_QWORD *)v52 + 16) = 0;
            *((_BYTE *)v52 + 136) = 0;
            *(_DWORD *)((char *)v52 + 137) = *(_DWORD *)((char *)&v74 + 1);
            *(_WORD *)((char *)v52 + 141) = *(_WORD *)((char *)&v74 + 5);
            *((_BYTE *)v52 + 143) = HIBYTE(v74);
            *((_QWORD *)v52 + 18) = 0;
            *((_DWORD *)v52 + 38) = 1;
            *((_DWORD *)v52 + 39) = v75;
            v54 = *((_QWORD *)v52 + 12);
            *((_QWORD *)v52 + 12) = 0;
            if ( v54 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            *(_QWORD *)length = 0;
            v29 = (*(__int64 (__fastcall **)(RTL_SRWLOCK *, GUID *, UINT32 *))v4->Ptr)(
                    v4,
                    &GUID_00000038_0000_0000_c000_000000000046,
                    length);
            if ( v29 < 0 )
            {
              v61 = *(_QWORD *)length;
              if ( *(_QWORD *)length )
              {
                *(_QWORD *)length = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
              }
            }
            else
            {
              ppunkMarshal = 0;
              v29 = (*(__int64 (__fastcall **)(_QWORD, LPUNKNOWN *))(**(_QWORD **)length + 24LL))(
                      *(_QWORD *)length,
                      &ppunkMarshal);
              if ( v29 < 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
              }
              else
              {
                v55 = ppunkMarshal;
                if ( ppunkMarshal )
                  ((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->AddRef)(ppunkMarshal);
                v56 = *((_QWORD *)v53 + 12);
                *((_QWORD *)v53 + 12) = v55;
                if ( v56 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                v57 = ppunkMarshal;
                if ( ppunkMarshal )
                {
                  ppunkMarshal = 0;
                  ((void (__fastcall *)(LPUNKNOWN))v57->lpVtbl->Release)(v57);
                }
                v58 = *(_QWORD *)length;
                if ( *(_QWORD *)length )
                {
                  *(_QWORD *)length = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                }
                v29 = 0;
              }
            }
            if ( v29 < 0 )
            {
              v59 = 1176;
              goto LABEL_122;
            }
            if ( !v3 || v3 != *((HSTRING *)v53 + 11) )
            {
              WindowsDeleteString(*((HSTRING *)v53 + 11));
              *((_QWORD *)v53 + 11) = 0;
              v29 = WindowsDuplicateString(v3, (HSTRING *)v53 + 11);
              if ( v29 < 0 )
              {
                v59 = 1177;
LABEL_122:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v59,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdstilepropertiesbatched.cpp",
                  (const char *)(unsigned int)v29,
                  length[0]);
                Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties>::InternalRelease(&string);
                Microsoft::WRL::Details::MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>::~MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>(&v67);
                goto LABEL_36;
              }
            }
            *v27 = (struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *)v53;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v53 + 8LL))(v53);
            if ( !v53 )
              goto LABEL_44;
            v62 = *((_QWORD *)v53 + 10);
            while ( v62 >= 0 )
            {
              if ( (_DWORD)v62 == 0x7FFFFFFF )
                goto LABEL_44;
              v63 = v62 - 1;
              v64 = v62;
              v62 = _InterlockedCompareExchange64((volatile signed __int64 *)v53 + 10, v62 - 1, v62);
              if ( v64 == v62 )
                goto LABEL_137;
            }
            v63 = Microsoft::WRL::Details::StrongReference::DecrementStrongReference((Microsoft::WRL::Details::StrongReference *)(2 * v62 + 16));
LABEL_137:
            if ( v63 )
              goto LABEL_44;
            (*(void (__fastcall **)(HSTRING, __int64))(*(_QWORD *)v53 + 64LL))(v53, 1);
            v35 = Microsoft::WRL::Details::ModuleBase::module_;
            if ( !Microsoft::WRL::Details::ModuleBase::module_ )
              goto LABEL_44;
LABEL_139:
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_44:
            if ( v69 )
              std::_Ref_count_base::_Decref(v69);
            if ( v8 )
              std::_Ref_count_base::_Decref(v8);
            if ( SRWLock )
              ReleaseSRWLockShared(SRWLock);
            if ( v5 )
              ReleaseSRWLockShared(v5);
            return 0;
          }
          *v67 = 0;
          v36 = (char *)operator new(0xB0u, (const struct std::nothrow_t *)std::nothrow);
          if ( v36 )
          {
            *((_QWORD *)v36 + 5) = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
            *((_QWORD *)v36 + 8) = 0;
            ppunkMarshal = 0;
            if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
            {
              v37 = ppunkMarshal;
              v38 = ppunkMarshal->lpVtbl->QueryInterface;
              *(_QWORD *)length = v38;
              v39 = (_QWORD *)*((_QWORD *)v36 + 8);
              if ( v39 )
              {
                *((_QWORD *)v36 + 8) = 0;
                (*(void (__fastcall **)(_QWORD *, _QWORD))(*v39 + 16LL))(v39, *v39);
                v38 = *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))length;
              }
              ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))v38)(
                v37,
                &GUID_00000003_0000_0000_c000_000000000046,
                v36 + 64);
            }
            v40 = ppunkMarshal;
            if ( ppunkMarshal )
            {
              ppunkMarshal = 0;
              ((void (__fastcall *)(LPUNKNOWN))v40->lpVtbl->Release)(v40);
            }
            *((_QWORD *)v36 + 10) = 1;
            *(_QWORD *)v36 = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem'};
            *((_QWORD *)v36 + 1) = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'};
            *((_QWORD *)v36 + 2) = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>'};
            *((_QWORD *)v36 + 3) = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'};
            *((_QWORD *)v36 + 4) = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>'};
            *((_QWORD *)v36 + 5) = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            if ( Microsoft::WRL::Details::ModuleBase::module_ )
              (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
            *(_QWORD *)v36 = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem'};
            *((_QWORD *)v36 + 1) = &Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'};
            *((_QWORD *)v36 + 2) = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>'};
            *((_QWORD *)v36 + 3) = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'};
            *((_QWORD *)v36 + 4) = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>'};
            *((_QWORD *)v36 + 5) = &WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            *((_QWORD *)v36 + 11) = 0;
            *((_QWORD *)v36 + 12) = 0;
            *((_QWORD *)v36 + 13) = 0;
            *((_QWORD *)v36 + 14) = 0;
            *((_DWORD *)v36 + 30) = 0;
            *((_WORD *)v36 + 62) = 0;
            v36[126] = 0;
            *((_QWORD *)v36 + 16) = 0;
            v36[136] = 0;
            *((_QWORD *)v36 + 18) = 0;
            *((_DWORD *)v36 + 38) = 1;
            *((_DWORD *)v36 + 40) = 0;
            InitializeSRWLock((PSRWLOCK)v36 + 21);
            if ( v4 == (RTL_SRWLOCK *)16 )
              v4 = 0;
            *(_OWORD *)(v36 + 104) = *(_OWORD *)&lpVtbl[2].Release;
            *(_OWORD *)(v36 + 120) = *(_OWORD *)&lpVtbl[3].AddRef;
            *(_OWORD *)(v36 + 136) = *(_OWORD *)&lpVtbl[4].QueryInterface;
            *((_QWORD *)v36 + 19) = lpVtbl[4].Release;
            v41 = *((_QWORD *)v36 + 12);
            *((_QWORD *)v36 + 12) = 0;
            if ( v41 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            *(_QWORD *)length = 0;
            v42 = (*(__int64 (__fastcall **)(RTL_SRWLOCK *, GUID *, UINT32 *))v4->Ptr)(
                    v4,
                    &GUID_00000038_0000_0000_c000_000000000046,
                    length);
            if ( v42 < 0 )
            {
              v60 = *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))length;
              if ( *(_QWORD *)length )
              {
                *(_QWORD *)length = 0;
                (*(void (__fastcall **)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **)))(*(_QWORD *)v60 + 16LL))(v60);
              }
            }
            else
            {
              ppunkMarshal = 0;
              v42 = (*(__int64 (__fastcall **)(_QWORD, LPUNKNOWN *))(**(_QWORD **)length + 24LL))(
                      *(_QWORD *)length,
                      &ppunkMarshal);
              if ( v42 < 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
              }
              else
              {
                v43 = ppunkMarshal;
                if ( ppunkMarshal )
                  ((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->AddRef)(ppunkMarshal);
                v44 = *((_QWORD *)v36 + 12);
                *((_QWORD *)v36 + 12) = v43;
                if ( v44 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                v45 = ppunkMarshal;
                if ( ppunkMarshal )
                {
                  ppunkMarshal = 0;
                  ((void (__fastcall *)(LPUNKNOWN))v45->lpVtbl->Release)(v45);
                }
                v46 = *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))length;
                if ( *(_QWORD *)length )
                {
                  *(_QWORD *)length = 0;
                  (*(void (__fastcall **)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **)))(*(_QWORD *)v46 + 16LL))(v46);
                }
                v42 = 0;
              }
            }
            if ( v42 < 0 )
            {
              v48 = 1176;
            }
            else
            {
              v47 = string;
              if ( string && string == *((HSTRING *)v36 + 11)
                || (WindowsDeleteString(*((HSTRING *)v36 + 11)),
                    *((_QWORD *)v36 + 11) = 0,
                    v42 = WindowsDuplicateString(v47, (HSTRING *)v36 + 11),
                    v42 >= 0) )
              {
                *v67 = (struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *)v36;
                (*(void (__fastcall **)(char *))(*(_QWORD *)v36 + 8LL))(v36);
                v33 = *((_QWORD *)v36 + 10);
                while ( v33 >= 0 )
                {
                  if ( (_DWORD)v33 == 0x7FFFFFFF )
                    goto LABEL_44;
                  v32 = v33 - 1;
                  v34 = v33;
                  v33 = _InterlockedCompareExchange64((volatile signed __int64 *)v36 + 10, v33 - 1, v33);
                  if ( v34 == v33 )
                    goto LABEL_42;
                }
                v32 = Microsoft::WRL::Details::StrongReference::DecrementStrongReference((Microsoft::WRL::Details::StrongReference *)(2 * v33 + 16));
LABEL_42:
                if ( v32 )
                  goto LABEL_44;
                (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v36 + 64LL))(v36, 1);
                v35 = Microsoft::WRL::Details::ModuleBase::module_;
                if ( !Microsoft::WRL::Details::ModuleBase::module_ )
                  goto LABEL_44;
                goto LABEL_139;
              }
              v48 = 1177;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v48,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdstilepropertiesbatched.cpp",
              (const char *)(unsigned int)v42,
              length[0]);
            v49 = *((_QWORD *)v36 + 10);
            while ( v49 >= 0 )
            {
              if ( (_DWORD)v49 == 0x7FFFFFFF )
                goto LABEL_88;
              v50 = v49 - 1;
              v51 = v49;
              v49 = _InterlockedCompareExchange64((volatile signed __int64 *)v36 + 10, v49 - 1, v49);
              if ( v51 == v49 )
                goto LABEL_85;
            }
            v50 = Microsoft::WRL::Details::StrongReference::DecrementStrongReference((Microsoft::WRL::Details::StrongReference *)(2 * v49 + 16));
LABEL_85:
            if ( !v50 )
            {
              (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v36 + 64LL))(v36, 1);
              if ( Microsoft::WRL::Details::ModuleBase::module_ )
                (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                     + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
            }
          }
          else
          {
            v42 = -2147024882;
          }
LABEL_88:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12D,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdstilepropertiesbatched.cpp",
            (const char *)(unsigned int)v42,
            length[0]);
          if ( v69 )
            std::_Ref_count_base::_Decref(v69);
          if ( v8 )
            std::_Ref_count_base::_Decref(v8);
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
          if ( v5 )
            ReleaseSRWLockShared(v5);
          return (unsigned int)v42;
        }
      }
      else if ( v22 >= QueryInterface )
      {
        goto LABEL_30;
      }
    }
    v26 = ppunkMarshal;
    lpVtbl = ppunkMarshal->lpVtbl;
    goto LABEL_31;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x135,
                           (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\cdsdatatransformer\\lib\\cdst"
                                         "ilepropertiesbatched.cpp",
                           v30);
  }
  return result;
}

```

## disassembly

```asm
0x180019f20  push    rbx
0x180019f22  push    rsi
0x180019f23  push    rdi
0x180019f24  push    r12
0x180019f26  push    r13
0x180019f28  push    r14
0x180019f2a  push    r15
0x180019f2c  sub     rsp, 0D0h
0x180019f33  mov     rax, cs:__security_cookie
0x180019f3a  xor     rax, rsp
0x180019f3d  mov     [rsp+108h+var_40], rax
0x180019f45  mov     [rsp+108h+var_D8], r8
0x180019f4a  mov     r14, rdx
0x180019f4d  mov     [rsp+108h+string], rdx
0x180019f52  mov     r15, rcx
0x180019f55  xor     r13d, r13d
0x180019f58  mov     [r8], r13
0x180019f5b  lea     rdi, [rcx+1E0h]
0x180019f62  mov     rcx, rdi; SRWLock
0x180019f65  call    cs:__imp_AcquireSRWLockShared
0x180019f6b  mov     [rsp+108h+var_80], rdi
0x180019f73  cmp     [r15+90h], r13
0x180019f7a  jz      loc_18001A60E
0x180019f80  mov     rax, [r15+98h]
0x180019f87  test    rax, rax
0x180019f8a  jz      short loc_180019F90
0x180019f8c  lock inc dword ptr [rax+8]
0x180019f90  mov     rbx, [r15+90h]
0x180019f97  mov     [rsp+108h+var_B0], rbx
0x180019f9c  mov     r12, [r15+98h]
0x180019fa3  mov     [rsp+108h+var_A8], r12
0x180019fa8  lea     rsi, [rbx+28h]
0x180019fac  mov     [rsp+108h+SRWLock], rsi
0x180019fb1  mov     rcx, rsi; SRWLock
0x180019fb4  call    cs:__imp_AcquireSRWLockShared
0x180019fba  mov     [rsp+108h+var_B8], rsi
0x180019fbf  mov     rax, [rbx+38h]
0x180019fc3  test    rax, rax
0x180019fc6  jz      short loc_180019FCC
0x180019fc8  lock inc dword ptr [rax+8]
0x180019fcc  mov     rsi, [rbx+30h]
0x180019fd0  mov     [rsp+108h+ppunkMarshal], rsi
0x180019fd5  mov     [rsp+108h+var_A0], rsi
0x180019fda  mov     rax, [rbx+38h]
0x180019fde  mov     [rsp+108h+var_C8], rax
0x180019fe3  mov     [rsp+108h+var_98], rax
0x180019fe8  mov     [rsp+108h+length], r13d; int
0x180019fed  lea     rdx, [rsp+108h+length]; length
0x180019ff2  mov     rcx, r14; string
0x180019ff5  call    cs:__imp_WindowsGetStringRawBuffer
0x180019ffb  xorps   xmm0, xmm0
0x180019ffe  movups  xmmword ptr [rsp+108h+S2], xmm0
0x18001a006  xorps   xmm1, xmm1
0x18001a009  movdqu  xmmword ptr [rsp+108h+N], xmm1
0x18001a012  mov     r8d, [rsp+108h+length]
0x18001a017  mov     rdx, rax
0x18001a01a  lea     rcx, [rsp+108h+S2]
0x18001a022  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a027  mov     r13, [rsi]
0x18001a02a  mov     rbx, [r13+8]
0x18001a02e  xor     eax, eax
0x18001a030  mov     [rsp+108h+var_6C], eax
0x18001a037  cmp     [rbx+19h], al
0x18001a03a  jnz     short loc_18001A0A2
0x18001a03c  lea     rcx, [rbx+20h]; S1
0x18001a040  mov     r14, [rsp+108h+N]
0x18001a048  lea     rdx, [rsp+108h+S2]
0x18001a050  cmp     [rsp+108h+N+8], 7
0x18001a059  cmova   rdx, [rsp+108h+S2]; S2
0x18001a062  mov     rsi, [rbx+30h]
0x18001a066  cmp     qword ptr [rcx+18h], 7
0x18001a06b  ja      loc_18001A204
0x18001a071  mov     r8, rsi
0x18001a074  cmp     r14, rsi
0x18001a077  cmovb   r8, r14; N
0x18001a07b  call    wmemcmp
0x18001a080  test    eax, eax
0x18001a082  jz      short loc_18001A08B
0x18001a084  js      short loc_18001A090
0x18001a086  mov     r13, rbx
0x18001a089  jmp     short loc_18001A094
0x18001a08b  cmp     rsi, r14
0x18001a08e  jnb     short loc_18001A086
0x18001a090  add     rbx, 10h
0x18001a094  mov     rbx, [rbx]
0x18001a097  cmp     byte ptr [rbx+19h], 0
0x18001a09b  jz      short loc_18001A03C
0x18001a09d  mov     r14, [rsp+108h+string]
0x18001a0a2  cmp     byte ptr [r13+19h], 0
0x18001a0a7  jnz     loc_18001A819
0x18001a0ad  lea     rdx, [r13+20h]
0x18001a0b1  mov     rbx, [rdx+10h]
0x18001a0b5  cmp     qword ptr [rdx+18h], 7
0x18001a0ba  jbe     short loc_18001A0BF
0x18001a0bc  mov     rdx, [rdx]; S2
0x18001a0bf  mov     rsi, [rsp+108h+N]
0x18001a0c7  lea     rcx, [rsp+108h+S2]
0x18001a0cf  cmp     [rsp+108h+N+8], 7
0x18001a0d8  cmova   rcx, [rsp+108h+S2]; S1
0x18001a0e1  mov     r8, rsi
0x18001a0e4  cmp     rbx, rsi
0x18001a0e7  cmovb   r8, rbx; N
0x18001a0eb  call    wmemcmp
0x18001a0f0  test    eax, eax
0x18001a0f2  jz      loc_18001A810
0x18001a0f8  js      loc_18001A819
0x18001a0fe  mov     rbx, [rsp+108h+ppunkMarshal]
0x18001a103  mov     rdx, [rsp+108h+N+8]
0x18001a10b  cmp     rdx, 7
0x18001a10f  ja      loc_18001A5F4
0x18001a115  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a11c  mov     ecx, 0B0h; unsigned __int64
0x18001a121  cmp     r13, [rbx]
0x18001a124  jnz     loc_18001A20C
0x18001a12a  mov     r13, [rsp+108h+var_D8]
0x18001a12f  xor     ebx, ebx
0x18001a131  mov     [r13+0], rbx
0x18001a135  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a13a  test    rax, rax
0x18001a13d  jnz     loc_18001A643
0x18001a143  mov     ebx, 8007000Eh
0x18001a148  mov     rcx, [rsp+108h]; this
0x18001a150  mov     r9d, ebx; char *
0x18001a153  lea     r8, aShellcommonShe_28; "shellcommon\\shell\\datastorecache\\tra"...
0x18001a15a  mov     edx, 131h; void *
0x18001a15f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a164  nop
0x18001a165  lea     rcx, [rsp+108h+var_B8]
0x18001a16a  call    ??1?$GenericCloudItemReadableData@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@@QEAA@XZ; GenericCloudItemReadableData<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>::~GenericCloudItemReadableData<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(void)
0x18001a16f  nop
0x18001a170  test    rdi, rdi
0x18001a173  jz      short loc_18001A17E
0x18001a175  mov     rcx, rdi; SRWLock
0x18001a178  call    cs:__imp_ReleaseSRWLockShared
0x18001a17e  mov     eax, ebx
0x18001a180  jmp     loc_18001A5C7
0x18001a185  test    rax, rax
0x18001a188  js      loc_18001A982
0x18001a18e  cmp     eax, 7FFFFFFFh
0x18001a193  jz      short loc_18001A1C9
0x18001a195  lea     rcx, [rax-1]
0x18001a199  lock cmpxchg [rsi+50h], rcx
0x18001a19f  jnz     short loc_18001A185
0x18001a1a1  test    ecx, ecx
0x18001a1a3  jnz     short loc_18001A1C9
0x18001a1a5  mov     rax, [rsi]
0x18001a1a8  mov     edx, 1
0x18001a1ad  mov     rcx, rsi
0x18001a1b0  mov     rax, [rax+40h]
0x18001a1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001a1c0  test    rcx, rcx
0x18001a1c3  jnz     loc_18001A8DE
0x18001a1c9  mov     rcx, [rsp+108h+var_C8]; this
0x18001a1ce  test    rcx, rcx
0x18001a1d1  jz      short loc_18001A1D8
0x18001a1d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a1d8  test    r12, r12
0x18001a1db  jz      short loc_18001A1E5
0x18001a1dd  mov     rcx, r12; this
0x18001a1e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a1e5  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18001a1ea  test    rcx, rcx
0x18001a1ed  jz      short loc_18001A1F6
0x18001a1ef  call    cs:__imp_ReleaseSRWLockShared
0x18001a1f5  nop
0x18001a1f6  test    rdi, rdi
0x18001a1f9  jz      loc_18001A5C5
0x18001a1ff  jmp     loc_18001A5BC
0x18001a204  mov     rcx, [rcx]
0x18001a207  jmp     loc_18001A071
0x18001a20c  mov     rax, [rsp+108h+var_D8]
0x18001a211  xor     ebx, ebx
0x18001a213  mov     [rax], rbx
0x18001a216  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a21b  mov     rsi, rax
0x18001a21e  test    rax, rax
0x18001a221  jz      loc_18001A919
0x18001a227  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18001a22e  mov     [rsi+28h], rax
0x18001a232  mov     [rsi+40h], rbx
0x18001a236  mov     [rsp+108h+ppunkMarshal], rbx
0x18001a23b  lea     rdx, [rsp+108h+ppunkMarshal]; ppunkMarshal
0x18001a240  xor     ecx, ecx; punkOuter
0x18001a242  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001a248  test    eax, eax
0x18001a24a  js      short loc_18001A294
0x18001a24c  mov     rbx, [rsp+108h+ppunkMarshal]
0x18001a251  mov     rax, [rbx]
0x18001a254  mov     rax, [rax]
0x18001a257  mov     qword ptr [rsp+108h+length], rax
0x18001a25c  mov     rcx, [rsi+40h]
0x18001a260  test    rcx, rcx
0x18001a263  jz      short loc_18001A27E
0x18001a265  mov     qword ptr [rsi+40h], 0
0x18001a26d  mov     rdx, [rcx]
0x18001a270  mov     rax, [rdx+10h]
0x18001a274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a279  mov     rax, qword ptr [rsp+108h+length]
0x18001a27e  lea     r8, [rsi+40h]
0x18001a282  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001a289  mov     rcx, rbx
0x18001a28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a291  nop
0x18001a292  xor     ebx, ebx
0x18001a294  mov     rcx, [rsp+108h+ppunkMarshal]
0x18001a299  test    rcx, rcx
0x18001a29c  jz      short loc_18001A2B0
0x18001a29e  mov     [rsp+108h+ppunkMarshal], rbx
0x18001a2a3  mov     rax, [rcx]
0x18001a2a6  mov     rax, [rax+10h]
0x18001a2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2af  nop
0x18001a2b0  mov     qword ptr [rsi+50h], 1
0x18001a2b8  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6BICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem'}
0x18001a2bf  mov     [rsi], rax
0x18001a2c2  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@23@UICDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'}
0x18001a2c9  mov     [rsi+8], rax
0x18001a2cd  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>'}
0x18001a2d4  mov     [rsi+10h], rax
0x18001a2d8  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'}
0x18001a2df  mov     [rsi+18h], rax
0x18001a2e3  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>'}
0x18001a2ea  mov     [rsi+20h], rax
0x18001a2ee  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a2f5  mov     [rsi+28h], rax
0x18001a2f9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001a300  test    rcx, rcx
0x18001a303  jz      short loc_18001A312
0x18001a305  mov     rax, [rcx]
0x18001a308  mov     rax, [rax+8]
0x18001a30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a311  nop
0x18001a312  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6BICDSTilePropertiesItem@123@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem'}
0x18001a319  mov     [rsi], rax
0x18001a31c  lea     rax, ??_7?$RuntimeClass@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@UICDSLocalTileProperties@234@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@67@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@23@UICDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'}
0x18001a323  mov     [rsi+8], rax
0x18001a327  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSTilePropertiesItemPriv@CDSProperties@Shell@WindowsInternal@@@Details@WRL@Microsoft@@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItemPriv>'}
0x18001a32e  mov     [rsi+10h], rax
0x18001a332  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@U?$CloakedIid@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTileProperties,Microsoft::WRL::CloakedIid<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>,Microsoft::WRL::FtmBase>'}
0x18001a339  mov     [rsi+18h], rax
0x18001a33d  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@Details@WRL@Microsoft@@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>'}
0x18001a344  mov     [rsi+20h], rax
0x18001a348  lea     rax, ??_7CDSLocalTileProperties@CDSProperties@Shell@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const WindowsInternal::Shell::CDSProperties::CDSLocalTileProperties::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a34f  mov     [rsi+28h], rax
0x18001a353  mov     [rsi+58h], rbx
0x18001a357  mov     [rsi+60h], rbx
0x18001a35b  mov     qword ptr [rsi+68h], 0
0x18001a363  mov     qword ptr [rsi+70h], 0
0x18001a36b  mov     [rsi+78h], ebx
0x18001a36e  mov     word ptr [rsi+7Ch], 0
0x18001a374  mov     byte ptr [rsi+7Eh], 0
0x18001a378  mov     [rsi+80h], rbx
0x18001a37f  mov     byte ptr [rsi+88h], 0
0x18001a386  mov     [rsi+90h], rbx
0x18001a38d  mov     dword ptr [rsi+98h], 1
0x18001a397  mov     [rsi+0A0h], ebx
0x18001a39d  lea     rcx, [rsi+0A8h]; SRWLock
0x18001a3a4  call    cs:__imp_InitializeSRWLock
0x18001a3aa  lea     rdx, [r15-10h]
0x18001a3ae  test    rdx, rdx
0x18001a3b1  cmovz   r15, rbx
0x18001a3b5  movups  xmm0, xmmword ptr [r13+40h]
0x18001a3ba  movups  xmmword ptr [rsi+68h], xmm0
0x18001a3be  movups  xmm1, xmmword ptr [r13+50h]
0x18001a3c3  movups  xmmword ptr [rsi+78h], xmm1
0x18001a3c7  movups  xmm0, xmmword ptr [r13+60h]
0x18001a3cc  movups  xmmword ptr [rsi+88h], xmm0
0x18001a3d3  movsd   xmm1, qword ptr [r13+70h]
0x18001a3d9  movsd   qword ptr [rsi+98h], xmm1
0x18001a3e1  mov     rcx, [rsi+60h]
0x18001a3e5  mov     [rsi+60h], rbx
0x18001a3e9  test    rcx, rcx
0x18001a3ec  jz      short loc_18001A3FB
0x18001a3ee  mov     rax, [rcx]
0x18001a3f1  mov     rax, [rax+10h]
0x18001a3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3fa  nop
0x18001a3fb  mov     qword ptr [rsp+108h+length], rbx
0x18001a400  mov     rax, [r15]
0x18001a403  lea     r8, [rsp+108h+length]
0x18001a408  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x18001a40f  mov     rcx, r15
0x18001a412  mov     rax, [rax]
0x18001a415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a41a  mov     ebx, eax
0x18001a41c  test    eax, eax
0x18001a41e  js      loc_18001A82D
0x18001a424  xor     r15d, r15d
0x18001a427  mov     [rsp+108h+ppunkMarshal], r15
0x18001a42c  mov     rcx, qword ptr [rsp+108h+length]
0x18001a431  mov     rax, [rcx]
0x18001a434  lea     rdx, [rsp+108h+ppunkMarshal]
0x18001a439  mov     rax, [rax+18h]
0x18001a43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a442  mov     ebx, eax
0x18001a444  test    eax, eax
0x18001a446  js      loc_18001A923
0x18001a44c  mov     rbx, [rsp+108h+ppunkMarshal]
0x18001a451  test    rbx, rbx
  ... truncated ...
```
