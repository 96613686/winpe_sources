# GetCachedAppInventory(ushort * *)

- ea: `0x180057730`
- end: `0x180057e21`
- name: `?GetCachedAppInventory@@YAJPEAPEAG@Z`
- size: `1777`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000e458`
- `0x180016510`
- `0x1800197d4`
- `0x180026d38`
- `0x1800289d0`
- `0x18002bdfc`
- `0x18002d3b8`
- `0x18002d5d0`
- `0x18002debc`
- `0x18002ee80`
- `0x18002ff68`
- `0x1800403ac`
- `0x1800417a8`
- `0x18005169c`
- `0x18005198c`
- `0x180051bc0`
- `0x180052dc0`
- `0x180052fc8`
- `0x180056140`
- `0x180057730`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x18005e100`
- `0x18005eb3c`
- `0x180064288`
- `0x180067c64`
- `0x1800f863c`
- `0x1800f9c18`
- `0x18010bf8c`
- `0x180125400`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180057782`
- `KERNEL32!GetCurrentThread` at `0x180057db6`
- `KERNEL32!GetCurrentThread` at `0x180057782`
- `KERNEL32!GetCurrentThread` at `0x180057db6`
- `KERNEL32!QueryThreadCycleTime` at `0x180057790`
- `KERNEL32!QueryThreadCycleTime` at `0x180057dc4`
- `KERNEL32!QueryThreadCycleTime` at `0x180057790`
- `KERNEL32!QueryThreadCycleTime` at `0x180057dc4`
- `KERNEL32!GetTickCount` at `0x180057797`
- `KERNEL32!GetTickCount` at `0x180057c82`
- `KERNEL32!GetTickCount` at `0x180057797`
- `KERNEL32!GetTickCount` at `0x180057c82`
- `OLEAUT32!__imp_VariantClear` at `0x180057c22`
- `OLEAUT32!__imp_VariantClear` at `0x180057c22`

## string_xrefs

- `0x1800577ea`: `GetCachedAppInventory`
- `0x180057837`: `GetCachedAppInventory`
- `0x18005792e`: `GetCachedAppInventory`
- `0x180057a36`: `GetCachedAppInventory`
- `0x180057c9c`: `GetCachedAppInventory`
- `0x180057d33`: `GetCachedAppInventory`
- `0x180057c8f`: `GetCachedAppInventory elapsed time: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall GetCachedAppInventory(unsigned __int16 **a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // edx
  struct THUNKS *v4; // rcx
  unsigned __int16 v5; // r8
  unsigned int v6; // edx
  int v7; // ebx
  int v9; // ebx
  Application *v10; // rax
  const unsigned __int16 *v11; // rdx
  int v12; // ebx
  File *v13; // rax
  const unsigned __int16 *v14; // rdx
  int v15; // ebx
  __int64 *ApplicationsFromCache; // rdi
  __int64 v17; // rsi
  __int64 v18; // rbx
  __int64 FilesFromCache; // rax
  _bstr_t *v20; // rax
  char v21; // bl
  int v22; // ebx
  int v23; // eax
  HANDLE v24; // rax
  int v25; // [rsp+40h] [rbp-13E8h] BYREF
  int v26; // [rsp+44h] [rbp-13E4h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-13E0h]
  char v28; // [rsp+4Ch] [rbp-13DCh] BYREF
  VARIANTARG *p_pvarg; // [rsp+50h] [rbp-13D8h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-13D0h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp-13C8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-13C0h] BYREF
  __int64 v33; // [rsp+80h] [rbp-13A8h] BYREF
  __int64 v34; // [rsp+88h] [rbp-13A0h]
  __int64 v35; // [rsp+90h] [rbp-1398h]
  int v36; // [rsp+98h] [rbp-1390h]
  _QWORD v37[7]; // [rsp+A0h] [rbp-1388h] BYREF
  _BYTE v38[232]; // [rsp+D8h] [rbp-1350h] BYREF
  __int64 v39; // [rsp+1C0h] [rbp-1268h] BYREF
  _BYTE v40[80]; // [rsp+1C8h] [rbp-1260h] BYREF
  __int64 v41; // [rsp+218h] [rbp-1210h]
  __int16 v42; // [rsp+220h] [rbp-1208h]
  __int64 v43; // [rsp+228h] [rbp-1200h]
  __int128 v44; // [rsp+230h] [rbp-11F8h]
  __int64 v45; // [rsp+240h] [rbp-11E8h]
  int v46; // [rsp+248h] [rbp-11E0h]
  char v47; // [rsp+24Ch] [rbp-11DCh]
  __int64 v48; // [rsp+260h] [rbp-11C8h] BYREF
  _BYTE v49[80]; // [rsp+268h] [rbp-11C0h] BYREF
  __int64 v50; // [rsp+2B8h] [rbp-1170h]
  __int16 v51; // [rsp+2C0h] [rbp-1168h]
  __int64 v52; // [rsp+2C8h] [rbp-1160h]
  __int128 v53; // [rsp+2D0h] [rbp-1158h]
  __int64 v54; // [rsp+2E0h] [rbp-1148h]
  int v55; // [rsp+2E8h] [rbp-1140h]
  char v56; // [rsp+2ECh] [rbp-113Ch]
  _BYTE v57[240]; // [rsp+2F0h] [rbp-1138h] BYREF
  _BYTE v58[4096]; // [rsp+3E0h] [rbp-1048h] BYREF

  v37[3] = -2;
  v36 = 0;
  v27 = 0;
  CycleTime = 0;
  v30 = 0;
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, &CycleTime);
  GetTickCount();
  DownlevelThunksInitEx(v4, v3);
  v26 = -2147221008;
  v25 = -2147221008;
  if ( IsWindowsVersionOrGreater(6u, 2u, v5) )
  {
    v7 = Common::AutoWinRTInitialize::Initialize(&v25);
    if ( v7 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetCachedAppInventory", 552, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
      return (unsigned int)v7;
    }
  }
  else
  {
    v9 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v26, v6);
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetCachedAppInventory", 556, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
      return (unsigned int)v9;
    }
  }
  memset_0(v49, 0, 0x4Eu);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v50 = 0;
  v48 = 0;
  p_pvarg = (VARIANTARG *)operator new(0x3F0u);
  v10 = Application::Application((Application *)p_pvarg);
  v11 = (const unsigned __int16 *)&Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v11 = (const unsigned __int16 *)Application::ApplicationCacheProviderName;
  v12 = TelCacheProvider::Initialize(&v48, v11, (__int64)v10, 0, 2, 5u, 0x1F4u);
  if ( v12 >= 0 )
  {
    memset_0(v40, 0, 0x4Eu);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v41 = 0;
    v39 = 0;
    p_pvarg = (VARIANTARG *)operator new(0x330u);
    v13 = File::File((File *)p_pvarg);
    v14 = (const unsigned __int16 *)&File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180183038 > 7 )
      v14 = (const unsigned __int16 *)File::FileCacheProviderName;
    v15 = TelCacheProvider::Initialize(&v39, v14, ((unsigned __int64)v13 + 8) & -(__int64)(v13 != 0), 0, 2, 5u, 0x1F4u);
    if ( v15 >= 0 )
    {
      ConfigSettings::ConfigSettings(v58, 5, &v48, &v39);
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(&v33);
      ApplicationsFromCache = (__int64 *)Application::GetApplicationsFromCache(&pvarg, v58);
      if ( &v33 == ApplicationsFromCache )
      {
        v18 = v34;
        v17 = v33;
      }
      else
      {
        std::vector<Application>::_Tidy(&v33);
        v17 = *ApplicationsFromCache;
        v33 = *ApplicationsFromCache;
        v18 = ApplicationsFromCache[1];
        v34 = v18;
        v35 = ApplicationsFromCache[2];
        *ApplicationsFromCache = 0;
        ApplicationsFromCache[1] = 0;
        ApplicationsFromCache[2] = 0;
      }
      std::vector<Application>::_Tidy(&pvarg);
      ConfigSettings::ConfigSettings(v57, 4, &v48, &v39);
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(v37);
      FilesFromCache = File::GetFilesFromCache(&pvarg, v57);
      std::vector<File>::operator=(v37, FilesFromCache);
      std::vector<File>::_Tidy(&pvarg);
      pvarg.vt = 11;
      if ( a1 )
        pvarg.iVal = -1;
      else
        pvarg.iVal = 0;
      v36 = 1;
      v20 = _bstr_t::_bstr_t((_bstr_t *)&p_pvarg, (const struct _variant_t *)&pvarg);
      if ( !_bstr_t::length(v20)
        || !(0xEFBEFBEFBEFBEFBFuLL * ((v18 - v17) >> 4))
        || (v21 = 1, !(0xFAFAFAFAFAFAFAFBuLL * ((__int64)(v37[1] - v37[0]) >> 4))) )
      {
        v21 = 0;
      }
      _bstr_t::~_bstr_t((_bstr_t *)&p_pvarg);
      VariantClear(&pvarg);
      if ( v21 )
      {
        p_pvarg = &pvarg;
        v22 = std::vector<File>::vector<File>(&pvarg, v37);
        v23 = std::vector<Application>::vector<Application>(v38, &v33);
        XmlBuilder::XmlBuilder((unsigned int)&v28, (unsigned int)v57, v23, v22, (__int64)a1);
        GetTickCount();
        AslLogCallPrintf(
          3,
          (unsigned int)"GetCachedAppInventory",
          591,
          (unsigned int)"GetCachedAppInventory elapsed time: %d");
        std::vector<File>::_Tidy(v37);
        ConfigSettings::~ConfigSettings((ConfigSettings *)v57);
        std::vector<Application>::_Tidy(&v33);
        ConfigSettings::~ConfigSettings((ConfigSettings *)v58);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v39);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v48);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
        Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
        v24 = GetCurrentThread();
        QueryThreadCycleTime(v24, &v30);
        AslTelemetryTrackMetric(
          qword_1801822A0,
          "AppInv_Simple_Cpu_mCycles",
          (unsigned int)((v30 - CycleTime) / 0xF4240));
        return v27;
      }
      else
      {
        AslLogCallPrintf(1, (unsigned int)"GetCachedAppInventory", 588, (unsigned int)"[%#x]");
        std::vector<File>::_Tidy(v37);
        ConfigSettings::~ConfigSettings((ConfigSettings *)v57);
        std::vector<Application>::_Tidy(&v33);
        ConfigSettings::~ConfigSettings((ConfigSettings *)v58);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v39);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v48);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
        Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
        return 2147500037LL;
      }
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"GetCachedAppInventory", 565, (unsigned int)"[%#x]");
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v39);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v48);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
      return (unsigned int)v15;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"GetCachedAppInventory", 561, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v48);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v25);
    Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v26);
    return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x180057730  push    rbx
