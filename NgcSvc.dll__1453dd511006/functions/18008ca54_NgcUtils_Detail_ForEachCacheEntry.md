# NgcUtils::Detail::ForEachCacheEntry

- ea: `0x18008ca54`
- end: `0x18008d1e6`
- name: `NgcUtils::Detail::ForEachCacheEntry`
- size: `1938`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008c0d8`
- `0x18008c1e0`

## callees

- `0x180006b60`
- `0x18000782c`
- `0x180007964`
- `0x18000e960`
- `0x18000ff4c`
- `0x180010990`
- `0x1800129e0`
- `0x180022f90`
- `0x1800281e0`
- `0x1800288a0`
- `0x18002a3bc`
- `0x18002c850`
- `0x180046fd8`
- `0x180048304`
- `0x18005cee0`
- `0x18008abec`
- `0x18008b1b4`
- `0x18008b5b0`
- `0x18008b5d8`
- `0x18008ca54`
- `0x1800cd010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18008cfb4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18008cfb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008cedd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008cedd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008cc37`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008cc37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cde4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cde4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008cbb5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008cbb5`

## string_xrefs

- `0x18008cacc`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008cbc7`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008cdfd`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall NgcUtils::Detail::ForEachCacheEntry(__int64 a1)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  __m128i si128; // xmm6
  const WCHAR *v8; // rcx
  const char *v9; // r9
  unsigned int LastError; // esi
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rcx
  DWORD LengthSid; // eax
  __int64 v15; // rdx
  const WCHAR *v16; // r8
  int v17; // esi
  int v18; // eax
  const WCHAR *v19; // r8
  int v20; // r14d
  int v21; // eax
  const WCHAR *v22; // rdx
  unsigned int ValueW; // eax
  unsigned int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // rcx
  LPCWSTR *v27; // rcx
  __int64 v28; // r13
  __int64 v29; // r12
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // r15d
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // rdx
  int pdwType; // [rsp+20h] [rbp-298h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-298h]
  bool v42[8]; // [rsp+40h] [rbp-278h] BYREF
  char v43; // [rsp+48h] [rbp-270h]
  PSID Sid; // [rsp+50h] [rbp-268h] BYREF
  LPCWSTR v45; // [rsp+58h] [rbp-260h] BYREF
  unsigned int v46; // [rsp+60h] [rbp-258h]
  int pvData; // [rsp+64h] [rbp-254h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-250h] BYREF
  int i; // [rsp+6Ch] [rbp-24Ch]
  int v50; // [rsp+70h] [rbp-248h]
  __int64 v51; // [rsp+78h] [rbp-240h]
  __int64 v52; // [rsp+80h] [rbp-238h]
  _QWORD v53[2]; // [rsp+88h] [rbp-230h] BYREF
  int v54; // [rsp+98h] [rbp-220h]
  _QWORD v55[2]; // [rsp+A0h] [rbp-218h] BYREF
  int v56; // [rsp+B0h] [rbp-208h]
  _BYTE v57[24]; // [rsp+B8h] [rbp-200h] BYREF
  _QWORD v58[2]; // [rsp+D0h] [rbp-1E8h] BYREF
  int v59; // [rsp+E0h] [rbp-1D8h]
  HKEY hKey; // [rsp+E8h] [rbp-1D0h] BYREF
  unsigned int v61; // [rsp+F0h] [rbp-1C8h]
  char v62; // [rsp+100h] [rbp-1B8h] BYREF
  HKEY hkey; // [rsp+118h] [rbp-1A0h] BYREF
  int v64; // [rsp+120h] [rbp-198h]
  char v65; // [rsp+130h] [rbp-188h] BYREF
  HKEY v66; // [rsp+148h] [rbp-170h] BYREF
  int v67; // [rsp+150h] [rbp-168h]
  char v68; // [rsp+160h] [rbp-158h] BYREF
  _OWORD *v69; // [rsp+178h] [rbp-140h]
  _OWORD *v70; // [rsp+180h] [rbp-138h]
  _BYTE *v71; // [rsp+188h] [rbp-130h]
  __int64 v72; // [rsp+190h] [rbp-128h]
  _BYTE v73[24]; // [rsp+198h] [rbp-120h] BYREF
  _BYTE v74[32]; // [rsp+1B0h] [rbp-108h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+1D0h] [rbp-E8h] BYREF
  __m128i v76; // [rsp+1E0h] [rbp-D8h]
  LPCWSTR StringSid[4]; // [rsp+1F0h] [rbp-C8h] BYREF
  LPCWSTR v78[4]; // [rsp+210h] [rbp-A8h] BYREF
  _OWORD v79[2]; // [rsp+230h] [rbp-88h] BYREF
  LPCWSTR v80[4]; // [rsp+250h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v51 = a1;
  v45 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v45,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (unsigned __int16 *)&v45);
  v3 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    try
    {
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey, HKEY_LOCAL_MACHINE, v45);
      v58[0] = hKey;
      v58[1] = &v62;
      v33 = 0;
      v59 = 0;
      v34 = v61;
      v46 = v61;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        if ( v33 == v34 )
        {
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
          v36 = *(_QWORD *)(a1 + 56);
          if ( v36 )
          {
            LOBYTE(v35) = v36 != a1;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 32LL))(v36, v35);
            *(_QWORD *)(a1 + 56) = 0;
          }
          result = 0;
          goto LABEL_49;
        }
        NgcUtils::RegKeyIterator::Iterator::operator*(v58, StringSid);
        Sid = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &Sid,
          0);
        v8 = (const WCHAR *)StringSid;
        if ( StringSid[3] > (LPCWSTR)7 )
          v8 = StringSid[0];
        if ( !ConvertStringSidToSidW(v8, &Sid) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x3E8,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                        v9);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
          v13 = *(_QWORD *)(a1 + 56);
          if ( v13 )
          {
            LOBYTE(v11) = v13 != a1;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v11);
            *(_QWORD *)(a1 + 56) = 0;
          }
          result = LastError;
          goto LABEL_49;
        }
        LengthSid = GetLengthSid(Sid);
        std::vector<unsigned char>::vector<unsigned char>(v57, Sid, (char *)Sid + LengthSid);
        v15 = std::operator+<unsigned short>(v79, StringSid);
        std::operator+<unsigned short>(v80, v15);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
        v16 = (const WCHAR *)v80;
        if ( v80[3] > (LPCWSTR)7 )
          v16 = v80[0];
        NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v66, hKey, v16);
        v55[0] = v66;
        v55[1] = &v68;
        v17 = 0;
        v56 = 0;
        v18 = v67;
        v50 = v67;
