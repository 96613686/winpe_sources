# Microsoft::WRL::Details::Make<BitmapBufferImpl,Microsoft::WRL::ComPtr<SoftwareBitmapState> &,Windows::Graphics::Imaging::BitmapBufferAccessMode const &>(Microsoft::WRL::ComPtr<SoftwareBitmapState> &,Windows::Graphics::Imaging::BitmapBufferAccessMode const &)

- ea: `0x1800049c0`
- end: `0x180004faa`
- name: `??$Make@VBitmapBufferImpl@@AEAV?$ComPtr@VSoftwareBitmapState@@@WRL@Microsoft@@AEBW4BitmapBufferAccessMode@Imaging@Graphics@Windows@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VBitmapBufferImpl@@@12@AEAV?$ComPtr@VSoftwareBitmapState@@@12@AEBW4BitmapBufferAccessMode@Imaging@Graphics@Windows@@@Z`
- size: `1514`
- prototype: `RTL_SRWLOCK **__fastcall(RTL_SRWLOCK **, RTL_SRWLOCK **, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x1800019c0`
- `0x1800049c0`
- `0x180005cd0`
- `0x180011e00`
- `0x180013000`
- `0x180026920`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x1800349d0`
- `0x180034a18`
- `0x180038bc0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004c15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004c15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d90`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180004b10`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180004b10`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004a51`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004a51`

## pseudocode

```c
RTL_SRWLOCK **__fastcall Microsoft::WRL::Details::Make<BitmapBufferImpl,Microsoft::WRL::ComPtr<SoftwareBitmapState> &,enum Windows::Graphics::Imaging::BitmapBufferAccessMode const &>(
        RTL_SRWLOCK **a1,
        RTL_SRWLOCK **a2,
        int *a3)
{
  RTL_SRWLOCK **v4; // rdi
  RTL_SRWLOCK *v6; // rax
  RTL_SRWLOCK *v7; // rbx
  int v8; // r14d
  LPUNKNOWN v9; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r12
  PVOID Ptr; // rcx
  LPUNKNOWN v12; // rcx
  RTL_SRWLOCK *v13; // rdx
  unsigned int v14; // r13d
  signed __int32 i; // eax
  RTL_SRWLOCK *v16; // rsi
  RTL_SRWLOCK *v17; // r12
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  LPUNKNOWN v21; // rdx
  PVOID v22; // rcx
  unsigned int v23; // r13d
  PVOID v24; // r14
  __int64 (__fastcall *v25)(PVOID, __int64 *, _QWORD, LPUNKNOWN *); // rdi
  int v26; // eax
  int v27; // eax
  int v28; // eax
  LPUNKNOWN v29; // rcx
  LPUNKNOWN v30; // rdi
  PVOID v31; // rdx
  unsigned int v33; // eax
  int v34; // edx
  int v35; // eax
  int v36; // r14d
  int v37; // r14d
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp-59h] BYREF
  int v39; // [rsp+48h] [rbp-51h] BYREF
  int v40; // [rsp+4Ch] [rbp-4Dh] BYREF
  IUnknown *v41; // [rsp+50h] [rbp-49h] BYREF
  int v42; // [rsp+58h] [rbp-41h]
  void **pExceptionObject; // [rsp+60h] [rbp-39h] BYREF
  int v44; // [rsp+68h] [rbp-31h]
  __int128 v45; // [rsp+70h] [rbp-29h]
  RTL_SRWLOCK **v46; // [rsp+80h] [rbp-19h]
  RTL_SRWLOCK *v47; // [rsp+88h] [rbp-11h]
  RTL_SRWLOCK *v48; // [rsp+90h] [rbp-9h]
  RTL_SRWLOCK *v49; // [rsp+98h] [rbp-1h]
  RTL_SRWLOCK *v50; // [rsp+A0h] [rbp+7h]
  __int64 v51; // [rsp+A8h] [rbp+Fh] BYREF
  int v52; // [rsp+B0h] [rbp+17h]
  int Ptr_high; // [rsp+B4h] [rbp+1Bh]

  v4 = a2;
  v41 = (IUnknown *)a2;
  v46 = a1;
  *a1 = 0;
  v42 = 1;
  v6 = (RTL_SRWLOCK *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v47 = v6;
  v48 = v6;
  if ( v6 )
  {
    v49 = v6;
    v8 = *a3;
    v6[6].Ptr = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
    v6[9].Ptr = 0;
    ppunkMarshal = 0;
    if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
    {
      v9 = ppunkMarshal;
      QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
      Ptr = v7[9].Ptr;
      if ( Ptr )
      {
        v7[9].Ptr = 0;
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      }
      ((void (__fastcall *)(LPUNKNOWN, GUID *, RTL_SRWLOCK *))QueryInterface)(
        v9,
        &GUID_00000003_0000_0000_c000_000000000046,
        &v7[9]);
      v4 = (RTL_SRWLOCK **)v41;
    }
    v12 = ppunkMarshal;
    if ( ppunkMarshal )
    {
      ppunkMarshal = 0;
      ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
    }
    v7[2].Ptr = &MediaBufferImpl::`vftable';
    v7[3].Ptr = &MediaBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'};
    v7[4].Ptr = &MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'};
    v7[5].Ptr = &MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'};
    v7[6].Ptr = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
    v7[11].Ptr = 0;
    v7[12].Ptr = 0;
    LODWORD(v7[13].Ptr) = 0;
    WORD2(v7[13].Ptr) = 0;
    BYTE6(v7[13].Ptr) = 0;
    InitializeSRWLock(v7 + 14);
    v7[16].Ptr = (PVOID)1;
    v7->Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable';
    v7[1].Ptr = &BitmapBufferImpl::`vftable'{for `IWeakReferenceSource'};
    v7[2].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>'};
    v7[3].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Windows::Foundation::IMemoryBuffer'};
    v7[4].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'};
    v7[5].Ptr = &BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'};
    v7[6].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v7->Ptr = &BitmapBufferImpl::`vftable';
    v7[1].Ptr = &BitmapBufferImpl::`vftable'{for `IWeakReferenceSource'};
    v7[2].Ptr = &BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>'};
    v7[3].Ptr = &BitmapBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'};
    v7[4].Ptr = &BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'};
    v7[5].Ptr = &BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'};
    v7[6].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    LODWORD(v7[17].Ptr) = v8;
    v13 = *v4;
    v7[18].Ptr = *v4;
    v14 = 0x7FFFFFFF;
    if ( v13 )
    {
      for ( i = HIDWORD(v13[1].Ptr); i != 0x7FFFFFFF; i = HIDWORD(v13[1].Ptr) )
      {
        if ( i == _InterlockedCompareExchange((volatile signed __int32 *)&v13[1].Ptr + 1, i + 1, i) )
          break;
      }
    }
    LODWORD(v7[19].Ptr) = 0;
    v16 = *v4;
    v17 = *v4 + 15;
    AcquireSRWLockExclusive(v17);
    v50 = v17;
    if ( BYTE4(v16[8].Ptr) )
      MF::ThrowOriginateError<28>(2147942405LL, L"Bitmap exclusive lock taken");
    v18 = (int)v16[8].Ptr;
    if ( v8 )
    {
      if ( v18 )
        MF::ThrowOriginateError<25>(2147942405LL, L"Bitmap shared lock taken");
      BYTE4(v16[8].Ptr) = 1;
      v19 = 0;
      v20 = 1;
    }
    else
    {
      v19 = v18 + 1;
      LODWORD(v16[8].Ptr) = v19;
      v20 = 0;
    }
    if ( g_wppLevels >= 0x20u )
      WPP_SF_qdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_03d17f9697cd315fdc8f56dcf9899f83_Traceguids,
        v16,
        v20,
        v19);
    v21 = (LPUNKNOWN)v16[9].Ptr;
    if ( !v21 )
    {
      v22 = v16[11].Ptr;
      if ( v22 )
      {
        if ( v8 )
        {
          v37 = v8 - 1;
          if ( v37 )
          {
            if ( v37 == 1 )
              v14 = 2;
          }
          else
          {
            v14 = 3;
          }
        }
        else
        {
          v14 = 1;
        }
        v41 = 0;
        ppunkMarshal = 0;
        v40 = 0;
        v39 = 0;
        v33 = (*(__int64 (__fastcall **)(PVOID, _QWORD, IUnknown **, int *, LPUNKNOWN *, int *))(*(_QWORD *)v22 + 80LL))(
                v22,
                v14,
                &v41,
                &v40,
                &ppunkMarshal,
                &v39);
        MF::ThrowIfFailed((MF *)v33, v34);
        v21 = ppunkMarshal;
        v16[9].Ptr = ppunkMarshal;
        LODWORD(v16[10].Ptr) = v39;
        v35 = v40;
        HIDWORD(v16[10].Ptr) = v40;
        if ( v35 < 0 )
          MF::ThrowOriginateError<30>();
      }
      else
      {
        if ( v8 )
        {
          v23 = 0;
          v36 = v8 - 1;
          if ( v36 )
          {
            if ( v36 == 1 )
              v23 = 2;
          }
          else
          {
            v23 = 3;
          }
        }
        else
        {
          v23 = 1;
        }
        v51 = 0;
        v52 = (int)v16[3].Ptr;
        Ptr_high = HIDWORD(v16[3].Ptr);
        ppunkMarshal = 0;
        v41 = 0;
        v39 = 0;
        v40 = 0;
        v24 = v16[13].Ptr;
        v25 = *(__int64 (__fastcall **)(PVOID, __int64 *, _QWORD, LPUNKNOWN *))(*(_QWORD *)v24 + 64LL);
        Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppunkMarshal);
        v26 = v25(v24, &v51, v23, &ppunkMarshal);
        if ( v26 < 0 )
        {
          pExceptionObject = &_com_error::`vftable';
          v44 = v26;
          v45 = 0;
          throw (_com_error *)&pExceptionObject;
        }
        v27 = ((__int64 (__fastcall *)(LPUNKNOWN, int *, IUnknown **))ppunkMarshal->lpVtbl[1].Release)(
                ppunkMarshal,
                &v40,
                &v41);
        if ( v27 < 0 )
        {
          pExceptionObject = &_com_error::`vftable';
          v44 = v27;
          v45 = 0;
          throw (_com_error *)&pExceptionObject;
        }
        v28 = ((__int64 (__fastcall *)(LPUNKNOWN, int *))ppunkMarshal->lpVtbl[1].AddRef)(ppunkMarshal, &v39);
        if ( v28 < 0 )
        {
          pExceptionObject = &_com_error::`vftable';
          v44 = v28;
          v45 = 0;
          throw (_com_error *)&pExceptionObject;
        }
        v29 = ppunkMarshal;
        if ( v16[14].Ptr != ppunkMarshal )
        {
          v30 = ppunkMarshal;
          if ( ppunkMarshal )
          {
            ((void (*)(void))ppunkMarshal->lpVtbl->AddRef)();
            v29 = ppunkMarshal;
          }
          v31 = v16[14].Ptr;
          v16[14].Ptr = v30;
          if ( v31 )
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v31 + 16LL))(v31);
            v29 = ppunkMarshal;
          }
        }
        v21 = v41;
        v16[9].Ptr = v41;
        LODWORD(v16[10].Ptr) = v40;
        HIDWORD(v16[10].Ptr) = v39;
        if ( v29 )
        {
          ppunkMarshal = 0;
          ((void (__fastcall *)(LPUNKNOWN))v29->lpVtbl->Release)(v29);
          v21 = (LPUNKNOWN)v16[9].Ptr;
        }
      }
    }
    v7[11].Ptr = v21;
    LODWORD(v7[12].Ptr) = v16[10].Ptr;
    LODWORD(v7[19].Ptr) = HIDWORD(v16[10].Ptr);
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    BYTE6(v7[13].Ptr) = 0;
    HIDWORD(v7[12].Ptr) = v7[12].Ptr;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::Release();
    *a1 = v7;
    v7 = 0;
  }
  if ( v7 )
    operator delete(v7);
  return a1;
}

```

## disassembly

```asm
0x1800049c0  mov     [rsp-8+arg_10], rbx
0x1800049c5  push    rbp
0x1800049c6  push    rsi
0x1800049c7  push    rdi
0x1800049c8  push    r12
0x1800049ca  push    r13
0x1800049cc  push    r14
0x1800049ce  push    r15
0x1800049d0  lea     rbp, [rsp-27h]
0x1800049d5  sub     rsp, 0C0h
0x1800049dc  mov     rax, cs:__security_cookie
0x1800049e3  xor     rax, rsp
0x1800049e6  mov     [rbp+57h+var_38], rax
0x1800049ea  mov     r14, r8
0x1800049ed  mov     rdi, rdx
0x1800049f0  mov     [rbp+57h+var_A0], rdx
0x1800049f4  mov     r15, rcx
0x1800049f7  mov     [rbp+57h+var_70], rcx
0x1800049fb  xor     r12d, r12d
0x1800049fe  mov     [rbp+57h+var_98], r12d
0x180004a02  mov     [rcx], r12
0x180004a05  mov     [rbp+57h+var_98], 1
0x180004a0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a13  mov     ecx, 0A0h; unsigned __int64
0x180004a18  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004a1d  mov     rbx, rax
0x180004a20  mov     [rbp+57h+var_68], rax
0x180004a24  mov     [rbp+57h+var_60], rax
0x180004a28  test    rax, rax
0x180004a2b  jz      loc_180004DB2
0x180004a31  mov     [rbp+57h+var_58], rax
0x180004a35  mov     r14d, [r14]
0x180004a38  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180004a3f  mov     [rbx+30h], rax
0x180004a43  mov     [rbx+48h], r12
0x180004a47  mov     [rbp+57h+ppunkMarshal], r12
0x180004a4b  lea     rdx, [rbp+57h+ppunkMarshal]; ppunkMarshal
0x180004a4f  xor     ecx, ecx; punkOuter
0x180004a51  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180004a57  test    eax, eax
0x180004a59  js      short loc_180004AA1
0x180004a5b  mov     rdi, [rbp+57h+ppunkMarshal]
0x180004a5f  mov     rax, [rdi]
0x180004a62  mov     r12, [rax]
0x180004a65  mov     rcx, [rbx+48h]
0x180004a69  test    rcx, rcx
0x180004a6c  jz      short loc_180004A83
0x180004a6e  mov     qword ptr [rbx+48h], 0
0x180004a76  mov     rdx, [rcx]
0x180004a79  mov     rax, [rdx+10h]
0x180004a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a82  nop
0x180004a83  lea     r8, [rbx+48h]
0x180004a87  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180004a8e  mov     rcx, rdi
0x180004a91  mov     rax, r12
0x180004a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a99  nop
0x180004a9a  mov     rdi, [rbp+57h+var_A0]
0x180004a9e  xor     r12d, r12d
0x180004aa1  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004aa5  test    rcx, rcx
0x180004aa8  jz      short loc_180004ABB
0x180004aaa  mov     [rbp+57h+ppunkMarshal], r12
0x180004aae  mov     rax, [rcx]
0x180004ab1  mov     rax, [rax+10h]
0x180004ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aba  nop
0x180004abb  lea     rax, ??_7MediaBufferImpl@@6B@; const MediaBufferImpl::`vftable'
0x180004ac2  mov     [rbx+10h], rax
0x180004ac6  lea     rax, ??_7MediaBufferImpl@@6BIMemoryBuffer@Foundation@Windows@@@; const MediaBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'}
0x180004acd  mov     [rbx+18h], rax
0x180004ad1  lea     rax, ??_7MediaBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIClosableBuffer@Streams@Storage@Windows@@@23@U?$CloakedIid@UIClosableByteAccess@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'}
0x180004ad8  mov     [rbx+20h], rax
0x180004adc  lea     rax, ??_7MediaBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosableByteAccess@@@Details@WRL@Microsoft@@@; const MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'}
0x180004ae3  mov     [rbx+28h], rax
0x180004ae7  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180004aee  mov     [rbx+30h], rax
0x180004af2  mov     [rbx+58h], r12
0x180004af6  mov     qword ptr [rbx+60h], 0
0x180004afe  mov     [rbx+68h], r12d
0x180004b02  mov     word ptr [rbx+6Ch], 0
0x180004b08  mov     byte ptr [rbx+6Eh], 0
0x180004b0c  lea     rcx, [rbx+70h]; SRWLock
0x180004b10  call    cs:__imp_InitializeSRWLock
0x180004b16  mov     qword ptr [rbx+80h], 1
0x180004b21  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'
0x180004b28  mov     [rbx], rax
0x180004b2b  lea     rax, ??_7BitmapBufferImpl@@6BIWeakReferenceSource@@@; const BitmapBufferImpl::`vftable'{for `IWeakReferenceSource'}
0x180004b32  mov     [rbx+8], rax
0x180004b36  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VMediaBufferImpl@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>'}
0x180004b3d  mov     [rbx+10h], rax
0x180004b41  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6BIMemoryBuffer@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Windows::Foundation::IMemoryBuffer'}
0x180004b48  mov     [rbx+18h], rax
0x180004b4c  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIClosableBuffer@Streams@Storage@Windows@@@23@U?$CloakedIid@UIClosableByteAccess@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'}
0x180004b53  mov     [rbx+20h], rax
0x180004b57  lea     rax, ??_7BitmapBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosableByteAccess@@@Details@WRL@Microsoft@@@; const BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'}
0x180004b5e  mov     [rbx+28h], rax
0x180004b62  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180004b69  mov     [rbx+30h], rax
0x180004b6d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004b74  test    rcx, rcx
0x180004b77  jz      short loc_180004B86
0x180004b79  mov     rax, [rcx]
0x180004b7c  mov     rax, [rax+8]
0x180004b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b85  nop
0x180004b86  lea     rax, ??_7BitmapBufferImpl@@6B@; const BitmapBufferImpl::`vftable'
0x180004b8d  mov     [rbx], rax
0x180004b90  lea     rax, ??_7BitmapBufferImpl@@6BIWeakReferenceSource@@@; const BitmapBufferImpl::`vftable'{for `IWeakReferenceSource'}
0x180004b97  mov     [rbx+8], rax
0x180004b9b  lea     rax, ??_7BitmapBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VMediaBufferImpl@@@Details@23@@Details@WRL@Microsoft@@@; const BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>'}
0x180004ba2  mov     [rbx+10h], rax
0x180004ba6  lea     rax, ??_7BitmapBufferImpl@@6BIMemoryBuffer@Foundation@Windows@@@; const BitmapBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'}
0x180004bad  mov     [rbx+18h], rax
0x180004bb1  lea     rax, ??_7BitmapBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIClosableBuffer@Streams@Storage@Windows@@@23@U?$CloakedIid@UIClosableByteAccess@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'}
0x180004bb8  mov     [rbx+20h], rax
0x180004bbc  lea     rax, ??_7BitmapBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosableByteAccess@@@Details@WRL@Microsoft@@@; const BitmapBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'}
0x180004bc3  mov     [rbx+28h], rax
0x180004bc7  lea     rax, ??_7?$RuntimeClass@UIBitmapBuffer@Imaging@Graphics@Windows@@VMediaBufferImpl@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Graphics::Imaging::IBitmapBuffer,MediaBufferImpl>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180004bce  mov     [rbx+30h], rax
0x180004bd2  mov     [rbx+88h], r14d
0x180004bd9  mov     rdx, [rdi]
0x180004bdc  mov     [rbx+90h], rdx
0x180004be3  mov     r13d, 7FFFFFFFh
0x180004be9  test    rdx, rdx
0x180004bec  jz      short loc_180004C04
0x180004bee  mov     eax, [rdx+0Ch]
0x180004bf1  cmp     eax, r13d
0x180004bf4  jz      short loc_180004C04
0x180004bf6  lea     ecx, [rax+1]
0x180004bf9  lock cmpxchg [rdx+0Ch], ecx
0x180004bfe  jnz     loc_180004DE9
0x180004c04  mov     [rbx+98h], r12d
0x180004c0b  mov     rsi, [rdi]
0x180004c0e  lea     r12, [rsi+78h]
0x180004c12  mov     rcx, r12; SRWLock
0x180004c15  call    cs:__imp_AcquireSRWLockExclusive
0x180004c1b  mov     [rbp+57h+var_50], r12
0x180004c1f  cmp     byte ptr [rsi+44h], 0
0x180004c23  jnz     loc_180004F70
0x180004c29  mov     eax, [rsi+40h]
0x180004c2c  test    r14d, r14d
0x180004c2f  jnz     loc_180004E8B
0x180004c35  inc     eax
0x180004c37  mov     [rsi+40h], eax
0x180004c3a  xor     edi, edi
0x180004c3c  mov     ecx, edi
0x180004c3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180004c45  jnb     loc_180004F44
0x180004c4b  mov     rdx, [rsi+48h]
0x180004c4f  test    rdx, rdx
0x180004c52  jnz     loc_180004D75
0x180004c58  mov     rcx, [rsi+58h]
0x180004c5c  test    rcx, rcx
0x180004c5f  jnz     loc_180004DFA
0x180004c65  test    r14d, r14d
0x180004c68  jnz     loc_180004E69
0x180004c6e  mov     r13d, 1
0x180004c74  mov     [rbp+57h+var_48], 0
0x180004c7c  mov     eax, [rsi+18h]
0x180004c7f  mov     [rbp+57h+var_40], eax
0x180004c82  mov     eax, [rsi+1Ch]
0x180004c85  mov     [rbp+57h+var_3C], eax
0x180004c88  mov     [rbp+57h+ppunkMarshal], rdi
0x180004c8c  mov     [rbp+57h+var_A0], rdi
0x180004c90  mov     [rbp+57h+var_A8], edi
0x180004c93  mov     [rbp+57h+var_A4], edi
0x180004c96  mov     r14, [rsi+68h]
0x180004c9a  mov     rax, [r14]
0x180004c9d  mov     rdi, [rax+40h]
0x180004ca1  lea     rcx, [rbp+57h+ppunkMarshal]
0x180004ca5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180004caa  lea     r9, [rbp+57h+ppunkMarshal]
0x180004cae  mov     r8d, r13d
0x180004cb1  lea     rdx, [rbp+57h+var_48]
0x180004cb5  mov     rcx, r14
0x180004cb8  mov     rax, rdi
0x180004cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc0  test    eax, eax
0x180004cc2  js      loc_180004EC4
0x180004cc8  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004ccc  mov     rax, [rcx]
0x180004ccf  lea     r8, [rbp+57h+var_A0]
0x180004cd3  lea     rdx, [rbp+57h+var_A4]
0x180004cd7  mov     rax, [rax+28h]
0x180004cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce0  test    eax, eax
0x180004ce2  js      loc_180004EEB
0x180004ce8  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004cec  mov     rax, [rcx]
0x180004cef  lea     rdx, [rbp+57h+var_A8]
0x180004cf3  mov     rax, [rax+20h]
0x180004cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cfc  test    eax, eax
0x180004cfe  js      loc_180004F12
0x180004d04  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004d08  cmp     [rsi+70h], rcx
0x180004d0c  jz      short loc_180004D46
0x180004d0e  mov     rdi, rcx
0x180004d11  test    rcx, rcx
0x180004d14  jz      short loc_180004D26
0x180004d16  mov     rax, [rcx]
0x180004d19  mov     rax, [rax+8]
0x180004d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d22  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004d26  mov     rdx, [rsi+70h]
0x180004d2a  mov     [rsi+70h], rdi
0x180004d2e  test    rdx, rdx
0x180004d31  jz      short loc_180004D46
0x180004d33  mov     rax, [rdx]
0x180004d36  mov     rcx, rdx
0x180004d39  mov     rax, [rax+10h]
0x180004d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d42  mov     rcx, [rbp+57h+ppunkMarshal]
0x180004d46  mov     rdx, [rbp+57h+var_A0]
0x180004d4a  mov     [rsi+48h], rdx
0x180004d4e  mov     eax, [rbp+57h+var_A4]
0x180004d51  mov     [rsi+50h], eax
0x180004d54  mov     eax, [rbp+57h+var_A8]
0x180004d57  mov     [rsi+54h], eax
0x180004d5a  xor     edi, edi
0x180004d5c  test    rcx, rcx
0x180004d5f  jz      short loc_180004D75
0x180004d61  mov     [rbp+57h+ppunkMarshal], rdi
0x180004d65  mov     rax, [rcx]
0x180004d68  mov     rax, [rax+10h]
0x180004d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d71  mov     rdx, [rsi+48h]
0x180004d75  mov     [rbx+58h], rdx
0x180004d79  mov     eax, [rsi+50h]
0x180004d7c  mov     [rbx+60h], eax
0x180004d7f  mov     eax, [rsi+54h]
0x180004d82  mov     [rbx+98h], eax
0x180004d88  test    r12, r12
0x180004d8b  jz      short loc_180004D96
0x180004d8d  mov     rcx, r12; SRWLock
0x180004d90  call    cs:__imp_ReleaseSRWLockExclusive
0x180004d96  mov     byte ptr [rbx+6Eh], 0
0x180004d9a  mov     eax, [rbx+60h]
0x180004d9d  mov     [rbx+64h], eax
0x180004da0  mov     rcx, [r15]
0x180004da3  test    rcx, rcx
0x180004da6  jnz     loc_180004F9F
0x180004dac  mov     [r15], rbx
0x180004daf  mov     rbx, rdi
0x180004db2  test    rbx, rbx
0x180004db5  jz      short loc_180004DBF
0x180004db7  mov     rcx, rbx; Block
0x180004dba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004dbf  mov     rax, r15
0x180004dc2  mov     rcx, [rbp+57h+var_38]
0x180004dc6  xor     rcx, rsp; StackCookie
0x180004dc9  call    __security_check_cookie
0x180004dce  mov     rbx, [rsp+0F0h+arg_10]
0x180004dd6  add     rsp, 0C0h
0x180004ddd  pop     r15
0x180004ddf  pop     r14
0x180004de1  pop     r13
0x180004de3  pop     r12
0x180004de5  pop     rdi
0x180004de6  pop     rsi
0x180004de7  pop     rbp
0x180004de8  retn
0x180004de9  mov     eax, [rdx+0Ch]
0x180004dec  cmp     eax, r13d
0x180004def  jnz     loc_180004BF6
0x180004df5  jmp     loc_180004C04
0x180004dfa  test    r14d, r14d
0x180004dfd  jnz     loc_180004EA5
0x180004e03  mov     r13d, 1
0x180004e09  mov     [rbp+57h+var_A0], rdi
0x180004e0d  mov     [rbp+57h+ppunkMarshal], rdi
0x180004e11  mov     [rbp+57h+var_A4], edi
0x180004e14  mov     [rbp+57h+var_A8], edi
0x180004e17  mov     rax, [rcx]
0x180004e1a  lea     rdx, [rbp+57h+var_A8]
0x180004e1e  mov     [rsp+0F0h+var_C8], rdx
0x180004e23  lea     rdx, [rbp+57h+ppunkMarshal]
0x180004e27  mov     [rsp+0F0h+var_D0], rdx
0x180004e2c  lea     r9, [rbp+57h+var_A4]
0x180004e30  lea     r8, [rbp+57h+var_A0]
0x180004e34  mov     edx, r13d
0x180004e37  mov     rax, [rax+50h]
0x180004e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e40  mov     ecx, eax; this
0x180004e42  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180004e47  mov     rdx, [rbp+57h+ppunkMarshal]
0x180004e4b  mov     [rsi+48h], rdx
0x180004e4f  mov     eax, [rbp+57h+var_A8]
0x180004e52  mov     [rsi+50h], eax
0x180004e55  mov     eax, [rbp+57h+var_A4]
0x180004e58  mov     [rsi+54h], eax
0x180004e5b  test    eax, eax
0x180004e5d  jns     loc_180004D75
0x180004e63  call    ??$ThrowOriginateError@$0BO@@MF@@YAXJAEAY0BO@$$CBG@Z; MF::ThrowOriginateError<30>(long,ushort const (&)[30])
0x180004e69  mov     r13d, edi
0x180004e6c  sub     r14d, 1
0x180004e70  jz      loc_180004F39
0x180004e76  cmp     r14d, 1
  ... truncated ...
```
