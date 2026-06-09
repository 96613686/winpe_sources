# MpRegPreDeleteValueKey

- ea: `0x14004a930`
- end: `0x14004b4ca`
- name: `MpRegPreDeleteValueKey`
- size: `2970`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x1400064b0`
- `0x14000d060`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x1400493f0`
- `0x140049680`
- `0x14004a758`
- `0x14004a930`
- `0x14004b6d0`
- `0x14004c630`
- `0x14004f59c`
- `0x14004f6bc`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14004abfa`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004af3c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004abfa`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004af3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004aa66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b45b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b48a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004aa66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b45b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b48a`

## string_xrefs

- `0x14004ade1`: `RegNtPreDeleteValueKey`
- `0x14004b1d3`: `RegNtPreDeleteValueKey`
- `0x14004b227`: `RegNtPreDeleteValueKey`
- `0x14004b25a`: `RegNtPreDeleteValueKey`
- `0x14004afb6`: `[Mini-filter] Denied registry keyvalue delete of [%wZ@%wZ] triggered by process [%wZ].`
- `0x14004b078`: `[Mini-filter][TP] Denied registry value delete [%wZ\%wZ] triggered by process [%wZ].`
- `0x14004b16f`: `[Mini-filter][TPv2] %ls registry value delete [%wZ\%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreDeleteValueKey(_QWORD *a1, unsigned __int64 a2, __int64 *a3, char *a4, _QWORD *a5)
{
  _QWORD *v5; // r15
  int KeyName; // ebx
  void *v8; // rsi
  __int64 v9; // r14
  _DWORD *v10; // r12
  volatile signed __int32 *v11; // r13
  PVOID v12; // rdi
  void (__fastcall *v13)(PVOID); // rax
  char v15; // dl
  int matched; // eax
  int v17; // r8d
  char v18; // al
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // r10d
  int v23; // ecx
  struct _KPROCESS *v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rax
  __int64 v29; // rdx
  char v30; // al
  unsigned __int64 v31; // rdx
  struct _KPROCESS *CurrentProcess; // rax
  unsigned __int8 IsRegistryHardeningExemptByContext; // al
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r9
  const wchar_t *v37; // rdx
  __int64 v38; // r8
  const wchar_t *v39; // r9
  __int64 v40; // rcx
  unsigned __int8 IsTamperProtectedLevelExempt; // al
  __int64 v42; // r8
  _QWORD *v43; // rcx
  void *v44; // rcx
  void (__fastcall *v45)(_QWORD *); // rax
  void *v46; // rcx
  int v47; // [rsp+20h] [rbp-71h]
  bool v48; // [rsp+40h] [rbp-51h]
  char v49; // [rsp+40h] [rbp-51h]
  bool v50; // [rsp+41h] [rbp-50h]
  unsigned __int8 v51; // [rsp+41h] [rbp-50h]
  int v52; // [rsp+44h] [rbp-4Dh]
  __int64 v53; // [rsp+48h] [rbp-49h]
  volatile signed __int32 *v55; // [rsp+58h] [rbp-39h] BYREF
  __int64 v56; // [rsp+60h] [rbp-31h] BYREF
  void *v57; // [rsp+68h] [rbp-29h]
  _DWORD *v58; // [rsp+70h] [rbp-21h] BYREF
  int v59; // [rsp+78h] [rbp-19h] BYREF
  PVOID v60; // [rsp+80h] [rbp-11h]
  __int64 *v61; // [rsp+88h] [rbp-9h]
  PVOID Entry; // [rsp+90h] [rbp-1h]

  v5 = a5;
  v61 = a3;
  Entry = 0;
  KeyName = 0;
  v57 = 0;
  v8 = 0;
  v60 = 0;
  v9 = 0;
  v56 = 0;
  v10 = 0;
  v58 = 0;
  v11 = 0;
  v55 = 0;
  v59 = 0;
  v52 = 0;
  if ( !a1 )
  {
    if ( a3 )
      *a3 = 0;
LABEL_66:
    KeyName = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v29 = 78;
      v47 = -1073741811;
LABEL_69:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v29,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        v47);
      goto LABEL_7;
    }
    goto LABEL_11;
  }
  if ( !a3 )
    goto LABEL_66;
  *a3 = 0;
  v50 = (*(_DWORD *)(MpData + 868) & 0x40) != 0;
  v48 = (*(_DWORD *)(MpData + 868) & 0x200) != 0;
  if ( (a2 & 0x800) != 0
    || (*(_DWORD *)(MpData + 868) & 0x40) != 0 && (a2 & 0x2000000) != 0
    || (*(_DWORD *)(MpData + 868) & 0x200) != 0 && ((v31 = a2 >> 24, (v31 & 0x10) != 0) || (v31 & 0x20) != 0) )
  {
    if ( a5 )
    {
      Entry = a5;
      v5 = 0;
    }
    else
    {
      KeyName = MpRegpGetKeyName((PVOID)*a1);
      if ( KeyName < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          v29 = 79;
          v47 = KeyName;
          goto LABEL_69;
        }
LABEL_7:
        v12 = Entry;
        if ( Entry )
        {
          v13 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
          if ( v13 )
          {
            v13(Entry);
          }
          else
          {
            v44 = (void *)*((_QWORD *)Entry + 2);
            if ( v44 )
              ExFreePoolWithTag(v44, 0x4B72504Du);
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v12);
          }
          Entry = 0;
        }
        goto LABEL_11;
      }
    }
    KeyName = MpRegpCopyUnicodeString((PCUNICODE_STRING)a1[1]);
    if ( KeyName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          80,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          KeyName);
      }
      v8 = v57;
      goto LABEL_7;
    }
    v53 = 2048;
    v15 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      BYTE2(v53) = 16;
      v15 = 1;
    }
    v8 = v57;
    BYTE4(v53) = v15 | 2;
    BYTE3(v53) = 2 * (v50 | (2 * (v50 | (2 * (v50 | (2 * (v48 | (2 * (v48 | (2 * (v50 | (2 * v50))))))))))));
    matched = MpRegMatchData(Entry, v57, v53, &v56);
    KeyName = matched;
    if ( matched < 0 )
    {
      if ( matched == -1073741198 )
      {
        v9 = v56;
        KeyName = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            81,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            matched);
        }
        v9 = v56;
      }
      goto LABEL_7;
    }
    v9 = v56;
    if ( !v56 )
    {
      KeyName = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          82,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          -1073741823);
      goto LABEL_7;
    }
    LOBYTE(v17) = 0;
    v51 = 0;
    if ( (*(_BYTE *)(v56 + 26) & 0x10) != 0 || (*(_BYTE *)(v56 + 28) & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v55);
      v11 = v55;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v55);
      v17 = IsRegistryHardeningExemptByContext;
      v51 = IsRegistryHardeningExemptByContext;
    }
    if ( (*(_BYTE *)(v9 + 26) & 0x10) != 0 )
    {
      v52 = 1;
      if ( !v11 || (_BYTE)v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v11 )
            v34 = *((_QWORD *)v11 + 16);
          else
            v34 = 0;
          WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 84, v17, (_DWORD)Entry, a1[1], v34);
        }
        *(_BYTE *)(v9 + 26) &= ~0x10u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 83, v17, (_DWORD)Entry, a1[1], *((_QWORD *)v11 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry keyvalue delete of [%wZ@%wZ] triggered by process [%wZ].",
          Entry,
          a1[1],
          *((_QWORD *)v11 + 16));
        *a4 = 1;
        *(_BYTE *)(v9 + 25) = *(_BYTE *)(v9 + 25) & 0xC7 | 8;
      }
    }
    v18 = MpRegTPAllowChange(v9 + 24, Entry, &v55);
    v11 = v55;
    v22 = 2;
    if ( v18 )
    {
      v23 = v52;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v55 )
          v35 = *((_QWORD *)v55 + 16);
        else
          v35 = 0;
        WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 85, v20, (_DWORD)Entry, a1[1], v35);
      }
      if ( v11 )
        v36 = *((_QWORD *)v11 + 16);
      else
        v36 = 0;
      MpLogPrintfW(
        L"[Mini-filter][TP] Denied registry value delete [%wZ\\%wZ] triggered by process [%wZ].",
        Entry,
        a1[1],
        v36);
      v22 = 2;
      v23 = 2;
      v52 = 2;
      *a4 = 1;
      *(_BYTE *)(v9 + 25) = *(_BYTE *)(v9 + 25) & 0xC7 | 8;
    }
    v49 = 0;
    if ( (*(_BYTE *)(v9 + 27) & 0x30) == 0 )
      goto LABEL_47;
    if ( !v11 )
    {
      v24 = IoGetCurrentProcess();
      MpGetProcessContextByObject(v24, &v55);
      v11 = v55;
      if ( !v55 )
      {
LABEL_118:
        v37 = L"Denied";
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          if ( v11 )
            v38 = *((_QWORD *)v11 + 16);
          else
            v38 = 0;
          v39 = L"Denied";
          if ( (*(_BYTE *)(v9 + 27) & 0x10) == 0 )
            v39 = L"Ignored";
          WPP_SF_SZZZ(WPP_GLOBAL_Control->AttachedDevice, 86, v38, (_DWORD)v39, (__int64)Entry, a1[1], v38);
          v37 = L"Denied";
        }
        if ( v11 )
          v40 = *((_QWORD *)v11 + 16);
        else
          v40 = 0;
        if ( (*(_BYTE *)(v9 + 27) & 0x10) == 0 )
          v37 = L"Ignored";
        MpLogPrintfW(
          L"[Mini-filter][TPv2] %ls registry value delete [%wZ\\%wZ] triggered by process [%wZ].",
          v37,
          Entry,
          a1[1],
          v40);
        v22 = 2;
        if ( (*(_BYTE *)(v9 + 27) & 0x10) == 0 )
          goto LABEL_117;
        v23 = 2;
        v52 = 2;
        *a4 = 1;
        *(_BYTE *)(v9 + 25) = *(_BYTE *)(v9 + 25) & 0xC7 | 8;
LABEL_47:
        v25 = a4;
        if ( *a4 == 1 )
          *(_BYTE *)(v9 + 26) |= 0x10u;
        if ( v23 )
        {
          if ( v23 == 2 && v11 && (v25 = a4, (v11[15] & 0x200) != 0) )
          {
            LOBYTE(v19) = *a4 == 0;
            MpTraceRegHardeningNotification(
              3,
              v19,
              (_DWORD)v11,
              (unsigned int)"RegNtPreDeleteValueKey",
              (__int64)Entry,
              0,
              (__int64)v8);
            v22 = 2;
            v30 = *a4;
          }
          else
          {
            v30 = *v25;
            if ( v23 != 2 )
              v22 = 1;
          }
          LOBYTE(v19) = v30 == 0;
          MpTraceRegHardeningNotification(
            v22,
            v19,
            (_DWORD)v11,
            (unsigned int)"RegNtPreDeleteValueKey",
            (__int64)Entry,
            0,
            (__int64)v8);
        }
        if ( *(char *)(v9 + 27) < 0 )
        {
          IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v55, v19, v20, v21);
          v11 = v55;
          MpTraceRegHardeningNotification(
            4,
            IsTamperProtectedLevelExempt,
            (_DWORD)v55,
            (unsigned int)"RegNtPreDeleteValueKey",
            (__int64)Entry,
            0,
            (__int64)v8);
        }
        if ( (*(_BYTE *)(v9 + 28) & 1) != 0 )
          MpTraceRegHardeningNotification(
            5,
            v51,
            (_DWORD)v11,
            (unsigned int)"RegNtPreDeleteValueKey",
            (__int64)Entry,
            0,
            (__int64)v8);
        if ( *(_BYTE *)(v9 + 16) == 1 )
        {
          KeyName = MpRegpQueryValueKeyByPointer(*a1, v8, &v59, &v58);
          if ( (int)(KeyName + 0x80000000) >= 0 && KeyName != -1073741772 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                87,
                WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                KeGetCurrentThread(),
                KeyName);
            }
            v10 = v58;
            goto LABEL_7;
          }
          v10 = v58;
        }
        if ( *a4 != 1 )
        {
          v26 = MpRegpAllocDeleteValueContext();
          v27 = v26;
          if ( v26 )
          {
            *(_QWORD *)(v26 + 64) = v9;
            *(_QWORD *)(v26 + 40) = Entry;
            *(_BYTE *)(v26 + 72) = v49;
            v28 = v61;
            *(_QWORD *)(v27 + 48) = v8;
            *(_QWORD *)(v27 + 56) = v10;
            Entry = 0;
            *v28 = v27;
            goto LABEL_20;
          }
          KeyName = -1073741670;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_7;
          }
          v29 = 90;
          v47 = -1073741670;
          goto LABEL_69;
        }
        v60 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
        if ( v60 )
        {
          memset(v60, 0, 0x78u);
          v43 = v60;
          *((_QWORD *)v60 + 12) = v9;
          v43[1] = Entry;
          v43[2] = v8;
          *v43 = *a1;
          v43[11] = *(_QWORD *)(v9 + 24);
          *((_BYTE *)v43 + 108) = v49;
          *((_DWORD *)v43 + 26) = v52;
          if ( v10 )
          {
            *((_DWORD *)v43 + 13) = v10[2];
            v43[7] = v10 + 3;
            *((_DWORD *)v43 + 12) = v10[1];
          }
          KeyName = MpRegpSendNotification((__int64)v11, (__int64)v43, v42);
          if ( KeyName >= 0
            || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_7;
          }
          _mm_lfence();
          v29 = 89;
          v47 = KeyName;
          goto LABEL_69;
        }
        KeyName = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v29 = 88;
          v47 = -1073741670;
          goto LABEL_69;
        }
        goto LABEL_7;
      }
      v23 = v52;
      v22 = 2;
    }
    if ( (v11[15] & 0x20) != 0 )
    {
LABEL_46:
      v49 = 1;
      goto LABEL_47;
    }
    if ( (*(_DWORD *)(MpData + 868) & 0x80000) != 0 && *((_DWORD *)v11 + 60) == 19 )
    {
      v23 = v52;
      goto LABEL_46;
    }
    if ( (v11[73] & 0xF) != 1 && !*((_DWORD *)v11 + 74) )
    {
      v49 = 1;
LABEL_117:
      v23 = v52;
      goto LABEL_47;
    }
    goto LABEL_118;
  }
