# CRequestFtmChildJob::ProcessFtmResponse(_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *)

- ea: `0x1400c1afc`
- end: `0x1400c23ae`
- name: `?ProcessFtmResponse@CRequestFtmChildJob@@AEAAHPEAU_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS@@@Z`
- size: `2226`
- prototype: `__int64 __fastcall(CRequestFtmChildJob *this, struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400c1460`

## callees

- `0x140010730`
- `0x1400122e0`
- `0x1400297a0`
- `0x14002aa28`
- `0x1400489f0`
- `0x1400c1864`
- `0x1400c19e4`
- `0x1400c1afc`
- `0x1400c257c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c1c20`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1c20`

## pseudocode

```c
__int64 __fastcall CRequestFtmChildJob::ProcessFtmResponse(
        CRequestFtmChildJob *this,
        struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *a2,
        unsigned int a3)
{
  struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *v3; // r14
  _DOT11_FTM_RESPONSE *v5; // rdx
  unsigned int m_uNumberOfTargetsSent; // ecx
  unsigned int ElementCount; // eax
  unsigned int v8; // edi
  unsigned int v9; // ebp
  __int64 v10; // rax
  char v11; // r12
  _WDI_FTM_RESPONSE_CONTAINER *pElements; // rbp
  unsigned int v13; // r13d
  __int64 v14; // rdi
  _WDI_MAC_ADDRESS *p_BSSID; // r14
  unsigned __int64 v16; // rsi
  int v17; // r9d
  _WDI_FTM_RESPONSE_STATUS Status; // ecx
  _DOT11_FTM_RESPONSE *m_pFtmResponses; // rax
  __int32 v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  _WDI_FTM_RESPONSE_CONTAINER::_WDI_FTM_RESPONSE_CONTAINER_Optional Optional; // ecx
  _WDI_FTM_PROPAGATION PropagationProperty; // ecx
  __int32 v27; // ecx
  unsigned __int8 *v28; // r14
  int v30; // r9d
  int v31; // [rsp+20h] [rbp-68h]
  char v32; // [rsp+28h] [rbp-60h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-58h]
  char LCIStatus; // [rsp+38h] [rbp-50h]
  unsigned int v35; // [rsp+90h] [rbp+8h]

  v3 = a2;
  v5 = (_DOT11_FTM_RESPONSE *)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      a3,
      38,
      (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
      (char)this,
      this->m_ActivityId);
    v5 = (_DOT11_FTM_RESPONSE *)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids;
  }
  m_uNumberOfTargetsSent = this->m_uNumberOfTargetsSent;
  ElementCount = v3->FTMResponseList.ElementCount;
  if ( v3->FTMResponseList.ElementCount == m_uNumberOfTargetsSent )
  {
    v8 = 0;
    v35 = 0;
    v9 = 0;
    if ( !ElementCount )
      goto LABEL_112;
    while ( 2 )
    {
      v10 = v9;
      v11 = 0;
      pElements = v3->FTMResponseList.pElements;
      v13 = 0;
      v14 = v10;
      p_BSSID = &pElements[v10].BSSID;
      while ( 1 )
      {
        if ( v13 >= this->m_uNumberOfResponses )
        {
          if ( !v11 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 2;
            WPP_RECORDER_SF_qD_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              a3,
              53,
              (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
              (char)this,
              this->m_ActivityId,
              (__int64)p_BSSID);
          }
          goto LABEL_110;
        }
        v16 = v13;
        if ( RtlCompareMemory(p_BSSID, &this->m_pFtmResponses[v16], 6u) == 6 )
          break;
LABEL_105:
        ++v13;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
        v17 = 0;
      }
      else if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || (v17 = 0, LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          40,
          (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
          (char)this,
          this->m_ActivityId,
          (__int64)p_BSSID);
        v17 = 0;
      }
      Status = pElements[v14].Status;
      m_pFtmResponses = this->m_pFtmResponses;
      if ( Status )
      {
        v20 = Status - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  if ( v24 == 1 )
                    m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_ABORTED;
                  else
                    m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED;
                }
                else
                {
                  m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_NOT_ATTEMPTED;
                }
              }
              else
              {
                m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_TIMEOUT;
              }
            }
            else
            {
              m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_INCAPABLE;
            }
          }
          else
          {
            m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_REJECTED;
          }
        }
        else
        {
          m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED_UNREACHABLE;
        }
      }
      else
      {
        m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_SUCCESS;
      }
      if ( pElements[v14].Status )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LCIStatus = pElements[v14].Status;
          v30 = 41;
          m_ActivityId = this->m_ActivityId;
          v32 = (char)this;
