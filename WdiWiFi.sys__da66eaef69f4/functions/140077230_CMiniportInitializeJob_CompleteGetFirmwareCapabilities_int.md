# CMiniportInitializeJob::CompleteGetFirmwareCapabilities(int)

- ea: `0x140077230`
- end: `0x14007795c`
- name: `?CompleteGetFirmwareCapabilities@CMiniportInitializeJob@@AEAAHH@Z`
- size: `1836`
- prototype: `__int64 __fastcall(CMiniportInitializeJob *__hidden this, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140076da0`

## callees

- `0x1400100f8`
- `0x1400101c8`
- `0x140011ad4`
- `0x140011c5c`
- `0x1400122e0`
- `0x140013000`
- `0x140017388`
- `0x1400176b0`
- `0x14002aa28`
- `0x140034e04`
- `0x140042ad0`
- `0x140060af4`
- `0x140061328`
- `0x140077230`
- `0x1400874ec`
- `0x14008d680`
- `0x1400a3478`
- `0x1400a8268`
- `0x1400a86b8`
- `0x1400a915c`
- `0x1400a965c`
- `0x1400aa770`
- `0x1400aab64`
- `0x1400da680`

## pseudocode

```c
__int64 __fastcall CMiniportInitializeJob::CompleteGetFirmwareCapabilities(
        CMiniportInitializeJob *this,
        unsigned int a2,
        int a3)
{
  unsigned int StatusFromCommandResult; // edi
  int v5; // edx
  int v6; // r8d
  int CommandResult; // eax
  int v8; // r9d
  _WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *p_m_AdapterCapabilities; // r14
  CMiniportInitializeJob *v10; // rcx
  int v11; // edx
  int v12; // r8d
  char v13; // si
  struct CAdapterPropertyCache *AdapterPropertyCache; // rax
  unsigned __int8 PropertyBooleanOrDefault; // al
  unsigned int SupportedWakeUpEvents; // r9d
  unsigned int *p_MediaSpecificWakeUpEvents; // rdx
  unsigned int *p_SupportedWoLPacketPatterns; // rcx
  _WDI_OS_POWER_MANAGEMENT_FLAGS EnableFlags; // eax
  unsigned int v20; // ecx
  int v21; // r8d
  unsigned __int8 v22; // r13
  IPropertyCacheDirectory *v23; // rcx
  CPropertyCache *v24; // rax
  CAdapterPropertyCache *v25; // rax
  CAdapterPropertyCache *v26; // rax
  CAdapterPropertyCache *v27; // rax
  CAdapterPropertyCache *v28; // rax
  struct CAdapterPropertyCache *v29; // rax
  char v30; // al
  int v31; // edx
  int v32; // r8d
  int v33; // r9d
  unsigned int v34; // r12d
  unsigned int v35; // r15d
  CAdapterPropertyCache *v36; // rax
  __int64 v37; // r8
  struct _WFC_REG_ENTRY *v38; // r9
  CAdapterPropertyCache *v39; // rax
  __int64 v40; // r8
  struct _WFC_REG_ENTRY *v41; // r9
  CAdapter *m_pAdapter; // rcx
  CPropertyCache *v43; // rax
  CAdapterPropertyCache *v44; // rax
  unsigned int PropertyULongOrDefault; // eax
  int v47; // [rsp+20h] [rbp-60h]
  __int64 v48; // [rsp+38h] [rbp-48h]
  unsigned int v49; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v50[3]; // [rsp+74h] [rbp-Ch] BYREF
  int v51; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int v52; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int8 *v53; // [rsp+D8h] [rbp+58h] BYREF

  StatusFromCommandResult = a2;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        59,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
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
        60,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
  }
  if ( StatusFromCommandResult )
    goto LABEL_71;
  StatusFromCommandResult = CMessageHelper::GetStatusFromCommandResult(&this->m_FirmwareCapabilitiesCommand, &v51);
  if ( !StatusFromCommandResult )
  {
    CommandResult = DeviceCommand::get_CommandResult(&this->m_FirmwareCapabilitiesCommand, &v52, &v53);
    if ( CommandResult )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromCommandResult;
      v8 = 62;
LABEL_69:
      LODWORD(v48) = CommandResult;
      goto LABEL_70;
    }
    p_m_AdapterCapabilities = &this->m_AdapterCapabilities;
    StatusFromCommandResult = ParseWdiGetAdapterCapabilitiesFromIhv(
                                v52 - 48,
                                v53 + 48,
                                &this->m_pAdapter->m_TlvContext,
                                &this->m_AdapterCapabilities);
    if ( StatusFromCommandResult )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromCommandResult;
      v8 = 63;
      goto LABEL_17;
    }
    StatusFromCommandResult = CMiniportInitializeJob::ApplyDriverCapabilities(this);
    if ( StatusFromCommandResult )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromCommandResult;
      v8 = 64;
LABEL_17:
      LODWORD(v48) = 0;
LABEL_70:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        v8,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v48);
      goto LABEL_71;
    }
    CMiniportInitializeJob::OverrideUnsupportedAuthCipherCombinations(v10, &this->m_AdapterCapabilities);
    StatusFromCommandResult = CMiniportInitializeJob::ApplyAdapterCapabilitiesOverride(this);
    if ( StatusFromCommandResult )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromCommandResult;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        65,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
      goto LABEL_71;
    }
    this->m_AdapterCapabilities.PmCapabilities.Flags &= 0xFFFFFFF3;
    v13 = 2;
    if ( this->m_pAdapter->m_MiniportDriver->m_bMiniportIsWhitelistedForNaps
      || (this->m_AdapterCapabilities.OsPowerMgmtFeatures.EnableFlags & 1) != 0 )
    {
      AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
      PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(AdapterPropertyCache, 0x7Du, 1u);
      SupportedWakeUpEvents = this->m_AdapterCapabilities.PmCapabilities.SupportedWakeUpEvents;
      p_MediaSpecificWakeUpEvents = &this->m_AdapterCapabilities.PmCapabilities.MediaSpecificWakeUpEvents;
      if ( ((SupportedWakeUpEvents & 2) != 0 || (*p_MediaSpecificWakeUpEvents & 2) != 0)
        && (p_SupportedWoLPacketPatterns = &this->m_AdapterCapabilities.PmCapabilities.SupportedWoLPacketPatterns,
            this->m_AdapterCapabilities.PmCapabilities.SupportedWoLPacketPatterns)
        && (unsigned int)(this->m_AdapterCapabilities.PmCapabilities.MinPatternWakeUp - 3) <= 1 )
      {
        if ( PropertyBooleanOrDefault )
        {
          EnableFlags = this->m_AdapterCapabilities.OsPowerMgmtFeatures.EnableFlags;
          v20 = this->m_AdapterCapabilities.PmCapabilities.Flags | 4;
          this->m_AdapterCapabilities.PmCapabilities.Flags = v20;
          if ( (EnableFlags & 2) != 0 )
            this->m_AdapterCapabilities.PmCapabilities.Flags = v20 | 8;
          goto LABEL_37;
        }
        v21 = 1;
      }
      else
      {
        p_SupportedWoLPacketPatterns = &this->m_AdapterCapabilities.PmCapabilities.SupportedWoLPacketPatterns;
        v21 = 0;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDdDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)p_MediaSpecificWakeUpEvents,
          v21,
          SupportedWakeUpEvents,
          v47,
          (char)this,
          this->m_ActivityId,
          v21,
          SupportedWakeUpEvents,
          *p_MediaSpecificWakeUpEvents,
          *p_SupportedWoLPacketPatterns);
    }
LABEL_37:
    v22 = CMiniportInitializeJob::Is11adBandPresent(this, &this->m_AdapterCapabilities);
    if ( v22 )
      this->m_pAdapter->m_ServicesManager.m_MaxResponseFragmentSize = 900;
    v23 = &this->m_pAdapter->IPropertyCacheDirectory;
    v52 = 0;
    LODWORD(v53) = 0;
    v49 = 0;
    v50[0] = 0;
    v24 = v23->GetAdapterPropertyCache(v23);
    CPropertyCache::SetPropertyBoolean(v24, 0x84u, 0);
    v25 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    CPropertyCache::GetPropertyULong(v25, 0x80u, &v52);
    v26 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    CPropertyCache::GetPropertyULong(v26, 0x81u, (unsigned int *)&v53);
    v27 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    CPropertyCache::GetPropertyULong(v27, 0x82u, &v49);
    v28 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    CPropertyCache::GetPropertyULong(v28, 0x83u, v50);
    v29 = CJobBase::get_AdapterPropertyCache(this);
    v30 = CPropertyCache::GetPropertyBooleanOrDefault(v29, 0x88u, 1u);
    LOBYTE(v51) = v30;
    v34 = v49;
    v35 = v50[0];
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_qDDDdddd(
        WPP_GLOBAL_Control->DeviceExtension,
        (*(_DWORD *)&p_m_AdapterCapabilities->Optional >> 10) & 1,
        v32,
        v33,
        v47,
        (char)this,
        this->m_ActivityId,
        (*(_DWORD *)&p_m_AdapterCapabilities->Optional & 0x400) != 0,
        v30,
        v52,
        (char)v53,
        v49,
        v50[0]);
      v30 = v51;
    }
    if ( v30
      && !v52
      && !(_DWORD)v53
      && ((*(_DWORD *)&p_m_AdapterCapabilities->Optional & 0x400) == 0
       || !this->m_AdapterCapabilities.TcpOffloadCapabilities.ReceiveOffloadCapabilities.Ipv4Enabled
       && !this->m_AdapterCapabilities.TcpOffloadCapabilities.ReceiveOffloadCapabilities.Ipv6Enabled) )
    {
      if ( v34 == 2 )
      {
        v34 = 1;
        v36 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
        CPropertyCache::SetPropertyULong(v36, 0x82u, 1u);
        CAdapter::PersistAdapterProperty(this->m_pAdapter, 0x82u, v37, v38);
      }
      if ( v35 == 2 )
      {
        v35 = 1;
        v39 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
        CPropertyCache::SetPropertyULong(v39, 0x83u, 1u);
        CAdapter::PersistAdapterProperty(this->m_pAdapter, 0x83u, v40, v41);
      }
      if ( v34 == 1 || v35 == 1 )
      {
        *(_DWORD *)&p_m_AdapterCapabilities->Optional |= 0x400u;
        m_pAdapter = this->m_pAdapter;
        this->m_AdapterCapabilities.TcpOffloadCapabilities.ReceiveOffloadCapabilities.Ipv4Enabled = v34 == 1;
        this->m_AdapterCapabilities.TcpOffloadCapabilities.ReceiveOffloadCapabilities.Ipv6Enabled = v35 == 1;
        v43 = m_pAdapter->GetAdapterPropertyCache(&m_pAdapter->IPropertyCacheDirectory);
        CPropertyCache::SetPropertyBoolean(v43, 0x84u, 1u);
      }
    }
    if ( (*(_DWORD *)&p_m_AdapterCapabilities->Optional & 0x400) == 0 )
      goto LABEL_64;
    v44 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(v44, 0x87u, 2u);
    v13 = PropertyULongOrDefault;
    if ( PropertyULongOrDefault == 2 )
    {
      if ( v22 )
      {
LABEL_64:
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qDDddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v31,
            v32,
            69,
            (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
            (char)this,
            this->m_ActivityId,
            (*(_DWORD *)&p_m_AdapterCapabilities->Optional & 0x400) != 0,
            v34,
            v35,
            v13);
        CommandResult = CAdapter::SetFirmwareCapabilitiesProperties(this->m_pAdapter, &this->m_AdapterCapabilities);
        if ( !CommandResult )
          goto LABEL_71;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return StatusFromCommandResult;
        v8 = 70;
        goto LABEL_69;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v31) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          PropertyULongOrDefault - 1,
          PropertyULongOrDefault + 66,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
      }
      v13 = 0;
    }
    else if ( PropertyULongOrDefault )
    {
      if ( PropertyULongOrDefault == 1 )
        this->m_AdapterCapabilities.TcpOffloadCapabilities.OffloadScope = (_WDI_OFFLOAD_SCOPE)16843009;
      goto LABEL_64;
    }
    this->m_AdapterCapabilities.TcpOffloadCapabilities.OffloadScope = 0;
    goto LABEL_64;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return StatusFromCommandResult;
  LOBYTE(v5) = 2;
  WPP_RECORDER_SF_qDDd(
    WPP_GLOBAL_Control->DeviceExtension,
    v5,
    v6,
    61,
    (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
    (char)this,
    this->m_ActivityId,
    StatusFromCommandResult,
    v51);
LABEL_71:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v48) = StatusFromCommandResult;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      71,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v48);
  }
  return StatusFromCommandResult;
}

```