LABEL_11:
  if ( v5 )
  {
    v45 = (void (__fastcall *)(_QWORD *))*((_QWORD *)MpRegData + 5);
    if ( v45 )
    {
      v45(v5);
    }
    else
    {
      v46 = (void *)v5[2];
      if ( v46 )
        ExFreePoolWithTag(v46, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v5);
    }
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x5364504Du);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x5672504Du);
  if ( v9 )
    MpRegFreeMatchingInfo((PVOID)v9);
  if ( v60 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v60);
LABEL_20:
  if ( v11 )
    MpReleaseProcessContext(v11);
  return (unsigned int)KeyName;
}

```

## disassembly

```asm
0x14004a930  push    rbp
0x14004a932  push    rbx
0x14004a933  push    rsi
0x14004a934  push    rdi
0x14004a935  push    r12
0x14004a937  push    r13
0x14004a939  push    r14
0x14004a93b  push    r15
0x14004a93d  lea     rbp, [rsp-17h]
0x14004a942  sub     rsp, 0A8h
0x14004a949  mov     rax, cs:__security_cookie
0x14004a950  xor     rax, rsp
0x14004a953  mov     [rbp+4Fh+var_48], rax
0x14004a957  mov     r15, [rbp+4Fh+arg_20]
0x14004a95b  mov     rax, r8
0x14004a95e  mov     [rbp+4Fh+var_90], r9
0x14004a962  mov     rdi, rcx
0x14004a965  xor     r9d, r9d
0x14004a968  mov     [rbp+4Fh+var_58], rax
0x14004a96c  mov     [rbp+4Fh+Entry], r9
0x14004a970  mov     ebx, r9d
0x14004a973  mov     [rbp+4Fh+var_78], r9
0x14004a977  mov     esi, r9d
0x14004a97a  mov     [rbp+4Fh+var_60], r9
0x14004a97e  mov     r14d, r9d
0x14004a981  mov     [rbp+4Fh+var_80], r9
0x14004a985  mov     r12d, r9d
0x14004a988  mov     [rbp+4Fh+var_70], r9
0x14004a98c  mov     r13d, r9d
0x14004a98f  mov     [rbp+4Fh+var_88], r9
0x14004a993  mov     [rbp+4Fh+var_68], r9d
0x14004a997  mov     [rbp+4Fh+var_9C], r9d
0x14004a99b  test    rcx, rcx
0x14004a99e  jz      loc_14004AD33
0x14004a9a4  test    rax, rax
0x14004a9a7  jz      loc_14004AD3C
0x14004a9ad  mov     [r8], r9
0x14004a9b0  mov     rax, cs:MpData
0x14004a9b7  mov     ecx, [rax+364h]
0x14004a9bd  mov     rax, cs:MpData
0x14004a9c4  and     ecx, 40h
0x14004a9c7  setnz   [rbp+4Fh+var_9F]
0x14004a9cb  mov     r8d, [rax+364h]
0x14004a9d2  mov     rax, rdx
0x14004a9d5  and     r8d, 200h
0x14004a9dc  setnz   [rbp+4Fh+var_A0]
0x14004a9e0  shr     rax, 8
0x14004a9e4  test    al, 8
0x14004a9e6  jz      loc_14004AE05
0x14004a9ec  test    r15, r15
0x14004a9ef  jnz     loc_14004AABD
0x14004a9f5  mov     rcx, [rdi]; Object
0x14004a9f8  lea     rdx, [rbp+4Fh+Entry]
0x14004a9fc  call    MpRegpGetKeyName
0x14004aa01  mov     ebx, eax
0x14004aa03  test    eax, eax
0x14004aa05  jns     loc_14004AAC4
0x14004aa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa12  lea     rax, WPP_GLOBAL_Control
0x14004aa19  cmp     rcx, rax
0x14004aa1c  jnz     loc_14004AE3C
0x14004aa22  mov     rdi, [rbp+4Fh+Entry]
0x14004aa26  test    rdi, rdi
0x14004aa29  jz      short loc_14004AA50
0x14004aa2b  mov     rax, cs:MpRegData
0x14004aa32  mov     rax, [rax+28h]
0x14004aa36  test    rax, rax
0x14004aa39  jz      loc_14004B3FA
0x14004aa3f  mov     rcx, rdi
0x14004aa42  call    cs:__guard_dispatch_icall_fptr
0x14004aa48  mov     [rbp+4Fh+Entry], 0
0x14004aa50  test    r15, r15
0x14004aa53  jnz     loc_14004B42F
0x14004aa59  test    rsi, rsi
0x14004aa5c  jz      short loc_14004AA72
0x14004aa5e  mov     edx, 5364504Dh; Tag
0x14004aa63  mov     rcx, rsi; P
0x14004aa66  call    cs:__imp_ExFreePoolWithTag
0x14004aa6d  nop     dword ptr [rax+rax+00h]
0x14004aa72  test    r12, r12
0x14004aa75  jnz     loc_14004B482
0x14004aa7b  test    r14, r14
0x14004aa7e  jnz     loc_14004B49B
0x14004aa84  mov     rdx, [rbp+4Fh+var_60]; Entry
0x14004aa88  test    rdx, rdx
0x14004aa8b  jnz     loc_14004B4A8
0x14004aa91  test    r13, r13
0x14004aa94  jnz     loc_14004B4BD
0x14004aa9a  mov     eax, ebx
0x14004aa9c  mov     rcx, [rbp+4Fh+var_48]
0x14004aaa0  xor     rcx, rsp; StackCookie
0x14004aaa3  call    __security_check_cookie
0x14004aaa8  add     rsp, 0A8h
0x14004aaaf  pop     r15
0x14004aab1  pop     r14
0x14004aab3  pop     r13
0x14004aab5  pop     r12
0x14004aab7  pop     rdi
0x14004aab8  pop     rsi
0x14004aab9  pop     rbx
0x14004aaba  pop     rbp
0x14004aabb  retn
0x14004aabd  mov     [rbp+4Fh+Entry], r15
0x14004aac1  mov     r15, r9
0x14004aac4  mov     rcx, [rdi+8]; SourceString
0x14004aac8  lea     rdx, [rbp+4Fh+var_78]
0x14004aacc  call    MpRegpCopyUnicodeString
0x14004aad1  mov     ebx, eax
0x14004aad3  test    eax, eax
0x14004aad5  js      loc_14004AB68
0x14004aadb  mov     rax, cs:MpData
0x14004aae2  mov     [rbp+4Fh+var_98], rsi
0x14004aae6  movzx   edx, byte ptr [rbp+4Fh+var_98+4]
0x14004aaea  mov     byte ptr [rbp+4Fh+var_98+1], 8
0x14004aaee  mov     ecx, [rax+364h]
0x14004aaf4  test    cl, 8
0x14004aaf7  jz      short loc_14004AB00
0x14004aaf9  or      byte ptr [rbp+4Fh+var_98+2], 10h
0x14004aafd  or      dl, 1
0x14004ab00  movzx   eax, [rbp+4Fh+var_9F]
0x14004ab04  lea     r9, [rbp+4Fh+var_80]
0x14004ab08  mov     rsi, [rbp+4Fh+var_78]
0x14004ab0c  movzx   ecx, al
0x14004ab0f  add     cl, cl
0x14004ab11  or      dl, 2
0x14004ab14  or      cl, al
0x14004ab16  mov     byte ptr [rbp+4Fh+var_98+4], dl
0x14004ab19  add     cl, cl
0x14004ab1b  mov     rdx, rsi
0x14004ab1e  or      cl, [rbp+4Fh+var_A0]
0x14004ab21  add     cl, cl
0x14004ab23  or      cl, [rbp+4Fh+var_A0]
0x14004ab26  add     cl, cl
0x14004ab28  or      cl, al
0x14004ab2a  add     cl, cl
0x14004ab2c  or      cl, al
0x14004ab2e  add     cl, cl
0x14004ab30  or      cl, al
0x14004ab32  movzx   eax, byte ptr [rbp+4Fh+var_98+3]
0x14004ab36  add     cl, cl
0x14004ab38  and     al, 1
0x14004ab3a  or      cl, al
0x14004ab3c  mov     byte ptr [rbp+4Fh+var_98+3], cl
0x14004ab3f  mov     r8, [rbp+4Fh+var_98]
0x14004ab43  mov     rcx, [rbp+4Fh+Entry]
0x14004ab47  call    MpRegMatchData
0x14004ab4c  mov     ebx, eax
0x14004ab4e  test    eax, eax
0x14004ab50  jns     short loc_14004AB88
0x14004ab52  cmp     eax, 0C0000272h
0x14004ab57  jnz     loc_14004AE94
0x14004ab5d  mov     r14, [rbp+4Fh+var_80]
0x14004ab61  xor     ebx, ebx
0x14004ab63  jmp     loc_14004AA22
0x14004ab68  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab6f  lea     rax, WPP_GLOBAL_Control
0x14004ab76  cmp     rcx, rax
0x14004ab79  jnz     loc_14004AE58
0x14004ab7f  mov     rsi, [rbp+4Fh+var_78]
0x14004ab83  jmp     loc_14004AA22
0x14004ab88  mov     r14, [rbp+4Fh+var_80]
0x14004ab8c  test    r14, r14
0x14004ab8f  jz      loc_14004AEE3
0x14004ab95  xor     r8b, r8b
0x14004ab98  test    byte ptr [r14+1Ah], 10h
0x14004ab9d  mov     [rbp+4Fh+var_9F], r8b
0x14004aba1  jnz     loc_14004AF3C
0x14004aba7  test    byte ptr [r14+1Ch], 1
0x14004abac  jnz     loc_14004AF3C
0x14004abb2  test    byte ptr [r14+1Ah], 10h
0x14004abb7  lea     rax, WPP_GLOBAL_Control
0x14004abbe  jnz     loc_14004AD02
0x14004abc4  mov     rdx, [rbp+4Fh+Entry]
0x14004abc8  lea     rcx, [r14+18h]
0x14004abcc  lea     r8, [rbp+4Fh+var_88]
0x14004abd0  call    MpRegTPAllowChange
0x14004abd5  mov     r13, [rbp+4Fh+var_88]
0x14004abd9  mov     r10d, 2
0x14004abdf  test    al, al
0x14004abe1  jz      loc_14004B018
0x14004abe7  mov     ecx, [rbp+4Fh+var_9C]
0x14004abea  test    byte ptr [r14+1Bh], 30h
0x14004abef  mov     [rbp+4Fh+var_A0], r12b
0x14004abf3  jz      short loc_14004AC5C
0x14004abf5  test    r13, r13
0x14004abf8  jnz     short loc_14004AC28
0x14004abfa  call    cs:__imp_IoGetCurrentProcess
0x14004ac01  nop     dword ptr [rax+rax+00h]
0x14004ac06  mov     rcx, rax; Process
0x14004ac09  lea     rdx, [rbp+4Fh+var_88]
0x14004ac0d  call    MpGetProcessContextByObject
0x14004ac12  mov     r13, [rbp+4Fh+var_88]
0x14004ac16  test    r13, r13
0x14004ac19  jz      loc_14004B0D1
0x14004ac1f  mov     ecx, [rbp+4Fh+var_9C]
0x14004ac22  mov     r10d, 2
0x14004ac28  mov     eax, [r13+3Ch]
0x14004ac2c  test    al, 20h
0x14004ac2e  jnz     short loc_14004AC58
0x14004ac30  mov     rax, cs:MpData
0x14004ac37  mov     ecx, [rax+364h]
0x14004ac3d  bt      ecx, 13h
0x14004ac41  jnb     loc_14004B0AD
0x14004ac47  cmp     dword ptr [r13+0F0h], 13h
0x14004ac4f  jnz     loc_14004B0AD
0x14004ac55  mov     ecx, [rbp+4Fh+var_9C]
0x14004ac58  mov     [rbp+4Fh+var_A0], 1
0x14004ac5c  mov     rax, [rbp+4Fh+var_90]
0x14004ac60  cmp     byte ptr [rax], 1
0x14004ac63  jz      loc_14004B1AB
0x14004ac69  test    ecx, ecx
0x14004ac6b  jnz     loc_14004ADC1
0x14004ac71  cmp     [r14+1Bh], r12b
0x14004ac75  jl      loc_14004B21A
0x14004ac7b  test    byte ptr [r14+1Ch], 1
0x14004ac80  jnz     loc_14004B256
0x14004ac86  cmp     byte ptr [r14+10h], 1
0x14004ac8b  jnz     short loc_14004ACB5
0x14004ac8d  mov     rcx, [rdi]
0x14004ac90  lea     r9, [rbp+4Fh+var_70]
0x14004ac94  lea     r8, [rbp+4Fh+var_68]
0x14004ac98  mov     rdx, rsi
0x14004ac9b  call    MpRegpQueryValueKeyByPointer
0x14004aca0  mov     ecx, 80000000h
0x14004aca5  mov     ebx, eax
0x14004aca7  add     eax, ecx
0x14004aca9  test    ecx, eax
0x14004acab  jz      loc_14004AD95
0x14004acb1  mov     r12, [rbp+4Fh+var_70]
0x14004acb5  mov     rax, [rbp+4Fh+var_90]
0x14004acb9  cmp     byte ptr [rax], 1
0x14004acbc  jz      loc_14004B2C2
0x14004acc2  call    MpRegpAllocDeleteValueContext
0x14004acc7  mov     rcx, rax
0x14004acca  test    rax, rax
0x14004accd  jz      loc_14004B3B9
0x14004acd3  mov     [rax+40h], r14
0x14004acd7  mov     rax, [rbp+4Fh+Entry]
0x14004acdb  mov     [rcx+28h], rax
0x14004acdf  movzx   eax, [rbp+4Fh+var_A0]
0x14004ace3  mov     [rcx+48h], al
0x14004ace6  mov     rax, [rbp+4Fh+var_58]
0x14004acea  mov     [rcx+30h], rsi
0x14004acee  mov     [rcx+38h], r12
0x14004acf2  mov     [rbp+4Fh+Entry], 0
0x14004acfa  mov     [rax], rcx
0x14004acfd  jmp     loc_14004AA91
0x14004ad02  mov     [rbp+4Fh+var_9C], 1
0x14004ad09  test    r13, r13
0x14004ad0c  jnz     loc_14004AF6C
0x14004ad12  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad19  cmp     rcx, rax
0x14004ad1c  jz      short loc_14004AD29
0x14004ad1e  mov     eax, [rcx+2Ch]
0x14004ad21  test    al, 4
0x14004ad23  jnz     loc_14004AFE3
0x14004ad29  and     byte ptr [r14+1Ah], 0EFh
0x14004ad2e  jmp     loc_14004ABC4
0x14004ad33  test    rax, rax
0x14004ad36  jnz     loc_14004B3F2
0x14004ad3c  mov     ebx, 0C000000Dh
0x14004ad41  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad48  lea     rax, WPP_GLOBAL_Control
0x14004ad4f  cmp     rcx, rax
0x14004ad52  jz      loc_14004AA50
0x14004ad58  mov     eax, [rcx+2Ch]
0x14004ad5b  test    al, 1
0x14004ad5d  jz      loc_14004AA50
0x14004ad63  mov     edx, 4Eh ; 'N'
0x14004ad68  mov     dword ptr [rsp+0E0h+var_C0], 0C000000Dh
0x14004ad70  mov     r9, gs:188h
0x14004ad79  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004ad80  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad87  mov     rcx, [rcx+18h]
0x14004ad8b  call    WPP_SF_qD
0x14004ad90  jmp     loc_14004AA22
0x14004ad95  cmp     ebx, 0C0000034h
0x14004ad9b  jz      loc_14004ACB1
0x14004ada1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ada8  lea     rax, WPP_GLOBAL_Control
0x14004adaf  cmp     rcx, rax
0x14004adb2  jnz     loc_14004B286
0x14004adb8  mov     r12, [rbp+4Fh+var_70]
0x14004adbc  jmp     loc_14004AA22
0x14004adc1  cmp     ecx, 2
0x14004adc4  jz      loc_14004B1B5
0x14004adca  movzx   eax, byte ptr [rax]
0x14004adcd  cmp     ecx, 2
0x14004add0  jnz     loc_14004B20F
0x14004add6  test    al, al
0x14004add8  mov     [rsp+0E0h+var_B0], rsi
0x14004addd  mov     rax, [rbp+4Fh+Entry]
0x14004ade1  lea     r9, aRegntpredelete_0; "RegNtPreDeleteValueKey"
0x14004ade8  setz    dl
0x14004adeb  mov     [rsp+0E0h+var_B8], r12
0x14004adf0  mov     r8, r13
0x14004adf3  mov     [rsp+0E0h+var_C0], rax
0x14004adf8  mov     ecx, r10d
0x14004adfb  call    MpTraceRegHardeningNotification
0x14004ae00  jmp     loc_14004AC71
  ... truncated ...
```
