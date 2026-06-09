# SetApplicationSecurity(HKEY__ *,ushort const *,ulong)

- ea: `0x14002e814`
- end: `0x14002eebf`
- name: `?SetApplicationSecurity@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `1707`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018624`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x1400234b8`
- `0x14002e814`
- `0x140046430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e89f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e937`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e9de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002ea87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002eb2f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e89f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e937`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002e9de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002ea87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002eb2f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002ecfc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002ecfc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002ece0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002ece0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e887`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e929`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e9cf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002ea79`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002eb21`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e887`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e929`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002e9cf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002ea79`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002eb21`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002e8cf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002e964`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002ea0e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002eab8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002eb5f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002e8cf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002e964`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002ea0e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002eab8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002eb5f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002ebd8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002ebd8`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec06`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec34`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec60`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec8c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ecbb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec06`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec34`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec60`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ec8c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ecbb`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14002ed62`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14002ed62`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14002ed2f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14002ed2f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee0e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee1e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee3c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee4b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee0e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee1e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee3c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002ee4b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14002ed3d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14002ed3d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14002ed16`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14002ed16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002ed8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002ed8d`
- `wbemcomn!GetMemLogObject` at `0x14002ee55`
- `wbemcomn!GetMemLogObject` at `0x14002ee55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002ee60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002ee60`

## pseudocode

