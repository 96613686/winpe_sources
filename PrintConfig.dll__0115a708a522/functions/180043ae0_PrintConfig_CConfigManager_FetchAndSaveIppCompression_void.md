# PrintConfig::CConfigManager::FetchAndSaveIppCompression(void)

- ea: `0x180043ae0`
- end: `0x180043f72`
- name: `?FetchAndSaveIppCompression@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `1170`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb3c`

## callees

- `0x180003400`
- `0x180004564`
- `0x1800060e8`
- `0x18000de1c`
- `0x18000ded0`
- `0x18000f830`
- `0x18000fa4c`
- `0x18001535c`
- `0x180018f00`
- `0x180018f58`
- `0x180020fa4`
- `0x180022268`
- `0x180025038`
- `0x18003df5c`
- `0x18003f348`
- `0x180040a68`
- `0x180043ae0`
- `0x18004619c`
- `0x1800464d4`
- `0x18004c344`
- `0x18004c53c`
- `0x1801b56c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043c16`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043c73`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043d14`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043c16`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043c73`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180043d14`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043df7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043df7`
- `WINSPOOL!SetPrinterDataW` at `0x180043e9e`
- `WINSPOOL!SetPrinterDataW` at `0x180043e9e`

## string_xrefs

- `0x180043da5`: `Failed to get printer attributes from cache.`
- `0x180043e42`: `'compress' is the only compression algorithm supported by this printer`
- `0x180043dac`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180043e49`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180043e69`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180043ec3`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180043bab`: `Failed to get compression supported attribute from cache.`
- `0x180043ce8`: `compress`
- `0x180043e93`: `ippCompressionSupported`
- `0x180043e62`: `SetPrinterData compression: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PrintConfig::CConfigManager::FetchAndSaveIppCompression(
        PrintConfig::CConfigManager *this,
        __int64 a2,
        __int64 a3,
        double a4)
{
  char v5; // r15
  __int64 v6; // r8
  unsigned __int16 *v7; // rdx
  unsigned __int64 v8; // rsi
  __int64 v9; // rdi
  char **v10; // rcx
  int v11; // ebx
  __int64 v12; // r8
  char **v13; // rcx
  int v14; // ebx
  __int64 v15; // r8
  LPBYTE *v16; // rbx
  char **v17; // rcx
  int v18; // ebx
  LPBYTE *v19; // rcx
  __int128 *p_pExceptionObject; // rdx
  LPBYTE *v21; // rcx
  bool v22; // bl
  _DWORD *v23; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v24; // rcx
  LPBYTE *v25; // r8
  BYTE *v26; // r9
  signed int v27; // eax
  signed int v28; // ebx
  unsigned int v29; // eax
  const char *v30; // rdx
  unsigned __int64 *v31; // [rsp+38h] [rbp-89h] BYREF
  __int128 v32; // [rsp+40h] [rbp-81h] BYREF
  __int64 v33; // [rsp+50h] [rbp-71h]
  __int64 v34; // [rsp+58h] [rbp-69h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-61h] BYREF
  __int128 v36; // [rsp+70h] [rbp-51h]
  LPBYTE pData[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v38; // [rsp+90h] [rbp-31h]
  unsigned __int64 v39; // [rsp+98h] [rbp-29h]
  char *v40[3]; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v41; // [rsp+B8h] [rbp-9h]
  _BYTE v42[8]; // [rsp+C0h] [rbp-1h] BYREF
  char *v43; // [rsp+C8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  v34 = -2;
  v5 = 0;
  *(_OWORD *)pData = 0;
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>(pData, L"none", 4u);
  PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(
    (PrintCore::IppPrinterAttributesCache *)v42,
    *((void **)this + 8));
  v32 = 0;
  v33 = 0;
  if ( (int)PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(
              (__int64)v42,
              (PrintCore::IppAttribute **)&v32) < 0 )
  {
    v7 = L"Failed to get printer attributes from cache.";
    goto LABEL_29;
  }
  std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const *>(
    &v31,
    (unsigned __int64 *)v32,
    *((unsigned __int64 **)&v32 + 1),
    (const void **)&PrintCore::PrinterAttributes::CompressionSupported);
  if ( v31 == *((unsigned __int64 **)&v32 + 1) )
  {
    v7 = L"Failed to get compression supported attribute from cache.";
LABEL_29:
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
      v7);
    goto LABEL_30;
  }
  v8 = v31[5];
  v9 = v31[4];
  if ( v9 == v8 )
  {
    std::string::c_str(v31);
    v29 = wil::verify_hresult<long>(0x8000FFFF);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      1276,
      (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\IppEncoding.hxx",
      (const char *)v29,
      (unsigned __int64)"GetValues: IPP attribute '%hs' contains no values",
      v30);
  }
  while ( 1 )
  {
    PrintCore::IppValue::GetStringValue(v9, (__int64)v40, v6, a4);
    pExceptionObject = 0;
    v36 = 0;
    std::string::_Construct<1,char const *>(&pExceptionObject, "gzip", 4u);
    v10 = v40;
    if ( v41 > 0xF )
      v10 = (char **)v40[0];
    v11 = _o__stricmp(v10);
    std::string::~string((char **)&pExceptionObject);
    if ( !v11 )
      break;
    pExceptionObject = 0;
    v36 = 0;
    std::string::_Construct<1,char const *>(&pExceptionObject, "deflate", 7u);
    v13 = v40;
    if ( v41 > 0xF )
      v13 = (char **)v40[0];
    v14 = _o__stricmp(v13);
    std::string::~string((char **)&pExceptionObject);
    if ( v14 )
    {
      pExceptionObject = 0;
      v36 = 0;
      std::string::_Construct<1,char const *>(&pExceptionObject, "compress", 8u);
      v17 = v40;
      if ( v41 > 0xF )
        v17 = (char **)v40[0];
      v18 = _o__stricmp(v17);
      std::string::~string((char **)&pExceptionObject);
      if ( !v18 )
        v5 = 1;
    }
    else if ( v39 < 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)pData,
        7u,
        v15,
        L"deflate");
    }
    else
    {
      v16 = pData;
      if ( v39 > 7 )
        v16 = (LPBYTE *)pData[0];
      v38 = 7;
      memmove_0(v16, L"deflate", 0xEu);
      *((_WORD *)v16 + 7) = 0;
    }
    std::string::~string(v40);
    v9 += 88;
    if ( v9 == v8 )
      goto LABEL_30;
  }
  v19 = pData;
  if ( v39 < 4 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)pData,
      4u,
      v12,
      L"gzip");
  }
  else
  {
    if ( v39 > 7 )
      v19 = (LPBYTE *)pData[0];
    v38 = 4;
    *v19 = (LPBYTE)0x700069007A0067LL;
    *((_WORD *)v19 + 4) = 0;
  }
  std::string::~string(v40);
LABEL_30:
  pExceptionObject = 0;
  v36 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"none", 4u);
  p_pExceptionObject = &pExceptionObject;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    p_pExceptionObject = (__int128 *)pExceptionObject;
  v21 = pData;
  if ( v39 > 7 )
    v21 = (LPBYTE *)pData[0];
  v22 = !(unsigned int)_o__wcsicmp(v21, p_pExceptionObject) && v5;
  std::wstring::~wstring((char **)&pExceptionObject);
  if ( v22 )
  {
    v23 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
    if ( v23 && *v23 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
      Print::Driver::Telemetry::PrintConfigTelemetry::SupportsCompressOnly_(v24, *((unsigned __int16 *const *)this + 2));
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
      L"'compress' is the only compression algorithm supported by this printer");
  }
  v25 = pData;
  if ( v39 > 7 )
    v25 = (LPBYTE *)pData[0];
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
    L"SetPrinterData compression: %ws",
    v25);
  v26 = (BYTE *)pData;
  if ( v39 > 7 )
    v26 = pData[0];
  v27 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"ippCompressionSupported", 1u, v26, 2 * v38 + 2);
  v28 = v27;
  if ( v27 > 0 )
    v28 = (unsigned __int16)v27 | 0x80070000;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
    L"SetPrinterData returned with: 0x%x",
    (unsigned int)v28);
  if ( v28 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v28);
    throw (hr_error *)&pExceptionObject;
  }
  std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>((__int64)&v32);
  std::wstring::~wstring(&v43);
  std::wstring::~wstring((char **)pData);
}

```

