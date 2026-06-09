# CP2PDiscoverJob::InitializeDiscoverByGroupID(CAdapter *,ulong,_DOT11_WFD_GROUP_ID const &,bool,bool,bool,bool,_DOT11_WFD_CHANNEL *,CBSSEntry *)

- ea: `0x1400c9de8`
- end: `0x1400ca2e9`
- name: `?InitializeDiscoverByGroupID@CP2PDiscoverJob@@QEAAHPEAVCAdapter@@KAEBU_DOT11_WFD_GROUP_ID@@_N222PEAU_DOT11_WFD_CHANNEL@@PEAVCBSSEntry@@@Z`
- size: `1281`
- prototype: `__int64 __usercall@<rax>(CP2PDiscoverJob *__hidden this@<rcx>, struct CAdapter *@<rdx>, unsigned int@<r8d>, const struct _DOT11_WFD_GROUP_ID *@<r9>, bool, bool, bool, bool, struct _DOT11_WFD_CHANNEL *, struct CBSSEntry *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140023f24`
- `0x1400475b0`
- `0x1400cdd70`

## callees

- `0x1400122e0`
- `0x140023ae0`
- `0x140028764`
- `0x14002aa28`
- `0x1400adf18`
- `0x1400c9de8`
- `0x1400ce9dc`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400ca0df`
- `ntoskrnl!RtlCompareMemory` at `0x1400ca0df`
- `ntoskrnl!ExAllocatePool2` at `0x1400ca03f`
- `ntoskrnl!ExAllocatePool2` at `0x1400ca03f`

## pseudocode

```c
__int64 __fastcall CP2PDiscoverJob::InitializeDiscoverByGroupID(
        CP2PDiscoverJob *this,
        struct CAdapter *a2,
        unsigned int a3,
        const struct _DOT11_WFD_GROUP_ID *a4,
        char a5,
        char a6,
        char a7,
        bool a8,
        struct _DOT11_WFD_CHANNEL *a9,
        struct CBSSEntry *a10)
{
  struct CAdapter *v12; // rbp
  unsigned __int8 *m_pIndicationBuffer; // rcx
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *m_pDeviceFilterList; // rcx
  unsigned int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ebp
  int v21; // r9d
  _DOT11_SSID *p_SSID; // r15
  unsigned int v23; // eax
  __int64 Pool2; // rax
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *v25; // rcx
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *v26; // rax
  CAdapterPropertyCache *v27; // rax
  int v29; // [rsp+20h] [rbp-78h]
  enum _WFC_SERIALIZED_JOB_PRIORITY m_ActivityId; // [rsp+30h] [rbp-68h]
  char v31; // [rsp+38h] [rbp-60h]

