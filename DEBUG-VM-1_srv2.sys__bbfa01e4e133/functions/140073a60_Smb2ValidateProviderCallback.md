# Smb2ValidateProviderCallback

- ea: `0x140073a60`
- end: `0x1400744af`
- name: `Smb2ValidateProviderCallback`
- size: `2639`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `broker_com_uri`

## callees

- `0x140004dcc`
- `0x140007400`
- `0x140013bf0`
- `0x14001cef0`
- `0x14001d624`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x1400260fc`
- `0x1400261cc`
- `0x140027304`
- `0x1400384d0`
- `0x140059f9c`
- `0x14005a9c0`
- `0x14005b1c0`
- `0x14005b5d0`
- `0x14005c010`
- `0x14005cba0`
- `0x14005d230`
- `0x14006a5f0`
- `0x14006a830`
- `0x14006aee0`
- `0x140073a60`
- `0x1400744b8`
- `0x140074c50`
- `0x140081ef0`
- `0x1400834a0`
- `0x140086290`
- `0x140087730`
- `0x1400884a0`
- `0x1400886b0`
- `0x140089500`
- `0x14008c400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400743c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400743c4`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140073e4c`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140073e4c`
- `ksecdd!FreeContextBuffer` at `0x14007441a`
- `ksecdd!FreeContextBuffer` at `0x14007441a`
- `ksecdd!QueryContextAttributesW` at `0x140073f3d`
- `ksecdd!QueryContextAttributesW` at `0x140073f3d`

## pseudocode

```c
__int64 __fastcall Smb2ValidateProviderCallback(ULONG_PTR BugCheckParameter4, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rbp
  unsigned int v8; // ecx
  PDEVICE_OBJECT v9; // rcx
  unsigned int v10; // ecx
  int v11; // edx
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // edi
  __int64 (__fastcall *v17)(); // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  char v24; // al
  int v25; // ebp
  struct _UNICODE_STRING v26; // xmm0
  bool v27; // r14
  int v28; // r15d
  __int64 *v29; // rcx
  __int64 v30; // rsi
  struct _SecHandle *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbp
  ADDRESS_FAMILY *v34; // rdi
  UCHAR v35; // al
  __int64 v36; // r11
  __int64 v37; // rdx
  int v38; // ecx
  __int16 v39; // r10
  __int64 *v40; // rax
  __int64 v41; // rdi
  UCHAR v42; // al
  __int64 v43; // r11
  __int64 v44; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF
  WCHAR *pBuffer; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(BugCheckParameter4 + 560);
  v6 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 24LL);
  v7 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  *(_DWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 24) = BugCheckParameter4;
  *(_QWORD *)(v5 + 168) = -1;
  *(_QWORD *)(BugCheckParameter4 + 536) = Smb2PreSendPacket;
  v8 = *(_DWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL);
  if ( v8 < 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
        BugCheckParameter4);
    }
    *(_BYTE *)(BugCheckParameter4 + 474) = 1;
    Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 0);
    return 3221225485LL;
  }
  if ( *(_DWORD *)v6 == 1112364030 )
  {
    if ( v8 < 0x40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 2);
      return 3221225485LL;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDiiD(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int16 *)(v6 + 12),
        a3,
        BugCheckParameter4,
        *(unsigned __int16 *)(v6 + 12),
        *(_QWORD *)(v6 + 24),
        *(_QWORD *)(v6 + 40),
        *(_DWORD *)(v6 + 16));
    }
    if ( *(_WORD *)(v6 + 12) >= 0x14u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 3);
      return 3221225485LL;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(BugCheckParameter4 + 96) + 510LL)
      && !(unsigned __int8)SrvAdminAllowAnonymousAccess(v9, a2, a3, a4)
      && *(_WORD *)(v6 + 12) >= 2u )
    {
      if ( Microsoft_Windows_SMBServerEnableBits < 0 )
      {
        v29 = *(__int64 **)(v5 + 32);
        v30 = (__int64)(v29 + 9);
        if ( v29 )
        {
          v33 = *v29;
        }
        else
        {
          v30 = 0;
          LOBYTE(v33) = 0;
        }
        v34 = (ADDRESS_FAMILY *)(*(_QWORD *)(BugCheckParameter4 + 96) + 216LL);
        v35 = SOCKADDR_SIZE(*v34);
        McTemplateK0qbr0hzr2ijj_EtwWriteTransfer(
          v38,
          v37,
          BugCheckParameter4 + 584,
          v35,
          (__int64)v34,
          v39,
          *(_QWORD *)(v36 + 368),
          v33,
          v30,
          v37);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      return 3221225485LL;
    }
    if ( *(_WORD *)(v6 + 4) != 64 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 4);
      return 3221225485LL;
    }
    v10 = *(unsigned __int16 *)(v6 + 12);
    v11 = *(unsigned __int16 *)(v7 + 44);
    if ( (_WORD)v10 )
    {
      if ( (_WORD)v11 == 0xFFFF || (_WORD)v11 == 767 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 5);
        return 3221225485LL;
      }
    }
    else if ( (_WORD)v11 != 0xFFFF && (_WORD)v11 != 767 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4,
          v11);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 6);
      return 3221225485LL;
    }
    if ( (*(_BYTE *)(v7 + 49) & 2) == 0 || v10 > 0x11 || (v12 = 248576, !_bittest(&v12, v10)) )
    {
      v22 = *(_DWORD *)(BugCheckParameter4 + 404);
      if ( v22 > 0x11000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4,
            v22,
            69632);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 7);
        return 3221225485LL;
      }
    }
    if ( !*(_BYTE *)(BugCheckParameter4 + 472) && !*(_BYTE *)(BugCheckParameter4 + 473) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 772;
      v21 = 3221225626LL;
      goto LABEL_37;
    }
    *(_BYTE *)(v5 + 5) = (*(_DWORD *)(v6 + 16) & 0x20000000) != 0;
    *(_WORD *)(v5 + 12) = *(_WORD *)(v6 + 8);
    v13 = *(_DWORD *)(v6 + 16);
    if ( (v13 & 0x70) == 0 || (v14 = ((v13 >> 4) & 7) - 1, v14 > 2) )
      v14 = 2;
    *(_DWORD *)(v5 + 188) = v14;
    if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 0x1000) != 0 )
    {
      if ( (*(_BYTE *)(v7 + 49) & 8) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 8);
        return 3221225485LL;
      }
      v15 = *(_DWORD *)(v6 + 16);
      if ( (v15 & 8) != 0 )
      {
        *(_DWORD *)(v6 + 16) = v15 & 0xFFFFFFF7;
        *(_OWORD *)(v6 + 48) = 0;
      }
      *(_DWORD *)(v5 + 8) = 2;
      LOBYTE(a4) = 1;
      v16 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, a4, 0, 0);
      if ( v16 >= 0 )
        goto LABEL_24;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 830;
    }
    else
    {
      if ( (*(_BYTE *)(v6 + 16) & 8) != 0 )
      {
        if ( !*(_QWORD *)(v7 + 8) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            847);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 9);
          return 0;
        }
        if ( *(_WORD *)(v6 + 12) != 1 )
          goto LABEL_66;
        v23 = *(_DWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL);
        if ( v23 < 0x58 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              26,
              &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4,
              v23);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            871);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 10);
          return 0;
        }
        if ( (*(_BYTE *)(v6 + 66) & 1) != 0 )
          v24 = 1;
        else
