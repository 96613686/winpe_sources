# CreateBaseAcls

- ea: `0x180004210`
- end: `0x180004d6e`
- name: `CreateBaseAcls`
- size: `2910`
- prototype: `NTSTATUS __fastcall(PACL *, PACL *, PACL *, PACL *, PACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002f50`

## callees

- `0x180004210`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004655`
- `ntdll!RtlAllocateHeap` at `0x180004744`
- `ntdll!RtlAllocateHeap` at `0x18000488c`
- `ntdll!RtlAllocateHeap` at `0x180004a3f`
- `ntdll!RtlAllocateHeap` at `0x180004b44`
- `ntdll!RtlAllocateHeap` at `0x180004655`
- `ntdll!RtlAllocateHeap` at `0x180004744`
- `ntdll!RtlAllocateHeap` at `0x18000488c`
- `ntdll!RtlAllocateHeap` at `0x180004a3f`
- `ntdll!RtlAllocateHeap` at `0x180004b44`
- `ntdll!NtQuerySystemInformation` at `0x1800043b3`
- `ntdll!NtQuerySystemInformation` at `0x1800043b3`
- `ntdll!NtOpenKey` at `0x18000430f`
- `ntdll!NtOpenKey` at `0x18000430f`
- `ntdll!NtQueryValueKey` at `0x180004359`
- `ntdll!NtQueryValueKey` at `0x180004359`
- `ntdll!NtClose` at `0x180004381`
- `ntdll!NtClose` at `0x180004381`
- `ntdll!RtlFreeHeap` at `0x180004bd0`
- `ntdll!RtlFreeHeap` at `0x180004bf4`
- `ntdll!RtlFreeHeap` at `0x180004c18`
- `ntdll!RtlFreeHeap` at `0x180004c3d`
- `ntdll!RtlFreeHeap` at `0x180004c67`
- `ntdll!RtlFreeHeap` at `0x180004c89`
- `ntdll!RtlFreeHeap` at `0x180004ca7`
- `ntdll!RtlFreeHeap` at `0x180004cc6`
- `ntdll!RtlFreeHeap` at `0x180004ce5`
- `ntdll!RtlFreeHeap` at `0x180004d03`
- `ntdll!RtlFreeHeap` at `0x180004d21`
- `ntdll!RtlFreeHeap` at `0x180004d3f`
- `ntdll!RtlFreeHeap` at `0x180004bd0`
- `ntdll!RtlFreeHeap` at `0x180004bf4`
- `ntdll!RtlFreeHeap` at `0x180004c18`
- `ntdll!RtlFreeHeap` at `0x180004c3d`
- `ntdll!RtlFreeHeap` at `0x180004c67`
- `ntdll!RtlFreeHeap` at `0x180004c89`
- `ntdll!RtlFreeHeap` at `0x180004ca7`
- `ntdll!RtlFreeHeap` at `0x180004cc6`
- `ntdll!RtlFreeHeap` at `0x180004ce5`
- `ntdll!RtlFreeHeap` at `0x180004d03`
- `ntdll!RtlFreeHeap` at `0x180004d21`
- `ntdll!RtlFreeHeap` at `0x180004d3f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800043fc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000444b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004495`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800044e0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000452c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000457d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800045cb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800043fc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000444b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004495`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800044e0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000452c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000457d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800045cb`
- `ntdll!RtlCreateAcl` at `0x180004678`
- `ntdll!RtlCreateAcl` at `0x180004767`
- `ntdll!RtlCreateAcl` at `0x1800048b6`
- `ntdll!RtlCreateAcl` at `0x180004a6d`
- `ntdll!RtlCreateAcl` at `0x180004b6a`
- `ntdll!RtlCreateAcl` at `0x180004678`
- `ntdll!RtlCreateAcl` at `0x180004767`
- `ntdll!RtlCreateAcl` at `0x1800048b6`
- `ntdll!RtlCreateAcl` at `0x180004a6d`
- `ntdll!RtlCreateAcl` at `0x180004b6a`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000469e`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046c4`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046ec`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004715`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000478d`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800047b3`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800047db`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004804`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800048db`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004905`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000492c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004953`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000497a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004a93`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004aba`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004ae2`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004b0b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000469e`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046c4`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046ec`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004715`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000478d`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800047b3`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800047db`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004804`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800048db`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004905`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000492c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004953`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000497a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004a93`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004aba`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004ae2`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004b0b`
- `ntdll!RtlLengthSid` at `0x1800045fc`
- `ntdll!RtlLengthSid` at `0x18000460f`
- `ntdll!RtlLengthSid` at `0x180004621`
- `ntdll!RtlLengthSid` at `0x180004634`
- `ntdll!RtlLengthSid` at `0x18000481f`
- `ntdll!RtlLengthSid` at `0x180004833`
- `ntdll!RtlLengthSid` at `0x180004845`
- `ntdll!RtlLengthSid` at `0x180004858`
- `ntdll!RtlLengthSid` at `0x18000486b`
- `ntdll!RtlLengthSid` at `0x1800049e6`
- `ntdll!RtlLengthSid` at `0x1800049f9`
- `ntdll!RtlLengthSid` at `0x180004a0b`
- `ntdll!RtlLengthSid` at `0x180004a1e`
- `ntdll!RtlLengthSid` at `0x180004b25`
- `ntdll!RtlLengthSid` at `0x1800045fc`
- `ntdll!RtlLengthSid` at `0x18000460f`
- `ntdll!RtlLengthSid` at `0x180004621`
- `ntdll!RtlLengthSid` at `0x180004634`
- `ntdll!RtlLengthSid` at `0x18000481f`
- `ntdll!RtlLengthSid` at `0x180004833`
- `ntdll!RtlLengthSid` at `0x180004845`
- `ntdll!RtlLengthSid` at `0x180004858`
- `ntdll!RtlLengthSid` at `0x18000486b`
- `ntdll!RtlLengthSid` at `0x1800049e6`
- `ntdll!RtlLengthSid` at `0x1800049f9`
- `ntdll!RtlLengthSid` at `0x180004a0b`
- `ntdll!RtlLengthSid` at `0x180004a1e`
- `ntdll!RtlLengthSid` at `0x180004b25`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800049ad`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800049ad`
- `ntdll!RtlAddMandatoryAce` at `0x180004b97`
- `ntdll!RtlAddMandatoryAce` at `0x180004b97`
- `ntdll!RtlInitUnicodeString` at `0x1800042bf`
- `ntdll!RtlInitUnicodeString` at `0x18000432a`
- `ntdll!RtlInitUnicodeString` at `0x1800042bf`
- `ntdll!RtlInitUnicodeString` at `0x18000432a`

