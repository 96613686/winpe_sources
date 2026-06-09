# BaseSrvDefineDosDevice

- ea: `0x180001010`
- end: `0x180001e9f`
- name: `BaseSrvDefineDosDevice`
- size: `3727`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001010`
- `0x180001eb0`
- `0x180002020`
- `0x180002190`
- `0x180002250`
- `0x18000d707`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001189`
- `ntdll!RtlAllocateHeap` at `0x180001189`
- `ntdll!_wcsicmp` at `0x1800012c5`
- `ntdll!_wcsicmp` at `0x1800012c5`
- `ntdll!NtClose` at `0x1800013ba`
- `ntdll!NtClose` at `0x18000167b`
- `ntdll!NtClose` at `0x180001e4d`
- `ntdll!NtClose` at `0x18000d7f4`
- `ntdll!NtClose` at `0x1800013ba`
- `ntdll!NtClose` at `0x18000167b`
- `ntdll!NtClose` at `0x180001e4d`
- `ntdll!NtClose` at `0x18000d7f4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800014b2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800014b2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180001589`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180001589`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180001611`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180001611`
- `ntdll!RtlFreeHeap` at `0x180001d75`
- `ntdll!RtlFreeHeap` at `0x18000d811`
- `ntdll!RtlFreeHeap` at `0x180001d75`
- `ntdll!RtlFreeHeap` at `0x18000d811`
- `ntdll!RtlEnterCriticalSection` at `0x1800011b0`
- `ntdll!RtlEnterCriticalSection` at `0x1800011b0`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180001abb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180001abb`
- `ntdll!_snwprintf_s` at `0x180001757`
- `ntdll!_snwprintf_s` at `0x1800018ce`
- `ntdll!_snwprintf_s` at `0x180001757`
- `ntdll!_snwprintf_s` at `0x1800018ce`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180001823`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180001823`
- `ntdll!wcsnlen` at `0x18000193e`
- `ntdll!wcsnlen` at `0x18000193e`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800019f9`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800019f9`
- `ntdll!NtMakeTemporaryObject` at `0x1800013a2`
- `ntdll!NtMakeTemporaryObject` at `0x1800013a2`
- `ntdll!_wcsnicmp` at `0x180001c80`
- `ntdll!_wcsnicmp` at `0x180001c80`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001435`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001488`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001435`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001488`
- `ntdll!RtlFreeSid` at `0x180001552`
- `ntdll!RtlFreeSid` at `0x180001566`
- `ntdll!RtlFreeSid` at `0x180001d15`
- `ntdll!RtlFreeSid` at `0x180001552`
- `ntdll!RtlFreeSid` at `0x180001566`
- `ntdll!RtlFreeSid` at `0x180001d15`
- `ntdll!RtlCreateAcl` at `0x1800014d3`
- `ntdll!RtlCreateAcl` at `0x1800014d3`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001512`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000153a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001512`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000153a`
- `ntdll!NtMakePermanentObject` at `0x180001663`
- `ntdll!NtMakePermanentObject` at `0x180001663`
- `ntdll!RtlCopyLuid` at `0x180001e78`
- `ntdll!RtlCopyLuid` at `0x18000d85a`
- `ntdll!RtlCopyLuid` at `0x180001e78`
- `ntdll!RtlCopyLuid` at `0x18000d85a`
- `ntdll!RtlLeaveCriticalSection` at `0x180001d8e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d8c4`
- `ntdll!RtlLeaveCriticalSection` at `0x180001d8e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d8c4`
- `ntdll!RtlInitUnicodeString` at `0x180001389`
- `ntdll!RtlInitUnicodeString` at `0x18000179d`
- `ntdll!RtlInitUnicodeString` at `0x180001389`
- `ntdll!RtlInitUnicodeString` at `0x18000179d`
- `CSRSRV!CsrIsClientSandboxed` at `0x1800016a6`
- `CSRSRV!CsrIsClientSandboxed` at `0x1800016a6`
- `CSRSRV!CsrRevertToSelf` at `0x18000163d`
- `CSRSRV!CsrRevertToSelf` at `0x180001836`
- `CSRSRV!CsrRevertToSelf` at `0x18000163d`
- `CSRSRV!CsrRevertToSelf` at `0x180001836`
- `CSRSRV!CsrImpersonateClient` at `0x1800015cc`
- `CSRSRV!CsrImpersonateClient` at `0x1800017ee`
- `CSRSRV!CsrImpersonateClient` at `0x1800015cc`
- `CSRSRV!CsrImpersonateClient` at `0x1800017ee`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000111e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001162`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000111e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001162`

## pseudocode

```c
__int64 __fastcall BaseSrvDefineDosDevice(__int64 a1)
{
  _WORD *v2; // r13
  unsigned __int16 v3; // cx
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // ax
  wchar_t *Heap; // r12
  int v8; // ecx
  bool v9; // r14
  int v10; // edx
  char v11; // di
  NTSTATUS TemporaryObject; // r15d
  wchar_t *v13; // r13
  wchar_t *v14; // rdi
  char v15; // dl
  wchar_t v16; // ax
  int v17; // esi
  wchar_t *v18; // rcx
  unsigned int v19; // eax
  wchar_t *v20; // r13
  __int64 v21; // rax
  wchar_t *v22; // rax
  __int16 v23; // dx
  wchar_t *v24; // r13
  const WCHAR *v25; // rdx
  ACCESS_MASK v26; // ebx
  char v27; // di
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  wchar_t *v31; // rdi
  __int64 v32; // rcx
  unsigned int v33; // r13d
  unsigned __int16 v34; // ax
  unsigned __int16 v35; // ax
  size_t v36; // rdi
  wchar_t *v37; // rsi
  unsigned int v38; // ecx
  __int64 v39; // rdx
  unsigned __int16 *v40; // rax
  unsigned int v41; // eax
  int v42; // ecx
  unsigned int v44; // ebx
  char v45; // [rsp+60h] [rbp-258h]
  char v46; // [rsp+61h] [rbp-257h]
  int CallerLuid; // [rsp+64h] [rbp-254h]
  char v48; // [rsp+68h] [rbp-250h]
  char v49; // [rsp+69h] [rbp-24Fh] BYREF
  char v50; // [rsp+6Ah] [rbp-24Eh]
  unsigned int MaxCount; // [rsp+6Ch] [rbp-24Ch]
  char MaxCount_4; // [rsp+70h] [rbp-248h]
  char MaxCount_5; // [rsp+71h] [rbp-247h]
  bool MaxCount_6; // [rsp+72h] [rbp-246h]
  HANDLE Handle; // [rsp+78h] [rbp-240h] BYREF
  ULONG DataWritten; // [rsp+80h] [rbp-238h] BYREF
  _LUID DestinationLuid; // [rsp+88h] [rbp-230h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-228h] BYREF
  int v59; // [rsp+A0h] [rbp-218h]
  struct _LUID SourceLuid; // [rsp+A8h] [rbp-210h]
  wchar_t *String2; // [rsp+B0h] [rbp-208h]
  __int16 v62; // [rsp+B8h] [rbp-200h]
  int v63; // [rsp+BCh] [rbp-1FCh]
  wchar_t *v64; // [rsp+C0h] [rbp-1F8h]
  unsigned int v65; // [rsp+C8h] [rbp-1F0h]
  unsigned int v66; // [rsp+CCh] [rbp-1ECh]
  PSID Sid; // [rsp+D0h] [rbp-1E8h] BYREF
  PSID v68; // [rsp+D8h] [rbp-1E0h] BYREF
  int v69; // [rsp+E0h] [rbp-1D8h]
  wchar_t *v70; // [rsp+E8h] [rbp-1D0h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-1C8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp-1B8h] BYREF
  wchar_t *v73; // [rsp+130h] [rbp-188h]
  wchar_t *v74; // [rsp+138h] [rbp-180h]
  _OWORD SecurityDescriptor[2]; // [rsp+140h] [rbp-178h] BYREF
  __int64 v76; // [rsp+160h] [rbp-158h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+168h] [rbp-150h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v78; // [rsp+170h] [rbp-148h] BYREF
  _ACL Acl; // [rsp+180h] [rbp-138h] BYREF

  DestinationString = 0;
  *(_OWORD *)String1 = 0;
  memset(&ObjectAttributes, 0, 44);
  DataWritten = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)v78.Value = 0;
  *(_WORD *)&v78.Value[4] = 1280;
  v68 = 0;
  Sid = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v76 = 0;
  DestinationLuid = 0;
  v49 = 0;
  v45 = 0;
  v63 = 0;
  v50 = 0;
  v2 = (_WORD *)(a1 + 72);
  v3 = *(_WORD *)(a1 + 72);
  if ( (v3 & 1) != 0 )
    return 3221225485LL;
  v4 = *(_WORD *)(a1 + 74);
  if ( (v4 & 1) != 0 )
    return 3221225485LL;
  if ( v3 > v4 )
    return 3221225485LL;
  if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 80, *(unsigned __int16 *)(a1 + 74), 1) )
    return 3221225485LL;
  v5 = *(_WORD *)(a1 + 88);
  if ( (v5 & 1) != 0 )
    return 3221225485LL;
  v6 = *(_WORD *)(a1 + 90);
  if ( (v6 & 1) != 0
    || v5 > v6
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 96, *(unsigned __int16 *)(a1 + 90), 1) )
  {
    return 3221225485LL;
  }
  Heap = (wchar_t *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x2000u);
  v74 = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlEnterCriticalSection(&BaseSrvDosDeviceCritSec);
  v8 = *(_DWORD *)(a1 + 64);
  v9 = (v8 & 2) != 0;
  MaxCount_6 = v9;
  v65 = 0;
  v66 = 0;
  Handle = 0;
  v46 = 0;
  LOBYTE(v10) = v8;
  if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) != 1 )
    goto LABEL_12;
  if ( (v8 & 8) != 0 )
    goto LABEL_12;
  v40 = *(unsigned __int16 **)(a1 + 80);
  LOBYTE(v10) = v8;
  if ( !v40 || *v2 != 4 || v40[1] != 58 )
    goto LABEL_12;
  v41 = *v40;
  v62 = v41;
  if ( v41 < 0x7B && v41 >= 0x61 )
  {
    LOWORD(v41) = RtlUpcaseUnicodeChar(v41);
    v62 = v41;
    v10 = *(_DWORD *)(a1 + 64);
  }
  v65 = (unsigned __int16)v41 - 65;
  v66 = v65;
  if ( v65 < 0x1A )
  {
    v11 = 1;
    v45 = 1;
  }
  else
  {
LABEL_12:
    v11 = 0;
  }
  if ( (v10 & 0x10) != 0 && !v11 )
  {
    TemporaryObject = -1073741811;
    goto LABEL_132;
  }
  v64 = Heap;
  v59 = 4096;
  v30 = _snwprintf_s(Heap, 0x1000u, 0xFFFu, L"\\??\\%wZ", v2);
  if ( v30 == -1 )
    v30 = 4095;
  v31 = &Heap[v30 + 1];
  String2 = v31;
  v64 = v31;
  MaxCount = 4095 - v30;
  v59 = 4095 - v30;
  RtlInitUnicodeString(&DestinationString, Heap);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v48 = 1;
  MaxCount_5 = CsrImpersonateClient(0);
  if ( !MaxCount_5 )
  {
    TemporaryObject = -1073741659;
    v11 = v45;
    goto LABEL_132;
  }
  if ( v45 == 1 )
  {
    CallerLuid = GetCallerLuid(&DestinationLuid);
    v42 = (unsigned __int8)v63;
    if ( CallerLuid >= 0 )
      v42 = 1;
    v63 = v42;
    v50 = v42;
  }
  TemporaryObject = NtOpenSymbolicLinkObject(&Handle, 0x10001u, &ObjectAttributes);
  CsrRevertToSelf(v32);
  if ( (*(_BYTE *)(a1 + 64) & 0x10) != 0 )
  {
    if ( TemporaryObject < 0 )
      Handle = 0;
    if ( v9 && TemporaryObject == -1073741772 )
      TemporaryObject = 0;
    goto LABEL_59;
  }
  if ( TemporaryObject == -1073741772 )
  {
    Handle = 0;
    if ( v9 )
    {
      if ( !*(_WORD *)(a1 + 88) )
        TemporaryObject = 0;
      goto LABEL_59;
    }
    v48 = 0;
    TemporaryObject = 0;
  }
  else
  {
    if ( TemporaryObject < 0 )
    {
LABEL_58:
      Handle = 0;
      goto LABEL_59;
    }
    if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) == 1 )
    {
      TemporaryObject = IsGlobalSymbolicLink(Handle);
      if ( TemporaryObject < 0 )
        goto LABEL_59;
    }
  }
  v33 = MaxCount;
  v34 = *(_WORD *)(a1 + 88);
  if ( v34 )
  {
    v35 = wcsnlen(*(const wchar_t **)(a1 + 96), (unsigned __int64)v34 >> 1);
    MaxCount = v35;
    if ( (unsigned int)v35 + 1 >= v33 )
    {
      TemporaryObject = -1073741619;
      v11 = v45;
      goto LABEL_132;
    }
    v36 = v35;
    v37 = String2;
    memmove_0(String2, *(const void **)(a1 + 96), v36 * 2);
    v37[v36] = 0;
    String2 = v37;
    v38 = MaxCount;
    v31 = &v37[MaxCount + 1];
    v64 = v31;
    v33 += -1 - MaxCount;
    v59 = v33;
  }
  else
  {
    String2 = 0;
    v38 = 0;
    MaxCount = 0;
  }
  if ( !v48 )
  {
    if ( v9 )
      v25 = 0;
    else
      v25 = &v31[-v38 - 1];
    RtlInitUnicodeString((PUNICODE_STRING)String1, v25);
    goto LABEL_36;
  }
  LOWORD(String1[0]) = 0;
  WORD1(String1[0]) = 2 * v33;
  String1[1] = v31;
  DataWritten = 0;
  TemporaryObject = NtQuerySymbolicLinkObject(Handle, (PUNICODE_STRING)String1, &DataWritten);
  if ( DataWritten == WORD1(String1[0]) )
    goto LABEL_111;
  if ( TemporaryObject < 0 )
    goto LABEL_59;
  v39 = DataWritten >> 1;
  if ( (unsigned int)v39 >= 2 && !v31[(unsigned int)(v39 - 2)] && !v31[(unsigned int)(v39 - 1)] )
  {
    WORD1(String1[0]) = DataWritten;
    goto LABEL_36;
  }
  if ( !(_DWORD)v39 || v31[(unsigned int)(v39 - 1)] )
  {
    if ( (unsigned __int64)DataWritten + 2 < WORD1(String1[0]) )
    {
      v31[v39] = 0;
      v31[(unsigned int)(v39 + 1)] = 0;
      WORD1(String1[0]) = DataWritten + 4;
      goto LABEL_36;
    }
LABEL_111:
    TemporaryObject = -2147483643;
    v11 = v45;
    goto LABEL_132;
  }
  v31[v39] = 0;
  WORD1(String1[0]) = DataWritten + 2;