LABEL_66:
          v24 = 0;
        LOBYTE(a4) = 1;
        v25 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, a4, 0, v24);
        if ( v25 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              27,
              &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            (unsigned int)v25,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            892);
          return 0;
        }
        if ( !*(_QWORD *)(v5 + 112) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            906);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 11);
          return 0;
        }
        v26 = *(struct _UNICODE_STRING *)(v6 + 48);
        *(_OWORD *)(v6 + 48) = 0;
        DestinationString = v26;
        v27 = *(_WORD *)(v6 + 12) != 1 || (*(_BYTE *)(v6 + 16) & 1) == 0;
        v28 = Smb2VerifySignature(BugCheckParameter4, &DestinationString);
        *(struct _UNICODE_STRING *)(v6 + 48) = DestinationString;
        if ( v28 < 0 )
        {
          *(_QWORD *)&DestinationString.Length = 0;
          DestinationString.Buffer = 0;
          pBuffer = 0;
          v31 = *(struct _SecHandle **)(v5 + 48);
          if ( v31
            && (v31[2].dwLower || v31[2].dwUpper)
            && QueryContextAttributesW(v31 + 2, 1u, &pBuffer) >= 0
            && pBuffer )
          {
            RtlInitUnicodeString(&DestinationString, pBuffer);
          }
          else
          {
            DestinationString = 0;
          }
          if ( v27 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
                BugCheckParameter4);
            }
            if ( byte_14004C339 < 0 )
            {
              v40 = *(__int64 **)(v5 + 32);
              if ( v40 )
                v41 = *v40;
              else
                LOBYTE(v41) = 0;
              v42 = SOCKADDR_SIZE(*(_WORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 216LL));
              McTemplateK0hzr0hzr2qbr4i_EtwWriteTransfer(
                DestinationString.Length >> 1,
                v42,
                BugCheckParameter4 + 584,
                *(_WORD *)(v43 + 360) >> 1,
                *(_QWORD *)(v43 + 368),
                DestinationString.Length >> 1,
                (__int64)DestinationString.Buffer,
                v42,
                v44,
                v41);
            }
          }
          if ( pBuffer )
            FreeContextBuffer(pBuffer);
          Smb2SetError(
            BugCheckParameter4,
            (unsigned int)v28,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            963);
          return 0;
        }
        *(_QWORD *)(BugCheckParameter4 + 536) = Smb2SignPacket;
        *(_DWORD *)(v5 + 8) = 1;
        goto LABEL_24;
      }
      v19 = *(_QWORD *)(v6 + 40);
      if ( !v19
        || *(_WORD *)(v6 + 12) == 1
        || (LOBYTE(a4) = 1, v16 = Smb2VerifySessionExEx(BugCheckParameter4, v19, v6, a4, 1, 0), v16 >= 0) )
      {
LABEL_24:
        if ( !*(_DWORD *)(BugCheckParameter4 + 480) )
        {
          if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 0x40) != 0 )
          {
            v32 = *(_QWORD *)(BugCheckParameter4 + 416);
            if ( v32 )
              *(_DWORD *)(v32 + 484) |= 0x40u;
          }
          goto LABEL_26;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225760LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
          1000);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 984;
    }
    v21 = (unsigned int)v16;
