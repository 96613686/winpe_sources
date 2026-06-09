# RdpWorkItemManager::GetProgressiveVideoWorkItem(_GUID,RdpSurface *,IRdpPipeManager *,IRdpPipeEvents *,_RDPX_QUALITY,_RDP_ENCODER_POLICY_ *,IRdpProgressiveEncoderWorkItem * *)

- ea: `0x18007d460`
- end: `0x18007db27`
- name: `?GetProgressiveVideoWorkItem@RdpWorkItemManager@@UEAAJU_GUID@@PEAVRdpSurface@@PEAVIRdpPipeManager@@PEAVIRdpPipeEvents@@T_RDPX_QUALITY@@PEAU_RDP_ENCODER_POLICY_@@PEAPEAVIRdpProgressiveEncoderWorkItem@@@Z`
- size: `1735`
- prototype: `int __high(struct _GUID, struct RdpSurface *, struct IRdpPipeManager *, struct IRdpPipeEvents *, union _RDPX_QUALITY, struct _RDP_ENCODER_POLICY_ *, struct IRdpProgressiveEncoderWorkItem **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ce04`
- `0x18000e4ec`
- `0x18001f2bc`
- `0x18001f810`
- `0x18004af60`
- `0x180076090`
- `0x1800772e0`
- `0x180077aa0`
- `0x180079770`
- `0x18007d460`
- `0x18007f6b0`
- `0x1800d0d18`
- `0x1800d2ef8`
- `0x180158180`
- `0x18019b310`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d75e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d75e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d77a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d77a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d723`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d723`

## string_xrefs

- `0x18007d715`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18007d8db`: `spProtocol`
- `0x18007da81`: `WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail`
- `0x18007d7f5`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x18007d890`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x18007d837`: `GetProtocol failed.`
- `0x18007d96b`: `m_spExtensionFactory`

## pseudocode

```c
__int64 __fastcall RdpWorkItemManager::GetProgressiveVideoWorkItem(
        __int64 a1,
        _OWORD *a2,
        RdpSurface *a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        struct IRdpProgressiveEncoderWorkItem **a8)
{
  int ProgressiveVideoWorkitem; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  struct IRdpProgressiveEncoderWorkItem **v16; // r14
  struct IRdpProgressiveEncoderWorkItem **v17; // rdx
  unsigned int v18; // eax
  int v19; // edx
  const char *v20; // rcx
  AvcVideoProgressiveWorkItem *v21; // rax
  AvcVideoProgressiveWorkItem *v22; // rax
  AvcVideoProgressiveWorkItem *v23; // rsi
  __int64 v24; // rax
  signed int v25; // eax
  unsigned int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  unsigned int v29; // eax
  int v30; // edx
  const char *v31; // rcx
  __int64 v32; // r8
  signed int v33; // eax
  struct IRdpProgressiveEncoderWorkItem *v34; // rbx
  unsigned int v35; // eax
  int phkResult; // [rsp+28h] [rbp-A1h]
  int phkResulta; // [rsp+28h] [rbp-A1h]
  DWORD Type; // [rsp+78h] [rbp-51h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-4Dh] BYREF
  __int64 v41; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v42[2]; // [rsp+88h] [rbp-41h] BYREF
  HKEY hKey[2]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-21h] BYREF
  _QWORD v45[11]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 Data; // [rsp+128h] [rbp+5Fh] BYREF

  v42[0] = 0;
  v45[0] = 0;
  v44 = 0;
  AvcEncodeSettings::GetDefaultOrFallbackAvcEncoderInfo();
  if ( !a3 )
  {
    ProgressiveVideoWorkitem = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
      "WorkItemManagerError_GetProgWorkItemNullPtr",
      (char *)0x659,
      0x80004003,
      phkResult);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 107;
      v15 = "pSurface";
