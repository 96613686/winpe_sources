# BfeFilterCreate

- ea: `0x180006ed0`
- end: `0x18000794f`
- name: `BfeFilterCreate`
- size: `2687`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005b60`
- `0x180005ba0`
- `0x180005fe0`
- `0x180006584`
- `0x180006ed0`
- `0x180007958`
- `0x18000798c`
- `0x1800079f8`
- `0x180007cd0`
- `0x1800084b0`
- `0x18000ef30`
- `0x18000fb34`
- `0x18000fb90`
- `0x180012d8c`
- `0x1800133a0`
- `0x180013f60`
- `0x1800197d0`
- `0x180022b04`
- `0x1800286b0`
- `0x180033684`
- `0x180039cd4`
- `0x1800592f4`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180006fce`
- `ntdll!RtlLookupEntryHashTable` at `0x1800070a8`
- `ntdll!RtlLookupEntryHashTable` at `0x1800071a1`
- `ntdll!RtlLookupEntryHashTable` at `0x180006fce`
- `ntdll!RtlLookupEntryHashTable` at `0x1800070a8`
- `ntdll!RtlLookupEntryHashTable` at `0x1800071a1`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075c2`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075da`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075f2`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075c2`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075da`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800075f2`

## string_xrefs

- `0x18000740d`: `BfeFilterCreate`
- `0x18000793b`: `BfeFilterCreate`

## pseudocode

