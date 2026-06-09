# CPort::OnIncomingP2PActionFrameReceived(ulong,uchar *)

- ea: `0x1400b40f4`
- end: `0x1400b48e8`
- name: `?OnIncomingP2PActionFrameReceived@CPort@@QEAAXKPEAE@Z`
- size: `2036`
- prototype: `void __fastcall(CPort *this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e2c0`

## callees

- `0x14000da4c`
- `0x140010390`
- `0x1400122e0`
- `0x140019574`
- `0x140019700`
- `0x14001a568`
- `0x140023ae0`
- `0x14002aa28`
- `0x14002ed64`
- `0x140034e04`
- `0x140034ec4`
- `0x14005abb4`
- `0x140082d74`
- `0x14008db50`
- `0x1400adf18`
- `0x1400b40f4`
- `0x1400b918c`
- `0x1400d79b4`
- `0x1400d8338`
- `0x1400da4f0`
- `0x1400da680`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b4382`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4738`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4382`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4738`

## pseudocode

```c
void __fastcall CPort::OnIncomingP2PActionFrameReceived(CPort *this, unsigned int a2, unsigned __int8 *a3)
{
  bool v3; // si
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  char v10; // r12
  int v11; // edx
  unsigned int v12; // eax
  int v13; // r14d
  unsigned int v14; // r13d
  __int64 Pool2; // rax
  int v16; // r8d
  _DWORD *v17; // rbx
  __int16 v18; // ax
  void *v19; // rcx
  size_t v20; // rax
  __int16 v21; // ax
  __int16 v22; // ax
  unsigned int v23; // eax
  __int16 v24; // ax
  __int16 v25; // ax
  __int16 SAEIndicationType; // ax
  unsigned int ElementCount; // eax
  CAdapterPropertyCache *v28; // rax
  int v29; // edx
  int v30; // r8d
  CAdapter *m_pAdapter; // r15
  struct CBSSEntry *BSSEntryByGroupID; // rsi
  CBSSEntry *v33; // rax
  CBSSEntry *v34; // rax
  CBSSEntry *v35; // r8
  _BOOL8 v36; // r9
  IPropertyCacheDirectory *v37; // rcx
  CAdapterPropertyCache *v38; // rax
  struct CAdapterPropertyCache *v39; // rax
  enum _WDI_BAND_ID v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v41; // [rsp+58h] [rbp-A8h]
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS v42; // [rsp+60h] [rbp-A0h] BYREF
  struct _DOT11_WFD_GROUP_ID v43; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v44[5]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int8 v45[6]; // [rsp+100h] [rbp+0h] BYREF

  *(_DWORD *)&v42.Optional &= ~1u;
  v3 = 0;
  *(_QWORD *)v42.BssId.Address = 0;
  *(_QWORD *)&v42.SAEIndicationType = 0;
  v42.SAEStatus = WDI_SAE_STATUS_SUCCESS;
  *((_BYTE *)&v42.SAEStatus + 4) = 0;
  *(_QWORD *)v43.DeviceAddress = 0;
  v41 = a3;
  strcpy((char *)v43.SSID.ucSSID, "DIRECT-");
  v42.SAECommitResponse.pElements = 0;
  v42.SAECommitResponse.MemoryInternallyAllocated = 0;
  v42.SAEConfirmResponse.ElementCount = 0;
  v42.SAEConfirmResponse.pElements = 0;
  v42.SAEConfirmResponse.MemoryInternallyAllocated = 0;
  v43.SSID.uSSIDLength = 7;
  memset(&v43.SSID.ucSSID[8], 0, 24);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      360,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  v7 = ParseWdiIndicationP2pActionFrameReceivedFromIhv(a2 - 48, a3 + 48, &this->m_pAdapter->m_TlvContext, &v42);
  v10 = v7;
  if ( !v7 )
  {
    *(_DWORD *)v43.DeviceAddress = *(_DWORD *)&v42.BssId.Address[4];
    *(_DWORD *)v45 = *(_DWORD *)&v42.BssId.Address[4];
    *(_WORD *)&v43.DeviceAddress[4] = v42.SAEIndicationType;
    *(_WORD *)&v45[4] = v42.SAEIndicationType;
    v12 = 28;
    v11 = 32;
    if ( *(_DWORD *)v42.BssId.Address == 1 )
    {
      v13 = 1073938453;
    }
    else
    {
      if ( *(_DWORD *)v42.BssId.Address != 2 )
      {
        switch ( *(_DWORD *)v42.BssId.Address )
        {
          case 3:
            v12 = 20;
            v13 = 1073938457;
            goto LABEL_26;
          case 4:
            v13 = 1073938459;
            break;
          case 5:
            v13 = 1073938461;
            goto LABEL_26;
          case 6:
            v13 = 1073938463;
            break;
          case 7:
            v13 = 1073938465;
LABEL_26:
            v14 = v42.SAECommitResponse.ElementCount + v12;
            if ( v42.SAECommitResponse.ElementCount + v12 < v12 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v11) = 2;
                WPP_RECORDER_SF_qDDDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v11,
                  40,
                  363,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                  (char)this,
                  this->m_WfcPortId,
                  v42.SAECommitResponse.ElementCount,
                  -1,
                  1);
              }
              v10 = 1;
              goto LABEL_69;
            }
            Pool2 = ExAllocatePool2(64, v14, 1198089303);
            v17 = (_DWORD *)Pool2;
            if ( !Pool2 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v11) = 2;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v11,
                  v16,
                  364,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                  (char)this,
                  this->m_WfcPortId);
              }
              v10 = -102;
              goto LABEL_69;
            }
            switch ( *(_DWORD *)v42.BssId.Address )
            {
              case 1:
                *(_DWORD *)Pool2 = 2097536;
                *(_BYTE *)(Pool2 + 10) = BYTE2(v42.SAEIndicationType);
                *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
                SAEIndicationType = v42.SAEIndicationType;
                v17[6] = 32;
                *((_WORD *)v17 + 4) = SAEIndicationType;
                ElementCount = v42.SAECommitResponse.ElementCount;
                v17[7] = v42.SAECommitResponse.ElementCount;
                memmove(v17 + 8, v42.SAECommitResponse.pElements, ElementCount);
                v3 = GetSimpleAttribute(
                       v42.SAECommitResponse.pElements,
                       v42.SAECommitResponse.ElementCount,
                       6u,
                       &v42.SAEStatus,
                       5u) >= 0;
                goto LABEL_54;
              case 2:
                *(_DWORD *)Pool2 = 2097536;
                *(_BYTE *)(Pool2 + 10) = BYTE2(v42.SAEIndicationType);
                *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
                v25 = v42.SAEIndicationType;
                v17[6] = 32;
                v19 = v17 + 8;
                *((_WORD *)v17 + 4) = v25;
                v20 = v42.SAECommitResponse.ElementCount;
                v17[7] = v42.SAECommitResponse.ElementCount;
                goto LABEL_52;
              case 3:
                *(_DWORD *)Pool2 = 1311104;
                *(_BYTE *)(Pool2 + 10) = BYTE2(v42.SAEIndicationType);
                *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
                v24 = v42.SAEIndicationType;
                v17[3] = 20;
                v19 = v17 + 5;
                *((_WORD *)v17 + 4) = v24;
                v20 = v42.SAECommitResponse.ElementCount;
                v17[4] = v42.SAECommitResponse.ElementCount;
                goto LABEL_52;
              case 4:
                *(_DWORD *)Pool2 = 2621824;
                v40 = WDI_BAND_ID_UNKNOWN;
                memset(&v44[2], 0, 22);
                *(_BYTE *)(Pool2 + 16) = BYTE2(v42.SAEIndicationType);
                *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
                v22 = v42.SAEIndicationType;
                v17[8] = 40;
                *((_WORD *)v17 + 4) = v22;
                v23 = v42.SAECommitResponse.ElementCount;
                v17[9] = v42.SAECommitResponse.ElementCount;
                *(_OWORD *)v44 = 0;
                memmove(v17 + 10, v42.SAECommitResponse.pElements, v23);
                if ( GetSimpleAttribute(
                       v42.SAECommitResponse.pElements,
                       v42.SAECommitResponse.ElementCount,
                       0x11u,
                       &v42.SAEStatus,
                       5u) >= 0
                  && (int)WFDGetGroupID(v42.SAECommitResponse.pElements, v42.SAECommitResponse.ElementCount, &v40, v44) >= 0
                  && (int)WFDConvertGroupIDFromOTAtoDot11(v44, (unsigned int)v40, &v43) >= 0
                  && GetSimpleAttribute(
                       v42.SAECommitResponse.pElements,
                       v42.SAECommitResponse.ElementCount,
                       7u,
                       v45,
                       6u) >= 0 )
                {
                  v3 = 1;
                }
LABEL_54:
                v28 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
                if ( CPropertyCache::SetPropertyBuffer(v28, 0x31u, a2, v41)
                  && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v29) = 2;
                  WPP_RECORDER_SF_qD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v29,
                    v30,
                    366,
                    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                    (char)this,
                    this->m_WfcPortId);
                }
                if ( !v3 )
                  goto LABEL_67;
                m_pAdapter = this->m_pAdapter;
                BSSEntryByGroupID = CBSSListManager::FindBSSEntryByGroupID(
                                      &m_pAdapter->m_DevicePortBSSList,
                                      &v43,
                                      1,
                                      1,
                                      1);
                if ( !BSSEntryByGroupID )
                {
                  v33 = (CBSSEntry *)ExAllocatePool2(64, 800, 1198089303);
                  if ( !v33 )
                    goto LABEL_67;
                  v34 = CBSSEntry::CBSSEntry(v33, (const unsigned __int8 (*)[6])v45, 0);
                  BSSEntryByGroupID = v34;
                  if ( !v34 )
                    goto LABEL_67;
                  LOBYTE(v36) = 1;
                  *(_OWORD *)v34->m_GroupId.DeviceAddress = *(_OWORD *)v43.DeviceAddress;
                  *(_OWORD *)&v34->m_GroupId.SSID.ucSSID[4] = *(_OWORD *)&v43.SSID.ucSSID[4];
                  *(_OWORD *)&v34->m_GroupId.SSID.ucSSID[16] = *(_OWORD *)&v43.SSID.ucSSID[16];
                  if ( m_pAdapter->m_DevicePortBSSList.AddBSSEntry(&m_pAdapter->m_DevicePortBSSList, v34, v35, v36) )
                  {
                    ((void (__fastcall *)(struct CBSSEntry *, __int64))BSSEntryByGroupID->~CBSSEntry)(
                      BSSEntryByGroupID,
                      1);
LABEL_67:
                    CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisPortNumber, v13, 0, v17, v14);
LABEL_68:
                    operator delete(v17);
                    goto LABEL_69;
                  }
                }
                v37 = &this->m_pAdapter->IPropertyCacheDirectory;
                *(_DWORD *)v45 = 0;
                v40 = WDI_BAND_ID_UNKNOWN;
                v38 = v37->GetAdapterPropertyCache(v37);
                if ( !(unsigned int)ConvertP2PChannelToBandChannel(
                                      v38,
                                      (struct _WFD_OTA_CHANNEL *)&v42.SAEStatus,
                                      &v40,
                                      (unsigned int *)v45) )
                {
                  v39 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
                  CBSSEntry::SetChannelAndPhyID(BSSEntryByGroupID, 0, v39, *(unsigned int *)v45, v40);
                }
                if ( m_pAdapter->m_DevicePortBSSList.m_BackgroundDiscoveryEnabled )
                  CBSSEntry::UpdateBackgroundDeviceIndicatedByDriver(BSSEntryByGroupID, this->m_pAdapter);
                goto LABEL_67;
            }
            if ( *(_DWORD *)v42.BssId.Address != 5 )
            {
              if ( *(_DWORD *)v42.BssId.Address == 6 )
              {
                *(_DWORD *)Pool2 = 2621824;
                *(_BYTE *)(Pool2 + 16) = BYTE2(v42.SAEIndicationType);
                *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
                v21 = v42.SAEIndicationType;
                v17[8] = 40;
                v19 = v17 + 10;
                *((_WORD *)v17 + 4) = v21;
                v20 = v42.SAECommitResponse.ElementCount;
                v17[9] = v42.SAECommitResponse.ElementCount;
                goto LABEL_52;
              }
              if ( *(_DWORD *)v42.BssId.Address != 7 )
              {
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v11) = 2;
                  WPP_RECORDER_SF_qD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v11,
                    v16,
                    365,
                    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                    (char)this,
                    this->m_WfcPortId);
                }
                goto LABEL_68;
              }
            }
            *(_DWORD *)Pool2 = 1835392;
            *(_BYTE *)(Pool2 + 16) = BYTE2(v42.SAEIndicationType);
            *(_DWORD *)(Pool2 + 4) = *(_DWORD *)&v42.BssId.Address[4];
            v18 = v42.SAEIndicationType;
            v17[5] = 28;
            v19 = v17 + 7;
            *((_WORD *)v17 + 4) = v18;
            v20 = v42.SAECommitResponse.ElementCount;
            v17[6] = v42.SAECommitResponse.ElementCount;
LABEL_52:
            memmove(v19, v42.SAECommitResponse.pElements, v20);
            goto LABEL_54;
          default:
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_73;
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              40,
              362,
              (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
              (char)this,
              this->m_WfcPortId);
            goto LABEL_69;
        }
        v12 = 40;
        goto LABEL_26;
      }
      v13 = 1073938455;
    }
    v12 = 32;
    goto LABEL_26;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    goto LABEL_73;
  LOBYTE(v8) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v8,
    v9,
    361,
    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
    (char)this,
    this->m_WfcPortId,
    v7);
LABEL_69:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      367,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v10);
  }
LABEL_73:
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS(&v42);
}

```

