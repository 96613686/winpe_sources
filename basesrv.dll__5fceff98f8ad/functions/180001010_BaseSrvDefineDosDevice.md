# BaseSrvDefineDosDevice

- ea: `0x180001010`
- end: `0x180001e97`
- name: `BaseSrvDefineDosDevice`
- size: `3719`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001010`
- `0x180001ea0`
- `0x180002010`
- `0x180002180`
- `0x180002240`
- `0x18000db11`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000117c`
- `ntdll!RtlAllocateHeap` at `0x18000117c`
- `ntdll!_wcsicmp` at `0x1800012c8`
- `ntdll!_wcsicmp` at `0x1800012c8`
- `ntdll!NtClose` at `0x1800013a6`
- `ntdll!NtClose` at `0x180001681`
- `ntdll!NtClose` at `0x180001e45`
- `ntdll!NtClose` at `0x18000dc04`
- `ntdll!NtClose` at `0x1800013a6`
- `ntdll!NtClose` at `0x180001681`
- `ntdll!NtClose` at `0x180001e45`
- `ntdll!NtClose` at `0x18000dc04`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800014b6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800014b6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000158f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000158f`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180001617`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180001617`
- `ntdll!RtlFreeHeap` at `0x180001d6c`
- `ntdll!RtlFreeHeap` at `0x18000dc21`
- `ntdll!RtlFreeHeap` at `0x180001d6c`
- `ntdll!RtlFreeHeap` at `0x18000dc21`
- `ntdll!RtlEnterCriticalSection` at `0x1800011b8`
- `ntdll!RtlEnterCriticalSection` at `0x1800011b8`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180001abb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180001abb`
- `ntdll!_snwprintf_s` at `0x18000175f`
- `ntdll!_snwprintf_s` at `0x1800018d6`
- `ntdll!_snwprintf_s` at `0x18000175f`
- `ntdll!_snwprintf_s` at `0x1800018d6`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18000182f`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18000182f`
- `ntdll!wcsnlen` at `0x180001946`
- `ntdll!wcsnlen` at `0x180001946`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800019fc`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800019fc`
- `ntdll!NtMakeTemporaryObject` at `0x18000138e`
- `ntdll!NtMakeTemporaryObject` at `0x18000138e`
- `ntdll!_wcsnicmp` at `0x180001c7b`
- `ntdll!_wcsnicmp` at `0x180001c7b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001421`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000148c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001421`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000148c`
- `ntdll!RtlFreeSid` at `0x180001558`
- `ntdll!RtlFreeSid` at `0x18000156c`
- `ntdll!RtlFreeSid` at `0x180001d12`
- `ntdll!RtlFreeSid` at `0x180001558`
- `ntdll!RtlFreeSid` at `0x18000156c`
- `ntdll!RtlFreeSid` at `0x180001d12`
- `ntdll!RtlCreateAcl` at `0x1800014d9`
- `ntdll!RtlCreateAcl` at `0x1800014d9`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001518`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001540`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001518`
- `ntdll!RtlAddAccessAllowedAce` at `0x180001540`
- `ntdll!NtMakePermanentObject` at `0x180001669`
- `ntdll!NtMakePermanentObject` at `0x180001669`
- `ntdll!RtlCopyLuid` at `0x180001e70`
- `ntdll!RtlCopyLuid` at `0x18000dc6a`
- `ntdll!RtlCopyLuid` at `0x180001e70`
- `ntdll!RtlCopyLuid` at `0x18000dc6a`
- `ntdll!RtlLeaveCriticalSection` at `0x180001d86`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dcd4`
- `ntdll!RtlLeaveCriticalSection` at `0x180001d86`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dcd4`
- `ntdll!RtlInitUnicodeString` at `0x180001375`
- `ntdll!RtlInitUnicodeString` at `0x1800017aa`
- `ntdll!RtlInitUnicodeString` at `0x180001375`
- `ntdll!RtlInitUnicodeString` at `0x1800017aa`
- `CSRSRV!CsrIsClientSandboxed` at `0x1800016ab`
- `CSRSRV!CsrIsClientSandboxed` at `0x1800016ab`
- `CSRSRV!CsrRevertToSelf` at `0x180001643`
- `CSRSRV!CsrRevertToSelf` at `0x180001842`
- `CSRSRV!CsrRevertToSelf` at `0x180001643`
- `CSRSRV!CsrRevertToSelf` at `0x180001842`
- `CSRSRV!CsrImpersonateClient` at `0x1800015d2`
- `CSRSRV!CsrImpersonateClient` at `0x1800017fb`
- `CSRSRV!CsrImpersonateClient` at `0x1800015d2`
- `CSRSRV!CsrImpersonateClient` at `0x1800017fb`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001111`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001155`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001111`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180001155`

## pseudocode

```c
__int64 __fastcall BaseSrvDefineDosDevice(__int64 a1)
{
  _WORD *v2; // r13
  unsigned __int16 v3; // cx
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // ax
  wchar_t *Heap; // rax
  wchar_t *v8; // r15
  int v9; // ecx
  bool v10; // r12
  int v11; // edi
  NTSTATUS TemporaryObject; // r14d
  wchar_t *v13; // r13
  wchar_t *v14; // rdi
  char v15; // dl
  wchar_t v16; // ax
  int v17; // esi
  wchar_t *v18; // rcx
  unsigned int v19; // eax
  wchar_t *v20; // r13
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r13
  const WCHAR *v24; // rdx
  ACCESS_MASK v25; // ebx
  char v26; // di
  __int64 v27; // rax
  int v28; // eax
  char *v29; // r13
  size_t v30; // rdi
  unsigned __int16 v31; // ax
  unsigned __int16 v32; // ax
  int v33; // ecx
  unsigned __int64 v34; // rdx
  WCHAR *v35; // rax
  WCHAR v36; // cx
  int v37; // ecx
  unsigned int v39; // ebx
  char v40; // [rsp+60h] [rbp-258h]
  int CallerLuid; // [rsp+64h] [rbp-254h]
  char v42; // [rsp+68h] [rbp-250h]
  char v43; // [rsp+69h] [rbp-24Fh] BYREF
  char v44; // [rsp+6Ah] [rbp-24Eh]
  char v45; // [rsp+6Bh] [rbp-24Dh]
  int v46; // [rsp+6Ch] [rbp-24Ch]
  HANDLE Handle; // [rsp+70h] [rbp-248h] BYREF
  char v48; // [rsp+78h] [rbp-240h]
  char v49; // [rsp+79h] [rbp-23Fh]
  bool v50; // [rsp+7Ah] [rbp-23Eh]
  int v51; // [rsp+7Ch] [rbp-23Ch]
  ULONG DataWritten; // [rsp+80h] [rbp-238h] BYREF
  _LUID DestinationLuid; // [rsp+88h] [rbp-230h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-228h] BYREF
  size_t MaxCount; // [rsp+A0h] [rbp-218h]
  int v56; // [rsp+A8h] [rbp-210h]
  struct _LUID SourceLuid; // [rsp+B0h] [rbp-208h]
  WCHAR v58; // [rsp+B8h] [rbp-200h]
  int v59; // [rsp+BCh] [rbp-1FCh]
  unsigned int v60; // [rsp+C0h] [rbp-1F8h]
  wchar_t *v61; // [rsp+C8h] [rbp-1F0h]
  PSID Sid; // [rsp+D0h] [rbp-1E8h] BYREF
  wchar_t *String2; // [rsp+D8h] [rbp-1E0h]
  PSID v64; // [rsp+E0h] [rbp-1D8h] BYREF
  int v65; // [rsp+E8h] [rbp-1D0h]
  wchar_t *v66; // [rsp+F0h] [rbp-1C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+F8h] [rbp-1C0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+108h] [rbp-1B0h] BYREF
  wchar_t *v69; // [rsp+138h] [rbp-180h]
  wchar_t *v70; // [rsp+140h] [rbp-178h]
  _OWORD SecurityDescriptor[2]; // [rsp+148h] [rbp-170h] BYREF
  __int64 v72; // [rsp+168h] [rbp-150h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+170h] [rbp-148h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v74; // [rsp+178h] [rbp-140h] BYREF
  _ACL Acl; // [rsp+180h] [rbp-138h] BYREF

  DestinationString = 0;
  *(_OWORD *)String1 = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  DataWritten = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)v74.Value = 0;
  *(_WORD *)&v74.Value[4] = 1280;
  v64 = 0;
  Sid = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v72 = 0;
  DestinationLuid = 0;
  v43 = 0;
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
  v8 = Heap;
  v70 = Heap;
  if ( !Heap )
    return 3221225495LL;
  LOBYTE(Heap) = 0;
  v46 = (int)Heap;
  v44 = 0;
  v59 = (int)Heap;
  v45 = 0;
  RtlEnterCriticalSection(&BaseSrvDosDeviceCritSec);
  v9 = *(_DWORD *)(a1 + 64);
  v10 = (v9 & 2) != 0;
  v50 = v10;
  v60 = 0;
  Handle = 0;
  v40 = 0;
  if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) == 1
    && (v9 & 8) == 0
    && (v35 = *(WCHAR **)(a1 + 80)) != 0
    && *v2 == 4
    && v35[1] == 58 )
  {
    v58 = *v35;
    v36 = v58;
    if ( (unsigned int)v58 - 97 <= 0x19 )
    {
      v36 = RtlUpcaseUnicodeChar(v58);
      v58 = v36;
    }
    v60 = v36 - 65;
    v11 = (unsigned __int8)v46;
    if ( v60 < 0x1A )
      v11 = 1;
    v46 = v11;
    v44 = v11;
  }
  else
  {
    LOBYTE(v11) = v46;
  }
  if ( (*(_BYTE *)(a1 + 64) & 0x10) != 0 && !(_BYTE)v11 )
  {
    TemporaryObject = -1073741811;
    goto LABEL_129;
  }
  v61 = v8;
  v56 = 4096;
  v28 = _snwprintf_s(v8, 0x1000u, 0xFFFu, L"\\??\\%wZ", v2);
  if ( v28 == -1 )
    v28 = 4095;
  MaxCount = (size_t)&v8[v28 + 1];
  v61 = (wchar_t *)MaxCount;
  v51 = 4095 - v28;
  v56 = 4095 - v28;
  RtlInitUnicodeString(&DestinationString, v8);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v42 = 1;
  v49 = CsrImpersonateClient(0);
  if ( !v49 )
  {
    TemporaryObject = -1073741659;
    goto LABEL_129;
  }
  if ( (_BYTE)v11 == 1 )
  {
    CallerLuid = GetCallerLuid(&DestinationLuid);
    v37 = (unsigned __int8)v59;
    if ( CallerLuid >= 0 )
      v37 = 1;
    v59 = v37;
    v45 = v37;
  }
  TemporaryObject = NtOpenSymbolicLinkObject(&Handle, 0x10001u, &ObjectAttributes);
  CsrRevertToSelf();
  if ( (*(_BYTE *)(a1 + 64) & 0x10) != 0 )
  {
    if ( TemporaryObject < 0 )
      Handle = 0;
    if ( v10 && TemporaryObject == -1073741772 )
      TemporaryObject = 0;
    goto LABEL_129;
  }
  if ( TemporaryObject == -1073741772 )
  {
    Handle = 0;
    if ( v10 )
    {
      if ( !*(_WORD *)(a1 + 88) )
        TemporaryObject = 0;
      goto LABEL_129;
    }
    v42 = 0;
    TemporaryObject = 0;
  }
  else
  {
    if ( TemporaryObject < 0 )
      goto LABEL_57;
    if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) == 1 )
    {
      TemporaryObject = IsGlobalSymbolicLink(Handle);
      if ( TemporaryObject < 0 )
        goto LABEL_129;
    }
  }
  v29 = (char *)MaxCount;
  LODWORD(v30) = v51;
  v31 = *(_WORD *)(a1 + 88);
  if ( v31 )
  {
    v32 = wcsnlen(*(const wchar_t **)(a1 + 96), (unsigned __int64)v31 >> 1);
    LODWORD(MaxCount) = v32;
    if ( (unsigned int)v32 + 1 >= (unsigned int)v30 )
    {
      TemporaryObject = -1073741619;
      goto LABEL_129;
    }
    v30 = 2LL * v32;
    memmove_0(v29, *(const void **)(a1 + 96), v30);
    *(_WORD *)&v29[v30] = 0;
    String2 = (wchar_t *)v29;
    v33 = MaxCount;
    v29 += 2 * (unsigned int)(MaxCount + 1);
    v61 = (wchar_t *)v29;
    LOWORD(v30) = -1 - MaxCount + v51;
    v56 = -1 - MaxCount + v51;
  }
  else
  {
    String2 = 0;
    v33 = 0;
    LODWORD(MaxCount) = 0;
  }
  if ( !v42 )
  {
    if ( v10 )
      v24 = 0;
    else
      v24 = (const WCHAR *)&v29[-2 * (v33 + 1)];
    RtlInitUnicodeString((PUNICODE_STRING)String1, v24);
    goto LABEL_35;
  }
  LOWORD(String1[0]) = 0;
  WORD1(String1[0]) = 2 * v30;
  String1[1] = (wchar_t *)v29;
  DataWritten = 0;
  TemporaryObject = NtQuerySymbolicLinkObject(Handle, (PUNICODE_STRING)String1, &DataWritten);
  if ( DataWritten == WORD1(String1[0]) )
    goto LABEL_109;
  if ( TemporaryObject < 0 )
    goto LABEL_129;
  v34 = (unsigned __int64)DataWritten >> 1;
  if ( (unsigned int)v34 >= 2
    && !*(_WORD *)&v29[2 * (unsigned int)(v34 - 2)]
    && !*(_WORD *)&v29[2 * (unsigned int)(v34 - 1)] )
  {
    WORD1(String1[0]) = DataWritten;
    goto LABEL_35;
  }
  if ( !(_DWORD)v34 || *(_WORD *)&v29[2 * (unsigned int)(v34 - 1)] )
  {
    if ( (unsigned __int64)DataWritten + 2 < WORD1(String1[0]) )
    {
      *(_WORD *)&v29[2 * (unsigned int)v34] = 0;
      *(_WORD *)&v29[2 * (unsigned int)(v34 + 1)] = 0;
      WORD1(String1[0]) = DataWritten + 4;
      goto LABEL_35;
    }
LABEL_109:
    TemporaryObject = -2147483643;
    goto LABEL_129;
  }
  *(_WORD *)&v29[2 * (unsigned int)v34] = 0;
  WORD1(String1[0]) = DataWritten + 2;
