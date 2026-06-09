# CAppln::InitServicesConfig(void)

- ea: `0x18000268c`
- end: `0x18000285d`
- name: `?InitServicesConfig@CAppln@@AEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(CAppln *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800054e8`

## callees

- `0x180002488`
- `0x18000268c`
- `0x180013178`
- `0x180013230`
- `0x180023dd0`
- `0x180031fa0`
- `0x180062e38`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800026f8`
- `ole32!CoCreateInstance` at `0x1800026f8`
- `iisutil!PuDbgPrint` at `0x180024d11`
- `iisutil!PuDbgPrint` at `0x1800250a6`
- `iisutil!PuDbgPrint` at `0x180024d11`
- `iisutil!PuDbgPrint` at `0x1800250a6`

## string_xrefs

- `0x180024cdd`: `New Application Failed: InitServicesConfig() - Could not CCI ServicesConfig, hr = %#08x\n`
- `0x180024cfe`: `CAppln::InitServicesConfig`
- `0x180025093`: `CAppln::InitServicesConfig`
- `0x180024d34`: `New Application Failed: InitServicesConfig() - Could not QI for IServiceThreadPoolConfig, hr = %#08x\n`
- `0x180024d63`: `New Application Failed: InitServicesConfig() - Failed to Configure MTA, hr = %#08x\n`
- `0x180024d83`: `New Application Failed: InitServicesConfig() - Failed to Configure STA, hr = %#08x\n`
- `0x180024da6`: `New Application Failed: InitServicesConfig() - Failed to SelectThreadPool, hr = %#08x\n`
- `0x180024dc9`: `New Application Failed: InitServicesConfig() - Could not QI for IServiceSynchronizationConfig, hr = %#08x\n`
- `0x180024dec`: `New Application Failed: InitServicesConfig() - Could not ConfigureSynchronization, hr = %#08x\n`
- `0x180024e4e`: `New Application Failed: InitServicesConfig() - Could not QI for IServicePartitionConfig, hr = %#08x\n`
- `0x180024e8d`: `New Application Failed: InitServicesConfig() - Could not set PartitionConfig, hr = %#08x\n`
- `0x180024ee9`: `New Application Failed: InitServicesConfig() - Could not set PartitionID, hr = %#08x\n`
- `0x180024f18`: `New Application Failed: InitServicesConfig() - fUsePartition Set, but no PartitionID\n`
- `0x180024f61`: `New Application Failed: InitServicesConfig() - Could not QI for IServiceSxsConfig, hr = %#08x\n`
- `0x180024fa0`: `New Application Failed: InitServicesConfig() - Could not set SxsConfig, hr = %#08x\n`
- `0x180024cf0`: `New Application Failed: InitServicesConfig() - Could not set SxsDirectory, hr = %#08x\n`
- `0x18002504d`: `New Application Failed: InitServicesConfig() - Could not convert SxsName to UNICODE, hr = %#08x\n`
- `0x180025085`: `New Application Failed: InitServicesConfig() - Could not set SxsName, hr = %#08x\n`

## pseudocode

