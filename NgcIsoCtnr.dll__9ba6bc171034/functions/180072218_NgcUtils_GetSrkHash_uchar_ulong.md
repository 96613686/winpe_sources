# NgcUtils::GetSrkHash(uchar * *,ulong *)

- ea: `0x180072218`
- end: `0x1800726ef`
- name: `?GetSrkHash@NgcUtils@@YAJPEAPEAEPEAK@Z`
- size: `1239`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019ad0`
- `0x18001a444`

## callees

- `0x18000d60c`
- `0x18000d62c`
- `0x1800108e4`
- `0x180017f94`
- `0x1800273c4`
- `0x18002bfec`
- `0x1800721d0`
- `0x180072218`
- `0x180073c40`
- `0x180073d64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072637`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007268a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007269d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800726c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800725ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072637`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007268a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007269d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800726c2`
- `ncrypt!NCryptImportKey` at `0x180072362`
- `ncrypt!NCryptImportKey` at `0x180072362`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007225c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800722fc`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007225c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800722fc`
- `bcrypt!BCryptHash` at `0x18007259a`
- `bcrypt!BCryptHash` at `0x18007259a`
- `CRYPT32!CryptDecodeObjectEx` at `0x180072423`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800724d4`
- `CRYPT32!CryptDecodeObjectEx` at `0x180072423`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800724d4`

## string_xrefs

- `0x18007226c`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x1800722c6`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18007230c`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x180072372`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x1800723bf`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18007243c`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x180072476`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x1800724ed`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x1800725a8`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x180072651`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetSrkHash(NgcUtils *this, unsigned __int8 **a2, unsigned int *a3)
{
  SECURITY_STATUS v5; // eax
  unsigned __int64 v6; // rdx
  int NCryptBinaryBlob; // ebx
  SECURITY_STATUS v8; // eax
  BYTE *pbData; // rbx
  SECURITY_STATUS v10; // eax
  struct _CERT_PUBLIC_KEY_INFO **v11; // r8
  BOOL v12; // ebx
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  BOOL v16; // ebx
  const char *v17; // r9
  int *v18; // rbx
  int v19; // ecx
  _QWORD *v20; // rsi
  unsigned int v21; // r10d
  __int64 v22; // rdx
  __int64 v23; // rax
  char v24; // r8
  _BYTE *v25; // rax
  bool v26; // zf
  unsigned __int8 *v27; // rdi
  int v28; // eax
  HLOCAL v29; // rcx
  HLOCAL v30; // rcx
  HLOCAL v31; // rcx
  PBYTE v32; // rcx
  HLOCAL v34; // rcx
  HLOCAL v35; // rcx
  HLOCAL v36; // rcx
  PBYTE v37; // rcx
  unsigned int *phKey; // [rsp+20h] [rbp-49h]
  int phKeya; // [rsp+20h] [rbp-49h]
  int phKeyb; // [rsp+20h] [rbp-49h]
  int phKeyc; // [rsp+20h] [rbp-49h]
  int phKeyd; // [rsp+20h] [rbp-49h]
  int phKeye; // [rsp+20h] [rbp-49h]
  PBYTE v44; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL v45; // [rsp+48h] [rbp-21h] BYREF
  HLOCAL v46; // [rsp+50h] [rbp-19h] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+58h] [rbp-11h] BYREF
  NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey; // [rsp+60h] [rbp-9h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-1h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+70h] [rbp+7h] BYREF
  void *p_hMem; // [rsp+78h] [rbp+Fh] BYREF
  __int64 pvStructInfo; // [rsp+80h] [rbp+17h] BYREF
  char v53; // [rsp+88h] [rbp+1Fh]
  DWORD v54[4]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned __int8 *cbData; // [rsp+E0h] [rbp+77h] BYREF
  DWORD pcbStructInfo; // [rsp+E8h] [rbp+7Fh] BYREF

  phProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phProvider,
    0);
  v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  NCryptBinaryBlob = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v5,
      (int)phKey);
