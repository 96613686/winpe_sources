# CRdpSaUtils::s_RestrictProcessDacl(void *,void *)

- ea: `0x140005058`
- end: `0x1400054e7`
- name: `?s_RestrictProcessDacl@CRdpSaUtils@@SAJPEAX0@Z`
- size: `1167`
- prototype: `__int64 __fastcall(HANDLE handle, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140002944`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140005058`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400050ac`
- `ADVAPI32!GetTokenInformation` at `0x140005180`
- `ADVAPI32!GetTokenInformation` at `0x1400050ac`
- `ADVAPI32!GetTokenInformation` at `0x140005180`
- `ADVAPI32!SetSecurityInfo` at `0x1400053cc`
- `ADVAPI32!SetSecurityInfo` at `0x1400053cc`
- `ADVAPI32!AddAce` at `0x140005392`
- `ADVAPI32!AddAce` at `0x140005392`
- `ADVAPI32!GetAce` at `0x14000536b`
- `ADVAPI32!GetAce` at `0x14000536b`
- `ADVAPI32!AddAccessDeniedAce` at `0x14000530b`
- `ADVAPI32!AddAccessDeniedAce` at `0x14000530b`
- `ADVAPI32!InitializeAcl` at `0x1400052ae`
- `ADVAPI32!InitializeAcl` at `0x1400052ae`
- `ADVAPI32!GetLengthSid` at `0x14000524d`
- `ADVAPI32!GetLengthSid` at `0x14000524d`
- `ADVAPI32!GetSecurityInfo` at `0x1400051f6`
- `ADVAPI32!GetSecurityInfo` at `0x1400051f6`
- `KERNEL32!LocalFree` at `0x140005440`
- `KERNEL32!LocalFree` at `0x140005449`
- `KERNEL32!LocalFree` at `0x140005452`
- `KERNEL32!LocalFree` at `0x140005440`
- `KERNEL32!LocalFree` at `0x140005449`
- `KERNEL32!LocalFree` at `0x140005452`
- `KERNEL32!LocalAlloc` at `0x140005107`
- `KERNEL32!LocalAlloc` at `0x14000525c`
- `KERNEL32!LocalAlloc` at `0x140005107`
- `KERNEL32!LocalAlloc` at `0x14000525c`
- `KERNEL32!GetLastError` at `0x1400050b2`
- `KERNEL32!GetLastError` at `0x1400050bf`
- `KERNEL32!GetLastError` at `0x14000518a`
- `KERNEL32!GetLastError` at `0x140005200`
- `KERNEL32!GetLastError` at `0x1400052b8`
- `KERNEL32!GetLastError` at `0x140005315`
- `KERNEL32!GetLastError` at `0x1400053d6`
- `KERNEL32!GetLastError` at `0x14000546f`
- `KERNEL32!GetLastError` at `0x1400054a5`
- `KERNEL32!GetLastError` at `0x1400050b2`
- `KERNEL32!GetLastError` at `0x1400050bf`
- `KERNEL32!GetLastError` at `0x14000518a`
- `KERNEL32!GetLastError` at `0x140005200`
- `KERNEL32!GetLastError` at `0x1400052b8`
- `KERNEL32!GetLastError` at `0x140005315`
- `KERNEL32!GetLastError` at `0x1400053d6`
- `KERNEL32!GetLastError` at `0x14000546f`
- `KERNEL32!GetLastError` at `0x1400054a5`

## pseudocode

