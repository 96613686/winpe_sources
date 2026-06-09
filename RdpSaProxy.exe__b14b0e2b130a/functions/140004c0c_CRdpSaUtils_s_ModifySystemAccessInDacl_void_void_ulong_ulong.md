# CRdpSaUtils::s_ModifySystemAccessInDacl(void *,void *,ulong,ulong *)

- ea: `0x140004c0c`
- end: `0x140005052`
- name: `?s_ModifySystemAccessInDacl@CRdpSaUtils@@SAJPEAX0KPEAK@Z`
- size: `1094`
- prototype: `__int64 __fastcall(HANDLE handle, void *, DWORD, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002944`
- `0x140004240`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140004c0c`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x140004e7f`
- `ADVAPI32!EqualSid` at `0x140004e7f`
- `ADVAPI32!CreateWellKnownSid` at `0x140004cb4`
- `ADVAPI32!CreateWellKnownSid` at `0x140004cb4`
- `ADVAPI32!SetSecurityInfo` at `0x140004fd2`
- `ADVAPI32!SetSecurityInfo` at `0x140004fd2`
- `ADVAPI32!AddAce` at `0x140004eab`
- `ADVAPI32!AddAce` at `0x140004eab`
- `ADVAPI32!GetAce` at `0x140004e60`
- `ADVAPI32!GetAce` at `0x140004e60`
- `ADVAPI32!InitializeAcl` at `0x140004e00`
- `ADVAPI32!InitializeAcl` at `0x140004e00`
- `ADVAPI32!GetLengthSid` at `0x140004d9e`
- `ADVAPI32!GetLengthSid` at `0x140004d9e`
- `ADVAPI32!GetSecurityInfo` at `0x140004d53`
- `ADVAPI32!GetSecurityInfo` at `0x140004d53`
- `ADVAPI32!AddAccessAllowedAce` at `0x140004ed9`
- `ADVAPI32!AddAccessAllowedAce` at `0x140004ed9`
- `KERNEL32!LocalFree` at `0x140005027`
- `KERNEL32!LocalFree` at `0x140005030`
- `KERNEL32!LocalFree` at `0x140005039`
- `KERNEL32!LocalFree` at `0x140005027`
- `KERNEL32!LocalFree` at `0x140005030`
- `KERNEL32!LocalFree` at `0x140005039`
- `KERNEL32!LocalAlloc` at `0x140004c47`
- `KERNEL32!LocalAlloc` at `0x140004dad`
- `KERNEL32!LocalAlloc` at `0x140004c47`
- `KERNEL32!LocalAlloc` at `0x140004dad`
- `KERNEL32!GetLastError` at `0x140004cbe`
- `KERNEL32!GetLastError` at `0x140004d5d`
- `KERNEL32!GetLastError` at `0x140004e0a`
- `KERNEL32!GetLastError` at `0x140004ee7`
- `KERNEL32!GetLastError` at `0x140004f29`
- `KERNEL32!GetLastError` at `0x140004f6b`
- `KERNEL32!GetLastError` at `0x140004fdc`
- `KERNEL32!GetLastError` at `0x140004cbe`
- `KERNEL32!GetLastError` at `0x140004d5d`
- `KERNEL32!GetLastError` at `0x140004e0a`
- `KERNEL32!GetLastError` at `0x140004ee7`
- `KERNEL32!GetLastError` at `0x140004f29`
- `KERNEL32!GetLastError` at `0x140004f6b`
- `KERNEL32!GetLastError` at `0x140004fdc`

## pseudocode