## disassembly

```asm
0x1400b40f4  mov     [rsp-8+arg_18], rbx
0x1400b40f9  push    rbp
0x1400b40fa  push    rsi
0x1400b40fb  push    rdi
0x1400b40fc  push    r12
0x1400b40fe  push    r13
0x1400b4100  push    r14
0x1400b4102  push    r15
0x1400b4104  lea     rbp, [rsp-10h]
0x1400b4109  sub     rsp, 110h
0x1400b4110  mov     rax, cs:__security_cookie
0x1400b4117  xor     rax, rsp
0x1400b411a  mov     [rbp+40h+var_38], rax
0x1400b411e  and     dword ptr [rsp+140h+var_E0.Optional.SAECommitResponse_IsPresent], 0FFFFFFFEh
0x1400b4123  xor     eax, eax
0x1400b4125  xor     esi, esi
0x1400b4127  mov     qword ptr [rsp+140h+var_E0.BssId.Address], rax
0x1400b412c  mov     qword ptr [rsp+140h+var_E0.SAEIndicationType], rax
0x1400b4131  mov     rbx, r8
0x1400b4134  mov     [rbp+40h+var_E0.SAEStatus], eax
0x1400b4137  xorps   xmm0, xmm0
0x1400b413a  mov     byte ptr [rbp+40h+var_E0+44h], al
0x1400b413d  mov     r15d, edx
0x1400b4140  mov     qword ptr [rbp+40h+var_98.DeviceAddress], rax
0x1400b4144  mov     rdi, rcx
0x1400b4147  mov     rax, 2D544345524944h
0x1400b4151  mov     [rsp+140h+var_E8], rbx
0x1400b4156  mov     qword ptr [rbp+40h+var_98.SSID.ucSSID], rax
0x1400b415a  xor     eax, eax
0x1400b415c  mov     qword ptr [rbp+40h+var_98.SSID.ucSSID+18h], rax
0x1400b4160  mov     [rsp+140h+var_E0.SAECommitResponse.pElements], rsi
0x1400b4165  mov     [rbp+40h+var_E0.SAECommitResponse.MemoryInternallyAllocated], sil
0x1400b4169  mov     [rbp+40h+var_E0.SAEConfirmResponse.ElementCount], esi
0x1400b416c  mov     [rbp+40h+var_E0.SAEConfirmResponse.pElements], rsi
0x1400b4170  mov     [rbp+40h+var_E0.SAEConfirmResponse.MemoryInternallyAllocated], sil
0x1400b4174  mov     [rbp+40h+var_98.SSID.uSSIDLength], 7
0x1400b417b  movups  xmmword ptr [rbp+40h+var_98.SSID.ucSSID+8], xmm0
0x1400b417f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b4186  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b418d  lea     edx, [rsi+5]
0x1400b4190  lea     r13, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b4197  lea     r14d, [rsi+1]
0x1400b419b  jz      short loc_1400B41C6
0x1400b419d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b41a4  cmp     [rcx+29h], dl
0x1400b41a7  jnb     short loc_1400B41AF
0x1400b41a9  cmp     [rcx+48h], si
0x1400b41ad  jz      short loc_1400B41C6
0x1400b41af  mov     rcx, [rcx+40h]
0x1400b41b3  mov     r9d, 168h
0x1400b41b9  mov     r8d, r14d
0x1400b41bc  mov     qword ptr [rsp+140h+var_120], r13
0x1400b41c1  call    WPP_RECORDER_SF_
0x1400b41c6  mov     r8, [rdi+58h]
0x1400b41ca  lea     rdx, [rbx+30h]
0x1400b41ce  add     r8, 3FF8h
0x1400b41d5  lea     ecx, [r15-30h]
0x1400b41d9  lea     r9, [rsp+140h+var_E0]
0x1400b41de  call    ParseWdiIndicationP2pActionFrameReceivedFromIhv
0x1400b41e3  mov     r12d, eax
0x1400b41e6  test    eax, eax
0x1400b41e8  jz      short loc_1400B4232
0x1400b41ea  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b41f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b41f8  jz      loc_1400B48B6
0x1400b41fe  movzx   ecx, word ptr [rdi+64h]
0x1400b4202  mov     r9d, 169h
0x1400b4208  mov     [rsp+140h+var_108], r12d
0x1400b420d  mov     dl, 2
0x1400b420f  mov     [rsp+140h+var_110], ecx
0x1400b4213  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b421a  mov     qword ptr [rsp+140h+var_118], rdi
0x1400b421f  mov     qword ptr [rsp+140h+var_120], r13
0x1400b4224  mov     rcx, [rcx+40h]
0x1400b4228  call    WPP_RECORDER_SF_qDD
0x1400b422d  jmp     loc_1400B4871
0x1400b4232  movzx   eax, word ptr [rsp+140h+var_E0.SAEIndicationType]
0x1400b4237  mov     ecx, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b423b  mov     dword ptr [rbp+40h+var_98.DeviceAddress], ecx
0x1400b423e  mov     dword ptr [rbp+40h+var_40], ecx
0x1400b4241  mov     ecx, dword ptr [rsp+140h+var_E0.BssId.Address]
0x1400b4245  mov     word ptr [rbp+40h+var_98.DeviceAddress+4], ax
0x1400b4249  mov     word ptr [rbp+40h+var_40+4], ax
0x1400b424d  mov     eax, 1Ch
0x1400b4252  lea     edx, [rax+4]
0x1400b4255  lea     r8d, [rax+0Ch]
0x1400b4259  sub     ecx, r14d
0x1400b425c  jz      loc_1400B42FF
0x1400b4262  sub     ecx, r14d
0x1400b4265  jz      loc_1400B42F7
0x1400b426b  sub     ecx, r14d
0x1400b426e  jz      short loc_1400B42EA
0x1400b4270  sub     ecx, r14d
0x1400b4273  jz      short loc_1400B42DF
0x1400b4275  sub     ecx, r14d
0x1400b4278  jz      short loc_1400B42D7
0x1400b427a  sub     ecx, r14d
0x1400b427d  jz      short loc_1400B42CF
0x1400b427f  cmp     ecx, r14d
0x1400b4282  jz      short loc_1400B42C7
0x1400b4284  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b428b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b4292  jz      loc_1400B48B6
0x1400b4298  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b429f  mov     r9d, 16Ah
0x1400b42a5  movzx   eax, word ptr [rdi+64h]
0x1400b42a9  mov     dl, 2
0x1400b42ab  mov     [rsp+140h+var_110], eax
0x1400b42af  mov     qword ptr [rsp+140h+var_118], rdi
0x1400b42b4  mov     rcx, [rcx+40h]
0x1400b42b8  mov     qword ptr [rsp+140h+var_120], r13
0x1400b42bd  call    WPP_RECORDER_SF_qD
0x1400b42c2  jmp     loc_1400B4871
0x1400b42c7  mov     r14d, 40030021h
0x1400b42cd  jmp     short loc_1400B4307
0x1400b42cf  mov     r14d, 4003001Fh
0x1400b42d5  jmp     short loc_1400B42E5
0x1400b42d7  mov     r14d, 4003001Dh
0x1400b42dd  jmp     short loc_1400B4307
0x1400b42df  mov     r14d, 4003001Bh
0x1400b42e5  mov     eax, r8d
0x1400b42e8  jmp     short loc_1400B4307
0x1400b42ea  mov     eax, 14h
0x1400b42ef  mov     r14d, 40030019h
0x1400b42f5  jmp     short loc_1400B4307
0x1400b42f7  mov     r14d, 40030017h
0x1400b42fd  jmp     short loc_1400B4305
0x1400b42ff  mov     r14d, 40030015h
0x1400b4305  mov     eax, edx
0x1400b4307  mov     ecx, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b430b  lea     r13d, [rcx+rax]
0x1400b430f  cmp     r13d, eax
0x1400b4312  jnb     short loc_1400B4374
0x1400b4314  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b431b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b4322  lea     r13, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b4329  jz      short loc_1400B4369
0x1400b432b  movzx   eax, word ptr [rdi+64h]
0x1400b432f  mov     r9d, 16Bh
0x1400b4335  mov     [rsp+140h+var_F8], 0C0000001h
0x1400b433d  mov     dl, 2
0x1400b433f  mov     [rsp+140h+var_100], 0FFFFFFFFh
0x1400b4347  mov     [rsp+140h+var_108], ecx
0x1400b434b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4352  mov     [rsp+140h+var_110], eax
0x1400b4356  mov     qword ptr [rsp+140h+var_118], rdi
0x1400b435b  mov     qword ptr [rsp+140h+var_120], r13
0x1400b4360  mov     rcx, [rcx+40h]
0x1400b4364  call    WPP_RECORDER_SF_qDDDD
0x1400b4369  mov     r12d, 0C0000001h
0x1400b436f  jmp     loc_1400B486B
0x1400b4374  mov     edx, r13d
0x1400b4377  mov     ecx, 40h ; '@'
0x1400b437c  mov     r8d, 47696457h
0x1400b4382  call    cs:__imp_ExAllocatePool2
0x1400b4389  nop     dword ptr [rax+rax+00h]
0x1400b438e  mov     rbx, rax
0x1400b4391  test    rax, rax
0x1400b4394  jnz     short loc_1400B43E2
0x1400b4396  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b439d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b43a4  lea     r13, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b43ab  jz      short loc_1400B43D7
0x1400b43ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b43b4  mov     r9d, 16Ch
0x1400b43ba  movzx   eax, word ptr [rdi+64h]
0x1400b43be  mov     dl, 2
0x1400b43c0  mov     [rsp+140h+var_110], eax
0x1400b43c4  mov     qword ptr [rsp+140h+var_118], rdi
0x1400b43c9  mov     rcx, [rcx+40h]
0x1400b43cd  mov     qword ptr [rsp+140h+var_120], r13
0x1400b43d2  call    WPP_RECORDER_SF_qD
0x1400b43d7  mov     r12d, 0C000009Ah
0x1400b43dd  jmp     loc_1400B486B
0x1400b43e2  mov     ecx, dword ptr [rsp+140h+var_E0.BssId.Address]
0x1400b43e6  sub     ecx, 1
0x1400b43e9  jz      loc_1400B461A
0x1400b43ef  sub     ecx, 1
0x1400b43f2  jz      loc_1400B45DB
0x1400b43f8  sub     ecx, 1
0x1400b43fb  jz      loc_1400B45A9
0x1400b4401  sub     ecx, 1
0x1400b4404  jz      loc_1400B44D1
0x1400b440a  sub     ecx, 1
0x1400b440d  jz      short loc_1400B4467
0x1400b440f  sub     ecx, 1
0x1400b4412  jz      loc_1400B449C
0x1400b4418  cmp     ecx, 1
0x1400b441b  jz      short loc_1400B4467
0x1400b441d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b4424  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b442b  lea     r13, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b4432  jz      loc_1400B4861
0x1400b4438  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b443f  mov     r9d, 16Dh
0x1400b4445  movzx   eax, word ptr [rdi+64h]
0x1400b4449  mov     dl, 2
0x1400b444b  mov     [rsp+140h+var_110], eax
0x1400b444f  mov     qword ptr [rsp+140h+var_118], rdi
0x1400b4454  mov     rcx, [rcx+40h]
0x1400b4458  mov     qword ptr [rsp+140h+var_120], r13
0x1400b445d  call    WPP_RECORDER_SF_qD
0x1400b4462  jmp     loc_1400B4861
0x1400b4467  mov     dword ptr [rax], 1C0180h
0x1400b446d  mov     ecx, 1Ch
0x1400b4472  mov     al, byte ptr [rsp+140h+var_E0.SAEIndicationType+2]
0x1400b4476  mov     [rbx+10h], al
0x1400b4479  mov     eax, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b447d  mov     [rbx+4], eax
0x1400b4480  movzx   eax, word ptr [rsp+140h+var_E0.SAEIndicationType]
0x1400b4485  mov     [rbx+14h], ecx
0x1400b4488  lea     rcx, [rbx+1Ch]
0x1400b448c  mov     [rbx+8], ax
0x1400b4490  mov     eax, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b4494  mov     [rbx+18h], eax
0x1400b4497  jmp     loc_1400B460B
0x1400b449c  mov     dword ptr [rax], 280180h
0x1400b44a2  mov     ecx, 28h ; '('
0x1400b44a7  mov     al, byte ptr [rsp+140h+var_E0.SAEIndicationType+2]
0x1400b44ab  mov     [rbx+10h], al
0x1400b44ae  mov     eax, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b44b2  mov     [rbx+4], eax
0x1400b44b5  movzx   eax, word ptr [rsp+140h+var_E0.SAEIndicationType]
0x1400b44ba  mov     [rbx+20h], ecx
0x1400b44bd  lea     rcx, [rbx+28h]
0x1400b44c1  mov     [rbx+8], ax
0x1400b44c5  mov     eax, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b44c9  mov     [rbx+24h], eax
0x1400b44cc  jmp     loc_1400B460B
0x1400b44d1  xor     eax, eax
0x1400b44d3  mov     dword ptr [rbx], 280180h
0x1400b44d9  mov     [rsp+140h+var_F0], eax
0x1400b44dd  xorps   xmm0, xmm0
0x1400b44e0  movups  xmmword ptr [rbp+40h+var_58], xmm0
0x1400b44e4  mov     qword ptr [rbp+40h+var_58+0Eh], rax
0x1400b44e8  lea     ecx, [rax+28h]
0x1400b44eb  mov     al, byte ptr [rsp+140h+var_E0.SAEIndicationType+2]
0x1400b44ef  mov     [rbx+10h], al
0x1400b44f2  mov     eax, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b44f6  mov     [rbx+4], eax
0x1400b44f9  movzx   eax, word ptr [rsp+140h+var_E0.SAEIndicationType]
0x1400b44fe  mov     [rbx+20h], ecx
0x1400b4501  lea     rcx, [rbx+28h]; void *
0x1400b4505  mov     [rbx+8], ax
0x1400b4509  mov     eax, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b450d  mov     [rbx+24h], eax
0x1400b4510  mov     r8d, eax; Size
0x1400b4513  mov     rdx, [rsp+140h+var_E0.SAECommitResponse.pElements]; Src
0x1400b4518  movups  [rbp+40h+var_68], xmm0
0x1400b451c  call    memmove
0x1400b4521  mov     edx, [rsp+140h+var_E0.SAECommitResponse.ElementCount]; unsigned int
0x1400b4525  lea     r9, [rbp+40h+var_E0.SAEStatus]; void *
0x1400b4529  mov     rcx, [rsp+140h+var_E0.SAECommitResponse.pElements]; unsigned __int8 *
0x1400b452e  mov     r8b, 11h; unsigned __int8
0x1400b4531  mov     word ptr [rsp+140h+var_120], 5; unsigned __int16
0x1400b4538  call    ?GetSimpleAttribute@@YAJPEAEKEPEAXG@Z; GetSimpleAttribute(uchar *,ulong,uchar,void *,ushort)
0x1400b453d  test    eax, eax
0x1400b453f  js      loc_1400B4684
0x1400b4545  mov     edx, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b4549  lea     r9, [rbp+40h+var_68]
0x1400b454d  mov     rcx, [rsp+140h+var_E0.SAECommitResponse.pElements]
0x1400b4552  lea     r8, [rsp+140h+var_F0]
0x1400b4557  call    WFDGetGroupID
0x1400b455c  test    eax, eax
0x1400b455e  js      loc_1400B4684
0x1400b4564  mov     edx, [rsp+140h+var_F0]
0x1400b4568  lea     r8, [rbp+40h+var_98]
0x1400b456c  lea     rcx, [rbp+40h+var_68]
0x1400b4570  call    WFDConvertGroupIDFromOTAtoDot11
0x1400b4575  test    eax, eax
0x1400b4577  js      loc_1400B4684
0x1400b457d  mov     edx, [rsp+140h+var_E0.SAECommitResponse.ElementCount]; unsigned int
0x1400b4581  lea     r9, [rbp+40h+var_40]; void *
0x1400b4585  mov     rcx, [rsp+140h+var_E0.SAECommitResponse.pElements]; unsigned __int8 *
0x1400b458a  mov     r8b, 7; unsigned __int8
0x1400b458d  mov     word ptr [rsp+140h+var_120], 6; unsigned __int16
0x1400b4594  call    ?GetSimpleAttribute@@YAJPEAEKEPEAXG@Z; GetSimpleAttribute(uchar *,ulong,uchar,void *,ushort)
0x1400b4599  test    eax, eax
0x1400b459b  js      loc_1400B4684
0x1400b45a1  mov     sil, 1
0x1400b45a4  jmp     loc_1400B4684
0x1400b45a9  mov     dword ptr [rax], 140180h
0x1400b45af  mov     ecx, 14h
0x1400b45b4  mov     al, byte ptr [rsp+140h+var_E0.SAEIndicationType+2]
0x1400b45b8  mov     [rbx+0Ah], al
0x1400b45bb  mov     eax, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b45bf  mov     [rbx+4], eax
0x1400b45c2  movzx   eax, word ptr [rsp+140h+var_E0.SAEIndicationType]
0x1400b45c7  mov     [rbx+0Ch], ecx
0x1400b45ca  lea     rcx, [rbx+14h]
0x1400b45ce  mov     [rbx+8], ax
0x1400b45d2  mov     eax, [rsp+140h+var_E0.SAECommitResponse.ElementCount]
0x1400b45d6  mov     [rbx+10h], eax
0x1400b45d9  jmp     short loc_1400B460B
0x1400b45db  mov     dword ptr [rax], 200180h
0x1400b45e1  mov     ecx, 20h ; ' '
0x1400b45e6  mov     al, byte ptr [rsp+140h+var_E0.SAEIndicationType+2]
0x1400b45ea  mov     [rbx+0Ah], al
0x1400b45ed  mov     eax, dword ptr [rsp+140h+var_E0.BssId.Address+4]
0x1400b45f1  mov     [rbx+4], eax
  ... truncated ...
```
