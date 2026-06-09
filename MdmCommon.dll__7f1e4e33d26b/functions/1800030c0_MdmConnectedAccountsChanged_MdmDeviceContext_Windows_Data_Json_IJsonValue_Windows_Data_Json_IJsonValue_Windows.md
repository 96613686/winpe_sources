# MdmConnectedAccountsChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *)

- ea: `0x1800030c0`
- end: `0x18000349e`
- name: `?MdmConnectedAccountsChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@111PEAH@Z`
- size: `990`
- prototype: `__int64 __fastcall(int, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, _DWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de4`
- `0x1800030c0`
- `0x1800064f0`
- `0x180006548`
- `0x1800066b0`
- `0x180008a6c`
- `0x18000b350`
- `0x180012578`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800032ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000345a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800032ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000345a`

## string_xrefs

- `0x180003194`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003259`: `CHR(MdmSettings::GetConnectedAccountsHash(eDeviceType, wstrConnectedAccountsHashFromRegistry))`
- `0x1800032a3`: `CHR(MdmHttpWrapper::CreateConnectedAccountsEntity(pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pConnectedAccounts.GetAddressOf()))`

## pseudocode

```c
__int64 __fastcall MdmConnectedAccountsChanged(
        int a1,
        struct Windows::Data::Json::IJsonValue *a2,
        struct Windows::Data::Json::IJsonValue *a3,
        struct Windows::Data::Json::IJsonValue *a4,
        struct Windows::Data::Json::IJsonValue *a5,
        _DWORD *a6)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  int ConnectedAccountsHash; // ebx
  struct Windows::Data::Json::IJsonValue *v13; // rdi
  __int64 (__fastcall *v14)(struct Windows::Data::Json::IJsonValue *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  BYTE *v18; // rdi
  __int64 v19; // rbx
  size_t v20; // rdi
  const wchar_t *v21; // rdx
  size_t v22; // rsi
  const wchar_t *v23; // rcx
  size_t v24; // r8
  unsigned int v25; // eax
  char v27; // [rsp+20h] [rbp-A9h]
  const char *v28; // [rsp+28h] [rbp-A1h]
  HSTRING string; // [rsp+30h] [rbp-99h] BYREF
  int v30; // [rsp+38h] [rbp-91h] BYREF
  struct Windows::Data::Json::IJsonValue *v31; // [rsp+40h] [rbp-89h] BYREF
  BYTE pbData[16]; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int64 v33; // [rsp+58h] [rbp-71h]
  unsigned __int64 v34; // [rsp+60h] [rbp-69h]
  wchar_t *S1[2]; // [rsp+68h] [rbp-61h] BYREF
  size_t N; // [rsp+78h] [rbp-51h]
  unsigned __int64 v37; // [rsp+80h] [rbp-49h]
  wchar_t *S2[2]; // [rsp+88h] [rbp-41h] BYREF
  size_t v39; // [rsp+98h] [rbp-31h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-29h]
  _BYTE v41[16]; // [rsp+A8h] [rbp-21h] BYREF
  int *v42; // [rsp+B8h] [rbp-11h]
  __int64 v43; // [rsp+C0h] [rbp-9h]

  v31 = 0;
  string = 0;
  *(_OWORD *)S2 = 0;
  v39 = 0;
  v10 = 7;
  v40 = 7;
  LOWORD(S2[0]) = 0;
  *(_OWORD *)S1 = 0;
  N = 0;
  v37 = 7;
  LOWORD(S1[0]) = 0;
  *(_OWORD *)pbData = 0;
  v33 = 0;
  v34 = 7;
  *(_WORD *)pbData = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(7, MDMCOMMON_CONNECTED_ACCOUNTS_CHANGED, a3, 1, v41);
  if ( !a2 )
  {
    v11 = 2147942487LL;
    ConnectedAccountsHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v28 = "CPR(pAdmins)";
    v27 = 98;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v11 = 2147942487LL;
    ConnectedAccountsHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        99,
        "CPR(pDeviceOwners)");
    goto LABEL_48;
  }
  if ( !a4 )
  {
    v11 = 2147942487LL;
    ConnectedAccountsHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        100,
        "CPR(pStandardUsers)");
    goto LABEL_48;
  }
  if ( !a6 )
  {
    v11 = 2147942487LL;
    ConnectedAccountsHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        101,
        "CPR(pfChanged)");
    goto LABEL_48;
  }
  ConnectedAccountsHash = MdmSettings::GetConnectedAccountsHash(a1, S2);
  if ( ConnectedAccountsHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v28 = "CHR(MdmSettings::GetConnectedAccountsHash(eDeviceType, wstrConnectedAccountsHashFromRegistry))";
    v27 = 104;
LABEL_20:
    LODWORD(v11) = ConnectedAccountsHash;
LABEL_6:
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      (_DWORD)a2,
      v11,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      v27,
      v28);
    goto LABEL_48;
  }
  ConnectedAccountsHash = MdmHttpWrapper::CreateConnectedAccountsEntity(a2, a3, a4, a5, &v31);
  if ( ConnectedAccountsHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v28 = "CHR(MdmHttpWrapper::CreateConnectedAccountsEntity(pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pC"
          "onnectedAccounts.GetAddressOf()))";
    v27 = 107;
    goto LABEL_20;
  }
  v13 = v31;
  v14 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, HSTRING *))(*(_QWORD *)v31 + 56LL);
  WindowsDeleteString(string);
  string = 0;
  ConnectedAccountsHash = v14(v13, &string);
  if ( ConnectedAccountsHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v28 = "CHR(pConnectedAccounts->Stringify(hstrConnectedAccounts.GetAddressOf()))";
    v27 = 108;
    goto LABEL_20;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v17 = -1;
  do
    ++v17;
  while ( StringRawBuffer[v17] );
  if ( v17 > v34 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)pbData,
      v17,
      v16,
      StringRawBuffer);
  }
  else
  {
    v18 = pbData;
    if ( v34 > 7 )
      v18 = *(BYTE **)pbData;
    v33 = v17;
    v19 = 2 * v17;
    memmove_0(v18, StringRawBuffer, 2 * v17);
    *(_WORD *)&v18[v19] = 0;
  }
  ConnectedAccountsHash = MdmCrypto::HashString(pbData, S1);
  if ( ConnectedAccountsHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v28 = "CHR(MdmCrypto::HashString(wstrConnectedAccounts, wstrConnectedAccountsNewHash))";
    v27 = 112;
    goto LABEL_20;
  }
  v20 = v39;
  v21 = (const wchar_t *)S2;
  if ( v40 > 7 )
    v21 = S2[0];
  v22 = N;
  v23 = (const wchar_t *)S1;
  if ( v37 > 7 )
    v23 = S1[0];
  v24 = v39;
  if ( v39 >= N )
    v24 = N;
  v25 = wmemcmp(v23, v21, v24);
  v11 = v25;
  if ( !v25 )
  {
    if ( v22 >= v20 )
      v11 = v22 > v20;
    else
      v11 = 0xFFFFFFFFLL;
  }
  *a6 = v11 != 0;
LABEL_48:
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v30 = ConnectedAccountsHash;
    v42 = &v30;
    v43 = 4;
    McGenEventWrite_EventWriteTransfer(v10, MDMCOMMON_CONNECTED_ACCOUNTS_CHANGED_RESULT, v11, 2, v41);
  }
  std::wstring::~wstring((char **)pbData);
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring((char **)S2);
  WindowsDeleteString(string);
  string = 0;
  if ( v31 )
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)ConnectedAccountsHash;
}

```