LABEL_15:
        if ( v17 != v18 )
          break;
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v66);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v80);
        std::vector<unsigned char>::_Tidy(v57);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
        v59 = ++v33;
        v34 = v46;
      }
      NgcUtils::RegKeyIterator::Iterator::operator*(v55, v78);
      v19 = (const WCHAR *)v78;
      if ( v78[3] > (LPCWSTR)7 )
        v19 = v78[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, v66, v19);
      v53[0] = hkey;
      v53[1] = &v65;
      v20 = 0;
      v54 = 0;
      v21 = v64;
      for ( i = v64; ; v21 = i )
      {
        if ( v20 == v21 )
        {
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v78);
          v56 = ++v17;
          v18 = v50;
          goto LABEL_15;
        }
        NgcUtils::RegKeyIterator::Iterator::operator*(v53, lpSubKey);
        pvData = 0;
        pcbData = 4;
        v22 = (const WCHAR *)lpSubKey;
        if ( v76.m128i_i64[1] > 7uLL )
          v22 = lpSubKey[0];
        ValueW = RegGetValueW(hkey, v22, L"UserEntered", 0x10u, 0, &pvData, &pcbData);
        if ( ValueW )
        {
          v24 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x3FE,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                  (const char *)ValueW,
                  pdwTypea);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v78);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v66);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v80);
          std::vector<unsigned char>::_Tidy(v57);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
          v26 = *(_QWORD *)(a1 + 56);
          if ( v26 )
          {
            LOBYTE(v25) = v26 != a1;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 32LL))(v26, v25);
            *(_QWORD *)(a1 + 56) = 0;
          }
          result = v24;
          goto LABEL_49;
        }
        v27 = lpSubKey;
        if ( v76.m128i_i64[1] > 7uLL )
          v27 = (LPCWSTR *)lpSubKey[0];
        if ( !(unsigned int)_o__wcsicmp(v27, L"{9BF82404-AAD1-48E1-97D1-C0EC3B42B59A}") )
          std::wstring::_Assign<unsigned short>(lpSubKey, 0, 0);
        v42[0] = pvData != 0;
        v69 = v79;
        v79[0] = *(_OWORD *)lpSubKey;
        v79[1] = v76;
        v76 = si128;
        LOWORD(lpSubKey[0]) = 0;
        v70 = v79;
        v71 = v74;
        v28 = std::wstring::wstring(v74, v78);
        v72 = v28;
        v29 = std::vector<unsigned char>::vector<unsigned char>(v73, v57);
        v52 = v29;
        v30 = *(_QWORD *)(a1 + 56);
        if ( !v30 )
          std::_Xbad_function_call();
        v43 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _OWORD *, bool *))(*(_QWORD *)v30 + 16LL))(
                v30,
                v29,
                v28,
                v79,
                v42);
        std::vector<unsigned char>::_Tidy(v29);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v28);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        if ( v43 )
          break;
        v54 = ++v20;
      }
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v78);
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v66);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v80);
      std::vector<unsigned char>::_Tidy(v57);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
      v32 = *(_QWORD *)(a1 + 56);
      if ( v32 )
      {
        LOBYTE(v31) = v32 != a1;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 32LL))(v32, v31);
        *(_QWORD *)(a1 + 56) = 0;
      }
      result = 0;
    }
    catch ( ... )
    {
      v46 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x413,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
              v12);
      v37 = v51;
      v38 = *(_QWORD *)(v51 + 56);
      if ( v38 )
      {
        LOBYTE(v39) = v38 != v51;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, v39);
        *(_QWORD *)(v37 + 56) = 0;
      }
      result = v46;
    }
