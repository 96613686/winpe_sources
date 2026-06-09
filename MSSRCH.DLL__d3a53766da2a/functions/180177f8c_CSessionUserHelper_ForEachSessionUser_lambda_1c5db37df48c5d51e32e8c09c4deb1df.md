# CSessionUserHelper::ForEachSessionUser__lambda_1c5db37df48c5d51e32e8c09c4deb1df___

- ea: `0x180177f8c`
- end: `0x180178277`
- name: `CSessionUserHelper::ForEachSessionUser__lambda_1c5db37df48c5d51e32e8c09c4deb1df___`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180178b34`

## callees

- `0x18000f880`
- `0x1800f8f24`
- `0x180129d58`
- `0x18012a138`
- `0x180177f40`
- `0x180177f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178051`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180178022`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180178022`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801780c8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801780c8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180178047`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180178047`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180177fd1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180177fd1`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1801781e0`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1801781e0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18017815f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18017815f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801780ef`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801780ef`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180178086`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180178213`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180178086`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180178213`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1801781cf`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1801781cf`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801781b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180178253`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801781b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180178253`

## string_xrefs

- `0x180177fdf`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x180178102`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18017818f`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801781ee`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSessionUserHelper::ForEachSessionUser__lambda_1c5db37df48c5d51e32e8c09c4deb1df___(
        DWORD a1,
        __int64 a2)
{
  signed int v3; // ebx
  const char *v4; // r9
  __int64 i; // rdi
  ULONG SessionId; // esi
  WTS_CONNECTSTATE_CLASS State; // r14d
  signed int LastError; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  DWORD j; // edi
  __int64 v14; // rsi
  unsigned int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rdx
  const char *v18; // r9
  __int64 v19; // rcx
  int pCount; // [rsp+20h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  __int64 v23; // [rsp+40h] [rbp-30h]
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+48h] [rbp-28h]
  __int64 v25; // [rsp+50h] [rbp-20h]
  void **p_phToken; // [rsp+58h] [rbp-18h]
  char v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD v29; // [rsp+A0h] [rbp+30h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+B0h] [rbp+40h] BYREF
  void *phToken; // [rsp+B8h] [rbp+48h] BYREF

  v29 = a1;
  v3 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v29 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v29) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v4);
    p_ppSessionInfo = &ppSessionInfo;
    LOBYTE(v25) = 1;
    for ( i = 0; (unsigned int)i < v29; i = (unsigned int)(i + 1) )
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
          {
            v22 = SessionId;
            v23 = v21;
            v3 = CSessionUserHelper::CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___(v10, phToken, a2);
          }
        }
        else if ( v3 == -2147023584 )
        {
          v3 = 0;
        }
      }
    }
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    goto LABEL_42;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v29 = 0;
    phToken = 0;
    v11 = UMgrEnumerateSessionUsers(&v29, &phToken);
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
    v27 = 1;
    for ( j = 0; j < v29; ++j )
    {
      if ( v3 )
        goto LABEL_40;
      v14 = *((_QWORD *)phToken + 2 * j);
      if ( v14 )
      {
        v15 = *((_DWORD *)phToken + 4 * j + 2);
        ppSessionInfo = 0;
        v3 = UMgrQueryUserToken(v14, &ppSessionInfo);
        if ( v3 < 0 )
        {
          v17 = 123;
          goto LABEL_30;
        }
        v22 = v15;
        v23 = v14;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___(v16, ppSessionInfo, a2);
      }
    }
    if ( !v3 )
    {
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
                 v18);
          goto LABEL_31;
        }
        v22 = 0;
        v3 = UMgrQueryUserContext(v21, &v22);
        if ( v3 < 0 )
        {
          v17 = 139;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
            (const char *)(unsigned int)v3,
            pCount);
LABEL_31:
          if ( phToken )
            UMgrFreeSessionUsers();
          return (unsigned int)v3;
        }
        p_ppSessionInfo = (PWTS_SESSION_INFOW *)(unsigned int)ppSessionInfo;
        v25 = v22;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___(v19, v21, a2);
      }
    }
LABEL_40:
    if ( phToken )
      UMgrFreeSessionUsers();
LABEL_42:
    if ( v3 == 1 )
      return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180177f8c  mov     [rsp-28h+arg_8], rbx
