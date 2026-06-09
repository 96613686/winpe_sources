# WSManHttpListener::Initialize(ulong,CSoapProcessor *,int)

- ea: `0x18016ccdc`
- end: `0x18016d434`
- name: `?Initialize@WSManHttpListener@@QEAAKKPEAVCSoapProcessor@@H@Z`
- size: `1880`
- prototype: `unsigned int __fastcall(WSManHttpListener *__hidden this, unsigned int, struct CSoapProcessor *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801717c8`

## callees

- `0x180026e80`
- `0x18002dd80`
- `0x18005c09c`
- `0x1800621e0`
- `0x1800bac30`
- `0x1800d5b00`
- `0x1800d7a88`
- `0x1800f8630`
- `0x18010a174`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x18016ccdc`
- `0x18016fd4c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016cec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016cec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016d243`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18016d1f1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18016d1f1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18016d278`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18016d278`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016ce0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016ce64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016ce0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016ce64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016cdbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016cdbc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18016d286`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18016d286`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18016d196`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18016d196`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18016d238`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18016d238`
- `SspiCli!FreeContextBuffer` at `0x18016d0ab`
- `SspiCli!FreeContextBuffer` at `0x18016d0ab`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18016d08e`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18016d08e`
- `SspiCli!AcquireCredentialsHandleW` at `0x18016d036`
- `SspiCli!AcquireCredentialsHandleW` at `0x18016d036`
- `HTTPAPI!HttpCreateHttpHandle` at `0x18016d129`
- `HTTPAPI!HttpCreateHttpHandle` at `0x18016d129`
- `HTTPAPI!HttpInitialize` at `0x18016d0c0`
- `HTTPAPI!HttpInitialize` at `0x18016d0c0`

## string_xrefs

- `0x18016cdae`: `System\CurrentControlSet\Services\HTTP\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WSManHttpListener::Initialize(WSManHttpListener *this, int a2, struct CSoapProcessor *a3, int a4)
{
  unsigned int v8; // eax
  unsigned int ErrorCode; // ebx
  LSTATUS v10; // eax
  bool v11; // zf
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD LastError; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  SECURITY_STATUS v20; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  PSecPkgInfoW v23; // rcx
  ULONG HttpHandle; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  PTP_IO ThreadpoolIo; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD v29; // eax
  unsigned int v30; // eax
  HTTPAPI_VERSION Version[2]; // [rsp+50h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-51h] BYREF
  void **v34; // [rsp+60h] [rbp-49h] BYREF
  signed __int32 v35[4]; // [rsp+68h] [rbp-41h] BYREF
  char v36; // [rsp+78h] [rbp-31h]
  const wchar_t *v37; // [rsp+80h] [rbp-29h]
  const wchar_t *v38; // [rsp+88h] [rbp-21h]
  const wchar_t *v39; // [rsp+90h] [rbp-19h]
  const wchar_t *v40; // [rsp+98h] [rbp-11h]
  PSecPkgInfoW ppPackageInfo; // [rsp+A0h] [rbp-9h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+A8h] [rbp-1h] BYREF
  HTTPAPI_VERSION *v43; // [rsp+B0h] [rbp+7h]
  __int64 v44; // [rsp+B8h] [rbp+Fh]
  int Data; // [rsp+110h] [rbp+67h] BYREF
  DWORD Type; // [rsp+118h] [rbp+6Fh] BYREF
  int v47; // [rsp+120h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+128h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  *((_DWORD *)this + 34) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_DWORD *)this + 43) = a4;
  v8 = IsDomainJoined(0, (int *)this + 33);
  ErrorCode = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v8);
    return ErrorCode;
  }
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\HTTP\\Parameters", 0, 0x20119u, &hKey);
  ErrorCode = v10;
  if ( v10 )
  {
    if ( v10 == 2 )
      goto LABEL_22;
    v11 = v10 == 161;
    goto LABEL_18;
  }
  Data = 0;
  cbData = 4;
  Type = 4;
  v12 = RegQueryValueExW(hKey, L"MaxRequestBytes", 0, &Type, (LPBYTE)&Data, &cbData);
  ErrorCode = v12;
  if ( v12 )
  {
    if ( v12 != 2 )
      goto LABEL_102;
  }
  else
  {
    if ( Type != 4 )
      goto LABEL_101;
    *((_DWORD *)this + 231) = Data;
  }
  v47 = 0;
  cbData = 4;
  Type = 4;
  v13 = RegQueryValueExW(hKey, L"MaxFieldLength", 0, &Type, (LPBYTE)&v47, &cbData);
  ErrorCode = v13;
  if ( !v13 )
  {
    if ( Type == 4 )
    {
      *((_DWORD *)this + 232) = v47;
      goto LABEL_22;
    }
LABEL_101:
    ErrorCode = -2144108539;
    goto LABEL_102;
  }
  v11 = v13 == 2;