LABEL_121:
          LOBYTE(v5) = 2;
          WPP_RECORDER_SF_qDL(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v5,
            a3,
            v30,
            (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
            v32,
            m_ActivityId,
            LCIStatus);
        }
LABEL_110:
        v3 = a2;
        v9 = v35 + 1;
        v35 = v9;
        if ( v9 >= a2->FTMResponseList.ElementCount )
        {
          v8 = 0;
          goto LABEL_112;
        }
        continue;
      }
      break;
    }
    Optional = pElements[v14].Optional;
    if ( (*(_BYTE *)&Optional & 0x10) == 0 || (*(_BYTE *)&Optional & 2) == 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          42,
          (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
          (char)this,
          this->m_ActivityId,
          (*(_DWORD *)&pElements[v14].Optional & 0x10) != 0,
          (*(_DWORD *)&pElements[v14].Optional & 2) != 0);
      }
      this->m_pFtmResponses[v16].dot11FtmRequestResult = DOT11_FTM_REQUEST_RESULT_FAILED;
      goto LABEL_110;
    }
    v11 = 1;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        a3,
        43,
        (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
        (char)this,
        this->m_ActivityId,
        pElements[v14].RTT,
        pElements[v14].NumberOfMeasurements);
      v17 = 0;
    }
    this->m_pFtmResponses[v16].lRtt = pElements[v14].RTT;
    this->m_pFtmResponses[v16].uNumberOfMeasurements = pElements[v14].NumberOfMeasurements;
    if ( (*(_DWORD *)&pElements[v14].Optional & 1) != 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          44,
          (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
          (char)this,
          this->m_ActivityId,
          pElements[v14].RetryAfter);
      }
      this->m_pFtmResponses[v16].uRetryAfter = pElements[v14].RetryAfter;
    }
    if ( (*(_DWORD *)&pElements[v14].Optional & 4) != 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          45,
          (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
          (char)this,
          this->m_ActivityId,
          pElements[v14].SignalInfo.RSSI,
          pElements[v14].SignalInfo.LinkQuality);
      }
      this->m_pFtmResponses[v16].lRssi = pElements[v14].SignalInfo.RSSI;
      this->m_pFtmResponses[v16].ulLinkQuality = pElements[v14].SignalInfo.LinkQuality;
    }
    if ( (*(_DWORD *)&pElements[v14].Optional & 0x20) != 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF_qDI(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          v17,
          v31,
          (char)this,
          this->m_ActivityId,
          pElements[v14].RTTVariance);
      }
      this->m_pFtmResponses[v16].ullRTTVariance = pElements[v14].RTTVariance;
    }
    if ( (*(_DWORD *)&pElements[v14].Optional & 8) == 0 )
    {
LABEL_81:
      if ( (*(_DWORD *)&pElements[v14].Optional & 0x40) == 0 )
        goto LABEL_92;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          48,
          (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
          (char)this,
          this->m_ActivityId,
          pElements[v14].PropagationProperty);
      }
      PropagationProperty = pElements[v14].PropagationProperty;
      v5 = this->m_pFtmResponses;
      if ( PropagationProperty )
      {
        v27 = PropagationProperty - 1;
        if ( !v27 )
        {
          v5[v16].dot11FtmPropagation = DOT11_FTM_PROPAGATION_INDIRECT_PATH;
          goto LABEL_92;
        }
        if ( v27 == 1 )
        {
          v5[v16].dot11FtmPropagation = DOT11_FTM_PROPAGATION_LINE_OF_SIGHT;
          goto LABEL_92;
        }
      }
      v5[v16].dot11FtmPropagation = DOT11_FTM_PROPAGATION_UNKNOWN;
