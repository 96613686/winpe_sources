# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x180819088`
- end: `0x180819284`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `508`
- prototype: `HRESULT __fastcall(void *oldSD, void *userSid, unsigned int flags, bool *exists, void *newSD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180818410`

## callees

- `0x1805117cc`
- `0x1806925ec`
- `0x18076e110`
- `0x180819088`
- `0x180822eb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1808191b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1808191b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1808191c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1808191c5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18081925c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18081925c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180819247`
- `ntdll!RtlAddAccessAllowedAce` at `0x180819247`
- `ntdll!RtlAddAce` at `0x180819231`
- `ntdll!RtlAddAce` at `0x180819231`
- `ntdll!RtlGetAce` at `0x180819210`
- `ntdll!RtlGetAce` at `0x180819210`
- `ntdll!RtlCreateAcl` at `0x1808191f4`
- `ntdll!RtlCreateAcl` at `0x1808191f4`
- `ntdll!RtlLengthSid` at `0x1808191a3`
- `ntdll!RtlLengthSid` at `0x1808191a3`
- `ntdll!RtlQueryInformationAcl` at `0x18081916b`
- `ntdll!RtlQueryInformationAcl` at `0x180819192`
- `ntdll!RtlQueryInformationAcl` at `0x18081916b`
- `ntdll!RtlQueryInformationAcl` at `0x180819192`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1808190d1`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1808190d1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180819104`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180819104`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18081911e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18081911e`

## pseudocode

```c
HRESULT __fastcall BuildUserSD(void *oldSD, void *userSid, ACCESS_MASK flags, bool *exists, PSECURITY_DESCRIPTOR newSD)
{
  NTSTATUS DaclSecurityDescriptor; // eax
  DWORD i; // ebx
  _ACE_HEADER *v11; // rdi
  ULONG v12; // eax
  ULONG v13; // r14d
  HANDLE ProcessHeap; // rax
  _ACL *v15; // rax
  _ACL *v16; // rdi
  HRESULT v17; // ebx
  NTSTATUS Acl; // eax
  unsigned __int8 daclDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 daclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  _ACL_REVISION_INFORMATION aclRevisionInfo; // [rsp+34h] [rbp-3Ch] BYREF
  _ACL *dacl; // [rsp+38h] [rbp-38h] BYREF
  _ACE_HEADER *aceHeader; // [rsp+40h] [rbp-30h] BYREF
  _ACCESS_ALLOWED_ACE *ace; // [rsp+48h] [rbp-28h] BYREF
  _ACL_SIZE_INFORMATION aclSizeInfo; // [rsp+50h] [rbp-20h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+38h]

  daclPresent[0] = 0;
  dacl = 0;
  daclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(oldSD, daclPresent, &dacl, &daclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
    return wil::details::in1diag0::Return_NtStatus(retaddr, DaclSecurityDescriptor);
  for ( i = 0; i < dacl->AceCount; ++i )
  {
    aceHeader = 0;
    if ( GetAce(dacl, i, (LPVOID *)&aceHeader) )
    {
      v11 = aceHeader;
      if ( !aceHeader->AceType && EqualSid(&aceHeader[2], userSid) && (flags & *(_DWORD *)&v11[1]) == flags )
      {
        *exists = 1;
        return 0;
      }
    }
  }
  *(_QWORD *)&aclSizeInfo.AceCount = 0;
  aclSizeInfo.AclBytesFree = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(dacl, &aclSizeInfo, 0xCu, AclSizeInformation);
  if ( DaclSecurityDescriptor < 0 )
    return wil::details::in1diag0::Return_NtStatus(retaddr, DaclSecurityDescriptor);
  aclRevisionInfo.AclRevision = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(dacl, &aclRevisionInfo, 4u, AclRevisionInformation);
  if ( DaclSecurityDescriptor < 0 )
    return wil::details::in1diag0::Return_NtStatus(retaddr, DaclSecurityDescriptor);
  v12 = RtlLengthSid(userSid);
  v13 = v12 + aclSizeInfo.AclBytesInUse + 8;
  ProcessHeap = GetProcessHeap();
  v15 = (_ACL *)HeapAlloc(ProcessHeap, 8u, v13);
  v16 = v15;
  if ( v15 )
  {
    Acl = RtlCreateAcl(v15, v13, aclRevisionInfo.AclRevision);
    if ( Acl >= 0 )
    {
      ace = 0;
      Acl = RtlGetAce(dacl, 0, (PVOID *)&ace);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAce(v16, aclRevisionInfo.AclRevision, 0, ace, aclSizeInfo.AclBytesInUse - 8);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v16, aclRevisionInfo.AclRevision, flags, userSid);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(newSD, 1u, v16, 0);
            if ( Acl >= 0 )
              return 0;
          }
        }
      }
    }
    v17 = wil::details::in1diag0::Return_NtStatus(retaddr, Acl);
    DeallocateWarningContext((WarningContext *)v16);
  }
  else
  {
    v17 = -2147024882;
    wil::details::in1diag0::Return_Hr(retaddr, -2147024882);
  }
  return v17;
}

```

