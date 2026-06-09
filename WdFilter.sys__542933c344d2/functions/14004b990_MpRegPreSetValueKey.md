# MpRegPreSetValueKey

- ea: `0x14004b990`
- end: `0x14004c621`
- name: `MpRegPreSetValueKey`
- size: `3217`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x1400064b0`
- `0x140007eec`
- `0x14000d060`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x1400493f0`
- `0x14004a700`
- `0x14004a758`
- `0x14004b6d0`
- `0x14004b990`
- `0x14004c630`
- `0x14004f59c`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14004bcd9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004be15`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004bcd9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004be15`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004bbe2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004bbe2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c569`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c569`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5eb`

## string_xrefs

- `0x14004bed4`: `[Mini-filter] Denied registry access to [%wZ@%wZ] triggered by process [%wZ].`
- `0x14004c192`: `[Mini-filter][TP] Denied registry value change [%wZ\%wZ] triggered by process [%wZ].`
- `0x14004c262`: `[Mini-filter][TPv2] %ls registry value change [%wZ\%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreSetValueKey(PVOID *a1, unsigned __int64 a2, __int64 *a3, _BYTE *a4, _QWORD *a5)
{
  _QWORD *v5; // r14
  PVOID *v7; // r10
  int KeyName; // esi
  _BYTE *v9; // rdi
  PVOID v10; // rbx
  _DWORD *v11; // r13
  volatile signed __int32 *v12; // r15
  bool v13; // r9
  bool v14; // r11
  char v15; // dl
  int v16; // r8d
  PVOID v17; // rbx
  void (__fastcall *v18)(PVOID); // rax
  NTSTATUS v20; // eax
  PVOID *v21; // rbx
  unsigned __int8 IsRegistryHardeningExemptByContext; // dl
  char v23; // al
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // r9
  __int64 v27; // r8
  struct _KPROCESS *v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v33; // rax
  int v34; // ecx
  unsigned __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  int matched; // eax
  __int64 v39; // rax
  __int64 v40; // r9
  const wchar_t *v41; // rdx
  __int64 v42; // r8
  const wchar_t *v43; // r9
  __int64 v44; // rcx
  unsigned __int8 IsTamperProtectedLevelExempt; // al
  PVOID v46; // rax
  __int64 v47; // rsi
  __int64 v48; // r8
  void *v49; // rcx
  void (__fastcall *v50)(_QWORD *); // rax
  void *v51; // rcx
  int v52; // [rsp+20h] [rbp-81h]
  bool v53; // [rsp+40h] [rbp-61h]
  char v54; // [rsp+40h] [rbp-61h]
  bool v55; // [rsp+41h] [rbp-60h]
  char v56; // [rsp+42h] [rbp-5Fh]
  unsigned __int8 v57; // [rsp+42h] [rbp-5Fh]
  unsigned int v58; // [rsp+44h] [rbp-5Dh]
  __int64 v59; // [rsp+48h] [rbp-59h]
  PVOID P; // [rsp+50h] [rbp-51h] BYREF
  PVOID *v61; // [rsp+58h] [rbp-49h]
  volatile signed __int32 *v62; // [rsp+60h] [rbp-41h] BYREF
  _BYTE *v63; // [rsp+68h] [rbp-39h]
  _DWORD *v64; // [rsp+70h] [rbp-31h] BYREF
  int v65; // [rsp+78h] [rbp-29h] BYREF
  PVOID v66; // [rsp+80h] [rbp-21h]
  PVOID Entry; // [rsp+88h] [rbp-19h]
  UNICODE_STRING SourceString; // [rsp+90h] [rbp-11h] BYREF

  v5 = a5;
  v63 = a4;
  v61 = a1;
  Entry = 0;
  v7 = a1;
  P = 0;
  KeyName = 0;
  v66 = 0;
  v9 = 0;
  v64 = 0;
  v10 = 0;
  v62 = 0;
  v11 = 0;
  v65 = 0;
  v12 = 0;
  v58 = 0;
  v56 = 0;
  SourceString = 0;
  if ( !a1 )
  {
    if ( a3 )
      *a3 = 0;
LABEL_165:
    KeyName = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v36 = 54;
      v52 = -1073741811;
      goto LABEL_168;
    }
    goto LABEL_18;
  }
  if ( !a3 )
    goto LABEL_165;
  *a3 = 0;
  v13 = (*(_DWORD *)(MpData + 868) & 0x40) != 0;
  v55 = v13;
  v14 = (*(_DWORD *)(MpData + 868) & 0x200) != 0;
  v53 = v14;
  if ( (a2 & 0x100) != 0
    || (*(_DWORD *)(MpData + 868) & 0x40) != 0 && (a2 & 0x2000000) != 0
    || (*(_DWORD *)(MpData + 868) & 0x200) != 0 && ((v35 = a2 >> 24, (v35 & 0x10) != 0) || (v35 & 0x20) != 0) )
  {
    if ( a5 )
    {
      Entry = a5;
      v5 = 0;
    }
    else
    {
      KeyName = MpRegpGetKeyName(*a1);
      if ( KeyName < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_13;
        v36 = 55;
LABEL_99:
        _mm_lfence();
        v52 = KeyName;
LABEL_168:
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v36,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          v52);
        goto LABEL_13;
      }
      v7 = v61;
      v13 = v55;
      v14 = v53;
    }
    if ( (*(_DWORD *)(MpData + 868) & 0x400) != 0 && *((_DWORD *)v7 + 5) == 6 )
    {
      if ( RtlCompareUnicodeString((PCUNICODE_STRING)v7[1], &RegSymLinkValue, 1u) )
      {
        v7 = v61;
      }
      else
      {
        SourceString.Buffer = (PWSTR)v61[3];
        SourceString.Length = *((_WORD *)v61 + 16);
        SourceString.MaximumLength = SourceString.Length;
        v20 = RtlUnicodeStringValidateWorker(&SourceString, 0x7FFFu, 0);
        if ( v20 >= 0 )
        {
          v56 = 1;
          v7 = v61;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              56,
              WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
              KeGetCurrentThread(),
              v20);
          }
          v7 = v61;
        }
      }
      v13 = v55;
      v14 = v53;
    }
    v59 = 256;
    v15 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      BYTE2(v59) = 32;
      v15 = 1;
    }
    BYTE4(v59) = v15 | 2;
    BYTE3(v59) = 2 * (v13 | (2 * (v13 | (2 * (v13 | (2 * (v14 | (2 * (v14 | (2 * (v13 | (2 * v13))))))))))));
    KeyName = MpRegMatchData(Entry, v7[1], v59, &P);
    if ( KeyName < 0 && !v56 )
    {
      if ( KeyName == -1073741198 )
      {
        v9 = P;
        KeyName = 0;
LABEL_13:
        v17 = Entry;
        if ( Entry )
        {
          v18 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
          if ( v18 )
          {
            v18(Entry);
          }
          else
          {
            v49 = (void *)*((_QWORD *)Entry + 2);
            if ( v49 )
              ExFreePoolWithTag(v49, 0x4B72504Du);
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v17);
          }
          Entry = 0;
        }
        v10 = v66;
        goto LABEL_18;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_107:
        v9 = P;
        goto LABEL_13;
      }
      v37 = 57;
