# Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(ushort const *,void * const,bool)

- ea: `0x180068824`
- end: `0x180068aa5`
- name: `?AddUserReadExecuteAccessHelper@AccessHelpers@Deployment@Common@@SAJPEBGQEAX_N@Z`
- size: `641`
- prototype: `__int64 __fastcall(const unsigned __int16 *, PSID pSid2, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d8ea0`

## callees

- `0x18000669c`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800225fc`
- `0x180022f94`
- `0x180050e60`
- `0x180068824`
- `0x180068aac`
- `0x180069eb4`
- `0x180099b44`
- `0x1800da7c0`
- `0x18017fcbc`
- `0x18017ffa0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800689c5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800689c5`
- `ADVAPI32!GetAce` at `0x18006899f`
- `ADVAPI32!GetAce` at `0x18006899f`
- `ADVAPI32!InitializeAcl` at `0x180068925`
- `ADVAPI32!InitializeAcl` at `0x180068925`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800688c9`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800688c9`

## string_xrefs

- `0x18006886d`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800688e0`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180068939`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180068a17`: `onecore\admin\appmodel\common\accesshelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(
        const unsigned __int16 *a1,
        PSID pSid2,
        unsigned __int8 a3)
{
  int v3; // edi
  int v6; // eax
  unsigned int LastError; // ebx
  DWORD NamedSecurityInfoW; // eax
  void *v10; // r8
  int v11; // r12d
  PACL v12; // rsi
  const char *v13; // r9
  PACL p_pAcl; // r8
  DWORD i; // edi
  struct _ACL v16; // rbx
  int v17; // eax
  const unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  int ppsidGroup; // [rsp+20h] [rbp-48h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-48h]
  PACL ppDacl; // [rsp+40h] [rbp-28h] BYREF
  struct _ACL pAcl; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  PSECURITY_DESCRIPTOR P; // [rsp+C8h] [rbp+60h] BYREF

  v3 = a3;
  ppDacl = 0;
  v26[0] = 0;
  v26[1] = 0;
  P = 0;
  v6 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v26, 0);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (const char *)(unsigned int)v6,
      ppsidGroup);
    Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(P);
LABEL_3:
    if ( LODWORD(v26[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v26);
    return LastError;
  }
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &P);
  if ( NamedSecurityInfoW )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                  (const char *)NamedSecurityInfoW,
                  ppsidGroupa);
    Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(P);
    goto LABEL_3;
  }
  v11 = 32 * v3 + 1179785;
  v12 = ppDacl;
  if ( ppDacl )
  {
    if ( (_BYTE)v3 )
    {
      if ( Common::Deployment::UserHasReadExecuteAccess(ppDacl, pSid2, v10) )
        goto LABEL_29;
    }
    else
    {
      pAcl = 0;
      for ( i = 0; i < v12->AceCount && GetAce(v12, i, (LPVOID *)&pAcl); ++i )
      {
        v16 = pAcl;
        if ( !*(_BYTE *)pAcl.AclRevision
          && (*(_BYTE *)(*(_QWORD *)&pAcl + 1LL) & 0x10) == 0
          && EqualSid((PSID)(*(_QWORD *)&pAcl + 8LL), pSid2)
          && (*(_DWORD *)(*(_QWORD *)&v16 + 4LL) & 0x120089) != 0 )
        {
          goto LABEL_29;
        }
      }
    }
    p_pAcl = ppDacl;
  }
  else
  {
    pAcl = 0;
    if ( !InitializeAcl(&pAcl, 8u, 2u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xE2,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                    v13);
      Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(P);
      goto LABEL_3;
    }
    p_pAcl = &pAcl;
  }
  v17 = Common::Deployment::AddUserAccessWithoutCheck(a1, 3, p_pAcl, pSid2);
  LastError = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (const char *)(unsigned int)v17,
      v11);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    {
      v18 = RemovePIIfromFilePath(a1);
      McTemplateU0zd_EventWriteTransfer(v19, &ChangingAccessRightsFailed, v18, LastError);
    }
    v20 = RemovePIIfromFilePath(a1);
    details::appxLog<unsigned short *,unsigned short *>(LastError, v21, &ChangingAccessRightsFailed, v20);
    Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(P);
    goto LABEL_3;
  }
LABEL_29:
  Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(P);
  if ( LODWORD(v26[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v26);
  return 0;
}

```

## disassembly