LABEL_36:
  if ( Handle )
  {
    TemporaryObject = NtMakeTemporaryObject(Handle);
    NtClose(Handle);
    Handle = 0;
  }
  if ( TemporaryObject < 0 )
    goto LABEL_59;
  if ( !v9 )
  {
    if ( v48 )
    {
      String1[1] += -MaxCount - 1;
      LOWORD(v22) = 2 * MaxCount;
      LOWORD(String1[0]) = 2 * MaxCount;
      WORD1(String1[0]) += 2 * MaxCount + 2;
    }
    else
    {
      LOWORD(v22) = String1[0];
    }
    goto LABEL_42;
  }
  v13 = String1[1];
  v70 = String1[1];
  v14 = String1[1];
  v73 = String1[1];
  v15 = 0;
  v46 = 0;
  MaxCount_4 = 0;
  while ( 1 )
  {
    v16 = *v14;
    if ( !*v14 )
      break;
    v17 = 0;
    v69 = 0;
    v18 = v14;
    v64 = v14;
    while ( 1 )
    {
      v73 = ++v14;
      if ( !v16 )
        break;
      v69 = ++v17;
      v16 = *v14;
    }
    if ( v15 )
      goto LABEL_63;
    v19 = MaxCount;
    if ( (*(_BYTE *)(a1 + 64) & 4) == 0 )
      goto LABEL_148;
    if ( MaxCount == v17 )
    {
      if ( !_wcsicmp(v18, String2) )
        goto LABEL_25;
      v19 = MaxCount;
      v18 = v64;
      v15 = v46;
    }
    if ( (*(_BYTE *)(a1 + 64) & 4) != 0 )
    {
LABEL_63:
      if ( v18 != v13 )
      {
        memmove_0(v13, v18, 2LL * (unsigned int)(v17 + 1));
        v15 = v46;
      }
      v13 += (unsigned int)(v17 + 1);
      v70 = v13;
    }
    else
    {
LABEL_148:
      if ( v19 && _wcsnicmp(v18, String2, v19) )
      {
        v18 = v64;
        v15 = v46;
        goto LABEL_63;
      }
LABEL_25:
      v15 = 1;
      v46 = 1;
      MaxCount_4 = 1;
    }
  }
  *v13 = 0;
  v20 = v13 + 1;
  v70 = v20;
  v21 = -1;
  do
    ++v21;
  while ( String1[1][v21] );
  v22 = (wchar_t *)(2 * v21);
  String2 = v22;
  if ( (unsigned __int64)v22 > 0xFFFF )
  {
    LOWORD(v22) = -1;
    v23 = -1;
  }
  else
  {
    v23 = (__int16)v22;
  }
  LOWORD(String1[0]) = (_WORD)v22;
  if ( v23 )
  {
    v24 = (wchar_t *)((char *)v20 - (char *)String1[1]);
    String2 = v24;
    if ( (unsigned __int64)v24 > 0xFFFF )
      WORD1(String1[0]) = -1;
    else
      WORD1(String1[0]) = (_WORD)v24;
  }