## disassembly

```asm
0x180819088  push    rbp
0x18081908a  push    rbx
0x18081908b  push    rsi
0x18081908c  push    rdi
0x18081908d  push    r12
0x18081908f  push    r14
0x180819091  push    r15
0x180819093  mov     rbp, rsp
0x180819096  sub     rsp, 70h
0x18081909a  mov     rax, cs:__security_cookie
0x1808190a1  xor     rax, rsp
0x1808190a4  mov     [rbp+var_10], rax
0x1808190a8  mov     r12, [rbp+SecurityDescriptor]
0x1808190ac  mov     r14, exists
0x1808190af  mov     esi, flags
0x1808190b2  mov     [rbp+daclPresent], 0
0x1808190b6  mov     r15, userSid
0x1808190b9  mov     [rbp+dacl], 0
0x1808190c1  lea     exists, [rbp+daclDefaulted]; DaclDefaulted
0x1808190c5  mov     [rbp+daclDefaulted], 0
0x1808190c9  lea     r8, [rbp+dacl]; Dacl
0x1808190cd  lea     userSid, [rbp+daclPresent]; DaclPresent
0x1808190d1  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1808190d7  test    eax, eax
0x1808190d9  jns     short loc_1808190E8
0x1808190db  mov     oldSD, [rbp+38h]; callerReturnAddress
0x1808190df  mov     edx, eax; status
0x1808190e1  call    ?Return_NtStatus@in1diag0@details@wil@@YAJPEAXJ@Z; wil::details::in1diag0::Return_NtStatus(void *,long)
0x1808190e6  jmp     short loc_18081913B
0x1808190e8  xor     ebx, ebx
0x1808190ea  mov     oldSD, [rbp+dacl]; Acl
0x1808190ee  movzx   eax, word ptr [oldSD+4]
0x1808190f2  cmp     ebx, eax
0x1808190f4  jnb     short loc_180819156
0x1808190f6  lea     r8, [rbp+aceHeader]; pAce
0x1808190fa  mov     [rbp+aceHeader], 0
0x180819102  mov     edx, ebx; dwAceIndex
0x180819104  call    cs:__imp_GetAce
0x18081910a  test    eax, eax
0x18081910c  jz      short loc_180819131
0x18081910e  mov     rdi, [rbp+aceHeader]
0x180819112  cmp     byte ptr [rdi], 0
0x180819115  jnz     short loc_180819131
0x180819117  lea     oldSD, [rdi+8]; pSid1
0x18081911b  mov     userSid, r15; pSid2
0x18081911e  call    cs:__imp_EqualSid
0x180819124  test    eax, eax
0x180819126  jz      short loc_180819131
0x180819128  mov     eax, [rdi+4]
0x18081912b  and     eax, esi
0x18081912d  cmp     eax, esi
0x18081912f  jz      short loc_180819135
0x180819131  inc     ebx
0x180819133  jmp     short loc_1808190EA
0x180819135  mov     byte ptr [r14], 1
0x180819139  xor     eax, eax
0x18081913b  mov     oldSD, [rbp+var_10]
0x18081913f  xor     oldSD, rsp; StackCookie
0x180819142  call    __security_check_cookie
0x180819147  add     rsp, 70h
0x18081914b  pop     r15
0x18081914d  pop     r14
0x18081914f  pop     r12
0x180819151  pop     rdi
0x180819152  pop     rsi
0x180819153  pop     rbx
0x180819154  pop     rbp
0x180819155  retn
0x180819156  xor     eax, eax
0x180819158  lea     userSid, [rbp+aclSizeInfo]; Information
0x18081915c  mov     qword ptr [rbp+aclSizeInfo.AceCount], rax
0x180819160  mov     [rbp+aclSizeInfo.AclBytesFree], eax
0x180819163  lea     r9d, [rax+2]; InformationClass
0x180819167  lea     flags, [rax+0Ch]; InformationLength
0x18081916b  call    cs:__imp_RtlQueryInformationAcl
0x180819171  test    eax, eax
0x180819173  js      loc_1808190DB
0x180819179  mov     oldSD, [rbp+dacl]; Acl
0x18081917d  lea     userSid, [rbp+aclRevisionInfo]; Information
0x180819181  mov     r9d, 1; InformationClass
0x180819187  mov     [rbp+aclRevisionInfo.AclRevision], 0
0x18081918e  lea     flags, [exists+3]; InformationLength
0x180819192  call    cs:__imp_RtlQueryInformationAcl
0x180819198  test    eax, eax
0x18081919a  js      loc_1808190DB
0x1808191a0  mov     oldSD, r15; Sid
0x1808191a3  call    cs:__imp_RtlLengthSid
0x1808191a9  mov     r14d, [rbp+aclSizeInfo.AclBytesInUse]
0x1808191ad  add     r14d, 8
0x1808191b1  add     r14d, eax
0x1808191b4  call    cs:__imp_GetProcessHeap
0x1808191ba  mov     flags, r14d; dwBytes
0x1808191bd  mov     edx, 8; dwFlags
0x1808191c2  mov     oldSD, rax; hHeap
0x1808191c5  call    cs:__imp_HeapAlloc
0x1808191cb  mov     rdi, rax
0x1808191ce  test    rax, rax
0x1808191d1  jnz     short loc_1808191EA
0x1808191d3  mov     oldSD, [rbp+38h]; callerReturnAddress
0x1808191d7  mov     ebx, 8007000Eh
0x1808191dc  mov     edx, ebx; hr
0x1808191de  call    ?Return_Hr@in1diag0@details@wil@@YAXPEAXJ@Z; wil::details::in1diag0::Return_Hr(void *,long)
0x1808191e3  mov     eax, ebx
0x1808191e5  jmp     loc_18081913B
0x1808191ea  mov     flags, [rbp+aclRevisionInfo.AclRevision]; AclRevision
0x1808191ee  mov     edx, r14d; AclSize
0x1808191f1  mov     oldSD, rdi; Acl
0x1808191f4  call    cs:__imp_RtlCreateAcl
0x1808191fa  test    eax, eax
0x1808191fc  js      short loc_18081926A
0x1808191fe  mov     oldSD, [rbp+dacl]; Acl
0x180819202  lea     r8, [rbp+ace]; Ace
0x180819206  xor     edx, edx; AceIndex
0x180819208  mov     [rbp+ace], 0
0x180819210  call    cs:__imp_RtlGetAce
0x180819216  test    eax, eax
0x180819218  js      short loc_18081926A
0x18081921a  mov     eax, [rbp+aclSizeInfo.AclBytesInUse]
0x18081921d  xor     flags, flags; StartingAceIndex
0x180819220  mov     exists, [rbp+ace]; AceList
0x180819224  add     eax, 0FFFFFFF8h
0x180819227  mov     edx, [rbp+aclRevisionInfo.AclRevision]; AceRevision
0x18081922a  mov     oldSD, rdi; Acl
0x18081922d  mov     [rsp+70h+AceListLength], eax; AceListLength
0x180819231  call    cs:__imp_RtlAddAce
0x180819237  test    eax, eax
0x180819239  js      short loc_18081926A
0x18081923b  mov     edx, [rbp+aclRevisionInfo.AclRevision]; Revision
0x18081923e  mov     exists, r15; Sid
0x180819241  mov     flags, esi; AccessMask
0x180819244  mov     oldSD, rdi; Acl
0x180819247  call    cs:__imp_RtlAddAccessAllowedAce
0x18081924d  test    eax, eax
0x18081924f  js      short loc_18081926A
0x180819251  xor     r9d, r9d; DaclDefaulted
0x180819254  mov     r8, rdi; Dacl
0x180819257  mov     dl, 1; DaclPresent
0x180819259  mov     oldSD, r12; SecurityDescriptor
0x18081925c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180819262  test    eax, eax
0x180819264  jns     loc_180819139
0x18081926a  mov     oldSD, [rbp+38h]; callerReturnAddress
0x18081926e  mov     edx, eax; status
0x180819270  call    ?Return_NtStatus@in1diag0@details@wil@@YAJPEAXJ@Z; wil::details::in1diag0::Return_NtStatus(void *,long)
0x180819275  mov     oldSD, rdi; context
0x180819278  mov     ebx, eax
0x18081927a  call    ?DeallocateWarningContext@@YAHPEAUWarningContext@@@Z; DeallocateWarningContext(WarningContext *)
0x18081927f  jmp     loc_1808191E3
```
