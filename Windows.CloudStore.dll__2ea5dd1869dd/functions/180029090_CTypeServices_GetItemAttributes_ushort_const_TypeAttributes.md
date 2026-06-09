# CTypeServices::GetItemAttributes(ushort const *,TypeAttributes *)

- ea: `0x180029090`
- end: `0x1800294a6`
- name: `?GetItemAttributes@CTypeServices@@UEAAJPEBGPEAUTypeAttributes@@@Z`
- size: `1046`
- prototype: `int(CTypeServices *__hidden this, const unsigned __int16 *, struct TypeAttributes *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180016c60`
- `0x180019720`
- `0x1800204b0`
- `0x1800205a0`
- `0x1800219e0`
- `0x180022ab0`
- `0x180022c3c`
- `0x180028128`
- `0x180028640`
- `0x180028ee0`
- `0x180029090`
- `0x1800297b8`
- `0x18002c020`
- `0x1800901dc`
- `0x1800c8458`
- `0x1800d1d08`
- `0x1800d1d50`
- `0x1800e2e9c`
- `0x1801201a0`
- `0x180120668`
- `0x18012353c`
- `0x1801235a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029127`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800293dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029127`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800293dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002913e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002913e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800291a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800291a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002918a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002934a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029405`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002918a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002934a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029405`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029439`

## string_xrefs

