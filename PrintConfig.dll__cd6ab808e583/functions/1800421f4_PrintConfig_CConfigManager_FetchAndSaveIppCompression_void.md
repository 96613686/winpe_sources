# PrintConfig::CConfigManager::FetchAndSaveIppCompression(void)

- ea: `0x1800421f4`
- end: `0x180042667`
- name: `?FetchAndSaveIppCompression@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `1139`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x180005f6c`
- `0x18000da28`
- `0x18000dadc`
- `0x18000f380`
- `0x18000f590`
- `0x180014a48`
- `0x1800183a0`
- `0x1800183f8`
- `0x180020560`
- `0x180021820`
- `0x18002441c`
- `0x18003c954`
- `0x18003dd10`
- `0x18003f318`
- `0x1800421f4`
- `0x180044700`
- `0x1800449fc`
- `0x18004a458`
- `0x18004a650`
- `0x1801adb58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18004232a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180042381`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18004241c`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18004232a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180042381`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18004241c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800424f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800424f9`
- `WINSPOOL!SetPrinterDataW` at `0x18004259a`
- `WINSPOOL!SetPrinterDataW` at `0x18004259a`

## string_xrefs

- `0x1800424a7`: `Failed to get printer attributes from cache.`
- `0x18004253e`: `'compress' is the only compression algorithm supported by this printer`
- `0x1800424ae`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180042545`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x180042565`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x1800425b9`: `PrintConfig::CConfigManager::FetchAndSaveIppCompression`
- `0x1800422bf`: `Failed to get compression supported attribute from cache.`
- `0x1800423f0`: `compress`
- `0x18004258f`: `ippCompressionSupported`
- `0x18004255e`: `SetPrinterData compression: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PrintConfig::CConfigManager::FetchAndSaveIppCompression(PrintConfig::CConfigManager *this)
{
  char v2; // r15
  unsigned __int16 *v3; // rdx
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int128 *p_pExceptionObject; // rdx
  char **v7; // rcx
  int v8; // ebx
  __int128 *v9; // rdx
  char **v10; // rcx
  int v11; // ebx
  LPBYTE *v12; // rbx
  __int128 *v13; // rdx
  char **v14; // rcx
  int v15; // ebx
  LPBYTE *v16; // rcx
  __int128 *v17; // rdx
  LPBYTE *v18; // rcx
  bool v19; // bl
  _DWORD *v20; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v21; // rcx
  LPBYTE *v22; // r8
  BYTE *v23; // r9
  signed int v24; // eax
  signed int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r8
  unsigned int v28; // eax
  const char *v29; // rdx
  __int64 v30; // [rsp+38h] [rbp-89h] BYREF
  __int128 v31; // [rsp+40h] [rbp-81h] BYREF
  __int64 v32; // [rsp+50h] [rbp-71h]
  __int64 v33; // [rsp+58h] [rbp-69h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-61h] BYREF
  __int128 v35; // [rsp+70h] [rbp-51h]
  LPBYTE pData[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v37; // [rsp+90h] [rbp-31h]
  unsigned __int64 v38; // [rsp+98h] [rbp-29h]
  char *v39[3]; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v40; // [rsp+B8h] [rbp-9h]
  _BYTE v41[8]; // [rsp+C0h] [rbp-1h] BYREF
  _BYTE v42[32]; // [rsp+C8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  v33 = -2;
  v2 = 0;
  *(_OWORD *)pData = 0;
  v37 = 0;
  v38 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)pData, L"none", 4u);
  PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(
    (PrintCore::IppPrinterAttributesCache *)v41,
    *((void **)this + 8));
  v31 = 0;
  v32 = 0;
  if ( (int)PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache((__int64)v41, &v31) < 0 )
  {
    v3 = L"Failed to get printer attributes from cache.";
    goto LABEL_35;
  }
  std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const *>(
    &v30,
    v31,
    *((_QWORD *)&v31 + 1),
    &PrintCore::PrinterAttributes::CompressionSupported);
  if ( v30 == *((_QWORD *)&v31 + 1) )
  {
    v3 = L"Failed to get compression supported attribute from cache.";
LABEL_35:
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
      v3);
    goto LABEL_36;
  }
  v4 = *(_QWORD *)(v30 + 40);
  v5 = *(_QWORD *)(v30 + 32);
  if ( v5 == v4 )
  {
    v26 = std::string::c_str();
    v28 = wil::verify_hresult<long>(2147549183LL, v26, v27);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x501,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\IppEncoding.hxx",
      (const char *)v28,
      (int)"GetValues: IPP attribute '%hs' contains no values",
      v29);
  }
  while ( 1 )
  {
    PrintCore::IppValue::GetStringValue(v5, v39);
    pExceptionObject = 0;
    v35 = 0;
    std::string::_Construct<1,char const *>(&pExceptionObject, "gzip", 4);
    p_pExceptionObject = &pExceptionObject;
    if ( *((_QWORD *)&v35 + 1) > 0xFu )
      p_pExceptionObject = (__int128 *)pExceptionObject;
    v7 = v39;
    if ( v40 > 0xF )
      v7 = (char **)v39[0];
    v8 = _o__stricmp(v7, p_pExceptionObject);
    std::string::~string((char **)&pExceptionObject);
    if ( !v8 )
      break;
    pExceptionObject = 0;
    v35 = 0;
    std::string::_Construct<1,char const *>(&pExceptionObject, "deflate", 7);
    v9 = &pExceptionObject;
    if ( *((_QWORD *)&v35 + 1) > 0xFu )
      v9 = (__int128 *)pExceptionObject;
    v10 = v39;
    if ( v40 > 0xF )
      v10 = (char **)v39[0];
    v11 = _o__stricmp(v10, v9);
    std::string::~string((char **)&pExceptionObject);
    if ( v11 )
    {
      pExceptionObject = 0;
      v35 = 0;
      std::string::_Construct<1,char const *>(&pExceptionObject, "compress", 8);
      v13 = &pExceptionObject;
      if ( *((_QWORD *)&v35 + 1) > 0xFu )
        v13 = (__int128 *)pExceptionObject;
      v14 = v39;
      if ( v40 > 0xF )
        v14 = (char **)v39[0];
      v15 = _o__stricmp(v14, v13);
      std::string::~string((char **)&pExceptionObject);
      if ( !v15 )
        v2 = 1;
    }
    else if ( v38 < 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pData);
    }
    else
    {
      v12 = pData;
      if ( v38 > 7 )
        v12 = (LPBYTE *)pData[0];
      v37 = 7;
      memmove_0(v12, L"deflate", 0xEu);
      *((_WORD *)v12 + 7) = 0;
    }
    std::string::~string(v39);
    v5 += 88;
    if ( v5 == v4 )
      goto LABEL_36;
  }
  v16 = pData;
  if ( v38 < 4 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pData);
  }
  else
  {
    if ( v38 > 7 )
      v16 = (LPBYTE *)pData[0];
    v37 = 4;
    *v16 = (LPBYTE)0x700069007A0067LL;
    *((_WORD *)v16 + 4) = 0;
  }
  std::string::~string(v39);
LABEL_36:
  pExceptionObject = 0;
  v35 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, L"none", 4u);
  v17 = &pExceptionObject;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    v17 = (__int128 *)pExceptionObject;
  v18 = pData;
  if ( v38 > 7 )
    v18 = (LPBYTE *)pData[0];
  v19 = !(unsigned int)_o__wcsicmp(v18, v17) && v2;
  std::wstring::~wstring(&pExceptionObject);
  if ( v19 )
  {
    v20 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
    if ( v20 && *v20 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
      Print::Driver::Telemetry::PrintConfigTelemetry::SupportsCompressOnly_(v21, *((unsigned __int16 *const *)this + 2));
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
      L"'compress' is the only compression algorithm supported by this printer");
  }
  v22 = pData;
  if ( v38 > 7 )
    v22 = (LPBYTE *)pData[0];
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
    L"SetPrinterData compression: %ws",
    v22);
  v23 = (BYTE *)pData;
  if ( v38 > 7 )
    v23 = pData[0];
  v24 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"ippCompressionSupported", 1u, v23, 2 * v37 + 2);
  v25 = v24;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchAndSaveIppCompression",
    L"SetPrinterData returned with: 0x%x",
    (unsigned int)v25);
  if ( v25 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v25);
    throw (hr_error *)&pExceptionObject;
  }
  std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(&v31);
  std::wstring::~wstring(v42);
  std::wstring::~wstring(pData);
}

```