```c
__int64 __fastcall SetApplicationSecurity(HKEY a1, const unsigned __int16 *a2)
{
  _WORD *v2; // r13
  DWORD LengthSid; // edi
  char *v4; // rax
  _DWORD *v5; // rsi
  int v6; // ebx
  DWORD v7; // edi
  __int16 v8; // r14
  char *v9; // rax
  _DWORD *v10; // r15
  unsigned __int16 v11; // di
  DWORD v12; // r13d
  __int16 v13; // r14
  char *v14; // rax
  _DWORD *v15; // r12
  char *v16; // rax
  _WORD *v17; // r14
  char *v18; // rax
  unsigned __int16 v19; // ax
  DWORD v20; // edi
  struct _ACL *v21; // rax
  BOOL v22; // eax
  DWORD v23; // edi
  DWORD v24; // r8d
  struct _ACL *v25; // rdi
  BYTE *v26; // rax
  BYTE *v27; // rdi
  CMemoryLog *MemLogObject; // rax
  DWORD nDestinationSidLength; // [rsp+60h] [rbp-A0h] BYREF
  PACL pAcl; // [rsp+68h] [rbp-98h]
  SIZE_T v32; // [rsp+70h] [rbp-90h]
  PSID pOwner; // [rsp+78h] [rbp-88h] BYREF
  PSID pSourceSid; // [rsp+80h] [rbp-80h] BYREF
  SIZE_T v35; // [rsp+88h] [rbp-78h]
  SIZE_T v36; // [rsp+90h] [rbp-70h]
  SIZE_T v37; // [rsp+98h] [rbp-68h]
  SIZE_T v38; // [rsp+A0h] [rbp-60h]
  PSID pSid; // [rsp+A8h] [rbp-58h] BYREF
  PSID v40; // [rsp+B0h] [rbp-50h] BYREF
  PSID v41; // [rsp+B8h] [rbp-48h] BYREF
  DWORD nAceListLength; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h]
  _OWORD pSecurityDescriptor[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-10h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+F8h] [rbp-8h] BYREF

  v2 = 0;
  hKey = a1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSourceSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v38 = (unsigned __int16)(LengthSid + 8);
    v4 = (char *)operator new(v38);
    v5 = v4;
    if ( v4 )
    {
      v6 = 0;
      CopySid(LengthSid, v4 + 8, pSourceSid);
      v5[1] = 1;
      *(_WORD *)v5 = 768;
      *((_WORD *)v5 + 1) = LengthSid + 8;
      goto LABEL_6;
    }
  }
  else
  {
    v5 = 0;
    LOWORD(v38) = 0;
  }
  v6 = -2147024882;
LABEL_6:
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v7 = GetLengthSid(pSid);
    v8 = v7 + 8;
    v35 = (unsigned __int16)(v7 + 8);
    v9 = (char *)operator new(v35);
    v10 = v9;
    if ( v9 )
    {
      CopySid(v7, v9 + 8, pSid);
      v10[1] = 1;
      v11 = v7 + 8;
      *(_WORD *)v10 = 768;
      *((_WORD *)v10 + 1) = v8;
      goto LABEL_12;
    }
    v11 = v35;
  }
  else
  {
    v11 = 0;
    v10 = 0;
    v35 = 0;
  }
  v6 = -2147024882;
LABEL_12:
  pOwner = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pOwner) )
  {
    v12 = GetLengthSid(pOwner);
    v13 = v12 + 8;
    v36 = (unsigned __int16)(v12 + 8);
    v14 = (char *)operator new(v36);
    v15 = v14;
    if ( v14 )
    {
      CopySid(v12, v14 + 8, pOwner);
      v2 = 0;
      v15[1] = 1;
      *(_WORD *)v15 = 768;
      *((_WORD *)v15 + 1) = v13;
      goto LABEL_18;
    }
    v2 = 0;
  }
  else
  {
    v15 = 0;
    LOWORD(v36) = 0;
  }
  v6 = -2147024882;
LABEL_18:
  v40 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &v40) )
  {
    nDestinationSidLength = GetLengthSid(v40);
    v37 = (unsigned __int16)(nDestinationSidLength + 8);
    v16 = (char *)operator new(v37);
    v2 = v16;
    if ( v16 )
    {
      CopySid(nDestinationSidLength, v16 + 8, v40);
      v2[1] = nDestinationSidLength + 8;
      v17 = 0;
      *((_DWORD *)v2 + 1) = 1;
      *v2 = 768;
      goto LABEL_24;
    }
    v17 = 0;
  }
  else
  {
    v17 = 0;
    LOWORD(v37) = 0;
  }
  v6 = -2147024882;
LABEL_24:
  v41 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v41) )
  {
    nDestinationSidLength = GetLengthSid(v41);
    v32 = (unsigned __int16)(nDestinationSidLength + 8);
    v18 = (char *)operator new(v32);
    v17 = v18;
    if ( v18 )
    {
      CopySid(nDestinationSidLength, v18 + 8, v41);
      v19 = v32;
      v17[1] = v32;
      *((_DWORD *)v17 + 1) = 1;
      *v17 = 768;
      goto LABEL_29;
    }
  }
  else
  {
    LOWORD(v32) = 0;
  }
  v19 = v32;
  v6 = -2147024882;
LABEL_29:
  nAceListLength = v19;
  nDestinationSidLength = v11;
  v20 = v11 + (unsigned __int16)v36 + (unsigned __int16)v37 + v19 + (unsigned __int16)v38 + 8;
  v21 = (struct _ACL *)operator new(v20);
  pAcl = v21;
  if ( v21 )
  {
    v22 = InitializeAcl(v21, v20, 2u);
    v23 = 0;
    if ( v22 )
    {
      if ( (_WORD)v35 )
        v23 = AddAce(pAcl, 2u, 0, v10, nDestinationSidLength);
      if ( (_WORD)v36 && AddAce(pAcl, 2u, v23, v15, (unsigned __int16)v36) )
        ++v23;
      if ( (_WORD)v37 && AddAce(pAcl, 2u, v23, v2, (unsigned __int16)v37) )
        ++v23;
      if ( (_WORD)v32 && AddAce(pAcl, 2u, v23, v17, nAceListLength) )
        ++v23;
      if ( (_WORD)v38 )
      {
        v24 = v23;
        v25 = pAcl;
        AddAce(pAcl, 2u, v24, v5, (unsigned __int16)v38);
      }
      else
      {
        v25 = pAcl;
      }
      v45 = 0;
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v25, 0)
        && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorGroup(pSecurityDescriptor, pSourceSid, 0) )
      {
        nDestinationSidLength = GetSecurityDescriptorLength(pSecurityDescriptor);
        v26 = (BYTE *)operator new(nDestinationSidLength);
        v27 = v26;
        if ( v26 )
        {
          if ( MakeSelfRelativeSD(pSecurityDescriptor, v26, &nDestinationSidLength)
            && RegSetValueExW(hKey, L"LaunchPermission", 0, 3u, v27, nDestinationSidLength) )
          {
            v6 = -2147467259;
          }
          operator delete(v27);
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
    operator delete(pAcl);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v5 )
    operator delete(v5);
  if ( v10 )
    operator delete(v10);
  if ( v15 )
    operator delete(v15);
  if ( v2 )
    operator delete(v2);
  if ( v17 )
    operator delete(v17);
  if ( pSid )
    FreeSid(pSid);
  if ( pOwner )
    FreeSid(pOwner);
  if ( v40 )
    FreeSid(v40);
  if ( v41 )
    FreeSid(v41);
  if ( pSourceSid )
    FreeSid(pSourceSid);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ab3eb8767f543ce5f762c54a6df9dbe9_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002e814  push    rbp
0x14002e816  push    rbx
0x14002e817  push    rsi
0x14002e818  push    rdi
0x14002e819  push    r12
0x14002e81b  push    r13
0x14002e81d  push    r14
0x14002e81f  push    r15
0x14002e821  lea     rbp, [rsp-18h]
0x14002e826  sub     rsp, 118h
0x14002e82d  mov     rax, cs:__security_cookie
0x14002e834  xor     rax, rsp
0x14002e837  mov     [rbp+50h+var_50], rax
0x14002e83b  xor     r13d, r13d
0x14002e83e  mov     [rbp+50h+hKey], rcx
0x14002e842  lea     rax, [rbp+50h+pSourceSid]
0x14002e846  mov     dword ptr [rbp+50h+pIdentifierAuthority.Value], r13d
0x14002e84a  mov     [rsp+150h+pSid], rax; pSid
0x14002e84f  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x14002e853  mov     [rsp+150h+nSubAuthority7], r13d; nSubAuthority7
0x14002e858  mov     r9d, 220h; nSubAuthority1
0x14002e85e  mov     [rsp+150h+nSubAuthority6], r13d; nSubAuthority6
0x14002e863  lea     r8d, [r13+20h]; nSubAuthority0
0x14002e867  mov     [rsp+150h+nSubAuthority5], r13d; nSubAuthority5
0x14002e86c  mov     dl, 2; nSubAuthorityCount
0x14002e86e  mov     [rsp+150h+nSubAuthority4], r13d; nSubAuthority4
0x14002e873  mov     [rsp+150h+nSubAuthority3], r13d; nSubAuthority3
0x14002e878  mov     [rsp+150h+nSubAuthority2], r13d; nSubAuthority2
0x14002e87d  mov     word ptr [rbp+50h+pIdentifierAuthority.Value+4], 500h
0x14002e883  mov     [rbp+50h+pSourceSid], r13
0x14002e887  call    cs:__imp_AllocateAndInitializeSid
0x14002e88d  lea     r15d, [r13+1]
0x14002e891  mov     r12d, 8007000Eh
0x14002e897  test    eax, eax
0x14002e899  jz      short loc_14002E8E5
0x14002e89b  mov     rcx, [rbp+50h+pSourceSid]; pSid
0x14002e89f  call    cs:__imp_GetLengthSid
0x14002e8a5  mov     edi, eax
0x14002e8a7  lea     ecx, [rax+8]
0x14002e8aa  movzx   r14d, cx
0x14002e8ae  mov     ecx, r14d; dwBytes
0x14002e8b1  mov     [rbp+50h+var_B0], r14
0x14002e8b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e8ba  mov     rsi, rax
0x14002e8bd  test    rax, rax
0x14002e8c0  jz      short loc_14002E8ED
0x14002e8c2  mov     r8, [rbp+50h+pSourceSid]; pSourceSid
0x14002e8c6  lea     rdx, [rax+8]; pDestinationSid
0x14002e8ca  mov     ecx, edi; nDestinationSidLength
0x14002e8cc  mov     ebx, r13d
0x14002e8cf  call    cs:__imp_CopySid
0x14002e8d5  mov     [rsi+4], r15d
0x14002e8d9  mov     word ptr [rsi], 300h
0x14002e8de  mov     [rsi+2], r14w
0x14002e8e3  jmp     short loc_14002E8F0
0x14002e8e5  mov     rsi, r13
0x14002e8e8  mov     word ptr [rbp+50h+var_B0], r13w
0x14002e8ed  mov     ebx, r12d
0x14002e8f0  lea     rax, [rbp+50h+var_A8]
0x14002e8f4  mov     [rbp+50h+var_A8], r13
0x14002e8f8  mov     [rsp+150h+pSid], rax; pSid
0x14002e8fd  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x14002e901  mov     [rsp+150h+nSubAuthority7], r13d; nSubAuthority7
0x14002e906  xor     r9d, r9d; nSubAuthority1
0x14002e909  mov     [rsp+150h+nSubAuthority6], r13d; nSubAuthority6
0x14002e90e  mov     dl, r15b; nSubAuthorityCount
0x14002e911  mov     [rsp+150h+nSubAuthority5], r13d; nSubAuthority5
0x14002e916  mov     [rsp+150h+nSubAuthority4], r13d; nSubAuthority4
0x14002e91b  mov     [rsp+150h+nSubAuthority3], r13d; nSubAuthority3
0x14002e920  lea     r8d, [r9+4]; nSubAuthority0
0x14002e924  mov     [rsp+150h+nSubAuthority2], r13d; nSubAuthority2
0x14002e929  call    cs:__imp_AllocateAndInitializeSid
0x14002e92f  test    eax, eax
0x14002e931  jz      short loc_14002E988
0x14002e933  mov     rcx, [rbp+50h+var_A8]; pSid
0x14002e937  call    cs:__imp_GetLengthSid
0x14002e93d  mov     edi, eax
0x14002e93f  lea     ecx, [rax+8]
0x14002e942  movzx   r14d, cx
0x14002e946  mov     ecx, r14d; dwBytes
0x14002e949  mov     [rbp+50h+var_C8], r14
0x14002e94d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e952  mov     r15, rax
0x14002e955  test    rax, rax
0x14002e958  jz      short loc_14002E982
0x14002e95a  mov     r8, [rbp+50h+var_A8]; pSourceSid
0x14002e95e  lea     rdx, [rax+8]; pDestinationSid
0x14002e962  mov     ecx, edi; nDestinationSidLength
0x14002e964  call    cs:__imp_CopySid
0x14002e96a  mov     dword ptr [r15+4], 1
0x14002e972  mov     edi, r14d
0x14002e975  mov     word ptr [r15], 300h
0x14002e97b  mov     [r15+2], r14w
0x14002e980  jmp     short loc_14002E995
0x14002e982  mov     rdi, [rbp+50h+var_C8]
0x14002e986  jmp     short loc_14002E992
0x14002e988  mov     edi, r13d
0x14002e98b  mov     r15, r13
0x14002e98e  mov     [rbp+50h+var_C8], rdi
0x14002e992  mov     ebx, r12d
0x14002e995  lea     rax, [rsp+150h+pOwner]
0x14002e99a  mov     [rsp+150h+pOwner], r13
0x14002e99f  mov     [rsp+150h+pSid], rax; pSid
0x14002e9a4  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x14002e9a8  mov     [rsp+150h+nSubAuthority7], r13d; nSubAuthority7
0x14002e9ad  xor     r9d, r9d; nSubAuthority1
0x14002e9b0  mov     [rsp+150h+nSubAuthority6], r13d; nSubAuthority6
0x14002e9b5  mov     dl, 1; nSubAuthorityCount
0x14002e9b7  mov     [rsp+150h+nSubAuthority5], r13d; nSubAuthority5
0x14002e9bc  mov     [rsp+150h+nSubAuthority4], r13d; nSubAuthority4
0x14002e9c1  mov     [rsp+150h+nSubAuthority3], r13d; nSubAuthority3
0x14002e9c6  lea     r8d, [r9+12h]; nSubAuthority0
0x14002e9ca  mov     [rsp+150h+nSubAuthority2], r13d; nSubAuthority2
0x14002e9cf  call    cs:__imp_AllocateAndInitializeSid
0x14002e9d5  test    eax, eax
0x14002e9d7  jz      short loc_14002EA34
0x14002e9d9  mov     rcx, [rsp+150h+pOwner]; pSid
0x14002e9de  call    cs:__imp_GetLengthSid
0x14002e9e4  mov     r13d, eax
0x14002e9e7  lea     ecx, [rax+8]
0x14002e9ea  movzx   r14d, cx
0x14002e9ee  mov     ecx, r14d; dwBytes
0x14002e9f1  mov     [rbp+50h+var_C0], r14
0x14002e9f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e9fa  mov     r12, rax
0x14002e9fd  test    rax, rax
0x14002ea00  jz      short loc_14002EA2F
0x14002ea02  mov     r8, [rsp+150h+pOwner]; pSourceSid
0x14002ea07  lea     rdx, [rax+8]; pDestinationSid
0x14002ea0b  mov     ecx, r13d; nDestinationSidLength
0x14002ea0e  call    cs:__imp_CopySid
0x14002ea14  xor     r13d, r13d
0x14002ea17  mov     dword ptr [r12+4], 1
0x14002ea20  mov     word ptr [r12], 300h
0x14002ea27  mov     [r12+2], r14w
0x14002ea2d  jmp     short loc_14002EA41
0x14002ea2f  xor     r13d, r13d
0x14002ea32  jmp     short loc_14002EA3C
0x14002ea34  mov     r12, r13
0x14002ea37  mov     word ptr [rbp+50h+var_C0], r13w
0x14002ea3c  mov     ebx, 8007000Eh
0x14002ea41  lea     rax, [rbp+50h+var_A0]
0x14002ea45  mov     [rbp+50h+var_A0], r13
0x14002ea49  mov     [rsp+150h+pSid], rax; pSid
0x14002ea4e  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x14002ea52  mov     [rsp+150h+nSubAuthority7], r13d; nSubAuthority7
0x14002ea57  xor     r9d, r9d; nSubAuthority1
0x14002ea5a  mov     [rsp+150h+nSubAuthority6], r13d; nSubAuthority6
0x14002ea5f  mov     dl, 1; nSubAuthorityCount
0x14002ea61  mov     [rsp+150h+nSubAuthority5], r13d; nSubAuthority5
0x14002ea66  mov     [rsp+150h+nSubAuthority4], r13d; nSubAuthority4
0x14002ea6b  mov     [rsp+150h+nSubAuthority3], r13d; nSubAuthority3
0x14002ea70  lea     r8d, [r9+13h]; nSubAuthority0
0x14002ea74  mov     [rsp+150h+nSubAuthority2], r13d; nSubAuthority2
0x14002ea79  call    cs:__imp_AllocateAndInitializeSid
0x14002ea7f  test    eax, eax
0x14002ea81  jz      short loc_14002EADC
0x14002ea83  mov     rcx, [rbp+50h+var_A0]; pSid
0x14002ea87  call    cs:__imp_GetLengthSid
0x14002ea8d  mov     [rsp+150h+nDestinationSidLength], eax
0x14002ea91  lea     ecx, [rax+8]
0x14002ea94  movzx   r14d, cx
0x14002ea98  mov     ecx, r14d; dwBytes
0x14002ea9b  mov     [rbp+50h+var_B8], r14
0x14002ea9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002eaa4  mov     r13, rax
0x14002eaa7  test    rax, rax
0x14002eaaa  jz      short loc_14002EAD7
0x14002eaac  mov     r8, [rbp+50h+var_A0]; pSourceSid
0x14002eab0  lea     rdx, [rax+8]; pDestinationSid
0x14002eab4  mov     ecx, [rsp+150h+nDestinationSidLength]; nDestinationSidLength
0x14002eab8  call    cs:__imp_CopySid
0x14002eabe  mov     [r13+2], r14w
0x14002eac3  xor     r14d, r14d
0x14002eac6  mov     dword ptr [r13+4], 1
0x14002eace  mov     word ptr [r13+0], 300h
0x14002ead5  jmp     short loc_14002EAE9
0x14002ead7  xor     r14d, r14d
0x14002eada  jmp     short loc_14002EAE4
0x14002eadc  xor     r14d, r14d
0x14002eadf  mov     word ptr [rbp+50h+var_B8], r14w
0x14002eae4  mov     ebx, 8007000Eh
0x14002eae9  lea     rax, [rbp+50h+var_98]
0x14002eaed  mov     [rbp+50h+var_98], r14
0x14002eaf1  mov     [rsp+150h+pSid], rax; pSid
0x14002eaf6  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x14002eafa  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x14002eaff  xor     r9d, r9d; nSubAuthority1
0x14002eb02  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x14002eb07  mov     dl, 1; nSubAuthorityCount
0x14002eb09  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x14002eb0e  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x14002eb13  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x14002eb18  lea     r8d, [r9+14h]; nSubAuthority0
0x14002eb1c  mov     [rsp+150h+nSubAuthority2], r14d; nSubAuthority2
0x14002eb21  call    cs:__imp_AllocateAndInitializeSid
0x14002eb27  test    eax, eax
0x14002eb29  jz      short loc_14002EB7F
0x14002eb2b  mov     rcx, [rbp+50h+var_98]; pSid
0x14002eb2f  call    cs:__imp_GetLengthSid
0x14002eb35  mov     [rsp+150h+nDestinationSidLength], eax
0x14002eb39  lea     ecx, [rax+8]
0x14002eb3c  movzx   eax, cx
0x14002eb3f  mov     ecx, eax; dwBytes
0x14002eb41  mov     [rsp+150h+var_E0], rax
0x14002eb46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002eb4b  mov     r14, rax
0x14002eb4e  test    rax, rax
0x14002eb51  jz      short loc_14002EB86
0x14002eb53  mov     r8, [rbp+50h+var_98]; pSourceSid
0x14002eb57  lea     rdx, [rax+8]; pDestinationSid
0x14002eb5b  mov     ecx, [rsp+150h+nDestinationSidLength]; nDestinationSidLength
0x14002eb5f  call    cs:__imp_CopySid
0x14002eb65  mov     rax, [rsp+150h+var_E0]
0x14002eb6a  mov     [r14+2], ax
0x14002eb6f  mov     dword ptr [r14+4], 1
0x14002eb77  mov     word ptr [r14], 300h
0x14002eb7d  jmp     short loc_14002EB90
0x14002eb7f  xor     eax, eax
0x14002eb81  mov     word ptr [rsp+150h+var_E0], ax
0x14002eb86  mov     rax, [rsp+150h+var_E0]
0x14002eb8b  mov     ebx, 8007000Eh
0x14002eb90  movzx   r8d, word ptr [rbp+50h+var_B8]
0x14002eb95  movzx   r9d, word ptr [rbp+50h+var_B0]
0x14002eb9a  movzx   edx, word ptr [rbp+50h+var_C0]
0x14002eb9e  movzx   eax, ax
0x14002eba1  movzx   ecx, di
0x14002eba4  mov     [rbp+50h+nAceListLength], eax
0x14002eba7  lea     edi, [r9+8]
0x14002ebab  add     eax, r8d
0x14002ebae  mov     [rsp+150h+nDestinationSidLength], ecx
0x14002ebb2  add     eax, edx
0x14002ebb4  add     eax, ecx
0x14002ebb6  add     edi, eax
0x14002ebb8  mov     ecx, edi; dwBytes
0x14002ebba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ebbf  mov     [rsp+150h+pAcl], rax
0x14002ebc4  test    rax, rax
0x14002ebc7  jz      loc_14002EDBF
0x14002ebcd  mov     r8d, 2; dwAclRevision
0x14002ebd3  mov     edx, edi; nAclLength
0x14002ebd5  mov     rcx, rax; pAcl
0x14002ebd8  call    cs:__imp_InitializeAcl
0x14002ebde  xor     edi, edi
0x14002ebe0  test    eax, eax
0x14002ebe2  jz      loc_14002EDB3
0x14002ebe8  xor     eax, eax
0x14002ebea  cmp     word ptr [rbp+50h+var_C8], ax
0x14002ebee  jz      short loc_14002EC16
0x14002ebf0  mov     eax, [rsp+150h+nDestinationSidLength]
0x14002ebf4  lea     edx, [rdi+2]; dwAceRevision
0x14002ebf7  mov     rcx, [rsp+150h+pAcl]; pAcl
0x14002ebfc  mov     r9, r15; pAceList
0x14002ebff  xor     r8d, r8d; dwStartingAceIndex
0x14002ec02  mov     [rsp+150h+nSubAuthority2], eax; nAceListLength
0x14002ec06  call    cs:__imp_AddAce
0x14002ec0c  test    eax, eax
0x14002ec0e  lea     eax, [rdi+1]
0x14002ec11  cmovnz  edi, eax
0x14002ec14  xor     eax, eax
0x14002ec16  cmp     word ptr [rbp+50h+var_C0], ax
0x14002ec1a  jz      short loc_14002EC42
0x14002ec1c  movzx   eax, word ptr [rbp+50h+var_C0]
0x14002ec20  mov     r9, r12; pAceList
0x14002ec23  mov     rcx, [rsp+150h+pAcl]; pAcl
0x14002ec28  mov     r8d, edi; dwStartingAceIndex
0x14002ec2b  mov     edx, 2; dwAceRevision
0x14002ec30  mov     [rsp+150h+nSubAuthority2], eax; nAceListLength
0x14002ec34  call    cs:__imp_AddAce
0x14002ec3a  test    eax, eax
0x14002ec3c  jz      short loc_14002EC40
0x14002ec3e  inc     edi
0x14002ec40  xor     eax, eax
0x14002ec42  cmp     word ptr [rbp+50h+var_B8], ax
0x14002ec46  jz      short loc_14002EC6E
0x14002ec48  movzx   eax, word ptr [rbp+50h+var_B8]
0x14002ec4c  mov     r9, r13; pAceList
0x14002ec4f  mov     rcx, [rsp+150h+pAcl]; pAcl
0x14002ec54  mov     r8d, edi; dwStartingAceIndex
0x14002ec57  mov     edx, 2; dwAceRevision
0x14002ec5c  mov     [rsp+150h+nSubAuthority2], eax; nAceListLength
0x14002ec60  call    cs:__imp_AddAce
0x14002ec66  test    eax, eax
0x14002ec68  jz      short loc_14002EC6C
0x14002ec6a  inc     edi
0x14002ec6c  xor     eax, eax
0x14002ec6e  cmp     word ptr [rsp+150h+var_E0], ax
0x14002ec73  jz      short loc_14002EC9A
0x14002ec75  mov     eax, [rbp+50h+nAceListLength]
0x14002ec78  mov     r9, r14; pAceList
0x14002ec7b  mov     rcx, [rsp+150h+pAcl]; pAcl
0x14002ec80  mov     r8d, edi; dwStartingAceIndex
0x14002ec83  mov     edx, 2; dwAceRevision
0x14002ec88  mov     [rsp+150h+nSubAuthority2], eax; nAceListLength
0x14002ec8c  call    cs:__imp_AddAce
0x14002ec92  test    eax, eax
0x14002ec94  jz      short loc_14002EC98
0x14002ec96  inc     edi
0x14002ec98  xor     eax, eax
0x14002ec9a  cmp     word ptr [rbp+50h+var_B0], ax
  ... truncated ...
```