- `0x1800293ee`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x180029422`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CTypeServices::GetItemAttributes(
        CTypeServices *this,
        const unsigned __int16 *a2,
        struct TypeAttributes *a3)
{
  unsigned __int64 v6; // rdx
  HRESULT v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  PCWSTR StringRawBuffer; // r8
  __int64 SchemaOfTypeNameInternal; // rax
  const char *v12; // rdx
  const char *v13; // r9
  HSTRING v14; // rcx
  __int64 AttributeDataBy; // rax
  const char *v16; // r9
  HSTRING v17; // rcx
  int v19; // [rsp+20h] [rbp-188h]
  int v20; // [rsp+20h] [rbp-188h]
  int v21; // [rsp+30h] [rbp-178h] BYREF
  HSTRING v22; // [rsp+38h] [rbp-170h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-168h] BYREF
  HSTRING v24[2]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v25[24]; // [rsp+58h] [rbp-150h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-138h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-130h] BYREF
  HSTRING string; // [rsp+90h] [rbp-118h] BYREF
  _BYTE v29[64]; // [rsp+A0h] [rbp-108h] BYREF
  _QWORD v30[15]; // [rsp+E0h] [rbp-C8h] BYREF
  _BYTE v31[8]; // [rsp+158h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  *(_OWORD *)a3 = 0;
  WindowsDeleteString(0);
  v23 = 0;
  v21 = 0;
  WindowsDeleteString(0);
  v24[0] = 0;
  WindowsDeleteString(0);
  v22 = 0;
  string = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0xFFFFFFFF || (int)v6 + 1 < (unsigned int)v6 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v7 = WindowsCreateStringReference(a2, v6, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v8 = CTypeServices::ParseDataStoreId(
         (CTypeServices *)((char *)this - 16),
         string,
         (enum Windows::Internal::Storage::Cloud::PartitionKind *)&v21,
         &v22,
         &v23,
         v24);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x476,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
      (const char *)(unsigned int)v8,
      v19);
    WindowsDeleteString(v24[0]);
    WindowsDeleteString(v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40D,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
      (const char *)v9,
      v20);
    WindowsDeleteString(v23);
    return v9;
  }
  else
  {
    WindowsDeleteString(v24[0]);
    WindowsDeleteString(v22);
    StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
    SchemaOfTypeNameInternal = CTypeServices::GetSchemaOfTypeNameInternal((char *)this - 16, v25, StringRawBuffer);
    bond::StructDef::StructDef(
      (bond::StructDef *)v29,
      (const struct bond::StructDef *)(**(_QWORD **)SchemaOfTypeNameInternal
                                     + 216LL * *(unsigned __int16 *)(*(_QWORD *)(SchemaOfTypeNameInternal + 8) + 4LL)));
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v26);
    *(_OWORD *)v24 = 0;
    v12 = *(const char **)(GetAttributeDataById<enum CloudDataStructAttribute,18>(1) + 8);
    std::string::string(&hstringHeader, v12);
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
      v30,
      &v22,
      &hstringHeader);
    std::string::_Tidy_deallocate(&hstringHeader);
    if ( v22 == (HSTRING)v30[0] )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudattributes.cpp",
        v13);
    v14 = v22 + 16;
    if ( !*((_QWORD *)v22 + 10) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudattributes.cpp",
        v13);
    if ( *((_QWORD *)v22 + 11) > 0xFu )
      v14 = *(HSTRING *)v14;
    LODWORD(v24[0]) = MapValueInTypedList<enum ScopeValue>(v14);
    BYTE4(v24[0]) = GetMultipleInstances(v29);
    LODWORD(v24[1]) = GetConflictPolicy(v29);
    AttributeDataBy = GetAttributeDataById<enum CloudDataStructAttribute,18>(8);
    std::string::string(&hstringHeader, *(const char **)(AttributeDataBy + 8));
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
      v30,
      &v22,
      &hstringHeader);
    std::string::_Tidy_deallocate(&hstringHeader);
    if ( v22 == (HSTRING)v30[0] )
    {
      if ( __TSS0__7____GetCloudAttributeValueStringHelper_W4CloudDataStructAttribute___0BC___YAAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBUMetadata_bond__W4CloudDataStructAttribute__W4GetAttributeOptions__AEAY0BC___CBU__AttributeData_W4CloudDataStructAttribute_____Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 268LL) )
      {
        Init_thread_header(&__TSS0__7____GetCloudAttributeValueStringHelper_W4CloudDataStructAttribute___0BC___YAAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBUMetadata_bond__W4CloudDataStructAttribute__W4GetAttributeOptions__AEAY0BC___CBU__AttributeData_W4CloudDataStructAttribute_____Z_4HA);
        if ( __TSS0__7____GetCloudAttributeValueStringHelper_W4CloudDataStructAttribute___0BC___YAAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBUMetadata_bond__W4CloudDataStructAttribute__W4GetAttributeOptions__AEAY0BC___CBU__AttributeData_W4CloudDataStructAttribute_____Z_4HA == -1 )
        {
          `GetCloudAttributeValueStringHelper<enum CloudDataStructAttribute,18>'::`8'::s_empty = 0;
          xmmword_1802A36E0 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(`GetCloudAttributeValueStringHelper<enum CloudDataStructAttribute,18>'::`8'::s_empty) = 0;
          atexit(GetCloudAttributeValueStringHelper_enum_CloudDataStructAttribute_18__::_8_::_dynamic_atexit_destructor_for__s_empty__);
          Init_thread_footer(&__TSS0__7____GetCloudAttributeValueStringHelper_W4CloudDataStructAttribute___0BC___YAAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBUMetadata_bond__W4CloudDataStructAttribute__W4GetAttributeOptions__AEAY0BC___CBU__AttributeData_W4CloudDataStructAttribute_____Z_4HA);
        }
      }
      v17 = (HSTRING)&`GetCloudAttributeValueStringHelper<enum CloudDataStructAttribute,18>'::`8'::s_empty;
    }
    else
    {
      v17 = v22 + 16;
      if ( !*((_QWORD *)v22 + 10) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudattributes.cpp",
          v16);
    }
    if ( *((_QWORD *)v17 + 3) > 0xFu )
      v17 = *(HSTRING *)v17;
    HIDWORD(v24[1]) = MapValueInTypedList<enum UploadPolicyValue>(v17);
    *(_OWORD *)a3 = *(_OWORD *)v24;
    std::vector<bond::FieldDef>::_Tidy(v32);
    bond::nullable<bond::TypeDef,void>::reset(v31);
    bond::Metadata::~Metadata((bond::Metadata *)v29);
    WindowsDeleteString(v23);
    return 0;
  }
}

