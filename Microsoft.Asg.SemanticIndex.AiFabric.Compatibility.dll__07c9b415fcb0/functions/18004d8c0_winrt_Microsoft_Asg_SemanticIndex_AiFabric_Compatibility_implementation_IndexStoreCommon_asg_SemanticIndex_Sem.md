# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::SimpleAddOrUpdateTextItem(winrt::guid,winrt::hstring const &,winrt::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsOptions const &)

- ea: `0x18004d8c0`
- end: `0x18004e048`
- name: `?SimpleAddOrUpdateTextItem@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUMultipleEmbeddingsResult@345678@Uguid@8@AEBUhstring@8@1AEBUTextEmbeddingsOptions@345678@@Z`
- size: `1928`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180052130`

## callees

- `0x180003bd0`
- `0x180010dd0`
- `0x180023600`
- `0x18002f8e0`
- `0x180030cc0`
- `0x180032f20`
- `0x18004d8c0`
- `0x18004e050`
- `0x18004eac0`
- `0x18006f3f0`
- `0x1801d2b20`
- `0x1801f7110`
- `0x1801f7190`
- `0x180242120`

## string_xrefs

- `0x18004d9da`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18004db32`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18004dd3b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_Mtx_t *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::SimpleAddOrUpdateTextItem(
        __int64 a1,
        _Mtx_t *a2,
        __int128 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int128 *v7; // rdi
  _QWORD *v10; // rax
  _Mtx_t *result; // rax
  __int64 v12; // rdi
  int v13; // eax
  _QWORD *v14; // rax
  struct _Mtx_internal_imp_t *v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rax
  char v21; // bl
  volatile signed __int32 *v22; // rsi
  __int64 v23; // rcx
  char *v24; // rax
  _Mtx_t v25; // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  _QWORD *v29; // rax
  int v30; // eax
  _QWORD *v31; // rax
  int v32; // eax
  int v33; // eax
  _QWORD *v34; // rax
  char v35[4]; // [rsp+30h] [rbp-E8h] BYREF
  _DWORD v36[3]; // [rsp+34h] [rbp-E4h] BYREF
  _BYTE v37[24]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-B8h] BYREF
  _Mtx_t v39; // [rsp+68h] [rbp-B0h] BYREF
  char v40; // [rsp+70h] [rbp-A8h]
  _QWORD *v41; // [rsp+78h] [rbp-A0h]
  __int128 v42; // [rsp+80h] [rbp-98h] BYREF
  _Mtx_t *v43; // [rsp+90h] [rbp-88h]
  __int64 v44; // [rsp+98h] [rbp-80h]
  __int128 v45; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v46; // [rsp+C0h] [rbp-58h] BYREF

  v7 = a3;
  v44 = a1;
  v41 = (_QWORD *)a1;
  v43 = a2;
  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    a1,
    &v39,
    a3);
  if ( *(_BYTE *)(a1 + 203) )
  {
    v10 = operator new(0x38u);
    v41 = v10;
    v10[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *((_DWORD *)v10 + 6) = 110;
    *((_DWORD *)v10 + 7) = -2147467259;
    v10[4] = 0;
    v10[5] = 0;
    v10[6] = 0;
    *v10 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
    *a2 = (_Mtx_t)(v10 + 2);
    if ( v40 )
      Mtx_unlock(v39);
    return a2;
  }
  if ( v40 )
    Mtx_unlock(v39);
  v45 = *v7;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::BeginItemUpdate(
    a1,
    &v38,
    &v45);
  v36[0] = 0;
  *(_DWORD *)v37 = 229;
  *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\"
                       "winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  *(_QWORD *)&v37[16] = 0;
  v12 = v38;
  v13 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v38 + 56LL))(v38, v36);
  if ( v13 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v13, v37);
  }
  if ( v36[0] )
  {
    switch ( v36[0] )
    {
      case 'e':
        v14 = operator new(0x38u);
        v15 = (struct _Mtx_internal_imp_t *)(v14 + 2);
        v14[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v14[1] = 1;
        *((_DWORD *)v14 + 6) = 102;
        break;
      case 'g':
        v14 = operator new(0x38u);
        v15 = (struct _Mtx_internal_imp_t *)(v14 + 2);
        v14[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v14[1] = 1;
        *((_DWORD *)v14 + 6) = 109;
        break;
      case 'h':
        v14 = operator new(0x38u);
        v15 = (struct _Mtx_internal_imp_t *)(v14 + 2);
        v14[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v14[1] = 1;
        *((_DWORD *)v14 + 6) = 112;
        break;
      default:
        v14 = operator new(0x38u);
        v15 = (struct _Mtx_internal_imp_t *)(v14 + 2);
        v14[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v14[1] = 1;
        *((_DWORD *)v14 + 6) = 103;
        break;
    }
    v41 = v14;
    *((_DWORD *)v14 + 7) = -2147467259;
    v14[4] = 0;
    v14[5] = 0;
    v14[6] = 0;
    *v14 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
    *a2 = v15;
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
    return a2;
  }
  v46 = 0;
  *(_DWORD *)v37 = 265;
  *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\"
                       "winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  *(_QWORD *)&v37[16] = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 72LL))(v12, &v46);
  try
  {
    if ( v16 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v16, v37);
    }
    v42 = v46;
    LOBYTE(v17) = 1;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
      a1,
      &v39,
      v17);
    v19 = std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>::operator()<winrt::guid>(
            v18,
            (unsigned __int8 *)&v42);
    v20 = std::_Hash<std::_Umap_traits<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>,std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>,std::allocator<std::pair<winrt::guid const,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>>,0>>::_Find<winrt::guid>(
            (_QWORD *)(a1 + 312),
            &v42,
            v19);
    if ( v20 == *(_QWORD *)(a1 + 320) )
    {
      v21 = 0;
      v37[0] = 0;
      *(_OWORD *)&v37[8] = 0;
      if ( v40 )
        Mtx_unlock(v39);
      v22 = *(volatile signed __int32 **)&v37[16];
    }
    else
    {
      v21 = 1;
      v37[0] = 1;
      v23 = *(_QWORD *)(v20 + 40);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      *(_QWORD *)&v37[8] = *(_QWORD *)(v20 + 32);
      v22 = *(volatile signed __int32 **)(v20 + 40);
      *(_QWORD *)&v37[16] = v22;
      if ( v40 )
        Mtx_unlock(v39);
    }
    if ( v21 )
    {
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession::AddRegionToItem(
        *(_QWORD *)&v37[8],
        &v39,
        a4,
        a5,
        a6);
      v25 = v39;
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_35;
        }
      }
    }
    else
    {
      v24 = (char *)operator new(0x38u);
      v25 = (_Mtx_t)(v24 + 16);
      *((_QWORD *)v24 + 2) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v24 + 1) = 1;
      *((_DWORD *)v24 + 6) = 101;
      *((_DWORD *)v24 + 7) = -2147467259;
      *((_QWORD *)v24 + 4) = 0;
      *((_QWORD *)v24 + 5) = 0;
      *((_QWORD *)v24 + 6) = 0;
      *(_QWORD *)v24 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
      v39 = (_Mtx_t)(v24 + 16);
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
LABEL_35:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
    }
    v35[0] = 0;
    *(_DWORD *)v37 = 1138;
    *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated File"
                         "s\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    *(_QWORD *)&v37[16] = 0;
    v26 = (*(__int64 (__fastcall **)(_Mtx_t, char *))(*(_QWORD *)v25 + 48LL))(v25, v35);
    if ( v26 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v26, v37);
    }
    *(_DWORD *)v37 = 265;
    *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated File"
                         "s\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    *(_QWORD *)&v37[16] = 0;
    v45 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 72LL))(v12, &v45);
    if ( v35[0] )
    {
      if ( v27 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v27, v37);
      }
      *(_OWORD *)v37 = v45;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::CommitItemUpdate(
        v44,
        &v42,
        v37);
      v36[0] = 0;
      *(_DWORD *)v37 = 301;
      *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fi"
                           "les\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *(_QWORD *)&v37[16] = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)v42 + 56LL))(v42, v36);
      if ( v28 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v28, v37);
      }
      if ( v36[0] )
      {
        v29 = operator new(0x38u);
        v29[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v29[1] = 1;
        *((_DWORD *)v29 + 6) = 103;
        *((_DWORD *)v29 + 7) = -2147467259;
        v29[4] = 0;
        v29[5] = 0;
        v29[6] = 0;
        *v29 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
        *a2 = (_Mtx_t)(v29 + 2);
        if ( !(_QWORD)v42 )
        {
LABEL_43:
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v39);
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
          return a2;
        }
LABEL_42:
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v42);
        goto LABEL_43;
      }
    }
    else
    {
      if ( v27 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v27, v37);
      }
      *(_OWORD *)v37 = v45;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AbortItemUpdate(
        v44,
        &v42,
        v37);
      v36[0] = 0;
      *(_DWORD *)v37 = 49;
      *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fi"
                           "les\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *(_QWORD *)&v37[16] = 0;
      v30 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)v42 + 56LL))(v42, v36);
      if ( v30 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v30, v37);
      }
      if ( v36[0] )
      {
        v31 = operator new(0x38u);
        v31[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v31[1] = 1;
        *((_DWORD *)v31 + 6) = 103;
        *((_DWORD *)v31 + 7) = -2147467259;
        v31[4] = 0;
        v31[5] = 0;
        v31[6] = 0;
        *v31 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
        *a2 = (_Mtx_t)(v31 + 2);
        if ( !(_QWORD)v42 )
          goto LABEL_43;
        goto LABEL_42;
      }
    }
    if ( (_QWORD)v42 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v42);
    *a2 = v25;
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
    result = a2;
  }
  catch ( ... )
  {
    winrt::to_hresult(&v42);
    v45 = 0;
    *(_DWORD *)v37 = 265;
    *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated File"
                         "s\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    *(_QWORD *)&v37[16] = 0;
    v32 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v38 + 72LL))(v38, &v45);
    if ( v32 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v32, v37);
    }
    *(_OWORD *)v37 = v45;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AbortItemUpdate(
      v41,
      &v39,
      v37);
    v36[0] = 0;
    *(_DWORD *)v37 = 49;
    *(_QWORD *)&v37[8] = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated File"
                         "s\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    *(_QWORD *)&v37[16] = 0;
    v33 = (*(__int64 (__fastcall **)(_Mtx_t, _DWORD *))(*(_QWORD *)v39 + 56LL))(v39, v36);
    if ( v33 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v33, v37);
    }
    v34 = operator new(0x38u);
    v41 = v34;
    v34[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    if ( v36[0] )
    {
      v34[1] = 1;
      *((_DWORD *)v34 + 6) = 103;
      *((_DWORD *)v34 + 7) = -2147467259;
    }
    else
    {
      v34[1] = 1;
      *((_DWORD *)v34 + 6) = 100;
      *((_DWORD *)v34 + 7) = v42;
    }
    v34[4] = 0;
    v34[5] = 0;
    v34[6] = 0;
    *v34 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable';
    *v43 = (_Mtx_t)(v34 + 2);
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v39);
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
    return v43;
  }
  return result;
}

