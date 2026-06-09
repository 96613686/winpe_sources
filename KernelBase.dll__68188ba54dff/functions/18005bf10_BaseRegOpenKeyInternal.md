# BaseRegOpenKeyInternal

- ea: `0x18005bf10`
- end: `0x18005caf7`
- name: `BaseRegOpenKeyInternal`
- size: `3047`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, int, PHANDLE, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b710`
- `0x18005e9c0`

## callees

- `0x18005bf10`
- `0x18005cb00`
- `0x18005cc40`
- `0x18005d6f0`
- `0x18005dd30`
- `0x18005e890`
- `0x1800a29f0`
- `0x1800c9270`
- `0x18012d119`
- `0x18012ffa4`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005c5c5`
- `ntdll!RtlFreeUnicodeString` at `0x18005c99c`
- `ntdll!RtlFreeUnicodeString` at `0x18005c5c5`
- `ntdll!RtlFreeUnicodeString` at `0x18005c99c`
- `ntdll!_wcsnicmp` at `0x18005c963`
- `ntdll!_wcsnicmp` at `0x180190165`
- `ntdll!_wcsnicmp` at `0x1801901f0`
- `ntdll!_wcsnicmp` at `0x18005c963`
- `ntdll!_wcsnicmp` at `0x180190165`
- `ntdll!_wcsnicmp` at `0x1801901f0`
- `ntdll!NtOpenKey` at `0x18005c197`
- `ntdll!NtOpenKey` at `0x18005c1ff`
- `ntdll!NtOpenKey` at `0x18005c59b`
- `ntdll!NtOpenKey` at `0x18005c764`
- `ntdll!NtOpenKey` at `0x18005c197`
- `ntdll!NtOpenKey` at `0x18005c1ff`
- `ntdll!NtOpenKey` at `0x18005c59b`
- `ntdll!NtOpenKey` at `0x18005c764`
- `ntdll!RtlNtStatusToDosError` at `0x18005c250`
- `ntdll!RtlNtStatusToDosError` at `0x18005c250`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c497`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c4b1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c501`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c51d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c535`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c65f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c67b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c6ce`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c6ea`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c702`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c497`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c4b1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c501`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c51d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c535`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c65f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c67b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c6ce`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c6ea`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005c702`
- `ntdll!NtClose` at `0x18005c7ba`
- `ntdll!NtClose` at `0x18005c7cc`
- `ntdll!NtClose` at `0x18005c91e`
- `ntdll!NtClose` at `0x18005caa7`
- `ntdll!NtClose` at `0x18005c7ba`
- `ntdll!NtClose` at `0x18005c7cc`
- `ntdll!NtClose` at `0x18005c91e`
- `ntdll!NtClose` at `0x18005caa7`
- `ntdll!NtQueryKey` at `0x18005c2d7`
- `ntdll!NtQueryKey` at `0x18005ca9c`
- `ntdll!NtQueryKey` at `0x1801901af`
- `ntdll!NtQueryKey` at `0x18005c2d7`
- `ntdll!NtQueryKey` at `0x18005ca9c`
- `ntdll!NtQueryKey` at `0x1801901af`
- `ntdll!RtlFreeHeap` at `0x18005c0fc`
- `ntdll!RtlFreeHeap` at `0x18005c5b7`
- `ntdll!RtlFreeHeap` at `0x18005c780`
- `ntdll!RtlFreeHeap` at `0x18005c798`
- `ntdll!RtlFreeHeap` at `0x18005c7eb`
- `ntdll!RtlFreeHeap` at `0x18005c8ab`
- `ntdll!RtlFreeHeap` at `0x18005c8c8`
- `ntdll!RtlFreeHeap` at `0x18005ca06`
- `ntdll!RtlFreeHeap` at `0x18005c0fc`
- `ntdll!RtlFreeHeap` at `0x18005c5b7`
- `ntdll!RtlFreeHeap` at `0x18005c780`
- `ntdll!RtlFreeHeap` at `0x18005c798`
- `ntdll!RtlFreeHeap` at `0x18005c7eb`
- `ntdll!RtlFreeHeap` at `0x18005c8ab`
- `ntdll!RtlFreeHeap` at `0x18005c8c8`
- `ntdll!RtlFreeHeap` at `0x18005ca06`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c312`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c34a`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c37f`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c3f9`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c312`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c34a`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c37f`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005c3f9`
- `ntdll!RtlAllocateHeap` at `0x18005c2ab`
- `ntdll!RtlAllocateHeap` at `0x18005c46b`
- `ntdll!RtlAllocateHeap` at `0x18005c633`
- `ntdll!RtlAllocateHeap` at `0x18005c2ab`
- `ntdll!RtlAllocateHeap` at `0x18005c46b`
- `ntdll!RtlAllocateHeap` at `0x18005c633`
- `ntdll!NtOpenKeyEx` at `0x18005c0da`
- `ntdll!NtOpenKeyEx` at `0x18005c0da`
- `ntdll!NtSetInformationKey` at `0x18005c909`
- `ntdll!NtSetInformationKey` at `0x18005c909`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005c9e4`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005c9e4`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvOpenRegEntry` at `0x18005c5eb`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvOpenRegEntry` at `0x18005c5eb`

