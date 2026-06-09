# TurnOnBitLocker(void *,bool)

- ea: `0x18004b698`
- end: `0x18004bd69`
- name: `?TurnOnBitLocker@@YAJPEAX_N@Z`
- size: `1745`
- prototype: `__int64 __fastcall(void *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004d7f0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180024468`
- `0x180034070`
- `0x180048cd0`
- `0x180048ddc`
- `0x18004aaec`
- `0x18004b698`
- `0x18004bd70`
- `0x1800717fc`

## import_xrefs

- `FVEAPI!FveBindDataVolume` at `0x18004ba45`
- `FVEAPI!FveBindDataVolume` at `0x18004ba45`
- `FVEAPI!FveInitVolumeEx2` at `0x18004b8e3`
- `FVEAPI!FveInitVolumeEx2` at `0x18004b8e3`
- `FVEAPI!FveConversionEncryptEx` at `0x18004bc46`
- `FVEAPI!FveConversionEncryptEx` at `0x18004bc46`
- `FVEAPI!FveCommitChangesEx` at `0x18004bbd8`
- `FVEAPI!FveCommitChangesEx` at `0x18004bbd8`
- `FVEAPI!FveRevertVolume` at `0x18004bcdf`
- `FVEAPI!FveRevertVolume` at `0x18004bcdf`

## pseudocode

