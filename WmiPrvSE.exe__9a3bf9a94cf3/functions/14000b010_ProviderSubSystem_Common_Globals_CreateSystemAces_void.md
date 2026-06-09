# ProviderSubSystem_Common_Globals::CreateSystemAces(void)

- ea: `0x14000b010`
- end: `0x14000b418`
- name: `?CreateSystemAces@ProviderSubSystem_Common_Globals@@SAJXZ`
- size: `1032`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x14000a530`
- `0x14000b010`
- `0x140046430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b08a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b167`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b244`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b324`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b08a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b167`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b244`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000b324`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b078`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b155`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b232`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b312`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b078`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b155`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b232`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000b312`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b0be`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b103`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b19b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b1e0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b278`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b2bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b354`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b397`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b0be`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b103`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b19b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b1e0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b278`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b2bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b354`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000b397`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3da`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3e9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3f8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3da`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3e9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000b3f8`

## pseudocode

```c
__int64 ProviderSubSystem_Common_Globals::CreateSystemAces(void)
{
  DWORD LengthSid; // ebx
  char *v1; // rax
  _WORD *v2; // rcx
  unsigned int v3; // eax
  char *v4; // rax
  _DWORD *v5; // rcx
  DWORD v6; // ebx
  char *v7; // rax
  _WORD *v8; // rcx
  unsigned int v9; // eax
  char *v10; // rax
  _DWORD *v11; // rcx
  DWORD v12; // ebx
  char *v13; // rax
  _WORD *v14; // rcx
  unsigned int v15; // eax
  char *v16; // rax
  _DWORD *v17; // rcx
  DWORD v18; // edi
  char *v19; // rax
  _WORD *v20; // rcx
  unsigned int v21; // eax
  char *v22; // rax
  unsigned int v23; // ebx
  _WORD *v24; // rcx
  unsigned __int16 v25; // ax
  PSID v27; // [rsp+60h] [rbp+7h] BYREF
  PSID pSourceSid; // [rsp+68h] [rbp+Fh] BYREF
  PSID pSid; // [rsp+70h] [rbp+17h] BYREF
  PSID v30; // [rsp+78h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSourceSid = 0;
  pSid = 0;
  v30 = 0;
  v27 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSourceSid) )
    goto LABEL_14;
  LengthSid = GetLengthSid(pSourceSid);
  ProviderSubSystem_Common_Globals::s_System_ACESize = LengthSid + 8;
  v1 = (char *)operator new((unsigned __int16)(LengthSid + 8));
  ProviderSubSystem_Common_Globals::s_Provider_System_ACE = v1;
  if ( !v1 )
    goto LABEL_14;
  CopySid(LengthSid, v1 + 8, pSourceSid);
  v2 = ProviderSubSystem_Common_Globals::s_Provider_System_ACE;
  v3 = ProviderSubSystem_Common_Globals::s_System_ACESize;
  *((_DWORD *)ProviderSubSystem_Common_Globals::s_Provider_System_ACE + 1) = 1;
  *v2 = 768;
  v2[1] = v3;
  v4 = (char *)operator new(v3);
  ProviderSubSystem_Common_Globals::s_Token_All_Access_System_ACE = v4;
  if ( !v4 )
    goto LABEL_14;
  CopySid(LengthSid, v4 + 8, pSourceSid);
  v5 = ProviderSubSystem_Common_Globals::s_Token_All_Access_System_ACE;
  *((_WORD *)ProviderSubSystem_Common_Globals::s_Token_All_Access_System_ACE + 1) = ProviderSubSystem_Common_Globals::s_System_ACESize;
  v5[1] = 983551;
  *(_WORD *)v5 = 768;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_14;
  v6 = GetLengthSid(pSid);
  ProviderSubSystem_Common_Globals::s_LocalService_ACESize = v6 + 8;
  v7 = (char *)operator new((unsigned __int16)(v6 + 8));
  ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE = v7;
  if ( !v7 )
    goto LABEL_14;
  CopySid(v6, v7 + 8, pSid);
  v8 = ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE;
  v9 = ProviderSubSystem_Common_Globals::s_LocalService_ACESize;
  *((_DWORD *)ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE + 1) = 1;
  *v8 = 768;
  v8[1] = v9;
  v10 = (char *)operator new(v9);
  ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalService_ACE = v10;
  if ( !v10 )
    goto LABEL_14;
  CopySid(v6, v10 + 8, pSid);
  v11 = ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalService_ACE;
  *((_WORD *)ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalService_ACE + 1) = ProviderSubSystem_Common_Globals::s_LocalService_ACESize;
  v11[1] = 983551;
  *(_WORD *)v11 = 768;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v30) )
    goto LABEL_14;
  v12 = GetLengthSid(v30);
  ProviderSubSystem_Common_Globals::s_NetworkService_ACESize = v12 + 8;
  v13 = (char *)operator new((unsigned __int16)(v12 + 8));
  ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE = v13;
  if ( !v13 )
    goto LABEL_14;
  CopySid(v12, v13 + 8, v30);
  v14 = ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE;
  v15 = ProviderSubSystem_Common_Globals::s_NetworkService_ACESize;
  *((_DWORD *)ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE + 1) = 1;
  *v14 = 768;
  v14[1] = v15;
  v16 = (char *)operator new(v15);
  ProviderSubSystem_Common_Globals::s_Token_All_Access_NetworkService_ACE = v16;
  if ( !v16 )
    goto LABEL_14;
  CopySid(v12, v16 + 8, v30);
  v17 = ProviderSubSystem_Common_Globals::s_Token_All_Access_NetworkService_ACE;
  *((_WORD *)ProviderSubSystem_Common_Globals::s_Token_All_Access_NetworkService_ACE + 1) = ProviderSubSystem_Common_Globals::s_NetworkService_ACESize;
  v17[1] = 983551;
  *(_WORD *)v17 = 768;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v27) )
    goto LABEL_14;
  v18 = GetLengthSid(v27);
  ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize = v18 + 8;
  v19 = (char *)operator new((unsigned __int16)(v18 + 8));
  ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE = v19;
  if ( !v19 )
    goto LABEL_14;
  CopySid(v18, v19 + 8, v27);
  v20 = ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE;
  v21 = ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize;
  *((_DWORD *)ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE + 1) = 1;
  *v20 = 768;
  v20[1] = v21;
  v22 = (char *)operator new(v21);
  ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalAdmins_ACE = v22;
  if ( v22 )
  {
    v23 = 0;
    CopySid(v18, v22 + 8, v27);
    v24 = ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalAdmins_ACE;
    v25 = ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize;
    *((_DWORD *)ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalAdmins_ACE + 1) = 983551;
    *v24 = 768;
    v24[1] = v25;
  }
  else
  {
LABEL_14:
    v23 = -2147024882;
  }
  if ( v27 )
    FreeSid(v27);
  if ( pSourceSid )
    FreeSid(pSourceSid);
  if ( pSid )
    FreeSid(pSid);
  if ( v30 )
    FreeSid(v30);
  return v23;
}