## string_xrefs

- `0x180004258`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`

## pseudocode

```c
NTSTATUS __fastcall CreateBaseAcls(PACL *a1, PACL *a2, PACL *a3, PACL *a4, PACL *a5)
{
  PVOID *v5; // rdi
  NTSTATUS Acl; // ebx
  ACCESS_MASK v10; // r13d
  ULONG v11; // edi
  ULONG v12; // edi
  ULONG v13; // edi
  ULONG v14; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v16; // rax
  ULONG v17; // ebx
  ULONG v18; // ebx
  ULONG v19; // ebx
  ULONG v20; // ebx
  ULONG v21; // ebx
  struct _ACL *v22; // rax
  NTSTATUS result; // eax
  ULONG v24; // ebx
  ULONG v25; // ebx
  ULONG v26; // ebx
  ULONG v27; // ebx
  struct _ACL *v28; // rax
  ULONG v29; // ebx
  struct _ACL *v30; // rax
  PULONG ResultLength; // [rsp+28h] [rbp-D8h]
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PSID v34; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  int SystemInformation; // [rsp+80h] [rbp-80h] BYREF
  PSID P; // [rsp+88h] [rbp-78h] BYREF
  ACCESS_MASK AccessMask; // [rsp+90h] [rbp-70h]
  PSID v39; // [rsp+98h] [rbp-68h] BYREF
  PSID v40; // [rsp+A0h] [rbp-60h] BYREF
  PSID v41; // [rsp+A8h] [rbp-58h] BYREF
  ULONG v42; // [rsp+B0h] [rbp-50h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+100h] [rbp+0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v47; // [rsp+108h] [rbp+8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v48; // [rsp+110h] [rbp+10h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v49; // [rsp+118h] [rbp+18h] BYREF
  char KeyValueInformation[4]; // [rsp+120h] [rbp+20h] BYREF
  int v51; // [rsp+124h] [rbp+24h]
  __int64 v52; // [rsp+12Ch] [rbp+2Ch]

  v5 = (PVOID *)a2;
  pSid = 0;
  P = 0;
  Sid = 0;
  v34 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  *(_DWORD *)v49.Value = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v48.Value = 0;
  *(_DWORD *)v47.Value = 0;
  KeyHandle = 0;
  v42 = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  SystemInformation = 0;
  *(_WORD *)&v49.Value[4] = 4096;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_WORD *)&v48.Value[4] = 256;
  *(_WORD *)&v47.Value[4] = 3840;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager");
  *a1 = 0;
  *v5 = 0;
  *a4 = 0;
  *a3 = 0;
  if ( a5 )
    *a5 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ProtectionMode");
    if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, KeyValueInformation, 0x40u, &v42) >= 0
      && v51 == 4
      && (_DWORD)v52 )
    {
      ProtectionMode = v52;
    }
    NtClose(KeyHandle);
  }
  if ( NtCurrentPeb()->SessionId != ServiceSessionId
    && NtQuerySystemInformation(SystemObjectSecurityMode, &SystemInformation, 4u, 0) < 0 )
  {
    SystemInformation = 0;
  }
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 3u, 0x5Au, 0, SessionId, 0, 0, 0, 0, 0, &P);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&v48, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v34);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&v49, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &v39);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&v47, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v40);
  if ( Acl < 0 )
    goto LABEL_60;
  Acl = RtlAllocateAndInitializeSid(&v47, 2u, 2u, 2u, 0, 0, 0, 0, 0, 0, &v41);
  if ( Acl < 0 )
    goto LABEL_60;
  v10 = 3;
  if ( !SystemInformation )
    v10 = 131087;
  AccessMask = 131087;
  v11 = RtlLengthSid(v34);
  v12 = RtlLengthSid(Sid) + v11;
  v13 = RtlLengthSid(P) + v12;
  v14 = RtlLengthSid(pSid) + 56 + v13;
  Heap = (struct _ACL *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, v14);
  *a1 = Heap;
  if ( !Heap )
    goto LABEL_58;
  Acl = RtlCreateAcl(Heap, v14, 2u);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a1, 2u, v10, Sid);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a1, 2u, 2u, v34);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a1, 2u, 0xF000Fu, P);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a1, 2u, 0xF000Fu, pSid);
  if ( Acl < 0 )
    goto LABEL_59;
  if ( !a5 )
    goto LABEL_34;
  v16 = (struct _ACL *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, v14);
  *a5 = v16;
  if ( !v16 )
  {
LABEL_58:
    Acl = -1073741801;
    goto LABEL_59;
  }
  Acl = RtlCreateAcl(v16, v14, 2u);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a5, 2u, 2u, Sid);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a5, 2u, 2u, v34);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a5, 2u, 0xF000Fu, P);
  if ( Acl < 0 )
    goto LABEL_59;
  Acl = RtlAddAccessAllowedAce(*a5, 2u, 0xF000Fu, pSid);
  if ( Acl < 0 )
    goto LABEL_59;