LABEL_42:
  if ( !(_WORD)v22
    || (TemporaryObject = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid),
        TemporaryObject < 0) )
  {
LABEL_59:
    v11 = v45;
    goto LABEL_132;
  }
  TemporaryObject = RtlAllocateAndInitializeSid(&v78, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v68);
  if ( TemporaryObject < 0 )
  {
    RtlFreeSid(Sid);
    goto LABEL_59;
  }
  v26 = 1;
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlCreateAcl(&Acl, 0x100u, 2u);
  if ( SessionId == ServiceSessionId || (ProtectionMode & 3) == 0 )
    v26 = 65537;
  RtlAddAccessAllowedAce(&Acl, 2u, v26, Sid);
  RtlAddAccessAllowedAce(&Acl, 2u, v26, v68);
  RtlFreeSid(Sid);
  RtlFreeSid(v68);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 1u);
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) != 1 )
  {
    TemporaryObject = CsrIsClientSandboxed(0, &v49);
    if ( TemporaryObject < 0 )
      goto LABEL_59;
    if ( v49 )
    {
      TemporaryObject = -1073741790;
      goto LABEL_59;
    }
    v27 = MaxCount_5;
LABEL_49:
    if ( !*(_BYTE *)(BaseSrvpStaticServerData + 2508) )
      ObjectAttributes.Attributes |= 0x10u;
    TemporaryObject = NtCreateSymbolicLinkObject(&Handle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)String1);
    v29 = BaseSrvpStaticServerData;
    if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) == 1 && v27 )
    {
      CsrRevertToSelf(v28);
      v29 = BaseSrvpStaticServerData;
    }
    if ( TemporaryObject >= 0 )
    {
      if ( *(_BYTE *)(v29 + 2508) == 1 )
        TemporaryObject = NtMakePermanentObject(Handle);
      NtClose(Handle);
      if ( v9 && !v46 )
        TemporaryObject = -1073741772;
    }
    goto LABEL_58;
  }
  v27 = CsrImpersonateClient(0);
  if ( v27 )
    goto LABEL_49;
  TemporaryObject = -1073741659;
  v11 = v45;