0x180177f91  mov     [rsp-28h+arg_0], ecx
0x180177f95  push    rbp
0x180177f96  push    rsi
0x180177f97  push    rdi
0x180177f98  push    r14
0x180177f9a  push    r15
0x180177f9c  mov     rbp, rsp
0x180177f9f  sub     rsp, 70h
0x180177fa3  mov     r15, rdx
0x180177fa6  xor     ebx, ebx
0x180177fa8  call    IsWTSEnumerateSessionsWPresent
0x180177fad  test    al, al
0x180177faf  jz      loc_1801780D3
0x180177fb5  mov     [rbp+arg_0], ebx
0x180177fb8  mov     [rbp+ppSessionInfo], rbx
0x180177fbc  lea     rax, [rbp+arg_0]
0x180177fc0  mov     qword ptr [rsp+70h+pCount], rax; pCount
0x180177fc5  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180177fc9  xor     edx, edx; Reserved
0x180177fcb  xor     ecx, ecx; hServer
0x180177fcd  lea     r8d, [rbx+1]; Version
0x180177fd1  call    cs:__imp_WTSEnumerateSessionsW
0x180177fd7  test    eax, eax
0x180177fd9  jnz     short loc_180177FF3
0x180177fdb  mov     rcx, [rbp+28h]; this
0x180177fdf  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180177fe6  lea     edx, [rbx+26h]; void *
0x180177fe9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180177fee  jmp     loc_180178263
0x180177ff3  lea     rax, [rbp+ppSessionInfo]
0x180177ff7  mov     [rbp+var_28], rax
0x180177ffb  mov     byte ptr [rbp+var_20], 1
0x180177fff  xor     edi, edi
0x180178001  cmp     [rbp+arg_0], edi
0x180178004  jbe     loc_1801780BB
0x18017800a  test    ebx, ebx
0x18017800c  jnz     loc_1801780BB
0x180178012  lea     rcx, [rdi+rdi*2]
0x180178016  mov     rax, [rbp+ppSessionInfo]
0x18017801a  mov     esi, [rax+rcx*8]
0x18017801d  mov     r14d, [rax+rcx*8+10h]
0x180178022  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180178028  cmp     esi, eax
0x18017802a  jz      loc_1801780B0
0x180178030  test    r14d, 0FFFFFFFBh
0x180178037  jnz     short loc_1801780B0
0x180178039  mov     [rbp+phToken], 0
0x180178041  lea     rdx, [rbp+phToken]; phToken
0x180178045  mov     ecx, esi; SessionId
0x180178047  call    cs:__imp_WTSQueryUserToken
0x18017804d  test    eax, eax
0x18017804f  jnz     short loc_180178076
0x180178051  call    cs:__imp_GetLastError
0x180178057  mov     ebx, eax
0x180178059  test    eax, eax
0x18017805b  jle     short loc_180178066
0x18017805d  movzx   ebx, ax
0x180178060  or      ebx, 80070000h
0x180178066  test    ebx, ebx
0x180178068  jns     short loc_180178076
0x18017806a  cmp     ebx, 80070520h
0x180178070  jnz     short loc_1801780B0
0x180178072  xor     ebx, ebx
0x180178074  jmp     short loc_1801780B0
0x180178076  mov     [rbp+var_40], 0
0x18017807e  lea     rdx, [rbp+var_40]
0x180178082  mov     rcx, [rbp+phToken]
0x180178086  call    cs:__imp_UMgrQueryUserContext
0x18017808c  mov     ebx, eax
0x18017808e  test    eax, eax
0x180178090  js      short loc_1801780B0
0x180178092  mov     dword ptr [rbp+var_38], esi
0x180178095  xor     eax, eax
0x180178097  mov     dword ptr [rbp+var_38+4], eax
0x18017809a  mov     rax, [rbp+var_40]
0x18017809e  mov     [rbp+var_30], rax
0x1801780a2  mov     r8, r15
0x1801780a5  mov     rdx, [rbp+phToken]
0x1801780a9  call    CSessionUserHelper__CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___
0x1801780ae  mov     ebx, eax
0x1801780b0  inc     edi
0x1801780b2  cmp     edi, [rbp+arg_0]
0x1801780b5  jb      loc_18017800A
0x1801780bb  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x1801780bf  test    rcx, rcx
0x1801780c2  jz      loc_180178259
0x1801780c8  call    cs:__imp_WTSFreeMemory
0x1801780ce  jmp     loc_180178259
0x1801780d3  call    IsUMgrEnumerateSessionUsersPresent
0x1801780d8  test    al, al
0x1801780da  jz      loc_180178261
0x1801780e0  mov     [rbp+arg_0], ebx
0x1801780e3  mov     [rbp+phToken], rbx
0x1801780e7  lea     rdx, [rbp+phToken]
0x1801780eb  lea     rcx, [rbp+arg_0]
0x1801780ef  call    cs:__imp_UMgrEnumerateSessionUsers
0x1801780f5  mov     edi, eax
0x1801780f7  test    eax, eax
0x1801780f9  jns     short loc_18017811A
0x1801780fb  mov     rcx, [rbp+28h]; this
0x1801780ff  mov     r9d, eax; char *
0x180178102  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178109  mov     edx, 69h ; 'i'; void *
0x18017810e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178113  mov     eax, edi
0x180178115  jmp     loc_180178263
0x18017811a  lea     rax, [rbp+phToken]
0x18017811e  mov     [rbp+var_18], rax
0x180178122  mov     [rbp+var_10], 1
0x180178126  xor     edi, edi
0x180178128  cmp     edi, [rbp+arg_0]
0x18017812b  jnb     loc_1801781BB
0x180178131  test    ebx, ebx
0x180178133  jnz     loc_18017824A
0x180178139  mov     eax, edi
0x18017813b  add     rax, rax
0x18017813e  mov     rcx, [rbp+phToken]
0x180178142  mov     rsi, [rcx+rax*8]
0x180178146  test    rsi, rsi
0x180178149  jz      short loc_180178186
0x18017814b  mov     r14d, [rcx+rax*8+8]
0x180178150  mov     [rbp+ppSessionInfo], 0
0x180178158  lea     rdx, [rbp+ppSessionInfo]
0x18017815c  mov     rcx, rsi
0x18017815f  call    cs:__imp_UMgrQueryUserToken
0x180178165  mov     ebx, eax
0x180178167  test    eax, eax
0x180178169  js      short loc_18017818A
0x18017816b  mov     dword ptr [rbp+var_38], r14d
0x18017816f  xor     eax, eax
0x180178171  mov     dword ptr [rbp+var_38+4], eax
0x180178174  mov     [rbp+var_30], rsi
0x180178178  mov     r8, r15
0x18017817b  mov     rdx, [rbp+ppSessionInfo]
0x18017817f  call    CSessionUserHelper__CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___
0x180178184  mov     ebx, eax
0x180178186  inc     edi
0x180178188  jmp     short loc_180178128
0x18017818a  mov     edx, 7Bh ; '{'; void *
0x18017818f  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178196  mov     r9d, ebx; char *
0x180178199  mov     rcx, [rbp+28h]; this
0x18017819d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801781a2  nop
0x1801781a3  mov     rcx, [rbp+phToken]
0x1801781a7  test    rcx, rcx
0x1801781aa  jz      loc_180178261
0x1801781b0  call    cs:__imp_UMgrFreeSessionUsers
0x1801781b6  jmp     loc_180178261
0x1801781bb  test    ebx, ebx
0x1801781bd  jnz     loc_18017824A
0x1801781c3  mov     [rbp+var_40], 0
0x1801781cb  lea     rcx, [rbp+var_40]
0x1801781cf  call    cs:__imp_UMgrQueryDefaultAccountToken
0x1801781d5  test    eax, eax
0x1801781d7  js      short loc_18017824A
0x1801781d9  mov     dword ptr [rbp+ppSessionInfo], ebx
0x1801781dc  lea     rcx, [rbp+ppSessionInfo]
0x1801781e0  call    cs:__imp_QueryActiveSession
0x1801781e6  test    eax, eax
0x1801781e8  jnz     short loc_180178203
0x1801781ea  mov     rcx, [rbp+28h]; this
0x1801781ee  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801781f5  mov     edx, 88h; void *
0x1801781fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801781ff  mov     ebx, eax
0x180178201  jmp     short loc_1801781A3
0x180178203  mov     [rbp+var_38], 0
0x18017820b  lea     rdx, [rbp+var_38]
0x18017820f  mov     rcx, [rbp+var_40]
0x180178213  call    cs:__imp_UMgrQueryUserContext
0x180178219  mov     ebx, eax
0x18017821b  test    eax, eax
0x18017821d  jns     short loc_180178229
0x18017821f  mov     edx, 8Bh
0x180178224  jmp     loc_18017818F
0x180178229  mov     eax, dword ptr [rbp+ppSessionInfo]
0x18017822c  mov     dword ptr [rbp+var_28], eax
0x18017822f  xor     eax, eax
0x180178231  mov     dword ptr [rbp+var_28+4], eax
0x180178234  mov     rax, [rbp+var_38]
0x180178238  mov     [rbp+var_20], rax
0x18017823c  mov     r8, r15
0x18017823f  mov     rdx, [rbp+var_40]
0x180178243  call    CSessionUserHelper__CallbackUserToken__lambda_1c5db37df48c5d51e32e8c09c4deb1df___
0x180178248  mov     ebx, eax
0x18017824a  mov     rcx, [rbp+phToken]
0x18017824e  test    rcx, rcx
0x180178251  jz      short loc_180178259
0x180178253  call    cs:__imp_UMgrFreeSessionUsers
0x180178259  xor     eax, eax
0x18017825b  cmp     ebx, 1
0x18017825e  cmovz   ebx, eax
0x180178261  mov     eax, ebx
0x180178263  mov     rbx, [rsp+70h+arg_8]
0x18017826b  add     rsp, 70h
0x18017826f  pop     r15
0x180178271  pop     r14
0x180178273  pop     rdi
0x180178274  pop     rsi
0x180178275  pop     rbp
0x180178276  retn
```
