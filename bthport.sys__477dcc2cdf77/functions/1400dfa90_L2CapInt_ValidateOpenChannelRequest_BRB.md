# L2CapInt_ValidateOpenChannelRequest(_BRB *)

- ea: `0x1400dfa90`
- end: `0x1400e0aff`
- name: `?L2CapInt_ValidateOpenChannelRequest@@YAEPEAU_BRB@@@Z`
- size: `4207`
- prototype: `unsigned __int8 __fastcall(struct _BRB *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400e1e50`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005a64`
- `0x140005b4c`
- `0x14000764c`
- `0x1400c4e70`
- `0x1400c8750`
- `0x1400dfa90`
- `0x1400e3b28`
- `0x1400e3b84`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400e0606`
- `ntoskrnl!RtlCompareMemory` at `0x1400e06d4`
- `ntoskrnl!RtlCompareMemory` at `0x1400e076d`
- `ntoskrnl!RtlCompareMemory` at `0x1400e0865`
- `ntoskrnl!RtlCompareMemory` at `0x1400e0606`
- `ntoskrnl!RtlCompareMemory` at `0x1400e06d4`
- `ntoskrnl!RtlCompareMemory` at `0x1400e076d`
- `ntoskrnl!RtlCompareMemory` at `0x1400e0865`

## pseudocode