LABEL_49:
    ;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      pdwType);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
    v5 = *(_QWORD *)(a1 + 56);
    if ( v5 )
    {
      LOBYTE(v4) = v5 != a1;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, v4);
      *(_QWORD *)(a1 + 56) = 0;
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18008ca54  mov     rax, rsp
0x18008ca57  mov     [rax+10h], rbx
0x18008ca5b  mov     [rax+18h], rsi
0x18008ca5f  push    rdi
0x18008ca60  push    r12
0x18008ca62  push    r13
0x18008ca64  push    r14
0x18008ca66  push    r15
0x18008ca68  sub     rsp, 290h
0x18008ca6f  movaps  xmmword ptr [rax-38h], xmm6
0x18008ca73  mov     rax, cs:__security_cookie
0x18008ca7a  xor     rax, rsp
0x18008ca7d  mov     [rsp+2B8h+var_48], rax
0x18008ca85  mov     rdi, rcx
0x18008ca88  mov     [rsp+2B8h+var_240], rcx
0x18008ca8d  xor     ebx, ebx
0x18008ca8f  mov     [rsp+2B8h+var_260], rbx
0x18008ca94  xor     edx, edx
0x18008ca96  lea     rcx, [rsp+2B8h+var_260]
0x18008ca9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008caa0  lea     r9, [rsp+2B8h+var_260]; unsigned __int16 *
0x18008caa5  xor     r8d, r8d; unsigned __int16 *
0x18008caa8  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008caaf  lea     rcx, aNgccredprov; "NgcCredprov"
0x18008cab6  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18008cabb  mov     esi, eax
0x18008cabd  test    eax, eax
0x18008cabf  jns     short loc_18008CB0F
0x18008cac1  mov     rcx, [rsp+2B8h]; this
0x18008cac9  mov     r9d, eax; char *
0x18008cacc  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008cad3  mov     edx, 3DFh; void *
0x18008cad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cadd  nop
0x18008cade  lea     rcx, [rsp+2B8h+var_260]; void *
0x18008cae3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008cae8  nop
0x18008cae9  mov     rcx, [rdi+38h]
0x18008caed  test    rcx, rcx
0x18008caf0  jz      short loc_18008CB08
0x18008caf2  mov     rax, [rcx]
0x18008caf5  cmp     rcx, rdi
0x18008caf8  setnz   dl
0x18008cafb  mov     rax, [rax+20h]
0x18008caff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb04  mov     [rdi+38h], rbx
0x18008cb08  mov     eax, esi
0x18008cb0a  jmp     loc_18008D1B4
0x18008cb0f  mov     r8, [rsp+2B8h+var_260]; lpSubKey
0x18008cb14  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18008cb1b  lea     rcx, [rsp+2B8h+hKey]; this
0x18008cb23  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008cb28  nop
0x18008cb29  mov     rax, [rsp+2B8h+hKey]
0x18008cb31  mov     [rsp+2B8h+var_1E8], rax
0x18008cb39  lea     rax, [rsp+2B8h+var_1B8]
0x18008cb41  mov     [rsp+2B8h+var_1E0], rax
0x18008cb49  mov     r15d, ebx
0x18008cb4c  mov     [rsp+2B8h+var_1D8], ebx
0x18008cb53  mov     eax, [rsp+2B8h+var_1C8]
0x18008cb5a  mov     [rsp+2B8h+var_258], eax
0x18008cb5e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18008cb66  cmp     r15d, eax
0x18008cb69  jz      loc_18008D14E
0x18008cb6f  lea     rdx, [rsp+2B8h+StringSid]
0x18008cb77  lea     rcx, [rsp+2B8h+var_1E8]
0x18008cb7f  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008cb84  nop
0x18008cb85  mov     [rsp+2B8h+Sid], rbx
0x18008cb8a  xor     edx, edx
0x18008cb8c  lea     rcx, [rsp+2B8h+Sid]
0x18008cb91  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18008cb96  lea     rcx, [rsp+2B8h+StringSid]
0x18008cb9e  cmp     [rsp+2B8h+var_B0], 7
0x18008cba7  cmova   rcx, [rsp+2B8h+StringSid]; StringSid
0x18008cbb0  lea     rdx, [rsp+2B8h+Sid]; Sid
0x18008cbb5  call    cs:__imp_ConvertStringSidToSidW
0x18008cbbb  test    eax, eax
0x18008cbbd  jnz     short loc_18008CC32
0x18008cbbf  mov     rcx, [rsp+2B8h]; this
0x18008cbc7  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008cbce  mov     edx, 3E8h; void *
0x18008cbd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008cbd8  mov     esi, eax
0x18008cbda  lea     rcx, [rsp+2B8h+Sid]; void *
0x18008cbdf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008cbe4  nop
0x18008cbe5  lea     rcx, [rsp+2B8h+StringSid]
0x18008cbed  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008cbf2  nop
0x18008cbf3  lea     rcx, [rsp+2B8h+hKey]; this
0x18008cbfb  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008cc00  nop
0x18008cc01  lea     rcx, [rsp+2B8h+var_260]; void *
0x18008cc06  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008cc0b  nop
0x18008cc0c  mov     rcx, [rdi+38h]
0x18008cc10  test    rcx, rcx
0x18008cc13  jz      short loc_18008CC2B
0x18008cc15  mov     rax, [rcx]
0x18008cc18  cmp     rcx, rdi
0x18008cc1b  setnz   dl
0x18008cc1e  mov     rax, [rax+20h]
0x18008cc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc27  mov     [rdi+38h], rbx
0x18008cc2b  mov     eax, esi
0x18008cc2d  jmp     loc_18008D1B4
0x18008cc32  mov     rcx, [rsp+2B8h+Sid]; pSid
0x18008cc37  call    cs:__imp_GetLengthSid
0x18008cc3d  mov     r8d, eax
0x18008cc40  mov     rdx, [rsp+2B8h+Sid]
0x18008cc45  add     r8, rdx
0x18008cc48  lea     rcx, [rsp+2B8h+var_200]
0x18008cc50  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x18008cc55  nop
0x18008cc56  lea     rdx, [rsp+2B8h+StringSid]
0x18008cc5e  lea     rcx, [rsp+2B8h+var_88]
0x18008cc66  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18008cc6b  nop
0x18008cc6c  mov     rdx, rax
0x18008cc6f  lea     rcx, [rsp+2B8h+var_68]
0x18008cc77  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18008cc7c  nop
0x18008cc7d  lea     rcx, [rsp+2B8h+var_88]
0x18008cc85  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008cc8a  lea     r8, [rsp+2B8h+var_68]
0x18008cc92  cmp     [rsp+2B8h+var_50], 7
0x18008cc9b  cmova   r8, [rsp+2B8h+var_68]; lpSubKey
0x18008cca4  mov     rdx, [rsp+2B8h+hKey]; hKey
0x18008ccac  lea     rcx, [rsp+2B8h+var_170]; this
0x18008ccb4  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008ccb9  nop
0x18008ccba  mov     rax, [rsp+2B8h+var_170]
0x18008ccc2  mov     [rsp+2B8h+var_218], rax
0x18008ccca  lea     rax, [rsp+2B8h+var_158]
0x18008ccd2  mov     [rsp+2B8h+var_210], rax
0x18008ccda  mov     esi, ebx
0x18008ccdc  mov     [rsp+2B8h+var_208], ebx
0x18008cce3  mov     eax, [rsp+2B8h+var_168]
0x18008ccea  mov     [rsp+2B8h+var_248], eax
0x18008ccee  cmp     esi, eax
0x18008ccf0  jz      loc_18008D0F8
0x18008ccf6  lea     rdx, [rsp+2B8h+var_A8]
0x18008ccfe  lea     rcx, [rsp+2B8h+var_218]
0x18008cd06  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008cd0b  nop
0x18008cd0c  lea     r8, [rsp+2B8h+var_A8]
0x18008cd14  cmp     [rsp+2B8h+var_90], 7
0x18008cd1d  cmova   r8, [rsp+2B8h+var_A8]; lpSubKey
0x18008cd26  mov     rdx, [rsp+2B8h+var_170]; hKey
0x18008cd2e  lea     rcx, [rsp+2B8h+hkey]; this
0x18008cd36  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008cd3b  nop
0x18008cd3c  mov     rax, [rsp+2B8h+hkey]
0x18008cd44  mov     [rsp+2B8h+var_230], rax
0x18008cd4c  lea     rax, [rsp+2B8h+var_188]
0x18008cd54  mov     [rsp+2B8h+var_228], rax
0x18008cd5c  mov     r14d, ebx
0x18008cd5f  mov     [rsp+2B8h+var_220], ebx
0x18008cd66  mov     eax, [rsp+2B8h+var_198]
0x18008cd6d  mov     [rsp+2B8h+var_24C], eax
0x18008cd71  cmp     r14d, eax
0x18008cd74  jz      loc_18008D0CB
0x18008cd7a  lea     rdx, [rsp+2B8h+lpSubKey]
0x18008cd82  lea     rcx, [rsp+2B8h+var_230]
0x18008cd8a  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008cd8f  nop
0x18008cd90  mov     [rsp+2B8h+var_254], ebx
0x18008cd94  mov     [rsp+2B8h+var_250], 4
0x18008cd9c  lea     rdx, [rsp+2B8h+lpSubKey]
0x18008cda4  cmp     [rsp+2B8h+var_D0], 7
0x18008cdad  cmova   rdx, [rsp+2B8h+lpSubKey]; lpSubKey
0x18008cdb6  lea     rax, [rsp+2B8h+var_250]
0x18008cdbb  mov     [rsp+2B8h+pcbData], rax; pcbData
0x18008cdc0  lea     rax, [rsp+2B8h+var_254]
0x18008cdc5  mov     [rsp+2B8h+pvData], rax; pvData
0x18008cdca  mov     [rsp+2B8h+pdwType], rbx; unsigned int
0x18008cdcf  mov     r9d, 10h; dwFlags
0x18008cdd5  lea     r8, aUserentered; "UserEntered"
0x18008cddc  mov     rcx, [rsp+2B8h+hkey]; hkey
0x18008cde4  call    cs:__imp_RegGetValueW
0x18008cdea  test    eax, eax
0x18008cdec  jz      loc_18008CEBC
0x18008cdf2  mov     rcx, [rsp+2B8h]; this
0x18008cdfa  mov     r9d, eax; char *
0x18008cdfd  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008ce04  mov     edx, 3FEh; void *
0x18008ce09  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008ce0e  mov     esi, eax
0x18008ce10  lea     rcx, [rsp+2B8h+lpSubKey]
0x18008ce18  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008ce1d  nop
0x18008ce1e  lea     rcx, [rsp+2B8h+hkey]; this
0x18008ce26  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008ce2b  nop
0x18008ce2c  lea     rcx, [rsp+2B8h+var_A8]
0x18008ce34  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008ce39  nop
0x18008ce3a  lea     rcx, [rsp+2B8h+var_170]; this
0x18008ce42  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008ce47  nop
0x18008ce48  lea     rcx, [rsp+2B8h+var_68]
0x18008ce50  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008ce55  nop
0x18008ce56  lea     rcx, [rsp+2B8h+var_200]
0x18008ce5e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008ce63  nop
0x18008ce64  lea     rcx, [rsp+2B8h+Sid]; void *
0x18008ce69  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008ce6e  nop
0x18008ce6f  lea     rcx, [rsp+2B8h+StringSid]
0x18008ce77  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008ce7c  nop
0x18008ce7d  lea     rcx, [rsp+2B8h+hKey]; this
0x18008ce85  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008ce8a  nop
0x18008ce8b  lea     rcx, [rsp+2B8h+var_260]; void *
0x18008ce90  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008ce95  nop
0x18008ce96  mov     rcx, [rdi+38h]
0x18008ce9a  test    rcx, rcx
0x18008ce9d  jz      short loc_18008CEB5
0x18008ce9f  mov     rax, [rcx]
0x18008cea2  cmp     rcx, rdi
0x18008cea5  setnz   dl
0x18008cea8  mov     rax, [rax+20h]
0x18008ceac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ceb1  mov     [rdi+38h], rbx
0x18008ceb5  mov     eax, esi
0x18008ceb7  jmp     loc_18008D1B4
0x18008cebc  lea     rcx, [rsp+2B8h+lpSubKey]
0x18008cec4  cmp     [rsp+2B8h+var_D0], 7
0x18008cecd  cmova   rcx, [rsp+2B8h+lpSubKey]
0x18008ced6  lea     rdx, a9bf82404Aad148; "{9BF82404-AAD1-48E1-97D1-C0EC3B42B59A}"
0x18008cedd  call    cs:__imp__o__wcsicmp
0x18008cee3  test    eax, eax
0x18008cee5  jnz     short loc_18008CEF9
0x18008cee7  xor     r8d, r8d
0x18008ceea  xor     edx, edx
0x18008ceec  lea     rcx, [rsp+2B8h+lpSubKey]
0x18008cef4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008cef9  cmp     [rsp+2B8h+var_254], ebx
0x18008cefd  setnz   [rsp+2B8h+var_278]
0x18008cf02  lea     rax, [rsp+2B8h+var_88]
0x18008cf0a  mov     [rsp+2B8h+var_140], rax
0x18008cf12  movups  xmm0, xmmword ptr [rsp+2B8h+lpSubKey]
0x18008cf1a  movups  [rsp+2B8h+var_88], xmm0
0x18008cf22  movups  xmm1, xmmword ptr [rsp+1E0h]
0x18008cf2a  movups  [rsp+2B8h+var_78], xmm1
0x18008cf32  movdqu  xmmword ptr [rsp+1E0h], xmm6
0x18008cf3b  mov     word ptr [rsp+2B8h+lpSubKey], bx
0x18008cf43  lea     rax, [rsp+2B8h+var_88]
0x18008cf4b  mov     [rsp+2B8h+var_138], rax
0x18008cf53  lea     rax, [rsp+2B8h+var_108]
0x18008cf5b  mov     [rsp+2B8h+var_130], rax
0x18008cf63  lea     rdx, [rsp+2B8h+var_A8]
0x18008cf6b  lea     rcx, [rsp+2B8h+var_108]
0x18008cf73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008cf78  mov     r13, rax
0x18008cf7b  mov     [rsp+2B8h+var_128], rax
0x18008cf83  lea     rdx, [rsp+2B8h+var_200]
0x18008cf8b  lea     rcx, [rsp+2B8h+var_120]
0x18008cf93  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18008cf98  mov     r12, rax
0x18008cf9b  mov     [rsp+2B8h+var_238], rax
0x18008cfa3  mov     al, [rsp+2B8h+var_278]
0x18008cfa7  mov     [rsp+2B8h+var_278], al
0x18008cfab  mov     rcx, [rdi+38h]
0x18008cfaf  test    rcx, rcx
0x18008cfb2  jnz     short loc_18008CFBA
0x18008cfb4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18008cfba  mov     rax, [rcx]
0x18008cfbd  lea     rdx, [rsp+2B8h+var_278]
0x18008cfc2  mov     [rsp+2B8h+pdwType], rdx
0x18008cfc7  lea     r9, [rsp+2B8h+var_88]
0x18008cfcf  mov     r8, r13
0x18008cfd2  mov     rdx, r12
0x18008cfd5  mov     rax, [rax+10h]
0x18008cfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cfde  mov     [rsp+2B8h+var_270], al
0x18008cfe2  mov     rcx, r12
0x18008cfe5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008cfea  nop
0x18008cfeb  mov     rcx, r13
0x18008cfee  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008cff3  nop
0x18008cff4  lea     rcx, [rsp+2B8h+var_88]
0x18008cffc  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008d001  nop
0x18008d002  lea     rcx, [rsp+2B8h+lpSubKey]
0x18008d00a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008d00f  cmp     [rsp+2B8h+var_270], bl
0x18008d013  jz      loc_18008D0B7
0x18008d019  lea     rcx, [rsp+2B8h+hkey]; this
0x18008d021  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008d026  nop
0x18008d027  lea     rcx, [rsp+2B8h+var_A8]
0x18008d02f  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008d034  nop
0x18008d035  lea     rcx, [rsp+2B8h+var_170]; this
  ... truncated ...
```
