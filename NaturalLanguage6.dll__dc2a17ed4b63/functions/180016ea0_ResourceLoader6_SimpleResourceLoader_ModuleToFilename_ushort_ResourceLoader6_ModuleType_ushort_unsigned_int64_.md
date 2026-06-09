# ResourceLoader6::SimpleResourceLoader::ModuleToFilename(ushort,ResourceLoader6::ModuleType,ushort *,unsigned __int64,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *)

- ea: `0x180016ea0`
- end: `0x180017852`
- name: `?ModuleToFilename@SimpleResourceLoader@ResourceLoader6@@MEAA_NGW4ModuleType@2@PEAG_KPEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@@Z`
- size: `2482`
- prototype: `char __fastcall(__int64, unsigned __int16, int, unsigned __int16 *, unsigned __int64, IID *lpiid)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005190`
- `0x1800162e4`
- `0x180016ea0`
- `0x180017858`
- `0x18001a07c`
- `0x18001a0d8`
- `0x18002ee48`
- `0x180035640`
- `0x180038a4c`
- `0x18003ed6c`
- `0x180041288`
- `0x1800418f4`
- `0x180041b1c`
- `0x180049618`
- `0x18004997c`
- `0x180049e8c`
- `0x18004af2c`
- `0x18004cb68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001731e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001762f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001764d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001731e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001762f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001764d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800171a6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800173f6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800171a6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800173f6`

## string_xrefs

