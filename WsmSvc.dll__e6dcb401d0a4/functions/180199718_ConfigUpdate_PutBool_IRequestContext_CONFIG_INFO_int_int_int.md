# ConfigUpdate::PutBool(IRequestContext *,_CONFIG_INFO *,int,int,int *)

- ea: `0x180199718`
- end: `0x180199c7f`
- name: `?PutBool@ConfigUpdate@@AEAAHPEAVIRequestContext@@PEAU_CONFIG_INFO@@HHPEAH@Z`
- size: `1383`
- prototype: `__int64 __fastcall(ConfigUpdate *this, struct IRequestContext *, struct _CONFIG_INFO *, int, int, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18019a0b0`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18006b200`
- `0x180101610`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x18011ff54`
- `0x180199718`
- `0x18019b390`
- `0x18019db50`
- `0x18019dbd0`
- `0x1801a0010`
- `0x1801a0710`
- `0x1801b0504`
- `0x1801b06fc`
- `0x1801b2204`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801998c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019992d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801998c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019992d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199a0e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18019986f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18019986f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801998f6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801998f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18019990b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801999db`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801999e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180199a1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180199a27`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18019990b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801999db`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801999e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180199a1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180199a27`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801999ce`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801999ce`

## string_xrefs

- `0x180199770`: `onecore\admin\wmi\wmx\config\configupdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConfigUpdate::PutBool(
        ConfigUpdate *this,
        struct IRequestContext *a2,
        struct _CONFIG_INFO *a3,
        int a4,
        int a5,
        int *a6)
{
  PVOID *v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  SC_HANDLE v13; // rax
  SC_HANDLE v14; // r14
  DWORD LastError; // eax
  __int64 v16; // rdx
  void (__fastcall *v17)(struct IRequestContext *, __int64); // rbx
  __int64 v18; // rdx
  SC_HANDLE v19; // rax
  SC_HANDLE v20; // r15
  DWORD v21; // eax
  const unsigned __int16 *ComputerNameFQDN; // rax
  int v23; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int8 v24[8]; // [rsp+48h] [rbp-81h] BYREF
  int v25; // [rsp+50h] [rbp-79h] BYREF
  int v26; // [rsp+54h] [rbp-75h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-71h] BYREF
  void **v28; // [rsp+60h] [rbp-69h] BYREF
  signed __int32 v29[4]; // [rsp+68h] [rbp-61h] BYREF
  char v30; // [rsp+78h] [rbp-51h]
  const wchar_t *v31; // [rsp+80h] [rbp-49h]
  const wchar_t *v32; // [rsp+88h] [rbp-41h]
  const wchar_t *v33; // [rsp+90h] [rbp-39h]
  const wchar_t *v34; // [rsp+98h] [rbp-31h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+A0h] [rbp-29h] BYREF

  *(_DWORD *)v24 = a4;
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configupdate.cpp", 0xD64u, L"3428", 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configupdate.cpp", 0xD65u, L"3429", 0x54Fu, a2);
    return 0;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, this);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      a4 = *(_DWORD *)v24;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200000) != 0 )
    {
      WPP_SF_Dd(v10[2], 122, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids);
      a4 = *(_DWORD *)v24;
    }
  }
  if ( *(_DWORD *)a3 != 2021 )
    goto LABEL_64;
  if ( !*((_DWORD *)this + 2882) )
  {
    CFirewallManager::CFirewallManager((CFirewallManager *)&v28);
    v11 = CFirewallManager::SwitchException((CFirewallManager *)&v28, *(_DWORD *)v24 != 0);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( v11 != -2147023137 && v11 != -2147023143 )
      {
LABEL_17:
        (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v12);
LABEL_24:
        CFirewallManager::~CFirewallManager((CFirewallManager *)&v28);
        return 0;
      }
      v13 = OpenSCManagerW(0, 0, 0xF003Fu);
      v14 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_23;
        LastError = GetLastError();
        v16 = 123;
LABEL_22:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, LastError);
LABEL_23:
        v17 = *(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL);
        v18 = GetLastError();
        v17(a2, v18);
        goto LABEL_24;
      }
      v19 = OpenServiceW(v13, L"mpssvc", 4u);
      v20 = v19;
      if ( v19 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !QueryServiceStatus(v19, &ServiceStatus) )
        {
          CloseServiceHandle(v20);
          CloseServiceHandle(v14);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
            goto LABEL_23;
          LastError = GetLastError();
          v16 = 125;
          goto LABEL_22;
        }
        CloseServiceHandle(v20);
        CloseServiceHandle(v14);
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids);
          goto LABEL_17;
        }
      }
      else
      {
        CloseServiceHandle(v14);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          v21 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, v21);
        }
      }
    }
    CFirewallManager::~CFirewallManager((CFirewallManager *)&v28);
    a4 = *(_DWORD *)v24;
  }
  if ( *(_DWORD *)a3 == 2021 )
  {
    if ( !a4 || *((_DWORD *)this + 2882) )
      return ConfigUpdate::UpdateRegValue(this, a2, a3, 4u, v24, 4u, a5, a6);
    OnHTTPInitialize::OnHTTPInitialize((OnHTTPInitialize *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 72LL))(a2);
LABEL_35:
      OnHTTPInitialize::~OnHTTPInitialize((OnHTTPInitialize *)&v23);
      return 0;
    }
    if ( !UpdateHttpsBinding(
            a2,
            L"http://+:80/wsman/",
            L"D:(A;;GX;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;;GX;;;S-1-5-80-4059739203-877974"
             "739-1245631912-527174227-2996563517)",
            &v25,
            *((_DWORD *)this + 2882),
            0) )
      goto LABEL_35;
  }
  else
  {
LABEL_64:
    if ( *(_DWORD *)a3 != 2022 || !a4 || *((_DWORD *)this + 2882) )
      return ConfigUpdate::UpdateRegValue(this, a2, a3, 4u, v24, 4u, a5, a6);
    OnHTTPInitialize::OnHTTPInitialize((OnHTTPInitialize *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 72LL))(a2);
      goto LABEL_35;
    }
    v25 = 0;
    if ( !UpdateHttpsBinding(
            a2,
            L"https://+:443/wsman/",
            L"D:(A;;GX;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;;GX;;;S-1-5-80-4059739203-877974"
             "739-1245631912-527174227-2996563517)",
            &v25,
            *((_DWORD *)this + 2882),
            0) )
      goto LABEL_35;
    ComputerNameFQDN = GetComputerNameFQDN(a2);
    if ( !ComputerNameFQDN )
      goto LABEL_35;
    v27 = 0;
    v29[0] = 0;
    v28 = &CErrorContext::`vftable';
    v29[2] = 0;
    v29[3] = -1;
    v31 = &Class;
    v32 = &Class;
    v33 = &Class;
    v34 = &Class;
    v30 = 1;
    _InterlockedIncrement(v29);
    if ( (unsigned int)FindCertificate((struct IRequestContext *)&v28, (__int64)ComputerNameFQDN, &v27) )
    {
      v26 = 0;
      if ( ConfigRegistry::CheckSharedSSLConfiguration(this, a2, L"0.0.0.0", L"443", 0, &v26) )
      {
        if ( !v26 )
        {
          *(_OWORD *)&ServiceStatus.dwServiceType = WSMAN_SSLCONFIG_GUID;
          if ( !(unsigned int)UpdateHttpsCertificate(
                                a2,
                                L"0.0.0.0",
                                L"443",
                                v27,
                                &v25,
                                0,
                                (struct _GUID *)&ServiceStatus) )
          {
            v28 = &ILifeTimeMgmt::`vftable';
            AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
            goto LABEL_35;
          }
        }
      }
    }
    v28 = &ILifeTimeMgmt::`vftable';
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
  }
  OnHTTPInitialize::~OnHTTPInitialize((OnHTTPInitialize *)&v23);
  return ConfigUpdate::UpdateRegValue(this, a2, a3, 4u, v24, 4u, a5, a6);
}

```

## disassembly

```asm
0x180199718  push    rbp
0x18019971a  push    rbx
0x18019971b  push    rsi
0x18019971c  push    rdi
0x18019971d  push    r12
0x18019971f  push    r13
0x180199721  push    r14
0x180199723  push    r15
0x180199725  lea     rbp, [rsp-0Fh]
0x18019972a  sub     rsp, 0D8h
0x180199731  mov     rax, cs:__security_cookie
0x180199738  xor     rax, rsp
0x18019973b  mov     [rbp+47h+var_50], rax
0x18019973f  mov     r12, r8
0x180199742  mov     rdi, rdx
0x180199745  mov     rsi, rcx
0x180199748  mov     dword ptr [rsp+110h+var_C8], r9d
0x18019974d  mov     r13, [rbp+47h+arg_28]
0x180199751  xor     r15d, r15d
0x180199754  test    rdx, rdx
0x180199757  jnz     short loc_180199783
0x180199759  mov     [rsp+110h+var_F0], r15; struct IRequestContext *
0x18019975e  lea     r8, a3428; "3428"
0x180199765  mov     edx, 0D64h; unsigned int
0x18019976a  mov     r9d, 54Fh; unsigned int
0x180199770  lea     rcx, aOnecoreAdminWm_146; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180199777  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019977c  xor     eax, eax
0x18019977e  jmp     loc_180199AE1
0x180199783  test    r12, r12
0x180199786  jnz     short loc_18019979B
0x180199788  mov     [rsp+110h+var_F0], rdi
0x18019978d  lea     r8, a3429; "3429"
0x180199794  mov     edx, 0D65h
0x180199799  jmp     short loc_18019976A
0x18019979b  lea     rbx, WPP_GLOBAL_Control
0x1801997a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801997a9  cmp     rcx, rbx
0x1801997ac  jz      short loc_18019980C
0x1801997ae  test    dword ptr [rcx+1Ch], 200000h
0x1801997b5  jz      short loc_1801997DB
0x1801997b7  mov     edx, 79h ; 'y'
0x1801997bc  mov     r9, rsi
0x1801997bf  lea     r8, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x1801997c6  mov     rcx, [rcx+10h]
0x1801997ca  call    WPP_SF_q
0x1801997cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801997d6  mov     r9d, dword ptr [rsp+110h+var_C8]
0x1801997db  cmp     rcx, rbx
0x1801997de  jz      short loc_18019980C
0x1801997e0  test    dword ptr [rcx+1Ch], 200000h
0x1801997e7  jz      short loc_18019980C
0x1801997e9  mov     edx, 7Ah ; 'z'
0x1801997ee  mov     dword ptr [rsp+110h+var_F0], r9d
0x1801997f3  mov     r9d, [r12]
0x1801997f7  lea     r8, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x1801997fe  mov     rcx, [rcx+10h]
0x180199802  call    WPP_SF_Dd
0x180199807  mov     r9d, dword ptr [rsp+110h+var_C8]
0x18019980c  cmp     dword ptr [r12], 7E5h
0x180199814  jnz     loc_180199B01
0x18019981a  cmp     [rsi+2D08h], r15d
0x180199821  jnz     loc_180199962
0x180199827  lea     rcx, [rbp+47h+var_B0]; this
0x18019982b  call    ??0CFirewallManager@@QEAA@XZ; CFirewallManager::CFirewallManager(void)
0x180199830  nop
0x180199831  cmp     dword ptr [rsp+110h+var_C8], r15d
0x180199836  setnz   dl; bool
0x180199839  lea     rcx, [rbp+47h+var_B0]; this
0x18019983d  call    ?SwitchException@CFirewallManager@@QEAAJ_N@Z; CFirewallManager::SwitchException(bool)
0x180199842  mov     ebx, eax
0x180199844  test    eax, eax
0x180199846  jns     loc_180199954
0x18019984c  cmp     eax, 800706DFh
0x180199851  jz      short loc_180199865
0x180199853  cmp     eax, 800706D9h
0x180199858  jz      short loc_180199865
0x18019985a  mov     rcx, [rdi]
0x18019985d  mov     rax, [rcx+48h]
0x180199861  mov     edx, ebx
0x180199863  jmp     short loc_1801998CF
0x180199865  xor     edx, edx; lpDatabaseName
0x180199867  xor     ecx, ecx; lpMachineName
0x180199869  mov     r8d, 0F003Fh; dwDesiredAccess
0x18019986f  call    cs:__imp_OpenSCManagerW
0x180199875  mov     r14, rax
0x180199878  test    rax, rax
0x18019987b  jnz     short loc_1801998E6
0x18019987d  mov     rax, cs:WPP_GLOBAL_Control
0x180199884  lea     rdx, WPP_GLOBAL_Control
0x18019988b  cmp     rax, rdx
0x18019988e  jz      short loc_1801998BD
0x180199890  test    dword ptr [rax+1Ch], 400000h
0x180199897  jz      short loc_1801998BD
0x180199899  call    cs:__imp_GetLastError
0x18019989f  lea     edx, [r14+7Bh]
0x1801998a3  mov     r9d, eax
0x1801998a6  lea     r8, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x1801998ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1801998b4  mov     rcx, [rcx+10h]
0x1801998b8  call    WPP_SF_d
0x1801998bd  mov     rax, [rdi]
0x1801998c0  mov     rbx, [rax+48h]
0x1801998c4  call    cs:__imp_GetLastError
0x1801998ca  mov     edx, eax
0x1801998cc  mov     rax, rbx
0x1801998cf  mov     rcx, rdi
0x1801998d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801998d7  nop
0x1801998d8  lea     rcx, [rbp+47h+var_B0]; this
0x1801998dc  call    ??1CFirewallManager@@QEAA@XZ; CFirewallManager::~CFirewallManager(void)
0x1801998e1  jmp     loc_18019977C
0x1801998e6  mov     r8d, 4; dwDesiredAccess
0x1801998ec  lea     rdx, ServiceName; "mpssvc"
0x1801998f3  mov     rcx, r14; hSCManager
0x1801998f6  call    cs:__imp_OpenServiceW
0x1801998fc  mov     r15, rax
0x1801998ff  test    rax, rax
0x180199902  jnz     loc_1801999BC
0x180199908  mov     rcx, r14; hSCObject
0x18019990b  call    cs:__imp_CloseServiceHandle
0x180199911  mov     rax, cs:WPP_GLOBAL_Control
0x180199918  lea     rdx, WPP_GLOBAL_Control
0x18019991f  cmp     rax, rdx
0x180199922  jz      short loc_180199951
0x180199924  test    dword ptr [rax+1Ch], 400000h
0x18019992b  jz      short loc_180199951
0x18019992d  call    cs:__imp_GetLastError
0x180199933  lea     edx, [r15+7Ch]
0x180199937  mov     r9d, eax
0x18019993a  lea     r8, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x180199941  mov     rcx, cs:WPP_GLOBAL_Control
0x180199948  mov     rcx, [rcx+10h]
0x18019994c  call    WPP_SF_d
0x180199951  xor     r15d, r15d
0x180199954  lea     rcx, [rbp+47h+var_B0]; this
0x180199958  call    ??1CFirewallManager@@QEAA@XZ; CFirewallManager::~CFirewallManager(void)
0x18019995d  mov     r9d, dword ptr [rsp+110h+var_C8]
0x180199962  cmp     dword ptr [r12], 7E5h
0x18019996a  jnz     loc_180199B01
0x180199970  test    r9d, r9d
0x180199973  jz      loc_180199AAF
0x180199979  cmp     [rsi+2D08h], r15d
0x180199980  jnz     loc_180199AAF
0x180199986  lea     rcx, [rsp+110h+var_D0]; this
0x18019998b  call    ??0OnHTTPInitialize@@QEAA@XZ; OnHTTPInitialize::OnHTTPInitialize(void)
0x180199990  nop
0x180199991  mov     edx, [rsp+110h+var_D0]
0x180199995  mov     rcx, rdi; struct IRequestContext *
0x180199998  test    edx, edx
0x18019999a  jz      loc_180199A76
0x1801999a0  mov     rax, [rdi]
0x1801999a3  mov     rax, [rax+48h]
0x1801999a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801999ac  nop
0x1801999ad  lea     rcx, [rsp+110h+var_D0]; this
0x1801999b2  call    ??1OnHTTPInitialize@@QEAA@XZ; OnHTTPInitialize::~OnHTTPInitialize(void)
0x1801999b7  jmp     loc_18019977C
0x1801999bc  xorps   xmm0, xmm0
0x1801999bf  movups  xmmword ptr [rbp+47h+ServiceStatus.dwServiceType], xmm0
0x1801999c3  movups  xmmword ptr [rbp+47h+ServiceStatus.dwWin32ExitCode], xmm0
0x1801999c7  lea     rdx, [rbp+47h+ServiceStatus]; lpServiceStatus
0x1801999cb  mov     rcx, r15; hService
0x1801999ce  call    cs:__imp_QueryServiceStatus
0x1801999d4  mov     rcx, r15; hSCObject
0x1801999d7  test    eax, eax
0x1801999d9  jnz     short loc_180199A1E
0x1801999db  call    cs:__imp_CloseServiceHandle
0x1801999e1  mov     rcx, r14; hSCObject
0x1801999e4  call    cs:__imp_CloseServiceHandle
0x1801999ea  mov     rax, cs:WPP_GLOBAL_Control
0x1801999f1  lea     rdx, WPP_GLOBAL_Control
0x1801999f8  cmp     rax, rdx
0x1801999fb  jz      loc_1801998BD
0x180199a01  test    dword ptr [rax+1Ch], 400000h
0x180199a08  jz      loc_1801998BD
0x180199a0e  call    cs:__imp_GetLastError
0x180199a14  mov     edx, 7Dh ; '}'
0x180199a19  jmp     loc_1801998A3
0x180199a1e  call    cs:__imp_CloseServiceHandle
0x180199a24  mov     rcx, r14; hSCObject
0x180199a27  call    cs:__imp_CloseServiceHandle
0x180199a2d  cmp     [rbp+47h+ServiceStatus.dwCurrentState], 4
0x180199a31  jnz     loc_180199951
0x180199a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180199a3e  lea     rdx, WPP_GLOBAL_Control
0x180199a45  cmp     rcx, rdx
0x180199a48  jz      short loc_180199A68
0x180199a4a  test    dword ptr [rcx+1Ch], 200000h
0x180199a51  jz      short loc_180199A68
0x180199a53  mov     edx, 7Eh ; '~'
0x180199a58  lea     r8, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x180199a5f  mov     rcx, [rcx+10h]
0x180199a63  call    WPP_SF_
0x180199a68  mov     rax, [rdi]
0x180199a6b  mov     edx, ebx
0x180199a6d  mov     rax, [rax+48h]
0x180199a71  jmp     loc_1801998CF
0x180199a76  mov     dword ptr [rsp+110h+var_E8], r15d; int
0x180199a7b  mov     eax, [rsi+2D08h]
0x180199a81  mov     dword ptr [rsp+110h+var_F0], eax; int
0x180199a85  lea     r9, [rbp+47h+var_C0]; int *
0x180199a89  lea     r8, aDAGxS158056925; "D:(A;;GX;;;S-1-5-80-569256582-295340335"...
0x180199a90  lea     rdx, aHttp80Wsman; "http://+:80/wsman/"
0x180199a97  call    ?UpdateHttpsBinding@@YAHPEAVIRequestContext@@PEBG1PEAHHH@Z; UpdateHttpsBinding(IRequestContext *,ushort const *,ushort const *,int *,int,int)
0x180199a9c  nop
0x180199a9d  lea     rcx, [rsp+110h+var_D0]; this
0x180199aa2  test    eax, eax
0x180199aa4  jz      loc_1801999B2
0x180199aaa  call    ??1OnHTTPInitialize@@QEAA@XZ; OnHTTPInitialize::~OnHTTPInitialize(void)
0x180199aaf  mov     [rsp+110h+var_D8], r13; int *
0x180199ab4  mov     eax, [rbp+47h+arg_20]
0x180199ab7  mov     dword ptr [rsp+110h+var_E0], eax; int
0x180199abb  mov     dword ptr [rsp+110h+var_E8], 4; unsigned int
0x180199ac3  lea     rax, [rsp+110h+var_C8]
0x180199ac8  mov     [rsp+110h+var_F0], rax; unsigned __int8 *
0x180199acd  mov     r9d, 4; unsigned int
0x180199ad3  mov     r8, r12; struct _CONFIG_INFO *
0x180199ad6  mov     rdx, rdi; struct IRequestContext *
0x180199ad9  mov     rcx, rsi; this
0x180199adc  call    ?UpdateRegValue@ConfigUpdate@@AEAAHPEAVIRequestContext@@PEAU_CONFIG_INFO@@KPEAEKHPEAH@Z; ConfigUpdate::UpdateRegValue(IRequestContext *,_CONFIG_INFO *,ulong,uchar *,ulong,int,int *)
0x180199ae1  mov     rcx, [rbp+47h+var_50]
0x180199ae5  xor     rcx, rsp; StackCookie
0x180199ae8  call    __security_check_cookie
0x180199aed  add     rsp, 0D8h
0x180199af4  pop     r15
0x180199af6  pop     r14
0x180199af8  pop     r13
0x180199afa  pop     r12
0x180199afc  pop     rdi
0x180199afd  pop     rsi
0x180199afe  pop     rbx
0x180199aff  pop     rbp
0x180199b00  retn
0x180199b01  cmp     dword ptr [r12], 7E6h
0x180199b09  jnz     short loc_180199AAF
0x180199b0b  test    r9d, r9d
0x180199b0e  jz      short loc_180199AAF
0x180199b10  cmp     [rsi+2D08h], r15d
0x180199b17  jnz     short loc_180199AAF
0x180199b19  lea     rcx, [rsp+110h+var_D0]; this
0x180199b1e  call    ??0OnHTTPInitialize@@QEAA@XZ; OnHTTPInitialize::OnHTTPInitialize(void)
0x180199b23  nop
0x180199b24  mov     edx, [rsp+110h+var_D0]
0x180199b28  mov     rcx, rdi; struct IRequestContext *
0x180199b2b  test    edx, edx
0x180199b2d  jz      short loc_180199B41
0x180199b2f  mov     rax, [rdi]
0x180199b32  mov     rax, [rax+48h]
0x180199b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199b3b  nop
0x180199b3c  jmp     loc_1801999AD
0x180199b41  mov     [rbp+47h+var_C0], r15d
0x180199b45  mov     dword ptr [rsp+110h+var_E8], r15d; int
0x180199b4a  mov     eax, [rsi+2D08h]
0x180199b50  mov     dword ptr [rsp+110h+var_F0], eax; int
0x180199b54  lea     r9, [rbp+47h+var_C0]; int *
0x180199b58  lea     r8, aDAGxS158056925; "D:(A;;GX;;;S-1-5-80-569256582-295340335"...
0x180199b5f  lea     rdx, aHttps443Wsman; "https://+:443/wsman/"
0x180199b66  call    ?UpdateHttpsBinding@@YAHPEAVIRequestContext@@PEBG1PEAHHH@Z; UpdateHttpsBinding(IRequestContext *,ushort const *,ushort const *,int *,int,int)
0x180199b6b  test    eax, eax
0x180199b6d  jz      short loc_180199B3C
0x180199b6f  mov     rcx, rdi; struct IRequestContext *
0x180199b72  call    ?GetComputerNameFQDN@@YAPEBGAEAVIRequestContext@@@Z; GetComputerNameFQDN(IRequestContext &)
0x180199b77  test    rax, rax
0x180199b7a  jz      short loc_180199B3C
0x180199b7c  mov     [rbp+47h+var_B8], r15
0x180199b80  mov     [rbp+47h+var_A8], r15d
0x180199b84  lea     rcx, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180199b8b  mov     [rbp+47h+var_B0], rcx
0x180199b8f  mov     [rbp+47h+var_A0], r15d
0x180199b93  mov     [rbp+47h+var_9C], 0FFFFFFFFh
0x180199b9a  lea     rcx, Class
0x180199ba1  mov     [rbp+47h+var_90], rcx
0x180199ba5  mov     [rbp+47h+var_88], rcx
0x180199ba9  mov     [rbp+47h+var_80], rcx
0x180199bad  mov     [rbp+47h+var_78], rcx
0x180199bb1  mov     [rbp+47h+var_98], 1
0x180199bb5  lock inc [rbp+47h+var_A8]
0x180199bb9  lea     r8, [rbp+47h+var_B8]
0x180199bbd  mov     rdx, rax
0x180199bc0  lea     rcx, [rbp+47h+var_B0]
0x180199bc4  call    ?FindCertificate@@YAHPEAVIRequestContext@@PEBGAEAV?$AutoDelete@G@@@Z; FindCertificate(IRequestContext *,ushort const *,AutoDelete<ushort> &)
0x180199bc9  test    eax, eax
0x180199bcb  jz      loc_180199C60
0x180199bd1  mov     [rbp+47h+var_BC], r15d
0x180199bd5  lea     rax, [rbp+47h+var_BC]
0x180199bd9  mov     [rsp+110h+var_E8], rax; int *
0x180199bde  mov     dword ptr [rsp+110h+var_F0], r15d; int
0x180199be3  lea     r9, a443; "443"
0x180199bea  lea     r8, WideCharStr; "0.0.0.0"
0x180199bf1  mov     rdx, rdi; struct IRequestContext *
0x180199bf4  mov     rcx, rsi; this
0x180199bf7  call    ?CheckSharedSSLConfiguration@ConfigRegistry@@IEAAHPEAVIRequestContext@@PEBG1HPEAH@Z; ConfigRegistry::CheckSharedSSLConfiguration(IRequestContext *,ushort const *,ushort const *,int,int *)
0x180199bfc  test    eax, eax
0x180199bfe  jz      short loc_180199C60
0x180199c00  cmp     [rbp+47h+var_BC], r15d
0x180199c04  jnz     short loc_180199C60
0x180199c06  movups  xmm0, cs:WSMAN_SSLCONFIG_GUID
0x180199c0d  movdqu  xmmword ptr [rbp+47h+ServiceStatus.dwServiceType], xmm0
  ... truncated ...
```
