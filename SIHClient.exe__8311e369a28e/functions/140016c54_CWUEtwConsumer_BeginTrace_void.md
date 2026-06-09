# CWUEtwConsumer::BeginTrace(void)

- ea: `0x140016c54`
- end: `0x140017019`
- name: `?BeginTrace@CWUEtwConsumer@@QEAAJXZ`
- size: `965`
- prototype: `__int64 __fastcall(wchar_t *this, __int64, __int64, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140004a7c`

## callees

- `0x1400067c8`
- `0x14000e194`
- `0x14000ee68`
- `0x1400129cc`
- `0x140016268`
- `0x140016c54`
- `0x140017020`
- `0x140017934`
- `0x140017da4`
- `0x140018394`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016fe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016fe1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d8a`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140016f70`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140016fb1`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140016f70`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140016fb1`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140016eaa`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140016ef6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140016eaa`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140016ef6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140016ec7`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140016ec7`

## string_xrefs

- `0x140016d7c`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`

## pseudocode

```c
__int64 __fastcall CWUEtwConsumer::BeginTrace(wchar_t *this, __int64 a2, __int64 a3, wchar_t **a4)
{
  __int64 RegKeyPath; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  wchar_t **v9; // r9
  signed int LogFilenameTemplate; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  UCHAR v13; // r12
  __int64 v14; // rdx
  __int64 v15; // r8
  wchar_t **v16; // r9
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // r15d
  unsigned int v20; // r8d
  __int64 v21; // rdx
  unsigned int *v22; // r9
  __int64 v23; // r9
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  wchar_t v26; // ax
  wchar_t *v27; // rax
  void *v28; // r8
  signed int started; // edi
  __int64 v30; // rbx
  __int64 v31; // r14
  ULONGLONG v32; // rcx
  int v33; // r9d
  bool v34; // zf
  ULONG64 TraceHandle; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t v39[264]; // [rsp+268h] [rbp+160h] BYREF
  wchar_t v40[264]; // [rsp+478h] [rbp+370h] BYREF

  TraceHandle = -1;
  hKey = 0;
  RegKeyPath = GetRegKeyPath(21, a2, a3, a4);
  if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(v6, RegKeyPath, L"WPPLogDisabled", 0) )
  {
    LogFilenameTemplate = -2147020684;
    goto LABEL_38;
  }
  v11 = GetRegKeyPath(21, v7, v8, v9);
  v13 = RegQueryDwordValueWithDefaultAndRangeCheck(v12, v11, L"Level", 4);
  v17 = GetRegKeyPath(21, v14, v15, v16);
  v19 = ~(unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(v18, v17, L"DisabledCategories", 0) & 0x1FFFFFF;
  LogFilenameTemplate = CWUEtwConsumer::GenerateLogFilenameTemplate((CWUEtwConsumer *)this, v40, v20);
  if ( LogFilenameTemplate >= 0 )
  {
    LogFilenameTemplate = GetSusBaseDirectoryW(v39, v21, L"Logs", v22);
    if ( LogFilenameTemplate >= 0 )
    {
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\EditionSettings", 0, 1u, &hKey) )
      {
        RegQueryStringValueWithDefaultAndExpand(hKey, L"LogDir", pszDest, v23, v39);
        goto LABEL_14;
      }
      v24 = 260;
      v25 = pszDest;
      do
      {
        if ( v24 == -2147483386 )
          break;
        v26 = *(wchar_t *)((char *)v25 + (char *)v39 - (char *)pszDest);
        if ( !v26 )
          break;
        *v25++ = v26;
        --v24;
      }
      while ( v24 );
      v27 = v25 - 1;
      if ( v24 )
        v27 = v25;
      *v27 = 0;
      LogFilenameTemplate = v24 == 0 ? 0x8007007A : 0;
      if ( v24 )
      {
LABEL_14:
        LogFilenameTemplate = WUPathCchCombine(pszDest, 0x104u, pszDest, this);
        if ( LogFilenameTemplate < 0 )
          goto LABEL_38;
        LogFilenameTemplate = WUPathCchCombine(pszDest, 0x104u, pszDest, v40);
        if ( LogFilenameTemplate < 0 )
          goto LABEL_38;
        LogFilenameTemplate = CWUEtwConsumer::InitTraceProperties((CWUEtwConsumer *)this, this + 128, pszDest);
        if ( LogFilenameTemplate < 0 )
          goto LABEL_38;
        LogFilenameTemplate = SusMakeDirectoryForFile(this + 616, 0, v28);
        if ( LogFilenameTemplate < 0 )
          goto LABEL_38;
        started = StartTraceW(&TraceHandle, this + 128, (PEVENT_TRACE_PROPERTIES)(this + 296));
        if ( started == 183 )
        {
          started = ControlTraceW(0, this + 128, (PEVENT_TRACE_PROPERTIES)(this + 296), 1u);
          if ( started )
            goto LABEL_36;
          if ( CWUEtwConsumer::InitTraceProperties((CWUEtwConsumer *)this, this + 128, pszDest) < 0 )
            goto LABEL_23;
          started = StartTraceW(&TraceHandle, this + 128, (PEVENT_TRACE_PROPERTIES)(this + 296));
        }
        if ( started )
          goto LABEL_36;
LABEL_23:
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::GetImpl'::`2'::impl) )
        {
          v30 = *((_QWORD *)this + 72);
          v31 = v30 + 24LL * *((unsigned int *)this + 147);
          if ( v30 == v31 )
          {
LABEL_35:
            *((_QWORD *)this + 220) = TraceHandle;
LABEL_36:
            LogFilenameTemplate = (unsigned __int16)started | 0x80070000;
            if ( started <= 0 )
              LogFilenameTemplate = started;
            goto LABEL_38;
          }
          do
          {
            if ( !started )
            {
              v32 = v19;
              if ( *(_DWORD *)(v30 + 20) != -1 )
                v32 = *(unsigned int *)(v30 + 20);
              v33 = *(_DWORD *)(v30 + 16);
              if ( v33 == -1 )
                LOBYTE(v33) = v13;
              started = EnableTraceEx2(TraceHandle, (LPCGUID)v30, 1u, v33, v32, 0, 0, 0);
            }
            v30 += 24;
          }
          while ( v30 != v31 );
          v34 = started == 0;
        }
        else
        {
          started = EnableTraceEx2(TraceHandle, (LPCGUID)(this + 274), 1u, v13, v19, 0, 0, 0);
          v34 = started == 0;
        }
        if ( !v34 )
          goto LABEL_36;
        goto LABEL_35;
      }
    }
  }
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)LogFilenameTemplate;
}