LABEL_92:
      if ( (*(_DWORD *)&pElements[v14].Optional & 0x80u) != 0 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v5) = 5;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v5,
            a3,
            49,
            (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
            (char)this,
            this->m_ActivityId);
        }
        this->m_pFtmResponses[v16].dot11LciValidFields = DOT11_LCI_VALID_FIELDS_NONE;
        if ( pElements[v14].LCIStatus )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_110;
          LCIStatus = pElements[v14].LCIStatus;
          v30 = 50;
          m_ActivityId = this->m_ActivityId;
          v32 = (char)this;
          goto LABEL_121;
        }
        if ( (*(_DWORD *)&pElements[v14].Optional & 0x100) == 0 || (a3 = pElements[v14].LCIReport.ElementCount, a3 < 2) )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              a3,
              51,
              (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          goto LABEL_110;
        }
        v28 = pElements[v14].LCIReport.pElements;
        if ( a3 == 2 && !*v28 && !v28[1] )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v5) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              2,
              52,
              (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          goto LABEL_110;
        }
        if ( !CRequestFtmChildJob::ParseLCISubelement(
                this,
                pElements[v14].LCIReport.pElements,
                a3,
                &this->m_pFtmResponses[v16]) )
          goto LABEL_110;
        CRequestFtmChildJob::ParseZSubelement(
          this,
          v28,
          pElements[v14].LCIReport.ElementCount,
          &this->m_pFtmResponses[v16]);
        p_BSSID = &pElements[v14].BSSID;
      }
      goto LABEL_105;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        a3 = 0;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_64;
      }
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        a3,
        47,
        (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
        (char)this,
        this->m_ActivityId,
        pElements[v14].BandwidthUsed);
    }
    a3 = 0;
LABEL_64:
    v5 = this->m_pFtmResponses;
    switch ( pElements[v14].BandwidthUsed )
    {
      case WDI_FTM_BANDWIDTH_5:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_5;
        break;
      case WDI_FTM_BANDWIDTH_10:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_10;
        break;
      case WDI_FTM_BANDWIDTH_20:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_20;
        break;
      case WDI_FTM_BANDWIDTH_40:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_40;
        break;
      case WDI_FTM_BANDWIDTH_80:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_80;
        break;
      case WDI_FTM_BANDWIDTH_80_80:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_80_80;
        break;
      case WDI_FTM_BANDWIDTH_160:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_160;
        break;
      case WDI_FTM_BANDWIDTH_2160:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_2160;
        break;
      default:
        v5[v16].dot11FtmBandwidth = DOT11_FTM_BANDWIDTH_UNKNOWN;
        break;
    }
    goto LABEL_81;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      a3,
      39,
      (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
      (char)this,
      this->m_ActivityId,
      ElementCount,
      m_uNumberOfTargetsSent);
  }
  v8 = -1073676267;
LABEL_112:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      this->m_ActivityId,
      54,
      (__int64)WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids,
      (char)this,
      this->m_ActivityId,
      v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1400c1afc  mov     [rsp+arg_8], rdx