## disassembly

```asm
0x1800421f4  mov     rax, rsp
0x1800421f7  push    rbp
0x1800421f8  push    rdi
0x1800421f9  push    r13
0x1800421fb  push    r14
0x1800421fd  push    r15
0x1800421ff  lea     rbp, [rax-5Fh]
0x180042203  sub     rsp, 0F0h
0x18004220a  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFEh
0x180042212  mov     [rax+10h], rbx
0x180042216  mov     [rax+18h], rsi
0x18004221a  mov     rax, cs:__security_cookie
0x180042221  xor     rax, rsp
0x180042224  mov     [rbp+57h+var_30], rax
0x180042228  mov     r14, rcx
0x18004222b  xor     r15b, r15b
0x18004222e  xorps   xmm0, xmm0
0x180042231  movups  xmmword ptr [rbp+57h+pData], xmm0
0x180042235  mov     [rbp+57h+var_88], 0
0x18004223d  mov     [rbp+57h+var_80], 0
0x180042245  mov     r8d, 4
0x18004224b  lea     rdx, aNone; "none"
0x180042252  lea     rcx, [rbp+57h+pData]
0x180042256  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004225b  nop
0x18004225c  mov     rdx, [r14+40h]; void *
0x180042260  lea     rcx, [rbp+57h+var_58]; this
0x180042264  call    ??0IppPrinterAttributesCache@PrintCore@@QEAA@PEAX@Z; PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(void *)
0x180042269  nop
0x18004226a  xorps   xmm0, xmm0
0x18004226d  movdqu  [rsp+110h+var_E0+8], xmm0
0x180042273  mov     [rbp+57h+var_C8], 0
0x18004227b  lea     rdx, [rsp+110h+var_E0+8]
0x180042280  lea     rcx, [rbp+57h+var_58]
0x180042284  call    ?GetPrinterAttributesCache@IppPrinterAttributesCache@PrintCore@@QEAAJAEAV?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@@Z; PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(std::vector<PrintCore::IppAttribute> &)
0x180042289  mov     edi, 1
0x18004228e  lea     r13d, [rdi+6]
0x180042292  test    eax, eax
0x180042294  js      loc_1800424A7
0x18004229a  lea     r9, ?CompressionSupported@PrinterAttributes@PrintCore@@2QEBDEB; char const * const PrintCore::PrinterAttributes::CompressionSupported
0x1800422a1  mov     r8, [rbp+57h+var_D0]
0x1800422a5  mov     rdx, qword ptr [rsp+110h+var_E0+8]
0x1800422aa  lea     rcx, [rsp+110h+var_E0]
0x1800422af  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VIppAttribute@PrintCore@@@std@@@std@@@std@@PEBD@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VIppAttribute@PrintCore@@@std@@@std@@@0@V10@V10@AEBQEBD@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const *>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PrintCore::IppAttribute>>>,char const * const &)
0x1800422b4  mov     rcx, qword ptr [rsp+110h+var_E0]
0x1800422b9  cmp     rcx, [rbp+57h+var_D0]
0x1800422bd  jnz     short loc_1800422CB
0x1800422bf  lea     rdx, aFailedToGetCom; "Failed to get compression supported att"...
0x1800422c6  jmp     loc_1800424AE
0x1800422cb  mov     rsi, [rcx+28h]
0x1800422cf  mov     rdi, [rcx+20h]
0x1800422d3  cmp     rdi, rsi
0x1800422d6  jz      loc_18004262B
0x1800422dc  lea     rdx, [rbp+57h+var_78]
0x1800422e0  mov     rcx, rdi
0x1800422e3  call    ?GetStringValue@IppValue@PrintCore@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; PrintCore::IppValue::GetStringValue(void)
0x1800422e8  nop
0x1800422e9  xorps   xmm0, xmm0
0x1800422ec  movups  [rbp+57h+pExceptionObject], xmm0
0x1800422f0  xorps   xmm1, xmm1
0x1800422f3  movdqu  [rbp+57h+var_A8], xmm1
0x1800422f8  mov     r8d, 4
0x1800422fe  lea     rdx, aGzip; "gzip"
0x180042305  lea     rcx, [rbp+57h+pExceptionObject]
0x180042309  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004230e  lea     rdx, [rbp+57h+pExceptionObject]
0x180042312  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x180042317  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x18004231c  lea     rcx, [rbp+57h+var_78]
0x180042320  cmp     [rbp+57h+var_60], 0Fh
0x180042325  cmova   rcx, [rbp+57h+var_78]
0x18004232a  call    cs:__imp__o__stricmp
0x180042330  mov     ebx, eax
0x180042332  lea     rcx, [rbp+57h+pExceptionObject]
0x180042336  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004233b  test    ebx, ebx
0x18004233d  jz      loc_180042459
0x180042343  xorps   xmm0, xmm0
0x180042346  movups  [rbp+57h+pExceptionObject], xmm0
0x18004234a  xorps   xmm1, xmm1
0x18004234d  movdqu  [rbp+57h+var_A8], xmm1
0x180042352  mov     r8, r13
0x180042355  lea     rdx, aDeflate; "deflate"
0x18004235c  lea     rcx, [rbp+57h+pExceptionObject]
0x180042360  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180042365  lea     rdx, [rbp+57h+pExceptionObject]
0x180042369  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x18004236e  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180042373  lea     rcx, [rbp+57h+var_78]
0x180042377  cmp     [rbp+57h+var_60], 0Fh
0x18004237c  cmova   rcx, [rbp+57h+var_78]
0x180042381  call    cs:__imp__o__stricmp
0x180042387  mov     ebx, eax
0x180042389  lea     rcx, [rbp+57h+pExceptionObject]
0x18004238d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180042392  test    ebx, ebx
0x180042394  jnz     short loc_1800423DB
0x180042396  cmp     [rbp+57h+var_80], r13
0x18004239a  jb      short loc_1800423C6
0x18004239c  lea     rbx, [rbp+57h+pData]
0x1800423a0  cmova   rbx, [rbp+57h+pData]
0x1800423a5  mov     [rbp+57h+var_88], r13
0x1800423a9  mov     r8d, 0Eh; Size
0x1800423af  lea     rdx, aDeflate_0; "deflate"
0x1800423b6  mov     rcx, rbx; void *
0x1800423b9  call    memmove_0
0x1800423be  xor     eax, eax
0x1800423c0  mov     [rbx+0Eh], ax
0x1800423c4  jmp     short loc_18004243C
0x1800423c6  lea     r9, aDeflate_0; "deflate"
0x1800423cd  mov     rdx, r13
0x1800423d0  lea     rcx, [rbp+57h+pData]
0x1800423d4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800423d9  jmp     short loc_18004243C
0x1800423db  xorps   xmm0, xmm0
0x1800423de  movups  [rbp+57h+pExceptionObject], xmm0
0x1800423e2  xorps   xmm1, xmm1
0x1800423e5  movdqu  [rbp+57h+var_A8], xmm1
0x1800423ea  mov     r8d, 8
0x1800423f0  lea     rdx, aCompress; "compress"
0x1800423f7  lea     rcx, [rbp+57h+pExceptionObject]
0x1800423fb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180042400  lea     rdx, [rbp+57h+pExceptionObject]
0x180042404  cmp     qword ptr [rbp+57h+var_A8+8], 0Fh
0x180042409  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x18004240e  lea     rcx, [rbp+57h+var_78]
0x180042412  cmp     [rbp+57h+var_60], 0Fh
0x180042417  cmova   rcx, [rbp+57h+var_78]
0x18004241c  call    cs:__imp__o__stricmp
0x180042422  mov     ebx, eax
0x180042424  lea     rcx, [rbp+57h+pExceptionObject]
0x180042428  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004242d  movzx   r15d, r15b
0x180042431  test    ebx, ebx
0x180042433  mov     eax, 1
0x180042438  cmovz   r15d, eax
0x18004243c  lea     rcx, [rbp+57h+var_78]
0x180042440  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180042445  add     rdi, 58h ; 'X'
0x180042449  cmp     rdi, rsi
0x18004244c  jnz     loc_1800422DC
0x180042452  mov     edi, 1
0x180042457  jmp     short loc_1800424BA
0x180042459  lea     rcx, [rbp+57h+pData]
0x18004245d  cmp     [rbp+57h+var_80], 4
0x180042462  jb      short loc_18004248A
0x180042464  cmp     [rbp+57h+var_80], r13
0x180042468  cmova   rcx, [rbp+57h+pData]
0x18004246d  mov     [rbp+57h+var_88], 4
0x180042475  mov     rax, 700069007A0067h
0x18004247f  mov     [rcx], rax
0x180042482  xor     eax, eax
0x180042484  mov     [rcx+8], ax
0x180042488  jmp     short loc_18004249C
0x18004248a  lea     r9, aGzip_0; "gzip"
0x180042491  mov     edx, 4
0x180042496  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18004249b  nop
0x18004249c  lea     rcx, [rbp+57h+var_78]
0x1800424a0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800424a5  jmp     short loc_180042452
0x1800424a7  lea     rdx, aFailedToGetPri; "Failed to get printer attributes from c"...
0x1800424ae  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x1800424b5  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800424ba  xorps   xmm0, xmm0
0x1800424bd  movups  [rbp+57h+pExceptionObject], xmm0
0x1800424c1  xorps   xmm1, xmm1
0x1800424c4  movdqu  [rbp+57h+var_A8], xmm1
0x1800424c9  mov     r8d, 4
0x1800424cf  lea     rdx, aNone; "none"
0x1800424d6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800424da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800424df  lea     rdx, [rbp+57h+pExceptionObject]
0x1800424e3  cmp     qword ptr [rbp+57h+var_A8+8], r13
0x1800424e7  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x1800424ec  lea     rcx, [rbp+57h+pData]
0x1800424f0  cmp     [rbp+57h+var_80], r13
0x1800424f4  cmova   rcx, [rbp+57h+pData]
0x1800424f9  call    cs:__imp__o__wcsicmp
0x1800424ff  test    eax, eax
0x180042501  jnz     short loc_18004250D
0x180042503  test    r15b, r15b
0x180042506  jz      short loc_18004250D
0x180042508  mov     bl, dil
0x18004250b  jmp     short loc_18004250F
0x18004250d  xor     bl, bl
0x18004250f  lea     rcx, [rbp+57h+pExceptionObject]
0x180042513  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042518  test    bl, bl
0x18004251a  jz      short loc_180042551
0x18004251c  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180042521  mov     rax, [rax+8]
0x180042525  test    rax, rax
0x180042528  jz      short loc_18004253E
0x18004252a  mov     eax, [rax]
0x18004252c  test    eax, eax
0x18004252e  jz      short loc_18004253E
0x180042530  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180042535  mov     rdx, [r14+10h]; unsigned __int16 *
0x180042539  call    ?SupportsCompressOnly_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEAG@Z; Print::Driver::Telemetry::PrintConfigTelemetry::SupportsCompressOnly_(ushort * const)
0x18004253e  lea     rdx, aCompressIsTheO; "'compress' is the only compression algo"...
0x180042545  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x18004254c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042551  lea     r8, [rbp+57h+pData]
0x180042555  cmp     [rbp+57h+var_80], r13
0x180042559  cmova   r8, [rbp+57h+pData]
0x18004255e  lea     rdx, aSetprinterdata_1; "SetPrinterData compression: %ws"
0x180042565  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x18004256c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042571  mov     eax, dword ptr [rbp+57h+var_88]
0x180042574  lea     r9, [rbp+57h+pData]
0x180042578  cmp     [rbp+57h+var_80], r13
0x18004257c  cmova   r9, [rbp+57h+pData]; pData
0x180042581  lea     eax, ds:2[rax*2]
0x180042588  mov     [rsp+110h+cbData], eax; cbData
0x18004258c  mov     r8d, edi; Type
0x18004258f  lea     rdx, aIppcompression; "ippCompressionSupported"
0x180042596  mov     rcx, [r14+40h]; hPrinter
0x18004259a  call    cs:__imp_SetPrinterDataW
0x1800425a0  mov     ebx, eax
0x1800425a2  test    eax, eax
0x1800425a4  jle     short loc_1800425AF
0x1800425a6  movzx   ebx, ax
0x1800425a9  or      ebx, 80070000h
0x1800425af  mov     r8d, ebx
0x1800425b2  lea     rdx, aSetprinterdata_2; "SetPrinterData returned with: 0x%x"
0x1800425b9  lea     rcx, aPrintconfigCco_21; "PrintConfig::CConfigManager::FetchAndSa"...
0x1800425c0  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800425c5  test    ebx, ebx
0x1800425c7  js      short loc_18004260F
0x1800425c9  lea     rcx, [rsp+110h+var_E0+8]
0x1800425ce  call    ??1?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@QEAA@XZ; std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(void)
0x1800425d3  nop
0x1800425d4  lea     rcx, [rbp+57h+var_50]
0x1800425d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800425dd  nop
0x1800425de  lea     rcx, [rbp+57h+pData]
0x1800425e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800425e7  mov     rcx, [rbp+57h+var_30]
0x1800425eb  xor     rcx, rsp; StackCookie
0x1800425ee  call    __security_check_cookie
0x1800425f3  lea     r11, [rsp+110h+var_20]
0x1800425fb  mov     rbx, [r11+38h]
0x1800425ff  mov     rsi, [r11+40h]
0x180042603  mov     rsp, r11
0x180042606  pop     r15
0x180042608  pop     r14
0x18004260a  pop     r13
0x18004260c  pop     rdi
0x18004260d  pop     rbp
0x18004260e  retn
0x18004260f  mov     edx, ebx; int
0x180042611  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180042615  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004261a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180042621  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180042625  call    _CxxThrowException_0
0x18004262b  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180042630  mov     rdx, rax
0x180042633  mov     ecx, 8000FFFFh
0x180042638  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004263d  mov     r9d, eax; char *
0x180042640  mov     rcx, [rbp+5Fh]; this
0x180042644  mov     [rsp+110h+var_E8], rdx; char *
0x180042649  lea     rax, aGetvaluesIppAt; "GetValues: IPP attribute '%hs' contains"...
0x180042650  mov     qword ptr [rsp+110h+cbData], rax; int
0x180042655  lea     r8, aOnecoreuapInte_3; "OneCoreUap\\Internal\\PrintScan\\inc\\I"...
0x18004265c  mov     edx, 501h; void *
0x180042661  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
