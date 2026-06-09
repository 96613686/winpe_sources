# Windows::Internal::CapabilityAccess::Private::PackageHasCapability(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const *,bool *)

- ea: `0x180045434`
- end: `0x180045860`
- name: `?PackageHasCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@PEA_N@Z`
- size: `1068`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044f4c`
- `0x18005ae04`
- `0x18006874c`
- `0x180073d8c`
- `0x1800797b4`

## callees

- `0x1800094c0`
- `0x18002392c`
- `0x180029408`
- `0x18002f260`
- `0x18003ae98`
- `0x18003f2c0`
- `0x18003f310`
- `0x18003f3c4`
- `0x18003f3dc`
- `0x18003f728`
- `0x18003f738`
- `0x180042fe8`
- `0x180045434`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180045601`
- `ntdll!RtlEqualSid` at `0x180045633`
- `ntdll!RtlEqualSid` at `0x1800456ad`
- `ntdll!RtlEqualSid` at `0x180045723`
- `ntdll!RtlEqualSid` at `0x18004574c`
- `ntdll!RtlEqualSid` at `0x1800457ff`
- `ntdll!RtlEqualSid` at `0x180045601`
- `ntdll!RtlEqualSid` at `0x180045633`
- `ntdll!RtlEqualSid` at `0x1800456ad`
- `ntdll!RtlEqualSid` at `0x180045723`
- `ntdll!RtlEqualSid` at `0x18004574c`
- `ntdll!RtlEqualSid` at `0x1800457ff`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800454be`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800456f1`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800457bc`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800454be`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800456f1`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800457bc`
- `ntdll!RtlInitUnicodeString` at `0x1800454ac`
- `ntdll!RtlInitUnicodeString` at `0x1800456df`
- `ntdll!RtlInitUnicodeString` at `0x1800457aa`
- `ntdll!RtlInitUnicodeString` at `0x1800454ac`
- `ntdll!RtlInitUnicodeString` at `0x1800456df`
- `ntdll!RtlInitUnicodeString` at `0x1800457aa`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180045584`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180045584`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Windows::Internal::CapabilityAccess::Private::PackageHasCapability(
        void *a1,
        __int64 a2,
        __int64 *a3,
        _BYTE *a4)
{
  __int64 v6; // rdx
  const WCHAR *v7; // rax
  int v8; // eax
  int v9; // edi
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r10
  int ApplicationCapabilities; // eax
  unsigned __int64 v15; // rax
  unsigned int i; // ebx
  PSID *v17; // rax
  unsigned int j; // ebx
  PSID *v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rsi
  unsigned __int64 k; // rdi
  PSID *v23; // rax
  const WCHAR *v24; // rax
  int v25; // eax
  unsigned int m; // edi
  PSID *v27; // rax
  unsigned int n; // edi
  PSID *v29; // rax
  int v31; // eax
  unsigned int ii; // ebx
  PSID *v33; // rax
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  _BYTE v36[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v37; // [rsp+68h] [rbp-98h]
  int v38; // [rsp+70h] [rbp-90h]
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v41; // [rsp+88h] [rbp-78h]
  _BYTE v42[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v43; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v47[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Sid2[48]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v49[48]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  Sid = a1;
  if ( a4 )
    *a4 = 0;
  v38 = 0;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v36);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v42);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v40);
  DestinationString = 0;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  RtlInitUnicodeString(&DestinationString, v7);
  v8 = RtlDeriveCapabilitySidsFromName(&DestinationString, v49, Sid2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v8,
      v34);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
    v40,
    v47);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v40);
  v9 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
         v42,
         v46);
  v10 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v42);
  v11 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
          v36,
          v45);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v36);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Sid);
  v35 = v9 + 8;
  ApplicationCapabilities = QueryApplicationCapabilitiesEx(v12, v13, v11 + 8, v10);
  if ( ApplicationCapabilities < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A0,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)ApplicationCapabilities,
      v35);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v45);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v46);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v47);
  if ( v38 == 2 )
  {
LABEL_48:
    if ( a4 )
      *a4 = 1;
LABEL_40:
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v40);
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v42);
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v36);
    return 1;
  }
  else
  {
    v15 = v37;
    if ( v37 || v41 )
    {
      for ( i = 0; i < v15; ++i )
      {
        v17 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v36);
        if ( RtlEqualSid(*v17, Sid2) )
          goto LABEL_40;
        v15 = v37;
      }
      for ( j = 0; j < v41; ++j )
      {
        v19 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v40);
        if ( RtlEqualSid(*v19, Sid2) )
          goto LABEL_40;
      }
      if ( a3 )
      {
        v20 = *a3;
        v21 = a3[1];
        while ( v20 != v21 )
        {
          if ( *(_QWORD *)(v20 + 16) > 1u
            && *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20) == 83
            && *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20) + 2) == 45 )
          {
            Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(&Sid);
            for ( k = 0; ; ++k )
            {
              if ( k >= v43 )
              {
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
                goto LABEL_29;
              }
              v23 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v42);
              if ( RtlEqualSid(*v23, Sid) == 1 )
                break;
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
            goto LABEL_40;
          }
          v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
          RtlInitUnicodeString(&DestinationString, v24);
          v25 = RtlDeriveCapabilitySidsFromName(&DestinationString, v49, Sid2);
          if ( v25 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x4DB,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
              (const char *)(unsigned int)v25,
              v35);
          for ( m = 0; m < v37; ++m )
          {
            v27 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v36);
            if ( RtlEqualSid(*v27, Sid2) )
              goto LABEL_40;
          }
          for ( n = 0; n < v41; ++n )
          {
            v29 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v40);
            if ( RtlEqualSid(*v29, Sid2) )
              goto LABEL_40;
          }