```c
__int64 __fastcall CAppln::InitServicesConfig(LPVOID *this)
{
  _QWORD *v1; // rsi
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // r9d
  const char **v19; // rdx
  int v20; // eax
  int v21; // eax
  HRESULT v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+28h] [rbp-D8h]
  int v30; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+28h] [rbp-D8h]
  int v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  char *v42; // [rsp+50h] [rbp-B0h] BYREF
  char v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+258h] [rbp+158h]

  v1 = this + 24;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  Instance = CoCreateInstance(&CLSID_CServiceConfig, 0, 1u, &IID_IUnknown, this + 24);
  v4 = Instance;
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 7) != 0 )
    {
      v22 = Instance;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
        1310,
        "CAppln::InitServicesConfig",
        "New Application Failed: InitServicesConfig() - Could not CCI ServicesConfig, hr = %#08x\n",
        v22);
    }
  }
  else
  {
    v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v1)(*v1, &IID_IServiceThreadPoolConfig, &v40);
    v4 = v5;
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 7) != 0 )
      {
        v24 = v5;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
          1316,
          "CAppln::InitServicesConfig",
          "New Application Failed: InitServicesConfig() - Could not QI for IServiceThreadPoolConfig, hr = %#08x\n",
          v24);
      }
    }
    else
    {
      if ( *((_DWORD *)this[19] + 23) )
      {
        v11 = ViperConfigureMTA();
        v4 = v11;
        if ( v11 < 0 )
        {
          if ( (g_dwDebugFlags & 7) != 0 )
          {
            v25 = v11;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
              1323,
              "CAppln::InitServicesConfig",
              "New Application Failed: InitServicesConfig() - Failed to Configure MTA, hr = %#08x\n",
              v25);
          }
          goto LABEL_10;
        }
      }
      else
      {
        v6 = ViperConfigureSTA();
        v4 = v6;
        if ( v6 < 0 )
        {
          if ( (g_dwDebugFlags & 7) != 0 )
          {
            v26 = v6;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
              1330,
              "CAppln::InitServicesConfig",
              "New Application Failed: InitServicesConfig() - Failed to Configure STA, hr = %#08x\n",
              v26);
          }
          goto LABEL_10;
        }
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 24LL))(
             v40,
             (unsigned int)(*((_DWORD *)this[19] + 23) != 0) + 2);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( (g_dwDebugFlags & 7) != 0 )
        {
          v27 = v7;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
            1337,
            "CAppln::InitServicesConfig",
            "New Application Failed: InitServicesConfig() - Failed to SelectThreadPool, hr = %#08x\n",
            v27);
        }
      }
      else
      {
        v8 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v1)(*v1, &IID_IServiceSynchronizationConfig, &v41);
        v4 = v8;
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 7) != 0 )
          {
            v28 = v8;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
              1343,
              "CAppln::InitServicesConfig",
              "New Application Failed: InitServicesConfig() - Could not QI for IServiceSynchronizationConfig, hr = %#08x\n",
              v28);
          }
        }
        else
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 24LL))(
                 v41,
                 *((_DWORD *)this[19] + 23) != 0 ? 3 : 1);
          v4 = v9;
          if ( v9 < 0 )
          {
            if ( (g_dwDebugFlags & 7) != 0 )
            {
              v29 = v9;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                1349,
                "CAppln::InitServicesConfig",
                "New Application Failed: InitServicesConfig() - Could not ConfigureSynchronization, hr = %#08x\n",
                v29);
            }
          }
          else
          {
            if ( !*((_DWORD *)this[19] + 31) )
              goto LABEL_9;
            if ( (-(__int64)((*((_DWORD *)this[19] + 3) & 8) != 0) & ((unsigned __int64)this[19] + 100)) != 0 )
            {
              v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v1)(
                      *v1,
                      &IID_IServicePartitionConfig,
                      &v38);
              v4 = v12;
              if ( v12 >= 0 )
              {
                v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 24LL))(v38, 2);
                v4 = v13;
                if ( v13 >= 0 )
                {
                  v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v38 + 32LL))(
                          v38,
                          ((unsigned __int64)this[19] + 100) & -(__int64)((*((_DWORD *)this[19] + 3) & 8) != 0));
                  v4 = v14;
                  if ( v14 >= 0 )
                  {
LABEL_9:
                    if ( *((_DWORD *)this[19] + 29) )
                    {
                      v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v1)(
                              *v1,
                              &IID_IServiceSxsConfig,
                              &v39);
                      v4 = v15;
                      if ( v15 >= 0 )
                      {
                        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 24LL))(v39, 2);
                        v4 = v16;
                        if ( v16 >= 0 )
                        {
                          v17 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v39 + 40LL))(v39, this[14]);
                          v4 = v17;
                          if ( v17 >= 0 )
                          {
                            if ( *((_QWORD *)this[19] + 27) && **((_BYTE **)this[19] + 27) )
                            {
                              v19 = (const char **)this[19];
                              v42 = &v43;
                              v44 = 0;
                              v20 = CMBCSToWChar::Init((LPVOID *)&v42, v19[27], 0, v18);
                              v4 = v20;
                              if ( v20 >= 0 )
                              {
                                v21 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 32LL))(v39, v42);
                                v4 = v21;
                                if ( v21 < 0 && (g_dwDebugFlags & 7) != 0 )
                                {
                                  v37 = v21;
                                  PuDbgPrint(
                                    g_pDebug,
                                    "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                                    1428,
                                    "CAppln::InitServicesConfig",
                                    "New Application Failed: InitServicesConfig() - Could not set SxsName, hr = %#08x\n",
                                    v37);
                                }
                              }
                              else if ( (g_dwDebugFlags & 7) != 0 )
                              {
                                v36 = v20;
                                PuDbgPrint(
                                  g_pDebug,
                                  "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                                  1422,
                                  "CAppln::InitServicesConfig",
                                  "New Application Failed: InitServicesConfig() - Could not convert SxsName to UNICODE, hr = %#08x\n",
                                  v36);
                              }
                              CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v42);
                            }
                          }
                          else if ( (g_dwDebugFlags & 7) != 0 )
                          {
                            v23 = v17;
                            PuDbgPrint(
                              g_pDebug,
                              "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                              1413,
                              "CAppln::InitServicesConfig",
                              "New Application Failed: InitServicesConfig() - Could not set SxsDirectory, hr = %#08x\n",
                              v23);
                          }
                        }
                        else if ( (g_dwDebugFlags & 7) != 0 )
                        {
                          v35 = v16;
                          PuDbgPrint(
                            g_pDebug,
                            "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                            1393,
                            "CAppln::InitServicesConfig",
                            "New Application Failed: InitServicesConfig() - Could not set SxsConfig, hr = %#08x\n",
                            v35);
                        }
                      }
                      else if ( (g_dwDebugFlags & 7) != 0 )
                      {
                        v34 = v15;
                        PuDbgPrint(
                          g_pDebug,
                          "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                          1387,
                          "CAppln::InitServicesConfig",
                          "New Application Failed: InitServicesConfig() - Could not QI for IServiceSxsConfig, hr = %#08x\n",
                          v34);
                      }
                    }
                    goto LABEL_10;
                  }
                  if ( (g_dwDebugFlags & 7) != 0 )
                  {
                    v32 = v14;
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                      1371,
                      "CAppln::InitServicesConfig",
                      "New Application Failed: InitServicesConfig() - Could not set PartitionID, hr = %#08x\n",
                      v32);
                  }
                }
                else if ( (g_dwDebugFlags & 7) != 0 )
                {
                  v31 = v13;
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                    1365,
                    "CAppln::InitServicesConfig",
                    "New Application Failed: InitServicesConfig() - Could not set PartitionConfig, hr = %#08x\n",
                    v31);
                }
              }
              else if ( (g_dwDebugFlags & 7) != 0 )
              {
                v30 = v12;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                  1359,
                  "CAppln::InitServicesConfig",
                  "New Application Failed: InitServicesConfig() - Could not QI for IServicePartitionConfig, hr = %#08x\n",
                  v30);
              }
            }
            else
            {
              CAppln::LogSWCError(this, 1);
              v4 = -2147467259;
              if ( (g_dwDebugFlags & 7) != 0 )
              {
                v33 = -2147467259;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                  1378,
                  "CAppln::InitServicesConfig",
                  "New Application Failed: InitServicesConfig() - fUsePartition Set, but no PartitionID\n",
                  v33);
              }
            }
          }
        }
      }
    }
  }
LABEL_10:
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return v4;
}

```