LABEL_34:
  v17 = 2 * RtlLengthSid(pSid);
  v18 = RtlLengthSid(v41) + v17;
  v19 = RtlLengthSid(v40) + v18;
  v20 = RtlLengthSid(v34) + v19;
  v21 = RtlLengthSid(Sid) + 80 + v20;
  v22 = (struct _ACL *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, v21);
  *a3 = v22;
  if ( !v22 )
    return -1073741801;
  result = RtlCreateAcl(v22, v21, 2u);
  if ( result >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(*a3, 2u, v10, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(*a3, 2u, 0xF000Fu, pSid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(*a3, 2u, 2u, v34);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(*a3, 2u, 3u, v40);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(*a3, 2u, 3u, v41);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(*a3, 2u, 0xBu, 0x10000000u, pSid);
              if ( Acl >= 0 )
              {
                if ( SessionId != ServiceSessionId && (ProtectionMode & 3) != 0 )
                  AccessMask = 131075;
                v24 = RtlLengthSid(v34);
                v25 = RtlLengthSid(Sid) + v24;
                v26 = RtlLengthSid(P) + v25;
                v27 = RtlLengthSid(pSid) + 56 + v26;
                v28 = (struct _ACL *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, v27);
                v5 = (PVOID *)a2;
                *a2 = v28;
                if ( v28 )
                {
                  Acl = RtlCreateAcl(v28, v27, 2u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlAddAccessAllowedAce(*a2, 2u, v10, Sid);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlAddAccessAllowedAce(*a2, 2u, AccessMask, v34);
                      if ( Acl >= 0 )
                      {
                        Acl = RtlAddAccessAllowedAce(*a2, 2u, 0xF000Fu, P);
                        if ( Acl >= 0 )
                        {
                          Acl = RtlAddAccessAllowedAce(*a2, 2u, 0xF000Fu, pSid);
                          if ( Acl >= 0 )
                          {
                            v29 = RtlLengthSid(v39) + 20;
                            v30 = (struct _ACL *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, v29);
                            *a4 = v30;
                            if ( v30 )
                            {
                              Acl = RtlCreateAcl(v30, v29, 2u);
                              if ( Acl >= 0 )
                              {
                                LODWORD(ResultLength) = 1;
                                Acl = RtlAddMandatoryAce(*a4, 2u, 0, (ULONG)v39, 0x11u, ResultLength);
                                if ( Acl >= 0 )
                                {
LABEL_71:
                                  if ( pSid )
                                    RtlFreeHeap(BaseSrvHeap, 0, pSid);
                                  if ( P )
                                    RtlFreeHeap(BaseSrvHeap, 0, P);
                                  if ( v34 )
                                    RtlFreeHeap(BaseSrvHeap, 0, v34);
                                  if ( Sid )
                                    RtlFreeHeap(BaseSrvHeap, 0, Sid);
                                  if ( v39 )
                                    RtlFreeHeap(BaseSrvHeap, 0, v39);
                                  if ( v40 )
                                    RtlFreeHeap(BaseSrvHeap, 0, v40);
                                  if ( v41 )
                                    RtlFreeHeap(BaseSrvHeap, 0, v41);
                                  return Acl;
                                }
                              }
                            }
                            else
                            {
                              Acl = -1073741801;
                            }
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  Acl = -1073741801;
                }
LABEL_60:
                if ( *a1 )
                {
                  RtlFreeHeap(BaseSrvHeap, BaseSrvTag, *a1);
                  *a1 = 0;
                }
                if ( *v5 )
                {
                  RtlFreeHeap(BaseSrvHeap, BaseSrvTag, *v5);
                  *v5 = 0;
                }
                if ( *a4 )
                {
                  RtlFreeHeap(BaseSrvHeap, BaseSrvTag, *a4);
                  *a4 = 0;
                }
                if ( *a3 )
                {
                  RtlFreeHeap(BaseSrvHeap, BaseSrvTag, *a3);
                  *a3 = 0;
                }
                if ( a5 && *a5 )
                {
                  RtlFreeHeap(BaseSrvHeap, BaseSrvTag, *a5);
                  *a5 = 0;
                }
                goto LABEL_71;
              }
            }
          }
        }
      }
    }
LABEL_59:
    v5 = (PVOID *)a2;
    goto LABEL_60;
  }
  return result;
}

