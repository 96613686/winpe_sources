# CSessionUserHelper::ForEachSessionUser__lambda_322b3d444e89a45205c8bfe5e21eca2c___

- ea: `0x180179294`
- end: `0x180179544`
- name: `CSessionUserHelper::ForEachSessionUser__lambda_322b3d444e89a45205c8bfe5e21eca2c___`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18018146c`

## callees

- `0x18000f880`
- `0x1800f8f24`
- `0x180129d58`
- `0x18012a138`
- `0x1801791f8`
- `0x180179294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179355`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18017932a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18017932a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801793bc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801793bc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18017934b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18017934b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1801792d9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1801792d9`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180179499`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180179499`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180179449`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180179449`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801793e3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801793e3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18017938a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801794f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18017938a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801794f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180179480`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180179480`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801794de`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180179520`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801794de`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180179520`

## string_xrefs

- `0x1801792e7`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801793f6`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801794a7`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801794c1`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSessionUserHelper::ForEachSessionUser__lambda_322b3d444e89a45205c8bfe5e21eca2c___(
        DWORD a1,
        __int64 a2)
{
  signed int v3; // ebx
  const char *v4; // r9
  __int64 i; // rdi
  ULONG SessionId; // esi
  WTS_CONNECTSTATE_CLASS State; // r15d
  signed int LastError; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edi
  DWORD v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  int pCount; // [rsp+20h] [rbp-40h]
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+38h] [rbp-28h] BYREF
  char v23; // [rsp+40h] [rbp-20h]
  void **p_phToken; // [rsp+48h] [rbp-18h]
  char v25; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD v27; // [rsp+90h] [rbp+30h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A0h] [rbp+40h] BYREF
  void *phToken; // [rsp+A8h] [rbp+48h] BYREF

  v27 = a1;
  v3 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v27 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v27) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v4);
    p_ppSessionInfo = &ppSessionInfo;
    v23 = 1;
    for ( i = 0; (unsigned int)i < v27; i = (unsigned int)(i + 1) )
    {
      if ( v3 )
        break;
      SessionId = ppSessionInfo[i].SessionId;
      State = ppSessionInfo[i].State;
      if ( SessionId != (unsigned int)RtlGetCurrentServiceSessionId() && (State & 0xFFFFFFFB) == 0 )
      {
        phToken = 0;
        if ( WTSQueryUserToken(SessionId, &phToken) )
          goto LABEL_14;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
        {
LABEL_14:
          v21 = 0;
          v3 = UMgrQueryUserContext(phToken, &v21);
          if ( v3 >= 0 )
            v3 = CSessionUserHelper::CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___(v10, phToken, a2);
        }
        else if ( v3 == -2147023584 )
        {
          v3 = 0;
        }
      }
    }
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    goto LABEL_41;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v27 = 0;
    phToken = 0;
    v11 = UMgrEnumerateSessionUsers(&v27, &phToken);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
        (const char *)(unsigned int)v11,
        pCount);
      return v12;
    }
    p_phToken = &phToken;
    v25 = 1;
    v13 = 0;
    v14 = v27;
    if ( v27 )
    {
      while ( !v3 )
      {
        v15 = *((_QWORD *)phToken + 2 * v13);
        if ( v15 )
        {
          ppSessionInfo = 0;
          v3 = UMgrQueryUserToken(v15, &ppSessionInfo);
          if ( v3 < 0 )
          {
            v18 = 123;
            goto LABEL_33;
          }
          v3 = CSessionUserHelper::CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___(v16, ppSessionInfo, a2);
          v14 = v27;
        }
        if ( ++v13 >= v14 )
        {
          if ( v3 )
            goto LABEL_39;
          goto LABEL_29;
        }
      }
      goto LABEL_39;
    }
LABEL_29:
    v21 = 0;
    if ( (int)UMgrQueryDefaultAccountToken(&v21) >= 0 )
    {
      LODWORD(ppSessionInfo) = 0;
      if ( !(unsigned int)QueryActiveSession(&ppSessionInfo) )
      {
        v3 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x88,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v17);
LABEL_34:
        if ( phToken )
          UMgrFreeSessionUsers();
        return (unsigned int)v3;
      }
      p_ppSessionInfo = 0;
      v3 = UMgrQueryUserContext(v21, &p_ppSessionInfo);
      if ( v3 < 0 )
      {
        v18 = 139;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
          (const char *)(unsigned int)v3,
          pCount);
        goto LABEL_34;
      }
      v3 = CSessionUserHelper::CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___(v19, v21, a2);
    }
LABEL_39:
    if ( phToken )
      UMgrFreeSessionUsers();
LABEL_41:
    if ( v3 == 1 )
      return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180179294  mov     [rsp-28h+arg_8], rbx
0x180179299  mov     [rsp-28h+arg_0], ecx
0x18017929d  push    rbp
0x18017929e  push    rsi
0x18017929f  push    rdi
0x1801792a0  push    r14
0x1801792a2  push    r15
0x1801792a4  mov     rbp, rsp
0x1801792a7  sub     rsp, 60h
0x1801792ab  mov     r14, rdx
0x1801792ae  xor     ebx, ebx
0x1801792b0  call    IsWTSEnumerateSessionsWPresent
0x1801792b5  test    al, al
0x1801792b7  jz      loc_1801793C7
0x1801792bd  mov     [rbp+arg_0], ebx
0x1801792c0  mov     [rbp+ppSessionInfo], rbx
0x1801792c4  lea     rax, [rbp+arg_0]
0x1801792c8  mov     qword ptr [rsp+60h+pCount], rax; pCount
0x1801792cd  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1801792d1  xor     edx, edx; Reserved
0x1801792d3  xor     ecx, ecx; hServer
0x1801792d5  lea     r8d, [rbx+1]; Version
0x1801792d9  call    cs:__imp_WTSEnumerateSessionsW
0x1801792df  test    eax, eax
0x1801792e1  jnz     short loc_1801792FB
0x1801792e3  mov     rcx, [rbp+28h]; this
0x1801792e7  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801792ee  lea     edx, [rbx+26h]; void *
0x1801792f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801792f6  jmp     loc_180179530
0x1801792fb  lea     rax, [rbp+ppSessionInfo]
0x1801792ff  mov     [rbp+var_28], rax
0x180179303  mov     [rbp+var_20], 1
0x180179307  xor     edi, edi
0x180179309  cmp     [rbp+arg_0], edi
0x18017930c  jbe     loc_1801793AF
0x180179312  test    ebx, ebx
0x180179314  jnz     loc_1801793AF
0x18017931a  lea     rdx, [rdi+rdi*2]
0x18017931e  mov     rax, [rbp+ppSessionInfo]
0x180179322  mov     esi, [rax+rdx*8]
0x180179325  mov     r15d, [rax+rdx*8+10h]
0x18017932a  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180179330  cmp     esi, eax
0x180179332  jz      short loc_1801793A4
0x180179334  test    r15d, 0FFFFFFFBh
0x18017933b  jnz     short loc_1801793A4
0x18017933d  mov     [rbp+phToken], 0
0x180179345  lea     rdx, [rbp+phToken]; phToken
0x180179349  mov     ecx, esi; SessionId
0x18017934b  call    cs:__imp_WTSQueryUserToken
0x180179351  test    eax, eax
0x180179353  jnz     short loc_18017937A
0x180179355  call    cs:__imp_GetLastError
0x18017935b  mov     ebx, eax
0x18017935d  test    eax, eax
0x18017935f  jle     short loc_18017936A
0x180179361  movzx   ebx, ax
0x180179364  or      ebx, 80070000h
0x18017936a  test    ebx, ebx
0x18017936c  jns     short loc_18017937A
0x18017936e  cmp     ebx, 80070520h
0x180179374  jnz     short loc_1801793A4
0x180179376  xor     ebx, ebx
0x180179378  jmp     short loc_1801793A4
0x18017937a  mov     [rbp+var_30], 0
0x180179382  lea     rdx, [rbp+var_30]
0x180179386  mov     rcx, [rbp+phToken]
0x18017938a  call    cs:__imp_UMgrQueryUserContext
0x180179390  mov     ebx, eax
0x180179392  test    eax, eax
0x180179394  js      short loc_1801793A4
0x180179396  mov     r8, r14
0x180179399  mov     rdx, [rbp+phToken]
0x18017939d  call    CSessionUserHelper__CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___
0x1801793a2  mov     ebx, eax
0x1801793a4  inc     edi
0x1801793a6  cmp     edi, [rbp+arg_0]
0x1801793a9  jb      loc_180179312
0x1801793af  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x1801793b3  test    rcx, rcx
0x1801793b6  jz      loc_180179526
0x1801793bc  call    cs:__imp_WTSFreeMemory
0x1801793c2  jmp     loc_180179526
0x1801793c7  call    IsUMgrEnumerateSessionUsersPresent
0x1801793cc  test    al, al
0x1801793ce  jz      loc_18017952E
0x1801793d4  mov     [rbp+arg_0], ebx
0x1801793d7  mov     [rbp+phToken], rbx
0x1801793db  lea     rdx, [rbp+phToken]
0x1801793df  lea     rcx, [rbp+arg_0]
0x1801793e3  call    cs:__imp_UMgrEnumerateSessionUsers
0x1801793e9  mov     edi, eax
0x1801793eb  test    eax, eax
0x1801793ed  jns     short loc_18017940E
0x1801793ef  mov     rcx, [rbp+28h]; this
0x1801793f3  mov     r9d, eax; char *
0x1801793f6  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801793fd  mov     edx, 69h ; 'i'; void *
0x180179402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180179407  mov     eax, edi
0x180179409  jmp     loc_180179530
0x18017940e  lea     rax, [rbp+phToken]
0x180179412  mov     [rbp+var_18], rax
0x180179416  mov     [rbp+var_10], 1
0x18017941a  xor     edi, edi
0x18017941c  mov     edx, [rbp+arg_0]
0x18017941f  test    edx, edx
0x180179421  jz      short loc_180179474
0x180179423  test    ebx, ebx
0x180179425  jnz     loc_180179517
0x18017942b  mov     ecx, edi
0x18017942d  add     rcx, rcx
0x180179430  mov     rax, [rbp+phToken]
0x180179434  mov     rcx, [rax+rcx*8]
0x180179438  test    rcx, rcx
0x18017943b  jz      short loc_180179466
0x18017943d  mov     [rbp+ppSessionInfo], 0
0x180179445  lea     rdx, [rbp+ppSessionInfo]
0x180179449  call    cs:__imp_UMgrQueryUserToken
0x18017944f  mov     ebx, eax
0x180179451  test    eax, eax
0x180179453  js      short loc_1801794BC
0x180179455  mov     r8, r14
0x180179458  mov     rdx, [rbp+ppSessionInfo]
0x18017945c  call    CSessionUserHelper__CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___
0x180179461  mov     ebx, eax
0x180179463  mov     edx, [rbp+arg_0]
0x180179466  inc     edi
0x180179468  cmp     edi, edx
0x18017946a  jb      short loc_180179423
0x18017946c  test    ebx, ebx
0x18017946e  jnz     loc_180179517
0x180179474  mov     [rbp+var_30], 0
0x18017947c  lea     rcx, [rbp+var_30]
0x180179480  call    cs:__imp_UMgrQueryDefaultAccountToken
0x180179486  test    eax, eax
0x180179488  js      loc_180179517
0x18017948e  mov     dword ptr [rbp+ppSessionInfo], 0
0x180179495  lea     rcx, [rbp+ppSessionInfo]
0x180179499  call    cs:__imp_QueryActiveSession
0x18017949f  test    eax, eax
0x1801794a1  jnz     short loc_1801794E6
0x1801794a3  mov     rcx, [rbp+28h]; this
0x1801794a7  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801794ae  mov     edx, 88h; void *
0x1801794b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801794b8  mov     ebx, eax
0x1801794ba  jmp     short loc_1801794D5
0x1801794bc  mov     edx, 7Bh ; '{'; void *
0x1801794c1  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801794c8  mov     r9d, ebx; char *
0x1801794cb  mov     rcx, [rbp+28h]; this
0x1801794cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801794d4  nop
0x1801794d5  mov     rcx, [rbp+phToken]
0x1801794d9  test    rcx, rcx
0x1801794dc  jz      short loc_18017952E
0x1801794de  call    cs:__imp_UMgrFreeSessionUsers
0x1801794e4  jmp     short loc_18017952E
0x1801794e6  mov     [rbp+var_28], 0
0x1801794ee  lea     rdx, [rbp+var_28]
0x1801794f2  mov     rcx, [rbp+var_30]
0x1801794f6  call    cs:__imp_UMgrQueryUserContext
0x1801794fc  mov     ebx, eax
0x1801794fe  test    eax, eax
0x180179500  jns     short loc_180179509
0x180179502  mov     edx, 8Bh
0x180179507  jmp     short loc_1801794C1
0x180179509  mov     r8, r14
0x18017950c  mov     rdx, [rbp+var_30]
0x180179510  call    CSessionUserHelper__CallbackUserToken__lambda_322b3d444e89a45205c8bfe5e21eca2c___
0x180179515  mov     ebx, eax
0x180179517  mov     rcx, [rbp+phToken]
0x18017951b  test    rcx, rcx
0x18017951e  jz      short loc_180179526
0x180179520  call    cs:__imp_UMgrFreeSessionUsers
0x180179526  xor     eax, eax
0x180179528  cmp     ebx, 1
0x18017952b  cmovz   ebx, eax
0x18017952e  mov     eax, ebx
0x180179530  mov     rbx, [rsp+60h+arg_8]
0x180179538  add     rsp, 60h
0x18017953c  pop     r15
0x18017953e  pop     r14
0x180179540  pop     rdi
0x180179541  pop     rsi
0x180179542  pop     rbp
0x180179543  retn
```