LABEL_50:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return (unsigned int)NCryptBinaryBlob;
  }
  p_hMem = &v44;
  v53 = 1;
  LODWORD(cbData) = 0;
  v44 = 0;
  pvStructInfo = 0;
  NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(
                       phProvider,
                       v6,
                       (const unsigned __int16 *)&pvStructInfo,
                       &cbData,
                       phKey);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( NCryptBinaryBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)NCryptBinaryBlob,
      phKeya);
    goto LABEL_48;
  }
  hProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hProvider,
    0);
  v8 = NCryptOpenStorageProvider(&hProvider, L"Microsoft Software Key Storage Provider", 0);
  NCryptBinaryBlob = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v8,
      phKeya);
LABEL_47:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
LABEL_48:
    v37 = v44;
    v44 = 0;
    if ( v37 )
      LocalFree(v37);
    goto LABEL_50;
  }
  pbData = v44;
  hCryptProvOrNCryptKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hCryptProvOrNCryptKey,
    0);
  v10 = NCryptImportKey(hProvider, 0, L"PUBLICBLOB", 0, &hCryptProvOrNCryptKey, pbData, (DWORD)cbData, 0);
  NCryptBinaryBlob = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v10,
      phKeyb);
LABEL_46:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hCryptProvOrNCryptKey);
    goto LABEL_47;
  }
  p_hMem = &v45;
  v45 = 0;
  pvStructInfo = 0;
  v53 = 1;
  NCryptBinaryBlob = NgcUtils::ExportPublicKeyInfo(hCryptProvOrNCryptKey, (unsigned __int64)&pvStructInfo, v11);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( NCryptBinaryBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)NCryptBinaryBlob,
      phKeyb);
LABEL_44:
    v36 = v45;
    v45 = 0;
    if ( v36 )
      LocalFree(v36);
    goto LABEL_46;
  }
  p_hMem = &v46;
  pcbStructInfo = 0;
  v46 = 0;
  pvStructInfo = 0;
  v53 = 1;
  v12 = CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x22,
          *((const BYTE **)v45 + 4),
          *((_DWORD *)v45 + 6),
          0x8000u,
          0,
          &pvStructInfo,
          &pcbStructInfo);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v12 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x15C,
                         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                         v13);
    goto LABEL_42;
  }
  if ( !*(_DWORD *)v46 )
  {
    v14 = 351;
LABEL_17:
    NCryptBinaryBlob = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)0x8007000DLL,
      phKeyc);
LABEL_42:
    v35 = v46;
    v46 = 0;
    if ( v35 )
      LocalFree(v35);
    goto LABEL_44;
  }
  if ( !**((_DWORD **)v46 + 1) )
  {
    v14 = 352;
    goto LABEL_17;
  }
  v54[0] = 0;
  p_hMem = &hMem;
  hMem = 0;
  v15 = *((_QWORD *)v46 + 1);
  pvStructInfo = 0;
  v53 = 1;
  v16 = CryptDecodeObjectEx(1u, (LPCSTR)0x1C, *(const BYTE **)(v15 + 8), *(_DWORD *)v15, 0x8000u, 0, &pvStructInfo, v54);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v16 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x16C,
                         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                         v17);
    goto LABEL_40;
  }
  v18 = (int *)hMem;
  v19 = *(_DWORD *)hMem;
  v20 = (char *)hMem + 8;
  if ( (*(_DWORD *)hMem & 0xFFFFFFFE) != 0 )
  {
    v21 = 0;
    do
    {
      v22 = v21;
      v23 = v19 + ~v21++;
      v24 = *(_BYTE *)(v22 + *v20);
      *(_BYTE *)(v22 + *v20) = *(_BYTE *)(v23 + *v20);
      *(_BYTE *)((unsigned int)v23 + *v20) = v24;
      v19 = *v18;
    }
    while ( v21 < (unsigned int)*v18 >> 1 );
  }
  if ( v19 )
  {
    do
    {
      v25 = (_BYTE *)*v20;
      if ( *(_BYTE *)*v20 )
        break;
      v26 = (*v18)-- == 1;
      *v20 = v25 + 1;
    }
    while ( !v26 );
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&cbData, 0x14u);
  v27 = cbData;
  if ( !cbData )
  {
    NCryptBinaryBlob = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)0x8007000ELL,
      phKeyd);
