# PersistenceManager::OpenRegistry(WPN_INSTANCE_PRIVILEGE)

- ea: `0x1800aaef4`
- end: `0x1800ab3fa`
- name: `?OpenRegistry@PersistenceManager@@AEAAJW4WPN_INSTANCE_PRIVILEGE@@@Z`
- size: `1286`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e5070`
- `0x1800e67f0`

## callees

- `0x180004e38`
- `0x180011618`
- `0x180017a20`
- `0x18002ee38`
- `0x1800a0b2c`
- `0x1800a61dc`
- `0x1800aaef4`
- `0x1800af0a4`
- `0x1800e4154`
- `0x1800e4774`
- `0x1800e4fd4`
- `0x1800e6b9c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab056`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab056`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab075`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab075`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab007`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab180`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab007`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab180`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800ab06b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800ab06b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ab22e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ab327`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ab22e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ab327`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ab3d4`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ab3d4`

## string_xrefs

- `0x1800ab275`: `PersistenceManager::OpenRegistry`
- `0x1800ab2be`: `PersistenceManager::OpenRegistry`
- `0x1800ab34a`: `PersistenceManager::OpenRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistenceManager::OpenRegistry(__int64 a1, int a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rcx
  signed int v7; // ebx
  const WCHAR *v8; // rax
  LSTATUS ValueW; // eax
  const WCHAR *v10; // rax
  unsigned int v11; // ecx
  unsigned __int64 v12; // r15
  unsigned int v13; // ebx
  unsigned __int16 v14; // ax
  PersistenceManager *v15; // rcx
  unsigned __int16 InitialAppCount; // r8
  int HeaderBuffer; // eax
  unsigned int v18; // ecx
  int v19; // r9d
  const WCHAR *v20; // rax
  LSTATUS v21; // eax
  unsigned int v22; // ecx
  int v23; // r9d
  int v24; // eax
  DWORD v25; // ebx
  const WCHAR *v26; // rax
  LSTATUS v27; // eax
  bool v28; // sf
  const WCHAR *v29; // rax
  LSTATUS v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  _WORD *v35; // r8
  int pdwType; // [rsp+20h] [rbp-50h]
  int pdwTypea; // [rsp+20h] [rbp-50h]
  __int64 v39; // [rsp+40h] [rbp-30h] BYREF
  PVOID lpAddress; // [rsp+48h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  __int128 v42; // [rsp+58h] [rbp-18h]
  __int64 v43; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char pvData; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  DWORD v47; // [rsp+B8h] [rbp+48h] BYREF

  v47 = 0;
  pvData = 0;
  v4 = 0;
  lpAddress = 0;
  v39 = 0;
  cbData = 1;
  v5 = *(_QWORD *)(a1 + 176);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IPlatformConfigurationProvider>::InternalAddRef(v5 + 336);
  v6 = *(_QWORD *)(v5 + 336);
  v39 = v6;
  if ( !v6 )
  {
    v7 = -2143420155;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      pdwType);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x950,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
      (const char *)0x803E0105LL,
      pdwTypea);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids, 2151547141LL);
    goto LABEL_60;
  }
  v8 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  ValueW = RegGetValueW(HKEY_CURRENT_USER, v8, L"AppDB", 8u, &v47, &pvData, &cbData);
  v7 = ValueW;
  if ( (ValueW == 1630 || !ValueW) && !a2 )
  {
    phkResult = 0;
    v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, v10, 0, 2u, &phkResult) )
    {
      RegDeleteValueW(phkResult, L"AppDB");
      RegCloseKey(phkResult);
    }
    v7 = 2;
  }
  WORD2(v42) = 3;
  v43 = 0;
  LODWORD(v42) = 1464880712;
  *((_QWORD *)&v42 + 1) = 1;
  WORD3(v42) = PersistenceManager::GetInitialAppCount((PersistenceManager *)a1);
  if ( v7 == 2 )
    goto LABEL_42;
  if ( v7 != 234 )
  {
    v28 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v28 = v7 < 0;
    }
    if ( v28 )
    {
      WpnDebugInitTrace(
        v11,
        L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        L"PersistenceManager::OpenRegistry",
        2500,
        v7);
      goto LABEL_60;
    }
    goto LABEL_52;
  }
  if ( cbData < 0x18 )
  {
LABEL_42:
    WORD3(v42) = PersistenceManager::GetInitialAppCount((PersistenceManager *)a1);
    WORD2(v43) = 0;
    HeaderBuffer = PersistenceManager::CreateHeaderBuffer(0, 0, WORD3(v42), (struct WPN_APPDB_REG_HEADER **)&lpAddress);
    v7 = HeaderBuffer;
    if ( HeaderBuffer < 0 )
    {
      v19 = 2434;
      goto LABEL_44;
    }
    v4 = lpAddress;
    *(_OWORD *)lpAddress = v42;
    *((_QWORD *)v4 + 2) = v43;
    if ( !a2 )
    {
      v29 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
      v30 = RegSetKeyValueW(HKEY_CURRENT_USER, v29, L"AppDB", 3u, v4, 0x18u);
      v7 = v30;
      if ( v30 > 0 )
        v7 = (unsigned __int16)v30 | 0x80070000;
      if ( v7 < 0 )
      {
        v23 = 2452;
        goto LABEL_50;
      }
    }
  }
  else
  {
    if ( cbData < 0x19 )
    {
      InitialAppCount = PersistenceManager::GetInitialAppCount((PersistenceManager *)a1);
      LOWORD(v12) = 0;
    }
    else
    {
      v12 = ((unsigned __int64)cbData - 24) / 0x488;
      v13 = (unsigned int)v12 / PersistenceManager::GetInitialAppCount((PersistenceManager *)a1) + 1;
      v14 = PersistenceManager::GetInitialAppCount((PersistenceManager *)a1);
      v15 = (PersistenceManager *)(unsigned __int16)v13;
      InitialAppCount = v13 * v14;
    }
    HeaderBuffer = PersistenceManager::CreateHeaderBuffer(
                     v15,
                     cbData,
                     InitialAppCount,
                     (struct WPN_APPDB_REG_HEADER **)&lpAddress);
    v7 = HeaderBuffer;
    if ( HeaderBuffer < 0 )
    {
      v19 = 2468;
LABEL_44:
      WpnDebugInitTrace(
        v18,
        L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        L"PersistenceManager::OpenRegistry",
        v19,
        HeaderBuffer);
      v4 = lpAddress;
      goto LABEL_58;
    }
    v20 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
    v4 = lpAddress;
    v21 = RegGetValueW(HKEY_CURRENT_USER, v20, L"AppDB", 8u, &v47, lpAddress, &cbData);
    v7 = v21;
    if ( v21 > 0 )
      v7 = (unsigned __int16)v21 | 0x80070000;
    if ( v7 < 0 )
    {
      v23 = 2479;
LABEL_50:
      WpnDebugInitTrace(
        v22,
        L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        L"PersistenceManager::OpenRegistry",
        v23,
        v7);
LABEL_58:
      if ( v4 )
        VirtualFree(v4, 0, 0x8000u);
      goto LABEL_60;
    }
    v24 = 0;
    if ( *v4 != 1464880712 )
    {
      v24 = 1;
      *v4 = 1464880712;
    }
    if ( *((_BYTE *)v4 + 4) != 3 )
    {
      v24 = 1;
      *((_BYTE *)v4 + 4) = 3;
    }
    if ( (unsigned __int16)v12 >= *((_WORD *)v4 + 10) )
    {
      LOWORD(v12) = *((_WORD *)v4 + 10);
    }
    else
    {
      v24 = 1;
      *((_WORD *)v4 + 10) = v12;
    }
    if ( *((_WORD *)v4 + 8) <= (unsigned __int16)v12 )
    {
      if ( !v24 )
        goto LABEL_52;
    }
    else
    {
      *((_WORD *)v4 + 8) = v12;
    }
    if ( !a2 )
    {
      v25 = cbData;
      v26 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
      v27 = RegSetKeyValueW(HKEY_CURRENT_USER, v26, L"AppDB", 3u, v4, v25);
      v7 = v27;
      if ( v27 > 0 )
        v7 = (unsigned __int16)v27 | 0x80070000;
      if ( v7 < 0 )
      {
        v23 = 2492;
        goto LABEL_50;
      }
    }
  }
LABEL_52:
  v31 = BinaryStatusSet::Init((unsigned __int16 **)(a1 + 96), *((unsigned __int16 *)v4 + 3));
  v7 = v31;
  if ( v31 < 0 )
  {
    WpnDebugInitTrace(
      v33,
      L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
      L"PersistenceManager::OpenRegistry",
      2508,
      v31);
    goto LABEL_58;
  }
  if ( *(_QWORD *)(a1 + 56) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v33, v32, v34);
  v35 = v4;
  *(_QWORD *)(a1 + 56) = v4;
  *(_QWORD *)(a1 + 48) = v4 + 6;
  v4 = 0;
  if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x10) != 0 )
  {
    McTemplateU0hhh_EventWriteTransfer(
      v33,
      (unsigned int)WPNPLAT_LOAD_FILE,
      (unsigned __int16)v35[8],
      (unsigned __int16)v35[10],
      v35[3]);
    goto LABEL_58;
  }
LABEL_60:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800aaef4  mov     [rsp-28h+arg_8], rbx
0x1800aaef9  push    rbp
0x1800aaefa  push    rsi
0x1800aaefb  push    rdi
0x1800aaefc  push    r12
0x1800aaefe  push    r15
0x1800aaf00  mov     rbp, rsp
0x1800aaf03  sub     rsp, 70h
0x1800aaf07  mov     r12d, edx
0x1800aaf0a  mov     rsi, rcx
0x1800aaf0d  mov     [rbp+arg_18], 0
0x1800aaf14  mov     [rbp+arg_0], 0
0x1800aaf18  xor     edi, edi
0x1800aaf1a  mov     [rbp+lpAddress], rdi
0x1800aaf1e  mov     [rbp+var_30], rdi
0x1800aaf22  mov     [rbp+cbData], 1
0x1800aaf29  mov     rbx, [rcx+0B0h]
0x1800aaf30  lea     rcx, [rbp+var_30]
0x1800aaf34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aaf39  lea     rcx, [rbx+150h]
0x1800aaf40  call    ?InternalAddRef@?$ComPtr@UIPlatformConfigurationProvider@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IPlatformConfigurationProvider>::InternalAddRef(void)
0x1800aaf45  mov     rcx, [rbx+150h]
0x1800aaf4c  mov     [rbp+var_30], rcx
0x1800aaf50  test    rcx, rcx
0x1800aaf53  jnz     short loc_1800AAFC9
0x1800aaf55  mov     rcx, [rbp+28h]; this
0x1800aaf59  mov     ebx, 803E0105h
0x1800aaf5e  mov     r9d, ebx; char *
0x1800aaf61  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aaf68  mov     edx, 400h; void *
0x1800aaf6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aaf72  mov     rcx, [rbp+28h]; this
0x1800aaf76  mov     r9d, ebx; char *
0x1800aaf79  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aaf80  mov     edx, 950h; void *
0x1800aaf85  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aaf8a  lea     rax, WPP_GLOBAL_Control
0x1800aaf91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf98  cmp     rcx, rax
0x1800aaf9b  jz      loc_1800AB3DB
0x1800aafa1  test    byte ptr [rcx+1Ch], 80h
0x1800aafa5  jz      loc_1800AB3DB
0x1800aafab  lea     edx, [rdi+4Ch]
0x1800aafae  mov     r9d, 803E0105h
0x1800aafb4  lea     r8, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids
0x1800aafbb  mov     rcx, [rcx+10h]
0x1800aafbf  call    WPP_SF_d
0x1800aafc4  jmp     loc_1800AB3DB
0x1800aafc9  mov     rax, [rcx]
0x1800aafcc  mov     rax, [rax+18h]
0x1800aafd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aafd5  mov     rdx, rax; lpSubKey
0x1800aafd8  lea     rax, [rbp+cbData]
0x1800aafdc  mov     [rsp+70h+pcbData], rax; pcbData
0x1800aafe1  lea     rax, [rbp+arg_0]
0x1800aafe5  mov     [rsp+70h+pvData], rax; pvData
0x1800aafea  lea     rax, [rbp+arg_18]
0x1800aafee  mov     [rsp+70h+pdwType], rax; pdwType
0x1800aaff3  mov     r9d, 8; dwFlags
0x1800aaff9  lea     r8, aAppdb; "AppDB"
0x1800ab000  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800ab007  call    cs:__imp_RegGetValueW
0x1800ab00d  mov     ebx, eax
0x1800ab00f  mov     r15d, 2
0x1800ab015  cmp     eax, 65Eh
0x1800ab01a  jz      short loc_1800AB020
0x1800ab01c  test    eax, eax
0x1800ab01e  jnz     short loc_1800AB07E
0x1800ab020  test    r12d, r12d
0x1800ab023  jnz     short loc_1800AB07E
0x1800ab025  mov     [rbp+phkResult], 0
0x1800ab02d  mov     rcx, [rbp+var_30]
0x1800ab031  mov     rax, [rcx]
0x1800ab034  mov     rax, [rax+18h]
0x1800ab038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab03d  mov     rdx, rax; lpSubKey
0x1800ab040  lea     rax, [rbp+phkResult]
0x1800ab044  mov     [rsp+70h+pdwType], rax; phkResult
0x1800ab049  mov     r9d, r15d; samDesired
0x1800ab04c  xor     r8d, r8d; ulOptions
0x1800ab04f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ab056  call    cs:__imp_RegOpenKeyExW
0x1800ab05c  test    eax, eax
0x1800ab05e  jnz     short loc_1800AB07B
0x1800ab060  lea     rdx, aAppdb; "AppDB"
0x1800ab067  mov     rcx, [rbp+phkResult]; hKey
0x1800ab06b  call    cs:__imp_RegDeleteValueW
0x1800ab071  mov     rcx, [rbp+phkResult]; hKey
0x1800ab075  call    cs:__imp_RegCloseKey
0x1800ab07b  mov     ebx, r15d
0x1800ab07e  mov     word ptr [rbp+var_18+4], 3
0x1800ab084  mov     [rbp+var_8], 0
0x1800ab08c  mov     dword ptr [rbp+var_18], 57504E48h
0x1800ab093  mov     qword ptr [rbp+var_18+8], 1
0x1800ab09b  mov     rcx, rsi; this
0x1800ab09e  call    ?GetInitialAppCount@PersistenceManager@@AEAAGXZ; PersistenceManager::GetInitialAppCount(void)
0x1800ab0a3  mov     word ptr [rbp+var_18+6], ax
0x1800ab0a7  cmp     ebx, r15d
0x1800ab0aa  jz      loc_1800AB28D
0x1800ab0b0  cmp     ebx, 0EAh
0x1800ab0b6  jnz     loc_1800AB256
0x1800ab0bc  mov     eax, [rbp+cbData]
0x1800ab0bf  cmp     eax, 18h
0x1800ab0c2  jb      loc_1800AB28D
0x1800ab0c8  cmp     eax, 19h
0x1800ab0cb  jb      short loc_1800AB10F
0x1800ab0cd  lea     rcx, [rax-18h]
0x1800ab0d1  mov     rax, 70FE3C070FE3C071h
0x1800ab0db  mul     rcx
0x1800ab0de  mov     r15, rdx
0x1800ab0e1  shr     r15, 9
0x1800ab0e5  mov     rcx, rsi; this
0x1800ab0e8  call    ?GetInitialAppCount@PersistenceManager@@AEAAGXZ; PersistenceManager::GetInitialAppCount(void)
0x1800ab0ed  movzx   ecx, ax
0x1800ab0f0  mov     eax, r15d
0x1800ab0f3  xor     edx, edx
0x1800ab0f5  div     ecx
0x1800ab0f7  lea     ebx, [rax+1]
0x1800ab0fa  mov     rcx, rsi; this
0x1800ab0fd  call    ?GetInitialAppCount@PersistenceManager@@AEAAGXZ; PersistenceManager::GetInitialAppCount(void)
0x1800ab102  movzx   ecx, bx
0x1800ab105  movzx   r8d, ax
0x1800ab109  imul    r8d, ecx
0x1800ab10d  jmp     short loc_1800AB121
0x1800ab10f  mov     rcx, rsi; this
0x1800ab112  call    ?GetInitialAppCount@PersistenceManager@@AEAAGXZ; PersistenceManager::GetInitialAppCount(void)
0x1800ab117  movzx   r8d, ax; unsigned __int16
0x1800ab11b  xor     eax, eax
0x1800ab11d  movzx   r15d, ax
0x1800ab121  lea     r9, [rbp+lpAddress]; struct WPN_APPDB_REG_HEADER **
0x1800ab125  mov     edx, [rbp+cbData]; unsigned int
0x1800ab128  call    ?CreateHeaderBuffer@PersistenceManager@@AEAAJKGPEAPEAUWPN_APPDB_REG_HEADER@@@Z; PersistenceManager::CreateHeaderBuffer(ulong,ushort,WPN_APPDB_REG_HEADER * *)
0x1800ab12d  mov     ebx, eax
0x1800ab12f  test    eax, eax
0x1800ab131  jns     short loc_1800AB13E
0x1800ab133  mov     r9d, 9A4h
0x1800ab139  jmp     loc_1800AB2BA
0x1800ab13e  mov     rcx, [rbp+var_30]
0x1800ab142  mov     rax, [rcx]
0x1800ab145  mov     rax, [rax+18h]
0x1800ab149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab14e  lea     rcx, [rbp+cbData]
0x1800ab152  mov     [rsp+70h+pcbData], rcx; pcbData
0x1800ab157  mov     rdi, [rbp+lpAddress]
0x1800ab15b  mov     [rsp+70h+pvData], rdi; pvData
0x1800ab160  lea     rcx, [rbp+arg_18]
0x1800ab164  mov     [rsp+70h+pdwType], rcx; pdwType
0x1800ab169  mov     r9d, 8; dwFlags
0x1800ab16f  lea     r8, aAppdb; "AppDB"
0x1800ab176  mov     rdx, rax; lpSubKey
0x1800ab179  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800ab180  call    cs:__imp_RegGetValueW
0x1800ab186  mov     ebx, eax
0x1800ab188  test    eax, eax
0x1800ab18a  jle     short loc_1800AB195
0x1800ab18c  movzx   ebx, ax
0x1800ab18f  or      ebx, 80070000h
0x1800ab195  test    ebx, ebx
0x1800ab197  jns     short loc_1800AB1A4
0x1800ab199  mov     r9d, 9AFh
0x1800ab19f  jmp     loc_1800AB346
0x1800ab1a4  xor     eax, eax
0x1800ab1a6  mov     ecx, 57504E48h
0x1800ab1ab  cmp     [rdi], ecx
0x1800ab1ad  jz      short loc_1800AB1B6
0x1800ab1af  mov     eax, 1
0x1800ab1b4  mov     [rdi], ecx
0x1800ab1b6  cmp     byte ptr [rdi+4], 3
0x1800ab1ba  jz      short loc_1800AB1C5
0x1800ab1bc  mov     eax, 1
0x1800ab1c1  mov     byte ptr [rdi+4], 3
0x1800ab1c5  cmp     r15w, [rdi+14h]
0x1800ab1ca  jnb     short loc_1800AB1D8
0x1800ab1cc  mov     eax, 1
0x1800ab1d1  mov     [rdi+14h], r15w
0x1800ab1d6  jmp     short loc_1800AB1DD
0x1800ab1d8  movzx   r15d, word ptr [rdi+14h]
0x1800ab1dd  cmp     [rdi+10h], r15w
0x1800ab1e2  jbe     short loc_1800AB1EB
0x1800ab1e4  mov     [rdi+10h], r15w
0x1800ab1e9  jmp     short loc_1800AB1F3
0x1800ab1eb  test    eax, eax
0x1800ab1ed  jz      loc_1800AB35F
0x1800ab1f3  test    r12d, r12d
0x1800ab1f6  jnz     loc_1800AB35F
0x1800ab1fc  mov     ebx, [rbp+cbData]
0x1800ab1ff  mov     rcx, [rbp+var_30]
0x1800ab203  mov     rax, [rcx]
0x1800ab206  mov     rax, [rax+18h]
0x1800ab20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab20f  mov     dword ptr [rsp+70h+pvData], ebx; cbData
0x1800ab213  mov     [rsp+70h+pdwType], rdi; lpData
0x1800ab218  lea     r9d, [r12+3]; dwType
0x1800ab21d  lea     r8, aAppdb; "AppDB"
0x1800ab224  mov     rdx, rax; lpSubKey
0x1800ab227  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ab22e  call    cs:__imp_RegSetKeyValueW
0x1800ab234  mov     ebx, eax
0x1800ab236  test    eax, eax
0x1800ab238  jle     short loc_1800AB243
0x1800ab23a  movzx   ebx, ax
0x1800ab23d  or      ebx, 80070000h
0x1800ab243  test    ebx, ebx
0x1800ab245  jns     loc_1800AB35F
0x1800ab24b  mov     r9d, 9BCh
0x1800ab251  jmp     loc_1800AB346
0x1800ab256  test    ebx, ebx
0x1800ab258  jle     short loc_1800AB265
0x1800ab25a  movzx   ebx, bx
0x1800ab25d  or      ebx, 80070000h
0x1800ab263  test    ebx, ebx
0x1800ab265  jns     loc_1800AB35F
0x1800ab26b  mov     dword ptr [rsp+70h+pdwType], ebx; int
0x1800ab26f  mov     r9d, 9C4h; int
0x1800ab275  lea     r8, aPersistenceman_1; "PersistenceManager::OpenRegistry"
0x1800ab27c  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ab283  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800ab288  jmp     loc_1800AB3DB
0x1800ab28d  mov     rcx, rsi; this
0x1800ab290  call    ?GetInitialAppCount@PersistenceManager@@AEAAGXZ; PersistenceManager::GetInitialAppCount(void)
0x1800ab295  mov     word ptr [rbp+var_18+6], ax
0x1800ab299  xor     ecx, ecx; this
0x1800ab29b  mov     word ptr [rbp+var_8+4], cx
0x1800ab29f  lea     r9, [rbp+lpAddress]; struct WPN_APPDB_REG_HEADER **
0x1800ab2a3  movzx   r8d, ax; unsigned __int16
0x1800ab2a7  xor     edx, edx; unsigned int
0x1800ab2a9  call    ?CreateHeaderBuffer@PersistenceManager@@AEAAJKGPEAPEAUWPN_APPDB_REG_HEADER@@@Z; PersistenceManager::CreateHeaderBuffer(ulong,ushort,WPN_APPDB_REG_HEADER * *)
0x1800ab2ae  mov     ebx, eax
0x1800ab2b0  test    eax, eax
0x1800ab2b2  jns     short loc_1800AB2DA
0x1800ab2b4  mov     r9d, 982h; int
0x1800ab2ba  mov     dword ptr [rsp+70h+pdwType], eax; int
0x1800ab2be  lea     r8, aPersistenceman_1; "PersistenceManager::OpenRegistry"
0x1800ab2c5  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ab2cc  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800ab2d1  mov     rdi, [rbp+lpAddress]
0x1800ab2d5  jmp     loc_1800AB3C4
0x1800ab2da  mov     rdi, [rbp+lpAddress]
0x1800ab2de  movups  xmm0, [rbp+var_18]
0x1800ab2e2  movups  xmmword ptr [rdi], xmm0
0x1800ab2e5  movsd   xmm1, [rbp+var_8]
0x1800ab2ea  movsd   qword ptr [rdi+10h], xmm1
0x1800ab2ef  test    r12d, r12d
0x1800ab2f2  jnz     short loc_1800AB35F
0x1800ab2f4  mov     rcx, [rbp+var_30]
0x1800ab2f8  mov     rax, [rcx]
0x1800ab2fb  mov     rax, [rax+18h]
0x1800ab2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab304  mov     dword ptr [rsp+70h+pvData], 18h; cbData
0x1800ab30c  mov     [rsp+70h+pdwType], rdi; lpData
0x1800ab311  lea     r9d, [r12+3]; dwType
0x1800ab316  lea     r8, aAppdb; "AppDB"
0x1800ab31d  mov     rdx, rax; lpSubKey
0x1800ab320  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ab327  call    cs:__imp_RegSetKeyValueW
0x1800ab32d  mov     ebx, eax
0x1800ab32f  test    eax, eax
0x1800ab331  jle     short loc_1800AB33C
0x1800ab333  movzx   ebx, ax
0x1800ab336  or      ebx, 80070000h
0x1800ab33c  test    ebx, ebx
0x1800ab33e  jns     short loc_1800AB35F
0x1800ab340  mov     r9d, 994h; int
0x1800ab346  mov     dword ptr [rsp+70h+pdwType], ebx; int
0x1800ab34a  lea     r8, aPersistenceman_1; "PersistenceManager::OpenRegistry"
0x1800ab351  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ab358  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800ab35d  jmp     short loc_1800AB3C4
0x1800ab35f  movzx   edx, word ptr [rdi+6]; unsigned int
0x1800ab363  lea     rcx, [rsi+60h]; this
0x1800ab367  call    ?Init@BinaryStatusSet@@QEAAJI@Z; BinaryStatusSet::Init(uint)
0x1800ab36c  mov     ebx, eax
0x1800ab36e  test    eax, eax
0x1800ab370  jns     short loc_1800AB37E
0x1800ab372  mov     dword ptr [rsp+70h+pdwType], eax
0x1800ab376  mov     r9d, 9CCh
0x1800ab37c  jmp     short loc_1800AB34A
0x1800ab37e  cmp     qword ptr [rsi+38h], 0
0x1800ab383  jz      short loc_1800AB38A
0x1800ab385  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_AppDBRegHeader == NULL")
0x1800ab38a  mov     r8, rdi
0x1800ab38d  mov     [rsi+38h], rdi
0x1800ab391  lea     rax, [rdi+18h]
0x1800ab395  mov     [rsi+30h], rax
0x1800ab399  xor     edi, edi
0x1800ab39b  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 10h
0x1800ab3a2  jz      short loc_1800AB3DB
0x1800ab3a4  movzx   eax, word ptr [r8+6]
0x1800ab3a9  mov     word ptr [rsp+70h+pdwType], ax
0x1800ab3ae  movzx   r9d, word ptr [r8+14h]
0x1800ab3b3  movzx   r8d, word ptr [r8+10h]
0x1800ab3b8  lea     rdx, WPNPLAT_LOAD_FILE
0x1800ab3bf  call    McTemplateU0hhh_EventWriteTransfer
0x1800ab3c4  test    rdi, rdi
0x1800ab3c7  jz      short loc_1800AB3DB
0x1800ab3c9  xor     edx, edx; dwSize
0x1800ab3cb  mov     r8d, 8000h; dwFreeType
0x1800ab3d1  mov     rcx, rdi; lpAddress
0x1800ab3d4  call    cs:__imp_VirtualFree
0x1800ab3da  nop
  ... truncated ...
```