LABEL_35:
  if ( Handle )
  {
    TemporaryObject = NtMakeTemporaryObject(Handle);
    NtClose(Handle);
    Handle = 0;
  }
  if ( TemporaryObject < 0 )
    goto LABEL_129;
  if ( !v10 )
  {
    if ( v42 )
    {
      String1[1] -= (unsigned int)(MaxCount + 1);
      LOWORD(v22) = 2 * MaxCount;
      LOWORD(String1[0]) = 2 * MaxCount;
      WORD1(String1[0]) += 2 * MaxCount + 2;
    }
    else
    {
      LOWORD(v22) = String1[0];
    }
    goto LABEL_41;
  }
  v13 = String1[1];
  v66 = String1[1];
  v14 = String1[1];
  v69 = String1[1];
  v15 = 0;
  v40 = 0;
  v48 = 0;
  while ( 1 )
  {
    v16 = *v14;
    if ( !*v14 )
      break;
    v17 = 0;
    v65 = 0;
    v18 = v14;
    v61 = v14;
    while ( 1 )
    {
      v69 = ++v14;
      if ( !v16 )
        break;
      v65 = ++v17;
      v16 = *v14;
    }
    if ( v15 )
      goto LABEL_61;
    v19 = MaxCount;
    if ( (*(_BYTE *)(a1 + 64) & 4) == 0 )
      goto LABEL_145;
    if ( (_DWORD)MaxCount == v17 )
    {
      if ( !_wcsicmp(v18, String2) )
        goto LABEL_25;
      v19 = MaxCount;
      v18 = v61;
      v15 = v40;
    }
    if ( (*(_BYTE *)(a1 + 64) & 4) != 0 )
    {
LABEL_61:
      if ( v18 != v13 )
      {
        memmove_0(v13, v18, 2LL * (unsigned int)(v17 + 1));
        v15 = v40;
      }
      v13 += (unsigned int)(v17 + 1);
      v66 = v13;
    }
    else
    {
LABEL_145:
      if ( v19 && _wcsnicmp(v18, String2, v19) )
      {
        v18 = v61;
        v15 = v40;
        goto LABEL_61;
      }
LABEL_25:
      v15 = 1;
      v40 = 1;
      v48 = 1;
    }
  }
  *v13 = 0;
  v20 = v13 + 1;
  v66 = v20;
  v21 = -1;
  do
    ++v21;
  while ( String1[1][v21] );
  v22 = 2 * v21;
  if ( v22 > 0xFFFF )
  {
    LOWORD(v22) = -1;
    LOWORD(String1[0]) = -1;
    goto LABEL_30;
  }
  LOWORD(String1[0]) = v22;
  if ( (_WORD)v22 )
  {
LABEL_30:
    v23 = (char *)v20 - (char *)String1[1];
    if ( v23 > 0xFFFF )
      WORD1(String1[0]) = -1;
    else
      WORD1(String1[0]) = v23;
  }