```c
__int64 __fastcall CRdpSaUtils::s_ModifySystemAccessInDacl(HANDLE handle, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // edi
  struct _ACL *v8; // r12
  HLOCAL v9; // rax
  void *v10; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v12; // rdx
  signed int LastError; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int AclSize; // ebx
  DWORD v17; // ebx
  struct _ACL *v18; // rax
  struct _ACL *v19; // rcx
  DWORD v20; // ebx
  unsigned __int16 *v21; // r9
  LPVOID pAce; // [rsp+40h] [rbp-28h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-18h] BYREF
  DWORD cbSid; // [rsp+B8h] [rbp+50h] BYREF
  int v27; // [rsp+BCh] [rbp+54h]

  v27 = HIDWORD(a2);
  v4 = 0;
  pAcl = 0;
  hMem = 0;
  pAce = 0;
  v8 = 0;
  cbSid = 68;
  v9 = LocalAlloc(0x40u, 0x44u);
  v10 = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 25;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024882);
LABEL_7:
    LastError = -2147024882;
    goto LABEL_62;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v9, &cbSid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 26;
    goto LABEL_13;
  }
  if ( GetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 27;
    goto LABEL_13;
  }
  AclSize = pAcl->AclSize;
  v17 = GetLengthSid(v10) + AclSize + 8;
  v18 = (struct _ACL *)LocalAlloc(0, v17);
  v8 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 28;
    goto LABEL_6;
  }
  if ( !InitializeAcl(v18, v17, 2u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 29;
    goto LABEL_13;
  }
  v19 = pAcl;
  v20 = 0;
  if ( !pAcl->AceCount )
  {
LABEL_42:
    if ( !a3 || AddAccessAllowedAce(v8, 2u, a3, v10) )
    {
      if ( !SetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, v8, 0) )
      {
        LastError = 0;
        *a4 = v4;
        goto LABEL_62;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 33;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 32;
    }
LABEL_13:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids, v14, LastError);
    goto LABEL_14;
  }
  while ( GetAce(v19, v20, &pAce) )
  {
    v21 = (unsigned __int16 *)pAce;
    if ( !*(_BYTE *)pAce )
    {
      if ( EqualSid(v10, (char *)pAce + 8) )
      {
        v4 = *((_DWORD *)pAce + 1);
        goto LABEL_41;
      }
      v21 = (unsigned __int16 *)pAce;
    }
    if ( !AddAce(v8, 2u, 0xFFFFFFFF, v21, v21[1]) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 31;
        goto LABEL_13;
      }
      goto LABEL_14;
    }
LABEL_41:
    v19 = pAcl;
    if ( ++v20 >= pAcl->AceCount )
      goto LABEL_42;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 30;
    goto LABEL_13;
  }
LABEL_14:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
LABEL_62:
  LocalFree(hMem);
  LocalFree(v8);
  LocalFree(v10);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140004c0c  mov     qword ptr [rsp-40h+cbSid], rdx
0x140004c11  push    rbp
0x140004c12  push    rbx
0x140004c13  push    rsi
0x140004c14  push    rdi
0x140004c15  push    r12
0x140004c17  push    r13
0x140004c19  push    r14
0x140004c1b  push    r15
0x140004c1d  mov     rbp, rsp
0x140004c20  sub     rsp, 68h
0x140004c24  xor     edi, edi
0x140004c26  mov     r14, rcx
0x140004c29  mov     r15, r9
0x140004c2c  mov     [rbp+pAcl], rdi
0x140004c30  mov     esi, r8d
0x140004c33  mov     [rbp+hMem], rdi
0x140004c37  mov     [rbp+pAce], rdi
0x140004c3b  mov     r12d, edi
0x140004c3e  lea     edx, [rdi+44h]; uBytes
0x140004c41  lea     ecx, [rdi+40h]; uFlags
0x140004c44  mov     [rbp+cbSid], edx
0x140004c47  call    cs:__imp_LocalAlloc
0x140004c4d  mov     r13, rax
0x140004c50  test    rax, rax
0x140004c53  jnz     short loc_140004CA8
0x140004c55  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c5c  lea     rax, WPP_GLOBAL_Control
0x140004c63  cmp     rcx, rax
0x140004c66  jz      short loc_140004C9E
0x140004c68  test    byte ptr [rcx+1Ch], 8
0x140004c6c  jz      short loc_140004C9E
0x140004c6e  cmp     byte ptr [rcx+19h], 2
0x140004c72  jb      short loc_140004C9E
0x140004c74  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004c79  lea     edx, [rdi+19h]
0x140004c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c83  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x140004c8a  mov     r9d, eax
0x140004c8d  mov     dword ptr [rsp+68h+ppsidGroup], 8007000Eh
0x140004c95  mov     rcx, [rcx+10h]
0x140004c99  call    WPP_SF_Dd
0x140004c9e  mov     ebx, 8007000Eh
0x140004ca3  jmp     loc_140005023
0x140004ca8  xor     edx, edx; DomainSid
0x140004caa  lea     r9, [rbp+cbSid]; cbSid
0x140004cae  mov     r8, r13; pSid
0x140004cb1  lea     ecx, [rdx+16h]; WellKnownSidType
0x140004cb4  call    cs:__imp_CreateWellKnownSid
0x140004cba  test    eax, eax
0x140004cbc  jnz     short loc_140004D29
0x140004cbe  call    cs:__imp_GetLastError
0x140004cc4  mov     ebx, eax
0x140004cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ccd  lea     rax, WPP_GLOBAL_Control
0x140004cd4  cmp     rcx, rax
0x140004cd7  jz      short loc_140004D0D
0x140004cd9  test    byte ptr [rcx+1Ch], 8
0x140004cdd  jz      short loc_140004D0D
0x140004cdf  cmp     byte ptr [rcx+19h], 2
0x140004ce3  jb      short loc_140004D0D
0x140004ce5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004cea  mov     edx, 1Ah
0x140004cef  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cf6  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x140004cfd  mov     r9d, eax
0x140004d00  mov     dword ptr [rsp+68h+ppsidGroup], ebx
0x140004d04  mov     rcx, [rcx+10h]
0x140004d08  call    WPP_SF_Dd
0x140004d0d  test    ebx, ebx
0x140004d0f  jle     short loc_140004D1A
0x140004d11  movzx   ebx, bx
0x140004d14  or      ebx, 80070000h
0x140004d1a  test    ebx, ebx
0x140004d1c  mov     eax, 80004005h
0x140004d21  cmovns  ebx, eax
0x140004d24  jmp     loc_140005023
0x140004d29  xor     r9d, r9d; ppsidOwner
0x140004d2c  lea     rax, [rbp+hMem]
0x140004d30  mov     [rsp+68h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x140004d35  mov     rcx, r14; handle
0x140004d38  lea     rax, [rbp+pAcl]
0x140004d3c  mov     [rsp+68h+ppSacl], rdi; ppSacl
0x140004d41  mov     [rsp+68h+ppDacl], rax; ppDacl
0x140004d46  lea     edx, [r9+6]; ObjectType
0x140004d4a  mov     [rsp+68h+ppsidGroup], rdi; ppsidGroup
0x140004d4f  lea     r8d, [r9+4]; SecurityInfo
0x140004d53  call    cs:__imp_GetSecurityInfo
0x140004d59  test    eax, eax
0x140004d5b  jz      short loc_140004D93
0x140004d5d  call    cs:__imp_GetLastError
0x140004d63  mov     ebx, eax
0x140004d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d6c  lea     rax, WPP_GLOBAL_Control
0x140004d73  cmp     rcx, rax
0x140004d76  jz      short loc_140004D0D
0x140004d78  test    byte ptr [rcx+1Ch], 8
0x140004d7c  jz      short loc_140004D0D
0x140004d7e  cmp     byte ptr [rcx+19h], 2
0x140004d82  jb      short loc_140004D0D
0x140004d84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004d89  mov     edx, 1Bh
0x140004d8e  jmp     loc_140004CEF
0x140004d93  mov     rax, [rbp+pAcl]
0x140004d97  mov     rcx, r13; pSid
0x140004d9a  movzx   ebx, word ptr [rax+2]
0x140004d9e  call    cs:__imp_GetLengthSid
0x140004da4  add     ebx, 8
0x140004da7  xor     ecx, ecx; uFlags
0x140004da9  add     ebx, eax
0x140004dab  mov     edx, ebx; uBytes
0x140004dad  call    cs:__imp_LocalAlloc
0x140004db3  mov     r12, rax
0x140004db6  test    rax, rax
0x140004db9  jnz     short loc_140004DF5
0x140004dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dc2  lea     rax, WPP_GLOBAL_Control
0x140004dc9  cmp     rcx, rax
0x140004dcc  jz      loc_140004C9E
0x140004dd2  test    byte ptr [rcx+1Ch], 8
0x140004dd6  jz      loc_140004C9E
0x140004ddc  cmp     byte ptr [rcx+19h], 2
0x140004de0  jb      loc_140004C9E
0x140004de6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004deb  lea     edx, [r12+1Ch]
0x140004df0  jmp     loc_140004C7C
0x140004df5  mov     r8d, 2; dwAclRevision
0x140004dfb  mov     edx, ebx; nAclLength
0x140004dfd  mov     rcx, r12; pAcl
0x140004e00  call    cs:__imp_InitializeAcl
0x140004e06  test    eax, eax
0x140004e08  jnz     short loc_140004E4C
0x140004e0a  call    cs:__imp_GetLastError
0x140004e10  mov     ebx, eax
0x140004e12  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e19  lea     rax, WPP_GLOBAL_Control
0x140004e20  cmp     rcx, rax
0x140004e23  jz      loc_140004D0D
0x140004e29  test    byte ptr [rcx+1Ch], 8
0x140004e2d  jz      loc_140004D0D
0x140004e33  cmp     byte ptr [rcx+19h], 2
0x140004e37  jb      loc_140004D0D
0x140004e3d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004e42  mov     edx, 1Dh
0x140004e47  jmp     loc_140004CEF
0x140004e4c  mov     rcx, [rbp+pAcl]; pAcl
0x140004e50  xor     ebx, ebx
0x140004e52  xor     eax, eax
0x140004e54  cmp     ax, [rcx+4]
0x140004e58  jnb     short loc_140004EC3
0x140004e5a  lea     r8, [rbp+pAce]; pAce
0x140004e5e  mov     edx, ebx; dwAceIndex
0x140004e60  call    cs:__imp_GetAce
0x140004e66  test    eax, eax
0x140004e68  jz      loc_140004F6B
0x140004e6e  mov     r9, [rbp+pAce]
0x140004e72  cmp     byte ptr [r9], 0
0x140004e76  jnz     short loc_140004E96
0x140004e78  lea     rdx, [r9+8]; pSid2
0x140004e7c  mov     rcx, r13; pSid1
0x140004e7f  call    cs:__imp_EqualSid
0x140004e85  test    eax, eax
0x140004e87  jz      short loc_140004E92
0x140004e89  mov     rax, [rbp+pAce]
0x140004e8d  mov     edi, [rax+4]
0x140004e90  jmp     short loc_140004EB5
0x140004e92  mov     r9, [rbp+pAce]; pAceList
0x140004e96  movzx   eax, word ptr [r9+2]
0x140004e9b  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140004e9f  mov     edx, 2; dwAceRevision
0x140004ea4  mov     dword ptr [rsp+68h+ppsidGroup], eax; nAceListLength
0x140004ea8  mov     rcx, r12; pAcl
0x140004eab  call    cs:__imp_AddAce
0x140004eb1  test    eax, eax
0x140004eb3  jz      short loc_140004F29
0x140004eb5  mov     rcx, [rbp+pAcl]
0x140004eb9  inc     ebx
0x140004ebb  movzx   eax, word ptr [rcx+4]
0x140004ebf  cmp     ebx, eax
0x140004ec1  jb      short loc_140004E5A
0x140004ec3  test    esi, esi
0x140004ec5  jz      loc_140004FAD
0x140004ecb  mov     r9, r13; pSid
0x140004ece  mov     r8d, esi; AccessMask
0x140004ed1  mov     edx, 2; dwAceRevision
0x140004ed6  mov     rcx, r12; pAcl
0x140004ed9  call    cs:__imp_AddAccessAllowedAce
0x140004edf  test    eax, eax
0x140004ee1  jnz     loc_140004FAD
0x140004ee7  call    cs:__imp_GetLastError
0x140004eed  mov     ebx, eax
0x140004eef  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ef6  lea     rax, WPP_GLOBAL_Control
0x140004efd  cmp     rcx, rax
0x140004f00  jz      loc_140004D0D
0x140004f06  test    byte ptr [rcx+1Ch], 8
0x140004f0a  jz      loc_140004D0D
0x140004f10  cmp     byte ptr [rcx+19h], 2
0x140004f14  jb      loc_140004D0D
0x140004f1a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004f1f  mov     edx, 20h ; ' '
0x140004f24  jmp     loc_140004CEF
0x140004f29  call    cs:__imp_GetLastError
0x140004f2f  mov     ebx, eax
0x140004f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f38  lea     rax, WPP_GLOBAL_Control
0x140004f3f  cmp     rcx, rax
0x140004f42  jz      loc_140004D0D
0x140004f48  test    byte ptr [rcx+1Ch], 8
0x140004f4c  jz      loc_140004D0D
0x140004f52  cmp     byte ptr [rcx+19h], 2
0x140004f56  jb      loc_140004D0D
0x140004f5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004f61  mov     edx, 1Fh
0x140004f66  jmp     loc_140004CEF
0x140004f6b  call    cs:__imp_GetLastError
0x140004f71  mov     ebx, eax
0x140004f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f7a  lea     rax, WPP_GLOBAL_Control
0x140004f81  cmp     rcx, rax
0x140004f84  jz      loc_140004D0D
0x140004f8a  test    byte ptr [rcx+1Ch], 8
0x140004f8e  jz      loc_140004D0D
0x140004f94  cmp     byte ptr [rcx+19h], 2
0x140004f98  jb      loc_140004D0D
0x140004f9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004fa3  mov     edx, 1Eh
0x140004fa8  jmp     loc_140004CEF
0x140004fad  xor     r9d, r9d; psidOwner
0x140004fb0  mov     [rsp+68h+ppSacl], 0; pSacl
0x140004fb9  mov     [rsp+68h+ppDacl], r12; pDacl
0x140004fbe  mov     rcx, r14; handle
0x140004fc1  mov     [rsp+68h+ppsidGroup], 0; psidGroup
0x140004fca  lea     edx, [r9+6]; ObjectType
0x140004fce  lea     r8d, [r9+4]; SecurityInfo
0x140004fd2  call    cs:__imp_SetSecurityInfo
0x140004fd8  test    eax, eax
0x140004fda  jz      short loc_14000501E
0x140004fdc  call    cs:__imp_GetLastError
0x140004fe2  mov     ebx, eax
0x140004fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x140004feb  lea     rax, WPP_GLOBAL_Control
0x140004ff2  cmp     rcx, rax
0x140004ff5  jz      loc_140004D0D
0x140004ffb  test    byte ptr [rcx+1Ch], 8
0x140004fff  jz      loc_140004D0D
0x140005005  cmp     byte ptr [rcx+19h], 2
0x140005009  jb      loc_140004D0D
0x14000500f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140005014  mov     edx, 21h ; '!'
0x140005019  jmp     loc_140004CEF
0x14000501e  xor     ebx, ebx
0x140005020  mov     [r15], edi
0x140005023  mov     rcx, [rbp+hMem]; hMem
0x140005027  call    cs:__imp_LocalFree
0x14000502d  mov     rcx, r12; hMem
0x140005030  call    cs:__imp_LocalFree
0x140005036  mov     rcx, r13; hMem
0x140005039  call    cs:__imp_LocalFree
0x14000503f  mov     eax, ebx
0x140005041  add     rsp, 68h
0x140005045  pop     r15
0x140005047  pop     r14
0x140005049  pop     r13
0x14000504b  pop     r12
0x14000504d  pop     rdi
0x14000504e  pop     rsi
0x14000504f  pop     rbx
0x140005050  pop     rbp
0x140005051  retn
```