LABEL_132:
  if ( Handle )
    NtClose(Handle);
  RtlFreeHeap(BaseSrvHeap, 0, Heap);
  if ( v11 == 1 && !TemporaryObject && (_BYTE)v63 == 1 )
  {
    SourceLuid = (struct _LUID)999LL;
    v44 = v65;
    AddBSMRequest(v65, v9, &DestinationLuid);
    if ( v9 && (DestinationLuid.LowPart != SourceLuid.LowPart || DestinationLuid.HighPart != SourceLuid.HighPart) )
    {
      if ( (unsigned __int8)CheckForGlobalDriveLetter(v44) )
        AddBSMRequest(v44, 0, &DestinationLuid);
    }
  }
  RtlLeaveCriticalSection(&BaseSrvDosDeviceCritSec);
  return (unsigned int)TemporaryObject;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  mov     [r11+10h], rbx
0x180001017  mov     [r11+18h], rsi
0x18000101b  push    rdi
0x18000101c  push    r12
0x18000101e  push    r13
0x180001020  push    r14
0x180001022  push    r15
0x180001024  sub     rsp, 290h
0x18000102b  mov     rax, cs:__security_cookie
0x180001032  xor     rax, rsp
0x180001035  mov     [rsp+2B8h+var_38], rax
0x18000103d  mov     rbx, rcx
0x180001040  xorps   xmm0, xmm0
0x180001043  movups  xmmword ptr [rsp+2B8h+DestinationString.Length], xmm0
0x18000104b  xorps   xmm1, xmm1
0x18000104e  movups  xmmword ptr [rsp+2B8h+String1], xmm1
0x180001056  xor     eax, eax
0x180001058  movups  xmmword ptr [rsp+2B8h+ObjectAttributes.Length], xmm0
0x180001060  movups  xmmword ptr [rsp+2B8h+ObjectAttributes.ObjectName], xmm0
0x180001068  mov     [r11-198h], rax
0x18000106f  mov     dword ptr [rsp+2B8h+ObjectAttributes.SecurityQualityOfService], eax
0x180001076  xor     ecx, ecx
0x180001078  mov     [rsp+2B8h+DataWritten], ecx
0x18000107f  mov     dword ptr [rsp+2B8h+IdentifierAuthority.Value], eax
0x180001086  mov     word ptr [rsp+2B8h+IdentifierAuthority.Value+4], 100h
0x180001090  mov     dword ptr [rsp+2B8h+var_148.Value], eax
0x180001097  mov     word ptr [rsp+2B8h+var_148.Value+4], 500h
0x1800010a1  mov     [r11-1E0h], rcx
0x1800010a8  mov     [r11-1E8h], rcx
0x1800010af  movups  [rsp+2B8h+SecurityDescriptor], xmm0
0x1800010b7  movups  [rsp+2B8h+var_168], xmm0
0x1800010bf  mov     [r11-158h], rax
0x1800010c6  mov     [r11-230h], rcx
0x1800010cd  mov     [rsp+2B8h+var_24F], al
0x1800010d1  mov     [rsp+2B8h+var_258], al
0x1800010d5  mov     [rsp+2B8h+var_1FC], eax
0x1800010dc  mov     [rsp+2B8h+var_24E], al
0x1800010e0  mov     [rsp+2B8h+var_256], cl
0x1800010e4  lea     r13, [rbx+48h]
0x1800010e8  movzx   ecx, word ptr [r13+0]
0x1800010ed  test    cl, 1
0x1800010f0  jnz     loc_180001DCB
0x1800010f6  movzx   eax, word ptr [rbx+4Ah]
0x1800010fa  test    al, 1
0x1800010fc  jnz     loc_180001DCB
0x180001102  cmp     cx, ax
0x180001105  ja      loc_180001DCB
0x18000110b  mov     r8d, eax
0x18000110e  mov     r15d, 1
0x180001114  mov     r9d, r15d
0x180001117  lea     rdx, [rbx+50h]
0x18000111b  mov     rcx, rbx
0x18000111e  call    cs:__imp_CsrValidateMessageBuffer
0x180001125  nop     dword ptr [rax+rax+00h]
0x18000112a  test    al, al
0x18000112c  jz      loc_180001DCB
0x180001132  movzx   ecx, word ptr [rbx+58h]
0x180001136  test    r15b, cl
0x180001139  jnz     loc_180001DCB
0x18000113f  movzx   eax, word ptr [rbx+5Ah]
0x180001143  test    r15b, al
0x180001146  jnz     loc_180001DCB
0x18000114c  cmp     cx, ax
0x18000114f  ja      loc_180001DCB
0x180001155  mov     r8d, eax
0x180001158  mov     r9d, r15d
0x18000115b  lea     rdx, [rbx+60h]
0x18000115f  mov     rcx, rbx
0x180001162  call    cs:__imp_CsrValidateMessageBuffer
0x180001169  nop     dword ptr [rax+rax+00h]
0x18000116e  test    al, al
0x180001170  jz      loc_180001DCB
0x180001176  mov     r8d, 2000h; Size
0x18000117c  mov     edx, cs:BaseSrvTag; Flags
0x180001182  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180001189  call    cs:__imp_RtlAllocateHeap
0x180001190  nop     dword ptr [rax+rax+00h]
0x180001195  mov     r12, rax
0x180001198  mov     [rsp+2B8h+var_180], rax
0x1800011a0  test    rax, rax
0x1800011a3  jz      loc_180001E5E
0x1800011a9  lea     rcx, BaseSrvDosDeviceCritSec; CriticalSection
0x1800011b0  call    cs:__imp_RtlEnterCriticalSection
0x1800011b7  nop     dword ptr [rax+rax+00h]
0x1800011bc  mov     ecx, [rbx+40h]
0x1800011bf  movzx   r14d, cl
0x1800011c3  shr     r14b, 1
0x1800011c6  and     r14b, r15b
0x1800011c9  mov     byte ptr [rsp+2B8h+MaxCount+6], r14b
0x1800011ce  xor     r9d, r9d
0x1800011d1  mov     [rsp+2B8h+var_1F0], r9d
0x1800011d9  mov     [rsp+2B8h+var_1EC], r9d
0x1800011e1  mov     [rsp+2B8h+Handle], r9
0x1800011e6  mov     [rsp+2B8h+var_257], r9b
0x1800011eb  mov     [rsp+2B8h+var_254], r9d
0x1800011f0  mov     edx, ecx
0x1800011f2  mov     rax, cs:BaseSrvpStaticServerData
0x1800011f9  cmp     [rax+9CCh], r15b
0x180001200  jnz     short loc_18000120B
0x180001202  test    cl, 8
0x180001205  jz      loc_180001A7A
0x18000120b  xor     dil, dil
0x18000120e  test    dl, 10h
0x180001211  jz      loc_18000172A
0x180001217  test    dil, dil
0x18000121a  jnz     loc_18000172A
0x180001220  mov     r15d, 0C000000Dh
0x180001226  mov     [rsp+2B8h+var_254], r15d
0x18000122b  jmp     loc_180001D5B
0x180001230  mov     r13, [rsp+2B8h+String1+8]
0x180001238  mov     [rsp+2B8h+var_1D0], r13
0x180001240  mov     rdi, r13
0x180001243  mov     [rsp+2B8h+var_188], r13
0x18000124b  xor     dl, dl
0x18000124d  mov     [rsp+2B8h+var_257], dl
0x180001251  mov     byte ptr [rsp+2B8h+MaxCount+4], dl
0x180001255  movzx   eax, word ptr [rdi]
0x180001258  test    ax, ax
0x18000125b  jz      loc_1800012EB
0x180001261  mov     esi, r9d
0x180001264  mov     [rsp+2B8h+var_1D8], r9d
0x18000126c  mov     rcx, rdi; String1
0x18000126f  mov     [rsp+2B8h+var_1F8], rcx
0x180001277  nop     word ptr [rax+rax+00000000h]
0x180001280  add     rdi, 2
0x180001284  mov     [rsp+2B8h+var_188], rdi
0x18000128c  test    ax, ax
0x18000128f  jz      short loc_18000129F
0x180001291  inc     esi
0x180001293  mov     [rsp+2B8h+var_1D8], esi
0x18000129a  movzx   eax, word ptr [rdi]
0x18000129d  jmp     short loc_180001280
0x18000129f  test    dl, dl
0x1800012a1  jnz     loc_1800016D2
0x1800012a7  mov     eax, dword ptr [rsp+2B8h+MaxCount]
0x1800012ab  test    byte ptr [rbx+40h], 4
0x1800012af  jz      loc_180001C6D
0x1800012b5  cmp     eax, esi
0x1800012b7  jnz     loc_180001C63
0x1800012bd  mov     rdx, [rsp+2B8h+String2]; String2
0x1800012c5  call    cs:__imp__wcsicmp
0x1800012cc  nop     dword ptr [rax+rax+00h]
0x1800012d1  test    eax, eax
0x1800012d3  jnz     loc_180001C52
0x1800012d9  mov     dl, 1
0x1800012db  mov     [rsp+2B8h+var_257], dl
0x1800012df  mov     byte ptr [rsp+2B8h+MaxCount+4], dl
0x1800012e3  xor     r9d, r9d
0x1800012e6  jmp     loc_180001255
0x1800012eb  mov     [r13+0], r9w
0x1800012f0  add     r13, 2
0x1800012f4  mov     [rsp+2B8h+var_1D0], r13
0x1800012fc  mov     rcx, [rsp+2B8h+String1+8]
0x180001304  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000130b  nop     dword ptr [rax+rax+00h]
0x180001310  inc     rax
0x180001313  cmp     word ptr [rcx+rax*2], 0
0x180001318  jnz     short loc_180001310
0x18000131a  add     rax, rax
0x18000131d  mov     [rsp+2B8h+String2], rax
0x180001325  mov     r8d, 0FFFFh
0x18000132b  cmp     rax, r8
0x18000132e  ja      loc_180001705
0x180001334  movzx   edx, ax
0x180001337  mov     word ptr [rsp+2B8h+String1], ax
0x18000133f  test    dx, dx
0x180001342  jz      loc_1800013F1
0x180001348  sub     r13, rcx
0x18000134b  mov     [rsp+2B8h+String2], r13
0x180001353  cmp     r13, r8
0x180001356  ja      loc_180001CC2
0x18000135c  mov     word ptr [rsp+2B8h+String1+2], r13w
0x180001365  jmp     loc_1800013F1
0x18000136a  test    r14b, r14b
0x18000136d  jnz     loc_180001723
0x180001373  lea     eax, [rcx+1]
0x180001376  mov     ecx, eax
0x180001378  add     rcx, rcx
0x18000137b  sub     rdi, rcx
0x18000137e  mov     rdx, rdi; SourceString
0x180001381  lea     rcx, [rsp+2B8h+String1]; DestinationString
0x180001389  call    cs:__imp_RtlInitUnicodeString
0x180001390  nop     dword ptr [rax+rax+00h]
0x180001395  xor     r9d, r9d
0x180001398  mov     rcx, [rsp+2B8h+Handle]; Handle
0x18000139d  test    rcx, rcx
0x1800013a0  jz      short loc_1800013CE
0x1800013a2  call    cs:__imp_NtMakeTemporaryObject
0x1800013a9  nop     dword ptr [rax+rax+00h]
0x1800013ae  mov     r15d, eax
0x1800013b1  mov     [rsp+2B8h+var_254], eax
0x1800013b5  mov     rcx, [rsp+2B8h+Handle]; Handle
0x1800013ba  call    cs:__imp_NtClose
0x1800013c1  nop     dword ptr [rax+rax+00h]
0x1800013c6  xor     r9d, r9d
0x1800013c9  mov     [rsp+2B8h+Handle], r9
0x1800013ce  test    r15d, r15d
0x1800013d1  js      loc_180001695
0x1800013d7  test    r14b, r14b
0x1800013da  jnz     loc_180001230
0x1800013e0  test    sil, sil
0x1800013e3  jnz     loc_180001CD0
0x1800013e9  movzx   eax, word ptr [rsp+2B8h+String1]
0x1800013f1  test    ax, ax
0x1800013f4  jz      loc_180001695
0x1800013fa  lea     rax, [rsp+2B8h+var_1E8]
0x180001402  mov     [rsp+2B8h+Sid], rax; Sid
0x180001407  mov     [rsp+2B8h+SubAuthority7], r9d; SubAuthority7
0x18000140c  mov     [rsp+2B8h+SubAuthority6], r9d; SubAuthority6
0x180001411  mov     [rsp+2B8h+SubAuthority5], r9d; SubAuthority5
0x180001416  mov     [rsp+2B8h+SubAuthority4], r9d; SubAuthority4
0x18000141b  mov     [rsp+2B8h+SubAuthority3], r9d; SubAuthority3
0x180001420  mov     [rsp+2B8h+SubAuthority2], r9d; SubAuthority2
0x180001425  xor     r9d, r9d; SubAuthority1
0x180001428  xor     r8d, r8d; SubAuthority0
0x18000142b  mov     dl, 1; SubAuthorityCount
0x18000142d  lea     rcx, [rsp+2B8h+IdentifierAuthority]; IdentifierAuthority
0x180001435  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000143c  nop     dword ptr [rax+rax+00h]
0x180001441  mov     r15d, eax
0x180001444  mov     [rsp+2B8h+var_254], eax
0x180001448  test    eax, eax
0x18000144a  js      loc_180001695
0x180001450  lea     rax, [rsp+2B8h+var_1E0]
0x180001458  mov     [rsp+2B8h+Sid], rax; Sid
0x18000145d  xor     esi, esi
0x18000145f  mov     [rsp+2B8h+SubAuthority7], esi; SubAuthority7
0x180001463  mov     [rsp+2B8h+SubAuthority6], esi; SubAuthority6
0x180001467  mov     [rsp+2B8h+SubAuthority5], esi; SubAuthority5
0x18000146b  mov     [rsp+2B8h+SubAuthority4], esi; SubAuthority4
0x18000146f  mov     [rsp+2B8h+SubAuthority3], esi; SubAuthority3
0x180001473  mov     [rsp+2B8h+SubAuthority2], esi; SubAuthority2
0x180001477  xor     r9d, r9d; SubAuthority1
0x18000147a  lea     r8d, [rsi+0Ch]; SubAuthority0
0x18000147e  mov     dl, 1; SubAuthorityCount
0x180001480  lea     rcx, [rsp+2B8h+var_148]; IdentifierAuthority
0x180001488  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000148f  nop     dword ptr [rax+rax+00h]
0x180001494  mov     r15d, eax
0x180001497  mov     [rsp+2B8h+var_254], eax
0x18000149b  test    eax, eax
0x18000149d  js      loc_180001D0D
0x1800014a3  mov     ebx, 1
0x1800014a8  mov     edx, ebx; Revision
0x1800014aa  lea     rcx, [rsp+2B8h+SecurityDescriptor]; SecurityDescriptor
0x1800014b2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800014b9  nop     dword ptr [rax+rax+00h]
0x1800014be  mov     [rsp+2B8h+var_254], eax
0x1800014c2  mov     edx, 100h; AclSize
0x1800014c7  lea     r8d, [rsi+2]; AclRevision
0x1800014cb  lea     rcx, [rsp+2B8h+Acl]; Acl
0x1800014d3  call    cs:__imp_RtlCreateAcl
0x1800014da  nop     dword ptr [rax+rax+00h]
0x1800014df  mov     [rsp+2B8h+var_254], eax
0x1800014e3  mov     eax, cs:ServiceSessionId
0x1800014e9  cmp     cs:SessionId, eax
0x1800014ef  jnz     loc_180001711
0x1800014f5  mov     ebx, 10001h
0x1800014fa  mov     r9, [rsp+2B8h+var_1E8]; Sid
0x180001502  mov     r8d, ebx; AccessMask
0x180001505  mov     edx, 2; Revision
0x18000150a  lea     rcx, [rsp+2B8h+Acl]; Acl
0x180001512  call    cs:__imp_RtlAddAccessAllowedAce
0x180001519  nop     dword ptr [rax+rax+00h]
0x18000151e  mov     [rsp+2B8h+var_254], eax
0x180001522  mov     r9, [rsp+2B8h+var_1E0]; Sid
0x18000152a  mov     r8d, ebx; AccessMask
0x18000152d  mov     edx, 2; Revision
0x180001532  lea     rcx, [rsp+2B8h+Acl]; Acl
0x18000153a  call    cs:__imp_RtlAddAccessAllowedAce
0x180001541  nop     dword ptr [rax+rax+00h]
0x180001546  mov     [rsp+2B8h+var_254], eax
0x18000154a  mov     rcx, [rsp+2B8h+var_1E8]; Sid
0x180001552  call    cs:__imp_RtlFreeSid
0x180001559  nop     dword ptr [rax+rax+00h]
0x18000155e  mov     rcx, [rsp+2B8h+var_1E0]; Sid
0x180001566  call    cs:__imp_RtlFreeSid
0x18000156d  nop     dword ptr [rax+rax+00h]
0x180001572  mov     r9b, 1; DaclDefaulted
0x180001575  lea     r8, [rsp+2B8h+Acl]; Dacl
0x18000157d  movzx   edx, r9b; DaclPresent
0x180001581  lea     rcx, [rsp+2B8h+SecurityDescriptor]; SecurityDescriptor
0x180001589  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180001590  nop     dword ptr [rax+rax+00h]
0x180001595  mov     [rsp+2B8h+var_254], eax
0x180001599  lea     rax, [rsp+2B8h+SecurityDescriptor]
0x1800015a1  mov     [rsp+2B8h+ObjectAttributes.SecurityDescriptor], rax
0x1800015a9  mov     rax, cs:BaseSrvpStaticServerData
0x1800015b0  movzx   ebx, [rsp+2B8h+var_256]
0x1800015b5  cmp     byte ptr [rax+9CCh], 1
0x1800015bc  jnz     loc_18000169F
0x1800015c2  test    bl, bl
0x1800015c4  jnz     loc_18000169F
0x1800015ca  xor     ecx, ecx
0x1800015cc  call    cs:__imp_CsrImpersonateClient
0x1800015d3  nop     dword ptr [rax+rax+00h]
0x1800015d8  movzx   edi, al
0x1800015db  test    al, al
0x1800015dd  jz      loc_1800016F0
  ... truncated ...
```
