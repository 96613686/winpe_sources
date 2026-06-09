# IPxlatInterface::IPxlatInterface(unsigned __int64,ulong,in_addr,in_addr,uchar,_IPV6_PREFIX *,_IPV6_PREFIX *,_IPXLAT_TRIGGER_SOURCE)

- ea: `0x1800128d0`
- end: `0x1800131ca`
- name: `??0IPxlatInterface@@QEAA@_KKUin_addr@@1EPEAU_IPV6_PREFIX@@2W4_IPXLAT_TRIGGER_SOURCE@@@Z`
- size: `2298`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, int, char, __int64, void *, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f9f0`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180002a34`
- `0x18000b12c`
- `0x18000c1cc`
- `0x18000c224`
- `0x18000dcc8`
- `0x18000f184`
- `0x180011dc0`
- `0x180011f3c`
- `0x180012290`
- `0x1800122a0`
- `0x180012430`
- `0x180012620`
- `0x1800128d0`
- `0x180013720`
- `0x180017710`
- `0x180017930`
- `0x1800179d0`
- `0x180017e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013193`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012dfc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012dfc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012db4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012dd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012db4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012dd1`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180012d7a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180012d97`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180012d7a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180012d97`
- `RPCRT4!UuidCreate` at `0x180012956`
- `RPCRT4!UuidCreate` at `0x180012956`
- `NSI!NsiGetAllParameters` at `0x1800129eb`
- `NSI!NsiGetAllParameters` at `0x1800129eb`

## string_xrefs

- `0x180013000`: `Reading Registry Configuration Failed`
- `0x1800130a7`: `CreateWaitableTimer failed for DNS query time`
- `0x1800130e6`: `CreateWaitableTimer failed for DNS ttl timer`
- `0x180013125`: `CreateEvent failed for exit thread event`
- `0x180013164`: `CreateEvent failed for IP state change event`
- `0x1800131a3`: `CreateThread failed`
- `0x180012e18`: `Successfully created interface object`

## pseudocode

```c
__int64 __fastcall IPxlatInterface::IPxlatInterface(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        char a6,
        __int64 a7,
        void *a8,
        int a9)
{
  __int64 v9; // r14
  unsigned __int8 *v10; // rsi
  unsigned int v12; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  unsigned __int8 v17; // al
  char v18; // al
  unsigned __int8 v19; // al
  char v20; // al
  int v21; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned __int64 IsEnabled; // rax
  __int64 v25; // rcx
  unsigned __int8 v26; // r11
  int v27; // r9d
  unsigned __int8 i; // r10
  int v29; // edx
  char v30; // al
  __int64 v31; // rcx
  __int64 v32; // r8
  HANDLE WaitableTimer; // rax
  HANDLE v34; // rax
  HANDLE EventW; // rax
  HANDLE v36; // rax
  HANDLE Thread; // rax
  __int64 v38; // rcx
  __int64 v39; // r8
  char v40; // al
  int v41; // ebx
  char v42; // r11
  __int64 v43; // r8
  char v44; // r9
  __int64 v45; // r10
  char v46; // dl
  int v47; // ecx
  const struct std::error_category *v49; // rax
  const struct std::error_category *v50; // rax
  int v51; // edx
  const struct std::error_category *v52; // rax
  const struct std::error_category *v53; // rax
  const struct std::error_category *v54; // rax
  int v55; // edx
  const struct std::error_category *v56; // rax
  int v57; // edx
  const struct std::error_category *v58; // rax
  int v59; // edx
  const struct std::error_category *v60; // rax
  int v61; // edx
  const struct std::error_category *v62; // rax
  int v63; // edx
  unsigned int v64; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v65; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v66[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v67[130]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v68; // [rsp+288h] [rbp+188h]
  __int128 v69; // [rsp+298h] [rbp+198h]
  int v70; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v71[532]; // [rsp+2E4h] [rbp+1E4h] BYREF
  unsigned __int16 v72; // [rsp+4F8h] [rbp+3F8h]
  _BYTE Src[566]; // [rsp+4FAh] [rbp+3FAh] BYREF
  __int128 pExceptionObject; // [rsp+730h] [rbp+630h] BYREF
  const char *v75; // [rsp+740h] [rbp+640h]
  __int64 v76; // [rsp+748h] [rbp+648h]
  __int64 *v77; // [rsp+750h] [rbp+650h]
  __int64 v78; // [rsp+758h] [rbp+658h]

  v9 = a7;
  v10 = (unsigned __int8 *)a8;
  *(_DWORD *)(a1 + 28) = 0;
  *(_OWORD *)(a1 + 36) = 0;
  *(_BYTE *)(a1 + 52) = 0;
  v12 = a3;
  *(_OWORD *)(a1 + 53) = 0;
  *(_BYTE *)(a1 + 69) = 0;
  *(_DWORD *)(a1 + 224) = 0;
  v64 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl'::`2'::impl)
    && UuidCreate((UUID *)(a1 + 208)) )
  {
    *(_OWORD *)(a1 + 208) = 0;
  }
  *(_QWORD *)a1 = a2;
  v70 = 0;
  memset_0(v71, 0, 0x440u);
  memset_0(v67, 0, 0x258u);
  v65 = a2;
  if ( (unsigned int)NsiGetAllParameters(1, &NPI_MS_NDIS_MODULEID, 0, &v65, 8, &v70, 1092, 0, 0, v67, 600) )
  {
    v49 = std::system_category();
    std::system_error::system_error((std::system_error *)&pExceptionObject, 632, v49, "Interface does not exist");
    throw (std::system_error *)&pExceptionObject;
  }
  *(_DWORD *)(a1 + 8) = v67[0];
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::GetImpl'::`2'::impl) )
    *(_OWORD *)(a1 + 12) = v69;
  if ( v72 > 0x20u )
    *(_WORD *)(a1 + 186) = 32;
  else
    *(_WORD *)(a1 + 186) = v72;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl'::`2'::impl) )
    *(_DWORD *)(a1 + 28) = v68;
  memcpy_0((void *)(a1 + 154), Src, *(unsigned __int16 *)(a1 + 186));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)(a1 + 28);
    if ( (unsigned int)(v15 - 243) > 1 && v15 != 237 )
    {
      pExceptionObject = 0;
      LODWORD(v75) = 0;
      if ( (unsigned int)IPxlatPolicyMgrReadConfiguration(&pExceptionObject) )
      {
        v50 = std::system_category();
        std::system_error::system_error(
          (std::system_error *)&pExceptionObject,
          v51,
          v50,
          "Reading Registry Configuration Failed");
        throw (std::system_error *)&pExceptionObject;
      }
      *(_QWORD *)(a1 + 192) = *(_QWORD *)((char *)&pExceptionObject + 4);
      *(_DWORD *)(a1 + 200) = HIDWORD(pExceptionObject);
    }
  }
  if ( v12 > 0x270F && v12 != -1 )
  {
    v52 = std::system_category();
    std::system_error::system_error((std::system_error *)&pExceptionObject, 87, v52, "Metric is invalid");
    throw (std::system_error *)&pExceptionObject;
  }
  v16 = 0x101010101LL;
  if ( v9 )
  {
    v17 = *(_BYTE *)(v9 + 16) - 32;
    if ( v17 <= 0x20u && _bittest64(&v16, v17) || (v18 = 0, *(_BYTE *)(v9 + 16) == 96) )
      v18 = 1;
    if ( !v18 )
      goto LABEL_87;
  }
  if ( v10 )
  {
    v19 = v10[16] - 32;
    if ( v19 <= 0x20u && _bittest64(&v16, v19) || (v20 = 0, v10[16] == 96) )
      v20 = 1;
    if ( !v20 )
    {
LABEL_87:
      v53 = std::system_category();
      std::system_error::system_error((std::system_error *)&pExceptionObject, 87, v53, "Prefix invalid");
      throw (std::system_error *)&pExceptionObject;
    }
  }
  *(_DWORD *)(a1 + 128) = a4;
  v21 = a5;
  *(_DWORD *)(a1 + 32) = v12;
  *(_BYTE *)(a1 + 70) = v9 != 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 132) = v21;
  *(_BYTE *)(a1 + 71) = v10 != 0;
  *(_BYTE *)(a1 + 152) = a6;
  *(_DWORD *)(a1 + 188) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl'::`2'::impl) )
    *(_DWORD *)(a1 + 204) = -(v9 != 0);
  *(_BYTE *)(a1 + 153) = 32;
  *(_OWORD *)(a1 + 136) = 0;
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    LODWORD(v65) = v21;
    v75 = (const char *)v66;
    v66[0] = a2;
    v76 = 8;
    v77 = &v65;
    v78 = 4;
    McGenEventWrite_EventWriteTransfer(v22, IPXLATCFG_SYNTHETIC_IPV4_EVENT, v23, 3, &pExceptionObject);
  }
  if ( *(_BYTE *)(a1 + 70) )
  {
    *(_BYTE *)(a1 + 52) = *(_BYTE *)(v9 + 16);
    *(_OWORD *)(a1 + 36) = *(_OWORD *)v9;
  }
  if ( *(_BYTE *)(a1 + 71) )
  {
    *(_BYTE *)(a1 + 69) = v10[16];
    *(_OWORD *)(a1 + 53) = *(_OWORD *)v10;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl'::`2'::impl);
    if ( !(_BYTE)IsEnabled )
    {
      LOBYTE(IsEnabled) = v10[16] - 32;
      if ( (unsigned __int8)IsEnabled <= 0x20u && (v25 = 0x101010101LL, _bittest64(&v25, IsEnabled)) || v10[16] == 96 )
      {
        v26 = 0;
        v27 = v10[16] >> 3;
        for ( i = 0; i < 4u; ++i )
        {
          v29 = i;
          v30 = *((_BYTE *)&a5 + i);
          if ( v27 + i == 8 )
            v26 = 1;
          *(_BYTE *)(v29 + v27 + (unsigned int)v26 + a1 + 136) = v30;
        }
        v12 = v64;
      }
      memcpy_0((void *)(a1 + 136), v10, (unsigned __int64)v10[16] >> 3);
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
      {
        v77 = (__int64 *)(a1 + 136);
        v75 = (const char *)v66;
        v66[0] = a2;
        v76 = 8;
        v78 = 16;
        McGenEventWrite_EventWriteTransfer(v31, IPXLATCFG_SYNTHETIC_IPV6_EVENT, v32, 3, &pExceptionObject);
      }
    }
  }
  *(_QWORD *)(a1 + 120) = -300000000;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 104) = WaitableTimer;
  if ( !WaitableTimer )
  {
    IPxlatInterface::Cleanup((IPxlatInterface *)a1);
    GetLastError();
    v54 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)&pExceptionObject,
      v55,
      v54,
      "CreateWaitableTimer failed for DNS query time");
    throw (std::system_error *)&pExceptionObject;
  }
  v34 = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 112) = v34;
  if ( !v34 )
  {
    IPxlatInterface::Cleanup((IPxlatInterface *)a1);
    GetLastError();
    v56 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)&pExceptionObject,
      v57,
      v56,
      "CreateWaitableTimer failed for DNS ttl timer");
    throw (std::system_error *)&pExceptionObject;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( !EventW )
  {
    IPxlatInterface::Cleanup((IPxlatInterface *)a1);
    GetLastError();
    v58 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)&pExceptionObject,
      v59,
      v58,
      "CreateEvent failed for exit thread event");
    throw (std::system_error *)&pExceptionObject;
  }
  v36 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 96) = v36;
  if ( !v36 )
  {
    IPxlatInterface::Cleanup((IPxlatInterface *)a1);
    GetLastError();
    v60 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)&pExceptionObject,
      v61,
      v60,
      "CreateEvent failed for IP state change event");
    throw (std::system_error *)&pExceptionObject;
  }
  Thread = CreateThread(0, 0, IPxlatInterface::InterfaceTriggerHandler, (LPVOID)a1, 0, 0);
  *(_QWORD *)(a1 + 80) = Thread;
  if ( !Thread )
  {
    IPxlatInterface::Cleanup((IPxlatInterface *)a1);
    GetLastError();
    v62 = std::system_category();
    std::system_error::system_error((std::system_error *)&pExceptionObject, v63, v62, "CreateThread failed");
    throw (std::system_error *)&pExceptionObject;
  }
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    v66[0] = a2;
    v75 = "Successfully created interface object";
    v76 = 38;
    v77 = v66;
    v78 = 8;
    McGenEventWrite_EventWriteTransfer(v38, IPXLATCFG_INTERFACE_INFO_EVENT, v39, 3, &pExceptionObject);
  }
  v40 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl'::`2'::impl);
  v41 = a9;
  if ( v40 )
  {
    v64 = *(_DWORD *)(a1 + 28);
    LODWORD(v65) = a9;
    IPxlatTelemetry::IPxlatEnabled<_GUID &,unsigned int,unsigned int>(a1 + 208, &v65, &v64);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl'::`2'::impl) )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) != 0 )
    {
      if ( v10 )
        v42 = v10[16];
      else
        v42 = 0;
      v43 = (__int64)v10;
      if ( !v10 )
        v43 = 0;
      if ( v9 )
        v44 = *(_BYTE *)(v9 + 16);
      else
        v44 = 0;
      v45 = v9;
      if ( !v9 )
        v45 = 0;
      McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer(
        v9 != 0 ? 0x10 : 0,
        (unsigned int)IPXLATCFG_ENABLE_XLAT_EVENT,
        v41,
        a2,
        v12,
        v9 != 0 ? 0x10 : 0,
        v45,
        v44,
        v10 != 0 ? 0x10 : 0,
        v43,
        v42);
    }
  }
  else if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) != 0 )
  {
    if ( v10 )
      v46 = v10[16];
    else
      v46 = 0;
    if ( !v10 )
      v10 = 0;
    if ( v9 )
      v47 = *(unsigned __int8 *)(v9 + 16);
    else
      v47 = 0;
    if ( !v9 )
      v9 = 0;
    McTemplateU0xqb16qb16q_EventWriteTransfer(
      v47,
      (unsigned int)IPXLATCFG_ENABLE_XLAT_EVENT_OLD,
      a2,
      v12,
      v9,
      v47,
      (__int64)v10,
      v46);
  }
  return a1;
}