LABEL_40:
    v34 = hMem;
    hMem = 0;
    if ( v34 )
      LocalFree(v34);
    goto LABEL_42;
  }
  phKeye = *v18;
  v28 = BCryptHash(49, 0, 0, *v20);
  if ( v28 < 0 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_NtStatus(
                         retaddr,
                         (void *)0x18C,
                         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                         (const char *)(unsigned int)v28,
                         phKeye);
    if ( v27 )
      LocalFree(v27);
    goto LABEL_40;
  }
  v29 = hMem;
  *(_QWORD *)this = v27;
  *(_DWORD *)a2 = 20;
  hMem = 0;
  if ( v29 )
    LocalFree(v29);
  v30 = v46;
  v46 = 0;
  if ( v30 )
    LocalFree(v30);
  v31 = v45;
  v45 = 0;
  if ( v31 )
    LocalFree(v31);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hCryptProvOrNCryptKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
  v32 = v44;
  v44 = 0;
  if ( v32 )
    LocalFree(v32);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return 0;
}

```

## disassembly

```asm
0x180072218  mov     [rsp-8+arg_0], rbx
0x18007221d  mov     [rsp-8+arg_8], rsi
0x180072222  push    rbp
0x180072223  push    rdi
0x180072224  push    r12
0x180072226  push    r14
0x180072228  push    r15
0x18007222a  lea     rbp, [rsp-37h]
0x18007222f  sub     rsp, 0A0h
0x180072236  mov     r14, rdx
0x180072239  mov     r15, rcx
0x18007223c  xor     r12d, r12d
0x18007223f  lea     rcx, [rbp+57h+phProvider]
0x180072243  xor     edx, edx
0x180072245  mov     [rbp+57h+phProvider], r12
0x180072249  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18007224e  xor     r8d, r8d; dwFlags
0x180072251  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180072258  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18007225c  call    cs:__imp_NCryptOpenStorageProvider
0x180072262  mov     ebx, eax
0x180072264  test    eax, eax
0x180072266  jns     short loc_180072285
0x180072268  mov     rcx, [rbp+5Fh]; this
0x18007226c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072273  mov     r9d, eax; char *
0x180072276  mov     edx, 131h; void *
0x18007227b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072280  jmp     loc_1800726C8
0x180072285  mov     rcx, [rbp+57h+phProvider]; hObject
0x180072289  lea     rax, [rbp+57h+var_80]
0x18007228d  mov     edi, 1
0x180072292  mov     [rbp+57h+var_48], rax
0x180072296  lea     r9, [rbp+57h+arg_10]; unsigned __int8 **
0x18007229a  mov     [rbp+57h+var_38], dil
0x18007229e  lea     r8, [rbp+57h+pvStructInfo]; unsigned __int16 *
0x1800722a2  mov     dword ptr [rbp+57h+arg_10], r12d
0x1800722a6  mov     [rbp+57h+var_80], r12
0x1800722aa  mov     [rbp+57h+pvStructInfo], r12
0x1800722ae  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x1800722b3  lea     rcx, [rbp+57h+var_48]
0x1800722b7  mov     ebx, eax
0x1800722b9  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800722be  test    ebx, ebx
0x1800722c0  jns     short loc_1800722DF
0x1800722c2  mov     rcx, [rbp+5Fh]; this
0x1800722c6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800722cd  mov     r9d, ebx; char *
0x1800722d0  mov     edx, 139h; void *
0x1800722d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800722da  jmp     loc_1800726B5
0x1800722df  xor     edx, edx
0x1800722e1  mov     [rbp+57h+hProvider], r12
0x1800722e5  lea     rcx, [rbp+57h+hProvider]
0x1800722e9  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800722ee  xor     r8d, r8d; dwFlags
0x1800722f1  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x1800722f8  lea     rcx, [rbp+57h+hProvider]; phProvider
0x1800722fc  call    cs:__imp_NCryptOpenStorageProvider
0x180072302  mov     ebx, eax
0x180072304  test    eax, eax
0x180072306  jns     short loc_180072325
0x180072308  mov     rcx, [rbp+5Fh]; this
0x18007230c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072313  mov     r9d, eax; char *
0x180072316  mov     edx, 13Fh; void *
0x18007231b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072320  jmp     loc_1800726AC
0x180072325  mov     rbx, [rbp+57h+var_80]
0x180072329  lea     rcx, [rbp+57h+hCryptProvOrNCryptKey]
0x18007232d  xor     edx, edx
0x18007232f  mov     [rbp+57h+hCryptProvOrNCryptKey], r12
0x180072333  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180072338  mov     eax, dword ptr [rbp+57h+arg_10]
0x18007233b  lea     r8, aPublicblob; "PUBLICBLOB"
0x180072342  mov     rcx, [rbp+57h+hProvider]; hProvider
0x180072346  xor     r9d, r9d; pParameterList
0x180072349  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18007234e  xor     edx, edx; hImportKey
0x180072350  mov     [rsp+0C0h+cbData], eax; cbData
0x180072354  lea     rax, [rbp+57h+hCryptProvOrNCryptKey]
0x180072358  mov     [rsp+0C0h+pbData], rbx; pbData
0x18007235d  mov     [rsp+0C0h+phKey], rax; int
0x180072362  call    cs:__imp_NCryptImportKey
0x180072368  mov     ebx, eax
0x18007236a  test    eax, eax
0x18007236c  jns     short loc_18007238B
0x18007236e  mov     rcx, [rbp+5Fh]; this
0x180072372  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072379  mov     r9d, eax; char *
0x18007237c  mov     edx, 14Ah; void *
0x180072381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072386  jmp     loc_1800726A3
0x18007238b  mov     rcx, [rbp+57h+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18007238f  lea     rax, [rbp+57h+var_78]
0x180072393  lea     rdx, [rbp+57h+pvStructInfo]; unsigned __int64
0x180072397  mov     [rbp+57h+var_48], rax
0x18007239b  mov     [rbp+57h+var_78], r12
0x18007239f  mov     [rbp+57h+pvStructInfo], r12
0x1800723a3  mov     [rbp+57h+var_38], dil
0x1800723a7  call    ?ExportPublicKeyInfo@NgcUtils@@YAJ_KPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z; NgcUtils::ExportPublicKeyInfo(unsigned __int64,_CERT_PUBLIC_KEY_INFO * *)
0x1800723ac  lea     rcx, [rbp+57h+var_48]
0x1800723b0  mov     ebx, eax
0x1800723b2  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800723b7  test    ebx, ebx
0x1800723b9  jns     short loc_1800723D8
0x1800723bb  mov     rcx, [rbp+5Fh]; this
0x1800723bf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800723c6  mov     r9d, ebx; char *
0x1800723c9  mov     edx, 14Fh; void *
0x1800723ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723d3  jmp     loc_180072690
0x1800723d8  mov     r8, [rbp+57h+var_78]
0x1800723dc  lea     rax, [rbp+57h+var_70]
0x1800723e0  mov     [rbp+57h+var_48], rax
0x1800723e4  mov     esi, 8000h
0x1800723e9  mov     [rbp+57h+pcbStructInfo], r12d
0x1800723ed  lea     rax, [rbp+57h+pcbStructInfo]
0x1800723f1  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbStructInfo
0x1800723f6  mov     edx, 22h ; '"'; lpszStructType
0x1800723fb  mov     [rbp+57h+var_70], r12
0x1800723ff  lea     rax, [rbp+57h+pvStructInfo]
0x180072403  mov     [rbp+57h+pvStructInfo], r12
0x180072407  mov     ecx, edi; dwCertEncodingType
0x180072409  mov     [rbp+57h+var_38], dil
0x18007240d  mov     r9d, [r8+18h]; cbEncoded
0x180072411  mov     r8, [r8+20h]; pbEncoded
0x180072415  mov     qword ptr [rsp+0C0h+cbData], rax; pvStructInfo
0x18007241a  mov     [rsp+0C0h+pbData], r12; pDecodePara
0x18007241f  mov     dword ptr [rsp+0C0h+phKey], esi; int
0x180072423  call    cs:__imp_CryptDecodeObjectEx
0x180072429  lea     rcx, [rbp+57h+var_48]
0x18007242d  mov     ebx, eax
0x18007242f  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180072434  test    ebx, ebx
0x180072436  jnz     short loc_180072454
0x180072438  mov     rcx, [rbp+5Fh]; this
0x18007243c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072443  mov     edx, 15Ch; void *
0x180072448  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007244d  mov     ebx, eax
0x18007244f  jmp     loc_18007267D
0x180072454  mov     r8, [rbp+57h+var_70]
0x180072458  cmp     [r8], edi
0x18007245b  jnb     short loc_180072464
0x18007245d  mov     edx, 15Fh
0x180072462  jmp     short loc_180072472
0x180072464  mov     rax, [r8+8]
0x180072468  cmp     [rax], r12d
0x18007246b  jnz     short loc_18007248F
0x18007246d  mov     edx, 160h; void *
0x180072472  mov     rcx, [rbp+5Fh]; this
0x180072476  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18007247d  mov     ebx, 8007000Dh
0x180072482  mov     r9d, ebx; char *
0x180072485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007248a  jmp     loc_18007267D
0x18007248f  mov     [rbp+57h+var_30], r12d
0x180072493  lea     rax, [rbp+57h+hMem]
0x180072497  mov     [rbp+57h+var_48], rax
0x18007249b  mov     edx, 1Ch; lpszStructType
0x1800724a0  mov     [rbp+57h+hMem], r12
0x1800724a4  lea     rax, [rbp+57h+var_30]
0x1800724a8  mov     r8, [r8+8]
0x1800724ac  mov     ecx, edi; dwCertEncodingType
0x1800724ae  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbStructInfo
0x1800724b3  lea     rax, [rbp+57h+pvStructInfo]
0x1800724b7  mov     [rbp+57h+pvStructInfo], r12
0x1800724bb  mov     [rbp+57h+var_38], dil
0x1800724bf  mov     r9d, [r8]; cbEncoded
0x1800724c2  mov     r8, [r8+8]; pbEncoded
0x1800724c6  mov     qword ptr [rsp+0C0h+cbData], rax; pvStructInfo
0x1800724cb  mov     [rsp+0C0h+pbData], r12; pDecodePara
0x1800724d0  mov     dword ptr [rsp+0C0h+phKey], esi; int
0x1800724d4  call    cs:__imp_CryptDecodeObjectEx
0x1800724da  lea     rcx, [rbp+57h+var_48]
0x1800724de  mov     ebx, eax
0x1800724e0  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800724e5  test    ebx, ebx
0x1800724e7  jnz     short loc_180072505
0x1800724e9  mov     rcx, [rbp+5Fh]; this
0x1800724ed  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800724f4  mov     edx, 16Ch; void *
0x1800724f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800724fe  mov     ebx, eax
0x180072500  jmp     loc_18007266A
0x180072505  mov     rbx, [rbp+57h+hMem]
0x180072509  mov     ecx, [rbx]
0x18007250b  lea     rsi, [rbx+8]
0x18007250f  test    ecx, 0FFFFFFFEh
0x180072515  jbe     short loc_18007254A
0x180072517  mov     r10d, r12d
0x18007251a  mov     r9, [rsi]
0x18007251d  mov     eax, r10d
0x180072520  not     eax
0x180072522  mov     edx, r10d
0x180072525  add     eax, ecx
0x180072527  add     r10d, edi
0x18007252a  mov     ecx, eax
0x18007252c  mov     r8b, [rdx+r9]
0x180072530  mov     al, [rax+r9]
0x180072534  mov     [rdx+r9], al
0x180072538  mov     rax, [rsi]
0x18007253b  mov     [rcx+rax], r8b
0x18007253f  mov     ecx, [rbx]
0x180072541  mov     eax, ecx
0x180072543  shr     eax, 1
0x180072545  cmp     r10d, eax
0x180072548  jb      short loc_18007251A
0x18007254a  test    ecx, ecx
0x18007254c  jz      short loc_180072561
0x18007254e  mov     rax, [rsi]
0x180072551  cmp     [rax], r12b
0x180072554  jnz     short loc_180072561
0x180072556  inc     rax
0x180072559  add     dword ptr [rbx], 0FFFFFFFFh
0x18007255c  mov     [rsi], rax
0x18007255f  jnz     short loc_18007254E
0x180072561  mov     edx, 14h
0x180072566  lea     rcx, [rbp+57h+arg_10]
0x18007256a  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18007256f  mov     rdi, [rbp+57h+arg_10]
0x180072573  test    rdi, rdi
0x180072576  jz      loc_18007264D
0x18007257c  mov     eax, [rbx]
0x18007257e  xor     edx, edx
0x180072580  mov     r9, [rsi]
0x180072583  xor     r8d, r8d
0x180072586  mov     [rsp+0C0h+cbData], 14h
0x18007258e  mov     [rsp+0C0h+pbData], rdi
0x180072593  lea     ecx, [rdx+31h]
0x180072596  mov     dword ptr [rsp+0C0h+phKey], eax; int
0x18007259a  call    cs:__imp_BCryptHash
0x1800725a0  test    eax, eax
0x1800725a2  jns     short loc_1800725D5
0x1800725a4  mov     rcx, [rbp+5Fh]; this
0x1800725a8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800725af  mov     r9d, eax; char *
0x1800725b2  mov     edx, 18Ch; void *
0x1800725b7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800725bc  mov     ebx, eax
0x1800725be  test    rdi, rdi
0x1800725c1  jz      loc_18007266A
0x1800725c7  mov     rcx, rdi; hMem
0x1800725ca  call    cs:__imp_LocalFree
0x1800725d0  jmp     loc_18007266A
0x1800725d5  mov     rcx, [rbp+57h+hMem]; hMem
0x1800725d9  mov     [r15], rdi
0x1800725dc  mov     dword ptr [r14], 14h
0x1800725e3  mov     [rbp+57h+hMem], r12
0x1800725e7  test    rcx, rcx
0x1800725ea  jz      short loc_1800725F2
0x1800725ec  call    cs:__imp_LocalFree
0x1800725f2  mov     rcx, [rbp+57h+var_70]; hMem
0x1800725f6  mov     [rbp+57h+var_70], r12
0x1800725fa  test    rcx, rcx
0x1800725fd  jz      short loc_180072605
0x1800725ff  call    cs:__imp_LocalFree
0x180072605  mov     rcx, [rbp+57h+var_78]; hMem
0x180072609  mov     [rbp+57h+var_78], r12
0x18007260d  test    rcx, rcx
0x180072610  jz      short loc_180072618
0x180072612  call    cs:__imp_LocalFree
0x180072618  lea     rcx, [rbp+57h+hCryptProvOrNCryptKey]
0x18007261c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180072621  lea     rcx, [rbp+57h+hProvider]
0x180072625  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007262a  mov     rcx, [rbp+57h+var_80]; hMem
0x18007262e  mov     [rbp+57h+var_80], r12
0x180072632  test    rcx, rcx
0x180072635  jz      short loc_18007263D
0x180072637  call    cs:__imp_LocalFree
0x18007263d  lea     rcx, [rbp+57h+phProvider]
0x180072641  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180072646  xor     eax, eax
0x180072648  jmp     loc_1800726D3
0x18007264d  mov     rcx, [rbp+5Fh]; this
0x180072651  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072658  mov     ebx, 8007000Eh
0x18007265d  mov     edx, 183h; void *
0x180072662  mov     r9d, ebx; char *
0x180072665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007266a  mov     rcx, [rbp+57h+hMem]; hMem
0x18007266e  mov     [rbp+57h+hMem], r12
0x180072672  test    rcx, rcx
0x180072675  jz      short loc_18007267D
0x180072677  call    cs:__imp_LocalFree
0x18007267d  mov     rcx, [rbp+57h+var_70]; hMem
0x180072681  mov     [rbp+57h+var_70], r12
0x180072685  test    rcx, rcx
0x180072688  jz      short loc_180072690
0x18007268a  call    cs:__imp_LocalFree
0x180072690  mov     rcx, [rbp+57h+var_78]; hMem
0x180072694  mov     [rbp+57h+var_78], r12
0x180072698  test    rcx, rcx
0x18007269b  jz      short loc_1800726A3
0x18007269d  call    cs:__imp_LocalFree
0x1800726a3  lea     rcx, [rbp+57h+hCryptProvOrNCryptKey]
0x1800726a7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800726ac  lea     rcx, [rbp+57h+hProvider]
  ... truncated ...
```