## disassembly

```asm
0x180043ae0  mov     rax, rsp
0x180043ae3  push    rbp
0x180043ae4  push    rdi
0x180043ae5  push    r13
0x180043ae7  push    r14
0x180043ae9  push    r15
0x180043aeb  lea     rbp, [rax-5Fh]
0x180043aef  sub     rsp, 0F0h
0x180043af6  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFEh
0x180043afe  mov     [rax+10h], rbx
0x180043b02  mov     [rax+18h], rsi
0x180043b06  mov     rax, cs:__security_cookie
0x180043b0d  xor     rax, rsp
0x180043b10  mov     [rbp+57h+var_30], rax
0x180043b14  mov     r14, rcx
0x180043b17  xor     r15b, r15b
0x180043b1a  xorps   xmm0, xmm0
0x180043b1d  movups  xmmword ptr [rbp+57h+pData], xmm0
0x180043b21  mov     [rbp+57h+var_88], 0
0x180043b29  mov     [rbp+57h+var_80], 0
0x180043b31  mov     r8d, 4
0x180043b37  lea     rdx, aNone; "none"
0x180043b3e  lea     rcx, [rbp+57h+pData]
0x180043b42  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043b47  nop
0x180043b48  mov     rdx, [r14+40h]; void *
0x180043b4c  lea     rcx, [rbp+57h+var_58]; this
0x180043b50  call    ??0IppPrinterAttributesCache@PrintCore@@QEAA@PEAX@Z; PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(void *)
0x180043b55  nop
0x180043b56  xorps   xmm0, xmm0
0x180043b59  movdqu  [rsp+110h+var_E0+8], xmm0
0x180043b5f  mov     [rbp+57h+var_C8], 0
0x180043b67  lea     rdx, [rsp+110h+var_E0+8]
0x180043b6c  lea     rcx, [rbp+57h+var_58]
0x180043b70  call    ?GetPrinterAttributesCache@IppPrinterAttributesCache@PrintCore@@QEAAJAEAV?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@@Z; PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(std::vector<PrintCore::IppAttribute> &)
0x180043b75  mov     edi, 1
0x180043b7a  lea     r13d, [rdi+6]
0x180043b7e  test    eax, eax
0x180043b80  js      loc_180043DA5
0x180043b86  lea     r9, ?CompressionSupported@PrinterAttributes@PrintCore@@2QEBDEB; char const * const PrintCore::PrinterAttributes::CompressionSupported
0x180043b8d  mov     r8, [rbp+57h+var_D0]
0x180043b91  mov     rdx, qword ptr [rsp+110h+var_E0+8]
0x180043b96  lea     rcx, [rsp+110h+var_E0]
0x180043b9b  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VIppAttribute@PrintCore@@@std@@@std@@@std@@PEBD@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VIppAttribute@PrintCore@@@std@@@std@@@0@V10@V10@AEBQEBD@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const *>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const * const &)
0x180043ba0  mov     rcx, qword ptr [rsp+110h+var_E0]
0x180043ba5  cmp     rcx, [rbp+57h+var_D0]
0x180043ba9  jnz     short loc_180043BB7
0x180043bab  lea     rdx, aFailedToGetCom; "Failed to get compression supported att"...
0x180043bb2  jmp     loc_180043DAC
0x180043bb7  mov     rsi, [rcx+28h]
0x180043bbb  mov     rdi, [rcx+20h]
0x180043bbf  cmp     rdi, rsi
0x180043bc2  jz      loc_180043F36
0x180043bc8  lea     rdx, [rbp+57h+var_78]
0x180043bcc  mov     rcx, rdi
0x180043bcf  call    ?GetStringValue@IppValue@PrintCore@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; PrintCore::IppValue::GetStringValue(void)
0x180043bd4  nop
0x180043bd5  xorps   xmm0, xmm0
0x180043bd8  movups  [rbp+57h+pExceptionObject], xmm0
0x180043bdc  xorps   xmm1, xmm1
0x180043bdf  movdqu  [rbp+57h+var_A8], xmm1
0x180043be4  mov     r8d, 4
0x180043bea  lea     rdx, aGzip; "gzip"
0x180043bf1  lea     rcx, [rbp+57h+pExceptionObject]
0x180043bf5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180043bfa  lea     rdx, [rbp+57h+pExceptionObject]
0x180043bfe  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x180043c03  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180043c08  lea     rcx, [rbp+57h+var_78]
0x180043c0c  cmp     [rbp+57h+var_60], 0Fh
0x180043c11  cmova   rcx, [rbp+57h+var_78]
0x180043c16  call    cs:__imp__o__stricmp
0x180043c1d  nop     dword ptr [rax+rax+00h]
0x180043c22  mov     ebx, eax
0x180043c24  lea     rcx, [rbp+57h+pExceptionObject]
0x180043c28  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180043c2d  test    ebx, ebx
0x180043c2f  jz      loc_180043D57
0x180043c35  xorps   xmm0, xmm0
0x180043c38  movups  [rbp+57h+pExceptionObject], xmm0
0x180043c3c  xorps   xmm1, xmm1
0x180043c3f  movdqu  [rbp+57h+var_A8], xmm1
0x180043c44  mov     r8, r13
0x180043c47  lea     rdx, aDeflate; "deflate"
0x180043c4e  lea     rcx, [rbp+57h+pExceptionObject]
0x180043c52  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180043c57  lea     rdx, [rbp+57h+pExceptionObject]
0x180043c5b  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x180043c60  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180043c65  lea     rcx, [rbp+57h+var_78]
0x180043c69  cmp     [rbp+57h+var_60], 0Fh
0x180043c6e  cmova   rcx, [rbp+57h+var_78]
0x180043c73  call    cs:__imp__o__stricmp
0x180043c7a  nop     dword ptr [rax+rax+00h]
0x180043c7f  mov     ebx, eax
0x180043c81  lea     rcx, [rbp+57h+pExceptionObject]
0x180043c85  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180043c8a  test    ebx, ebx
0x180043c8c  jnz     short loc_180043CD3
0x180043c8e  cmp     [rbp+57h+var_80], r13
0x180043c92  jb      short loc_180043CBE
0x180043c94  lea     rbx, [rbp+57h+pData]
0x180043c98  cmova   rbx, [rbp+57h+pData]
0x180043c9d  mov     [rbp+57h+var_88], r13
0x180043ca1  mov     r8d, 0Eh; Size
0x180043ca7  lea     rdx, aDeflate_0; "deflate"
0x180043cae  mov     rcx, rbx; void *
0x180043cb1  call    memmove_0
0x180043cb6  xor     eax, eax
0x180043cb8  mov     [rbx+0Eh], ax
0x180043cbc  jmp     short loc_180043D3A
0x180043cbe  lea     r9, aDeflate_0; "deflate"
0x180043cc5  mov     rdx, r13
0x180043cc8  lea     rcx, [rbp+57h+pData]
0x180043ccc  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180043cd1  jmp     short loc_180043D3A
0x180043cd3  xorps   xmm0, xmm0
0x180043cd6  movups  [rbp+57h+pExceptionObject], xmm0
0x180043cda  xorps   xmm1, xmm1
0x180043cdd  movdqu  [rbp+57h+var_A8], xmm1
0x180043ce2  mov     r8d, 8
0x180043ce8  lea     rdx, aCompress; "compress"
0x180043cef  lea     rcx, [rbp+57h+pExceptionObject]
0x180043cf3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180043cf8  lea     rdx, [rbp+57h+pExceptionObject]
0x180043cfc  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x180043d01  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180043d06  lea     rcx, [rbp+57h+var_78]
0x180043d0a  cmp     [rbp+57h+var_60], 0Fh
0x180043d0f  cmova   rcx, [rbp+57h+var_78]
0x180043d14  call    cs:__imp__o__stricmp
0x180043d1b  nop     dword ptr [rax+rax+00h]
0x180043d20  mov     ebx, eax
0x180043d22  lea     rcx, [rbp+57h+pExceptionObject]
0x180043d26  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180043d2b  movzx   r15d, r15b
0x180043d2f  test    ebx, ebx
0x180043d31  mov     eax, 1
0x180043d36  cmovz   r15d, eax
0x180043d3a  lea     rcx, [rbp+57h+var_78]
0x180043d3e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180043d43  add     rdi, 58h ; 'X'
0x180043d47  cmp     rdi, rsi
0x180043d4a  jnz     loc_180043BC8
0x180043d50  mov     edi, 1
0x180043d55  jmp     short loc_180043DB8
0x180043d57  lea     rcx, [rbp+57h+pData]
0x180043d5b  cmp     [rbp+57h+var_80], 4
0x180043d60  jb      short loc_180043D88
0x180043d62  cmp     [rbp+57h+var_80], r13
0x180043d66  cmova   rcx, [rbp+57h+pData]
0x180043d6b  mov     [rbp+57h+var_88], 4
0x180043d73  mov     rax, 700069007A0067h
0x180043d7d  mov     [rcx], rax
0x180043d80  xor     eax, eax
0x180043d82  mov     [rcx+8], ax
0x180043d86  jmp     short loc_180043D9A
0x180043d88  lea     r9, aGzip_0; "gzip"
0x180043d8f  mov     edx, 4
0x180043d94  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180043d99  nop
0x180043d9a  lea     rcx, [rbp+57h+var_78]
0x180043d9e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180043da3  jmp     short loc_180043D50
0x180043da5  lea     rdx, aFailedToGetPri; "Failed to get printer attributes from c"...
0x180043dac  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x180043db3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180043db8  xorps   xmm0, xmm0
0x180043dbb  movups  [rbp+57h+pExceptionObject], xmm0
0x180043dbf  xorps   xmm1, xmm1
0x180043dc2  movdqu  [rbp+57h+var_A8], xmm1
0x180043dc7  mov     r8d, 4
0x180043dcd  lea     rdx, aNone; "none"
0x180043dd4  lea     rcx, [rbp+57h+pExceptionObject]
0x180043dd8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043ddd  lea     rdx, [rbp+57h+pExceptionObject]
0x180043de1  cmp     qword ptr [rbp+57h+var_A8+8], r13
0x180043de5  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180043dea  lea     rcx, [rbp+57h+pData]
0x180043dee  cmp     [rbp+57h+var_80], r13
0x180043df2  cmova   rcx, [rbp+57h+pData]
0x180043df7  call    cs:__imp__o__wcsicmp
0x180043dfe  nop     dword ptr [rax+rax+00h]
0x180043e03  test    eax, eax
0x180043e05  jnz     short loc_180043E11
0x180043e07  test    r15b, r15b
0x180043e0a  jz      short loc_180043E11
0x180043e0c  mov     bl, dil
0x180043e0f  jmp     short loc_180043E13
0x180043e11  xor     bl, bl
0x180043e13  lea     rcx, [rbp+57h+pExceptionObject]
0x180043e17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043e1c  test    bl, bl
0x180043e1e  jz      short loc_180043E55
0x180043e20  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180043e25  mov     rax, [rax+8]
0x180043e29  test    rax, rax
0x180043e2c  jz      short loc_180043E42
0x180043e2e  mov     eax, [rax]
0x180043e30  test    eax, eax
0x180043e32  jz      short loc_180043E42
0x180043e34  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180043e39  mov     rdx, [r14+10h]; unsigned __int16 *
0x180043e3d  call    ?SupportsCompressOnly_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEAG@Z; Print::Driver::Telemetry::PrintConfigTelemetry::SupportsCompressOnly_(ushort * const)
0x180043e42  lea     rdx, aCompressIsTheO; "'compress' is the only compression algo"...
0x180043e49  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x180043e50  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043e55  lea     r8, [rbp+57h+pData]
0x180043e59  cmp     [rbp+57h+var_80], r13
0x180043e5d  cmova   r8, [rbp+57h+pData]
0x180043e62  lea     rdx, aSetprinterdata_1; "SetPrinterData compression: %ws"
0x180043e69  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x180043e70  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043e75  mov     eax, dword ptr [rbp+57h+var_88]
0x180043e78  lea     r9, [rbp+57h+pData]
0x180043e7c  cmp     [rbp+57h+var_80], r13
0x180043e80  cmova   r9, [rbp+57h+pData]; pData
0x180043e85  lea     eax, ds:2[rax*2]
0x180043e8c  mov     [rsp+110h+cbData], eax; cbData
0x180043e90  mov     r8d, edi; Type
0x180043e93  lea     rdx, aIppcompression; "ippCompressionSupported"
0x180043e9a  mov     rcx, [r14+40h]; hPrinter
0x180043e9e  call    cs:__imp_SetPrinterDataW
0x180043ea5  nop     dword ptr [rax+rax+00h]
0x180043eaa  mov     ebx, eax
0x180043eac  test    eax, eax
0x180043eae  jle     short loc_180043EB9
0x180043eb0  movzx   ebx, ax
0x180043eb3  or      ebx, 80070000h
0x180043eb9  mov     r8d, ebx
0x180043ebc  lea     rdx, aSetprinterdata_2; "SetPrinterData returned with: 0x%x"
0x180043ec3  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x180043eca  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043ecf  test    ebx, ebx
0x180043ed1  js      short loc_180043F1A
0x180043ed3  lea     rcx, [rsp+110h+var_E0+8]
0x180043ed8  call    ??1?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@QEAA@XZ; std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(void)
0x180043edd  nop
0x180043ede  lea     rcx, [rbp+57h+var_50]
0x180043ee2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043ee7  nop
0x180043ee8  lea     rcx, [rbp+57h+pData]
0x180043eec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043ef1  mov     rcx, [rbp+57h+var_30]
0x180043ef5  xor     rcx, rsp; StackCookie
0x180043ef8  call    __security_check_cookie
0x180043efd  lea     r11, [rsp+110h+var_20]
0x180043f05  mov     rbx, [r11+38h]
0x180043f09  mov     rsi, [r11+40h]
0x180043f0d  mov     rsp, r11
0x180043f10  pop     r15
0x180043f12  pop     r14
0x180043f14  pop     r13
0x180043f16  pop     rdi
0x180043f17  pop     rbp
0x180043f18  retn
0x180043f1a  mov     edx, ebx; int
0x180043f1c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043f20  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043f25  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043f2c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043f30  call    _CxxThrowException_0
0x180043f36  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180043f3b  mov     rdx, rax
0x180043f3e  mov     ecx, 8000FFFFh
0x180043f43  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180043f48  mov     r9d, eax; char *
0x180043f4b  mov     rcx, [rbp+5Fh]; this
0x180043f4f  mov     [rsp+110h+var_E8], rdx; char *
0x180043f54  lea     rax, aGetvaluesIppAt; "GetValues: IPP attribute '%hs' contains"...
0x180043f5b  mov     qword ptr [rsp+110h+cbData], rax; int
0x180043f60  lea     r8, aOnecoreuapInte_3; "OneCoreUap\\Internal\\PrintScan\\inc\\I"...
0x180043f67  mov     edx, 4FCh; void *
0x180043f6c  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