```

## disassembly

```asm
0x180004210  push    rbp
0x180004212  push    rbx
0x180004213  push    rsi
0x180004214  push    rdi
0x180004215  push    r12
0x180004217  push    r13
0x180004219  push    r14
0x18000421b  push    r15
0x18000421d  lea     rbp, [rsp-78h]
0x180004222  sub     rsp, 178h
0x180004229  mov     rax, cs:__security_cookie
0x180004230  xor     rax, rsp
0x180004233  mov     [rbp+0B0h+var_50], rax
0x180004237  mov     r14, [rbp+0B0h+arg_20]
0x18000423e  xor     r13d, r13d
0x180004241  mov     rdi, rdx
0x180004244  mov     [rsp+1B0h+var_150], rdx
0x180004249  mov     rsi, rcx
0x18000424c  mov     [rsp+1B0h+pSid], r13
0x180004251  xorps   xmm0, xmm0
0x180004254  mov     [rbp+0B0h+P], r13
0x180004258  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000425f  mov     [rsp+1B0h+var_138], r13
0x180004264  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180004268  mov     [rsp+1B0h+var_140], r13
0x18000426d  mov     [rbp+0B0h+var_118], r13
0x180004271  mov     r15, r9
0x180004274  mov     [rbp+0B0h+var_110], r13
0x180004278  mov     r12, r8
0x18000427b  mov     [rbp+0B0h+var_108], r13
0x18000427f  mov     dword ptr [rbp+0B0h+var_98.Value], r13d
0x180004283  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r13d
0x180004287  mov     dword ptr [rbp+0B0h+var_A0.Value], r13d
0x18000428b  mov     dword ptr [rbp+0B0h+var_A8.Value], r13d
0x18000428f  mov     [rbp+0B0h+KeyHandle], r13
0x180004293  mov     [rbp+0B0h+var_100], r13d
0x180004297  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18000429b  mov     dword ptr [rbp+0B0h+ObjectAttributes+4], r13d
0x18000429f  mov     dword ptr [rbp+0B0h+ObjectAttributes+1Ch], r13d
0x1800042a3  mov     [rbp+0B0h+SystemInformation], r13d
0x1800042a7  mov     word ptr [rbp+0B0h+var_98.Value+4], 1000h
0x1800042ad  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x1800042b3  mov     word ptr [rbp+0B0h+var_A0.Value+4], 100h
0x1800042b9  mov     word ptr [rbp+0B0h+var_A8.Value+4], 0F00h
0x1800042bf  call    cs:__imp_RtlInitUnicodeString
0x1800042c6  nop     dword ptr [rax+rax+00h]
0x1800042cb  mov     [rsi], r13
0x1800042ce  mov     [rdi], r13
0x1800042d1  mov     [r15], r13
0x1800042d4  mov     [r12], r13
0x1800042d8  test    r14, r14
0x1800042db  jz      short loc_1800042E0
0x1800042dd  mov     [r14], r13
0x1800042e0  lea     rax, [rbp+0B0h+DestinationString]
0x1800042e4  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x1800042eb  xorps   xmm0, xmm0
0x1800042ee  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x1800042f2  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1800042f6  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r13
0x1800042fa  mov     edx, 20019h; DesiredAccess
0x1800042ff  mov     [rbp+0B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180004306  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x18000430a  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000430f  call    cs:__imp_NtOpenKey
0x180004316  nop     dword ptr [rax+rax+00h]
0x18000431b  test    eax, eax
0x18000431d  js      short loc_18000438D
0x18000431f  lea     rdx, aProtectionmode; "ProtectionMode"
0x180004326  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x18000432a  call    cs:__imp_RtlInitUnicodeString
0x180004331  nop     dword ptr [rax+rax+00h]
0x180004336  mov     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x18000433a  lea     rax, [rbp+0B0h+var_100]
0x18000433e  mov     [rsp+1B0h+ResultLength], rax; ResultLength
0x180004343  lea     r9, [rbp+0B0h+KeyValueInformation]; KeyValueInformation
0x180004347  mov     r8d, 2; KeyValueInformationClass
0x18000434d  mov     [rsp+1B0h+Length], 40h ; '@'; Length
0x180004355  lea     rdx, [rbp+0B0h+DestinationString]; ValueName
0x180004359  call    cs:__imp_NtQueryValueKey
0x180004360  nop     dword ptr [rax+rax+00h]
0x180004365  test    eax, eax
0x180004367  js      short loc_18000437D
0x180004369  cmp     [rbp+0B0h+var_8C], 4
0x18000436d  jnz     short loc_18000437D
0x18000436f  mov     rax, [rbp+0B0h+var_84]
0x180004373  test    eax, eax
0x180004375  jz      short loc_18000437D
0x180004377  mov     cs:ProtectionMode, eax
0x18000437d  mov     rcx, [rbp+0B0h+KeyHandle]; Handle
0x180004381  call    cs:__imp_NtClose
0x180004388  nop     dword ptr [rax+rax+00h]
0x18000438d  mov     rcx, gs:60h
0x180004396  mov     eax, cs:ServiceSessionId
0x18000439c  cmp     [rcx+2C0h], eax
0x1800043a2  jz      short loc_1800043C7
0x1800043a4  xor     r9d, r9d; ReturnLength
0x1800043a7  lea     rdx, [rbp+0B0h+SystemInformation]; SystemInformation
0x1800043ab  lea     r8d, [r9+4]; SystemInformationLength
0x1800043af  lea     ecx, [r9+46h]; SystemInformationClass
0x1800043b3  call    cs:__imp_NtQuerySystemInformation
0x1800043ba  nop     dword ptr [rax+rax+00h]
0x1800043bf  test    eax, eax
0x1800043c1  jns     short loc_1800043C7
0x1800043c3  mov     [rbp+0B0h+SystemInformation], r13d
0x1800043c7  lea     rax, [rsp+1B0h+pSid]
0x1800043cc  xor     r9d, r9d; SubAuthority1
0x1800043cf  mov     [rsp+1B0h+Sid], rax; Sid
0x1800043d4  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x1800043d8  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x1800043dd  mov     dl, 1; SubAuthorityCount
0x1800043df  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x1800043e4  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x1800043e9  lea     r8d, [r9+12h]; SubAuthority0
0x1800043ed  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x1800043f2  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x1800043f7  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x1800043fc  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004403  nop     dword ptr [rax+rax+00h]
0x180004408  mov     ebx, eax
0x18000440a  test    eax, eax
0x18000440c  js      loc_180004BBB
0x180004412  lea     rax, [rbp+0B0h+P]
0x180004416  xor     r9d, r9d; SubAuthority1
0x180004419  mov     [rsp+1B0h+Sid], rax; Sid
0x18000441e  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x180004422  mov     eax, cs:SessionId
0x180004428  mov     dl, 3; SubAuthorityCount
0x18000442a  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x18000442f  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x180004434  lea     r8d, [r9+5Ah]; SubAuthority0
0x180004438  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x18000443d  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x180004442  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x180004447  mov     [rsp+1B0h+Length], eax; SubAuthority2
0x18000444b  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004452  nop     dword ptr [rax+rax+00h]
0x180004457  mov     ebx, eax
0x180004459  test    eax, eax
0x18000445b  js      loc_180004BBB
0x180004461  lea     rax, [rsp+1B0h+var_138]
0x180004466  xor     r9d, r9d; SubAuthority1
0x180004469  mov     [rsp+1B0h+Sid], rax; Sid
0x18000446e  lea     rcx, [rbp+0B0h+var_A0]; IdentifierAuthority
0x180004472  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x180004477  xor     r8d, r8d; SubAuthority0
0x18000447a  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x18000447f  mov     dl, 1; SubAuthorityCount
0x180004481  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x180004486  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x18000448b  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x180004490  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x180004495  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000449c  nop     dword ptr [rax+rax+00h]
0x1800044a1  mov     ebx, eax
0x1800044a3  test    eax, eax
0x1800044a5  js      loc_180004BBB
0x1800044ab  lea     rax, [rsp+1B0h+var_140]
0x1800044b0  xor     r9d, r9d; SubAuthority1
0x1800044b3  mov     [rsp+1B0h+Sid], rax; Sid
0x1800044b8  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x1800044bc  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x1800044c1  mov     dl, 1; SubAuthorityCount
0x1800044c3  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x1800044c8  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x1800044cd  lea     r8d, [r9+0Ch]; SubAuthority0
0x1800044d1  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x1800044d6  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x1800044db  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x1800044e0  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800044e7  nop     dword ptr [rax+rax+00h]
0x1800044ec  mov     ebx, eax
0x1800044ee  test    eax, eax
0x1800044f0  js      loc_180004BBB
0x1800044f6  lea     rax, [rbp+0B0h+var_118]
0x1800044fa  xor     r9d, r9d; SubAuthority1
0x1800044fd  mov     [rsp+1B0h+Sid], rax; Sid
0x180004502  lea     rcx, [rbp+0B0h+var_98]; IdentifierAuthority
0x180004506  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x18000450b  mov     r8d, 1000h; SubAuthority0
0x180004511  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x180004516  mov     dl, 1; SubAuthorityCount
0x180004518  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x18000451d  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x180004522  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x180004527  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x18000452c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004533  nop     dword ptr [rax+rax+00h]
0x180004538  mov     ebx, eax
0x18000453a  test    eax, eax
0x18000453c  js      loc_180004BBB
0x180004542  lea     rax, [rbp+0B0h+var_110]
0x180004546  mov     r8d, 2; SubAuthority0
0x18000454c  mov     [rsp+1B0h+Sid], rax; Sid
0x180004551  lea     rcx, [rbp+0B0h+var_A8]; IdentifierAuthority
0x180004555  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x18000455a  mov     r9d, 1; SubAuthority1
0x180004560  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x180004565  movzx   edx, r8b; SubAuthorityCount
0x180004569  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x18000456e  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x180004573  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x180004578  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x18000457d  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004584  nop     dword ptr [rax+rax+00h]
0x180004589  mov     ebx, eax
0x18000458b  test    eax, eax
0x18000458d  js      loc_180004BBB
0x180004593  mov     r9d, 2; SubAuthority1
0x180004599  lea     rax, [rbp+0B0h+var_108]
0x18000459d  mov     [rsp+1B0h+Sid], rax; Sid
0x1800045a2  lea     rcx, [rbp+0B0h+var_A8]; IdentifierAuthority
0x1800045a6  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x1800045ab  mov     r8d, r9d; SubAuthority0
0x1800045ae  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x1800045b3  movzx   edx, r9b; SubAuthorityCount
0x1800045b7  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x1800045bc  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x1800045c1  mov     dword ptr [rsp+1B0h+ResultLength], r13d; SubAuthority3
0x1800045c6  mov     [rsp+1B0h+Length], r13d; SubAuthority2
0x1800045cb  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800045d2  nop     dword ptr [rax+rax+00h]
0x1800045d7  mov     ebx, eax
0x1800045d9  test    eax, eax
0x1800045db  js      loc_180004BBB
0x1800045e1  cmp     [rbp+0B0h+SystemInformation], 0
0x1800045e5  mov     eax, 2000Fh
0x1800045ea  mov     rcx, [rsp+1B0h+var_140]; Sid
0x1800045ef  mov     r13d, 3
0x1800045f5  cmovz   r13d, eax
0x1800045f9  mov     [rbp+0B0h+AccessMask], eax
0x1800045fc  call    cs:__imp_RtlLengthSid
0x180004603  nop     dword ptr [rax+rax+00h]
0x180004608  mov     rcx, [rsp+1B0h+var_138]; Sid
0x18000460d  mov     edi, eax
0x18000460f  call    cs:__imp_RtlLengthSid
0x180004616  nop     dword ptr [rax+rax+00h]
0x18000461b  mov     rcx, [rbp+0B0h+P]; Sid
0x18000461f  add     edi, eax
0x180004621  call    cs:__imp_RtlLengthSid
0x180004628  nop     dword ptr [rax+rax+00h]
0x18000462d  mov     rcx, [rsp+1B0h+pSid]; Sid
0x180004632  add     edi, eax
0x180004634  call    cs:__imp_RtlLengthSid
0x18000463b  nop     dword ptr [rax+rax+00h]
0x180004640  mov     edx, cs:BaseSrvTag; Flags
0x180004646  add     eax, 38h ; '8'
0x180004649  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180004650  add     edi, eax
0x180004652  mov     r8d, edi; Size
0x180004655  call    cs:__imp_RtlAllocateHeap
0x18000465c  nop     dword ptr [rax+rax+00h]
0x180004661  mov     [rsi], rax
0x180004664  test    rax, rax
0x180004667  jz      loc_180004BAE
0x18000466d  mov     r8d, 2; AclRevision
0x180004673  mov     edx, edi; AclSize
0x180004675  mov     rcx, rax; Acl
0x180004678  call    cs:__imp_RtlCreateAcl
0x18000467f  nop     dword ptr [rax+rax+00h]
0x180004684  mov     ebx, eax
0x180004686  test    eax, eax
0x180004688  js      loc_180004BB3
0x18000468e  mov     r9, [rsp+1B0h+var_138]; Sid
0x180004693  mov     r8d, r13d; AccessMask
0x180004696  mov     rcx, [rsi]; Acl
0x180004699  mov     edx, 2; Revision
0x18000469e  call    cs:__imp_RtlAddAccessAllowedAce
0x1800046a5  nop     dword ptr [rax+rax+00h]
0x1800046aa  mov     ebx, eax
0x1800046ac  test    eax, eax
0x1800046ae  js      loc_180004BB3
0x1800046b4  mov     r9, [rsp+1B0h+var_140]; Sid
0x1800046b9  mov     edx, 2; Revision
0x1800046be  mov     rcx, [rsi]; Acl
0x1800046c1  mov     r8d, edx; AccessMask
0x1800046c4  call    cs:__imp_RtlAddAccessAllowedAce
0x1800046cb  nop     dword ptr [rax+rax+00h]
0x1800046d0  mov     ebx, eax
0x1800046d2  test    eax, eax
0x1800046d4  js      loc_180004BB3
0x1800046da  mov     r9, [rbp+0B0h+P]; Sid
0x1800046de  mov     edx, 2; Revision
0x1800046e3  mov     rcx, [rsi]; Acl
0x1800046e6  mov     r8d, 0F000Fh; AccessMask
0x1800046ec  call    cs:__imp_RtlAddAccessAllowedAce
0x1800046f3  nop     dword ptr [rax+rax+00h]
0x1800046f8  mov     ebx, eax
0x1800046fa  test    eax, eax
0x1800046fc  js      loc_180004BB3
0x180004702  mov     r9, [rsp+1B0h+pSid]; Sid
0x180004707  mov     edx, 2; Revision
0x18000470c  mov     rcx, [rsi]; Acl
0x18000470f  mov     r8d, 0F000Fh; AccessMask
0x180004715  call    cs:__imp_RtlAddAccessAllowedAce
0x18000471c  nop     dword ptr [rax+rax+00h]
0x180004721  mov     ebx, eax
0x180004723  test    eax, eax
0x180004725  js      loc_180004BB3
0x18000472b  test    r14, r14
0x18000472e  jz      loc_18000481A
  ... truncated ...
```