LABEL_106:
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v37,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        KeyName);
      goto LABEL_107;
    }
    v9 = P;
    if ( P )
    {
      v21 = v61;
    }
    else
    {
      if ( !v56 )
      {
        KeyName = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            -1073741823);
        goto LABEL_13;
      }
      v21 = v61;
      matched = MpRegMatchData(&SourceString, v61[1], v59, &P);
      KeyName = matched;
      if ( matched < 0 )
      {
        if ( matched == -1073741198 )
        {
          v9 = P;
          KeyName = 0;
          goto LABEL_13;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_107;
        v37 = 58;
        goto LABEL_106;
      }
      v9 = P;
    }
    IsRegistryHardeningExemptByContext = 0;
    v57 = 0;
    if ( (v9[26] & 0x20) != 0 || (v9[28] & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v62);
      v12 = v62;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v62);
      v57 = IsRegistryHardeningExemptByContext;
    }
    if ( (v9[26] & 0x20) != 0 )
    {
      v58 = 1;
      if ( !v12 || IsRegistryHardeningExemptByContext )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v12 )
            v33 = *((_QWORD *)v12 + 16);
          else
            v33 = 0;
          WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 61, v16, (_DWORD)Entry, (__int64)v21[1], v33);
        }
        v9[26] &= ~0x20u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 60, v16, (_DWORD)Entry, (__int64)v21[1], *((_QWORD *)v12 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry access to [%wZ@%wZ] triggered by process [%wZ].",
          Entry,
          v21[1],
          *((_QWORD *)v12 + 16));
        *v63 = 1;
        v9[25] = v9[25] & 0xF8 | 1;
      }
    }
    v23 = MpRegTPAllowChange(v9 + 24, Entry, &v62);
    v12 = v62;
    v26 = 2;
    if ( v23 )
    {
      v27 = v58;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v62 )
          v39 = *((_QWORD *)v62 + 16);
        else
          v39 = 0;
        WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 62, v25, (_DWORD)Entry, (__int64)v21[1], v39);
      }
      if ( v12 )
        v40 = *((_QWORD *)v12 + 16);
      else
        v40 = 0;
      MpLogPrintfW(
        L"[Mini-filter][TP] Denied registry value change [%wZ\\%wZ] triggered by process [%wZ].",
        Entry,
        v21[1],
        v40);
      v26 = 2;
      v27 = 2;
      v58 = 2;
      *v63 = 1;
      v9[25] = v9[25] & 0xF8 | 1;
    }
    v54 = 0;
    if ( (v9[27] & 0x30) == 0 )
    {
LABEL_54:
      v29 = (__int64)v63;
      if ( *v63 == 1 )
        v9[26] |= 0x20u;
      if ( (_DWORD)v27 )
      {
        if ( (_DWORD)v27 == 2 && v12 && (v12[15] & 0x200) != 0 )
        {
          LOBYTE(v24) = *(_BYTE *)v29 == 0;
          MpTraceRegHardeningNotification(
            3,
            v24,
            (_DWORD)v12,
            (unsigned int)"RegNtPreSetValueKey",
            (__int64)Entry,
            0,
            (__int64)v21[1]);
          v29 = (__int64)v63;
          LODWORD(v27) = v58;
        }
        LOBYTE(v24) = *(_BYTE *)v29 == 0;
        v34 = 1;
        if ( (_DWORD)v27 == 2 )
          v34 = 2;
        MpTraceRegHardeningNotification(
          v34,
          v24,
          (_DWORD)v12,
          (unsigned int)"RegNtPreSetValueKey",
          (__int64)Entry,
          0,
          (__int64)v21[1]);
      }
      if ( (char)v9[27] < 0 )
      {
        IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v62, v24, v27, v26);
        v12 = v62;
        MpTraceRegHardeningNotification(
          4,
          IsTamperProtectedLevelExempt,
          (_DWORD)v62,
          (unsigned int)"RegNtPreSetValueKey",
          (__int64)Entry,
          0,
          (__int64)v21[1]);
      }
      if ( (v9[28] & 1) != 0 )
        MpTraceRegHardeningNotification(
          5,
          v57,
          (_DWORD)v12,
          (unsigned int)"RegNtPreSetValueKey",
          (__int64)Entry,
          0,
          (__int64)v21[1]);
      if ( v9[16] == 1 )
      {
        v30 = MpRegpQueryValueKeyByPointer(*v21, v21[1], &v65, &v64);
        v29 = 0x80000000LL;
        KeyName = v30;
        if ( (int)(v30 + 0x80000000) >= 0 && v30 != -1073741772 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              64,
              WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
              KeGetCurrentThread(),
              v30);
          }
          v11 = v64;
          goto LABEL_13;
        }
        v11 = v64;
      }
      if ( *v63 != 1 )
      {
        v31 = MpRegpAllocSetValueContext(v29, v24, v27, v26);
        if ( v31 )
        {
          *(_QWORD *)(v31 + 64) = v9;
          *(_QWORD *)(v31 + 40) = Entry;
          *(_QWORD *)(v31 + 48) = v11;
          *(_DWORD *)(v31 + 56) = *((_DWORD *)v21 + 5);
          *(_BYTE *)(v31 + 72) = v54;
          Entry = 0;
          *a3 = v31;
          goto LABEL_25;
        }
        KeyName = -1073741670;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_13;
        v36 = 67;
        v52 = -1073741670;
        goto LABEL_168;
      }
      v46 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
      v66 = v46;
      v47 = (__int64)v46;
      if ( !v46 )
      {
        KeyName = -1073741670;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_13;
        v36 = 65;
        v52 = -1073741670;
        goto LABEL_168;
      }
      memset(v46, 0, 0x78u);
      *(_QWORD *)(v47 + 96) = v9;
      *(_QWORD *)(v47 + 8) = Entry;
      *(_QWORD *)(v47 + 16) = v21[1];
      *(_QWORD *)v47 = *v21;
      *(_QWORD *)(v47 + 88) = *((_QWORD *)v9 + 3);
      *(_DWORD *)(v47 + 64) = *((_DWORD *)v21 + 5);
      *(_DWORD *)(v47 + 104) = v58;
      *(_BYTE *)(v47 + 108) = v54;
      if ( v9[16] == 1 )
      {
        *(_DWORD *)(v47 + 68) = *((_DWORD *)v21 + 8);
        *(_QWORD *)(v47 + 80) = v21[3];
        if ( v11 )
        {
          *(_DWORD *)(v47 + 52) = v11[2];
          *(_QWORD *)(v47 + 56) = v11 + 3;
          *(_DWORD *)(v47 + 48) = v11[1];
        }
      }
      KeyName = MpRegpSendNotification((__int64)v12, v47, v48);
      if ( KeyName >= 0
        || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
        goto LABEL_13;
      }
      v36 = 66;
      goto LABEL_99;
    }
    if ( !v12 )
    {
      v28 = IoGetCurrentProcess();
      MpGetProcessContextByObject(v28, &v62);
      v12 = v62;
      if ( !v62 )
        goto LABEL_128;
      v27 = v58;
      v26 = 2;
    }
    if ( (v12[15] & 0x20) != 0
      || (*(_DWORD *)(MpData + 868) & 0x80000) != 0 && *((_DWORD *)v12 + 60) == 19
      || (v12[73] & 0xF) != 1 && !*((_DWORD *)v12 + 74) )
    {
      v54 = 1;
      goto LABEL_54;
    }
