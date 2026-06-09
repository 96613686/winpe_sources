# IPxlatSvcControl::Start(void)

- ea: `0x18000ba4c`
- end: `0x18000becb`
- name: `?Start@IPxlatSvcControl@@QEAAKXZ`
- size: `1151`
- prototype: `__int64 __fastcall(IPxlatSvcControl *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ce30`

## callees

- `0x180001d40`
- `0x18000214c`
- `0x18000ba4c`
- `0x18000bed4`
- `0x18000c1cc`
- `0x18000c224`
- `0x18000c9dc`
- `0x18000cb48`
- `0x18000ea3c`
- `0x180011400`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ba81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ba81`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bb69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bd44`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000be24`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bb69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bd44`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000be24`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bb0d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bb0d`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000bdf8`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000be0a`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000bdf8`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000be0a`

## string_xrefs

- `0x18000baad`: `Could not create event.`
- `0x18000bb91`: `Could not update service status to start pending.`
- `0x18000bd63`: `Could not update service status to running.`
- `0x18000be43`: `Could not update service status to stopped.`

## pseudocode

```c
__int64 __fastcall IPxlatSvcControl::Start(IPxlatSvcControl *this)
{
  IPxlatSvcControl *v1; // r14
  HANDLE EventW; // rax
  DWORD v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // esi
  const char *v7; // rax
  SERVICE_STATUS_HANDLE v8; // rax
  DWORD LastError; // eax
  DWORD v10; // eax
  unsigned int updated; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // r15d
  IPxlatInterfaceMgr *v15; // rsi
  _DWORD *v16; // rax
  volatile signed __int32 *v17; // rsi
  BOOL v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  DWORD v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rcx
  DWORD v34; // [rsp+30h] [rbp-A8h] BYREF
  int v35; // [rsp+38h] [rbp-A0h]
  IPxlatInterfaceMgr *v36; // [rsp+40h] [rbp-98h] BYREF
  IPxlatSvcControl *v37; // [rsp+48h] [rbp-90h]
  const std::system_error *v38; // [rsp+50h] [rbp-88h] BYREF
  const std::system_error *v39; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v40[16]; // [rsp+60h] [rbp-78h] BYREF
  const char *v41; // [rsp+70h] [rbp-68h]
  __int64 v42; // [rsp+78h] [rbp-60h]
  IPxlatInterfaceMgr **v43; // [rsp+80h] [rbp-58h]
  __int64 v44; // [rsp+88h] [rbp-50h]

  v1 = this;
  v37 = this;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)v1 = EventW;
  if ( EventW )
  {
    v8 = RegisterServiceCtrlHandlerExW(L"IPxlatCfgSvc", IPxlatSvcControl::ScmNotificationHandler, v1);
    *((_QWORD *)v1 + 5) = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
        goto LABEL_36;
      v34 = LastError;
      v7 = "Could not register with SCM.";
      v42 = 29;
      goto LABEL_4;
    }
    *((_DWORD *)v1 + 2) = 32;
    *(_QWORD *)((char *)v1 + 12) = 2;
    if ( !SetServiceStatus(v8, (LPSERVICE_STATUS)((char *)v1 + 8)) )
    {
      v10 = GetLastError();
      v6 = v10;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
        goto LABEL_36;
      v34 = v10;
      v7 = "Could not update service status to start pending.";
      v42 = 50;
      goto LABEL_4;
    }
    updated = IPxlatSvcControl::UpdateWinNatDriver(v1);
    v6 = updated;
    if ( updated )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
        goto LABEL_36;
      v34 = updated;
      v7 = "Could not load WinNat driver.";
      v42 = 30;
      goto LABEL_4;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl'::`2'::impl) )
    {
      v12 = InitializeIPxlatRpcServer((RPC_WSTR)L"IPxlatRpc", qword_18001A360);
      v6 = v12;
      if ( v12 )
      {
LABEL_16:
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
          goto LABEL_36;
        v34 = v12;
        v7 = "Could not initialize RPC server.";
        v42 = 33;
        goto LABEL_4;
      }
      v13 = InitializeIPxlatRpcServer((RPC_WSTR)L"IPxlatRpc1", qword_18001A740);
      v14 = v13;
      v34 = v13;
      if ( v13 )
      {
        v6 = v13;
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
          goto LABEL_36;
        v34 = v13;
        v7 = "Could not initialize Query RPC server.";
        v42 = 39;
        goto LABEL_4;
      }
    }
    else
    {
      v12 = InitializeIPxlatRpcServer_Scrap();
      v14 = v12;
      v34 = v12;
      if ( v12 )
      {
        v6 = v12;
        goto LABEL_16;
      }
    }
    try
    {
      v36 = (IPxlatInterfaceMgr *)operator new(0xA0u);
      v15 = IPxlatInterfaceMgr::IPxlatInterfaceMgr(v36, *(void **)v1);
      v36 = v15;
      v16 = operator new(0x18u);
      v16[2] = 1;
      v16[3] = 1;
      *(_QWORD *)v16 = &std::_Ref_count<IPxlatInterfaceMgr>::`vftable';
      *((_QWORD *)v16 + 2) = v15;
      *((_QWORD *)v1 + 9) = v15;
      v17 = (volatile signed __int32 *)*((_QWORD *)v1 + 10);
      *((_QWORD *)v1 + 10) = v16;
      if ( v17 )
      {
        if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      *((_DWORD *)v1 + 2) = 32;
      *((_DWORD *)v1 + 4) = 5;
      *((_DWORD *)v1 + 3) = 4;
      v18 = SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v1 + 5), (LPSERVICE_STATUS)((char *)v1 + 8));
    }
    catch ( const std::system_error *v39 )
    {
      v31 = *((_DWORD *)v39 + 6);
      v35 = v31;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      {
        v32 = (*(__int64 (__fastcall **)(const std::system_error *))(*(_QWORD *)v39 + 8LL))(v39);
        McTemplateU0sq_EventWriteTransfer(v33, IPXLATCFG_ERROR_EVENT, v32, v31);
      }
      v1 = v37;
      v14 = v34;
      v6 = v35;
      goto LABEL_32;
    }
    catch ( ... )
    {
      v35 = 1359;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      {
        LODWORD(v36) = 1359;
        v41 = "Internal error occured while creating the interface manager";
        v42 = 60;
        v43 = &v36;
        v44 = 4;
        McGenEventWrite_EventWriteTransfer(v19, IPXLATCFG_ERROR_EVENT, v20, 3, v40);
      }
      v1 = v37;
      v14 = v34;
      v6 = v35;
      goto LABEL_32;
    }
    try
    {
      if ( v18 )
      {
        _InterlockedCompareExchange((volatile signed __int32 *)v1 + 12, 1, 0);
        v6 = IPxlatInterfaceMgr::WaitForXlatInterfaces(*((IPxlatInterfaceMgr **)v1 + 9));
      }
      else
      {
        v21 = GetLastError();
        v6 = v21;
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        {
          v34 = v21;
          v41 = "Could not update service status to running.";
          v42 = 44;
          v43 = (IPxlatInterfaceMgr **)&v34;
          v44 = 4;
          McGenEventWrite_EventWriteTransfer(v22, IPXLATCFG_ERROR_EVENT, v23, 3, v40);
        }
      }
    }
    catch ( const std::system_error *v38 )
    {
      v28 = *((_DWORD *)v38 + 6);
      v35 = v28;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      {
        v29 = (*(__int64 (__fastcall **)(const std::system_error *))(*(_QWORD *)v38 + 8LL))(v38);
        McTemplateU0sq_EventWriteTransfer(v30, IPXLATCFG_ERROR_EVENT, v29, v28);
      }
      v1 = v37;
      v14 = v34;
      v6 = v35;
    }
    catch ( ... )
    {
      v35 = 1359;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      {
        LODWORD(v36) = 1359;
        v41 = "Internal error occured while waiting for RPC calls";
        v42 = 51;
        v43 = &v36;
        v44 = 4;
        McGenEventWrite_EventWriteTransfer(v22, IPXLATCFG_ERROR_EVENT, v23, 3, v40);
      }
      v1 = v37;
      v14 = v34;
      v6 = v35;
    }
LABEL_32:
    if ( !v14 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl'::`2'::impl) )
        RpcServerUnregisterIf(qword_18001A740, 0, 0);
      RpcServerUnregisterIf(qword_18001A360, 0, 0);
    }
    goto LABEL_36;
  }
  v3 = GetLastError();
  v6 = v3;
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
  {
    v34 = v3;
    v7 = "Could not create event.";
    v42 = 24;
LABEL_4:
    v41 = v7;
    v43 = (IPxlatInterfaceMgr **)&v34;
    v44 = 4;
    McGenEventWrite_EventWriteTransfer(v4, IPXLATCFG_ERROR_EVENT, v5, 3, v40);
  }