```c
__int64 __fastcall CRdpSaUtils::s_RestrictProcessDacl(HANDLE handle, HANDLE TokenHandle)
{
  struct _ACL *v2; // r14
  PSID *v5; // rsi
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int AclSize; // ebx
  DWORD v12; // ebx
  struct _ACL *v13; // rax
  struct _ACL *v14; // rcx
  DWORD v15; // ebx
  bool v16; // sf
  PACL pAcl; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+90h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  pAcl = 0;
  hMem = 0;
  pAce = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() == 122 )
  {
    v5 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v5 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &ReturnLength) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_48;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 12;
        goto LABEL_47;
      }
      if ( GetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_48;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 13;
        goto LABEL_47;
      }
      AclSize = pAcl->AclSize;
      v12 = GetLengthSid(*v5) + AclSize + 8;
      v13 = (struct _ACL *)LocalAlloc(0, v12);
      v2 = v13;
      if ( v13 )
      {
        if ( InitializeAcl(v13, v12, 2u) )
        {
          if ( AddAccessDeniedAce(v2, 2u, 0x111FFFFFu, *v5) )
          {
            v14 = pAcl;
            v15 = 0;
            if ( pAcl->AceCount )
            {
              while ( GetAce(v14, v15, &pAce) )
              {
                if ( !AddAce(v2, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
                {
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                    v8 = 18;
                    goto LABEL_47;
                  }
                  goto LABEL_48;
                }
                v14 = pAcl;
                if ( ++v15 >= pAcl->AceCount )
                  goto LABEL_42;
              }
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v8 = 17;
                goto LABEL_47;
              }
              goto LABEL_48;
            }
LABEL_42:
            LastError = 0;
            if ( !SetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, v2, 0) )
              goto LABEL_52;
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 19;
          }
          else
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 16;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_48;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 15;
        }
        goto LABEL_47;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_12:
        LastError = -2147024882;
        goto LABEL_52;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 14;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 11;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids,
      v9,
      -2147024882);
    goto LABEL_12;
  }
  v5 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_48;
  }
  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
  v8 = 10;
LABEL_47:
  WPP_SF_Dd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v8,
    WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids,
    CurrentThreadActivityIdPrefix,
    LastError);
LABEL_48:
  v16 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = LastError < 0;
  }
  if ( !v16 )
    LastError = -2147467259;
LABEL_52:
  LocalFree(hMem);
  LocalFree(v2);
  LocalFree(v5);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140005058  mov     [rsp-18h+arg_0], rbx
0x14000505d  mov     [rsp-18h+arg_8], rsi
0x140005062  push    rbp
0x140005063  push    rdi
0x140005064  push    r14
0x140005066  mov     rbp, rsp
0x140005069  sub     rsp, 60h
0x14000506d  xor     r14d, r14d
0x140005070  mov     [rbp+pAcl], 0
0x140005078  mov     rbx, rdx
0x14000507b  mov     [rbp+hMem], 0
0x140005083  mov     rdi, rcx
0x140005086  mov     [rbp+pAce], 0
0x14000508e  lea     rax, [rbp+TokenInformationLength]
0x140005092  mov     [rbp+TokenInformationLength], r14d
0x140005096  lea     edx, [r14+1]; TokenInformationClass
0x14000509a  mov     [rbp+arg_18], r14d
0x14000509e  xor     r9d, r9d; TokenInformationLength
0x1400050a1  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1400050a6  xor     r8d, r8d; TokenInformation
0x1400050a9  mov     rcx, rbx; TokenHandle
0x1400050ac  call    cs:__imp_GetTokenInformation
0x1400050b2  call    cs:__imp_GetLastError
0x1400050b8  cmp     eax, 7Ah ; 'z'
0x1400050bb  jz      short loc_1400050FF
0x1400050bd  xor     esi, esi
0x1400050bf  call    cs:__imp_GetLastError
0x1400050c5  mov     ebx, eax
0x1400050c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050ce  lea     rax, WPP_GLOBAL_Control
0x1400050d5  cmp     rcx, rax
0x1400050d8  jz      loc_140005425
0x1400050de  test    byte ptr [rcx+1Ch], 8
0x1400050e2  jz      loc_140005425
0x1400050e8  cmp     byte ptr [rcx+19h], 2
0x1400050ec  jb      loc_140005425
0x1400050f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400050f7  lea     edx, [rsi+0Ah]
0x1400050fa  jmp     loc_140005407
0x1400050ff  mov     edx, [rbp+TokenInformationLength]; uBytes
0x140005102  mov     ecx, 40h ; '@'; uFlags
0x140005107  call    cs:__imp_LocalAlloc
0x14000510d  mov     rsi, rax
0x140005110  test    rax, rax
0x140005113  jnz     short loc_140005168
0x140005115  mov     rcx, cs:WPP_GLOBAL_Control
0x14000511c  lea     rax, WPP_GLOBAL_Control
0x140005123  cmp     rcx, rax
0x140005126  jz      short loc_14000515E
0x140005128  test    byte ptr [rcx+1Ch], 8
0x14000512c  jz      short loc_14000515E
0x14000512e  cmp     byte ptr [rcx+19h], 2
0x140005132  jb      short loc_14000515E
0x140005134  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140005139  lea     edx, [rsi+0Bh]
0x14000513c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005143  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x14000514a  mov     r9d, eax
0x14000514d  mov     dword ptr [rsp+60h+ReturnLength], 8007000Eh
0x140005155  mov     rcx, [rcx+10h]
0x140005159  call    WPP_SF_Dd
0x14000515e  mov     ebx, 8007000Eh
0x140005163  jmp     loc_14000543C
0x140005168  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14000516c  lea     rax, [rbp+arg_18]
0x140005170  mov     r8, rsi; TokenInformation
0x140005173  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x140005178  mov     edx, 1; TokenInformationClass
0x14000517d  mov     rcx, rbx; TokenHandle
0x140005180  call    cs:__imp_GetTokenInformation
0x140005186  test    eax, eax
0x140005188  jnz     short loc_1400051CC
0x14000518a  call    cs:__imp_GetLastError
0x140005190  mov     ebx, eax
0x140005192  mov     rcx, cs:WPP_GLOBAL_Control
0x140005199  lea     rax, WPP_GLOBAL_Control
0x1400051a0  cmp     rcx, rax
0x1400051a3  jz      loc_140005425
0x1400051a9  test    byte ptr [rcx+1Ch], 8
0x1400051ad  jz      loc_140005425
0x1400051b3  cmp     byte ptr [rcx+19h], 2
0x1400051b7  jb      loc_140005425
0x1400051bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400051c2  mov     edx, 0Ch
0x1400051c7  jmp     loc_140005407
0x1400051cc  xor     r9d, r9d; ppsidOwner
0x1400051cf  lea     rax, [rbp+hMem]
0x1400051d3  mov     [rsp+60h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1400051d8  mov     rcx, rdi; handle
0x1400051db  lea     rax, [rbp+pAcl]
0x1400051df  mov     [rsp+60h+ppSacl], r14; ppSacl
0x1400051e4  mov     [rsp+60h+ppDacl], rax; ppDacl
0x1400051e9  lea     edx, [r9+6]; ObjectType
0x1400051ed  mov     [rsp+60h+ReturnLength], r14; ppsidGroup
0x1400051f2  lea     r8d, [r9+4]; SecurityInfo
0x1400051f6  call    cs:__imp_GetSecurityInfo
0x1400051fc  test    eax, eax
0x1400051fe  jz      short loc_140005242
0x140005200  call    cs:__imp_GetLastError
0x140005206  mov     ebx, eax
0x140005208  mov     rcx, cs:WPP_GLOBAL_Control
0x14000520f  lea     rax, WPP_GLOBAL_Control
0x140005216  cmp     rcx, rax
0x140005219  jz      loc_140005425
0x14000521f  test    byte ptr [rcx+1Ch], 8
0x140005223  jz      loc_140005425
0x140005229  cmp     byte ptr [rcx+19h], 2
0x14000522d  jb      loc_140005425
0x140005233  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140005238  mov     edx, 0Dh
0x14000523d  jmp     loc_140005407
0x140005242  mov     rax, [rbp+pAcl]
0x140005246  mov     rcx, [rsi]; pSid
0x140005249  movzx   ebx, word ptr [rax+2]
0x14000524d  call    cs:__imp_GetLengthSid
0x140005253  add     ebx, 8
0x140005256  xor     ecx, ecx; uFlags
0x140005258  add     ebx, eax
0x14000525a  mov     edx, ebx; uBytes
0x14000525c  call    cs:__imp_LocalAlloc
0x140005262  mov     r14, rax
0x140005265  test    rax, rax
0x140005268  jnz     short loc_1400052A3
0x14000526a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005271  lea     rax, WPP_GLOBAL_Control
0x140005278  cmp     rcx, rax
0x14000527b  jz      loc_14000515E
0x140005281  test    byte ptr [rcx+1Ch], 8
0x140005285  jz      loc_14000515E
0x14000528b  cmp     byte ptr [rcx+19h], 2
0x14000528f  jb      loc_14000515E
0x140005295  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000529a  lea     edx, [r14+0Eh]
0x14000529e  jmp     loc_14000513C
0x1400052a3  mov     r8d, 2; dwAclRevision
0x1400052a9  mov     edx, ebx; nAclLength
0x1400052ab  mov     rcx, r14; pAcl
0x1400052ae  call    cs:__imp_InitializeAcl
0x1400052b4  test    eax, eax
0x1400052b6  jnz     short loc_1400052FA
0x1400052b8  call    cs:__imp_GetLastError
0x1400052be  mov     ebx, eax
0x1400052c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052c7  lea     rax, WPP_GLOBAL_Control
0x1400052ce  cmp     rcx, rax
0x1400052d1  jz      loc_140005425
0x1400052d7  test    byte ptr [rcx+1Ch], 8
0x1400052db  jz      loc_140005425
0x1400052e1  cmp     byte ptr [rcx+19h], 2
0x1400052e5  jb      loc_140005425
0x1400052eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400052f0  mov     edx, 0Fh
0x1400052f5  jmp     loc_140005407
0x1400052fa  mov     r9, [rsi]; pSid
0x1400052fd  mov     edx, 2; dwAceRevision
0x140005302  mov     r8d, 111FFFFFh; AccessMask
0x140005308  mov     rcx, r14; pAcl
0x14000530b  call    cs:__imp_AddAccessDeniedAce
0x140005311  test    eax, eax
0x140005313  jnz     short loc_140005357
0x140005315  call    cs:__imp_GetLastError
0x14000531b  mov     ebx, eax
0x14000531d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005324  lea     rax, WPP_GLOBAL_Control
0x14000532b  cmp     rcx, rax
0x14000532e  jz      loc_140005425
0x140005334  test    byte ptr [rcx+1Ch], 8
0x140005338  jz      loc_140005425
0x14000533e  cmp     byte ptr [rcx+19h], 2
0x140005342  jb      loc_140005425
0x140005348  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000534d  mov     edx, 10h
0x140005352  jmp     loc_140005407
0x140005357  mov     rcx, [rbp+pAcl]; pAcl
0x14000535b  xor     ebx, ebx
0x14000535d  xor     eax, eax
0x14000535f  cmp     ax, [rcx+4]
0x140005363  jnb     short loc_1400053AE
0x140005365  lea     r8, [rbp+pAce]; pAce
0x140005369  mov     edx, ebx; dwAceIndex
0x14000536b  call    cs:__imp_GetAce
0x140005371  test    eax, eax
0x140005373  jz      loc_1400054A5
0x140005379  mov     r9, [rbp+pAce]; pAceList
0x14000537d  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140005381  mov     edx, 2; dwAceRevision
0x140005386  mov     rcx, r14; pAcl
0x140005389  movzx   eax, word ptr [r9+2]
0x14000538e  mov     dword ptr [rsp+60h+ReturnLength], eax; nAceListLength
0x140005392  call    cs:__imp_AddAce
0x140005398  test    eax, eax
0x14000539a  jz      loc_14000546F
0x1400053a0  mov     rcx, [rbp+pAcl]
0x1400053a4  inc     ebx
0x1400053a6  movzx   eax, word ptr [rcx+4]
0x1400053aa  cmp     ebx, eax
0x1400053ac  jb      short loc_140005365
0x1400053ae  xor     ebx, ebx
0x1400053b0  xor     r9d, r9d; psidOwner
0x1400053b3  mov     [rsp+60h+ppSacl], rbx; pSacl
0x1400053b8  mov     rcx, rdi; handle
0x1400053bb  mov     [rsp+60h+ppDacl], r14; pDacl
0x1400053c0  mov     [rsp+60h+ReturnLength], rbx; psidGroup
0x1400053c5  lea     edx, [rbx+6]; ObjectType
0x1400053c8  lea     r8d, [rbx+4]; SecurityInfo
0x1400053cc  call    cs:__imp_SetSecurityInfo
0x1400053d2  test    eax, eax
0x1400053d4  jz      short loc_14000543C
0x1400053d6  call    cs:__imp_GetLastError
0x1400053dc  mov     ebx, eax
0x1400053de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053e5  lea     rax, WPP_GLOBAL_Control
0x1400053ec  cmp     rcx, rax
0x1400053ef  jz      short loc_140005425
0x1400053f1  test    byte ptr [rcx+1Ch], 8
0x1400053f5  jz      short loc_140005425
0x1400053f7  cmp     byte ptr [rcx+19h], 2
0x1400053fb  jb      short loc_140005425
0x1400053fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140005402  mov     edx, 13h
0x140005407  mov     rcx, cs:WPP_GLOBAL_Control
0x14000540e  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x140005415  mov     r9d, eax
0x140005418  mov     dword ptr [rsp+60h+ReturnLength], ebx
0x14000541c  mov     rcx, [rcx+10h]
0x140005420  call    WPP_SF_Dd
0x140005425  test    ebx, ebx
0x140005427  jle     short loc_140005434
0x140005429  movzx   ebx, bx
0x14000542c  or      ebx, 80070000h
0x140005432  test    ebx, ebx
0x140005434  mov     eax, 80004005h
0x140005439  cmovns  ebx, eax
0x14000543c  mov     rcx, [rbp+hMem]; hMem
0x140005440  call    cs:__imp_LocalFree
0x140005446  mov     rcx, r14; hMem
0x140005449  call    cs:__imp_LocalFree
0x14000544f  mov     rcx, rsi; hMem
0x140005452  call    cs:__imp_LocalFree
0x140005458  lea     r11, [rsp+60h+var_s0]
0x14000545d  mov     eax, ebx
0x14000545f  mov     rbx, [r11+20h]
0x140005463  mov     rsi, [r11+28h]
0x140005467  mov     rsp, r11
0x14000546a  pop     r14
0x14000546c  pop     rdi
0x14000546d  pop     rbp
0x14000546e  retn
0x14000546f  call    cs:__imp_GetLastError
0x140005475  mov     ebx, eax
0x140005477  mov     rcx, cs:WPP_GLOBAL_Control
0x14000547e  lea     rax, WPP_GLOBAL_Control
0x140005485  cmp     rcx, rax
0x140005488  jz      short loc_140005425
0x14000548a  test    byte ptr [rcx+1Ch], 8
0x14000548e  jz      short loc_140005425
0x140005490  cmp     byte ptr [rcx+19h], 2
0x140005494  jb      short loc_140005425
0x140005496  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000549b  mov     edx, 12h
0x1400054a0  jmp     loc_140005407
0x1400054a5  call    cs:__imp_GetLastError
0x1400054ab  mov     ebx, eax
0x1400054ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054b4  lea     rax, WPP_GLOBAL_Control
0x1400054bb  cmp     rcx, rax
0x1400054be  jz      loc_140005425
0x1400054c4  test    byte ptr [rcx+1Ch], 8
0x1400054c8  jz      loc_140005425
0x1400054ce  cmp     byte ptr [rcx+19h], 2
0x1400054d2  jb      loc_140005425
0x1400054d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400054dd  mov     edx, 11h
0x1400054e2  jmp     loc_140005407
```