## disassembly

```asm
0x18000268c  push    rbp
0x18000268e  push    rbx
0x18000268f  push    rsi
0x180002690  push    rdi
0x180002691  lea     rbp, [rsp-178h]
0x180002699  sub     rsp, 278h
0x1800026a0  mov     rax, cs:__security_cookie
0x1800026a7  xor     rax, rsp
0x1800026aa  mov     [rbp+190h+var_30], rax
0x1800026b1  lea     rsi, [rcx+0C0h]
0x1800026b8  mov     [rsp+290h+var_250], 0
0x1800026c1  xor     edx, edx; pUnkOuter
0x1800026c3  mov     [rsp+290h+var_248], 0
0x1800026cc  mov     rdi, rcx
0x1800026cf  mov     [rsp+290h+var_260], 0
0x1800026d8  lea     r9, IID_IUnknown; riid
0x1800026df  mov     [rsp+290h+var_258], 0
0x1800026e8  lea     rcx, CLSID_CServiceConfig; rclsid
0x1800026ef  mov     [rsp+290h+ppv], rsi; ppv
0x1800026f4  lea     r8d, [rdx+1]; dwClsContext
0x1800026f8  call    cs:__imp_CoCreateInstance
0x1800026fe  mov     ebx, eax
0x180002700  test    eax, eax
0x180002702  js      loc_180024CC6
0x180002708  mov     rcx, [rsi]
0x18000270b  lea     r8, [rsp+290h+var_250]
0x180002710  lea     rdx, IID_IServiceThreadPoolConfig
0x180002717  mov     rax, [rcx]
0x18000271a  mov     rax, [rax]
0x18000271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002722  mov     ebx, eax
0x180002724  test    eax, eax
0x180002726  js      loc_180024D1D
0x18000272c  mov     rax, [rdi+98h]
0x180002733  cmp     dword ptr [rax+5Ch], 0
0x180002737  jnz     loc_180024D3D
0x18000273d  call    ?ViperConfigureSTA@@YAJXZ; ViperConfigureSTA(void)
0x180002742  mov     ebx, eax
0x180002744  test    eax, eax
0x180002746  js      loc_180024D6C
0x18000274c  mov     rax, [rsp+290h+var_250]
0x180002751  mov     rcx, [rax]
0x180002754  mov     rax, [rcx+18h]
0x180002758  mov     rcx, [rdi+98h]
0x18000275f  mov     edx, [rcx+5Ch]
0x180002762  mov     rcx, [rsp+290h+var_250]
0x180002767  neg     edx
0x180002769  sbb     edx, edx
0x18000276b  neg     edx
0x18000276d  add     edx, 2
0x180002770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002775  mov     ebx, eax
0x180002777  test    eax, eax
0x180002779  js      loc_180024D8F
0x18000277f  mov     rcx, [rsi]
0x180002782  lea     r8, [rsp+290h+var_248]
0x180002787  lea     rdx, IID_IServiceSynchronizationConfig
0x18000278e  mov     rax, [rcx]
0x180002791  mov     rax, [rax]
0x180002794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002799  mov     ebx, eax
0x18000279b  test    eax, eax
0x18000279d  js      loc_180024DB2
0x1800027a3  mov     rax, [rsp+290h+var_248]
0x1800027a8  mov     rcx, [rax]
0x1800027ab  mov     rax, [rcx+18h]
0x1800027af  mov     rcx, [rdi+98h]
0x1800027b6  mov     edx, [rcx+5Ch]
0x1800027b9  mov     rcx, [rsp+290h+var_248]
0x1800027be  neg     edx
0x1800027c0  sbb     edx, edx
0x1800027c2  and     edx, 2
0x1800027c5  inc     edx
0x1800027c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cc  mov     ebx, eax
0x1800027ce  test    eax, eax
0x1800027d0  js      loc_180024DD5
0x1800027d6  mov     rax, [rdi+98h]
0x1800027dd  cmp     dword ptr [rax+7Ch], 0
0x1800027e1  jnz     loc_180024DF8
0x1800027e7  mov     rax, [rdi+98h]
0x1800027ee  cmp     dword ptr [rax+74h], 0
0x1800027f2  jnz     loc_180024F2A
0x1800027f8  mov     rcx, [rsp+290h+var_250]
0x1800027fd  test    rcx, rcx
0x180002800  jz      short loc_18000280E
0x180002802  mov     rax, [rcx]
0x180002805  mov     rax, [rax+10h]
0x180002809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280e  mov     rcx, [rsp+290h+var_248]
0x180002813  test    rcx, rcx
0x180002816  jz      short loc_180002824
0x180002818  mov     rax, [rcx]
0x18000281b  mov     rax, [rax+10h]
0x18000281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002824  mov     rcx, [rsp+290h+var_260]
0x180002829  test    rcx, rcx
0x18000282c  jnz     loc_1800250BC
0x180002832  mov     rcx, [rsp+290h+var_258]
0x180002837  test    rcx, rcx
0x18000283a  jnz     loc_1800250CE
0x180002840  mov     eax, ebx
0x180002842  mov     rcx, [rbp+190h+var_30]
0x180002849  xor     rcx, rsp; StackCookie
0x18000284c  call    __security_check_cookie
0x180002851  add     rsp, 278h
0x180002858  pop     rdi
0x180002859  pop     rsi
0x18000285a  pop     rbx
0x18000285b  pop     rbp
0x18000285c  retn
0x180024cc6  test    byte ptr cs:g_dwDebugFlags, 7
0x180024ccd  jz      loc_1800027F8
0x180024cd3  mov     [rsp+290h+var_268], eax
0x180024cd7  mov     r8d, 51Eh
0x180024cdd  lea     rax, aNewApplication_25; "New Application Failed: InitServicesCon"...
0x180024ce4  jmp     short loc_180024CF7
0x180024ce6  mov     [rsp+290h+var_268], eax
0x180024cea  mov     r8d, 585h
0x180024cf0  lea     rax, aNewApplication_19; "New Application Failed: InitServicesCon"...
0x180024cf7  mov     rcx, cs:g_pDebug
0x180024cfe  lea     r9, aCapplnInitserv; "CAppln::InitServicesConfig"
0x180024d05  lea     rdx, aInetsrvIisSvcs_7; "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.c"...
0x180024d0c  mov     [rsp+290h+ppv], rax
0x180024d11  call    cs:__imp_PuDbgPrint
0x180024d17  nop
0x180024d18  jmp     loc_1800027F8
0x180024d1d  test    byte ptr cs:g_dwDebugFlags, 7
0x180024d24  jz      loc_1800027F8
0x180024d2a  mov     [rsp+290h+var_268], eax
0x180024d2e  mov     r8d, 524h
0x180024d34  lea     rax, aNewApplication_8; "New Application Failed: InitServicesCon"...
0x180024d3b  jmp     short loc_180024CF7
0x180024d3d  call    ?ViperConfigureMTA@@YAJXZ; ViperConfigureMTA(void)
0x180024d42  mov     ebx, eax
0x180024d44  test    eax, eax
0x180024d46  jns     loc_18000274C
0x180024d4c  test    byte ptr cs:g_dwDebugFlags, 7
0x180024d53  jz      loc_1800027F8
0x180024d59  mov     [rsp+290h+var_268], eax
0x180024d5d  mov     r8d, 52Bh
0x180024d63  lea     rax, aNewApplication_4; "New Application Failed: InitServicesCon"...
0x180024d6a  jmp     short loc_180024CF7
0x180024d6c  test    byte ptr cs:g_dwDebugFlags, 7
0x180024d73  jz      loc_1800027F8
0x180024d79  mov     [rsp+290h+var_268], eax
0x180024d7d  mov     r8d, 532h
0x180024d83  lea     rax, aNewApplication_6; "New Application Failed: InitServicesCon"...
0x180024d8a  jmp     loc_180024CF7
0x180024d8f  test    byte ptr cs:g_dwDebugFlags, 7
0x180024d96  jz      loc_1800027F8
0x180024d9c  mov     [rsp+290h+var_268], eax
0x180024da0  mov     r8d, 539h
0x180024da6  lea     rax, aNewApplication_2; "New Application Failed: InitServicesCon"...
0x180024dad  jmp     loc_180024CF7
0x180024db2  test    byte ptr cs:g_dwDebugFlags, 7
0x180024db9  jz      loc_1800027F8
0x180024dbf  mov     [rsp+290h+var_268], eax
0x180024dc3  mov     r8d, 53Fh
0x180024dc9  lea     rax, aNewApplication_18; "New Application Failed: InitServicesCon"...
0x180024dd0  jmp     loc_180024CF7
0x180024dd5  test    byte ptr cs:g_dwDebugFlags, 7
0x180024ddc  jz      loc_1800027F8
0x180024de2  mov     [rsp+290h+var_268], eax
0x180024de6  mov     r8d, 545h
0x180024dec  lea     rax, aNewApplication_7; "New Application Failed: InitServicesCon"...
0x180024df3  jmp     loc_180024CF7
0x180024df8  mov     rax, [rdi+98h]
0x180024dff  mov     edx, [rax+0Ch]
0x180024e02  lea     rcx, [rax+64h]
0x180024e06  and     dl, 8
0x180024e09  neg     dl
0x180024e0b  sbb     rax, rax
0x180024e0e  test    rcx, rax
0x180024e11  jz      loc_180024EF5
0x180024e17  mov     rcx, [rsi]
0x180024e1a  lea     r8, [rsp+290h+var_260]
0x180024e1f  lea     rdx, IID_IServicePartitionConfig
0x180024e26  mov     rax, [rcx]
0x180024e29  mov     rax, [rax]
0x180024e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e31  mov     ebx, eax
0x180024e33  test    eax, eax
0x180024e35  jns     short loc_180024E5A
0x180024e37  test    byte ptr cs:g_dwDebugFlags, 7
0x180024e3e  jz      loc_1800027F8
0x180024e44  mov     [rsp+290h+var_268], eax
0x180024e48  mov     r8d, 54Fh
0x180024e4e  lea     rax, aNewApplication_23; "New Application Failed: InitServicesCon"...
0x180024e55  jmp     loc_180024CF7
0x180024e5a  mov     rcx, [rsp+290h+var_260]
0x180024e5f  mov     edx, 2
0x180024e64  mov     rax, [rcx]
0x180024e67  mov     rax, [rax+18h]
0x180024e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e70  mov     ebx, eax
0x180024e72  test    eax, eax
0x180024e74  jns     short loc_180024E99
0x180024e76  test    byte ptr cs:g_dwDebugFlags, 7
0x180024e7d  jz      loc_1800027F8
0x180024e83  mov     [rsp+290h+var_268], eax
0x180024e87  mov     r8d, 555h
0x180024e8d  lea     rax, aNewApplication_13; "New Application Failed: InitServicesCon"...
0x180024e94  jmp     loc_180024CF7
0x180024e99  mov     rax, [rsp+290h+var_260]
0x180024e9e  mov     rcx, [rax]
0x180024ea1  mov     rax, [rcx+20h]
0x180024ea5  mov     rcx, [rdi+98h]
0x180024eac  mov     edx, [rcx+0Ch]
0x180024eaf  add     rcx, 64h ; 'd'
0x180024eb3  and     dl, 8
0x180024eb6  neg     dl
0x180024eb8  sbb     rdx, rdx
0x180024ebb  and     rdx, rcx
0x180024ebe  mov     rcx, [rsp+290h+var_260]
0x180024ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec8  mov     ebx, eax
0x180024eca  test    eax, eax
0x180024ecc  jns     loc_1800027E7
0x180024ed2  test    byte ptr cs:g_dwDebugFlags, 7
0x180024ed9  jz      loc_1800027F8
0x180024edf  mov     [rsp+290h+var_268], eax
0x180024ee3  mov     r8d, 55Bh
0x180024ee9  lea     rax, aNewApplication_26; "New Application Failed: InitServicesCon"...
0x180024ef0  jmp     loc_180024CF7
0x180024ef5  mov     edx, 1
0x180024efa  mov     rcx, rdi
0x180024efd  call    ?LogSWCError@CAppln@@QEAAXW4eSWCERRORS@@@Z; CAppln::LogSWCError(eSWCERRORS)
0x180024f02  test    byte ptr cs:g_dwDebugFlags, 7
0x180024f09  mov     ebx, 80004005h
0x180024f0e  jz      loc_1800027F8
0x180024f14  mov     [rsp+290h+var_268], ebx
0x180024f18  lea     rax, aNewApplication_15; "New Application Failed: InitServicesCon"...
0x180024f1f  mov     r8d, 562h
0x180024f25  jmp     loc_180024CF7
0x180024f2a  mov     rcx, [rsi]
0x180024f2d  lea     r8, [rsp+290h+var_258]
0x180024f32  lea     rdx, IID_IServiceSxsConfig
0x180024f39  mov     rax, [rcx]
0x180024f3c  mov     rax, [rax]
0x180024f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f44  mov     ebx, eax
0x180024f46  test    eax, eax
0x180024f48  jns     short loc_180024F6D
0x180024f4a  test    byte ptr cs:g_dwDebugFlags, 7
0x180024f51  jz      loc_1800027F8
0x180024f57  mov     [rsp+290h+var_268], eax
0x180024f5b  mov     r8d, 56Bh
0x180024f61  lea     rax, aNewApplication_20; "New Application Failed: InitServicesCon"...
0x180024f68  jmp     loc_180024CF7
0x180024f6d  mov     rcx, [rsp+290h+var_258]
0x180024f72  mov     edx, 2
0x180024f77  mov     rax, [rcx]
0x180024f7a  mov     rax, [rax+18h]
0x180024f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f83  mov     ebx, eax
0x180024f85  test    eax, eax
0x180024f87  jns     short loc_180024FAC
0x180024f89  test    byte ptr cs:g_dwDebugFlags, 7
0x180024f90  jz      loc_1800027F8
0x180024f96  mov     [rsp+290h+var_268], eax
0x180024f9a  mov     r8d, 571h
0x180024fa0  lea     rax, aNewApplication_27; "New Application Failed: InitServicesCon"...
0x180024fa7  jmp     loc_180024CF7
0x180024fac  mov     rcx, [rsp+290h+var_258]
0x180024fb1  mov     rdx, [rdi+70h]
0x180024fb5  mov     rax, [rcx]
0x180024fb8  mov     rax, [rax+28h]
0x180024fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fc1  mov     ebx, eax
0x180024fc3  test    eax, eax
0x180024fc5  jns     short loc_180024FD9
0x180024fc7  test    byte ptr cs:g_dwDebugFlags, 7
0x180024fce  jz      loc_1800027F8
0x180024fd4  jmp     loc_180024CE6
0x180024fd9  mov     rax, [rdi+98h]
0x180024fe0  cmp     qword ptr [rax+0D8h], 0
0x180024fe8  jz      loc_1800027F8
0x180024fee  mov     rax, [rdi+98h]
0x180024ff5  mov     rcx, [rax+0D8h]
0x180024ffc  cmp     byte ptr [rcx], 0
0x180024fff  jz      loc_1800027F8
0x180025005  mov     rdx, [rdi+98h]
0x18002500c  lea     rax, [rsp+290h+var_238]
0x180025011  mov     [rsp+290h+var_240], rax
0x180025016  lea     rcx, [rsp+290h+var_240]; this
0x18002501b  mov     [rbp+190h+var_38], 0
0x180025025  xor     r8d, r8d; unsigned int
0x180025028  mov     rdx, [rdx+0D8h]; char *
0x18002502f  call    ?Init@CMBCSToWChar@@QEAAJPEBDIH@Z; CMBCSToWChar::Init(char const *,uint,int)
0x180025034  mov     ebx, eax
0x180025036  test    eax, eax
0x180025038  jns     short loc_180025056
0x18002503a  test    byte ptr cs:g_dwDebugFlags, 7
0x180025041  jz      short loc_1800250AC
0x180025043  mov     [rsp+290h+var_268], eax
0x180025047  mov     r8d, 58Eh
0x18002504d  lea     rax, aNewApplication_17; "New Application Failed: InitServicesCon"...
0x180025054  jmp     short loc_18002508C
0x180025056  mov     rcx, [rsp+290h+var_258]
  ... truncated ...
```
