# AvcVideoProgressiveWorkItem::Initialize(IUnknown *,uchar,_RDP_ENCODER_POLICY_ *,PipelineCodec,RdpSurface *,ulong,IRdpPipeEvents *,CapsDataAvc &,_RDPX_QUALITY,AvcEncodeSettings::MftSetting,float,IRdpPipeExtensionFactory *)

- ea: `0x1800d2ef8`
- end: `0x1800d33e0`
- name: `?Initialize@AvcVideoProgressiveWorkItem@@QEAAJPEAUIUnknown@@EPEAU_RDP_ENCODER_POLICY_@@W4PipelineCodec@@PEAVRdpSurface@@KPEAVIRdpPipeEvents@@AEAVCapsDataAvc@@T_RDPX_QUALITY@@W4MftSetting@AvcEncodeSettings@@MPEAVIRdpPipeExtensionFactory@@@Z`
- size: `1256`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007d460`

## callees

- `0x18000ce04`
- `0x18000e4ec`
- `0x180010d6c`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007cf90`
- `0x1800ce1fc`
- `0x1800d2ef8`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d3397`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d33c3`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d3397`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d33c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d31a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d31a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d31c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d31c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d3165`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d3165`

## string_xrefs

- `0x1800d3157`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800d3033`: `pExtensionFactory`
- `0x1800d3247`: `failed to create Dirty BA`
- `0x1800d32be`: `failed to create target BA`

## pseudocode

