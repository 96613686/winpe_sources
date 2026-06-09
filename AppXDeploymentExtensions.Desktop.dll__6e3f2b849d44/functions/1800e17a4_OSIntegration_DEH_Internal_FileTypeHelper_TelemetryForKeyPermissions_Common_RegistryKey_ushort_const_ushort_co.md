# OSIntegration::DEH::Internal::FileTypeHelper::TelemetryForKeyPermissions(Common::RegistryKey &,ushort const *,ushort const *,ushort const *)

- ea: `0x1800e17a4`
- end: `0x1800e1a58`
- name: `?TelemetryForKeyPermissions@FileTypeHelper@Internal@DEH@OSIntegration@@AEAAJAEAVRegistryKey@Common@@PEBG11@Z`
- size: `692`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::FileTypeHelper *__hidden this, struct Common::RegistryKey *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e1a60`

## callees

- `0x180001a58`
- `0x18000669c`
- `0x18001adb4`
- `0x180048cd4`
- `0x1800530c0`
- `0x180059570`
- `0x1800864e0`
- `0x1800af1bc`
- `0x1800e17a4`
- `0x180172950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e18e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e18e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800e1837`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800e1837`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800e186f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800e186f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800e1892`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800e1892`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800e18d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800e18d6`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::FileTypeHelper::TelemetryForKeyPermissions(
        OSIntegration::DEH::Internal::FileTypeHelper *this,
        struct Common::RegistryKey *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int KeySecurity; // eax
  unsigned int LastError; // ebx
  const char *v9; // r9
  __int64 v10; // rdx
  signed int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r9
  int v14; // r8d
  int v15; // r9d
  int StringSecurityDescriptorLen; // [rsp+28h] [rbp-E0h]
  int StringSecurityDescriptorLena; // [rsp+28h] [rbp-E0h]
  WINBOOL bDaclPresent; // [rsp+88h] [rbp-80h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+8Ch] [rbp-7Ch] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+90h] [rbp-78h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+98h] [rbp-70h] BYREF
  ULONG v23; // [rsp+A0h] [rbp-68h] BYREF
  int v24; // [rsp+A4h] [rbp-64h] BYREF
  WINBOOL v25; // [rsp+A8h] [rbp-60h] BYREF
  WINBOOL v26; // [rsp+ACh] [rbp-5Ch] BYREF
  WINBOOL v27; // [rsp+B0h] [rbp-58h] BYREF
  int v28; // [rsp+B4h] [rbp-54h] BYREF
  PSID pGroup; // [rsp+B8h] [rbp-50h] BYREF
  PSID pOwner; // [rsp+C0h] [rbp-48h] BYREF
  int v31; // [rsp+C8h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+D0h] [rbp-38h]
  int v33; // [rsp+D8h] [rbp-30h]
  PACL pDacl; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-20h] BYREF
  LPWSTR v36; // [rsp+F0h] [rbp-18h] BYREF
  PSID v37; // [rsp+F8h] [rbp-10h] BYREF
  PSID v38; // [rsp+100h] [rbp-8h] BYREF
  const unsigned __int16 *v39; // [rsp+108h] [rbp+0h] BYREF
  const unsigned __int16 *v40; // [rsp+110h] [rbp+8h] BYREF
  const unsigned __int16 *v41; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]
  OSIntegration::DEH::Internal::FileTypeHelper *bDaclDefaulted; // [rsp+148h] [rbp+40h] BYREF

  bDaclDefaulted = this;
  pSecurityDescriptor = 0;
  v31 = 0;
  v33 = 0;
  KeySecurity = Common::RegistryKey::GetKeySecurity(a2, 7u, (struct Common::ByteBuffer *)&v31);
  LastError = KeySecurity;
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x399,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
      (const char *)(unsigned int)KeySecurity,
      StringSecurityDescriptorLen);
    goto LABEL_19;
  }
  pDacl = 0;
  bDaclPresent = 0;
  LODWORD(bDaclDefaulted) = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)&bDaclDefaulted) )
  {
    v10 = 931;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                  v9);
    goto LABEL_19;
  }
  if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    v10 = 932;
    goto LABEL_5;
  }
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bGroupDefaulted) )
  {
    v10 = 933;
    goto LABEL_5;
  }
  StringSecurityDescriptor = 0;
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSecurityDescriptor,
    0);
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         pSecurityDescriptor,
         1u,
         4u,
         &StringSecurityDescriptor,
         &v23) )
  {
    goto LABEL_15;
  }
  v11 = GetLastError();
  LastError = v11;
  if ( v11 > 0 )
    LastError = (unsigned __int16)v11 | 0x80070000;
  if ( (LastError & 0x80000000) == 0 )
  {
LABEL_15:
    v12 = AppXDEHTelemetry::Provider();
    if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v12, v13) )
    {
      v24 = (int)bDaclDefaulted;
      v25 = bDaclPresent;
      v26 = bGroupDefaulted;
      v37 = pGroup;
      v27 = bOwnerDefaulted;
      v38 = pOwner;
      v39 = a5;
      v36 = StringSecurityDescriptor;
      v35 = 0x1000000;
      v28 = 983103;
      v40 = a3;
      v41 = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)&word_18021C996,
        v14,
        v15,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v28,
        (__int64)&v38,
        (__int64)&v27,
        (__int64)&v37,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v36,
        (__int64)&v35);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSecurityDescriptor);
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
      (const char *)LastError,
      StringSecurityDescriptorLena);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSecurityDescriptor);
  }
LABEL_19:
  operator delete(pSecurityDescriptor, (const struct std::nothrow_t *)1);
  return LastError;
}

```

