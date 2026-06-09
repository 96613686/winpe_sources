# CSessionUserHelper::ForEachSessionUser__lambda_aeaaf71cc9043e5f79cc1861797bc557___

- ea: `0x18017954c`
- end: `0x1801797f5`
- name: `CSessionUserHelper::ForEachSessionUser__lambda_aeaaf71cc9043e5f79cc1861797bc557___`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18017d0e0`

## callees

- `0x18000f880`
- `0x1800f8f24`
- `0x180129d58`
- `0x18012a138`
- `0x180179244`
- `0x18017954c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801795e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801795e9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180179657`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180179657`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1801795df`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1801795df`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180179591`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180179591`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180179764`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180179764`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801796e2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801796e2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18017967e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18017967e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18017960f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180179797`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18017960f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180179797`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180179753`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180179753`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180179732`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801797d9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180179732`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801797d9`

## string_xrefs

- `0x18017959f`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18017968e`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18017971a`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x180179772`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`

## pseudocode

```c
__int64 __fastcall CSessionUserHelper::ForEachSessionUser__lambda_aeaaf71cc9043e5f79cc1861797bc557___(
        DWORD a1,
        __int64 a2)
{
  int v3; // ebx
  const char *v4; // r9
  __int64 i; // rdi
  ULONG SessionId; // ebx
  signed int LastError; // eax
  bool v9; // sf
  int v10; // eax
  unsigned int v11; // edi
  DWORD j; // edi
  __int64 v13; // rsi
  unsigned int v14; // r14d
  __int64 v15; // rcx
  int v16; // ebx
  __int64 v17; // rdx
  const char *v18; // r9
  int pCount; // [rsp+20h] [rbp-40h]
  __int64 v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h]
  _DWORD v23[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD v26; // [rsp+90h] [rbp+30h] BYREF
  void *phToken; // [rsp+A0h] [rbp+40h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A8h] [rbp+48h] BYREF

  v26 = a1;
  v3 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v26 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v26) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v4);
    for ( i = 0; (unsigned int)i < v26; i = (unsigned int)(i + 1) )
    {
      if ( v3 )
        break;
      SessionId = ppSessionInfo[i].SessionId;
      phToken = 0;
      if ( !WTSQueryUserToken(SessionId, &phToken) )
      {
        LastError = GetLastError();
        v9 = LastError < 0;
        if ( LastError > 0 )
          v9 = 1;
        if ( v9 )
          goto LABEL_12;
      }
      v20 = 0;
      if ( (int)UMgrQueryUserContext(phToken, &v20) < 0 )
      {
LABEL_12:
        v3 = 0;
      }
      else
      {
        v21 = SessionId;
        v22 = v20;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___(&v21, phToken, a2);
      }
    }
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    return 0;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v26 = 0;
    ppSessionInfo = 0;
    v10 = UMgrEnumerateSessionUsers(&v26, &ppSessionInfo);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
        (const char *)(unsigned int)v10,
        pCount);
      return v11;
    }
    for ( j = 0; j < v26; ++j )
    {
      if ( v3 )
        goto LABEL_38;
      v13 = *((_QWORD *)&ppSessionInfo->SessionId + 2 * j);
      if ( v13 )
      {
        v14 = *((_DWORD *)&ppSessionInfo->pWinStationName + 4 * j);
        v15 = *((_QWORD *)&ppSessionInfo->SessionId + 2 * j);
        phToken = 0;
        v16 = UMgrQueryUserToken(v15, &phToken);
        if ( v16 < 0 )
        {
          v17 = 123;
          goto LABEL_27;
        }
        v21 = v14;
        v22 = v13;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___(&v21, phToken, a2);
      }
    }
    if ( !v3 )
    {
      v20 = 0;
      if ( (int)UMgrQueryDefaultAccountToken(&v20) >= 0 )
      {
        LODWORD(phToken) = 0;
        if ( !(unsigned int)QueryActiveSession(&phToken) )
        {
          v16 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x88,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
                  v18);
          goto LABEL_28;
        }
        v21 = 0;
        v16 = UMgrQueryUserContext(v20, &v21);
        if ( v16 < 0 )
        {
          v17 = 139;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
            (const char *)(unsigned int)v16,
            pCount);
LABEL_28:
          if ( ppSessionInfo )
            UMgrFreeSessionUsers();
          return (unsigned int)v16;
        }
        v23[0] = (_DWORD)phToken;
        v23[1] = 0;
        v24 = v21;
        CSessionUserHelper::CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___(v23, v20, a2);
      }
    }
LABEL_38:
    if ( ppSessionInfo )
      UMgrFreeSessionUsers();
  }
  return 0;
}

