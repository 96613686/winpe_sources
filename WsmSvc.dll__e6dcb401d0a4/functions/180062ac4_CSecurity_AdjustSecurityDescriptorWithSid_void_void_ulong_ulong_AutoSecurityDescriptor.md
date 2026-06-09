# CSecurity::AdjustSecurityDescriptorWithSid(void *,void *,ulong,ulong,AutoSecurityDescriptor &)

- ea: `0x180062ac4`
- end: `0x180062fb4`
- name: `?AdjustSecurityDescriptorWithSid@CSecurity@@SAHPEAX0KKAEAVAutoSecurityDescriptor@@@Z`
- size: `1264`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor@<rcx>, PSID pSid@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct AutoSecurityDescriptor *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007965c`
- `0x1800c6a94`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800621e0`
- `0x180062ac4`
- `0x180064250`
- `0x1800b5490`
- `0x1801123a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ef1`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180062ba2`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180062d7c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180062ba2`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180062d7c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180062cf6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180062cf6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180062dde`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180062dde`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180062e26`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180062ecb`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180062e26`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180062ecb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180062ea4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180062ea4`
- `ntdll!RtlLengthSid` at `0x180062b5a`
- `ntdll!RtlLengthSid` at `0x180062b5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSecurity::AdjustSecurityDescriptorWithSid(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        PSID pSid,
        DWORD a3,
        DWORD a4,
        void **a5)
{
  void **v7; // rdi
  __int16 v8; // r14
  BOOL AbsoluteSD; // ebx
  DWORD LastError; // eax
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // rcx
  struct _ACL *v15; // rbx
  struct _ACL *pSacl; // r13
  void *v17; // rsi
  void *v18; // rsi
  void *v19; // rsi
  BOOL SelfRelativeSD; // ebx
  DWORD v21; // eax
  HLOCAL v22; // rbx
  DWORD v23; // eax
  void *v25; // [rsp+68h] [rbp-31h] BYREF
  void *v26; // [rsp+70h] [rbp-29h] BYREF
  struct _ACL *v27; // [rsp+78h] [rbp-21h] BYREF
  struct _ACL *v28; // [rsp+80h] [rbp-19h] BYREF
  void *v29; // [rsp+88h] [rbp-11h] BYREF
  DWORD dwOwnerSize; // [rsp+90h] [rbp-9h] BYREF
  DWORD dwSaclSize; // [rsp+94h] [rbp-5h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+98h] [rbp-1h] BYREF
  DWORD dwDaclSize; // [rsp+9Ch] [rbp+3h] BYREF
  DWORD dwBufferLength; // [rsp+A0h] [rbp+7h] BYREF
  PSID pPrimaryGroup; // [rsp+A8h] [rbp+Fh]
  PSID pOwner; // [rsp+B0h] [rbp+17h]
  DWORD dwPrimaryGroupSize; // [rsp+F8h] [rbp+5Fh] BYREF
  DWORD AccessMask; // [rsp+108h] [rbp+6Fh]
  DWORD AceFlags; // [rsp+110h] [rbp+77h]

  AceFlags = a4;
  AccessMask = a3;
  if ( pSelfRelativeSecurityDescriptor )
  {
    v7 = a5;
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(a5);
    *v7 = 0;
    dwBufferLength = 0;
    v29 = 0;
    dwAbsoluteSecurityDescriptorSize = 40;
    v28 = 0;
    v27 = 0;
    v26 = 0;
    v25 = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    v8 = RtlLengthSid(pSid);
    AbsoluteSD = MakeAbsoluteSD(
                   pSelfRelativeSecurityDescriptor,
                   0,
                   &dwAbsoluteSecurityDescriptorSize,
                   0,
                   &dwDaclSize,
                   0,
                   &dwSaclSize,
                   0,
                   &dwOwnerSize,
                   0,
                   &dwPrimaryGroupSize);
    LastError = GetLastError();
    if ( AbsoluteSD )
    {
      if ( LastError != 122 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 821, L"821", 0x54Fu, 0);
        goto LABEL_45;
      }
    }
    else if ( LastError != 122 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_45;
      v11 = GetLastError();
      v12 = 36;
      goto LABEL_8;
    }
    v15 = (struct _ACL *)WSManMemory::Alloc(65530, 0, 0);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
    v28 = v15;
    pSacl = (struct _ACL *)WSManMemory::Alloc(dwSaclSize, 0, 0);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
    v27 = pSacl;
    v17 = (void *)WSManMemory::Alloc(dwOwnerSize, 0, 0);
    pOwner = v17;
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v26);
    v26 = v17;
    v18 = (void *)WSManMemory::Alloc(dwPrimaryGroupSize, 0, 0);
    pPrimaryGroup = v18;
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v25);
    v25 = v18;
    v19 = (void *)WSManMemory::Alloc(dwAbsoluteSecurityDescriptorSize, 0, 0);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
    v29 = v19;
    if ( v15 && pSacl && pOwner && pPrimaryGroup && v19 )
    {
      if ( !InitializeSecurityDescriptor(v19, 1u) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_45;
        v11 = GetLastError();
        v12 = 37;
        goto LABEL_8;
      }
      if ( !MakeAbsoluteSD(
              pSelfRelativeSecurityDescriptor,
              v19,
              &dwAbsoluteSecurityDescriptorSize,
              v15,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_45;
        v11 = GetLastError();
        v12 = 38;
        goto LABEL_8;
      }
      v15->AclSize = dwDaclSize + v8 + 8;
      if ( !AddAccessAllowedAceEx(v15, 2u, AceFlags, AccessMask, pSid) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_45;
        v11 = GetLastError();
        v12 = 39;
LABEL_8:
        v13 = v11;
        v14 = WPP_GLOBAL_Control;
LABEL_34:
        WPP_SF_d(v14[2], v12, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v13);
LABEL_45:
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v25);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v26);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
        return 0;
      }
      SelfRelativeSD = MakeSelfRelativeSD(v19, *v7, &dwBufferLength);
      v21 = GetLastError();
      if ( SelfRelativeSD )
      {
        if ( v21 != 122 )
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 881, L"881", 0x54Fu, 0);
          goto LABEL_45;
        }
      }
      else if ( v21 != 122 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_45;
        v12 = 40;
        v13 = v21;
        goto LABEL_34;
      }
      v22 = LocalAlloc(0, dwBufferLength);
      AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(v7);
      *v7 = v22;
      if ( v22 )
      {
        if ( MakeSelfRelativeSD(v19, v22, &dwBufferLength) )
        {
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v25);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v26);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
          return 1;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          v23 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v23);
        }
        AutoCleanup<AutoLocalFree,void *>::operator=(v7, 0);
        goto LABEL_45;
      }
    }
    SetLastError(0xEu);
    goto LABEL_45;
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 787, L"787", 0x54Fu, 0);
  return 0;
}

```