## string_xrefs

- `0x18005c30b`: `\Registry\Machine\`
- `0x18005c343`: `\Registry\Machine\`
- `0x18005c378`: `\Registry\User\`

## pseudocode

```c
ULONG __fastcall BaseRegOpenKeyInternal(
        HANDLE KeyHandle,
        UNICODE_STRING *Source,
        int a3,
        unsigned int a4,
        int a5,
        _QWORD *KeyHandlea,
        __int64 a7)
{
  HANDLE v10; // rsi
  UNICODE_STRING v11; // xmm6
  __int64 v12; // rbx
  USHORT v13; // ax
  int v14; // eax
  int KeySemantics; // ebx
  int v16; // r15d
  char v17; // al
  char v18; // al
  ULONG v20; // eax
  unsigned __int16 *Heap; // r15
  NTSTATUS CurrentUserSid; // ebx
  unsigned __int16 *v23; // rax
  void *v24; // rbx
  unsigned __int16 v25; // bx
  bool v26; // dl
  __int16 v27; // cx
  __int64 *v28; // r8
  USHORT v29; // bx
  WCHAR *v30; // rax
  __int16 v31; // ax
  USHORT v32; // bx
  WCHAR *v33; // rax
  int v34; // edx
  int v35; // eax
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  unsigned __int16 v38[2]; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG Length; // [rsp+44h] [rbp-2B4h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-2A0h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-298h] BYREF
  struct _OBJECT_ATTRIBUTES v43; // [rsp+70h] [rbp-288h] BYREF
  ULONG v44; // [rsp+A0h] [rbp-258h] BYREF
  ULONG ResultLength; // [rsp+A4h] [rbp-254h] BYREF
  struct _OBJECT_ATTRIBUTES v46; // [rsp+A8h] [rbp-250h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-220h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-218h] BYREF
  _BYTE v49[400]; // [rsp+110h] [rbp-1E8h] BYREF

  v10 = KeyHandle;
  v47 = a7;
  memset(&v46, 0, 44);
  if ( !Source || Source->Length < 2u || (Source->Length & 1) != 0 || !Source->Buffer || (v11 = *Source, !KeyHandlea) )
  {
    KeySemantics = -1073741811;
    return RtlNtStatusToDosError(KeySemantics);
  }
  v12 = 0;
  *KeyHandlea = 0;
  v13 = Source->Length - 2;
  Source->Length = v13;
  v46.Length = 48;
  v46.RootDirectory = KeyHandle;
  if ( (a3 & 8) != 0 )
    v46.Attributes = 320;
  else
    v46.Attributes = 64;
  v46.ObjectName = Source;
  *(_OWORD *)&v46.SecurityDescriptor = 0;
  if ( ((unsigned __int8)KeyHandle & 2) != 0 )
    goto LABEL_83;
  if ( (g_RegKrnGlobalState & 2) != 0 )
  {
    v44 = 0;
    if ( v13 >= 0xEu )
    {
      if ( !_wcsnicmp(Source->Buffer, L"Classes\\", 7u) && (Source->Length <= 0xEu || Source->Buffer[7] == 92)
        || Source->Length >= 0x20u
        && !_wcsnicmp(Source->Buffer, L"Software\\Classes\\", 0x10u)
        && ((v12 = 1, Source->Length <= 0x20u) || Source->Buffer[16] == 92) )
      {
        if ( NtQueryKey(v10, KeyNameInformation, &dword_18039EA18, 0x3Eu, &v44) >= 0
          && dword_18039EA18 == (unsigned __int16)word_1802DA628[v12]
          && !_wcsnicmp(&word_18039EA1C, off_180276EF0[v12], (unsigned __int16)word_1802DA630[v12])
          && (::Handle || !(unsigned int)OpenClassesRootInternal(v36, 0x2000000, &::Handle, a7)) )
        {
          v37 = (unsigned __int16)word_1802DA62C[v12];
          if ( Source->Length > (unsigned __int16)v37 )
          {
            Source->Length -= v37;
            Source->MaximumLength -= v37;
            Source->Buffer += v37 >> 1;
          }
          else
          {
            Source->Length = 0;
          }
          v10 = ::Handle;
LABEL_83:
          memset_0(v49, 0, 0x182u);
          *(_QWORD *)(&ObjectAttributes.Length + 1) = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)v49;
          HIDWORD(ObjectAttributes.RootDirectory) = 386;
          ObjectAttributes.Length = 0;
          KeySemantics = BaseRegGetKeySemantics(v10, Source);
          if ( KeySemantics >= 0 )
          {
            KeySemantics = BaseRegOpenClassKeyFromLocation(&ObjectAttributes, v10, Source, a4, 3, a3, KeyHandlea, a7);
            if ( (ObjectAttributes.Length & 0x20) != 0 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ObjectAttributes.ObjectName);
          }
          goto LABEL_19;
        }
      }
    }
  }
  memset(&ObjectAttributes, 0, 40);
  ResultLength = 0;
  P[0] = 0;
  Length = 0;
  *(_QWORD *)&Destination.Length = 0;
  LOWORD(Destination.Buffer) = 0;
  BYTE2(Destination.Buffer) = 0;
  Handle = 0;
  LOBYTE(v38[0]) = 0;
  v43 = v46;
  v14 = ConstructKernelKeyPath(
          a4,
          (unsigned int)&v43,
          (unsigned int)&Length,
          (unsigned int)&Destination,
          (__int64)v38,
          (__int64)P);
  KeySemantics = v14;
  if ( a7 )
  {
    if ( v14 < 0 )
      goto LABEL_18;
    v16 = NtOpenKeyTransactedEx(&Handle, a4, &v43, a3 & 0x1C, a7);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( v16 < 0 )
      goto LABEL_17;
    if ( !LOBYTE(v38[0]) )
      goto LABEL_16;
    goto LABEL_88;
  }
  if ( v14 >= 0 )
  {
    v16 = NtOpenKeyEx(&Handle, a4, &v43, a3 & 0x1C);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( v16 < 0 )
      goto LABEL_17;
    if ( !LOBYTE(v38[0]) )
    {
LABEL_16:
      *KeyHandlea = Handle;
LABEL_17:
      KeySemantics = v16;
      goto LABEL_18;
    }
LABEL_88:
    if ( Length )
    {
      Length &= 0xF01u;
      KeySemantics = NtSetInformationKey(Handle, KeySetHandleTagsInformation, &Length, 4u);
      if ( KeySemantics < 0 )
      {
        NtClose(Handle);
        goto LABEL_18;
      }
    }
    goto LABEL_16;
  }