  v12 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      87,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  m_pIndicationBuffer = this->m_pIndicationBuffer;
  if ( m_pIndicationBuffer )
  {
    operator delete(m_pIndicationBuffer);
    this->m_pIndicationBuffer = 0;
  }
  m_pDeviceFilterList = this->m_pDeviceFilterList;
  if ( m_pDeviceFilterList )
  {
    operator delete(m_pDeviceFilterList);
    this->m_pDeviceFilterList = 0;
  }
  v16 = COidJobBase::InitializeWithoutOid(
          this,
          WiFiJobP2PDiscover,
          v12,
          1,
          0,
          WiFiPriorityScopeAdapter,
          WiFiSerializedJobPriority_Lowest,
          a3,
          0);
  v20 = v16;
  if ( v16 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v20;
    v21 = 88;
    v31 = v16;
    m_ActivityId = this->m_ActivityId;
  }
  else
  {
    p_SSID = &a4->SSID;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qD_SSID__MAC_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        a9 != 0,
        v18,
        v19,
        v29,
        (char)this,
        this->m_ActivityId,
        (__int64)&a4->SSID,
        (__int64)a4,
        a5,
        a6,
        a9 != 0);
    *((_BYTE *)this + 1153) |= 8u;
    *(_OWORD *)this->m_TargetGroupID.DeviceAddress = *(_OWORD *)a4->DeviceAddress;
    *(_OWORD *)&this->m_TargetGroupID.SSID.ucSSID[4] = *(_OWORD *)&a4->SSID.ucSSID[4];
    *(_OWORD *)&this->m_TargetGroupID.SSID.ucSSID[16] = *(_OWORD *)&a4->SSID.ucSSID[16];
    if ( a6 || !a5 )
    {
      v23 = 5000;
      if ( !a8 )
        v23 = 15000;
    }
    else
    {
      v23 = 120000;
    }
    *(_DWORD *)&this->m_DiscoverParameters.Optional |= 2u;
    this->m_DiscoverTimeoutInMs = v23;
    this->m_DiscoverParameters.DwellTime.MaximumScanTime = v23;
    this->m_RemainingTimeoutInMs = v23;
    this->m_DiscoverParameters.DiscoverMode.DiscoveryType = WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS;
    this->m_DiscoverParameters.DiscoverMode.ForcedDiscovery = 1;
    this->m_DiscoverParameters.SSIDList.ElementCount = 1;
    this->m_DeviceFilterCount = 1;
    this->m_DefaultDiscoverSSIDs[0].pElements = this->m_TargetGroupID.SSID.ucSSID;
    this->m_DefaultDiscoverSSIDs[0].ElementCount = this->m_TargetGroupID.SSID.uSSIDLength;
    this->m_DiscoverParameters.SSIDList.pElements = this->m_DefaultDiscoverSSIDs;
    this->m_DiscoverParameters.DiscoverMode.ScanType = WDI_P2P_SCAN_TYPE_AUTO;
    this->m_DiscoverParameters.DiscoverMode.ScanRepeatCount = 0;
    this->m_DiscoverParameters.DiscoverMode.TimeBetweenScans = 50;
    this->m_DiscoverParameters.DwellTime.ActiveChannelDwellTime = 40;
    this->m_DiscoverParameters.DwellTime.PassiveChannelDwellTime = 100;
    Pool2 = ExAllocatePool2(64, 44, 1198089303);
    this->m_pDeviceFilterList = (_DOT11_WFD_DISCOVER_DEVICE_FILTER *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = *(_DWORD *)a4->DeviceAddress;
      *(_WORD *)(Pool2 + 4) = *(_WORD *)&a4->DeviceAddress[4];
      v25 = this->m_pDeviceFilterList;
      *(_OWORD *)&v25->GroupSSID.uSSIDLength = *(_OWORD *)&p_SSID->uSSIDLength;
      *(_OWORD *)&v25->GroupSSID.ucSSID[12] = *(_OWORD *)&a4->SSID.ucSSID[12];
      *(_DWORD *)&v25->GroupSSID.ucSSID[28] = *(_DWORD *)&a4->SSID.ucSSID[28];
      this->m_pDeviceFilterList->ucBitmask = 1;
      if ( p_SSID->uSSIDLength != 7 || RtlCompareMemory(a4->SSID.ucSSID, "DIRECT-", 7u) != 7 )
      {
        v26 = this->m_pDeviceFilterList;
        this->m_DiscoverParameters.DiscoverMode.DiscoveryType = WDI_P2P_DISCOVER_TYPE_SCAN_ONLY;
        v26->ucBitmask = 2;
      }
      *((_BYTE *)this + 1152) = (8 * a5) | (16 * a6) | *((_BYTE *)this + 1152) & 0xE7;
      if ( a9 )
      {
        v27 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
        if ( !(unsigned int)ConvertP2PChannelToBandChannel(
                              v27,
                              (struct _WFD_OTA_CHANNEL *)a9,
                              &this->m_ChannelHintBandInfo.BandID,
                              &this->m_ChannelHintChannelNumber) )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              v18,
              91,
              (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          *((_BYTE *)this + 1152) |= 0x20u;
        }
      }
      if ( (*((_BYTE *)this + 1152) & 0x20) == 0 && a10 )
      {
        if ( a10->m_CachedChannelInfoAvailable )
        {
          this->m_ChannelHintBandInfo.BandID = a10->m_CachedBandID;
          this->m_ChannelHintChannelNumber = a10->m_CachedChannelNumber;
        }
        if ( a10->m_CachedChannelInfoAvailable )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              v18,
              92,
              (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          *((_BYTE *)this + 1152) |= 0x20u;
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v18,
          93,
          (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
          (char)this,
          this->m_ActivityId,
          a7);
      }
      *((_BYTE *)this + 1153) = (4 * a7) | *((_BYTE *)this + 1153) & 0xFB;
      goto LABEL_42;
    }
    v20 = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v20;
    v21 = 90;
    v31 = -102;
    m_ActivityId = this->m_ActivityId;
  }
  LOBYTE(v17) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v17,
    v18,
    v21,
    (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
    (char)this,
    m_ActivityId,
    v31);
LABEL_42:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      v18,
      94,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId,
      v20);
  }
  return v20;
}