0x180057732  push    rsi
0x180057733  push    rdi
0x180057734  push    r12
0x180057736  push    r14
0x180057738  push    r15
0x18005773a  mov     eax, 13F8h
0x18005773f  call    _alloca_probe
0x180057744  sub     rsp, rax
0x180057747  mov     [rsp+1428h+var_1370], 0FFFFFFFFFFFFFFFEh
0x180057753  mov     rax, cs:__security_cookie
0x18005775a  xor     rax, rsp
0x18005775d  mov     [rsp+1428h+var_48], rax
0x180057765  mov     r14, rcx
0x180057768  xor     r12d, r12d
0x18005776b  mov     [rsp+1428h+var_1390], r12d
0x180057773  mov     [rsp+1428h+var_13E0], r12d
0x180057778  mov     [rsp+1428h+CycleTime], r12
0x18005777d  mov     [rsp+1428h+var_13D0], r12
0x180057782  call    cs:__imp_GetCurrentThread
0x180057788  mov     rcx, rax; ThreadHandle
0x18005778b  lea     rdx, [rsp+1428h+CycleTime]; CycleTime
0x180057790  call    cs:__imp_QueryThreadCycleTime
0x180057796  nop
0x180057797  call    cs:__imp_GetTickCount
0x18005779d  mov     r15d, eax
0x1800577a0  call    ?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z; DownlevelThunksInitEx(THUNKS *,ulong)
0x1800577a5  mov     eax, 800401F0h
0x1800577aa  mov     [rsp+1428h+var_13E4], eax
0x1800577ae  mov     [rsp+1428h+var_13E8], eax
0x1800577b2  lea     esi, [r12+2]
0x1800577b7  mov     edx, esi; unsigned __int16
0x1800577b9  lea     ecx, [rsi+4]; unsigned __int16
0x1800577bc  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800577c1  test    al, al
0x1800577c3  jz      short loc_180057816
0x1800577c5  lea     rcx, [rsp+1428h+var_13E8]
0x1800577ca  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x1800577cf  mov     ebx, eax
0x1800577d1  test    eax, eax
0x1800577d3  jns     loc_180057865
0x1800577d9  mov     dword ptr [rsp+1428h+var_1408], eax
0x1800577dd  lea     r9, asc_18013E640; "[%#x]"
0x1800577e4  mov     r8d, 228h
0x1800577ea  lea     rdx, aGetcachedappin_1; "GetCachedAppInventory"
0x1800577f1  lea     ecx, [rsi-1]
0x1800577f4  call    AslLogCallPrintf
0x1800577f9  nop
0x1800577fa  lea     rcx, [rsp+1428h+var_13E8]; this
0x1800577ff  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180057804  nop
0x180057805  lea     rcx, [rsp+1428h+var_13E4]; this
0x18005780a  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x18005780f  mov     eax, ebx
0x180057811  jmp     loc_180057DFF
0x180057816  lea     rcx, [rsp+1428h+var_13E4]; this
0x18005781b  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180057820  mov     ebx, eax
0x180057822  test    eax, eax
0x180057824  jns     short loc_180057865
0x180057826  mov     dword ptr [rsp+1428h+var_1408], eax
0x18005782a  lea     r9, asc_18013E640; "[%#x]"
0x180057831  mov     r8d, 22Ch
0x180057837  lea     rdx, aGetcachedappin_1; "GetCachedAppInventory"
0x18005783e  mov     ecx, 1
0x180057843  call    AslLogCallPrintf
0x180057848  nop
0x180057849  lea     rcx, [rsp+1428h+var_13E8]; this
0x18005784e  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180057853  nop
0x180057854  lea     rcx, [rsp+1428h+var_13E4]; this
0x180057859  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x18005785e  mov     eax, ebx
0x180057860  jmp     loc_180057DFF
0x180057865  mov     edi, 4Eh ; 'N'
0x18005786a  mov     r8d, edi; Size
0x18005786d  xor     edx, edx; Val
0x18005786f  lea     rcx, [rsp+1428h+var_11C0]; void *
0x180057877  call    memset_0
0x18005787c  mov     [rsp+1428h+var_1168], r12w
0x180057885  mov     [rsp+1428h+var_1160], r12
0x18005788d  xorps   xmm0, xmm0
0x180057890  movdqa  [rsp+1428h+var_1158], xmm0
0x180057899  mov     [rsp+1428h+var_1148], r12
0x1800578a1  mov     [rsp+1428h+var_1140], r12d
0x1800578a9  mov     [rsp+1428h+var_113C], r12b
0x1800578b1  mov     [rsp+1428h+var_1170], r12
0x1800578b9  mov     [rsp+1428h+var_11C8], r12
0x1800578c1  mov     ecx, 3F0h; Size
0x1800578c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800578cb  mov     [rsp+1428h+var_13D8], rax
0x1800578d0  mov     rcx, rax; this
0x1800578d3  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x1800578d8  nop
0x1800578d9  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x1800578e0  cmp     cs:qword_180182A38, 7
0x1800578e8  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x1800578f0  mov     [rsp+1428h+var_13F8], 1F4h
0x1800578f8  mov     [rsp+1428h+var_1400], 5
0x180057900  mov     dword ptr [rsp+1428h+var_1408], esi
0x180057904  xor     r9d, r9d
0x180057907  mov     r8, rax
0x18005790a  lea     rcx, [rsp+1428h+var_11C8]
0x180057912  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180057917  mov     ebx, eax
0x180057919  test    eax, eax
0x18005791b  jns     short loc_180057968
0x18005791d  mov     dword ptr [rsp+1428h+var_1408], eax
0x180057921  lea     r9, asc_18013E640; "[%#x]"
0x180057928  mov     r8d, 231h
0x18005792e  lea     rdx, aGetcachedappin_1; "GetCachedAppInventory"
0x180057935  lea     ecx, [rdi-4Dh]
0x180057938  call    AslLogCallPrintf
0x18005793d  nop
0x18005793e  lea     rcx, [rsp+1428h+var_11C8]; this
0x180057946  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18005794b  nop
0x18005794c  lea     rcx, [rsp+1428h+var_13E8]; this
0x180057951  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180057956  nop
0x180057957  lea     rcx, [rsp+1428h+var_13E4]; this
0x18005795c  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180057961  mov     eax, ebx
0x180057963  jmp     loc_180057DFF
0x180057968  mov     r8, rdi; Size
0x18005796b  xor     edx, edx; Val
0x18005796d  lea     rcx, [rsp+1428h+var_1260]; void *
0x180057975  call    memset_0
0x18005797a  mov     [rsp+1428h+var_1208], r12w
0x180057983  mov     [rsp+1428h+var_1200], r12
0x18005798b  xorps   xmm0, xmm0
0x18005798e  movdqa  [rsp+1428h+var_11F8], xmm0
0x180057997  mov     [rsp+1428h+var_11E8], r12
0x18005799f  mov     [rsp+1428h+var_11E0], r12d
0x1800579a7  mov     [rsp+1428h+var_11DC], r12b
0x1800579af  mov     [rsp+1428h+var_1210], r12
0x1800579b7  mov     [rsp+1428h+var_1268], r12
0x1800579bf  mov     ecx, 330h; Size
0x1800579c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800579c9  mov     [rsp+1428h+var_13D8], rax
0x1800579ce  mov     rcx, rax; this
0x1800579d1  call    ??0File@@QEAA@XZ; File::File(void)
0x1800579d6  nop
0x1800579d7  lea     rcx, [rax+8]
0x1800579db  neg     rax
0x1800579de  sbb     r8, r8
0x1800579e1  and     r8, rcx
0x1800579e4  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x1800579eb  cmp     cs:qword_180183038, 7
0x1800579f3  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x1800579fb  mov     [rsp+1428h+var_13F8], 1F4h
0x180057a03  mov     [rsp+1428h+var_1400], 5
0x180057a0b  mov     dword ptr [rsp+1428h+var_1408], esi
0x180057a0f  xor     r9d, r9d
0x180057a12  lea     rcx, [rsp+1428h+var_1268]
0x180057a1a  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180057a1f  mov     ebx, eax
0x180057a21  test    eax, eax
0x180057a23  jns     short loc_180057A80
0x180057a25  mov     dword ptr [rsp+1428h+var_1408], eax
0x180057a29  lea     r9, asc_18013E640; "[%#x]"
0x180057a30  mov     r8d, 235h
0x180057a36  lea     rdx, aGetcachedappin_1; "GetCachedAppInventory"
0x180057a3d  mov     ecx, 1
0x180057a42  call    AslLogCallPrintf
0x180057a47  nop
0x180057a48  lea     rcx, [rsp+1428h+var_1268]; this
0x180057a50  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180057a55  nop
0x180057a56  lea     rcx, [rsp+1428h+var_11C8]; this
0x180057a5e  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180057a63  nop
0x180057a64  lea     rcx, [rsp+1428h+var_13E8]; this
0x180057a69  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180057a6e  nop
0x180057a6f  lea     rcx, [rsp+1428h+var_13E4]; this
0x180057a74  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180057a79  mov     eax, ebx
0x180057a7b  jmp     loc_180057DFF
0x180057a80  lea     r9, [rsp+1428h+var_1268]
0x180057a88  lea     r8, [rsp+1428h+var_11C8]
0x180057a90  mov     edx, 5
0x180057a95  lea     rcx, [rsp+1428h+var_1048]
0x180057a9d  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool)
0x180057aa2  nop
0x180057aa3  lea     rcx, [rsp+1428h+var_13A8]
0x180057aab  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180057ab0  nop
0x180057ab1  lea     rdx, [rsp+1428h+var_1048]
0x180057ab9  lea     rcx, [rsp+1428h+pvarg]
0x180057abe  call    ?GetApplicationsFromCache@Application@@SA?AV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEBVConfigSettings@@@Z; Application::GetApplicationsFromCache(ConfigSettings const &)
0x180057ac3  mov     rdi, rax
0x180057ac6  lea     rax, [rsp+1428h+var_13A8]
0x180057ace  cmp     rax, rdi
0x180057ad1  jz      short loc_180057B10
0x180057ad3  lea     rcx, [rsp+1428h+var_13A8]
0x180057adb  call    ?_Tidy@?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAAXXZ; std::vector<Application>::_Tidy(void)
0x180057ae0  mov     rsi, [rdi]
0x180057ae3  mov     [rsp+1428h+var_13A8], rsi
0x180057aeb  mov     rbx, [rdi+8]
0x180057aef  mov     [rsp+1428h+var_13A0], rbx
0x180057af7  mov     rax, [rdi+10h]
0x180057afb  mov     [rsp+1428h+var_1398], rax
0x180057b03  mov     [rdi], r12
0x180057b06  mov     [rdi+8], r12
0x180057b0a  mov     [rdi+10h], r12
0x180057b0e  jmp     short loc_180057B20
0x180057b10  mov     rbx, [rsp+1428h+var_13A0]
0x180057b18  mov     rsi, [rsp+1428h+var_13A8]
0x180057b20  lea     rcx, [rsp+1428h+pvarg]
0x180057b25  call    ?_Tidy@?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAAXXZ; std::vector<Application>::_Tidy(void)
0x180057b2a  lea     r9, [rsp+1428h+var_1268]
0x180057b32  lea     r8, [rsp+1428h+var_11C8]
0x180057b3a  mov     edx, 4
0x180057b3f  lea     rcx, [rsp+1428h+var_1138]
0x180057b47  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool)
0x180057b4c  nop
0x180057b4d  lea     rcx, [rsp+1428h+var_1388]
0x180057b55  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180057b5a  nop
0x180057b5b  lea     rdx, [rsp+1428h+var_1138]
0x180057b63  lea     rcx, [rsp+1428h+pvarg]
0x180057b68  call    ?GetFilesFromCache@File@@SA?AV?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEBVConfigSettings@@@Z; File::GetFilesFromCache(ConfigSettings const &)
0x180057b6d  mov     rdx, rax
0x180057b70  lea     rcx, [rsp+1428h+var_1388]
0x180057b78  call    ??4?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<File>::operator=(std::vector<File> &&)
0x180057b7d  lea     rcx, [rsp+1428h+pvarg]
0x180057b82  call    ?_Tidy@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAXXZ; std::vector<File>::_Tidy(void)
0x180057b87  mov     eax, 0Bh
0x180057b8c  mov     word ptr [rsp+1428h+pvarg], ax
0x180057b91  test    r14, r14
0x180057b94  jz      short loc_180057BA0
0x180057b96  or      eax, 0FFFFFFFFh
0x180057b99  mov     word ptr [rsp+1428h+pvarg+8], ax
0x180057b9e  jmp     short loc_180057BA6
0x180057ba0  mov     word ptr [rsp+1428h+pvarg+8], r12w
0x180057ba6  mov     [rsp+1428h+var_1390], 1
0x180057bb1  lea     rdx, [rsp+1428h+pvarg]; struct _variant_t *
0x180057bb6  lea     rcx, [rsp+1428h+var_13D8]; this
0x180057bbb  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180057bc0  mov     rcx, rax; this
0x180057bc3  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180057bc8  test    eax, eax
0x180057bca  jz      short loc_180057C0F
0x180057bcc  sub     rbx, rsi
0x180057bcf  sar     rbx, 4
0x180057bd3  mov     rax, 0EFBEFBEFBEFBEFBFh
0x180057bdd  imul    rbx, rax
0x180057be1  test    rbx, rbx
0x180057be4  jz      short loc_180057C0F
0x180057be6  mov     rax, [rsp+1428h+var_1380]
0x180057bee  sub     rax, [rsp+1428h+var_1388]
0x180057bf6  sar     rax, 4
0x180057bfa  mov     rcx, 0FAFAFAFAFAFAFAFBh
0x180057c04  imul    rax, rcx
0x180057c08  test    rax, rax
0x180057c0b  mov     bl, 1
0x180057c0d  jnz     short loc_180057C12
0x180057c0f  mov     bl, r12b
0x180057c12  lea     rcx, [rsp+1428h+var_13D8]; this
0x180057c17  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180057c1c  nop
0x180057c1d  lea     rcx, [rsp+1428h+pvarg]; pvarg
0x180057c22  call    cs:__imp_VariantClear
0x180057c28  test    bl, bl
0x180057c2a  jz      loc_180057D1D
0x180057c30  lea     rax, [rsp+1428h+pvarg]
0x180057c35  mov     [rsp+1428h+var_13D8], rax
0x180057c3a  lea     rdx, [rsp+1428h+var_1388]
0x180057c42  lea     rcx, [rsp+1428h+pvarg]
0x180057c47  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180057c4c  mov     rbx, rax
0x180057c4f  lea     rdx, [rsp+1428h+var_13A8]
0x180057c57  lea     rcx, [rsp+1428h+var_1350]
0x180057c5f  call    ??0?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Application>::vector<Application>(std::vector<Application> const &)
0x180057c64  nop
0x180057c65  mov     [rsp+1428h+var_1408], r14
0x180057c6a  mov     r9, rbx
0x180057c6d  mov     r8, rax
0x180057c70  lea     rdx, [rsp+1428h+var_1138]
0x180057c78  lea     rcx, [rsp+1428h+var_13DC]
0x180057c7d  call    ??0XmlBuilder@@QEAA@AEBVConfigSettings@@V?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@V?$vector@VFile@@V?$allocator@VFile@@@std@@@3@PEAPEAG@Z; XmlBuilder::XmlBuilder(ConfigSettings const &,std::vector<Application>,std::vector<File>,ushort * *)
0x180057c82  call    cs:__imp_GetTickCount
0x180057c88  sub     eax, r15d
0x180057c8b  mov     dword ptr [rsp+1428h+var_1408], eax
0x180057c8f  lea     r9, aGetcachedappin_0; "GetCachedAppInventory elapsed time: %d"
0x180057c96  mov     r8d, 24Fh
0x180057c9c  lea     rdx, aGetcachedappin_1; "GetCachedAppInventory"
0x180057ca3  mov     ecx, 3
0x180057ca8  call    AslLogCallPrintf
0x180057cad  nop
0x180057cae  lea     rcx, [rsp+1428h+var_1388]
0x180057cb6  call    ?_Tidy@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAXXZ; std::vector<File>::_Tidy(void)
0x180057cbb  nop
0x180057cbc  lea     rcx, [rsp+1428h+var_1138]; this
0x180057cc4  call    ??1ConfigSettings@@UEAA@XZ; ConfigSettings::~ConfigSettings(void)
0x180057cc9  nop
0x180057cca  lea     rcx, [rsp+1428h+var_13A8]
0x180057cd2  call    ?_Tidy@?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAAXXZ; std::vector<Application>::_Tidy(void)
0x180057cd7  nop
  ... truncated ...
```