LABEL_18:
  if ( KeySemantics == 1073741846 )
  {
    KeySemantics = NtQueryKey((HANDLE)*KeyHandlea, KeyCachedInformation, &ObjectAttributes, 0x28u, &ResultLength);
    NtClose((HANDLE)*KeyHandlea);
    if ( KeySemantics >= 0 )
      *KeyHandlea = SHIDWORD(ObjectAttributes.ObjectName);
  }
LABEL_19:
  if ( KeySemantics == -1073741772 )
  {
    if ( byte_1803A1942 )
    {
      v18 = byte_1803A1941;
    }
    else
    {
      P[0] = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&stru_180198AE0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(P, 0x80000100, &ObjectAttributes) >= 0 )
      {
        NtClose(P[0]);
        v17 = 1;
      }
      else
      {
        v17 = 0;
      }
      byte_1803A1940 = v17;
      P[0] = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&::Source;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(P, 0x80000100, &ObjectAttributes) >= 0 )
      {
        NtClose(P[0]);
        v18 = 1;
      }
      else
      {
        v18 = 0;
      }
      byte_1803A1941 = v18;
      byte_1803A1942 = 1;
    }
    if ( byte_1803A1940 || v18 )
    {
      Destination = 0;
      v20 = 256;
      for ( Length = 256; ; v20 = Length )
      {
        Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        if ( !Heap )
        {
          CurrentUserSid = -1073741670;
          goto LABEL_76;
        }
        CurrentUserSid = NtQueryKey(v10, KeyNameInformation, Heap, Length, &Length);
        if ( CurrentUserSid >= 0 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( CurrentUserSid != -1073741789 && CurrentUserSid != -2147483643 )
          goto LABEL_76;
      }
      v23 = Heap + 2;
      v24 = (void *)*Heap;
      Handle = v24;
      if ( v24 != (void *)34 )
        goto LABEL_41;
      if ( !(unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\Machine\\", 17, Heap + 2) )
        goto LABEL_64;
      v23 = Heap + 2;
LABEL_41:
      if ( (unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\Machine\\", 18, v23) )
      {
        if ( !(unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\User\\", 15, Heap + 2) && byte_1803A1941 )
        {
          *(_OWORD *)&ObjectAttributes.Length = 0;
          CurrentUserSid = DaxLookasideGetCurrentUserSid((PUNICODE_STRING)&ObjectAttributes);
          if ( CurrentUserSid < 0 )
            goto LABEL_75;
          v25 = (unsigned __int16)Handle;
          if ( (unsigned __int64)Handle < (unsigned __int64)((unsigned int)LOWORD(ObjectAttributes.Length) + 30) + 16 )
          {
            v26 = 0;
          }
          else
          {
            v26 = (unsigned int)RtlCompareUnicodeStrings(
                                  L"_Classes",
                                  8,
                                  &Heap[((unsigned __int64)((unsigned int)LOWORD(ObjectAttributes.Length) + 30) >> 1)
                                      + 2]) == 0;
            if ( v26 )
            {
              v27 = 140;
              goto LABEL_48;
            }
          }
          v27 = 122;
LABEL_48:
          v28 = &qword_180198C20;
          if ( !v26 )
            v28 = (__int64 *)&stru_180198B00;
          P[0] = v28;
          v38[0] = LOWORD(ObjectAttributes.Length) + 32;
          if ( v25 > (unsigned __int16)(LOWORD(ObjectAttributes.Length) + 32) )
            v27 = v25 + v27 - (LOWORD(ObjectAttributes.Length) + 32) + 2;
          v29 = Source->Length + v27 + 2;
          v30 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
          if ( v30 )
          {
            Destination.Buffer = v30;
            Destination.Length = 0;
            Destination.MaximumLength = v29;
            CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &::Source);
            if ( CurrentUserSid >= 0 )
            {
              CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)P[0]);
              if ( CurrentUserSid >= 0 )
              {
                if ( (unsigned __int16)Handle <= v38[0]
                  || (HIWORD(P[0]) = 0,
                      LOWORD(P[0]) = (_WORD)Handle - v38[0],
                      *(_DWORD *)((char *)P + 2) = (unsigned __int16)((_WORD)Handle - v38[0]),
                      P[1] = &Heap[((unsigned __int64)v38[0] >> 1) + 2],
                      CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)P),
                      CurrentUserSid >= 0)
                  && (CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_180198B00), CurrentUserSid >= 0) )
                {
                  CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, Source);
                  if ( CurrentUserSid >= 0 )
                  {
                    Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
                    *(_QWORD *)&v43.Length = 48;
                    *(_QWORD *)&v43.Attributes = 64;
                    v43.RootDirectory = 0;
                    v43.ObjectName = &Destination;
                    *(_OWORD *)&v43.SecurityDescriptor = 0;
                    CurrentUserSid = NtOpenKey((PHANDLE)KeyHandlea, 0x80000100, &v43);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
                    RtlFreeUnicodeString((PUNICODE_STRING)&ObjectAttributes);
                    goto LABEL_75;
                  }
                }
              }
            }
          }
          else
          {
            CurrentUserSid = -1073741670;
          }
          RtlFreeUnicodeString((PUNICODE_STRING)&ObjectAttributes);
LABEL_75:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_76:
          if ( CurrentUserSid >= 0 )
          {
            KeySemantics = 0;
            goto LABEL_29;
          }
LABEL_82:
          KeySemantics = -1073741772;
          goto LABEL_29;
        }
      }
      else
      {
LABEL_64:
        if ( byte_1803A1940 )
        {
          v31 = 128;
          if ( (unsigned int)v24 > 0x24 )
            v31 = (_WORD)v24 + 94;
          v32 = Source->Length + v31 + 2;
          v33 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
          if ( v33 )
          {
            Destination.Buffer = v33;
            Destination.Length = 0;
            Destination.MaximumLength = v32;
            CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_180198AE0);
            if ( CurrentUserSid >= 0 )
            {
              CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_180198B00);
              if ( CurrentUserSid >= 0 )
              {
                if ( (unsigned __int16)Handle <= 0x24u
                  || (*((_WORD *)&ObjectAttributes.Length + 3) = 0,
                      LOWORD(ObjectAttributes.Length) = (_WORD)Handle - 36,
                      *(ULONG *)((char *)&ObjectAttributes.Length + 2) = (unsigned __int16)((_WORD)Handle - 36),
                      ObjectAttributes.RootDirectory = Heap + 20,
                      CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&ObjectAttributes),
                      CurrentUserSid >= 0)
                  && (CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_180198B00), CurrentUserSid >= 0) )
                {
                  CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, Source);
                  if ( CurrentUserSid >= 0 )
                  {
                    Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
                    *(_QWORD *)&v43.Length = 48;
                    *(_QWORD *)&v43.Attributes = 64;
                    v43.RootDirectory = 0;
                    v43.ObjectName = &Destination;
                    *(_OWORD *)&v43.SecurityDescriptor = 0;
                    CurrentUserSid = NtOpenKey((PHANDLE)KeyHandlea, 0x80000100, &v43);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
                  }
                }
              }
            }
          }
          else
          {
            CurrentUserSid = -1073741670;
          }
          goto LABEL_75;
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      goto LABEL_82;
    }
    KeySemantics = -1073741772;
  }
