# BfeFilterCreate

- ea: `0x1800069d0`
- end: `0x18000742a`
- name: `BfeFilterCreate`
- size: `2650`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052f0`
- `0x1800060a8`
- `0x1800069d0`
- `0x180007430`
- `0x180007460`
- `0x1800074cc`
- `0x180007790`
- `0x180007f30`
- `0x18000e680`
- `0x18000f1a8`
- `0x18000f200`
- `0x18001236c`
- `0x180012950`
- `0x180013480`
- `0x180018b74`
- `0x1800204c4`
- `0x180026c50`
- `0x180026f00`
- `0x180033d90`
- `0x1800358c4`
- `0x18003b5b4`
- `0x1800575c4`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180006ace`
- `ntdll!RtlLookupEntryHashTable` at `0x180006ba2`
- `ntdll!RtlLookupEntryHashTable` at `0x180006c95`
- `ntdll!RtlLookupEntryHashTable` at `0x180006ace`
- `ntdll!RtlLookupEntryHashTable` at `0x180006ba2`
- `ntdll!RtlLookupEntryHashTable` at `0x180006c95`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070af`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070c1`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070d3`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070af`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070c1`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800070d3`

## string_xrefs

- `0x180006efb`: `BfeFilterCreate`
- `0x180007416`: `BfeFilterCreate`

## pseudocode