0x1400c1b01  push    rbx
0x1400c1b02  push    rbp
0x1400c1b03  push    rsi
0x1400c1b04  push    rdi
0x1400c1b05  push    r12
0x1400c1b07  push    r13
0x1400c1b09  push    r14
0x1400c1b0b  sub     rsp, 50h
0x1400c1b0f  mov     r14, rdx
0x1400c1b12  mov     rbx, rcx
0x1400c1b15  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c1b1c  xor     r9d, r9d
0x1400c1b1f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c1b26  lea     rdx, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1b2d  jz      short loc_1400C1B6F
0x1400c1b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1b36  cmp     byte ptr [rcx+29h], 5
0x1400c1b3a  jnb     short loc_1400C1B43
0x1400c1b3c  cmp     [rcx+48h], r9w
0x1400c1b41  jz      short loc_1400C1B6F
0x1400c1b43  mov     eax, [rbx+10h]
0x1400c1b46  mov     r9d, 26h ; '&'
0x1400c1b4c  mov     rcx, [rcx+40h]
0x1400c1b50  mov     [rsp+88h+var_58], eax
0x1400c1b54  mov     [rsp+88h+var_60], rbx
0x1400c1b59  mov     [rsp+88h+var_68], rdx
0x1400c1b5e  mov     dl, 5
0x1400c1b60  call    WPP_RECORDER_SF_qD
0x1400c1b65  xor     r9d, r9d
0x1400c1b68  lea     rdx, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1b6f  mov     ecx, [rbx+40Ch]
0x1400c1b75  mov     eax, [r14]
0x1400c1b78  cmp     eax, ecx
0x1400c1b7a  jz      short loc_1400C1BC0
0x1400c1b7c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400c1b83  jz      short loc_1400C1BB6
0x1400c1b85  mov     [rsp+88h+var_48], ecx
0x1400c1b89  mov     r9d, 27h ; '''
0x1400c1b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1b96  mov     dword ptr [rsp+88h+var_50], eax
0x1400c1b9a  mov     eax, [rbx+10h]
0x1400c1b9d  mov     [rsp+88h+var_58], eax
0x1400c1ba1  mov     rcx, [rcx+40h]
0x1400c1ba5  mov     [rsp+88h+var_60], rbx
0x1400c1baa  mov     [rsp+88h+var_68], rdx
0x1400c1baf  mov     dl, 2
0x1400c1bb1  call    WPP_RECORDER_SF_qDdd
0x1400c1bb6  mov     edi, 0C0010015h
0x1400c1bbb  jmp     loc_1400C21F9
0x1400c1bc0  mov     [rsp+88h+arg_10], r9d
0x1400c1bc8  mov     edi, r9d
0x1400c1bcb  mov     [rsp+88h+arg_0], r9d
0x1400c1bd3  mov     ebp, r9d
0x1400c1bd6  test    eax, eax
0x1400c1bd8  jz      loc_1400C21F9
0x1400c1bde  mov     eax, ebp
0x1400c1be0  mov     r12b, r9b
0x1400c1be3  mov     rbp, [r14+8]
0x1400c1be7  mov     r13d, r9d
0x1400c1bea  lea     rdi, [rax+rax*4]
0x1400c1bee  shl     rdi, 4
0x1400c1bf2  lea     r14, [rbp+4]
0x1400c1bf6  add     r14, rdi
0x1400c1bf9  cmp     r13d, [rbx+408h]
0x1400c1c00  jnb     loc_1400C2354
0x1400c1c06  mov     rdx, [rbx+400h]
0x1400c1c0d  mov     r8d, 6; Length
0x1400c1c13  mov     eax, r13d
0x1400c1c16  mov     rcx, r14; Source1
0x1400c1c19  imul    rsi, rax, 68h ; 'h'
0x1400c1c1d  add     rdx, rsi; Source2
0x1400c1c20  call    cs:__imp_RtlCompareMemory
0x1400c1c27  nop     dword ptr [rax+rax+00h]
0x1400c1c2c  cmp     rax, 6
0x1400c1c30  jnz     loc_1400C2176
0x1400c1c36  lea     r10, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c1c3d  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400c1c44  jz      short loc_1400C1C97
0x1400c1c46  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1c4d  cmp     byte ptr [rcx+29h], 5
0x1400c1c51  jnb     short loc_1400C1C5D
0x1400c1c53  xor     r9d, r9d
0x1400c1c56  cmp     [rcx+48h], r9w
0x1400c1c5b  jz      short loc_1400C1C9A
0x1400c1c5d  mov     eax, [rbx+10h]
0x1400c1c60  lea     r12, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1c67  mov     rcx, [rcx+40h]
0x1400c1c6b  mov     r9d, 28h ; '('
0x1400c1c71  mov     [rsp+88h+var_50], r14
0x1400c1c76  mov     dl, 5
0x1400c1c78  mov     [rsp+88h+var_58], eax
0x1400c1c7c  mov     [rsp+88h+var_60], rbx
0x1400c1c81  mov     [rsp+88h+var_68], r12
0x1400c1c86  call    WPP_RECORDER_SF_qD_MAC_
0x1400c1c8b  xor     r9d, r9d
0x1400c1c8e  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1c95  jmp     short loc_1400C1CA1
0x1400c1c97  xor     r9d, r9d
0x1400c1c9a  lea     r12, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1ca1  mov     ecx, [rdi+rbp+0Ch]
0x1400c1ca5  mov     rax, [rbx+400h]
0x1400c1cac  test    ecx, ecx
0x1400c1cae  jz      short loc_1400C1D14
0x1400c1cb0  sub     ecx, 1
0x1400c1cb3  jz      short loc_1400C1D0A
0x1400c1cb5  sub     ecx, 1
0x1400c1cb8  jz      short loc_1400C1D00
0x1400c1cba  sub     ecx, 1
0x1400c1cbd  jz      short loc_1400C1CF6
0x1400c1cbf  sub     ecx, 1
0x1400c1cc2  jz      short loc_1400C1CEC
0x1400c1cc4  sub     ecx, 1
0x1400c1cc7  jz      short loc_1400C1CE2
0x1400c1cc9  cmp     ecx, 1
0x1400c1ccc  jz      short loc_1400C1CD8
0x1400c1cce  mov     dword ptr [rax+rsi+8], 7
0x1400c1cd6  jmp     short loc_1400C1D19
0x1400c1cd8  mov     dword ptr [rax+rsi+8], 6
0x1400c1ce0  jmp     short loc_1400C1D19
0x1400c1ce2  mov     dword ptr [rax+rsi+8], 5
0x1400c1cea  jmp     short loc_1400C1D19
0x1400c1cec  mov     dword ptr [rax+rsi+8], 4
0x1400c1cf4  jmp     short loc_1400C1D19
0x1400c1cf6  mov     dword ptr [rax+rsi+8], 3
0x1400c1cfe  jmp     short loc_1400C1D19
0x1400c1d00  mov     dword ptr [rax+rsi+8], 2
0x1400c1d08  jmp     short loc_1400C1D19
0x1400c1d0a  mov     dword ptr [rax+rsi+8], 1
0x1400c1d12  jmp     short loc_1400C1D19
0x1400c1d14  mov     [rax+rsi+8], r9d
0x1400c1d19  mov     eax, [rdi+rbp+0Ch]
0x1400c1d1d  test    eax, eax
0x1400c1d1f  jnz     loc_1400C2327
0x1400c1d25  mov     ecx, [rdi+rbp]
0x1400c1d28  test    cl, 10h
0x1400c1d2b  jz      loc_1400C22C9
0x1400c1d31  test    cl, 2
0x1400c1d34  jz      loc_1400C22C9
0x1400c1d3a  mov     r12b, 1
0x1400c1d3d  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400c1d44  jz      short loc_1400C1D9E
0x1400c1d46  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1d4d  cmp     byte ptr [rcx+29h], 5
0x1400c1d51  jnb     short loc_1400C1D5A
0x1400c1d53  cmp     [rcx+48h], r9w
0x1400c1d58  jz      short loc_1400C1D9E
0x1400c1d5a  movzx   eax, word ptr [rdi+rbp+12h]
0x1400c1d5f  mov     r9d, 2Bh ; '+'
0x1400c1d65  mov     rcx, [rcx+40h]
0x1400c1d69  mov     dl, 5
0x1400c1d6b  mov     [rsp+88h+var_48], eax
0x1400c1d6f  mov     eax, [rdi+rbp+20h]
0x1400c1d73  mov     dword ptr [rsp+88h+var_50], eax
0x1400c1d77  mov     eax, [rbx+10h]
0x1400c1d7a  mov     [rsp+88h+var_58], eax
0x1400c1d7e  lea     rax, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1d85  mov     [rsp+88h+var_60], rbx
0x1400c1d8a  mov     [rsp+88h+var_68], rax
0x1400c1d8f  call    WPP_RECORDER_SF_qDdd
0x1400c1d94  xor     r9d, r9d
0x1400c1d97  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1d9e  mov     eax, [rdi+rbp+20h]
0x1400c1da2  mov     rcx, [rbx+400h]
0x1400c1da9  mov     [rcx+rsi+1Ch], eax
0x1400c1dad  movzx   eax, word ptr [rdi+rbp+12h]
0x1400c1db2  mov     rcx, [rbx+400h]
0x1400c1db9  mov     [rcx+rsi+0Eh], ax
0x1400c1dbe  mov     eax, [rdi+rbp]
0x1400c1dc1  test    r12b, al
0x1400c1dc4  jz      short loc_1400C1E2D
0x1400c1dc6  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400c1dcd  jz      short loc_1400C1E1C
0x1400c1dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1dd6  cmp     byte ptr [rcx+29h], 5
0x1400c1dda  jnb     short loc_1400C1DE3
0x1400c1ddc  cmp     [rcx+48h], r9w
0x1400c1de1  jz      short loc_1400C1E1C
0x1400c1de3  movzx   eax, word ptr [rdi+rbp+10h]
0x1400c1de8  mov     r9d, 2Ch ; ','
0x1400c1dee  mov     rcx, [rcx+40h]
0x1400c1df2  mov     dl, 5
0x1400c1df4  mov     dword ptr [rsp+88h+var_50], eax
0x1400c1df8  mov     eax, [rbx+10h]
0x1400c1dfb  mov     [rsp+88h+var_58], eax
0x1400c1dff  lea     rax, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1e06  mov     [rsp+88h+var_60], rbx
0x1400c1e0b  mov     [rsp+88h+var_68], rax
0x1400c1e10  call    WPP_RECORDER_SF_qDL
0x1400c1e15  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1e1c  mov     rcx, [rbx+400h]
0x1400c1e23  movzx   eax, word ptr [rdi+rbp+10h]
0x1400c1e28  mov     [rcx+rsi+0Ch], ax
0x1400c1e2d  mov     eax, [rdi+rbp]
0x1400c1e30  test    al, 4
0x1400c1e32  jz      short loc_1400C1EB0
0x1400c1e34  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400c1e3b  jz      short loc_1400C1E92
0x1400c1e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1e44  cmp     byte ptr [rcx+29h], 5
0x1400c1e48  jnb     short loc_1400C1E52
0x1400c1e4a  xor     eax, eax
0x1400c1e4c  cmp     [rcx+48h], ax
0x1400c1e50  jz      short loc_1400C1E92
0x1400c1e52  mov     eax, [rdi+rbp+18h]
0x1400c1e56  mov     r9d, 2Dh ; '-'
0x1400c1e5c  mov     rcx, [rcx+40h]
0x1400c1e60  mov     dl, 5
0x1400c1e62  mov     [rsp+88h+var_48], eax
0x1400c1e66  mov     eax, [rdi+rbp+14h]
0x1400c1e6a  mov     dword ptr [rsp+88h+var_50], eax
0x1400c1e6e  mov     eax, [rbx+10h]
0x1400c1e71  mov     [rsp+88h+var_58], eax
0x1400c1e75  lea     rax, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1e7c  mov     [rsp+88h+var_60], rbx
0x1400c1e81  mov     [rsp+88h+var_68], rax
0x1400c1e86  call    WPP_RECORDER_SF_qDdd
0x1400c1e8b  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1e92  mov     rcx, [rbx+400h]
0x1400c1e99  mov     eax, [rdi+rbp+14h]
0x1400c1e9d  mov     [rcx+rsi+10h], eax
0x1400c1ea1  mov     rcx, [rbx+400h]
0x1400c1ea8  mov     eax, [rdi+rbp+18h]
0x1400c1eac  mov     [rcx+rsi+14h], eax
0x1400c1eb0  mov     eax, [rdi+rbp]
0x1400c1eb3  test    al, 20h
0x1400c1eb5  jz      short loc_1400C1F0C
0x1400c1eb7  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400c1ebe  jz      short loc_1400C1EFB
0x1400c1ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1ec7  cmp     byte ptr [rcx+29h], 5
0x1400c1ecb  jnb     short loc_1400C1ED5
0x1400c1ecd  xor     eax, eax
0x1400c1ecf  cmp     [rcx+48h], ax
0x1400c1ed3  jz      short loc_1400C1EFB
0x1400c1ed5  mov     rax, [rdi+rbp+28h]
0x1400c1eda  mov     rcx, [rcx+40h]
0x1400c1ede  mov     [rsp+88h+var_50], rax
0x1400c1ee3  mov     eax, [rbx+10h]
0x1400c1ee6  mov     [rsp+88h+var_58], eax
0x1400c1eea  mov     [rsp+88h+var_60], rbx
0x1400c1eef  call    WPP_RECORDER_SF_qDI
0x1400c1ef4  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1efb  mov     rcx, [rbx+400h]
0x1400c1f02  mov     rax, [rdi+rbp+28h]
0x1400c1f07  mov     [rcx+rsi+20h], rax
0x1400c1f0c  mov     eax, [rdi+rbp]
0x1400c1f0f  test    al, 8
0x1400c1f11  jz      loc_1400C1FFA
0x1400c1f17  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400c1f1e  jz      short loc_1400C1F6F
0x1400c1f20  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1f27  cmp     byte ptr [rcx+29h], 5
0x1400c1f2b  jnb     short loc_1400C1F37
0x1400c1f2d  xor     r8d, r8d
0x1400c1f30  cmp     [rcx+48h], r8w
0x1400c1f35  jz      short loc_1400C1F72
0x1400c1f37  mov     eax, [rdi+rbp+1Ch]
0x1400c1f3b  mov     r9d, 2Fh ; '/'
0x1400c1f41  mov     rcx, [rcx+40h]
0x1400c1f45  mov     dl, 5
0x1400c1f47  mov     dword ptr [rsp+88h+var_50], eax
0x1400c1f4b  mov     eax, [rbx+10h]
0x1400c1f4e  mov     [rsp+88h+var_58], eax
0x1400c1f52  lea     rax, WPP_d35b6af1b14e32008a5fc6807ffe07bd_Traceguids
0x1400c1f59  mov     [rsp+88h+var_60], rbx
0x1400c1f5e  mov     [rsp+88h+var_68], rax
0x1400c1f63  call    WPP_RECORDER_SF_qDL
0x1400c1f68  lea     r10, WPP_RECORDER_INITIALIZED
0x1400c1f6f  xor     r8d, r8d
0x1400c1f72  mov     ecx, [rdi+rbp+1Ch]
0x1400c1f76  mov     rdx, [rbx+400h]
0x1400c1f7d  sub     ecx, 1
0x1400c1f80  jz      short loc_1400C1FF2
0x1400c1f82  sub     ecx, 1
0x1400c1f85  jz      short loc_1400C1FE8
0x1400c1f87  sub     ecx, 1
0x1400c1f8a  jz      short loc_1400C1FDE
0x1400c1f8c  sub     ecx, 1
0x1400c1f8f  jz      short loc_1400C1FD4
0x1400c1f91  sub     ecx, 1
0x1400c1f94  jz      short loc_1400C1FCA
0x1400c1f96  sub     ecx, 1
0x1400c1f99  jz      short loc_1400C1FC0
0x1400c1f9b  sub     ecx, 1
0x1400c1f9e  jz      short loc_1400C1FB6
0x1400c1fa0  cmp     ecx, 1
0x1400c1fa3  jz      short loc_1400C1FAC
0x1400c1fa5  mov     [rdx+rsi+18h], r8d
0x1400c1faa  jmp     short loc_1400C1FFA
0x1400c1fac  mov     dword ptr [rdx+rsi+18h], 8
0x1400c1fb4  jmp     short loc_1400C1FFA
0x1400c1fb6  mov     dword ptr [rdx+rsi+18h], 7
0x1400c1fbe  jmp     short loc_1400C1FFA
0x1400c1fc0  mov     dword ptr [rdx+rsi+18h], 6
0x1400c1fc8  jmp     short loc_1400C1FFA
0x1400c1fca  mov     dword ptr [rdx+rsi+18h], 5
0x1400c1fd2  jmp     short loc_1400C1FFA
0x1400c1fd4  mov     dword ptr [rdx+rsi+18h], 4
0x1400c1fdc  jmp     short loc_1400C1FFA
  ... truncated ...
```