LABEL_41:
  if ( !(_WORD)v22 )
    goto LABEL_129;
  TemporaryObject = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( TemporaryObject < 0 )
    goto LABEL_129;
  TemporaryObject = RtlAllocateAndInitializeSid(&v74, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v64);
  if ( TemporaryObject < 0 )
  {
    RtlFreeSid(Sid);
    goto LABEL_129;
  }
  v25 = 1;
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlCreateAcl(&Acl, 0x100u, 2u);
  if ( SessionId == ServiceSessionId || (ProtectionMode & 3) == 0 )
    v25 = 65537;
  RtlAddAccessAllowedAce(&Acl, 2u, v25, Sid);
  RtlAddAccessAllowedAce(&Acl, 2u, v25, v64);
  RtlFreeSid(Sid);
  RtlFreeSid(v64);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 1u);
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) != 1 )
  {
    TemporaryObject = CsrIsClientSandboxed(0, &v43);
    if ( TemporaryObject < 0 )
      goto LABEL_129;
    if ( v43 )
    {
      TemporaryObject = -1073741790;
      goto LABEL_129;
    }
    v26 = v49;
LABEL_48:
    if ( !*(_BYTE *)(BaseSrvpStaticServerData + 2508) )
      ObjectAttributes.Attributes |= 0x10u;
    TemporaryObject = NtCreateSymbolicLinkObject(&Handle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)String1);
    v27 = BaseSrvpStaticServerData;
    if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) == 1 && v26 )
    {
      CsrRevertToSelf();
      v27 = BaseSrvpStaticServerData;
    }
    if ( TemporaryObject >= 0 )
    {
      if ( *(_BYTE *)(v27 + 2508) == 1 )
        TemporaryObject = NtMakePermanentObject(Handle);
      NtClose(Handle);
      if ( v10 && !v40 )
        TemporaryObject = -1073741772;
    }
