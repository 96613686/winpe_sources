# L2CapInt_ValidateReconfigChannelRequest(_BRB *)

- ea: `0x1400e0bb4`
- end: `0x1400e1967`
- name: `?L2CapInt_ValidateReconfigChannelRequest@@YA_NPEAU_BRB@@@Z`
- size: `3507`
- prototype: `bool __fastcall(struct _BRB *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400e1e50`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005a64`
- `0x140005b4c`
- `0x1400c4e70`
- `0x1400e0bb4`
- `0x1400e3b28`
- `0x1400e3b84`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400e13fd`
- `ntoskrnl!RtlCompareMemory` at `0x1400e14d3`
- `ntoskrnl!RtlCompareMemory` at `0x1400e156c`
- `ntoskrnl!RtlCompareMemory` at `0x1400e1665`
- `ntoskrnl!RtlCompareMemory` at `0x1400e13fd`
- `ntoskrnl!RtlCompareMemory` at `0x1400e14d3`
- `ntoskrnl!RtlCompareMemory` at `0x1400e156c`
- `ntoskrnl!RtlCompareMemory` at `0x1400e1665`

## pseudocode

```c
char __fastcall L2CapInt_ValidateReconfigChannelRequest(struct _BRB *a1, __int16 a2, __int16 a3)
{
  int Type; // r8d
  int v5; // edx
  wchar_t *DeviceInterfaceString; // rax
  wchar_t *IndicationCallback; // rax
  void *ServerHandle; // rax
  unsigned int TransferFlags; // r15d
  unsigned int ConfigInFlagsForBrb; // eax
  const struct _BRB *v11; // rcx
  int v12; // r9d
  PDEVICE_OBJECT v13; // rcx
  char v14; // r9
  __int16 v15; // r10
  __int16 v16; // r11
  unsigned __int8 *v17; // rcx
  unsigned int v18; // r11d
  unsigned __int16 v19; // ax
  PDEVICE_OBJECT v20; // r10
  int Preferred; // r8d
  unsigned __int8 *v22; // rcx
  PDEVICE_OBJECT v23; // r10
  _L2CAP_CONFIG_VALUE_RANGE *p_Mtu; // rcx
  unsigned int Min; // r9d
  unsigned __int16 v26; // ax
  unsigned __int8 *v27; // rcx
  char *p_Flow; // rax
  struct _L2CAP_CONFIG_OPTION *ChannelHandle; // rcx
  unsigned int NumExtraOptions; // edx
  int v31; // ebp
  unsigned __int16 v32; // cx
  unsigned int *p_Length; // rcx
  unsigned __int16 v34; // cx
  char *v35; // rcx
  wchar_t *v37; // rax
  __int16 v38; // [rsp+30h] [rbp-A8h]
  __int16 v39; // [rsp+30h] [rbp-A8h]
  __int16 v40; // [rsp+30h] [rbp-A8h]
  char v41; // [rsp+40h] [rbp-98h]
  char v42; // [rsp+40h] [rbp-98h]
  unsigned __int16 v43; // [rsp+48h] [rbp-90h]
  __int16 v44; // [rsp+48h] [rbp-90h]
  unsigned __int16 Max; // [rsp+50h] [rbp-88h]
  __int64 Source2; // [rsp+60h] [rbp-78h] BYREF
  char v47; // [rsp+68h] [rbp-70h]
  __int128 v48; // [rsp+70h] [rbp-68h] BYREF

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(a2) = 0;
  LOBYTE(a3) = 1;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    3,
    91,
    (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
    (char)a1);
  Type = a1->BrbHeader.Type;
  v5 = 258;
  if ( (unsigned __int16)(Type - 258) > 1u
    && (unsigned __int16)(Type - 530) > 1u
    && (unsigned __int16)(Type + 16119) > 1u )
  {
    if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
      goto LABEL_243;
    DeviceInterfaceString = a1->BrbGetDeviceInterfaceString.DeviceInterfaceString;
  }
  else
  {
    DeviceInterfaceString = (wchar_t *)a1->BrbL2caRegisterServer.IndicationCallback;
  }
  if ( !DeviceInterfaceString )
    goto LABEL_243;
  if ( (unsigned __int16)(Type - 258) > 1u
    && (unsigned __int16)(Type - 530) > 1u
    && (unsigned __int16)(Type + 16119) > 1u )
  {
    if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
      goto LABEL_24;
    IndicationCallback = a1->BrbGetDeviceInterfaceString.DeviceInterfaceString;
  }
  else
  {
    IndicationCallback = (wchar_t *)a1->BrbL2caRegisterServer.IndicationCallback;
  }
  if ( ((unsigned __int64)IndicationCallback & 0xFFFF000000000000uLL) != 0 )
  {
LABEL_243:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v5) = 0;
    if ( (unsigned __int16)(Type - 258) > 1u
      && (unsigned __int16)(Type - 530) > 1u
      && (unsigned __int16)(Type + 16119) > 1u )
    {
      if ( (unsigned __int16)(Type + 32512) > 1u && (LOWORD(Type) = Type + 32510, (unsigned __int16)Type > 1u) )
        LOBYTE(v37) = 0;
      else
        v37 = a1->BrbGetDeviceInterfaceString.DeviceInterfaceString;
    }
    else
    {
      v37 = (wchar_t *)a1->BrbL2caRegisterServer.IndicationCallback;
    }
    LOBYTE(Type) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_WORD)v5,
      (_WORD)Type,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      3,
      92,
      (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
      (char)v37);
    return 0;
  }
  if ( (unsigned __int16)(Type - 258) <= 1u
    || (unsigned __int16)(Type - 530) <= 1u
    || (unsigned __int16)(Type + 16119) <= 1u )
  {
    ServerHandle = a1->BrbGetDeviceInterfaceString.DeviceInterfaceString;
    goto LABEL_27;
  }
LABEL_24:
  if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
    goto LABEL_239;
  ServerHandle = a1->BrbL2caUnregisterServer.ServerHandle;
LABEL_27:
  if ( !ServerHandle )
  {
LABEL_239:
    v13 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v5) = 0;
    v38 = 93;
    goto LABEL_42;
  }
  if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - 530) > 1u )
  {
    if ( (unsigned __int16)(Type + 16119) > 1u )
    {
      if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
        TransferFlags = 0;
      else
        TransferFlags = a1->BrbL2caAclTransfer.TransferFlags;
    }
    else
    {
      TransferFlags = a1->BrbScoOpenChannel.CallbackFlags;
    }
  }
  else
  {
    TransferFlags = a1->BrbL2caOpenChannel.ConfigOut.Flags;
  }
  ConfigInFlagsForBrb = L2capCon_GetConfigInFlagsForBrb(a1);
  if ( (~ConfigInFlagsForBrb & v12) == 0 )
  {
    if ( (~L2capCon_GetConfigOutFlagsForBrb(v11) & TransferFlags) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v5) = 0;
      v38 = 95;
      goto LABEL_42;
    }
    if ( (v14 & 1) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u )
      {
        if ( (unsigned __int16)(Type - v15) > 1u )
        {
          if ( (unsigned __int16)(v16 + Type) > 1u )
          {
            if ( (unsigned __int16)(Type + 32512) > 1u )
            {
              v17 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 236;
              if ( (unsigned __int16)(Type + 32510) > 1u )
                v17 = 0;
            }
            else
            {
              v17 = &a1->BrbL2caPing.PingResponseData[30];
            }
          }
          else
          {
            v17 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 252;
          }
        }
        else
        {
          v17 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 244;
        }
      }
      else
      {
        v17 = &a1->BrbL2caPing.PingResponseData[38];
      }
      v18 = *(unsigned __int16 *)v17;
      if ( v18 < 0x30
        || (v5 = *((unsigned __int16 *)v17 + 2), (unsigned __int16)v5 < (unsigned __int16)v18)
        || (v19 = *((_WORD *)v17 + 1), v19 < (unsigned __int16)v18)
        || v19 > (unsigned __int16)v5 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v5) = 0;
        Preferred = *((unsigned __int16 *)v17 + 1);
        Max = *((_WORD *)v17 + 2);
        v43 = *((_WORD *)v17 + 1);
        v41 = *(_WORD *)v17;
        v39 = 96;
LABEL_67:
        LOBYTE(Preferred) = 1;
        WPP_RECORDER_AND_TRACE_SF_LLL(
          v20->AttachedDevice,
          v5,
          Preferred,
          v20->DeviceExtension,
          2,
          3,
          v39,
          (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
          v41,
          v43,
          Max);
        return 0;
      }
      v16 = 16119;
    }
    v5 = 258;
    if ( (v14 & 2) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u )
      {
        if ( (unsigned __int16)(Type - v15) > 1u )
        {
          if ( (unsigned __int16)(v16 + Type) > 1u )
          {
            if ( (unsigned __int16)(Type + 32512) > 1u )
            {
              v22 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 242;
              if ( (unsigned __int16)(Type + 32510) > 1u )
                v22 = 0;
            }
            else
            {
              v22 = &a1->BrbL2caPing.PingResponseData[36];
            }
          }
          else
          {
            v22 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 258;
          }
        }
        else
        {
          v22 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 250;
        }
      }
      else
      {
        v22 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 210;
      }
      if ( !*(_WORD *)v22 || *((_WORD *)v22 + 1) < *(_WORD *)v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v5) = 0;
        v44 = *((_WORD *)v22 + 1);
        v42 = *(_WORD *)v22;
        v40 = 97;
LABEL_86:
        LOBYTE(Type) = 1;
        WPP_RECORDER_AND_TRACE_SF_LL(
          v23->AttachedDevice,
          v5,
          Type,
          v23->DeviceExtension,
          2,
          3,
          v40,
          (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
          v42,
          v44);
        return 0;
      }
    }
    if ( (TransferFlags & 1) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v15) > 1u )
      {
        if ( (unsigned __int16)(v16 + Type) > 1u )
        {
          p_Mtu = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 132);
          if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
            p_Mtu = 0;
        }
        else
        {
          p_Mtu = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 148);
        }
      }
      else
      {
        p_Mtu = &a1->BrbL2caOpenChannel.ConfigOut.Mtu;
      }
      Min = p_Mtu->Min;
      if ( Min < 0x30
        || (v5 = p_Mtu->Max, (unsigned __int16)v5 < (unsigned __int16)Min)
        || (v26 = p_Mtu->Preferred, v26 < (unsigned __int16)Min)
        || v26 > (unsigned __int16)v5 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v5) = 0;
        Preferred = p_Mtu->Preferred;
        Max = p_Mtu->Max;
        v43 = p_Mtu->Preferred;
        v41 = p_Mtu->Min;
        v39 = 98;
        goto LABEL_67;
      }
    }
    v5 = 258;
    if ( (TransferFlags & 2) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v15) > 1u )
      {
        if ( (unsigned __int16)(v16 + Type) > 1u )
        {
          v27 = &a1->BrbL2caPing.PingRequestData[17];
          if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
            v27 = 0;
        }
        else
        {
          v27 = &a1->BrbL2caPing.PingRequestData[33];
        }
      }
      else
      {
        v27 = &a1->BrbL2caPing.PingRequestData[25];
      }
      if ( !*(_WORD *)v27 || *((_WORD *)v27 + 2) < *(_WORD *)v27 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v5) = 0;
        v44 = *((_WORD *)v27 + 2);
        v42 = *(_WORD *)v27;
        v40 = 99;
        goto LABEL_86;
      }
    }
    if ( (TransferFlags & 4) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v15) > 1u )
      {
        if ( (unsigned __int16)(v16 + Type) > 1u )
        {
          if ( (unsigned __int16)(Type + 32512) > 1u )
          {
            p_Flow = (char *)&a1->BrbL2caPing.PingRequestData[23];
            if ( (unsigned __int16)(Type + 32510) > 1u )
              p_Flow = 0;
          }
          else
          {
            p_Flow = (char *)&a1->BrbL2caPing.PingRequestData[23];
          }
        }
        else
        {
          p_Flow = (char *)&a1->BrbL2caPing.PingRequestData[39];
        }
      }
      else
      {
        p_Flow = (char *)&a1->BrbL2caOpenChannel.ConfigOut.Flow;
      }
      if ( *p_Flow )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v5) = 0;
        LOBYTE(Type) = 1;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          Type,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          3,
          100,
          (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
          *p_Flow);
        return 0;
      }
    }
    if ( (TransferFlags & 8) == 0 )
    {
LABEL_154:
      if ( a1->BrbHeader.Type == 0x8102 )
      {
        v31 = *((_DWORD *)&a1->BrbAclEnterActiveMode + 48);
        Source2 = 0;
        v47 = 0;
        if ( (TransferFlags & 0x40) != 0 )
        {
          if ( (v31 & 0xFFFFFFF8) != 0 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
              || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            {
              LOBYTE(v5) = 0;
            }
            v38 = 102;
            goto LABEL_42;
          }
          if ( (v31 & 4) != 0 )
          {
            if ( (v31 & 2) != 0 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
                || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
              {
                LOBYTE(v5) = 0;
              }
              v38 = 103;
              goto LABEL_42;
            }
            if ( RtlCompareMemory((char *)&a1->BrbAclEnterActiveMode + 196, &Source2, 7u) != 7
              || *(_WORD *)((char *)&a1->BrbAclEnterActiveMode + 203) < 0x30u )
            {
              v13 = WPP_GLOBAL_Control;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
                || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
              {
                LOBYTE(v5) = 0;
              }
              v38 = 104;
              goto LABEL_42;
            }
            if ( (TransferFlags & 2) == 0 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
                || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
              {
                LOBYTE(v5) = 0;
              }
              v38 = 105;
              goto LABEL_42;
            }
          }
        }
        else if ( v31 || RtlCompareMemory((char *)&a1->BrbAclEnterActiveMode + 196, &Source2, 9u) != 9 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 101;
          goto LABEL_42;
        }
        if ( (v31 & 7) == 1 && RtlCompareMemory((char *)&a1->BrbAclEnterActiveMode + 196, &Source2, 9u) != 9 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 106;
          goto LABEL_42;
        }
        if ( (v31 & 2) != 0
          && (a1->BrbL2caPing.PingResponseData[30]
           || (unsigned __int8)(a1->BrbL2caPing.PingResponseData[31] - 1) > 0x3Eu
           || *(_WORD *)((char *)&a1->BrbAclEnterActiveMode + 199)
           || *(_WORD *)((char *)&a1->BrbAclEnterActiveMode + 201)
           || *(_WORD *)((char *)&a1->BrbAclEnterActiveMode + 203) < 0x30u) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 107;
          goto LABEL_42;
        }
        if ( (TransferFlags & 0x80u) != 0 && a1->BrbL2caOpenChannel.ConfigIn.Mtu.Max >= 2u )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 108;
          goto LABEL_42;
        }
        v48 = 0;
        if ( RtlCompareMemory((char *)&a1->BrbAclEnterActiveMode + 210, &v48, 0x10u) != 16 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 109;
          goto LABEL_42;
        }
        if ( *((_WORD *)&a1->BrbAclEnterActiveMode + 113) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v5) = 0;
          v38 = 110;
          goto LABEL_42;
        }
      }
      v32 = a1->BrbHeader.Type;
      if ( (unsigned __int16)(v32 - 258) <= 1u )
      {
        *((_OWORD *)&a1->BrbAclEnterActiveMode + 19) = 0;
        *((_OWORD *)&a1->BrbAclEnterActiveMode + 20) = 0;
        *((_OWORD *)&a1->BrbAclEnterActiveMode + 21) = 0;
        *((_QWORD *)&a1->BrbAclEnterActiveMode + 44) = 0;
        goto LABEL_227;
      }
      if ( (unsigned __int16)(v32 - 530) <= 1u )
      {
        memset(&a1[1].BrbL2caAclTransfer.Hdr.ListEntry.Blink, 0, 0x58u);
        goto LABEL_227;
      }
      if ( (unsigned __int16)(v32 + 16119) > 1u )
      {
        if ( (unsigned __int16)(v32 + 32512) <= 1u )
        {
          *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 264) = 0;
          *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 280) = 0;
          *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 296) = 0;
          *((_QWORD *)&a1->BrbAclEnterActiveMode + 39) = 0;
          goto LABEL_227;
        }
        if ( (unsigned __int16)(v32 + 32510) > 1u )
        {
LABEL_227:
          v34 = a1->BrbHeader.Type;
          if ( (unsigned __int16)(v34 - 258) <= 1u )
          {
            *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 248) = 0;
            *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 264) = 0;
            *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 280) = 0;
            *((_QWORD *)&a1->BrbAclEnterActiveMode + 37) = 0;
LABEL_238:
            a1->BrbHeader.Context[1] = 0;
            return 1;
          }
          if ( (unsigned __int16)(v34 - 530) > 1u )
          {
            if ( (unsigned __int16)(v34 + 16119) > 1u )
            {
              if ( (unsigned __int16)(v34 + 32512) <= 1u )
              {
                *((_OWORD *)&a1->BrbAclEnterActiveMode + 13) = 0;
                *((_OWORD *)&a1->BrbAclEnterActiveMode + 14) = 0;
                *((_OWORD *)&a1->BrbAclEnterActiveMode + 15) = 0;
                *((_QWORD *)&a1->BrbAclEnterActiveMode + 32) = 0;
                goto LABEL_238;
              }
              if ( (unsigned __int16)(v34 + 32510) > 1u )
                goto LABEL_238;
              v35 = (char *)&a1->BrbAclEnterActiveMode + 248;
            }
            else
            {
              v35 = (char *)&a1->BrbAclEnterActiveMode + 296;
            }
          }
          else
          {
            v35 = (char *)&a1->BrbAclEnterActiveMode + 288;
          }
          memset(v35, 0, 0x58u);
          goto LABEL_238;
        }
        p_Length = (unsigned int *)((char *)&a1->BrbAclEnterActiveMode + 336);
      }
      else
      {
        p_Length = &a1[1].BrbHeader.Length;
      }
      memset(p_Length, 0, 0x58u);
      goto LABEL_227;
    }
    if ( (unsigned __int16)(Type - 258) > 1u )
    {
      if ( (unsigned __int16)(Type - v15) > 1u )
      {
        if ( (unsigned __int16)(v16 + Type) > 1u )
        {
          if ( (unsigned __int16)(Type + 32512) <= 1u || (unsigned __int16)(Type + 32510) <= 1u )
            ChannelHandle = (struct _L2CAP_CONFIG_OPTION *)a1->BrbScoOpenChannel.ChannelHandle;
          else
            ChannelHandle = 0;
        }
        else
        {
          ChannelHandle = (struct _L2CAP_CONFIG_OPTION *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 24);
        }
      }
      else
      {
        ChannelHandle = a1->BrbL2caOpenChannel.ConfigOut.ExtraOptions;
      }
      if ( (unsigned __int16)(Type - v15) > 1u )
      {
        if ( (unsigned __int16)(v16 + Type) > 1u )
        {
          if ( (unsigned __int16)(Type + 32512) > 1u && (unsigned __int16)(Type + 32510) > 1u )
            NumExtraOptions = 0;
          else
            NumExtraOptions = *((_DWORD *)&a1->BrbAclEnterActiveMode + 42);
        }
        else
        {
          NumExtraOptions = *((_DWORD *)&a1->BrbAclEnterActiveMode + 46);
        }
LABEL_153:
        if ( !L2CapInt_ValidateExtraOptions(ChannelHandle, NumExtraOptions) )
          return 0;
        goto LABEL_154;
      }
    }
    else
    {
      ChannelHandle = a1->BrbL2caOpenChannel.ConfigOut.ExtraOptions;
    }
    NumExtraOptions = a1->BrbL2caOpenChannel.ConfigOut.NumExtraOptions;
    goto LABEL_153;
  }
  v13 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v5) = 0;
  v38 = 94;
LABEL_42:
  LOBYTE(Type) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    v13->AttachedDevice,
    v5,
    Type,
    v13->DeviceExtension,
    2,
    3,
    v38,
    (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400e0bb4  push    rbx
0x1400e0bb6  push    rbp
0x1400e0bb7  push    rsi
0x1400e0bb8  push    rdi
0x1400e0bb9  push    r12
0x1400e0bbb  push    r13
0x1400e0bbd  push    r14
0x1400e0bbf  push    r15
0x1400e0bc1  sub     rsp, 98h
0x1400e0bc8  mov     rax, cs:__security_cookie
0x1400e0bcf  xor     rax, rsp
0x1400e0bd2  mov     [rsp+0D8h+var_58], rax
0x1400e0bda  mov     rbx, rcx
0x1400e0bdd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400e0be4  xor     r13d, r13d
0x1400e0be7  mov     sil, 4
0x1400e0bea  mov     r12w, 1
0x1400e0bef  mov     eax, [rcx+2Ch]
0x1400e0bf2  test    sil, al
0x1400e0bf5  jz      short loc_1400E0C00
0x1400e0bf7  mov     dl, r12b
0x1400e0bfa  cmp     [rcx+29h], sil
0x1400e0bfe  jnb     short loc_1400E0C03
0x1400e0c00  mov     dl, r13b
0x1400e0c03  mov     r9, [rcx+40h]
0x1400e0c07  lea     r14, WPP_6ff04b5cc55f3e31603028274367341f_Traceguids
0x1400e0c0e  mov     rcx, [rcx+18h]
0x1400e0c12  mov     ebp, 3
0x1400e0c17  mov     [rsp+0D8h+var_98], rbx
0x1400e0c1c  mov     r8b, r12b
0x1400e0c1f  mov     [rsp+0D8h+var_A0], r14
0x1400e0c24  mov     [rsp+0D8h+var_A8], 5Bh ; '['
0x1400e0c2b  mov     [rsp+0D8h+var_B0], ebp
0x1400e0c2f  mov     [rsp+0D8h+var_B8], sil
0x1400e0c34  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400e0c39  movzx   r8d, word ptr [rbx+16h]
0x1400e0c3e  mov     edx, 102h
0x1400e0c43  movzx   eax, r8w
0x1400e0c47  mov     edi, 7F00h
0x1400e0c4c  sub     ax, dx
0x1400e0c4f  mov     r11d, 3EF7h
0x1400e0c55  mov     r10d, 212h
0x1400e0c5b  lea     r15d, [rdi-2]
0x1400e0c5f  cmp     ax, r12w
0x1400e0c63  jbe     short loc_1400E0C7D
0x1400e0c65  movzx   eax, r8w
0x1400e0c69  sub     ax, r10w
0x1400e0c6d  cmp     ax, r12w
0x1400e0c71  jbe     short loc_1400E0C7D
0x1400e0c73  lea     eax, [r11+r8]
0x1400e0c77  cmp     ax, r12w
0x1400e0c7b  ja      short loc_1400E0C86
0x1400e0c7d  mov     rax, [rbx+80h]
0x1400e0c84  jmp     short loc_1400E0CA2
0x1400e0c86  lea     eax, [rdi+r8]
0x1400e0c8a  cmp     ax, r12w
0x1400e0c8e  jbe     short loc_1400E0C9E
0x1400e0c90  lea     eax, [r15+r8]
0x1400e0c94  cmp     ax, r12w
0x1400e0c98  ja      loc_1400E18A0
0x1400e0c9e  mov     rax, [rbx+70h]
0x1400e0ca2  test    rax, rax
0x1400e0ca5  jz      loc_1400E18A0
0x1400e0cab  movzx   eax, r8w
0x1400e0caf  sub     ax, dx
0x1400e0cb2  cmp     ax, r12w
0x1400e0cb6  jbe     short loc_1400E0CD0
0x1400e0cb8  movzx   eax, r8w
0x1400e0cbc  sub     ax, r10w
0x1400e0cc0  cmp     ax, r12w
0x1400e0cc4  jbe     short loc_1400E0CD0
0x1400e0cc6  lea     eax, [r11+r8]
0x1400e0cca  cmp     ax, r12w
0x1400e0cce  ja      short loc_1400E0CD9
0x1400e0cd0  mov     rax, [rbx+80h]
0x1400e0cd7  jmp     short loc_1400E0CF1
0x1400e0cd9  lea     eax, [rdi+r8]
0x1400e0cdd  cmp     ax, r12w
0x1400e0ce1  jbe     short loc_1400E0CED
0x1400e0ce3  lea     eax, [r15+r8]
0x1400e0ce7  cmp     ax, r12w
0x1400e0ceb  ja      short loc_1400E0D2F
0x1400e0ced  mov     rax, [rbx+70h]
0x1400e0cf1  mov     rcx, 0FFFF000000000000h
0x1400e0cfb  test    rcx, rax
0x1400e0cfe  jnz     loc_1400E18A0
0x1400e0d04  movzx   eax, r8w
0x1400e0d08  sub     ax, dx
0x1400e0d0b  cmp     ax, r12w
0x1400e0d0f  jbe     short loc_1400E0D29
0x1400e0d11  movzx   eax, r8w
0x1400e0d15  sub     ax, r10w
0x1400e0d19  cmp     ax, r12w
0x1400e0d1d  jbe     short loc_1400E0D29
0x1400e0d1f  lea     eax, [r11+r8]
0x1400e0d23  cmp     ax, r12w
0x1400e0d27  ja      short loc_1400E0D2F
0x1400e0d29  mov     rax, [rbx+70h]
0x1400e0d2d  jmp     short loc_1400E0D4B
0x1400e0d2f  lea     eax, [rdi+r8]
0x1400e0d33  cmp     ax, r12w
0x1400e0d37  jbe     short loc_1400E0D47
0x1400e0d39  lea     eax, [r15+r8]
0x1400e0d3d  cmp     ax, r12w
0x1400e0d41  ja      loc_1400E186F
0x1400e0d47  mov     rax, [rbx+78h]
0x1400e0d4b  test    rax, rax
0x1400e0d4e  jz      loc_1400E186F
0x1400e0d54  movzx   eax, r8w
0x1400e0d58  sub     ax, dx
0x1400e0d5b  cmp     ax, r12w
0x1400e0d5f  movzx   eax, r8w
0x1400e0d63  ja      short loc_1400E0D77
0x1400e0d65  mov     r9d, [rbx+0C8h]
0x1400e0d6c  sub     ax, dx
0x1400e0d6f  cmp     ax, r12w
0x1400e0d73  ja      short loc_1400E0DC6
0x1400e0d75  jmp     short loc_1400E0DD4
0x1400e0d77  sub     ax, r10w
0x1400e0d7b  cmp     ax, r12w
0x1400e0d7f  ja      short loc_1400E0D8A
0x1400e0d81  mov     r9d, [rbx+0F0h]
0x1400e0d88  jmp     short loc_1400E0DC6
0x1400e0d8a  lea     eax, [r11+r8]
0x1400e0d8e  cmp     ax, r12w
0x1400e0d92  ja      short loc_1400E0D9D
0x1400e0d94  mov     r9d, [rbx+0F8h]
0x1400e0d9b  jmp     short loc_1400E0DC6
0x1400e0d9d  lea     eax, [rdi+r8]
0x1400e0da1  cmp     ax, r12w
0x1400e0da5  ja      short loc_1400E0DB0
0x1400e0da7  mov     r9d, [rbx+0C0h]
0x1400e0dae  jmp     short loc_1400E0DC6
0x1400e0db0  lea     eax, [r15+r8]
0x1400e0db4  cmp     ax, r12w
0x1400e0db8  ja      short loc_1400E0DC3
0x1400e0dba  mov     r9d, [rbx+0E8h]
0x1400e0dc1  jmp     short loc_1400E0DC6
0x1400e0dc3  mov     r9d, r13d
0x1400e0dc6  movzx   eax, r8w
0x1400e0dca  sub     ax, r10w
0x1400e0dce  cmp     ax, r12w
0x1400e0dd2  ja      short loc_1400E0DDD
0x1400e0dd4  mov     r15d, [rbx+88h]
0x1400e0ddb  jmp     short loc_1400E0E10
0x1400e0ddd  lea     eax, [r11+r8]
0x1400e0de1  cmp     ax, r12w
0x1400e0de5  ja      short loc_1400E0DF0
0x1400e0de7  mov     r15d, [rbx+90h]
0x1400e0dee  jmp     short loc_1400E0E10
0x1400e0df0  lea     eax, [rdi+r8]
0x1400e0df4  cmp     ax, r12w
0x1400e0df8  jbe     short loc_1400E0E04
0x1400e0dfa  lea     eax, [r15+r8]
0x1400e0dfe  cmp     ax, r12w
0x1400e0e02  ja      short loc_1400E0E0D
0x1400e0e04  mov     r15d, [rbx+80h]
0x1400e0e0b  jmp     short loc_1400E0E10
0x1400e0e0d  mov     r15d, r13d
0x1400e0e10  mov     rcx, rbx; struct _BRB *
0x1400e0e13  call    ?L2capCon_GetConfigInFlagsForBrb@@YAKPEBU_BRB@@@Z; L2capCon_GetConfigInFlagsForBrb(_BRB const *)
0x1400e0e18  not     eax
0x1400e0e1a  test    r9d, eax
0x1400e0e1d  jz      short loc_1400E0E69
0x1400e0e1f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400e0e26  mov     edi, 2
0x1400e0e2b  mov     eax, [rcx+2Ch]
0x1400e0e2e  test    sil, al
0x1400e0e31  jz      short loc_1400E0E3C
0x1400e0e33  mov     dl, r12b
0x1400e0e36  cmp     [rcx+29h], dil
0x1400e0e3a  jnb     short loc_1400E0E3F
0x1400e0e3c  mov     dl, r13b
0x1400e0e3f  mov     [rsp+0D8h+var_A0], r14
0x1400e0e44  mov     [rsp+0D8h+var_A8], 5Eh ; '^'
0x1400e0e4b  mov     [rsp+0D8h+var_B0], ebp
0x1400e0e4f  mov     r9, [rcx+40h]
0x1400e0e53  mov     r8b, r12b
0x1400e0e56  mov     rcx, [rcx+18h]
0x1400e0e5a  mov     [rsp+0D8h+var_B8], dil
0x1400e0e5f  call    WPP_RECORDER_AND_TRACE_SF_
0x1400e0e64  jmp     loc_1400E1940
0x1400e0e69  call    ?L2capCon_GetConfigOutFlagsForBrb@@YAKPEBU_BRB@@@Z; L2capCon_GetConfigOutFlagsForBrb(_BRB const *)
0x1400e0e6e  not     eax
0x1400e0e70  test    r15d, eax
0x1400e0e73  jz      short loc_1400E0EA3
0x1400e0e75  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400e0e7c  mov     edi, 2
0x1400e0e81  mov     eax, [rcx+2Ch]
0x1400e0e84  test    sil, al
0x1400e0e87  jz      short loc_1400E0E92
0x1400e0e89  mov     dl, r12b
0x1400e0e8c  cmp     [rcx+29h], dil
0x1400e0e90  jnb     short loc_1400E0E95
0x1400e0e92  mov     dl, r13b
0x1400e0e95  mov     [rsp+0D8h+var_A0], r14
0x1400e0e9a  mov     [rsp+0D8h+var_A8], 5Fh ; '_'
0x1400e0ea1  jmp     short loc_1400E0E4B
0x1400e0ea3  test    r12b, r9b
0x1400e0ea6  jz      loc_1400E0FA7
0x1400e0eac  movzx   eax, r8w
0x1400e0eb0  mov     ecx, 102h
0x1400e0eb5  sub     ax, cx
0x1400e0eb8  cmp     ax, r12w
0x1400e0ebc  ja      short loc_1400E0EC7
0x1400e0ebe  lea     rcx, [rbx+0CCh]
0x1400e0ec5  jmp     short loc_1400E0F1C
0x1400e0ec7  movzx   eax, r8w
0x1400e0ecb  sub     ax, r10w
0x1400e0ecf  cmp     ax, r12w
0x1400e0ed3  ja      short loc_1400E0EDE
0x1400e0ed5  lea     rcx, [rbx+0F4h]
0x1400e0edc  jmp     short loc_1400E0F1C
0x1400e0ede  lea     eax, [r11+r8]
0x1400e0ee2  cmp     ax, r12w
0x1400e0ee6  ja      short loc_1400E0EF1
0x1400e0ee8  lea     rcx, [rbx+0FCh]
0x1400e0eef  jmp     short loc_1400E0F1C
0x1400e0ef1  lea     eax, [rdi+r8]
0x1400e0ef5  cmp     ax, r12w
0x1400e0ef9  ja      short loc_1400E0F04
0x1400e0efb  lea     rcx, [rbx+0C4h]
0x1400e0f02  jmp     short loc_1400E0F1C
0x1400e0f04  mov     eax, 7EFEh
0x1400e0f09  lea     rcx, [rbx+0ECh]
0x1400e0f10  add     eax, r8d
0x1400e0f13  cmp     ax, r12w
0x1400e0f17  jbe     short loc_1400E0F1C
0x1400e0f19  mov     rcx, r13
0x1400e0f1c  movzx   r11d, word ptr [rcx]
0x1400e0f20  cmp     r11d, 30h ; '0'
0x1400e0f24  jb      short loc_1400E0F3F
0x1400e0f26  movzx   edx, word ptr [rcx+4]
0x1400e0f2a  cmp     dx, r11w
0x1400e0f2e  jb      short loc_1400E0F3F
0x1400e0f30  movzx   eax, word ptr [rcx+2]
0x1400e0f34  cmp     ax, r11w
0x1400e0f38  jb      short loc_1400E0F3F
0x1400e0f3a  cmp     ax, dx
0x1400e0f3d  jbe     short loc_1400E0FA1
0x1400e0f3f  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400e0f46  mov     edi, 2
0x1400e0f4b  mov     eax, [r10+2Ch]
0x1400e0f4f  test    sil, al
0x1400e0f52  jz      short loc_1400E0F5D
0x1400e0f54  mov     dl, r12b
0x1400e0f57  cmp     [r10+29h], dil
0x1400e0f5b  jnb     short loc_1400E0F60
0x1400e0f5d  mov     dl, r13b
0x1400e0f60  movzx   eax, word ptr [rcx+4]
0x1400e0f64  movzx   r8d, word ptr [rcx+2]
0x1400e0f69  mov     dword ptr [rsp+0D8h+var_88], eax
0x1400e0f6d  mov     dword ptr [rsp+0D8h+var_90], r8d
0x1400e0f72  mov     dword ptr [rsp+0D8h+var_98], r11d
0x1400e0f77  mov     [rsp+0D8h+var_A0], r14
0x1400e0f7c  mov     [rsp+0D8h+var_A8], 60h ; '`'
0x1400e0f83  mov     r9, [r10+40h]
0x1400e0f87  mov     r8b, r12b
0x1400e0f8a  mov     rcx, [r10+18h]
0x1400e0f8e  mov     [rsp+0D8h+var_B0], ebp
0x1400e0f92  mov     [rsp+0D8h+var_B8], dil
0x1400e0f97  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x1400e0f9c  jmp     loc_1400E1940
0x1400e0fa1  mov     r11d, 3EF7h
0x1400e0fa7  mov     edi, 2
0x1400e0fac  mov     edx, 102h
0x1400e0fb1  test    dil, r9b
0x1400e0fb4  jz      loc_1400E108D
0x1400e0fba  movzx   eax, r8w
0x1400e0fbe  sub     ax, dx
0x1400e0fc1  cmp     ax, r12w
0x1400e0fc5  ja      short loc_1400E0FD0
0x1400e0fc7  lea     rcx, [rbx+0D2h]
0x1400e0fce  jmp     short loc_1400E1029
0x1400e0fd0  movzx   eax, r8w
0x1400e0fd4  sub     ax, r10w
0x1400e0fd8  cmp     ax, r12w
0x1400e0fdc  ja      short loc_1400E0FE7
0x1400e0fde  lea     rcx, [rbx+0FAh]
0x1400e0fe5  jmp     short loc_1400E1029
0x1400e0fe7  lea     eax, [r11+r8]
0x1400e0feb  cmp     ax, r12w
0x1400e0fef  ja      short loc_1400E0FFA
0x1400e0ff1  lea     rcx, [rbx+102h]
0x1400e0ff8  jmp     short loc_1400E1029
0x1400e0ffa  mov     eax, 7F00h
0x1400e0fff  add     eax, r8d
0x1400e1002  cmp     ax, r12w
0x1400e1006  ja      short loc_1400E1011
0x1400e1008  lea     rcx, [rbx+0CAh]
0x1400e100f  jmp     short loc_1400E1029
0x1400e1011  mov     eax, 7EFEh
0x1400e1016  lea     rcx, [rbx+0F2h]
0x1400e101d  add     eax, r8d
0x1400e1020  cmp     ax, r12w
0x1400e1024  jbe     short loc_1400E1029
0x1400e1026  mov     rcx, r13
0x1400e1029  movzx   r9d, word ptr [rcx]
0x1400e102d  cmp     r9w, r12w
0x1400e1031  jb      short loc_1400E103A
  ... truncated ...
```