```asm
0x180068824  push    rbp
0x180068826  push    rbx
0x180068827  push    rsi
0x180068828  push    rdi
0x180068829  push    r12
0x18006882b  push    r13
0x18006882d  push    r14
0x18006882f  push    r15
0x180068831  mov     rbp, rsp
0x180068834  sub     rsp, 68h
0x180068838  movzx   edi, r8b
0x18006883c  mov     r15, rdx
0x18006883f  mov     r14, rcx
0x180068842  xor     r13d, r13d
0x180068845  mov     [rbp+var_28], r13
0x180068849  mov     [rbp+var_18], r13
0x18006884d  mov     [rbp+var_10], r13
0x180068851  mov     [rbp+P], r13
0x180068855  xor     edx, edx; void *
0x180068857  lea     rcx, [rbp+var_18]; this
0x18006885b  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180068860  mov     ebx, eax
0x180068862  test    eax, eax
0x180068864  jns     short loc_18006889F
0x180068866  mov     rcx, [rbp+40h]; this
0x18006886a  mov     r9d, eax; char *
0x18006886d  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x180068874  mov     edx, 0D2h; void *
0x180068879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006887e  nop
0x18006887f  mov     rcx, [rbp+P]; P
0x180068883  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x180068888  nop
0x180068889  cmp     dword ptr [rbp+var_18], r13d
0x18006888d  jz      short loc_180068898
0x18006888f  lea     rcx, [rbp+var_18]; this
0x180068893  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180068898  mov     eax, ebx
0x18006889a  jmp     loc_180068A93
0x18006889f  lea     rax, [rbp+P]
0x1800688a3  mov     [rsp+68h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800688a8  mov     [rsp+68h+ppSacl], r13; ppSacl
0x1800688ad  lea     rax, [rbp+var_28]
0x1800688b1  mov     [rsp+68h+ppDacl], rax; ppDacl
0x1800688b6  mov     [rsp+68h+ppsidGroup], r13; unsigned int
0x1800688bb  xor     r9d, r9d; ppsidOwner
0x1800688be  lea     edx, [r9+1]; ObjectType
0x1800688c2  lea     r8d, [r9+4]; SecurityInfo
0x1800688c6  mov     rcx, r14; pObjectName
0x1800688c9  call    cs:__imp_GetNamedSecurityInfoW
0x1800688d0  nop     dword ptr [rax+rax+00h]
0x1800688d5  test    eax, eax
0x1800688d7  jz      short loc_1800688FF
0x1800688d9  mov     rcx, [rbp+40h]; this
0x1800688dd  mov     r9d, eax; char *
0x1800688e0  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x1800688e7  mov     edx, 0DCh; void *
0x1800688ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800688f1  mov     ebx, eax
0x1800688f3  mov     rcx, [rbp+P]; P
0x1800688f7  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x1800688fc  nop
0x1800688fd  jmp     short loc_180068889
0x1800688ff  mov     r12d, edi
0x180068902  shl     r12d, 5
0x180068906  add     r12d, 120089h
0x18006890d  mov     rsi, [rbp+var_28]
0x180068911  test    rsi, rsi
0x180068914  jnz     short loc_180068964
0x180068916  mov     qword ptr [rbp+pAcl.AclRevision], r13
0x18006891a  lea     edx, [rsi+8]; nAclLength
0x18006891d  lea     r8d, [rsi+2]; dwAclRevision
0x180068921  lea     rcx, [rbp+pAcl]; pAcl
0x180068925  call    cs:__imp_InitializeAcl
0x18006892c  nop     dword ptr [rax+rax+00h]
0x180068931  test    eax, eax
0x180068933  jnz     short loc_18006895B
0x180068935  mov     rcx, [rbp+40h]; this
0x180068939  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x180068940  mov     edx, 0E2h; void *
0x180068945  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006894a  mov     ebx, eax
0x18006894c  mov     rcx, [rbp+P]; P
0x180068950  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x180068955  nop
0x180068956  jmp     loc_180068889
0x18006895b  lea     r8, [rbp+pAcl]
0x18006895f  jmp     loc_1800689F5
0x180068964  test    dil, dil
0x180068967  jz      short loc_180068987
0x180068969  mov     rdx, r15; pSid2
0x18006896c  mov     rcx, rsi; pAcl
0x18006896f  call    ?UserHasReadExecuteAccess@Deployment@Common@@YA_NQEAU_ACL@@QEAX@Z; Common::Deployment::UserHasReadExecuteAccess(_ACL * const,void * const)
0x180068974  test    al, al
0x180068976  jz      short loc_1800689F1
0x180068978  mov     rcx, [rbp+P]; P
0x18006897c  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x180068981  nop
0x180068982  jmp     loc_180068A82
0x180068987  mov     qword ptr [rbp+pAcl.AclRevision], r13
0x18006898b  mov     edi, r13d
0x18006898e  movzx   eax, word ptr [rsi+4]
0x180068992  cmp     edi, eax
0x180068994  jnb     short loc_1800689F1
0x180068996  lea     r8, [rbp+pAcl]; pAce
0x18006899a  mov     edx, edi; dwAceIndex
0x18006899c  mov     rcx, rsi; pAcl
0x18006899f  call    cs:__imp_GetAce
0x1800689a6  nop     dword ptr [rax+rax+00h]
0x1800689ab  test    eax, eax
0x1800689ad  jz      short loc_1800689F1
0x1800689af  mov     rbx, qword ptr [rbp+pAcl.AclRevision]
0x1800689b3  cmp     [rbx], r13b
0x1800689b6  jnz     short loc_1800689DE
0x1800689b8  test    byte ptr [rbx+1], 10h
0x1800689bc  jnz     short loc_1800689DE
0x1800689be  lea     rcx, [rbx+8]; pSid1
0x1800689c2  mov     rdx, r15; pSid2
0x1800689c5  call    cs:__imp_EqualSid
0x1800689cc  nop     dword ptr [rax+rax+00h]
0x1800689d1  test    eax, eax
0x1800689d3  jz      short loc_1800689DE
0x1800689d5  test    dword ptr [rbx+4], 120089h
0x1800689dc  jnz     short loc_1800689E2
0x1800689de  inc     edi
0x1800689e0  jmp     short loc_18006898E
0x1800689e2  mov     rcx, [rbp+P]; P
0x1800689e6  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x1800689eb  nop
0x1800689ec  jmp     loc_180068A82
0x1800689f1  mov     r8, [rbp+var_28]
0x1800689f5  mov     dword ptr [rsp+68h+ppsidGroup], r12d; int
0x1800689fa  mov     r9, r15
0x1800689fd  mov     edx, 3
0x180068a02  mov     rcx, r14
0x180068a05  call    ?AddUserAccessWithoutCheck@Deployment@Common@@YAJPEBGW4InheritFlags@12@QEAU_ACL@@QEAXK@Z; Common::Deployment::AddUserAccessWithoutCheck(ushort const *,Common::Deployment::InheritFlags,_ACL * const,void * const,ulong)
0x180068a0a  mov     ebx, eax
0x180068a0c  test    eax, eax
0x180068a0e  jns     short loc_180068A78
0x180068a10  mov     rcx, [rbp+40h]; this
0x180068a14  mov     r9d, eax; char *
0x180068a17  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x180068a1e  mov     edx, 0FBh; void *
0x180068a23  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068a28  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r13b
0x180068a2f  jge     short loc_180068A4B
0x180068a31  mov     rcx, r14; unsigned __int16 *
0x180068a34  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180068a39  mov     r8, rax
0x180068a3c  mov     r9d, ebx
0x180068a3f  lea     rdx, ChangingAccessRightsFailed
0x180068a46  call    McTemplateU0zd_EventWriteTransfer
0x180068a4b  mov     rcx, r14; unsigned __int16 *
0x180068a4e  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180068a53  mov     r9, rax
0x180068a56  mov     dword ptr [rsp+68h+ppsidGroup], ebx
0x180068a5a  lea     r8, ChangingAccessRightsFailed
0x180068a61  mov     ecx, ebx
0x180068a63  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x180068a68  nop
0x180068a69  mov     rcx, [rbp+P]; P
0x180068a6d  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x180068a72  nop
0x180068a73  jmp     loc_180068889
0x180068a78  mov     rcx, [rbp+P]; P
0x180068a7c  call    ?MemFree@?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@SAXPEAPEAVStatementCacheEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>::MemFree(StateRepository::StatementCacheEntry * *)
0x180068a81  nop
0x180068a82  cmp     dword ptr [rbp+var_18], r13d
0x180068a86  jz      short loc_180068A91
0x180068a88  lea     rcx, [rbp+var_18]; this
0x180068a8c  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180068a91  xor     eax, eax
0x180068a93  add     rsp, 68h
0x180068a97  pop     r15
0x180068a99  pop     r14
0x180068a9b  pop     r13
0x180068a9d  pop     r12
0x180068a9f  pop     rdi
0x180068aa0  pop     rsi
0x180068aa1  pop     rbx
0x180068aa2  pop     rbp
0x180068aa3  retn
```
