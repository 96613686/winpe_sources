# wWinMain(x,x,x,x)

- ea: `0x409212`
- end: `0x40951f`
- name: `_wWinMain@16`
- size: `781`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x40c8c9`

## callees

- `0x402ae4`
- `0x402bbc`
- `0x407fd4`
- `0x409212`
- `0x409551`
- `0x4098bb`
- `0x409933`
- `0x409b1a`
- `0x40a13c`
- `0x40a256`
- `0x40cb60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x4094f0`
- `KERNEL32!CloseHandle` at `0x4094f0`
- `KERNEL32!CreateEventW` at `0x40944c`
- `KERNEL32!CreateEventW` at `0x40944c`
- `KERNEL32!HeapSetInformation` at `0x409289`
- `KERNEL32!HeapSetInformation` at `0x409289`
- `KERNEL32!SetProcessDEPPolicy` at `0x40927c`
- `KERNEL32!SetProcessDEPPolicy` at `0x40927c`
- `KERNEL32!ReleaseActCtx` at `0x4094c9`
- `KERNEL32!ReleaseActCtx` at `0x4094c9`
- `KERNEL32!GetLastError` at `0x4094f8`
- `KERNEL32!GetLastError` at `0x4094f8`
- `KERNEL32!WaitForSingleObject` at `0x4094b4`
- `KERNEL32!WaitForSingleObject` at `0x4094b4`
- `msvcrt!_wcsnicmp` at `0x4092b8`
- `msvcrt!_wcsnicmp` at `0x4092d9`
- `msvcrt!_wcsnicmp` at `0x4092f2`
- `msvcrt!_wcsnicmp` at `0x40930b`
- `msvcrt!_wcsnicmp` at `0x409320`
- `msvcrt!_wcsnicmp` at `0x409335`
- `msvcrt!_wcsnicmp` at `0x40935b`
- `msvcrt!_wcsnicmp` at `0x4092b8`
- `msvcrt!_wcsnicmp` at `0x4092d9`
- `msvcrt!_wcsnicmp` at `0x4092f2`
- `msvcrt!_wcsnicmp` at `0x40930b`
- `msvcrt!_wcsnicmp` at `0x409320`
- `msvcrt!_wcsnicmp` at `0x409335`
- `msvcrt!_wcsnicmp` at `0x40935b`
- `msvcrt!wcstok_s` at `0x40929a`
- `msvcrt!wcstok_s` at `0x409395`
- `msvcrt!wcstok_s` at `0x40929a`
- `msvcrt!wcstok_s` at `0x409395`
- `msvcrt!_wtoi` at `0x40936c`
- `msvcrt!_wtoi` at `0x40936c`
- `ole32!CoUninitialize` at `0x4094e4`
- `ole32!CoUninitialize` at `0x4094e4`
- `ole32!CoInitializeSecurity` at `0x40948a`
- `ole32!CoInitializeSecurity` at `0x40948a`
- `ole32!CLSIDFromString` at `0x40934b`
- `ole32!CLSIDFromString` at `0x40934b`
- `ole32!CoInitializeEx` at `0x409461`
- `ole32!CoInitializeEx` at `0x409461`

## string_xrefs

- `0x40932f`: `-CLSID:`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // ebx
  wchar_t *v5; // esi
  int v6; // edi
  int v7; // ecx
  signed int LastError; // eax
  GUID v11; // [esp-10h] [ebp-4Ch]
  GUID v12; // [esp-10h] [ebp-4Ch]
  int v13; // [esp+18h] [ebp-24h]
  int v14; // [esp+1Ch] [ebp-20h]
  int v15; // [esp+20h] [ebp-1Ch]
  wchar_t *Context[2]; // [esp+24h] [ebp-18h] BYREF
  wchar_t Delimiter[6]; // [esp+2Ch] [ebp-10h] BYREF

  wcscpy(Delimiter, L" ,\t\n");
  v4 = -2147024809;
  Context[0] = 0;
  v14 = 0;
  v15 = 0;
  v13 = 0;
  Context[1] = 0;
  g_clsid = GUID_NULL;
  GetBOOL((int *)SettingStore::IEVALUE_InetCPL_DepOff);
  SetProcessDEPPolicy(1u);
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v5 = _wcstok_s(lpCmdLine, Delimiter, Context);
  if ( v5 )
  {
    v6 = 0;
    do
    {
      if ( __wcsnicmp(v5, L"-Embedding", 0xBu) )
      {
        if ( __wcsnicmp(v5, L"/REGSERVER", 0xBu) && __wcsnicmp(v5, L"-REGSERVER", 0xBu) )
        {
          if ( __wcsnicmp(v5, L"/UNREGSERVER", 0xDu) && __wcsnicmp(v5, L"-UNREGSERVER", 0xDu) )
          {
            if ( __wcsnicmp(v5, L"-CLSID:", 7u) )
            {
              if ( !__wcsnicmp(v5, L"-PID:", 5u) )
                g_dwIntegrity = __wtoi(v5 + 5);
            }
            else
            {
              CLSIDFromString(v5 + 7, &g_clsid);
            }
          }
          else
          {
            v15 = 1;
          }
        }
        else
        {
          v14 = 1;
        }
      }
      else
      {
        v13 = 1;
      }
      ++v6;
      v5 = _wcstok_s(0, Delimiter, Context);
    }
    while ( v5 );
    if ( v6 != 1 )
    {
      if ( v6 != 2 )
        return v4;
      v7 = 0;
      while ( *(&g_clsid.Data1 + v7) == *(&GUID_NULL.Data1 + v7) )
      {
        if ( ++v7 == 4 )
          return v4;
      }
    }
    if ( v15 )
    {
      v11.Data1 = 2066347157;
      *(_DWORD *)&v11.Data2 = dword_40149C[1];
      *(_QWORD *)v11.Data4 = *(_QWORD *)&dword_40149C[2];
      return UnregisterLocalServer(CLSID_CIeAxiInstaller, v11);
    }
    if ( v14 )
    {
      v12.Data1 = 2066347157;
      *(_DWORD *)&v12.Data2 = dword_40149C[1];
      *(_QWORD *)v12.Data4 = *(_QWORD *)&dword_40149C[2];
      v4 = RegisterLocalServer(CLSID_CIeAxiInstaller, v12);
      if ( v4 < 0 )
        return v4;
      return RegisterProxyDll();
    }
    if ( v13 )
    {
      g_hQuitEvent = CreateEventW(0, 1, 0, 0);
      if ( g_hQuitEvent )
      {
        v4 = CoInitializeEx(0, 0);
        if ( v4 >= 0 )
        {
          if ( SHFusionInitializeFromModuleID(hInstance, 1u) )
          {
            v4 = CoInitializeSecurity(0, -1, 0, 0, 2u, 3u, 0, 0, 0);
            if ( v4 >= 0 )
            {
              v4 = RegisterClassFactory();
              if ( v4 >= 0 )
              {
                IESetProcessDPIAware();
                v4 = CleanupTempDirs();
                WaitForSingleObject(g_hQuitEvent, 0xFFFFFFFF);
                RevokeClassFactory();
              }
            }
            if ( g_hActCtx != (HANDLE)-1 )
            {
              ReleaseActCtx(g_hActCtx);
              g_hActCtx = (HANDLE)-1;
            }
            if ( hModule )
              hModule = (HMODULE)-1;
          }
          CoUninitialize();
        }
        CloseHandle(g_hQuitEvent);
      }
      else
      {
        LastError = GetLastError();
        v4 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          return LastError;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x409212  mov     edi, edi
0x409214  push    ebp
0x409215  mov     ebp, esp
0x409217  sub     esp, 30h
0x40921a  mov     eax, ___security_cookie
0x40921f  xor     eax, ebp
0x409221  mov     [ebp+var_4], eax
0x409224  push    ebx
0x409225  push    esi
0x409226  push    edi; unsigned __int16 *
0x409227  mov     esi, offset asc_401BAC; " ,\t\n"
0x40922c  mov     eax, [ebp+hInstance]
0x40922f  lea     edi, [ebp+Delimiter]
0x409232  mov     [ebp+hModule], eax
0x409235  mov     eax, [ebp+lpCmdLine]
0x409238  xor     ecx, ecx
0x40923a  push    ds:?IEVALUE_InetCPL_DepOff@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_InetCPL_DepOff
0x409240  movsd
0x409241  mov     ebx, 80070057h
0x409246  mov     [ebp+var_2C], ecx
0x409249  mov     [ebp+Context], ecx
0x40924c  mov     [ebp+var_20], ecx
0x40924f  movsd
0x409250  mov     [ebp+var_1C], ecx
0x409253  mov     [ebp+var_24], ecx
0x409256  mov     [ebp+var_14], ecx
0x409259  lea     ecx, [ebp+var_14]
0x40925c  movsw
0x40925e  mov     esi, offset _GUID_NULL
0x409263  mov     [ebp+String], eax
0x409266  mov     edi, offset ?g_clsid@@3U_GUID@@A; _GUID g_clsid
0x40926b  movsd
0x40926c  movsd
0x40926d  movsd
0x40926e  movsd
0x40926f  call    _GetBOOL@8; GetBOOL(x,x)
0x409274  cmp     [ebp+var_14], 0
0x409278  jnz     short loc_409282
0x40927a  push    1; dwFlags
0x40927c  call    ds:__imp__SetProcessDEPPolicy@4; SetProcessDEPPolicy(x)
0x409282  xor     eax, eax
0x409284  push    eax; HeapInformationLength
0x409285  push    eax; HeapInformation
0x409286  push    1; HeapInformationClass
0x409288  push    eax; struct _GUID
0x409289  call    ds:__imp__HeapSetInformation@16; HeapSetInformation(x,x,x,x)
0x40928f  lea     eax, [ebp+Context]
0x409292  push    eax; Context
0x409293  lea     eax, [ebp+Delimiter]
0x409296  push    eax; Delimiter
0x409297  push    [ebp+String]; String
0x40929a  call    ds:__imp__wcstok_s
0x4092a0  mov     esi, eax
0x4092a2  add     esp, 0Ch
0x4092a5  test    esi, esi
0x4092a7  jz      loc_40950C
0x4092ad  mov     edi, [ebp+var_2C]
0x4092b0  push    0Bh; MaxCount
0x4092b2  push    offset aEmbedding; "-Embedding"
0x4092b7  push    esi; String1
0x4092b8  call    ds:__imp___wcsnicmp
0x4092be  add     esp, 0Ch
0x4092c1  test    eax, eax
0x4092c3  jnz     short loc_4092D1
0x4092c5  mov     [ebp+var_24], 1
0x4092cc  jmp     loc_40938A
0x4092d1  push    0Bh; MaxCount
0x4092d3  push    offset aRegserver_1; "/REGSERVER"
0x4092d8  push    esi; String1
0x4092d9  call    ds:__imp___wcsnicmp
0x4092df  add     esp, 0Ch
0x4092e2  test    eax, eax
0x4092e4  jz      loc_409383
0x4092ea  push    0Bh; MaxCount
0x4092ec  push    offset aRegserver; "-REGSERVER"
0x4092f1  push    esi; String1
0x4092f2  call    ds:__imp___wcsnicmp
0x4092f8  add     esp, 0Ch
0x4092fb  test    eax, eax
0x4092fd  jz      loc_409383
0x409303  push    0Dh; MaxCount
0x409305  push    offset aUnregserver; "/UNREGSERVER"
0x40930a  push    esi; String1
0x40930b  call    ds:__imp___wcsnicmp
0x409311  add     esp, 0Ch
0x409314  test    eax, eax
0x409316  jz      short loc_40937A
0x409318  push    0Dh; MaxCount
0x40931a  push    offset aUnregserver_0; "-UNREGSERVER"
0x40931f  push    esi; String1
0x409320  call    ds:__imp___wcsnicmp
0x409326  add     esp, 0Ch
0x409329  test    eax, eax
0x40932b  jz      short loc_40937A
0x40932d  push    7; MaxCount
0x40932f  push    offset aClsid; "-CLSID:"
0x409334  push    esi; String1
0x409335  call    ds:__imp___wcsnicmp
0x40933b  add     esp, 0Ch
0x40933e  test    eax, eax
0x409340  jnz     short loc_409353
0x409342  push    offset ?g_clsid@@3U_GUID@@A; pclsid
0x409347  lea     eax, [esi+0Eh]
0x40934a  push    eax; lpsz
0x40934b  call    ds:__imp__CLSIDFromString@8; CLSIDFromString(x,x)
0x409351  jmp     short loc_40938A
0x409353  push    5; MaxCount
0x409355  push    offset aPid; "-PID:"
0x40935a  push    esi; String1
0x40935b  call    ds:__imp___wcsnicmp
0x409361  add     esp, 0Ch
0x409364  test    eax, eax
0x409366  jnz     short loc_40938A
0x409368  lea     eax, [esi+0Ah]
0x40936b  push    eax; String
0x40936c  call    ds:__imp___wtoi
0x409372  pop     ecx
0x409373  mov     ?g_dwIntegrity@@3KA, eax; ulong g_dwIntegrity
0x409378  jmp     short loc_40938A
0x40937a  mov     [ebp+var_1C], 1
0x409381  jmp     short loc_40938A
0x409383  mov     [ebp+var_20], 1
0x40938a  lea     eax, [ebp+Context]
0x40938d  inc     edi
0x40938e  push    eax; Context
0x40938f  lea     eax, [ebp+Delimiter]
0x409392  push    eax; Delimiter
0x409393  push    0; String
0x409395  call    ds:__imp__wcstok_s
0x40939b  mov     esi, eax
0x40939d  add     esp, 0Ch
0x4093a0  test    esi, esi
0x4093a2  jnz     loc_4092B0
0x4093a8  cmp     edi, 1
0x4093ab  jz      short loc_4093D5
0x4093ad  cmp     edi, 2
0x4093b0  jnz     loc_40950C
0x4093b6  mov     ecx, esi
0x4093b8  mov     edx, offset _GUID_NULL
0x4093bd  mov     eax, offset ?g_clsid@@3U_GUID@@A; _GUID g_clsid
0x4093c2  mov     eax, [eax+ecx*4]
0x4093c5  cmp     eax, [edx+ecx*4]
0x4093c8  jnz     short loc_4093D7
0x4093ca  inc     ecx
0x4093cb  cmp     ecx, 4
0x4093ce  jnz     short loc_4093BD
0x4093d0  jmp     loc_40950C
0x4093d5  xor     esi, esi
0x4093d7  cmp     [ebp+var_1C], 0
0x4093db  jz      short loc_409405
0x4093dd  sub     esp, 10h
0x4093e0  mov     esi, offset dword_40149C
0x4093e5  mov     edi, esp
0x4093e7  sub     esp, 10h
0x4093ea  movsd
0x4093eb  movsd
0x4093ec  movsd
0x4093ed  movsd
0x4093ee  mov     edi, esp
0x4093f0  mov     esi, offset _CLSID_CIeAxiInstaller
0x4093f5  movsd
0x4093f6  movsd
0x4093f7  movsd
0x4093f8  movsd
0x4093f9  call    ?UnregisterLocalServer@@YGJU_GUID@@U1@@Z; UnregisterLocalServer(_GUID,_GUID)
0x4093fe  mov     ebx, eax
0x409400  jmp     loc_40950C
0x409405  cmp     [ebp+var_20], 0
0x409409  jz      short loc_40943D
0x40940b  sub     esp, 10h
0x40940e  mov     esi, offset dword_40149C
0x409413  mov     edi, esp
0x409415  sub     esp, 10h
0x409418  movsd
0x409419  movsd
0x40941a  movsd
0x40941b  movsd
0x40941c  mov     edi, esp
0x40941e  mov     esi, offset _CLSID_CIeAxiInstaller
0x409423  movsd
0x409424  movsd
0x409425  movsd
0x409426  movsd
0x409427  call    ?RegisterLocalServer@@YGJU_GUID@@U1@@Z; RegisterLocalServer(_GUID,_GUID)
0x40942c  mov     ebx, eax
0x40942e  test    ebx, ebx
0x409430  js      loc_40950C
0x409436  call    ?RegisterProxyDll@@YGJPBG@Z; RegisterProxyDll(ushort const *)
0x40943b  jmp     short loc_4093FE
0x40943d  cmp     [ebp+var_24], 0
0x409441  jz      loc_40950C
0x409447  push    esi; lpName
0x409448  push    esi; bInitialState
0x409449  push    1; bManualReset
0x40944b  push    esi; lpEventAttributes
0x40944c  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x409452  mov     ?g_hQuitEvent@@3PAXA, eax; void * g_hQuitEvent
0x409457  test    eax, eax
0x409459  jz      loc_4094F8
0x40945f  push    esi; dwCoInit
0x409460  push    esi; pvReserved
0x409461  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x409467  mov     ebx, eax
0x409469  test    ebx, ebx
0x40946b  js      short loc_4094EA
0x40946d  mov     ecx, [ebp+hModule]; hModule
0x409470  xor     edx, edx
0x409472  inc     edx
0x409473  call    _SHFusionInitializeFromModuleID@8; SHFusionInitializeFromModuleID(x,x)
0x409478  test    eax, eax
0x40947a  jz      short loc_4094E4
0x40947c  push    esi; pReserved3
0x40947d  push    esi; dwCapabilities
0x40947e  push    esi; pAuthList
0x40947f  push    3; dwImpLevel
0x409481  push    2; dwAuthnLevel
0x409483  push    esi; pReserved1
0x409484  push    esi; asAuthSvc
0x409485  or      edi, 0FFFFFFFFh
0x409488  push    edi; cAuthSvc
0x409489  push    esi; pSecDesc
0x40948a  call    ds:__imp__CoInitializeSecurity@36; CoInitializeSecurity(x,x,x,x,x,x,x,x,x)
0x409490  mov     ebx, eax
0x409492  test    ebx, ebx
0x409494  js      short loc_4094BF
0x409496  call    ?RegisterClassFactory@@YGJXZ; RegisterClassFactory(void)
0x40949b  mov     ebx, eax
0x40949d  test    ebx, ebx
0x40949f  js      short loc_4094BF
0x4094a1  call    ?IESetProcessDPIAware@@YGHXZ; IESetProcessDPIAware(void)
0x4094a6  call    ?CleanupTempDirs@@YGJXZ; CleanupTempDirs(void)
0x4094ab  push    edi; dwMilliseconds
0x4094ac  push    ?g_hQuitEvent@@3PAXA; hHandle
0x4094b2  mov     ebx, eax
0x4094b4  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x4094ba  call    ?RevokeClassFactory@@YGJXZ; RevokeClassFactory(void)
0x4094bf  mov     eax, _g_hActCtx
0x4094c4  cmp     eax, edi
0x4094c6  jz      short loc_4094D5
0x4094c8  push    eax; hActCtx
0x4094c9  call    ds:__imp__ReleaseActCtx@4; ReleaseActCtx(x)
0x4094cf  mov     _g_hActCtx, edi
0x4094d5  cmp     hModule, 0
0x4094dc  jz      short loc_4094E4
0x4094de  mov     hModule, edi
0x4094e4  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x4094ea  push    ?g_hQuitEvent@@3PAXA; hObject
0x4094f0  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4094f6  jmp     short loc_40950C
0x4094f8  call    ds:__imp__GetLastError@0; GetLastError()
0x4094fe  movzx   ebx, ax
0x409501  or      ebx, 80070000h
0x409507  test    eax, eax
0x409509  cmovle  ebx, eax
0x40950c  mov     ecx, [ebp+var_4]
0x40950f  mov     eax, ebx
0x409511  pop     edi
0x409512  pop     esi
0x409513  xor     ecx, ebp; StackCookie
0x409515  pop     ebx
0x409516  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40951b  leave
0x40951c  retn    10h
```