LABEL_6:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v15);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  v16 = a8;
  if ( a8 )
  {
    if ( !a4 )
    {
      ProgressiveVideoWorkitem = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemNullPtr",
        (char *)0x65D,
        0x80004003,
        phkResult);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 109;
        v15 = "pPipeManager";
        goto LABEL_6;
      }
      goto LABEL_65;
    }
    v17 = a8;
    *a8 = 0;
    ProgressiveVideoWorkitem = RdpSurface::GetProgressiveVideoWorkitem(a3, v17);
    if ( ProgressiveVideoWorkitem >= 0 )
      goto LABEL_65;
    if ( memcmp_0(a2, &CODEC_GUID_AVC420_CODEC, 0x10u) )
    {
      ProgressiveVideoWorkitem = -2147024846;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 110;
      v20 = "Only AVC 420 supported in Video Codec!";
      goto LABEL_23;
    }
    *(_OWORD *)hKey = *a2;
    if ( (unsigned int)CTSSimpleKeyComPtrArray<_GUID,RdpWorkItemManager::CodecEntry>::Find(a1 + 8, hKey, &v44) )
    {
      ProgressiveVideoWorkitem = -2147024846;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 111;
      v20 = "Only ONE AVC 420 codec supported when using Video Codec!";
LABEL_23:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        v18,
        (__int64)v20,
        50);
      goto LABEL_65;
    }
    hKey[0] = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
            0,
            0x20019u,
            hKey) )
    {
      LODWORD(Data) = 0;
      cbData = 4;
      Type = 0;
      RegQueryValueExW(hKey[0], L"AVCHardwareEncodePreferred", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey[0]);
    }
    v21 = (AvcVideoProgressiveWorkItem *)operator new(0x100u);
    if ( !v21 || (v22 = AvcVideoProgressiveWorkItem::AvcVideoProgressiveWorkItem(v21), (v23 = v22) == 0) )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail",
        (char *)0x698,
        0x80004003,
        phkResulta);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v35,
          (__int64)"AvcVideoProgressiveWorkItem");
      }
      ProgressiveVideoWorkitem = -2147024882;
      goto LABEL_65;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 + 4) + 8LL))(*((_QWORD *)v22 + 4));
    TCntPtr<IRDPCoreVirtualChannel>::operator=(v42, ((unsigned __int64)v23 + 48) & -(__int64)(v23 != 0));
    v24 = *a4;
    v41 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v24 + 32))(a4, &v41);
    ProgressiveVideoWorkitem = v25;
    if ( v25 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
        (char *)0x69F,
        v25,
        phkResulta);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_39;
      }
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      v27 = 113;
      v28 = "GetProtocol failed.";
LABEL_38:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        v26,
        (__int64)v28,
        ProgressiveVideoWorkitem);
LABEL_39:
      TCntPtr<IRdpVCMgr>::SafeRelease(&v41);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 4) + 16LL))(*((_QWORD *)v23 + 4));
      goto LABEL_65;
    }
    ProgressiveVideoWorkitem = -2147467261;
    if ( v41
      || (RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
            (char *)0x6A2,
            0x80004003,
            phkResulta),
          v41) )
    {
      if ( !*(_QWORD *)(a1 + 56) )
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
          "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
          (char *)0x6A5,
          0x80004003,
          phkResulta);
      Data = *(_QWORD *)(a1 + 56);
      if ( Data )
      {
        (*(void (__fastcall **)(__int64 *))(*a4 + 208))(a4);
        (*(void (__fastcall **)(__int64 *))(*a4 + 96))(a4);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 192LL))(v41);
        v33 = AvcVideoProgressiveWorkItem::Initialize(v23, *(_QWORD *)(a1 + 48), v32, a7);
        ProgressiveVideoWorkitem = v33;
        if ( v33 >= 0 )
        {
          v34 = (struct IRdpProgressiveEncoderWorkItem *)v42[0];
          TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)a3 + 104, v42[0]);
          ProgressiveVideoWorkitem = 0;
          *v16 = v34;
          v42[0] = 0;
          goto LABEL_39;
        }
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
          "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
          (char *)0x6B6,
          v33,
          phkResulta);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        v27 = 116;
        v28 = "AvcProgressiveWorkItem::Initialize failed.";
        goto LABEL_38;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_39;
      }
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      v30 = 115;
      v31 = "m_spExtensionFactory";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_39;
      }
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      v30 = 114;
      v31 = "spProtocol";
    }
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
      v29,
      (__int64)v31);
    goto LABEL_39;
  }
  ProgressiveVideoWorkitem = -2147467261;
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
    "WorkItemManagerError_GetProgWorkItemNullPtr",
    (char *)0x65B,
    0x80004003,
    phkResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 108;
    v15 = "ppWorkItem";
    goto LABEL_6;
  }