LABEL_29:
  if ( KeySemantics == -1073741790 && (g_RegKrnGlobalState & 1) != 0 )
  {
    v34 = a4 & 0x1000300 | 0x2000000;
    if ( ((unsigned __int8)v10 & 2) != 0 )
      v35 = BaseRegOpenClassKey(v10, Source, (__int64)KeyHandlea, v47);
    else
      v35 = v47
          ? Wow64NtOpenKey((_DWORD)KeyHandlea, v34, (unsigned int)&v46, 0, v47)
          : Wow64NtOpenKey((_DWORD)KeyHandlea, v34, (unsigned int)&v46, 0, 0);
    KeySemantics = v35;
    if ( v35 < 0 )
      KeySemantics = -1073741790;
  }
  if ( ((unsigned __int8)v10 & 2) == 0
    && KeySemantics < 0
    && (unsigned __int8)IsTermsrvDeleteKeyPresent()
    && (unsigned int)TermsrvOpenRegEntry(KeyHandlea, a4, &v46) )
  {
    KeySemantics = 0;
  }
  *Source = v11;
  return RtlNtStatusToDosError(KeySemantics);
}

```

## disassembly

```asm
0x18005bf10  push    rbx
0x18005bf12  push    rsi
0x18005bf13  push    rdi
0x18005bf14  push    r12
0x18005bf16  push    r13
0x18005bf18  push    r14
0x18005bf1a  push    r15
0x18005bf1c  sub     rsp, 2C0h
0x18005bf23  movaps  [rsp+2F8h+var_48], xmm6
0x18005bf2b  mov     rax, cs:__security_cookie
0x18005bf32  xor     rax, rsp
0x18005bf35  mov     [rsp+2F8h+var_58], rax
0x18005bf3d  mov     r13d, r9d
0x18005bf40  mov     r12d, r8d
0x18005bf43  mov     rdi, rdx
0x18005bf46  mov     rsi, rcx
0x18005bf49  mov     r14, [rsp+2F8h+KeyHandle]
0x18005bf51  mov     r15, [rsp+2F8h+arg_30]
0x18005bf59  mov     [rsp+2F8h+var_220], r15
0x18005bf61  xor     eax, eax
0x18005bf63  xorps   xmm0, xmm0
0x18005bf66  movups  [rsp+2F8h+var_250], xmm0
0x18005bf6e  movups  [rsp+2F8h+var_240], xmm0
0x18005bf76  movups  [rsp+2F8h+var_240+0Ch], xmm0
0x18005bf7e  test    rdx, rdx
0x18005bf81  jz      loc_18005C281
0x18005bf87  movzx   eax, word ptr [rdx]
0x18005bf8a  cmp     ax, 2
0x18005bf8e  jb      loc_18005C281
0x18005bf94  test    al, 1
0x18005bf96  jnz     loc_18005C281
0x18005bf9c  cmp     qword ptr [rdx+8], 0
0x18005bfa1  jz      loc_18005C281
0x18005bfa7  movups  xmm6, xmmword ptr [rdx]
0x18005bfaa  test    r14, r14
0x18005bfad  jz      loc_18005C281
0x18005bfb3  xor     ebx, ebx
0x18005bfb5  mov     [r14], rbx
0x18005bfb8  jmp     short loc_18005BFC1
0x18005bfba  mov     ebx, eax
0x18005bfbc  jmp     loc_18005C24E
0x18005bfc1  movzx   eax, word ptr [rdx]
0x18005bfc4  sub     ax, 2
0x18005bfc8  mov     [rdx], ax
0x18005bfcb  mov     dword ptr [rsp+2F8h+var_250], 30h ; '0'
0x18005bfd6  mov     qword ptr [rsp+2F8h+var_250+8], rsi
0x18005bfde  test    r12b, 8
0x18005bfe2  jnz     loc_18005C9B3
0x18005bfe8  mov     dword ptr [rsp+2F8h+var_240+8], 40h ; '@'
0x18005bff3  mov     qword ptr [rsp+2F8h+var_240], rdi
0x18005bffb  movdqu  [rsp+2F8h+var_230], xmm0
0x18005c004  test    sil, 2
0x18005c008  jnz     loc_18005C7FB
0x18005c00e  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005c015  jnz     loc_18005C941
0x18005c01b  xorps   xmm0, xmm0
0x18005c01e  xor     eax, eax
0x18005c020  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.Length], xmm0
0x18005c028  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.ObjectName], xmm0
0x18005c030  mov     [rsp+2F8h+ObjectAttributes.SecurityDescriptor], rax
0x18005c038  mov     [rsp+2F8h+var_254], ebx
0x18005c03f  mov     [rsp+2F8h+P], rbx
0x18005c044  movups  xmm0, [rsp+2F8h+var_250]
0x18005c04c  movups  xmm1, [rsp+2F8h+var_240]
0x18005c054  mov     [rsp+2F8h+Length], ebx
0x18005c058  mov     qword ptr [rsp+2F8h+Destination.Length], rax
0x18005c05d  mov     word ptr [rsp+2F8h+Destination.Buffer], ax
0x18005c062  mov     byte ptr [rsp+2F8h+Destination.Buffer+2], al
0x18005c066  mov     [rsp+2F8h+Handle], rbx
0x18005c06b  mov     byte ptr [rsp+2F8h+var_2B8], al
0x18005c06f  lea     r9, [rsp+2F8h+Destination]
0x18005c074  lea     r8, [rsp+2F8h+Length]
0x18005c079  lea     rdx, [rsp+2F8h+var_288]
0x18005c07e  mov     ecx, r13d
0x18005c081  movups  xmmword ptr [rsp+2F8h+var_288.Length], xmm0
0x18005c086  movups  xmmword ptr [rsp+2F8h+var_288.ObjectName], xmm1
0x18005c08e  lea     rax, [rsp+2F8h+P]
0x18005c093  movups  xmm0, [rsp+2F8h+var_230]
0x18005c09b  mov     [rsp+2F8h+var_2D0], rax
0x18005c0a0  movups  xmmword ptr [rsp+2F8h+var_288.SecurityDescriptor], xmm0
0x18005c0a8  lea     rax, [rsp+2F8h+var_2B8]
0x18005c0ad  mov     [rsp+2F8h+ResultLength], rax
0x18005c0b2  call    ConstructKernelKeyPath
0x18005c0b7  mov     ebx, eax
0x18005c0b9  test    r15, r15
0x18005c0bc  jnz     loc_18005C9C3
0x18005c0c2  test    eax, eax
0x18005c0c4  js      short loc_18005C11D
0x18005c0c6  mov     r9d, r12d
0x18005c0c9  and     r9d, 1Ch
0x18005c0cd  lea     r8, [rsp+2F8h+var_288]
0x18005c0d2  mov     edx, r13d
0x18005c0d5  lea     rcx, [rsp+2F8h+Handle]
0x18005c0da  call    cs:__imp_NtOpenKeyEx
0x18005c0e0  mov     r15d, eax
0x18005c0e3  mov     r8, [rsp+2F8h+P]; P
0x18005c0e8  test    r8, r8
0x18005c0eb  jz      short loc_18005C102
0x18005c0ed  mov     rcx, gs:60h
0x18005c0f6  xor     edx, edx; Flags
0x18005c0f8  mov     rcx, [rcx+30h]; HeapHandle
0x18005c0fc  call    cs:__imp_RtlFreeHeap
0x18005c102  test    r15d, r15d
0x18005c105  js      short loc_18005C11A
0x18005c107  cmp     byte ptr [rsp+2F8h+var_2B8], 0
0x18005c10c  jnz     loc_18005C8DF
0x18005c112  mov     rax, [rsp+2F8h+Handle]
0x18005c117  mov     [r14], rax
0x18005c11a  mov     ebx, r15d
0x18005c11d  cmp     ebx, 40000016h
0x18005c123  jz      loc_18005CA79
0x18005c129  cmp     ebx, 0C0000034h
0x18005c12f  jnz     loc_18005C22E
0x18005c135  cmp     cs:byte_1803A1942, 0
0x18005c13c  jnz     loc_18005C7A9
0x18005c142  xor     r15d, r15d
0x18005c145  mov     [rsp+2F8h+P], r15
0x18005c14a  mov     qword ptr [rsp+2F8h+ObjectAttributes.Length], 30h ; '0'
0x18005c156  mov     qword ptr [rsp+2F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18005c162  mov     [rsp+2F8h+ObjectAttributes.RootDirectory], r15
0x18005c16a  lea     rbx, stru_180198AE0
0x18005c171  mov     [rsp+2F8h+ObjectAttributes.ObjectName], rbx
0x18005c179  xorps   xmm0, xmm0
0x18005c17c  movdqu  xmmword ptr [rsp+2F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c185  lea     r8, [rsp+2F8h+ObjectAttributes]; ObjectAttributes
0x18005c18d  mov     edx, 80000100h; DesiredAccess
0x18005c192  lea     rcx, [rsp+2F8h+P]; KeyHandle
0x18005c197  call    cs:__imp_NtOpenKey
0x18005c19d  test    eax, eax
0x18005c19f  jns     loc_18005C7B5
0x18005c1a5  xor     al, al
0x18005c1a7  mov     cs:byte_1803A1940, al
0x18005c1ad  mov     [rsp+2F8h+P], r15
0x18005c1b2  mov     qword ptr [rsp+2F8h+ObjectAttributes.Length], 30h ; '0'
0x18005c1be  mov     qword ptr [rsp+2F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18005c1ca  mov     [rsp+2F8h+ObjectAttributes.RootDirectory], r15
0x18005c1d2  lea     rbx, Source
0x18005c1d9  mov     [rsp+2F8h+ObjectAttributes.ObjectName], rbx
0x18005c1e1  xorps   xmm0, xmm0
0x18005c1e4  movdqu  xmmword ptr [rsp+2F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c1ed  lea     r8, [rsp+2F8h+ObjectAttributes]; ObjectAttributes
0x18005c1f5  mov     edx, 80000100h; DesiredAccess
0x18005c1fa  lea     rcx, [rsp+2F8h+P]; KeyHandle
0x18005c1ff  call    cs:__imp_NtOpenKey
0x18005c205  test    eax, eax
0x18005c207  jns     loc_18005C7C7
0x18005c20d  xor     al, al
0x18005c20f  mov     cs:byte_1803A1941, al
0x18005c215  mov     cs:byte_1803A1942, 1
0x18005c21c  cmp     cs:byte_1803A1940, 0
0x18005c223  jnz     short loc_18005C288
0x18005c225  test    al, al
0x18005c227  jnz     short loc_18005C288
0x18005c229  mov     ebx, 0C0000034h
0x18005c22e  mov     r15d, 0C0000022h
0x18005c234  cmp     ebx, r15d
0x18005c237  jz      loc_18005CA25
0x18005c23d  test    sil, 2
0x18005c241  jnz     short loc_18005C24B
0x18005c243  test    ebx, ebx
0x18005c245  js      loc_18005C5D0
0x18005c24b  movups  xmmword ptr [rdi], xmm6
0x18005c24e  mov     ecx, ebx; Status
0x18005c250  call    cs:__imp_RtlNtStatusToDosError
0x18005c256  mov     rcx, [rsp+2F8h+var_58]
0x18005c25e  xor     rcx, rsp; StackCookie
0x18005c261  call    __security_check_cookie
0x18005c266  movaps  xmm6, [rsp+2F8h+var_48]
0x18005c26e  add     rsp, 2C0h
0x18005c275  pop     r15
0x18005c277  pop     r14
0x18005c279  pop     r13
0x18005c27b  pop     r12
0x18005c27d  pop     rdi
0x18005c27e  pop     rsi
0x18005c27f  pop     rbx
0x18005c280  retn
0x18005c281  mov     ebx, 0C000000Dh
0x18005c286  jmp     short loc_18005C24E
0x18005c288  xorps   xmm0, xmm0
0x18005c28b  movups  xmmword ptr [rsp+2F8h+Destination.Length], xmm0
0x18005c290  mov     eax, 100h
0x18005c295  mov     [rsp+2F8h+Length], eax
0x18005c299  mov     r8d, eax; Size
0x18005c29c  mov     rcx, gs:60h
0x18005c2a5  xor     edx, edx; Flags
0x18005c2a7  mov     rcx, [rcx+30h]; HeapHandle
0x18005c2ab  call    cs:__imp_RtlAllocateHeap
0x18005c2b1  mov     r15, rax
0x18005c2b4  test    rax, rax
0x18005c2b7  jz      loc_18005C929
0x18005c2bd  lea     rax, [rsp+2F8h+Length]
0x18005c2c2  mov     [rsp+2F8h+ResultLength], rax; ResultLength
0x18005c2c7  mov     r9d, [rsp+2F8h+Length]; Length
0x18005c2cc  mov     r8, r15; KeyInformation
0x18005c2cf  mov     edx, 3; KeyInformationClass
0x18005c2d4  mov     rcx, rsi; KeyHandle
0x18005c2d7  call    cs:__imp_NtQueryKey
0x18005c2dd  mov     ebx, eax
0x18005c2df  test    eax, eax
0x18005c2e1  js      loc_18005C8B6
0x18005c2e7  lea     rax, [r15+4]
0x18005c2eb  movzx   ebx, word ptr [r15]
0x18005c2ef  mov     [rsp+2F8h+Handle], rbx
0x18005c2f4  cmp     rbx, 22h ; '"'
0x18005c2f8  jnz     short loc_18005C324
0x18005c2fa  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005c2ff  mov     r9d, 11h
0x18005c305  mov     r8, rax
0x18005c308  mov     edx, r9d
0x18005c30b  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\"
0x18005c312  call    cs:__imp_RtlCompareUnicodeStrings
0x18005c318  test    eax, eax
0x18005c31a  jz      loc_18005C5FD
0x18005c320  lea     rax, [r15+4]
0x18005c324  mov     r9, rbx
0x18005c327  mov     ecx, 24h ; '$'
0x18005c32c  cmp     rbx, rcx
0x18005c32f  cmova   r9, rcx
0x18005c333  shr     r9, 1
0x18005c336  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005c33b  mov     r8, rax
0x18005c33e  mov     edx, 12h
0x18005c343  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\"
0x18005c34a  call    cs:__imp_RtlCompareUnicodeStrings
0x18005c350  test    eax, eax
0x18005c352  jz      loc_18005C5FD
0x18005c358  mov     r9, rbx
0x18005c35b  mov     eax, 1Eh
0x18005c360  cmp     rbx, rax
0x18005c363  cmova   r9, rax
0x18005c367  shr     r9, 1
0x18005c36a  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005c36f  lea     r8, [r15+4]
0x18005c373  mov     edx, 0Fh
0x18005c378  lea     rcx, aRegistryUser_0; "\\Registry\\User\\"
0x18005c37f  call    cs:__imp_RtlCompareUnicodeStrings
0x18005c385  test    eax, eax
0x18005c387  jnz     loc_18005C7D9
0x18005c38d  cmp     cs:byte_1803A1941, al
0x18005c393  jz      loc_18005C7D9
0x18005c399  xorps   xmm0, xmm0
0x18005c39c  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.Length], xmm0
0x18005c3a4  lea     rcx, [rsp+2F8h+ObjectAttributes]; UnicodeString
0x18005c3ac  call    DaxLookasideGetCurrentUserSid
0x18005c3b1  mov     ebx, eax
0x18005c3b3  test    eax, eax
0x18005c3b5  js      loc_18005C786
0x18005c3bb  movzx   eax, word ptr [rsp+2F8h+ObjectAttributes.Length]
0x18005c3c3  add     eax, 1Eh
0x18005c3c6  mov     ecx, eax
0x18005c3c8  add     rax, 10h
0x18005c3cc  mov     rbx, [rsp+2F8h+Handle]
0x18005c3d1  cmp     rbx, rax
0x18005c3d4  jb      loc_18005C9A7
0x18005c3da  shr     rcx, 1
0x18005c3dd  add     rcx, 2
0x18005c3e1  lea     r8, [r15+rcx*2]
0x18005c3e5  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005c3ea  mov     edx, 8
0x18005c3ef  mov     r9d, edx
0x18005c3f2  lea     rcx, aClasses_0; "_Classes"
0x18005c3f9  call    cs:__imp_RtlCompareUnicodeStrings
0x18005c3ff  test    eax, eax
0x18005c401  jnz     loc_18005CAC5
0x18005c407  mov     dl, 1
0x18005c409  test    dl, dl
0x18005c40b  jz      loc_18005C9A9
0x18005c411  mov     ecx, 8Ch
0x18005c416  lea     rax, stru_180198B00
0x18005c41d  lea     r8, qword_180198C20
0x18005c424  test    dl, dl
0x18005c426  cmovz   r8, rax
0x18005c42a  mov     [rsp+2F8h+P], r8
0x18005c42f  movzx   eax, word ptr [rsp+2F8h+ObjectAttributes.Length]
0x18005c437  add     ax, 20h ; ' '
0x18005c43b  mov     [rsp+2F8h+var_2B8], ax
0x18005c440  cmp     bx, ax
0x18005c443  jbe     short loc_18005C44F
0x18005c445  sub     cx, ax
0x18005c448  add     cx, 2
0x18005c44c  add     cx, bx
0x18005c44f  add     cx, 2
0x18005c453  add     cx, [rdi]
0x18005c456  movzx   ebx, cx
0x18005c459  mov     r8d, ebx; Size
0x18005c45c  mov     rcx, gs:60h
0x18005c465  xor     edx, edx; Flags
0x18005c467  mov     rcx, [rcx+30h]; HeapHandle
0x18005c46b  call    cs:__imp_RtlAllocateHeap
0x18005c471  test    rax, rax
0x18005c474  jz      loc_18005C98F
0x18005c47a  mov     [rsp+2F8h+Destination.Buffer], rax
0x18005c47f  xor     eax, eax
0x18005c481  mov     [rsp+2F8h+Destination.Length], ax
0x18005c486  mov     [rsp+2F8h+Destination.MaximumLength], bx
0x18005c48b  lea     rdx, Source; Source
0x18005c492  lea     rcx, [rsp+2F8h+Destination]; Destination
0x18005c497  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005c49d  mov     ebx, eax
  ... truncated ...
```
