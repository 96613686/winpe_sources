# WindowsInternal::Shell::UnifiedTile::UnifiedTileMRTHelper::ResolvePath(HSTRING__ *,WindowsInternal::Shell::UnifiedTile::MRTHelperResolvePathOptions,WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions *,WindowsInternal::Shell::UnifiedTile::ITileImageResourceCandidate * *)

- ea: `0x1800413f0`
- end: `0x180041b36`
- name: `?ResolvePath@UnifiedTileMRTHelper@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUHSTRING__@@W4MRTHelperResolvePathOptions@234@PEAUITileImageResourceOptions@234@PEAPEAUITileImageResourceCandidate@234@@Z`
- size: `1862`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180030e28`
- `0x18003f52c`
- `0x180040fb0`
- `0x180041338`
- `0x1800413f0`
- `0x180041be4`
- `0x180041de8`
- `0x1800421ac`
- `0x18004258c`
- `0x1800a061c`
- `0x1801b80a8`
- `0x18020be0c`
- `0x1802e11c4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800417e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004187b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800418c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004190d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800417e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004187b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800418c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004190d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b12`

## string_xrefs

- `0x180041698`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x180041766`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x180041867`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x1800418b0`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x1800418f9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x180041971`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x1800419a9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x1800419d7`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x180041a8a`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`
- `0x180041ae7`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemrthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileMRTHelper::ResolvePath(
        WindowsInternal::Shell::UnifiedTile::UnifiedTileMRTHelper *a1,
        __int64 a2,
        char a3,
        _QWORD *a4,
        _QWORD *a5)
{
  _QWORD *v5; // rbx
  _QWORD *v9; // r15
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ebx
  __int64 v20; // r14
  HSTRING *v21; // rdi
  HSTRING v22; // rbx
  enum DEVICE_SCALE_FACTOR v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *v26; // rsi
  __int64 (__fastcall *v27)(struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *, _QWORD, HSTRING, __int64 *); // rdi
  int v28; // eax
  unsigned int v29; // edi
  struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *v30; // rcx
  WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate *v31; // rax
  __int64 v32; // rsi
  int v33; // edi
  __int64 v34; // rcx
  const char *v35; // r9
  _QWORD *v36; // rcx
  __int64 result; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *v41; // rcx
  __int64 v42; // rcx
  _QWORD *v43; // rcx
  int v44; // eax
  unsigned int v45; // edi
  int v46; // eax
  unsigned int v47; // ebx
  _QWORD *v48; // rcx
  _QWORD *v49; // rcx
  _QWORD *v50; // rcx
  int v51; // eax
  unsigned int v52; // ebx
  enum DEVICE_SCALE_FACTOR v53; // [rsp+20h] [rbp-A8h]
  unsigned int v54; // [rsp+60h] [rbp-68h] BYREF
  struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *v55; // [rsp+68h] [rbp-60h] BYREF
  _QWORD *v56; // [rsp+70h] [rbp-58h] BYREF
  __int64 v57; // [rsp+78h] [rbp-50h] BYREF
  __int64 v58; // [rsp+80h] [rbp-48h] BYREF
  HSTRING v59; // [rsp+88h] [rbp-40h]
  HSTRING string[2]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned int v63; // [rsp+E8h] [rbp+20h] BYREF

  try
  {
    v5 = a4;
    v9 = a5;
    *a5 = 0;
    v56 = 0;
    if ( !a4 )
    {
      v51 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::TileImageResourceOptions,WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions,>(&v56);
      v52 = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
          (const char *)(unsigned int)v51,
          v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        return v52;
      }
      v5 = v56;
    }
    v54 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *))(*v5 + 48LL))(v5, &v54);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
        (const char *)(unsigned int)v10,
        v53);
      v40 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
      }
      result = v11;
    }
    else
    {
      v63 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *))(*v5 + 64LL))(v5, &v63);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
          (const char *)(unsigned int)v12,
          v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        return v13;
      }
      LODWORD(a5) = 0;
      v14 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v5 + 112LL))(v5, &a5);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
          (const char *)(unsigned int)v14,
          v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        return v15;
      }
      v59 = 0;
      v16 = *v5;
      if ( (a3 & 2) != 0 )
      {
        v58 = 0;
        v44 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v16 + 96))(v5, &v58);
        v45 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
            (const char *)(unsigned int)v44,
            v53);
          WindowsDeleteString(0);
          v50 = v56;
          if ( v56 )
          {
            v56 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
          }
          return v45;
        }
        v55 = 0;
        v46 = (*(__int64 (__fastcall **)(_QWORD *, struct Windows::Internal::Storage::IStorageFileStartExperienceStatic **))(*v5 + 128LL))(
                v5,
                &v55);
        v47 = v46;
        if ( v46 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
            (const char *)(unsigned int)v46,
            v53);
          WindowsDeleteString(0);
          v48 = v56;
          if ( v56 )
          {
            v56 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
          }
          return v47;
        }
        LOWORD(v53) = (int)*(float *)&v58;
        v21 = (HSTRING *)DataStoreCache::MRTHelper::ResolvePath(*((_QWORD *)a1 + 8), string, a2, 5);
        WindowsDeleteString(0);
      }
      else
      {
        LODWORD(v55) = 0;
        v17 = (*(__int64 (__fastcall **)(_QWORD *, struct Windows::Internal::Storage::IStorageFileStartExperienceStatic **))(v16 + 80))(
                v5,
                &v55);
        v19 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
            (const char *)(unsigned int)v17,
            v53);
          WindowsDeleteString(0);
          v49 = v56;
          if ( v56 )
          {
            v56 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
          }
          return v19;
        }
        v20 = *((_QWORD *)a1 + 8);
        v53 = ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent(
                (ShellMRTHelper::Common *)(unsigned int)v55,
                v18);
        v21 = (HSTRING *)DataStoreCache::MRTHelper::ResolvePath(v20, string, a2, 0);
        WindowsDeleteString(0);
      }
      v22 = *v21;
      *v21 = 0;
      v59 = v22;
      WindowsDeleteString(string[0]);
      v23 = DEVICE_SCALE_FACTOR_INVALID;
      v57 = 0;
      if ( (a3 & 1) != 0 )
      {
        v55 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        v24 = WindowsInternal::Shell::UnifiedTile::UnifiedTileMRTHelper::EnsureStorageFileHelper(a1, &v55);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x95,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
            (const char *)(unsigned int)v24,
            v53);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
          WindowsDeleteString(v22);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
          return v25;
        }
        v26 = v55;
        v27 = *(__int64 (__fastcall **)(struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v55 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        v28 = v27(v26, *((_QWORD *)a1 + 9), v22, &v57);
        v29 = v28;
        if ( v28 < 0 )
        {
          if ( v28 == -2147024894 || IsServerFailedError(v28) )
          {
            v41 = v55;
            if ( v55 )
            {
              v55 = 0;
              (*(void (__fastcall **)(struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *))(*(_QWORD *)v41 + 16LL))(v41);
            }
            v42 = v57;
            if ( v57 )
            {
              v57 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            }
            WindowsDeleteString(v22);
            v43 = v56;
            if ( v56 )
            {
              v56 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
            }
            return v29;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9B,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
              (const char *)v29,
              v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
            WindowsDeleteString(v22);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
            return v29;
          }
        }
        v30 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::Storage::IStorageFileStartExperienceStatic *))(*(_QWORD *)v30 + 16LL))(v30);
        }
        v23 = (int)v57;
      }
      *v9 = 0;
      v31 = (WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate *)operator new(
                                                                                 0x60u,
                                                                                 (const struct std::nothrow_t *)std::nothrow);
      if ( !v31 )
      {
        v33 = -2147024882;
        goto LABEL_20;
      }
      v32 = WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate::TileImageResourceCandidate(v31);
      string[0] = 0;
      v53 = v23;
      v33 = WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate::RuntimeClassInitialize(
              v32,
              v54,
              v63,
              (unsigned int)a5);
      if ( v33 < 0 )
      {
        if ( v32 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IMRTHelper,Microsoft::WRL::FtmBase>::Release(v32);
        Microsoft::WRL::Details::MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>::~MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>(string);
        goto LABEL_20;
      }
      v33 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileImageResourceCandidate,Microsoft::WRL::FtmBase>>(
              v32,
              &GUID_5fd6631d_35f8_43f8_a9c9_b741dde2e664,
              v9);
      if ( v32 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IMRTHelper,Microsoft::WRL::FtmBase>::Release(v32);
      if ( v33 < 0 )
      {
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
          (const char *)(unsigned int)v33,
          v53);
        v34 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        WindowsDeleteString(v22);
        v36 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v36 + 16LL))(v36, *v36);
        }
        return (unsigned int)v33;
      }
      v38 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      WindowsDeleteString(v22);
      v39 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
      }
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(a5) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xA8,
                    (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemrthelper.cpp",
                    v35);
    return (unsigned int)a5;
  }
  return result;
}