LABEL_57:
    Handle = 0;
    goto LABEL_129;
  }
  v26 = CsrImpersonateClient(0);
  if ( v26 )
    goto LABEL_48;
  TemporaryObject = -1073741659;
LABEL_129:
  if ( Handle )
    NtClose(Handle);
  RtlFreeHeap(BaseSrvHeap, 0, v8);
  if ( (_BYTE)v46 == 1 && !TemporaryObject && (_BYTE)v59 == 1 )
  {
    SourceLuid = (struct _LUID)999LL;
    v39 = v60;
    AddBSMRequest(v60, v10, &DestinationLuid);
    if ( v10 && (DestinationLuid.LowPart != SourceLuid.LowPart || DestinationLuid.HighPart != SourceLuid.HighPart) )
    {
      if ( (unsigned __int8)CheckForGlobalDriveLetter(v39) )
        AddBSMRequest(v39, 0, &DestinationLuid);
    }
  }
  RtlLeaveCriticalSection(&BaseSrvDosDeviceCritSec);
  return (unsigned int)TemporaryObject;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  mov     [rsp+arg_10], rsi
0x18000101a  push    rdi
0x18000101b  push    r12
0x18000101d  push    r13
0x18000101f  push    r14
0x180001021  push    r15
0x180001023  sub     rsp, 290h
0x18000102a  mov     rax, cs:__security_cookie
0x180001031  xor     rax, rsp
0x180001034  mov     [rsp+2B8h+var_38], rax
0x18000103c  mov     rbx, rcx
0x18000103f  xorps   xmm0, xmm0
0x180001042  movups  xmmword ptr [rsp+2B8h+DestinationString.Length], xmm0
0x18000104a  xorps   xmm1, xmm1
0x18000104d  movups  xmmword ptr [rsp+2B8h+String1], xmm1
0x180001055  xor     ecx, ecx
0x180001057  mov     [rsp+2B8h+Handle], rcx
0x18000105c  xor     eax, eax
0x18000105e  movups  xmmword ptr [rsp+2B8h+ObjectAttributes.Length], xmm0
0x180001066  movups  xmmword ptr [rsp+2B8h+ObjectAttributes.ObjectName], xmm0
0x18000106e  movups  xmmword ptr [rsp+2B8h+ObjectAttributes+1Ch], xmm0
0x180001076  mov     [rsp+2B8h+DataWritten], ecx
0x18000107d  mov     dword ptr [rsp+2B8h+IdentifierAuthority.Value], eax
0x180001084  mov     word ptr [rsp+2B8h+IdentifierAuthority.Value+4], 100h
0x18000108e  mov     dword ptr [rsp+2B8h+var_140.Value], eax
0x180001095  mov     word ptr [rsp+2B8h+var_140.Value+4], 500h
0x18000109f  mov     [rsp+2B8h+var_1D8], rcx
0x1800010a7  mov     [rsp+2B8h+var_1E8], rcx
0x1800010af  movups  [rsp+2B8h+SecurityDescriptor], xmm0
0x1800010b7  movups  [rsp+2B8h+var_160], xmm0
0x1800010bf  mov     [rsp+2B8h+var_150], rax
0x1800010c7  mov     qword ptr [rsp+2B8h+DestinationLuid.LowPart], rcx
0x1800010cf  mov     [rsp+2B8h+var_24F], al
0x1800010d3  mov     [rsp+2B8h+var_257], al
0x1800010d7  lea     r13, [rbx+48h]
0x1800010db  movzx   ecx, word ptr [r13+0]
0x1800010e0  test    cl, 1
0x1800010e3  jnz     loc_180001DC3
0x1800010e9  movzx   eax, word ptr [rbx+4Ah]
0x1800010ed  test    al, 1
0x1800010ef  jnz     loc_180001DC3
0x1800010f5  cmp     cx, ax
0x1800010f8  ja      loc_180001DC3
0x1800010fe  mov     r8d, eax
0x180001101  mov     r14d, 1
0x180001107  mov     r9d, r14d
0x18000110a  lea     rdx, [rbx+50h]
0x18000110e  mov     rcx, rbx
0x180001111  call    cs:__imp_CsrValidateMessageBuffer
0x180001118  nop     dword ptr [rax+rax+00h]
0x18000111d  test    al, al
0x18000111f  jz      loc_180001DC3
0x180001125  movzx   ecx, word ptr [rbx+58h]
0x180001129  test    r14b, cl
0x18000112c  jnz     loc_180001DC3
0x180001132  movzx   eax, word ptr [rbx+5Ah]
0x180001136  test    r14b, al
0x180001139  jnz     loc_180001DC3
0x18000113f  cmp     cx, ax
0x180001142  ja      loc_180001DC3
0x180001148  mov     r8d, eax
0x18000114b  mov     r9d, r14d
0x18000114e  lea     rdx, [rbx+60h]
0x180001152  mov     rcx, rbx
0x180001155  call    cs:__imp_CsrValidateMessageBuffer
0x18000115c  nop     dword ptr [rax+rax+00h]
0x180001161  test    al, al
0x180001163  jz      loc_180001DC3
0x180001169  mov     r8d, 2000h; Size
0x18000116f  mov     edx, cs:BaseSrvTag; Flags
0x180001175  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000117c  call    cs:__imp_RtlAllocateHeap
0x180001183  nop     dword ptr [rax+rax+00h]
0x180001188  mov     r15, rax
0x18000118b  mov     [rsp+2B8h+var_178], rax
0x180001193  test    rax, rax
0x180001196  jz      loc_180001E56
0x18000119c  xor     al, al
0x18000119e  mov     [rsp+2B8h+var_24C], eax
0x1800011a2  mov     [rsp+2B8h+var_24E], al
0x1800011a6  mov     [rsp+2B8h+var_1FC], eax
0x1800011ad  mov     [rsp+2B8h+var_24D], al
0x1800011b1  lea     rcx, BaseSrvDosDeviceCritSec; CriticalSection
0x1800011b8  call    cs:__imp_RtlEnterCriticalSection
0x1800011bf  nop     dword ptr [rax+rax+00h]
0x1800011c4  mov     ecx, [rbx+40h]
0x1800011c7  movzx   r12d, cl
0x1800011cb  shr     r12b, 1
0x1800011ce  and     r12b, r14b
0x1800011d1  mov     [rsp+2B8h+var_23E], r12b
0x1800011d6  xor     r8d, r8d
0x1800011d9  mov     [rsp+2B8h+var_1F8], r8d
0x1800011e1  mov     [rsp+2B8h+Handle], r8
0x1800011e6  mov     [rsp+2B8h+var_258], r8b
0x1800011eb  mov     [rsp+2B8h+var_254], r8d
0x1800011f0  mov     rax, cs:BaseSrvpStaticServerData
0x1800011f7  cmp     [rax+9CCh], r14b
0x1800011fe  jnz     short loc_180001209
0x180001200  test    cl, 8
0x180001203  jz      loc_180001A84
0x180001209  mov     edi, [rsp+2B8h+var_24C]
0x18000120d  test    byte ptr [rbx+40h], 10h
0x180001211  jz      loc_180001732
0x180001217  test    dil, dil
0x18000121a  jnz     loc_180001732
0x180001220  mov     r14d, 0C000000Dh
0x180001226  mov     [rsp+2B8h+var_254], r14d
0x18000122b  jmp     loc_180001D52
0x180001230  mov     r13, [rsp+2B8h+String1+8]
0x180001238  mov     [rsp+2B8h+var_1C8], r13
0x180001240  mov     rdi, r13
0x180001243  mov     [rsp+2B8h+var_180], r13
0x18000124b  xor     dl, dl
0x18000124d  mov     [rsp+2B8h+var_258], dl
0x180001251  mov     [rsp+2B8h+var_240], dl
0x180001255  movzx   eax, word ptr [rdi]
0x180001258  test    ax, ax
0x18000125b  jz      loc_1800012EE
0x180001261  mov     esi, r8d
0x180001264  mov     [rsp+2B8h+var_1D0], r8d
0x18000126c  mov     rcx, rdi; String1
0x18000126f  mov     [rsp+2B8h+var_1F0], rcx
0x180001277  nop     word ptr [rax+rax+00000000h]
0x180001280  add     rdi, 2
0x180001284  mov     [rsp+2B8h+var_180], rdi
0x18000128c  test    ax, ax
0x18000128f  jz      short loc_18000129F
0x180001291  inc     esi
0x180001293  mov     [rsp+2B8h+var_1D0], esi
0x18000129a  movzx   eax, word ptr [rdi]
0x18000129d  jmp     short loc_180001280
0x18000129f  test    dl, dl
0x1800012a1  jnz     loc_1800016DB
0x1800012a7  mov     eax, dword ptr [rsp+2B8h+MaxCount]
0x1800012ae  test    byte ptr [rbx+40h], 4
0x1800012b2  jz      loc_180001C68
0x1800012b8  cmp     eax, esi
0x1800012ba  jnz     loc_180001C5E
0x1800012c0  mov     rdx, [rsp+2B8h+String2]; String2
0x1800012c8  call    cs:__imp__wcsicmp
0x1800012cf  nop     dword ptr [rax+rax+00h]
0x1800012d4  test    eax, eax
0x1800012d6  jnz     loc_180001C4A
0x1800012dc  mov     dl, 1
0x1800012de  mov     [rsp+2B8h+var_258], dl
0x1800012e2  mov     [rsp+2B8h+var_240], dl
0x1800012e6  xor     r8d, r8d
0x1800012e9  jmp     loc_180001255
0x1800012ee  mov     [r13+0], r8w
0x1800012f3  add     r13, 2
0x1800012f7  mov     [rsp+2B8h+var_1C8], r13
0x1800012ff  mov     rcx, [rsp+2B8h+String1+8]
0x180001307  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000130e  xchg    ax, ax
0x180001310  inc     rax
0x180001313  cmp     word ptr [rcx+rax*2], 0
0x180001318  jnz     short loc_180001310
0x18000131a  add     rax, rax
0x18000131d  mov     edx, 0FFFFh
0x180001322  cmp     rax, rdx
0x180001325  ja      loc_180001709
0x18000132b  mov     word ptr [rsp+2B8h+String1], ax
0x180001333  test    ax, ax
0x180001336  jz      loc_1800013DD
0x18000133c  sub     r13, rcx
0x18000133f  cmp     r13, rdx
0x180001342  ja      loc_180001CBD
0x180001348  mov     word ptr [rsp+2B8h+String1+2], r13w
0x180001351  jmp     loc_1800013DD
0x180001356  test    r12b, r12b
0x180001359  jnz     loc_18000172B
0x18000135f  lea     eax, [rcx+1]
0x180001362  mov     ecx, eax
0x180001364  add     rcx, rcx
0x180001367  sub     r13, rcx
0x18000136a  mov     rdx, r13; SourceString
0x18000136d  lea     rcx, [rsp+2B8h+String1]; DestinationString
0x180001375  call    cs:__imp_RtlInitUnicodeString
0x18000137c  nop     dword ptr [rax+rax+00h]
0x180001381  xor     r8d, r8d
0x180001384  mov     rcx, [rsp+2B8h+Handle]; Handle
0x180001389  test    rcx, rcx
0x18000138c  jz      short loc_1800013BA
0x18000138e  call    cs:__imp_NtMakeTemporaryObject
0x180001395  nop     dword ptr [rax+rax+00h]
0x18000139a  mov     r14d, eax
0x18000139d  mov     [rsp+2B8h+var_254], eax
0x1800013a1  mov     rcx, [rsp+2B8h+Handle]; Handle
0x1800013a6  call    cs:__imp_NtClose
0x1800013ad  nop     dword ptr [rax+rax+00h]
0x1800013b2  xor     r8d, r8d
0x1800013b5  mov     [rsp+2B8h+Handle], r8
0x1800013ba  test    r14d, r14d
0x1800013bd  js      loc_180001D52
0x1800013c3  test    r12b, r12b
0x1800013c6  jnz     loc_180001230
0x1800013cc  test    sil, sil
0x1800013cf  jnz     loc_180001CCA
0x1800013d5  movzx   eax, word ptr [rsp+2B8h+String1]
0x1800013dd  test    ax, ax
0x1800013e0  jz      loc_180001D52
0x1800013e6  lea     rax, [rsp+2B8h+var_1E8]
0x1800013ee  mov     [rsp+2B8h+Sid], rax; Sid
0x1800013f3  mov     [rsp+2B8h+SubAuthority7], r8d; SubAuthority7
0x1800013f8  mov     [rsp+2B8h+SubAuthority6], r8d; SubAuthority6
0x1800013fd  mov     [rsp+2B8h+SubAuthority5], r8d; SubAuthority5
0x180001402  mov     [rsp+2B8h+SubAuthority4], r8d; SubAuthority4
0x180001407  mov     [rsp+2B8h+SubAuthority3], r8d; SubAuthority3
0x18000140c  mov     [rsp+2B8h+SubAuthority2], r8d; SubAuthority2
0x180001411  xor     r9d, r9d; SubAuthority1
0x180001414  xor     r8d, r8d; SubAuthority0
0x180001417  mov     dl, 1; SubAuthorityCount
0x180001419  lea     rcx, [rsp+2B8h+IdentifierAuthority]; IdentifierAuthority
0x180001421  call    cs:__imp_RtlAllocateAndInitializeSid
0x180001428  nop     dword ptr [rax+rax+00h]
0x18000142d  mov     r14d, eax
0x180001430  mov     [rsp+2B8h+var_254], eax
0x180001434  test    eax, eax
0x180001436  js      loc_180001D52
0x18000143c  lea     rax, [rsp+2B8h+var_1D8]
0x180001444  mov     [rsp+2B8h+Sid], rax; Sid
0x180001449  mov     [rsp+2B8h+SubAuthority7], 0; SubAuthority7
0x180001451  mov     [rsp+2B8h+SubAuthority6], 0; SubAuthority6
0x180001459  mov     [rsp+2B8h+SubAuthority5], 0; SubAuthority5
0x180001461  mov     [rsp+2B8h+SubAuthority4], 0; SubAuthority4
0x180001469  mov     [rsp+2B8h+SubAuthority3], 0; SubAuthority3
0x180001471  mov     [rsp+2B8h+SubAuthority2], 0; SubAuthority2
0x180001479  xor     r9d, r9d; SubAuthority1
0x18000147c  mov     r8d, 0Ch; SubAuthority0
0x180001482  mov     dl, 1; SubAuthorityCount
0x180001484  lea     rcx, [rsp+2B8h+var_140]; IdentifierAuthority
0x18000148c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180001493  nop     dword ptr [rax+rax+00h]
0x180001498  mov     r14d, eax
0x18000149b  mov     [rsp+2B8h+var_254], eax
0x18000149f  test    eax, eax
0x1800014a1  js      loc_180001D0A
0x1800014a7  mov     ebx, 1
0x1800014ac  mov     edx, ebx; Revision
0x1800014ae  lea     rcx, [rsp+2B8h+SecurityDescriptor]; SecurityDescriptor
0x1800014b6  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800014bd  nop     dword ptr [rax+rax+00h]
0x1800014c2  mov     [rsp+2B8h+var_254], eax
0x1800014c6  mov     edx, 100h; AclSize
0x1800014cb  mov     r8d, 2; AclRevision
0x1800014d1  lea     rcx, [rsp+2B8h+Acl]; Acl
0x1800014d9  call    cs:__imp_RtlCreateAcl
0x1800014e0  nop     dword ptr [rax+rax+00h]
0x1800014e5  mov     [rsp+2B8h+var_254], eax
0x1800014e9  mov     eax, cs:ServiceSessionId
0x1800014ef  cmp     cs:SessionId, eax
0x1800014f5  jnz     loc_180001719
0x1800014fb  mov     ebx, 10001h
0x180001500  mov     r9, [rsp+2B8h+var_1E8]; Sid
0x180001508  mov     r8d, ebx; AccessMask
0x18000150b  mov     edx, 2; Revision
0x180001510  lea     rcx, [rsp+2B8h+Acl]; Acl
0x180001518  call    cs:__imp_RtlAddAccessAllowedAce
0x18000151f  nop     dword ptr [rax+rax+00h]
0x180001524  mov     [rsp+2B8h+var_254], eax
0x180001528  mov     r9, [rsp+2B8h+var_1D8]; Sid
0x180001530  mov     r8d, ebx; AccessMask
0x180001533  mov     edx, 2; Revision
0x180001538  lea     rcx, [rsp+2B8h+Acl]; Acl
0x180001540  call    cs:__imp_RtlAddAccessAllowedAce
0x180001547  nop     dword ptr [rax+rax+00h]
0x18000154c  mov     [rsp+2B8h+var_254], eax
0x180001550  mov     rcx, [rsp+2B8h+var_1E8]; Sid
0x180001558  call    cs:__imp_RtlFreeSid
0x18000155f  nop     dword ptr [rax+rax+00h]
0x180001564  mov     rcx, [rsp+2B8h+var_1D8]; Sid
0x18000156c  call    cs:__imp_RtlFreeSid
0x180001573  nop     dword ptr [rax+rax+00h]
0x180001578  mov     r9b, 1; DaclDefaulted
0x18000157b  lea     r8, [rsp+2B8h+Acl]; Dacl
0x180001583  movzx   edx, r9b; DaclPresent
0x180001587  lea     rcx, [rsp+2B8h+SecurityDescriptor]; SecurityDescriptor
0x18000158f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180001596  nop     dword ptr [rax+rax+00h]
0x18000159b  mov     [rsp+2B8h+var_254], eax
0x18000159f  lea     rax, [rsp+2B8h+SecurityDescriptor]
0x1800015a7  mov     [rsp+2B8h+ObjectAttributes.SecurityDescriptor], rax
0x1800015af  mov     rax, cs:BaseSrvpStaticServerData
0x1800015b6  movzx   ebx, [rsp+2B8h+var_257]
0x1800015bb  cmp     byte ptr [rax+9CCh], 1
0x1800015c2  jnz     loc_1800016A4
0x1800015c8  test    bl, bl
0x1800015ca  jnz     loc_1800016A4
0x1800015d0  xor     ecx, ecx
0x1800015d2  call    cs:__imp_CsrImpersonateClient
0x1800015d9  nop     dword ptr [rax+rax+00h]
0x1800015de  movzx   edi, al
0x1800015e1  test    al, al
0x1800015e3  jz      loc_1800016F9
0x1800015e9  mov     rax, cs:BaseSrvpStaticServerData
0x1800015f0  cmp     byte ptr [rax+9CCh], 0
0x1800015f7  jz      loc_180001D2D
0x1800015fd  lea     r9, [rsp+2B8h+String1]; Name
0x180001605  lea     r8, [rsp+2B8h+ObjectAttributes]; ObjectAttributes
  ... truncated ...
```