```c
__int64 __fastcall AvcVideoProgressiveWorkItem::Initialize(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned int Data,
        __int64 cbData,
        int a7,
        __int64 a8,
        HKEY hKey,
        unsigned __int8 a10,
        int a11,
        int a12,
        __int64 a13)
{
  __int64 v13; // r14
  int Instance; // ebx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  __int64 v19; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RDPGraphicsTraceLogging *CodecName; // rax
  unsigned int v22; // eax
  RDPGraphicsTraceLogging *v23; // rax
  unsigned int v24; // eax
  RDPGraphicsTraceLogging *v25; // rax
  unsigned int v26; // eax
  int v27; // edx
  RDPGraphicsTraceLogging *v28; // rax
  __int64 v29; // rdx
  int phkResult; // [rsp+20h] [rbp-10h]
  int phkResulta; // [rsp+20h] [rbp-10h]
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF

  LOBYTE(Type) = a3;
  v13 = cbData;
  if ( cbData )
  {
    if ( a4 )
    {
      v19 = a13;
      if ( !a13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"pExtensionFactory");
        }
        return (unsigned int)-2147467261;
      }
      if ( *(_QWORD *)(a1 + 56) )
      {
        CodecName = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
        Instance = -2147467259;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          CodecName,
          "AvcVideoProgressiveWorkItemError_InitializeReinitializeFail",
          (char *)0x74,
          0x80004005,
          phkResult);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)&WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids,
            v22,
            (__int64)"Initialize called again??",
            5);
        }
        return (unsigned int)Instance;
      }
      TCntPtr<IRDPCoreVirtualChannel>::operator=(a1 + 144, a2);
      *(_DWORD *)(a1 + 88) = a11;
      *(_DWORD *)(a1 + 76) = 7;
      if ( v19 != *(_QWORD *)(a1 + 240) )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease(a1 + 240);
        *(_QWORD *)(a1 + 240) = v19;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      }
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
              0,
              0x20019u,
              &hKey) )
      {
        Type = 0;
        Data = 70;
        LODWORD(cbData) = 4;
        if ( !RegQueryValueExW(hKey, L"AVCVideoHardwareAllowedThreshold", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData)
          && Type == 4
          && Data <= 0x64 )
        {
          *(_DWORD *)(a1 + 232) = Data;
        }
        RegCloseKey(hKey);
      }
      if ( a10 != 0xFF )
        *(_DWORD *)(a1 + 196) = a10;
      Instance = RgnlibBA_CreateInstance(a1 + 152);
      if ( Instance < 0 )
      {
        v23 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          v23,
          "AvcVideoProgressiveWorkItemError_InitializeInitializeFail",
          (char *)0xAB,
          Instance,
          phkResulta);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids,
            v24,
            (__int64)"failed to create Dirty BA",
            Instance);
        }
        return (unsigned int)Instance;
      }
      Instance = RgnlibBA_CreateInstance(a1 + 160);
      if ( Instance >= 0 )
      {
        Instance = RgnlibBA_CreateInstance(a1 + 168);
        if ( Instance >= 0 )
        {
          v29 = a8;
          *(_DWORD *)(a1 + 224) = a12;
          *(_QWORD *)(a1 + 176) = 0;
          *(_QWORD *)(a1 + 184) = 0;
          *(_QWORD *)(a1 + 64) = v13;
          *(_BYTE *)(a1 + 120) = 11;
          TCntPtr<IRdpPipeEvents>::operator=(a1 + 112, v29);
          *(_DWORD *)(a1 + 228) = a7;
          Instance = RDPAPI_GetGenericCounter(
                       L"RDV::RDP::GraphicsPipeline::WorkItemCodecStart",
                       0xFFFFFFFFLL,
                       0xFFFFFFFFLL,
                       0xFFFFFFFFLL,
                       4,
                       a1 + 96);
          if ( Instance >= 0 )
            return (unsigned int)RDPAPI_GetGenericCounter(
                                   L"RDV::RDP::GraphicsPipeline::WorkItemCodecEnd",
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   4,
                                   a1 + 104);
          return (unsigned int)Instance;
        }
        v28 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          v28,
          "AvcVideoProgressiveWorkItemError_InitializeInitializeFail",
          (char *)0xB3,
          Instance,
          phkResulta);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)Instance;
        }
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        v27 = 16;
      }
      else
      {
        v25 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          v25,
          "AvcVideoProgressiveWorkItemError_InitializeInitializeFail",
          (char *)0xAF,
          Instance,
          phkResulta);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)Instance;
        }
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        v27 = 15;
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        (unsigned int)&WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids,
        v26,
        (__int64)"failed to create target BA",
        Instance);
      return (unsigned int)Instance;
    }
    Instance = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"m_codecGuid",
      "AvcVideoProgressiveWorkItemError_InitializeNullPointer",
      (char *)0x6D,
      0x80004003,
      phkResult);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 11;
      v18 = "policy";
      goto LABEL_6;
    }
  }
  else
  {
    Instance = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"m_codecGuid",
      "AvcVideoProgressiveWorkItemError_InitializeNullPointer",
      (char *)0x6B,
      0x80004003,
      phkResult);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 10;
      v18 = "pSurface";
LABEL_6:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)&WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids,
        v16,
        (__int64)v18);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800d2ef8  mov     [rsp-18h+arg_0], rbx
0x1800d2efd  mov     [rsp-18h+arg_8], rsi
0x1800d2f02  mov     byte ptr [rsp-18h+Type], r8b
0x1800d2f07  push    rbp
0x1800d2f08  push    rdi
0x1800d2f09  push    r14
0x1800d2f0b  mov     rbp, rsp
0x1800d2f0e  sub     rsp, 30h
0x1800d2f12  mov     r14, [rbp+cbData]
0x1800d2f16  mov     rdi, rcx
0x1800d2f19  test    r14, r14
0x1800d2f1c  jnz     short loc_1800D2F9C
0x1800d2f1e  mov     ebx, 80004003h
0x1800d2f23  lea     r8d, [r14+6Bh]; char *
0x1800d2f27  mov     r9d, ebx; unsigned int
0x1800d2f2a  lea     rdx, aAvcvideoprogre_18; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d2f31  lea     rcx, aMCodecguid; "m_codecGuid"
0x1800d2f38  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d2f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2f44  lea     rax, WPP_GLOBAL_Control
0x1800d2f4b  cmp     rcx, rax
0x1800d2f4e  jz      loc_1800D33CB
0x1800d2f54  test    byte ptr [rcx+1Ch], 8
0x1800d2f58  jz      loc_1800D33CB
0x1800d2f5e  cmp     byte ptr [rcx+19h], 2
0x1800d2f62  jb      loc_1800D33CB
0x1800d2f68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d2f6d  lea     edx, [r14+0Ah]
0x1800d2f71  lea     rcx, aPsurface; "pSurface"
0x1800d2f78  mov     [rsp+30h+phkResult], rcx
0x1800d2f7d  lea     r8, WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids
0x1800d2f84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2f8b  mov     r9d, eax
0x1800d2f8e  mov     rcx, [rcx+10h]
0x1800d2f92  call    WPP_SF_Ds
0x1800d2f97  jmp     loc_1800D33CB
0x1800d2f9c  test    r9, r9
0x1800d2f9f  jnz     short loc_1800D3003
0x1800d2fa1  mov     ebx, 80004003h
0x1800d2fa6  lea     rdx, aAvcvideoprogre_18; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d2fad  mov     r9d, ebx; unsigned int
0x1800d2fb0  lea     rcx, aMCodecguid; "m_codecGuid"
0x1800d2fb7  mov     r8d, 6Dh ; 'm'; char *
0x1800d2fbd  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d2fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2fc9  lea     rax, WPP_GLOBAL_Control
0x1800d2fd0  cmp     rcx, rax
0x1800d2fd3  jz      loc_1800D33CB
0x1800d2fd9  test    byte ptr [rcx+1Ch], 8
0x1800d2fdd  jz      loc_1800D33CB
0x1800d2fe3  cmp     byte ptr [rcx+19h], 2
0x1800d2fe7  jb      loc_1800D33CB
0x1800d2fed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d2ff2  mov     edx, 0Bh
0x1800d2ff7  lea     rcx, aPolicy; "policy"
0x1800d2ffe  jmp     loc_1800D2F78
0x1800d3003  mov     rbx, [rbp+arg_60]
0x1800d300a  test    rbx, rbx
0x1800d300d  jnz     short loc_1800D3066
0x1800d300f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3016  lea     rax, WPP_GLOBAL_Control
0x1800d301d  cmp     rcx, rax
0x1800d3020  jz      short loc_1800D305C
0x1800d3022  test    byte ptr [rcx+1Ch], 8
0x1800d3026  jz      short loc_1800D305C
0x1800d3028  cmp     byte ptr [rcx+19h], 2
0x1800d302c  jb      short loc_1800D305C
0x1800d302e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d3033  lea     rcx, aPextensionfact; "pExtensionFactory"
0x1800d303a  mov     r9d, eax
0x1800d303d  mov     [rsp+30h+phkResult], rcx
0x1800d3042  lea     edx, [rbx+0Ch]
0x1800d3045  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d304c  lea     r8, WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids
0x1800d3053  mov     rcx, [rcx+10h]
0x1800d3057  call    WPP_SF_Ds
0x1800d305c  mov     ebx, 80004003h
0x1800d3061  jmp     loc_1800D33CB
0x1800d3066  cmp     qword ptr [rcx+38h], 0
0x1800d306b  jz      loc_1800D30FE
0x1800d3071  mov     ecx, [rcx+4Ch]
0x1800d3074  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800d3079  mov     ebx, 80004005h
0x1800d307e  lea     rdx, aAvcvideoprogre_20; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d3085  mov     r9d, ebx; unsigned int
0x1800d3088  mov     rcx, rax; this
0x1800d308b  mov     r8d, 74h ; 't'; char *
0x1800d3091  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d3096  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d309d  lea     rax, WPP_GLOBAL_Control
0x1800d30a4  cmp     rcx, rax
0x1800d30a7  jz      loc_1800D33CB
0x1800d30ad  test    byte ptr [rcx+1Ch], 8
0x1800d30b1  jz      loc_1800D33CB
0x1800d30b7  cmp     byte ptr [rcx+19h], 2
0x1800d30bb  jb      loc_1800D33CB
0x1800d30c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d30c6  mov     edx, 0Dh
0x1800d30cb  mov     dword ptr [rsp+30h+lpcbData], 80004005h
0x1800d30d3  lea     rcx, aInitializeCall; "Initialize called again??"
0x1800d30da  mov     [rsp+30h+phkResult], rcx
0x1800d30df  lea     r8, WPP_5ec6fc3f1a1e360121de0bb731478632_Traceguids
0x1800d30e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d30ed  mov     r9d, eax
0x1800d30f0  mov     rcx, [rcx+10h]
0x1800d30f4  call    WPP_SF_DsD
0x1800d30f9  jmp     loc_1800D33CB
0x1800d30fe  add     rcx, 90h
0x1800d3105  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800d310a  mov     eax, [rbp+arg_50]
0x1800d310d  lea     rsi, [rdi+0F0h]
0x1800d3114  mov     [rdi+58h], eax
0x1800d3117  mov     dword ptr [rdi+4Ch], 7
0x1800d311e  cmp     rbx, [rsi]
0x1800d3121  jz      short loc_1800D313D
0x1800d3123  mov     rcx, rsi
0x1800d3126  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800d312b  mov     [rsi], rbx
0x1800d312e  mov     rcx, rbx
0x1800d3131  mov     rax, [rbx]
0x1800d3134  mov     rax, [rax+8]
0x1800d3138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d313d  lea     rax, [rbp+hKey]
0x1800d3141  mov     [rbp+hKey], 0
0x1800d3149  mov     r9d, 20019h; samDesired
0x1800d314f  mov     [rsp+30h+phkResult], rax; phkResult
0x1800d3154  xor     r8d, r8d; ulOptions
0x1800d3157  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x1800d315e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d3165  call    cs:__imp_RegOpenKeyExW
0x1800d316b  test    eax, eax
0x1800d316d  jnz     short loc_1800D31CC
0x1800d316f  mov     rcx, [rbp+hKey]; hKey
0x1800d3173  lea     r9, [rbp+Type]; lpType
0x1800d3177  mov     [rbp+Type], eax
0x1800d317a  lea     rdx, aAvcvideohardwa; "AVCVideoHardwareAllowedThreshold"
0x1800d3181  lea     rax, [rbp+cbData]
0x1800d3185  mov     [rbp+Data], 46h ; 'F'
0x1800d318c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800d3191  xor     r8d, r8d; lpReserved
0x1800d3194  lea     rax, [rbp+Data]
0x1800d3198  mov     dword ptr [rbp+cbData], 4
0x1800d319f  mov     [rsp+30h+phkResult], rax; int
0x1800d31a4  call    cs:__imp_RegQueryValueExW
0x1800d31aa  test    eax, eax
0x1800d31ac  jnz     short loc_1800D31C2
0x1800d31ae  cmp     [rbp+Type], 4
0x1800d31b2  jnz     short loc_1800D31C2
0x1800d31b4  mov     eax, [rbp+Data]
0x1800d31b7  cmp     eax, 64h ; 'd'
0x1800d31ba  ja      short loc_1800D31C2
0x1800d31bc  mov     [rdi+0E8h], eax
0x1800d31c2  mov     rcx, [rbp+hKey]; hKey
0x1800d31c6  call    cs:__imp_RegCloseKey
0x1800d31cc  cmp     [rbp+arg_48], 0FFh
0x1800d31d0  jz      short loc_1800D31DC
0x1800d31d2  movzx   eax, [rbp+arg_48]
0x1800d31d6  mov     [rdi+0C4h], eax
0x1800d31dc  lea     rcx, [rdi+98h]
0x1800d31e3  call    RgnlibBA_CreateInstance
0x1800d31e8  mov     ebx, eax
0x1800d31ea  test    eax, eax
0x1800d31ec  jns     short loc_1800D3253
0x1800d31ee  mov     ecx, [rdi+4Ch]
0x1800d31f1  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800d31f6  mov     rcx, rax; this
0x1800d31f9  lea     rdx, aAvcvideoprogre_12; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d3200  mov     r9d, ebx; unsigned int
0x1800d3203  mov     r8d, 0ABh; char *
0x1800d3209  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d320e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3215  lea     rax, WPP_GLOBAL_Control
0x1800d321c  cmp     rcx, rax
0x1800d321f  jz      loc_1800D33CB
0x1800d3225  test    byte ptr [rcx+1Ch], 8
0x1800d3229  jz      loc_1800D33CB
0x1800d322f  cmp     byte ptr [rcx+19h], 2
0x1800d3233  jb      loc_1800D33CB
0x1800d3239  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d323e  mov     edx, 0Eh
0x1800d3243  mov     dword ptr [rsp+30h+lpcbData], ebx
0x1800d3247  lea     rcx, aFailedToCreate_52; "failed to create Dirty BA"
0x1800d324e  jmp     loc_1800D30DA
0x1800d3253  lea     rcx, [rdi+0A0h]
0x1800d325a  call    RgnlibBA_CreateInstance
0x1800d325f  mov     ebx, eax
0x1800d3261  test    eax, eax
0x1800d3263  jns     short loc_1800D32CA
0x1800d3265  mov     ecx, [rdi+4Ch]
0x1800d3268  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800d326d  mov     rcx, rax; this
0x1800d3270  lea     rdx, aAvcvideoprogre_12; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d3277  mov     r9d, ebx; unsigned int
0x1800d327a  mov     r8d, 0AFh; char *
0x1800d3280  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d3285  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d328c  lea     rax, WPP_GLOBAL_Control
0x1800d3293  cmp     rcx, rax
0x1800d3296  jz      loc_1800D33CB
0x1800d329c  test    byte ptr [rcx+1Ch], 8
0x1800d32a0  jz      loc_1800D33CB
0x1800d32a6  cmp     byte ptr [rcx+19h], 2
0x1800d32aa  jb      loc_1800D33CB
0x1800d32b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d32b5  mov     edx, 0Fh
0x1800d32ba  mov     dword ptr [rsp+30h+lpcbData], ebx
0x1800d32be  lea     rcx, aFailedToCreate_74; "failed to create target BA"
0x1800d32c5  jmp     loc_1800D30DA
0x1800d32ca  lea     rcx, [rdi+0A8h]
0x1800d32d1  call    RgnlibBA_CreateInstance
0x1800d32d6  mov     ebx, eax
0x1800d32d8  test    eax, eax
0x1800d32da  jns     short loc_1800D3333
0x1800d32dc  mov     ecx, [rdi+4Ch]
0x1800d32df  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800d32e4  mov     rcx, rax; this
0x1800d32e7  lea     rdx, aAvcvideoprogre_12; "AvcVideoProgressiveWorkItemError_Initia"...
0x1800d32ee  mov     r9d, ebx; unsigned int
0x1800d32f1  mov     r8d, 0B3h; char *
0x1800d32f7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d32fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3303  lea     rax, WPP_GLOBAL_Control
0x1800d330a  cmp     rcx, rax
0x1800d330d  jz      loc_1800D33CB
0x1800d3313  test    byte ptr [rcx+1Ch], 8
0x1800d3317  jz      loc_1800D33CB
0x1800d331d  cmp     byte ptr [rcx+19h], 2
0x1800d3321  jb      loc_1800D33CB
0x1800d3327  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d332c  mov     edx, 10h
0x1800d3331  jmp     short loc_1800D32BA
0x1800d3333  movss   xmm0, [rbp+arg_58]
0x1800d3338  lea     rcx, [rdi+70h]
0x1800d333c  mov     rdx, [rbp+arg_38]
0x1800d3340  movss   dword ptr [rdi+0E0h], xmm0
0x1800d3348  mov     qword ptr [rdi+0B0h], 0
0x1800d3353  mov     qword ptr [rdi+0B8h], 0
0x1800d335e  mov     [rdi+40h], r14
0x1800d3362  mov     byte ptr [rdi+78h], 0Bh
0x1800d3366  call    ??4?$TCntPtr@VIRdpPipeEvents@@@@QEAAPEAVIRdpPipeEvents@@PEAV1@@Z; TCntPtr<IRdpPipeEvents>::operator=(IRdpPipeEvents *)
0x1800d336b  mov     eax, [rbp+arg_30]
0x1800d336e  lea     rcx, aRdvRdpGraphics_3; "RDV::RDP::GraphicsPipeline::WorkItemCod"...
0x1800d3375  or      esi, 0FFFFFFFFh
0x1800d3378  mov     [rdi+0E4h], eax
0x1800d337e  lea     rax, [rdi+60h]
0x1800d3382  mov     r9d, esi
0x1800d3385  mov     [rsp+30h+lpcbData], rax
0x1800d338a  mov     r8d, esi
0x1800d338d  mov     edx, esi
0x1800d338f  mov     dword ptr [rsp+30h+phkResult], 4
0x1800d3397  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800d339d  mov     ebx, eax
0x1800d339f  test    eax, eax
0x1800d33a1  js      short loc_1800D33CB
0x1800d33a3  lea     rax, [rdi+68h]
0x1800d33a7  mov     r9d, esi
0x1800d33aa  mov     [rsp+30h+lpcbData], rax
0x1800d33af  lea     rcx, aRdvRdpGraphics_41; "RDV::RDP::GraphicsPipeline::WorkItemCod"...
0x1800d33b6  mov     r8d, esi
0x1800d33b9  mov     dword ptr [rsp+30h+phkResult], 4
0x1800d33c1  mov     edx, esi
0x1800d33c3  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800d33c9  mov     ebx, eax
0x1800d33cb  mov     rsi, [rsp+30h+arg_8]
0x1800d33d0  mov     eax, ebx
0x1800d33d2  mov     rbx, [rsp+30h+arg_0]
0x1800d33d7  add     rsp, 30h
0x1800d33db  pop     r14
0x1800d33dd  pop     rdi
0x1800d33de  pop     rbp
0x1800d33df  retn
```