```c
__int64 __fastcall BfeFilterCreate(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // r13
  __int64 v4; // r12
  __int64 v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r15
  __int64 i; // rax
  __int64 v12; // r8
  __int64 NameResolutionInfo; // rbx
  __int64 PrivateState; // rsi
  __int64 v15; // r14
  _QWORD *v16; // rbx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // r15
  __int64 j; // rax
  __int64 v21; // r8
  void *v22; // rcx
  __int64 *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r14
  _QWORD *v26; // rbx
  __int64 v27; // rsi
  __int64 v28; // r15
  __int64 v29; // rdx
  __int64 k; // rax
  __int64 v31; // r8
  __int64 *v32; // r14
  __int64 v33; // r9
  _QWORD *v34; // rax
  __int64 v35; // r9
  _QWORD *v36; // rsi
  __int64 v37; // r15
  int v38; // ecx
  int v39; // r8d
  __int64 v40; // r12
  __int64 v41; // r15
  __int64 v42; // rdx
  int v43; // ebx
  _QWORD *v45; // rsi
  _QWORD *v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // rsi
  _QWORD *v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rsi
  _QWORD *Key; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  int v56; // eax
  int v57; // [rsp+40h] [rbp-39h] BYREF
  int v58; // [rsp+48h] [rbp-31h] BYREF
  __int64 v59; // [rsp+50h] [rbp-29h]
  __int64 v60; // [rsp+58h] [rbp-21h] BYREF
  __int64 v61; // [rsp+60h] [rbp-19h] BYREF
  __int128 v62; // [rsp+68h] [rbp-11h] BYREF
  const char *v63; // [rsp+78h] [rbp-1h]
  __int64 v64; // [rsp+80h] [rbp+7h]
  int *v65; // [rsp+88h] [rbp+Fh]
  __int64 v66; // [rsp+90h] [rbp+17h]

  v2 = 0;
  *((_DWORD *)a1 + 6) = -1;
  *((_DWORD *)a1 + 7) = -1;
  *(_OWORD *)(a1 + 5) = 0;
  v4 = 0;
  *a1 = *a2;
  *a2 = 0;
  v5 = *a1;
  v59 = 0;
  v61 = 0;
  v60 = 0;
  *(_DWORD *)(v5 + 32) &= 0xFFFFFF9F;
  v6 = (_QWORD *)*a1;
  v58 = 0;
  if ( (v6[4] & 3) == 0 || !gBfeDb )
    v6[22] = gBfeFilterComponent++;
  if ( (*(_BYTE *)(*a1 + 32LL) & 3) != 0 )
    BfeObjectSetPersistent(a1);
  v7 = *(_QWORD **)(*a1 + 40LL);
  if ( v7 )
  {
    if ( a1 == (_QWORD *)144 || !*(a1 - 18) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    v8 = gBfeObjMgr;
    v63 = 0;
    v62 = 0;
    if ( !*(_DWORD *)gBfeObjMgr )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    v9 = *v7 ^ v7[1];
    if ( !v9 )
      v9 = -1;
    v10 = v8 + 240;
    for ( i = RtlLookupEntryHashTable(v8 + 240, v9, &v62); ; i = RtlGetNextEntryHashTable(v10, &v62) )
    {
      if ( !i )
        goto LABEL_16;
      v51 = (_QWORD *)(i - 16);
      Key = (_QWORD *)BfeObjectGetKey(i - 16);
      v53 = *Key - *v7;
      if ( !v53 )
        v53 = Key[1] - v7[1];
      if ( !v53 && (unsigned int)BfeObjectIsVisible(v51) )
        break;
    }
    BfeObjectIsVisible(v51);
    if ( v51 )
    {
      NameResolutionInfo = BfeObjectAssociate(0, a1 - 18, v51);
      if ( !NameResolutionInfo )
      {
        PrivateState = BfeObjectGetPrivateState(v51);
        v59 = PrivateState;
LABEL_22:
        if ( gBfeDb )
        {
          if ( (*(_BYTE *)(*(_QWORD *)PrivateState + 32LL) & 0x10) != 0 )
          {
            v6 = (_QWORD *)*a1;
            v56 = *(_DWORD *)(*a1 + 32LL);
            if ( (v56 & 2) == 0 )
              *((_DWORD *)v6 + 8) = v56 | 0x20;
          }
        }
        goto LABEL_23;
      }
    }
    else
    {
LABEL_16:
      LODWORD(NameResolutionInfo) = *(_DWORD *)(gBfeObjMgr + 72);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          v12,
          0,
          (__int64)"BfeObjectAssociateByKey",
          *(_DWORD *)(gBfeObjMgr + 72));
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v57 = NameResolutionInfo;
        v65 = &v57;
        v63 = "BfeObjectAssociateByKey";
        v64 = 24;
        v66 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v12,
          3,
          (__int64)&v62);
      }
      if ( (int)NameResolutionInfo > 0 )
        LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
      NameResolutionInfo = (int)NameResolutionInfo;
      v59 = 0;
      PrivateState = 0;
      if ( !(_DWORD)NameResolutionInfo )
        goto LABEL_22;
    }
LABEL_142:
    WfpReportError(NameResolutionInfo, "BfeObjectAssociateByKey");
    goto LABEL_144;
  }
LABEL_23:
  v15 = *a1;
  if ( a1 )
  {
    v16 = a1 - 18;
    if ( a1 != (_QWORD *)144 && *v16 )
      goto LABEL_27;
  }
  else
  {
    v16 = 0;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v6);
LABEL_27:
  v17 = gBfeObjMgr;
  v63 = 0;
  v62 = 0;
  if ( !*(_DWORD *)(gBfeObjMgr + 1224) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v18 = *(_QWORD *)(v15 + 64) ^ *(_QWORD *)(v15 + 72);
  if ( !v18 )
    v18 = -1;
  v19 = v17 + 1464;
  for ( j = RtlLookupEntryHashTable(v17 + 1464, v18, &v62); j; j = RtlGetNextEntryHashTable(v19, &v62) )
  {
    v45 = (_QWORD *)(j - 16);
    v46 = (_QWORD *)BfeObjectGetKey(j - 16);
    v47 = *v46 - *(_QWORD *)(v15 + 64);
    if ( *v46 == *(_QWORD *)(v15 + 64) )
      v47 = v46[1] - *(_QWORD *)(v15 + 72);
    if ( !v47 && (unsigned int)BfeObjectIsVisible(v45) )
    {
      BfeObjectIsVisible(v45);
      if ( v45 )
      {
        NameResolutionInfo = BfeObjectAssociate(0, v16, v45);
        if ( NameResolutionInfo )
          goto LABEL_142;
        if ( a1 != (_QWORD *)-8LL )
          a1[1] = BfeObjectGetPrivateState(v45);
        goto LABEL_39;
      }
      break;
    }
  }
  LODWORD(NameResolutionInfo) = *(_DWORD *)(gBfeObjMgr + 1296);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      v21,
      0,
      (__int64)"BfeObjectAssociateByKey",
      *(_DWORD *)(gBfeObjMgr + 1296));
  }
  if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
  {
    v57 = NameResolutionInfo;
    v65 = &v57;
    v63 = "BfeObjectAssociateByKey";
    v64 = 24;
    v66 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      &MICROSOFT_WFP_PROVIDER_Context,
      (__int64)WFP_USERMODE_ERROR,
      v21,
      3,
      (__int64)&v62);
  }
  if ( (int)NameResolutionInfo > 0 )
    LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
  NameResolutionInfo = (int)NameResolutionInfo;
  if ( (_DWORD)NameResolutionInfo )
    goto LABEL_142;
LABEL_39:
  v23 = (__int64 *)(*a1 + 80LL);
  if ( *a1 == -80 )
    goto LABEL_130;
  v24 = *v23;
  if ( !*v23 )
    v24 = *(_QWORD *)(*a1 + 88LL);
  if ( !v24 )
  {
LABEL_130:
    v55 = a1[1];
    v22 = *(void **)v55;
    *(_OWORD *)v23 = *(_OWORD *)(*(_QWORD *)v55 + 48LL);
  }
  v25 = *a1;
  if ( a1 )
  {
    v26 = a1 - 18;
    if ( a1 != (_QWORD *)144 && *v26 )
      goto LABEL_47;
  }
  else
  {
    v26 = 0;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v22);
LABEL_47:
  v27 = gBfeObjMgr;
  v63 = 0;
  v62 = 0;
  if ( !*(_DWORD *)(gBfeObjMgr + 816) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v22);
  v28 = v27 + 1056;
  v29 = *(_QWORD *)(v25 + 80) ^ *(_QWORD *)(v25 + 88);
  if ( !v29 )
    v29 = -1;
  for ( k = RtlLookupEntryHashTable(v27 + 1056, v29, &v62); k; k = RtlGetNextEntryHashTable(v28, &v62) )
  {
    v48 = (_QWORD *)(k - 16);
    v49 = (_QWORD *)BfeObjectGetKey(k - 16);
    v50 = *v49 - *(_QWORD *)(v25 + 80);
    if ( *v49 == *(_QWORD *)(v25 + 80) )
      v50 = v49[1] - *(_QWORD *)(v25 + 88);
    if ( !v50 && (unsigned int)BfeObjectIsVisible(v48) )
    {
      BfeObjectIsVisible(v48);
      if ( v48 )
      {
        NameResolutionInfo = BfeObjectAssociate(0, v26, v48);
        if ( NameResolutionInfo )
          goto LABEL_142;
        v32 = (__int64 *)BfeObjectGetPrivateState(v48);
        goto LABEL_59;
      }
      break;
    }
  }
  LODWORD(NameResolutionInfo) = *(_DWORD *)(gBfeObjMgr + 888);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      v31,
      0,
      (__int64)"BfeObjectAssociateByKey",
      *(_DWORD *)(gBfeObjMgr + 888));
  }
  if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
  {
    v57 = NameResolutionInfo;
    v65 = &v57;
    v63 = "BfeObjectAssociateByKey";
    v64 = 24;
    v66 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      &MICROSOFT_WFP_PROVIDER_Context,
      (__int64)WFP_USERMODE_ERROR,
      v31,
      3,
      (__int64)&v62);
  }
  if ( (int)NameResolutionInfo > 0 )
    LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
  NameResolutionInfo = (int)NameResolutionInfo;
  v32 = 0;
  if ( (_DWORD)NameResolutionInfo )
    goto LABEL_142;
LABEL_59:
  v33 = *a1;
  if ( (*(_DWORD *)(*a1 + 128LL) & 0x4000) != 0 )
  {
    NameResolutionInfo = BfeObjectAssociateByKey(0, (_DWORD)a1, 4, (int)v33 + 132, (__int64)&v61);
    if ( NameResolutionInfo )
      goto LABEL_144;
    v33 = *a1;
    v54 = *(_QWORD *)(*a1 + 132LL) - *(_QWORD *)&FWPM_CALLOUT_IPSEC_DOSP_FORWARD_V6.Data1;
    if ( !v54 )
      v54 = *(_QWORD *)(v33 + 140) - *(_QWORD *)FWPM_CALLOUT_IPSEC_DOSP_FORWARD_V6.Data4;
    if ( !v54 )
    {
      dword_1800F5F44 = 1;
      v33 = *a1;
    }
  }
  else
  {
    v34 = (_QWORD *)a1[1];
    if ( !*(_DWORD *)(*v34 + 36LL) )
    {
      NameResolutionInfo = WfpReportSysErrorAsWinError(*v34, "BfeFilterCreate", 2150760468LL);
      if ( NameResolutionInfo )
        goto LABEL_144;
      return NameResolutionInfo;
    }
  }
  if ( (*(_BYTE *)(v33 + 32) & 4) != 0 )
  {
    NameResolutionInfo = BfeObjectAssociateByKey(0, (_DWORD)a1, 1, (int)v33 + 152, (__int64)&v60);
    if ( NameResolutionInfo )
      goto LABEL_144;
    v4 = v60;
    if ( (unsigned int)BfeProviderContextUsesImpersonation(v60)
      && (unsigned __int16)(*(_WORD *)(*(_QWORD *)a1[1] + 64LL) - 89) <= 3u )
    {
      *((_DWORD *)a1 + 8) = 1;
      ++dword_1800F5EB0;
    }
  }
  v35 = *(_QWORD *)(*a1 + 168LL);
  if ( !v35 || (NameResolutionInfo = BfeObjectAssociateByKey(11, (_DWORD)a1, 5, v35, 0)) == 0 )
  {
    v36 = a1 + 2;
    v37 = v61;
    NameResolutionInfo = (__int64)BfeFilterConvertM2S((_QWORD *)a1[1], v32, v61, v4, *a1, a1 + 2);
    if ( !NameResolutionInfo )
    {
      if ( (*(_WORD *)(*v36 + 26LL) & 0x100) != 0 )
        *(_DWORD *)(*a1 + 32LL) |= 0x4000u;
      NameResolutionInfo = BfeFilterComputeWeight(a1);
      if ( !NameResolutionInfo )
      {
        if ( v4 )
          v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 - 144) + 120LL))(v4);
        v40 = 0;
        if ( v37 )
          v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v37 - 144) + 120LL))(v37);
        v41 = 0;
        if ( v32 )
          v41 = (*(__int64 (__fastcall **)(__int64 *))(*(v32 - 18) + 120))(v32);
        v42 = a1[1];
        v43 = 0;
        if ( v42 )
          v43 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v42 - 144) + 120LL))(a1[1]);
        if ( v59 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v59 - 144) + 120LL))(v59);
        NameResolutionInfo = BfeFwpmFilterAssocValidate(v38, *v36, v39, v43, v41, v40, v2);
        if ( !NameResolutionInfo
          && ((unsigned __int16)(*(_WORD *)(*(_QWORD *)a1[1] + 64LL) - 91) > 1u
           || (NameResolutionInfo = BfeFilterAddRefIkeExemptions(a1)) == 0) )
        {
          NameResolutionInfo = BfeIndicesAssignFilterToIndex(
                                 *(_QWORD *)(a1[1] + 16LL),
                                 *v36,
                                 (int)a1 + 24,
                                 (int)a1 + 28,
                                 (__int64)&v58);
          if ( !NameResolutionInfo )
          {
            if ( v58 )
              *(_DWORD *)(*a1 + 32LL) |= 0x40u;
            NameResolutionInfo = BfeOptionalCreateNameResolutionInfo(a1);
            if ( !NameResolutionInfo )
            {
              NameResolutionInfo = BfeFeFilterAdd(
                                     *(unsigned __int16 *)(*(_QWORD *)a1[1] + 64LL),
                                     *((unsigned int *)a1 + 7),
                                     *a1,
                                     *v36);
              if ( !NameResolutionInfo )
              {
                if ( (*(_BYTE *)(*a1 + 32LL) & 2) != 0 )
                  dword_1800F5E8C = 1;
                return NameResolutionInfo;
              }
            }
          }
        }
      }
    }
  }
LABEL_144:
  BfeObjectTraceAddFailure(5, *a1);
  BfeFilterDestroy(a1);
  WfpReportError(NameResolutionInfo, "BfeFilterCreate");
  return NameResolutionInfo;
}

```

