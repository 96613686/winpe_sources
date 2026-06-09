# NgcHandler::EnumContainers(void *,_NGC_RPC_CONTAINER_INFO_LIST * *)

- ea: `0x180010654`
- end: `0x18001100c`
- name: `?EnumContainers@NgcHandler@@QEAAJPEAXPEAPEAU_NGC_RPC_CONTAINER_INFO_LIST@@@Z`
- size: `2488`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, struct _NGC_RPC_CONTAINER_INFO_LIST **)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800105a0`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x18000b1b0`
- `0x18000b41c`
- `0x18000c7e0`
- `0x18000d450`
- `0x18000d50c`
- `0x180010654`
- `0x1800121c0`
- `0x180012330`
- `0x1800134a0`
- `0x180013d2c`
- `0x180014350`
- `0x180014384`
- `0x180015160`
- `0x180016550`
- `0x180018194`
- `0x18001e500`
- `0x18001f5c8`
- `0x180021c38`
- `0x1800260ac`
- `0x180029430`
- `0x18002c640`
- `0x18002cdec`
- `0x18002d518`
- `0x180047bfc`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800106dd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800107bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010fce`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800106dd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800107bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010fce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800109d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800109d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcHandler::EnumContainers(NgcHandler *this, void *a2, struct _NGC_RPC_CONTAINER_INFO_LIST **a3)
{
  int v4; // r15d
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall *v8)(__int64 *); // rbx
  int v9; // eax
  int v10; // eax
  int v11; // edi
  _QWORD *v12; // rax
  unsigned int v13; // r12d
  __m128i si128; // xmm6
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 **); // rbx
  int v17; // eax
  char *v18; // rdx
  int v19; // eax
  __int16 *v20; // rdx
  BOOL v21; // ebx
  __int64 v22; // r8
  __int64 v23; // r8
  __int128 **v24; // r14
  unsigned int v25; // ebx
  __int64 v26; // rax
  int v27; // eax
  __int64 **v28; // rcx
  __int64 (__fastcall *v29)(__int128 *, _QWORD *); // rbx
  int v30; // eax
  unsigned __int8 *v31; // rdx
  struct _NGC_RPC_CONTAINER_INFO_LIST *v32; // rbx
  size_t v33; // r15
  _QWORD *v34; // rax
  _QWORD *v35; // r14
  __int64 v36; // r8
  __int64 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 **v40; // rdx
  __int64 *i; // rax
  __int64 *j; // rdx
  bool v43; // zf
  char v44[8]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v45; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  DWORD LastError; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+78h] [rbp-88h] BYREF
  int v53; // [rsp+7Ch] [rbp-84h] BYREF
  int v54; // [rsp+80h] [rbp-80h] BYREF
  __int128 v55; // [rsp+88h] [rbp-78h] BYREF
  int v56; // [rsp+98h] [rbp-68h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h] BYREF
  struct _NGC_RPC_CONTAINER_INFO_LIST **v58; // [rsp+A8h] [rbp-58h]
  __m128i v59; // [rsp+B0h] [rbp-50h] BYREF
  int v60; // [rsp+C0h] [rbp-40h]
  int v61; // [rsp+C4h] [rbp-3Ch]
  __int128 *v62; // [rsp+C8h] [rbp-38h] BYREF
  PSID Sid; // [rsp+D0h] [rbp-30h] BYREF
  char v64; // [rsp+D8h] [rbp-28h]
  __int128 v65; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR StringSid; // [rsp+100h] [rbp+0h] BYREF
  int v67; // [rsp+108h] [rbp+8h]
  int v68; // [rsp+10Ch] [rbp+Ch]
  int v69; // [rsp+110h] [rbp+10h] BYREF
  char *v70; // [rsp+118h] [rbp+18h] BYREF
  char *v71; // [rsp+138h] [rbp+38h] BYREF

  v58 = a3;
  v4 = 0;
  v44[0] = 0;
  v5 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v44, (unsigned int)a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v47 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA90F,
        0,
        0,
        (__int64)&v47);
    }
LABEL_4:
    if ( v44[0] )
      CoUninitialize();
    return v6;
  }
  v51 = 0;
  v8 = (__int64 (__fastcall *)(__int64 *))*((_QWORD *)this + 2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v9 = v8(&v51);
  v6 = v9;
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v47 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA8D1,
        0,
        0,
        (__int64)&v47);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    goto LABEL_4;
  }
  v52 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v51 + 24LL))(v51, &v52);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v47 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA825,
        0,
        0,
        (__int64)&v47);
    }
    goto LABEL_14;
  }
  v55 = 0;
  v12 = operator new(0xA8u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  *(_QWORD *)&v55 = v12;
  v13 = 0;
  if ( v52 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v46 = 0;
      v15 = v51;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v51 + 32LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
      v17 = v16(v15, v13, &v46);
      if ( v17 < 0 )
        break;
      v53 = 0;
      v50 = xmmword_18008F2D8;
      v11 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v46 + 88))(v46, &v50, &v53);
      if ( v11 < 0 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          LODWORD(v45) = v11;
          v18 = byte_1800AA85D;
LABEL_22:
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)v18,
            0,
            0,
            (__int64)&v45);
        }
LABEL_23:
        v11 = 0;
        goto LABEL_93;
      }
      if ( v53 )
      {
        NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo::NgcEnumContainerInfo(&v65);
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v46 + 64))(v46, &v65);
        if ( v19 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            v20 = &word_1800AA786;
            goto LABEL_31;
          }
LABEL_32:
          v11 = 0;
LABEL_92:
          NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo::_NgcEnumContainerInfo(&v65);
          goto LABEL_93;
        }
        v19 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v46 + 24))(v46, &v69);
        if ( v19 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 3 )
            goto LABEL_32;
          v20 = (__int16 *)byte_1800AA7F1;
          goto LABEL_31;
        }
        v56 = 0;
        v54 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 *, int *, int *))(*v46 + 72))(v46, &v56, &v54);
        if ( v19 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 3 )
            goto LABEL_32;
          v20 = &word_1800AA7B6;
LABEL_31:
          LODWORD(v45) = v19;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)v20,
            0,
            0,
            (__int64)&v45);
          goto LABEL_32;
        }
        if ( v54 )
          v68 |= 4u;
        v11 = NgcHandler::AllocateAndCopyContainerStringProperty(&v46, 1u, (void **)&StringSid);
        if ( v11 < 0 )
          goto LABEL_32;
        *(_QWORD *)&v50 = 0;
        v62 = &v50;
        Sid = 0;
        v64 = 1;
        v21 = ConvertStringSidToSidW(StringSid, &Sid);
        wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v62);
        if ( !v21 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            LastError = GetLastError();
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_1800BE0B8,
              (unsigned __int8 *)byte_1800AA745,
              0,
              0,
              (__int64)&LastError);
          }
          wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v50,
            0);
          goto LABEL_92;
        }
        wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &v50,
          0);
        v45 = 0;
        if ( (int)NgcHandler::AllocateAndCopyContainerStringProperty(&v46, 3u, (void **)&v45) < 0 )
        {
          v11 = 0;
LABEL_48:
          std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v45);
          goto LABEL_92;
        }
        if ( v45 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v45[v22] );
          std::wstring::_Assign<unsigned short>(&v70, v45, (char *)v22);
        }
        *(_QWORD *)&v50 = 0;
        v11 = NgcHandler::AllocateAndCopyContainerStringProperty(&v46, 4u, (void **)&v50);
        if ( v11 < 0 )
        {
          v11 = 0;
          std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v50);
          goto LABEL_48;
        }
        if ( (_QWORD)v50 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *(_WORD *)(v50 + 2 * v23) );
          std::wstring::_Assign<unsigned short>(&v71, (const void *)v50, (char *)v23);
        }
        std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v50);
        std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v45);
        v59 = si128;
        v60 = 16;
        v61 = 64;
        v24 = (__int128 **)&v59;
        do
        {
          v25 = *(_DWORD *)v24;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl)
            || v25 != 64 )
          {
            v4 |= v25;
            LODWORD(v45) = 0;
            v11 = NgcHandler::GestureTypeToProtectorId(v25, &v45);
            if ( v11 >= 0 )
            {
              v47 = 0;
              v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(*v46 + 184))(v46, (unsigned int)v45, &v47);
              if ( v11 >= 0 )
              {
                if ( v47 )
                  v67 |= v25;
              }
              else if ( (unsigned int)dword_1800BE0B8 > 2 )
              {
                LODWORD(v45) = v11;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_1800BE0B8,
                  (unsigned __int8 *)&unk_1800AA6C8,
                  0,
                  0,
                  (__int64)&v45);
              }
            }
          }
          v24 = (__int128 **)((char *)v24 + 4);
        }
        while ( v24 != &v62 );
        if ( (v4 & v67) == 0 && v69 == 2 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            LODWORD(v45) = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_1800BE0B8,
              (unsigned __int8 *)byte_1800AA699,
              0,
              0,
              (__int64)&v45);
          }
          NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo::_NgcEnumContainerInfo(&v65);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          v4 = 0;
          goto LABEL_94;
        }
        std::wstring::wstring(&v62, StringSid);
        std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo____0___::find(
          &v55,
          &v57,
          &v62);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v62);
        if ( v57 == (_QWORD)v55 )
        {
          std::wstring::wstring(&v62, StringSid);
          v26 = std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____::operator[](
                  &v55,
                  &v62);
          NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo::operator_(v26, &v65);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v62);
          v4 = 0;
          goto LABEL_92;
        }
        v4 = 0;
        if ( !*(_QWORD *)(v57 + 120) && !*(_QWORD *)(v57 + 152) )
        {
          v50 = xmmword_18008F2D8;
          v27 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v46 + 48))(v46, &v50);
          if ( v27 < 0 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 3 )
            {
              LODWORD(v45) = v27;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (__int64)&dword_1800BE0B8,
                (unsigned __int8 *)byte_1800AA707,
                0,
                0,
                (__int64)&v45);
            }
            goto LABEL_92;
          }
          v28 = &v46;
          goto LABEL_91;
        }
        std::swap__NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_0_(v57 + 64, &v65);
        v49[0] = 0;
        v29 = *(__int64 (__fastcall **)(__int128 *, _QWORD *))this;
        v50 = v65;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v49);
        v30 = v29(&v50, v49);
        if ( v30 >= 0 )
        {
          v50 = xmmword_18008F2D8;
          v30 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v49[0] + 48LL))(v49[0], &v50);
          if ( v30 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v49);
          }
          else if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            v31 = (unsigned __int8 *)byte_1800AA5A5;
LABEL_85:
            LODWORD(v45) = v30;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_1800BE0B8,
              v31,
              0,
              0,
              (__int64)&v45);
          }
        }
        else if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          v31 = (unsigned __int8 *)&word_1800AA5DE;
          goto LABEL_85;
        }
        v28 = (__int64 **)v49;
LABEL_91:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
        goto LABEL_92;
      }
LABEL_93:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
LABEL_94:
      if ( ++v13 >= v52 )
        goto LABEL_95;
    }
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v45) = v17;
      v18 = byte_1800AA89B;
      goto LABEL_22;
    }
    goto LABEL_23;
  }
LABEL_95:
  v32 = (struct _NGC_RPC_CONTAINER_INFO_LIST *)MIDL_user_allocate(0x10u);
  *(_QWORD *)&v50 = v32;
  if ( v32 )
  {
    if ( !*((_QWORD *)&v55 + 1) )
    {
      *(_DWORD *)v32 = 0;
      *((_QWORD *)v32 + 1) = 0;
LABEL_114:
      *(_QWORD *)&v50 = 0;
      *v58 = v32;
      std::unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>(&v50);
      std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____::_map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____(&v55);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      if ( v44[0] )
        CoUninitialize();
      return (unsigned int)v11;
    }
    v33 = 40LL * *((_QWORD *)&v55 + 1);
    v34 = MIDL_user_allocate(40LL * *((_QWORD *)&v55 + 1));
    v35 = v34;
    v49[0] = v34;
    if ( v34 )
    {
      memset_0(v34, 0, v33);
      v36 = 0;
      v37 = *(__int64 **)v55;
      while ( !*((_BYTE *)v37 + 25) )
      {
        v38 = 5 * v36;
        *(_OWORD *)&v35[v38] = *((_OWORD *)v37 + 4);
        v39 = v37[10];
        v37[10] = 0;
        v35[v38 + 2] = v39;
        LODWORD(v35[v38 + 3]) = *((_DWORD *)v37 + 22);
        HIDWORD(v35[v38 + 3]) = *((_DWORD *)v37 + 23);
        LODWORD(v35[v38 + 4]) = *((_DWORD *)v37 + 24);
        ++v36;
        v40 = (__int64 **)v37[2];
        if ( *((_BYTE *)v40 + 25) )
        {
          for ( i = (__int64 *)v37[1]; !*((_BYTE *)i + 25) && v37 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v37 = i;
          v37 = i;
        }
        else
        {
          v37 = (__int64 *)v37[2];
          for ( j = *v40; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v37 = j;
        }
      }
      *(_DWORD *)v32 = DWORD2(v55);
      v49[0] = 0;
      *((_QWORD *)v32 + 1) = v35;
      std::unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>(v49);
      goto LABEL_114;
    }
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LastError = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA613,
        0,
        0,
        (__int64)&LastError);
    }
    std::unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>(v49);
    std::unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>(&v50);
    std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____::_map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____(&v55);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v43 = v44[0] == 0;
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LastError = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AA654,
        0,
        0,
        (__int64)&LastError);
    }
    std::unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO_LIST,rpcmem_delete<_NGC_RPC_CONTAINER_INFO_LIST>>(&v50);
    std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____::_map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___NgcHandler::EnumContainers_::_2_::NgcEnumContainerInfo_____(&v55);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v43 = v44[0] == 0;
  }
  if ( !v43 )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x180010654  mov     rax, rsp
0x180010657  mov     [rax+10h], rbx
0x18001065b  push    rbp
0x18001065c  push    rsi
0x18001065d  push    rdi
0x18001065e  push    r12
0x180010660  push    r13
0x180010662  push    r14
0x180010664  push    r15
0x180010666  lea     rbp, [rsp-80h]
0x18001066b  sub     rsp, 180h
0x180010672  movaps  xmmword ptr [rax-48h], xmm6
0x180010676  mov     rax, cs:__security_cookie
0x18001067d  xor     rax, rsp
0x180010680  mov     [rbp+0B0h+var_50], rax
0x180010684  mov     [rbp+0B0h+var_108], r8
0x180010688  mov     r13, rcx
0x18001068b  xor     r15d, r15d
0x18001068e  mov     [rsp+1B0h+var_180], r15b
0x180010693  lea     rcx, [rsp+1B0h+var_180]; this
0x180010698  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18001069d  mov     ebx, eax
0x18001069f  test    eax, eax
0x1800106a1  jns     short loc_1800106F0
0x1800106a3  mov     ecx, cs:dword_1800BE0B8
0x1800106a9  cmp     ecx, 2
0x1800106ac  jbe     short loc_1800106D6
0x1800106ae  mov     [rsp+1B0h+var_168], eax
0x1800106b2  lea     rax, [rsp+1B0h+var_168]
0x1800106b7  mov     [rsp+1B0h+var_190], rax
0x1800106bc  xor     r9d, r9d
0x1800106bf  xor     r8d, r8d
0x1800106c2  lea     rdx, byte_1800AA90F
0x1800106c9  lea     rcx, dword_1800BE0B8
0x1800106d0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800106d5  nop
0x1800106d6  cmp     [rsp+1B0h+var_180], r15b
0x1800106db  jz      short loc_1800106E9
0x1800106dd  call    cs:__imp_CoUninitialize
0x1800106e4  nop     dword ptr [rax+rax+00h]
0x1800106e9  mov     eax, ebx
0x1800106eb  jmp     loc_180010FDF
0x1800106f0  mov     [rsp+1B0h+var_140], r15
0x1800106f5  mov     rbx, [r13+10h]
0x1800106f9  lea     rcx, [rsp+1B0h+var_140]
0x1800106fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010703  lea     rcx, [rsp+1B0h+var_140]
0x180010708  mov     rax, rbx
0x18001070b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010710  mov     ebx, eax
0x180010712  test    eax, eax
0x180010714  jns     short loc_180010755
0x180010716  mov     ecx, cs:dword_1800BE0B8
0x18001071c  cmp     ecx, 2
0x18001071f  jbe     short loc_180010749
0x180010721  mov     [rsp+1B0h+var_168], eax
0x180010725  lea     rax, [rsp+1B0h+var_168]
0x18001072a  mov     [rsp+1B0h+var_190], rax
0x18001072f  xor     r9d, r9d
0x180010732  xor     r8d, r8d
0x180010735  lea     rdx, byte_1800AA8D1
0x18001073c  lea     rcx, dword_1800BE0B8
0x180010743  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010748  nop
0x180010749  lea     rcx, [rsp+1B0h+var_140]
0x18001074e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010753  jmp     short loc_1800106D6
0x180010755  mov     [rsp+1B0h+var_138], r15d
0x18001075a  mov     rcx, [rsp+1B0h+var_140]
0x18001075f  mov     rax, [rcx]
0x180010762  lea     rdx, [rsp+1B0h+var_138]
0x180010767  mov     rax, [rax+18h]
0x18001076b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010770  mov     edi, eax
0x180010772  test    eax, eax
0x180010774  jns     short loc_1800107CE
0x180010776  mov     ecx, cs:dword_1800BE0B8
0x18001077c  cmp     ecx, 2
0x18001077f  jbe     short loc_1800107A9
0x180010781  mov     [rsp+1B0h+var_168], eax
0x180010785  lea     rax, [rsp+1B0h+var_168]
0x18001078a  mov     [rsp+1B0h+var_190], rax
0x18001078f  xor     r9d, r9d
0x180010792  xor     r8d, r8d
0x180010795  lea     rdx, byte_1800AA825
0x18001079c  lea     rcx, dword_1800BE0B8
0x1800107a3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800107a8  nop
0x1800107a9  lea     rcx, [rsp+1B0h+var_140]
0x1800107ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800107b3  nop
0x1800107b4  cmp     [rsp+1B0h+var_180], r15b
0x1800107b9  jz      short loc_1800107C7
0x1800107bb  call    cs:__imp_CoUninitialize
0x1800107c2  nop     dword ptr [rax+rax+00h]
0x1800107c7  mov     eax, edi
0x1800107c9  jmp     loc_180010FDF
0x1800107ce  xorps   xmm0, xmm0
0x1800107d1  movdqu  [rbp+0B0h+var_128], xmm0
0x1800107d6  mov     ecx, 0A8h; Size
0x1800107db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800107e0  mov     [rax], rax
0x1800107e3  mov     [rax+8], rax
0x1800107e7  mov     [rax+10h], rax
0x1800107eb  mov     word ptr [rax+18h], 101h
0x1800107f1  mov     qword ptr [rbp+0B0h+var_128], rax
0x1800107f5  mov     r12d, r15d
0x1800107f8  lea     rsi, dword_1800BE0B8
0x1800107ff  cmp     [rsp+1B0h+var_138], r15d
0x180010804  jbe     loc_180010DE2
0x18001080a  movdqa  xmm6, cs:__xmm@00000008000000040000000200000001
0x180010812  mov     [rsp+1B0h+var_170], r15
0x180010817  mov     rdi, [rsp+1B0h+var_140]
0x18001081c  mov     rax, [rdi]
0x18001081f  mov     rbx, [rax+20h]
0x180010823  lea     rcx, [rsp+1B0h+var_170]
0x180010828  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001082d  lea     r8, [rsp+1B0h+var_170]
0x180010832  mov     edx, r12d
0x180010835  mov     rcx, rdi
0x180010838  mov     rax, rbx
0x18001083b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010840  test    eax, eax
0x180010842  jns     short loc_18001087A
0x180010844  mov     ecx, cs:dword_1800BE0B8
0x18001084a  cmp     ecx, 2
0x18001084d  jbe     short loc_180010872
0x18001084f  mov     dword ptr [rsp+1B0h+var_178], eax
0x180010853  lea     rdx, byte_1800AA89B
0x18001085a  xor     r9d, r9d
0x18001085d  lea     rax, [rsp+1B0h+var_178]
0x180010862  xor     r8d, r8d
0x180010865  mov     [rsp+1B0h+var_190], rax
0x18001086a  mov     rcx, rsi
0x18001086d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010872  mov     edi, r15d
0x180010875  jmp     loc_180010DCA
0x18001087a  mov     [rsp+1B0h+var_134], r15d
0x18001087f  mov     rcx, [rsp+1B0h+var_170]
0x180010884  movups  xmm0, cs:xmmword_18008F2D8
0x18001088b  movdqu  [rsp+1B0h+var_150], xmm0
0x180010891  mov     rax, [rcx]
0x180010894  lea     r8, [rsp+1B0h+var_134]
0x180010899  lea     rdx, [rsp+1B0h+var_150]
0x18001089e  mov     rax, [rax+58h]
0x1800108a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a7  mov     edi, eax
0x1800108a9  test    eax, eax
0x1800108ab  jns     short loc_1800108C5
0x1800108ad  mov     eax, cs:dword_1800BE0B8
0x1800108b3  cmp     eax, 3
0x1800108b6  jbe     short loc_180010872
0x1800108b8  mov     dword ptr [rsp+1B0h+var_178], edi
0x1800108bc  lea     rdx, byte_1800AA85D
0x1800108c3  jmp     short loc_18001085A
0x1800108c5  cmp     [rsp+1B0h+var_134], r15d
0x1800108ca  jz      loc_180010DCA
0x1800108d0  lea     rcx, [rbp+0B0h+var_C0]
0x1800108d4  call    _NgcHandler__EnumContainers____2___NgcEnumContainerInfo__NgcEnumContainerInfo
0x1800108d9  nop
0x1800108da  mov     rcx, [rsp+1B0h+var_170]
0x1800108df  mov     rax, [rcx]
0x1800108e2  lea     rdx, [rbp+0B0h+var_C0]
0x1800108e6  mov     rax, [rax+40h]
0x1800108ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ef  test    eax, eax
0x1800108f1  jns     short loc_180010929
0x1800108f3  mov     ecx, cs:dword_1800BE0B8
0x1800108f9  cmp     ecx, 3
0x1800108fc  jbe     short loc_180010921
0x1800108fe  lea     rdx, word_1800AA786
0x180010905  mov     dword ptr [rsp+1B0h+var_178], eax
0x180010909  lea     rax, [rsp+1B0h+var_178]
0x18001090e  xor     r9d, r9d
0x180010911  mov     [rsp+1B0h+var_190], rax
0x180010916  xor     r8d, r8d
0x180010919  mov     rcx, rsi
0x18001091c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010921  mov     edi, r15d
0x180010924  jmp     loc_180010DC0
0x180010929  mov     rcx, [rsp+1B0h+var_170]
0x18001092e  mov     rax, [rcx]
0x180010931  lea     rdx, [rbp+0B0h+var_A0]
0x180010935  mov     rax, [rax+18h]
0x180010939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001093e  test    eax, eax
0x180010940  jns     short loc_180010956
0x180010942  mov     ecx, cs:dword_1800BE0B8
0x180010948  cmp     ecx, 3
0x18001094b  jbe     short loc_180010921
0x18001094d  lea     rdx, byte_1800AA7F1
0x180010954  jmp     short loc_180010905
0x180010956  mov     [rbp+0B0h+var_118], r15d
0x18001095a  mov     [rbp+0B0h+var_130], r15d
0x18001095e  mov     rcx, [rsp+1B0h+var_170]
0x180010963  mov     rax, [rcx]
0x180010966  lea     r8, [rbp+0B0h+var_130]
0x18001096a  lea     rdx, [rbp+0B0h+var_118]
0x18001096e  mov     rax, [rax+48h]
0x180010972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010977  test    eax, eax
0x180010979  jns     short loc_180010992
0x18001097b  mov     ecx, cs:dword_1800BE0B8
0x180010981  cmp     ecx, 3
0x180010984  jbe     short loc_180010921
0x180010986  lea     rdx, word_1800AA7B6
0x18001098d  jmp     loc_180010905
0x180010992  cmp     [rbp+0B0h+var_130], r15d
0x180010996  jz      short loc_18001099C
0x180010998  or      [rbp+0B0h+var_A4], 4
0x18001099c  lea     r8, [rbp+0B0h+StringSid]
0x1800109a0  mov     edx, 1
0x1800109a5  lea     rcx, [rsp+1B0h+var_170]
0x1800109aa  call    ?AllocateAndCopyContainerStringProperty@NgcHandler@@CAJAEAV?$ComPtr@UINgcCtnrContainer@@@WRL@Microsoft@@W4NgcCtnrContainerProperty@@PEAV?$unique_ptr@GU?$rpcmem_delete@G@@@std@@@Z; NgcHandler::AllocateAndCopyContainerStringProperty(Microsoft::WRL::ComPtr<INgcCtnrContainer> &,NgcCtnrContainerProperty,std::unique_ptr<ushort,rpcmem_delete<ushort>> *)
0x1800109af  mov     edi, eax
0x1800109b1  test    eax, eax
0x1800109b3  js      loc_180010921
0x1800109b9  mov     qword ptr [rsp+1B0h+var_150], r15
0x1800109be  lea     rax, [rsp+1B0h+var_150]
0x1800109c3  mov     [rbp+0B0h+var_E8], rax
0x1800109c7  mov     [rbp+0B0h+Sid], r15
0x1800109cb  mov     [rbp+0B0h+var_D8], 1
0x1800109cf  lea     rdx, [rbp+0B0h+Sid]; Sid
0x1800109d3  mov     rcx, [rbp+0B0h+StringSid]; StringSid
0x1800109d7  call    cs:__imp_ConvertStringSidToSidW
0x1800109de  nop     dword ptr [rax+rax+00h]
0x1800109e3  mov     ebx, eax
0x1800109e5  lea     rcx, [rbp+0B0h+var_E8]
0x1800109e9  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800109ee  test    ebx, ebx
0x1800109f0  jnz     short loc_180010A3D
0x1800109f2  mov     eax, cs:dword_1800BE0B8
0x1800109f8  cmp     eax, 3
0x1800109fb  jbe     short loc_180010A2C
0x1800109fd  call    cs:__imp_GetLastError
0x180010a04  nop     dword ptr [rax+rax+00h]
0x180010a09  mov     [rsp+1B0h+var_164], eax
0x180010a0d  lea     rax, [rsp+1B0h+var_164]
0x180010a12  mov     [rsp+1B0h+var_190], rax
0x180010a17  xor     r9d, r9d
0x180010a1a  xor     r8d, r8d
0x180010a1d  lea     rdx, byte_1800AA745
0x180010a24  mov     rcx, rsi
0x180010a27  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010a2c  xor     edx, edx
0x180010a2e  lea     rcx, [rsp+1B0h+var_150]
0x180010a33  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x180010a38  jmp     loc_180010DC0
0x180010a3d  xor     edx, edx
0x180010a3f  lea     rcx, [rsp+1B0h+var_150]
0x180010a44  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x180010a49  mov     [rsp+1B0h+var_178], r15
0x180010a4e  lea     r8, [rsp+1B0h+var_178]
0x180010a53  mov     edx, 3
0x180010a58  lea     rcx, [rsp+1B0h+var_170]
0x180010a5d  call    ?AllocateAndCopyContainerStringProperty@NgcHandler@@CAJAEAV?$ComPtr@UINgcCtnrContainer@@@WRL@Microsoft@@W4NgcCtnrContainerProperty@@PEAV?$unique_ptr@GU?$rpcmem_delete@G@@@std@@@Z; NgcHandler::AllocateAndCopyContainerStringProperty(Microsoft::WRL::ComPtr<INgcCtnrContainer> &,NgcCtnrContainerProperty,std::unique_ptr<ushort,rpcmem_delete<ushort>> *)
0x180010a62  test    eax, eax
0x180010a64  jns     short loc_180010A78
0x180010a66  mov     edi, r15d
0x180010a69  lea     rcx, [rsp+1B0h+var_178]
0x180010a6e  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180010a73  jmp     loc_180010DC0
0x180010a78  mov     rdx, [rsp+1B0h+var_178]
0x180010a7d  test    rdx, rdx
0x180010a80  jz      short loc_180010A99
0x180010a82  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010a86  inc     r8
0x180010a89  cmp     [rdx+r8*2], r15w
0x180010a8e  jnz     short loc_180010A86
0x180010a90  lea     rcx, [rbp+0B0h+var_98]
0x180010a94  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010a99  mov     qword ptr [rsp+1B0h+var_150], r15
0x180010a9e  lea     r8, [rsp+1B0h+var_150]
0x180010aa3  mov     edx, 4
0x180010aa8  lea     rcx, [rsp+1B0h+var_170]
0x180010aad  call    ?AllocateAndCopyContainerStringProperty@NgcHandler@@CAJAEAV?$ComPtr@UINgcCtnrContainer@@@WRL@Microsoft@@W4NgcCtnrContainerProperty@@PEAV?$unique_ptr@GU?$rpcmem_delete@G@@@std@@@Z; NgcHandler::AllocateAndCopyContainerStringProperty(Microsoft::WRL::ComPtr<INgcCtnrContainer> &,NgcCtnrContainerProperty,std::unique_ptr<ushort,rpcmem_delete<ushort>> *)
0x180010ab2  mov     edi, eax
0x180010ab4  test    eax, eax
0x180010ab6  jns     short loc_180010AC7
0x180010ab8  mov     edi, r15d
0x180010abb  lea     rcx, [rsp+1B0h+var_150]
0x180010ac0  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180010ac5  jmp     short loc_180010A69
0x180010ac7  mov     rdx, qword ptr [rsp+1B0h+var_150]
0x180010acc  test    rdx, rdx
0x180010acf  jz      short loc_180010AE9
0x180010ad1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010ad5  inc     r8
0x180010ad8  cmp     [rdx+r8*2], r15w
0x180010add  jnz     short loc_180010AD5
0x180010adf  lea     rcx, [rbp+0B0h+var_78]
0x180010ae3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010ae8  nop
0x180010ae9  lea     rcx, [rsp+1B0h+var_150]
0x180010aee  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180010af3  nop
0x180010af4  lea     rcx, [rsp+1B0h+var_178]
0x180010af9  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180010afe  movdqu  [rbp+0B0h+var_100], xmm6
0x180010b03  mov     [rbp+0B0h+var_F0], 10h
  ... truncated ...
```