LABEL_65:
  TCntPtr<CImageClassifier>::SafeRelease(&v44);
  TCntPtr<IRdpVCMgr>::SafeRelease(v45);
  TCntPtr<IRdpVCMgr>::SafeRelease(v42);
  return (unsigned int)ProgressiveVideoWorkitem;
}

```

## disassembly

```asm
0x18007d460  mov     rax, rsp
0x18007d463  push    rbp
0x18007d464  push    rbx
0x18007d465  push    rsi
0x18007d466  push    rdi
0x18007d467  push    r12
0x18007d469  push    r13
0x18007d46b  push    r14
0x18007d46d  push    r15
0x18007d46f  lea     rbp, [rax-47h]
0x18007d473  sub     rsp, 0C8h
0x18007d47a  xor     edi, edi
0x18007d47c  movaps  xmmword ptr [rax-58h], xmm6
0x18007d480  mov     [rbp+3Fh+var_80], rdi
0x18007d484  mov     r12, r9
0x18007d487  mov     [rbp+3Fh+var_58], rdi
0x18007d48b  mov     r13, r8
0x18007d48e  mov     [rbp+3Fh+var_60], rdi
0x18007d492  mov     rsi, rdx
0x18007d495  mov     r15, rcx
0x18007d498  call    ?GetDefaultOrFallbackAvcEncoderInfo@AvcEncodeSettings@@SA?AW4MftSetting@1@XZ; AvcEncodeSettings::GetDefaultOrFallbackAvcEncoderInfo(void)
0x18007d49d  mov     ebx, eax
0x18007d49f  test    r13, r13
0x18007d4a2  jnz     loc_18007D528
0x18007d4a8  mov     edi, 80004003h
0x18007d4ad  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x18007d4b4  mov     r9d, edi; unsigned int
0x18007d4b7  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d4be  mov     r8d, 659h; char *
0x18007d4c4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4d0  lea     rax, WPP_GLOBAL_Control
0x18007d4d7  cmp     rcx, rax
0x18007d4da  jz      loc_18007DAEE
0x18007d4e0  test    byte ptr [rcx+1Ch], 8
0x18007d4e4  jz      loc_18007DAEE
0x18007d4ea  cmp     byte ptr [rcx+19h], 2
0x18007d4ee  jb      loc_18007DAEE
0x18007d4f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d4f9  lea     edx, [r13+6Bh]
0x18007d4fd  lea     rcx, aPsurface; "pSurface"
0x18007d504  mov     [rsp+100h+phkResult], rcx
0x18007d509  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x18007d510  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d517  mov     r9d, eax
0x18007d51a  mov     rcx, [rcx+10h]
0x18007d51e  call    WPP_SF_Ds
0x18007d523  jmp     loc_18007DAEE
0x18007d528  mov     r14, [rbp+3Fh+arg_38]
0x18007d52f  test    r14, r14
0x18007d532  jnz     short loc_18007D595
0x18007d534  mov     edi, 80004003h
0x18007d539  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x18007d540  mov     r9d, edi; unsigned int
0x18007d543  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d54a  mov     r8d, 65Bh; char *
0x18007d550  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d555  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d55c  lea     rax, WPP_GLOBAL_Control
0x18007d563  cmp     rcx, rax
0x18007d566  jz      loc_18007DAEE
0x18007d56c  test    byte ptr [rcx+1Ch], 8
0x18007d570  jz      loc_18007DAEE
0x18007d576  cmp     byte ptr [rcx+19h], 2
0x18007d57a  jb      loc_18007DAEE
0x18007d580  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d585  lea     edx, [r14+6Ch]
0x18007d589  lea     rcx, aPpworkitem; "ppWorkItem"
0x18007d590  jmp     loc_18007D504
0x18007d595  test    r12, r12
0x18007d598  jnz     short loc_18007D5FC
0x18007d59a  mov     edi, 80004003h
0x18007d59f  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x18007d5a6  mov     r9d, edi; unsigned int
0x18007d5a9  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d5b0  mov     r8d, 65Dh; char *
0x18007d5b6  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5c2  lea     rax, WPP_GLOBAL_Control
0x18007d5c9  cmp     rcx, rax
0x18007d5cc  jz      loc_18007DAEE
0x18007d5d2  test    byte ptr [rcx+1Ch], 8
0x18007d5d6  jz      loc_18007DAEE
0x18007d5dc  cmp     byte ptr [rcx+19h], 2
0x18007d5e0  jb      loc_18007DAEE
0x18007d5e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d5eb  lea     edx, [r12+6Dh]
0x18007d5f0  lea     rcx, aPpipemanager; "pPipeManager"
0x18007d5f7  jmp     loc_18007D504
0x18007d5fc  mov     rdx, r14; struct IRdpProgressiveEncoderWorkItem **
0x18007d5ff  mov     [r14], rdi
0x18007d602  mov     rcx, r13; this
0x18007d605  call    ?GetProgressiveVideoWorkitem@RdpSurface@@QEAAJPEAPEAVIRdpProgressiveEncoderWorkItem@@@Z; RdpSurface::GetProgressiveVideoWorkitem(IRdpProgressiveEncoderWorkItem * *)
0x18007d60a  mov     edi, eax
0x18007d60c  test    eax, eax
0x18007d60e  jns     loc_18007DAEE
0x18007d614  mov     r8d, 10h; Size
0x18007d61a  lea     rdx, CODEC_GUID_AVC420_CODEC; Buf2
0x18007d621  mov     rcx, rsi; Buf1
0x18007d624  call    memcmp_0
0x18007d629  xor     edi, edi
0x18007d62b  test    eax, eax
0x18007d62d  jz      short loc_18007D69C
0x18007d62f  mov     edi, 80070032h
0x18007d634  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d63b  lea     rax, WPP_GLOBAL_Control
0x18007d642  cmp     rcx, rax
0x18007d645  jz      loc_18007DAEE
0x18007d64b  test    byte ptr [rcx+1Ch], 8
0x18007d64f  jz      loc_18007DAEE
0x18007d655  cmp     byte ptr [rcx+19h], 2
0x18007d659  jb      loc_18007DAEE
0x18007d65f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d664  mov     edx, 6Eh ; 'n'
0x18007d669  lea     rcx, aOnlyAvc420Supp; "Only AVC 420 supported in Video Codec!"
0x18007d670  mov     dword ptr [rsp+100h+lpcbData], 80070032h
0x18007d678  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x18007d67f  mov     [rsp+100h+phkResult], rcx
0x18007d684  mov     r9d, eax
0x18007d687  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d68e  mov     rcx, [rcx+10h]
0x18007d692  call    WPP_SF_DsD
0x18007d697  jmp     loc_18007DAEE
0x18007d69c  movups  xmm0, xmmword ptr [rsi]
0x18007d69f  lea     rcx, [r15+8]
0x18007d6a3  lea     r8, [rbp+3Fh+var_60]
0x18007d6a7  lea     rdx, [rbp+3Fh+hKey]
0x18007d6ab  movdqu  xmmword ptr [rbp+3Fh+hKey], xmm0
0x18007d6b0  call    ?Find@?$CTSSimpleKeyComPtrArray@U_GUID@@UCodecEntry@RdpWorkItemManager@@@@QEAAHU_GUID@@PEAPEAUCodecEntry@RdpWorkItemManager@@@Z; CTSSimpleKeyComPtrArray<_GUID,RdpWorkItemManager::CodecEntry>::Find(_GUID,RdpWorkItemManager::CodecEntry * *)
0x18007d6b5  test    eax, eax
0x18007d6b7  jz      short loc_18007D6FF
0x18007d6b9  mov     edi, 80070032h
0x18007d6be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d6c5  lea     rax, WPP_GLOBAL_Control
0x18007d6cc  cmp     rcx, rax
0x18007d6cf  jz      loc_18007DAEE
0x18007d6d5  test    byte ptr [rcx+1Ch], 8
0x18007d6d9  jz      loc_18007DAEE
0x18007d6df  cmp     byte ptr [rcx+19h], 2
0x18007d6e3  jb      loc_18007DAEE
0x18007d6e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d6ee  mov     edx, 6Fh ; 'o'
0x18007d6f3  lea     rcx, aOnlyOneAvc420C; "Only ONE AVC 420 codec supported when u"...
0x18007d6fa  jmp     loc_18007D670
0x18007d6ff  lea     rax, [rbp+3Fh+hKey]
0x18007d703  mov     [rbp+3Fh+hKey], rdi
0x18007d707  mov     r9d, 20019h; samDesired
0x18007d70d  mov     [rsp+100h+phkResult], rax; phkResult
0x18007d712  xor     r8d, r8d; ulOptions
0x18007d715  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x18007d71c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d723  call    cs:__imp_RegOpenKeyExW
0x18007d729  test    eax, eax
0x18007d72b  jnz     short loc_18007D780
0x18007d72d  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18007d731  lea     rax, [rbp+3Fh+cbData]
0x18007d735  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18007d73a  lea     r9, [rbp+3Fh+Type]; lpType
0x18007d73e  lea     rax, [rbp+3Fh+Data]
0x18007d742  mov     dword ptr [rbp+3Fh+Data], edi
0x18007d745  xor     r8d, r8d; lpReserved
0x18007d748  mov     [rsp+100h+phkResult], rax; int
0x18007d74d  lea     rdx, aAvchardwareenc; "AVCHardwareEncodePreferred"
0x18007d754  mov     [rbp+3Fh+cbData], 4
0x18007d75b  mov     [rbp+3Fh+Type], edi
0x18007d75e  call    cs:__imp_RegQueryValueExW
0x18007d764  test    eax, eax
0x18007d766  jnz     short loc_18007D776
0x18007d768  cmp     [rbp+3Fh+Type], 4
0x18007d76c  jnz     short loc_18007D776
0x18007d76e  cmp     dword ptr [rbp+3Fh+Data], 3
0x18007d772  cmovbe  ebx, dword ptr [rbp+3Fh+Data]
0x18007d776  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18007d77a  call    cs:__imp_RegCloseKey
0x18007d780  mov     ecx, 100h; Size
0x18007d785  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d78a  test    rax, rax
0x18007d78d  jz      loc_18007DA7B
0x18007d793  mov     rcx, rax; this
0x18007d796  call    ??0AvcVideoProgressiveWorkItem@@QEAA@XZ; AvcVideoProgressiveWorkItem::AvcVideoProgressiveWorkItem(void)
0x18007d79b  mov     rsi, rax
0x18007d79e  test    rax, rax
0x18007d7a1  jz      loc_18007DA7B
0x18007d7a7  mov     rcx, [rax+20h]
0x18007d7ab  mov     rdx, [rcx]
0x18007d7ae  mov     rax, [rdx+8]
0x18007d7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7b7  lea     r8, [rsi+30h]
0x18007d7bb  mov     rcx, rsi
0x18007d7be  neg     rcx
0x18007d7c1  lea     rcx, [rbp+3Fh+var_80]
0x18007d7c5  sbb     rdx, rdx
0x18007d7c8  and     rdx, r8
0x18007d7cb  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18007d7d0  mov     rax, [r12]
0x18007d7d4  lea     rdx, [rbp+3Fh+var_88]
0x18007d7d8  mov     rcx, r12
0x18007d7db  mov     [rbp+3Fh+var_88], rdi
0x18007d7df  mov     rax, [rax+20h]
0x18007d7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7e8  mov     edi, eax
0x18007d7ea  test    eax, eax
0x18007d7ec  jns     loc_18007D87F
0x18007d7f2  mov     r9d, eax; unsigned int
0x18007d7f5  lea     rdx, aWorkitemmanage_12; "WorkItemManagerError_GetProgWorkItemGet"...
0x18007d7fc  mov     r8d, 69Fh; char *
0x18007d802  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d809  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d80e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d815  lea     rax, WPP_GLOBAL_Control
0x18007d81c  cmp     rcx, rax
0x18007d81f  jz      short loc_18007D861
0x18007d821  test    byte ptr [rcx+1Ch], 8
0x18007d825  jz      short loc_18007D861
0x18007d827  cmp     byte ptr [rcx+19h], 2
0x18007d82b  jb      short loc_18007D861
0x18007d82d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d832  mov     edx, 71h ; 'q'
0x18007d837  lea     rcx, aGetprotocolFai_0; "GetProtocol failed."
0x18007d83e  mov     dword ptr [rsp+100h+lpcbData], edi
0x18007d842  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x18007d849  mov     [rsp+100h+phkResult], rcx
0x18007d84e  mov     r9d, eax
0x18007d851  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d858  mov     rcx, [rcx+10h]
0x18007d85c  call    WPP_SF_DsD
0x18007d861  lea     rcx, [rbp+3Fh+var_88]
0x18007d865  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18007d86a  mov     rcx, [rsi+20h]
0x18007d86e  mov     rax, [rcx]
0x18007d871  mov     rax, [rax+10h]
0x18007d875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d87a  jmp     loc_18007DAEE
0x18007d87f  mov     rax, [rbp+3Fh+var_88]
0x18007d883  mov     edi, 80004003h
0x18007d888  test    rax, rax
0x18007d88b  jnz     short loc_18007D906
0x18007d88d  mov     r9d, edi; unsigned int
0x18007d890  lea     rdx, aWorkitemmanage_12; "WorkItemManagerError_GetProgWorkItemGet"...
0x18007d897  mov     r8d, 6A2h; char *
0x18007d89d  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d8a4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d8a9  mov     rax, [rbp+3Fh+var_88]
0x18007d8ad  test    rax, rax
0x18007d8b0  jnz     short loc_18007D906
0x18007d8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d8b9  lea     rax, WPP_GLOBAL_Control
0x18007d8c0  cmp     rcx, rax
0x18007d8c3  jz      short loc_18007D861
0x18007d8c5  test    byte ptr [rcx+1Ch], 8
0x18007d8c9  jz      short loc_18007D861
0x18007d8cb  cmp     byte ptr [rcx+19h], 2
0x18007d8cf  jb      short loc_18007D861
0x18007d8d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d8d6  mov     edx, 72h ; 'r'
0x18007d8db  lea     rcx, aSpprotocol; "spProtocol"
0x18007d8e2  mov     [rsp+100h+phkResult], rcx
0x18007d8e7  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x18007d8ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d8f5  mov     r9d, eax
0x18007d8f8  mov     rcx, [rcx+10h]
0x18007d8fc  call    WPP_SF_Ds
0x18007d901  jmp     loc_18007D861
0x18007d906  cmp     qword ptr [r15+38h], 0
0x18007d90b  jnz     short loc_18007D929
0x18007d90d  mov     r9d, edi; unsigned int
0x18007d910  lea     rdx, aWorkitemmanage_6; "WorkItemManagerError_GetProgWorkItemGet"...
0x18007d917  mov     r8d, 6A5h; char *
0x18007d91d  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x18007d924  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18007d929  mov     rax, [r15+38h]
0x18007d92d  mov     [rbp+3Fh+Data], rax
0x18007d931  test    rax, rax
0x18007d934  jnz     short loc_18007D977
0x18007d936  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d93d  lea     rax, WPP_GLOBAL_Control
0x18007d944  cmp     rcx, rax
0x18007d947  jz      loc_18007D861
0x18007d94d  test    byte ptr [rcx+1Ch], 8
0x18007d951  jz      loc_18007D861
0x18007d957  cmp     byte ptr [rcx+19h], 2
0x18007d95b  jb      loc_18007D861
0x18007d961  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007d966  mov     edx, 73h ; 's'
0x18007d96b  lea     rcx, aMSpextensionfa; "m_spExtensionFactory"
0x18007d972  jmp     loc_18007D8E2
0x18007d977  mov     rax, [r12]
0x18007d97b  mov     rcx, r12
0x18007d97e  mov     rax, [rax+0D0h]
0x18007d985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d98a  mov     rax, [r12]
0x18007d98e  mov     rcx, r12
0x18007d991  movaps  xmm6, xmm0
0x18007d994  mov     rax, [rax+60h]
0x18007d998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d99d  mov     rcx, [rbp+3Fh+var_88]
0x18007d9a1  mov     rax, [rcx]
0x18007d9a4  mov     rax, [rax+0C0h]
0x18007d9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9b0  mov     r9, [rbp+3Fh+arg_30]
  ... truncated ...
```