```

## disassembly

```asm
0x1800128d0  push    rbp
0x1800128d2  push    rbx
0x1800128d3  push    rsi
0x1800128d4  push    rdi
0x1800128d5  push    r12
0x1800128d7  push    r13
0x1800128d9  push    r14
0x1800128db  push    r15
0x1800128dd  lea     rbp, [rsp-678h]
0x1800128e5  sub     rsp, 778h
0x1800128ec  mov     rax, cs:__security_cookie
0x1800128f3  xor     rax, rsp
0x1800128f6  mov     [rbp+6B0h+var_50], rax
0x1800128fd  mov     r14, [rbp+6B0h+arg_30]
0x180012904  xor     eax, eax
0x180012906  mov     rsi, [rbp+6B0h+arg_38]
0x18001290d  xorps   xmm0, xmm0
0x180012910  mov     dword ptr [rcx+1Ch], 0
0x180012917  mov     ebx, r9d
0x18001291a  movups  xmmword ptr [rcx+24h], xmm0
0x18001291e  mov     [rcx+34h], al
0x180012921  mov     r13d, r8d
0x180012924  movups  xmmword ptr [rcx+35h], xmm0
0x180012928  mov     [rcx+45h], al
0x18001292b  mov     r12, rdx
0x18001292e  mov     [rcx+0E0h], eax
0x180012934  mov     rdi, rcx
0x180012937  mov     [rsp+7B0h+var_750], r8d
0x18001293c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl(void)'::`2'::impl
0x180012943  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(void)
0x180012948  test    al, al
0x18001294a  jz      short loc_180012967
0x18001294c  lea     r15, [rdi+0D0h]
0x180012953  mov     rcx, r15; Uuid
0x180012956  call    cs:__imp_UuidCreate
0x18001295c  test    eax, eax
0x18001295e  jz      short loc_180012967
0x180012960  xorps   xmm0, xmm0
0x180012963  movups  xmmword ptr [r15], xmm0
0x180012967  xor     edx, edx; Val
0x180012969  mov     [rdi], r12
0x18001296c  mov     r8d, 440h; Size
0x180012972  mov     [rbp+6B0h+var_4D0], 0
0x18001297c  lea     rcx, [rbp+6B0h+var_4CC]; void *
0x180012983  call    memset_0
0x180012988  mov     r15d, 258h
0x18001298e  lea     rcx, [rbp+6B0h+var_730]; void *
0x180012992  mov     r8d, r15d; Size
0x180012995  xor     edx, edx; Val
0x180012997  call    memset_0
0x18001299c  mov     [rsp+7B0h+var_760], r15d
0x1800129a1  lea     rax, [rbp+6B0h+var_730]
0x1800129a5  mov     [rsp+7B0h+var_768], rax
0x1800129aa  lea     r9, [rsp+7B0h+var_748]
0x1800129af  xor     r15d, r15d
0x1800129b2  mov     [rsp+7B0h+var_748], r12
0x1800129b7  mov     [rsp+7B0h+var_770], r15d
0x1800129bc  lea     rax, [rbp+6B0h+var_4D0]
0x1800129c3  mov     [rsp+7B0h+var_778], r15
0x1800129c8  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800129cf  mov     dword ptr [rsp+7B0h+var_780], 444h
0x1800129d7  xor     r8d, r8d
0x1800129da  mov     [rsp+7B0h+lpThreadId], rax
0x1800129df  lea     ecx, [r15+1]
0x1800129e3  mov     [rsp+7B0h+dwCreationFlags], 8
0x1800129eb  call    cs:__imp_NsiGetAllParameters
0x1800129f1  test    eax, eax
0x1800129f3  jnz     loc_180012FC4
0x1800129f9  mov     eax, [rbp+6B0h+var_730]
0x1800129fc  mov     [rdi+8], eax
0x1800129ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS> `wil::Feature<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::GetImpl(void)'::`2'::impl
0x180012a06  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::__private_IsEnabled(void)
0x180012a0b  test    al, al
0x180012a0d  jz      short loc_180012A1B
0x180012a0f  movups  xmm0, [rbp+6B0h+var_518]
0x180012a16  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180012a1b  movzx   eax, [rbp+6B0h+var_2B8]
0x180012a22  mov     ecx, 20h ; ' '
0x180012a27  cmp     ax, cx
0x180012a2a  ja      short loc_180012A35
0x180012a2c  mov     [rdi+0BAh], ax
0x180012a33  jmp     short loc_180012A3C
0x180012a35  mov     [rdi+0BAh], cx
0x180012a3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl(void)'::`2'::impl
0x180012a43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(void)
0x180012a48  test    al, al
0x180012a4a  jz      short loc_180012A56
0x180012a4c  movzx   eax, [rbp+6B0h+var_528]
0x180012a53  mov     [rdi+1Ch], eax
0x180012a56  movzx   r8d, word ptr [rdi+0BAh]; Size
0x180012a5e  lea     rcx, [rdi+9Ah]; void *
0x180012a65  lea     rdx, [rbp+6B0h+Src]; Src
0x180012a6c  call    memcpy_0
0x180012a71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x180012a78  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)
0x180012a7d  test    al, al
0x180012a7f  jz      short loc_180012AE3
0x180012a81  mov     ecx, [rdi+1Ch]
0x180012a84  lea     eax, [rcx-0F3h]
0x180012a8a  cmp     eax, 1
0x180012a8d  jbe     short loc_180012AE3
0x180012a8f  cmp     ecx, 0EDh
0x180012a95  jz      short loc_180012AE3
0x180012a97  xorps   xmm0, xmm0
0x180012a9a  lea     rcx, [rbp+6B0h+pExceptionObject]
0x180012aa1  xor     eax, eax
0x180012aa3  movups  [rbp+6B0h+pExceptionObject], xmm0
0x180012aaa  mov     dword ptr [rbp+6B0h+var_70], eax
0x180012ab0  call    IPxlatPolicyMgrReadConfiguration
0x180012ab5  mov     edx, eax
0x180012ab7  test    eax, eax
0x180012ab9  jnz     loc_180012FF8
0x180012abf  mov     eax, dword ptr [rbp+6B0h+pExceptionObject+4]
0x180012ac5  mov     [rdi+0C0h], eax
0x180012acb  mov     eax, dword ptr [rbp+6B0h+pExceptionObject+8]
0x180012ad1  mov     [rdi+0C4h], eax
0x180012ad7  mov     eax, dword ptr [rbp+6B0h+pExceptionObject+0Ch]
0x180012add  mov     [rdi+0C8h], eax
0x180012ae3  cmp     r13d, 270Fh
0x180012aea  jbe     short loc_180012AF6
0x180012aec  cmp     r13d, 0FFFFFFFFh
0x180012af0  jnz     loc_180013027
0x180012af6  mov     rdx, 101010101h
0x180012b00  mov     ecx, 20h ; ' '
0x180012b05  test    r14, r14
0x180012b08  jz      short loc_180012B31
0x180012b0a  mov     al, [r14+10h]
0x180012b0e  sub     al, cl
0x180012b10  cmp     al, cl
0x180012b12  ja      short loc_180012B1D
0x180012b14  movzx   eax, al
0x180012b17  bt      rdx, rax
0x180012b1b  jb      short loc_180012B27
0x180012b1d  cmp     byte ptr [r14+10h], 60h ; '`'
0x180012b22  mov     al, r15b
0x180012b25  jnz     short loc_180012B29
0x180012b27  mov     al, 1
0x180012b29  test    al, al
0x180012b2b  jz      loc_18001305B
0x180012b31  test    rsi, rsi
0x180012b34  jz      short loc_180012B5B
0x180012b36  mov     al, [rsi+10h]
0x180012b39  sub     al, cl
0x180012b3b  cmp     al, cl
0x180012b3d  ja      short loc_180012B48
0x180012b3f  movzx   eax, al
0x180012b42  bt      rdx, rax
0x180012b46  jb      short loc_180012B51
0x180012b48  cmp     byte ptr [rsi+10h], 60h ; '`'
0x180012b4c  mov     al, r15b
0x180012b4f  jnz     short loc_180012B53
0x180012b51  mov     al, 1
0x180012b53  test    al, al
0x180012b55  jz      loc_18001305B
0x180012b5b  test    r14, r14
0x180012b5e  mov     [rdi+80h], ebx
0x180012b64  mov     ebx, [rbp+6B0h+arg_20]
0x180012b6a  setnz   al
0x180012b6d  mov     [rdi+20h], r13d
0x180012b71  mov     [rdi+46h], al
0x180012b74  test    rsi, rsi
0x180012b77  mov     [rdi+48h], r15d
0x180012b7b  setnz   al
0x180012b7e  mov     [rdi+84h], ebx
0x180012b84  mov     [rdi+47h], al
0x180012b87  mov     al, [rbp+6B0h+arg_28]
0x180012b8d  mov     [rdi+98h], al
0x180012b93  mov     [rdi+0BCh], r15d
0x180012b9a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl(void)'::`2'::impl
0x180012ba1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(void)
0x180012ba6  test    al, al
0x180012ba8  jz      short loc_180012BBB
0x180012baa  mov     rax, r15
0x180012bad  sub     rax, r14
0x180012bb0  neg     rax
0x180012bb3  sbb     eax, eax
0x180012bb5  mov     [rdi+0CCh], eax
0x180012bbb  mov     byte ptr [rdi+99h], 20h ; ' '
0x180012bc2  lea     r15, [rdi+88h]
0x180012bc9  xorps   xmm0, xmm0
0x180012bcc  movups  xmmword ptr [r15], xmm0
0x180012bd0  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180012bd7  jz      short loc_180012C30
0x180012bd9  lea     rax, [rsp+7B0h+var_740]
0x180012bde  mov     dword ptr [rsp+7B0h+var_748], ebx
0x180012be2  mov     [rbp+6B0h+var_70], rax
0x180012be9  lea     rdx, IPXLATCFG_SYNTHETIC_IPV4_EVENT
0x180012bf0  xor     ebx, ebx
0x180012bf2  mov     [rsp+7B0h+var_740], r12
0x180012bf7  lea     rax, [rsp+7B0h+var_748]
0x180012bfc  mov     [rbp+6B0h+var_68], 8
0x180012c07  mov     [rbp+6B0h+var_60], rax
0x180012c0e  lea     rax, [rbp+6B0h+pExceptionObject]
0x180012c15  mov     qword ptr [rsp+7B0h+dwCreationFlags], rax
0x180012c1a  lea     r9d, [rbx+3]
0x180012c1e  mov     [rbp+6B0h+var_58], 4
0x180012c29  call    McGenEventWrite_EventWriteTransfer
0x180012c2e  jmp     short loc_180012C32
0x180012c30  xor     ebx, ebx
0x180012c32  cmp     [rdi+46h], bl
0x180012c35  jz      short loc_180012C47
0x180012c37  mov     al, [r14+10h]
0x180012c3b  mov     [rdi+34h], al
0x180012c3e  movups  xmm0, xmmword ptr [r14]
0x180012c42  movdqu  xmmword ptr [rdi+24h], xmm0
0x180012c47  cmp     [rdi+47h], bl
0x180012c4a  jz      loc_180012D4C
0x180012c50  mov     al, [rsi+10h]
0x180012c53  mov     [rdi+45h], al
0x180012c56  movups  xmm0, xmmword ptr [rsi]
0x180012c59  movdqu  xmmword ptr [rdi+35h], xmm0
0x180012c5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl(void)'::`2'::impl
0x180012c65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(void)
0x180012c6a  test    al, al
0x180012c6c  jnz     loc_180012D4C
0x180012c72  mov     al, [rsi+10h]
0x180012c75  sub     al, 20h ; ' '
0x180012c77  cmp     al, 20h ; ' '
0x180012c79  ja      short loc_180012C8B
0x180012c7b  mov     rcx, 101010101h
0x180012c85  bt      rcx, rax
0x180012c89  jb      short loc_180012C91
0x180012c8b  cmp     byte ptr [rsi+10h], 60h ; '`'
0x180012c8f  jnz     short loc_180012CE0
0x180012c91  movzx   r9d, byte ptr [rsi+10h]
0x180012c96  mov     r11b, bl
0x180012c99  shr     r9d, 3
0x180012c9d  mov     r10b, bl
0x180012ca0  mov     r13d, 1
0x180012ca6  movzx   edx, r10b
0x180012caa  movzx   r8d, r10b
0x180012cae  movzx   r11d, r11b
0x180012cb2  lea     eax, [r9+rdx]
0x180012cb6  cmp     eax, 8
0x180012cb9  mov     al, byte ptr [rbp+r8+6B0h+arg_20]
0x180012cc1  cmovz   r11d, r13d
0x180012cc5  add     r10b, r13b
0x180012cc8  movzx   ecx, r11b
0x180012ccc  add     ecx, r9d
0x180012ccf  add     ecx, edx
0x180012cd1  mov     [rcx+r15], al
0x180012cd5  cmp     r10b, 4
0x180012cd9  jb      short loc_180012CA6
0x180012cdb  mov     r13d, [rsp+7B0h+var_750]
0x180012ce0  movzx   r8d, byte ptr [rsi+10h]
0x180012ce5  mov     rdx, rsi; Src
0x180012ce8  shr     r8, 3; Size
0x180012cec  mov     rcx, r15; void *
0x180012cef  call    memcpy_0
0x180012cf4  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180012cfb  jz      short loc_180012D4C
0x180012cfd  mov     [rbp+6B0h+var_60], r15
0x180012d04  lea     rax, [rsp+7B0h+var_740]
0x180012d09  xor     r15d, r15d
0x180012d0c  mov     [rbp+6B0h+var_70], rax
0x180012d13  lea     rax, [rbp+6B0h+pExceptionObject]
0x180012d1a  mov     [rsp+7B0h+var_740], r12
0x180012d1f  lea     rdx, IPXLATCFG_SYNTHETIC_IPV6_EVENT
0x180012d26  mov     [rbp+6B0h+var_68], 8
0x180012d31  mov     [rbp+6B0h+var_58], 10h
0x180012d3c  lea     r9d, [r15+3]
0x180012d40  mov     qword ptr [rsp+7B0h+dwCreationFlags], rax
0x180012d45  call    McGenEventWrite_EventWriteTransfer
0x180012d4a  jmp     short loc_180012D4F
0x180012d4c  xor     r15d, r15d
0x180012d4f  mov     ebx, 1F0003h
0x180012d54  mov     qword ptr [rdi+78h], 0FFFFFFFFEE1E5D00h
0x180012d5c  mov     r9d, ebx; dwDesiredAccess
0x180012d5f  mov     [rdi+68h], r15
0x180012d63  xor     r8d, r8d; dwFlags
0x180012d66  mov     [rdi+70h], r15
0x180012d6a  xor     edx, edx; lpTimerName
0x180012d6c  mov     [rdi+58h], r15
0x180012d70  xor     ecx, ecx; lpTimerAttributes
0x180012d72  mov     [rdi+60h], r15
0x180012d76  mov     [rdi+50h], r15
0x180012d7a  call    cs:__imp_CreateWaitableTimerExW
0x180012d80  mov     [rdi+68h], rax
0x180012d84  test    rax, rax
0x180012d87  jz      loc_18001308F
0x180012d8d  mov     r9d, ebx; dwDesiredAccess
0x180012d90  xor     r8d, r8d; dwFlags
0x180012d93  xor     edx, edx; lpTimerName
0x180012d95  xor     ecx, ecx; lpTimerAttributes
0x180012d97  call    cs:__imp_CreateWaitableTimerExW
0x180012d9d  mov     [rdi+70h], rax
0x180012da1  test    rax, rax
0x180012da4  jz      loc_1800130CE
0x180012daa  xor     r9d, r9d; lpName
0x180012dad  xor     r8d, r8d; bInitialState
0x180012db0  xor     edx, edx; bManualReset
0x180012db2  xor     ecx, ecx; lpEventAttributes
0x180012db4  call    cs:__imp_CreateEventW
0x180012dba  mov     [rdi+58h], rax
0x180012dbe  test    rax, rax
0x180012dc1  jz      loc_18001310D
0x180012dc7  xor     r9d, r9d; lpName
0x180012dca  xor     r8d, r8d; bInitialState
0x180012dcd  xor     edx, edx; bManualReset
0x180012dcf  xor     ecx, ecx; lpEventAttributes
  ... truncated ...
```