## disassembly

```asm
0x180006ed0  mov     [rsp-8+arg_10], rbx
0x180006ed5  push    rbp
0x180006ed6  push    rsi
0x180006ed7  push    rdi
0x180006ed8  push    r12
0x180006eda  push    r13
0x180006edc  push    r14
0x180006ede  push    r15
0x180006ee0  lea     rbp, [rsp-27h]
0x180006ee5  sub     rsp, 0A0h
0x180006eec  mov     rax, cs:__security_cookie
0x180006ef3  xor     rax, rsp
0x180006ef6  mov     [rbp+57h+var_38], rax
0x180006efa  xor     r13d, r13d
0x180006efd  or      eax, 0FFFFFFFFh
0x180006f00  mov     [rcx+18h], eax
0x180006f03  xorps   xmm0, xmm0
0x180006f06  mov     [rcx+1Ch], eax
0x180006f09  mov     rdi, rcx
0x180006f0c  movups  xmmword ptr [rcx+28h], xmm0
0x180006f10  mov     rax, [rdx]
0x180006f13  mov     r12d, r13d
0x180006f16  mov     [rcx], rax
0x180006f19  mov     [rdx], r13
0x180006f1c  lea     edx, [r13+3]
0x180006f20  mov     rax, [rcx]
0x180006f23  mov     [rbp+57h+var_80], r13
0x180006f27  mov     [rbp+57h+var_70], r13
0x180006f2b  mov     [rbp+57h+var_78], r13
0x180006f2f  and     dword ptr [rax+20h], 0FFFFFF9Fh
0x180006f33  mov     rcx, [rcx]
0x180006f36  mov     [rbp+57h+var_88], r13d
0x180006f3a  test    [rcx+20h], dl
0x180006f3d  jz      short loc_180006F48
0x180006f3f  cmp     cs:gBfeDb, r13d
0x180006f46  jnz     short loc_180006F5D
0x180006f48  mov     rax, cs:gBfeFilterComponent
0x180006f4f  mov     [rcx+0B0h], rax
0x180006f56  inc     cs:gBfeFilterComponent
0x180006f5d  mov     rax, [rdi]
0x180006f60  test    [rax+20h], dl
0x180006f63  jz      short loc_180006F6D
0x180006f65  mov     rcx, rdi
0x180006f68  call    BfeObjectSetPersistent
0x180006f6d  mov     rax, [rdi]
0x180006f70  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006f74  mov     r14, [rax+28h]
0x180006f78  test    r14, r14
0x180006f7b  jz      loc_18000704A
0x180006f81  lea     rbx, [rdi-90h]
0x180006f88  test    rbx, rbx
0x180006f8b  jz      short loc_180006F92
0x180006f8d  cmp     [rbx], r13
0x180006f90  jnz     short loc_180006F97
0x180006f92  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(from)")
0x180006f97  mov     rsi, cs:gBfeObjMgr
0x180006f9e  xor     eax, eax
0x180006fa0  xorps   xmm0, xmm0
0x180006fa3  mov     [rbp+57h+var_58], rax
0x180006fa7  movups  [rbp+57h+var_68], xmm0
0x180006fab  cmp     [rsi], r13d
0x180006fae  jnz     short loc_180006FB5
0x180006fb0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x180006fb5  mov     rdx, [r14+8]
0x180006fb9  lea     r8, [rbp+57h+var_68]
0x180006fbd  xor     rdx, [r14]
0x180006fc0  cmovz   rdx, r15
0x180006fc4  lea     r15, [rsi+0F0h]
0x180006fcb  mov     rcx, r15
0x180006fce  call    cs:__imp_RtlLookupEntryHashTable
0x180006fd5  nop     dword ptr [rax+rax+00h]
0x180006fda  test    rax, rax
0x180006fdd  jnz     loc_18000754D
0x180006fe3  mov     rax, cs:gBfeObjMgr
0x180006fea  mov     ebx, [rax+48h]
0x180006fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ff4  lea     rax, WPP_GLOBAL_Control
0x180006ffb  cmp     rcx, rax
0x180006ffe  jz      short loc_18000700A
0x180007000  cmp     byte ptr [rcx+19h], 2
0x180007004  jnb     loc_180007663
0x18000700a  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180007011  cmp     cs:gWfpLogUserModeErrors, r13d
0x180007018  jnz     loc_180007820
0x18000701e  test    ebx, ebx
0x180007020  jg      loc_1800078B5
0x180007026  movsxd  rbx, ebx
0x180007029  mov     [rbp+57h+var_80], r13
0x18000702d  mov     rsi, r13
0x180007030  test    rbx, rbx
0x180007033  jnz     loc_1800078E9
0x180007039  cmp     cs:gBfeDb, r13d
0x180007040  jnz     loc_1800078C3
0x180007046  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000704a  mov     r14, [rdi]
0x18000704d  test    rdi, rdi
0x180007050  jz      loc_180007450
0x180007056  lea     rbx, [rdi-90h]
0x18000705d  test    rbx, rbx
0x180007060  jz      short loc_180007067
0x180007062  cmp     [rbx], r13
0x180007065  jnz     short loc_18000706C
0x180007067  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(from)")
0x18000706c  mov     rsi, cs:gBfeObjMgr
0x180007073  xor     eax, eax
0x180007075  xorps   xmm0, xmm0
0x180007078  mov     [rbp+57h+var_58], rax
0x18000707c  movups  [rbp+57h+var_68], xmm0
0x180007080  cmp     [rsi+4C8h], r13d
0x180007087  jnz     short loc_18000708E
0x180007089  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x18000708e  mov     rdx, [r14+48h]
0x180007092  lea     r8, [rbp+57h+var_68]
0x180007096  xor     rdx, [r14+40h]
0x18000709a  cmovz   rdx, r15
0x18000709e  lea     r15, [rsi+5B8h]
0x1800070a5  mov     rcx, r15
0x1800070a8  call    cs:__imp_RtlLookupEntryHashTable
0x1800070af  nop     dword ptr [rax+rax+00h]
0x1800070b4  test    rax, rax
0x1800070b7  jnz     loc_180007460
0x1800070bd  mov     rax, cs:gBfeObjMgr
0x1800070c4  mov     ebx, [rax+510h]
0x1800070ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d1  lea     rax, WPP_GLOBAL_Control
0x1800070d8  cmp     rcx, rax
0x1800070db  jz      short loc_1800070E7
0x1800070dd  cmp     byte ptr [rcx+19h], 2
0x1800070e1  jnb     loc_180007603
0x1800070e7  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x1800070ee  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800070f5  jnz     loc_18000777A
0x1800070fb  test    ebx, ebx
0x1800070fd  jg      loc_180007899
0x180007103  movsxd  rbx, ebx
0x180007106  test    rbx, rbx
0x180007109  jnz     loc_1800078E9
0x18000710f  mov     rdx, [rdi]
0x180007112  add     rdx, 50h ; 'P'
0x180007116  jz      loc_180007766
0x18000711c  mov     rax, [rdx]
0x18000711f  sub     rax, cs:qword_1800B69A8
0x180007126  jnz     short loc_180007133
0x180007128  mov     rax, [rdx+8]
0x18000712c  sub     rax, cs:qword_1800B69B0
0x180007133  test    rax, rax
0x180007136  jz      loc_180007766
0x18000713c  mov     r14, [rdi]
0x18000713f  test    rdi, rdi
0x180007142  jz      loc_180007458
0x180007148  lea     rbx, [rdi-90h]
0x18000714f  test    rbx, rbx
0x180007152  jz      short loc_180007159
0x180007154  cmp     [rbx], r13
0x180007157  jnz     short loc_18000715E
0x180007159  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(from)")
0x18000715e  mov     rsi, cs:gBfeObjMgr
0x180007165  xor     eax, eax
0x180007167  xorps   xmm0, xmm0
0x18000716a  mov     [rbp+57h+var_58], rax
0x18000716e  movups  [rbp+57h+var_68], xmm0
0x180007172  cmp     [rsi+330h], r13d
0x180007179  jnz     short loc_180007180
0x18000717b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x180007180  mov     rdx, [r14+58h]
0x180007184  lea     r15, [rsi+420h]
0x18000718b  xor     rdx, [r14+50h]
0x18000718f  lea     r8, [rbp+57h+var_68]
0x180007193  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000719a  mov     rcx, r15
0x18000719d  cmovz   rdx, rax
0x1800071a1  call    cs:__imp_RtlLookupEntryHashTable
0x1800071a8  nop     dword ptr [rax+rax+00h]
0x1800071ad  test    rax, rax
0x1800071b0  jnz     loc_1800074DD
0x1800071b6  mov     rax, cs:gBfeObjMgr
0x1800071bd  mov     ebx, [rax+378h]
0x1800071c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071ca  lea     rax, WPP_GLOBAL_Control
0x1800071d1  cmp     rcx, rax
0x1800071d4  jz      short loc_1800071E0
0x1800071d6  cmp     byte ptr [rcx+19h], 2
0x1800071da  jnb     loc_180007633
0x1800071e0  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x1800071e7  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800071ee  jnz     loc_1800077CD
0x1800071f4  test    ebx, ebx
0x1800071f6  jg      loc_1800078A7
0x1800071fc  movsxd  rbx, ebx
0x1800071ff  mov     r14, r13
0x180007202  test    rbx, rbx
0x180007205  jnz     loc_1800078E9
0x18000720b  mov     r9, [rdi]
0x18000720e  test    dword ptr [r9+80h], 4000h
0x180007219  jnz     loc_180007693
0x18000721f  mov     rax, [rdi+8]
0x180007223  mov     rcx, [rax]
0x180007226  cmp     [rcx+24h], r13d
0x18000722a  jz      loc_180007407
0x180007230  test    byte ptr [r9+20h], 4
0x180007235  jnz     loc_1800076FB
0x18000723b  mov     rax, [rdi]
0x18000723e  mov     r9, [rax+0A8h]
0x180007245  test    r9, r9
0x180007248  jnz     loc_1800078FA
0x18000724e  mov     rax, [rdi]
0x180007251  lea     rsi, [rdi+10h]
0x180007255  mov     r15, [rbp+57h+var_70]
0x180007259  mov     r9, r12
0x18000725c  mov     rcx, [rdi+8]
0x180007260  mov     r8, r15
0x180007263  mov     [rsp+0D0h+var_A8], rsi
0x180007268  mov     rdx, r14
0x18000726b  mov     [rsp+0D0h+var_B0], rax
0x180007270  call    BfeFilterConvertM2S
0x180007275  mov     rbx, rax
0x180007278  test    rax, rax
0x18000727b  jnz     loc_18000791D
0x180007281  mov     rax, [rsi]
0x180007284  mov     ecx, 100h
0x180007289  test    [rax+1Ah], cx
0x18000728d  jnz     loc_18000788C
0x180007293  mov     rcx, rdi
0x180007296  call    BfeFilterComputeWeight
0x18000729b  mov     rbx, rax
0x18000729e  test    rax, rax
0x1800072a1  jnz     loc_18000791D
0x1800072a7  test    r12, r12
0x1800072aa  jz      short loc_1800072C3
0x1800072ac  mov     rax, [r12-90h]
0x1800072b4  mov     rcx, r12
0x1800072b7  mov     rax, [rax+78h]
0x1800072bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c0  mov     r13, rax
0x1800072c3  xor     r12d, r12d
0x1800072c6  test    r15, r15
0x1800072c9  jz      short loc_1800072E1
0x1800072cb  mov     rcx, [r15-90h]
0x1800072d2  mov     rax, [rcx+78h]
0x1800072d6  mov     rcx, r15
0x1800072d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072de  mov     r12, rax
0x1800072e1  xor     r15d, r15d
0x1800072e4  test    r14, r14
0x1800072e7  jz      short loc_1800072FF
0x1800072e9  mov     rcx, [r14-90h]
0x1800072f0  mov     rax, [rcx+78h]
0x1800072f4  mov     rcx, r14
0x1800072f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072fc  mov     r15, rax
0x1800072ff  mov     rdx, [rdi+8]
0x180007303  xor     ebx, ebx
0x180007305  test    rdx, rdx
0x180007308  jz      short loc_180007320
0x18000730a  mov     rcx, [rdx-90h]
0x180007311  mov     rax, [rcx+78h]
0x180007315  mov     rcx, rdx
0x180007318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000731d  mov     rbx, rax
0x180007320  mov     rdx, [rbp+57h+var_80]
0x180007324  test    rdx, rdx
0x180007327  jz      short loc_18000733C
0x180007329  mov     rcx, [rdx-90h]
0x180007330  mov     rax, [rcx+78h]
0x180007334  mov     rcx, rdx
0x180007337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733c  mov     rdx, [rsi]
0x18000733f  mov     r9, rbx
0x180007342  mov     [rsp+0D0h+var_A0], r13
0x180007347  mov     [rsp+0D0h+var_A8], r12
0x18000734c  mov     [rsp+0D0h+var_B0], r15
0x180007351  call    BfeFwpmFilterAssocValidate
0x180007356  xor     r13d, r13d
0x180007359  mov     rbx, rax
0x18000735c  test    rax, rax
0x18000735f  jnz     loc_18000791D
0x180007365  mov     rax, [rdi+8]
0x180007369  lea     r15d, [rbx+1]
0x18000736d  mov     rcx, [rax]
0x180007370  movzx   eax, word ptr [rcx+40h]
0x180007374  sub     ax, 5Bh ; '['
0x180007378  cmp     ax, r15w
0x18000737c  jbe     loc_180007873
0x180007382  mov     rcx, [rdi+8]
0x180007386  lea     rax, [rbp+57h+var_88]
0x18000738a  mov     rdx, [rsi]
0x18000738d  lea     r9, [rdi+1Ch]
0x180007391  lea     r8, [rdi+18h]
0x180007395  mov     [rsp+0D0h+var_B0], rax
0x18000739a  mov     rcx, [rcx+10h]
0x18000739e  call    BfeIndicesAssignFilterToIndex
0x1800073a3  mov     rbx, rax
0x1800073a6  test    rax, rax
0x1800073a9  jnz     loc_18000791D
0x1800073af  cmp     [rbp+57h+var_88], r13d
0x1800073b3  jz      short loc_1800073BC
0x1800073b5  mov     rax, [rdi]
0x1800073b8  or      dword ptr [rax+20h], 40h
0x1800073bc  mov     rcx, rdi
0x1800073bf  call    BfeOptionalCreateNameResolutionInfo
  ... truncated ...
```