```c
__int64 __fastcall TurnOnBitLocker(void *a1, unsigned __int8 a2)
{
  unsigned int v2; // esi
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  int StatusFlags; // eax
  int v9; // eax
  char v10; // r12
  PVOID *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // r15d
  _BOOL8 v14; // r9
  __int64 *v15; // r8
  int inited; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v30; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v31; // [rsp+24h] [rbp-44h] BYREF
  struct _GUID v32; // [rsp+28h] [rbp-40h] BYREF

  v2 = a2;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 == (void *)-1LL )
  {
    v5 = -2147024809;
    if ( v4 == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)v4 + 28) & 0x40) == 0 )
      goto LABEL_117;
    v6 = 295;
    goto LABEL_8;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(v4[2], 296, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v2);
  StatusFlags = CFveApiWrapper::GetStatusFlags(a1, &v30);
  v5 = StatusFlags;
  if ( StatusFlags < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          297,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)StatusFlags);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v6 = 298;
LABEL_8:
          v7 = v5;
LABEL_115:
          WPP_SF_d(v4[2], v6, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v7);
          goto LABEL_116;
        }
        goto LABEL_117;
      }
    }
    return v5;
  }
  v9 = ValidateVolumeStateForSilentBitLocker(a1, v30, v2, &v31);
  v5 = v9;
  if ( v9 >= 0 )
  {
    if ( (v30 & 1) != 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v10 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 302;
        goto LABEL_33;
      }
    }
    else
    {
      v10 = 1;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 301;
LABEL_33:
        WPP_SF_(v11[2], v12, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    v13 = v30 & 0x10000000;
    v14 = (v30 & 0x10000000) != 0;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
      WPP_SF_d(v11[2], 303, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v14);
    if ( v10 )
    {
      v15 = FVE_GUID_PROV_SCENARIO_SILENT_BL_FDV;
      if ( !(_BYTE)v2 )
        v15 = FVE_GUID_PROV_SCENARIO_SILENT_BL_OSV;
      inited = FveInitVolumeEx2(a1, v13 != 0 ? 0x100 : 0, v15, v14);
      v5 = inited;
      if ( inited < 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_111;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            304,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)inited);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 == &WPP_GLOBAL_Control )
        {
LABEL_111:
          v28 = FveRevertVolume(a1);
          if ( v28 < 0 )
          {
            v4 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v5;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_117;
            v6 = 323;
            v7 = (unsigned int)v28;
            goto LABEL_115;
          }
LABEL_116:
          v4 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_117;
        }
        if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          WPP_SF_d(v4[2], 305, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v5);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_108:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
          WPP_SF_(v4[2], 322, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        goto LABEL_111;
      }
    }
    v17 = ProvisionRecoveryPasswordForSilentEnablement(a1, v2);
    v5 = v17;
    if ( v17 < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            306,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v17);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v21 = 307;
LABEL_106:
          WPP_SF_d(v4[2], v21, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v5);
          v4 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_107;
        }
      }
      goto LABEL_107;
    }
    if ( (_BYTE)v2 )
    {
      if ( (v31 & 4) == 0 )
      {
        v22 = AddExternalKeyProtector(a1, &v32);
        v5 = v22;
        if ( v22 < 0 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                308,
                &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
                (unsigned int)v22);
              v4 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v21 = 309;
              goto LABEL_106;
            }
          }
LABEL_107:
          if ( !v10 )
            goto LABEL_117;
          goto LABEL_108;
        }
        v23 = FveBindDataVolume(a1, &v32);
        v5 = v23;
        if ( v23 < 0 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                310,
                &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
                (unsigned int)v23);
              v4 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v21 = 311;
              goto LABEL_106;
            }
          }
          goto LABEL_107;
        }
      }
    }
    else if ( (v31 & 1) == 0 )
    {
      v24 = AddTPMOnlyProtector(a1, v18, v19, v20);
      v5 = v24;
      if ( v24 < 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              312,
              &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
              (unsigned int)v24);
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
          {
            v21 = 313;
            goto LABEL_106;
          }
        }
        goto LABEL_107;
      }
    }
    if ( (v30 & 0x400) == 0 )
      goto LABEL_90;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v25 = CFveApiWrapper::DeleteClearKey(a1);
    v5 = v25;
    if ( v25 < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            315,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v25);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v21 = 316;
          goto LABEL_106;
        }
      }
    }
    else
    {
LABEL_90:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 317, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      v26 = FveCommitChangesEx(a1, 4);
      v5 = v26;
      if ( v26 >= 0 )
      {
        v27 = FveConversionEncryptEx(a1, (unsigned int)(v13 != 0) + 64);
        v5 = v27;
        if ( v27 >= 0 )
          goto LABEL_116;
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_107;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            320,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v27);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 0x40) == 0 )
          goto LABEL_107;
        v21 = 321;
        goto LABEL_106;
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            318,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v26);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v21 = 319;
          goto LABEL_106;
        }
      }
    }
    goto LABEL_107;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        299,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)v9);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
      {
        v6 = 300;
        goto LABEL_8;
      }
LABEL_117:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
        WPP_SF_d(v4[2], 324, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18004b698  mov     [rsp+arg_10], rbx
0x18004b69d  push    rsi
0x18004b69e  push    r12
0x18004b6a0  push    r13
0x18004b6a2  push    r14
0x18004b6a4  push    r15
0x18004b6a6  sub     rsp, 40h
0x18004b6aa  mov     rax, cs:__security_cookie
0x18004b6b1  xor     rax, rsp
0x18004b6b4  mov     [rsp+68h+var_30], rax
0x18004b6b9  xorps   xmm0, xmm0
0x18004b6bc  movzx   esi, dl
0x18004b6bf  movups  xmmword ptr [rsp+68h+var_40.Data1], xmm0
0x18004b6c4  mov     r14, rcx
0x18004b6c7  mov     [rsp+68h+var_48], 0
0x18004b6cf  mov     [rsp+68h+var_44], 0
0x18004b6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b6de  lea     r13, WPP_GLOBAL_Control
0x18004b6e5  cmp     rcx, r13
0x18004b6e8  jz      short loc_18004B70C
0x18004b6ea  test    byte ptr [rcx+1Ch], 20h
0x18004b6ee  jz      short loc_18004B70C
0x18004b6f0  mov     rcx, [rcx+10h]
0x18004b6f4  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b6fb  mov     edx, 126h
0x18004b700  call    WPP_SF_
0x18004b705  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b70c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18004b710  jnz     short loc_18004B737
0x18004b712  mov     ebx, 80070057h
0x18004b717  cmp     rcx, r13
0x18004b71a  jz      loc_18004BD43
0x18004b720  test    byte ptr [rcx+1Ch], 40h
0x18004b724  jz      loc_18004BD20
0x18004b72a  mov     edx, 127h
0x18004b72f  mov     r9d, ebx
0x18004b732  jmp     loc_18004BD09
0x18004b737  cmp     rcx, r13
0x18004b73a  jz      short loc_18004B75A
0x18004b73c  test    byte ptr [rcx+1Ch], 8
0x18004b740  jz      short loc_18004B75A
0x18004b742  mov     rcx, [rcx+10h]
0x18004b746  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b74d  mov     r9d, esi
0x18004b750  mov     edx, 128h
0x18004b755  call    WPP_SF_d
0x18004b75a  lea     rdx, [rsp+68h+var_48]; unsigned int *
0x18004b75f  mov     rcx, r14; void *
0x18004b762  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x18004b767  mov     ebx, eax
0x18004b769  test    eax, eax
0x18004b76b  jns     short loc_18004B7BF
0x18004b76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b774  cmp     rcx, r13
0x18004b777  jz      loc_18004BD43
0x18004b77d  test    byte ptr [rcx+1Ch], 2
0x18004b781  jz      short loc_18004B7A2
0x18004b783  mov     rcx, [rcx+10h]
0x18004b787  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b78e  mov     edx, 129h
0x18004b793  mov     r9d, eax
0x18004b796  call    WPP_SF_d
0x18004b79b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7a2  cmp     rcx, r13
0x18004b7a5  jz      loc_18004BD43
0x18004b7ab  test    byte ptr [rcx+1Ch], 40h
0x18004b7af  jz      loc_18004BD20
0x18004b7b5  mov     edx, 12Ah
0x18004b7ba  jmp     loc_18004B72F
0x18004b7bf  mov     edx, [rsp+68h+var_48]; unsigned int
0x18004b7c3  lea     r9, [rsp+68h+var_44]; unsigned int *
0x18004b7c8  mov     r8b, sil; unsigned __int8
0x18004b7cb  mov     rcx, r14; void *
0x18004b7ce  call    ?ValidateVolumeStateForSilentBitLocker@@YAJPEAXKEPEAK@Z; ValidateVolumeStateForSilentBitLocker(void *,ulong,uchar,ulong *)
0x18004b7d3  mov     ebx, eax
0x18004b7d5  test    eax, eax
0x18004b7d7  jns     short loc_18004B82B
0x18004b7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7e0  cmp     rcx, r13
0x18004b7e3  jz      loc_18004BD43
0x18004b7e9  test    byte ptr [rcx+1Ch], 2
0x18004b7ed  jz      short loc_18004B80E
0x18004b7ef  mov     rcx, [rcx+10h]
0x18004b7f3  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b7fa  mov     edx, 12Bh
0x18004b7ff  mov     r9d, eax
0x18004b802  call    WPP_SF_d
0x18004b807  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b80e  cmp     rcx, r13
0x18004b811  jz      loc_18004BD43
0x18004b817  test    byte ptr [rcx+1Ch], 40h
0x18004b81b  jz      loc_18004BD20
0x18004b821  mov     edx, 12Ch
0x18004b826  jmp     loc_18004B72F
0x18004b82b  test    byte ptr [rsp+68h+var_48], 1
0x18004b830  jnz     short loc_18004B84E
0x18004b832  mov     r12b, 1
0x18004b835  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b83c  cmp     rcx, r13
0x18004b83f  jz      short loc_18004B87F
0x18004b841  test    byte ptr [rcx+1Ch], 8
0x18004b845  jz      short loc_18004B87F
0x18004b847  mov     edx, 12Dh
0x18004b84c  jmp     short loc_18004B868
0x18004b84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b855  xor     r12b, r12b
0x18004b858  cmp     rcx, r13
0x18004b85b  jz      short loc_18004B87F
0x18004b85d  test    byte ptr [rcx+1Ch], 8
0x18004b861  jz      short loc_18004B87F
0x18004b863  mov     edx, 12Eh
0x18004b868  mov     rcx, [rcx+10h]
0x18004b86c  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b873  call    WPP_SF_
0x18004b878  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b87f  mov     r15d, [rsp+68h+var_48]
0x18004b884  mov     r9d, 0
0x18004b88a  and     r15d, 10000000h
0x18004b891  setnz   r9b
0x18004b895  cmp     rcx, r13
0x18004b898  jz      short loc_18004B8B5
0x18004b89a  test    byte ptr [rcx+1Ch], 8
0x18004b89e  jz      short loc_18004B8B5
0x18004b8a0  mov     rcx, [rcx+10h]
0x18004b8a4  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b8ab  mov     edx, 12Fh
0x18004b8b0  call    WPP_SF_d
0x18004b8b5  test    r12b, r12b
0x18004b8b8  jz      loc_18004B961
0x18004b8be  lea     rax, FVE_GUID_PROV_SCENARIO_SILENT_BL_OSV
0x18004b8c5  test    sil, sil
0x18004b8c8  lea     r8, FVE_GUID_PROV_SCENARIO_SILENT_BL_FDV
0x18004b8cf  mov     rcx, r14
0x18004b8d2  cmovz   r8, rax
0x18004b8d6  mov     eax, r15d
0x18004b8d9  neg     eax
0x18004b8db  sbb     edx, edx
0x18004b8dd  and     edx, 100h
0x18004b8e3  call    cs:__imp_FveInitVolumeEx2
0x18004b8ea  nop     dword ptr [rax+rax+00h]
0x18004b8ef  mov     ebx, eax
0x18004b8f1  test    eax, eax
0x18004b8f3  jns     short loc_18004B961
0x18004b8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8fc  cmp     rcx, r13
0x18004b8ff  jz      loc_18004BCDC
0x18004b905  test    byte ptr [rcx+1Ch], 2
0x18004b909  jz      short loc_18004B92A
0x18004b90b  mov     rcx, [rcx+10h]
0x18004b90f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b916  mov     edx, 130h
0x18004b91b  mov     r9d, eax
0x18004b91e  call    WPP_SF_d
0x18004b923  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b92a  cmp     rcx, r13
0x18004b92d  jz      loc_18004BCDC
0x18004b933  test    byte ptr [rcx+1Ch], 40h
0x18004b937  jz      loc_18004BCBC
0x18004b93d  mov     rcx, [rcx+10h]
0x18004b941  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b948  mov     edx, 131h
0x18004b94d  mov     r9d, ebx
0x18004b950  call    WPP_SF_d
0x18004b955  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b95c  jmp     loc_18004BCBC
0x18004b961  mov     dl, sil; bool
0x18004b964  mov     rcx, r14; void *
0x18004b967  call    ?ProvisionRecoveryPasswordForSilentEnablement@@YAJPEAX_N@Z; ProvisionRecoveryPasswordForSilentEnablement(void *,bool)
0x18004b96c  mov     ebx, eax
0x18004b96e  test    eax, eax
0x18004b970  jns     short loc_18004B9C4
0x18004b972  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b979  cmp     rcx, r13
0x18004b97c  jz      loc_18004BCB7
0x18004b982  test    byte ptr [rcx+1Ch], 2
0x18004b986  jz      short loc_18004B9A7
0x18004b988  mov     rcx, [rcx+10h]
0x18004b98c  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004b993  mov     edx, 132h
0x18004b998  mov     r9d, eax
0x18004b99b  call    WPP_SF_d
0x18004b9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9a7  cmp     rcx, r13
0x18004b9aa  jz      loc_18004BCB7
0x18004b9b0  test    byte ptr [rcx+1Ch], 40h
0x18004b9b4  jz      loc_18004BCB7
0x18004b9ba  mov     edx, 133h
0x18004b9bf  jmp     loc_18004BC9D
0x18004b9c4  test    sil, sil
0x18004b9c7  jz      loc_18004BAAD
0x18004b9cd  test    byte ptr [rsp+68h+var_44], 4
0x18004b9d2  jnz     loc_18004BB14
0x18004b9d8  lea     rdx, [rsp+68h+var_40]; struct _GUID *
0x18004b9dd  mov     rcx, r14; void *
0x18004b9e0  call    ?AddExternalKeyProtector@@YAJPEAXPEAU_GUID@@@Z; AddExternalKeyProtector(void *,_GUID *)
0x18004b9e5  mov     ebx, eax
0x18004b9e7  test    eax, eax
0x18004b9e9  jns     short loc_18004BA3D
0x18004b9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9f2  cmp     rcx, r13
0x18004b9f5  jz      loc_18004BCB7
0x18004b9fb  test    byte ptr [rcx+1Ch], 2
0x18004b9ff  jz      short loc_18004BA20
0x18004ba01  mov     rcx, [rcx+10h]
0x18004ba05  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ba0c  mov     edx, 134h
0x18004ba11  mov     r9d, eax
0x18004ba14  call    WPP_SF_d
0x18004ba19  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba20  cmp     rcx, r13
0x18004ba23  jz      loc_18004BCB7
0x18004ba29  test    byte ptr [rcx+1Ch], 40h
0x18004ba2d  jz      loc_18004BCB7
0x18004ba33  mov     edx, 135h
0x18004ba38  jmp     loc_18004BC9D
0x18004ba3d  lea     rdx, [rsp+68h+var_40]
0x18004ba42  mov     rcx, r14
0x18004ba45  call    cs:__imp_FveBindDataVolume
0x18004ba4c  nop     dword ptr [rax+rax+00h]
0x18004ba51  mov     ebx, eax
0x18004ba53  test    eax, eax
0x18004ba55  jns     loc_18004BB14
0x18004ba5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba62  cmp     rcx, r13
0x18004ba65  jz      loc_18004BCB7
0x18004ba6b  test    byte ptr [rcx+1Ch], 2
0x18004ba6f  jz      short loc_18004BA90
0x18004ba71  mov     rcx, [rcx+10h]
0x18004ba75  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ba7c  mov     edx, 136h
0x18004ba81  mov     r9d, eax
0x18004ba84  call    WPP_SF_d
0x18004ba89  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba90  cmp     rcx, r13
0x18004ba93  jz      loc_18004BCB7
0x18004ba99  test    byte ptr [rcx+1Ch], 40h
0x18004ba9d  jz      loc_18004BCB7
0x18004baa3  mov     edx, 137h
0x18004baa8  jmp     loc_18004BC9D
0x18004baad  test    byte ptr [rsp+68h+var_44], 1
0x18004bab2  jnz     short loc_18004BB14
0x18004bab4  mov     rcx, r14; void *
0x18004bab7  call    ?AddTPMOnlyProtector@@YAJPEAX@Z; AddTPMOnlyProtector(void *)
0x18004babc  mov     ebx, eax
0x18004babe  test    eax, eax
0x18004bac0  jns     short loc_18004BB14
0x18004bac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bac9  cmp     rcx, r13
0x18004bacc  jz      loc_18004BCB7
0x18004bad2  test    byte ptr [rcx+1Ch], 2
0x18004bad6  jz      short loc_18004BAF7
0x18004bad8  mov     rcx, [rcx+10h]
0x18004badc  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004bae3  mov     edx, 138h
0x18004bae8  mov     r9d, eax
0x18004baeb  call    WPP_SF_d
0x18004baf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004baf7  cmp     rcx, r13
0x18004bafa  jz      loc_18004BCB7
0x18004bb00  test    byte ptr [rcx+1Ch], 40h
0x18004bb04  jz      loc_18004BCB7
0x18004bb0a  mov     edx, 139h
0x18004bb0f  jmp     loc_18004BC9D
0x18004bb14  test    [rsp+68h+var_48], 400h
0x18004bb1c  jz      loc_18004BBA9
0x18004bb22  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb29  cmp     rcx, r13
0x18004bb2c  jz      short loc_18004BB49
0x18004bb2e  test    byte ptr [rcx+1Ch], 8
0x18004bb32  jz      short loc_18004BB49
0x18004bb34  mov     rcx, [rcx+10h]
0x18004bb38  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004bb3f  mov     edx, 13Ah
0x18004bb44  call    WPP_SF_
0x18004bb49  mov     rcx, r14; void *
0x18004bb4c  call    ?DeleteClearKey@CFveApiWrapper@@SAJPEAX@Z; CFveApiWrapper::DeleteClearKey(void *)
0x18004bb51  mov     ebx, eax
0x18004bb53  test    eax, eax
0x18004bb55  jns     short loc_18004BBA9
0x18004bb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb5e  cmp     rcx, r13
0x18004bb61  jz      loc_18004BCB7
0x18004bb67  test    byte ptr [rcx+1Ch], 2
0x18004bb6b  jz      short loc_18004BB8C
0x18004bb6d  mov     rcx, [rcx+10h]
0x18004bb71  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004bb78  mov     edx, 13Bh
0x18004bb7d  mov     r9d, eax
0x18004bb80  call    WPP_SF_d
0x18004bb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb8c  cmp     rcx, r13
0x18004bb8f  jz      loc_18004BCB7
0x18004bb95  test    byte ptr [rcx+1Ch], 40h
0x18004bb99  jz      loc_18004BCB7
0x18004bb9f  mov     edx, 13Ch
0x18004bba4  jmp     loc_18004BC9D
0x18004bba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbb0  cmp     rcx, r13
0x18004bbb3  jz      short loc_18004BBD0
0x18004bbb5  test    byte ptr [rcx+1Ch], 8
  ... truncated ...
```
