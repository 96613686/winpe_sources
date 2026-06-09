# Int_FWAddOrSetObject

- ea: `0x18001494c`
- end: `0x180015565`
- name: `Int_FWAddOrSetObject`
- size: `3097`
- prototype: `__int64 __fastcall(unsigned int, int, __int64 (__fastcall *)(_QWORD, __int128 *), _QWORD *, _QWORD *, unsigned __int16 *, _OWORD *Src)`
- caller_count: `10`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800140b0`
- `0x180014690`
- `0x18004a970`
- `0x18004ab00`
- `0x18004aca0`
- `0x18004b130`
- `0x18004fcd0`
- `0x18004fe60`
- `0x18004fff0`
- `0x180050b90`

## callees

- `0x180005954`
- `0x18001494c`
- `0x18001556c`
- `0x180024c3c`
- `0x18002514c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x1800516bc`
- `0x180051710`
- `0x180051cc0`
- `0x18005b698`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b99a`
- `RPCRT4!RpcExceptionFilter` at `0x18005b99a`
- `fwbase!Int_FwValidateComplianceAndReduceFirewallRuleToVersion` at `0x180014dd0`
- `fwbase!Int_FwValidateComplianceAndReduceCryptoSetToVersion` at `0x180014eb4`
- `fwbase!Int_FwValidateComplianceAndReduceAuthSetToVersion` at `0x180014fdf`
- `fwbase!Int_FwValidateComplianceAndReduceMainModeRuleToVersion` at `0x180014ab5`
- `fwbase!Int_FwValidateComplianceAndReduceConnSecRuleToVersion` at `0x18001504a`
- `fwbase!FwHResultToWindowsError` at `0x180014eeb`
- `fwbase!FwHResultToWindowsError` at `0x180015206`
- `fwbase!FwHResultToWindowsError` at `0x180015277`
- `fwbase!FwHResultToWindowsError` at `0x180014eeb`
- `fwbase!FwHResultToWindowsError` at `0x180015206`
- `fwbase!FwHResultToWindowsError` at `0x180015277`
- `FWPolicyIOMgr!FwAddRule` at `0x18001524c`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x180014aae`
- `FWPolicyIOMgr!FwCopyRule` at `0x180014dc9`
- `FWPolicyIOMgr!FwSetRule` at `0x180015241`
- `FWPolicyIOMgr!FwSetSet` at `0x1800151cf`
- `FWPolicyIOMgr!FwFreeRules` at `0x180015506`
- `FWPolicyIOMgr!FwFreeRules` at `0x180015506`
- `FWPolicyIOMgr!FwAddSet` at `0x1800151da`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x180014ee3`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x180014ee3`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800153c1`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800153d1`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800153c1`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800153d1`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180015431`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180015431`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x180015043`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x180014ead`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Int_FWAddOrSetObject(
        unsigned int a1,
        int a2,
        __int64 (__fastcall *a3)(_QWORD, __int128 *),
        _QWORD *a4,
        _QWORD *a5,
        unsigned __int16 *a6,
        _OWORD *Src)
{
  FwPolicy2 *v8; // rbx
  __int128 *v9; // rax
  __int128 *v10; // rcx
  __int64 v11; // rdx
  size_t v12; // rbx
  __int64 v13; // r13
  unsigned int SvrCompatibleObject; // esi
  _QWORD *v15; // r10
  unsigned int v16; // edx
  unsigned int v17; // ecx
  __int128 *v18; // r8
  __int64 v19; // rdx
  unsigned __int16 *v20; // r8
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // xmm1_8
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(_QWORD, bool, _QWORD, __int128 *); // rax
  unsigned int v28; // eax
  __int64 (__fastcall *v29)(_QWORD, __int64, __int128 *); // rax
  __int64 v30; // rdx
  unsigned int v31; // eax
  int v32; // ecx
  int v33; // eax
  __int64 v34; // rdx
  __int128 *v35; // rcx
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  __int64 v40; // rdx
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  unsigned __int16 *v46; // [rsp+48h] [rbp-2C0h]
  _DWORD v48[2]; // [rsp+60h] [rbp-2A8h] BYREF
  _QWORD *v49; // [rsp+68h] [rbp-2A0h]
  unsigned __int16 *v50; // [rsp+70h] [rbp-298h]
  _OWORD *v51; // [rsp+80h] [rbp-288h]
  __int64 (__fastcall *v52)(_QWORD, __int128 *); // [rsp+88h] [rbp-280h]
  _QWORD *v53; // [rsp+90h] [rbp-278h]
  __int128 *v54; // [rsp+98h] [rbp-270h] BYREF
  __int128 *v55; // [rsp+A0h] [rbp-268h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-258h] BYREF
  __int128 v57; // [rsp+C0h] [rbp-248h]
  __int128 v58; // [rsp+D0h] [rbp-238h]
  __int128 v59; // [rsp+E0h] [rbp-228h]
  __int128 v60; // [rsp+F0h] [rbp-218h]
  __int64 v61; // [rsp+100h] [rbp-208h]
  __int64 v62; // [rsp+108h] [rbp-200h]
  __int64 v63; // [rsp+1A8h] [rbp-160h]
  int v64; // [rsp+1B0h] [rbp-158h]
  int v65; // [rsp+200h] [rbp-108h]
  __int64 v66; // [rsp+208h] [rbp-100h]
  __int64 v67; // [rsp+228h] [rbp-E0h]
  int v68; // [rsp+230h] [rbp-D8h]
  int v69; // [rsp+2C0h] [rbp-48h] BYREF

  v53 = a4;
  v52 = a3;
  v49 = a5;
  v51 = Src;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v54 = 0;
  v69 = 0x10000;
  v55 = 0;
  v48[0] = 0;
  *(_QWORD *)&v56 = 0;
  memset_0((char *)&v56 + 8, 0, 0x200u);
  if ( !a6 || !Src )
  {
    v20 = 0;
    v46 = 0;
    SvrCompatibleObject = 87;
    if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 301, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
      v8 = WPP_GLOBAL_Control;
      v20 = 0;
    }
    goto LABEL_38;
  }
  v46 = a6;
  v50 = a6;
  switch ( a1 )
  {
    case 0u:
      if ( *a6 >= 0x20Au )
      {
        if ( *a6 >= 0x214u )
        {
          if ( *a6 >= 0x218u )
          {
            if ( *a6 >= 0x219u )
            {
              if ( *a6 >= 0x21Au )
              {
                if ( *a6 >= 0x21Bu )
                {
                  if ( *a6 >= 0x21Fu )
                  {
                    v12 = 504;
                    if ( *a6 < 0x221u )
                      v12 = 496;
                  }
                  else
                  {
                    v12 = 464;
                  }
                }
                else
                {
                  v12 = 448;
                }
              }
              else
              {
                v12 = 432;
              }
            }
            else
            {
              v12 = 424;
            }
          }
          else
          {
            v12 = 400;
          }
        }
        else
        {
          v12 = 368;
        }
      }
      else
      {
        v12 = 360;
      }
      memset_0(&v56, 0, 0x1F8u);
      memcpy_0(&v56, Src, v12);
      v66 = 0;
      LODWORD(v12) = (_DWORD)FwCopyRule;
      v13 = Int_FwValidateComplianceAndReduceFirewallRuleToVersion;
      goto LABEL_10;
    case 1u:
      if ( *a6 >= 0x20Au )
        v12 = (-(__int64)(*a6 < 0x214u) & 0xFFFFFFFFFFFFFF98uLL) + 520;
      else
        v12 = 392;
      memset_0(&v56, 0, 0x208u);
      memcpy_0(&v56, Src, v12);
      v67 = 0;
      LODWORD(v12) = FwCopyCSRule;
      v13 = Int_FwValidateComplianceAndReduceConnSecRuleToVersion;
      goto LABEL_10;
    case 2u:
      v9 = Src;
      v10 = &v56;
      v11 = 2;
      do
      {
        *v10 = *v9;
        v10[1] = v9[1];
        v10[2] = v9[2];
        v10[3] = v9[3];
        v10[4] = v9[4];
        v10[5] = v9[5];
        v10[6] = v9[6];
        v10[7] = v9[7];
        v10 += 8;
        v9 += 8;
        --v11;
      }
      while ( v11 );
      *v10 = *v9;
      v63 = 0;
      LODWORD(v12) = FwCopyMMRule;
      v13 = Int_FwValidateComplianceAndReduceMainModeRuleToVersion;
      goto LABEL_10;
    case 3u:
      if ( *a6 >= 0x214u )
      {
        v56 = *Src;
        v57 = Src[1];
        v58 = Src[2];
        v59 = Src[3];
        v60 = Src[4];
        v24 = *((_QWORD *)Src + 10);
      }
      else
      {
        v23 = FwCopyAuthsetToHigherVersion(522, Src, &v55);
        SvrCompatibleObject = FwHResultToWindowsError(v23);
        if ( SvrCompatibleObject )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              302,
              WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
              SvrCompatibleObject);
            v8 = WPP_GLOBAL_Control;
          }
          v20 = a6;
          goto LABEL_38;
        }
        v56 = *v55;
        v57 = v55[1];
        v58 = v55[2];
        v59 = v55[3];
        v60 = v55[4];
        v24 = *((_QWORD *)v55 + 10);
      }
      v61 = v24;
      *((_QWORD *)&v60 + 1) = 0;
      v12 = (size_t)FwCopyAuthSet;
      v13 = Int_FwValidateComplianceAndReduceAuthSetToVersion;
      goto LABEL_10;
    case 4u:
      v56 = *Src;
      v57 = Src[1];
      v58 = Src[2];
      v59 = Src[3];
      v60 = Src[4];
      v62 = *((_QWORD *)Src + 11);
      v61 = 0;
      LODWORD(v12) = FwCopyCryptoSet;
      v13 = Int_FwValidateComplianceAndReduceCryptoSetToVersion;
LABEL_10:
      *(_QWORD *)&v56 = 0;
      goto LABEL_11;
  }
  LODWORD(v12) = 0;
  v13 = 0;
  MicrosoftTelemetryAssertTriggeredArgs(a1 - 3, a1);
LABEL_11:
  SvrCompatibleObject = v52(*a6, &v56);
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 303;
    goto LABEL_82;
  }
  if ( *((_DWORD *)a6 + 1) > 1u )
  {
    if ( *((_DWORD *)a6 + 1) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    SvrCompatibleObject = Int_FWOpenGPOPolicyStore(a6);
    if ( SvrCompatibleObject )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 309;
      goto LABEL_82;
    }
    if ( !*((_QWORD *)a6 + 7) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a1 <= 2 )
    {
      v29 = (__int64 (__fastcall *)(_QWORD, __int64, __int128 *))FwSetRule;
      if ( a2 )
        v29 = (__int64 (__fastcall *)(_QWORD, __int64, __int128 *))FwAddRule;
      v30 = 0;
      if ( a1 )
      {
        LOBYTE(v30) = a1 != 1;
        v30 = (unsigned int)(v30 + 1);
      }
      v31 = v29(*((_QWORD *)a6 + 7), v30, &v56);
      SvrCompatibleObject = FwHResultToWindowsError(v31);
      if ( !SvrCompatibleObject )
        goto LABEL_96;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 310;
    }
    else
    {
      v26 = a1 - 3;
      if ( (unsigned int)v26 >= 2 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(v26, a1);
LABEL_96:
        SvrCompatibleObject = Int_FWCloseGPOPolicyStore(a6, 1);
        if ( !SvrCompatibleObject )
          goto LABEL_84;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v22 = 312;
        goto LABEL_82;
      }
      v27 = (__int64 (__fastcall *)(_QWORD, bool, _QWORD, __int128 *))FwSetSet;
      if ( a2 )
        v27 = (__int64 (__fastcall *)(_QWORD, bool, _QWORD, __int128 *))FwAddSet;
      v28 = v27(*((_QWORD *)a6 + 7), a1 != 3, HIDWORD(v56), &v56);
      SvrCompatibleObject = FwHResultToWindowsError(v28);
      if ( !SvrCompatibleObject )
        goto LABEL_96;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 311;
    }
LABEL_82:
    v25 = SvrCompatibleObject;
LABEL_83:
    WPP_SF_d(*((_QWORD *)v8 + 2), v22, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v25);
LABEL_84:
    v8 = WPP_GLOBAL_Control;
LABEL_37:
    v20 = a6;
LABEL_38:
    v19 = a1;
    goto LABEL_32;
  }
  if ( !*((_QWORD *)a6 + 4) || !*((_QWORD *)a6 + 5) )
  {
    v25 = 87;
    SvrCompatibleObject = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 304;
    goto LABEL_83;
  }
  v15 = v53;
  if ( *((_DWORD *)a6 + 1) )
    v15 = v49;
  v16 = *(_DWORD *)v15;
  if ( *(_DWORD *)v15 )
  {
    v17 = 0;
    do
    {
      if ( *(_WORD *)(v15[1] + 16LL * v17 + 8) > a6[1] )
        break;
      v16 = v17++;
    }
    while ( v17 < *(_DWORD *)v15 );
  }
  if ( v16 == *(_DWORD *)v15 || (v49 = *(_QWORD **)(v15[1] + 16LL * v16)) == 0 )
  {
    SvrCompatibleObject = 50;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 305;
    goto LABEL_82;
  }
  SvrCompatibleObject = Int_FwMakeSvrCompatibleObject(
                          (unsigned int)&v56,
                          (unsigned int)&v54,
                          a6[24],
                          v12,
                          v13,
                          a6[1],
                          a1,
                          (__int64)v48);
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 306;
    goto LABEL_82;
  }
  v18 = &v56;
  if ( v54 )
    v18 = v54;
  SvrCompatibleObject = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *, int *))v49)(
                          *((_QWORD *)a6 + 4),
                          *((_QWORD *)a6 + 5),
                          v18,
                          &v69);
  v48[1] = SvrCompatibleObject;
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        307,
        WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
        SvrCompatibleObject);
      v8 = WPP_GLOBAL_Control;
    }
    v19 = a1;
    v20 = a6;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    v19 = a1;
    v20 = a6;
  }
LABEL_32:
  if ( a6 && Src )
  {
    if ( (_DWORD)v19 )
    {
      if ( (_DWORD)v19 == 1 )
      {
        v41 = v69;
        v42 = v69;
        if ( v69 == 0x10000 )
          v42 = v68;
        *((_DWORD *)Src + 96) = v42;
        if ( !v54 )
          goto LABEL_167;
        if ( v41 == 0x10000 )
          *((_DWORD *)Src + 96) = 0x20000;
        v40 = 1;
      }
      else
      {
        if ( (_DWORD)v19 != 2 )
        {
          if ( (_DWORD)v19 == 3 )
          {
            v36 = v69;
            v37 = v69;
            if ( v69 == 0x10000 )
              v37 = v61;
            *((_DWORD *)Src + 20) = v37;
            if ( v54 )
            {
              if ( v36 == 0x10000 && (v20[1] >= 0x214u || v48[0] == 1) )
                *((_DWORD *)Src + 20) = 0x20000;
              if ( v20[1] >= 0x214u )
                FwFreeSets(v54, 0);
              else
                FwDownlevelAuthSetFree(522, v54);
            }
            v34 = 0;
            v35 = v55;
          }
          else
          {
            if ( (_DWORD)v19 != 4 )
            {
              MicrosoftTelemetryAssertTriggeredArgs((unsigned int)(v19 - 3), v19);
LABEL_167:
              v8 = WPP_GLOBAL_Control;
              goto LABEL_33;
            }
            v32 = v69;
            v33 = v69;
            if ( v69 == 0x10000 )
              v33 = v62;
            *((_DWORD *)Src + 22) = v33;
            if ( !v54 )
              goto LABEL_167;
            if ( v32 == 0x10000 )
              *((_DWORD *)Src + 22) = 0x20000;
            v34 = 1;
            v35 = v54;
          }
          FwFreeSets(v35, v34);
          goto LABEL_167;
        }
        v38 = v69;
        v39 = v69;
        if ( v69 == 0x10000 )
          v39 = v64;
        *((_DWORD *)Src + 64) = v39;
        if ( !v54 )
          goto LABEL_167;
        if ( v38 == 0x10000 )
          *((_DWORD *)Src + 64) = 0x20000;
        v40 = 2;
      }
    }
    else
    {
      v43 = v69;
      v44 = v69;
      if ( v69 == 0x10000 )
        v44 = v65;
      *((_DWORD *)Src + 84) = v44;
      if ( !v54 )
        goto LABEL_167;
      if ( v43 == 0x10000 )
        *((_DWORD *)Src + 84) = 0x20000;
      v40 = 0;
    }
    FwFreeRules(v54, v40, v20);
    goto LABEL_167;
  }
LABEL_33:
  if ( SvrCompatibleObject && v46 && *((_DWORD *)v46 + 1) == 2 )
  {
    Int_FWCleanupGPOPolicyStore(v46, v19, v20);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v8 + 2), 313, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  return SvrCompatibleObject;
}

```

