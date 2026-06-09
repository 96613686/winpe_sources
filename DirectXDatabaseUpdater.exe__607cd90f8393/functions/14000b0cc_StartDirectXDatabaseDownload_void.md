# StartDirectXDatabaseDownload(void)

- ea: `0x14000b0cc`
- end: `0x14000b582`
- name: `?StartDirectXDatabaseDownload@@YAJXZ`
- size: `1206`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f2a4`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140005204`
- `0x140005680`
- `0x140005cac`
- `0x140005f34`
- `0x140006060`
- `0x140006a10`
- `0x140006c80`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000ac0c`
- `0x14000adcc`
- `0x14000b0cc`
- `0x14000b5fc`
- `0x14000b6e4`
- `0x14000bb94`
- `0x14000cc54`
- `0x14000df28`
- `0x14000e17c`
- `0x140010ce8`
- `0x1400120b0`
- `0x1400122f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000b1de`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000b1de`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x14000b315`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x14000b315`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x14000b1a5`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x14000b1a5`

## string_xrefs

- `0x14000b343`: `CreateDbDownloadJobActivity`
- `0x14000b1ef`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000b24a`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000b40b`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000b4b5`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000b527`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000b197`: `DisableDirectXDatabaseUpdate`
- `0x14000b388`: `.microsoft.com/`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 StartDirectXDatabaseDownload(void)
{
  __int64 v0; // rcx
  int JsonFile; // eax
  unsigned int LastError; // ebx
  __int64 v3; // rdx
  bool v4; // dl
  const char *v5; // r9
  bool v6; // si
  const unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rdx
  const struct VersionInfo *v10; // rax
  unsigned int v11; // ebx
  int v12; // eax
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rdx
  int inited; // eax
  const wchar_t *v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  _DWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[32]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v29[42]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v30[42]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v31[32]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v32[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  WCHAR Buffer[264]; // [rsp+5D0h] [rbp+4D0h] BYREF
  WCHAR FileName[264]; // [rsp+7E0h] [rbp+6E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A28h] [rbp+928h]

  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "GetSettingsPayloadActivity");
  v30[0] = &DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::`vftable';
  DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StartActivity((DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *)v30);
  *(_OWORD *)v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21[0]) = 0;
  *(_OWORD *)v23 = 0;
  v24 = si128;
  LOWORD(v23[0]) = 0;
  LOBYTE(v0) = 1;
  JsonFile = ReadJsonFile(v0, v21, v23, 0);
  LastError = JsonFile;
  if ( JsonFile < 0 )
  {
    v3 = 33;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)JsonFile,
      (int)v17);
    goto LABEL_44;
  }
  if ( JsonFile != 1 )
  {
    v19[0] = 0;
    if ( (int)PolicyManager_GetPolicyInt(L"System", L"DisableDirectXDatabaseUpdate", v19) >= 0 && v19[0] == 1 )
    {
      v4 = 1;
      goto LABEL_5;
    }
    memset_0(Buffer, 0, 0x208u);
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x34,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
                    v5);
      goto LABEL_44;
    }
    memset_0(v32, 0, 0x208u);
    v17 = (const wchar_t *)L"apppatch";
    JsonFile = StringCchPrintfW(v32, 0x104u, L"%ws\\%ws", Buffer);
    LastError = JsonFile;
    if ( JsonFile < 0 )
    {
      v3 = 55;
      goto LABEL_14;
    }
    memset_0(FileName, 0, 0x208u);
    v17 = L"DirectXApps.sdb";
    JsonFile = StringCchPrintfW(FileName, 0x104u, L"%ws\\%ws", v32);
    LastError = JsonFile;
    if ( JsonFile < 0 )
    {
      v3 = 57;
      goto LABEL_14;
    }
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v30);
    memset_0(v31, 0, sizeof(v31));
    v19[1] = 64;
    JsonFile = DoesFileExist(FileName);
    LastError = JsonFile;
    if ( JsonFile < 0 )
    {
      v3 = 66;
      goto LABEL_14;
    }
    v6 = 0;
    if ( !JsonFile )
    {
      v17 = v31;
      v6 = (int)QueryDirectXDatabaseConfig(0, 0, 0, 0) >= 0;
    }
    v7 = (const unsigned __int16 *)v21;
    if ( si128.m128i_i64[1] > 7uLL )
      v7 = v21[0];
    v8 = (const unsigned __int16 *)v23;
    if ( v24.m128i_i64[1] > 7uLL )
      v8 = v23[0];
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v29,
      "CreateDbDownloadJobActivity");
    v29[0] = &DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::`vftable';
    DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::StartActivity(
      (DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *)v29,
      v8,
      v7);
    if ( !std::wstring::find(v23, L"https://") && std::wstring::find(v23, L".microsoft.com/") != -1 )
    {
      if ( v6 )
      {
        VersionInfo::VersionInfo((VersionInfo *)v25, v31);
        v9 = (const unsigned __int16 *)v21;
        if ( si128.m128i_i64[1] > 7uLL )
          v9 = v21[0];
        v10 = VersionInfo::VersionInfo((VersionInfo *)v27, v9);
        v11 = (unsigned int)VersionInfo::Compare((VersionInfo *)v25, v10) >> 31;
        std::wstring::_Tidy_deallocate(v28);
        if ( (unsigned __int8)v11 != 1 )
        {
          v12 = AcknowledgeSettingsPayload();
          LastError = v12;
          if ( v12 >= 0 )
          {
            DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::Stop(
              (DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *)v29,
              v31);
            std::wstring::_Tidy_deallocate(v26);
            DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity((DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *)v29);
            goto LABEL_6;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5B,
            (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
            (const char *)(unsigned int)v12,
            (int)v17);
          std::wstring::_Tidy_deallocate(v26);
LABEL_43:
          DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity((DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *)v29);
          goto LABEL_44;
        }
        std::wstring::_Tidy_deallocate(v26);
      }
      v20 = 0;
      v13 = (const unsigned __int16 *)v21;
      if ( si128.m128i_i64[1] > 7uLL )
        v13 = v21[0];
      v14 = (const unsigned __int16 *)v23;
      if ( v24.m128i_i64[1] > 7uLL )
        v14 = v23[0];
      inited = BitsHelper::InitJob((BitsHelper *)&v20, v14, v13, v32, L"DirectXApps.lzma");
      LastError = inited;
      if ( inited >= 0 )
      {
        wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v20);
        DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity((DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *)v29);
        std::wstring::_Tidy_deallocate(v23);
        std::wstring::_Tidy_deallocate(v21);
        DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity((DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *)v30);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
        (const char *)(unsigned int)inited,
        v18);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v20);
      goto LABEL_43;
    }
    LastError = -2143485920;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)0x803D0020LL,
      (int)v17);
    goto LABEL_43;
  }
  v4 = 0;
LABEL_5:
  DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::Stop(
    (DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *)v30,
    v4);
LABEL_6:
  LastError = 0;
LABEL_44:
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v21);
  DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity((DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *)v30);
  return LastError;
}

```

