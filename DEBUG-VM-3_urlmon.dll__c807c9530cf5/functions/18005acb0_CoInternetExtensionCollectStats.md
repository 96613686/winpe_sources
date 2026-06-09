# CoInternetExtensionCollectStats

- ea: `0x18005acb0`
- end: `0x18005afd0`
- name: `CoInternetExtensionCollectStats`
- size: `800`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005ab50`
- `0x1800caf48`

## callees

- `0x180001f94`
- `0x18002d6f0`
- `0x18005acb0`
- `0x180083498`
- `0x18008c6a4`
- `0x180091fb4`
- `0x1800923a0`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18005ae6c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18005af64`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18005ae6c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18005af64`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18005ace3`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18005acff`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18005ace3`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18005acff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ada8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ada8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005addd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ae1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005aefa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005addd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ae1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005aefa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005afb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005afb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005aece`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005aece`

## pseudocode

```c
LSTATUS __fastcall CoInternetExtensionCollectStats(struct _GUID *a1, unsigned int a2, int a3)
{
  struct ILegacyBrowsingEnvironment *v5; // rax
  struct ILegacyBrowsingEnvironment *LegacyBrowsingEnvironment; // rax
  LSTATUS result; // eax
  unsigned __int64 v8; // r8
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  char v15[8]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  BYTE v20[4]; // [rsp+74h] [rbp-8Ch] BYREF
  struct _GUID *v21; // [rsp+78h] [rbp-88h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v22; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *CLSID; // [rsp+88h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  *(_DWORD *)Data = a3;
  if ( (a2 & 2) != 0
    || (v5 = GetLegacyBrowsingEnvironment(),
        !(*(unsigned __int8 (__fastcall **)(struct ILegacyBrowsingEnvironment *))(*(_QWORD *)v5 + 120LL))(v5)) )
  {
    hKey = 0;
    dwDisposition = 0;
    *(_DWORD *)v20 = 0;
    result = CoInternetIsFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u);
    if ( result != 1 )
    {
      result = Ext_GetStatsKey(a1, SubKey, v8);
      if ( result >= 0 )
      {
        result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
        if ( !result )
        {
          RegSetValueExW(hKey, L"Type", 0, 4u, Data, 4u);
          if ( dwDisposition == 1 )
          {
            *(_DWORD *)v20 = 0;
            RegSetValueExW(hKey, L"Flags", 0, 4u, v20, 4u);
            if ( (unsigned int)dword_180159000 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_180159000, 0x400000000000LL) )
              {
                v17 = *(_DWORD *)Data;
                v21 = a1;
                v15[0] = 1;
                v22 = GlobalThreadState();
                CLSID = (struct _GUID *)IEConfiguration_GetCLSID(268435459);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                  v9,
                  (unsigned int)&unk_180145ED7,
                  v10,
                  v11,
                  (__int64)&CLSID,
                  (__int64)&v22,
                  (__int64)v15,
                  (__int64)&v17,
                  (__int64)&v21);
              }
            }
          }
          IncrementRegDword(hKey, L"Count");
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          RegSetValueExW(hKey, L"Time", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
          if ( (a2 & 1) != 0 )
          {
            if ( (unsigned int)dword_180159000 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_180159000, 0x400000000000LL) )
              {
                v17 = *(_DWORD *)Data;
                CLSID = a1;
                v15[0] = 1;
                v22 = GlobalThreadState();
                v21 = (struct _GUID *)IEConfiguration_GetCLSID(268435459);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                  v12,
                  (unsigned int)&unk_180145F41,
                  v13,
                  v14,
                  (__int64)&v21,
                  (__int64)&v22,
                  (__int64)v15,
                  (__int64)&v17,
                  (__int64)&CLSID);
              }
            }
          }
          else
          {
            IncrementRegDword(hKey, L"Blocked");
          }
          return RegCloseKey(hKey);
        }
      }
    }
  }
  else
  {
    LegacyBrowsingEnvironment = GetLegacyBrowsingEnvironment();
    return (*(__int64 (__fastcall **)(struct ILegacyBrowsingEnvironment *, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)LegacyBrowsingEnvironment + 112LL))(
             LegacyBrowsingEnvironment,
             a1,
             a2,
             *(unsigned int *)Data);
  }
  return result;
}

```

## disassembly