## disassembly

```asm
0x18001494c  push    rbx
0x18001494e  push    rsi
0x18001494f  push    rdi
0x180014950  push    r12
0x180014952  push    r13
0x180014954  push    r14
0x180014956  push    r15
0x180014958  sub     rsp, 2D0h
0x18001495f  mov     rax, cs:__security_cookie
0x180014966  xor     rax, rsp
0x180014969  mov     [rsp+308h+var_40], rax
0x180014971  mov     [rsp+308h+var_278], r9
0x180014979  mov     [rsp+308h+var_280], r8
0x180014981  mov     [rsp+308h+var_2B8], edx
0x180014985  mov     esi, ecx
0x180014987  mov     [rsp+308h+var_2C8], ecx
0x18001498b  mov     rax, [rsp+308h+arg_20]
0x180014993  mov     [rsp+308h+var_2A0], rax
0x180014998  mov     r15, [rsp+308h+arg_28]
0x1800149a0  mov     r14, [rsp+308h+Src]
0x1800149a8  mov     [rsp+308h+var_2B0], ecx
0x1800149ac  mov     [rsp+308h+var_288], r14
0x1800149b4  lea     r12, WPP_GLOBAL_Control
0x1800149bb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800149c2  cmp     rbx, r12
0x1800149c5  jnz     loc_180014E07
0x1800149cb  xor     edi, edi
0x1800149cd  mov     [rsp+308h+var_270], rdi
0x1800149d5  mov     [rsp+308h+var_48], 10000h
0x1800149e0  mov     [rsp+308h+var_268], rdi
0x1800149e8  mov     [rsp+308h+var_2A8], edi
0x1800149ec  mov     qword ptr [rsp+308h+var_258], rdi
0x1800149f4  xor     edx, edx; Val
0x1800149f6  mov     r8d, 200h; Size
0x1800149fc  lea     rcx, [rsp+308h+var_258+8]; void *
0x180014a04  call    memset_0
0x180014a09  test    r15, r15
0x180014a0c  jz      loc_1800152F0
0x180014a12  test    r14, r14
0x180014a15  jz      loc_1800152F0
0x180014a1b  mov     rcx, r15
0x180014a1e  mov     [rsp+308h+var_2C0], rcx
0x180014a23  mov     [rsp+308h+var_298], rcx
0x180014a28  mov     ecx, esi
0x180014a2a  test    esi, esi
0x180014a2c  jz      loc_180014D81
0x180014a32  sub     ecx, 1
0x180014a35  jz      loc_180014FEB
0x180014a3b  sub     ecx, 1
0x180014a3e  jnz     loc_180014E32
0x180014a44  mov     rax, r14
0x180014a47  lea     rcx, [rsp+308h+var_258]
0x180014a4f  lea     edx, [rdi+2]
0x180014a52  lea     r8d, [rdx+7Eh]
0x180014a56  movups  xmm0, xmmword ptr [rax]
0x180014a59  movups  xmmword ptr [rcx], xmm0
0x180014a5c  movups  xmm1, xmmword ptr [rax+10h]
0x180014a60  movups  xmmword ptr [rcx+10h], xmm1
0x180014a64  movups  xmm0, xmmword ptr [rax+20h]
0x180014a68  movups  xmmword ptr [rcx+20h], xmm0
0x180014a6c  movups  xmm1, xmmword ptr [rax+30h]
0x180014a70  movups  xmmword ptr [rcx+30h], xmm1
0x180014a74  movups  xmm0, xmmword ptr [rax+40h]
0x180014a78  movups  xmmword ptr [rcx+40h], xmm0
0x180014a7c  movups  xmm1, xmmword ptr [rax+50h]
0x180014a80  movups  xmmword ptr [rcx+50h], xmm1
0x180014a84  movups  xmm0, xmmword ptr [rax+60h]
0x180014a88  movups  xmmword ptr [rcx+60h], xmm0
0x180014a8c  movups  xmm1, xmmword ptr [rax+70h]
0x180014a90  movups  xmmword ptr [rcx+70h], xmm1
0x180014a94  add     rcx, r8
0x180014a97  add     rax, r8
0x180014a9a  sub     rdx, 1
0x180014a9e  jnz     short loc_180014A56
0x180014aa0  movups  xmm0, xmmword ptr [rax]
0x180014aa3  movups  xmmword ptr [rcx], xmm0
0x180014aa6  mov     [rsp+308h+var_160], rdi
0x180014aae  mov     rbx, cs:__imp_FwCopyMMRule
0x180014ab5  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceMainModeRuleToVersion
0x180014abc  mov     r12d, 214h
0x180014ac2  mov     qword ptr [rsp+308h+var_258], rdi
0x180014aca  lea     rdx, [rsp+308h+var_258]
0x180014ad2  movzx   ecx, word ptr [r15]
0x180014ad6  mov     rax, [rsp+308h+var_280]
0x180014ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae3  mov     esi, eax
0x180014ae5  test    eax, eax
0x180014ae7  jnz     loc_180014DDC
0x180014aed  cmp     dword ptr [r15+4], 1
0x180014af2  ja      loc_180015109
0x180014af8  cmp     [r15+20h], rdi
0x180014afc  jz      loc_1800152C1
0x180014b02  cmp     [r15+28h], rdi
0x180014b06  jz      loc_1800152C1
0x180014b0c  cmp     [r15+4], edi
0x180014b10  mov     r10, [rsp+308h+var_278]
0x180014b18  cmovnz  r10, [rsp+308h+var_2A0]
0x180014b1e  mov     edx, [r10]
0x180014b21  test    edx, edx
0x180014b23  jz      short loc_180014B46
0x180014b25  mov     ecx, edi
0x180014b27  movzx   r8d, word ptr [r15+2]
0x180014b2c  mov     r9, [r10+8]
0x180014b30  mov     eax, ecx
0x180014b32  add     rax, rax
0x180014b35  cmp     [r9+rax*8+8], r8w
0x180014b3b  ja      short loc_180014B46
0x180014b3d  mov     edx, ecx
0x180014b3f  inc     ecx
0x180014b41  cmp     ecx, [r10]
0x180014b44  jb      short loc_180014B30
0x180014b46  cmp     edx, [r10]
0x180014b49  jz      loc_180014D33
0x180014b4f  mov     ecx, edx
0x180014b51  add     rcx, rcx
0x180014b54  mov     rax, [r10+8]
0x180014b58  mov     rax, [rax+rcx*8]
0x180014b5c  mov     [rsp+308h+var_2A0], rax
0x180014b61  test    rax, rax
0x180014b64  jz      loc_180014D33
0x180014b6a  lea     rax, [rsp+308h+var_2A8]
0x180014b6f  mov     [rsp+308h+var_2D0], rax
0x180014b74  mov     eax, [rsp+308h+var_2C8]
0x180014b78  mov     [rsp+308h+var_2D8], eax
0x180014b7c  movzx   eax, word ptr [r15+2]
0x180014b81  mov     [rsp+308h+var_2E0], ax
0x180014b86  mov     [rsp+308h+var_2E8], r13
0x180014b8b  mov     r9, rbx
0x180014b8e  movzx   r8d, word ptr [r15+30h]
0x180014b93  lea     rdx, [rsp+308h+var_270]
0x180014b9b  lea     rcx, [rsp+308h+var_258]
0x180014ba3  call    Int_FwMakeSvrCompatibleObject
0x180014ba8  mov     esi, eax
0x180014baa  test    eax, eax
0x180014bac  jnz     loc_180014D5E
0x180014bb2  lea     r8, [rsp+308h+var_258]
0x180014bba  cmp     [rsp+308h+var_270], rdi
0x180014bc2  cmovnz  r8, [rsp+308h+var_270]
0x180014bcb  lea     r9, [rsp+308h+var_48]
0x180014bd3  mov     rdx, [r15+28h]
0x180014bd7  mov     rcx, [r15+20h]
0x180014bdb  mov     rax, [rsp+308h+var_2A0]
0x180014be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014be5  mov     esi, eax
0x180014be7  mov     [rsp+308h+var_2A4], eax
0x180014beb  test    eax, eax
0x180014bed  jz      short loc_180014C3B
0x180014bef  mov     rbx, cs:WPP_GLOBAL_Control
0x180014bf6  lea     rax, WPP_GLOBAL_Control
0x180014bfd  cmp     rbx, rax
0x180014c00  jz      short loc_180014C27
0x180014c02  test    byte ptr [rbx+1Ch], 1
0x180014c06  jz      short loc_180014C27
0x180014c08  mov     edx, 133h
0x180014c0d  mov     r9d, esi
0x180014c10  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014c17  mov     rcx, [rbx+10h]
0x180014c1b  call    WPP_SF_d
0x180014c20  mov     rbx, cs:WPP_GLOBAL_Control
0x180014c27  mov     r13d, 20Ah
0x180014c2d  mov     edx, [rsp+308h+var_2C8]
0x180014c31  mov     r8, [rsp+308h+var_2C0]
0x180014c36  jmp     loc_180014CED
0x180014c3b  mov     rbx, cs:WPP_GLOBAL_Control
0x180014c42  mov     r13d, 20Ah
0x180014c48  mov     edx, [rsp+308h+var_2C8]
0x180014c4c  mov     r8, [rsp+308h+var_2C0]
0x180014c51  jmp     loc_180014CED
0x180014c56  mov     esi, eax
0x180014c58  mov     [rsp+308h+var_2A4], eax
0x180014c5c  test    eax, eax
0x180014c5e  jz      short loc_180014CC0
0x180014c60  lea     rax, WPP_GLOBAL_Control
0x180014c67  mov     rbx, cs:WPP_GLOBAL_Control
0x180014c6e  cmp     rbx, rax
0x180014c71  jz      short loc_180014C98
0x180014c73  test    byte ptr [rbx+1Ch], 1
0x180014c77  jz      short loc_180014C98
0x180014c79  mov     edx, 134h
0x180014c7e  mov     r9d, esi
0x180014c81  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014c88  mov     rcx, [rbx+10h]
0x180014c8c  call    WPP_SF_d
0x180014c91  mov     rbx, cs:WPP_GLOBAL_Control
0x180014c98  xor     edi, edi
0x180014c9a  mov     r12d, 214h
0x180014ca0  lea     r13d, [r12-0Ah]
0x180014ca5  mov     r8, [rsp+308h+var_298]
0x180014caa  mov     [rsp+308h+var_2C0], r8
0x180014caf  mov     edx, [rsp+308h+var_2B0]
0x180014cb3  mov     r15, r8
0x180014cb6  mov     r14, [rsp+308h+var_288]
0x180014cbe  jmp     short loc_180014CED
0x180014cc0  xor     edi, edi
0x180014cc2  mov     r12d, 214h
0x180014cc8  lea     r13d, [r12-0Ah]
0x180014ccd  mov     r8, [rsp+308h+var_298]
0x180014cd2  mov     [rsp+308h+var_2C0], r8
0x180014cd7  mov     rbx, cs:WPP_GLOBAL_Control
0x180014cde  mov     edx, [rsp+308h+var_2B0]
0x180014ce2  mov     r15, r8
0x180014ce5  mov     r14, [rsp+308h+var_288]
0x180014ced  test    r15, r15
0x180014cf0  jnz     loc_180015336
0x180014cf6  test    esi, esi
0x180014cf8  jnz     loc_180015518
0x180014cfe  lea     rax, WPP_GLOBAL_Control
0x180014d05  cmp     rbx, rax
0x180014d08  jnz     loc_180015541
0x180014d0e  mov     eax, esi
0x180014d10  mov     rcx, [rsp+308h+var_40]
0x180014d18  xor     rcx, rsp; StackCookie
0x180014d1b  call    __security_check_cookie
0x180014d20  add     rsp, 2D0h
0x180014d27  pop     r15
0x180014d29  pop     r14
0x180014d2b  pop     r13
0x180014d2d  pop     r12
0x180014d2f  pop     rdi
0x180014d30  pop     rsi
0x180014d31  pop     rbx
0x180014d32  retn
0x180014d33  mov     esi, 32h ; '2'
0x180014d38  mov     rbx, cs:WPP_GLOBAL_Control
0x180014d3f  lea     rax, WPP_GLOBAL_Control
0x180014d46  cmp     rbx, rax
0x180014d49  jnz     loc_1800152B2
0x180014d4f  mov     r8, r15
0x180014d52  mov     r13d, 20Ah
0x180014d58  mov     edx, [rsp+308h+var_2C8]
0x180014d5c  jmp     short loc_180014CED
0x180014d5e  mov     rbx, cs:WPP_GLOBAL_Control
0x180014d65  lea     rax, WPP_GLOBAL_Control
0x180014d6c  cmp     rbx, rax
0x180014d6f  jz      short loc_180014D4F
0x180014d71  test    byte ptr [rbx+1Ch], 1
0x180014d75  jz      short loc_180014D4F
0x180014d77  mov     edx, 132h
0x180014d7c  jmp     loc_1800150E3
0x180014d81  mov     eax, 20Ah
0x180014d86  lea     r12d, [rax+0Ah]
0x180014d8a  cmp     [r15], ax
0x180014d8e  jnb     loc_180015056
0x180014d94  mov     ebx, 168h
0x180014d99  xor     edx, edx; Val
0x180014d9b  mov     r8d, 1F8h; Size
0x180014da1  lea     rcx, [rsp+308h+var_258]; void *
0x180014da9  call    memset_0
0x180014dae  mov     r8, rbx; Size
0x180014db1  mov     rdx, r14; Src
0x180014db4  lea     rcx, [rsp+308h+var_258]; void *
0x180014dbc  call    memcpy_0
0x180014dc1  mov     [rsp+308h+var_100], rdi
0x180014dc9  mov     rbx, cs:__imp_FwCopyRule
0x180014dd0  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceFirewallRuleToVersion
0x180014dd7  jmp     loc_180014AC2
0x180014ddc  mov     rbx, cs:WPP_GLOBAL_Control
0x180014de3  lea     rax, WPP_GLOBAL_Control
0x180014dea  cmp     rbx, rax
0x180014ded  jz      loc_180014D4F
0x180014df3  test    byte ptr [rbx+1Ch], 1
0x180014df7  jz      loc_180014D4F
0x180014dfd  mov     edx, 12Fh
0x180014e02  jmp     loc_1800150E3
0x180014e07  test    byte ptr [rbx+1Ch], 8
0x180014e0b  jz      loc_1800149CB
0x180014e11  mov     edx, 12Ch
0x180014e16  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014e1d  mov     rcx, [rbx+10h]
0x180014e21  call    WPP_SF_
0x180014e26  mov     rbx, cs:WPP_GLOBAL_Control
0x180014e2d  jmp     loc_1800149CB
0x180014e32  sub     ecx, 1
0x180014e35  jz      loc_180014EC0
0x180014e3b  cmp     ecx, 1
0x180014e3e  jz      short loc_180014E58
0x180014e40  mov     rbx, rdi
0x180014e43  mov     r13, rdi
0x180014e46  mov     edx, esi
0x180014e48  call    MicrosoftTelemetryAssertTriggeredArgs
0x180014e4d  mov     r12d, 214h
0x180014e53  jmp     loc_180014ACA
0x180014e58  movups  xmm0, xmmword ptr [r14]
0x180014e5c  movaps  [rsp+308h+var_258], xmm0
0x180014e64  movups  xmm1, xmmword ptr [r14+10h]
0x180014e69  movaps  [rsp+308h+var_248], xmm1
0x180014e71  movups  xmm0, xmmword ptr [r14+20h]
0x180014e76  movaps  [rsp+308h+var_238], xmm0
0x180014e7e  movups  xmm1, xmmword ptr [r14+30h]
0x180014e83  movaps  [rsp+308h+var_228], xmm1
0x180014e8b  movups  xmm0, xmmword ptr [r14+40h]
0x180014e90  movaps  [rsp+308h+var_218], xmm0
0x180014e98  movups  xmm1, xmmword ptr [r14+50h]
0x180014e9d  movaps  [rsp+308h+var_208], xmm1
0x180014ea5  mov     qword ptr [rsp+308h+var_208], rdi
0x180014ead  mov     rbx, cs:__imp_FwCopyCryptoSet
0x180014eb4  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceCryptoSetToVersion
0x180014ebb  jmp     loc_180014ABC
0x180014ec0  mov     r12d, 214h
0x180014ec6  cmp     [r15], r12w
  ... truncated ...
```