## disassembly

```asm
0x180062ac4  mov     rax, rsp
0x180062ac7  mov     [rax+10h], rbx
0x180062acb  mov     [rax+20h], r9d
0x180062acf  mov     [rax+18h], r8d
0x180062ad3  push    rbp
0x180062ad4  push    rsi
0x180062ad5  push    rdi
0x180062ad6  push    r12
0x180062ad8  push    r13
0x180062ada  push    r14
0x180062adc  push    r15
0x180062ade  lea     rbp, [rax-57h]
0x180062ae2  sub     rsp, 0B0h
0x180062ae9  mov     r12, rdx
0x180062aec  mov     r15, rcx
0x180062aef  xor     esi, esi
0x180062af1  test    rcx, rcx
0x180062af4  jnz     short loc_180062B1E
0x180062af6  mov     [rsp+0E0h+lpdwDaclSize], rsi; struct IRequestContext *
0x180062afb  mov     r9d, 54Fh; unsigned int
0x180062b01  lea     r8, a787; "787"
0x180062b08  mov     edx, 313h; unsigned int
0x180062b0d  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x180062b14  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180062b19  jmp     loc_180062F97
0x180062b1e  mov     rdi, [rbp+4Fh+arg_20]
0x180062b22  mov     rcx, rdi; void *
0x180062b25  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180062b2a  mov     [rdi], rsi
0x180062b2d  mov     [rbp+4Fh+dwBufferLength], esi
0x180062b30  mov     [rbp+4Fh+var_60], rsi
0x180062b34  mov     [rbp+4Fh+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x180062b3b  mov     [rbp+4Fh+var_68], rsi
0x180062b3f  mov     [rbp+4Fh+var_70], rsi
0x180062b43  mov     [rbp+4Fh+var_78], rsi
0x180062b47  mov     [rbp+4Fh+var_80], rsi
0x180062b4b  mov     [rbp+4Fh+dwDaclSize], esi
0x180062b4e  mov     [rbp+4Fh+dwSaclSize], esi
0x180062b51  mov     [rbp+4Fh+dwOwnerSize], esi
0x180062b54  mov     [rbp+4Fh+dwPrimaryGroupSize], esi
0x180062b57  mov     rcx, r12; Sid
0x180062b5a  call    cs:__imp_RtlLengthSid
0x180062b60  mov     r14d, eax
0x180062b63  lea     rax, [rbp+4Fh+dwPrimaryGroupSize]
0x180062b67  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180062b6c  mov     [rsp+0E0h+pPrimaryGroup], rsi; pPrimaryGroup
0x180062b71  lea     rax, [rbp+4Fh+dwOwnerSize]
0x180062b75  mov     [rsp+0E0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180062b7a  mov     [rsp+0E0h+pOwner], rsi; pOwner
0x180062b7f  lea     rax, [rbp+4Fh+dwSaclSize]
0x180062b83  mov     [rsp+0E0h+lpdwSaclSize], rax; lpdwSaclSize
0x180062b88  mov     [rsp+0E0h+pSacl], rsi; pSacl
0x180062b8d  lea     rax, [rbp+4Fh+dwDaclSize]
0x180062b91  mov     [rsp+0E0h+lpdwDaclSize], rax; lpdwDaclSize
0x180062b96  xor     r9d, r9d; pDacl
0x180062b99  lea     r8, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180062b9d  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180062b9f  mov     rcx, r15; pSelfRelativeSecurityDescriptor
0x180062ba2  call    cs:__imp_MakeAbsoluteSD
0x180062ba8  mov     ebx, eax
0x180062baa  call    cs:__imp_GetLastError
0x180062bb0  test    ebx, ebx
0x180062bb2  jnz     short loc_180062BF5
0x180062bb4  cmp     eax, 7Ah ; 'z'
0x180062bb7  jz      short loc_180062C22
0x180062bb9  lea     rax, WPP_GLOBAL_Control
0x180062bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bc7  cmp     rcx, rax
0x180062bca  jz      loc_180062F66
0x180062bd0  test    dword ptr [rcx+1Ch], 10000000h
0x180062bd7  jz      loc_180062F66
0x180062bdd  call    cs:__imp_GetLastError
0x180062be3  lea     edx, [rbx+24h]
0x180062be6  mov     r9d, eax
0x180062be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bf0  jmp     loc_180062E6A
0x180062bf5  cmp     eax, 7Ah ; 'z'
0x180062bf8  jz      short loc_180062C22
0x180062bfa  mov     [rsp+0E0h+lpdwDaclSize], rsi; struct IRequestContext *
0x180062bff  lea     r8, a821; "821"
0x180062c06  mov     edx, 335h; unsigned int
0x180062c0b  mov     r9d, 54Fh; unsigned int
0x180062c11  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x180062c18  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180062c1d  jmp     loc_180062F66
0x180062c22  xor     r8d, r8d
0x180062c25  xor     edx, edx
0x180062c27  mov     ecx, 0FFFAh
0x180062c2c  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180062c31  mov     rbx, rax
0x180062c34  lea     rcx, [rbp+4Fh+var_68]
0x180062c38  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062c3d  mov     [rbp+4Fh+var_68], rbx
0x180062c41  mov     ecx, [rbp+4Fh+dwSaclSize]
0x180062c44  xor     r8d, r8d
0x180062c47  xor     edx, edx
0x180062c49  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180062c4e  mov     r13, rax
0x180062c51  lea     rcx, [rbp+4Fh+var_70]
0x180062c55  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062c5a  mov     [rbp+4Fh+var_70], r13
0x180062c5e  mov     ecx, [rbp+4Fh+dwOwnerSize]
0x180062c61  xor     r8d, r8d
0x180062c64  xor     edx, edx
0x180062c66  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180062c6b  mov     rsi, rax
0x180062c6e  mov     [rbp+4Fh+var_38], rax
0x180062c72  lea     rcx, [rbp+4Fh+var_78]
0x180062c76  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062c7b  mov     [rbp+4Fh+var_78], rsi
0x180062c7f  mov     ecx, [rbp+4Fh+dwPrimaryGroupSize]
0x180062c82  xor     r8d, r8d
0x180062c85  xor     edx, edx
0x180062c87  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180062c8c  mov     rsi, rax
0x180062c8f  mov     [rbp+4Fh+var_40], rax
0x180062c93  lea     rcx, [rbp+4Fh+var_80]
0x180062c97  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062c9c  mov     [rbp+4Fh+var_80], rsi
0x180062ca0  mov     ecx, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]
0x180062ca3  xor     r8d, r8d
0x180062ca6  xor     edx, edx
0x180062ca8  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180062cad  mov     rsi, rax
0x180062cb0  lea     rcx, [rbp+4Fh+var_60]
0x180062cb4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062cb9  mov     [rbp+4Fh+var_60], rsi
0x180062cbd  test    rbx, rbx
0x180062cc0  jz      loc_180062F5A
0x180062cc6  test    r13, r13
0x180062cc9  jz      loc_180062F5A
0x180062ccf  cmp     [rbp+4Fh+var_38], 0
0x180062cd4  jz      loc_180062F5A
0x180062cda  cmp     [rbp+4Fh+var_40], 0
0x180062cdf  jz      loc_180062F5A
0x180062ce5  test    rsi, rsi
0x180062ce8  jz      loc_180062F5A
0x180062cee  mov     edx, 1; dwRevision
0x180062cf3  mov     rcx, rsi; pSecurityDescriptor
0x180062cf6  call    cs:__imp_InitializeSecurityDescriptor
0x180062cfc  test    eax, eax
0x180062cfe  jnz     short loc_180062D34
0x180062d00  lea     rax, WPP_GLOBAL_Control
0x180062d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d0e  cmp     rcx, rax
0x180062d11  jz      loc_180062F66
0x180062d17  test    dword ptr [rcx+1Ch], 10000000h
0x180062d1e  jz      loc_180062F66
0x180062d24  call    cs:__imp_GetLastError
0x180062d2a  mov     edx, 25h ; '%'
0x180062d2f  jmp     loc_180062BE6
0x180062d34  lea     rax, [rbp+4Fh+dwPrimaryGroupSize]
0x180062d38  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180062d3d  mov     rax, [rbp+4Fh+var_40]
0x180062d41  mov     [rsp+0E0h+pPrimaryGroup], rax; pPrimaryGroup
0x180062d46  lea     rax, [rbp+4Fh+dwOwnerSize]
0x180062d4a  mov     [rsp+0E0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180062d4f  mov     rax, [rbp+4Fh+var_38]
0x180062d53  mov     [rsp+0E0h+pOwner], rax; pOwner
0x180062d58  lea     rax, [rbp+4Fh+dwSaclSize]
0x180062d5c  mov     [rsp+0E0h+lpdwSaclSize], rax; lpdwSaclSize
0x180062d61  mov     [rsp+0E0h+pSacl], r13; pSacl
0x180062d66  lea     rax, [rbp+4Fh+dwDaclSize]
0x180062d6a  mov     [rsp+0E0h+lpdwDaclSize], rax; lpdwDaclSize
0x180062d6f  mov     r9, rbx; pDacl
0x180062d72  lea     r8, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180062d76  mov     rdx, rsi; pAbsoluteSecurityDescriptor
0x180062d79  mov     rcx, r15; pSelfRelativeSecurityDescriptor
0x180062d7c  call    cs:__imp_MakeAbsoluteSD
0x180062d82  test    eax, eax
0x180062d84  jnz     short loc_180062DBA
0x180062d86  lea     rax, WPP_GLOBAL_Control
0x180062d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d94  cmp     rcx, rax
0x180062d97  jz      loc_180062F66
0x180062d9d  test    dword ptr [rcx+1Ch], 10000000h
0x180062da4  jz      loc_180062F66
0x180062daa  call    cs:__imp_GetLastError
0x180062db0  mov     edx, 26h ; '&'
0x180062db5  jmp     loc_180062BE6
0x180062dba  add     r14w, 8
0x180062dbf  add     r14w, word ptr [rbp+4Fh+dwDaclSize]
0x180062dc4  mov     [rbx+2], r14w
0x180062dc9  mov     [rsp+0E0h+lpdwDaclSize], r12; pSid
0x180062dce  mov     r9d, [rbp+4Fh+AccessMask]; AccessMask
0x180062dd2  mov     r8d, [rbp+4Fh+AceFlags]; AceFlags
0x180062dd6  mov     edx, 2; dwAceRevision
0x180062ddb  mov     rcx, rbx; pAcl
0x180062dde  call    cs:__imp_AddAccessAllowedAceEx
0x180062de4  test    eax, eax
0x180062de6  jnz     short loc_180062E1C
0x180062de8  lea     rax, WPP_GLOBAL_Control
0x180062def  mov     rcx, cs:WPP_GLOBAL_Control
0x180062df6  cmp     rcx, rax
0x180062df9  jz      loc_180062F66
0x180062dff  test    dword ptr [rcx+1Ch], 10000000h
0x180062e06  jz      loc_180062F66
0x180062e0c  call    cs:__imp_GetLastError
0x180062e12  mov     edx, 27h ; '''
0x180062e17  jmp     loc_180062BE6
0x180062e1c  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x180062e20  mov     rdx, [rdi]; pSelfRelativeSecurityDescriptor
0x180062e23  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180062e26  call    cs:__imp_MakeSelfRelativeSD
0x180062e2c  mov     ebx, eax
0x180062e2e  call    cs:__imp_GetLastError
0x180062e34  mov     r8d, eax
0x180062e37  test    ebx, ebx
0x180062e39  jnz     short loc_180062E7F
0x180062e3b  cmp     eax, 7Ah ; 'z'
0x180062e3e  jz      short loc_180062E9F
0x180062e40  lea     rax, WPP_GLOBAL_Control
0x180062e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e4e  cmp     rcx, rax
0x180062e51  jz      loc_180062F66
0x180062e57  test    dword ptr [rcx+1Ch], 10000000h
0x180062e5e  jz      loc_180062F66
0x180062e64  lea     edx, [rbx+28h]
0x180062e67  mov     r9d, r8d
0x180062e6a  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180062e71  mov     rcx, [rcx+10h]
0x180062e75  call    WPP_SF_d
0x180062e7a  jmp     loc_180062F66
0x180062e7f  cmp     r8d, 7Ah ; 'z'
0x180062e83  jz      short loc_180062E9F
0x180062e85  mov     [rsp+0E0h+lpdwDaclSize], 0
0x180062e8e  lea     r8, a881; "881"
0x180062e95  mov     edx, 371h
0x180062e9a  jmp     loc_180062C0B
0x180062e9f  mov     edx, [rbp+4Fh+dwBufferLength]; uBytes
0x180062ea2  xor     ecx, ecx; uFlags
0x180062ea4  call    cs:__imp_LocalAlloc
0x180062eaa  mov     rbx, rax
0x180062ead  mov     rcx, rdi; void *
0x180062eb0  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180062eb5  mov     [rdi], rbx
0x180062eb8  test    rbx, rbx
0x180062ebb  jz      loc_180062F5A
0x180062ec1  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x180062ec5  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x180062ec8  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180062ecb  call    cs:__imp_MakeSelfRelativeSD
0x180062ed1  test    eax, eax
0x180062ed3  jnz     short loc_180062F22
0x180062ed5  lea     rax, WPP_GLOBAL_Control
0x180062edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ee3  cmp     rcx, rax
0x180062ee6  jz      short loc_180062F16
0x180062ee8  test    dword ptr [rcx+1Ch], 10000000h
0x180062eef  jz      short loc_180062F16
0x180062ef1  call    cs:__imp_GetLastError
0x180062ef7  mov     edx, 29h ; ')'
0x180062efc  mov     r9d, eax
0x180062eff  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180062f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f0d  mov     rcx, [rcx+10h]
0x180062f11  call    WPP_SF_d
0x180062f16  xor     edx, edx
0x180062f18  mov     rcx, rdi
0x180062f1b  call    ??4?$AutoCleanup@VAutoLocalFree@@PEAX@@QEAAAEAVAutoLocalFree@@PEAX@Z; AutoCleanup<AutoLocalFree,void *>::operator=(void *)
0x180062f20  jmp     short loc_180062F66
0x180062f22  lea     rcx, [rbp+4Fh+var_80]
0x180062f26  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f2b  nop
0x180062f2c  lea     rcx, [rbp+4Fh+var_78]
0x180062f30  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f35  nop
0x180062f36  lea     rcx, [rbp+4Fh+var_70]
0x180062f3a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f3f  nop
0x180062f40  lea     rcx, [rbp+4Fh+var_68]
0x180062f44  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f49  nop
0x180062f4a  lea     rcx, [rbp+4Fh+var_60]
0x180062f4e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f53  mov     eax, 1
0x180062f58  jmp     short loc_180062F99
0x180062f5a  mov     ecx, 0Eh; dwErrCode
0x180062f5f  call    cs:__imp_SetLastError
0x180062f65  nop
0x180062f66  lea     rcx, [rbp+4Fh+var_80]
0x180062f6a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f6f  nop
0x180062f70  lea     rcx, [rbp+4Fh+var_78]
0x180062f74  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f79  nop
0x180062f7a  lea     rcx, [rbp+4Fh+var_70]
0x180062f7e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f83  nop
0x180062f84  lea     rcx, [rbp+4Fh+var_68]
0x180062f88  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f8d  nop
0x180062f8e  lea     rcx, [rbp+4Fh+var_60]
0x180062f92  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180062f97  xor     eax, eax
0x180062f99  mov     rbx, [rsp+0E0h+arg_8]
0x180062fa1  add     rsp, 0B0h
0x180062fa8  pop     r15
0x180062faa  pop     r14
0x180062fac  pop     r13
  ... truncated ...
```