```

## disassembly

```asm
0x180029090  mov     [rsp+arg_18], rbx
0x180029095  push    rsi
0x180029096  push    rdi
0x180029097  push    r14
0x180029099  sub     rsp, 190h
0x1800290a0  mov     rax, cs:__security_cookie
0x1800290a7  xor     rax, rsp
0x1800290aa  mov     [rsp+1A8h+var_28], rax
0x1800290b2  mov     rsi, r8
0x1800290b5  mov     rbx, rdx
0x1800290b8  mov     rdi, rcx
0x1800290bb  xorps   xmm0, xmm0
0x1800290be  movups  xmmword ptr [r8], xmm0
0x1800290c2  xor     ecx, ecx; string
0x1800290c4  call    cs:__imp_WindowsDeleteString
0x1800290ca  xor     r14d, r14d
0x1800290cd  mov     [rsp+1A8h+var_168], r14
0x1800290d2  mov     [rsp+1A8h+var_178], r14d
0x1800290d7  xor     ecx, ecx; string
0x1800290d9  call    cs:__imp_WindowsDeleteString
0x1800290df  mov     [rsp+1A8h+var_160], r14
0x1800290e4  xor     ecx, ecx; string
0x1800290e6  call    cs:__imp_WindowsDeleteString
0x1800290ec  mov     [rsp+1A8h+var_170], r14
0x1800290f1  mov     [rsp+1A8h+string], r14
0x1800290f9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800290fd  inc     rdx; length
0x180029100  cmp     [rbx+rdx*2], r14w
0x180029105  jnz     short loc_1800290FD
0x180029107  mov     eax, 0FFFFFFFFh
0x18002910c  cmp     rdx, rax
0x18002910f  ja      short loc_180029118
0x180029111  lea     eax, [rdx+1]
0x180029114  cmp     eax, edx
0x180029116  jnb     short loc_18002912E
0x180029118  xor     r9d, r9d; lpArguments
0x18002911b  xor     r8d, r8d; nNumberOfArguments
0x18002911e  lea     edx, [r9+1]; dwExceptionFlags
0x180029122  mov     ecx, 80070216h; dwExceptionCode
0x180029127  call    cs:__imp_RaiseException
0x18002912d  int     3; Trap to Debugger
0x18002912e  lea     r9, [rsp+1A8h+string]; string
0x180029136  lea     r8, [rsp+1A8h+hstringHeader]; hstringHeader
0x18002913b  mov     rcx, rbx; sourceString
0x18002913e  call    cs:__imp_WindowsCreateStringReference
0x180029144  test    eax, eax
0x180029146  js      loc_1800293D0
0x18002914c  lea     rax, [rsp+1A8h+var_160]
0x180029151  mov     [rsp+1A8h+var_180], rax; HSTRING *
0x180029156  lea     rax, [rsp+1A8h+var_168]
0x18002915b  mov     [rsp+1A8h+var_188], rax; int
0x180029160  lea     r9, [rsp+1A8h+var_170]; HSTRING *
0x180029165  lea     r8, [rsp+1A8h+var_178]; enum Windows::Internal::Storage::Cloud::PartitionKind *
0x18002916a  mov     rdx, [rsp+1A8h+string]; HSTRING
0x180029172  lea     rcx, [rdi-10h]; this
0x180029176  call    ?ParseDataStoreId@CTypeServices@@UEAAJPEAUHSTRING__@@PEAW4PartitionKind@Cloud@Storage@Internal@Windows@@PEAPEAU2@22@Z; CTypeServices::ParseDataStoreId(HSTRING__ *,Windows::Internal::Storage::Cloud::PartitionKind *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x18002917b  mov     ebx, eax
0x18002917d  test    eax, eax
0x18002917f  js      loc_1800293E3
0x180029185  mov     rcx, [rsp+1A8h+var_160]; string
0x18002918a  call    cs:__imp_WindowsDeleteString
0x180029190  nop
0x180029191  mov     rcx, [rsp+1A8h+var_170]; string
0x180029196  call    cs:__imp_WindowsDeleteString
0x18002919c  xor     edx, edx; length
0x18002919e  mov     rcx, [rsp+1A8h+var_168]; string
0x1800291a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800291a9  mov     r8, rax
0x1800291ac  lea     rdx, [rsp+1A8h+var_150]
0x1800291b1  lea     rcx, [rdi-10h]
0x1800291b5  call    ?GetSchemaOfTypeNameInternal@CTypeServices@@AEAA?BVRuntimeSchema@bond@@PEBG@Z; CTypeServices::GetSchemaOfTypeNameInternal(ushort const *)
0x1800291ba  nop
0x1800291bb  mov     rcx, [rax+8]
0x1800291bf  movzx   edx, word ptr [rcx+4]
0x1800291c3  imul    rdx, 0D8h
0x1800291ca  mov     rax, [rax]
0x1800291cd  add     rdx, [rax]; struct bond::StructDef *
0x1800291d0  lea     rcx, [rsp+1A8h+var_108]; this
0x1800291d8  call    ??0StructDef@bond@@QEAA@AEBU01@@Z; bond::StructDef::StructDef(bond::StructDef const &)
0x1800291dd  nop
0x1800291de  lea     rcx, [rsp+1A8h+var_138]; this
0x1800291e3  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800291e8  xorps   xmm0, xmm0
0x1800291eb  movups  xmmword ptr [rsp+1A8h+var_160], xmm0
0x1800291f0  mov     ecx, 1
0x1800291f5  call    ??$GetAttributeDataById@W4CloudDataStructAttribute@@$0BC@@@YAAEBU?$AttributeData@W4CloudDataStructAttribute@@@@W4CloudDataStructAttribute@@AEAY0BC@$$CBU0@@Z; GetAttributeDataById<CloudDataStructAttribute,18>(CloudDataStructAttribute,AttributeData<CloudDataStructAttribute> const (&)[18])
0x1800291fa  mov     rdx, [rax+8]
0x1800291fe  lea     rcx, [rsp+1A8h+hstringHeader]
0x180029203  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180029208  lea     r8, [rsp+1A8h+hstringHeader]
0x18002920d  lea     rdx, [rsp+1A8h+var_170]
0x180029212  lea     rcx, [rsp+1A8h+var_C8]
0x18002921a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x18002921f  lea     rcx, [rsp+1A8h+hstringHeader]; void *
0x180029224  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180029229  mov     rax, [rsp+1A8h+var_170]
0x18002922e  cmp     rax, [rsp+1A8h+var_C8]
0x180029236  jz      loc_180029376
0x18002923c  lea     rcx, [rax+40h]
0x180029240  mov     rax, [rsp+1A8h]
0x180029248  cmp     [rcx+10h], r14
0x18002924c  jz      loc_1800293BB
0x180029252  cmp     qword ptr [rcx+18h], 0Fh
0x180029257  jbe     short loc_18002925C
0x180029259  mov     rcx, [rcx]
0x18002925c  call    ??$MapValueInTypedList@W4ScopeValue@@@@YA?AW4ScopeValue@@PEBDPEBU?$MapEntry@W4ScopeValue@@@@_K@Z; MapValueInTypedList<ScopeValue>(char const *,MapEntry<ScopeValue> const *,unsigned __int64)
0x180029261  mov     dword ptr [rsp+1A8h+var_160], eax
0x180029265  lea     rcx, [rsp+1A8h+var_108]
0x18002926d  call    ?GetMultipleInstances@@YAEAEBUMetadata@bond@@W4GetAttributeOptions@@@Z; GetMultipleInstances(bond::Metadata const &,GetAttributeOptions)
0x180029272  mov     byte ptr [rsp+1A8h+var_160+4], al
0x180029276  lea     rcx, [rsp+1A8h+var_108]
0x18002927e  call    ?GetConflictPolicy@@YA?AW4ConflictPolicyValue@@AEBUMetadata@bond@@W4GetAttributeOptions@@@Z; GetConflictPolicy(bond::Metadata const &,GetAttributeOptions)
0x180029283  mov     dword ptr [rsp+1A8h+var_160+8], eax
0x180029287  mov     ecx, 8
0x18002928c  call    ??$GetAttributeDataById@W4CloudDataStructAttribute@@$0BC@@@YAAEBU?$AttributeData@W4CloudDataStructAttribute@@@@W4CloudDataStructAttribute@@AEAY0BC@$$CBU0@@Z; GetAttributeDataById<CloudDataStructAttribute,18>(CloudDataStructAttribute,AttributeData<CloudDataStructAttribute> const (&)[18])
0x180029291  mov     rdx, [rax+8]
0x180029295  lea     rcx, [rsp+1A8h+hstringHeader]
0x18002929a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002929f  lea     r8, [rsp+1A8h+hstringHeader]
0x1800292a4  lea     rdx, [rsp+1A8h+var_170]
0x1800292a9  lea     rcx, [rsp+1A8h+var_C8]
0x1800292b1  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x1800292b6  lea     rcx, [rsp+1A8h+hstringHeader]; void *
0x1800292bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800292c0  mov     rax, [rsp+1A8h+var_170]
0x1800292c5  cmp     rax, [rsp+1A8h+var_C8]
0x1800292cd  jnz     loc_180029390
0x1800292d3  mov     ecx, cs:_tls_index
0x1800292d9  mov     rax, gs:58h
0x1800292e2  mov     edx, 10Ch
0x1800292e7  mov     rax, [rax+rcx*8]
0x1800292eb  mov     ecx, [rdx+rax]
0x1800292ee  cmp     cs:?$TSS0@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4HA, ecx
0x1800292f4  jg      loc_180029446
0x1800292fa  lea     rcx, ?s_empty@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4V12@B; std::string const `GetCloudAttributeValueStringHelper<CloudDataStructAttribute,18>(bond::Metadata const &,CloudDataStructAttribute,GetAttributeOptions,AttributeData<CloudDataStructAttribute> const (&)[18])'::`8'::s_empty
0x180029301  cmp     qword ptr [rcx+18h], 0Fh
0x180029306  jbe     short loc_18002930B
0x180029308  mov     rcx, [rcx]
0x18002930b  call    ??$MapValueInTypedList@W4UploadPolicyValue@@@@YA?AW4UploadPolicyValue@@PEBDPEBU?$MapEntry@W4UploadPolicyValue@@@@_K@Z; MapValueInTypedList<UploadPolicyValue>(char const *,MapEntry<UploadPolicyValue> const *,unsigned __int64)
0x180029310  mov     dword ptr [rsp+1A8h+var_160+0Ch], eax
0x180029314  movups  xmm0, xmmword ptr [rsp+1A8h+var_160]
0x180029319  movdqu  xmmword ptr [rsi], xmm0
0x18002931d  lea     rcx, [rsp+1A8h+var_48]
0x180029325  call    ?_Tidy@?$vector@UFieldDef@bond@@V?$allocator@UFieldDef@bond@@@std@@@std@@AEAAXXZ; std::vector<bond::FieldDef>::_Tidy(void)
0x18002932a  lea     rcx, [rsp+1A8h+var_50]
0x180029332  call    ?reset@?$nullable@UTypeDef@bond@@X@bond@@QEAAXXZ; bond::nullable<bond::TypeDef,void>::reset(void)
0x180029337  lea     rcx, [rsp+1A8h+var_108]; this
0x18002933f  call    ??1Metadata@bond@@QEAA@XZ; bond::Metadata::~Metadata(void)
0x180029344  nop
0x180029345  mov     rcx, [rsp+1A8h+var_168]; string
0x18002934a  call    cs:__imp_WindowsDeleteString
0x180029350  xor     eax, eax
0x180029352  mov     rcx, [rsp+1A8h+var_28]
0x18002935a  xor     rcx, rsp; StackCookie
0x18002935d  call    __security_check_cookie
0x180029362  mov     rbx, [rsp+1A8h+arg_18]
0x18002936a  add     rsp, 190h
0x180029371  pop     r14
0x180029373  pop     rdi
0x180029374  pop     rsi
0x180029375  retn
0x180029376  mov     rcx, [rsp+1A8h]; this
0x18002937e  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180029385  mov     edx, 0D8h; void *
0x18002938a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180029390  lea     rcx, [rax+40h]
0x180029394  mov     rax, [rsp+1A8h]
0x18002939c  cmp     [rcx+10h], r14
0x1800293a0  jnz     loc_180029301
0x1800293a6  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800293ad  mov     edx, 0E4h; void *
0x1800293b2  mov     rcx, rax; this
0x1800293b5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800293bb  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800293c2  mov     edx, 0E4h; void *
0x1800293c7  mov     rcx, rax; this
0x1800293ca  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800293d0  xor     r9d, r9d; lpArguments
0x1800293d3  xor     r8d, r8d; nNumberOfArguments
0x1800293d6  lea     edx, [r9+1]; dwExceptionFlags
0x1800293da  mov     ecx, eax; dwExceptionCode
0x1800293dc  call    cs:__imp_RaiseException
0x1800293e2  int     3; Trap to Debugger
0x1800293e3  mov     rcx, [rsp+1A8h]; this
0x1800293eb  mov     r9d, ebx; char *
0x1800293ee  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800293f5  mov     edx, 476h; void *
0x1800293fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293ff  nop
0x180029400  mov     rcx, [rsp+1A8h+var_160]; string
0x180029405  call    cs:__imp_WindowsDeleteString
0x18002940b  nop
0x18002940c  mov     rcx, [rsp+1A8h+var_170]; string
0x180029411  call    cs:__imp_WindowsDeleteString
0x180029417  mov     rcx, [rsp+1A8h]; this
0x18002941f  mov     r9d, ebx; char *
0x180029422  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180029429  mov     edx, 40Dh; void *
0x18002942e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029433  nop
0x180029434  mov     rcx, [rsp+1A8h+var_168]; string
0x180029439  call    cs:__imp_WindowsDeleteString
0x18002943f  mov     eax, ebx
0x180029441  jmp     loc_180029352
0x180029446  lea     rcx, ?$TSS0@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4HA
0x18002944d  call    _Init_thread_header
0x180029452  cmp     cs:?$TSS0@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4HA, 0FFFFFFFFh
0x180029459  jnz     loc_1800292FA
0x18002945f  xorps   xmm0, xmm0
0x180029462  movups  cs:?s_empty@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4V12@B, xmm0; std::string const `GetCloudAttributeValueStringHelper<CloudDataStructAttribute,18>(bond::Metadata const &,CloudDataStructAttribute,GetAttributeOptions,AttributeData<CloudDataStructAttribute> const (&)[18])'::`8'::s_empty
0x180029469  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180029471  movdqu  cs:xmmword_1802A36E0, xmm1
0x180029479  mov     byte ptr cs:?s_empty@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4V12@B, r14b; std::string const `GetCloudAttributeValueStringHelper<CloudDataStructAttribute,18>(bond::Metadata const &,CloudDataStructAttribute,GetAttributeOptions,AttributeData<CloudDataStructAttribute> const (&)[18])'::`8'::s_empty
0x180029480  lea     rcx, _GetCloudAttributeValueStringHelper_enum_CloudDataStructAttribute_18_____8____dynamic_atexit_destructor_for__s_empty__; void (__cdecl *)()
0x180029487  call    atexit
0x18002948c  lea     rcx, ?$TSS0@?7???$GetCloudAttributeValueStringHelper@W4CloudDataStructAttribute@@$0BC@@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUMetadata@bond@@W4CloudDataStructAttribute@@W4GetAttributeOptions@@AEAY0BC@$$CBU?$AttributeData@W4CloudDataStructAttribute@@@@@Z@4HA
0x180029493  call    _Init_thread_footer
0x180029498  jmp     loc_1800292FA
0x18002949d  mov     eax, [rsp+1A8h+var_178]
0x1800294a1  jmp     loc_180029352
```