```

## disassembly

```asm
0x18004d8c0  push    rbx
0x18004d8c2  push    rsi
0x18004d8c3  push    rdi
0x18004d8c4  push    r12
0x18004d8c6  push    r13
0x18004d8c8  push    r14
0x18004d8ca  push    r15
0x18004d8cc  sub     rsp, 0E0h
0x18004d8d3  mov     rax, cs:__security_cookie
0x18004d8da  xor     rax, rsp
0x18004d8dd  mov     [rsp+118h+var_48], rax
0x18004d8e5  mov     r15, r9
0x18004d8e8  mov     rdi, r8
0x18004d8eb  mov     r14, rdx
0x18004d8ee  mov     rbx, rcx
0x18004d8f1  mov     [rsp+118h+var_80], rcx
0x18004d8f9  mov     [rsp+118h+var_A0], rcx
0x18004d8fe  mov     [rsp+118h+var_88], rdx
0x18004d906  mov     r12, [rsp+118h+arg_20]
0x18004d90e  mov     r13, [rsp+118h+arg_28]
0x18004d916  xor     esi, esi
0x18004d918  mov     r8b, 1
0x18004d91b  lea     rdx, [rsp+118h+var_B0]
0x18004d920  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004d925  nop
0x18004d926  cmp     [rbx+0CBh], sil
0x18004d92d  jz      short loc_18004D99B
0x18004d92f  mov     ecx, 38h ; '8'; Size
0x18004d934  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d939  mov     [rsp+118h+var_A0], rax
0x18004d93e  lea     rcx, [rax+10h]
0x18004d942  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004d949  mov     [rcx], r15
0x18004d94c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004d953  mov     qword ptr [rax+8], 1
0x18004d95b  mov     dword ptr [rax+18h], 6Eh ; 'n'
0x18004d962  mov     dword ptr [rax+1Ch], 80004005h
0x18004d969  mov     [rax+20h], rsi
0x18004d96d  mov     [rax+28h], rsi
0x18004d971  mov     [rax+30h], rsi
0x18004d975  lea     r12, ??_7?$heap_implements@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable'
0x18004d97c  mov     [rax], r12
0x18004d97f  mov     [r14], rcx
0x18004d982  cmp     [rsp+118h+var_A8], sil
0x18004d987  jz      short loc_18004D993
0x18004d989  mov     rcx, [rsp+118h+var_B0]; _Mtx_t
0x18004d98e  call    _Mtx_unlock
0x18004d993  mov     rax, r14
0x18004d996  jmp     loc_18004DFB5
0x18004d99b  cmp     [rsp+118h+var_A8], 0
0x18004d9a0  jz      short loc_18004D9AC
0x18004d9a2  mov     rcx, [rsp+118h+var_B0]; _Mtx_t
0x18004d9a7  call    _Mtx_unlock
0x18004d9ac  movaps  xmm0, xmmword ptr [rdi]
0x18004d9af  movdqa  [rsp+118h+var_68], xmm0
0x18004d9b8  lea     r8, [rsp+118h+var_68]
0x18004d9c0  lea     rdx, [rsp+118h+var_B8]
0x18004d9c5  mov     rcx, rbx
0x18004d9c8  call    ?BeginItemUpdate@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUBeginItemUpdateResult@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::BeginItemUpdate(winrt::guid)
0x18004d9cd  nop
0x18004d9ce  mov     [rsp+118h+var_E4], esi
0x18004d9d2  mov     dword ptr [rsp+118h+var_D8], 0E5h
0x18004d9da  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18004d9e1  mov     qword ptr [rsp+118h+var_D8+8], rax
0x18004d9e6  mov     [rsp+118h+var_C8], rsi
0x18004d9eb  mov     rdi, [rsp+118h+var_B8]
0x18004d9f0  mov     rax, [rdi]
0x18004d9f3  lea     rdx, [rsp+118h+var_E4]
0x18004d9f8  mov     rcx, rdi
0x18004d9fb  mov     rax, [rax+38h]
0x18004d9ff  call    cs:__guard_dispatch_icall_fptr
0x18004da05  test    eax, eax
0x18004da07  js      loc_18004DFD8
0x18004da0d  mov     ecx, [rsp+118h+var_E4]
0x18004da11  test    ecx, ecx
0x18004da13  jz      loc_18004DB1F
0x18004da19  sub     ecx, 65h ; 'e'
0x18004da1c  jz      loc_18004DABA
0x18004da22  sub     ecx, 2
0x18004da25  jz      short loc_18004DA8A
0x18004da27  cmp     ecx, 1
0x18004da2a  mov     ecx, 38h ; '8'; Size
0x18004da2f  jz      short loc_18004DA5F
0x18004da31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004da36  lea     rcx, [rax+10h]
0x18004da3a  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004da41  mov     [rcx], r15
0x18004da44  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004da4b  mov     qword ptr [rax+8], 1
0x18004da53  mov     dword ptr [rax+18h], 67h ; 'g'
0x18004da5a  jmp     loc_18004DAE8
0x18004da5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004da64  lea     rcx, [rax+10h]
0x18004da68  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004da6f  mov     [rcx], r15
0x18004da72  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004da79  mov     qword ptr [rax+8], 1
0x18004da81  mov     dword ptr [rax+18h], 70h ; 'p'
0x18004da88  jmp     short loc_18004DAE8
0x18004da8a  mov     ecx, 38h ; '8'; Size
0x18004da8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004da94  lea     rcx, [rax+10h]
0x18004da98  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004da9f  mov     [rcx], r15
0x18004daa2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004daa9  mov     qword ptr [rax+8], 1
0x18004dab1  mov     dword ptr [rax+18h], 6Dh ; 'm'
0x18004dab8  jmp     short loc_18004DAE8
0x18004daba  mov     ecx, 38h ; '8'; Size
0x18004dabf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004dac4  lea     rcx, [rax+10h]
0x18004dac8  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004dacf  mov     [rcx], r15
0x18004dad2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004dad9  mov     qword ptr [rax+8], 1
0x18004dae1  mov     dword ptr [rax+18h], 66h ; 'f'
0x18004dae8  mov     [rsp+118h+var_A0], rax
0x18004daed  mov     dword ptr [rax+1Ch], 80004005h
0x18004daf4  mov     [rax+20h], rsi
0x18004daf8  mov     [rax+28h], rsi
0x18004dafc  mov     [rax+30h], rsi
0x18004db00  lea     r12, ??_7?$heap_implements@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable'
0x18004db07  mov     [rax], r12
0x18004db0a  mov     [r14], rcx
0x18004db0d  lea     rcx, [rsp+118h+var_B8]
0x18004db12  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004db17  mov     rax, r14
0x18004db1a  jmp     loc_18004DFB5
0x18004db1f  xorps   xmm0, xmm0
0x18004db22  movups  [rsp+118h+var_58], xmm0
0x18004db2a  mov     dword ptr [rsp+118h+var_D8], 109h
0x18004db32  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18004db39  mov     qword ptr [rsp+118h+var_D8+8], rax
0x18004db3e  mov     [rsp+118h+var_C8], rsi
0x18004db43  mov     rax, [rdi]
0x18004db46  lea     rdx, [rsp+118h+var_58]
0x18004db4e  mov     rcx, rdi
0x18004db51  mov     rax, [rax+48h]
0x18004db55  call    cs:__guard_dispatch_icall_fptr
0x18004db5b  test    eax, eax
0x18004db5d  js      loc_18004DFE8
0x18004db63  movaps  xmm0, [rsp+118h+var_58]
0x18004db6b  movdqa  [rsp+118h+var_98], xmm0
0x18004db74  mov     r8b, 1
0x18004db77  lea     rdx, [rsp+118h+var_B0]
0x18004db7c  mov     rcx, rbx
0x18004db7f  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004db84  lea     rdx, [rsp+118h+var_98]
0x18004db8c  call    ??$?RUguid@winrt@@@?$_Uhash_compare@Uguid@winrt@@U?$hash@Uguid@winrt@@@std@@U?$equal_to@Uguid@winrt@@@4@@std@@QEBA_KAEBUguid@winrt@@@Z; std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>::operator()<winrt::guid>(winrt::guid const &)
0x18004db91  mov     r8, rax
0x18004db94  lea     rdx, [rsp+118h+var_98]
0x18004db9c  lea     rcx, [rbx+138h]
0x18004dba3  call    ??$_Find@Uguid@winrt@@@?$_Hash@V?$_Umap_traits@Uguid@winrt@@V?$shared_ptr@UItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@V?$_Uhash_compare@Uguid@winrt@@U?$hash@Uguid@winrt@@@std@@U?$equal_to@Uguid@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUguid@winrt@@V?$shared_ptr@UItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@@4@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBUguid@winrt@@V?$shared_ptr@UItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@PEAX@1@AEBUguid@winrt@@_K@Z; std::_Hash<std::_Umap_traits<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>,std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>,std::allocator<std::pair<winrt::guid const,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>>,0>>::_Find<winrt::guid>(winrt::guid const &,unsigned __int64)
0x18004dba8  cmp     rax, [rbx+140h]
0x18004dbaf  jnz     short loc_18004DBD7
0x18004dbb1  xor     bl, bl
0x18004dbb3  mov     byte ptr [rsp+118h+var_D8], bl
0x18004dbb7  xorps   xmm1, xmm1
0x18004dbba  movdqu  [rsp+118h+var_D8+8], xmm1
0x18004dbc0  cmp     [rsp+118h+var_A8], bl
0x18004dbc4  jz      short loc_18004DBD0
0x18004dbc6  mov     rcx, [rsp+118h+var_B0]; _Mtx_t
0x18004dbcb  call    _Mtx_unlock
0x18004dbd0  mov     rsi, [rsp+118h+var_C8]
0x18004dbd5  jmp     short loc_18004DC0E
0x18004dbd7  mov     bl, 1
0x18004dbd9  mov     byte ptr [rsp+118h+var_D8], bl
0x18004dbdd  mov     rcx, [rax+28h]
0x18004dbe1  test    rcx, rcx
0x18004dbe4  jz      short loc_18004DBEA
0x18004dbe6  lock inc dword ptr [rcx+8]
0x18004dbea  mov     rcx, [rax+20h]
0x18004dbee  mov     qword ptr [rsp+118h+var_D8+8], rcx
0x18004dbf3  mov     rsi, [rax+28h]
0x18004dbf7  mov     [rsp+118h+var_C8], rsi
0x18004dbfc  cmp     [rsp+118h+var_A8], 0
0x18004dc01  jz      short loc_18004DC0E
0x18004dc03  mov     rcx, [rsp+118h+var_B0]; _Mtx_t
0x18004dc08  call    _Mtx_unlock
0x18004dc0d  nop
0x18004dc0e  test    bl, bl
0x18004dc10  jnz     loc_18004DCB9
0x18004dc16  mov     ecx, 38h ; '8'; Size
0x18004dc1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004dc20  lea     rbx, [rax+10h]
0x18004dc24  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004dc2b  mov     [rbx], r15
0x18004dc2e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004dc35  mov     qword ptr [rax+8], 1
0x18004dc3d  mov     dword ptr [rax+18h], 65h ; 'e'
0x18004dc44  mov     dword ptr [rax+1Ch], 80004005h
0x18004dc4b  xor     ecx, ecx
0x18004dc4d  mov     [rax+20h], rcx
0x18004dc51  mov     [rax+28h], rcx
0x18004dc55  mov     [rax+30h], rcx
0x18004dc59  lea     r12, ??_7?$heap_implements@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable'
0x18004dc60  mov     [rax], r12
0x18004dc63  mov     [rsp+118h+var_B0], rbx
0x18004dc68  test    rsi, rsi
0x18004dc6b  jz      loc_18004DD2E
0x18004dc71  mov     r13d, 0FFFFFFFFh
0x18004dc77  mov     eax, r13d
0x18004dc7a  lock xadd [rsi+8], eax
0x18004dc7f  cmp     eax, 1
0x18004dc82  jnz     loc_18004DD2E
0x18004dc88  mov     rax, [rsi]
0x18004dc8b  mov     rcx, rsi
0x18004dc8e  mov     rax, [rax]
0x18004dc91  call    cs:__guard_dispatch_icall_fptr
0x18004dc97  lock xadd [rsi+0Ch], r13d
0x18004dc9d  cmp     r13d, 1
0x18004dca1  jnz     loc_18004DD2E
0x18004dca7  mov     rax, [rsi]
0x18004dcaa  mov     rcx, rsi
0x18004dcad  mov     rax, [rax+8]
0x18004dcb1  call    cs:__guard_dispatch_icall_fptr
0x18004dcb7  jmp     short loc_18004DD2E
0x18004dcb9  mov     [rsp+118h+var_F8], r13
0x18004dcbe  mov     r9, r12
0x18004dcc1  mov     r8, r15
0x18004dcc4  lea     rdx, [rsp+118h+var_B0]
0x18004dcc9  mov     rcx, qword ptr [rsp+118h+var_D8+8]
0x18004dcce  call    ?AddRegionToItem@ItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUMultipleEmbeddingsResult@345678@AEBUhstring@8@0AEBUTextEmbeddingsOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession::AddRegionToItem(winrt::hstring const &,winrt::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsOptions const &)
0x18004dcd3  mov     rbx, [rsp+118h+var_B0]
0x18004dcd8  mov     [rsp+118h+var_B0], rbx
0x18004dcdd  test    rsi, rsi
0x18004dce0  jz      short loc_18004DD20
0x18004dce2  mov     r13d, 0FFFFFFFFh
0x18004dce8  mov     eax, r13d
0x18004dceb  lock xadd [rsi+8], eax
0x18004dcf0  cmp     eax, 1
0x18004dcf3  jnz     short loc_18004DD20
0x18004dcf5  mov     rax, [rsi]
0x18004dcf8  mov     rcx, rsi
0x18004dcfb  mov     rax, [rax]
0x18004dcfe  call    cs:__guard_dispatch_icall_fptr
0x18004dd04  lock xadd [rsi+0Ch], r13d
0x18004dd0a  cmp     r13d, 1
0x18004dd0e  jnz     short loc_18004DD20
0x18004dd10  mov     rax, [rsi]
0x18004dd13  mov     rcx, rsi
0x18004dd16  mov     rax, [rax+8]
0x18004dd1a  call    cs:__guard_dispatch_icall_fptr
0x18004dd20  lea     r12, ??_7?$heap_implements@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult>::`vftable'
0x18004dd27  lea     r15, ??_7?$produce@UMultipleEmbeddingsResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIMultipleEmbeddingsResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MultipleEmbeddingsResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IMultipleEmbeddingsResult>::`vftable'
0x18004dd2e  mov     [rsp+118h+var_E8], 0
0x18004dd33  mov     dword ptr [rsp+118h+var_D8], 472h
0x18004dd3b  lea     r13, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18004dd42  mov     qword ptr [rsp+118h+var_D8+8], r13
0x18004dd47  xor     esi, esi
0x18004dd49  mov     [rsp+118h+var_C8], rsi
0x18004dd4e  mov     rax, [rbx]
0x18004dd51  lea     rdx, [rsp+118h+var_E8]
0x18004dd56  mov     rcx, rbx
0x18004dd59  mov     rax, [rax+30h]
0x18004dd5d  call    cs:__guard_dispatch_icall_fptr
0x18004dd63  test    eax, eax
0x18004dd65  js      loc_18004DFF8
0x18004dd6b  xorps   xmm0, xmm0
0x18004dd6e  mov     dword ptr [rsp+118h+var_D8], 109h
0x18004dd76  mov     qword ptr [rsp+118h+var_D8+8], r13
0x18004dd7b  mov     [rsp+118h+var_C8], rsi
0x18004dd80  lea     rdx, [rsp+118h+var_68]
0x18004dd88  mov     rcx, rdi
0x18004dd8b  movups  [rsp+118h+var_68], xmm0
0x18004dd93  mov     rax, [rdi]
0x18004dd96  mov     rax, [rax+48h]
0x18004dd9a  call    cs:__guard_dispatch_icall_fptr
0x18004dda0  cmp     [rsp+118h+var_E8], sil
0x18004dda5  jz      loc_18004DE96
0x18004ddab  test    eax, eax
0x18004ddad  js      loc_18004E007
0x18004ddb3  movaps  xmm0, [rsp+118h+var_68]
0x18004ddbb  movdqa  [rsp+118h+var_D8], xmm0
0x18004ddc1  lea     r8, [rsp+118h+var_D8]
0x18004ddc6  lea     rdx, [rsp+118h+var_98]
0x18004ddce  mov     rcx, [rsp+118h+var_80]
0x18004ddd6  call    ?CommitItemUpdate@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUCommitItemUpdateResult@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::CommitItemUpdate(winrt::guid)
0x18004dddb  nop
0x18004dddc  mov     [rsp+118h+var_E4], esi
0x18004dde0  mov     rcx, qword ptr [rsp+118h+var_98]
0x18004dde8  mov     dword ptr [rsp+118h+var_D8], 12Dh
0x18004ddf0  mov     qword ptr [rsp+118h+var_D8+8], r13
0x18004ddf5  mov     [rsp+118h+var_C8], rsi
0x18004ddfa  mov     rax, [rcx]
0x18004ddfd  lea     rdx, [rsp+118h+var_E4]
0x18004de02  mov     rax, [rax+38h]
0x18004de06  call    cs:__guard_dispatch_icall_fptr
0x18004de0c  test    eax, eax
0x18004de0e  js      loc_18004E017
0x18004de14  cmp     [rsp+118h+var_E4], 0
0x18004de19  jz      short loc_18004DE91
0x18004de1b  mov     ecx, 38h ; '8'; Size
0x18004de20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004de25  lea     rcx, [rax+10h]
0x18004de29  mov     [rcx], r15
0x18004de2c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004de33  mov     qword ptr [rax+8], 1
0x18004de3b  mov     dword ptr [rax+18h], 67h ; 'g'
0x18004de42  mov     dword ptr [rax+1Ch], 80004005h
  ... truncated ...
```