```c
unsigned __int8 __fastcall L2CapInt_ValidateOpenChannelRequest(struct _BRB *a1, __int16 a2, __int16 a3)
{
  char *v4; // rdx
  int Type; // r8d
  void (__fastcall **p_IndicationCallback)(void *, _INDICATION_CODE, _INDICATION_PARAMETERS *); // rcx
  __int16 v7; // dx
  void (__fastcall *v8)(void *, _INDICATION_CODE, _INDICATION_PARAMETERS *); // rax
  unsigned int CallbackFlags; // r15d
  unsigned int ConfigInFlagsForBrb; // eax
  const struct _BRB *v11; // rcx
  int v12; // r9d
  PDEVICE_OBJECT v13; // rcx
  char v14; // r9
  __int16 v15; // r10
  __int16 v16; // r11
  _L2CAP_CONFIG_VALUE_RANGE *p_Mtu; // rcx
  unsigned int v18; // r11d
  unsigned __int16 v19; // ax
  PDEVICE_OBJECT v20; // r10
  int Preferred; // r8d
  unsigned __int16 v22; // r9
  char v23; // r10
  _L2CAP_CONFIG_VALUE_RANGE *v24; // rcx
  unsigned int Min; // r9d
  unsigned __int16 v26; // ax
  _L2CAP_CONFIG_VALUE_RANGE *p_FlushTO; // rcx
  unsigned __int16 v28; // r9
  unsigned __int16 v29; // ax
  void **p_CallbackContext; // rax
  PDEVICE_OBJECT v31; // rcx
  struct _L2CAP_CONFIG_OPTION *ExtraOptions; // rcx
  unsigned int NumExtraOptions; // edx
  __int16 v34; // r11
  __int16 v35; // r9
  __int16 v36; // r10
  int v37; // eax
  char v38; // al
  unsigned __int8 IncomingQueueDepth; // al
  unsigned int v40; // eax
  _L2CAP_CONFIG_OPTION *Callback; // rax
  void *ReferenceObject; // rax
  void *v43; // rcx
  _L2CAP_CONFIG_OPTION *v44; // rax
  unsigned int Flags; // ebp
  unsigned __int8 *v46; // rsi
  unsigned __int16 v47; // cx
  char *p_Length; // rcx
  unsigned __int16 v49; // cx
  char *v50; // rcx
  __int16 v52; // [rsp+30h] [rbp-A8h]
  __int16 v53; // [rsp+30h] [rbp-A8h]
  __int16 v54; // [rsp+30h] [rbp-A8h]
  char v55; // [rsp+40h] [rbp-98h]
  char v56; // [rsp+40h] [rbp-98h]
  unsigned __int16 v57; // [rsp+48h] [rbp-90h]
  __int16 v58; // [rsp+48h] [rbp-90h]
  unsigned __int16 Max; // [rsp+50h] [rbp-88h]
  __int64 Source2; // [rsp+60h] [rbp-78h] BYREF
  char v61; // [rsp+68h] [rbp-70h]
  __int128 v62; // [rsp+70h] [rbp-68h] BYREF

  v62 = 0;
  Source2 = 0;
  v61 = 0;
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
    49,
    (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
    (char)a1);
  Type = a1->BrbHeader.Type;
  if ( (unsigned __int16)(Type - 258) > 1u
    && (unsigned __int16)(Type - 530) > 1u
    && (unsigned __int16)(Type + 16119) > 1u
    || (p_IndicationCallback = &a1->BrbL2caRegisterServer.IndicationCallback, !a1->BrbL2caOpenChannel.BtAddress) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v52 = 50;
    goto LABEL_317;
  }
  if ( (unsigned __int16)(Type - 258) <= 1u
    || (unsigned __int16)(Type - 530) <= 1u
    || (unsigned __int16)(Type + 16119) <= 1u )
  {
    HIBYTE(v7) = 0;
    if ( ((unsigned __int64)*p_IndicationCallback & 0xFFFF000000000000uLL) != 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v7) = 0;
      if ( (unsigned __int16)(Type - 258) > 1u
        && (unsigned __int16)(Type - 530) > 1u
        && (LOWORD(Type) = Type + 16119, (unsigned __int16)Type > 1u) )
      {
        LOBYTE(v8) = 0;
      }
      else
      {
        v8 = *p_IndicationCallback;
      }
      LOBYTE(Type) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        (_WORD)Type,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        3,
        51,
        (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
        (char)v8);
      return 0;
    }
    if ( (unsigned __int16)(Type - 258) <= 1u )
      goto LABEL_23;
  }
  if ( (unsigned __int16)(Type - 530) > 1u )
  {
    if ( (unsigned __int16)(Type + 16119) > 1u )
      CallbackFlags = 0;
    else
      CallbackFlags = a1->BrbScoOpenChannel.CallbackFlags;
  }
  else
  {
LABEL_23:
    CallbackFlags = a1->BrbL2caOpenChannel.ConfigOut.Flags;
  }
  ConfigInFlagsForBrb = L2capCon_GetConfigInFlagsForBrb(a1);
  if ( (~ConfigInFlagsForBrb & v12) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v52 = 52;
LABEL_317:
    LOBYTE(Type) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v13->AttachedDevice,
      (_DWORD)v4,
      Type,
      v13->DeviceExtension,
      2,
      3,
      v52,
      (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids);
    return 0;
  }
  if ( (~L2capCon_GetConfigOutFlagsForBrb(v11) & CallbackFlags) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v52 = 53;
    goto LABEL_317;
  }
  if ( (unsigned __int16)(Type - v15) > 1u )
  {
    if ( (unsigned __int16)(Type - v16) > 1u )
    {
      p_Mtu = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 252);
      if ( (unsigned __int16)(Type + 16119) > 1u )
        p_Mtu = 0;
    }
    else
    {
      p_Mtu = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 244);
    }
  }
  else
  {
    p_Mtu = &a1->BrbL2caOpenChannel.ConfigIn.Mtu;
  }
  if ( (v14 & 1) == 0 )
  {
LABEL_54:
    if ( (unsigned __int16)(Type - v15) > 1u )
    {
      if ( (unsigned __int16)(Type - v16) > 1u )
      {
        v4 = (char *)&a1->BrbAclEnterActiveMode + 258;
        if ( (unsigned __int16)(Type + 16119) > 1u )
          v4 = 0;
      }
      else
      {
        v4 = (char *)&a1->BrbAclEnterActiveMode + 250;
      }
    }
    else
    {
      v4 = (char *)&a1->BrbAclEnterActiveMode + 210;
    }
    if ( (v14 & 2) != 0 )
    {
      v22 = *(_WORD *)v4;
      if ( !*(_WORD *)v4 || *((_WORD *)v4 + 1) < v22 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (v23 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          v23 = 0;
        LOBYTE(Type) = 1;
        v58 = *((_WORD *)v4 + 1);
        LOBYTE(v4) = v23;
        WPP_RECORDER_AND_TRACE_SF_LL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v4,
          Type,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          3,
          55,
          (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
          v22,
          v58);
        return 0;
      }
    }
    if ( (unsigned __int16)(Type - v15) > 1u && (unsigned __int16)(Type - v16) > 1u )
    {
      v24 = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 148);
      if ( (unsigned __int16)(Type + 16119) > 1u )
        v24 = 0;
    }
    else
    {
      v24 = &a1->BrbL2caOpenChannel.ConfigOut.Mtu;
    }
    if ( (CallbackFlags & 1) != 0 )
    {
      Min = v24->Min;
      if ( Min < 0x30
        || (LODWORD(v4) = v24->Max, (unsigned __int16)v4 < (unsigned __int16)Min)
        || (v26 = v24->Preferred, v26 < (unsigned __int16)Min)
        || v26 > (unsigned __int16)v4 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        Preferred = v24->Preferred;
        Max = v24->Max;
        v57 = v24->Preferred;
        v55 = v24->Min;
        v53 = 56;
        goto LABEL_52;
      }
    }
    LODWORD(v4) = 258;
    if ( (unsigned __int16)(Type - 258) > 1u )
    {
      if ( (unsigned __int16)(Type - v16) > 1u )
      {
        p_FlushTO = (_L2CAP_CONFIG_VALUE_RANGE *)((char *)&a1->BrbAclEnterActiveMode + 154);
        if ( (unsigned __int16)(Type + 16119) > 1u )
          p_FlushTO = 0;
      }
      else
      {
        p_FlushTO = &a1->BrbL2caOpenChannel.ConfigOut.FlushTO;
      }
    }
    else
    {
      p_FlushTO = &a1->BrbL2caOpenChannel.ConfigOut.FlushTO;
    }
    if ( (CallbackFlags & 2) != 0 )
    {
      v28 = p_FlushTO->Min;
      if ( !p_FlushTO->Min
        || (LODWORD(v4) = p_FlushTO->Max, (unsigned __int16)v4 < v28)
        || (v29 = p_FlushTO->Preferred, v29 < v28)
        || v29 > (unsigned __int16)v4 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        Preferred = p_FlushTO->Preferred;
        Max = p_FlushTO->Max;
        v57 = p_FlushTO->Preferred;
        v55 = p_FlushTO->Min;
        v53 = 57;
        goto LABEL_52;
      }
      LODWORD(v4) = 258;
    }
    if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v16) > 1u )
    {
      p_CallbackContext = &a1->BrbScoOpenChannel.CallbackContext;
      if ( (unsigned __int16)(Type + 16119) > 1u )
        p_CallbackContext = 0;
    }
    else
    {
      p_CallbackContext = &a1->BrbL2caRegisterServer.ServerHandle;
    }
    if ( (CallbackFlags & 4) != 0 && *(_BYTE *)p_CallbackContext )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v56 = *(_BYTE *)p_CallbackContext;
      v54 = 58;
LABEL_108:
      LOBYTE(Type) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        v31->AttachedDevice,
        (_DWORD)v4,
        Type,
        v31->DeviceExtension,
        2,
        3,
        v54,
        (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
        v56);
      return 0;
    }
    if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v16) > 1u )
    {
      if ( (unsigned __int16)(Type + 16119) > 1u )
        ExtraOptions = 0;
      else
        ExtraOptions = (struct _L2CAP_CONFIG_OPTION *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 24);
    }
    else
    {
      ExtraOptions = a1->BrbL2caOpenChannel.ConfigOut.ExtraOptions;
    }
    if ( (CallbackFlags & 8) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u && (unsigned __int16)(Type - v16) > 1u )
        NumExtraOptions = (unsigned __int16)(Type + 16119) > 1u ? 0 : *((_DWORD *)&a1->BrbAclEnterActiveMode + 46);
      else
        NumExtraOptions = a1->BrbL2caOpenChannel.ConfigOut.NumExtraOptions;
      if ( !L2CapInt_ValidateExtraOptions(ExtraOptions, NumExtraOptions) )
        return 0;
    }
    Type = a1->BrbHeader.Type;
    v34 = 258;
    v35 = 530;
    v36 = 16119;
    if ( (unsigned __int16)(Type - 258) > 1u
      && (unsigned __int16)(Type - 530) > 1u
      && (unsigned __int16)(Type + 16119) > 1u )
    {
      LODWORD(v4) = 0;
    }
    else
    {
      LODWORD(v4) = a1->BrbL2caRegisterServer.IndicationFlags;
    }
    if ( Type == 258 || Type == 259 || Type == 530 || Type == 531 )
    {
      v37 = -16712292;
    }
    else if ( (unsigned int)(Type - 49417) < 2 )
    {
      v37 = -33489508;
    }
    else
    {
      v37 = -1;
    }
    if ( (v37 & (unsigned int)v4) != 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (v38 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        v38 = 0;
      v56 = (char)v4;
      LOBYTE(v4) = v38;
      v54 = 59;
      goto LABEL_108;
    }
    if ( ((unsigned __int8)v4 & 3) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 60;
      goto LABEL_317;
    }
    if ( ((unsigned __int8)v4 & 0x60) == 0x60 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 61;
      goto LABEL_317;
    }
    if ( ((unsigned __int8)v4 & 0x60) != 0 )
    {
      if ( (unsigned __int16)(Type - 258) > 1u )
      {
        if ( (unsigned __int16)(Type - 530) > 1u )
        {
          if ( (unsigned __int16)(Type + 16119) > 1u )
            goto LABEL_155;
          IncomingQueueDepth = a1[1].BrbAclEnterActiveMode.Hdr.Reserved[0];
        }
        else
        {
          IncomingQueueDepth = (unsigned __int8)a1[1].BrbAclEnterActiveMode.Hdr.ClientContext[3];
        }
      }
      else
      {
        IncomingQueueDepth = a1->BrbL2caOpenChannel.IncomingQueueDepth;
      }
      if ( !IncomingQueueDepth )
      {
LABEL_155:
        v13 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        v52 = 62;
        goto LABEL_317;
      }
    }
    if ( ((unsigned int)v4 & 0x1000000) != 0 && L2capCon_GetMinimumEncryptionKeySizeForOpenBrb(a1) > 0x10u )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 63;
      goto LABEL_317;
    }
    if ( (unsigned __int16)(Type - v34) > 1u )
    {
      if ( (unsigned __int16)(Type - v35) > 1u )
      {
        if ( (unsigned __int16)(v36 + Type) > 1u )
          goto LABEL_286;
        v40 = *((_DWORD *)&a1->BrbAclEnterActiveMode + 66);
      }
      else
      {
        v40 = a1->BrbL2caOpenChannel.OutResults.Params.NumExtraOptions;
      }
    }
    else
    {
      v40 = a1->BrbL2caOpenChannel.CallbackFlags;
    }
    if ( (v40 & 0xFFFFFF80) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 64;
      goto LABEL_317;
    }
    if ( v40 )
    {
      if ( (unsigned __int16)(Type - v34) > 1u )
      {
        if ( (unsigned __int16)(Type - v35) > 1u )
        {
          if ( (unsigned __int16)(v36 + Type) > 1u )
            goto LABEL_191;
          Callback = (_L2CAP_CONFIG_OPTION *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 34);
        }
        else
        {
          Callback = a1->BrbL2caOpenChannel.OutResults.Params.ExtraOptions;
        }
      }
      else
      {
        Callback = (_L2CAP_CONFIG_OPTION *)a1->BrbL2caOpenChannel.Callback;
      }
      if ( !Callback )
        goto LABEL_191;
      if ( (unsigned __int16)(Type - v34) > 1u )
      {
        if ( (unsigned __int16)(Type - v35) > 1u )
        {
          if ( (unsigned __int16)(v36 + Type) > 1u )
            goto LABEL_191;
          ReferenceObject = (void *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 36);
        }
        else
        {
          ReferenceObject = (void *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 35);
        }
      }
      else
      {
        ReferenceObject = a1->BrbL2caOpenChannel.ReferenceObject;
      }
      if ( !ReferenceObject )
      {
LABEL_191:
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        if ( (unsigned __int16)(Type - v34) > 1u )
        {
          if ( (unsigned __int16)(Type - v35) > 1u )
          {
            if ( (unsigned __int16)(Type + 16119) > 1u )
              LOBYTE(v43) = 0;
            else
              v43 = (void *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 36);
          }
          else
          {
            v43 = (void *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 35);
          }
          if ( (unsigned __int16)(Type - v35) > 1u )
          {
            LOWORD(Type) = Type + 16119;
            if ( (unsigned __int16)Type > 1u )
              LOBYTE(v44) = 0;
            else
              v44 = (_L2CAP_CONFIG_OPTION *)*((_QWORD *)&a1->BrbAclEnterActiveMode + 34);
          }
          else
          {
            v44 = a1->BrbL2caOpenChannel.OutResults.Params.ExtraOptions;
          }
        }
        else
        {
          v43 = a1->BrbL2caOpenChannel.ReferenceObject;
          v44 = (_L2CAP_CONFIG_OPTION *)a1->BrbL2caOpenChannel.Callback;
        }
        LOBYTE(Type) = 1;
        WPP_RECORDER_AND_TRACE_SF_qi(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v4,
          Type,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          3,
          65,
          (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
          (char)v44,
          (char)v43);
        return 0;
      }
    }
    if ( (_WORD)Type == v35 )
    {
      Flags = a1->BrbL2caOpenChannel.ConfigIn.Flags;
      v46 = &a1->BrbL2caPing.PingResponseData[38];
    }
    else
    {
      if ( (_WORD)Type != 0xC109 )
      {
        if ( ((_WORD)Type == 259 || (_WORD)Type == 531 || (_WORD)Type == 0xC10A) && !a1->BrbL2caRegisterServer.BtAddress )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v4) = 0;
          v52 = 77;
          goto LABEL_317;
        }
LABEL_286:
        v47 = a1->BrbHeader.Type;
        if ( (unsigned __int16)(v47 - v34) <= 1u )
        {
          *((_OWORD *)&a1->BrbAclEnterActiveMode + 19) = 0;
          *((_OWORD *)&a1->BrbAclEnterActiveMode + 20) = 0;
          *((_OWORD *)&a1->BrbAclEnterActiveMode + 21) = 0;
          *((_QWORD *)&a1->BrbAclEnterActiveMode + 44) = 0;
          goto LABEL_297;
        }
        if ( (unsigned __int16)(v47 - v35) > 1u )
        {
          if ( (unsigned __int16)(v47 + 16119) > 1u )
          {
            if ( (unsigned __int16)(v47 + 32512) <= 1u )
            {
              *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 264) = 0;
              *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 280) = 0;
              *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 296) = 0;
              *((_QWORD *)&a1->BrbAclEnterActiveMode + 39) = 0;
              goto LABEL_297;
            }
            if ( (unsigned __int16)(v47 + 32510) > 1u )
            {
LABEL_297:
              v49 = a1->BrbHeader.Type;
              if ( (unsigned __int16)(v49 - v34) <= 1u )
              {
                *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 248) = 0;
                *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 264) = 0;
                *(_OWORD *)((char *)&a1->BrbAclEnterActiveMode + 280) = 0;
                *((_QWORD *)&a1->BrbAclEnterActiveMode + 37) = 0;
LABEL_308:
                a1->BrbHeader.Context[1] = 0;
                return 1;
              }
              if ( (unsigned __int16)(v49 - 530) > 1u )
              {
                if ( (unsigned __int16)(v49 + 16119) > 1u )
                {
                  if ( (unsigned __int16)(v49 + 32512) <= 1u )
                  {
                    *((_OWORD *)&a1->BrbAclEnterActiveMode + 13) = 0;
                    *((_OWORD *)&a1->BrbAclEnterActiveMode + 14) = 0;
                    *((_OWORD *)&a1->BrbAclEnterActiveMode + 15) = 0;
                    *((_QWORD *)&a1->BrbAclEnterActiveMode + 32) = 0;
                    goto LABEL_308;
                  }
                  if ( (unsigned __int16)(v49 + 32510) > 1u )
                    goto LABEL_308;
                  v50 = (char *)&a1->BrbAclEnterActiveMode + 248;
                }
                else
                {
                  v50 = (char *)&a1->BrbAclEnterActiveMode + 296;
                }
              }
              else
              {
                v50 = (char *)&a1->BrbAclEnterActiveMode + 288;
              }
              memset(v50, 0, 0x58u);
              goto LABEL_308;
            }
            p_Length = (char *)&a1->BrbAclEnterActiveMode + 336;
          }
          else
          {
            p_Length = (char *)&a1[1].BrbScoFlushChannel.Hdr.Length;
          }
        }
        else
        {
          p_Length = (char *)&a1[1].BrbL2caAclTransfer.Hdr.ListEntry.Blink;
        }
        memset(p_Length, 0, 0x58u);
        v34 = 258;
        goto LABEL_297;
      }
      Flags = *((_DWORD *)&a1->BrbAclEnterActiveMode + 52);
      v46 = (unsigned __int8 *)&a1->BrbAclEnterActiveMode + 212;
    }
    if ( (CallbackFlags & 0x40) != 0 )
    {
      if ( (Flags & 0xFFFFFFF8) != 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        v52 = 68;
        goto LABEL_317;
      }
      if ( (Flags & 4) != 0 )
      {
        if ( (Flags & 2) != 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v4) = 0;
          v52 = 69;
          goto LABEL_317;
        }
        if ( RtlCompareMemory(v46, &Source2, 7u) != 7 || *(_WORD *)(v46 + 7) < 0x30u )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v4) = 0;
          v52 = 70;
          goto LABEL_317;
        }
        if ( (CallbackFlags & 2) == 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v4) = 0;
          v52 = 71;
          goto LABEL_317;
        }
      }
    }
    else
    {
      if ( (CallbackFlags & 0x80u) != 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        v52 = 66;
        goto LABEL_317;
      }
      if ( Flags || RtlCompareMemory(v46, &Source2, 9u) != 9 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        v52 = 67;
        goto LABEL_317;
      }
    }
    if ( (Flags & 7) == 1 && RtlCompareMemory(v46, &Source2, 9u) != 9 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 72;
      goto LABEL_317;
    }
    if ( (Flags & 2) != 0 )
    {
      if ( *v46
        || (Type = 62, (unsigned __int8)(v46[1] - 1) > 0x3Eu)
        || *(_WORD *)(v46 + 3)
        || *(_WORD *)(v46 + 5)
        || *(_WORD *)(v46 + 7) < 0x30u )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v4) = 0;
        v52 = 73;
        goto LABEL_317;
      }
    }
    if ( (CallbackFlags & 0x80u) != 0 && *((_WORD *)&a1->BrbAclEnterActiveMode + 108) >= 2u )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 74;
      goto LABEL_317;
    }
    if ( RtlCompareMemory((char *)&a1->BrbAclEnterActiveMode + 218, &v62, 0x10u) != 16 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 75;
      goto LABEL_317;
    }
    if ( *((_WORD *)&a1->BrbAclEnterActiveMode + 117) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v4) = 0;
      v52 = 76;
      goto LABEL_317;
    }
    v35 = 530;
    v34 = 258;
    goto LABEL_286;
  }
  v18 = p_Mtu->Min;
  if ( v18 >= 0x30 )
  {
    LODWORD(v4) = p_Mtu->Max;
    if ( (unsigned __int16)v4 >= (unsigned __int16)v18 )
    {
      v19 = p_Mtu->Preferred;
      if ( v19 >= (unsigned __int16)v18 && v19 <= (unsigned __int16)v4 )
      {
        v16 = 530;
        goto LABEL_54;
      }
    }
  }
  v20 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v4) = 0;
  Preferred = p_Mtu->Preferred;
  Max = p_Mtu->Max;
  v57 = p_Mtu->Preferred;
  v55 = p_Mtu->Min;
  v53 = 54;
LABEL_52:
  LOBYTE(Preferred) = 1;
  WPP_RECORDER_AND_TRACE_SF_LLL(
    v20->AttachedDevice,
    (_DWORD)v4,
    Preferred,
    v20->DeviceExtension,
    2,
    3,
    v53,
    (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
    v55,
    v57,
    Max);
  return 0;
}

```