```

## disassembly

```asm
0x18017954c  mov     [rsp-28h+arg_8], rbx
0x180179551  mov     [rsp-28h+arg_0], ecx
0x180179555  push    rbp
0x180179556  push    rsi
0x180179557  push    rdi
0x180179558  push    r14
0x18017955a  push    r15
0x18017955c  mov     rbp, rsp
0x18017955f  sub     rsp, 60h
0x180179563  mov     r15, rdx
0x180179566  xor     ebx, ebx
0x180179568  call    IsWTSEnumerateSessionsWPresent
0x18017956d  test    al, al
0x18017956f  jz      loc_180179662
0x180179575  lea     rax, [rbp+arg_0]
0x180179579  mov     [rbp+arg_0], ebx
0x18017957c  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180179580  mov     qword ptr [rsp+60h+pCount], rax; pCount
0x180179585  xor     edx, edx; Reserved
0x180179587  mov     [rbp+ppSessionInfo], rbx
0x18017958b  xor     ecx, ecx; hServer
0x18017958d  lea     r8d, [rbx+1]; Version
0x180179591  call    cs:__imp_WTSEnumerateSessionsW
0x180179597  test    eax, eax
0x180179599  jnz     short loc_1801795B3
0x18017959b  mov     rcx, [rbp+28h]; this
0x18017959f  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801795a6  lea     edx, [rbx+26h]; void *
0x1801795a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801795ae  jmp     loc_1801797E1
0x1801795b3  xor     edi, edi
0x1801795b5  cmp     [rbp+arg_0], ebx
0x1801795b8  jbe     loc_18017964A
0x1801795be  test    ebx, ebx
0x1801795c0  jnz     loc_18017964A
0x1801795c6  mov     rax, [rbp+ppSessionInfo]
0x1801795ca  lea     rcx, [rdi+rdi*2]
0x1801795ce  lea     rdx, [rbp+phToken]; phToken
0x1801795d2  mov     ebx, [rax+rcx*8]
0x1801795d5  mov     ecx, ebx; SessionId
0x1801795d7  mov     [rbp+phToken], 0
0x1801795df  call    cs:__imp_WTSQueryUserToken
0x1801795e5  test    eax, eax
0x1801795e7  jnz     short loc_1801795FF
0x1801795e9  call    cs:__imp_GetLastError
0x1801795ef  test    eax, eax
0x1801795f1  jle     short loc_1801795FD
0x1801795f3  movzx   eax, ax
0x1801795f6  or      eax, 80070000h
0x1801795fb  test    eax, eax
0x1801795fd  js      short loc_18017963D
0x1801795ff  mov     rcx, [rbp+phToken]
0x180179603  lea     rdx, [rbp+var_30]
0x180179607  mov     [rbp+var_30], 0
0x18017960f  call    cs:__imp_UMgrQueryUserContext
0x180179615  test    eax, eax
0x180179617  js      short loc_18017963D
0x180179619  mov     rdx, [rbp+phToken]
0x18017961d  lea     rcx, [rbp+var_28]
0x180179621  xor     eax, eax
0x180179623  mov     dword ptr [rbp+var_28], ebx
0x180179626  mov     dword ptr [rbp+var_28+4], eax
0x180179629  mov     r8, r15
0x18017962c  mov     rax, [rbp+var_30]
0x180179630  mov     [rbp+var_20], rax
0x180179634  call    CSessionUserHelper__CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___
0x180179639  mov     ebx, eax
0x18017963b  jmp     short loc_18017963F
0x18017963d  xor     ebx, ebx
0x18017963f  inc     edi
0x180179641  cmp     edi, [rbp+arg_0]
0x180179644  jb      loc_1801795BE
0x18017964a  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18017964e  test    rcx, rcx
0x180179651  jz      loc_1801797DF
0x180179657  call    cs:__imp_WTSFreeMemory
0x18017965d  jmp     loc_1801797DF
0x180179662  call    IsUMgrEnumerateSessionUsersPresent
0x180179667  test    al, al
0x180179669  jz      loc_1801797DF
0x18017966f  lea     rdx, [rbp+ppSessionInfo]
0x180179673  mov     [rbp+arg_0], ebx
0x180179676  lea     rcx, [rbp+arg_0]
0x18017967a  mov     [rbp+ppSessionInfo], rbx
0x18017967e  call    cs:__imp_UMgrEnumerateSessionUsers
0x180179684  mov     edi, eax
0x180179686  test    eax, eax
0x180179688  jns     short loc_1801796A9
0x18017968a  mov     rcx, [rbp+28h]; this
0x18017968e  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180179695  mov     r9d, eax; char *
0x180179698  mov     edx, 69h ; 'i'; void *
0x18017969d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801796a2  mov     eax, edi
0x1801796a4  jmp     loc_1801797E1
0x1801796a9  xor     edi, edi
0x1801796ab  cmp     edi, [rbp+arg_0]
0x1801796ae  jnb     loc_18017973F
0x1801796b4  test    ebx, ebx
0x1801796b6  jnz     loc_1801797D0
0x1801796bc  mov     rcx, [rbp+ppSessionInfo]
0x1801796c0  mov     eax, edi
0x1801796c2  add     rax, rax
0x1801796c5  mov     rsi, [rcx+rax*8]
0x1801796c9  test    rsi, rsi
0x1801796cc  jz      short loc_18017970D
0x1801796ce  mov     r14d, [rcx+rax*8+8]
0x1801796d3  lea     rdx, [rbp+phToken]
0x1801796d7  mov     rcx, rsi
0x1801796da  mov     [rbp+phToken], 0
0x1801796e2  call    cs:__imp_UMgrQueryUserToken
0x1801796e8  mov     ebx, eax
0x1801796ea  test    eax, eax
0x1801796ec  js      short loc_180179711
0x1801796ee  mov     rdx, [rbp+phToken]
0x1801796f2  lea     rcx, [rbp+var_28]
0x1801796f6  xor     eax, eax
0x1801796f8  mov     dword ptr [rbp+var_28], r14d
0x1801796fc  mov     r8, r15
0x1801796ff  mov     dword ptr [rbp+var_28+4], eax
0x180179702  mov     [rbp+var_20], rsi
0x180179706  call    CSessionUserHelper__CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___
0x18017970b  mov     ebx, eax
0x18017970d  inc     edi
0x18017970f  jmp     short loc_1801796AB
0x180179711  mov     edx, 7Bh ; '{'; void *
0x180179716  mov     rcx, [rbp+28h]; this
0x18017971a  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180179721  mov     r9d, ebx; char *
0x180179724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180179729  mov     rcx, [rbp+ppSessionInfo]
0x18017972d  test    rcx, rcx
0x180179730  jz      short loc_180179738
0x180179732  call    cs:__imp_UMgrFreeSessionUsers
0x180179738  mov     eax, ebx
0x18017973a  jmp     loc_1801797E1
0x18017973f  test    ebx, ebx
0x180179741  jnz     loc_1801797D0
0x180179747  lea     rcx, [rbp+var_30]
0x18017974b  mov     [rbp+var_30], 0
0x180179753  call    cs:__imp_UMgrQueryDefaultAccountToken
0x180179759  test    eax, eax
0x18017975b  js      short loc_1801797D0
0x18017975d  lea     rcx, [rbp+phToken]
0x180179761  mov     dword ptr [rbp+phToken], ebx
0x180179764  call    cs:__imp_QueryActiveSession
0x18017976a  test    eax, eax
0x18017976c  jnz     short loc_180179787
0x18017976e  mov     rcx, [rbp+28h]; this
0x180179772  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180179779  mov     edx, 88h; void *
0x18017977e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180179783  mov     ebx, eax
0x180179785  jmp     short loc_180179729
0x180179787  mov     rcx, [rbp+var_30]
0x18017978b  lea     rdx, [rbp+var_28]
0x18017978f  mov     [rbp+var_28], 0
0x180179797  call    cs:__imp_UMgrQueryUserContext
0x18017979d  mov     ebx, eax
0x18017979f  test    eax, eax
0x1801797a1  jns     short loc_1801797AD
0x1801797a3  mov     edx, 8Bh
0x1801797a8  jmp     loc_180179716
0x1801797ad  mov     eax, dword ptr [rbp+phToken]
0x1801797b0  lea     rcx, [rbp+var_18]
0x1801797b4  mov     rdx, [rbp+var_30]
0x1801797b8  mov     r8, r15
0x1801797bb  mov     [rbp+var_18], eax
0x1801797be  xor     eax, eax
0x1801797c0  mov     [rbp+var_14], eax
0x1801797c3  mov     rax, [rbp+var_28]
0x1801797c7  mov     [rbp+var_10], rax
0x1801797cb  call    CSessionUserHelper__CallbackUserToken__lambda_aeaaf71cc9043e5f79cc1861797bc557___
0x1801797d0  mov     rcx, [rbp+ppSessionInfo]
0x1801797d4  test    rcx, rcx
0x1801797d7  jz      short loc_1801797DF
0x1801797d9  call    cs:__imp_UMgrFreeSessionUsers
0x1801797df  xor     eax, eax
0x1801797e1  mov     rbx, [rsp+60h+arg_8]
0x1801797e9  add     rsp, 60h
0x1801797ed  pop     r15
0x1801797ef  pop     r14
0x1801797f1  pop     rdi
0x1801797f2  pop     rsi
0x1801797f3  pop     rbp
0x1801797f4  retn
```
