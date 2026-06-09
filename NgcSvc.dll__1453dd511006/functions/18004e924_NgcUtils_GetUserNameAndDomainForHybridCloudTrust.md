# NgcUtils::GetUserNameAndDomainForHybridCloudTrust

- ea: `0x18004e924`
- end: `0x18004ed6d`
- name: `NgcUtils::GetUserNameAndDomainForHybridCloudTrust`
- size: `1097`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008d340`

## callees

- `0x18000782c`
- `0x180007964`
- `0x180009e94`
- `0x18000b52c`
- `0x18000e570`
- `0x18000e960`
- `0x1800137c0`
- `0x180016350`
- `0x180020a0c`
- `0x1800281e0`
- `0x1800288a0`
- `0x18002c9d8`
- `0x180047228`
- `0x18004e924`
- `0x18004f1b0`
- `0x18004f1dc`
- `0x18004f1f8`
- `0x18005bef0`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eb4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eb86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eb4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eb86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e9c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e9c9`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004ea19`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004ea19`
- `ncrypt!NCryptOpenKey` at `0x18004eadb`
- `ncrypt!NCryptOpenKey` at `0x18004eadb`
- `ncrypt!NCryptGetProperty` at `0x18004eb19`
- `ncrypt!NCryptGetProperty` at `0x18004eb19`
- `cryptngc!NgcEnumUserIdKeys` at `0x18004ea84`
- `cryptngc!NgcEnumUserIdKeys` at `0x18004ea84`

## string_xrefs

- `0x18004e9d7`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18004ea2c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18004ebe6`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18004ec32`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18004ec60`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18004ed28`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcUtils::GetUserNameAndDomainForHybridCloudTrust(
        PSID Sid,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rbx
  const char *v13; // r9
  SECURITY_STATUS v14; // eax
  SECURITY_STATUS Property; // edi
  const WCHAR *v16; // rdi
  HLOCAL v17; // rcx
  HLOCAL v18; // rcx
  bool v19; // zf
  __int64 v20; // rdx
  int v21; // eax
  char **v22; // rax
  char v23; // bl
  __int64 v24; // rdx
  HLOCAL v25; // rcx
  int dwFlags; // [rsp+20h] [rbp-C1h]
  int *dwFlagsa; // [rsp+20h] [rbp-C1h]
  HLOCAL hMem; // [rsp+30h] [rbp-B1h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-A9h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-A1h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-99h] BYREF
  BYTE pbOutput[8]; // [rsp+50h] [rbp-91h] BYREF
  __int64 v34; // [rsp+58h] [rbp-89h] BYREF
  __int64 v35; // [rsp+60h] [rbp-81h] BYREF
  DWORD pcbResult; // [rsp+68h] [rbp-79h] BYREF
  HLOCAL *p_hMem; // [rsp+70h] [rbp-71h] BYREF
  int v38[2]; // [rsp+78h] [rbp-69h] BYREF
  __int64 v39; // [rsp+80h] [rbp-61h]
  int v40; // [rsp+88h] [rbp-59h]
  _OWORD v41[2]; // [rsp+90h] [rbp-51h] BYREF
  _OWORD v42[2]; // [rsp+B0h] [rbp-31h] BYREF
  char *v43[4]; // [rsp+D0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v40 = 0;
  v41[0] = 0;
  v41[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v41[0]) = 0;
  v35 = 0;
  JoinInfo = DsrGetJoinInfo(Sid, &v35);
  LastError = JoinInfo;
  if ( JoinInfo < 0 )
  {
    v10 = (unsigned int)JoinInfo;
    v11 = 451;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)v10,
      dwFlags);
    goto LABEL_43;
  }
  v12 = v35;
  if ( !v35 || !*(_QWORD *)(v35 + 32) )
  {
    LastError = -2147418113;
    v10 = 2147549183LL;
    v11 = 452;
    goto LABEL_42;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v14 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    Property = v14;
    if ( v14 >= 0 )
    {
      v34 = 0;
      while ( 1 )
      {
        hMem = 0;
        p_hMem = &hMem;
        *(_QWORD *)v38 = 0;
        LOBYTE(v39) = 1;
        dwFlagsa = v38;
        Property = NgcEnumUserIdKeys(*(_QWORD *)(v12 + 24), *(_QWORD *)(v12 + 32), &sourceString, StringSid);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
        if ( Property == -2146893782 )
          goto LABEL_18;
        if ( Property < 0 )
          break;
        phKey = 0;
        v16 = (const WCHAR *)*((_QWORD *)hMem + 4);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &phKey,
          0);
        Property = NCryptOpenKey(phProvider, &phKey, v16, 0, 0x40u);
        if ( Property < 0 )
        {
          v24 = 478;
          goto LABEL_26;
        }
        *(_DWORD *)pbOutput = 0;
        pcbResult = 0;
        Property = NCryptGetProperty(phKey, L"NgcLogonCapableKey", pbOutput, 4u, &pcbResult, 0);
        if ( Property < 0 )
        {
          v24 = 483;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
            (const char *)(unsigned int)Property,
            (int)dwFlagsa);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
          goto LABEL_29;
        }
        if ( *(_DWORD *)pbOutput )
        {
          std::wstring::assign(v41, *((_QWORD *)hMem + 2));
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
LABEL_18:
          v18 = hMem;
          v19 = hMem == 0;
          hMem = 0;
          if ( !v19 )
            LocalFree(v18);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
          wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v35);
          p_hMem = 0;
          *(_QWORD *)v38 = 0;
          v39 = 0;
          v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                  &p_hMem,
                  v20,
                  L"Software\\Microsoft\\IdentityStore\\Providers\\{B16898C6-A148-4967-9171-64D755DA8520}",
                  L"Name");
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1EF,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
              (const char *)(unsigned int)v21,
              (int)dwFlagsa);
          std::wstring::operator=(a3, v41);
          if ( p_hMem && *(_WORD *)p_hMem )
          {
            v22 = std::wstring::wstring(v43, p_hMem);
            v23 = 2;
          }
          else
          {
            v42[0] = 0;
            v42[1] = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v42[0]) = 0;
            v22 = (char **)v42;
            v23 = 1;
          }
          std::wstring::operator=(a4, v22);
          if ( (v23 & 2) != 0 )
          {
            v23 &= ~2u;
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v43);
          }
          if ( (v23 & 1) != 0 )
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v42);
          if ( a5 )
            *a5 = 1;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&p_hMem);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v41);
          return 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        v17 = hMem;
        hMem = 0;
        if ( v17 )
          LocalFree(v17);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)Property,
        (int)v38);