## disassembly

```asm
0x140077230  mov     [rsp-38h+arg_0], rbx
0x140077235  push    rbp
0x140077236  push    rsi
0x140077237  push    rdi
0x140077238  push    r12
0x14007723a  push    r13
0x14007723c  push    r14
0x14007723e  push    r15
0x140077240  mov     rbp, rsp
0x140077243  sub     rsp, 80h
0x14007724a  xor     r15d, r15d
0x14007724d  mov     edi, edx
0x14007724f  mov     [rbp+arg_8], r15d
0x140077253  mov     rbx, rcx
0x140077256  mov     [rbp+arg_10], r15d
0x14007725a  mov     [rbp+arg_18], r15
0x14007725e  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077265  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007726c  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140077273  jz      short loc_1400772E1
0x140077275  mov     rcx, cs:WPP_GLOBAL_Control
0x14007727c  cmp     byte ptr [rcx+29h], 5
0x140077280  jnb     short loc_140077289
0x140077282  cmp     [rcx+48h], r15w
0x140077287  jz      short loc_1400772AB
0x140077289  mov     eax, [rbx+10h]
0x14007728c  mov     r9d, 3Bh ; ';'
0x140077292  mov     rcx, [rcx+40h]
0x140077296  mov     dl, 5
0x140077298  mov     [rsp+80h+var_50], eax
0x14007729c  mov     [rsp+80h+var_58], rbx
0x1400772a1  mov     [rsp+80h+var_60], r12
0x1400772a6  call    WPP_RECORDER_SF_qD
0x1400772ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400772b2  jz      short loc_1400772E1
0x1400772b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400772bb  mov     r9d, 3Ch ; '<'
0x1400772c1  mov     eax, [rbx+10h]
0x1400772c4  mov     dl, 4
0x1400772c6  mov     dword ptr [rsp+80h+var_48], edi
0x1400772ca  mov     [rsp+80h+var_50], eax
0x1400772ce  mov     rcx, [rcx+40h]
0x1400772d2  mov     [rsp+80h+var_58], rbx
0x1400772d7  mov     [rsp+80h+var_60], r12
0x1400772dc  call    WPP_RECORDER_SF_qDD
0x1400772e1  test    edi, edi
0x1400772e3  jnz     loc_1400778FB
0x1400772e9  lea     rsi, [rbx+14D8h]
0x1400772f0  mov     rcx, rsi; struct DeviceCommand *
0x1400772f3  lea     rdx, [rbp+arg_8]; int *
0x1400772f7  call    ?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z; CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)
0x1400772fc  mov     edi, eax
0x1400772fe  test    eax, eax
0x140077300  jz      short loc_140077348
0x140077302  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140077309  jz      loc_14007793E
0x14007730f  mov     eax, [rbp+arg_8]
0x140077312  mov     r9d, 3Dh ; '='
0x140077318  mov     rcx, cs:WPP_GLOBAL_Control
0x14007731f  mov     dl, 2
0x140077321  mov     [rsp+80h+var_40], eax
0x140077325  mov     eax, [rbx+10h]
0x140077328  mov     dword ptr [rsp+80h+var_48], edi
0x14007732c  mov     rcx, [rcx+40h]
0x140077330  mov     [rsp+80h+var_50], eax
0x140077334  mov     [rsp+80h+var_58], rbx
0x140077339  mov     [rsp+80h+var_60], r12
0x14007733e  call    WPP_RECORDER_SF_qDDd
0x140077343  jmp     loc_1400778FB
0x140077348  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x14007734c  mov     rcx, rsi; this
0x14007734f  lea     rdx, [rbp+arg_10]; unsigned int *
0x140077353  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x140077358  test    eax, eax
0x14007735a  jz      short loc_140077374
0x14007735c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140077363  jz      loc_14007793E
0x140077369  mov     r9d, 3Eh ; '>'
0x14007736f  jmp     loc_1400778D4
0x140077374  mov     ecx, [rbp+arg_10]
0x140077377  lea     r14, [rbx+1590h]
0x14007737e  mov     r8, [rbx+208h]
0x140077385  add     ecx, 0FFFFFFD0h
0x140077388  mov     rdx, [rbp+arg_18]
0x14007738c  add     r8, 3FF8h
0x140077393  add     rdx, 30h ; '0'
0x140077397  mov     r9, r14
0x14007739a  call    ParseWdiGetAdapterCapabilitiesFromIhv
0x14007739f  mov     edi, eax
0x1400773a1  test    eax, eax
0x1400773a3  jz      short loc_1400773C2
0x1400773a5  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400773ac  jz      loc_14007793E
0x1400773b2  mov     r9d, 3Fh ; '?'
0x1400773b8  mov     dword ptr [rsp+80h+var_48], r15d
0x1400773bd  jmp     loc_1400778D8
0x1400773c2  mov     rcx, rbx; this
0x1400773c5  call    ?ApplyDriverCapabilities@CMiniportInitializeJob@@AEAAHXZ; CMiniportInitializeJob::ApplyDriverCapabilities(void)
0x1400773ca  mov     edi, eax
0x1400773cc  test    eax, eax
0x1400773ce  jz      short loc_1400773E5
0x1400773d0  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400773d7  jz      loc_14007793E
0x1400773dd  mov     r9d, 40h ; '@'
0x1400773e3  jmp     short loc_1400773B8
0x1400773e5  mov     rdx, r14; struct _WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *
0x1400773e8  call    ?OverrideUnsupportedAuthCipherCombinations@CMiniportInitializeJob@@AEAAXAEAU_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS@@@Z; CMiniportInitializeJob::OverrideUnsupportedAuthCipherCombinations(_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS &)
0x1400773ed  mov     rcx, rbx; this
0x1400773f0  call    ?ApplyAdapterCapabilitiesOverride@CMiniportInitializeJob@@AEAAHXZ; CMiniportInitializeJob::ApplyAdapterCapabilitiesOverride(void)
0x1400773f5  mov     edi, eax
0x1400773f7  test    eax, eax
0x1400773f9  jz      short loc_140077436
0x1400773fb  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140077402  jz      loc_14007793E
0x140077408  mov     rcx, cs:WPP_GLOBAL_Control
0x14007740f  mov     r9d, 41h ; 'A'
0x140077415  mov     eax, [rbx+10h]
0x140077418  mov     dl, 2
0x14007741a  mov     [rsp+80h+var_50], eax
0x14007741e  mov     [rsp+80h+var_58], rbx
0x140077423  mov     rcx, [rcx+40h]
0x140077427  mov     [rsp+80h+var_60], r12
0x14007742c  call    WPP_RECORDER_SF_qD
0x140077431  jmp     loc_1400778FB
0x140077436  and     dword ptr [rbx+1788h], 0FFFFFFF3h
0x14007743d  mov     esi, 2
0x140077442  mov     rax, [rbx+208h]
0x140077449  mov     rcx, [rax+68h]
0x14007744d  cmp     [rcx+179h], r15b
0x140077454  jnz     short loc_140077464
0x140077456  mov     eax, [rbx+18D0h]
0x14007745c  test    al, 1
0x14007745e  jz      loc_14007752A
0x140077464  mov     rcx, rbx; this
0x140077467  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x14007746c  mov     r8b, 1; unsigned __int8
0x14007746f  mov     edx, 7Dh ; '}'; unsigned int
0x140077474  mov     rcx, rax; this
0x140077477  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14007747c  mov     r9d, [rbx+17B8h]
0x140077483  lea     rdx, [rbx+17BCh]
0x14007748a  mov     r8b, al
0x14007748d  test    sil, r9b
0x140077490  jnz     short loc_140077499
0x140077492  mov     ecx, [rdx]
0x140077494  test    sil, cl
0x140077497  jz      short loc_1400774E5
0x140077499  lea     rcx, [rbx+178Ch]
0x1400774a0  cmp     [rcx], r15d
0x1400774a3  jz      short loc_1400774E5
0x1400774a5  mov     eax, [rbx+17B0h]
0x1400774ab  sub     eax, 3
0x1400774ae  cmp     eax, 1
0x1400774b1  ja      short loc_1400774E5
0x1400774b3  test    r8b, r8b
0x1400774b6  jz      short loc_1400774DD
0x1400774b8  mov     ecx, [rbx+1788h]
0x1400774be  mov     eax, [rbx+18D0h]
0x1400774c4  or      ecx, 4
0x1400774c7  mov     [rbx+1788h], ecx
0x1400774cd  test    sil, al
0x1400774d0  jz      short loc_14007752A
0x1400774d2  or      ecx, 8
0x1400774d5  mov     [rbx+1788h], ecx
0x1400774db  jmp     short loc_14007752A
0x1400774dd  mov     r8d, 1
0x1400774e3  jmp     short loc_1400774EF
0x1400774e5  lea     rcx, [rbx+178Ch]
0x1400774ec  mov     r8d, r15d
0x1400774ef  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400774f6  jz      short loc_14007752A
0x1400774f8  mov     eax, [rcx]
0x1400774fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140077501  mov     [rsp+80h+var_30], eax
0x140077505  mov     eax, [rdx]
0x140077507  mov     [rsp+80h+var_38], eax
0x14007750b  mov     eax, [rbx+10h]
0x14007750e  mov     rcx, [rcx+40h]
0x140077512  mov     [rsp+80h+var_40], r9d
0x140077517  mov     dword ptr [rsp+80h+var_48], r8d
0x14007751c  mov     [rsp+80h+var_50], eax
0x140077520  mov     [rsp+80h+var_58], rbx
0x140077525  call    WPP_RECORDER_SF_qDdDDD
0x14007752a  mov     rdx, r14; struct _WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *
0x14007752d  mov     rcx, rbx; this
0x140077530  call    ?Is11adBandPresent@CMiniportInitializeJob@@AEAAEPEAU_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS@@@Z; CMiniportInitializeJob::Is11adBandPresent(_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *)
0x140077535  mov     r13b, al
0x140077538  test    al, al
0x14007753a  jz      short loc_14007754C
0x14007753c  mov     rcx, [rbx+208h]
0x140077543  mov     word ptr [rcx+0D54h], 384h
0x14007754c  mov     rcx, [rbx+208h]
0x140077553  add     rcx, 8
0x140077557  mov     [rbp+arg_10], r15d
0x14007755b  mov     dword ptr [rbp+arg_18], r15d
0x14007755f  mov     [rbp+var_10], r15d
0x140077563  mov     [rbp+var_C], r15d
0x140077567  mov     rax, [rcx]
0x14007756a  mov     rax, [rax+8]
0x14007756e  call    _guard_dispatch_icall
0x140077573  xor     r8d, r8d; unsigned __int8
0x140077576  mov     edx, 84h; unsigned int
0x14007757b  mov     rcx, rax; this
0x14007757e  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x140077583  mov     rcx, [rbx+208h]
0x14007758a  add     rcx, 8
0x14007758e  mov     rax, [rcx]
0x140077591  mov     rax, [rax+8]
0x140077595  call    _guard_dispatch_icall
0x14007759a  lea     r8, [rbp+arg_10]; unsigned int *
0x14007759e  mov     edx, 80h; unsigned int
0x1400775a3  mov     rcx, rax; this
0x1400775a6  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400775ab  mov     rcx, [rbx+208h]
0x1400775b2  add     rcx, 8
0x1400775b6  mov     rax, [rcx]
0x1400775b9  mov     rax, [rax+8]
0x1400775bd  call    _guard_dispatch_icall
0x1400775c2  lea     r8, [rbp+arg_18]; unsigned int *
0x1400775c6  mov     edx, 81h; unsigned int
0x1400775cb  mov     rcx, rax; this
0x1400775ce  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400775d3  mov     rcx, [rbx+208h]
0x1400775da  add     rcx, 8
0x1400775de  mov     rax, [rcx]
0x1400775e1  mov     rax, [rax+8]
0x1400775e5  call    _guard_dispatch_icall
0x1400775ea  lea     r8, [rbp+var_10]; unsigned int *
0x1400775ee  mov     edx, 82h; unsigned int
0x1400775f3  mov     rcx, rax; this
0x1400775f6  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400775fb  mov     rcx, [rbx+208h]
0x140077602  add     rcx, 8
0x140077606  mov     rax, [rcx]
0x140077609  mov     rax, [rax+8]
0x14007760d  call    _guard_dispatch_icall
0x140077612  lea     r8, [rbp+var_C]; unsigned int *
0x140077616  mov     edx, 83h; unsigned int
0x14007761b  mov     rcx, rax; this
0x14007761e  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140077623  mov     rcx, rbx; this
0x140077626  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x14007762b  mov     r8b, 1; unsigned __int8
0x14007762e  mov     edx, 88h; unsigned int
0x140077633  mov     rcx, rax; this
0x140077636  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14007763b  mov     byte ptr [rbp+arg_8], al
0x14007763e  mov     r12d, [rbp+var_10]; __annotation("TMF:",
0x140077642  lea     rcx, WPP_RECORDER_INITIALIZED
0x140077649  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140077650  mov     r15d, [rbp+var_C]
0x140077654  jz      short loc_1400776A1
0x140077656  mov     edx, [r14]
0x140077659  mov     [rsp+80h+var_20], r15d
0x14007765e  movzx   ecx, al
0x140077661  mov     eax, dword ptr [rbp+arg_18]
0x140077664  mov     [rsp+80h+var_28], r12d
0x140077669  mov     [rsp+80h+var_30], eax
0x14007766d  mov     eax, [rbp+arg_10]
0x140077670  mov     [rsp+80h+var_38], eax
0x140077674  mov     eax, [rbx+10h]
0x140077677  mov     [rsp+80h+var_40], ecx
0x14007767b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077682  shr     edx, 0Ah
0x140077685  and     edx, 1
0x140077688  mov     dword ptr [rsp+80h+var_48], edx
0x14007768c  mov     rcx, [rcx+40h]
0x140077690  mov     [rsp+80h+var_50], eax
0x140077694  mov     [rsp+80h+var_58], rbx
0x140077699  call    WPP_RECORDER_SF_qDDDdddd
0x14007769e  mov     al, byte ptr [rbp+arg_8]
0x1400776a1  xor     ecx, ecx
0x1400776a3  test    al, al
0x1400776a5  jz      loc_1400777B6
0x1400776ab  cmp     [rbp+arg_10], ecx
0x1400776ae  jnz     loc_1400777B6
0x1400776b4  cmp     dword ptr [rbp+arg_18], ecx
0x1400776b7  jnz     loc_1400777B6
0x1400776bd  test    dword ptr [r14], 400h
0x1400776c4  jz      short loc_1400776DE
0x1400776c6  cmp     [rbx+18ACh], cl
0x1400776cc  jnz     loc_1400777B6
0x1400776d2  cmp     [rbx+18ADh], cl
0x1400776d8  jnz     loc_1400777B6
0x1400776de  cmp     r12d, esi
0x1400776e1  jnz     short loc_140077721
0x1400776e3  mov     rcx, [rbx+208h]
0x1400776ea  mov     r12d, 1
0x1400776f0  add     rcx, 8
0x1400776f4  mov     rax, [rcx]
0x1400776f7  mov     rax, [rax+8]
0x1400776fb  call    _guard_dispatch_icall
0x140077700  mov     edx, 82h; unsigned int
0x140077705  mov     r8d, r12d; unsigned int
0x140077708  mov     rcx, rax; this
0x14007770b  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140077710  mov     rcx, [rbx+208h]; this
0x140077717  mov     edx, 82h; unsigned int
0x14007771c  call    ?PersistAdapterProperty@CAdapter@@QEAAHK@Z; CAdapter::PersistAdapterProperty(ulong)
0x140077721  cmp     r15d, esi
  ... truncated ...
```