LABEL_36:
  *(_QWORD *)((char *)v1 + 12) = 1;
  *((_DWORD *)v1 + 5) = v6;
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v1 + 5), (LPSERVICE_STATUS)((char *)v1 + 8)) )
  {
    v24 = GetLastError();
    v6 = v24;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      LODWORD(v36) = v24;
      v41 = "Could not update service status to stopped.";
      v42 = 44;
      v43 = &v36;
      v44 = 4;
      McGenEventWrite_EventWriteTransfer(v25, IPXLATCFG_ERROR_EVENT, v26, 3, v40);
    }
  }
  CloseHandle(*(HANDLE *)v1);
  _InterlockedCompareExchange((volatile signed __int32 *)v1 + 13, 1, 0);
  return v6;
}

```

## disassembly

```asm
0x18000ba4c  push    rbx
0x18000ba4e  push    rsi
0x18000ba4f  push    rdi
0x18000ba50  push    r12
0x18000ba52  push    r14
0x18000ba54  push    r15
0x18000ba56  sub     rsp, 0A8h
0x18000ba5d  mov     rax, cs:__security_cookie
0x18000ba64  xor     rax, rsp
0x18000ba67  mov     [rsp+0D8h+var_48], rax
0x18000ba6f  mov     r14, rcx
0x18000ba72  mov     [rsp+0D8h+var_90], rcx
0x18000ba77  xor     r9d, r9d; lpName
0x18000ba7a  xor     r8d, r8d; bInitialState
0x18000ba7d  xor     edx, edx; bManualReset
0x18000ba7f  xor     ecx, ecx; lpEventAttributes
0x18000ba81  call    cs:__imp_CreateEventW
0x18000ba87  mov     [r14], rax
0x18000ba8a  test    rax, rax
0x18000ba8d  jnz     short loc_18000BAFC
0x18000ba8f  call    cs:__imp_GetLastError
0x18000ba95  mov     esi, eax
0x18000ba97  mov     edi, 1
0x18000ba9c  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000baa3  jz      loc_18000BE10
0x18000baa9  mov     [rsp+0D8h+var_A8], eax
0x18000baad  lea     rax, aCouldNotCreate; "Could not create event."
0x18000bab4  mov     [rsp+0D8h+var_60], 18h
0x18000babd  mov     [rsp+0D8h+var_68], rax
0x18000bac2  lea     rax, [rsp+0D8h+var_A8]
0x18000bac7  mov     [rsp+0D8h+var_58], rax
0x18000bacf  mov     [rsp+0D8h+var_50], 4
0x18000badb  lea     rax, [rsp+0D8h+var_78]
0x18000bae0  mov     [rsp+0D8h+var_B8], rax
0x18000bae5  mov     r9d, 3
0x18000baeb  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000baf2  call    McGenEventWrite_EventWriteTransfer
0x18000baf7  jmp     loc_18000BE10
0x18000bafc  mov     r8, r14; lpContext
0x18000baff  lea     rdx, ?ScmNotificationHandler@IPxlatSvcControl@@CAKKKPEAX0@Z; lpHandlerProc
0x18000bb06  lea     rcx, ServiceName; "IPxlatCfgSvc"
0x18000bb0d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000bb13  mov     [r14+28h], rax
0x18000bb17  test    rax, rax
0x18000bb1a  jnz     short loc_18000BB4F
0x18000bb1c  call    cs:__imp_GetLastError
0x18000bb22  mov     esi, eax
0x18000bb24  mov     edi, 1
0x18000bb29  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bb30  jz      loc_18000BE10
0x18000bb36  mov     [rsp+0D8h+var_A8], eax
0x18000bb3a  lea     rax, aCouldNotRegist_0; "Could not register with SCM."
0x18000bb41  mov     [rsp+0D8h+var_60], 1Dh
0x18000bb4a  jmp     loc_18000BABD
0x18000bb4f  lea     r12, [r14+8]
0x18000bb53  mov     dword ptr [r12], 20h ; ' '
0x18000bb5b  mov     qword ptr [r14+0Ch], 2
0x18000bb63  mov     rdx, r12; lpServiceStatus
0x18000bb66  mov     rcx, rax; hServiceStatus
0x18000bb69  call    cs:__imp_SetServiceStatus
0x18000bb6f  test    eax, eax
0x18000bb71  jnz     short loc_18000BBA6
0x18000bb73  call    cs:__imp_GetLastError
0x18000bb79  mov     esi, eax
0x18000bb7b  mov     edi, 1
0x18000bb80  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bb87  jz      loc_18000BE10
0x18000bb8d  mov     [rsp+0D8h+var_A8], eax
0x18000bb91  lea     rax, aCouldNotUpdate_0; "Could not update service status to star"...
0x18000bb98  mov     [rsp+0D8h+var_60], 32h ; '2'
0x18000bba1  jmp     loc_18000BABD
0x18000bba6  mov     rcx, r14; this
0x18000bba9  call    ?UpdateWinNatDriver@IPxlatSvcControl@@AEAAK_N@Z; IPxlatSvcControl::UpdateWinNatDriver(bool)
0x18000bbae  mov     esi, eax
0x18000bbb0  test    eax, eax
0x18000bbb2  jz      short loc_18000BBDF
0x18000bbb4  mov     edi, 1
0x18000bbb9  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bbc0  jz      loc_18000BE10
0x18000bbc6  mov     [rsp+0D8h+var_A8], eax
0x18000bbca  lea     rax, aCouldNotLoadWi; "Could not load WinNat driver."
0x18000bbd1  mov     [rsp+0D8h+var_60], 1Eh
0x18000bbda  jmp     loc_18000BABD
0x18000bbdf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl(void)'::`2'::impl
0x18000bbe6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(void)
0x18000bbeb  test    al, al
0x18000bbed  jz      loc_18000BC82
0x18000bbf3  lea     rdx, qword_18001A360; IfSpec
0x18000bbfa  lea     rcx, Endpoint; "IPxlatRpc"
0x18000bc01  call    InitializeIPxlatRpcServer
0x18000bc06  mov     esi, eax
0x18000bc08  test    eax, eax
0x18000bc0a  jz      short loc_18000BC37
0x18000bc0c  mov     edi, 1
0x18000bc11  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bc18  jz      loc_18000BE10
0x18000bc1e  mov     [rsp+0D8h+var_A8], eax
0x18000bc22  lea     rax, aCouldNotInitia_0; "Could not initialize RPC server."
0x18000bc29  mov     [rsp+0D8h+var_60], 21h ; '!'
0x18000bc32  jmp     loc_18000BABD
0x18000bc37  lea     rdx, qword_18001A740; IfSpec
0x18000bc3e  lea     rcx, aIpxlatrpc1; "IPxlatRpc1"
0x18000bc45  call    InitializeIPxlatRpcServer
0x18000bc4a  mov     r15d, eax
0x18000bc4d  mov     [rsp+0D8h+var_A8], eax
0x18000bc51  test    eax, eax
0x18000bc53  jz      short loc_18000BC99
0x18000bc55  mov     esi, eax
0x18000bc57  mov     edi, 1
0x18000bc5c  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bc63  jz      loc_18000BE10
0x18000bc69  mov     [rsp+0D8h+var_A8], eax
0x18000bc6d  lea     rax, aCouldNotInitia; "Could not initialize Query RPC server."
0x18000bc74  mov     [rsp+0D8h+var_60], 27h ; '''
0x18000bc7d  jmp     loc_18000BABD
0x18000bc82  call    InitializeIPxlatRpcServer_Scrap
0x18000bc87  mov     r15d, eax
0x18000bc8a  mov     [rsp+0D8h+var_A8], eax
0x18000bc8e  test    eax, eax
0x18000bc90  jz      short loc_18000BC99
0x18000bc92  mov     esi, eax
0x18000bc94  jmp     loc_18000BC0C
0x18000bc99  mov     ecx, 0A0h; Size
0x18000bc9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bca3  mov     [rsp+0D8h+var_98], rax
0x18000bca8  mov     rdx, [r14]; void *
0x18000bcab  mov     rcx, rax; this
0x18000bcae  call    ??0IPxlatInterfaceMgr@@QEAA@PEAX@Z; IPxlatInterfaceMgr::IPxlatInterfaceMgr(void *)
0x18000bcb3  mov     rsi, rax
0x18000bcb6  mov     [rsp+0D8h+var_98], rax
0x18000bcbb  mov     ecx, 18h; Size
0x18000bcc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bcc5  mov     edi, 1
0x18000bcca  mov     [rax+8], edi
0x18000bccd  mov     [rax+0Ch], edi
0x18000bcd0  lea     rcx, ??_7?$_Ref_count@VIPxlatInterfaceMgr@@@std@@6B@; const std::_Ref_count<IPxlatInterfaceMgr>::`vftable'
0x18000bcd7  mov     [rax], rcx
0x18000bcda  mov     [rax+10h], rsi
0x18000bcde  mov     [r14+48h], rsi
0x18000bce2  mov     rsi, [r14+50h]
0x18000bce6  mov     [r14+50h], rax
0x18000bcea  test    rsi, rsi
0x18000bced  jz      short loc_18000BD25
0x18000bcef  or      eax, 0FFFFFFFFh
0x18000bcf2  lock xadd [rsi+8], eax
0x18000bcf7  cmp     eax, edi
0x18000bcf9  jnz     short loc_18000BD25
0x18000bcfb  mov     rax, [rsi]
0x18000bcfe  mov     rcx, rsi
0x18000bd01  mov     rax, [rax]
0x18000bd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd09  or      eax, 0FFFFFFFFh
0x18000bd0c  lock xadd [rsi+0Ch], eax
0x18000bd11  cmp     eax, edi
0x18000bd13  jnz     short loc_18000BD25
0x18000bd15  mov     rax, [rsi]
0x18000bd18  mov     rcx, rsi
0x18000bd1b  mov     rax, [rax+8]
0x18000bd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd24  nop
0x18000bd25  mov     dword ptr [r12], 20h ; ' '
0x18000bd2d  mov     dword ptr [r14+10h], 5
0x18000bd35  mov     dword ptr [r14+0Ch], 4
0x18000bd3d  mov     rdx, r12; lpServiceStatus
0x18000bd40  mov     rcx, [r14+28h]; hServiceStatus
0x18000bd44  call    cs:__imp_SetServiceStatus
0x18000bd4a  test    eax, eax
0x18000bd4c  jnz     short loc_18000BDAF
0x18000bd4e  call    cs:__imp_GetLastError
0x18000bd54  mov     esi, eax
0x18000bd56  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000bd5d  jz      short loc_18000BDD7
0x18000bd5f  mov     [rsp+0D8h+var_A8], eax
0x18000bd63  lea     rax, aCouldNotUpdate_3; "Could not update service status to runn"...
0x18000bd6a  mov     [rsp+0D8h+var_68], rax
0x18000bd6f  mov     [rsp+0D8h+var_60], 2Ch ; ','
0x18000bd78  lea     rax, [rsp+0D8h+var_A8]
0x18000bd7d  mov     [rsp+0D8h+var_58], rax
0x18000bd85  mov     [rsp+0D8h+var_50], 4
0x18000bd91  lea     rax, [rsp+0D8h+var_78]
0x18000bd96  mov     [rsp+0D8h+var_B8], rax
0x18000bd9b  mov     r9d, 3
0x18000bda1  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000bda8  call    McGenEventWrite_EventWriteTransfer
0x18000bdad  jmp     short loc_18000BDD7
0x18000bdaf  xor     eax, eax
0x18000bdb1  lock cmpxchg [r14+30h], edi
0x18000bdb7  mov     rcx, [r14+48h]; this
0x18000bdbb  call    ?WaitForXlatInterfaces@IPxlatInterfaceMgr@@QEAAKXZ; IPxlatInterfaceMgr::WaitForXlatInterfaces(void)
0x18000bdc0  mov     esi, eax
0x18000bdc2  jmp     short loc_18000BDD7
0x18000bdc4  mov     r14, [rsp+0D8h+var_90]
0x18000bdc9  mov     r15d, [rsp+0D8h+var_A8]
0x18000bdce  mov     esi, [rsp+0D8h+var_A0]
0x18000bdd2  mov     edi, 1
0x18000bdd7  test    r15d, r15d
0x18000bdda  jnz     short loc_18000BE10
0x18000bddc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl(void)'::`2'::impl
0x18000bde3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(void)
0x18000bde8  xor     r8d, r8d; WaitForCallsToComplete
0x18000bdeb  xor     edx, edx; MgrTypeUuid
0x18000bded  test    al, al
0x18000bdef  jz      short loc_18000BE03
0x18000bdf1  lea     rcx, qword_18001A740; IfSpec
0x18000bdf8  call    cs:__imp_RpcServerUnregisterIf
0x18000bdfe  xor     r8d, r8d; WaitForCallsToComplete
0x18000be01  xor     edx, edx; MgrTypeUuid
0x18000be03  lea     rcx, qword_18001A360; IfSpec
0x18000be0a  call    cs:__imp_RpcServerUnregisterIf
0x18000be10  mov     qword ptr [r14+0Ch], 1
0x18000be18  mov     [r14+14h], esi
0x18000be1c  lea     rdx, [r14+8]; lpServiceStatus
0x18000be20  mov     rcx, [r14+28h]; hServiceStatus
0x18000be24  call    cs:__imp_SetServiceStatus
0x18000be2a  test    eax, eax
0x18000be2c  jnz     short loc_18000BE8D
0x18000be2e  call    cs:__imp_GetLastError
0x18000be34  mov     esi, eax
0x18000be36  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000be3d  jz      short loc_18000BE8D
0x18000be3f  mov     dword ptr [rsp+0D8h+var_98], eax
0x18000be43  lea     rax, aCouldNotUpdate_2; "Could not update service status to stop"...
0x18000be4a  mov     [rsp+0D8h+var_68], rax
0x18000be4f  mov     [rsp+0D8h+var_60], 2Ch ; ','
0x18000be58  lea     rax, [rsp+0D8h+var_98]
0x18000be5d  mov     [rsp+0D8h+var_58], rax
0x18000be65  mov     [rsp+0D8h+var_50], 4
0x18000be71  lea     rax, [rsp+0D8h+var_78]
0x18000be76  mov     [rsp+0D8h+var_B8], rax
0x18000be7b  mov     r9d, 3
0x18000be81  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000be88  call    McGenEventWrite_EventWriteTransfer
0x18000be8d  mov     rcx, [r14]; hObject
0x18000be90  call    cs:__imp_CloseHandle
0x18000be96  xor     eax, eax
0x18000be98  lock cmpxchg [r14+34h], edi
0x18000be9e  mov     eax, esi
0x18000bea0  mov     rcx, [rsp+0D8h+var_48]
0x18000bea8  xor     rcx, rsp; StackCookie
0x18000beab  call    __security_check_cookie
0x18000beb0  add     rsp, 0A8h
0x18000beb7  pop     r15
0x18000beb9  pop     r14
0x18000bebb  pop     r12
0x18000bebd  pop     rdi
0x18000bebe  pop     rsi
0x18000bebf  pop     rbx
0x18000bec0  retn
0x18000bec1  jmp     loc_18000BDC4
0x18000bec6  jmp     loc_18000BDC4
```