LABEL_128:
    v41 = L"Denied";
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( v12 )
        v42 = *((_QWORD *)v12 + 16);
      else
        v42 = 0;
      v43 = L"Denied";
      if ( (v9[27] & 0x10) == 0 )
        v43 = L"Ignored";
      WPP_SF_SZZZ(WPP_GLOBAL_Control->AttachedDevice, 63, v42, (_DWORD)v43, (__int64)Entry, (__int64)v21[1], v42);
      v41 = L"Denied";
    }
    if ( v12 )
      v44 = *((_QWORD *)v12 + 16);
    else
      v44 = 0;
    if ( (v9[27] & 0x10) == 0 )
      v41 = L"Ignored";
    MpLogPrintfW(
      L"[Mini-filter][TPv2] %ls registry value change [%wZ\\%wZ] triggered by process [%wZ].",
      v41,
      Entry,
      v21[1],
      v44);
    v26 = 2;
    if ( (v9[27] & 0x10) != 0 )
    {
      v27 = 2;
      v58 = 2;
      *v63 = 1;
      v9[25] = v9[25] & 0xF8 | 1;
    }
    else
    {
      v27 = v58;
    }
    goto LABEL_54;
  }
LABEL_18:
  if ( v5 )
  {
    v50 = (void (__fastcall *)(_QWORD *))*((_QWORD *)MpRegData + 5);
    if ( v50 )
    {
      v50(v5);
    }
    else
    {
      v51 = (void *)v5[2];
      if ( v51 )
        ExFreePoolWithTag(v51, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v5);
    }
  }
  if ( v11 )
    ExFreePoolWithTag(v11, 0x5672504Du);
  if ( v9 )
    MpRegFreeMatchingInfo(v9);
  if ( v10 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v10);