```asm
0x18005acb0  push    rbp
0x18005acb2  push    rbx
0x18005acb3  push    rdi
0x18005acb4  lea     rbp, [rsp-1C0h]
0x18005acbc  sub     rsp, 2C0h
0x18005acc3  mov     rax, cs:__security_cookie
0x18005acca  xor     rax, rsp
0x18005accd  mov     [rbp+1D0h+var_20], rax
0x18005acd4  mov     dword ptr [rsp+2D0h+Data], r8d
0x18005acd9  mov     edi, edx
0x18005acdb  mov     rbx, rcx
0x18005acde  test    dl, 2
0x18005ace1  jnz     short loc_18005AD27
0x18005ace3  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18005ace9  mov     r9, rax
0x18005acec  mov     rcx, [rax]
0x18005acef  mov     rax, [rcx+78h]
0x18005acf3  mov     rcx, r9
0x18005acf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acfb  test    al, al
0x18005acfd  jz      short loc_18005AD27
0x18005acff  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18005ad05  mov     r9d, dword ptr [rsp+2D0h+Data]
0x18005ad0a  mov     r8d, edi
0x18005ad0d  mov     r10, rax
0x18005ad10  mov     rdx, rbx
0x18005ad13  mov     rcx, [rax]
0x18005ad16  mov     rax, [rcx+70h]
0x18005ad1a  mov     rcx, r10
0x18005ad1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad22  jmp     loc_18005AFB6
0x18005ad27  mov     edx, 2; dwFlags
0x18005ad2c  mov     [rsp+2D0h+hKey], 0
0x18005ad35  mov     [rsp+2D0h+dwDisposition], 0
0x18005ad3d  mov     dword ptr [rsp+2D0h+var_25C], 0
0x18005ad45  lea     ecx, [rdx+0Bh]; FeatureEntry
0x18005ad48  call    CoInternetIsFeatureEnabled
0x18005ad4d  cmp     eax, 1
0x18005ad50  jz      loc_18005AFB6
0x18005ad56  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18005ad5a  mov     rcx, rbx; struct _GUID *
0x18005ad5d  call    ?Ext_GetStatsKey@@YAJAEBU_GUID@@PEAG_K@Z; Ext_GetStatsKey(_GUID const &,ushort *,unsigned __int64)
0x18005ad62  test    eax, eax
0x18005ad64  js      loc_18005AFB6
0x18005ad6a  lea     rax, [rsp+2D0h+dwDisposition]
0x18005ad6f  xor     r9d, r9d; lpClass
0x18005ad72  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x18005ad77  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18005ad7b  lea     rax, [rsp+2D0h+hKey]
0x18005ad80  xor     r8d, r8d; Reserved
0x18005ad83  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18005ad88  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005ad8f  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005ad98  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x18005ada0  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x18005ada8  call    cs:__imp_RegCreateKeyExW
0x18005adae  test    eax, eax
0x18005adb0  jnz     loc_18005AFB6
0x18005adb6  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005adbb  lea     rax, [rsp+2D0h+Data]
0x18005adc0  mov     [rsp+2D0h+samDesired], 4; cbData
0x18005adc8  lea     rdx, aType; "Type"
0x18005adcf  mov     r9d, 4; dwType
0x18005add5  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18005adda  xor     r8d, r8d; Reserved
0x18005addd  call    cs:__imp_RegSetValueExW
0x18005ade3  cmp     [rsp+2D0h+dwDisposition], 1
0x18005ade8  jnz     loc_18005AEB2
0x18005adee  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005adf3  lea     rax, [rsp+2D0h+var_25C]
0x18005adf8  mov     [rsp+2D0h+samDesired], 4; cbData
0x18005ae00  lea     rdx, aFlags; "Flags"
0x18005ae07  mov     r9d, 4; dwType
0x18005ae0d  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18005ae12  xor     r8d, r8d; Reserved
0x18005ae15  mov     dword ptr [rsp+2D0h+var_25C], 0
0x18005ae1d  call    cs:__imp_RegSetValueExW
0x18005ae23  mov     eax, cs:dword_180159000
0x18005ae29  cmp     eax, 5
0x18005ae2c  jbe     loc_18005AEB2
0x18005ae32  mov     rdx, 400000000000h
0x18005ae3c  lea     rcx, dword_180159000
0x18005ae43  call    _tlgKeywordOn
0x18005ae48  test    al, al
0x18005ae4a  jz      short loc_18005AEB2
0x18005ae4c  mov     eax, dword ptr [rsp+2D0h+Data]
0x18005ae50  mov     [rsp+2D0h+var_270], eax
0x18005ae54  mov     [rsp+2D0h+var_258], rbx
0x18005ae59  mov     [rsp+2D0h+var_280], 1
0x18005ae5e  call    ?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18005ae63  mov     ecx, 10000003h
0x18005ae68  mov     [rbp+1D0h+var_250], rax
0x18005ae6c  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18005ae72  mov     [rbp+1D0h+var_248], rax
0x18005ae76  lea     rdx, unk_180145ED7
0x18005ae7d  lea     rax, [rsp+2D0h+var_258]
0x18005ae82  mov     [rsp+2D0h+lpdwDisposition], rax
0x18005ae87  lea     rax, [rsp+2D0h+var_270]
0x18005ae8c  mov     [rsp+2D0h+phkResult], rax
0x18005ae91  lea     rax, [rsp+2D0h+var_280]
0x18005ae96  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18005ae9b  lea     rax, [rbp+1D0h+var_250]
0x18005ae9f  mov     qword ptr [rsp+2D0h+samDesired], rax
0x18005aea4  lea     rax, [rbp+1D0h+var_248]
0x18005aea8  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18005aead  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18005aeb2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005aeb7  lea     rdx, aCount; "Count"
0x18005aebe  call    ?IncrementRegDword@@YAXPEAUHKEY__@@PEBG@Z; IncrementRegDword(HKEY__ *,ushort const *)
0x18005aec3  xorps   xmm0, xmm0
0x18005aec6  lea     rcx, [rbp+1D0h+SystemTime]; lpSystemTime
0x18005aeca  movups  xmmword ptr [rbp+1D0h+SystemTime.wYear], xmm0
0x18005aece  call    cs:__imp_GetSystemTime
0x18005aed4  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005aed9  lea     rax, [rbp+1D0h+SystemTime]
0x18005aedd  mov     [rsp+2D0h+samDesired], 10h; cbData
0x18005aee5  lea     rdx, aTime; "Time"
0x18005aeec  mov     r9d, 3; dwType
0x18005aef2  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18005aef7  xor     r8d, r8d; Reserved
0x18005aefa  call    cs:__imp_RegSetValueExW
0x18005af00  test    dil, 1
0x18005af04  jnz     short loc_18005AF1C
0x18005af06  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005af0b  lea     rdx, aBlocked; "Blocked"
0x18005af12  call    ?IncrementRegDword@@YAXPEAUHKEY__@@PEBG@Z; IncrementRegDword(HKEY__ *,ushort const *)
0x18005af17  jmp     loc_18005AFAB
0x18005af1c  mov     eax, cs:dword_180159000
0x18005af22  cmp     eax, 5
0x18005af25  jbe     loc_18005AFAB
0x18005af2b  mov     rdx, 400000000000h
0x18005af35  lea     rcx, dword_180159000
0x18005af3c  call    _tlgKeywordOn
0x18005af41  test    al, al
0x18005af43  jz      short loc_18005AFAB
0x18005af45  mov     eax, dword ptr [rsp+2D0h+Data]
0x18005af49  mov     [rsp+2D0h+var_270], eax
0x18005af4d  mov     [rbp+1D0h+var_248], rbx
0x18005af51  mov     [rsp+2D0h+var_280], 1
0x18005af56  call    ?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18005af5b  mov     ecx, 10000003h
0x18005af60  mov     [rbp+1D0h+var_250], rax
0x18005af64  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18005af6a  mov     [rsp+2D0h+var_258], rax
0x18005af6f  lea     rdx, unk_180145F41
0x18005af76  lea     rax, [rbp+1D0h+var_248]
0x18005af7a  mov     [rsp+2D0h+lpdwDisposition], rax
0x18005af7f  lea     rax, [rsp+2D0h+var_270]
0x18005af84  mov     [rsp+2D0h+phkResult], rax
0x18005af89  lea     rax, [rsp+2D0h+var_280]
0x18005af8e  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18005af93  lea     rax, [rbp+1D0h+var_250]
0x18005af97  mov     qword ptr [rsp+2D0h+samDesired], rax
0x18005af9c  lea     rax, [rsp+2D0h+var_258]
0x18005afa1  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18005afa6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18005afab  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005afb0  call    cs:__imp_RegCloseKey
0x18005afb6  mov     rcx, [rbp+1D0h+var_20]
0x18005afbd  xor     rcx, rsp; StackCookie
0x18005afc0  call    __security_check_cookie
0x18005afc5  add     rsp, 2C0h
0x18005afcc  pop     rdi
0x18005afcd  pop     rbx
0x18005afce  pop     rbp
0x18005afcf  retn
```