```

## disassembly

```asm
0x1800413f0  mov     rax, rsp
0x1800413f3  mov     [rax+8], rbx
0x1800413f7  mov     [rax+18h], rsi
0x1800413fb  mov     [rax+10h], rdx
0x1800413ff  push    rdi
0x180041400  push    r12
0x180041402  push    r13
0x180041404  push    r14
0x180041406  push    r15
0x180041408  sub     rsp, 0A0h
0x18004140f  mov     rbx, r9
0x180041412  mov     r12d, r8d
0x180041415  mov     rsi, rdx
0x180041418  mov     r13, rcx
0x18004141b  xor     r14d, r14d
0x18004141e  mov     r15, [rsp+0C8h+arg_20]
0x180041426  mov     [r15], r14
0x180041429  mov     [rax-58h], r14
0x18004142d  test    rbx, rbx
0x180041430  jz      loc_180041956
0x180041436  mov     [rsp+0C8h+var_68], r14d
0x18004143b  mov     rax, [rbx]
0x18004143e  lea     rdx, [rsp+0C8h+var_68]
0x180041443  mov     rcx, rbx
0x180041446  mov     rax, [rax+30h]
0x18004144a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004144f  mov     edi, eax
0x180041451  test    eax, eax
0x180041453  js      loc_18004175B
0x180041459  mov     [rsp+0C8h+arg_18], r14d
0x180041461  mov     rax, [rbx]
0x180041464  lea     rdx, [rsp+0C8h+arg_18]
0x18004146c  mov     rcx, rbx
0x18004146f  mov     rax, [rax+40h]
0x180041473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041478  mov     edi, eax
0x18004147a  test    eax, eax
0x18004147c  js      loc_18004199E
0x180041482  mov     dword ptr [rsp+0C8h+arg_20], r14d
0x18004148a  mov     rax, [rbx]
0x18004148d  lea     rdx, [rsp+0C8h+arg_20]
0x180041495  mov     rcx, rbx
0x180041498  mov     rax, [rax+70h]
0x18004149c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414a1  mov     edi, eax
0x1800414a3  test    eax, eax
0x1800414a5  js      loc_1800419CC
0x1800414ab  mov     [rsp+0C8h+var_40], r14
0x1800414b3  mov     rax, [rbx]
0x1800414b6  test    r12b, 2
0x1800414ba  jnz     loc_18004180C
0x1800414c0  mov     dword ptr [rsp+0C8h+var_60], r14d
0x1800414c5  lea     rdx, [rsp+0C8h+var_60]
0x1800414ca  mov     rcx, rbx
0x1800414cd  mov     rax, [rax+50h]
0x1800414d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414d6  mov     ebx, eax
0x1800414d8  test    eax, eax
0x1800414da  js      loc_1800418A5
0x1800414e0  mov     r14, [r13+40h]
0x1800414e4  mov     ebx, dword ptr [rsp+0C8h+arg_20]
0x1800414eb  mov     edi, [rsp+0C8h+arg_18]
0x1800414f2  mov     esi, [rsp+0C8h+var_68]
0x1800414f6  mov     ecx, dword ptr [rsp+0C8h+var_60]; this
0x1800414fa  call    ?DeviceScaleFactorFromScalePercent@Common@ShellMRTHelper@@YA?AW4DEVICE_SCALE_FACTOR@@I@Z; ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent(uint)
0x1800414ff  lea     rcx, [rsp+0C8h+arg_20]
0x180041507  mov     [rsp+0C8h+var_78], rcx
0x18004150c  lea     rcx, [rsp+0C8h+arg_18]
0x180041514  mov     [rsp+0C8h+var_80], rcx
0x180041519  lea     rcx, [rsp+0C8h+var_68]
0x18004151e  mov     [rsp+0C8h+var_88], rcx
0x180041523  mov     [rsp+0C8h+var_90], ebx
0x180041527  mov     [rsp+0C8h+var_98], edi
0x18004152b  mov     dword ptr [rsp+0C8h+var_A0], esi
0x18004152f  mov     [rsp+0C8h+var_A8], eax; int
0x180041533  xor     r9d, r9d
0x180041536  mov     r8, [rsp+0C8h+arg_8]
0x18004153e  lea     rdx, [rsp+0C8h+string]
0x180041546  mov     rcx, r14
0x180041549  call    ?ResolvePath@MRTHelper@DataStoreCache@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@W4ImageType@2@W4DEVICE_SCALE_FACTOR@@W4TileImageResourceContrast@UnifiedTile@Shell@WindowsInternal@@W4TileImageResourceTheme@UnifiedTile@Shell@WindowsInternal@@W4TileImageResourceAlternateForm@UnifiedTile@Shell@WindowsInternal@@PEAW4TileImageResourceContrast@UnifiedTile@Shell@WindowsInternal@@PEAW4TileImageResourceTheme@UnifiedTile@Shell@WindowsInternal@@PEAW4TileImageResourceAlternateForm@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::MRTHelper::ResolvePath(HSTRING__ *,DataStoreCache::ImageType,DEVICE_SCALE_FACTOR,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme,WindowsInternal::Shell::UnifiedTile::TileImageResourceAlternateForm,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast *,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme *,WindowsInternal::Shell::UnifiedTile::TileImageResourceAlternateForm *)
0x18004154e  mov     rdi, rax
0x180041551  xor     ecx, ecx; string
0x180041553  call    cs:__imp_WindowsDeleteString
0x180041559  xor     r14d, r14d
0x18004155c  mov     rbx, [rdi]
0x18004155f  mov     [rdi], r14
0x180041562  mov     [rsp+0C8h+var_40], rbx
0x18004156a  mov     rcx, [rsp+0C8h+string]; string
0x180041572  call    cs:__imp_WindowsDeleteString
0x180041578  mov     rdi, r14
0x18004157b  mov     [rsp+0C8h+var_50], r14
0x180041580  test    r12b, 1
0x180041584  jz      short loc_180041604
0x180041586  mov     [rsp+0C8h+var_60], r14
0x18004158b  lea     rcx, [rsp+0C8h+var_60]
0x180041590  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041595  lea     rdx, [rsp+0C8h+var_60]; struct Windows::Internal::Storage::IStorageFileStartExperienceStatic **
0x18004159a  mov     rcx, r13; this
0x18004159d  call    ?EnsureStorageFileHelper@UnifiedTileMRTHelper@UnifiedTile@Shell@WindowsInternal@@AEAAJPEAPEAUIStorageFileStartExperienceStatic@Storage@Internal@Windows@@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileMRTHelper::EnsureStorageFileHelper(Windows::Internal::Storage::IStorageFileStartExperienceStatic * *)
0x1800415a2  mov     edi, eax
0x1800415a4  test    eax, eax
0x1800415a6  js      loc_180041A7F
0x1800415ac  mov     rsi, [rsp+0C8h+var_60]
0x1800415b1  mov     rax, [rsi]
0x1800415b4  mov     rdi, [rax+38h]
0x1800415b8  lea     rcx, [rsp+0C8h+var_50]
0x1800415bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800415c2  lea     r9, [rsp+0C8h+var_50]
0x1800415c7  mov     r8, rbx
0x1800415ca  mov     rdx, [r13+48h]
0x1800415ce  mov     rcx, rsi
0x1800415d1  mov     rax, rdi
0x1800415d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415d9  mov     edi, eax
0x1800415db  test    eax, eax
0x1800415dd  js      loc_18004179B
0x1800415e3  mov     rcx, [rsp+0C8h+var_60]
0x1800415e8  test    rcx, rcx
0x1800415eb  jz      short loc_1800415FF
0x1800415ed  mov     [rsp+0C8h+var_60], r14
0x1800415f2  mov     rax, [rcx]
0x1800415f5  mov     rax, [rax+10h]
0x1800415f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415fe  nop
0x1800415ff  mov     rdi, [rsp+0C8h+var_50]
0x180041604  mov     [r15], r14
0x180041607  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004160e  mov     ecx, 60h ; '`'; unsigned __int64
0x180041613  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180041618  test    rax, rax
0x18004161b  jz      loc_18004170B
0x180041621  mov     rcx, rax; this
0x180041624  call    ??0TileImageResourceCandidate@UnifiedTile@Shell@WindowsInternal@@QEAA@XZ; WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate::TileImageResourceCandidate(void)
0x180041629  mov     rsi, rax
0x18004162c  mov     [rsp+0C8h+string], r14
0x180041634  mov     [rsp+0C8h+var_A0], rbx
0x180041639  mov     qword ptr [rsp+0C8h+var_A8], rdi; int
0x18004163e  mov     r9d, dword ptr [rsp+0C8h+arg_20]
0x180041646  mov     r8d, [rsp+0C8h+arg_18]
0x18004164e  mov     edx, [rsp+0C8h+var_68]
0x180041652  mov     rcx, rax
0x180041655  call    ?RuntimeClassInitialize@TileImageResourceCandidate@UnifiedTile@Shell@WindowsInternal@@QEAAJW4TileImageResourceContrast@234@W4TileImageResourceTheme@234@W4TileImageResourceAlternateForm@234@PEAUIRandomAccessStream@Streams@Storage@Windows@@PEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::TileImageResourceCandidate::RuntimeClassInitialize(WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme,WindowsInternal::Shell::UnifiedTile::TileImageResourceAlternateForm,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *)
0x18004165a  mov     edi, eax
0x18004165c  test    eax, eax
0x18004165e  js      loc_180041937
0x180041664  mov     r8, r15
0x180041667  lea     rdx, _GUID_5fd6631d_35f8_43f8_a9c9_b741dde2e664
0x18004166e  mov     rcx, rsi
0x180041671  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITileImageResourceCandidate@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITileImageResourceCandidate@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileImageResourceCandidate,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileImageResourceCandidate,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180041676  mov     edi, eax
0x180041678  test    rsi, rsi
0x18004167b  jz      short loc_180041685
0x18004167d  mov     rcx, rsi
0x180041680  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMRTHelper@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IMRTHelper,Microsoft::WRL::FtmBase>::Release(void)
0x180041685  test    edi, edi
0x180041687  jns     loc_180041715
0x18004168d  mov     rcx, [rsp+0C8h]; this
0x180041695  mov     r9d, edi; char *
0x180041698  lea     r8, aShellcommonShe_53; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18004169f  mov     edx, 0A5h; void *
0x1800416a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416a9  nop
0x1800416aa  mov     rcx, [rsp+0C8h+var_50]
0x1800416af  test    rcx, rcx
0x1800416b2  jz      short loc_1800416C6
0x1800416b4  mov     [rsp+0C8h+var_50], r14
0x1800416b9  mov     rax, [rcx]
0x1800416bc  mov     rax, [rax+10h]
0x1800416c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416c5  nop
0x1800416c6  mov     rcx, rbx; string
0x1800416c9  call    cs:__imp_WindowsDeleteString
0x1800416cf  nop
0x1800416d0  mov     rcx, [rsp+0C8h+var_58]
0x1800416d5  test    rcx, rcx
0x1800416d8  jz      short loc_1800416EC
0x1800416da  mov     [rsp+0C8h+var_58], r14
0x1800416df  mov     rdx, [rcx]
0x1800416e2  mov     rax, [rdx+10h]
0x1800416e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416eb  nop
0x1800416ec  mov     eax, edi
0x1800416ee  lea     r11, [rsp+0C8h+var_28]
0x1800416f6  mov     rbx, [r11+30h]
0x1800416fa  mov     rsi, [r11+40h]
0x1800416fe  mov     rsp, r11
0x180041701  pop     r15
0x180041703  pop     r14
0x180041705  pop     r13
0x180041707  pop     r12
0x180041709  pop     rdi
0x18004170a  retn
0x18004170b  mov     edi, 8007000Eh
0x180041710  jmp     loc_18004168D
0x180041715  mov     rcx, [rsp+0C8h+var_50]
0x18004171a  test    rcx, rcx
0x18004171d  jz      short loc_180041731
0x18004171f  mov     [rsp+0C8h+var_50], r14
0x180041724  mov     rax, [rcx]
0x180041727  mov     rax, [rax+10h]
0x18004172b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041730  nop
0x180041731  mov     rcx, rbx; string
0x180041734  call    cs:__imp_WindowsDeleteString
0x18004173a  nop
0x18004173b  mov     rcx, [rsp+0C8h+var_58]
0x180041740  test    rcx, rcx
0x180041743  jz      short loc_180041757
0x180041745  mov     [rsp+0C8h+var_58], r14
0x18004174a  mov     rax, [rcx]
0x18004174d  mov     rax, [rax+10h]
0x180041751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041756  nop
0x180041757  xor     eax, eax
0x180041759  jmp     short loc_1800416EE
0x18004175b  mov     rcx, [rsp+0C8h]; this
0x180041763  mov     r9d, edi; char *
0x180041766  lea     r8, aShellcommonShe_53; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18004176d  mov     edx, 63h ; 'c'; void *
0x180041772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041777  nop
0x180041778  mov     rcx, [rsp+0C8h+var_58]
0x18004177d  test    rcx, rcx
0x180041780  jz      short loc_180041794
0x180041782  mov     [rsp+0C8h+var_58], r14
0x180041787  mov     rax, [rcx]
0x18004178a  mov     rax, [rax+10h]
0x18004178e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041793  nop
0x180041794  mov     eax, edi
0x180041796  jmp     loc_1800416EE
0x18004179b  cmp     edi, 80070002h
0x1800417a1  jnz     loc_180041ACD
0x1800417a7  mov     rcx, [rsp+0C8h+var_60]
0x1800417ac  test    rcx, rcx
0x1800417af  jz      short loc_1800417C3
0x1800417b1  mov     [rsp+0C8h+var_60], r14
0x1800417b6  mov     rax, [rcx]
0x1800417b9  mov     rax, [rax+10h]
0x1800417bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417c2  nop
0x1800417c3  mov     rcx, [rsp+0C8h+var_50]
0x1800417c8  test    rcx, rcx
0x1800417cb  jz      short loc_1800417DF
0x1800417cd  mov     [rsp+0C8h+var_50], r14
0x1800417d2  mov     rax, [rcx]
0x1800417d5  mov     rax, [rax+10h]
0x1800417d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417de  nop
0x1800417df  mov     rcx, rbx; string
0x1800417e2  call    cs:__imp_WindowsDeleteString
0x1800417e8  nop
0x1800417e9  mov     rcx, [rsp+0C8h+var_58]
0x1800417ee  test    rcx, rcx
0x1800417f1  jz      short loc_180041805
0x1800417f3  mov     [rsp+0C8h+var_58], r14
0x1800417f8  mov     rax, [rcx]
0x1800417fb  mov     rax, [rax+10h]
0x1800417ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041804  nop
0x180041805  mov     eax, edi
0x180041807  jmp     loc_1800416EE
0x18004180c  xor     ecx, ecx
0x18004180e  mov     [rsp+0C8h+var_48], rcx
0x180041816  lea     rdx, [rsp+0C8h+var_48]
0x18004181e  mov     rcx, rbx
0x180041821  mov     rax, [rax+60h]
0x180041825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004182a  mov     edi, eax
0x18004182c  test    eax, eax
0x18004182e  js      loc_1800418EE
0x180041834  xor     eax, eax
0x180041836  mov     [rsp+0C8h+var_60], rax
0x18004183b  mov     rax, [rbx]
0x18004183e  lea     rdx, [rsp+0C8h+var_60]
0x180041843  mov     rcx, rbx
0x180041846  mov     rax, [rax+80h]
0x18004184d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041852  mov     ebx, eax
0x180041854  test    eax, eax
0x180041856  jns     loc_1800419FA
0x18004185c  mov     rcx, [rsp+0C8h]; this
0x180041864  mov     r9d, eax; char *
0x180041867  lea     r8, aShellcommonShe_53; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18004186e  mov     edx, 72h ; 'r'; void *
0x180041873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041878  nop
0x180041879  xor     ecx, ecx; string
0x18004187b  call    cs:__imp_WindowsDeleteString
0x180041881  nop
0x180041882  mov     rcx, [rsp+0C8h+var_58]
0x180041887  test    rcx, rcx
0x18004188a  jz      short loc_18004189E
0x18004188c  mov     [rsp+0C8h+var_58], r14
0x180041891  mov     rax, [rcx]
0x180041894  mov     rax, [rax+10h]
0x180041898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004189d  nop
0x18004189e  mov     eax, ebx
0x1800418a0  jmp     loc_1800416EE
  ... truncated ...
```