LABEL_18:
  if ( !v11 )
    goto LABEL_102;
LABEL_22:
  if ( !(unsigned int)CWSManCriticalSection::IsValid((WSManHttpListener *)((char *)this + 176)) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_27;
    v15 = 28;
LABEL_26:
    WPP_SF_(v14[2], v15, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
LABEL_27:
    LastError = GetLastError();
LABEL_28:
    ErrorCode = LastError;
LABEL_102:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
    return ErrorCode;
  }
  if ( !(unsigned int)CWSManCriticalSection::IsValid((WSManHttpListener *)((char *)this + 984)) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_27;
    v15 = 29;
    goto LABEL_26;
  }
  if ( !(unsigned int)CWSManCriticalSection::IsValid((WSManHttpListener *)((char *)this + 320)) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_27;
    v15 = 30;
    goto LABEL_26;
  }
  v35[0] = 0;
  v34 = &CErrorContext::`vftable';
  v35[2] = 0;
  v35[3] = -1;
  v37 = &Class;
  v38 = &Class;
  v39 = &Class;
  v40 = &Class;
  v36 = 1;
  _InterlockedAdd(v35, 1u);
  if ( !(**((unsigned __int8 (__fastcall ***)(char *, void ***))this + 59))((char *)this + 472, &v34)
    || !(**((unsigned __int8 (__fastcall ***)(char *, void ***))this + 47))((char *)this + 376, &v34) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v34);
    goto LABEL_58;
  }
  Version[0] = 0;
  v43 = Version;
  v17 = WSManMemory::Alloc(24, 0, 0);
  v44 = v17;
  if ( v17 )
    v18 = SafeMap_Iterator<StringKeyCI,unsigned long>::SafeMap_Iterator<StringKeyCI,unsigned long>(
            v17,
            (char *)this + 472,
            0);
  else
    v18 = 0;
  AutoCleanup<AutoDelete<SafeSet_Iterator<ListenerSourceSubscription *>>,SafeSet_Iterator<ListenerSourceSubscription *> *>::operator=(
    (char *)this + 568,
    v18);
  v19 = *((_QWORD *)this + 71);
  if ( !v19 || !*(_QWORD *)(v19 + 16) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    v34 = &ILifeTimeMgmt::`vftable';
    ErrorCode = 14;
    goto LABEL_102;
  }
  ppPackageInfo = 0;
  ptsExpiry.QuadPart = 0;
  v20 = AcquireCredentialsHandleW(
          0,
          (LPWSTR)L"Negotiate",
          1u,
          0,
          0,
          0,
          0,
          (PCredHandle)((char *)this + 248),
          &ptsExpiry);
  if ( v20 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_49;
    v22 = 33;
LABEL_48:
    WPP_SF_d(v21[2], v22, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, (unsigned int)v20);
LABEL_49:
    LastError = SecurityStatusToWin32(v20);
LABEL_50:
    v34 = &ILifeTimeMgmt::`vftable';
    goto LABEL_28;
  }
  v20 = QuerySecurityPackageInfoW((LPWSTR)L"Negotiate", &ppPackageInfo);
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_49;
    v22 = 34;
    goto LABEL_48;
  }
  v23 = ppPackageInfo;
  *((_DWORD *)this + 66) = ppPackageInfo->cbMaxToken;
  FreeContextBuffer(v23);
  Version[0] = (HTTPAPI_VERSION)1;
  HttpHandle = HttpInitialize((HTTPAPI_VERSION)1, 1u, 0);
  ErrorCode = HttpHandle;
  if ( HttpHandle )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_57;
    v26 = 38;
LABEL_56:
    WPP_SF_d(v25[2], v26, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, HttpHandle);
LABEL_57:
    (*(void (__fastcall **)(WSManHttpListener *))(*(_QWORD *)this + 24LL))(this);
    WSManHttpListener::DeInitialize(this);
LABEL_58:
    v34 = &ILifeTimeMgmt::`vftable';
    goto LABEL_102;
  }
  *((_DWORD *)this + 32) = 1;
  HttpHandle = HttpCreateHttpHandle((PHANDLE)this + 3, 0);
  ErrorCode = HttpHandle;
  if ( HttpHandle )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_57;
    v26 = 39;
    goto LABEL_56;
  }
  *((_DWORD *)this + 12) = 3;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 27) = 1;
  *((_DWORD *)this + 28) = 72;
  *((_DWORD *)this + 26) = 1;
  ThreadpoolIo = CreateThreadpoolIo(
                   *((HANDLE *)this + 3),
                   WSManHttpListener::_HttpIoCallback,
                   this,
                   (PTP_CALLBACK_ENVIRON)((char *)this + 48));
  *((_QWORD *)this + 15) = ThreadpoolIo;
  if ( !ThreadpoolIo )
  {
    HttpHandle = GetLastError();
    ErrorCode = HttpHandle;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_57;
    v26 = 40;
    goto LABEL_56;
  }
  if ( *((_DWORD *)this + 33) )
  {
    *(_QWORD *)&Version[0].HttpApiMajorVersion = 0;
    if ( !GetModuleHandleExW(4u, (LPCWSTR)WSManHttpListener::_CreateWsmanSpn, (HMODULE *)Version) )
    {
      HttpHandle = GetLastError();
      ErrorCode = HttpHandle;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_57;
      v26 = 41;
      goto LABEL_56;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       WSManHttpListener::_CreateWsmanSpn,
                       *(PVOID *)&Version[0].HttpApiMajorVersion,
                       0);
    if ( !ThreadpoolWork )
    {
      v29 = GetLastError();
      ErrorCode = v29;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v29);
      FreeLibrary(*(HMODULE *)&Version[0].HttpApiMajorVersion);
      goto LABEL_57;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  }
  if ( !(**((unsigned __int8 (__fastcall ***)(char *, void ***))this + 117))((char *)this + 936, &v34) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v30 = CErrorContext::GetErrorCode((CErrorContext *)&v34);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v30);
    }
    (*(void (__fastcall **)(WSManHttpListener *))(*(_QWORD *)this + 24LL))(this);
    WSManHttpListener::DeInitialize(this);
    LastError = CErrorContext::GetErrorCode((CErrorContext *)&v34);
    goto LABEL_50;
  }
  WSManSafeClientList::Startup((WSManHttpListener *)((char *)this + 640));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  v34 = &ILifeTimeMgmt::`vftable';
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18016ccdc  push    rbp
0x18016ccde  push    rbx
0x18016ccdf  push    rsi
0x18016cce0  push    rdi
0x18016cce1  push    r12
0x18016cce3  push    r13
0x18016cce5  push    r14
0x18016cce7  push    r15
0x18016cce9  lea     rbp, [rsp-1Fh]
0x18016ccee  sub     rsp, 0C8h
0x18016ccf5  mov     ebx, r9d
0x18016ccf8  mov     rsi, r8
0x18016ccfb  mov     r14d, edx
0x18016ccfe  mov     rdi, rcx
0x18016cd01  lea     r12, WPP_GLOBAL_Control
0x18016cd08  lea     r13, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18016cd0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18016cd16  cmp     rcx, r12
0x18016cd19  jz      short loc_18016CD38
0x18016cd1b  test    dword ptr [rcx+1Ch], 400h
0x18016cd22  jz      short loc_18016CD38
0x18016cd24  mov     edx, 1Ah
0x18016cd29  mov     r9, rdi
0x18016cd2c  mov     r8, r13
0x18016cd2f  mov     rcx, [rcx+10h]
0x18016cd33  call    WPP_SF_q
0x18016cd38  mov     [rdi+88h], r14d
0x18016cd3f  mov     [rdi+10h], rsi
0x18016cd43  mov     [rdi+0ACh], ebx
0x18016cd49  lea     r14, [rdi+84h]
0x18016cd50  mov     rdx, r14; int *
0x18016cd53  xor     ecx, ecx; struct IRequestContext *
0x18016cd55  call    ?IsDomainJoined@@YAKPEAVIRequestContext@@PEAH@Z; IsDomainJoined(IRequestContext *,int *)
0x18016cd5a  mov     ebx, eax
0x18016cd5c  xor     r15d, r15d
0x18016cd5f  test    eax, eax
0x18016cd61  jz      short loc_18016CD98
0x18016cd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18016cd6a  cmp     rcx, r12
0x18016cd6d  jz      loc_18016D41E
0x18016cd73  test    dword ptr [rcx+1Ch], 200h
0x18016cd7a  jz      loc_18016D41E
0x18016cd80  lea     edx, [r15+1Bh]
0x18016cd84  mov     r9d, eax
0x18016cd87  mov     r8, r13
0x18016cd8a  mov     rcx, [rcx+10h]
0x18016cd8e  call    WPP_SF_d
0x18016cd93  jmp     loc_18016D41E
0x18016cd98  mov     [rbp+57h+hKey], r15
0x18016cd9c  lea     rax, [rbp+57h+hKey]
0x18016cda0  mov     [rsp+100h+phkResult], rax; phkResult
0x18016cda5  mov     r9d, 20119h; samDesired
0x18016cdab  xor     r8d, r8d; ulOptions
0x18016cdae  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\HT"...
0x18016cdb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18016cdbc  call    cs:__imp_RegOpenKeyExW
0x18016cdc2  mov     ebx, eax
0x18016cdc4  mov     esi, 4
0x18016cdc9  test    eax, eax
0x18016cdcb  jz      short loc_18016CDE0
0x18016cdcd  cmp     eax, 2
0x18016cdd0  jz      loc_18016CE8C
0x18016cdd6  cmp     eax, 0A1h
0x18016cddb  jmp     loc_18016CE73
0x18016cde0  mov     [rbp+57h+Data], r15d
0x18016cde4  mov     [rbp+57h+cbData], esi
0x18016cde7  mov     [rbp+57h+Type], esi
0x18016cdea  lea     rax, [rbp+57h+cbData]
0x18016cdee  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18016cdf3  lea     rax, [rbp+57h+Data]
0x18016cdf7  mov     [rsp+100h+phkResult], rax; lpData
0x18016cdfc  lea     r9, [rbp+57h+Type]; lpType
0x18016ce00  xor     r8d, r8d; lpReserved
0x18016ce03  lea     rdx, aMaxrequestbyte; "MaxRequestBytes"
0x18016ce0a  mov     rcx, [rbp+57h+hKey]; hKey
0x18016ce0e  call    cs:__imp_RegQueryValueExW
0x18016ce14  mov     ebx, eax
0x18016ce16  test    eax, eax
0x18016ce18  jz      short loc_18016CE24
0x18016ce1a  cmp     eax, 2
0x18016ce1d  jz      short loc_18016CE36
0x18016ce1f  jmp     loc_18016D415
0x18016ce24  cmp     [rbp+57h+Type], esi
0x18016ce27  jnz     loc_18016D410
0x18016ce2d  mov     eax, [rbp+57h+Data]
0x18016ce30  mov     [rdi+39Ch], eax
0x18016ce36  mov     [rbp+57h+arg_10], r15d
0x18016ce3a  mov     [rbp+57h+cbData], esi
0x18016ce3d  mov     [rbp+57h+Type], esi
0x18016ce40  lea     rax, [rbp+57h+cbData]
0x18016ce44  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18016ce49  lea     rax, [rbp+57h+arg_10]
0x18016ce4d  mov     [rsp+100h+phkResult], rax; lpData
0x18016ce52  lea     r9, [rbp+57h+Type]; lpType
0x18016ce56  xor     r8d, r8d; lpReserved
0x18016ce59  lea     rdx, aMaxfieldlength; "MaxFieldLength"
0x18016ce60  mov     rcx, [rbp+57h+hKey]; hKey
0x18016ce64  call    cs:__imp_RegQueryValueExW
0x18016ce6a  mov     ebx, eax
0x18016ce6c  test    eax, eax
0x18016ce6e  jz      short loc_18016CE7A
0x18016ce70  cmp     eax, 2
0x18016ce73  jz      short loc_18016CE8C
0x18016ce75  jmp     loc_18016D415
0x18016ce7a  cmp     [rbp+57h+Type], esi
0x18016ce7d  jnz     loc_18016D410
0x18016ce83  mov     eax, [rbp+57h+arg_10]
0x18016ce86  mov     [rdi+3A0h], eax
0x18016ce8c  lea     rcx, [rdi+0B0h]; this
0x18016ce93  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x18016ce98  test    eax, eax
0x18016ce9a  jnz     short loc_18016CECD
0x18016ce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18016cea3  cmp     rcx, r12
0x18016cea6  jz      short loc_18016CEC0
0x18016cea8  test    dword ptr [rcx+1Ch], 200h
0x18016ceaf  jz      short loc_18016CEC0
0x18016ceb1  lea     edx, [rax+1Ch]
0x18016ceb4  mov     r8, r13
0x18016ceb7  mov     rcx, [rcx+10h]
0x18016cebb  call    WPP_SF_
0x18016cec0  call    cs:__imp_GetLastError
0x18016cec6  mov     ebx, eax
0x18016cec8  jmp     loc_18016D415
0x18016cecd  lea     rcx, [rdi+3D8h]; this
0x18016ced4  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x18016ced9  test    eax, eax
0x18016cedb  jnz     short loc_18016CEF7
0x18016cedd  mov     rcx, cs:WPP_GLOBAL_Control
0x18016cee4  cmp     rcx, r12
0x18016cee7  jz      short loc_18016CEC0
0x18016cee9  test    dword ptr [rcx+1Ch], 200h
0x18016cef0  jz      short loc_18016CEC0
0x18016cef2  lea     edx, [rax+1Dh]
0x18016cef5  jmp     short loc_18016CEB4
0x18016cef7  lea     rcx, [rdi+140h]; this
0x18016cefe  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x18016cf03  test    eax, eax
0x18016cf05  jnz     short loc_18016CF21
0x18016cf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18016cf0e  cmp     rcx, r12
0x18016cf11  jz      short loc_18016CEC0
0x18016cf13  test    dword ptr [rcx+1Ch], 200h
0x18016cf1a  jz      short loc_18016CEC0
0x18016cf1c  lea     edx, [rax+1Eh]
0x18016cf1f  jmp     short loc_18016CEB4
0x18016cf21  mov     [rbp+57h+var_98], r15d
0x18016cf25  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x18016cf2c  mov     [rbp+57h+var_A0], rax
0x18016cf30  mov     [rbp+57h+var_90], r15d
0x18016cf34  mov     [rbp+57h+var_8C], 0FFFFFFFFh
0x18016cf3b  lea     rax, Class
0x18016cf42  mov     [rbp+57h+var_80], rax
0x18016cf46  mov     [rbp+57h+var_78], rax
0x18016cf4a  mov     [rbp+57h+var_70], rax
0x18016cf4e  mov     [rbp+57h+var_68], rax
0x18016cf52  mov     esi, 1
0x18016cf57  mov     [rbp+57h+var_88], sil
0x18016cf5b  lock add [rbp+57h+var_98], esi
0x18016cf5f  lea     rbx, [rdi+1D8h]
0x18016cf66  mov     rax, [rbx]
0x18016cf69  lea     rdx, [rbp+57h+var_A0]
0x18016cf6d  mov     rcx, rbx
0x18016cf70  mov     rax, [rax]
0x18016cf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cf78  test    al, al
0x18016cf7a  jz      loc_18016D3DA
0x18016cf80  lea     rcx, [rdi+178h]
0x18016cf87  mov     rax, [rcx]
0x18016cf8a  lea     rdx, [rbp+57h+var_A0]
0x18016cf8e  mov     rax, [rax]
0x18016cf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cf96  test    al, al
0x18016cf98  jz      loc_18016D3DA
0x18016cf9e  mov     dword ptr [rbp+57h+Version.HttpApiMajorVersion], r15d
0x18016cfa2  lea     rax, [rbp+57h+Version]
0x18016cfa6  mov     [rbp+57h+var_50], rax
0x18016cfaa  xor     r8d, r8d
0x18016cfad  xor     edx, edx
0x18016cfaf  lea     ecx, [rsi+17h]
0x18016cfb2  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18016cfb7  mov     [rbp+57h+var_48], rax
0x18016cfbb  test    rax, rax
0x18016cfbe  jz      short loc_18016CFD0
0x18016cfc0  xor     r8d, r8d
0x18016cfc3  mov     rdx, rbx
0x18016cfc6  mov     rcx, rax
0x18016cfc9  call    ??0?$SafeMap_Iterator@VStringKeyCI@@K@@QEAA@AEAV?$SafeMap@VStringKeyCI@@KV?$SafeMap_Iterator@VStringKeyCI@@K@@@@_N@Z; SafeMap_Iterator<StringKeyCI,ulong>::SafeMap_Iterator<StringKeyCI,ulong>(SafeMap<StringKeyCI,ulong,SafeMap_Iterator<StringKeyCI,ulong>> &,bool)
0x18016cfce  jmp     short loc_18016CFD3
0x18016cfd0  mov     rax, r15
0x18016cfd3  lea     rbx, [rdi+238h]
0x18016cfda  mov     rdx, rax
0x18016cfdd  mov     rcx, rbx
0x18016cfe0  call    ??4?$AutoCleanup@V?$AutoDelete@V?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@PEAV?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@QEAAAEAV?$AutoDelete@V?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@PEAV?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@Z; AutoCleanup<AutoDelete<SafeSet_Iterator<ListenerSourceSubscription *>>,SafeSet_Iterator<ListenerSourceSubscription *> *>::operator=(SafeSet_Iterator<ListenerSourceSubscription *> *)
0x18016cfe5  mov     rax, [rbx]
0x18016cfe8  test    rax, rax
0x18016cfeb  jz      loc_18016D3A1
0x18016cff1  cmp     [rax+10h], r15
0x18016cff5  jz      loc_18016D3A1
0x18016cffb  mov     [rbp+57h+ppPackageInfo], r15
0x18016cfff  mov     qword ptr [rbp+57h+var_58], r15
0x18016d003  lea     rax, [rdi+0F8h]
0x18016d00a  lea     rcx, [rbp+57h+var_58]
0x18016d00e  mov     [rsp+100h+ptsExpiry], rcx; ptsExpiry
0x18016d013  mov     [rsp+100h+phCredential], rax; phCredential
0x18016d018  mov     [rsp+100h+pvGetKeyArgument], r15; pvGetKeyArgument
0x18016d01d  mov     [rsp+100h+lpcbData], r15; pGetKeyFn
0x18016d022  mov     [rsp+100h+phkResult], r15; pAuthData
0x18016d027  xor     r9d, r9d; pvLogonId
0x18016d02a  mov     r8d, esi; fCredentialUse
0x18016d02d  lea     rdx, pszPackageName; "Negotiate"
0x18016d034  xor     ecx, ecx; pszPrincipal
0x18016d036  call    cs:__imp_AcquireCredentialsHandleW
0x18016d03c  mov     ebx, eax
0x18016d03e  test    eax, eax
0x18016d040  jz      short loc_18016D083
0x18016d042  mov     rcx, cs:WPP_GLOBAL_Control
0x18016d049  cmp     rcx, r12
0x18016d04c  jz      short loc_18016D06B
0x18016d04e  test    dword ptr [rcx+1Ch], 200h
0x18016d055  jz      short loc_18016D06B
0x18016d057  mov     edx, 21h ; '!'
0x18016d05c  mov     r9d, ebx
0x18016d05f  mov     r8, r13
0x18016d062  mov     rcx, [rcx+10h]
0x18016d066  call    WPP_SF_d
0x18016d06b  mov     ecx, ebx; int
0x18016d06d  call    ?SecurityStatusToWin32@@YAKJ@Z; SecurityStatusToWin32(long)
0x18016d072  nop
0x18016d073  lea     rcx, ??_7ILifeTimeMgmt@@6B@; const ILifeTimeMgmt::`vftable'
0x18016d07a  mov     [rbp+57h+var_A0], rcx
0x18016d07e  jmp     loc_18016CEC6
0x18016d083  lea     rdx, [rbp+57h+ppPackageInfo]; ppPackageInfo
0x18016d087  lea     rcx, pszPackageName; "Negotiate"
0x18016d08e  call    cs:__imp_QuerySecurityPackageInfoW
0x18016d094  mov     ebx, eax
0x18016d096  test    eax, eax
0x18016d098  js      loc_18016D37A
0x18016d09e  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x18016d0a2  mov     eax, [rcx+8]
0x18016d0a5  mov     [rdi+108h], eax
0x18016d0ab  call    cs:__imp_FreeContextBuffer
0x18016d0b1  mov     dword ptr [rbp+57h+Version.HttpApiMajorVersion], 1
0x18016d0b8  xor     r8d, r8d; pReserved
0x18016d0bb  mov     edx, esi; Flags
0x18016d0bd  mov     ecx, dword ptr [rbp+57h+Version.HttpApiMajorVersion]; Version
0x18016d0c0  call    cs:__imp_HttpInitialize
0x18016d0c6  mov     ebx, eax
0x18016d0c8  test    eax, eax
0x18016d0ca  jz      short loc_18016D11D
0x18016d0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18016d0d3  cmp     rcx, r12
0x18016d0d6  jz      short loc_18016D0F5
0x18016d0d8  test    dword ptr [rcx+1Ch], 200h
0x18016d0df  jz      short loc_18016D0F5
0x18016d0e1  mov     edx, 26h ; '&'
0x18016d0e6  mov     r9d, eax
0x18016d0e9  mov     r8, r13
0x18016d0ec  mov     rcx, [rcx+10h]
0x18016d0f0  call    WPP_SF_d
0x18016d0f5  mov     rax, [rdi]
0x18016d0f8  mov     rcx, rdi
0x18016d0fb  mov     rax, [rax+18h]
0x18016d0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d104  mov     rcx, rdi; this
0x18016d107  call    ?DeInitialize@WSManHttpListener@@QEAAKXZ; WSManHttpListener::DeInitialize(void)
0x18016d10c  nop
0x18016d10d  lea     rcx, ??_7ILifeTimeMgmt@@6B@; const ILifeTimeMgmt::`vftable'
0x18016d114  mov     [rbp+57h+var_A0], rcx
0x18016d118  jmp     loc_18016D415
0x18016d11d  mov     [rdi+80h], esi
0x18016d123  xor     edx, edx; Reserved
0x18016d125  lea     rcx, [rdi+18h]; RequestQueueHandle
0x18016d129  call    cs:__imp_HttpCreateHttpHandle
0x18016d12f  mov     ebx, eax
0x18016d131  test    eax, eax
0x18016d133  jz      short loc_18016D151
0x18016d135  mov     rcx, cs:WPP_GLOBAL_Control
0x18016d13c  cmp     rcx, r12
0x18016d13f  jz      short loc_18016D0F5
0x18016d141  test    dword ptr [rcx+1Ch], 200h
0x18016d148  jz      short loc_18016D0F5
0x18016d14a  mov     edx, 27h ; '''
0x18016d14f  jmp     short loc_18016D0E6
0x18016d151  lea     r9, [rdi+30h]; pcbe
0x18016d155  mov     dword ptr [r9], 3
0x18016d15c  mov     [r9+8], r15
0x18016d160  mov     [r9+10h], r15
0x18016d164  mov     [r9+18h], r15
0x18016d168  mov     [r9+20h], r15
0x18016d16c  mov     [r9+28h], r15
0x18016d170  mov     [r9+30h], r15
0x18016d174  mov     eax, 1
0x18016d179  mov     [r9+3Ch], eax
0x18016d17d  mov     dword ptr [r9+40h], 48h ; 'H'
0x18016d185  mov     [rdi+68h], eax
0x18016d188  mov     r8, rdi; pv
0x18016d18b  lea     rdx, ?_HttpIoCallback@WSManHttpListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18016d192  mov     rcx, [rdi+18h]; fl
0x18016d196  call    cs:__imp_CreateThreadpoolIo
  ... truncated ...
```
