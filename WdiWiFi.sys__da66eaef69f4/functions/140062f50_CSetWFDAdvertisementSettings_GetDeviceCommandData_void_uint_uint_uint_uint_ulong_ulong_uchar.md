# CSetWFDAdvertisementSettings::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140062f50`
- end: `0x1400637aa`
- name: `?GetDeviceCommandData@CSetWFDAdvertisementSettings@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `2138`
- prototype: `__int64 __usercall@<rax>(CSetWFDAdvertisementSettings *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400122e0`
- `0x1400147e8`
- `0x1400176b0`
- `0x1400297a0`
- `0x14002aa28`
- `0x14002ed64`
- `0x14004ff88`
- `0x140061328`
- `0x140062f50`
- `0x1400861f8`
- `0x14008caa0`
- `0x1400ac754`
- `0x1400adbac`
- `0x1400c7568`

## pseudocode

```c
__int64 __fastcall CSetWFDAdvertisementSettings::GetDeviceCommandData(
        CSetWFDAdvertisementSettings *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST *v11; // rdi
  unsigned int WdiSetAdvertisementInformationToIhv; // r14d
  int v14; // ebp
  unsigned int *v15; // rax
  unsigned int *v16; // r9
  unsigned int v17; // edx
  unsigned __int8 **v18; // rax
  unsigned int *p_m_InformationBufferLength; // r15
  struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST *v20; // rsi
  __int64 v22; // rdx
  int v23; // edx
  int v24; // r8d
  unsigned int v25; // r10d
  char *v26; // rdx
  unsigned int v27; // r8d
  int v28; // r9d
  unsigned int v29; // eax
  _WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER *pElements; // r9
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned __int8 *v33; // rax
  unsigned __int8 v34; // si
  struct CPortPropertyCache *PortPropertyCache; // rax
  int v36; // r8d
  int v37; // edx
  int v38; // edx
  int v39; // r8d
  unsigned __int8 v40; // r9
  char v41; // al
  _WDI_ADDITIONAL_IES_CONTAINER *p_AdditionalIEs; // rdx
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // r8
  unsigned __int8 v45; // cl
  unsigned __int8 v46; // r8
  unsigned __int8 v47; // cl
  unsigned __int8 v48; // r8
  unsigned __int8 v49; // cl
  int v50; // edx
  int v51; // r8d
  unsigned int v52; // ecx
  __int64 v53; // [rsp+38h] [rbp-80h]
  struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST *v54; // [rsp+C0h] [rbp+8h] BYREF

  v11 = (struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST *)a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        13,
        (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        14,
        (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
        (char)this,
        this->m_ActivityId,
        this->m_JobType);
    }
  }
  switch ( this->m_JobType )
  {
    case WiFiJobP2PSetDeviceCapability:
      v14 = (_DWORD)this + 1088;
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 4u;
      v43 = (*((_BYTE *)v11 + 4) != 0) | 2;
      if ( !*((_BYTE *)v11 + 5) )
        v43 = *((_BYTE *)v11 + 4) != 0;
      v44 = v43;
      v45 = v43 | 4;
      if ( !*((_BYTE *)v11 + 6) )
        v45 = v44;
      v46 = v45;
      v47 = v45 | 8;
      if ( !*((_BYTE *)v11 + 7) )
        v47 = v46;
      v48 = v47;
      v49 = v47 | 0x10;
      if ( !*((_BYTE *)v11 + 8) )
        v49 = v48;
      v50 = v49;
      v51 = v49 | 0x20;
      if ( !*((_BYTE *)v11 + 9) )
        v51 = v49;
      this->m_AdvertisementParameters.DeviceCapability.OSSetDeviceCapabilities = 63;
      this->m_AdvertisementParameters.DeviceCapability.DeviceCapabilityBitmap = v51;
      v52 = *((_DWORD *)v11 + 3);
      this->m_AdvertisementParameters.DeviceCapability.WPSVersionsEnabled = v52;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v50) = 4;
        WPP_RECORDER_SF_qDDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v50,
          v51,
          15,
          (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51,
          63,
          v52);
      }
      goto LABEL_17;
    case WiFiJobP2PSetAdditionalIE:
      v14 = (_DWORD)this + 1088;
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 1u;
      p_AdditionalIEs = &this->m_AdvertisementParameters.AdditionalIEs;
      if ( *((_DWORD *)v11 + 2) )
      {
        *(_DWORD *)&p_AdditionalIEs->Optional |= 1u;
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalBeaconIEs.pElements = (unsigned __int8 *)v11
                                                                                    + *((unsigned int *)v11 + 1);
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalBeaconIEs.ElementCount = *((_DWORD *)v11 + 2);
      }
      if ( *((_DWORD *)v11 + 4) )
      {
        *(_DWORD *)&p_AdditionalIEs->Optional |= 2u;
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalProbeResponseIEs.pElements = (unsigned __int8 *)v11
                                                                                           + *((unsigned int *)v11 + 3);
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalProbeResponseIEs.ElementCount = *((_DWORD *)v11 + 4);
      }
      if ( *((_DWORD *)v11 + 6) )
      {
        *(_DWORD *)&p_AdditionalIEs->Optional |= 4u;
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalProbeRequestDefaultIEs.pElements = (unsigned __int8 *)v11
                                                                                                 + *((unsigned int *)v11 + 5);
        this->m_AdvertisementParameters.AdditionalIEs.AdditionalProbeRequestDefaultIEs.ElementCount = *((_DWORD *)v11 + 6);
      }
      goto LABEL_17;
    case WiFiJobP2PSetDeviceInfo:
      v14 = (_DWORD)this + 1088;
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 2u;
      *(_DWORD *)this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.DeviceAddress = *((_DWORD *)v11 + 1);
      *(_WORD *)&this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.DeviceAddress[4] = *((_WORD *)v11 + 4);
      this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.ConfigurationMethods = *((_WORD *)v11 + 5);
      this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.DeviceType.CategoryID = *((_WORD *)v11 + 6);
      this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.DeviceType.SubcategoryID = *((_WORD *)v11 + 7);
      *(_DWORD *)this->m_AdvertisementParameters.DeviceInformation.DeviceInfoParameters.DeviceType.OUI = *((_DWORD *)v11 + 4);
      this->m_AdvertisementParameters.DeviceInformation.DeviceName.pElements = (unsigned __int8 *)v11 + 24;
      this->m_AdvertisementParameters.DeviceInformation.DeviceName.ElementCount = *((_DWORD *)v11 + 5);
      goto LABEL_17;
    case WiFiJobP2PSetGroupOwnerCapability:
      v34 = 0;
      LODWORD(v54) = 0;
      PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
      if ( !(unsigned int)CPropertyCache::GetPropertyULong(PortPropertyCache, 0x18u, (unsigned int *)&v54) )
        v34 = ((unsigned __int8)v54 & 0x20) != 0;
      this->m_AdvertisementParameters.GroupOwnerCapability.OSSetGroupCapabilities = 0;
      v37 = *((unsigned __int8 *)v11 + 1);
      if ( v37 == 1 )
      {
        v40 = CDot11ToWabiConverter::MapWFDGroupCapabilities(
                v34,
                *((_BYTE *)v11 + 4),
                v36,
                *((_BYTE *)v11 + 5),
                *((_BYTE *)v11 + 6),
                *((_BYTE *)v11 + 7),
                *((_BYTE *)v11 + 8),
                0);
        v41 = 123;
      }
      else
      {
        if ( *((_BYTE *)v11 + 1) != 2 )
        {
          WdiSetAdvertisementInformationToIhv = -1073676267;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return WdiSetAdvertisementInformationToIhv;
          LOBYTE(v37) = 2;
          WPP_RECORDER_SF_qDDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v37,
            v36,
            16,
            (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
            (char)this,
            this->m_ActivityId,
            21,
            *((_BYTE *)v11 + 1));
          goto LABEL_33;
        }
        v40 = CDot11ToWabiConverter::MapWFDGroupCapabilities(
                v34,
                *((_BYTE *)v11 + 4),
                v36,
                *((_BYTE *)v11 + 5),
                *((_BYTE *)v11 + 6),
                *((_BYTE *)v11 + 7),
                *((_BYTE *)v11 + 8),
                *((_BYTE *)v11 + 16));
        this->m_AdvertisementParameters.GroupOwnerCapability.OSSetGroupCapabilities = 0x80;
        v41 = -5;
      }
      this->m_AdvertisementParameters.GroupOwnerCapability.GroupCapabilityBitmap = v40;
      v14 = (_DWORD)this + 1088;
      this->m_AdvertisementParameters.GroupOwnerCapability.MaximumGroupLimit = *((_DWORD *)v11 + 3);
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 8u;
      this->m_AdvertisementParameters.GroupOwnerCapability.OSSetGroupCapabilities = v41;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v38) = 4;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v38,
          v39,
          17,
          (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
          (char)this,
          this->m_ActivityId,
          v40,
          v41);
      }
      goto LABEL_17;
  }
  if ( this->m_JobType != WiFiJobP2PSetAdvertisementList )
  {
    if ( this->m_JobType == WiFiJobP2PSetSecondaryDeviceTypeList )
    {
      v14 = (_DWORD)this + 1088;
      this->m_AdvertisementParameters.SecondaryDeviceTypeList.pElements = (_WDI_P2P_DEVICE_TYPE *)((char *)v11 + 12);
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 0x10u;
      this->m_AdvertisementParameters.SecondaryDeviceTypeList.ElementCount = *((_DWORD *)v11 + 1);
    }
    else
    {
      if ( this->m_JobType != WiFiJobP2PSetCurrentASP2SessionID )
      {
        WdiSetAdvertisementInformationToIhv = -1073741823;
        goto LABEL_33;
      }
      v14 = (_DWORD)this + 1088;
    }
LABEL_17:
    v15 = a7;
    v16 = a8;
    v17 = a6;
    *a4 = a3;
    *v15 = 89;
    v18 = a9;
    *v16 = 0;
    WdiSetAdvertisementInformationToIhv = GenerateWdiSetAdvertisementInformationToIhv(
                                            v14,
                                            v17,
                                            (unsigned int)this->m_pAdapter + 16376,
                                            (_DWORD)v16,
                                            (__int64)v18);
    goto LABEL_33;
  }
  p_m_InformationBufferLength = &this->m_InformationBufferLength;
  v54 = v11;
  WdiSetAdvertisementInformationToIhv = CheckAdvListForOldVersion(
                                          this->m_InformationBufferLength,
                                          v11,
                                          &this->m_InformationBufferLength,
                                          &v54);
  if ( WdiSetAdvertisementInformationToIhv )
    goto LABEL_33;
  v20 = v54;
  if ( v11 != v54 )
    this->m_pInformationBuffer = v54;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      18,
      (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
      (char)this,
      this->m_ActivityId,
      *((_DWORD *)v20 + 2),
      *((_DWORD *)v20 + 5),
      *((_DWORD *)v20 + 9));
  }
  if ( (!*((_DWORD *)v20 + 2) || *((_DWORD *)v20 + 3) >= 0x28u)
    && (!*((_DWORD *)v20 + 5) || *((_DWORD *)v20 + 6) >= 0x28u) )
  {
    a2 = *((unsigned int *)v20 + 9);
    if ( (!(_DWORD)a2 || (unsigned int)a2 >= 0x28 && *((_DWORD *)v20 + 8) >= 0x28u)
      && a2 + 40 + *((unsigned int *)v20 + 4) + (unsigned __int64)*((unsigned int *)v20 + 7) <= this->m_InformationBufferLength )
    {
      v14 = (_DWORD)this + 1088;
      *(_DWORD *)&this->m_AdvertisementParameters.Optional |= 0x20u;
      this->m_AdvertisementParameters.AdvertisedServices.ServiceUpdateIndicator = *((_WORD *)v20 + 2);
      v22 = *((unsigned int *)v20 + 2);
      if ( (_DWORD)v22 )
      {
        WdiSetAdvertisementInformationToIhv = ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(
                                                &this->m_AdvertisementParameters.AdvertisedServices.ServiceEntry,
                                                v22,
                                                0);
        if ( WdiSetAdvertisementInformationToIhv )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return WdiSetAdvertisementInformationToIhv;
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_qDDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            v24,
            20,
            (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
            (char)this,
            this->m_ActivityId,
            WdiSetAdvertisementInformationToIhv,
            *((_DWORD *)v20 + 2));
          goto LABEL_33;
        }
        v25 = 0;
        *(_DWORD *)&this->m_AdvertisementParameters.AdvertisedServices.Optional |= 1u;
        v26 = (char *)v20 + *((unsigned int *)v20 + 3);
        while ( v25 < *((_DWORD *)v20 + 2) )
        {
          v27 = *((_DWORD *)v26 + 42);
          if ( v27 < 0x28
            || v27 + (unsigned __int8)v26[164] > *p_m_InformationBufferLength
            || (v28 = *((_DWORD *)v26 + 43)) != 0
            && ((v29 = *((_DWORD *)v26 + 44), v29 < 0x28) || v28 + v29 > *p_m_InformationBufferLength) )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              return WdiSetAdvertisementInformationToIhv;
            WPP_RECORDER_SF_qDDddddd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v26,
              v27,
              21,
              (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
              (char)this,
              this->m_ActivityId,
              0,
              v27,
              v26[164],
              *((_DWORD *)v26 + 44),
              *((_DWORD *)v26 + 43),
              this->m_InformationBufferLength);
            goto LABEL_33;
          }
          pElements = this->m_AdvertisementParameters.AdvertisedServices.ServiceEntry.pElements;
          v31 = v25;
          pElements[v31].ServiceStatus = v26[16];
          pElements[v31].AdvertisementID = *(_DWORD *)v26;
          pElements[v31].ConfigurationMethods = *((_WORD *)v26 + 6);
          pElements[v31].ServiceName.ElementCount = (unsigned __int8)v26[164];
          pElements[v31].ServiceName.pElements = (unsigned __int8 *)v20 + *((unsigned int *)v26 + 42);
          *(_DWORD *)pElements[v31].ServiceNameHash.Hash = *((_DWORD *)v26 + 1);
          *(_WORD *)&pElements[v31].ServiceNameHash.Hash[4] = *((_WORD *)v26 + 4);
          v32 = *((_DWORD *)v26 + 43);
          if ( v32 )
          {
            pElements[v31].ServiceInformation.ElementCount = v32;
            v33 = (unsigned __int8 *)v20 + *((unsigned int *)v26 + 44);
            *(_DWORD *)&pElements[v31].Optional |= 1u;
            pElements[v31].ServiceInformation.pElements = v33;
          }
          v26 += 180;
          ++v25;
        }
      }
      goto LABEL_17;
    }
  }
  WdiSetAdvertisementInformationToIhv = -1073676267;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return WdiSetAdvertisementInformationToIhv;
  WPP_RECORDER_SF_qDDddddd(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    (unsigned int)&WPP_RECORDER_INITIALIZED,
    19,
    (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
    (char)this,
    this->m_ActivityId,
    21,
    this->m_InformationBufferLength,
    40,
    *((_DWORD *)v20 + 4),
    *((_DWORD *)v20 + 7),
    *((_DWORD *)v20 + 9));
LABEL_33:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v53) = WdiSetAdvertisementInformationToIhv;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      24,
      (__int64)WPP_76884600380d36675c953a8b9856749c_Traceguids,
      (char)this,
      this->m_ActivityId,
      v53);
  }
  return WdiSetAdvertisementInformationToIhv;
}