- `0x180016f10`: `NLSGrammars%04x.dll`
- `0x180016f51`: `NLSModels%04x.dll`
- `0x180016f9e`: `NLSLexicons%04x.dll`
- `0x1800171e4`: `HKEY_CLASSES_ROOT\CLSID\`
- `0x18001749c`: `WBDLLPathOverride`
- `0x18001748c`: `StemmerDLLPathOverride`
- `0x180017437`: `NLSData%04x.dll`
- `0x180017804`: `spell.dll`
- `0x1800177b6`: `gram.dll`
- `0x180017768`: `hyph.dll`
- `0x18001771a`: `thes.dll`
- `0x18001769d`: `bthes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ResourceLoader6::SimpleResourceLoader::ModuleToFilename(
        __int64 a1,
        unsigned __int16 a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        IID *lpiid)
{
  unsigned __int16 *v6; // rdi
  unsigned __int16 v7; // r14
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  const unsigned __int16 *v12; // rcx
  HKEY v13; // rcx
  __int16 v14; // dx
  __int16 v15; // si
  const struct _variant_t *Value; // rax
  const unsigned __int16 *v17; // r8
  int v18; // eax
  const OLECHAR *v19; // rcx
  HRESULT v20; // eax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  const unsigned __int16 *v24; // rcx
  const wchar_t *v25; // rbx
  const struct _variant_t *DefaultValue; // rax
  const unsigned __int16 *v27; // r8
  int v28; // eax
  const OLECHAR *v29; // rcx
  HRESULT v30; // eax
  const unsigned __int16 *v31; // r13
  unsigned __int16 v32; // r15
  unsigned __int64 i; // r12
  __int64 v34; // rdx
  const unsigned __int16 **v35; // rbx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // r8d
  int v39; // r8d
  int v40; // r8d
  unsigned __int16 v41; // [rsp+30h] [rbp-4F8h]
  const unsigned __int16 **v42; // [rsp+38h] [rbp-4F0h] BYREF
  _QWORD *v43; // [rsp+40h] [rbp-4E8h] BYREF
  const unsigned __int16 **v44; // [rsp+48h] [rbp-4E0h] BYREF
  const unsigned __int16 **v45; // [rsp+50h] [rbp-4D8h] BYREF
  HKEY hKey[2]; // [rsp+58h] [rbp-4D0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-4C0h] BYREF
  int v48; // [rsp+70h] [rbp-4B8h]
  HKEY v49[2]; // [rsp+78h] [rbp-4B0h] BYREF
  const unsigned __int16 *v50; // [rsp+88h] [rbp-4A0h]
  char v51[8]; // [rsp+90h] [rbp-498h] BYREF
  const wchar_t *v52; // [rsp+98h] [rbp-490h]
  unsigned __int64 v53; // [rsp+A0h] [rbp-488h]
  _WORD v54[12]; // [rsp+A8h] [rbp-480h] BYREF
  char v55[8]; // [rsp+C0h] [rbp-468h] BYREF
  char v56[8]; // [rsp+C8h] [rbp-460h] BYREF
  char v57[8]; // [rsp+D0h] [rbp-458h] BYREF
  HKEY v58[2]; // [rsp+D8h] [rbp-450h] BYREF
  VARIANTARG v59; // [rsp+E8h] [rbp-440h] BYREF
  __int64 v60; // [rsp+100h] [rbp-428h]
  _com_error *v61; // [rsp+108h] [rbp-420h] BYREF
  VARIANTARG v62; // [rsp+110h] [rbp-418h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+128h] [rbp-400h] BYREF
  _BYTE v64[64]; // [rsp+168h] [rbp-3C0h] BYREF
  _BYTE v65[64]; // [rsp+1A8h] [rbp-380h] BYREF
  _BYTE v66[64]; // [rsp+1E8h] [rbp-340h] BYREF
  _BYTE v67[64]; // [rsp+228h] [rbp-300h] BYREF
  _BYTE v68[64]; // [rsp+268h] [rbp-2C0h] BYREF
  _BYTE v69[64]; // [rsp+2A8h] [rbp-280h] BYREF
  _BYTE v70[64]; // [rsp+2E8h] [rbp-240h] BYREF
  _BYTE v71[64]; // [rsp+328h] [rbp-200h] BYREF
  _BYTE v72[64]; // [rsp+368h] [rbp-1C0h] BYREF
  _BYTE v73[64]; // [rsp+3A8h] [rbp-180h] BYREF
  _BYTE v74[64]; // [rsp+3E8h] [rbp-140h] BYREF
  _BYTE v75[64]; // [rsp+428h] [rbp-100h] BYREF
  _BYTE v76[64]; // [rsp+468h] [rbp-C0h] BYREF
  _BYTE v77[128]; // [rsp+4A8h] [rbp-80h] BYREF
  const void *retaddr; // [rsp+528h] [rbp+0h]
  __int64 v79; // [rsp+530h] [rbp+8h]
  __int16 v81; // [rsp+540h] [rbp+18h]

  v79 = a1;
  v60 = -2;
  v6 = a4;
  v7 = a2;
  if ( a3 == 259 )
  {
    if ( StringCchPrintfW(a4, a5, L"NLSLexicons%04x.dll", a2) < 0 )
    {
      CNLException::CNLException((CNLException *)v71, -2147467259, retaddr);
      throw (CNLException *)v71;
    }
    return 0;
  }
  if ( a3 > 259 )
  {
    v37 = a3 - 512;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            if ( v40 != 1 )
              goto LABEL_85;
            if ( StringCchPrintfW(a4, a5, L"bthes.dll") < 0 )
            {
              CNLException::CNLException((CNLException *)v73, -2147467259, retaddr);
              throw (CNLException *)v73;
            }
          }
          else if ( StringCchPrintfW(a4, a5, L"thes.dll") < 0 )
          {
            CNLException::CNLException((CNLException *)v74, -2147467259, retaddr);
            throw (CNLException *)v74;
          }
        }
        else if ( StringCchPrintfW(a4, a5, L"hyph.dll") < 0 )
        {
          CNLException::CNLException((CNLException *)v75, -2147467259, retaddr);
          throw (CNLException *)v75;
        }
      }
      else if ( StringCchPrintfW(a4, a5, L"gram.dll") < 0 )
      {
        CNLException::CNLException((CNLException *)v76, -2147467259, retaddr);
        throw (CNLException *)v76;
      }
    }
    else if ( StringCchPrintfW(a4, a5, L"spell.dll") < 0 )
    {
      CNLException::CNLException((CNLException *)v77, -2147467259, retaddr);
      throw (CNLException *)v77;
    }
  }
  else
  {
    if ( a3 )
    {
      v8 = a3 - 1;
      if ( v8 )
      {
        v9 = v8 - 255;
        if ( !v9 )
        {
          if ( StringCchPrintfW(a4, a5, L"NLSData%04x.dll", a2) < 0 )
          {
            CNLException::CNLException((CNLException *)v65, -2147467259, retaddr);
            throw (CNLException *)v65;
          }
          return 0;
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          if ( StringCchPrintfW(a4, a5, L"NLSGrammars%04x.dll", a2) < 0 )
          {
            CNLException::CNLException((CNLException *)v64, -2147467259, retaddr);
            throw (CNLException *)v64;
          }
          return 0;
        }
        if ( v10 == 1 )
        {
          if ( StringCchPrintfW(a4, a5, L"NLSModels%04x.dll", a2) < 0 )
          {
            CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
            throw (CNLException *)pExceptionObject;
          }
          return 0;
        }
LABEL_85:
        CNLException::CNLException((CNLException *)v72, -2147467259, retaddr);
        throw (CNLException *)v72;
      }
      v25 = L"StemmerClass";
      v31 = L"StemmerDLLPathOverride";
    }
    else
    {
      v25 = L"WBreakerClass";
      v31 = L"WBDLLPathOverride";
    }
    v32 = a2;
    v50 = v31;
    v52 = v25;
    for ( i = 0; ; ++i )
    {
      v53 = i;
      v34 = *(_QWORD *)(a1 + 40);
      if ( i >= (*(_QWORD *)(a1 + 48) - v34) >> 5 )
        break;
      v12 = (const unsigned __int16 *)(v34 + 32 * i);
      if ( *((_QWORD *)v12 + 3) >= 8u )
        v12 = *(const unsigned __int16 **)v12;
      v13 = NLG::RegistryKey::OpenKey(v12, 0);
      v49[0] = v13;
      if ( v13 )
      {
        v14 = -1;
        v15 = v7 | 0x400;
        if ( v32 != (v7 & 0x3FF) )
          v15 = v32;
        v81 = v15;
        v41 = v32;
        while ( v15 != v14 )
        {
          v54[0] = 3;
          v54[4] = v15;
          v54[5] = 0;
          v47 = 0;
          NLG::RegistryKey::FindSubKeyWithValue(v49, hKey, v54);
          if ( hKey[0] )
          {
            Value = (const struct _variant_t *)NLG::RegistryKey::GetValue(hKey, &v62, v25);
            _bstr_t::_bstr_t((_bstr_t *)&v43, Value);
            _variant_t::~_variant_t(&v62);
            if ( !_bstr_t::length((_bstr_t *)&v43) )
            {
              CNLException::CNLException((CNLException *)v66, -2147467259, retaddr);
              throw (CNLException *)v66;
            }
            v35 = 0;
            v42 = 0;
            try
            {
              if ( NLG::RegistryKey::ContainsValueName((NLG::RegistryKey *)hKey, v31) )
              {
                v36 = NLG::RegistryKey::GetValue(hKey, &v59, v31);
                _bstr_t::operator=(&v42, v36);
                _variant_t::~_variant_t(&v59);
                v35 = v42;
              }
            }
            catch ( _com_error *v61 )
            {
              ImxTraceCatch(1, *((unsigned int *)v61 + 2), retaddr);
              v6 = a4;
              v7 = a2;
              v31 = v50;
              i = v53;
              v15 = v81;
              v35 = v42;
              v32 = v41;
            }
            if ( _bstr_t::length((_bstr_t *)&v42) )
            {
              if ( v35 )
                v17 = *v35;
              else
                v17 = 0;
              v18 = StringCchCopyW(v6, a5, v17);
              if ( v18 < 0 )
              {
                CNLException::CNLException((CNLException *)v67, v18, retaddr);
                throw (CNLException *)v67;
              }
              if ( lpiid )
              {
                v19 = v43 ? (const OLECHAR *)*v43 : 0LL;
                v20 = IIDFromString(v19, lpiid);
                if ( v20 < 0 )
                {
                  CNLException::CNLException((CNLException *)v68, v20, retaddr);
                  throw (CNLException *)v68;
                }
              }
LABEL_71:
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v42);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v43);
              if ( hKey[0] )
              {
                RegCloseKey(hKey[0]);
                hKey[0] = 0;
              }
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v47);
              _variant_t::~_variant_t((VARIANTARG *)v54);
              if ( v49[0] )
              {
                RegCloseKey(v49[0]);
                v49[0] = 0;
              }
              return 0;
            }
            ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
              (_bstr_t *)&v44,
              L"HKEY_CLASSES_ROOT\\CLSID\\");
            ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)((_bstr_t *)&v45, L"\\");
            v21 = _bstr_t::operator+(&v44, v57, &v45);
            v22 = _bstr_t::operator+(v21, v56, &v43);
            ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
              (_bstr_t *)v51,
              L"\\InprocServer32");
            v23 = _bstr_t::operator+(v22, v55, v51);
            _bstr_t::operator=(&v44, v23);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v55);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v51);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v56);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v57);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v45);
            if ( v44 )
              v24 = *v44;
            else
              v24 = 0;
            v58[0] = NLG::RegistryKey::OpenKey(v24, 0);
            if ( v58[0] )
            {
              DefaultValue = (const struct _variant_t *)NLG::RegistryKey::GetDefaultValue(v58, &v59);
              _bstr_t::_bstr_t((_bstr_t *)&v45, DefaultValue);
              _variant_t::~_variant_t(&v59);
              if ( v45 )
                v27 = *v45;
              else
                v27 = 0;
              v28 = StringCchCopyW(v6, a5, v27);
              if ( v28 < 0 )
              {
                CNLException::CNLException((CNLException *)v69, v28, retaddr);
                throw (CNLException *)v69;
              }
              if ( lpiid )
              {
                v29 = v43 ? (const OLECHAR *)*v43 : 0LL;
                v30 = IIDFromString(v29, lpiid);
                if ( v30 < 0 )
                {
                  CNLException::CNLException((CNLException *)v70, v30, retaddr);
                  throw (CNLException *)v70;
                }
              }
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v45);
              if ( v58[0] )
              {
                RegCloseKey(v58[0]);
                v58[0] = 0;
              }
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v44);
              goto LABEL_71;
            }
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v44);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v42);
            ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v43);
          }
          LOWORD(v48) = v15;
          v15 &= 0x3FFu;
          v81 = v15;
          if ( hKey[0] )
          {
            RegCloseKey(hKey[0]);
            hKey[0] = 0;
          }
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v47);
          _variant_t::~_variant_t((VARIANTARG *)v54);
          v13 = v49[0];
          v25 = v52;
          v14 = v48;
        }
      }
      if ( v13 )
      {
        RegCloseKey(v13);
        v49[0] = 0;
      }
      a1 = v79;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180016ea0  mov     rax, rsp
