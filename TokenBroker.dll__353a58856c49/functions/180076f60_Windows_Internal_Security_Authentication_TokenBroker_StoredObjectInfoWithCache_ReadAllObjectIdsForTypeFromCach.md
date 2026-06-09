# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::ReadAllObjectIdsForTypeFromCache(Windows::Internal::Security::Authentication::Web::IWamObjectStore *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>,std::allocator<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>> &)

- ea: `0x180076f60`
- end: `0x1800780ef`
- name: `?ReadAllObjectIdsForTypeFromCache@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@CAJPEAUIWamObjectStore@Web@3456@W4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z`
- size: `4495`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005a8ec`

## callees

- `0x180008fb0`
- `0x18000a5d0`
- `0x18000bd40`
- `0x1800426b0`
- `0x180076f60`
- `0x18007f9b0`
- `0x18008e690`
- `0x18008e6b4`
- `0x18008e6cc`
- `0x18009c780`
- `0x180110bf4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800780bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800780bb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180077099`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180077099`

## string_xrefs

- `0x1800770fe`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800771c4`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077247`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800772ca`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077760`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077830`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077999`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077afd`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077c60`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077fa5`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::ReadAllObjectIdsForTypeFromCache(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        void **a4)
{
  void **v4; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v6; // rcx
  int v7; // ecx
  int AllObjectsCacheKey; // eax
  int v9; // ebx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // r13
  __int64 v22; // rcx
  unsigned __int16 *v23; // r12
  char *v24; // r14
  char *v25; // rsi
  int v26; // eax
  unsigned int v27; // r15d
  _QWORD *v28; // rdi
  signed __int64 v29; // rbx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // r13
  size_t v33; // r13
  _QWORD *v34; // r15
  void *v35; // rax
  _QWORD *v36; // rdx
  _QWORD *v37; // rsi
  _QWORD *v38; // rcx
  _QWORD *v39; // rbx
  _QWORD *v40; // rcx
  volatile signed __int32 *v41; // rdi
  _BYTE *v42; // rcx
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // rcx
  __int64 v48; // rax
  const WCHAR *v49; // rbx
  char *v50; // rdi
  char *v51; // rsi
  volatile signed __int32 *v52; // rbx
  _BYTE *v53; // rcx
  char *v54; // rdi
  char *v55; // r14
  volatile signed __int32 *v56; // rbx
  _BYTE *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  char *v60; // rdi
  char *v61; // r14
  volatile signed __int32 *v62; // rbx
  _BYTE *v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  char *v66; // rdi
  char *v67; // r14
  volatile signed __int32 *v68; // rbx
  void *v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  char *v72; // rdi
  char *v73; // rsi
  volatile signed __int32 *v74; // rbx
  _BYTE *v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  char *v80; // rax
  char *v81; // rdi
  char *v82; // rax
  char *v83; // rsi
  char *v84; // rcx
  volatile signed __int32 *v85; // rbx
  _BYTE *v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  char *v89; // rdi
  char *v90; // r14
  volatile signed __int32 *v91; // rbx
  _BYTE *v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rcx
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  int v96; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v97; // [rsp+48h] [rbp-B8h] BYREF
  char v98; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v100; // [rsp+68h] [rbp-98h]
  __int64 v101; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v102; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR v103; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v104; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v105; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  int v107[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v108; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v109; // [rsp+B0h] [rbp-50h] BYREF
  void **v110; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  char *v112; // [rsp+D0h] [rbp-30h]
  char *v113; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING *p_string; // [rsp+F0h] [rbp-10h]
  __int64 v116; // [rsp+F8h] [rbp-8h]
  PCWSTR *v117; // [rsp+100h] [rbp+0h]
  __int64 v118; // [rsp+108h] [rbp+8h]
  PCWSTR v119; // [rsp+110h] [rbp+10h]
  int v120; // [rsp+118h] [rbp+18h]
  int v121; // [rsp+11Ch] [rbp+1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  unsigned int v123; // [rsp+188h] [rbp+88h] BYREF

  v123 = a2;
  v4 = a4;
  v110 = a4;
  v108 = a1;
  string = a3;
  v96 = 0;
  v102 = 0;
  v98 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LODWORD(v105) = v123;
    if ( StringRawBuffer )
    {
      v6 = -1;
      do
        ++v6;
      while ( StringRawBuffer[v6] );
      v7 = 2 * v6 + 2;
    }
    else
    {
      StringRawBuffer = &word_1801330B0;
      v7 = 2;
    }
    v119 = StringRawBuffer;
    v120 = v7;
    v121 = 0;
    v117 = &v105;
    v118 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180175008;
    UserData.Size = *(unsigned __int16 *)off_180175008;
    UserData.Reserved = 2;
    p_string = (HSTRING *)byte_180159541;
    v116 = 0x100000056LL;
    LODWORD(v103) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  UserData.Ptr = (ULONGLONG)&v96;
  *(_QWORD *)&UserData.Size = &v123;
  p_string = &string;
  v116 = (__int64)&v98;
  v117 = (PCWSTR *)&v108;
  v118 = (__int64)&v102;
  LOBYTE(v119) = 1;
  AllObjectsCacheKey = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(
                         v123,
                         string,
                         &v102);
  v9 = AllObjectsCacheKey;
  v96 = AllObjectsCacheKey;
  if ( AllObjectsCacheKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)AllObjectsCacheKey,
      UserDataCount);
    LOBYTE(v119) = 0;
    lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
LABEL_10:
    if ( v102 )
      WindowsDeleteString(v102);
    return (unsigned int)v9;
  }
  v97 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v108 + 48LL))(v108, v102, &v97);
  v96 = v9;
  if ( v9 < 0 )
  {
    v11 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
LABEL_34:
    LOBYTE(v119) = 0;
    lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
    goto LABEL_10;
  }
  v101 = 0;
  v109 = 0;
  v104 = 0;
  v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v97)(
          v97,
          &GUID_905a0fef_bc53_11df_8c49_001e4fc686da,
          &v101);
  v9 = v12;
  v96 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v12,
      UserDataCount);
    v13 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_34;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v101 + 24LL))(v101, &v109);
  v9 = v15;
  v96 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v15,
      UserDataCount);
    v16 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_34;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v97 + 56LL))(v97, &v104);
  v9 = v18;
  v96 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v18,
      UserDataCount);
    v19 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_34;
  }
  *(_OWORD *)Block = 0;
  v100 = 0;
  v21 = 0;
  v103 = 0;
  v22 = v104;
  *(_QWORD *)&EventDescriptor.Id = v104;
  v23 = v109;
  v98 = 1;
  if ( !v104 )
  {
LABEL_88:
    if ( v21 + 2 < v21 )
    {
      v96 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      v89 = (char *)Block[0];
      if ( Block[0] )
      {
        v90 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v91 = (volatile signed __int32 *)*((_QWORD *)v89 + 1);
            if ( v91 )
            {
              if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
                if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
              }
            }
            v89 += 16;
          }
          while ( v89 != v90 );
          v89 = (char *)Block[0];
        }
        if ( ((v100 - v89) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v92 = v89;
        }
        else
        {
          v92 = (_BYTE *)*((_QWORD *)v89 - 1);
          if ( (unsigned __int64)(v89 - v92 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v92);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v93 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      }
      v94 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      LOBYTE(v119) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v102 )
        WindowsDeleteString(v102);
      return 2147942934LL;
    }
    else if ( v21 + 2 == v22 )
    {
      if ( Block == v4 )
      {
        v83 = (char *)Block[1];
        v81 = (char *)Block[0];
      }
      else
      {
        v80 = (char *)Block[0];
        v81 = (char *)*v4;
        Block[0] = *v4;
        *v4 = v80;
        v82 = (char *)Block[1];
        v83 = (char *)v4[1];
        Block[1] = v83;
        v4[1] = v82;
        v84 = v100;
        v100 = (char *)v4[2];
        v4[2] = v84;
      }
      v96 = 0;
      if ( v81 )
      {
        if ( v81 != v83 )
        {
          do
          {
            v85 = (volatile signed __int32 *)*((_QWORD *)v81 + 1);
            if ( v85 )
            {
              if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v85)(v85);
                if ( _InterlockedExchangeAdd(v85 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 8LL))(v85);
              }
            }
            v81 += 16;
          }
          while ( v81 != v83 );
          v81 = (char *)Block[0];
        }
        if ( ((v100 - v81) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v86 = v81;
        }
        else
        {
          v86 = (_BYTE *)*((_QWORD *)v81 - 1);
          if ( (unsigned __int64)(v81 - v86 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v86);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v87 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      LOBYTE(v119) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v102 )
        WindowsDeleteString(v102);
      return 0;
    }
    else
    {
      v96 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x723,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x8007000DLL,
        UserDataCount);
      v50 = (char *)Block[0];
      if ( Block[0] )
      {
        v51 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v52 = (volatile signed __int32 *)*((_QWORD *)v50 + 1);
            if ( v52 )
            {
              if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
                if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
              }
            }
            v50 += 16;
          }
          while ( v50 != v51 );
          v50 = (char *)Block[0];
        }
        if ( ((v100 - v50) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v53 = v50;
        }
        else
        {
          v53 = (_BYTE *)*((_QWORD *)v50 - 1);
          if ( (unsigned __int64)(v50 - v53 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v53);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v78 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v79 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      }
      LOBYTE(v119) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v102 )
        WindowsDeleteString(v102);
      return 2147942413LL;
    }
  }
  while ( 1 )
  {
    if ( !*v23 )
    {
LABEL_87:
      v4 = v110;
      goto LABEL_88;
    }
    v24 = (char *)operator new(0x38u);
    *(_QWORD *)v107 = v24;
    *(_OWORD *)v24 = 0;
    *((_DWORD *)v24 + 2) = 1;
    *((_DWORD *)v24 + 3) = 1;
    *(_QWORD *)v24 = &std::_Ref_count_obj2<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>::`vftable';
    v25 = v24 + 16;
    *((_QWORD *)v24 + 2) = 0;
    *((_DWORD *)v24 + 6) = 0;
    *((_QWORD *)v24 + 4) = 0;
    *((_QWORD *)v24 + 5) = 0;
    *((_QWORD *)v24 + 6) = 0;
    v112 = v24 + 16;
    v113 = v24;
    v26 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(
            (HLOCAL *)v24 + 2,
            v23);
    v27 = v26;
    v96 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x707,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)v26,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v72 = (char *)Block[0];
      if ( Block[0] )
      {
        v73 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v74 = (volatile signed __int32 *)*((_QWORD *)v72 + 1);
            if ( v74 )
            {
              if ( _InterlockedExchangeAdd(v74 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
                if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
              }
            }
            v72 += 16;
          }
          while ( v72 != v73 );
          v72 = (char *)Block[0];
        }
        if ( ((v100 - v72) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v75 = v72;
        }
        else
        {
          v75 = (_BYTE *)*((_QWORD *)v72 - 1);
          if ( (unsigned __int64)(v72 - v75 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v75);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v76 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
      v77 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      }
      goto LABEL_185;
    }
    v28 = Block[1];
    if ( Block[1] != v100 )
    {
      *(_QWORD *)Block[1] = 0;
      v28[1] = 0;
      _InterlockedIncrement((volatile signed __int32 *)v24 + 2);
      *v28 = v25;
      v28[1] = v24;
      Block[1] = (char *)Block[1] + 16;
      goto LABEL_76;
    }
    v29 = ((char *)Block[1] - (char *)Block[0]) >> 4;
    if ( v29 == 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Xlength();
    v30 = (v100 - (char *)Block[0]) >> 4;
    v31 = v30 >> 1;
    if ( v30 > 0xFFFFFFFFFFFFFFFLL - (v30 >> 1) )
      goto LABEL_241;
    v105 = (PCWSTR)(v29 + 1);
    v32 = v29 + 1;
    if ( v31 + v30 >= v29 + 1 )
      v32 = v31 + v30;
    if ( v32 > 0xFFFFFFFFFFFFFFFLL )
LABEL_241:
      std::_Throw_bad_array_new_length();
    v33 = 16 * v32;
    if ( v33 )
    {
      if ( v33 < 0x1000 )
      {
        v34 = operator new(v33);
      }
      else
      {
        if ( v33 + 39 < v33 )
          goto LABEL_241;
        v35 = operator new(v33 + 39);
        if ( !v35 )
LABEL_101:
          __fastfail(5u);
        v34 = (_QWORD *)(((unsigned __int64)v35 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v34 - 1) = v35;
      }
    }
    else
    {
      v34 = 0;
    }
    v36 = &v34[2 * v29];
    *v36 = 0;
    v36[1] = 0;
    _InterlockedIncrement((volatile signed __int32 *)v24 + 2);
    *v36 = v25;
    v36[1] = v24;
    v37 = Block[1];
    v38 = v34;
    v39 = Block[0];
    if ( v28 != Block[1] )
    {
      if ( Block[0] != v28 )
      {
        do
        {
          *v38 = 0;
          v38[1] = 0;
          *v38 = *v39;
          v38[1] = v39[1];
          *v39 = 0;
          v39[1] = 0;
          v38 += 2;
          v39 += 2;
        }
        while ( v39 != v28 );
        v37 = Block[1];
        v39 = Block[0];
      }
      v40 = v36 + 2;
      if ( v28 == v37 )
        goto LABEL_62;
      do
      {
        *v40 = 0;
        v40[1] = 0;
        *v40 = *v28;
        v40[1] = v28[1];
        *v28 = 0;
        v28[1] = 0;
        v40 += 2;
        v28 += 2;
      }
      while ( v28 != v37 );
      goto LABEL_61;
    }
    if ( Block[0] != Block[1] )
    {
      do
      {
        *v38 = 0;
        v38[1] = 0;
        *v38 = *v39;
        v38[1] = v39[1];
        *v39 = 0;
        v39[1] = 0;
        v38 += 2;
        v39 += 2;
      }
      while ( v39 != v37 );
LABEL_61:
      v39 = Block[0];
      v37 = Block[1];
    }
LABEL_62:
    if ( v39 )
    {
      if ( v39 != v37 )
      {
        do
        {
          v41 = (volatile signed __int32 *)v39[1];
          if ( v41 )
          {
            if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
              if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
            }
          }
          v39 += 2;
        }
        while ( v39 != v37 );
        v39 = Block[0];
      }
      if ( ((v100 - (char *)v39) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
      {
        v42 = v39;
      }
      else
      {
        v42 = (_BYTE *)*(v39 - 1);
        if ( (unsigned __int64)((char *)v39 - v42 - 8) > 0x1F )
          goto LABEL_101;
      }
      operator delete(v42);
    }
    Block[0] = v34;
    Block[1] = &v34[2 * (_QWORD)v105];
    v100 = (char *)&v34[v33 / 8];
    v21 = (unsigned __int64)v103;
LABEL_76:
    if ( (unsigned int)dword_180175000 > 5 )
    {
      v103 = WindowsGetStringRawBuffer(v102, 0);
      v105 = WindowsGetStringRawBuffer(string, 0);
      *(_QWORD *)v107 = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v43,
        (unsigned int)&byte_1801596AF,
        v44,
        v45,
        (__int64)v107,
        (__int64)&v105,
        (__int64)&v103);
    }
    v46 = -1;
    do
      ++v46;
    while ( v23[v46] );
    v47 = v46 + 1;
    if ( v46 + 1 < v46 )
      break;
    *(_QWORD *)v107 = 0;
    v48 = 2 * v47;
    if ( !is_mul_ok(v47, 2u) )
    {
      v96 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x717,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v27 = -2147024362;
      v60 = (char *)Block[0];
      if ( Block[0] )
      {
        v61 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v62 = (volatile signed __int32 *)*((_QWORD *)v60 + 1);
            if ( v62 )
            {
              if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
                if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
              }
            }
            v60 += 16;
          }
          while ( v60 != v61 );
          v60 = (char *)Block[0];
        }
        if ( ((v100 - v60) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v63 = v60;
        }
        else
        {
          v63 = (_BYTE *)*((_QWORD *)v60 - 1);
          if ( (unsigned __int64)(v60 - v63 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v63);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v64 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      }
      v65 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      goto LABEL_185;
    }
    v49 = (const WCHAR *)(v48 + v21);
    if ( v48 + v21 < v21 )
    {
      v96 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x718,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v27 = -2147024362;
      v54 = (char *)Block[0];
      if ( Block[0] )
      {
        v55 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v56 = (volatile signed __int32 *)*((_QWORD *)v54 + 1);
            if ( v56 )
            {
              if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
                if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
              }
            }
            v54 += 16;
          }
          while ( v54 != v55 );
          v54 = (char *)Block[0];
        }
        if ( ((v100 - v54) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v57 = v54;
        }
        else
        {
          v57 = (_BYTE *)*((_QWORD *)v54 - 1);
          if ( (unsigned __int64)(v54 - v57 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v57);
        *(_OWORD *)Block = 0;
        v100 = 0;
      }
      v58 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      }
      v59 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      }
      goto LABEL_185;
    }
    v23 += v47;
    v96 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v24)(v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
    }
    v21 = (unsigned __int64)v49;
    v103 = v49;
    v22 = *(_QWORD *)&EventDescriptor.Id;
    if ( (unsigned __int64)v49 >= *(_QWORD *)&EventDescriptor.Id )
      goto LABEL_87;
  }
  v96 = -2147024362;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x713,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)0x80070216LL,
    UserDataCount);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v24)(v24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
  }
  v27 = -2147024362;
  v66 = (char *)Block[0];
  if ( Block[0] )
  {
    v67 = (char *)Block[1];
    if ( Block[0] != Block[1] )
    {
      do
      {
        v68 = (volatile signed __int32 *)*((_QWORD *)v66 + 1);
        if ( v68 )
        {
          if ( _InterlockedExchangeAdd(v68 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
            if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
          }
        }
        v66 += 16;
      }
      while ( v66 != v67 );
      v66 = (char *)Block[0];
    }
    if ( ((v100 - v66) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v69 = v66;
      goto LABEL_159;
    }
    v69 = (void *)*((_QWORD *)v66 - 1);
    if ( (unsigned __int64)(v66 - (_BYTE *)v69 - 8) <= 0x1F )
    {
LABEL_159:
      operator delete(v69);
      *(_OWORD *)Block = 0;
      v100 = 0;
      goto LABEL_160;
    }
LABEL_230:
    __fastfail(5u);
  }
LABEL_160:
  v70 = v101;
  if ( v101 )
  {
    v101 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  }
  v71 = v97;
  if ( v97 )
  {
    v97 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  }
LABEL_185:
  LOBYTE(v119) = 0;
  lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
  if ( v102 )
    WindowsDeleteString(v102);
  return v27;
}

```

## disassembly

```asm
0x180076f60  mov     [rsp-8+arg_8], edx
0x180076f64  push    rbp
0x180076f65  push    rbx
0x180076f66  push    rsi
0x180076f67  push    rdi
0x180076f68  push    r12
0x180076f6a  push    r13
0x180076f6c  push    r14
0x180076f6e  push    r15
0x180076f70  lea     rbp, [rsp-38h]
0x180076f75  sub     rsp, 138h
0x180076f7c  mov     rax, cs:__security_cookie
0x180076f83  xor     rax, rsp
0x180076f86  mov     [rbp+70h+var_50], rax
0x180076f8a  mov     r14, r9
0x180076f8d  mov     [rbp+70h+var_B8], r9
0x180076f91  mov     [rbp+70h+var_C8], rcx
0x180076f95  mov     [rbp+70h+string], r8
0x180076f99  xor     r15d, r15d
0x180076f9c  mov     [rsp+170h+var_130], r15d
0x180076fa1  mov     [rsp+170h+var_F8], r15
0x180076fa6  mov     [rsp+170h+var_120], r15b
0x180076fab  mov     eax, cs:dword_180175000
0x180076fb1  cmp     eax, 4
0x180076fb4  jbe     loc_18007709F
0x180076fba  xor     edx, edx; length
0x180076fbc  mov     rcx, [rbp+70h+string]; string
0x180076fc0  call    cs:__imp_WindowsGetStringRawBuffer
0x180076fc6  mov     ecx, [rbp+70h+arg_8]
0x180076fcc  mov     dword ptr [rbp+70h+var_E0], ecx
0x180076fcf  test    rax, rax
0x180076fd2  jz      short loc_180076FF4
0x180076fd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180076fdb  nop     dword ptr [rax+rax+00h]
0x180076fe0  lea     rcx, [rcx+1]
0x180076fe4  cmp     word ptr [rax+rcx*2], 0
0x180076fe9  jnz     short loc_180076FE0
0x180076feb  lea     ecx, ds:2[rcx*2]
0x180076ff2  jmp     short loc_180077000
0x180076ff4  lea     rax, word_1801330B0
0x180076ffb  mov     ecx, 2
0x180077000  mov     [rbp+70h+var_60], rax
0x180077004  mov     [rbp+70h+var_58], ecx
0x180077007  mov     [rbp+70h+var_54], r15d
0x18007700b  lea     rax, [rbp+70h+var_E0]
0x18007700f  mov     [rbp+70h+var_70], rax
0x180077013  mov     [rbp+70h+var_68], 4
0x18007701b  mov     dword ptr [rbp+70h+EventDescriptor.Id], 0B000000h
0x180077022  movzx   eax, cs:word_180159537
0x180077029  mov     dword ptr [rbp+70h+EventDescriptor.Level], eax
0x18007702c  mov     [rbp+70h+EventDescriptor.Keyword], r15
0x180077030  mov     rax, cs:off_180175008
0x180077037  mov     [rbp+70h+var_90.Ptr], rax
0x18007703b  movzx   eax, word ptr [rax]
0x18007703e  mov     [rbp+70h+var_90.Size], eax
0x180077041  mov     dword ptr [rbp+70h+var_90.0Ch], 2
0x180077048  lea     rax, byte_180159541
0x18007704f  mov     [rbp+70h+var_80], rax
0x180077053  mov     dword ptr [rbp+70h+var_78], 56h ; 'V'
0x18007705a  mov     dword ptr [rbp+70h+var_78+4], 1
0x180077061  lea     rax, _TraceLoggingMetadataEnd
0x180077068  lea     rcx, _TraceLoggingMetadata
0x18007706f  sub     eax, ecx
0x180077071  mov     dword ptr [rbp+70h+var_F0], eax
0x180077074  mov     eax, dword ptr [rbp+70h+var_F0]
0x180077077  lea     rax, [rbp+70h+var_90]
0x18007707b  mov     [rsp+170h+UserData], rax; UserData
0x180077080  mov     [rsp+170h+UserDataCount], 4; int
0x180077088  xor     r9d, r9d; RelatedActivityId
0x18007708b  xor     r8d, r8d; ActivityId
0x18007708e  lea     rdx, [rbp+70h+EventDescriptor]; EventDescriptor
0x180077092  mov     rcx, cs:RegHandle; RegHandle
0x180077099  call    cs:__imp_EventWriteTransfer
0x18007709f  lea     rax, [rsp+170h+var_130]
0x1800770a4  mov     [rbp+70h+var_90.Ptr], rax
0x1800770a8  lea     rax, [rbp+70h+arg_8]
0x1800770af  mov     qword ptr [rbp+70h+var_90.Size], rax
0x1800770b3  lea     rax, [rbp+70h+string]
0x1800770b7  mov     [rbp+70h+var_80], rax
0x1800770bb  lea     rax, [rsp+170h+var_120]
0x1800770c0  mov     [rbp+70h+var_78], rax
0x1800770c4  lea     rax, [rbp+70h+var_C8]
0x1800770c8  mov     [rbp+70h+var_70], rax
0x1800770cc  lea     rax, [rsp+170h+var_F8]
0x1800770d1  mov     [rbp+70h+var_68], rax
0x1800770d5  mov     byte ptr [rbp+70h+var_60], 1
0x1800770d9  lea     r8, [rsp+170h+var_F8]
0x1800770de  mov     rdx, [rbp+70h+string]
0x1800770e2  mov     ecx, [rbp+70h+arg_8]
0x1800770e8  call    ?GetAllObjectsCacheKey@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAVString@56@@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,Windows::Internal::String &)
0x1800770ed  mov     ebx, eax
0x1800770ef  mov     [rsp+170h+var_130], eax
0x1800770f3  test    eax, eax
0x1800770f5  jns     short loc_180077135
0x1800770f7  mov     rcx, [rbp+78h]; this
0x1800770fb  mov     r9d, eax; char *
0x1800770fe  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180077105  mov     edx, 6EBh; void *
0x18007710a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007710f  nop
0x180077110  mov     byte ptr [rbp+70h+var_60], 0
0x180077114  lea     rcx, [rbp+70h+var_90]
0x180077118  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007711d  nop
0x18007711e  mov     rcx, [rsp+170h+var_F8]; string
0x180077123  test    rcx, rcx
0x180077126  jz      short loc_18007712E
0x180077128  call    cs:__imp_WindowsDeleteString
0x18007712e  mov     eax, ebx
0x180077130  jmp     loc_1800780C3
0x180077135  mov     [rsp+170h+var_128], r15
0x18007713a  mov     rcx, [rbp+70h+var_C8]
0x18007713e  mov     rax, [rcx]
0x180077141  lea     r8, [rsp+170h+var_128]
0x180077146  mov     rdx, [rsp+170h+var_F8]
0x18007714b  mov     rax, [rax+30h]
0x18007714f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077154  mov     ebx, eax
0x180077156  mov     [rsp+170h+var_130], eax
0x18007715a  test    eax, eax
0x18007715c  jns     short loc_18007718A
0x18007715e  mov     rcx, [rsp+170h+var_128]
0x180077163  test    rcx, rcx
0x180077166  jz      short loc_18007717A
0x180077168  mov     [rsp+170h+var_128], r15
0x18007716d  mov     rdx, [rcx]
0x180077170  mov     rax, [rdx+10h]
0x180077174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077179  nop
0x18007717a  mov     byte ptr [rbp+70h+var_60], 0
0x18007717e  lea     rcx, [rbp+70h+var_90]
0x180077182  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x180077187  nop
0x180077188  jmp     short loc_18007711E
0x18007718a  mov     [rsp+170h+var_100], r15
0x18007718f  mov     [rbp+70h+var_C0], r15
0x180077193  mov     [rbp+70h+var_E8], r15d
0x180077197  mov     rcx, [rsp+170h+var_128]
0x18007719c  mov     rax, [rcx]
0x18007719f  lea     r8, [rsp+170h+var_100]
0x1800771a4  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x1800771ab  mov     rax, [rax]
0x1800771ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771b3  mov     ebx, eax
0x1800771b5  mov     [rsp+170h+var_130], eax
0x1800771b9  test    eax, eax
0x1800771bb  jns     short loc_180077221
0x1800771bd  mov     rcx, [rbp+78h]; this
0x1800771c1  mov     r9d, eax; char *
0x1800771c4  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800771cb  mov     edx, 6F3h; void *
0x1800771d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771d5  nop
0x1800771d6  mov     rcx, [rsp+170h+var_100]
0x1800771db  test    rcx, rcx
0x1800771de  jz      short loc_1800771F2
0x1800771e0  mov     [rsp+170h+var_100], r15
0x1800771e5  mov     rax, [rcx]
0x1800771e8  mov     rax, [rax+10h]
0x1800771ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771f1  nop
0x1800771f2  mov     rcx, [rsp+170h+var_128]
0x1800771f7  test    rcx, rcx
0x1800771fa  jz      short loc_18007720E
0x1800771fc  mov     [rsp+170h+var_128], r15
0x180077201  mov     rax, [rcx]
0x180077204  mov     rax, [rax+10h]
0x180077208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007720d  nop
0x18007720e  mov     byte ptr [rbp+70h+var_60], 0
0x180077212  lea     rcx, [rbp+70h+var_90]
0x180077216  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007721b  nop
0x18007721c  jmp     loc_18007711E
0x180077221  mov     rcx, [rsp+170h+var_100]
0x180077226  mov     rax, [rcx]
0x180077229  lea     rdx, [rbp+70h+var_C0]
0x18007722d  mov     rax, [rax+18h]
0x180077231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077236  mov     ebx, eax
0x180077238  mov     [rsp+170h+var_130], eax
0x18007723c  test    eax, eax
0x18007723e  jns     short loc_1800772A4
0x180077240  mov     rcx, [rbp+78h]; this
0x180077244  mov     r9d, eax; char *
0x180077247  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007724e  mov     edx, 6F4h; void *
0x180077253  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077258  nop
0x180077259  mov     rcx, [rsp+170h+var_100]
0x18007725e  test    rcx, rcx
0x180077261  jz      short loc_180077275
0x180077263  mov     [rsp+170h+var_100], r15
0x180077268  mov     rax, [rcx]
0x18007726b  mov     rax, [rax+10h]
0x18007726f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077274  nop
0x180077275  mov     rcx, [rsp+170h+var_128]
0x18007727a  test    rcx, rcx
0x18007727d  jz      short loc_180077291
0x18007727f  mov     [rsp+170h+var_128], r15
0x180077284  mov     rax, [rcx]
0x180077287  mov     rax, [rax+10h]
0x18007728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077290  nop
0x180077291  mov     byte ptr [rbp+70h+var_60], 0
0x180077295  lea     rcx, [rbp+70h+var_90]
0x180077299  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007729e  nop
0x18007729f  jmp     loc_18007711E
0x1800772a4  mov     rcx, [rsp+170h+var_128]
0x1800772a9  mov     rax, [rcx]
0x1800772ac  lea     rdx, [rbp+70h+var_E8]
0x1800772b0  mov     rax, [rax+38h]
0x1800772b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772b9  mov     ebx, eax
0x1800772bb  mov     [rsp+170h+var_130], eax
0x1800772bf  test    eax, eax
0x1800772c1  jns     short loc_180077327
0x1800772c3  mov     rcx, [rbp+78h]; this
0x1800772c7  mov     r9d, eax; char *
0x1800772ca  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800772d1  mov     edx, 6F5h; void *
0x1800772d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800772db  nop
0x1800772dc  mov     rcx, [rsp+170h+var_100]
0x1800772e1  test    rcx, rcx
0x1800772e4  jz      short loc_1800772F8
0x1800772e6  mov     [rsp+170h+var_100], r15
0x1800772eb  mov     rax, [rcx]
0x1800772ee  mov     rax, [rax+10h]
0x1800772f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772f7  nop
0x1800772f8  mov     rcx, [rsp+170h+var_128]
0x1800772fd  test    rcx, rcx
0x180077300  jz      short loc_180077314
0x180077302  mov     [rsp+170h+var_128], r15
0x180077307  mov     rax, [rcx]
0x18007730a  mov     rax, [rax+10h]
0x18007730e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077313  nop
0x180077314  mov     byte ptr [rbp+70h+var_60], 0
0x180077318  lea     rcx, [rbp+70h+var_90]
0x18007731c  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x180077321  nop
0x180077322  jmp     loc_18007711E
0x180077327  xorps   xmm0, xmm0
0x18007732a  movdqu  xmmword ptr [rsp+170h+Block], xmm0
0x180077330  mov     [rsp+170h+var_108], r15
0x180077335  mov     r13, r15
0x180077338  mov     [rbp+70h+var_F0], r15
0x18007733c  mov     ecx, [rbp+70h+var_E8]
0x18007733f  mov     qword ptr [rbp+70h+EventDescriptor.Id], rcx
0x180077343  mov     r12, [rbp+70h+var_C0]
0x180077347  mov     [rsp+170h+var_120], 1
0x18007734c  test    rcx, rcx
0x18007734f  jz      loc_180077738
0x180077355  lea     rbx, ??_7?$_Ref_count_obj2@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>::`vftable'
0x18007735c  cmp     word ptr [r12], 0
0x180077362  jz      loc_180077734
0x180077368  mov     ecx, 38h ; '8'; Size
0x18007736d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077372  mov     r14, rax
0x180077375  mov     qword ptr [rbp+70h+var_D0], rax
0x180077379  xorps   xmm0, xmm0
0x18007737c  movups  xmmword ptr [rax], xmm0
0x18007737f  mov     dword ptr [rax+8], 1
0x180077386  mov     dword ptr [rax+0Ch], 1
0x18007738d  mov     [rax], rbx
0x180077390  lea     rsi, [rax+10h]
0x180077394  mov     [rsi], r15
0x180077397  mov     [rsi+8], r15d
0x18007739b  mov     [rsi+10h], r15
0x18007739f  mov     [rsi+18h], r15
0x1800773a3  mov     [rsi+20h], r15
0x1800773a7  mov     [rbp+70h+var_A0], rsi
0x1800773ab  mov     [rbp+70h+var_98], rax
0x1800773af  mov     rdx, r12; unsigned __int16 *
0x1800773b2  mov     rcx, rsi; this
0x1800773b5  call    ?InitializeFromCryptString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAJPEBGK@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(ushort const *,ulong)
0x1800773ba  mov     r15d, eax
0x1800773bd  mov     [rsp+170h+var_130], eax
0x1800773c1  test    eax, eax
0x1800773c3  js      loc_180077C59
0x1800773c9  mov     rdi, [rsp+170h+Block+8]
0x1800773ce  mov     rcx, [rsp+170h+var_108]
0x1800773d3  cmp     rdi, rcx
0x1800773d6  jz      short loc_1800773F9
0x1800773d8  xor     r15d, r15d
0x1800773db  mov     [rdi], r15
0x1800773de  mov     [rdi+8], r15
0x1800773e2  lock inc dword ptr [r14+8]
0x1800773e7  mov     [rdi], rsi
0x1800773ea  mov     [rdi+8], r14
0x1800773ee  add     [rsp+170h+Block+8], 10h
0x1800773f4  jmp     loc_180077640
0x1800773f9  mov     rbx, rdi
0x1800773fc  mov     rax, [rsp+170h+Block]
0x180077401  sub     rbx, rax
0x180077404  sar     rbx, 4
  ... truncated ...
```