## disassembly

```asm
0x1800030c0  push    rbp
0x1800030c2  push    rbx
0x1800030c3  push    rsi
0x1800030c4  push    rdi
0x1800030c5  push    r12
0x1800030c7  push    r13
0x1800030c9  push    r14
0x1800030cb  push    r15
0x1800030cd  lea     rbp, [rsp-0Fh]
0x1800030d2  sub     rsp, 0D8h
0x1800030d9  mov     rax, cs:__security_cookie
0x1800030e0  xor     rax, rsp
0x1800030e3  mov     [rbp+47h+var_48], rax
0x1800030e7  mov     r14, r9
0x1800030ea  mov     rsi, r8
0x1800030ed  mov     rdi, rdx
0x1800030f0  mov     ebx, ecx
0x1800030f2  mov     r12, [rbp+47h+arg_20]
0x1800030f6  mov     r15, [rbp+47h+arg_28]
0x1800030fa  xor     r13d, r13d
0x1800030fd  mov     [rsp+110h+var_D0], r13
0x180003102  mov     [rsp+110h+string], r13
0x180003107  xorps   xmm0, xmm0
0x18000310a  movups  xmmword ptr [rbp+47h+S2], xmm0
0x18000310e  mov     [rbp+47h+var_78], r13
0x180003112  lea     ecx, [r13+7]
0x180003116  mov     [rbp+47h+var_70], rcx
0x18000311a  mov     word ptr [rbp+47h+S2], r13w
0x18000311f  movups  xmmword ptr [rbp+47h+S1], xmm0
0x180003123  mov     [rbp+47h+N], r13
0x180003127  mov     [rbp+47h+var_90], rcx
0x18000312b  mov     word ptr [rbp+47h+S1], r13w
0x180003130  movups  xmmword ptr [rsp+110h+pbData], xmm0
0x180003135  mov     [rbp+47h+var_B8], r13
0x180003139  mov     [rbp+47h+var_B0], rcx
0x18000313d  mov     word ptr [rsp+110h+pbData], r13w
0x180003143  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000314a  jz      short loc_180003165
0x18000314c  lea     rax, [rbp+47h+var_68]
0x180003150  mov     [rsp+110h+var_F0], rax
0x180003155  lea     r9d, [r13+1]
0x180003159  lea     rdx, MDMCOMMON_CONNECTED_ACCOUNTS_CHANGED
0x180003160  call    McGenEventWrite_EventWriteTransfer
0x180003165  test    rdi, rdi
0x180003168  jnz     short loc_1800031A5
0x18000316a  mov     r8d, 80070057h
0x180003170  mov     ebx, r8d
0x180003173  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000317a  jz      loc_1800033FC
0x180003180  lea     rax, aCprPadmins; "CPR(pAdmins)"
0x180003187  mov     [rsp+110h+var_E8], rax
0x18000318c  mov     dword ptr [rsp+110h+var_F0], 262h
0x180003194  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000319b  call    McTemplateU0dsqs_EventWriteTransfer
0x1800031a0  jmp     loc_1800033FC
0x1800031a5  test    rsi, rsi
0x1800031a8  jnz     short loc_1800031D6
0x1800031aa  mov     r8d, 80070057h
0x1800031b0  mov     ebx, r8d
0x1800031b3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800031ba  jz      loc_1800033FC
0x1800031c0  lea     rax, aCprPdeviceowne; "CPR(pDeviceOwners)"
0x1800031c7  mov     [rsp+110h+var_E8], rax
0x1800031cc  mov     dword ptr [rsp+110h+var_F0], 263h
0x1800031d4  jmp     short loc_180003194
0x1800031d6  test    r14, r14
0x1800031d9  jnz     short loc_180003207
0x1800031db  mov     r8d, 80070057h
0x1800031e1  mov     ebx, r8d
0x1800031e4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800031eb  jz      loc_1800033FC
0x1800031f1  lea     rax, aCprPstandardus; "CPR(pStandardUsers)"
0x1800031f8  mov     [rsp+110h+var_E8], rax
0x1800031fd  mov     dword ptr [rsp+110h+var_F0], 264h
0x180003205  jmp     short loc_180003194
0x180003207  test    r15, r15
0x18000320a  jnz     short loc_18000323B
0x18000320c  mov     r8d, 80070057h
0x180003212  mov     ebx, r8d
0x180003215  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000321c  jz      loc_1800033FC
0x180003222  lea     rax, aCprPfchanged; "CPR(pfChanged)"
0x180003229  mov     [rsp+110h+var_E8], rax
0x18000322e  mov     dword ptr [rsp+110h+var_F0], 265h
0x180003236  jmp     loc_180003194
0x18000323b  lea     rdx, [rbp+47h+S2]
0x18000323f  mov     ecx, ebx
0x180003241  call    ?GetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetConnectedAccountsHash(MdmDeviceContext,std::wstring &)
0x180003246  mov     ebx, eax
0x180003248  test    eax, eax
0x18000324a  jns     short loc_180003275
0x18000324c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003253  jz      loc_1800033FC
0x180003259  lea     rax, aChrMdmsettings_10; "CHR(MdmSettings::GetConnectedAccountsHa"...
0x180003260  mov     [rsp+110h+var_E8], rax
0x180003265  mov     dword ptr [rsp+110h+var_F0], 268h
0x18000326d  mov     r8d, ebx
0x180003270  jmp     loc_180003194
0x180003275  lea     rax, [rsp+110h+var_D0]
0x18000327a  mov     [rsp+110h+var_F0], rax; struct Windows::Data::Json::IJsonValue **
0x18000327f  mov     r9, r12; struct Windows::Data::Json::IJsonValue *
0x180003282  mov     r8, r14; struct Windows::Data::Json::IJsonValue *
0x180003285  mov     rdx, rsi; struct Windows::Data::Json::IJsonValue *
0x180003288  mov     rcx, rdi; struct Windows::Data::Json::IJsonValue *
0x18000328b  call    ?CreateConnectedAccountsEntity@MdmHttpWrapper@@SAJPEAUIJsonValue@Json@Data@Windows@@000PEAPEAU2345@@Z; MdmHttpWrapper::CreateConnectedAccountsEntity(Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue * *)
0x180003290  mov     ebx, eax
0x180003292  test    eax, eax
0x180003294  jns     short loc_1800032B9
0x180003296  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000329d  jz      loc_1800033FC
0x1800032a3  lea     rax, aChrMdmhttpwrap_4; "CHR(MdmHttpWrapper::CreateConnectedAcco"...
0x1800032aa  mov     [rsp+110h+var_E8], rax
0x1800032af  mov     dword ptr [rsp+110h+var_F0], 26Bh
0x1800032b7  jmp     short loc_18000326D
0x1800032b9  mov     rdi, [rsp+110h+var_D0]
0x1800032be  mov     rax, [rdi]
0x1800032c1  mov     rbx, [rax+38h]
0x1800032c5  mov     rcx, [rsp+110h+string]; string
0x1800032ca  call    cs:__imp_WindowsDeleteString
0x1800032d0  mov     [rsp+110h+string], r13
0x1800032d5  lea     rdx, [rsp+110h+string]
0x1800032da  mov     rcx, rdi
0x1800032dd  mov     rax, rbx
0x1800032e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e5  mov     ebx, eax
0x1800032e7  test    eax, eax
0x1800032e9  jns     short loc_180003311
0x1800032eb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800032f2  jz      loc_1800033FC
0x1800032f8  lea     rax, aChrPconnecteda; "CHR(pConnectedAccounts->Stringify(hstrC"...
0x1800032ff  mov     [rsp+110h+var_E8], rax
0x180003304  mov     dword ptr [rsp+110h+var_F0], 26Ch
0x18000330c  jmp     loc_18000326D
0x180003311  xor     edx, edx; length
0x180003313  mov     rcx, [rsp+110h+string]; string
0x180003318  call    cs:__imp_WindowsGetStringRawBuffer
0x18000331e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180003322  mov     rdx, r14
0x180003325  inc     rdx
0x180003328  cmp     [rax+rdx*2], r13w
0x18000332d  jnz     short loc_180003325
0x18000332f  cmp     rdx, [rbp+47h+var_B0]
0x180003333  ja      short loc_180003362
0x180003335  lea     rdi, [rsp+110h+pbData]
0x18000333a  cmp     [rbp+47h+var_B0], 7
0x18000333f  cmova   rdi, qword ptr [rsp+110h+pbData]
0x180003345  mov     [rbp+47h+var_B8], rdx
0x180003349  lea     rbx, [rdx+rdx]
0x18000334d  mov     r8, rbx; Size
0x180003350  mov     rdx, rax; Src
0x180003353  mov     rcx, rdi; void *
0x180003356  call    memmove_0
0x18000335b  mov     [rbx+rdi], r13w
0x180003360  jmp     short loc_18000336F
0x180003362  mov     r9, rax
0x180003365  lea     rcx, [rsp+110h+pbData]
0x18000336a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000336f  lea     rdx, [rbp+47h+S1]
0x180003373  lea     rcx, [rsp+110h+pbData]; pbData
0x180003378  call    ?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MdmCrypto::HashString(std::wstring &,std::wstring &)
0x18000337d  mov     ebx, eax
0x18000337f  test    eax, eax
0x180003381  jns     short loc_1800033A5
0x180003383  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000338a  jz      short loc_1800033FC
0x18000338c  lea     rax, aChrMdmcryptoHa; "CHR(MdmCrypto::HashString(wstrConnected"...
0x180003393  mov     [rsp+110h+var_E8], rax
0x180003398  mov     dword ptr [rsp+110h+var_F0], 270h
0x1800033a0  jmp     loc_18000326D
0x1800033a5  mov     rdi, [rbp+47h+var_78]
0x1800033a9  lea     rdx, [rbp+47h+S2]
0x1800033ad  cmp     [rbp+47h+var_70], 7
0x1800033b2  cmova   rdx, [rbp+47h+S2]; S2
0x1800033b7  mov     rsi, [rbp+47h+N]
0x1800033bb  lea     rcx, [rbp+47h+S1]
0x1800033bf  cmp     [rbp+47h+var_90], 7
0x1800033c4  cmova   rcx, [rbp+47h+S1]; S1
0x1800033c9  mov     r8, rdi
0x1800033cc  cmp     rdi, rsi
0x1800033cf  cmovnb  r8, rsi; N
0x1800033d3  call    wmemcmp
0x1800033d8  mov     r8d, eax
0x1800033db  test    eax, eax
0x1800033dd  jnz     short loc_1800033F0
0x1800033df  cmp     rsi, rdi
0x1800033e2  jnb     short loc_1800033E9
0x1800033e4  mov     r8d, r14d
0x1800033e7  jmp     short loc_1800033F0
0x1800033e9  mov     r8d, r13d
0x1800033ec  setnbe  r8b
0x1800033f0  mov     eax, r13d
0x1800033f3  test    r8d, r8d
0x1800033f6  setnz   al
0x1800033f9  mov     [r15], eax
0x1800033fc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003403  jz      short loc_180003436
0x180003405  mov     [rsp+110h+var_D8], ebx
0x180003409  lea     rax, [rsp+110h+var_D8]
0x18000340e  mov     [rbp+47h+var_58], rax
0x180003412  mov     [rbp+47h+var_50], 4
0x18000341a  lea     rax, [rbp+47h+var_68]
0x18000341e  mov     [rsp+110h+var_F0], rax
0x180003423  mov     r9d, 2
0x180003429  lea     rdx, MDMCOMMON_CONNECTED_ACCOUNTS_CHANGED_RESULT
0x180003430  call    McGenEventWrite_EventWriteTransfer
0x180003435  nop
0x180003436  lea     rcx, [rsp+110h+pbData]
0x18000343b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003440  nop
0x180003441  lea     rcx, [rbp+47h+S1]
0x180003445  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000344a  nop
0x18000344b  lea     rcx, [rbp+47h+S2]
0x18000344f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003454  nop
0x180003455  mov     rcx, [rsp+110h+string]; string
0x18000345a  call    cs:__imp_WindowsDeleteString
0x180003460  mov     [rsp+110h+string], r13
0x180003465  mov     rcx, [rsp+110h+var_D0]
0x18000346a  test    rcx, rcx
0x18000346d  jz      short loc_18000347C
0x18000346f  mov     rax, [rcx]
0x180003472  mov     rax, [rax+10h]
0x180003476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347b  nop
0x18000347c  mov     eax, ebx
0x18000347e  mov     rcx, [rbp+47h+var_48]
0x180003482  xor     rcx, rsp; StackCookie
0x180003485  call    __security_check_cookie
0x18000348a  add     rsp, 0D8h
0x180003491  pop     r15
0x180003493  pop     r14
0x180003495  pop     r13
0x180003497  pop     r12
0x180003499  pop     rdi
0x18000349a  pop     rsi
0x18000349b  pop     rbx
0x18000349c  pop     rbp
0x18000349d  retn
```