0x180016ea3  mov     [rax+20h], r9
0x180016ea7  mov     [rax+10h], dx
0x180016eab  mov     [rax+8], rcx
0x180016eaf  push    rbx
0x180016eb0  push    rsi
0x180016eb1  push    rdi
0x180016eb2  push    r12
0x180016eb4  push    r13
0x180016eb6  push    r14
0x180016eb8  push    r15
0x180016eba  sub     rsp, 4F0h
0x180016ec1  mov     qword ptr [rax-428h], 0FFFFFFFFFFFFFFFEh
0x180016ecc  mov     rdi, r9
0x180016ecf  movzx   r14d, dx
0x180016ed3  mov     eax, 103h
0x180016ed8  cmp     r8d, eax
0x180016edb  jz      loc_180016F9B
0x180016ee1  jg      loc_18001766C
0x180016ee7  test    r8d, r8d
0x180016eea  jz      loc_180017495
0x180016ef0  sub     r8d, 1
0x180016ef4  jz      loc_180017485
0x180016efa  sub     r8d, 0FFh
0x180016f01  jz      loc_180017434
0x180016f07  sub     r8d, 1
0x180016f0b  jnz     short loc_180016F44
0x180016f0d  mov     r9d, r14d
0x180016f10  lea     r8, aNlsgrammars04x; "NLSGrammars%04x.dll"
0x180016f17  mov     rdx, [rsp+528h+arg_20]; unsigned __int64
0x180016f1f  mov     rcx, rdi; unsigned __int16 *
0x180016f22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016f27  test    eax, eax
0x180016f29  js      loc_180016FEC
0x180016f2f  xor     al, al
0x180016f31  add     rsp, 4F0h
0x180016f38  pop     r15
0x180016f3a  pop     r14
0x180016f3c  pop     r13
0x180016f3e  pop     r12
0x180016f40  pop     rdi
0x180016f41  pop     rsi
0x180016f42  pop     rbx
0x180016f43  retn
0x180016f44  cmp     r8d, 1
0x180016f48  jnz     loc_1800176EB
0x180016f4e  mov     r9d, r14d
0x180016f51  lea     r8, aNlsmodels04xDl; "NLSModels%04x.dll"
0x180016f58  mov     rdx, [rsp+528h+arg_20]; unsigned __int64
0x180016f60  mov     rcx, rdi; unsigned __int16 *
0x180016f63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016f68  test    eax, eax
0x180016f6a  jns     short loc_180016F2F
0x180016f6c  mov     r8, [rsp+528h]; void *
0x180016f74  mov     edx, 80004005h; int
0x180016f79  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180016f81  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180016f86  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180016f8d  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180016f95  call    _CxxThrowException_0
0x180016f9b  mov     r9d, r14d
0x180016f9e  lea     r8, aNlslexicons04x; "NLSLexicons%04x.dll"
0x180016fa5  mov     rdx, [rsp+528h+arg_20]; unsigned __int64
0x180016fad  mov     rcx, rdi; unsigned __int16 *
0x180016fb0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016fb5  test    eax, eax
0x180016fb7  jns     loc_180016F2F
0x180016fbd  mov     r8, [rsp+528h]; void *
0x180016fc5  mov     edx, 80004005h; int
0x180016fca  lea     rcx, [rsp+528h+var_200]; this
0x180016fd2  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180016fd7  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180016fde  lea     rcx, [rsp+528h+var_200]; pExceptionObject
0x180016fe6  call    _CxxThrowException_0
0x180016fec  mov     r8, [rsp+528h]; void *
0x180016ff4  mov     edx, 80004005h; int
0x180016ff9  lea     rcx, [rsp+528h+var_3C0]; this
0x180017001  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180017006  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18001700d  lea     rcx, [rsp+528h+var_3C0]; pExceptionObject
0x180017015  call    _CxxThrowException_0
0x18001701b  mov     rcx, r12
0x18001701e  shl     rcx, 5
0x180017022  add     rcx, rdx
0x180017025  cmp     qword ptr [rcx+18h], 8
0x18001702a  jb      short loc_18001702F
0x18001702c  mov     rcx, [rcx]; unsigned __int16 *
0x18001702f  xor     edx, edx; HKEY
0x180017031  call    ?OpenKey@RegistryKey@NLG@@KAPEAUHKEY__@@PEBGPEAU3@@Z; NLG::RegistryKey::OpenKey(ushort const *,HKEY__ *)
0x180017036  mov     rcx, rax; hKey
0x180017039  mov     [rsp+528h+var_4B0], rax
0x18001703e  test    rax, rax
0x180017041  jz      loc_180017648
0x180017047  mov     edx, 0FFFFh
0x18001704c  movzx   eax, r14w
0x180017050  and     ax, si
0x180017053  movzx   esi, r14w
0x180017057  or      si, 400h
0x18001705c  cmp     r15w, ax
0x180017060  cmovnz  si, r15w
0x180017065  mov     [rsp+528h+arg_10], si
0x18001706d  mov     [rsp+528h+var_4F8], r15w
0x180017073  cmp     si, dx
0x180017076  jz      loc_180017643
0x18001707c  movzx   eax, si
0x18001707f  mov     ecx, 3
0x180017084  mov     [rsp+528h+var_480], cx
0x18001708c  mov     [rsp+528h+var_478], si
0x180017094  shr     eax, 10h
0x180017097  mov     [rsp+528h+var_476], ax
0x18001709f  mov     [rsp+528h+var_4C0], 0
0x1800170a8  lea     rax, [rsp+528h+var_4C0]
0x1800170ad  mov     [rsp+528h+var_508], rax
0x1800170b2  lea     r8, [rsp+528h+var_480]
0x1800170ba  lea     rdx, [rsp+528h+hKey]
0x1800170bf  lea     rcx, [rsp+528h+var_4B0]
0x1800170c4  call    ?FindSubKeyWithValue@RegistryKey@NLG@@QEBA?AV12@AEAV_variant_t@@PEAV12@PEAV_bstr_t@@@Z; NLG::RegistryKey::FindSubKeyWithValue(_variant_t &,NLG::RegistryKey *,_bstr_t *)
0x1800170c9  nop
0x1800170ca  cmp     [rsp+528h+hKey], 0
0x1800170d0  jz      loc_1800172FF
0x1800170d6  mov     r8, rbx
0x1800170d9  lea     rdx, [rsp+528h+var_418]
0x1800170e1  lea     rcx, [rsp+528h+hKey]
0x1800170e6  call    ?GetValue@RegistryKey@NLG@@QEBA?AV_variant_t@@PEBG@Z; NLG::RegistryKey::GetValue(ushort const *)
0x1800170eb  nop
0x1800170ec  mov     rdx, rax; struct _variant_t *
0x1800170ef  lea     rcx, [rsp+528h+var_4E8]; this
0x1800170f4  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x1800170f9  nop
0x1800170fa  lea     rcx, [rsp+528h+var_418]; this
0x180017102  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017107  lea     rcx, [rsp+528h+var_4E8]; this
0x18001710c  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180017111  test    eax, eax
0x180017113  jnz     loc_1800174E6
0x180017119  mov     r8, [rsp+528h]; void *
0x180017121  mov     edx, 80004005h; int
0x180017126  lea     rcx, [rsp+528h+var_340]; this
0x18001712e  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180017133  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18001713a  lea     rcx, [rsp+528h+var_340]; pExceptionObject
0x180017142  call    _CxxThrowException_0
0x180017148  test    rbx, rbx
0x18001714b  jz      short loc_180017194
0x18001714d  mov     r8, [rbx]; unsigned __int16 *
0x180017150  mov     rdx, [rsp+528h+arg_20]; unsigned __int64
0x180017158  mov     rcx, rdi; unsigned __int16 *
0x18001715b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017160  test    eax, eax
0x180017162  jns     loc_180017581
0x180017168  mov     r8, [rsp+528h]; void *
0x180017170  mov     edx, eax; int
0x180017172  lea     rcx, [rsp+528h+var_300]; this
0x18001717a  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18001717f  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180017186  lea     rcx, [rsp+528h+var_300]; pExceptionObject
0x18001718e  call    _CxxThrowException_0
0x180017194  xor     r8d, r8d
0x180017197  jmp     short loc_180017150
0x180017199  mov     rax, [rsp+528h+var_4E8]
0x18001719e  test    rax, rax
0x1800171a1  jz      short loc_1800171E0
0x1800171a3  mov     rcx, [rax]; lpsz
0x1800171a6  call    cs:__imp_IIDFromString
0x1800171ac  test    eax, eax
0x1800171ae  jns     loc_1800175D9
0x1800171b4  mov     r8, [rsp+528h]; void *
0x1800171bc  mov     edx, eax; int
0x1800171be  lea     rcx, [rsp+528h+var_2C0]; this
0x1800171c6  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800171cb  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800171d2  lea     rcx, [rsp+528h+var_2C0]; pExceptionObject
0x1800171da  call    _CxxThrowException_0
0x1800171e0  xor     ecx, ecx
0x1800171e2  jmp     short loc_1800171A6
0x1800171e4  lea     rdx, aHkeyClassesRoo_0; "HKEY_CLASSES_ROOT\\CLSID\\"
0x1800171eb  lea     rcx, [rsp+528h+var_4E0]; this
0x1800171f0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800171f5  nop
0x1800171f6  lea     rdx, asc_1800BE1AC; "\\"
0x1800171fd  lea     rcx, [rsp+528h+var_4D8]; this
0x180017202  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017207  nop
0x180017208  lea     r8, [rsp+528h+var_4D8]
0x18001720d  lea     rdx, [rsp+528h+var_458]
0x180017215  lea     rcx, [rsp+528h+var_4E0]
0x18001721a  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18001721f  nop
0x180017220  lea     r8, [rsp+528h+var_4E8]
0x180017225  lea     rdx, [rsp+528h+var_460]
0x18001722d  mov     rcx, rax
0x180017230  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180017235  mov     rbx, rax
0x180017238  lea     rdx, aInprocserver32; "\\InprocServer32"
0x18001723f  lea     rcx, [rsp+528h+var_498]; this
0x180017247  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001724c  nop
0x18001724d  lea     r8, [rsp+528h+var_498]
0x180017255  lea     rdx, [rsp+528h+var_468]
0x18001725d  mov     rcx, rbx
0x180017260  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180017265  nop
0x180017266  mov     rdx, rax
0x180017269  lea     rcx, [rsp+528h+var_4E0]
0x18001726e  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180017273  nop
0x180017274  lea     rcx, [rsp+528h+var_468]; this
0x18001727c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017281  nop
0x180017282  lea     rcx, [rsp+528h+var_498]; this
0x18001728a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001728f  nop
0x180017290  lea     rcx, [rsp+528h+var_460]; this
0x180017298  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001729d  nop
0x18001729e  lea     rcx, [rsp+528h+var_458]; this
0x1800172a6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800172ab  nop
0x1800172ac  lea     rcx, [rsp+528h+var_4D8]; this
0x1800172b1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800172b6  mov     rax, [rsp+528h+var_4E0]
0x1800172bb  test    rax, rax
0x1800172be  jz      loc_18001735B
0x1800172c4  mov     rcx, [rax]; unsigned __int16 *
0x1800172c7  xor     edx, edx; HKEY
0x1800172c9  call    ?OpenKey@RegistryKey@NLG@@KAPEAUHKEY__@@PEBGPEAU3@@Z; NLG::RegistryKey::OpenKey(ushort const *,HKEY__ *)
0x1800172ce  mov     [rsp+528h+var_450], rax
0x1800172d6  test    rax, rax
0x1800172d9  jnz     loc_180017362
0x1800172df  lea     rcx, [rsp+528h+var_4E0]; this
0x1800172e4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800172e9  nop
0x1800172ea  lea     rcx, [rsp+528h+var_4F0]; this
0x1800172ef  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800172f4  nop
0x1800172f5  lea     rcx, [rsp+528h+var_4E8]; this
0x1800172fa  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800172ff  mov     word ptr [rsp+528h+var_4B8], si
0x180017304  mov     eax, 3FFh
0x180017309  and     si, ax
0x18001730c  mov     [rsp+528h+arg_10], si
0x180017314  mov     rcx, [rsp+528h+hKey]; hKey
0x180017319  test    rcx, rcx
0x18001731c  jz      short loc_18001732D
0x18001731e  call    cs:__imp_RegCloseKey
0x180017324  mov     [rsp+528h+hKey], 0
0x18001732d  lea     rcx, [rsp+528h+var_4C0]; this
0x180017332  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017337  nop
0x180017338  lea     rcx, [rsp+528h+var_480]; this
0x180017340  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017345  mov     rcx, [rsp+528h+var_4B0]
0x18001734a  mov     rbx, [rsp+528h+var_490]
0x180017352  mov     edx, [rsp+528h+var_4B8]
0x180017356  jmp     loc_180017073
0x18001735b  xor     ecx, ecx
0x18001735d  jmp     loc_1800172C7
0x180017362  lea     rdx, [rsp+528h+var_440]
0x18001736a  lea     rcx, [rsp+528h+var_450]
0x180017372  call    ?GetDefaultValue@RegistryKey@NLG@@QEBA?AV_variant_t@@XZ; NLG::RegistryKey::GetDefaultValue(void)
0x180017377  nop
0x180017378  mov     rdx, rax; struct _variant_t *
0x18001737b  lea     rcx, [rsp+528h+var_4D8]; this
0x180017380  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180017385  nop
0x180017386  lea     rcx, [rsp+528h+var_440]; this
0x18001738e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017393  mov     rax, [rsp+528h+var_4D8]
0x180017398  test    rax, rax
0x18001739b  jz      short loc_1800173E4
0x18001739d  mov     r8, [rax]; unsigned __int16 *
0x1800173a0  mov     rdx, [rsp+528h+arg_20]; unsigned __int64
0x1800173a8  mov     rcx, rdi; unsigned __int16 *
0x1800173ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800173b0  test    eax, eax
0x1800173b2  jns     loc_180017593
0x1800173b8  mov     r8, [rsp+528h]; void *
0x1800173c0  mov     edx, eax; int
0x1800173c2  lea     rcx, [rsp+528h+var_280]; this
0x1800173ca  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800173cf  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800173d6  lea     rcx, [rsp+528h+var_280]; pExceptionObject
0x1800173de  call    _CxxThrowException_0
0x1800173e4  xor     r8d, r8d
0x1800173e7  jmp     short loc_1800173A0
0x1800173e9  mov     rax, [rsp+528h+var_4E8]
0x1800173ee  test    rax, rax
0x1800173f1  jz      short loc_180017430
0x1800173f3  mov     rcx, [rax]; lpsz
0x1800173f6  call    cs:__imp_IIDFromString
0x1800173fc  test    eax, eax
0x1800173fe  jns     loc_1800175A4
0x180017404  mov     r8, [rsp+528h]; void *
0x18001740c  mov     edx, eax; int
0x18001740e  lea     rcx, [rsp+528h+var_240]; this
0x180017416  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18001741b  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180017422  lea     rcx, [rsp+528h+var_240]; pExceptionObject
0x18001742a  call    _CxxThrowException_0
0x180017430  xor     ecx, ecx
  ... truncated ...
```
