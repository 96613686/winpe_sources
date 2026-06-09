# GetDetailedAppInventoryOrphanFile(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,ushort * *)

- ea: `0x1800629a0`
- end: `0x180062fa3`
- name: `?GetDetailedAppInventoryOrphanFile@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAPEAG@Z`
- size: `1539`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ecac`
- `0x180016510`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x180026d38`
- `0x1800289d0`
- `0x18002bdfc`
- `0x18002d3b8`
- `0x18002d5d0`
- `0x18002debc`
- `0x18002ee80`
- `0x18002ff68`
- `0x1800403ac`
- `0x18004d900`
- `0x18005198c`
- `0x180051bc0`
- `0x180056140`
- `0x1800568f8`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x1800629a0`
- `0x180064288`
- `0x180067c64`
- `0x1800f863c`
- `0x1800fbd50`
- `0x18010ca00`
- `0x180125400`
- `0x180130010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800629f6`
- `KERNEL32!GetCurrentThread` at `0x1800629f6`
- `KERNEL32!QueryThreadCycleTime` at `0x180062a04`
- `KERNEL32!QueryThreadCycleTime` at `0x180062a04`
- `KERNEL32!GetTickCount` at `0x180062a0b`
- `KERNEL32!GetTickCount` at `0x180062e61`
- `KERNEL32!GetTickCount` at `0x180062a0b`
- `KERNEL32!GetTickCount` at `0x180062e61`
- `OLEAUT32!__imp_VariantClear` at `0x180062e28`
- `OLEAUT32!__imp_VariantClear` at `0x180062e28`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetDetailedAppInventoryOrphanFile(__int64 *a1, __int64 a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // edx
  struct THUNKS *v6; // rcx
  unsigned __int16 v7; // r8
  unsigned int v8; // edx
  int v9; // edi
  int v11; // edi
  File *v12; // rax
  const unsigned __int16 *v13; // rdx
  int v14; // edi
  __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // rax
  _bstr_t *v18; // rax
  char v19; // di
  __int64 v20; // rax
  int v21; // [rsp+20h] [rbp-1738h]
  int v22; // [rsp+40h] [rbp-1718h] BYREF
  int v23; // [rsp+44h] [rbp-1714h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-1710h]
  _BYTE v25[4]; // [rsp+4Ch] [rbp-170Ch] BYREF
  int v26; // [rsp+50h] [rbp-1708h]
  File *v27; // [rsp+58h] [rbp-1700h] BYREF
  File *v28[2]; // [rsp+60h] [rbp-16F8h] BYREF
  File *v29; // [rsp+70h] [rbp-16E8h]
  unsigned __int64 CycleTime[5]; // [rsp+78h] [rbp-16E0h] BYREF
  _BYTE v31[240]; // [rsp+A0h] [rbp-16B8h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp-15C8h] BYREF
  __int64 v33; // [rsp+1B0h] [rbp-15A8h] BYREF
  _BYTE v34[80]; // [rsp+1B8h] [rbp-15A0h] BYREF
  __int64 v35; // [rsp+208h] [rbp-1550h]
  __int16 v36; // [rsp+210h] [rbp-1548h]
  __int64 v37; // [rsp+218h] [rbp-1540h]
  __int128 v38; // [rsp+220h] [rbp-1538h]
  __int64 v39; // [rsp+230h] [rbp-1528h]
  int v40; // [rsp+238h] [rbp-1520h]
  char v41; // [rsp+23Ch] [rbp-151Ch]
  __int64 v42; // [rsp+250h] [rbp-1508h] BYREF
  _BYTE v43[80]; // [rsp+258h] [rbp-1500h] BYREF
  __int64 v44; // [rsp+2A8h] [rbp-14B0h]
  __int16 v45; // [rsp+2B0h] [rbp-14A8h]
  __int64 v46; // [rsp+2B8h] [rbp-14A0h]
  __int128 v47; // [rsp+2C0h] [rbp-1498h]
  __int64 v48; // [rsp+2D0h] [rbp-1488h]
  int v49; // [rsp+2D8h] [rbp-1480h]
  char v50; // [rsp+2DCh] [rbp-147Ch]
  _BYTE v51[32]; // [rsp+2E0h] [rbp-1478h] BYREF
  _BYTE v52[240]; // [rsp+300h] [rbp-1458h] BYREF
  _QWORD v53[102]; // [rsp+3F0h] [rbp-1368h] BYREF
  _BYTE v54[4096]; // [rsp+720h] [rbp-1038h] BYREF

  CycleTime[1] = -2;
  v26 = 0;
  v24 = 0;
  CycleTime[0] = 0;
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, CycleTime);
  GetTickCount();
  DownlevelThunksInitEx(v6, v5);
  v23 = -2147221008;
  v22 = -2147221008;
  if ( IsWindowsVersionOrGreater(6u, 2u, v7) )
  {
    v9 = Common::AutoWinRTInitialize::Initialize(&v22);
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventoryOrphanFile", 200, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v22);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
      return (unsigned int)v9;
    }
  }
  else
  {
    v11 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v23, v8);
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventoryOrphanFile", 204, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v22);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
      return (unsigned int)v11;
    }
  }
  memset_0(v34, 0, 0x4Eu);
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v35 = 0;
  v33 = 0;
  memset_0(v43, 0, 0x4Eu);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v44 = 0;
  v42 = 0;
  v27 = (File *)operator new(0x330u);
  v12 = File::File(v27);
  v13 = (const unsigned __int16 *)&File::FileCacheProviderName;
  if ( (unsigned __int64)qword_180183038 > 7 )
    v13 = (const unsigned __int16 *)File::FileCacheProviderName;
  v14 = TelCacheProvider::Initialize(&v42, v13, ((unsigned __int64)v12 + 8) & -(__int64)(v12 != 0), 0, 3, 5u, 0x1F4u);
  if ( v14 >= 0 )
  {
    ConfigSettings::ConfigSettings(v52, 1, &v33, &v42);
    *(_OWORD *)v28 = 0;
    v29 = 0;
    File::File((File *)v54);
    v15 = *a1;
    v16 = a1[1];
    while ( v15 != v16 )
    {
      std::wstring::wstring(v51, v15);
      v17 = std::wstring::wstring(v31, v51);
      File::GetFilePathFromCache(&pvarg, &v42, v17);
      if ( pvarg.pRecInfo )
      {
        File::File((File *)v53, v21, 1);
        if ( *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v53[0] + 16LL))(v53) + 16) )
        {
          if ( v28[1] == v29 )
          {
            std::vector<File>::_Emplace_reallocate<File const &>(v28, v28[1], v53);
          }
          else
          {
            File::File(v28[1], (const struct File *)v53);
            v28[1] = (File *)((char *)v28[1] + 816);
          }
        }
        File::~File((File *)v53);
      }
      std::wstring::~wstring(&pvarg);
      std::wstring::~wstring(v51);
      v15 += 32;
    }
    pvarg.vt = 11;
    if ( a2 )
      pvarg.iVal = -1;
    else
      pvarg.iVal = 0;
    v26 = 1;
    v18 = _bstr_t::_bstr_t((_bstr_t *)&v27, (const struct _variant_t *)&pvarg);
    if ( !_bstr_t::length(v18) || (v19 = 1, !(0xFAFAFAFAFAFAFAFBuLL * ((v28[1] - v28[0]) >> 4))) )
      v19 = 0;
    _bstr_t::~_bstr_t((_bstr_t *)&v27);
    VariantClear(&pvarg);
    if ( v19 )
    {
      v20 = std::vector<File>::vector<File>(&pvarg, v28);
      XmlBuilder::XmlBuilder(v25, v52, v20, a2);
      GetTickCount();
      AslLogCallPrintf(
        3,
        (unsigned int)"GetDetailedAppInventoryOrphanFile",
        244,
        (unsigned int)"GetDetailedAppInventoryOrphanFile elapsed time: %d");
      File::~File((File *)v54);
      std::vector<File>::_Tidy(v28);
      ConfigSettings::~ConfigSettings((ConfigSettings *)v52);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v42);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v33);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v22);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
      return v24;
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventoryOrphanFile", 241, (unsigned int)"[%#x]");
      File::~File((File *)v54);
      std::vector<File>::_Tidy(v28);
      ConfigSettings::~ConfigSettings((ConfigSettings *)v52);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v42);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v33);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v22);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
      return 2147500037LL;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventoryOrphanFile", 211, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v42);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v33);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v22);
    Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x1800629a0  push    rsi
0x1800629a2  push    rdi
0x1800629a3  push    r12
0x1800629a5  push    r14
0x1800629a7  push    r15
0x1800629a9  mov     eax, 1730h
0x1800629ae  call    _alloca_probe
0x1800629b3  sub     rsp, rax
0x1800629b6  mov     [rsp+1758h+var_16D8], 0FFFFFFFFFFFFFFFEh
0x1800629c2  mov     [rsp+1758h+arg_10], rbx
0x1800629ca  mov     rax, cs:__security_cookie
0x1800629d1  xor     rax, rsp
0x1800629d4  mov     [rsp+1758h+var_38], rax
0x1800629dc  mov     r14, rdx
0x1800629df  mov     rsi, rcx
0x1800629e2  xor     r12d, r12d
0x1800629e5  mov     ebx, r12d
0x1800629e8  mov     [rsp+1758h+var_1708], ebx
0x1800629ec  mov     [rsp+1758h+var_1710], r12d
0x1800629f1  mov     [rsp+1758h+CycleTime], r12
0x1800629f6  call    cs:__imp_GetCurrentThread
0x1800629fc  mov     rcx, rax; ThreadHandle
0x1800629ff  lea     rdx, [rsp+1758h+CycleTime]; CycleTime
0x180062a04  call    cs:__imp_QueryThreadCycleTime
0x180062a0a  nop
0x180062a0b  call    cs:__imp_GetTickCount
0x180062a11  mov     r15d, eax
0x180062a14  call    ?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z; DownlevelThunksInitEx(THUNKS *,ulong)
0x180062a19  mov     eax, 800401F0h
0x180062a1e  mov     [rsp+1758h+var_1714], eax
0x180062a22  mov     [rsp+1758h+var_1718], eax
0x180062a26  lea     edx, [r12+2]; unsigned __int16
0x180062a2b  lea     ecx, [rdx+4]; unsigned __int16
0x180062a2e  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180062a33  test    al, al
0x180062a35  jz      short loc_180062A8A
0x180062a37  lea     rcx, [rsp+1758h+var_1718]
0x180062a3c  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x180062a41  mov     edi, eax
0x180062a43  test    eax, eax
0x180062a45  jns     loc_180062AD9
0x180062a4b  mov     [rsp+1758h+var_1738], eax
0x180062a4f  lea     r9, asc_18013E640; "[%#x]"
0x180062a56  mov     r8d, 0C8h
0x180062a5c  lea     rdx, aGetdetailedapp_7; "GetDetailedAppInventoryOrphanFile"
0x180062a63  lea     ecx, [r12+1]
0x180062a68  call    AslLogCallPrintf
0x180062a6d  nop
0x180062a6e  lea     rcx, [rsp+1758h+var_1718]; this
0x180062a73  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180062a78  nop
0x180062a79  lea     rcx, [rsp+1758h+var_1714]; this
0x180062a7e  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180062a83  mov     eax, edi
0x180062a85  jmp     loc_180062EEA
0x180062a8a  lea     rcx, [rsp+1758h+var_1714]; this
0x180062a8f  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180062a94  mov     edi, eax
0x180062a96  test    eax, eax
0x180062a98  jns     short loc_180062AD9
0x180062a9a  mov     [rsp+1758h+var_1738], eax
0x180062a9e  lea     r9, asc_18013E640; "[%#x]"
0x180062aa5  mov     r8d, 0CCh
0x180062aab  lea     rdx, aGetdetailedapp_7; "GetDetailedAppInventoryOrphanFile"
0x180062ab2  mov     ecx, 1
0x180062ab7  call    AslLogCallPrintf
0x180062abc  nop
0x180062abd  lea     rcx, [rsp+1758h+var_1718]; this
0x180062ac2  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180062ac7  nop
0x180062ac8  lea     rcx, [rsp+1758h+var_1714]; this
0x180062acd  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180062ad2  mov     eax, edi
0x180062ad4  jmp     loc_180062EEA
0x180062ad9  mov     edi, 4Eh ; 'N'
0x180062ade  mov     r8d, edi; Size
0x180062ae1  xor     edx, edx; Val
0x180062ae3  lea     rcx, [rsp+1758h+var_15A0]; void *
0x180062aeb  call    memset_0
0x180062af0  mov     [rsp+1758h+var_1548], r12w
0x180062af9  mov     [rsp+1758h+var_1540], r12
0x180062b01  xorps   xmm0, xmm0
0x180062b04  movdqa  [rsp+1758h+var_1538], xmm0
0x180062b0d  mov     [rsp+1758h+var_1528], r12
0x180062b15  mov     [rsp+1758h+var_1520], r12d
0x180062b1d  mov     [rsp+1758h+var_151C], r12b
0x180062b25  mov     [rsp+1758h+var_1550], r12
0x180062b2d  mov     [rsp+1758h+var_15A8], r12
0x180062b35  mov     r8d, edi; Size
0x180062b38  xor     edx, edx; Val
0x180062b3a  lea     rcx, [rsp+1758h+var_1500]; void *
0x180062b42  call    memset_0
0x180062b47  mov     [rsp+1758h+var_14A8], r12w
0x180062b50  mov     [rsp+1758h+var_14A0], r12
0x180062b58  xorps   xmm0, xmm0
0x180062b5b  movdqa  [rsp+1758h+var_1498], xmm0
0x180062b64  mov     [rsp+1758h+var_1488], r12
0x180062b6c  mov     [rsp+1758h+var_1480], r12d
0x180062b74  mov     [rsp+1758h+var_147C], r12b
0x180062b7c  mov     [rsp+1758h+var_14B0], r12
0x180062b84  mov     [rsp+1758h+var_1508], r12
0x180062b8c  mov     ecx, 330h; Size
0x180062b91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062b96  mov     [rsp+1758h+var_1700], rax
0x180062b9b  mov     rcx, rax; this
0x180062b9e  call    ??0File@@QEAA@XZ; File::File(void)
0x180062ba3  nop
0x180062ba4  lea     rcx, [rax+8]
0x180062ba8  neg     rax
0x180062bab  sbb     r8, r8
0x180062bae  and     r8, rcx
0x180062bb1  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180062bb8  cmp     cs:qword_180183038, 7
0x180062bc0  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180062bc8  mov     [rsp+1758h+var_1728], 1F4h
0x180062bd0  mov     [rsp+1758h+var_1730], 5
0x180062bd8  mov     [rsp+1758h+var_1738], 3
0x180062be0  xor     r9d, r9d
0x180062be3  lea     rcx, [rsp+1758h+var_1508]
0x180062beb  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180062bf0  mov     edi, eax
0x180062bf2  test    eax, eax
0x180062bf4  jns     short loc_180062C51
0x180062bf6  mov     [rsp+1758h+var_1738], eax
0x180062bfa  lea     r9, asc_18013E640; "[%#x]"
0x180062c01  mov     r8d, 0D3h
0x180062c07  lea     rdx, aGetdetailedapp_7; "GetDetailedAppInventoryOrphanFile"
0x180062c0e  mov     ecx, 1
0x180062c13  call    AslLogCallPrintf
0x180062c18  nop
0x180062c19  lea     rcx, [rsp+1758h+var_1508]; this
0x180062c21  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180062c26  nop
0x180062c27  lea     rcx, [rsp+1758h+var_15A8]; this
0x180062c2f  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180062c34  nop
0x180062c35  lea     rcx, [rsp+1758h+var_1718]; this
0x180062c3a  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180062c3f  nop
0x180062c40  lea     rcx, [rsp+1758h+var_1714]; this
0x180062c45  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180062c4a  mov     eax, edi
0x180062c4c  jmp     loc_180062EEA
0x180062c51  lea     r9, [rsp+1758h+var_1508]
0x180062c59  lea     r8, [rsp+1758h+var_15A8]
0x180062c61  mov     edx, 1
0x180062c66  lea     rcx, [rsp+1758h+var_1458]
0x180062c6e  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool)
0x180062c73  nop
0x180062c74  xorps   xmm1, xmm1
0x180062c77  movdqu  xmmword ptr [rsp+1758h+var_16F8], xmm1
0x180062c7d  mov     [rsp+1758h+var_16E8], r12
0x180062c82  lea     rcx, [rsp+1758h+var_1038]; this
0x180062c8a  call    ??0File@@QEAA@XZ; File::File(void)
0x180062c8f  nop
0x180062c90  mov     rdi, [rsi]
0x180062c93  mov     rsi, [rsi+8]
0x180062c97  cmp     rdi, rsi
0x180062c9a  jz      loc_180062D96
0x180062ca0  mov     rdx, rdi
0x180062ca3  lea     rcx, [rsp+1758h+var_1478]
0x180062cab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180062cb0  nop
0x180062cb1  lea     rdx, [rsp+1758h+var_1478]
0x180062cb9  lea     rcx, [rsp+1758h+var_16B8]
0x180062cc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180062cc6  mov     r8, rax
0x180062cc9  lea     rdx, [rsp+1758h+var_1508]
0x180062cd1  lea     rcx, [rsp+1758h+pvarg]
0x180062cd9  call    ?GetFilePathFromCache@File@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVTelCacheProvider@@V23@@Z; File::GetFilePathFromCache(TelCacheProvider *,std::wstring)
0x180062cde  nop
0x180062cdf  cmp     qword ptr [rsp+1758h+pvarg+10h], r12
0x180062ce7  jbe     loc_180062D72
0x180062ced  mov     byte ptr [rsp+1758h+var_1730], 1
0x180062cf2  lea     rdx, [rsp+1758h+pvarg]
0x180062cfa  lea     rcx, [rsp+1758h+var_1368]
0x180062d02  call    ??0File@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N111@Z; File::File(std::wstring const &,bool,bool,bool,bool)
0x180062d07  nop
0x180062d08  mov     rax, [rsp+1758h+var_1368]
0x180062d10  lea     rcx, [rsp+1758h+var_1368]
0x180062d18  mov     rax, [rax+10h]
0x180062d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d21  cmp     [rax+10h], r12
0x180062d25  jbe     short loc_180062D64
0x180062d27  mov     rax, [rsp+1758h+var_16F8+8]
0x180062d2c  cmp     rax, [rsp+1758h+var_16E8]
0x180062d31  jz      short loc_180062D4E
0x180062d33  lea     rdx, [rsp+1758h+var_1368]; struct File *
0x180062d3b  mov     rcx, rax; this
0x180062d3e  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x180062d43  add     [rsp+1758h+var_16F8+8], 330h
0x180062d4c  jmp     short loc_180062D64
0x180062d4e  lea     r8, [rsp+1758h+var_1368]
0x180062d56  mov     rdx, rax
0x180062d59  lea     rcx, [rsp+1758h+var_16F8]
0x180062d5e  call    ??$_Emplace_reallocate@AEBVFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@AEBV2@@Z; std::vector<File>::_Emplace_reallocate<File const &>(File * const,File const &)
0x180062d63  nop
0x180062d64  lea     rcx, [rsp+1758h+var_1368]; this
0x180062d6c  call    ??1File@@UEAA@XZ; File::~File(void)
0x180062d71  nop
0x180062d72  lea     rcx, [rsp+1758h+pvarg]
0x180062d7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180062d7f  nop
0x180062d80  lea     rcx, [rsp+1758h+var_1478]
0x180062d88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180062d8d  add     rdi, 20h ; ' '
0x180062d91  jmp     loc_180062C97
0x180062d96  mov     eax, 0Bh
0x180062d9b  mov     word ptr [rsp+1758h+pvarg], ax
0x180062da3  test    r14, r14
0x180062da6  jz      short loc_180062DB5
0x180062da8  or      eax, 0FFFFFFFFh
0x180062dab  mov     word ptr [rsp+1758h+pvarg+8], ax
0x180062db3  jmp     short loc_180062DBE
0x180062db5  mov     word ptr [rsp+1758h+pvarg+8], r12w
0x180062dbe  or      ebx, 1
0x180062dc1  mov     [rsp+1758h+var_1708], ebx
0x180062dc5  lea     rdx, [rsp+1758h+pvarg]; struct _variant_t *
0x180062dcd  lea     rcx, [rsp+1758h+var_1700]; this
0x180062dd2  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180062dd7  or      ebx, 2
0x180062dda  mov     rcx, rax; this
0x180062ddd  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180062de2  test    eax, eax
0x180062de4  jz      short loc_180062E0A
0x180062de6  mov     rax, [rsp+1758h+var_16F8+8]
0x180062deb  sub     rax, [rsp+1758h+var_16F8]
0x180062df0  sar     rax, 4
0x180062df4  mov     rcx, 0FAFAFAFAFAFAFAFBh
0x180062dfe  imul    rax, rcx
0x180062e02  test    rax, rax
0x180062e05  mov     dil, 1
0x180062e08  jnz     short loc_180062E0D
0x180062e0a  mov     dil, r12b
0x180062e0d  and     ebx, 0FFFFFFFDh
0x180062e10  lea     rcx, [rsp+1758h+var_1700]; this
0x180062e15  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180062e1a  nop
0x180062e1b  test    bl, 1
0x180062e1e  jz      short loc_180062E2E
0x180062e20  lea     rcx, [rsp+1758h+pvarg]; pvarg
0x180062e28  call    cs:__imp_VariantClear
0x180062e2e  test    dil, dil
0x180062e31  jz      loc_180062F12
0x180062e37  lea     rdx, [rsp+1758h+var_16F8]
0x180062e3c  lea     rcx, [rsp+1758h+pvarg]
0x180062e44  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180062e49  mov     r9, r14
0x180062e4c  mov     r8, rax
0x180062e4f  lea     rdx, [rsp+1758h+var_1458]
0x180062e57  lea     rcx, [rsp+1758h+var_170C]
0x180062e5c  call    ??0XmlBuilder@@QEAA@AEBVConfigSettings@@V?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@PEAPEAG@Z; XmlBuilder::XmlBuilder(ConfigSettings const &,std::vector<File>,ushort * *)
0x180062e61  call    cs:__imp_GetTickCount
0x180062e67  sub     eax, r15d
0x180062e6a  mov     [rsp+1758h+var_1738], eax
0x180062e6e  lea     r9, aGetdetailedapp_3; "GetDetailedAppInventoryOrphanFile elaps"...
0x180062e75  mov     r8d, 0F4h
0x180062e7b  lea     rdx, aGetdetailedapp_7; "GetDetailedAppInventoryOrphanFile"
0x180062e82  mov     ecx, 3
0x180062e87  call    AslLogCallPrintf
0x180062e8c  nop
0x180062e8d  lea     rcx, [rsp+1758h+var_1038]; this
0x180062e95  call    ??1File@@UEAA@XZ; File::~File(void)
0x180062e9a  nop
0x180062e9b  lea     rcx, [rsp+1758h+var_16F8]
0x180062ea0  call    ?_Tidy@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAXXZ; std::vector<File>::_Tidy(void)
0x180062ea5  nop
0x180062ea6  lea     rcx, [rsp+1758h+var_1458]; this
0x180062eae  call    ??1ConfigSettings@@UEAA@XZ; ConfigSettings::~ConfigSettings(void)
0x180062eb3  nop
0x180062eb4  lea     rcx, [rsp+1758h+var_1508]; this
0x180062ebc  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180062ec1  nop
0x180062ec2  lea     rcx, [rsp+1758h+var_15A8]; this
0x180062eca  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180062ecf  nop
0x180062ed0  lea     rcx, [rsp+1758h+var_1718]; this
0x180062ed5  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180062eda  nop
0x180062edb  lea     rcx, [rsp+1758h+var_1714]; this
0x180062ee0  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180062ee5  nop
0x180062ee6  mov     eax, [rsp+1758h+var_1710]
0x180062eea  mov     rcx, [rsp+1758h+var_38]
0x180062ef2  xor     rcx, rsp; StackCookie
0x180062ef5  call    __security_check_cookie
0x180062efa  mov     rbx, [rsp+1758h+arg_10]
0x180062f02  add     rsp, 1730h
0x180062f09  pop     r15
0x180062f0b  pop     r14
0x180062f0d  pop     r12
0x180062f0f  pop     rdi
0x180062f10  pop     rsi
0x180062f11  retn
0x180062f12  mov     ebx, 80004005h
0x180062f17  mov     [rsp+1758h+var_1738], ebx
0x180062f1b  lea     r9, asc_18013E640; "[%#x]"
0x180062f22  mov     r8d, 0F1h
0x180062f28  lea     rdx, aGetdetailedapp_7; "GetDetailedAppInventoryOrphanFile"
0x180062f2f  mov     ecx, 1
  ... truncated ...
```