LABEL_29:
          v20 += 32;
        }
      }
      RtlInitUnicodeString(&DestinationString, L"runFullTrust");
      v31 = RtlDeriveCapabilitySidsFromName(&DestinationString, v49, Sid2);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x4F2,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
          (const char *)(unsigned int)v31,
          v35);
      for ( ii = 0; ii < v37; ++ii )
      {
        v33 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v36);
        if ( RtlEqualSid(*v33, Sid2) == 1 )
          goto LABEL_48;
      }
    }
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v40);
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v42);
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v36);
    return 0;
  }
}

```

## disassembly

```asm
0x180045434  push    rbp
0x180045436  push    rbx
0x180045437  push    rsi
0x180045438  push    rdi
0x180045439  push    r12
0x18004543b  push    r13
0x18004543d  push    r14
0x18004543f  push    r15
0x180045441  lea     rbp, [rsp-58h]
0x180045446  sub     rsp, 158h
0x18004544d  mov     rax, cs:__security_cookie
0x180045454  xor     rax, rsp
0x180045457  mov     [rbp+90h+var_50], rax
0x18004545b  mov     r12, r9
0x18004545e  mov     r13, r8
0x180045461  mov     [rsp+190h+Sid], rcx
0x180045466  test    r9, r9
0x180045469  jz      short loc_18004546F
0x18004546b  mov     byte ptr [r9], 0
0x18004546f  mov     [rsp+190h+var_120], 0
0x180045477  lea     rcx, [rsp+190h+var_130]
0x18004547c  call    ??0?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045481  nop
0x180045482  lea     rcx, [rbp+90h+var_100]
0x180045486  call    ??0?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18004548b  nop
0x18004548c  lea     rcx, [rbp+90h+var_110]
0x180045490  call    ??0?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045495  nop
0x180045496  xorps   xmm0, xmm0
0x180045499  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18004549d  mov     rcx, rdx
0x1800454a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800454a5  mov     rdx, rax; SourceString
0x1800454a8  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800454ac  call    cs:__imp_RtlInitUnicodeString
0x1800454b2  lea     r8, [rbp+90h+Sid2]
0x1800454b6  lea     rdx, [rbp+90h+var_80]
0x1800454ba  lea     rcx, [rbp+90h+DestinationString]
0x1800454be  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800454c4  mov     rcx, [rbp+98h]; this
0x1800454cb  test    eax, eax
0x1800454cd  jns     short loc_1800454E4
0x1800454cf  mov     r9d, eax; char *
0x1800454d2  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800454d9  mov     edx, 49Dh; void *
0x1800454de  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800454e4  lea     rdx, [rbp+90h+var_C0]
0x1800454e8  lea     rcx, [rbp+90h+var_110]
0x1800454ec  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x1800454f1  mov     r14, rax
0x1800454f4  lea     rcx, [rbp+90h+var_110]
0x1800454f8  call    ??I?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x1800454fd  mov     r15, rax
0x180045500  lea     rdx, [rbp+90h+var_D0]
0x180045504  lea     rcx, [rbp+90h+var_100]
0x180045508  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x18004550d  mov     rdi, rax
0x180045510  lea     rcx, [rbp+90h+var_100]
0x180045514  call    ??I?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x180045519  mov     rsi, rax
0x18004551c  lea     rdx, [rbp+90h+var_E0]
0x180045520  lea     rcx, [rsp+190h+var_130]
0x180045525  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x18004552a  mov     rbx, rax
0x18004552d  lea     rcx, [rsp+190h+var_130]
0x180045532  call    ??I?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x180045537  mov     r10, rax
0x18004553a  mov     rcx, [rsp+190h+Sid]
0x18004553f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045544  lea     rcx, [r14+8]
0x180045548  lea     rdx, [rdi+8]
0x18004554c  lea     r8, [rbx+8]
0x180045550  xor     r14d, r14d
0x180045553  mov     [rsp+190h+var_140], r14
0x180045558  mov     [rsp+190h+var_148], r14
0x18004555d  lea     r9, [rsp+190h+var_120]
0x180045562  mov     [rsp+190h+var_150], r9
0x180045567  mov     [rsp+190h+var_158], r14
0x18004556c  mov     [rsp+190h+var_160], rcx
0x180045571  mov     [rsp+190h+var_168], r15
0x180045576  mov     qword ptr [rsp+190h+var_170], rdx; int
0x18004557b  mov     r9, rsi
0x18004557e  mov     rdx, r10
0x180045581  mov     rcx, rax
0x180045584  call    cs:__imp_QueryApplicationCapabilitiesEx
0x18004558a  mov     rcx, [rbp+98h]; this
0x180045591  test    eax, eax
0x180045593  jns     short loc_1800455AA
0x180045595  mov     r9d, eax; char *
0x180045598  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004559f  mov     edx, 4A0h; void *
0x1800455a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800455aa  lea     rcx, [rbp+90h+var_E0]
0x1800455ae  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1800455b3  nop
0x1800455b4  lea     rcx, [rbp+90h+var_D0]
0x1800455b8  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1800455bd  nop
0x1800455be  lea     rcx, [rbp+90h+var_C0]
0x1800455c2  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1800455c7  cmp     [rsp+190h+var_120], 2
0x1800455cc  jz      loc_18004580D
0x1800455d2  mov     rax, [rsp+190h+var_128]
0x1800455d7  test    rax, rax
0x1800455da  jnz     short loc_1800455E6
0x1800455dc  cmp     [rbp+90h+var_108], r14
0x1800455e0  jz      loc_180045820
0x1800455e6  mov     ebx, r14d
0x1800455e9  mov     edx, ebx
0x1800455eb  cmp     rdx, rax
0x1800455ee  jnb     short loc_180045618
0x1800455f0  lea     rcx, [rsp+190h+var_130]
0x1800455f5  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x1800455fa  lea     rdx, [rbp+90h+Sid2]; Sid2
0x1800455fe  mov     rcx, [rax]; Sid1
0x180045601  call    cs:__imp_RtlEqualSid
0x180045607  test    al, al
0x180045609  jnz     loc_180045765
0x18004560f  inc     ebx
0x180045611  mov     rax, [rsp+190h+var_128]
0x180045616  jmp     short loc_1800455E9
0x180045618  mov     ebx, r14d
0x18004561b  mov     edx, ebx
0x18004561d  cmp     rdx, [rbp+90h+var_108]
0x180045621  jnb     short loc_180045645
0x180045623  lea     rcx, [rbp+90h+var_110]
0x180045627  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x18004562c  lea     rdx, [rbp+90h+Sid2]; Sid2
0x180045630  mov     rcx, [rax]; Sid1
0x180045633  call    cs:__imp_RtlEqualSid
0x180045639  test    al, al
0x18004563b  jnz     loc_180045765
0x180045641  inc     ebx
0x180045643  jmp     short loc_18004561B
0x180045645  test    r13, r13
0x180045648  jz      loc_18004579F
0x18004564e  mov     rbx, [r13+0]
0x180045652  mov     rsi, [r13+8]
0x180045656  cmp     rbx, rsi
0x180045659  jz      loc_18004579F
0x18004565f  cmp     qword ptr [rbx+10h], 1
0x180045664  jbe     short loc_1800456D0
0x180045666  mov     rcx, rbx
0x180045669  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004566e  cmp     word ptr [rax], 53h ; 'S'
0x180045672  jnz     short loc_1800456D0
0x180045674  mov     rcx, rbx
0x180045677  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004567c  cmp     word ptr [rax+2], 2Dh ; '-'
0x180045681  jnz     short loc_1800456D0
0x180045683  mov     rdx, rbx
0x180045686  lea     rcx, [rsp+190h+Sid]; Sid
0x18004568b  call    ?GetSidFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(std::wstring const &)
0x180045690  mov     rdi, r14
0x180045693  cmp     rdi, [rbp+90h+var_F8]
0x180045697  jnb     short loc_1800456C0
0x180045699  mov     rdx, rdi
0x18004569c  lea     rcx, [rbp+90h+var_100]
0x1800456a0  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x1800456a5  mov     rdx, [rsp+190h+Sid]; Sid2
0x1800456aa  mov     rcx, [rax]; Sid1
0x1800456ad  call    cs:__imp_RtlEqualSid
0x1800456b3  cmp     al, 1
0x1800456b5  jz      loc_18004575A
0x1800456bb  inc     rdi
0x1800456be  jmp     short loc_180045693
0x1800456c0  lea     rcx, [rsp+190h+Sid]
0x1800456c5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800456ca  add     rbx, 20h ; ' '
0x1800456ce  jmp     short loc_180045656
0x1800456d0  mov     rcx, rbx
0x1800456d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800456d8  mov     rdx, rax; SourceString
0x1800456db  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800456df  call    cs:__imp_RtlInitUnicodeString
0x1800456e5  lea     r8, [rbp+90h+Sid2]
0x1800456e9  lea     rdx, [rbp+90h+var_80]
0x1800456ed  lea     rcx, [rbp+90h+DestinationString]
0x1800456f1  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800456f7  mov     rcx, [rbp+98h]; this
0x1800456fe  test    eax, eax
0x180045700  js      loc_18004578A
0x180045706  mov     edi, r14d
0x180045709  mov     edx, edi
0x18004570b  cmp     rdx, [rsp+190h+var_128]
0x180045710  jnb     short loc_180045731
0x180045712  lea     rcx, [rsp+190h+var_130]
0x180045717  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x18004571c  lea     rdx, [rbp+90h+Sid2]; Sid2
0x180045720  mov     rcx, [rax]; Sid1
0x180045723  call    cs:__imp_RtlEqualSid
0x180045729  test    al, al
0x18004572b  jnz     short loc_180045765
0x18004572d  inc     edi
0x18004572f  jmp     short loc_180045709
0x180045731  mov     edi, r14d
0x180045734  mov     edx, edi
0x180045736  cmp     rdx, [rbp+90h+var_108]
0x18004573a  jnb     short loc_1800456CA
0x18004573c  lea     rcx, [rbp+90h+var_110]
0x180045740  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x180045745  lea     rdx, [rbp+90h+Sid2]; Sid2
0x180045749  mov     rcx, [rax]; Sid1
0x18004574c  call    cs:__imp_RtlEqualSid
0x180045752  test    al, al
0x180045754  jnz     short loc_180045765
0x180045756  inc     edi
0x180045758  jmp     short loc_180045734
0x18004575a  lea     rcx, [rsp+190h+Sid]
0x18004575f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180045764  nop
0x180045765  lea     rcx, [rbp+90h+var_110]
0x180045769  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18004576e  nop
0x18004576f  lea     rcx, [rbp+90h+var_100]
0x180045773  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045778  nop
0x180045779  lea     rcx, [rsp+190h+var_130]
0x18004577e  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045783  mov     al, 1
0x180045785  jmp     loc_180045840
0x18004578a  mov     r9d, eax; char *
0x18004578d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045794  mov     edx, 4DBh; void *
0x180045799  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004579f  lea     rdx, SourceString; "runFullTrust"
0x1800457a6  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800457aa  call    cs:__imp_RtlInitUnicodeString
0x1800457b0  lea     r8, [rbp+90h+Sid2]
0x1800457b4  lea     rdx, [rbp+90h+var_80]
0x1800457b8  lea     rcx, [rbp+90h+DestinationString]
0x1800457bc  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800457c2  mov     rcx, [rbp+98h]; this
0x1800457c9  test    eax, eax
0x1800457cb  jns     short loc_1800457E2
0x1800457cd  mov     r9d, eax; char *
0x1800457d0  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800457d7  mov     edx, 4F2h; void *
0x1800457dc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800457e2  mov     ebx, r14d
0x1800457e5  mov     edx, ebx
0x1800457e7  cmp     rdx, [rsp+190h+var_128]
0x1800457ec  jnb     short loc_180045820
0x1800457ee  lea     rcx, [rsp+190h+var_130]
0x1800457f3  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x1800457f8  lea     rdx, [rbp+90h+Sid2]; Sid2
0x1800457fc  mov     rcx, [rax]; Sid1
0x1800457ff  call    cs:__imp_RtlEqualSid
0x180045805  cmp     al, 1
0x180045807  jz      short loc_18004580D
0x180045809  inc     ebx
0x18004580b  jmp     short loc_1800457E5
0x18004580d  test    r12, r12
0x180045810  jz      loc_180045765
0x180045816  mov     byte ptr [r12], 1
0x18004581b  jmp     loc_180045765
0x180045820  lea     rcx, [rbp+90h+var_110]
0x180045824  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045829  nop
0x18004582a  lea     rcx, [rbp+90h+var_100]
0x18004582e  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180045833  nop
0x180045834  lea     rcx, [rsp+190h+var_130]
0x180045839  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18004583e  xor     al, al
0x180045840  mov     rcx, [rbp+90h+var_50]
0x180045844  xor     rcx, rsp; StackCookie
0x180045847  call    __security_check_cookie
0x18004584c  add     rsp, 158h
0x180045853  pop     r15
0x180045855  pop     r14
0x180045857  pop     r13
0x180045859  pop     r12
0x18004585b  pop     rdi
0x18004585c  pop     rsi
0x18004585d  pop     rbx
0x18004585e  pop     rbp
0x18004585f  retn
```