```

## disassembly

```asm
0x140016c54  mov     rax, rsp
0x140016c57  mov     [rax+10h], rbx
0x140016c5b  mov     [rax+18h], rsi
0x140016c5f  mov     [rax+20h], rdi
0x140016c63  push    rbp
0x140016c64  push    r12
0x140016c66  push    r13
0x140016c68  push    r14
0x140016c6a  push    r15
0x140016c6c  lea     rbp, [rax-5B8h]
0x140016c73  sub     rsp, 690h
0x140016c7a  mov     rax, cs:__security_cookie
0x140016c81  xor     rax, rsp
0x140016c84  mov     [rbp+5B0h+var_30], rax
0x140016c8b  mov     rsi, rcx
0x140016c8e  mov     [rsp+6B0h+TraceHandle], 0FFFFFFFFFFFFFFFFh
0x140016c97  xor     r13d, r13d
0x140016c9a  mov     [rsp+6B0h+hKey], r13
0x140016c9f  lea     ebx, [r13+15h]
0x140016ca3  mov     ecx, ebx
0x140016ca5  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140016caa  or      edi, 0FFFFFFFFh
0x140016cad  mov     dword ptr [rsp+6B0h+MatchAllKeyword], edi
0x140016cb1  xor     r9d, r9d
0x140016cb4  lea     r8, aWpplogdisabled; "WPPLogDisabled"
0x140016cbb  mov     rdx, rax
0x140016cbe  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140016cc3  test    eax, eax
0x140016cc5  jz      short loc_140016CD1
0x140016cc7  mov     ebx, 80071074h
0x140016ccc  jmp     loc_140016FD7
0x140016cd1  mov     ecx, ebx
0x140016cd3  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140016cd8  mov     dword ptr [rsp+6B0h+MatchAllKeyword], edi
0x140016cdc  mov     r9d, 4
0x140016ce2  lea     r8, aLevel; "Level"
0x140016ce9  mov     rdx, rax
0x140016cec  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140016cf1  mov     r12d, eax
0x140016cf4  mov     ecx, ebx
0x140016cf6  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140016cfb  mov     dword ptr [rsp+6B0h+MatchAllKeyword], edi; int
0x140016cff  xor     r9d, r9d
0x140016d02  lea     r8, aDisabledcatego; "DisabledCategories"
0x140016d09  mov     rdx, rax
0x140016d0c  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140016d11  mov     r15d, eax
0x140016d14  not     r15d
0x140016d17  and     r15d, 1FFFFFFh
0x140016d1e  lea     rdx, [rbp+5B0h+var_240]; wchar_t *
0x140016d25  mov     rcx, rsi; this
0x140016d28  call    ?GenerateLogFilenameTemplate@CWUEtwConsumer@@AEBAJPEA_WI@Z; CWUEtwConsumer::GenerateLogFilenameTemplate(wchar_t *,uint)
0x140016d2d  mov     ebx, eax
0x140016d2f  test    eax, eax
0x140016d31  js      loc_140016FD7
0x140016d37  lea     r8, aLogs; "Logs"
0x140016d3e  lea     rcx, [rbp+5B0h+var_450]; pszDest
0x140016d45  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x140016d4a  mov     ebx, eax
0x140016d4c  test    eax, eax
0x140016d4e  js      loc_140016FD7
0x140016d54  mov     rcx, [rsp+6B0h+hKey]; hKey
0x140016d59  test    rcx, rcx
0x140016d5c  jz      short loc_140016D69
0x140016d5e  call    cs:__imp_RegCloseKey
0x140016d64  mov     [rsp+6B0h+hKey], r13
0x140016d69  lea     rax, [rsp+6B0h+hKey]
0x140016d6e  mov     [rsp+6B0h+phkResult], rax; phkResult
0x140016d73  mov     r9d, 1; samDesired
0x140016d79  xor     r8d, r8d; ulOptions
0x140016d7c  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x140016d83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016d8a  call    cs:__imp_RegOpenKeyExW
0x140016d90  mov     edi, 104h
0x140016d95  test    eax, eax
0x140016d97  jnz     short loc_140016DBD
0x140016d99  lea     rax, [rbp+5B0h+var_450]
0x140016da0  mov     [rsp+6B0h+phkResult], rax; wchar_t *
0x140016da5  lea     r8, [rsp+6B0h+pszDest]; pszDest
0x140016daa  lea     rdx, aLogdir; "LogDir"
0x140016db1  mov     rcx, [rsp+6B0h+hKey]; HKEY
0x140016db6  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x140016dbb  jmp     short loc_140016E1F
0x140016dbd  mov     rdx, rdi
0x140016dc0  lea     rcx, [rsp+6B0h+pszDest]
0x140016dc5  lea     r8, [rbp+5B0h+var_450]
0x140016dcc  lea     rax, [rsp+6B0h+pszDest]
0x140016dd1  sub     r8, rax
0x140016dd4  lea     rax, [rdx+7FFFFEFAh]
0x140016ddb  test    rax, rax
0x140016dde  jz      short loc_140016DF7
0x140016de0  movzx   eax, word ptr [rcx+r8]
0x140016de5  test    ax, ax
0x140016de8  jz      short loc_140016DF7
0x140016dea  mov     [rcx], ax
0x140016ded  add     rcx, 2
0x140016df1  sub     rdx, 1
0x140016df5  jnz     short loc_140016DD4
0x140016df7  lea     rax, [rcx-2]
0x140016dfb  test    rdx, rdx
0x140016dfe  cmovnz  rax, rcx
0x140016e02  mov     [rax], r13w
0x140016e06  mov     rax, rdx
0x140016e09  neg     rax
0x140016e0c  sbb     ebx, ebx
0x140016e0e  not     ebx
0x140016e10  and     ebx, 8007007Ah
0x140016e16  test    rdx, rdx
0x140016e19  jz      loc_140016FD7
0x140016e1f  mov     r9, rsi; wchar_t *
0x140016e22  lea     r8, [rsp+6B0h+pszDest]; wchar_t *
0x140016e27  mov     edx, edi; unsigned int
0x140016e29  lea     rcx, [rsp+6B0h+pszDest]; wchar_t *
0x140016e2e  call    ?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z; WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)
0x140016e33  mov     ebx, eax
0x140016e35  test    eax, eax
0x140016e37  js      loc_140016FD7
0x140016e3d  lea     r9, [rbp+5B0h+var_240]; wchar_t *
0x140016e44  lea     r8, [rsp+6B0h+pszDest]; wchar_t *
0x140016e49  mov     edx, edi; unsigned int
0x140016e4b  lea     rcx, [rsp+6B0h+pszDest]; wchar_t *
0x140016e50  call    ?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z; WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)
0x140016e55  mov     ebx, eax
0x140016e57  test    eax, eax
0x140016e59  js      loc_140016FD7
0x140016e5f  lea     r14, [rsi+100h]
0x140016e66  lea     r8, [rsp+6B0h+pszDest]; wchar_t *
0x140016e6b  mov     rdx, r14; wchar_t *
0x140016e6e  mov     rcx, rsi; this
0x140016e71  call    ?InitTraceProperties@CWUEtwConsumer@@QEAAJPEB_W0@Z; CWUEtwConsumer::InitTraceProperties(wchar_t const *,wchar_t const *)
0x140016e76  mov     ebx, eax
0x140016e78  test    eax, eax
0x140016e7a  js      loc_140016FD7
0x140016e80  lea     rcx, [rsi+4D0h]; wchar_t *
0x140016e87  xor     edx, edx; unsigned int
0x140016e89  call    ?SusMakeDirectoryForFile@@YAJPEB_WKPEAX@Z; SusMakeDirectoryForFile(wchar_t const *,ulong,void *)
0x140016e8e  mov     ebx, eax
0x140016e90  test    eax, eax
0x140016e92  js      loc_140016FD7
0x140016e98  lea     rbx, [rsi+250h]
0x140016e9f  mov     r8, rbx; Properties
0x140016ea2  mov     rdx, r14; InstanceName
0x140016ea5  lea     rcx, [rsp+6B0h+TraceHandle]; TraceHandle
0x140016eaa  call    cs:__imp_StartTraceW
0x140016eb0  mov     edi, eax
0x140016eb2  cmp     eax, 0B7h
0x140016eb7  jnz     short loc_140016EFE
0x140016eb9  mov     r9d, 1; ControlCode
0x140016ebf  mov     r8, rbx; Properties
0x140016ec2  mov     rdx, r14; InstanceName
0x140016ec5  xor     ecx, ecx; TraceHandle
0x140016ec7  call    cs:__imp_ControlTraceW
0x140016ecd  mov     edi, eax
0x140016ecf  test    eax, eax
0x140016ed1  jnz     loc_140016FC9
0x140016ed7  lea     r8, [rsp+6B0h+pszDest]; wchar_t *
0x140016edc  mov     rdx, r14; wchar_t *
0x140016edf  mov     rcx, rsi; this
0x140016ee2  call    ?InitTraceProperties@CWUEtwConsumer@@QEAAJPEB_W0@Z; CWUEtwConsumer::InitTraceProperties(wchar_t const *,wchar_t const *)
0x140016ee7  test    eax, eax
0x140016ee9  js      short loc_140016F06
0x140016eeb  mov     r8, rbx; Properties
0x140016eee  mov     rdx, r14; InstanceName
0x140016ef1  lea     rcx, [rsp+6B0h+TraceHandle]; TraceHandle
0x140016ef6  call    cs:__imp_StartTraceW
0x140016efc  mov     edi, eax
0x140016efe  test    edi, edi
0x140016f00  jnz     loc_140016FC9
0x140016f06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs> `wil::Feature<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::GetImpl(void)'::`2'::impl
0x140016f0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::__private_IsEnabled(void)
0x140016f12  test    al, al
0x140016f14  jz      short loc_140016F85
0x140016f16  mov     rbx, [rsi+240h]
0x140016f1d  mov     eax, [rsi+24Ch]
0x140016f23  lea     rcx, [rax+rax*2]
0x140016f27  lea     r14, [rbx+rcx*8]
0x140016f2b  cmp     rbx, r14
0x140016f2e  jz      loc_140016FBD
0x140016f34  test    edi, edi
0x140016f36  jnz     short loc_140016F78
0x140016f38  mov     ecx, r15d
0x140016f3b  or      edx, 0FFFFFFFFh
0x140016f3e  cmp     [rbx+14h], edx
0x140016f41  cmovnz  ecx, [rbx+14h]
0x140016f45  mov     r9d, [rbx+10h]
0x140016f49  cmp     r9d, edx
0x140016f4c  cmovz   r9d, r12d; Level
0x140016f50  mov     [rsp+6B0h+EnableParameters], r13; EnableParameters
0x140016f55  mov     [rsp+6B0h+Timeout], r13d; Timeout
0x140016f5a  mov     [rsp+6B0h+MatchAllKeyword], r13; MatchAllKeyword
0x140016f5f  mov     [rsp+6B0h+phkResult], rcx; MatchAnyKeyword
0x140016f64  lea     r8d, [rdi+1]; ControlCode
0x140016f68  mov     rdx, rbx; ProviderId
0x140016f6b  mov     rcx, [rsp+6B0h+TraceHandle]; TraceHandle
0x140016f70  call    cs:__imp_EnableTraceEx2
0x140016f76  mov     edi, eax
0x140016f78  add     rbx, 18h
0x140016f7c  cmp     rbx, r14
0x140016f7f  jnz     short loc_140016F34
0x140016f81  test    edi, edi
0x140016f83  jmp     short loc_140016FBB
0x140016f85  mov     eax, r15d
0x140016f88  lea     rdx, [rsi+224h]; ProviderId
0x140016f8f  mov     [rsp+6B0h+EnableParameters], r13; EnableParameters
0x140016f94  mov     [rsp+6B0h+Timeout], r13d; Timeout
0x140016f99  mov     [rsp+6B0h+MatchAllKeyword], r13; MatchAllKeyword
0x140016f9e  mov     [rsp+6B0h+phkResult], rax; MatchAnyKeyword
0x140016fa3  mov     r9b, r12b; Level
0x140016fa6  mov     r8d, 1; ControlCode
0x140016fac  mov     rcx, [rsp+6B0h+TraceHandle]; TraceHandle
0x140016fb1  call    cs:__imp_EnableTraceEx2
0x140016fb7  mov     edi, eax
0x140016fb9  test    eax, eax
0x140016fbb  jnz     short loc_140016FC9
0x140016fbd  mov     rax, [rsp+6B0h+TraceHandle]
0x140016fc2  mov     [rsi+6E0h], rax
0x140016fc9  movzx   ebx, di
0x140016fcc  or      ebx, 80070000h
0x140016fd2  test    edi, edi
0x140016fd4  cmovle  ebx, edi
0x140016fd7  mov     rcx, [rsp+6B0h+hKey]; hKey
0x140016fdc  test    rcx, rcx
0x140016fdf  jz      short loc_140016FE7
0x140016fe1  call    cs:__imp_RegCloseKey
0x140016fe7  mov     eax, ebx
0x140016fe9  mov     rcx, [rbp+5B0h+var_30]
0x140016ff0  xor     rcx, rsp; StackCookie
0x140016ff3  call    __security_check_cookie
0x140016ff8  lea     r11, [rsp+6B0h+var_20]
0x140017000  mov     rbx, [r11+38h]
0x140017004  mov     rsi, [r11+40h]
0x140017008  mov     rdi, [r11+48h]
0x14001700c  mov     rsp, r11
0x14001700f  pop     r15
0x140017011  pop     r14
0x140017013  pop     r13
0x140017015  pop     r12
0x140017017  pop     rbp
0x140017018  retn
```