## disassembly

```asm
0x14000b0cc  push    rbp
0x14000b0ce  push    rbx
0x14000b0cf  push    rsi
0x14000b0d0  push    rdi
0x14000b0d1  lea     rbp, [rsp-908h]
0x14000b0d9  sub     rsp, 0A08h
0x14000b0e0  mov     rax, cs:__security_cookie
0x14000b0e7  xor     rax, rsp
0x14000b0ea  mov     [rbp+920h+var_30], rax
0x14000b0f1  lea     rdx, aGetsettingspay; "GetSettingsPayloadActivity"
0x14000b0f8  lea     rcx, [rbp+920h+var_7F0]
0x14000b0ff  call    ??0?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000b104  lea     rax, ??_7GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::`vftable'
0x14000b10b  mov     [rbp+920h+var_7F0], rax
0x14000b112  lea     rcx, [rbp+920h+var_7F0]; this
0x14000b119  call    ?StartActivity@GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXXZ; DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StartActivity(void)
0x14000b11e  nop
0x14000b11f  xorps   xmm0, xmm0
0x14000b122  movups  xmmword ptr [rsp+0A20h+var_9E0], xmm0
0x14000b127  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000b12f  movdqu  [rsp+0A20h+var_9D0], xmm1
0x14000b135  xor     eax, eax
0x14000b137  mov     word ptr [rsp+0A20h+var_9E0], ax
0x14000b13c  movups  xmmword ptr [rsp+0A20h+var_9C0], xmm0
0x14000b141  movdqu  [rsp+0A20h+var_9B0], xmm1
0x14000b147  mov     word ptr [rsp+0A20h+var_9C0], ax
0x14000b14c  xor     r9d, r9d
0x14000b14f  lea     r8, [rsp+0A20h+var_9C0]
0x14000b154  lea     rdx, [rsp+0A20h+var_9E0]
0x14000b159  mov     cl, 1
0x14000b15b  call    ?ReadJsonFile@@YAJ_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; ReadJsonFile(bool,std::wstring *,std::wstring *,std::wstring *)
0x14000b160  mov     ebx, eax
0x14000b162  test    eax, eax
0x14000b164  jns     short loc_14000B170
0x14000b166  mov     edx, 21h ; '!'
0x14000b16b  jmp     loc_14000B24A
0x14000b170  cmp     eax, 1
0x14000b173  jnz     short loc_14000B18A
0x14000b175  xor     edx, edx; bool
0x14000b177  lea     rcx, [rbp+920h+var_7F0]; this
0x14000b17e  call    ?Stop@GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAAX_N@Z; DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::Stop(bool)
0x14000b183  xor     ebx, ebx
0x14000b185  jmp     loc_14000B543
0x14000b18a  mov     [rsp+0A20h+var_9F0], 0
0x14000b192  lea     r8, [rsp+0A20h+var_9F0]
0x14000b197  lea     rdx, aDisabledirectx; "DisableDirectXDatabaseUpdate"
0x14000b19e  lea     rcx, aSystem; "System"
0x14000b1a5  call    cs:__imp_PolicyManager_GetPolicyInt
0x14000b1ab  test    eax, eax
0x14000b1ad  js      short loc_14000B1BA
0x14000b1af  cmp     [rsp+0A20h+var_9F0], 1
0x14000b1b4  jnz     short loc_14000B1BA
0x14000b1b6  mov     dl, 1
0x14000b1b8  jmp     short loc_14000B177
0x14000b1ba  mov     edi, 208h
0x14000b1bf  mov     r8d, edi; Size
0x14000b1c2  xor     edx, edx; Val
0x14000b1c4  lea     rcx, [rbp+920h+Buffer]; void *
0x14000b1cb  call    memset_0
0x14000b1d0  mov     esi, 104h
0x14000b1d5  mov     edx, esi; uSize
0x14000b1d7  lea     rcx, [rbp+920h+Buffer]; lpBuffer
0x14000b1de  call    cs:__imp_GetWindowsDirectoryW
0x14000b1e4  test    eax, eax
0x14000b1e6  jnz     short loc_14000B205
0x14000b1e8  mov     rcx, [rbp+928h]; this
0x14000b1ef  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000b1f6  lea     edx, [rax+34h]; void *
0x14000b1f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b1fe  mov     ebx, eax
0x14000b200  jmp     loc_14000B543
0x14000b205  mov     r8, rdi; Size
0x14000b208  xor     edx, edx; Val
0x14000b20a  lea     rcx, [rbp+920h+var_660]; void *
0x14000b211  call    memset_0
0x14000b216  lea     rax, aApppatch; "apppatch"
0x14000b21d  mov     [rsp+0A20h+var_A00], rax; int
0x14000b222  lea     r9, [rbp+920h+Buffer]
0x14000b229  lea     r8, aWsWs; "%ws\\%ws"
0x14000b230  mov     rdx, rsi; unsigned __int64
0x14000b233  lea     rcx, [rbp+920h+var_660]; unsigned __int16 *
0x14000b23a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b23f  mov     ebx, eax
0x14000b241  test    eax, eax
0x14000b243  jns     short loc_14000B265
0x14000b245  mov     edx, 37h ; '7'; void *
0x14000b24a  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000b251  mov     r9d, eax; char *
0x14000b254  mov     rcx, [rbp+928h]; this
0x14000b25b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b260  jmp     loc_14000B543
0x14000b265  mov     r8, rdi; Size
0x14000b268  xor     edx, edx; Val
0x14000b26a  lea     rcx, [rbp+920h+FileName]; void *
0x14000b271  call    memset_0
0x14000b276  lea     rax, aDirectxappsSdb; "DirectXApps.sdb"
0x14000b27d  mov     [rsp+0A20h+var_A00], rax
0x14000b282  lea     r9, [rbp+920h+var_660]
0x14000b289  lea     r8, aWsWs; "%ws\\%ws"
0x14000b290  mov     rdx, rsi; unsigned __int64
0x14000b293  lea     rcx, [rbp+920h+FileName]; unsigned __int16 *
0x14000b29a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b29f  mov     ebx, eax
0x14000b2a1  test    eax, eax
0x14000b2a3  jns     short loc_14000B2AC
0x14000b2a5  mov     edx, 39h ; '9'
0x14000b2aa  jmp     short loc_14000B24A
0x14000b2ac  lea     rcx, [rbp+920h+var_7F0]
0x14000b2b3  call    ?Stop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000b2b8  mov     ebx, 40h ; '@'
0x14000b2bd  mov     r8d, ebx; Size
0x14000b2c0  xor     edx, edx; Val
0x14000b2c2  lea     rcx, [rbp+920h+var_6A0]; void *
0x14000b2c9  call    memset_0
0x14000b2ce  mov     [rsp+0A20h+var_9EC], ebx
0x14000b2d2  lea     rcx, [rbp+920h+FileName]; lpFileName
0x14000b2d9  call    ?DoesFileExist@@YAJPEBG@Z; DoesFileExist(ushort const *)
0x14000b2de  mov     ebx, eax
0x14000b2e0  test    eax, eax
0x14000b2e2  jns     short loc_14000B2EE
0x14000b2e4  mov     edx, 42h ; 'B'
0x14000b2e9  jmp     loc_14000B24A
0x14000b2ee  xor     sil, sil
0x14000b2f1  test    eax, eax
0x14000b2f3  jnz     short loc_14000B321
0x14000b2f5  lea     rax, [rsp+0A20h+var_9EC]
0x14000b2fa  mov     [rsp+0A20h+var_9F8], rax
0x14000b2ff  lea     rax, [rbp+920h+var_6A0]
0x14000b306  mov     [rsp+0A20h+var_A00], rax; int
0x14000b30b  xor     r9d, r9d
0x14000b30e  xor     r8d, r8d
0x14000b311  xor     edx, edx
0x14000b313  xor     ecx, ecx
0x14000b315  call    cs:__imp_QueryDirectXDatabaseConfig
0x14000b31b  test    eax, eax
0x14000b31d  setns   sil
0x14000b321  lea     rdi, [rsp+0A20h+var_9E0]
0x14000b326  cmp     qword ptr [rsp+0A20h+var_9D0+8], 7
0x14000b32c  cmova   rdi, [rsp+0A20h+var_9E0]
0x14000b332  lea     rbx, [rsp+0A20h+var_9C0]
0x14000b337  cmp     qword ptr [rsp+0A20h+var_9B0+8], 7
0x14000b33d  cmova   rbx, [rsp+0A20h+var_9C0]
0x14000b343  lea     rdx, aCreatedbdownlo; "CreateDbDownloadJobActivity"
0x14000b34a  lea     rcx, [rbp+920h+var_940]
0x14000b34e  call    ??0?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000b353  lea     rax, ??_7CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::`vftable'
0x14000b35a  mov     [rbp+920h+var_940], rax
0x14000b35e  mov     r8, rdi; unsigned __int16 *
0x14000b361  mov     rdx, rbx; unsigned __int16 *
0x14000b364  lea     rcx, [rbp+920h+var_940]; this
0x14000b368  call    ?StartActivity@CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG0@Z; DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::StartActivity(ushort const *,ushort const *)
0x14000b36d  nop
0x14000b36e  lea     rdx, aHttps; "https://"
0x14000b375  lea     rcx, [rsp+0A20h+var_9C0]
0x14000b37a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000b37f  test    rax, rax
0x14000b382  jnz     loc_14000B518
0x14000b388  lea     rdx, aMicrosoftCom; ".microsoft.com/"
0x14000b38f  lea     rcx, [rsp+0A20h+var_9C0]
0x14000b394  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000b399  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b39d  jz      loc_14000B518
0x14000b3a3  test    sil, sil
0x14000b3a6  jz      loc_14000B45D
0x14000b3ac  lea     rdx, [rbp+920h+var_6A0]; unsigned __int16 *
0x14000b3b3  lea     rcx, [rbp+920h+var_9A0]; this
0x14000b3b7  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x14000b3bc  nop
0x14000b3bd  lea     rdx, [rsp+0A20h+var_9E0]
0x14000b3c2  cmp     qword ptr [rsp+0A20h+var_9D0+8], 7
0x14000b3c8  cmova   rdx, [rsp+0A20h+var_9E0]; unsigned __int16 *
0x14000b3ce  lea     rcx, [rbp+920h+var_970]; this
0x14000b3d2  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x14000b3d7  mov     rdx, rax; struct VersionInfo *
0x14000b3da  lea     rcx, [rbp+920h+var_9A0]; this
0x14000b3de  call    ?Compare@VersionInfo@@QEBAHAEBV1@@Z; VersionInfo::Compare(VersionInfo const &)
0x14000b3e3  mov     ebx, eax
0x14000b3e5  shr     ebx, 1Fh
0x14000b3e8  lea     rcx, [rbp+920h+var_960]
0x14000b3ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b3f1  xor     bl, 1
0x14000b3f4  jz      short loc_14000B454
0x14000b3f6  call    ?AcknowledgeSettingsPayload@@YAJXZ; AcknowledgeSettingsPayload(void)
0x14000b3fb  mov     ebx, eax
0x14000b3fd  test    eax, eax
0x14000b3ff  jns     short loc_14000B42B
0x14000b401  mov     rcx, [rbp+928h]; this
0x14000b408  mov     r9d, eax; char *
0x14000b40b  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000b412  mov     edx, 5Bh ; '['; void *
0x14000b417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b41c  nop
0x14000b41d  lea     rcx, [rbp+920h+var_990]
0x14000b421  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b426  jmp     loc_14000B539
0x14000b42b  lea     rdx, [rbp+920h+var_6A0]; unsigned __int16 *
0x14000b432  lea     rcx, [rbp+920h+var_940]; this
0x14000b436  call    ?Stop@CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z; DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::Stop(ushort const *)
0x14000b43b  nop
0x14000b43c  lea     rcx, [rbp+920h+var_990]
0x14000b440  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b445  nop
0x14000b446  lea     rcx, [rbp+920h+var_940]; this
0x14000b44a  call    ??1CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity(void)
0x14000b44f  jmp     loc_14000B183
0x14000b454  lea     rcx, [rbp+920h+var_990]
0x14000b458  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b45d  mov     [rsp+0A20h+var_9E8], 0
0x14000b466  lea     r8, [rsp+0A20h+var_9E0]
0x14000b46b  cmp     qword ptr [rsp+0A20h+var_9D0+8], 7
0x14000b471  cmova   r8, [rsp+0A20h+var_9E0]; unsigned __int16 *
0x14000b477  lea     rdx, [rsp+0A20h+var_9C0]
0x14000b47c  cmp     qword ptr [rsp+0A20h+var_9B0+8], 7
0x14000b482  cmova   rdx, [rsp+0A20h+var_9C0]; unsigned __int16 *
0x14000b488  lea     rax, aDirectxappsLzm; "DirectXApps.lzma"
0x14000b48f  mov     [rsp+0A20h+var_A00], rax; int
0x14000b494  lea     r9, [rbp+920h+var_660]; unsigned __int16 *
0x14000b49b  lea     rcx, [rsp+0A20h+var_9E8]; this
0x14000b4a0  call    ?InitJob@BitsHelper@@QEAAJPEBG000@Z; BitsHelper::InitJob(ushort const *,ushort const *,ushort const *,ushort const *)
0x14000b4a5  mov     ebx, eax
0x14000b4a7  test    eax, eax
0x14000b4a9  jns     short loc_14000B4D3
0x14000b4ab  mov     rcx, [rbp+928h]; this
0x14000b4b2  mov     r9d, eax; char *
0x14000b4b5  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000b4bc  mov     edx, 64h ; 'd'; void *
0x14000b4c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b4c6  nop
0x14000b4c7  lea     rcx, [rsp+0A20h+var_9E8]
0x14000b4cc  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000b4d1  jmp     short loc_14000B539
0x14000b4d3  lea     rcx, [rbp+920h+var_940]
0x14000b4d7  call    ?Stop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000b4dc  nop
0x14000b4dd  lea     rcx, [rsp+0A20h+var_9E8]
0x14000b4e2  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000b4e7  nop
0x14000b4e8  lea     rcx, [rbp+920h+var_940]; this
0x14000b4ec  call    ??1CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity(void)
0x14000b4f1  nop
0x14000b4f2  lea     rcx, [rsp+0A20h+var_9C0]
0x14000b4f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b4fc  nop
0x14000b4fd  lea     rcx, [rsp+0A20h+var_9E0]
0x14000b502  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b507  nop
0x14000b508  lea     rcx, [rbp+920h+var_7F0]; this
0x14000b50f  call    ??1GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity(void)
0x14000b514  xor     eax, eax
0x14000b516  jmp     short loc_14000B567
0x14000b518  mov     rcx, [rbp+928h]; this
0x14000b51f  mov     ebx, 803D0020h
0x14000b524  mov     r9d, ebx; char *
0x14000b527  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000b52e  mov     edx, 51h ; 'Q'; void *
0x14000b533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b538  nop
0x14000b539  lea     rcx, [rbp+920h+var_940]; this
0x14000b53d  call    ??1CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity(void)
0x14000b542  nop
0x14000b543  lea     rcx, [rsp+0A20h+var_9C0]
0x14000b548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b54d  nop
0x14000b54e  lea     rcx, [rsp+0A20h+var_9E0]
0x14000b553  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b558  nop
0x14000b559  lea     rcx, [rbp+920h+var_7F0]; this
0x14000b560  call    ??1GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity(void)
0x14000b565  mov     eax, ebx
0x14000b567  mov     rcx, [rbp+920h+var_30]
0x14000b56e  xor     rcx, rsp; StackCookie
0x14000b571  call    __security_check_cookie
0x14000b576  add     rsp, 0A08h
0x14000b57d  pop     rdi
0x14000b57e  pop     rsi
0x14000b57f  pop     rbx
0x14000b580  pop     rbp
0x14000b581  retn
```