## disassembly

```asm
0x1400dfa90  push    rbx
0x1400dfa92  push    rbp
0x1400dfa93  push    rsi
0x1400dfa94  push    rdi
0x1400dfa95  push    r12
0x1400dfa97  push    r13
0x1400dfa99  push    r14
0x1400dfa9b  push    r15
0x1400dfa9d  sub     rsp, 98h
0x1400dfaa4  mov     rax, cs:__security_cookie
0x1400dfaab  xor     rax, rsp
0x1400dfaae  mov     [rsp+0D8h+var_58], rax
0x1400dfab6  xor     eax, eax
0x1400dfab8  xorps   xmm0, xmm0
0x1400dfabb  movups  [rsp+0D8h+var_68], xmm0
0x1400dfac0  mov     [rsp+0D8h+Source2], rax
0x1400dfac5  mov     rbx, rcx
0x1400dfac8  mov     [rsp+0D8h+var_70], al
0x1400dfacc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfad3  xor     r13d, r13d
0x1400dfad6  mov     sil, 4
0x1400dfad9  mov     r12w, 1
0x1400dfade  mov     eax, [rcx+2Ch]
0x1400dfae1  test    sil, al
0x1400dfae4  jz      short loc_1400DFAEF
0x1400dfae6  mov     dl, r12b
0x1400dfae9  cmp     [rcx+29h], sil
0x1400dfaed  jnb     short loc_1400DFAF2
0x1400dfaef  mov     dl, r13b
0x1400dfaf2  mov     r9, [rcx+40h]
0x1400dfaf6  lea     r14, WPP_6ff04b5cc55f3e31603028274367341f_Traceguids
0x1400dfafd  mov     rcx, [rcx+18h]
0x1400dfb01  mov     ebp, 3
0x1400dfb06  mov     [rsp+0D8h+var_98], rbx
0x1400dfb0b  mov     r8b, r12b
0x1400dfb0e  mov     [rsp+0D8h+var_A0], r14
0x1400dfb13  mov     [rsp+0D8h+var_A8], 31h ; '1'
0x1400dfb1a  mov     [rsp+0D8h+var_B0], ebp
0x1400dfb1e  mov     [rsp+0D8h+var_B8], sil
0x1400dfb23  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400dfb28  movzx   r8d, word ptr [rbx+16h]
0x1400dfb2d  mov     r10d, 102h
0x1400dfb33  movzx   eax, r8w
0x1400dfb37  mov     edi, 3EF7h
0x1400dfb3c  sub     ax, r10w
0x1400dfb40  mov     r11d, 212h
0x1400dfb46  cmp     ax, r12w
0x1400dfb4a  jbe     short loc_1400DFB68
0x1400dfb4c  movzx   eax, r8w
0x1400dfb50  sub     ax, r11w
0x1400dfb54  cmp     ax, r12w
0x1400dfb58  jbe     short loc_1400DFB68
0x1400dfb5a  lea     eax, [rdi+r8]
0x1400dfb5e  cmp     ax, r12w
0x1400dfb62  ja      loc_1400E0A93
0x1400dfb68  lea     rcx, [rbx+80h]
0x1400dfb6f  mov     rax, rcx
0x1400dfb72  cmp     [rax], r13
0x1400dfb75  jz      loc_1400E0A93
0x1400dfb7b  movzx   eax, r8w
0x1400dfb7f  sub     ax, r10w
0x1400dfb83  cmp     ax, r12w
0x1400dfb87  jbe     short loc_1400DFBA5
0x1400dfb89  movzx   eax, r8w
0x1400dfb8d  sub     ax, r11w
0x1400dfb91  cmp     ax, r12w
0x1400dfb95  jbe     short loc_1400DFBA5
0x1400dfb97  lea     eax, [rdi+r8]
0x1400dfb9b  cmp     ax, r12w
0x1400dfb9f  ja      loc_1400DFC8F
0x1400dfba5  mov     rax, rcx
0x1400dfba8  mov     rdx, 0FFFF000000000000h
0x1400dfbb2  test    [rax], rdx
0x1400dfbb5  jz      loc_1400DFC44
0x1400dfbbb  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfbc2  mov     edi, 2
0x1400dfbc7  mov     eax, [r10+2Ch]
0x1400dfbcb  test    sil, al
0x1400dfbce  jz      short loc_1400DFBD9
0x1400dfbd0  mov     dl, r12b
0x1400dfbd3  cmp     [r10+29h], dil
0x1400dfbd7  jnb     short loc_1400DFBDC
0x1400dfbd9  mov     dl, r13b
0x1400dfbdc  movzx   eax, r8w
0x1400dfbe0  mov     r9d, 102h
0x1400dfbe6  sub     ax, r9w
0x1400dfbea  cmp     ax, r12w
0x1400dfbee  jbe     short loc_1400DFC0D
0x1400dfbf0  movzx   eax, r8w
0x1400dfbf4  sub     ax, r11w
0x1400dfbf8  cmp     ax, r12w
0x1400dfbfc  jbe     short loc_1400DFC0D
0x1400dfbfe  mov     eax, 3EF7h
0x1400dfc03  add     r8w, ax
0x1400dfc07  cmp     r8w, r12w
0x1400dfc0b  ja      short loc_1400DFC12
0x1400dfc0d  mov     rax, [rcx]
0x1400dfc10  jmp     short loc_1400DFC15
0x1400dfc12  mov     rax, r13
0x1400dfc15  mov     r9, [r10+40h]
0x1400dfc19  mov     r8b, r12b
0x1400dfc1c  mov     rcx, [r10+18h]
0x1400dfc20  mov     [rsp+0D8h+var_98], rax
0x1400dfc25  mov     [rsp+0D8h+var_A0], r14
0x1400dfc2a  mov     [rsp+0D8h+var_A8], 33h ; '3'
0x1400dfc31  mov     [rsp+0D8h+var_B0], ebp
0x1400dfc35  mov     [rsp+0D8h+var_B8], dil
0x1400dfc3a  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400dfc3f  jmp     loc_1400E0AD8
0x1400dfc44  movzx   eax, r8w
0x1400dfc48  sub     ax, r10w
0x1400dfc4c  cmp     ax, r12w
0x1400dfc50  movzx   eax, r8w
0x1400dfc54  ja      short loc_1400DFC69
0x1400dfc56  mov     r9d, [rbx+0C8h]
0x1400dfc5d  sub     ax, r10w
0x1400dfc61  cmp     ax, r12w
0x1400dfc65  ja      short loc_1400DFC92
0x1400dfc67  jmp     short loc_1400DFCA0
0x1400dfc69  sub     ax, r11w
0x1400dfc6d  cmp     ax, r12w
0x1400dfc71  ja      short loc_1400DFC7C
0x1400dfc73  mov     r9d, [rbx+0F0h]
0x1400dfc7a  jmp     short loc_1400DFC92
0x1400dfc7c  lea     eax, [rdi+r8]
0x1400dfc80  cmp     ax, r12w
0x1400dfc84  ja      short loc_1400DFC8F
0x1400dfc86  mov     r9d, [rbx+0F8h]
0x1400dfc8d  jmp     short loc_1400DFC92
0x1400dfc8f  mov     r9d, r13d
0x1400dfc92  movzx   eax, r8w
0x1400dfc96  sub     ax, r11w
0x1400dfc9a  cmp     ax, r12w
0x1400dfc9e  ja      short loc_1400DFCA9
0x1400dfca0  mov     r15d, [rbx+88h]
0x1400dfca7  jmp     short loc_1400DFCBF
0x1400dfca9  lea     eax, [rdi+r8]
0x1400dfcad  cmp     ax, r12w
0x1400dfcb1  ja      short loc_1400DFCBC
0x1400dfcb3  mov     r15d, [rbx+90h]
0x1400dfcba  jmp     short loc_1400DFCBF
0x1400dfcbc  mov     r15d, r13d
0x1400dfcbf  mov     rcx, rbx; struct _BRB *
0x1400dfcc2  call    ?L2capCon_GetConfigInFlagsForBrb@@YAKPEBU_BRB@@@Z; L2capCon_GetConfigInFlagsForBrb(_BRB const *)
0x1400dfcc7  not     eax
0x1400dfcc9  test    r9d, eax
0x1400dfccc  jz      short loc_1400DFCFF
0x1400dfcce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfcd5  mov     edi, 2
0x1400dfcda  mov     eax, [rcx+2Ch]
0x1400dfcdd  test    sil, al
0x1400dfce0  jz      short loc_1400DFCEB
0x1400dfce2  mov     dl, r12b
0x1400dfce5  cmp     [rcx+29h], dil
0x1400dfce9  jnb     short loc_1400DFCEE
0x1400dfceb  mov     dl, r13b
0x1400dfcee  mov     [rsp+0D8h+var_A0], r14
0x1400dfcf3  mov     [rsp+0D8h+var_A8], 34h ; '4'
0x1400dfcfa  jmp     loc_1400E0ABF
0x1400dfcff  call    ?L2capCon_GetConfigOutFlagsForBrb@@YAKPEBU_BRB@@@Z; L2capCon_GetConfigOutFlagsForBrb(_BRB const *)
0x1400dfd04  not     eax
0x1400dfd06  test    r15d, eax
0x1400dfd09  jz      short loc_1400DFD3C
0x1400dfd0b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfd12  mov     edi, 2
0x1400dfd17  mov     eax, [rcx+2Ch]
0x1400dfd1a  test    sil, al
0x1400dfd1d  jz      short loc_1400DFD28
0x1400dfd1f  mov     dl, r12b
0x1400dfd22  cmp     [rcx+29h], dil
0x1400dfd26  jnb     short loc_1400DFD2B
0x1400dfd28  mov     dl, r13b
0x1400dfd2b  mov     [rsp+0D8h+var_A0], r14
0x1400dfd30  mov     [rsp+0D8h+var_A8], 35h ; '5'
0x1400dfd37  jmp     loc_1400E0ABF
0x1400dfd3c  movzx   eax, r8w
0x1400dfd40  sub     ax, r10w
0x1400dfd44  cmp     ax, r12w
0x1400dfd48  ja      short loc_1400DFD53
0x1400dfd4a  lea     rcx, [rbx+0CCh]
0x1400dfd51  jmp     short loc_1400DFD7E
0x1400dfd53  movzx   eax, r8w
0x1400dfd57  sub     ax, r11w
0x1400dfd5b  cmp     ax, r12w
0x1400dfd5f  ja      short loc_1400DFD6A
0x1400dfd61  lea     rcx, [rbx+0F4h]
0x1400dfd68  jmp     short loc_1400DFD7E
0x1400dfd6a  lea     eax, [rdi+r8]
0x1400dfd6e  lea     rcx, [rbx+0FCh]
0x1400dfd75  cmp     ax, r12w
0x1400dfd79  jbe     short loc_1400DFD7E
0x1400dfd7b  mov     rcx, r13
0x1400dfd7e  test    r12b, r9b
0x1400dfd81  jz      loc_1400DFE12
0x1400dfd87  movzx   r11d, word ptr [rcx]
0x1400dfd8b  cmp     r11d, 30h ; '0'
0x1400dfd8f  jb      short loc_1400DFDAA
0x1400dfd91  movzx   edx, word ptr [rcx+4]
0x1400dfd95  cmp     dx, r11w
0x1400dfd99  jb      short loc_1400DFDAA
0x1400dfd9b  movzx   eax, word ptr [rcx+2]
0x1400dfd9f  cmp     ax, r11w
0x1400dfda3  jb      short loc_1400DFDAA
0x1400dfda5  cmp     ax, dx
0x1400dfda8  jbe     short loc_1400DFE0C
0x1400dfdaa  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfdb1  mov     edi, 2
0x1400dfdb6  mov     eax, [r10+2Ch]
0x1400dfdba  test    sil, al
0x1400dfdbd  jz      short loc_1400DFDC8
0x1400dfdbf  mov     dl, r12b
0x1400dfdc2  cmp     [r10+29h], dil
0x1400dfdc6  jnb     short loc_1400DFDCB
0x1400dfdc8  mov     dl, r13b
0x1400dfdcb  movzx   eax, word ptr [rcx+4]
0x1400dfdcf  movzx   r8d, word ptr [rcx+2]
0x1400dfdd4  mov     dword ptr [rsp+0D8h+var_88], eax
0x1400dfdd8  mov     dword ptr [rsp+0D8h+var_90], r8d
0x1400dfddd  mov     dword ptr [rsp+0D8h+var_98], r11d
0x1400dfde2  mov     [rsp+0D8h+var_A0], r14
0x1400dfde7  mov     [rsp+0D8h+var_A8], 36h ; '6'
0x1400dfdee  mov     r9, [r10+40h]
0x1400dfdf2  mov     r8b, r12b
0x1400dfdf5  mov     rcx, [r10+18h]
0x1400dfdf9  mov     [rsp+0D8h+var_B0], ebp
0x1400dfdfd  mov     [rsp+0D8h+var_B8], dil
0x1400dfe02  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x1400dfe07  jmp     loc_1400E0AD8
0x1400dfe0c  mov     r11d, 212h
0x1400dfe12  movzx   eax, r8w
0x1400dfe16  sub     ax, r10w
0x1400dfe1a  cmp     ax, r12w
0x1400dfe1e  ja      short loc_1400DFE29
0x1400dfe20  lea     rdx, [rbx+0D2h]
0x1400dfe27  jmp     short loc_1400DFE54
0x1400dfe29  movzx   eax, r8w
0x1400dfe2d  sub     ax, r11w
0x1400dfe31  cmp     ax, r12w
0x1400dfe35  ja      short loc_1400DFE40
0x1400dfe37  lea     rdx, [rbx+0FAh]
0x1400dfe3e  jmp     short loc_1400DFE54
0x1400dfe40  lea     eax, [rdi+r8]
0x1400dfe44  lea     rdx, [rbx+102h]
0x1400dfe4b  cmp     ax, r12w
0x1400dfe4f  jbe     short loc_1400DFE54
0x1400dfe51  mov     rdx, r13
0x1400dfe54  mov     edi, 2
0x1400dfe59  test    dil, r9b
0x1400dfe5c  jz      short loc_1400DFEC4
0x1400dfe5e  movzx   r9d, word ptr [rdx]
0x1400dfe62  cmp     r9w, r12w
0x1400dfe66  jb      short loc_1400DFE6F
0x1400dfe68  cmp     [rdx+2], r9w
0x1400dfe6d  jnb     short loc_1400DFEC4
0x1400dfe6f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400dfe76  mov     eax, [rcx+2Ch]
0x1400dfe79  test    sil, al
0x1400dfe7c  jz      short loc_1400DFE87
0x1400dfe7e  mov     r10b, r12b
0x1400dfe81  cmp     [rcx+29h], dil
0x1400dfe85  jnb     short loc_1400DFE8A
0x1400dfe87  mov     r10b, r13b
0x1400dfe8a  movzx   eax, word ptr [rdx+2]
0x1400dfe8e  mov     r8b, r12b
0x1400dfe91  mov     dword ptr [rsp+0D8h+var_90], eax
0x1400dfe95  mov     dl, r10b
0x1400dfe98  mov     dword ptr [rsp+0D8h+var_98], r9d
0x1400dfe9d  mov     r9, [rcx+40h]
0x1400dfea1  mov     rcx, [rcx+18h]
0x1400dfea5  mov     [rsp+0D8h+var_A0], r14
0x1400dfeaa  mov     [rsp+0D8h+var_A8], 37h ; '7'
0x1400dfeb1  mov     [rsp+0D8h+var_B0], ebp
0x1400dfeb5  mov     [rsp+0D8h+var_B8], dil
0x1400dfeba  call    WPP_RECORDER_AND_TRACE_SF_LL
0x1400dfebf  jmp     loc_1400E0AD8
0x1400dfec4  movzx   eax, r8w
0x1400dfec8  sub     ax, r10w
0x1400dfecc  cmp     ax, r12w
0x1400dfed0  jbe     short loc_1400DFEE0
0x1400dfed2  movzx   eax, r8w
0x1400dfed6  sub     ax, r11w
0x1400dfeda  cmp     ax, r12w
0x1400dfede  ja      short loc_1400DFEE9
0x1400dfee0  lea     rcx, [rbx+8Ch]
0x1400dfee7  jmp     short loc_1400DFF01
0x1400dfee9  mov     eax, 3EF7h
0x1400dfeee  lea     rcx, [rbx+94h]
0x1400dfef5  add     eax, r8d
0x1400dfef8  cmp     ax, r12w
0x1400dfefc  jbe     short loc_1400DFF01
0x1400dfefe  mov     rcx, r13
0x1400dff01  mov     r10, rbx
0x1400dff04  test    r12b, r15b
0x1400dff07  jz      short loc_1400DFF70
0x1400dff09  movzx   r9d, word ptr [rcx]
0x1400dff0d  cmp     r9d, 30h ; '0'
0x1400dff11  jb      short loc_1400DFF2C
0x1400dff13  movzx   edx, word ptr [rcx+4]
0x1400dff17  cmp     dx, r9w
0x1400dff1b  jb      short loc_1400DFF2C
  ... truncated ...
```