```

## disassembly

```asm
0x1400c9de8  push    rbx
0x1400c9dea  push    rbp
0x1400c9deb  push    rsi
0x1400c9dec  push    rdi
0x1400c9ded  push    r13
0x1400c9def  push    r14
0x1400c9df1  push    r15
0x1400c9df3  sub     rsp, 60h
0x1400c9df7  mov     rbx, r9
0x1400c9dfa  mov     edi, r8d
0x1400c9dfd  mov     rbp, rdx
0x1400c9e00  mov     rsi, rcx
0x1400c9e03  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c9e0a  xor     r13d, r13d
0x1400c9e0d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400c9e14  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c9e1b  jz      short loc_1400C9E53
0x1400c9e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9e24  cmp     byte ptr [rcx+29h], 5
0x1400c9e28  jnb     short loc_1400C9E31
0x1400c9e2a  cmp     [rcx+48h], r13w
0x1400c9e2f  jz      short loc_1400C9E53
0x1400c9e31  mov     eax, [rsi+10h]
0x1400c9e34  mov     r9d, 57h ; 'W'
0x1400c9e3a  mov     rcx, [rcx+40h]
0x1400c9e3e  mov     dl, 5
0x1400c9e40  mov     [rsp+98h+var_68], eax
0x1400c9e44  mov     qword ptr [rsp+98h+var_70], rsi
0x1400c9e49  mov     qword ptr [rsp+98h+var_78], r14
0x1400c9e4e  call    WPP_RECORDER_SF_qD
0x1400c9e53  mov     rcx, [rsi+5B8h]; void *
0x1400c9e5a  test    rcx, rcx
0x1400c9e5d  jz      short loc_1400C9E6B
0x1400c9e5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c9e64  mov     [rsi+5B8h], r13
0x1400c9e6b  mov     rcx, [rsi+4A0h]; void *
0x1400c9e72  test    rcx, rcx
0x1400c9e75  jz      short loc_1400C9E83
0x1400c9e77  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c9e7c  mov     [rsi+4A0h], r13
0x1400c9e83  mov     [rsp+98h+var_58], r13b; bool
0x1400c9e88  mov     r9b, 1; bool
0x1400c9e8b  mov     [rsp+98h+var_60], edi; unsigned int
0x1400c9e8f  mov     r8, rbp; struct CAdapter *
0x1400c9e92  mov     [rsp+98h+var_68], 0Ch; enum _WFC_SERIALIZED_JOB_PRIORITY
0x1400c9e9a  mov     edx, 82h; enum _WFC_JOB_TYPE
0x1400c9e9f  mov     [rsp+98h+var_70], 1; enum _WFC_SERIALIZED_JOB_PRIORITY_SCOPE
0x1400c9ea7  mov     rcx, rsi; this
0x1400c9eaa  mov     [rsp+98h+var_78], r13b; bool
0x1400c9eaf  call    ?InitializeWithoutOid@COidJobBase@@IEAAHW4_WFC_JOB_TYPE@@PEAVCAdapter@@_N2W4_WFC_SERIALIZED_JOB_PRIORITY_SCOPE@@W4_WFC_SERIALIZED_JOB_PRIORITY@@K2@Z; COidJobBase::InitializeWithoutOid(_WFC_JOB_TYPE,CAdapter *,bool,bool,_WFC_SERIALIZED_JOB_PRIORITY_SCOPE,_WFC_SERIALIZED_JOB_PRIORITY,ulong,bool)
0x1400c9eb4  mov     ebp, eax
0x1400c9eb6  test    eax, eax
0x1400c9eb8  jz      short loc_1400C9EF9
0x1400c9eba  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400c9ec1  jz      loc_1400CA2D7
0x1400c9ec7  mov     ecx, [rsi+10h]
0x1400c9eca  mov     r9d, 58h ; 'X'
0x1400c9ed0  mov     [rsp+98h+var_60], eax
0x1400c9ed4  mov     [rsp+98h+var_68], ecx
0x1400c9ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9edf  mov     dl, 2
0x1400c9ee1  mov     qword ptr [rsp+98h+var_70], rsi
0x1400c9ee6  mov     qword ptr [rsp+98h+var_78], r14
0x1400c9eeb  mov     rcx, [rcx+40h]
0x1400c9eef  call    WPP_RECORDER_SF_qDD
0x1400c9ef4  jmp     loc_1400CA294
0x1400c9ef9  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400c9f00  lea     r15, [rbx+8]
0x1400c9f04  movzx   r14d, [rsp+98h+arg_28]
0x1400c9f0d  movzx   edi, [rsp+98h+arg_20]
0x1400c9f15  jz      short loc_1400C9F58
0x1400c9f17  cmp     [rsp+98h+arg_40], r13
0x1400c9f1f  mov     edx, r13d
0x1400c9f22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9f29  mov     eax, [rsi+10h]
0x1400c9f2c  setnz   dl
0x1400c9f2f  mov     [rsp+98h+var_40], edx
0x1400c9f33  mov     [rsp+98h+var_48], r14d
0x1400c9f38  mov     rcx, [rcx+40h]
0x1400c9f3c  mov     [rsp+98h+var_50], edi
0x1400c9f40  mov     qword ptr [rsp+98h+var_58], rbx
0x1400c9f45  mov     qword ptr [rsp+98h+var_60], r15
0x1400c9f4a  mov     [rsp+98h+var_68], eax
0x1400c9f4e  mov     qword ptr [rsp+98h+var_70], rsi
0x1400c9f53  call    WPP_RECORDER_SF_qD_SSID__MAC_ddd
0x1400c9f58  or      byte ptr [rsi+481h], 8
0x1400c9f5f  movups  xmm0, xmmword ptr [rbx]
0x1400c9f62  movups  xmmword ptr [rsi+270h], xmm0
0x1400c9f69  movups  xmm1, xmmword ptr [rbx+10h]
0x1400c9f6d  movups  xmmword ptr [rsi+280h], xmm1
0x1400c9f74  movups  xmm0, xmmword ptr [rbx+1Ch]
0x1400c9f78  movups  xmmword ptr [rsi+28Ch], xmm0
0x1400c9f7f  test    r14b, r14b
0x1400c9f82  jnz     short loc_1400C9F90
0x1400c9f84  test    dil, dil
0x1400c9f87  jz      short loc_1400C9F90
0x1400c9f89  mov     eax, 1D4C0h
0x1400c9f8e  jmp     short loc_1400C9FA4
0x1400c9f90  mov     eax, 1388h
0x1400c9f95  cmp     [rsp+98h+arg_38], r13b
0x1400c9f9d  jnz     short loc_1400C9FA4
0x1400c9f9f  mov     eax, 3A98h
0x1400c9fa4  or      dword ptr [rsi+4F0h], 2
0x1400c9fab  lea     rcx, [rsi+240h]
0x1400c9fb2  mov     edx, 1
0x1400c9fb7  mov     [rsi+29Ch], eax
0x1400c9fbd  mov     [rsi+514h], eax
0x1400c9fc3  mov     r8d, 47696457h
0x1400c9fc9  mov     [rsi+2A0h], eax
0x1400c9fcf  lea     rax, [rsi+27Ch]
0x1400c9fd6  mov     dword ptr [rsi+4F4h], 4
0x1400c9fe0  mov     [rsi+4F8h], dl
0x1400c9fe6  mov     [rsi+530h], edx
0x1400c9fec  mov     [rsi+498h], edx
0x1400c9ff2  mov     edx, 2Ch ; ','
0x1400c9ff7  mov     [rsi+248h], rax
0x1400c9ffe  mov     eax, [rsi+278h]
0x1400ca004  mov     [rcx], eax
0x1400ca006  mov     [rsi+538h], rcx
0x1400ca00d  lea     ecx, [rdx+14h]
0x1400ca010  mov     dword ptr [rsi+4FCh], 3
0x1400ca01a  mov     [rsi+504h], r13b
0x1400ca021  mov     dword ptr [rsi+508h], 32h ; '2'
0x1400ca02b  mov     dword ptr [rsi+50Ch], 28h ; '('
0x1400ca035  mov     dword ptr [rsi+510h], 64h ; 'd'
0x1400ca03f  call    cs:__imp_ExAllocatePool2
0x1400ca046  nop     dword ptr [rax+rax+00h]
0x1400ca04b  mov     [rsi+4A0h], rax
0x1400ca052  mov     rcx, rax
0x1400ca055  test    rax, rax
0x1400ca058  jnz     short loc_1400CA092
0x1400ca05a  mov     ebp, 0C000009Ah
0x1400ca05f  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ca066  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ca06d  jz      loc_1400CA2D7
0x1400ca073  lea     r9d, [rax+5Ah]
0x1400ca077  mov     [rsp+98h+var_60], 0C000009Ah
0x1400ca07f  mov     eax, [rsi+10h]
0x1400ca082  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400ca089  mov     [rsp+98h+var_68], eax
0x1400ca08d  jmp     loc_1400C9ED8
0x1400ca092  mov     eax, [rbx]
0x1400ca094  mov     [rcx], eax
0x1400ca096  movzx   eax, word ptr [rbx+4]
0x1400ca09a  mov     [rcx+4], ax
0x1400ca09e  mov     rcx, [rsi+4A0h]
0x1400ca0a5  movups  xmm0, xmmword ptr [r15]
0x1400ca0a9  movups  xmmword ptr [rcx+8], xmm0
0x1400ca0ad  movups  xmm1, xmmword ptr [r15+10h]
0x1400ca0b2  movups  xmmword ptr [rcx+18h], xmm1
0x1400ca0b6  mov     eax, [r15+20h]
0x1400ca0ba  mov     [rcx+28h], eax
0x1400ca0bd  mov     rax, [rsi+4A0h]
0x1400ca0c4  mov     byte ptr [rax+6], 1
0x1400ca0c8  cmp     dword ptr [r15], 7
0x1400ca0cc  jnz     short loc_1400CA0F1
0x1400ca0ce  lea     rcx, [r15+4]; Source1
0x1400ca0d2  mov     r8d, 7; Length
0x1400ca0d8  lea     rdx, aDirect; "DIRECT-"
0x1400ca0df  call    cs:__imp_RtlCompareMemory
0x1400ca0e6  nop     dword ptr [rax+rax+00h]
0x1400ca0eb  cmp     rax, 7
0x1400ca0ef  jz      short loc_1400CA106
0x1400ca0f1  mov     rax, [rsi+4A0h]
0x1400ca0f8  mov     dword ptr [rsi+4F4h], 1
0x1400ca102  mov     byte ptr [rax+6], 2
0x1400ca106  mov     al, [rsi+480h]
0x1400ca10c  and     al, 0EFh
0x1400ca10e  shl     r14b, 4
0x1400ca112  or      al, r14b
0x1400ca115  shl     dil, 3
0x1400ca119  and     al, 0F7h
0x1400ca11b  mov     r14b, 20h ; ' '
0x1400ca11e  or      al, dil
0x1400ca121  mov     [rsi+480h], al
0x1400ca127  cmp     [rsp+98h+arg_40], r13
0x1400ca12f  jz      loc_1400CA1B5
0x1400ca135  mov     rcx, [rsi+200h]
0x1400ca13c  add     rcx, 8
0x1400ca140  mov     rax, [rcx]
0x1400ca143  mov     rax, [rax+8]
0x1400ca147  call    _guard_dispatch_icall
0x1400ca14c  mov     rdx, [rsp+98h+arg_40]; struct _WFD_OTA_CHANNEL *
0x1400ca154  lea     r9, [rsi+4E8h]; unsigned int *
0x1400ca15b  mov     rcx, rax; this
0x1400ca15e  lea     r8, [rsi+4A8h]; enum _WDI_BAND_ID *
0x1400ca165  call    ?ConvertP2PChannelToBandChannel@@YAHPEAVCAdapterPropertyCache@@PEAU_WFD_OTA_CHANNEL@@PEAW4_WDI_BAND_ID@@PEAI@Z; ConvertP2PChannelToBandChannel(CAdapterPropertyCache *,_WFD_OTA_CHANNEL *,_WDI_BAND_ID *,uint *)
0x1400ca16a  test    eax, eax
0x1400ca16c  jnz     short loc_1400CA1B5
0x1400ca16e  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ca175  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ca17c  lea     rbx, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400ca183  jz      short loc_1400CA1AC
0x1400ca185  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca18c  lea     r9d, [rax+5Bh]
0x1400ca190  mov     eax, [rsi+10h]
0x1400ca193  mov     dl, 4
0x1400ca195  mov     [rsp+98h+var_68], eax
0x1400ca199  mov     qword ptr [rsp+98h+var_70], rsi
0x1400ca19e  mov     rcx, [rcx+40h]
0x1400ca1a2  mov     qword ptr [rsp+98h+var_78], rbx
0x1400ca1a7  call    WPP_RECORDER_SF_qD
0x1400ca1ac  or      [rsi+480h], r14b
0x1400ca1b3  jmp     short loc_1400CA1C3
0x1400ca1b5  lea     rbx, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400ca1bc  lea     r15, WPP_RECORDER_INITIALIZED
0x1400ca1c3  test    [rsi+480h], r14b
0x1400ca1ca  jnz     short loc_1400CA23C
0x1400ca1cc  mov     rcx, [rsp+98h+arg_48]
0x1400ca1d4  test    rcx, rcx
0x1400ca1d7  jz      short loc_1400CA23C
0x1400ca1d9  cmp     [rcx+270h], r13b
0x1400ca1e0  jz      short loc_1400CA1FA
0x1400ca1e2  mov     eax, [rcx+26Ch]
0x1400ca1e8  mov     [rsi+4A8h], eax
0x1400ca1ee  mov     eax, [rcx+268h]
0x1400ca1f4  mov     [rsi+4E8h], eax
0x1400ca1fa  cmp     byte ptr [rcx+270h], 1
0x1400ca201  jnz     short loc_1400CA23C
0x1400ca203  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400ca20a  jz      short loc_1400CA235
0x1400ca20c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca213  mov     r9d, 5Ch ; '\'
0x1400ca219  mov     eax, [rsi+10h]
0x1400ca21c  mov     dl, 4
0x1400ca21e  mov     [rsp+98h+var_68], eax
0x1400ca222  mov     qword ptr [rsp+98h+var_70], rsi
0x1400ca227  mov     rcx, [rcx+40h]
0x1400ca22b  mov     qword ptr [rsp+98h+var_78], rbx
0x1400ca230  call    WPP_RECORDER_SF_qD
0x1400ca235  or      [rsi+480h], r14b
0x1400ca23c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400ca243  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400ca24a  movzx   ebx, [rsp+98h+arg_30]
0x1400ca252  jz      short loc_1400CA281
0x1400ca254  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca25b  mov     r9d, 5Dh ; ']'
0x1400ca261  mov     eax, [rsi+10h]
0x1400ca264  mov     dl, 4
0x1400ca266  mov     [rsp+98h+var_60], ebx
0x1400ca26a  mov     [rsp+98h+var_68], eax
0x1400ca26e  mov     rcx, [rcx+40h]
0x1400ca272  mov     qword ptr [rsp+98h+var_70], rsi
0x1400ca277  mov     qword ptr [rsp+98h+var_78], r14
0x1400ca27c  call    WPP_RECORDER_SF_qDD
0x1400ca281  mov     al, [rsi+481h]
0x1400ca287  and     al, 0FBh
0x1400ca289  shl     bl, 2
0x1400ca28c  or      al, bl
0x1400ca28e  mov     [rsi+481h], al
0x1400ca294  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400ca29b  jz      short loc_1400CA2D7
0x1400ca29d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca2a4  cmp     byte ptr [rcx+29h], 5
0x1400ca2a8  jnb     short loc_1400CA2B1
0x1400ca2aa  cmp     [rcx+48h], r13w
0x1400ca2af  jz      short loc_1400CA2D7
0x1400ca2b1  mov     eax, [rsi+10h]
0x1400ca2b4  mov     r9d, 5Eh ; '^'
0x1400ca2ba  mov     rcx, [rcx+40h]
0x1400ca2be  mov     dl, 5
0x1400ca2c0  mov     [rsp+98h+var_60], ebp
0x1400ca2c4  mov     [rsp+98h+var_68], eax
0x1400ca2c8  mov     qword ptr [rsp+98h+var_70], rsi
0x1400ca2cd  mov     qword ptr [rsp+98h+var_78], r14
0x1400ca2d2  call    WPP_RECORDER_SF_qDD
0x1400ca2d7  mov     eax, ebp
0x1400ca2d9  add     rsp, 60h
0x1400ca2dd  pop     r15
0x1400ca2df  pop     r14
0x1400ca2e1  pop     r13
0x1400ca2e3  pop     rdi
0x1400ca2e4  pop     rsi
0x1400ca2e5  pop     rbp
0x1400ca2e6  pop     rbx
0x1400ca2e7  retn
```
