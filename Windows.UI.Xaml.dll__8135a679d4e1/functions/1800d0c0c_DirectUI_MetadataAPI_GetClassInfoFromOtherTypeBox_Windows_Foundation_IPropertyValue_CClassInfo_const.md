# DirectUI::MetadataAPI::GetClassInfoFromOtherTypeBox(Windows::Foundation::IPropertyValue *,CClassInfo const * *)

- ea: `0x1800d0c0c`
- end: `0x1800d0fbd`
- name: `?GetClassInfoFromOtherTypeBox@MetadataAPI@DirectUI@@CAJPEAUIPropertyValue@Foundation@Windows@@PEAPEBVCClassInfo@@@Z`
- size: `945`
- prototype: `HRESULT __fastcall(Windows::Foundation::IPropertyValue *pValue, const CClassInfo **ppType)`
- caller_count: `3`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cea98`
- `0x1800f3114`
- `0x1801e67c4`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x1800ab600`
- `0x1800adbb0`
- `0x1800d0c0c`
- `0x1800d1f5c`
- `0x1800fe130`
- `0x180100978`
- `0x18017ffdc`
- `0x1801e9520`
- `0x18021e4e0`
- `0x1804c7a1c`
- `0x180598bc0`
- `0x1806877a8`
- `0x180687890`
- `0x1806b2e84`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0cfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0cfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0e30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0e30`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d0f03`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d0f03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d0c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d0c9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0da8`
- `api-ms-win-ro-typeresolution-l1-1-0!RoParseTypeName` at `0x1800d0c65`
- `api-ms-win-ro-typeresolution-l1-1-0!RoParseTypeName` at `0x1800d0c65`

## pseudocode

```c
__int64 __fastcall DirectUI::MetadataAPI::GetClassInfoFromOtherTypeBox(
        Windows::Foundation::IPropertyValue *pValue,
        const CClassInfo **ppType)
{
  Windows::Foundation::IPropertyValue_vtbl *v3; // rax
  HRESULT v4; // eax
  unsigned int v5; // ebx
  HSTRING v6; // rcx
  int Storage; // eax
  const CClassInfo *BuiltinClassInfoByFullName; // rax
  HRESULT v9; // ecx
  DirectUI::DynamicMetadataStorage *Instance; // r14
  std::pair<xstring_ptr,CClassInfo const *> *Myfirst; // rbx
  unsigned __int64 v12; // rdi
  DesignerMode v13; // ecx
  HRESULT v14; // edi
  HSTRING__ **v15; // rax
  HRESULT v17; // eax
  __int64 i; // rdi
  DirectUI::DynamicMetadataStorage *v19; // rax
  std::pair<xstring_ptr,CClassInfo const *> *Ptr; // rbx
  HRESULT v21; // eax
  xstring_ptr pstrAssemblyName; // [rsp+20h] [rbp-30h] BYREF
  HSTRING__ *hRuntimeClassName; // [rsp+28h] [rbp-28h] BYREF
  std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<xstring_ptr,CClassInfo const *> > > > result; // [rsp+30h] [rbp-20h] BYREF
  xstring_ptr_view strTypeFullName; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-10h] BYREF
  int v27; // [rsp+48h] [rbp-8h]
  unsigned int nPartsCount; // [rsp+90h] [rbp+40h] BYREF
  xstring_ptr length; // [rsp+98h] [rbp+48h] BYREF
  xstring_ptr key; // [rsp+A0h] [rbp+50h] BYREF
  HSTRING__ **phTypeNameParts; // [rsp+A8h] [rbp+58h] BYREF

  *ppType = 0;
  v3 = pValue->__vftable;
  hRuntimeClassName = 0;
  nPartsCount = 0;
  phTypeNameParts = 0;
  v4 = v3->GetRuntimeClassName(pValue, &hRuntimeClassName);
  v5 = v4;
  if ( v4 < 0 || (v4 = RoParseTypeName(hRuntimeClassName, &nPartsCount, &phTypeNameParts), v5 = v4, v4 < 0) )
  {
    OnFailure_2990_(v4);
    goto $Cleanup_405;
  }
  if ( nPartsCount != 2 )
  {
    *ppType = DirectUI::MetadataAPI::GetClassInfoByIndex(Object);
    goto $Cleanup_405;
  }
  LODWORD(length.m_encodedStorage.Storage) = 0;
  v6 = phTypeNameParts[1];
  strTypeFullName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  StringRawBuffer = WindowsGetStringRawBuffer(v6, (UINT32 *)&length);
  Storage = (int)length.m_encodedStorage.Storage;
  if ( LODWORD(length.m_encodedStorage.Storage) > 0x3FFFFFFF )
  {
    pstrAssemblyName.m_encodedStorage.Storage = 0;
    LODWORD(key.m_encodedStorage.Storage) = 0;
    TraceForFailFast(-2147418113);
    OnNewFailureEncountered(-2147418113, 0, 0);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&pstrAssemblyName, (unsigned int *)&key);
    RoFailFastWithErrorContextInternal2(
      -2147418113,
      key.m_encodedStorage.RuntimeStringHandleMarker,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)pstrAssemblyName.m_encodedStorage.Storage);
    Storage = (int)length.m_encodedStorage.Storage;
  }
  v27 = Storage & 0x3FFFFFFF | 0x40000000;
  if ( ((__int64)strTypeFullName.m_encodedStorage.Storage & 1) != 0 )
    WindowsDeleteString((HSTRING)(strTypeFullName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
  strTypeFullName.m_encodedStorage.Storage = (const xstring_ptr_storage *)&StringRawBuffer;
  BuiltinClassInfoByFullName = DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(&strTypeFullName);
  *ppType = BuiltinClassInfoByFullName;
  if ( !BuiltinClassInfoByFullName )
  {
    EnterCriticalSection(&g_csStatic);
    Instance = DirectUI::DynamicMetadataStorage::GetInstance();
    Myfirst = Instance->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Myfirst;
    v12 = Instance->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast - Myfirst;
    while ( (__int64)v12 > 0 )
    {
      if ( xstring_ptr_view::Compare(&Myfirst[v12 >> 1].first, &strTypeFullName, xstrCompareCaseSensitive) < 0 )
      {
        Myfirst += (v12 >> 1) + 1;
        v12 += -1LL - (v12 >> 1);
      }
      else
      {
        v12 >>= 1;
      }
    }
    if ( Myfirst == Instance->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast
      || xstring_ptr_view::Compare(&strTypeFullName, &Myfirst->first, xstrCompareCaseSensitive) < 0 )
    {
      Myfirst = Instance->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast;
    }
    if ( Myfirst != DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast )
    {
      v14 = 0;
      *ppType = Myfirst->second;
LABEL_17:
      LeaveCriticalSection(&g_csStatic);
      goto LABEL_18;
    }
    LOBYTE(v13) = 1;
    if ( DesignerInterop::GetDesignerMode(v13) )
    {
      key.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
      pstrAssemblyName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
      length.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
      v21 = xstring_ptr_view::Promote(&strTypeFullName, &length);
      v14 = v21;
      if ( v21 < 0 )
      {
        OnFailure_2990_(v21);
        xstring_ptr::~xstring_ptr(&length);
        xstring_ptr::~xstring_ptr(&pstrAssemblyName);
        xstring_ptr::~xstring_ptr(&key);
        goto LABEL_29;
      }
      if ( TypeNameHelper::ParseAssemblyQualifiedTypeName(&length, &key, &pstrAssemblyName) >= 0 )
      {
        v19 = DirectUI::DynamicMetadataStorage::GetInstance();
        Ptr = containers::detail::vector_tree<containers::detail::map_traits<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>,0>>::find(
                &v19->m_customTypesByNameCache,
                &result,
                &key)->_Ptr;
        if ( Ptr != DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast )
        {
          *ppType = Ptr->second;
          xstring_ptr::~xstring_ptr(&length);
          xstring_ptr::~xstring_ptr(&pstrAssemblyName);
          xstring_ptr::~xstring_ptr(&key);
          goto LABEL_17;
        }
      }
      xstring_ptr::~xstring_ptr(&length);
      xstring_ptr::~xstring_ptr(&pstrAssemblyName);
      xstring_ptr::~xstring_ptr(&key);
    }
    v17 = DirectUI::MetadataAPI::ImportClassInfoFromMetadataProvider(&strTypeFullName, ppType);
    v14 = v17;
    if ( v17 >= 0 )
      goto LABEL_17;
    OnFailure_2990_(v17);
LABEL_29:
    LeaveCriticalSection(&g_csStatic);
    v5 = v14;
    OnFailure_2990_(v14);
    goto LABEL_30;
  }
  v14 = 0;
LABEL_18:
  if ( !*ppType )
  {
    OnNewFailure_1208_(v9);
    v5 = -2147467259;
    goto LABEL_30;
  }
  v5 = v14;
  if ( v14 < 0 )
LABEL_30:
    OnFailure_2990_(v5);
$Cleanup_405:
  v15 = phTypeNameParts;
  if ( phTypeNameParts )
  {
    for ( i = 0; (unsigned int)i < nPartsCount; i = (unsigned int)(i + 1) )
    {
      WindowsDeleteString(v15[i]);
      v15 = phTypeNameParts;
    }
  }
  CoTaskMemFree(v15);
  WindowsDeleteString(hRuntimeClassName);
  return v5;
}

```

## disassembly

```asm
0x1800d0c0c  push    rbp
0x1800d0c0e  push    rbx
0x1800d0c0f  push    rsi
0x1800d0c10  push    rdi
0x1800d0c11  push    r13
0x1800d0c13  push    r14
0x1800d0c15  push    r15
0x1800d0c17  mov     rbp, rsp
0x1800d0c1a  sub     rsp, 50h
0x1800d0c1e  mov     qword ptr [ppType], 0
0x1800d0c25  mov     rsi, ppType
0x1800d0c28  mov     rax, [pValue]
0x1800d0c2b  lea     ppType, [rbp+hRuntimeClassName]
0x1800d0c2f  mov     [rbp+hRuntimeClassName], 0
0x1800d0c37  mov     [rbp+nPartsCount], 0
0x1800d0c3e  mov     [rbp+phTypeNameParts], 0
0x1800d0c46  mov     rax, [rax+20h]
0x1800d0c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0c4f  mov     ebx, eax
0x1800d0c51  test    eax, eax
0x1800d0c53  js      loc_1800D0DF8
0x1800d0c59  mov     pValue, [rbp+hRuntimeClassName]
0x1800d0c5d  lea     r8, [rbp+phTypeNameParts]
0x1800d0c61  lea     ppType, [rbp+nPartsCount]
0x1800d0c65  call    cs:__imp_RoParseTypeName
0x1800d0c6b  mov     ebx, eax
0x1800d0c6d  test    eax, eax
0x1800d0c6f  js      loc_1800D0FB1
0x1800d0c75  cmp     [rbp+nPartsCount], 2
0x1800d0c79  jnz     loc_1800D0F9F
0x1800d0c7f  mov     rax, [rbp+phTypeNameParts]
0x1800d0c83  lea     r13, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d0c8a  lea     ppType, [rbp+length]; length
0x1800d0c8e  mov     dword ptr [rbp+length], 0
0x1800d0c95  mov     pValue, [rax+8]; string
0x1800d0c99  mov     qword ptr [rbp+strTypeFullName.m_encodedStorage.___u0], r13
0x1800d0c9d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d0ca3  mov     [rbp+var_10], rax
0x1800d0ca7  mov     edi, 3FFFFFFFh
0x1800d0cac  mov     eax, dword ptr [rbp+length]
0x1800d0caf  cmp     eax, edi
0x1800d0cb1  ja      loc_1800D0EC6
0x1800d0cb7  mov     pValue, qword ptr [rbp+strTypeFullName.m_encodedStorage.___u0]
0x1800d0cbb  and     eax, edi
0x1800d0cbd  bts     eax, 1Eh
0x1800d0cc1  mov     [rbp+var_8], eax
0x1800d0cc4  test    cl, 1
0x1800d0cc7  jz      short loc_1800D0CD3
0x1800d0cc9  and     pValue, 0FFFFFFFFFFFFFFFEh; string
0x1800d0ccd  call    cs:__imp_WindowsDeleteString
0x1800d0cd3  lea     rax, [rbp+var_10]
0x1800d0cd7  lea     pValue, [rbp+strTypeFullName]; strTypeFullName
0x1800d0cdb  mov     qword ptr [rbp+strTypeFullName.m_encodedStorage.___u0], rax
0x1800d0cdf  call    ?TryGetBuiltinClassInfoByFullName@MetadataAPI@DirectUI@@CAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(xstring_ptr_view const &)
0x1800d0ce4  mov     [rsi], rax
0x1800d0ce7  test    rax, rax
0x1800d0cea  jnz     loc_1800D0E4B
0x1800d0cf0  lea     r15, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csStatic
0x1800d0cf7  mov     pValue, r15; lpCriticalSection
0x1800d0cfa  call    cs:__imp_EnterCriticalSection
0x1800d0d00  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1800d0d05  mov     r14, rax
0x1800d0d08  mov     rbx, [rax+30h]
0x1800d0d0c  mov     rdi, [rax+38h]
0x1800d0d10  sub     rdi, rbx
0x1800d0d13  sar     rdi, 4
0x1800d0d17  test    rdi, rdi
0x1800d0d1a  jle     short loc_1800D0D59
0x1800d0d1c  mov     r15, rdi
0x1800d0d1f  lea     ppType, [rbp+strTypeFullName]; other
0x1800d0d23  shr     r15, 1
0x1800d0d26  xor     r8d, r8d; eCompareBehavior
0x1800d0d29  mov     r13, r15
0x1800d0d2c  shl     r13, 4
0x1800d0d30  add     r13, rbx
0x1800d0d33  mov     pValue, r13; this
0x1800d0d36  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1800d0d3b  test    eax, eax
0x1800d0d3d  js      loc_1800D0DC9
0x1800d0d43  mov     rdi, r15
0x1800d0d46  test    rdi, rdi
0x1800d0d49  jg      short loc_1800D0D1C
0x1800d0d4b  lea     r15, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csStatic
0x1800d0d52  lea     r13, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d0d59  cmp     rbx, [r14+38h]
0x1800d0d5d  jnz     short loc_1800D0DDC
0x1800d0d5f  mov     rbx, [r14+38h]
0x1800d0d63  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1800d0d68  cmp     rbx, [rax+38h]
0x1800d0d6c  jz      loc_1800D0E01
0x1800d0d72  mov     rax, [rbx+8]
0x1800d0d76  xor     edi, edi
0x1800d0d78  mov     [rsi], rax
0x1800d0d7b  mov     pValue, r15; lpCriticalSection
0x1800d0d7e  call    cs:__imp_LeaveCriticalSection
0x1800d0d84  cmp     qword ptr [rsi], 0
0x1800d0d88  jz      loc_1800D0F90
0x1800d0d8e  mov     ebx, edi
0x1800d0d90  test    edi, edi
0x1800d0d92  js      loc_1800D0E3F
0x1800d0d98  mov     rax, [rbp+phTypeNameParts]
0x1800d0d9c  test    rax, rax
0x1800d0d9f  jnz     loc_1800D0E52
0x1800d0da5  mov     pValue, rax; pv
0x1800d0da8  call    cs:__imp_CoTaskMemFree
0x1800d0dae  mov     pValue, [rbp+hRuntimeClassName]; string
0x1800d0db2  call    cs:__imp_WindowsDeleteString
0x1800d0db8  mov     eax, ebx
0x1800d0dba  add     rsp, 50h
0x1800d0dbe  pop     r15
0x1800d0dc0  pop     r14
0x1800d0dc2  pop     r13
0x1800d0dc4  pop     rdi
0x1800d0dc5  pop     rsi
0x1800d0dc6  pop     rbx
0x1800d0dc7  pop     rbp
0x1800d0dc8  retn
0x1800d0dc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d0dcd  lea     rbx, [r13+10h]
0x1800d0dd1  sub     rax, r15
0x1800d0dd4  add     rdi, rax
0x1800d0dd7  jmp     loc_1800D0D46
0x1800d0ddc  xor     r8d, r8d; eCompareBehavior
0x1800d0ddf  lea     pValue, [rbp+strTypeFullName]; this
0x1800d0de3  mov     ppType, rbx; other
0x1800d0de6  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1800d0deb  test    eax, eax
0x1800d0ded  jns     loc_1800D0D63
0x1800d0df3  jmp     loc_1800D0D5F
0x1800d0df8  mov     ecx, eax; failedFrameHR
0x1800d0dfa  call    OnFailure_2990_
0x1800d0dff  jmp     short $Cleanup_405
0x1800d0e01  mov     cl, 1; mode
0x1800d0e03  call    ?GetDesignerMode@DesignerInterop@@SA_NW4DesignerMode@@@Z; DesignerInterop::GetDesignerMode(DesignerMode)
0x1800d0e08  test    al, al
0x1800d0e0a  jnz     loc_1800D0F11
0x1800d0e10  mov     ppType, rsi; ppType
0x1800d0e13  lea     pValue, [rbp+strTypeFullName]; strTypeFullName
0x1800d0e17  call    ?ImportClassInfoFromMetadataProvider@MetadataAPI@DirectUI@@CAJAEBVxstring_ptr_view@@PEAPEBVCClassInfo@@@Z; DirectUI::MetadataAPI::ImportClassInfoFromMetadataProvider(xstring_ptr_view const &,CClassInfo const * *)
0x1800d0e1c  mov     edi, eax
0x1800d0e1e  test    eax, eax
0x1800d0e20  jns     loc_1800D0D7B
0x1800d0e26  mov     ecx, eax; failedFrameHR
0x1800d0e28  call    OnFailure_2990_
0x1800d0e2d  mov     pValue, r15; lpCriticalSection
0x1800d0e30  call    cs:__imp_LeaveCriticalSection
0x1800d0e36  mov     ecx, edi; failedFrameHR
0x1800d0e38  mov     ebx, edi
0x1800d0e3a  call    OnFailure_2990_
0x1800d0e3f  mov     ecx, ebx; failedFrameHR
0x1800d0e41  call    OnFailure_2990_
0x1800d0e46  jmp     $Cleanup_405
0x1800d0e4b  xor     edi, edi
0x1800d0e4d  jmp     loc_1800D0D84
0x1800d0e52  xor     edi, edi
0x1800d0e54  cmp     [rbp+nPartsCount], edi
0x1800d0e57  jbe     loc_1800D0DA5
0x1800d0e5d  mov     pValue, [rax+rdi*8]; string
0x1800d0e61  call    cs:__imp_WindowsDeleteString
0x1800d0e67  mov     rax, [rbp+phTypeNameParts]
0x1800d0e6b  inc     edi
0x1800d0e6d  cmp     edi, [rbp+nPartsCount]
0x1800d0e70  jb      short loc_1800D0E5D
0x1800d0e72  jmp     loc_1800D0DA5
0x1800d0e77  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1800d0e7c  lea     r8, [rbp+key]; key
0x1800d0e80  lea     ppType, [rbp+result]; result
0x1800d0e84  lea     pValue, [rax+30h]; this
0x1800d0e88  call    ?find@?$vector_tree@U?$map_traits@Vxstring_ptr@@PEBVCClassInfo@@U?$less@X@std@@V?$allocator@U?$pair@Vxstring_ptr@@PEBVCClassInfo@@@std@@@4@$0A@@detail@containers@@@detail@containers@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@Vxstring_ptr@@PEBVCClassInfo@@@std@@@std@@@std@@@std@@AEBVxstring_ptr@@@Z; containers::detail::vector_tree<containers::detail::map_traits<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>,0>>::find(xstring_ptr const &)
0x1800d0e8d  mov     rbx, [rax]
0x1800d0e90  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1800d0e95  cmp     rbx, [rax+38h]
0x1800d0e99  jz      loc_1800D0F49
0x1800d0e9f  mov     rax, [rbx+8]
0x1800d0ea3  lea     pValue, [rbp+length]; this
0x1800d0ea7  mov     [rsi], rax
0x1800d0eaa  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0eaf  lea     pValue, [rbp+pstrAssemblyName]; this
0x1800d0eb3  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0eb8  lea     pValue, [rbp+key]; this
0x1800d0ebc  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0ec1  jmp     loc_1800D0D7B
0x1800d0ec6  mov     ebx, 8000FFFFh
0x1800d0ecb  mov     qword ptr [rbp+pstrAssemblyName.m_encodedStorage.___u0], 0
0x1800d0ed3  mov     ecx, ebx; errorCode
0x1800d0ed5  mov     dword ptr [rbp+key.m_encodedStorage.___u0], 0
0x1800d0edc  call    TraceForFailFast
0x1800d0ee1  xor     r8d, r8d; contextRecord
0x1800d0ee4  xor     edx, edx; directCallerReturnAddress
0x1800d0ee6  mov     ecx, ebx; failedFrameHR
0x1800d0ee8  call    OnNewFailureEncountered
0x1800d0eed  lea     ppType, [rbp+key]; pcStowedExceptions
0x1800d0ef1  lea     pValue, [rbp+pstrAssemblyName]; pppStowedExceptions
0x1800d0ef5  call    GetStowedExceptionsForFailFast
0x1800d0efa  mov     r8, qword ptr [rbp+pstrAssemblyName.m_encodedStorage.___u0]
0x1800d0efe  mov     ecx, ebx
0x1800d0f00  mov     edx, dword ptr [rbp+key.m_encodedStorage.___u0]
0x1800d0f03  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800d0f09  mov     eax, dword ptr [rbp+length]
0x1800d0f0c  jmp     loc_1800D0CB7
0x1800d0f11  lea     ppType, [rbp+length]; pstrPromoted
0x1800d0f15  mov     qword ptr [rbp+key.m_encodedStorage.___u0], r13
0x1800d0f19  lea     pValue, [rbp+strTypeFullName]; this
0x1800d0f1d  mov     qword ptr [rbp+pstrAssemblyName.m_encodedStorage.___u0], r13
0x1800d0f21  mov     [rbp+length], r13
0x1800d0f25  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxstring_ptr@@@Z; xstring_ptr_view::Promote(xstring_ptr *)
0x1800d0f2a  mov     edi, eax
0x1800d0f2c  test    eax, eax
0x1800d0f2e  js      short loc_1800D0F69
0x1800d0f30  lea     r8, [rbp+pstrAssemblyName]; pstrAssemblyName
0x1800d0f34  lea     ppType, [rbp+key]; pstrTypeName
0x1800d0f38  lea     pValue, [rbp+length]; strAssemblyQualifiedTypeName
0x1800d0f3c  call    ?ParseAssemblyQualifiedTypeName@TypeNameHelper@@SAJAEBVxstring_ptr@@PEAV2@1@Z; TypeNameHelper::ParseAssemblyQualifiedTypeName(xstring_ptr const &,xstring_ptr *,xstring_ptr *)
0x1800d0f41  test    eax, eax
0x1800d0f43  jns     loc_1800D0E77
0x1800d0f49  lea     pValue, [rbp+length]; this
0x1800d0f4d  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f52  lea     pValue, [rbp+pstrAssemblyName]; this
0x1800d0f56  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f5b  lea     pValue, [rbp+key]; this
0x1800d0f5f  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f64  jmp     loc_1800D0E10
0x1800d0f69  mov     ecx, edi; failedFrameHR
0x1800d0f6b  call    OnFailure_2990_
0x1800d0f70  lea     pValue, [rbp+length]; this
0x1800d0f74  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f79  lea     pValue, [rbp+pstrAssemblyName]; this
0x1800d0f7d  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f82  lea     pValue, [rbp+key]; this
0x1800d0f86  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d0f8b  jmp     loc_1800D0E2D
0x1800d0f90  call    OnNewFailure_1208_
0x1800d0f95  mov     ebx, 80004005h
0x1800d0f9a  jmp     loc_1800D0E3F
0x1800d0f9f  mov     ecx, 28h ; '('; eTypeIndex
0x1800d0fa4  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1800d0fa9  mov     [rsi], rax
0x1800d0fac  jmp     $Cleanup_405
0x1800d0fb1  mov     ecx, eax; failedFrameHR
0x1800d0fb3  call    OnFailure_2990_
0x1800d0fb8  jmp     $Cleanup_405
```