```c
__int64 __fastcall BfeFilterCreate(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // r13
  __int64 v4; // r12
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r15
  __int64 i; // rax
  int v12; // r8d
  __int64 NameResolutionInfo; // rbx
  __int64 PrivateState; // rsi
  __int64 v15; // r14
  _QWORD *v16; // rbx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // r15
  __int64 j; // rax
  int v21; // r8d
  __int64 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r14
  _QWORD *v25; // rbx
  __int64 v26; // rsi
  __int64 v27; // r15
  __int64 v28; // rdx
  __int64 k; // rax
  int v30; // r8d
  __int64 *v31; // r14
  __int64 v32; // r9
  _QWORD *v33; // rax
  __int64 v34; // r9
  _QWORD *v35; // rsi
  __int64 v36; // r15
  int v37; // ecx
  int v38; // r8d
  __int64 v39; // r12
  __int64 v40; // r15
  __int64 v41; // rdx
  int v42; // ebx
  _QWORD *v44; // rsi
  _QWORD *v45; // rax
  __int64 v46; // rcx
  _QWORD *v47; // rsi
  _QWORD *v48; // rax
  __int64 v49; // rcx
  _QWORD *v50; // rsi
  _QWORD *Key; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  int v54; // eax
  int v55; // [rsp+40h] [rbp-39h] BYREF
  int v56; // [rsp+48h] [rbp-31h] BYREF
  __int64 v57; // [rsp+50h] [rbp-29h]
  __int64 v58; // [rsp+58h] [rbp-21h] BYREF
  __int64 v59; // [rsp+60h] [rbp-19h] BYREF
  __int128 v60; // [rsp+68h] [rbp-11h] BYREF
  const char *v61; // [rsp+78h] [rbp-1h]
  __int64 v62; // [rsp+80h] [rbp+7h]
  int *v63; // [rsp+88h] [rbp+Fh]
  __int64 v64; // [rsp+90h] [rbp+17h]

  v2 = 0;
  *((_DWORD *)a1 + 6) = -1;
  *((_DWORD *)a1 + 7) = -1;
  *(_OWORD *)(a1 + 5) = 0;
  v4 = 0;
  *a1 = *a2;
  *a2 = 0;
  v5 = *a1;
  v57 = 0;
  v59 = 0;
  v58 = 0;
  *(_DWORD *)(v5 + 32) &= 0xFFFFFF9F;
  v6 = *a1;
  v56 = 0;
  if ( (*(_BYTE *)(v6 + 32) & 3) == 0 || !gBfeDb )
    *(_QWORD *)(v6 + 176) = gBfeFilterComponent++;
  if ( (*(_BYTE *)(*a1 + 32LL) & 3) != 0 )
    BfeObjectSetPersistent(a1);
  v7 = *(_QWORD **)(*a1 + 40LL);
  if ( v7 )
  {
    if ( a1 == (_QWORD *)144 || !*(a1 - 18) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = gBfeObjMgr;
    v61 = 0;
    v60 = 0;
    if ( !*(_DWORD *)gBfeObjMgr )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = *v7 ^ v7[1];
    if ( !v9 )
      v9 = -1;
    v10 = v8 + 240;
    for ( i = RtlLookupEntryHashTable(v8 + 240, v9, &v60); ; i = RtlGetNextEntryHashTable(v10, &v60) )
    {
      if ( !i )
        goto LABEL_16;
      v50 = (_QWORD *)(i - 16);
      Key = (_QWORD *)BfeObjectGetKey(i - 16);
      v52 = *Key - *v7;
      if ( !v52 )
        v52 = Key[1] - v7[1];
      if ( !v52 && (unsigned int)BfeObjectIsVisible(v50) )
        break;
    }
    BfeObjectIsVisible(v50);
    if ( v50 )
    {
      NameResolutionInfo = BfeObjectAssociate(0, a1 - 18, v50);
      if ( !NameResolutionInfo )
      {
        PrivateState = BfeObjectGetPrivateState(v50);
        v57 = PrivateState;
LABEL_22:
        if ( gBfeDb )
        {
          if ( (*(_BYTE *)(*(_QWORD *)PrivateState + 32LL) & 0x10) != 0 )
          {
            v54 = *(_DWORD *)(*a1 + 32LL);
            if ( (v54 & 2) == 0 )
              *(_DWORD *)(*a1 + 32LL) = v54 | 0x20;
          }
        }
        goto LABEL_23;
      }
    }
    else
    {
LABEL_16:
      LODWORD(NameResolutionInfo) = *(_DWORD *)(gBfeObjMgr + 72);
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
      if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
      {
        v55 = NameResolutionInfo;
        v63 = &v55;
        v61 = "BfeObjectAssociateByKey";
        v62 = 24;
        v64 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v12,
          3,
          (__int64)&v60);
      }
      if ( (int)NameResolutionInfo > 0 )
        LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
      NameResolutionInfo = (int)NameResolutionInfo;
      v57 = 0;
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
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_27:
  v17 = gBfeObjMgr;
  v61 = 0;
  v60 = 0;
  if ( !*(_DWORD *)(gBfeObjMgr + 1224) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v18 = *(_QWORD *)(v15 + 64) ^ *(_QWORD *)(v15 + 72);
  if ( !v18 )
    v18 = -1;
  v19 = v17 + 1464;
  for ( j = RtlLookupEntryHashTable(v17 + 1464, v18, &v60); j; j = RtlGetNextEntryHashTable(v19, &v60) )
  {
    v44 = (_QWORD *)(j - 16);
    v45 = (_QWORD *)BfeObjectGetKey(j - 16);
    v46 = *v45 - *(_QWORD *)(v15 + 64);
    if ( *v45 == *(_QWORD *)(v15 + 64) )
      v46 = v45[1] - *(_QWORD *)(v15 + 72);
    if ( !v46 && (unsigned int)BfeObjectIsVisible(v44) )
    {
      BfeObjectIsVisible(v44);
      if ( v44 )
      {
        NameResolutionInfo = BfeObjectAssociate(0, v16, v44);
        if ( NameResolutionInfo )
          goto LABEL_142;
        if ( a1 != (_QWORD *)-8LL )
          a1[1] = BfeObjectGetPrivateState(v44);
        goto LABEL_39;
      }
      break;
    }
  }
  LODWORD(NameResolutionInfo) = *(_DWORD *)(gBfeObjMgr + 1296);
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
  if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
  {
    v55 = NameResolutionInfo;
    v63 = &v55;
    v61 = "BfeObjectAssociateByKey";
    v62 = 24;
    v64 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
      (unsigned int)WFP_USERMODE_ERROR,
      v21,
      3,
      (__int64)&v60);
  }
  if ( (int)NameResolutionInfo > 0 )
    LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
  NameResolutionInfo = (int)NameResolutionInfo;
  if ( (_DWORD)NameResolutionInfo )
    goto LABEL_142;
LABEL_39:
  v22 = (__int64 *)(*a1 + 80LL);
  if ( *a1 == -80 )
    goto LABEL_130;
  v23 = *v22;
  if ( !*v22 )
    v23 = *(_QWORD *)(*a1 + 88LL);
  if ( !v23 )
LABEL_130:
    *(_OWORD *)v22 = *(_OWORD *)(*(_QWORD *)a1[1] + 48LL);
  v24 = *a1;
  if ( a1 )
  {
    v25 = a1 - 18;
    if ( a1 != (_QWORD *)144 && *v25 )
      goto LABEL_47;
  }
  else
  {
    v25 = 0;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_47:
  v26 = gBfeObjMgr;
  v61 = 0;
  v60 = 0;
  if ( !*(_DWORD *)(gBfeObjMgr + 816) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v27 = v26 + 1056;
  v28 = *(_QWORD *)(v24 + 80) ^ *(_QWORD *)(v24 + 88);
  if ( !v28 )
    v28 = -1;
  for ( k = RtlLookupEntryHashTable(v26 + 1056, v28, &v60); k; k = RtlGetNextEntryHashTable(v27, &v60) )
  {
    v47 = (_QWORD *)(k - 16);
    v48 = (_QWORD *)BfeObjectGetKey(k - 16);
    v49 = *v48 - *(_QWORD *)(v24 + 80);
    if ( *v48 == *(_QWORD *)(v24 + 80) )
      v49 = v48[1] - *(_QWORD *)(v24 + 88);
    if ( !v49 && (unsigned int)BfeObjectIsVisible(v47) )
    {
      BfeObjectIsVisible(v47);
      if ( v47 )
      {
        NameResolutionInfo = BfeObjectAssociate(0, v25, v47);
        if ( NameResolutionInfo )
          goto LABEL_142;
        v31 = (__int64 *)BfeObjectGetPrivateState(v47);
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
      v30,
      0,
      (__int64)"BfeObjectAssociateByKey",
      *(_DWORD *)(gBfeObjMgr + 888));
  }
  if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
  {
    v55 = NameResolutionInfo;
    v63 = &v55;
    v61 = "BfeObjectAssociateByKey";
    v62 = 24;
    v64 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
      (unsigned int)WFP_USERMODE_ERROR,
      v30,
      3,
      (__int64)&v60);
  }
  if ( (int)NameResolutionInfo > 0 )
    LODWORD(NameResolutionInfo) = (unsigned __int16)NameResolutionInfo | 0x80070000;
  NameResolutionInfo = (int)NameResolutionInfo;
  v31 = 0;
  if ( (_DWORD)NameResolutionInfo )
    goto LABEL_142;
LABEL_59:
  v32 = *a1;
  if ( (*(_DWORD *)(*a1 + 128LL) & 0x4000) != 0 )
  {
    NameResolutionInfo = BfeObjectAssociateByKey(0, (_DWORD)a1, 4, (int)v32 + 132, (__int64)&v59);
    if ( NameResolutionInfo )
      goto LABEL_144;
    v32 = *a1;
    v53 = *(_QWORD *)(*a1 + 132LL) - *(_QWORD *)&FWPM_CALLOUT_IPSEC_DOSP_FORWARD_V6.Data1;
    if ( !v53 )
      v53 = *(_QWORD *)(v32 + 140) - *(_QWORD *)FWPM_CALLOUT_IPSEC_DOSP_FORWARD_V6.Data4;
    if ( !v53 )
    {
      dword_1800F2F24 = 1;
      v32 = *a1;
    }
  }
  else
  {
    v33 = (_QWORD *)a1[1];
    if ( !*(_DWORD *)(*v33 + 36LL) )
    {
      NameResolutionInfo = WfpReportSysErrorAsWinError(*v33, "BfeFilterCreate", 2150760468LL);
      if ( NameResolutionInfo )
        goto LABEL_144;
      return NameResolutionInfo;
    }
  }
  if ( (*(_BYTE *)(v32 + 32) & 4) != 0 )
  {
    NameResolutionInfo = BfeObjectAssociateByKey(0, (_DWORD)a1, 1, (int)v32 + 152, (__int64)&v58);
    if ( NameResolutionInfo )
      goto LABEL_144;
    v4 = v58;
    if ( (unsigned int)BfeProviderContextUsesImpersonation(v58)
      && (unsigned __int16)(*(_WORD *)(*(_QWORD *)a1[1] + 64LL) - 89) <= 3u )
    {
      *((_DWORD *)a1 + 8) = 1;
      ++dword_1800F2E90;
    }
  }
  v34 = *(_QWORD *)(*a1 + 168LL);
  if ( !v34 || (NameResolutionInfo = BfeObjectAssociateByKey(11, (_DWORD)a1, 5, v34, 0)) == 0 )
  {
    v35 = a1 + 2;
    v36 = v59;
    NameResolutionInfo = (__int64)BfeFilterConvertM2S((_QWORD *)a1[1], v31, v59, v4, *a1, a1 + 2);
    if ( !NameResolutionInfo )
    {
      if ( (*(_WORD *)(*v35 + 26LL) & 0x100) != 0 )
        *(_DWORD *)(*a1 + 32LL) |= 0x4000u;
      NameResolutionInfo = BfeFilterComputeWeight(a1);
      if ( !NameResolutionInfo )
      {
        if ( v4 )
          v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 - 144) + 120LL))(v4);
        v39 = 0;
        if ( v36 )
          v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v36 - 144) + 120LL))(v36);
        v40 = 0;
        if ( v31 )
          v40 = (*(__int64 (__fastcall **)(__int64 *))(*(v31 - 18) + 120))(v31);
        v41 = a1[1];
        v42 = 0;
        if ( v41 )
          v42 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v41 - 144) + 120LL))(a1[1]);
        if ( v57 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v57 - 144) + 120LL))(v57);
        NameResolutionInfo = BfeFwpmFilterAssocValidate(v37, *v35, v38, v42, v40, v39, v2);
        if ( !NameResolutionInfo
          && ((unsigned __int16)(*(_WORD *)(*(_QWORD *)a1[1] + 64LL) - 91) > 1u
           || (NameResolutionInfo = BfeFilterAddRefIkeExemptions(a1)) == 0) )
        {
          NameResolutionInfo = BfeIndicesAssignFilterToIndex(
                                 *(_QWORD *)(a1[1] + 16LL),
                                 *v35,
                                 (int)a1 + 24,
                                 (int)a1 + 28,
                                 (__int64)&v56);
          if ( !NameResolutionInfo )
          {
            if ( v56 )
              *(_DWORD *)(*a1 + 32LL) |= 0x40u;
            NameResolutionInfo = BfeOptionalCreateNameResolutionInfo(a1);
            if ( !NameResolutionInfo )
            {
              NameResolutionInfo = BfeFeFilterAdd(
                                     *(unsigned __int16 *)(*(_QWORD *)a1[1] + 64LL),
                                     *((unsigned int *)a1 + 7),
                                     *a1,
                                     *v35);
              if ( !NameResolutionInfo )
              {
                if ( (*(_BYTE *)(*a1 + 32LL) & 2) != 0 )
                  dword_1800F2E6C = 1;
                return NameResolutionInfo;
              }
            }
          }
        }
      }
    }
  }
LABEL_144:
  BfeObjectTraceAddFailure(5);
  BfeFilterDestroy(a1);
  WfpReportError(NameResolutionInfo, "BfeFilterCreate");
  return NameResolutionInfo;
}

```