LABEL_37:
    Smb2SetError(BugCheckParameter4, v21, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c", v20);
    return 0;
  }
  if ( *(_DWORD *)v6 == 1112364031 && *(_WORD *)(v7 + 44) == 0xFFFF )
  {
    *(_WORD *)(v5 + 14) = 0;
LABEL_26:
    v17 = Smb2ValidateRoutines[*(unsigned __int16 *)(v5 + 14)];
    if ( v17 )
      return ((__int64 (__fastcall *)(ULONG_PTR))v17)(BugCheckParameter4);
    else
      return Smb2ValidateNotImplemented(BugCheckParameter4);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      &WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
      BugCheckParameter4);
  }
  *(_BYTE *)(BugCheckParameter4 + 474) = 1;
  Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 1);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140073a60  mov     r11, rsp
0x140073a63  push    rbx
0x140073a64  push    rbp
0x140073a65  push    rsi
0x140073a66  push    rdi
0x140073a67  push    r12
0x140073a69  sub     rsp, 60h
0x140073a6d  mov     rax, [rcx+130h]
0x140073a74  mov     rbx, rcx
0x140073a77  mov     rsi, [rcx+230h]
0x140073a7e  mov     rdi, [rax+18h]
0x140073a82  mov     rax, [rcx+60h]
0x140073a86  mov     rbp, [rax+1F0h]
0x140073a8d  lea     rax, Smb2PreSendPacket
0x140073a94  mov     dword ptr [rsi+8], 0
0x140073a9b  mov     [rsi+18h], rcx
0x140073a9f  mov     qword ptr [rsi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140073aaa  mov     [rcx+218h], rax
0x140073ab1  mov     rax, [rcx+130h]
0x140073ab8  mov     ecx, [rax+24h]
0x140073abb  cmp     ecx, 4
0x140073abe  jb      loc_140073D23
0x140073ac4  mov     eax, [rdi]
0x140073ac6  mov     [r11+10h], r14
0x140073aca  mov     [r11+18h], r15
0x140073ace  cmp     eax, 424D53FEh
0x140073ad3  jnz     loc_140073D5C
0x140073ad9  cmp     ecx, 40h ; '@'
0x140073adc  jb      loc_140073ED2
0x140073ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ae9  lea     r12, WPP_GLOBAL_Control
0x140073af0  cmp     rcx, r12
0x140073af3  jz      short loc_140073B02
0x140073af5  test    dword ptr [rcx+2Ch], 800h
0x140073afc  jnz     loc_1400740BB
0x140073b02  cmp     word ptr [rdi+0Ch], 14h
0x140073b07  jnb     loc_1400740F7
0x140073b0d  mov     rax, [rbx+60h]
0x140073b11  cmp     byte ptr [rax+1FEh], 0
0x140073b18  jz      loc_140073E4C
0x140073b1e  cmp     word ptr [rdi+4], 40h ; '@'
0x140073b23  jnz     loc_140073FC0
0x140073b29  movzx   ecx, word ptr [rdi+0Ch]
0x140073b2d  mov     eax, 0FFFFh
0x140073b32  movzx   edx, word ptr [rbp+2Ch]
0x140073b36  test    cx, cx
0x140073b39  jz      loc_1400967CA
0x140073b3f  cmp     dx, ax
0x140073b42  jz      loc_140073F92
0x140073b48  mov     eax, 2FFh
0x140073b4d  cmp     dx, ax
0x140073b50  jz      loc_140073F92
0x140073b56  test    byte ptr [rbp+31h], 2
0x140073b5a  jz      loc_140073CE1
0x140073b60  cmp     ecx, 11h
0x140073b63  ja      loc_140073CE1
0x140073b69  mov     eax, 3CB00h
0x140073b6e  bt      eax, ecx
0x140073b71  jnb     loc_140073CE1
0x140073b77  cmp     byte ptr [rbx+1D8h], 0
0x140073b7e  jz      loc_140096838
0x140073b84  mov     eax, [rdi+10h]
0x140073b87  shr     eax, 1Dh
0x140073b8a  and     al, 1
0x140073b8c  mov     [rsi+5], al
0x140073b8f  movzx   eax, word ptr [rdi+8]
0x140073b93  mov     [rsi+0Ch], ax
0x140073b97  mov     eax, [rdi+10h]
0x140073b9a  test    al, 70h
0x140073b9c  jz      short loc_140073BAB
0x140073b9e  shr     eax, 4
0x140073ba1  and     eax, 7
0x140073ba4  dec     eax
0x140073ba6  cmp     eax, 2
0x140073ba9  jbe     short loc_140073BB0
0x140073bab  mov     eax, 2
0x140073bb0  mov     [rsi+0BCh], eax
0x140073bb6  test    dword ptr [rbx+1E4h], 1000h
0x140073bc0  jz      loc_140073C5F
0x140073bc6  test    byte ptr [rbp+31h], 8
0x140073bca  jz      loc_1400741E5
0x140073bd0  mov     eax, [rdi+10h]
0x140073bd3  test    al, 8
0x140073bd5  jnz     loc_14007422A
0x140073bdb  mov     dword ptr [rsi+8], 2
0x140073be2  mov     r9b, 1
0x140073be5  mov     rdx, [rdi+28h]
0x140073be9  mov     r8, rdi
0x140073bec  mov     byte ptr [rsp+88h+var_60], 0
0x140073bf1  mov     rcx, rbx
0x140073bf4  mov     byte ptr [rsp+88h+var_68], 0
0x140073bf9  call    Smb2VerifySessionExEx
0x140073bfe  mov     edi, eax
0x140073c00  test    eax, eax
0x140073c02  js      loc_140073CB3
0x140073c08  cmp     dword ptr [rbx+1E0h], 0
0x140073c0f  jnz     loc_140073FEE
0x140073c15  mov     eax, [rbx+1E4h]
0x140073c1b  test    al, 40h
0x140073c1d  jnz     loc_140074493
0x140073c23  movzx   eax, word ptr [rsi+0Eh]
0x140073c27  lea     rcx, Smb2ValidateRoutines
0x140073c2e  mov     rax, ds:(Smb2ValidateRoutines - 14003F000h)[rcx+rax*8]
0x140073c32  mov     rcx, rbx; BugCheckParameter4
0x140073c35  test    rax, rax
0x140073c38  jz      loc_140073D81
0x140073c3e  call    _guard_dispatch_icall
0x140073c43  mov     r14, [rsp+88h+arg_8]
0x140073c4b  mov     r15, [rsp+88h+arg_10]
0x140073c53  add     rsp, 60h
0x140073c57  pop     r12
0x140073c59  pop     rdi
0x140073c5a  pop     rsi
0x140073c5b  pop     rbp
0x140073c5c  pop     rbx
0x140073c5d  retn
0x140073c5f  test    byte ptr [rdi+10h], 8
0x140073c63  jnz     loc_140073D8B
0x140073c69  mov     rdx, [rdi+28h]
0x140073c6d  test    rdx, rdx
0x140073c70  jz      short loc_140073C08
0x140073c72  cmp     word ptr [rdi+0Ch], 1
0x140073c77  jz      short loc_140073C08
0x140073c79  mov     byte ptr [rsp+88h+var_60], 0
0x140073c7e  mov     r9b, 1
0x140073c81  mov     r8, rdi
0x140073c84  mov     byte ptr [rsp+88h+var_68], 1
0x140073c89  mov     rcx, rbx
0x140073c8c  call    Smb2VerifySessionExEx
0x140073c91  mov     edi, eax
0x140073c93  test    eax, eax
0x140073c95  jns     loc_140073C08
0x140073c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ca2  cmp     rcx, r12
0x140073ca5  jnz     loc_14007442B
0x140073cab  mov     r9d, 3D8h
0x140073cb1  jmp     short loc_140073CC9
0x140073cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140073cba  cmp     rcx, r12
0x140073cbd  jnz     loc_14007423C
0x140073cc3  mov     r9d, 33Eh
0x140073cc9  mov     edx, edi
0x140073ccb  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140073cd2  mov     rcx, rbx
0x140073cd5  call    _Smb2SetError
0x140073cda  xor     eax, eax
0x140073cdc  jmp     loc_140073C43
0x140073ce1  mov     r8d, [rbx+194h]
0x140073ce8  cmp     r8d, 11000h
0x140073cef  jbe     loc_140073B77
0x140073cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140073cfc  cmp     rcx, r12
0x140073cff  jnz     loc_1400741A4
0x140073d05  mov     edx, 7
0x140073d0a  mov     byte ptr [rbx+1DAh], 1
0x140073d11  mov     rcx, rsi
0x140073d14  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073d19  mov     eax, 0C000000Dh
0x140073d1e  jmp     loc_140073C43
0x140073d23  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d2a  lea     r12, WPP_GLOBAL_Control
0x140073d31  cmp     rcx, r12
0x140073d34  jnz     loc_14007401F
0x140073d3a  xor     edx, edx
0x140073d3c  mov     byte ptr [rbx+1DAh], 1
0x140073d43  mov     rcx, rsi
0x140073d46  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073d4b  mov     eax, 0C000000Dh
0x140073d50  add     rsp, 60h
0x140073d54  pop     r12
0x140073d56  pop     rdi
0x140073d57  pop     rsi
0x140073d58  pop     rbp
0x140073d59  pop     rbx
0x140073d5a  retn
0x140073d5c  cmp     eax, 424D53FFh
0x140073d61  jnz     loc_140073E96
0x140073d67  mov     eax, 0FFFFh
0x140073d6c  cmp     [rbp+2Ch], ax
0x140073d70  jnz     loc_140073E96
0x140073d76  xor     eax, eax
0x140073d78  mov     [rsi+0Eh], ax
0x140073d7c  jmp     loc_140073C23
0x140073d81  call    Smb2ValidateNotImplemented
0x140073d86  jmp     loc_140073C43
0x140073d8b  cmp     qword ptr [rbp+8], 0
0x140073d90  jz      loc_140074270
0x140073d96  cmp     word ptr [rdi+0Ch], 1
0x140073d9b  jnz     loc_140073ECB
0x140073da1  mov     rax, [rbx+130h]
0x140073da8  mov     r8d, [rax+24h]
0x140073dac  cmp     r8d, 58h ; 'X'
0x140073db0  jb      loc_1400742B5
0x140073db6  test    byte ptr [rdi+42h], 1
0x140073dba  jz      loc_140073ECB
0x140073dc0  mov     al, 1
0x140073dc2  mov     rdx, [rdi+28h]
0x140073dc6  mov     r9b, 1
0x140073dc9  mov     byte ptr [rsp+88h+var_60], al
0x140073dcd  mov     r8, rdi
0x140073dd0  mov     rcx, rbx
0x140073dd3  mov     byte ptr [rsp+88h+var_68], 0
0x140073dd8  call    Smb2VerifySessionExEx
0x140073ddd  mov     ebp, eax
0x140073ddf  test    eax, eax
0x140073de1  js      loc_1400742FF
0x140073de7  cmp     qword ptr [rsi+70h], 0
0x140073dec  jz      loc_140074344
0x140073df2  movups  xmm0, xmmword ptr [rdi+30h]
0x140073df6  mov     ebp, 1
0x140073dfb  xorps   xmm1, xmm1
0x140073dfe  movups  xmmword ptr [rdi+30h], xmm1
0x140073e02  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140073e07  cmp     bp, [rdi+0Ch]
0x140073e0b  jz      loc_140074389
0x140073e11  movzx   r14d, bpl
0x140073e15  lea     rdx, [rsp+88h+DestinationString]
0x140073e1a  mov     rcx, rbx
0x140073e1d  call    Smb2VerifySignature
0x140073e22  mov     r15d, eax
0x140073e25  movups  xmm0, xmmword ptr [rsp+88h+DestinationString.Length]
0x140073e2a  movups  xmmword ptr [rdi+30h], xmm0
0x140073e2e  test    eax, eax
0x140073e30  js      loc_140073F07
0x140073e36  lea     rax, Smb2SignPacket
0x140073e3d  mov     [rbx+218h], rax
0x140073e44  mov     [rsi+8], ebp
0x140073e47  jmp     loc_140073C08
0x140073e4c  call    cs:__imp_SrvAdminAllowAnonymousAccess
0x140073e53  nop     dword ptr [rax+rax+00h]
0x140073e58  test    al, al
0x140073e5a  jnz     loc_140073B1E
0x140073e60  cmp     word ptr [rdi+0Ch], 2
0x140073e65  jb      loc_140073B1E
0x140073e6b  cmp     cs:Microsoft_Windows_SMBServerEnableBits, al
0x140073e71  jge     loc_140096786
0x140073e77  mov     rcx, [rsi+20h]
0x140073e7b  xor     eax, eax
0x140073e7d  test    rcx, rcx
0x140073e80  lea     rsi, [rcx+48h]
0x140073e84  cmovz   rsi, rax
0x140073e88  jz      loc_140096724
0x140073e8e  mov     rbp, [rcx]
0x140073e91  jmp     loc_140096726
0x140073e96  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e9d  lea     r12, WPP_GLOBAL_Control
0x140073ea4  cmp     rcx, r12
0x140073ea7  jnz     loc_140074053
0x140073ead  mov     edx, 1
0x140073eb2  mov     byte ptr [rbx+1DAh], 1
0x140073eb9  mov     rcx, rsi
0x140073ebc  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073ec1  mov     eax, 0C000000Dh
0x140073ec6  jmp     loc_140073C43
0x140073ecb  xor     al, al
0x140073ecd  jmp     loc_140073DC2
0x140073ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ed9  lea     r12, WPP_GLOBAL_Control
0x140073ee0  cmp     rcx, r12
0x140073ee3  jnz     loc_140074087
0x140073ee9  mov     edx, 2
0x140073eee  mov     byte ptr [rbx+1DAh], 1
0x140073ef5  mov     rcx, rsi
0x140073ef8  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073efd  mov     eax, 0C000000Dh
0x140073f02  jmp     loc_140073C43
0x140073f07  xor     eax, eax
0x140073f09  mov     qword ptr [rsp+88h+DestinationString.Length], rax
0x140073f0e  mov     [rsp+88h+DestinationString.Buffer], rax
0x140073f13  mov     [rsp+88h+pBuffer], rax
0x140073f1b  mov     rax, [rsi+30h]
0x140073f1f  test    rax, rax
0x140073f22  jz      short loc_140073F51
0x140073f24  cmp     qword ptr [rax+20h], 0
0x140073f29  lea     rcx, [rax+20h]; phContext
0x140073f2d  jz      loc_14007439B
0x140073f33  lea     r8, [rsp+88h+pBuffer]; pBuffer
0x140073f3b  mov     edx, ebp; ulAttribute
0x140073f3d  call    cs:__imp_QueryContextAttributesW
0x140073f44  nop     dword ptr [rax+rax+00h]
0x140073f49  test    eax, eax
0x140073f4b  jns     loc_1400743AB
0x140073f51  xorps   xmm0, xmm0
0x140073f54  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140073f59  test    r14b, r14b
0x140073f5c  jnz     loc_1400743D5
0x140073f62  mov     rcx, [rsp+88h+pBuffer]; pvContextBuffer
0x140073f6a  test    rcx, rcx
0x140073f6d  jnz     loc_14007441A
0x140073f73  mov     r9d, 3C3h
0x140073f79  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140073f80  mov     edx, r15d
0x140073f83  mov     rcx, rbx
0x140073f86  call    _Smb2SetError
0x140073f8b  xor     eax, eax
0x140073f8d  jmp     loc_140073C43
0x140073f92  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f99  cmp     rcx, r12
0x140073f9c  jnz     loc_140074170
0x140073fa2  mov     edx, 5
  ... truncated ...
```