```

## disassembly

```asm
0x14000b010  push    rbp
0x14000b012  push    rbx
0x14000b013  push    rsi
0x14000b014  push    rdi
0x14000b015  lea     rbp, [rsp-3Fh]
0x14000b01a  sub     rsp, 98h
0x14000b021  mov     rax, cs:__security_cookie
0x14000b028  xor     rax, rsp
0x14000b02b  mov     [rbp+57h+var_28], rax
0x14000b02f  xor     esi, esi
0x14000b031  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14000b037  lea     rax, [rbp+57h+pSourceSid]
0x14000b03b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x14000b03e  mov     [rsp+0B0h+pSid], rax; pSid
0x14000b043  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000b047  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000b04b  xor     r9d, r9d; nSubAuthority1
0x14000b04e  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x14000b052  lea     r8d, [rsi+12h]; nSubAuthority0
0x14000b056  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x14000b05a  mov     dl, 1; nSubAuthorityCount
0x14000b05c  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x14000b060  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000b064  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000b068  mov     [rbp+57h+pSourceSid], rsi
0x14000b06c  mov     [rbp+57h+var_40], rsi
0x14000b070  mov     [rbp+57h+var_38], rsi
0x14000b074  mov     [rbp+57h+var_50], rsi
0x14000b078  call    cs:__imp_AllocateAndInitializeSid
0x14000b07e  test    eax, eax
0x14000b080  jz      loc_14000B3BD
0x14000b086  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x14000b08a  call    cs:__imp_GetLengthSid
0x14000b090  mov     ebx, eax
0x14000b092  lea     ecx, [rax+8]
0x14000b095  movzx   ecx, cx; dwBytes
0x14000b098  mov     cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA, cx; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x14000b09f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b0a4  mov     cs:?s_Provider_System_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_System_ACE
0x14000b0ab  test    rax, rax
0x14000b0ae  jz      loc_14000B3BD
0x14000b0b4  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x14000b0b8  lea     rdx, [rax+8]; pDestinationSid
0x14000b0bc  mov     ecx, ebx; nDestinationSidLength
0x14000b0be  call    cs:__imp_CopySid
0x14000b0c4  mov     rcx, cs:?s_Provider_System_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_System_ACE
0x14000b0cb  movzx   eax, cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x14000b0d2  mov     dword ptr [rcx+4], 1
0x14000b0d9  mov     word ptr [rcx], 300h
0x14000b0de  mov     [rcx+2], ax
0x14000b0e2  mov     ecx, eax; dwBytes
0x14000b0e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b0e9  mov     cs:?s_Token_All_Access_System_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_System_ACE
0x14000b0f0  test    rax, rax
0x14000b0f3  jz      loc_14000B3BD
0x14000b0f9  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x14000b0fd  lea     rdx, [rax+8]; pDestinationSid
0x14000b101  mov     ecx, ebx; nDestinationSidLength
0x14000b103  call    cs:__imp_CopySid
0x14000b109  mov     rcx, cs:?s_Token_All_Access_System_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_System_ACE
0x14000b110  lea     r8d, [rsi+13h]; nSubAuthority0
0x14000b114  movzx   eax, cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x14000b11b  xor     r9d, r9d; nSubAuthority1
0x14000b11e  mov     dl, 1; nSubAuthorityCount
0x14000b120  mov     [rcx+2], ax
0x14000b124  lea     rax, [rbp+57h+var_40]
0x14000b128  mov     [rsp+0B0h+pSid], rax; pSid
0x14000b12d  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000b131  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x14000b135  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x14000b139  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x14000b13d  mov     dword ptr [rcx+4], 0F01FFh
0x14000b144  mov     word ptr [rcx], 300h
0x14000b149  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000b14d  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000b151  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000b155  call    cs:__imp_AllocateAndInitializeSid
0x14000b15b  test    eax, eax
0x14000b15d  jz      loc_14000B3BD
0x14000b163  mov     rcx, [rbp+57h+var_40]; pSid
0x14000b167  call    cs:__imp_GetLengthSid
0x14000b16d  mov     ebx, eax
0x14000b16f  lea     ecx, [rax+8]
0x14000b172  movzx   ecx, cx; dwBytes
0x14000b175  mov     cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA, cx; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x14000b17c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b181  mov     cs:?s_Provider_LocalService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE
0x14000b188  test    rax, rax
0x14000b18b  jz      loc_14000B3BD
0x14000b191  mov     r8, [rbp+57h+var_40]; pSourceSid
0x14000b195  lea     rdx, [rax+8]; pDestinationSid
0x14000b199  mov     ecx, ebx; nDestinationSidLength
0x14000b19b  call    cs:__imp_CopySid
0x14000b1a1  mov     rcx, cs:?s_Provider_LocalService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE
0x14000b1a8  movzx   eax, cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x14000b1af  mov     dword ptr [rcx+4], 1
0x14000b1b6  mov     word ptr [rcx], 300h
0x14000b1bb  mov     [rcx+2], ax
0x14000b1bf  mov     ecx, eax; dwBytes
0x14000b1c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b1c6  mov     cs:?s_Token_All_Access_LocalService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalService_ACE
0x14000b1cd  test    rax, rax
0x14000b1d0  jz      loc_14000B3BD
0x14000b1d6  mov     r8, [rbp+57h+var_40]; pSourceSid
0x14000b1da  lea     rdx, [rax+8]; pDestinationSid
0x14000b1de  mov     ecx, ebx; nDestinationSidLength
0x14000b1e0  call    cs:__imp_CopySid
0x14000b1e6  mov     rcx, cs:?s_Token_All_Access_LocalService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalService_ACE
0x14000b1ed  lea     r8d, [rsi+14h]; nSubAuthority0
0x14000b1f1  movzx   eax, cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x14000b1f8  xor     r9d, r9d; nSubAuthority1
0x14000b1fb  mov     dl, 1; nSubAuthorityCount
0x14000b1fd  mov     [rcx+2], ax
0x14000b201  lea     rax, [rbp+57h+var_38]
0x14000b205  mov     [rsp+0B0h+pSid], rax; pSid
0x14000b20a  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000b20e  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x14000b212  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x14000b216  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x14000b21a  mov     dword ptr [rcx+4], 0F01FFh
0x14000b221  mov     word ptr [rcx], 300h
0x14000b226  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000b22a  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000b22e  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000b232  call    cs:__imp_AllocateAndInitializeSid
0x14000b238  test    eax, eax
0x14000b23a  jz      loc_14000B3BD
0x14000b240  mov     rcx, [rbp+57h+var_38]; pSid
0x14000b244  call    cs:__imp_GetLengthSid
0x14000b24a  mov     ebx, eax
0x14000b24c  lea     ecx, [rax+8]
0x14000b24f  movzx   ecx, cx; dwBytes
0x14000b252  mov     cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA, cx; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x14000b259  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b25e  mov     cs:?s_Provider_NetworkService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE
0x14000b265  test    rax, rax
0x14000b268  jz      loc_14000B3BD
0x14000b26e  mov     r8, [rbp+57h+var_38]; pSourceSid
0x14000b272  lea     rdx, [rax+8]; pDestinationSid
0x14000b276  mov     ecx, ebx; nDestinationSidLength
0x14000b278  call    cs:__imp_CopySid
0x14000b27e  mov     rcx, cs:?s_Provider_NetworkService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE
0x14000b285  movzx   eax, cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x14000b28c  mov     dword ptr [rcx+4], 1
0x14000b293  mov     word ptr [rcx], 300h
0x14000b298  mov     [rcx+2], ax
0x14000b29c  mov     ecx, eax; dwBytes
0x14000b29e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b2a3  mov     cs:?s_Token_All_Access_NetworkService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_NetworkService_ACE
0x14000b2aa  test    rax, rax
0x14000b2ad  jz      loc_14000B3BD
0x14000b2b3  mov     r8, [rbp+57h+var_38]; pSourceSid
0x14000b2b7  lea     rdx, [rax+8]; pDestinationSid
0x14000b2bb  mov     ecx, ebx; nDestinationSidLength
0x14000b2bd  call    cs:__imp_CopySid
0x14000b2c3  mov     rcx, cs:?s_Token_All_Access_NetworkService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_NetworkService_ACE
0x14000b2ca  lea     r8d, [rsi+20h]; nSubAuthority0
0x14000b2ce  movzx   eax, cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x14000b2d5  mov     r9d, 220h; nSubAuthority1
0x14000b2db  mov     dl, 2; nSubAuthorityCount
0x14000b2dd  mov     [rcx+2], ax
0x14000b2e1  lea     rax, [rbp+57h+var_50]
0x14000b2e5  mov     [rsp+0B0h+pSid], rax; pSid
0x14000b2ea  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000b2ee  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x14000b2f2  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x14000b2f6  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x14000b2fa  mov     dword ptr [rcx+4], 0F01FFh
0x14000b301  mov     word ptr [rcx], 300h
0x14000b306  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000b30a  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000b30e  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000b312  call    cs:__imp_AllocateAndInitializeSid
0x14000b318  test    eax, eax
0x14000b31a  jz      loc_14000B3BD
0x14000b320  mov     rcx, [rbp+57h+var_50]; pSid
0x14000b324  call    cs:__imp_GetLengthSid
0x14000b32a  mov     edi, eax
0x14000b32c  lea     ecx, [rax+8]
0x14000b32f  movzx   ecx, cx; dwBytes
0x14000b332  mov     cs:?s_LocalAdmins_ACESize@ProviderSubSystem_Common_Globals@@2GA, cx; ushort ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
0x14000b339  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b33e  mov     cs:?s_Provider_LocalAdmins_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE
0x14000b345  test    rax, rax
0x14000b348  jz      short loc_14000B3BD
0x14000b34a  mov     r8, [rbp+57h+var_50]; pSourceSid
0x14000b34e  lea     rdx, [rax+8]; pDestinationSid
0x14000b352  mov     ecx, edi; nDestinationSidLength
0x14000b354  call    cs:__imp_CopySid
0x14000b35a  mov     rcx, cs:?s_Provider_LocalAdmins_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE
0x14000b361  movzx   eax, cs:?s_LocalAdmins_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
0x14000b368  mov     dword ptr [rcx+4], 1
0x14000b36f  mov     word ptr [rcx], 300h
0x14000b374  mov     [rcx+2], ax
0x14000b378  mov     ecx, eax; dwBytes
0x14000b37a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b37f  mov     cs:?s_Token_All_Access_LocalAdmins_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA, rax; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalAdmins_ACE
0x14000b386  test    rax, rax
0x14000b389  jz      short loc_14000B3BD
0x14000b38b  mov     r8, [rbp+57h+var_50]; pSourceSid
0x14000b38f  lea     rdx, [rax+8]; pDestinationSid
0x14000b393  mov     ecx, edi; nDestinationSidLength
0x14000b395  mov     ebx, esi
0x14000b397  call    cs:__imp_CopySid
0x14000b39d  mov     rcx, cs:?s_Token_All_Access_LocalAdmins_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; _ACCESS_ALLOWED_ACE * ProviderSubSystem_Common_Globals::s_Token_All_Access_LocalAdmins_ACE
0x14000b3a4  movzx   eax, cs:?s_LocalAdmins_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
0x14000b3ab  mov     dword ptr [rcx+4], 0F01FFh
0x14000b3b2  mov     word ptr [rcx], 300h
0x14000b3b7  mov     [rcx+2], ax
0x14000b3bb  jmp     short loc_14000B3C2
0x14000b3bd  mov     ebx, 8007000Eh
0x14000b3c2  mov     rcx, [rbp+57h+var_50]; pSid
0x14000b3c6  test    rcx, rcx
0x14000b3c9  jz      short loc_14000B3D1
0x14000b3cb  call    cs:__imp_FreeSid
0x14000b3d1  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x14000b3d5  test    rcx, rcx
0x14000b3d8  jz      short loc_14000B3E0
0x14000b3da  call    cs:__imp_FreeSid
0x14000b3e0  mov     rcx, [rbp+57h+var_40]; pSid
0x14000b3e4  test    rcx, rcx
0x14000b3e7  jz      short loc_14000B3EF
0x14000b3e9  call    cs:__imp_FreeSid
0x14000b3ef  mov     rcx, [rbp+57h+var_38]; pSid
0x14000b3f3  test    rcx, rcx
0x14000b3f6  jz      short loc_14000B3FE
0x14000b3f8  call    cs:__imp_FreeSid
0x14000b3fe  mov     eax, ebx
0x14000b400  mov     rcx, [rbp+57h+var_28]
0x14000b404  xor     rcx, rsp; StackCookie
0x14000b407  call    __security_check_cookie
0x14000b40c  add     rsp, 98h
0x14000b413  pop     rdi
0x14000b414  pop     rsi
0x14000b415  pop     rbx
0x14000b416  pop     rbp
0x14000b417  retn
```