## disassembly

```asm
0x1800069d0  mov     [rsp-8+arg_10], rbx
0x1800069d5  push    rbp
0x1800069d6  push    rsi
0x1800069d7  push    rdi
0x1800069d8  push    r12
0x1800069da  push    r13
0x1800069dc  push    r14
0x1800069de  push    r15
0x1800069e0  lea     rbp, [rsp-27h]
0x1800069e5  sub     rsp, 0A0h
0x1800069ec  mov     rax, cs:__security_cookie
0x1800069f3  xor     rax, rsp
0x1800069f6  mov     [rbp+57h+var_38], rax
0x1800069fa  xor     r13d, r13d
0x1800069fd  or      eax, 0FFFFFFFFh
0x180006a00  mov     [rcx+18h], eax
0x180006a03  xorps   xmm0, xmm0
0x180006a06  mov     [rcx+1Ch], eax
0x180006a09  mov     rdi, rcx
0x180006a0c  movups  xmmword ptr [rcx+28h], xmm0
0x180006a10  mov     rax, [rdx]
0x180006a13  mov     r12d, r13d
0x180006a16  mov     [rcx], rax
0x180006a19  mov     [rdx], r13
0x180006a1c  lea     edx, [r13+3]
0x180006a20  mov     rax, [rcx]
0x180006a23  mov     [rbp+57h+var_80], r13
0x180006a27  mov     [rbp+57h+var_70], r13
0x180006a2b  mov     [rbp+57h+var_78], r13
0x180006a2f  and     dword ptr [rax+20h], 0FFFFFF9Fh
0x180006a33  mov     rcx, [rcx]
0x180006a36  mov     [rbp+57h+var_88], r13d
0x180006a3a  test    [rcx+20h], dl
0x180006a3d  jz      short loc_180006A48
0x180006a3f  cmp     cs:gBfeDb, r13d
0x180006a46  jnz     short loc_180006A5D
0x180006a48  mov     rax, cs:gBfeFilterComponent
0x180006a4f  mov     [rcx+0B0h], rax
0x180006a56  inc     cs:gBfeFilterComponent
0x180006a5d  mov     rax, [rdi]
0x180006a60  test    [rax+20h], dl
0x180006a63  jz      short loc_180006A6D
0x180006a65  mov     rcx, rdi
0x180006a68  call    BfeObjectSetPersistent
0x180006a6d  mov     rax, [rdi]
0x180006a70  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006a74  mov     r14, [rax+28h]
0x180006a78  test    r14, r14
0x180006a7b  jz      loc_180006B44
0x180006a81  lea     rbx, [rdi-90h]
0x180006a88  test    rbx, rbx
0x180006a8b  jz      short loc_180006A92
0x180006a8d  cmp     [rbx], r13
0x180006a90  jnz     short loc_180006A97
0x180006a92  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006a97  mov     rsi, cs:gBfeObjMgr
0x180006a9e  xor     eax, eax
0x180006aa0  xorps   xmm0, xmm0
0x180006aa3  mov     [rbp+57h+var_58], rax
0x180006aa7  movups  [rbp+57h+var_68], xmm0
0x180006aab  cmp     [rsi], r13d
0x180006aae  jnz     short loc_180006AB5
0x180006ab0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006ab5  mov     rdx, [r14+8]
0x180006ab9  lea     r8, [rbp+57h+var_68]
0x180006abd  xor     rdx, [r14]
0x180006ac0  cmovz   rdx, r15
0x180006ac4  lea     r15, [rsi+0F0h]
0x180006acb  mov     rcx, r15
0x180006ace  call    cs:__imp_RtlLookupEntryHashTable
0x180006ad4  test    rax, rax
0x180006ad7  jnz     loc_18000703A
0x180006add  mov     rax, cs:gBfeObjMgr
0x180006ae4  mov     ebx, [rax+48h]
0x180006ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aee  lea     rax, WPP_GLOBAL_Control
0x180006af5  cmp     rcx, rax
0x180006af8  jz      short loc_180006B04
0x180006afa  cmp     byte ptr [rcx+19h], 2
0x180006afe  jnb     loc_18000713E
0x180006b04  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006b0b  cmp     cs:gWfpLogUserModeErrors, r13d
0x180006b12  jnz     loc_1800072FB
0x180006b18  test    ebx, ebx
0x180006b1a  jg      loc_180007390
0x180006b20  movsxd  rbx, ebx
0x180006b23  mov     [rbp+57h+var_80], r13
0x180006b27  mov     rsi, r13
0x180006b2a  test    rbx, rbx
0x180006b2d  jnz     loc_1800073C4
0x180006b33  cmp     cs:gBfeDb, r13d
0x180006b3a  jnz     loc_18000739E
0x180006b40  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006b44  mov     r14, [rdi]
0x180006b47  test    rdi, rdi
0x180006b4a  jz      loc_180006F3D
0x180006b50  lea     rbx, [rdi-90h]
0x180006b57  test    rbx, rbx
0x180006b5a  jz      short loc_180006B61
0x180006b5c  cmp     [rbx], r13
0x180006b5f  jnz     short loc_180006B66
0x180006b61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006b66  mov     rsi, cs:gBfeObjMgr
0x180006b6d  xor     eax, eax
0x180006b6f  xorps   xmm0, xmm0
0x180006b72  mov     [rbp+57h+var_58], rax
0x180006b76  movups  [rbp+57h+var_68], xmm0
0x180006b7a  cmp     [rsi+4C8h], r13d
0x180006b81  jnz     short loc_180006B88
0x180006b83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006b88  mov     rdx, [r14+48h]
0x180006b8c  lea     r8, [rbp+57h+var_68]
0x180006b90  xor     rdx, [r14+40h]
0x180006b94  cmovz   rdx, r15
0x180006b98  lea     r15, [rsi+5B8h]
0x180006b9f  mov     rcx, r15
0x180006ba2  call    cs:__imp_RtlLookupEntryHashTable
0x180006ba8  test    rax, rax
0x180006bab  jnz     loc_180006F4D
0x180006bb1  mov     rax, cs:gBfeObjMgr
0x180006bb8  mov     ebx, [rax+510h]
0x180006bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bc5  lea     rax, WPP_GLOBAL_Control
0x180006bcc  cmp     rcx, rax
0x180006bcf  jz      short loc_180006BDB
0x180006bd1  cmp     byte ptr [rcx+19h], 2
0x180006bd5  jnb     loc_1800070DE
0x180006bdb  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006be2  cmp     cs:gWfpLogUserModeErrors, r13d
0x180006be9  jnz     loc_180007255
0x180006bef  test    ebx, ebx
0x180006bf1  jg      loc_180007374
0x180006bf7  movsxd  rbx, ebx
0x180006bfa  test    rbx, rbx
0x180006bfd  jnz     loc_1800073C4
0x180006c03  mov     rdx, [rdi]
0x180006c06  add     rdx, 50h ; 'P'
0x180006c0a  jz      loc_180007241
0x180006c10  mov     rax, [rdx]
0x180006c13  sub     rax, cs:qword_1800B3930
0x180006c1a  jnz     short loc_180006C27
0x180006c1c  mov     rax, [rdx+8]
0x180006c20  sub     rax, cs:qword_1800B3938
0x180006c27  test    rax, rax
0x180006c2a  jz      loc_180007241
0x180006c30  mov     r14, [rdi]
0x180006c33  test    rdi, rdi
0x180006c36  jz      loc_180006F45
0x180006c3c  lea     rbx, [rdi-90h]
0x180006c43  test    rbx, rbx
0x180006c46  jz      short loc_180006C4D
0x180006c48  cmp     [rbx], r13
0x180006c4b  jnz     short loc_180006C52
0x180006c4d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006c52  mov     rsi, cs:gBfeObjMgr
0x180006c59  xor     eax, eax
0x180006c5b  xorps   xmm0, xmm0
0x180006c5e  mov     [rbp+57h+var_58], rax
0x180006c62  movups  [rbp+57h+var_68], xmm0
0x180006c66  cmp     [rsi+330h], r13d
0x180006c6d  jnz     short loc_180006C74
0x180006c6f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006c74  mov     rdx, [r14+58h]
0x180006c78  lea     r15, [rsi+420h]
0x180006c7f  xor     rdx, [r14+50h]
0x180006c83  lea     r8, [rbp+57h+var_68]
0x180006c87  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006c8e  mov     rcx, r15
0x180006c91  cmovz   rdx, rax
0x180006c95  call    cs:__imp_RtlLookupEntryHashTable
0x180006c9b  test    rax, rax
0x180006c9e  jnz     loc_180006FCA
0x180006ca4  mov     rax, cs:gBfeObjMgr
0x180006cab  mov     ebx, [rax+378h]
0x180006cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cb8  lea     rax, WPP_GLOBAL_Control
0x180006cbf  cmp     rcx, rax
0x180006cc2  jz      short loc_180006CCE
0x180006cc4  cmp     byte ptr [rcx+19h], 2
0x180006cc8  jnb     loc_18000710E
0x180006cce  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006cd5  cmp     cs:gWfpLogUserModeErrors, r13d
0x180006cdc  jnz     loc_1800072A8
0x180006ce2  test    ebx, ebx
0x180006ce4  jg      loc_180007382
0x180006cea  movsxd  rbx, ebx
0x180006ced  mov     r14, r13
0x180006cf0  test    rbx, rbx
0x180006cf3  jnz     loc_1800073C4
0x180006cf9  mov     r9, [rdi]
0x180006cfc  test    dword ptr [r9+80h], 4000h
0x180006d07  jnz     loc_18000716E
0x180006d0d  mov     rax, [rdi+8]
0x180006d11  mov     rcx, [rax]
0x180006d14  cmp     [rcx+24h], r13d
0x180006d18  jz      loc_180006EF5
0x180006d1e  test    byte ptr [r9+20h], 4
0x180006d23  jnz     loc_1800071D6
0x180006d29  mov     rax, [rdi]
0x180006d2c  mov     r9, [rax+0A8h]
0x180006d33  test    r9, r9
0x180006d36  jnz     loc_1800073D5
0x180006d3c  mov     rax, [rdi]
0x180006d3f  lea     rsi, [rdi+10h]
0x180006d43  mov     r15, [rbp+57h+var_70]
0x180006d47  mov     r9, r12
0x180006d4a  mov     rcx, [rdi+8]
0x180006d4e  mov     r8, r15
0x180006d51  mov     [rsp+0D0h+var_A8], rsi
0x180006d56  mov     rdx, r14
0x180006d59  mov     [rsp+0D0h+var_B0], rax
0x180006d5e  call    BfeFilterConvertM2S
0x180006d63  mov     rbx, rax
0x180006d66  test    rax, rax
0x180006d69  jnz     loc_1800073F8
0x180006d6f  mov     rax, [rsi]
0x180006d72  mov     ecx, 100h
0x180006d77  test    [rax+1Ah], cx
0x180006d7b  jnz     loc_180007367
0x180006d81  mov     rcx, rdi
0x180006d84  call    BfeFilterComputeWeight
0x180006d89  mov     rbx, rax
0x180006d8c  test    rax, rax
0x180006d8f  jnz     loc_1800073F8
0x180006d95  test    r12, r12
0x180006d98  jz      short loc_180006DB1
0x180006d9a  mov     rax, [r12-90h]
0x180006da2  mov     rcx, r12
0x180006da5  mov     rax, [rax+78h]
0x180006da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dae  mov     r13, rax
0x180006db1  xor     r12d, r12d
0x180006db4  test    r15, r15
0x180006db7  jz      short loc_180006DCF
0x180006db9  mov     rcx, [r15-90h]
0x180006dc0  mov     rax, [rcx+78h]
0x180006dc4  mov     rcx, r15
0x180006dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dcc  mov     r12, rax
0x180006dcf  xor     r15d, r15d
0x180006dd2  test    r14, r14
0x180006dd5  jz      short loc_180006DED
0x180006dd7  mov     rcx, [r14-90h]
0x180006dde  mov     rax, [rcx+78h]
0x180006de2  mov     rcx, r14
0x180006de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dea  mov     r15, rax
0x180006ded  mov     rdx, [rdi+8]
0x180006df1  xor     ebx, ebx
0x180006df3  test    rdx, rdx
0x180006df6  jz      short loc_180006E0E
0x180006df8  mov     rcx, [rdx-90h]
0x180006dff  mov     rax, [rcx+78h]
0x180006e03  mov     rcx, rdx
0x180006e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0b  mov     rbx, rax
0x180006e0e  mov     rdx, [rbp+57h+var_80]
0x180006e12  test    rdx, rdx
0x180006e15  jz      short loc_180006E2A
0x180006e17  mov     rcx, [rdx-90h]
0x180006e1e  mov     rax, [rcx+78h]
0x180006e22  mov     rcx, rdx
0x180006e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2a  mov     rdx, [rsi]
0x180006e2d  mov     r9, rbx
0x180006e30  mov     [rsp+0D0h+var_A0], r13
0x180006e35  mov     [rsp+0D0h+var_A8], r12
0x180006e3a  mov     [rsp+0D0h+var_B0], r15
0x180006e3f  call    BfeFwpmFilterAssocValidate
0x180006e44  xor     r13d, r13d
0x180006e47  mov     rbx, rax
0x180006e4a  test    rax, rax
0x180006e4d  jnz     loc_1800073F8
0x180006e53  mov     rax, [rdi+8]
0x180006e57  lea     r15d, [rbx+1]
0x180006e5b  mov     rcx, [rax]
0x180006e5e  movzx   eax, word ptr [rcx+40h]
0x180006e62  sub     ax, 5Bh ; '['
0x180006e66  cmp     ax, r15w
0x180006e6a  jbe     loc_18000734E
0x180006e70  mov     rcx, [rdi+8]
0x180006e74  lea     rax, [rbp+57h+var_88]
0x180006e78  mov     rdx, [rsi]
0x180006e7b  lea     r9, [rdi+1Ch]
0x180006e7f  lea     r8, [rdi+18h]
0x180006e83  mov     [rsp+0D0h+var_B0], rax
0x180006e88  mov     rcx, [rcx+10h]
0x180006e8c  call    BfeIndicesAssignFilterToIndex
0x180006e91  mov     rbx, rax
0x180006e94  test    rax, rax
0x180006e97  jnz     loc_1800073F8
0x180006e9d  cmp     [rbp+57h+var_88], r13d
0x180006ea1  jz      short loc_180006EAA
0x180006ea3  mov     rax, [rdi]
0x180006ea6  or      dword ptr [rax+20h], 40h
0x180006eaa  mov     rcx, rdi
0x180006ead  call    BfeOptionalCreateNameResolutionInfo
0x180006eb2  mov     rbx, rax
0x180006eb5  test    rax, rax
0x180006eb8  jnz     loc_1800073F8
  ... truncated ...
```