LABEL_29:
      v25 = hMem;
      hMem = 0;
      if ( v25 )
        LocalFree(v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)v14,
        dwFlags);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    LastError = Property;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C7,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                  v13);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  }
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v35);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v41);
  return LastError;
}

```

## disassembly

```asm
0x18004e924  push    rbp
0x18004e926  push    rbx
0x18004e927  push    rsi
0x18004e928  push    rdi
0x18004e929  push    r12
0x18004e92b  push    r14
0x18004e92d  push    r15
0x18004e92f  lea     rbp, [rsp-1Fh]
0x18004e934  sub     rsp, 100h
0x18004e93b  mov     rax, cs:__security_cookie
0x18004e942  xor     rax, rsp
0x18004e945  mov     [rbp+4Fh+var_40], rax
0x18004e949  mov     r15, r9
0x18004e94c  mov     r14, r8
0x18004e94f  mov     rdi, rcx
0x18004e952  mov     rsi, [rbp+4Fh+arg_20]
0x18004e956  xor     r12d, r12d
0x18004e959  mov     [rbp+4Fh+var_A8], r12d
0x18004e95d  xorps   xmm0, xmm0
0x18004e960  movups  [rbp+4Fh+var_A0], xmm0
0x18004e964  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004e96c  movdqu  [rbp+4Fh+var_90], xmm1
0x18004e971  mov     word ptr [rbp+4Fh+var_A0], r12w
0x18004e976  mov     [rsp+130h+var_D0], r12
0x18004e97b  lea     rdx, [rsp+130h+var_D0]
0x18004e980  call    DsrGetJoinInfo
0x18004e985  mov     ebx, eax
0x18004e987  test    eax, eax
0x18004e989  jns     short loc_18004E998
0x18004e98b  mov     r9d, eax
0x18004e98e  mov     edx, 1C3h
0x18004e993  jmp     loc_18004ED28
0x18004e998  mov     rbx, [rsp+130h+var_D0]
0x18004e99d  test    rbx, rbx
0x18004e9a0  jz      loc_18004ED1B
0x18004e9a6  cmp     [rbx+20h], r12
0x18004e9aa  jz      loc_18004ED1B
0x18004e9b0  mov     [rsp+130h+StringSid], r12
0x18004e9b5  xor     edx, edx
0x18004e9b7  lea     rcx, [rsp+130h+StringSid]
0x18004e9bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004e9c1  lea     rdx, [rsp+130h+StringSid]; StringSid
0x18004e9c6  mov     rcx, rdi; Sid
0x18004e9c9  call    cs:__imp_ConvertSidToStringSidW
0x18004e9cf  test    eax, eax
0x18004e9d1  jnz     short loc_18004E9F9
0x18004e9d3  mov     rcx, [rbp+57h]; this
0x18004e9d7  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004e9de  mov     edx, 1C7h; void *
0x18004e9e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e9e8  mov     ebx, eax
0x18004e9ea  lea     rcx, [rsp+130h+StringSid]; void *
0x18004e9ef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e9f4  jmp     loc_18004ED39
0x18004e9f9  mov     [rsp+130h+phProvider], r12
0x18004e9fe  xor     edx, edx
0x18004ea00  lea     rcx, [rsp+130h+phProvider]
0x18004ea05  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004ea0a  xor     r8d, r8d; dwFlags
0x18004ea0d  lea     rdx, aMicrosoftPassp_0; "Microsoft Passport Key Storage Provider"
0x18004ea14  lea     rcx, [rsp+130h+phProvider]; phProvider
0x18004ea19  call    cs:__imp_NCryptOpenStorageProvider
0x18004ea1f  mov     edi, eax
0x18004ea21  test    eax, eax
0x18004ea23  jns     short loc_18004EA42
0x18004ea25  mov     rcx, [rbp+57h]; this
0x18004ea29  mov     r9d, eax; char *
0x18004ea2c  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004ea33  mov     edx, 1CAh; void *
0x18004ea38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ea3d  jmp     loc_18004EC93
0x18004ea42  mov     [rsp+130h+var_D8], r12
0x18004ea47  mov     [rsp+130h+hMem], r12
0x18004ea4c  lea     rax, [rsp+130h+hMem]
0x18004ea51  mov     [rbp+4Fh+var_C0], rax
0x18004ea55  mov     qword ptr [rbp+4Fh+var_B8], r12
0x18004ea59  mov     byte ptr [rbp+4Fh+var_B0], 1
0x18004ea5d  lea     rax, [rsp+130h+var_D8]
0x18004ea62  mov     qword ptr [rsp+130h+var_108], rax
0x18004ea67  lea     rax, [rbp+4Fh+var_B8]
0x18004ea6b  mov     qword ptr [rsp+130h+dwFlags], rax; int
0x18004ea70  mov     r9, [rsp+130h+StringSid]
0x18004ea75  lea     r8, sourceString
0x18004ea7c  mov     rdx, [rbx+20h]
0x18004ea80  mov     rcx, [rbx+18h]
0x18004ea84  call    cs:__imp_NgcEnumUserIdKeys
0x18004ea8a  mov     edi, eax
0x18004ea8c  lea     rcx, [rbp+4Fh+var_C0]
0x18004ea90  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004ea95  cmp     edi, 8009002Ah
0x18004ea9b  jz      loc_18004EB77
0x18004eaa1  test    edi, edi
0x18004eaa3  js      loc_18004EC59
0x18004eaa9  mov     [rsp+130h+phKey], r12
0x18004eaae  mov     rax, [rsp+130h+hMem]
0x18004eab3  mov     rdi, [rax+20h]
0x18004eab7  xor     edx, edx
0x18004eab9  lea     rcx, [rsp+130h+phKey]
0x18004eabe  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004eac3  mov     [rsp+130h+dwFlags], 40h ; '@'; dwFlags
0x18004eacb  xor     r9d, r9d; dwLegacyKeySpec
0x18004eace  mov     r8, rdi; pszKeyName
0x18004ead1  lea     rdx, [rsp+130h+phKey]; phKey
0x18004ead6  mov     rcx, [rsp+130h+phProvider]; hProvider
0x18004eadb  call    cs:__imp_NCryptOpenKey
0x18004eae1  mov     edi, eax
0x18004eae3  test    eax, eax
0x18004eae5  js      loc_18004EC52
0x18004eaeb  mov     dword ptr [rsp+130h+pbOutput], r12d
0x18004eaf0  mov     [rbp+4Fh+pcbResult], r12d
0x18004eaf4  mov     [rsp+130h+var_108], r12d; dwFlags
0x18004eaf9  lea     rax, [rbp+4Fh+pcbResult]
0x18004eafd  mov     qword ptr [rsp+130h+dwFlags], rax; int
0x18004eb02  mov     r9d, 4; cbOutput
0x18004eb08  lea     r8, [rsp+130h+pbOutput]; pbOutput
0x18004eb0d  lea     rdx, aNgclogoncapabl; "NgcLogonCapableKey"
0x18004eb14  mov     rcx, [rsp+130h+phKey]; hObject
0x18004eb19  call    cs:__imp_NCryptGetProperty
0x18004eb1f  mov     edi, eax
0x18004eb21  test    eax, eax
0x18004eb23  js      loc_18004EC2D
0x18004eb29  cmp     dword ptr [rsp+130h+pbOutput], r12d
0x18004eb2e  jnz     short loc_18004EB59
0x18004eb30  lea     rcx, [rsp+130h+phKey]
0x18004eb35  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004eb3a  nop
0x18004eb3b  mov     rcx, [rsp+130h+hMem]; hMem
0x18004eb40  mov     [rsp+130h+hMem], r12
0x18004eb45  test    rcx, rcx
0x18004eb48  jz      loc_18004EA47
0x18004eb4e  call    cs:__imp_LocalFree
0x18004eb54  jmp     loc_18004EA47
0x18004eb59  mov     rdx, [rsp+130h+hMem]
0x18004eb5e  mov     rdx, [rdx+10h]
0x18004eb62  lea     rcx, [rbp+4Fh+var_A0]
0x18004eb66  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18004eb6b  nop
0x18004eb6c  lea     rcx, [rsp+130h+phKey]
0x18004eb71  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004eb76  nop
0x18004eb77  mov     rcx, [rsp+130h+hMem]; hMem
0x18004eb7c  test    rcx, rcx
0x18004eb7f  mov     [rsp+130h+hMem], r12
0x18004eb84  jz      short loc_18004EB8D
0x18004eb86  call    cs:__imp_LocalFree
0x18004eb8c  nop
0x18004eb8d  lea     rcx, [rsp+130h+var_D8]
0x18004eb92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004eb97  nop
0x18004eb98  lea     rcx, [rsp+130h+phProvider]
0x18004eb9d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004eba2  nop
0x18004eba3  lea     rcx, [rsp+130h+StringSid]; void *
0x18004eba8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004ebad  nop
0x18004ebae  lea     rcx, [rsp+130h+var_D0]
0x18004ebb3  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18004ebb8  mov     [rbp+4Fh+var_C0], r12
0x18004ebbc  mov     qword ptr [rbp+4Fh+var_B8], r12
0x18004ebc0  mov     [rbp+4Fh+var_B0], r12
0x18004ebc4  lea     r9, aName; "Name"
0x18004ebcb  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\IdentityStore\\Pro"...
0x18004ebd2  lea     rcx, [rbp+4Fh+var_C0]
0x18004ebd6  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18004ebdb  mov     rcx, [rbp+57h]; this
0x18004ebdf  test    eax, eax
0x18004ebe1  jns     short loc_18004EBF7
0x18004ebe3  mov     r9d, eax; char *
0x18004ebe6  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004ebed  mov     edx, 1EFh; void *
0x18004ebf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ebf7  lea     rdx, [rbp+4Fh+var_A0]
0x18004ebfb  mov     rcx, r14
0x18004ebfe  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004ec03  mov     rdx, [rbp+4Fh+var_C0]
0x18004ec07  test    rdx, rdx
0x18004ec0a  jz      loc_18004ECAF
0x18004ec10  cmp     [rdx], r12w
0x18004ec14  jz      loc_18004ECAF
0x18004ec1a  lea     rcx, [rbp+4Fh+var_60]
0x18004ec1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ec23  mov     ebx, 2
0x18004ec28  jmp     loc_18004ECD1
0x18004ec2d  mov     edx, 1E3h; void *
0x18004ec32  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004ec39  mov     r9d, edi; char *
0x18004ec3c  mov     rcx, [rbp+57h]; this
0x18004ec40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec45  nop
0x18004ec46  lea     rcx, [rsp+130h+phKey]
0x18004ec4b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ec50  jmp     short loc_18004EC72
0x18004ec52  mov     edx, 1DEh
0x18004ec57  jmp     short loc_18004EC32
0x18004ec59  mov     rcx, [rbp+57h]; this
0x18004ec5d  mov     r9d, edi; char *
0x18004ec60  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004ec67  mov     edx, 1DBh; void *
0x18004ec6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec71  nop
0x18004ec72  mov     rcx, [rsp+130h+hMem]; hMem
0x18004ec77  mov     [rsp+130h+hMem], r12
0x18004ec7c  test    rcx, rcx
0x18004ec7f  jz      short loc_18004EC88
0x18004ec81  call    cs:__imp_LocalFree
0x18004ec87  nop
0x18004ec88  lea     rcx, [rsp+130h+var_D8]
0x18004ec8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004ec92  nop
0x18004ec93  lea     rcx, [rsp+130h+phProvider]
0x18004ec98  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ec9d  nop
0x18004ec9e  lea     rcx, [rsp+130h+StringSid]; void *
0x18004eca3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004eca8  mov     ebx, edi
0x18004ecaa  jmp     loc_18004ED39
0x18004ecaf  xorps   xmm0, xmm0
0x18004ecb2  movups  [rbp+4Fh+var_80], xmm0
0x18004ecb6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004ecbe  movdqu  [rbp+4Fh+var_70], xmm1
0x18004ecc3  mov     word ptr [rbp+4Fh+var_80], r12w
0x18004ecc8  lea     rax, [rbp+4Fh+var_80]
0x18004eccc  mov     ebx, 1
0x18004ecd1  mov     rdx, rax
0x18004ecd4  mov     rcx, r15
0x18004ecd7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004ecdc  test    bl, 2
0x18004ecdf  jz      short loc_18004ECEE
0x18004ece1  and     ebx, 0FFFFFFFDh
0x18004ece4  lea     rcx, [rbp+4Fh+var_60]
0x18004ece8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004eced  nop
0x18004ecee  test    bl, 1
0x18004ecf1  jz      short loc_18004ECFC
0x18004ecf3  lea     rcx, [rbp+4Fh+var_80]
0x18004ecf7  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004ecfc  test    rsi, rsi
0x18004ecff  jz      short loc_18004ED04
0x18004ed01  mov     byte ptr [rsi], 1
0x18004ed04  lea     rcx, [rbp+4Fh+var_C0]
0x18004ed08  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004ed0d  nop
0x18004ed0e  lea     rcx, [rbp+4Fh+var_A0]
0x18004ed12  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004ed17  xor     eax, eax
0x18004ed19  jmp     short loc_18004ED4F
0x18004ed1b  mov     ebx, 8000FFFFh
0x18004ed20  mov     r9d, ebx; char *
0x18004ed23  mov     edx, 1C4h; void *
0x18004ed28  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004ed2f  mov     rcx, [rbp+57h]; this
0x18004ed33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed38  nop
0x18004ed39  lea     rcx, [rsp+130h+var_D0]
0x18004ed3e  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18004ed43  nop
0x18004ed44  lea     rcx, [rbp+4Fh+var_A0]
0x18004ed48  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004ed4d  mov     eax, ebx
0x18004ed4f  mov     rcx, [rbp+4Fh+var_40]
0x18004ed53  xor     rcx, rsp; StackCookie
0x18004ed56  call    __security_check_cookie
0x18004ed5b  add     rsp, 100h
0x18004ed62  pop     r15
0x18004ed64  pop     r14
0x18004ed66  pop     r12
0x18004ed68  pop     rdi
0x18004ed69  pop     rsi
0x18004ed6a  pop     rbx
0x18004ed6b  pop     rbp
0x18004ed6c  retn
```
