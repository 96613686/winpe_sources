# MpRegPreReplaceKey

- ea: `0x14007ea68`
- end: `0x14007f16c`
- name: `MpRegPreReplaceKey`
- size: `1796`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x140006afc`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x14004a758`
- `0x14004b6d0`
- `0x14004c630`
- `0x14004f59c`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`
- `0x14007ea68`
- `0x14007fc94`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14007ec93`
- `ntoskrnl!IoGetCurrentProcess` at `0x14007ec93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f09e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f09e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0f6`

## string_xrefs

- `0x14007ee23`: `RegNtPreReplaceKey`
- `0x14007ee54`: `RegNtPreReplaceKey`
- `0x14007ee97`: `RegNtPreReplaceKey`
- `0x14007eeca`: `RegNtPreReplaceKey`
- `0x14007ed15`: `[Mini-filter] Denied registry key replace of [%wZ] triggered by process [%wZ].`
- `0x14007edd8`: `[Mini-filter][TP] Denied registry replace to [%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreReplaceKey(PVOID *a1, unsigned __int64 a2, __int64 *a3, _BYTE *a4, _QWORD *a5)
{
  _QWORD *v5; // r13
  __int64 v6; // rbx
  int v7; // r14d
  volatile signed __int32 *v8; // rsi
  PVOID *v10; // r12
  PVOID *v11; // r8
  int v12; // ecx
  bool v13; // di
  int KeyName; // eax
  __int64 v15; // rdx
  int matched; // eax
  char IsRegistryHardeningExemptByContext; // dl
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v19; // rax
  char v20; // al
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // r8
  _BYTE *v25; // rdx
  int v26; // ecx
  char IsTamperProtectedLevelExempt; // al
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 *v31; // rax
  PVOID *v32; // rax
  PVOID *v33; // rcx
  __int64 v34; // r8
  PVOID v35; // rdi
  void (__fastcall *v36)(PVOID); // rax
  void *v37; // rcx
  void (__fastcall *v38)(_QWORD *, unsigned __int64, PVOID *); // rax
  void *v39; // rcx
  int v41; // [rsp+20h] [rbp-51h]
  char v42; // [rsp+40h] [rbp-31h]
  int v43; // [rsp+44h] [rbp-2Dh]
  __int64 v44; // [rsp+48h] [rbp-29h]
  volatile signed __int32 *v45; // [rsp+50h] [rbp-21h] BYREF
  __int64 v46; // [rsp+58h] [rbp-19h] BYREF
  _BYTE *v47; // [rsp+60h] [rbp-11h]
  __int64 *v48; // [rsp+68h] [rbp-9h]
  PVOID *v49; // [rsp+70h] [rbp-1h]
  PVOID Entry; // [rsp+78h] [rbp+7h]

  v5 = a5;
  v6 = 0;
  v7 = 0;
  v47 = a4;
  v8 = 0;
  v49 = a1;
  Entry = 0;
  v10 = 0;
  v48 = a3;
  v46 = 0;
  v11 = a1;
  v45 = 0;
  v43 = 0;
  if ( !a1 || !a3 )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_93;
    v15 = 111;
    v41 = -1073741811;
    goto LABEL_85;
  }
  *a3 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 1) == 0 )
    goto LABEL_93;
  v12 = *(_DWORD *)(MpData + 868) & 0x40;
  v13 = v12 != 0;
  if ( (a2 & 0x8000) == 0 )
  {
    if ( !v12 )
      goto LABEL_93;
    a2 >>= 24;
    if ( (a2 & 2) == 0 )
      goto LABEL_93;
  }
  if ( a5 )
  {
    Entry = a5;
    v5 = 0;
LABEL_13:
    v44 = 0x8000;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      BYTE2(v44) = 64;
      BYTE4(v44) = 1;
    }
    BYTE3(v44) = 2 * (v13 | (2 * (v13 | (2 * (v13 | (8 * (v13 | (2 * v13))))))));
    matched = MpRegMatchData(Entry, 0, v44, &v46);
    v7 = matched;
    if ( matched < 0 )
    {
      if ( matched == -1073741198 )
      {
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          113,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          matched);
      }
      v6 = v46;
      goto LABEL_86;
    }
    v6 = v46;
    if ( !v46 )
    {
      v7 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          (unsigned int)(v46 + 114),
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          -1073741823);
      goto LABEL_86;
    }
    IsRegistryHardeningExemptByContext = 0;
    v42 = 0;
    if ( (*(_BYTE *)(v46 + 26) & 0x40) != 0 || (*(_BYTE *)(v46 + 28) & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v45);
      v8 = v45;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v45);
      v42 = IsRegistryHardeningExemptByContext;
    }
    if ( (*(_BYTE *)(v6 + 26) & 0x40) != 0 )
    {
      v43 = 1;
      if ( !v8 || IsRegistryHardeningExemptByContext )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v8 )
            v19 = *((_QWORD *)v8 + 16);
          else
            v19 = 0;
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 116, (_DWORD)v11, (_DWORD)Entry, v19);
        }
        *(_BYTE *)(v6 + 26) &= ~0x40u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 115, (_DWORD)v11, (_DWORD)Entry, *((_QWORD *)v8 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry key replace of [%wZ] triggered by process [%wZ].",
          Entry,
          *((_QWORD *)v8 + 16));
        *v47 = 1;
        *(_BYTE *)(v6 + 25) |= 0x80u;
      }
    }
    v20 = MpRegTPAllowChange(v6 + 24, Entry, &v45);
    v8 = v45;
    if ( v20 )
    {
      v26 = v43;
      v25 = v47;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v45 )
          v23 = *((_QWORD *)v45 + 16);
        else
          v23 = 0;
        WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 117, v21, (_DWORD)Entry, v23);
      }
      if ( v8 )
        v24 = *((_QWORD *)v8 + 16);
      else
        v24 = 0;
      MpLogPrintfW(L"[Mini-filter][TP] Denied registry replace to [%wZ] triggered by process [%wZ].", Entry, v24);
      v25 = v47;
      v26 = 2;
      v43 = 2;
      *v47 = 1;
      *(_BYTE *)(v6 + 25) |= 0x80u;
    }
    if ( *v25 == 1 )
      *(_BYTE *)(v6 + 26) |= 0x40u;
    if ( v26 )
    {
      if ( v26 == 2 && v8 && (v8[15] & 0x200) != 0 )
      {
        LOBYTE(v25) = *v25 == 0;
        MpTraceRegHardeningNotification(
          3,
          (_DWORD)v25,
          (_DWORD)v8,
          (unsigned int)"RegNtPreReplaceKey",
          (__int64)Entry,
          0,
          0);
        v25 = v47;
      }
      LOBYTE(v25) = *v25 == 0;
      MpTraceRegHardeningNotification(
        (v43 == 2) + 1,
        (_DWORD)v25,
        (_DWORD)v8,
        (unsigned int)"RegNtPreReplaceKey",
        (__int64)Entry,
        0,
        0);
    }
    if ( *(char *)(v6 + 27) < 0 )
    {
      IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v45, v25, v21, v22);
      v28 = (int)Entry;
      v8 = v45;
      LOBYTE(v28) = IsTamperProtectedLevelExempt;
      MpTraceRegHardeningNotification(4, v28, (_DWORD)v45, (unsigned int)"RegNtPreReplaceKey", (__int64)Entry, 0, 0);
    }
    if ( (*(_BYTE *)(v6 + 28) & 1) != 0 )
    {
      LOBYTE(v25) = v42;
      MpTraceRegHardeningNotification(
        5,
        (_DWORD)v25,
        (_DWORD)v8,
        (unsigned int)"RegNtPreReplaceKey",
        (__int64)Entry,
        0,
        0);
    }
    if ( *v47 )
    {
      v32 = (PVOID *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
      v10 = v32;
      if ( v32 )
      {
        memset(v32, 0, 0x78u);
        v33 = v49;
        v10[1] = Entry;
        v10[4] = v33[1];
        v10[5] = v33[2];
        *v10 = *v33;
        v10[12] = (PVOID)v6;
        v10[11] = *(PVOID *)(v6 + 24);
        *((_DWORD *)v10 + 26) = v43;
        v7 = MpRegpSendNotification((__int64)v8, (__int64)v10, v34);
        if ( v7 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          v15 = 120;
          v41 = v7;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_86;
      v15 = 119;
    }
    else
    {
      v29 = MpRegpAllocRenameKeyContext();
      v30 = v29;
      if ( v29 )
      {
        *(_QWORD *)(v29 + 48) = 0;
        *(_QWORD *)(v29 + 40) = Entry;
        v31 = v48;
        Entry = 0;
        *(_QWORD *)(v30 + 56) = v6;
        v6 = 0;
        *v31 = v30;
        goto LABEL_86;
      }
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_86;
      v15 = 118;
    }
    v41 = -1073741670;
    goto LABEL_85;
  }
  KeyName = MpRegpGetKeyName(*v11);
  v7 = KeyName;
  if ( KeyName >= 0 )
    goto LABEL_13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    _mm_lfence();
    v15 = 112;
    v41 = KeyName;
LABEL_85:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      v41);
  }
LABEL_86:
  v35 = Entry;
  if ( Entry )
  {
    v36 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
    if ( v36 )
    {
      v36(Entry);
    }
    else
    {
      v37 = (void *)*((_QWORD *)Entry + 2);
      if ( v37 )
        ExFreePoolWithTag(v37, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v35);
    }
    Entry = 0;
  }
LABEL_93:
  if ( v5 )
  {
    v38 = (void (__fastcall *)(_QWORD *, unsigned __int64, PVOID *))*((_QWORD *)MpRegData + 5);
    if ( v38 )
    {
      v38(v5, a2, v11);
    }
    else
    {
      v39 = (void *)v5[2];
      if ( v39 )
        ExFreePoolWithTag(v39, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v5);
    }
  }
  if ( v6 )
    MpRegFreeMatchingInfo((PVOID)v6);
  if ( v10 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v10);
  if ( v8 )
    MpReleaseProcessContext(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14007ea68  push    rbp
0x14007ea6a  push    rbx
0x14007ea6b  push    rsi
0x14007ea6c  push    rdi
0x14007ea6d  push    r12
0x14007ea6f  push    r13
0x14007ea71  push    r14
0x14007ea73  lea     rbp, [rsp-1Fh]
0x14007ea78  sub     rsp, 90h
0x14007ea7f  mov     rax, cs:__security_cookie
0x14007ea86  xor     rax, rsp
0x14007ea89  mov     [rbp+4Fh+var_40], rax
0x14007ea8d  mov     r13, [rbp+4Fh+arg_20]
0x14007ea91  xor     ebx, ebx
0x14007ea93  xor     r14d, r14d
0x14007ea96  mov     [rbp+4Fh+var_60], r9
0x14007ea9a  xor     esi, esi
0x14007ea9c  mov     [rbp+4Fh+var_50], rcx
0x14007eaa0  mov     rax, r8
0x14007eaa3  mov     [rbp+4Fh+Entry], r14
0x14007eaa7  xor     r12d, r12d
0x14007eaaa  mov     [rbp+4Fh+var_58], rax
0x14007eaae  mov     [rbp+4Fh+var_68], rbx
0x14007eab2  mov     r8, rcx
0x14007eab5  mov     [rbp+4Fh+var_70], rsi
0x14007eab9  mov     [rbp+4Fh+var_7C], ebx
0x14007eabc  test    rcx, rcx
0x14007eabf  jz      loc_14007F017
0x14007eac5  test    rax, rax
0x14007eac8  jz      loc_14007F017
0x14007eace  mov     [rax], rbx
0x14007ead1  mov     rcx, cs:MpData
0x14007ead8  mov     eax, [rcx+360h]
0x14007eade  test    al, 1
0x14007eae0  jz      loc_14007F0C8
0x14007eae6  mov     ecx, [rcx+364h]
0x14007eaec  mov     rax, rdx
0x14007eaef  and     ecx, 40h
0x14007eaf2  setnz   dil
0x14007eaf6  shr     rax, 8
0x14007eafa  test    al, al
0x14007eafc  js      short loc_14007EB13
0x14007eafe  test    ecx, ecx
0x14007eb00  jz      loc_14007F0C8
0x14007eb06  shr     rdx, 18h
0x14007eb0a  test    dl, 2
0x14007eb0d  jz      loc_14007F0C8
0x14007eb13  test    r13, r13
0x14007eb16  jnz     short loc_14007EB5E
0x14007eb18  mov     rcx, [r8]; Object
0x14007eb1b  lea     rdx, [rbp+4Fh+Entry]
0x14007eb1f  call    MpRegpGetKeyName
0x14007eb24  mov     r14d, eax
0x14007eb27  test    eax, eax
0x14007eb29  jns     short loc_14007EB65
0x14007eb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb32  lea     rdi, WPP_GLOBAL_Control
0x14007eb39  cmp     rcx, rdi
0x14007eb3c  jz      loc_14007F06C
0x14007eb42  mov     ecx, [rcx+2Ch]
0x14007eb45  test    cl, 4
0x14007eb48  jz      loc_14007F06C
0x14007eb4e  lfence
0x14007eb51  lea     edx, [r13+70h]
0x14007eb55  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14007eb59  jmp     loc_14007F04C
0x14007eb5e  mov     [rbp+4Fh+Entry], r13
0x14007eb62  xor     r13d, r13d
0x14007eb65  mov     rax, cs:MpData
0x14007eb6c  mov     [rbp+4Fh+var_78], rbx
0x14007eb70  mov     byte ptr [rbp+4Fh+var_78+1], 80h
0x14007eb74  mov     ecx, [rax+364h]
0x14007eb7a  test    cl, 8
0x14007eb7d  jz      short loc_14007EB87
0x14007eb7f  or      byte ptr [rbp+4Fh+var_78+2], 40h
0x14007eb83  or      byte ptr [rbp+4Fh+var_78+4], 1
0x14007eb87  mov     al, byte ptr [rbp+4Fh+var_78+3]
0x14007eb8a  lea     r9, [rbp+4Fh+var_68]
0x14007eb8e  mov     cl, dil
0x14007eb91  and     al, 31h
0x14007eb93  add     cl, cl
0x14007eb95  xor     edx, edx
0x14007eb97  or      cl, dil
0x14007eb9a  shl     cl, 3
0x14007eb9d  or      cl, dil
0x14007eba0  add     cl, cl
0x14007eba2  or      cl, dil
0x14007eba5  add     cl, cl
0x14007eba7  or      cl, dil
0x14007ebaa  add     cl, cl
0x14007ebac  or      cl, al
0x14007ebae  mov     byte ptr [rbp+4Fh+var_78+3], cl
0x14007ebb1  mov     r8, [rbp+4Fh+var_78]
0x14007ebb5  mov     rcx, [rbp+4Fh+Entry]
0x14007ebb9  call    MpRegMatchData
0x14007ebbe  mov     r14d, eax
0x14007ebc1  test    eax, eax
0x14007ebc3  jns     short loc_14007EC21
0x14007ebc5  cmp     eax, 0C0000272h
0x14007ebca  jnz     short loc_14007EBD1
0x14007ebcc  xor     r14d, r14d
0x14007ebcf  jmp     short loc_14007EC18
0x14007ebd1  mov     rax, cs:WPP_GLOBAL_Control
0x14007ebd8  lea     rdi, WPP_GLOBAL_Control
0x14007ebdf  cmp     rax, rdi
0x14007ebe2  jz      short loc_14007EC18
0x14007ebe4  mov     eax, [rax+2Ch]
0x14007ebe7  test    al, 1
0x14007ebe9  jz      short loc_14007EC18
0x14007ebeb  lfence
0x14007ebee  mov     r9, gs:188h
0x14007ebf7  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007ebfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec05  mov     edx, 71h ; 'q'
0x14007ec0a  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x14007ec0f  mov     rcx, [rcx+18h]
0x14007ec13  call    WPP_SF_qD
0x14007ec18  mov     rbx, [rbp+4Fh+var_68]
0x14007ec1c  jmp     loc_14007F06C
0x14007ec21  mov     rbx, [rbp+4Fh+var_68]
0x14007ec25  test    rbx, rbx
0x14007ec28  jnz     short loc_14007EC82
0x14007ec2a  mov     r14d, 0C0000001h
0x14007ec30  mov     rax, cs:WPP_GLOBAL_Control
0x14007ec37  lea     rdi, WPP_GLOBAL_Control
0x14007ec3e  cmp     rax, rdi
0x14007ec41  jz      loc_14007F06C
0x14007ec47  mov     eax, [rax+2Ch]
0x14007ec4a  test    al, 1
0x14007ec4c  jz      loc_14007F06C
0x14007ec52  mov     r9, gs:188h
0x14007ec5b  lea     edx, [rbx+72h]
0x14007ec5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec65  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007ec6c  mov     dword ptr [rsp+0C0h+var_A0], 0C0000001h
0x14007ec74  mov     rcx, [rcx+18h]
0x14007ec78  call    WPP_SF_qD
0x14007ec7d  jmp     loc_14007F06C
0x14007ec82  xor     dl, dl
0x14007ec84  test    byte ptr [rbx+1Ah], 40h
0x14007ec88  mov     [rbp+4Fh+var_80], dl
0x14007ec8b  jnz     short loc_14007EC93
0x14007ec8d  test    byte ptr [rbx+1Ch], 1
0x14007ec91  jz      short loc_14007ECBC
0x14007ec93  call    cs:__imp_IoGetCurrentProcess
0x14007ec9a  nop     dword ptr [rax+rax+00h]
0x14007ec9f  mov     rcx, rax; Process
0x14007eca2  lea     rdx, [rbp+4Fh+var_70]
0x14007eca6  call    MpGetProcessContextByObject
0x14007ecab  mov     rsi, [rbp+4Fh+var_70]
0x14007ecaf  mov     rcx, rsi
0x14007ecb2  call    MpIsRegistryHardeningExemptByContext
0x14007ecb7  mov     dl, al
0x14007ecb9  mov     [rbp+4Fh+var_80], al
0x14007ecbc  test    byte ptr [rbx+1Ah], 40h
0x14007ecc0  lea     rdi, WPP_GLOBAL_Control
0x14007ecc7  jz      loc_14007ED70
0x14007eccd  mov     [rbp+4Fh+var_7C], 1
0x14007ecd4  test    rsi, rsi
0x14007ecd7  jz      short loc_14007ED32
0x14007ecd9  test    dl, dl
0x14007ecdb  jnz     short loc_14007ED32
0x14007ecdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ece4  cmp     rcx, rdi
0x14007ece7  jz      short loc_14007ED0E
0x14007ece9  mov     eax, [rcx+2Ch]
0x14007ecec  test    al, 2
0x14007ecee  jz      short loc_14007ED0E
0x14007ecf0  mov     rax, [rsi+80h]
0x14007ecf7  mov     edx, 73h ; 's'
0x14007ecfc  mov     r9, [rbp+4Fh+Entry]
0x14007ed00  mov     rcx, [rcx+18h]
0x14007ed04  mov     [rsp+0C0h+var_A0], rax
0x14007ed09  call    WPP_SF_ZZ
0x14007ed0e  mov     r8, [rsi+80h]
0x14007ed15  lea     rcx, aMiniFilterDeni_13; "[Mini-filter] Denied registry key repla"...
0x14007ed1c  mov     rdx, [rbp+4Fh+Entry]
0x14007ed20  call    MpLogPrintfW
0x14007ed25  mov     rax, [rbp+4Fh+var_60]
0x14007ed29  mov     byte ptr [rax], 1
0x14007ed2c  or      byte ptr [rbx+19h], 80h
0x14007ed30  jmp     short loc_14007ED70
0x14007ed32  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed39  cmp     rcx, rdi
0x14007ed3c  jz      short loc_14007ED6C
0x14007ed3e  mov     eax, [rcx+2Ch]
0x14007ed41  test    al, 4
0x14007ed43  jz      short loc_14007ED6C
0x14007ed45  test    rsi, rsi
0x14007ed48  jz      short loc_14007ED53
0x14007ed4a  mov     rax, [rsi+80h]
0x14007ed51  jmp     short loc_14007ED55
0x14007ed53  xor     eax, eax
0x14007ed55  mov     r9, [rbp+4Fh+Entry]
0x14007ed59  mov     edx, 74h ; 't'
0x14007ed5e  mov     rcx, [rcx+18h]
0x14007ed62  mov     [rsp+0C0h+var_A0], rax
0x14007ed67  call    WPP_SF_ZZ
0x14007ed6c  and     byte ptr [rbx+1Ah], 0BFh
0x14007ed70  mov     rdx, [rbp+4Fh+Entry]
0x14007ed74  lea     rcx, [rbx+18h]
0x14007ed78  lea     r8, [rbp+4Fh+var_70]
0x14007ed7c  call    MpRegTPAllowChange
0x14007ed81  mov     rsi, [rbp+4Fh+var_70]
0x14007ed85  test    al, al
0x14007ed87  jnz     short loc_14007EDF9
0x14007ed89  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed90  cmp     rcx, rdi
0x14007ed93  jz      short loc_14007EDC3
0x14007ed95  mov     eax, [rcx+2Ch]
0x14007ed98  test    al, 2
0x14007ed9a  jz      short loc_14007EDC3
0x14007ed9c  test    rsi, rsi
0x14007ed9f  jz      short loc_14007EDAA
0x14007eda1  mov     rax, [rsi+80h]
0x14007eda8  jmp     short loc_14007EDAC
0x14007edaa  xor     eax, eax
0x14007edac  mov     r9, [rbp+4Fh+Entry]
0x14007edb0  mov     edx, 75h ; 'u'
0x14007edb5  mov     rcx, [rcx+18h]
0x14007edb9  mov     [rsp+0C0h+var_A0], rax
0x14007edbe  call    WPP_SF_ZZ
0x14007edc3  test    rsi, rsi
0x14007edc6  jz      short loc_14007EDD1
0x14007edc8  mov     r8, [rsi+80h]
0x14007edcf  jmp     short loc_14007EDD4
0x14007edd1  xor     r8d, r8d
0x14007edd4  mov     rdx, [rbp+4Fh+Entry]
0x14007edd8  lea     rcx, aMiniFilterTpDe_1; "[Mini-filter][TP] Denied registry repla"...
0x14007eddf  call    MpLogPrintfW
0x14007ede4  mov     rdx, [rbp+4Fh+var_60]
0x14007ede8  mov     ecx, 2
0x14007eded  mov     [rbp+4Fh+var_7C], ecx
0x14007edf0  mov     byte ptr [rdx], 1
0x14007edf3  or      byte ptr [rbx+19h], 80h
0x14007edf7  jmp     short loc_14007EE00
0x14007edf9  mov     ecx, [rbp+4Fh+var_7C]
0x14007edfc  mov     rdx, [rbp+4Fh+var_60]
0x14007ee00  cmp     byte ptr [rdx], 1
0x14007ee03  jnz     short loc_14007EE09
0x14007ee05  or      byte ptr [rbx+1Ah], 40h
0x14007ee09  test    ecx, ecx
0x14007ee0b  jz      short loc_14007EE84
0x14007ee0d  cmp     ecx, 2
0x14007ee10  jnz     short loc_14007EE51
0x14007ee12  test    rsi, rsi
0x14007ee15  jz      short loc_14007EE51
0x14007ee17  test    dword ptr [rsi+3Ch], 200h
0x14007ee1e  jz      short loc_14007EE51
0x14007ee20  cmp     [rdx], r12b
0x14007ee23  lea     r9, aRegntprereplac; "RegNtPreReplaceKey"
0x14007ee2a  mov     rax, [rbp+4Fh+Entry]
0x14007ee2e  mov     r8, rsi
0x14007ee31  mov     [rsp+0C0h+var_90], r12
0x14007ee36  setz    dl
0x14007ee39  mov     [rsp+0C0h+var_98], r12
0x14007ee3e  mov     ecx, 3
0x14007ee43  mov     [rsp+0C0h+var_A0], rax
0x14007ee48  call    MpTraceRegHardeningNotification
0x14007ee4d  mov     rdx, [rbp+4Fh+var_60]
0x14007ee51  cmp     [rdx], r12b
0x14007ee54  lea     r9, aRegntprereplac; "RegNtPreReplaceKey"
0x14007ee5b  mov     rax, [rbp+4Fh+Entry]
0x14007ee5f  mov     r8, rsi
0x14007ee62  setz    dl
0x14007ee65  mov     [rsp+0C0h+var_90], r12
0x14007ee6a  xor     ecx, ecx
0x14007ee6c  mov     [rsp+0C0h+var_98], r12
0x14007ee71  cmp     [rbp+4Fh+var_7C], 2
0x14007ee75  mov     [rsp+0C0h+var_A0], rax
0x14007ee7a  setz    cl
0x14007ee7d  inc     ecx
0x14007ee7f  call    MpTraceRegHardeningNotification
0x14007ee84  cmp     [rbx+1Bh], r12b
0x14007ee88  jge     short loc_14007EEC0
0x14007ee8a  lea     rcx, [rbp+4Fh+var_70]
0x14007ee8e  call    MpRegIsTamperProtectedLevelExempt
0x14007ee93  mov     rdx, [rbp+4Fh+Entry]
0x14007ee97  lea     r9, aRegntprereplac; "RegNtPreReplaceKey"
0x14007ee9e  mov     rsi, [rbp+4Fh+var_70]
0x14007eea2  mov     ecx, 4
0x14007eea7  mov     [rsp+0C0h+var_90], r12
0x14007eeac  mov     r8, rsi
0x14007eeaf  mov     [rsp+0C0h+var_98], r12
0x14007eeb4  mov     [rsp+0C0h+var_A0], rdx
0x14007eeb9  mov     dl, al
0x14007eebb  call    MpTraceRegHardeningNotification
0x14007eec0  test    byte ptr [rbx+1Ch], 1
0x14007eec4  jz      short loc_14007EEF0
0x14007eec6  mov     rax, [rbp+4Fh+Entry]
0x14007eeca  lea     r9, aRegntprereplac; "RegNtPreReplaceKey"
0x14007eed1  mov     dl, [rbp+4Fh+var_80]
0x14007eed4  mov     r8, rsi
0x14007eed7  mov     [rsp+0C0h+var_90], r12
0x14007eedc  mov     ecx, 5
0x14007eee1  mov     [rsp+0C0h+var_98], r12
0x14007eee6  mov     [rsp+0C0h+var_A0], rax
0x14007eeeb  call    MpTraceRegHardeningNotification
0x14007eef0  mov     rax, [rbp+4Fh+var_60]
0x14007eef4  cmp     [rax], r12b
  ... truncated ...
```