LABEL_25:
  if ( v12 )
    MpReleaseProcessContext(v12);
  return (unsigned int)KeyName;
}

```

## disassembly

```asm
0x14004b990  push    rbp
0x14004b992  push    rbx
0x14004b993  push    rsi
0x14004b994  push    rdi
0x14004b995  push    r12
0x14004b997  push    r13
0x14004b999  push    r14
0x14004b99b  push    r15
0x14004b99d  lea     rbp, [rsp-17h]
0x14004b9a2  sub     rsp, 0B8h
0x14004b9a9  mov     rax, cs:__security_cookie
0x14004b9b0  xor     rax, rsp
0x14004b9b3  mov     [rbp+4Fh+var_50], rax
0x14004b9b7  mov     r14, [rbp+4Fh+arg_20]
0x14004b9bb  xor     eax, eax
0x14004b9bd  mov     [rbp+4Fh+var_88], r9
0x14004b9c1  xorps   xmm0, xmm0
0x14004b9c4  mov     [rbp+4Fh+var_98], rcx
0x14004b9c8  mov     r12, r8
0x14004b9cb  mov     [rbp+4Fh+Entry], rax
0x14004b9cf  mov     r10, rcx
0x14004b9d2  mov     [rbp+4Fh+P], rax
0x14004b9d6  mov     esi, eax
0x14004b9d8  mov     [rbp+4Fh+var_70], rax
0x14004b9dc  mov     edi, eax
0x14004b9de  mov     [rbp+4Fh+var_80], rax
0x14004b9e2  mov     ebx, eax
0x14004b9e4  mov     [rbp+4Fh+var_90], rax
0x14004b9e8  mov     r13d, eax
0x14004b9eb  mov     [rbp+4Fh+var_78], eax
0x14004b9ee  mov     r15d, eax
0x14004b9f1  mov     [rbp+4Fh+var_AC], eax
0x14004b9f4  mov     [rbp+4Fh+var_AE], al
0x14004b9f7  movups  xmmword ptr [rbp+4Fh+SourceString.Length], xmm0
0x14004b9fb  test    rcx, rcx
0x14004b9fe  jz      loc_14004C4FA
0x14004ba04  test    r8, r8
0x14004ba07  jz      loc_14004C502
0x14004ba0d  mov     [r8], rax
0x14004ba10  mov     rax, cs:MpData
0x14004ba17  mov     ecx, [rax+364h]
0x14004ba1d  mov     rax, cs:MpData
0x14004ba24  and     ecx, 40h
0x14004ba27  setnz   r9b
0x14004ba2b  mov     [rbp+4Fh+var_AF], r9b
0x14004ba2f  mov     r8d, [rax+364h]
0x14004ba36  mov     rax, rdx
0x14004ba39  and     r8d, 200h
0x14004ba40  setnz   r11b
0x14004ba44  shr     rax, 8
0x14004ba48  mov     [rbp+4Fh+var_B0], r11b
0x14004ba4c  test    al, 1
0x14004ba4e  jz      loc_14004BFE1
0x14004ba54  test    r14, r14
0x14004ba57  jz      loc_14004BB9E
0x14004ba5d  mov     [rbp+4Fh+Entry], r14
0x14004ba61  mov     r14, rsi
0x14004ba64  mov     rax, cs:MpData
0x14004ba6b  lea     rdi, WPP_GLOBAL_Control
0x14004ba72  mov     ecx, [rax+364h]
0x14004ba78  bt      ecx, 0Ah
0x14004ba7c  jb      loc_14004BBC9
0x14004ba82  mov     rax, cs:MpData
0x14004ba89  mov     [rbp+4Fh+var_A8], rsi
0x14004ba8d  movzx   edx, byte ptr [rbp+4Fh+var_A8+4]
0x14004ba91  mov     byte ptr [rbp+4Fh+var_A8+1], 1
0x14004ba95  mov     ecx, [rax+364h]
0x14004ba9b  test    cl, 8
0x14004ba9e  jz      short loc_14004BAA7
0x14004baa0  or      byte ptr [rbp+4Fh+var_A8+2], 20h
0x14004baa4  or      dl, 1
0x14004baa7  movzx   eax, byte ptr [rbp+4Fh+var_A8+3]
0x14004baab  movzx   ecx, r9b
0x14004baaf  add     cl, cl
0x14004bab1  or      dl, 2
0x14004bab4  or      cl, r9b
0x14004bab7  mov     byte ptr [rbp+4Fh+var_A8+4], dl
0x14004baba  mov     rdx, [r10+8]
0x14004babe  add     cl, cl
0x14004bac0  or      cl, r11b
0x14004bac3  and     al, 1
0x14004bac5  add     cl, cl
0x14004bac7  or      cl, r11b
0x14004baca  add     cl, cl
0x14004bacc  or      cl, r9b
0x14004bacf  add     cl, cl
0x14004bad1  or      cl, r9b
0x14004bad4  add     cl, cl
0x14004bad6  or      cl, r9b
0x14004bad9  lea     r9, [rbp+4Fh+P]
0x14004badd  add     cl, cl
0x14004badf  or      cl, al
0x14004bae1  mov     byte ptr [rbp+4Fh+var_A8+3], cl
0x14004bae4  mov     rbx, [rbp+4Fh+var_A8]
0x14004bae8  mov     rcx, [rbp+4Fh+Entry]
0x14004baec  mov     r8, rbx
0x14004baef  call    MpRegMatchData
0x14004baf4  mov     esi, eax
0x14004baf6  test    eax, eax
0x14004baf8  movzx   eax, [rbp+4Fh+var_AE]
0x14004bafc  jns     loc_14004BC6F
0x14004bb02  test    al, al
0x14004bb04  jnz     loc_14004BC6F
0x14004bb0a  cmp     esi, 0C0000272h
0x14004bb10  jnz     loc_14004C058
0x14004bb16  mov     rdi, [rbp+4Fh+P]
0x14004bb1a  xor     r12d, r12d
0x14004bb1d  mov     esi, r12d
0x14004bb20  mov     rbx, [rbp+4Fh+Entry]
0x14004bb24  test    rbx, rbx
0x14004bb27  jz      short loc_14004BB4A
0x14004bb29  mov     rax, cs:MpRegData
0x14004bb30  mov     rax, [rax+28h]
0x14004bb34  test    rax, rax
0x14004bb37  jz      loc_14004C55B
0x14004bb3d  mov     rcx, rbx
0x14004bb40  call    cs:__guard_dispatch_icall_fptr
0x14004bb46  mov     [rbp+4Fh+Entry], r12
0x14004bb4a  mov     rbx, [rbp+4Fh+var_70]
0x14004bb4e  test    r14, r14
0x14004bb51  jnz     loc_14004C590
0x14004bb57  test    r13, r13
0x14004bb5a  jnz     loc_14004C5E3
0x14004bb60  test    rdi, rdi
0x14004bb63  jnz     loc_14004C5FC
0x14004bb69  test    rbx, rbx
0x14004bb6c  jnz     loc_14004C609
0x14004bb72  test    r15, r15
0x14004bb75  jnz     loc_14004BEFF
0x14004bb7b  mov     eax, esi
0x14004bb7d  mov     rcx, [rbp+4Fh+var_50]
0x14004bb81  xor     rcx, rsp; StackCookie
0x14004bb84  call    __security_check_cookie
0x14004bb89  add     rsp, 0B8h
0x14004bb90  pop     r15
0x14004bb92  pop     r14
0x14004bb94  pop     r13
0x14004bb96  pop     r12
0x14004bb98  pop     rdi
0x14004bb99  pop     rsi
0x14004bb9a  pop     rbx
0x14004bb9b  pop     rbp
0x14004bb9c  retn
0x14004bb9e  mov     rcx, [r10]; Object
0x14004bba1  lea     rdx, [rbp+4Fh+Entry]
0x14004bba5  call    MpRegpGetKeyName
0x14004bbaa  mov     esi, eax
0x14004bbac  test    eax, eax
0x14004bbae  js      loc_14004BDF6
0x14004bbb4  mov     r10, [rbp+4Fh+var_98]
0x14004bbb8  xor     esi, esi
0x14004bbba  movzx   r9d, [rbp+4Fh+var_AF]
0x14004bbbf  movzx   r11d, [rbp+4Fh+var_B0]
0x14004bbc4  jmp     loc_14004BA64
0x14004bbc9  cmp     dword ptr [r10+14h], 6
0x14004bbce  jnz     loc_14004BA82
0x14004bbd4  mov     rcx, [r10+8]; String1
0x14004bbd8  lea     rdx, RegSymLinkValue; String2
0x14004bbdf  mov     r8b, 1; CaseInSensitive
0x14004bbe2  call    cs:__imp_RtlCompareUnicodeString
0x14004bbe9  nop     dword ptr [rax+rax+00h]
0x14004bbee  test    eax, eax
0x14004bbf0  jnz     loc_14004C045
0x14004bbf6  mov     rbx, [rbp+4Fh+var_98]
0x14004bbfa  lea     rcx, [rbp+4Fh+SourceString]; SourceString
0x14004bbfe  xor     r8d, r8d; dwFlags
0x14004bc01  mov     edx, 7FFFh; cchMax
0x14004bc06  mov     rax, [rbx+18h]
0x14004bc0a  mov     [rbp+4Fh+SourceString.Buffer], rax
0x14004bc0e  movzx   eax, word ptr [rbx+20h]
0x14004bc12  mov     [rbp+4Fh+SourceString.Length], ax
0x14004bc16  mov     [rbp+4Fh+SourceString.MaximumLength], ax
0x14004bc1a  call    RtlUnicodeStringValidateWorker
0x14004bc1f  test    eax, eax
0x14004bc21  jns     loc_14004C03C
0x14004bc27  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc2e  cmp     rcx, rdi
0x14004bc31  jz      short loc_14004BC67
0x14004bc33  mov     ecx, [rcx+2Ch]
0x14004bc36  test    cl, 2
0x14004bc39  jz      short loc_14004BC67
0x14004bc3b  lfence
0x14004bc3e  mov     r9, gs:188h
0x14004bc47  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004bc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc55  mov     edx, 38h ; '8'
0x14004bc5a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14004bc5e  mov     rcx, [rcx+18h]
0x14004bc62  call    WPP_SF_qD
0x14004bc67  mov     r10, rbx
0x14004bc6a  jmp     loc_14004C049
0x14004bc6f  mov     rdi, [rbp+4Fh+P]
0x14004bc73  test    rdi, rdi
0x14004bc76  jz      loc_14004C0A7
0x14004bc7c  mov     rbx, [rbp+4Fh+var_98]
0x14004bc80  xor     dl, dl
0x14004bc82  test    byte ptr [rdi+1Ah], 20h
0x14004bc86  mov     [rbp+4Fh+var_AE], dl
0x14004bc89  jnz     loc_14004BE15
0x14004bc8f  test    byte ptr [rdi+1Ch], 1
0x14004bc93  jnz     loc_14004BE15
0x14004bc99  test    byte ptr [rdi+1Ah], 20h
0x14004bc9d  jnz     loc_14004BE44
0x14004bca3  mov     rdx, [rbp+4Fh+Entry]
0x14004bca7  lea     rcx, [rdi+18h]
0x14004bcab  lea     r8, [rbp+4Fh+var_90]
0x14004bcaf  call    MpRegTPAllowChange
0x14004bcb4  mov     r15, [rbp+4Fh+var_90]
0x14004bcb8  mov     r9d, 2
0x14004bcbe  test    al, al
0x14004bcc0  jz      loc_14004C132
0x14004bcc6  mov     r8d, [rbp+4Fh+var_AC]
0x14004bcca  test    byte ptr [rdi+1Bh], 30h
0x14004bcce  mov     [rbp+4Fh+var_B0], r13b
0x14004bcd2  jz      short loc_14004BD51
0x14004bcd4  test    r15, r15
0x14004bcd7  jnz     short loc_14004BD08
0x14004bcd9  call    cs:__imp_IoGetCurrentProcess
0x14004bce0  nop     dword ptr [rax+rax+00h]
0x14004bce5  mov     rcx, rax; Process
0x14004bce8  lea     rdx, [rbp+4Fh+var_90]
0x14004bcec  call    MpGetProcessContextByObject
0x14004bcf1  mov     r15, [rbp+4Fh+var_90]
0x14004bcf5  test    r15, r15
0x14004bcf8  jz      loc_14004C1C6
0x14004bcfe  mov     r8d, [rbp+4Fh+var_AC]
0x14004bd02  mov     r9d, 2
0x14004bd08  mov     eax, [r15+3Ch]
0x14004bd0c  test    al, 20h
0x14004bd0e  jnz     short loc_14004BD4D
0x14004bd10  mov     rax, cs:MpData
0x14004bd17  mov     ecx, [rax+364h]
0x14004bd1d  bt      ecx, 13h
0x14004bd21  jnb     short loc_14004BD2D
0x14004bd23  cmp     dword ptr [r15+0F0h], 13h
0x14004bd2b  jz      short loc_14004BD4D
0x14004bd2d  mov     eax, [r15+124h]
0x14004bd34  and     al, 0Fh
0x14004bd36  cmp     al, 1
0x14004bd38  jz      loc_14004C1C6
0x14004bd3e  mov     eax, [r15+128h]
0x14004bd45  test    eax, eax
0x14004bd47  jnz     loc_14004C1C6
0x14004bd4d  mov     [rbp+4Fh+var_B0], 1
0x14004bd51  mov     rcx, [rbp+4Fh+var_88]
0x14004bd55  cmp     byte ptr [rcx], 1
0x14004bd58  jz      loc_14004C2A1
0x14004bd5e  test    r8d, r8d
0x14004bd61  jnz     loc_14004BF3B
0x14004bd67  cmp     [rdi+1Bh], r13b
0x14004bd6b  jl      loc_14004C30F
0x14004bd71  test    byte ptr [rdi+1Ch], 1
0x14004bd75  jnz     loc_14004C34F
0x14004bd7b  cmp     byte ptr [rdi+10h], 1
0x14004bd7f  jnz     short loc_14004BDAA
0x14004bd81  mov     rdx, [rbx+8]
0x14004bd85  lea     r9, [rbp+4Fh+var_80]
0x14004bd89  mov     rcx, [rbx]
0x14004bd8c  lea     r8, [rbp+4Fh+var_78]
0x14004bd90  call    MpRegpQueryValueKeyByPointer
0x14004bd95  mov     ecx, 80000000h
0x14004bd9a  mov     esi, eax
0x14004bd9c  add     eax, ecx
0x14004bd9e  test    ecx, eax
0x14004bda0  jz      loc_14004BF0C
0x14004bda6  mov     r13, [rbp+4Fh+var_80]
0x14004bdaa  mov     rax, [rbp+4Fh+var_88]
0x14004bdae  cmp     byte ptr [rax], 1
0x14004bdb1  jz      loc_14004C3BF
0x14004bdb7  call    MpRegpAllocSetValueContext
0x14004bdbc  mov     rcx, rax
0x14004bdbf  test    rax, rax
0x14004bdc2  jz      loc_14004C4C4
0x14004bdc8  mov     [rax+40h], rdi
0x14004bdcc  mov     rax, [rbp+4Fh+Entry]
0x14004bdd0  mov     [rcx+28h], rax
0x14004bdd4  mov     [rcx+30h], r13
0x14004bdd8  mov     eax, [rbx+14h]
0x14004bddb  mov     [rcx+38h], eax
0x14004bdde  movzx   eax, [rbp+4Fh+var_B0]
0x14004bde2  mov     [rcx+48h], al
0x14004bde5  mov     [rbp+4Fh+Entry], 0
0x14004bded  mov     [r12], rcx
0x14004bdf1  jmp     loc_14004BB72
0x14004bdf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bdfd  lea     rax, WPP_GLOBAL_Control
0x14004be04  cmp     rcx, rax
0x14004be07  jnz     loc_14004C018
0x14004be0d  xor     r12d, r12d
0x14004be10  jmp     loc_14004BB20
0x14004be15  call    cs:__imp_IoGetCurrentProcess
0x14004be1c  nop     dword ptr [rax+rax+00h]
0x14004be21  mov     rcx, rax; Process
0x14004be24  lea     rdx, [rbp+4Fh+var_90]
0x14004be28  call    MpGetProcessContextByObject
0x14004be2d  mov     r15, [rbp+4Fh+var_90]
0x14004be31  mov     rcx, r15
0x14004be34  call    MpIsRegistryHardeningExemptByContext
0x14004be39  movzx   edx, al
0x14004be3c  mov     [rbp+4Fh+var_AE], al
  ... truncated ...
```