```

## disassembly

```asm
0x140062f50  push    rbx
0x140062f52  push    rbp
0x140062f53  push    rsi
0x140062f54  push    rdi
0x140062f55  push    r12
0x140062f57  push    r13
0x140062f59  push    r14
0x140062f5b  push    r15
0x140062f5d  sub     rsp, 78h
0x140062f61  mov     r12, r9
0x140062f64  mov     r13d, r8d
0x140062f67  mov     rdi, rdx
0x140062f6a  mov     rbx, rcx
0x140062f6d  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140062f74  xor     r14d, r14d
0x140062f77  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062f7e  lea     rbp, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x140062f85  jz      short loc_140062FF6
0x140062f87  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f8e  cmp     byte ptr [rcx+29h], 5
0x140062f92  jnb     short loc_140062F9B
0x140062f94  cmp     [rcx+48h], r14w
0x140062f99  jz      short loc_140062FBD
0x140062f9b  mov     eax, [rbx+10h]
0x140062f9e  mov     r9d, 0Dh
0x140062fa4  mov     rcx, [rcx+40h]
0x140062fa8  mov     dl, 5
0x140062faa  mov     dword ptr [rsp+0B8h+var_88], eax
0x140062fae  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140062fb3  mov     qword ptr [rsp+0B8h+var_98], rbp
0x140062fb8  call    WPP_RECORDER_SF_qD
0x140062fbd  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140062fc4  jz      short loc_140062FF6
0x140062fc6  mov     eax, [rbx+3Ch]
0x140062fc9  mov     r9d, 0Eh
0x140062fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140062fd6  mov     dl, 4
0x140062fd8  mov     dword ptr [rsp+0B8h+var_80], eax
0x140062fdc  mov     eax, [rbx+10h]
0x140062fdf  mov     dword ptr [rsp+0B8h+var_88], eax
0x140062fe3  mov     rcx, [rcx+40h]
0x140062fe7  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140062fec  mov     qword ptr [rsp+0B8h+var_98], rbp
0x140062ff1  call    WPP_RECORDER_SF_qDD
0x140062ff6  mov     ecx, [rbx+3Ch]
0x140062ff9  sub     ecx, 7Ch ; '|'
0x140062ffc  jz      loc_1400636CB
0x140063002  sub     ecx, 1
0x140063005  jz      loc_140063650
0x14006300b  sub     ecx, 3
0x14006300e  jz      loc_1400635EE
0x140063014  sub     ecx, 4
0x140063017  jz      loc_140063472
0x14006301d  sub     ecx, 4
0x140063020  jz      loc_1400630C0
0x140063026  sub     ecx, 3
0x140063029  jz      short loc_14006304B
0x14006302b  lea     rsi, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x140063032  cmp     ecx, 2Eh ; '.'
0x140063035  jz      short loc_140063042
0x140063037  mov     r14d, 0C0000001h
0x14006303d  jmp     loc_140063215
0x140063042  lea     rbp, [rbx+440h]
0x140063049  jmp     short loc_140063071
0x14006304b  lea     rax, [rdi+0Ch]
0x14006304f  lea     rbp, [rbx+440h]
0x140063056  mov     [rbx+4D8h], rax
0x14006305d  or      dword ptr [rbp+0], 10h
0x140063061  mov     eax, [rdi+4]
0x140063064  mov     [rbx+4D0h], eax
0x14006306a  lea     rsi, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x140063071  mov     rax, [rsp+0B8h+arg_30]
0x140063079  mov     rcx, rbp
0x14006307c  mov     r9, [rsp+0B8h+arg_38]
0x140063084  mov     edx, [rsp+0B8h+arg_28]
0x14006308b  mov     [r12], r13d
0x14006308f  mov     dword ptr [rax], 59h ; 'Y'
0x140063095  mov     rax, [rsp+0B8h+arg_40]
0x14006309d  mov     [r9], r14d
0x1400630a0  mov     r8, [rbx+200h]
0x1400630a7  add     r8, 3FF8h
0x1400630ae  mov     qword ptr [rsp+0B8h+var_98], rax
0x1400630b3  call    GenerateWdiSetAdvertisementInformationToIhv
0x1400630b8  mov     r14d, eax
0x1400630bb  jmp     loc_140063215
0x1400630c0  lea     r15, [rbx+238h]
0x1400630c7  mov     [rsp+0B8h+arg_0], rdi
0x1400630cf  mov     ecx, [r15]; unsigned int
0x1400630d2  lea     r9, [rsp+0B8h+arg_0]; struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST **
0x1400630da  mov     r8, r15; unsigned int *
0x1400630dd  mov     rdx, rdi; void *
0x1400630e0  call    ?CheckAdvListForOldVersion@@YAHIPEAXPEAIPEAPEAU_DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST@@@Z; CheckAdvListForOldVersion(uint,void *,uint *,_DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST * *)
0x1400630e5  mov     r14d, eax
0x1400630e8  test    eax, eax
0x1400630ea  jnz     loc_14006320E
0x1400630f0  mov     rsi, [rsp+0B8h+arg_0]
0x1400630f8  cmp     rdi, rsi
0x1400630fb  jz      short loc_140063104
0x1400630fd  mov     [rbx+230h], rsi
0x140063104  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006310b  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140063112  jz      short loc_140063159
0x140063114  mov     eax, [rsi+24h]
0x140063117  mov     r9d, 12h
0x14006311d  mov     rcx, cs:WPP_GLOBAL_Control
0x140063124  mov     dl, 4
0x140063126  mov     [rsp+0B8h+var_70], eax
0x14006312a  mov     eax, [rsi+14h]
0x14006312d  mov     [rsp+0B8h+var_78], eax
0x140063131  mov     eax, [rsi+8]
0x140063134  mov     rcx, [rcx+40h]
0x140063138  mov     dword ptr [rsp+0B8h+var_80], eax
0x14006313c  mov     eax, [rbx+10h]
0x14006313f  mov     dword ptr [rsp+0B8h+var_88], eax
0x140063143  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140063148  mov     qword ptr [rsp+0B8h+var_98], rbp
0x14006314d  call    WPP_RECORDER_SF_qDddd
0x140063152  lea     r8, WPP_RECORDER_INITIALIZED
0x140063159  xor     r14d, r14d
0x14006315c  cmp     [rsi+8], r14d
0x140063160  jz      short loc_140063168
0x140063162  cmp     dword ptr [rsi+0Ch], 28h ; '('
0x140063166  jb      short loc_1400631A5
0x140063168  cmp     [rsi+14h], r14d
0x14006316c  jz      short loc_140063174
0x14006316e  cmp     dword ptr [rsi+18h], 28h ; '('
0x140063172  jb      short loc_1400631A5
0x140063174  mov     edx, [rsi+24h]
0x140063177  test    edx, edx
0x140063179  jz      short loc_140063186
0x14006317b  cmp     edx, 28h ; '('
0x14006317e  jb      short loc_1400631A5
0x140063180  cmp     dword ptr [rsi+20h], 28h ; '('
0x140063184  jb      short loc_1400631A5
0x140063186  mov     eax, [rsi+10h]
0x140063189  mov     ecx, [rsi+1Ch]
0x14006318c  add     rcx, rax
0x14006318f  lea     rax, [rdx+28h]
0x140063193  add     rcx, rax
0x140063196  mov     eax, [rbx+238h]
0x14006319c  cmp     rcx, rax
0x14006319f  jbe     loc_140063276
0x1400631a5  mov     r14d, 0C0010015h
0x1400631ab  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x1400631b2  jz      loc_140063261
0x1400631b8  mov     eax, [rsi+24h]
0x1400631bb  mov     r9d, 13h
0x1400631c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631c8  mov     [rsp+0B8h+var_58], eax
0x1400631cc  mov     eax, [rsi+1Ch]
0x1400631cf  mov     [rsp+0B8h+var_60], eax
0x1400631d3  mov     eax, [rsi+10h]
0x1400631d6  mov     rcx, [rcx+40h]
0x1400631da  mov     [rsp+0B8h+var_68], eax
0x1400631de  mov     eax, [rbx+238h]
0x1400631e4  mov     [rsp+0B8h+var_70], 28h ; '('
0x1400631ec  mov     [rsp+0B8h+var_78], eax
0x1400631f0  mov     eax, [rbx+10h]
0x1400631f3  mov     dword ptr [rsp+0B8h+var_80], 0C0010015h
0x1400631fb  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400631ff  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140063204  mov     qword ptr [rsp+0B8h+var_98], rbp
0x140063209  call    WPP_RECORDER_SF_qDDddddd
0x14006320e  lea     rsi, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x140063215  xor     edi, edi
0x140063217  lea     rbp, WPP_RECORDER_INITIALIZED
0x14006321e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140063225  jz      short loc_140063261
0x140063227  mov     rcx, cs:WPP_GLOBAL_Control
0x14006322e  cmp     byte ptr [rcx+29h], 5
0x140063232  jnb     short loc_14006323A
0x140063234  cmp     [rcx+48h], di
0x140063238  jz      short loc_140063261
0x14006323a  mov     eax, [rbx+10h]
0x14006323d  mov     r9d, 18h
0x140063243  mov     rcx, [rcx+40h]
0x140063247  mov     dl, 5
0x140063249  mov     dword ptr [rsp+0B8h+var_80], r14d
0x14006324e  mov     dword ptr [rsp+0B8h+var_88], eax
0x140063252  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140063257  mov     qword ptr [rsp+0B8h+var_98], rsi
0x14006325c  call    WPP_RECORDER_SF_qDD
0x140063261  mov     eax, r14d
0x140063264  add     rsp, 78h
0x140063268  pop     r15
0x14006326a  pop     r14
0x14006326c  pop     r13
0x14006326e  pop     r12
0x140063270  pop     rdi
0x140063271  pop     rsi
0x140063272  pop     rbp
0x140063273  pop     rbx
0x140063274  retn
0x140063276  lea     rbp, [rbx+440h]
0x14006327d  or      dword ptr [rbp+0], 20h
0x140063281  movzx   eax, word ptr [rsi+4]
0x140063285  mov     [rbx+508h], ax
0x14006328c  mov     edx, [rsi+8]
0x14006328f  test    edx, edx
0x140063291  jz      loc_14006306A
0x140063297  lea     rcx, [rbx+4F0h]
0x14006329e  xor     r8d, r8d
0x1400632a1  call    ?AllocateElements@?$ArrayOfElements@U_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(uint,unsigned __int64)
0x1400632a6  xor     edi, edi
0x1400632a8  mov     r14d, eax
0x1400632ab  test    eax, eax
0x1400632ad  jz      short loc_1400632FE
0x1400632af  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400632b6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400632bd  jz      short loc_140063261
0x1400632bf  mov     eax, [rsi+8]
0x1400632c2  lea     r9d, [rdi+14h]
0x1400632c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632cd  lea     rsi, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x1400632d4  mov     [rsp+0B8h+var_78], eax
0x1400632d8  mov     dl, 2
0x1400632da  mov     eax, [rbx+10h]
0x1400632dd  mov     dword ptr [rsp+0B8h+var_80], r14d
0x1400632e2  mov     rcx, [rcx+40h]
0x1400632e6  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400632ea  mov     qword ptr [rsp+0B8h+var_90], rbx
0x1400632ef  mov     qword ptr [rsp+0B8h+var_98], rsi
0x1400632f4  call    WPP_RECORDER_SF_qDDd
0x1400632f9  jmp     loc_14006321E
0x1400632fe  mov     ecx, 1
0x140063303  mov     r10d, edi
0x140063306  or      [rbx+4E8h], ecx
0x14006330c  mov     edx, [rsi+0Ch]
0x14006330f  add     rdx, rsi
0x140063312  cmp     r10d, [rsi+8]
0x140063316  jnb     loc_14006346A
0x14006331c  mov     r8d, [rdx+0A8h]
0x140063323  cmp     r8d, 28h ; '('
0x140063327  jb      loc_1400633F1
0x14006332d  movzx   eax, byte ptr [rdx+0A4h]
0x140063334  mov     r11d, [r15]
0x140063337  add     eax, r8d
0x14006333a  cmp     eax, r11d
0x14006333d  ja      loc_1400633F1
0x140063343  mov     r9d, [rdx+0ACh]
0x14006334a  test    r9d, r9d
0x14006334d  jz      short loc_14006336A
0x14006334f  mov     eax, [rdx+0B0h]
0x140063355  cmp     eax, 28h ; '('
0x140063358  jb      loc_1400633F1
0x14006335e  add     eax, r9d
0x140063361  cmp     eax, r11d
0x140063364  ja      loc_1400633F1
0x14006336a  mov     r9, [rbx+4F8h]
0x140063371  mov     eax, r10d
0x140063374  lea     r8, [rax+rax*4]
0x140063378  mov     al, [rdx+10h]
0x14006337b  shl     r8, 4
0x14006337f  mov     [r8+r9+40h], al
0x140063384  mov     eax, [rdx]
0x140063386  mov     [r8+r9+44h], eax
0x14006338b  movzx   eax, word ptr [rdx+0Ch]
0x14006338f  mov     [r8+r9+48h], ax
0x140063395  movzx   eax, byte ptr [rdx+0A4h]
0x14006339c  mov     [r8+r9+8], eax
0x1400633a1  mov     eax, [rdx+0A8h]
0x1400633a7  add     rax, rsi
0x1400633aa  mov     [r8+r9+10h], rax
0x1400633af  mov     eax, [rdx+4]
0x1400633b2  mov     [r8+r9+20h], eax
0x1400633b7  movzx   eax, word ptr [rdx+8]
0x1400633bb  mov     [r8+r9+24h], ax
0x1400633c1  mov     eax, [rdx+0ACh]
0x1400633c7  test    eax, eax
0x1400633c9  jz      short loc_1400633E2
0x1400633cb  mov     [r8+r9+28h], eax
0x1400633d0  mov     eax, [rdx+0B0h]
0x1400633d6  add     rax, rsi
0x1400633d9  or      [r8+r9], ecx
0x1400633dd  mov     [r8+r9+30h], rax
0x1400633e2  add     rdx, 0B4h
0x1400633e9  add     r10d, ecx
0x1400633ec  jmp     loc_140063312
0x1400633f1  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400633f8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400633ff  jz      loc_140063261
0x140063405  mov     eax, [rbx+238h]
0x14006340b  lea     rsi, WPP_76884600380d36675c953a8b9856749c_Traceguids
0x140063412  movzx   ecx, byte ptr [rdx+0A4h]
0x140063419  mov     r9d, 15h
0x14006341f  mov     [rsp+0B8h+var_58], eax
0x140063423  mov     eax, [rdx+0ACh]
0x140063429  mov     [rsp+0B8h+var_60], eax
0x14006342d  mov     eax, [rdx+0B0h]
0x140063433  mov     [rsp+0B8h+var_68], eax
0x140063437  mov     eax, [rbx+10h]
0x14006343a  mov     [rsp+0B8h+var_70], ecx
0x14006343e  mov     rcx, cs:WPP_GLOBAL_Control
0x140063445  mov     [rsp+0B8h+var_78], r8d
0x14006344a  mov     dword ptr [rsp+0B8h+var_80], edi
0x14006344e  mov     dword ptr [rsp+0B8h+var_88], eax
0x140063452  mov     rcx, [rcx+40h]
0x140063456  mov     qword ptr [rsp+0B8h+var_90], rbx
0x14006345b  mov     qword ptr [rsp+0B8h+var_98], rsi
0x140063460  call    WPP_RECORDER_SF_qDDddddd
  ... truncated ...
```
