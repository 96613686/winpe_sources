# CRdpSessionAgentProxy::AccessCheckWellKnownUser(WELL_KNOWN_SID_TYPE)

- ea: `0x1400035d8`
- end: `0x1400039a0`
- name: `?AccessCheckWellKnownUser@CRdpSessionAgentProxy@@AEAAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140003c20`
- `0x140003d90`
- `0x140004370`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x1400035d8`
- `0x14000499c`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14000368a`
- `ADVAPI32!OpenThreadToken` at `0x14000368a`
- `ADVAPI32!GetTokenInformation` at `0x14000371d`
- `ADVAPI32!GetTokenInformation` at `0x140003840`
- `ADVAPI32!GetTokenInformation` at `0x14000371d`
- `ADVAPI32!GetTokenInformation` at `0x140003840`
- `KERNEL32!LocalFree` at `0x14000397b`
- `KERNEL32!LocalFree` at `0x14000397b`
- `KERNEL32!LocalAlloc` at `0x1400037c9`
- `KERNEL32!LocalAlloc` at `0x1400037c9`
- `KERNEL32!GetCurrentThread` at `0x140003676`
- `KERNEL32!GetCurrentThread` at `0x140003676`
- `KERNEL32!CloseHandle` at `0x14000398a`
- `KERNEL32!CloseHandle` at `0x14000398a`
- `KERNEL32!GetLastError` at `0x140003694`
- `KERNEL32!GetLastError` at `0x140003777`
- `KERNEL32!GetLastError` at `0x140003782`
- `KERNEL32!GetLastError` at `0x14000384a`
- `KERNEL32!GetLastError` at `0x140003694`
- `KERNEL32!GetLastError` at `0x140003777`
- `KERNEL32!GetLastError` at `0x140003782`
- `KERNEL32!GetLastError` at `0x14000384a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140003606`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140003606`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400036f9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140003972`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400036f9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140003972`

## string_xrefs

- `0x140003642`: `CoImpersonateClient`
- `0x140003903`: `CRdpSaUtils::s_CheckTokenUser failed!`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::AccessCheckWellKnownUser(
        CRdpSessionAgentProxy *this,
        enum WELL_KNOWN_SID_TYPE a2)
{
  int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  bool v8; // sf
  unsigned int v9; // eax
  HLOCAL v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // eax
  bool v13; // sf
  unsigned int v14; // eax
  unsigned int v15; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int v18; // [rsp+54h] [rbp+24h]
  int v19; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  v18 = HIDWORD(this);
  TokenInformationLength = 0;
  TokenHandle = 0;
  v19 = 0;
  LastError = CoImpersonateClient();
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"CoImpersonateClient",
        LastError);
    }
    goto LABEL_54;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 42;
LABEL_11:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v6, LastError);
LABEL_12:
    v8 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError < 0;
    }
    if ( !v8 )
      LastError = -2147467259;
LABEL_16:
    CoRevertToSelf();
    goto LABEL_54;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        v9,
        -2147418113);
    }
    LastError = -2147418113;
    goto LABEL_16;
  }
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 44;
    goto LABEL_11;
  }
  v10 = LocalAlloc(0, TokenInformationLength);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        v11,
        -2147024882);
    }
    LastError = -2147024882;
    goto LABEL_16;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = CRdpSaUtils::s_CheckTokenUser(TokenHandle, a2, &v19);
    if ( LastError >= 0 )
    {
      if ( !v19 )
      {
        LastError = -2147024891;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
            v15,
            (__int64)"User not authorized",
            5);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        v14,
        (__int64)"CRdpSaUtils::s_CheckTokenUser failed!",
        LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        v12,
        LastError);
    }
    v13 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError < 0;
    }
    if ( !v13 )
      LastError = -2147467259;
  }
  CoRevertToSelf();
  LocalFree(v10);
LABEL_54:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400035d8  mov     [rsp-18h+arg_8], rbx
0x1400035dd  mov     qword ptr [rsp-18h+TokenInformationLength], rcx
0x1400035e2  push    rbp
0x1400035e3  push    rsi
0x1400035e4  push    r14
0x1400035e6  mov     rbp, rsp
0x1400035e9  sub     rsp, 30h
0x1400035ed  mov     r14d, edx
0x1400035f0  mov     [rbp+TokenInformationLength], 0
0x1400035f7  mov     [rbp+TokenHandle], 0
0x1400035ff  mov     [rbp+arg_10], 0
0x140003606  call    cs:__imp_CoImpersonateClient
0x14000360c  mov     ebx, eax
0x14000360e  test    eax, eax
0x140003610  jns     short loc_140003676
0x140003612  mov     rcx, cs:WPP_GLOBAL_Control
0x140003619  lea     rax, WPP_GLOBAL_Control
0x140003620  cmp     rcx, rax
0x140003623  jz      loc_140003981
0x140003629  test    byte ptr [rcx+1Ch], 8
0x14000362d  jz      loc_140003981
0x140003633  cmp     byte ptr [rcx+19h], 2
0x140003637  jb      loc_140003981
0x14000363d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003642  lea     rcx, aCoimpersonatec; "CoImpersonateClient"
0x140003649  mov     [rsp+30h+var_8], ebx
0x14000364d  mov     [rsp+30h+ReturnLength], rcx
0x140003652  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003659  mov     rcx, cs:WPP_GLOBAL_Control
0x140003660  mov     edx, 29h ; ')'
0x140003665  mov     r9d, eax
0x140003668  mov     rcx, [rcx+10h]
0x14000366c  call    WPP_SF_DsD
0x140003671  jmp     loc_140003981
0x140003676  call    cs:__imp_GetCurrentThread
0x14000367c  xor     r8d, r8d; OpenAsSelf
0x14000367f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140003683  mov     rcx, rax; ThreadHandle
0x140003686  lea     edx, [r8+8]; DesiredAccess
0x14000368a  call    cs:__imp_OpenThreadToken
0x140003690  test    eax, eax
0x140003692  jnz     short loc_140003704
0x140003694  call    cs:__imp_GetLastError
0x14000369a  mov     ebx, eax
0x14000369c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036a3  lea     rax, WPP_GLOBAL_Control
0x1400036aa  cmp     rcx, rax
0x1400036ad  jz      short loc_1400036E3
0x1400036af  test    byte ptr [rcx+1Ch], 8
0x1400036b3  jz      short loc_1400036E3
0x1400036b5  cmp     byte ptr [rcx+19h], 2
0x1400036b9  jb      short loc_1400036E3
0x1400036bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400036c0  mov     edx, 2Ah ; '*'
0x1400036c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036cc  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x1400036d3  mov     r9d, eax
0x1400036d6  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x1400036da  mov     rcx, [rcx+10h]
0x1400036de  call    WPP_SF_Dd
0x1400036e3  test    ebx, ebx
0x1400036e5  jle     short loc_1400036F2
0x1400036e7  movzx   ebx, bx
0x1400036ea  or      ebx, 80070000h
0x1400036f0  test    ebx, ebx
0x1400036f2  js      short loc_1400036F9
0x1400036f4  mov     ebx, 80004005h
0x1400036f9  call    cs:__imp_CoRevertToSelf
0x1400036ff  jmp     loc_140003981
0x140003704  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140003708  lea     rax, [rbp+TokenInformationLength]
0x14000370c  xor     r9d, r9d; TokenInformationLength
0x14000370f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140003714  xor     r8d, r8d; TokenInformation
0x140003717  lea     ebx, [r9+1]
0x14000371b  mov     edx, ebx; TokenInformationClass
0x14000371d  call    cs:__imp_GetTokenInformation
0x140003723  test    eax, eax
0x140003725  jz      short loc_140003777
0x140003727  mov     rcx, cs:WPP_GLOBAL_Control
0x14000372e  lea     rax, WPP_GLOBAL_Control
0x140003735  cmp     rcx, rax
0x140003738  jz      short loc_140003770
0x14000373a  test    byte ptr [rcx+1Ch], 8
0x14000373e  jz      short loc_140003770
0x140003740  cmp     byte ptr [rcx+19h], 2
0x140003744  jb      short loc_140003770
0x140003746  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000374b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003752  lea     edx, [rbx+2Ah]
0x140003755  mov     r9d, eax
0x140003758  mov     dword ptr [rsp+30h+ReturnLength], 8000FFFFh
0x140003760  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003767  mov     rcx, [rcx+10h]
0x14000376b  call    WPP_SF_Dd
0x140003770  mov     ebx, 8000FFFFh
0x140003775  jmp     short loc_1400036F9
0x140003777  call    cs:__imp_GetLastError
0x14000377d  cmp     eax, 7Ah ; 'z'
0x140003780  jz      short loc_1400037C4
0x140003782  call    cs:__imp_GetLastError
0x140003788  mov     ebx, eax
0x14000378a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003791  lea     rax, WPP_GLOBAL_Control
0x140003798  cmp     rcx, rax
0x14000379b  jz      loc_1400036E3
0x1400037a1  test    byte ptr [rcx+1Ch], 8
0x1400037a5  jz      loc_1400036E3
0x1400037ab  cmp     byte ptr [rcx+19h], 2
0x1400037af  jb      loc_1400036E3
0x1400037b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400037ba  mov     edx, 2Ch ; ','
0x1400037bf  jmp     loc_1400036C5
0x1400037c4  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1400037c7  xor     ecx, ecx; uFlags
0x1400037c9  call    cs:__imp_LocalAlloc
0x1400037cf  mov     rsi, rax
0x1400037d2  test    rax, rax
0x1400037d5  jnz     short loc_14000382A
0x1400037d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037de  lea     rax, WPP_GLOBAL_Control
0x1400037e5  cmp     rcx, rax
0x1400037e8  jz      short loc_140003820
0x1400037ea  test    byte ptr [rcx+1Ch], 8
0x1400037ee  jz      short loc_140003820
0x1400037f0  cmp     byte ptr [rcx+19h], 2
0x1400037f4  jb      short loc_140003820
0x1400037f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400037fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003802  lea     edx, [rsi+2Dh]
0x140003805  mov     r9d, eax
0x140003808  mov     dword ptr [rsp+30h+ReturnLength], 8007000Eh
0x140003810  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003817  mov     rcx, [rcx+10h]
0x14000381b  call    WPP_SF_Dd
0x140003820  mov     ebx, 8007000Eh
0x140003825  jmp     loc_1400036F9
0x14000382a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14000382e  lea     rax, [rbp+TokenInformationLength]
0x140003832  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140003836  mov     r8, rsi; TokenInformation
0x140003839  mov     edx, ebx; TokenInformationClass
0x14000383b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140003840  call    cs:__imp_GetTokenInformation
0x140003846  test    eax, eax
0x140003848  jnz     short loc_1400038B8
0x14000384a  call    cs:__imp_GetLastError
0x140003850  mov     ebx, eax
0x140003852  mov     rcx, cs:WPP_GLOBAL_Control
0x140003859  lea     rax, WPP_GLOBAL_Control
0x140003860  cmp     rcx, rax
0x140003863  jz      short loc_140003899
0x140003865  test    byte ptr [rcx+1Ch], 8
0x140003869  jz      short loc_140003899
0x14000386b  cmp     byte ptr [rcx+19h], 2
0x14000386f  jb      short loc_140003899
0x140003871  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003876  mov     rcx, cs:WPP_GLOBAL_Control
0x14000387d  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003884  mov     edx, 2Eh ; '.'
0x140003889  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x14000388d  mov     r9d, eax
0x140003890  mov     rcx, [rcx+10h]
0x140003894  call    WPP_SF_Dd
0x140003899  test    ebx, ebx
0x14000389b  jle     short loc_1400038A8
0x14000389d  movzx   ebx, bx
0x1400038a0  or      ebx, 80070000h
0x1400038a6  test    ebx, ebx
0x1400038a8  js      loc_140003972
0x1400038ae  mov     ebx, 80004005h
0x1400038b3  jmp     loc_140003972
0x1400038b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400038bc  lea     r8, [rbp+arg_10]; int *
0x1400038c0  mov     edx, r14d; WellKnownSidType
0x1400038c3  call    ?s_CheckTokenUser@CRdpSaUtils@@SAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z; CRdpSaUtils::s_CheckTokenUser(void *,WELL_KNOWN_SID_TYPE,int *)
0x1400038c8  mov     ebx, eax
0x1400038ca  test    eax, eax
0x1400038cc  jns     short loc_14000390C
0x1400038ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038d5  lea     rax, WPP_GLOBAL_Control
0x1400038dc  cmp     rcx, rax
0x1400038df  jz      loc_140003972
0x1400038e5  test    byte ptr [rcx+1Ch], 8
0x1400038e9  jz      loc_140003972
0x1400038ef  cmp     byte ptr [rcx+19h], 2
0x1400038f3  jb      short loc_140003972
0x1400038f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400038fa  mov     edx, 2Fh ; '/'
0x1400038ff  mov     [rsp+30h+var_8], ebx
0x140003903  lea     rcx, aCrdpsautilsSCh; "CRdpSaUtils::s_CheckTokenUser failed!"
0x14000390a  jmp     short loc_140003953
0x14000390c  cmp     [rbp+arg_10], 0
0x140003910  jnz     short loc_140003972
0x140003912  mov     rcx, cs:WPP_GLOBAL_Control
0x140003919  lea     rax, WPP_GLOBAL_Control
0x140003920  mov     r14d, 80070005h
0x140003926  mov     ebx, r14d
0x140003929  cmp     rcx, rax
0x14000392c  jz      short loc_140003972
0x14000392e  test    byte ptr [rcx+1Ch], 8
0x140003932  jz      short loc_140003972
0x140003934  cmp     byte ptr [rcx+19h], 2
0x140003938  jb      short loc_140003972
0x14000393a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000393f  mov     edx, 30h ; '0'
0x140003944  mov     [rsp+30h+var_8], 80070005h
0x14000394c  lea     rcx, aUserNotAuthori; "User not authorized"
0x140003953  mov     [rsp+30h+ReturnLength], rcx
0x140003958  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x14000395f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003966  mov     r9d, eax
0x140003969  mov     rcx, [rcx+10h]
0x14000396d  call    WPP_SF_DsD
0x140003972  call    cs:__imp_CoRevertToSelf
0x140003978  mov     rcx, rsi; hMem
0x14000397b  call    cs:__imp_LocalFree
0x140003981  mov     rcx, [rbp+TokenHandle]; hObject
0x140003985  test    rcx, rcx
0x140003988  jz      short loc_140003990
0x14000398a  call    cs:__imp_CloseHandle
0x140003990  mov     eax, ebx
0x140003992  mov     rbx, [rsp+30h+arg_8]
0x140003997  add     rsp, 30h
0x14000399b  pop     r14
0x14000399d  pop     rsi
0x14000399e  pop     rbp
0x14000399f  retn
```