## disassembly

```asm
0x1800e17a4  mov     rax, rsp
0x1800e17a7  mov     [rax+10h], rbx
0x1800e17ab  mov     [rax+18h], rsi
0x1800e17af  mov     [rax+8], rcx
0x1800e17b3  push    rbp
0x1800e17b4  push    r14
0x1800e17b6  push    r15
0x1800e17b8  lea     rbp, [rax-38h]
0x1800e17bc  sub     rsp, 120h
0x1800e17c3  xor     r15d, r15d
0x1800e17c6  mov     r14, r8
0x1800e17c9  mov     rcx, rdx; this
0x1800e17cc  mov     [rbp+30h+pSecurityDescriptor], r15
0x1800e17d0  lea     r8, [rbp+30h+var_70]; struct Common::ByteBuffer *
0x1800e17d4  mov     [rbp+30h+var_70], r15d
0x1800e17d8  mov     rsi, r9
0x1800e17db  mov     [rbp+30h+var_60], r15d
0x1800e17df  lea     edx, [r15+7]; unsigned int
0x1800e17e3  call    ?GetKeySecurity@RegistryKey@Common@@QEAAJKAEAVByteBuffer@2@@Z; Common::RegistryKey::GetKeySecurity(ulong,Common::ByteBuffer &)
0x1800e17e8  mov     ebx, eax
0x1800e17ea  test    eax, eax
0x1800e17ec  jns     short loc_1800E180B
0x1800e17ee  mov     rcx, [rbp+38h]; this
0x1800e17f2  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e17f9  mov     r9d, eax; char *
0x1800e17fc  mov     edx, 399h; void *
0x1800e1801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1806  jmp     loc_1800E1A2E
0x1800e180b  mov     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x1800e180f  lea     r9, [rbp+30h+bDaclDefaulted]; lpbDaclDefaulted
0x1800e1813  lea     r8, [rbp+30h+pDacl]; pDacl
0x1800e1817  mov     [rbp+30h+pDacl], r15
0x1800e181b  lea     rdx, [rbp+30h+bDaclPresent]; lpbDaclPresent
0x1800e181f  mov     [rbp+30h+bDaclPresent], r15d
0x1800e1823  mov     dword ptr [rbp+30h+bDaclDefaulted], r15d
0x1800e1827  mov     [rbp+30h+bOwnerDefaulted], r15d
0x1800e182b  mov     [rbp+30h+bGroupDefaulted], r15d
0x1800e182f  mov     [rbp+30h+pOwner], r15
0x1800e1833  mov     [rbp+30h+pGroup], r15
0x1800e1837  call    cs:__imp_GetSecurityDescriptorDacl
0x1800e183e  nop     dword ptr [rax+rax+00h]
0x1800e1843  test    eax, eax
0x1800e1845  jnz     short loc_1800E1863
0x1800e1847  mov     edx, 3A3h; void *
0x1800e184c  mov     rcx, [rbp+38h]; this
0x1800e1850  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e1857  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e185c  mov     ebx, eax
0x1800e185e  jmp     loc_1800E1A2E
0x1800e1863  mov     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x1800e1867  lea     r8, [rbp+30h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800e186b  lea     rdx, [rbp+30h+pOwner]; pOwner
0x1800e186f  call    cs:__imp_GetSecurityDescriptorOwner
0x1800e1876  nop     dword ptr [rax+rax+00h]
0x1800e187b  test    eax, eax
0x1800e187d  jnz     short loc_1800E1886
0x1800e187f  mov     edx, 3A4h
0x1800e1884  jmp     short loc_1800E184C
0x1800e1886  mov     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x1800e188a  lea     r8, [rbp+30h+bGroupDefaulted]; lpbGroupDefaulted
0x1800e188e  lea     rdx, [rbp+30h+pGroup]; pGroup
0x1800e1892  call    cs:__imp_GetSecurityDescriptorGroup
0x1800e1899  nop     dword ptr [rax+rax+00h]
0x1800e189e  test    eax, eax
0x1800e18a0  jnz     short loc_1800E18A9
0x1800e18a2  mov     edx, 3A5h
0x1800e18a7  jmp     short loc_1800E184C
0x1800e18a9  xor     edx, edx
0x1800e18ab  mov     [rbp+30h+StringSecurityDescriptor], r15
0x1800e18af  lea     rcx, [rbp+30h+StringSecurityDescriptor]
0x1800e18b3  mov     [rbp+30h+var_98], r15d
0x1800e18b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800e18bc  mov     rcx, [rbp+30h+pSecurityDescriptor]; SecurityDescriptor
0x1800e18c0  lea     rax, [rbp+30h+var_98]
0x1800e18c4  mov     edx, 1; RequestedStringSDRevision
0x1800e18c9  mov     [rsp+130h+StringSecurityDescriptorLen], rax; int
0x1800e18ce  lea     r9, [rbp+30h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800e18d2  lea     r8d, [rdx+3]; SecurityInformation
0x1800e18d6  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800e18dd  nop     dword ptr [rax+rax+00h]
0x1800e18e2  test    eax, eax
0x1800e18e4  jnz     short loc_1800E192B
0x1800e18e6  call    cs:__imp_GetLastError
0x1800e18ed  nop     dword ptr [rax+rax+00h]
0x1800e18f2  mov     ebx, eax
0x1800e18f4  test    eax, eax
0x1800e18f6  jle     short loc_1800E1901
0x1800e18f8  movzx   ebx, ax
0x1800e18fb  or      ebx, 80070000h
0x1800e1901  test    ebx, ebx
0x1800e1903  jns     short loc_1800E192B
0x1800e1905  mov     rcx, [rbp+38h]; this
0x1800e1909  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e1910  mov     r9d, ebx; char *
0x1800e1913  mov     edx, 3B0h; void *
0x1800e1918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e191d  lea     rcx, [rbp+30h+StringSecurityDescriptor]
0x1800e1921  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800e1926  jmp     loc_1800E1A2E
0x1800e192b  call    ?Provider@AppXDEHTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDEHTelemetry::Provider(void)
0x1800e1930  mov     r8, rax
0x1800e1933  mov     ecx, [rax]
0x1800e1935  cmp     ecx, 2
0x1800e1938  jbe     loc_1800E1A22
0x1800e193e  mov     rdx, 400000000000h
0x1800e1948  mov     rcx, rax
0x1800e194b  call    _tlgKeywordOn
0x1800e1950  test    al, al
0x1800e1952  jz      loc_1800E1A22
0x1800e1958  mov     eax, dword ptr [rbp+30h+bDaclDefaulted]
0x1800e195b  lea     rdx, word_18021C996
0x1800e1962  mov     rcx, [rbp+30h+StringSecurityDescriptor]
0x1800e1966  mov     [rbp+30h+var_94], eax
0x1800e1969  mov     eax, [rbp+30h+bDaclPresent]
0x1800e196c  mov     [rbp+30h+var_90], eax
0x1800e196f  mov     eax, [rbp+30h+bGroupDefaulted]
0x1800e1972  mov     [rbp+30h+var_8C], eax
0x1800e1975  mov     rax, [rbp+30h+pGroup]
0x1800e1979  mov     [rbp+30h+var_40], rax
0x1800e197d  mov     eax, [rbp+30h+bOwnerDefaulted]
0x1800e1980  mov     [rbp+30h+var_88], eax
0x1800e1983  mov     rax, [rbp+30h+pOwner]
0x1800e1987  mov     [rbp+30h+var_38], rax
0x1800e198b  mov     rax, [rbp+30h+arg_20]
0x1800e198f  mov     [rbp+30h+var_30], rax
0x1800e1993  lea     rax, [rbp+30h+var_50]
0x1800e1997  mov     [rsp+130h+var_B8], rax
0x1800e199c  lea     rax, [rbp+30h+var_48]
0x1800e19a0  mov     [rsp+130h+var_C0], rax
0x1800e19a5  lea     rax, [rbp+30h+var_94]
0x1800e19a9  mov     [rsp+130h+var_C8], rax
0x1800e19ae  lea     rax, [rbp+30h+var_90]
0x1800e19b2  mov     [rsp+130h+var_D0], rax
0x1800e19b7  lea     rax, [rbp+30h+var_8C]
0x1800e19bb  mov     [rsp+130h+var_D8], rax
0x1800e19c0  lea     rax, [rbp+30h+var_40]
0x1800e19c4  mov     [rsp+130h+var_E0], rax
0x1800e19c9  lea     rax, [rbp+30h+var_88]
0x1800e19cd  mov     [rsp+130h+var_E8], rax
0x1800e19d2  lea     rax, [rbp+30h+var_38]
0x1800e19d6  mov     [rsp+130h+var_F0], rax
0x1800e19db  lea     rax, [rbp+30h+var_84]
0x1800e19df  mov     [rsp+130h+var_F8], rax
0x1800e19e4  lea     rax, [rbp+30h+var_30]
0x1800e19e8  mov     [rsp+130h+var_100], rax
0x1800e19ed  lea     rax, [rbp+30h+var_28]
0x1800e19f1  mov     [rsp+130h+var_108], rax
0x1800e19f6  lea     rax, [rbp+30h+var_20]
0x1800e19fa  mov     [rbp+30h+var_48], rcx
0x1800e19fe  mov     rcx, r8
0x1800e1a01  mov     [rsp+130h+StringSecurityDescriptorLen], rax
0x1800e1a06  mov     [rbp+30h+var_50], 1000000h
0x1800e1a0e  mov     [rbp+30h+var_84], 0F003Fh
0x1800e1a15  mov     [rbp+30h+var_28], r14
0x1800e1a19  mov     [rbp+30h+var_20], rsi
0x1800e1a1d  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSid@U_SID@@@@U2@U3@U2@U2@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSid@U_SID@@@@454443AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800e1a22  lea     rcx, [rbp+30h+StringSecurityDescriptor]
0x1800e1a26  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800e1a2b  mov     ebx, r15d
0x1800e1a2e  mov     rcx, [rbp+30h+pSecurityDescriptor]; void *
0x1800e1a32  mov     edx, 1; struct std::nothrow_t *
0x1800e1a37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e1a3c  lea     r11, [rsp+130h+var_10]
0x1800e1a44  mov     eax, ebx
0x1800e1a46  mov     rbx, [r11+28h]
0x1800e1a4a  mov     rsi, [r11+30h]
0x1800e1a4e  mov     rsp, r11
0x1800e1a51  pop     r15
0x1800e1a53  pop     r14
0x1800e1a55  pop     rbp
0x1800e1a56  retn
```
