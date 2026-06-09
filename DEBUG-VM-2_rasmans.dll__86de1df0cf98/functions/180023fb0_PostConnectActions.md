# PostConnectActions

- ea: `0x180023fb0`
- end: `0x1800244ea`
- name: `PostConnectActions`
- size: `1338`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035ea0`

## callees

- `0x180003404`
- `0x180003594`
- `0x180005e0c`
- `0x180005e34`
- `0x180023fb0`
- `0x18003ea70`
- `0x180040f08`
- `0x180041744`
- `0x180041828`
- `0x180050534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024224`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024307`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024224`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024311`
- `RPCRT4!RpcImpersonateClient` at `0x180024275`
- `RPCRT4!RpcImpersonateClient` at `0x180024275`
- `RPCRT4!RpcRevertToSelf` at `0x18002435d`
- `RPCRT4!RpcRevertToSelf` at `0x180024395`
- `RPCRT4!RpcRevertToSelf` at `0x18002435d`
- `RPCRT4!RpcRevertToSelf` at `0x180024395`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800241bd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800241bd`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024150`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002415e`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024150`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002415e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002413a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002413a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180024128`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180024128`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18002410d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18002410d`

## pseudocode

```c
int __fastcall PostConnectActions(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  int v5; // r14d
  __int64 Connection; // rax
  __int64 v7; // rsi
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // rbx
  int v12; // eax
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rdx
  DWORD v19; // eax
  HANDLE hExistingToken; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-8h] BYREF
  int v23; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 413, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  v4 = *(_QWORD *)(a3 + 8);
  v5 = 0;
  hExistingToken = 0;
  TokenHandle = 0;
  Connection = FindConnection(v4);
  v7 = Connection;
  if ( !Connection || !*(_QWORD *)(Connection + 56) )
  {
    v10 = 668;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_89;
    }
    v18 = 414;
    v17 = 668;
    goto LABEL_59;
  }
  v8 = g_RasMobileCore;
  if ( !g_RasMobileCore && (*(_DWORD *)(Connection + 112) & 0x100) == 0 )
  {
    LODWORD(Connection) = IsSystemOwnedConnection(Connection);
    if ( (_DWORD)Connection
      || (LODWORD(Connection) = IsRASConnectionOnWinLogon(v7), (_DWORD)Connection)
      || (LODWORD(Connection) = IsDemandDialRASConnection(v7), (_DWORD)Connection) )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        LODWORD(Connection) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 415, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      goto LABEL_89;
    }
    v8 = g_RasMobileCore;
  }
  if ( *(_DWORD *)(v7 + 860) == 2 )
  {
    v9 = **(_QWORD **)(v7 + 56);
    if ( *(_QWORD *)(v9 + 1240) )
    {
      TokenHandle = *(void **)(v9 + 1240);
LABEL_72:
      LODWORD(Connection) = ApplyPostConnectionActions(v7, TokenHandle);
      v10 = Connection;
      if ( !(_DWORD)Connection )
        goto LABEL_89;
      if ( !g_RasMobileCore && (*(_DWORD *)(v7 + 112) & 0x100) != 0 && (_DWORD)Connection == 5 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          LODWORD(Connection) = WPP_SF_d(
                                  WPP_GLOBAL_Control[1].Flink,
                                  423,
                                  WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                  5);
        }
        v10 = 0;
        goto LABEL_89;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_89;
      }
      v18 = 424;
      v17 = (unsigned int)Connection;
LABEL_59:
      LODWORD(Connection) = WPP_SF_d(v16[1].Flink, v18, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v17);
      goto LABEL_89;
    }
  }
  if ( v8 )
  {
    if ( !(unsigned __int8)IsQueryUserTokenPresent() )
      goto LABEL_32;
    if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
      goto LABEL_30;
    v23 = 0;
    v22 = 0;
    v11 = 0;
    if ( (int)UMgrEnumerateSessionUsers(&v23, &v22) >= 0 && v23 )
      v11 = *v22;
    if ( v22 )
      UMgrFreeSessionUsers(v22);
    if ( v11 )
      v12 = (int)UMgrQueryUserToken(v11, &hExistingToken) >= 0;
    else
LABEL_30:
      v12 = QueryUserToken(0, &hExistingToken);
    if ( !v12 )
    {
LABEL_32:
      LastError = GetLastError();
      if ( LastError
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 416, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
      }
    }
    if ( !DuplicateTokenEx(hExistingToken, 6u, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
    {
      v14 = GetLastError();
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 417, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v14);
        }
      }
    }
    goto LABEL_72;
  }
  if ( OpenProcessToken(*(HANDLE *)(v7 + 80), 2u, &TokenHandle) )
  {
    v5 = 1;
    goto LABEL_72;
  }
  v15 = GetLastError();
  if ( v15
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 418, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v15);
  }
  LODWORD(Connection) = RpcImpersonateClient(0);
  if ( (_DWORD)Connection )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
    {
      LODWORD(Connection) = WPP_SF_d(
                              WPP_GLOBAL_Control[1].Flink,
                              419,
                              WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                              (unsigned int)Connection);
      v16 = WPP_GLOBAL_Control;
    }
    v17 = 5;
    v10 = 5;
    if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v16[1].Blink) & 0x2000) != 0
      && BYTE1(v16[1].Blink) >= 2u )
    {
      v18 = 420;
      goto LABEL_59;
    }
  }
  else
  {
    if ( OpenProcessToken(*(HANDLE *)(v7 + 80), 2u, &TokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 422, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      RpcRevertToSelf();
      goto LABEL_72;
    }
    v19 = GetLastError();
    v10 = v19;
    if ( v19
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 421, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v19);
    }
    LODWORD(Connection) = RpcRevertToSelf();
  }
LABEL_89:
  if ( hExistingToken )
  {
    LODWORD(Connection) = CloseHandle(hExistingToken);
    hExistingToken = 0;
  }
  if ( TokenHandle && v5 == 1 )
  {
    LODWORD(Connection) = CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  *(_DWORD *)a3 = v10;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LODWORD(Connection) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 425, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  return Connection;
}

```

## disassembly

```asm
0x180023fb0  mov     [rsp-28h+arg_0], rbx
0x180023fb5  mov     [rsp-28h+arg_8], rsi
0x180023fba  push    rbp
0x180023fbb  push    rdi
0x180023fbc  push    r13
0x180023fbe  push    r14
0x180023fc0  push    r15
0x180023fc2  mov     rbp, rsp
0x180023fc5  sub     rsp, 40h
0x180023fc9  mov     r15, r8
0x180023fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fd3  lea     rbx, WPP_GLOBAL_Control
0x180023fda  mov     r13d, 2000h
0x180023fe0  cmp     rcx, rbx
0x180023fe3  jz      short loc_180024006
0x180023fe5  test    [rcx+1Ch], r13d
0x180023fe9  jz      short loc_180024006
0x180023feb  cmp     byte ptr [rcx+19h], 6
0x180023fef  jb      short loc_180024006
0x180023ff1  mov     rcx, [rcx+10h]
0x180023ff5  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023ffc  mov     edx, 19Dh
0x180024001  call    WPP_SF_
0x180024006  mov     rcx, [r15+8]
0x18002400a  xor     r14d, r14d
0x18002400d  mov     [rbp+hExistingToken], r14
0x180024011  mov     [rbp+TokenHandle], 0
0x180024019  call    FindConnection
0x18002401e  mov     rsi, rax
0x180024021  test    rax, rax
0x180024024  jz      loc_180024432
0x18002402a  cmp     [rax+38h], r14
0x18002402e  jz      loc_180024432
0x180024034  mov     edx, cs:g_RasMobileCore
0x18002403a  test    edx, edx
0x18002403c  jnz     short loc_180024071
0x18002403e  test    dword ptr [rax+70h], 100h
0x180024045  jnz     short loc_180024071
0x180024047  mov     rcx, rax
0x18002404a  call    IsSystemOwnedConnection
0x18002404f  test    eax, eax
0x180024051  jnz     short loc_18002409A
0x180024053  mov     rcx, rsi
0x180024056  call    IsRASConnectionOnWinLogon
0x18002405b  test    eax, eax
0x18002405d  jnz     short loc_18002409A
0x18002405f  mov     rcx, rsi
0x180024062  call    IsDemandDialRASConnection
0x180024067  test    eax, eax
0x180024069  jnz     short loc_18002409A
0x18002406b  mov     edx, cs:g_RasMobileCore
0x180024071  mov     edi, 2
0x180024076  cmp     [rsi+35Ch], edi
0x18002407c  jnz     short loc_1800240E1
0x18002407e  mov     rax, [rsi+38h]
0x180024082  mov     rcx, [rax]
0x180024085  mov     rax, [rcx+4D8h]
0x18002408c  test    rax, rax
0x18002408f  jz      short loc_1800240E1
0x180024091  mov     [rbp+TokenHandle], rax
0x180024095  jmp     loc_18002439B
0x18002409a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240a1  lea     rsi, WPP_GLOBAL_Control
0x1800240a8  xor     ebx, ebx
0x1800240aa  cmp     rcx, rsi
0x1800240ad  jz      loc_18002446F
0x1800240b3  test    [rcx+1Ch], r13d
0x1800240b7  jz      loc_18002446F
0x1800240bd  cmp     byte ptr [rcx+19h], 4
0x1800240c1  jb      loc_18002446F
0x1800240c7  mov     rcx, [rcx+10h]
0x1800240cb  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800240d2  mov     edx, 19Fh
0x1800240d7  call    WPP_SF_
0x1800240dc  jmp     loc_18002446F
0x1800240e1  test    edx, edx
0x1800240e3  jz      loc_18002421A
0x1800240e9  call    IsQueryUserTokenPresent
0x1800240ee  test    al, al
0x1800240f0  jz      short loc_180024168
0x1800240f2  call    IsUMgrEnumerateSessionUsersPresent
0x1800240f7  test    al, al
0x1800240f9  jz      short loc_180024158
0x1800240fb  lea     rdx, [rbp+var_8]
0x1800240ff  mov     [rbp+arg_10], r14d
0x180024103  lea     rcx, [rbp+arg_10]
0x180024107  mov     [rbp+var_8], r14
0x18002410b  xor     ebx, ebx
0x18002410d  call    cs:__imp_UMgrEnumerateSessionUsers
0x180024113  mov     rcx, [rbp+var_8]
0x180024117  test    eax, eax
0x180024119  js      short loc_180024123
0x18002411b  cmp     [rbp+arg_10], ebx
0x18002411e  jbe     short loc_180024123
0x180024120  mov     rbx, [rcx]
0x180024123  test    rcx, rcx
0x180024126  jz      short loc_18002412E
0x180024128  call    cs:__imp_UMgrFreeSessionUsers
0x18002412e  lea     rdx, [rbp+hExistingToken]
0x180024132  test    rbx, rbx
0x180024135  jz      short loc_18002414E
0x180024137  mov     rcx, rbx
0x18002413a  call    cs:__imp_UMgrQueryUserToken
0x180024140  not     eax
0x180024142  shr     eax, 1Fh
0x180024145  lea     rbx, WPP_GLOBAL_Control
0x18002414c  jmp     short loc_180024164
0x18002414e  xor     ecx, ecx
0x180024150  call    cs:__imp_QueryUserToken
0x180024156  jmp     short loc_180024145
0x180024158  lea     rdx, [rbp+hExistingToken]
0x18002415c  xor     ecx, ecx
0x18002415e  call    cs:__imp_QueryUserToken
0x180024164  test    eax, eax
0x180024166  jnz     short loc_1800241A2
0x180024168  call    cs:__imp_GetLastError
0x18002416e  test    eax, eax
0x180024170  jz      short loc_1800241A2
0x180024172  mov     rcx, cs:WPP_GLOBAL_Control
0x180024179  cmp     rcx, rbx
0x18002417c  jz      short loc_1800241A2
0x18002417e  test    [rcx+1Ch], r13d
0x180024182  jz      short loc_1800241A2
0x180024184  cmp     [rcx+19h], dil
0x180024188  jb      short loc_1800241A2
0x18002418a  mov     rcx, [rcx+10h]
0x18002418e  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180024195  mov     edx, 1A0h
0x18002419a  mov     r9d, eax
0x18002419d  call    WPP_SF_d
0x1800241a2  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x1800241a6  lea     rax, [rbp+TokenHandle]
0x1800241aa  xor     r8d, r8d; lpTokenAttributes
0x1800241ad  mov     [rsp+40h+phNewToken], rax; phNewToken
0x1800241b2  mov     r9d, edi; ImpersonationLevel
0x1800241b5  mov     [rsp+40h+TokenType], edi; TokenType
0x1800241b9  lea     edx, [r8+6]; dwDesiredAccess
0x1800241bd  call    cs:__imp_DuplicateTokenEx
0x1800241c3  test    eax, eax
0x1800241c5  jnz     loc_18002439B
0x1800241cb  call    cs:__imp_GetLastError
0x1800241d1  test    eax, eax
0x1800241d3  jz      loc_18002439B
0x1800241d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241e0  cmp     rcx, rbx
0x1800241e3  jz      loc_18002439B
0x1800241e9  test    [rcx+1Ch], r13d
0x1800241ed  jz      loc_18002439B
0x1800241f3  cmp     [rcx+19h], dil
0x1800241f7  jb      loc_18002439B
0x1800241fd  mov     rcx, [rcx+10h]
0x180024201  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180024208  mov     edx, 1A1h
0x18002420d  mov     r9d, eax
0x180024210  call    WPP_SF_d
0x180024215  jmp     loc_18002439B
0x18002421a  mov     rcx, [rsi+50h]; ProcessHandle
0x18002421e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180024222  mov     edx, edi; DesiredAccess
0x180024224  call    cs:__imp_OpenProcessToken
0x18002422a  test    eax, eax
0x18002422c  jz      short loc_180024239
0x18002422e  mov     r14d, 1
0x180024234  jmp     loc_18002439B
0x180024239  call    cs:__imp_GetLastError
0x18002423f  test    eax, eax
0x180024241  jz      short loc_180024273
0x180024243  mov     rcx, cs:WPP_GLOBAL_Control
0x18002424a  cmp     rcx, rbx
0x18002424d  jz      short loc_180024273
0x18002424f  test    [rcx+1Ch], r13d
0x180024253  jz      short loc_180024273
0x180024255  cmp     [rcx+19h], dil
0x180024259  jb      short loc_180024273
0x18002425b  mov     rcx, [rcx+10h]
0x18002425f  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180024266  mov     edx, 1A2h
0x18002426b  mov     r9d, eax
0x18002426e  call    WPP_SF_d
0x180024273  xor     ecx, ecx; BindingHandle
0x180024275  call    cs:__imp_RpcImpersonateClient
0x18002427b  test    eax, eax
0x18002427d  jz      short loc_1800242FD
0x18002427f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024286  cmp     rcx, rbx
0x180024289  jz      short loc_1800242B6
0x18002428b  test    [rcx+1Ch], r13d
0x18002428f  jz      short loc_1800242B6
0x180024291  cmp     byte ptr [rcx+19h], 3
0x180024295  jb      short loc_1800242B6
0x180024297  mov     rcx, [rcx+10h]
0x18002429b  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800242a2  mov     edx, 1A3h
0x1800242a7  mov     r9d, eax
0x1800242aa  call    WPP_SF_d
0x1800242af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242b6  mov     r9d, 5
0x1800242bc  mov     ebx, r9d
0x1800242bf  lea     rsi, WPP_GLOBAL_Control
0x1800242c6  cmp     rcx, rsi
0x1800242c9  jz      loc_18002446F
0x1800242cf  test    [rcx+1Ch], r13d
0x1800242d3  jz      loc_18002446F
0x1800242d9  cmp     [rcx+19h], dil
0x1800242dd  jb      loc_18002446F
0x1800242e3  mov     edx, 1A4h
0x1800242e8  mov     rcx, [rcx+10h]
0x1800242ec  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800242f3  call    WPP_SF_d
0x1800242f8  jmp     loc_18002446F
0x1800242fd  mov     rcx, [rsi+50h]; ProcessHandle
0x180024301  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180024305  mov     edx, edi; DesiredAccess
0x180024307  call    cs:__imp_OpenProcessToken
0x18002430d  test    eax, eax
0x18002430f  jnz     short loc_180024368
0x180024311  call    cs:__imp_GetLastError
0x180024317  mov     ebx, eax
0x180024319  test    eax, eax
0x18002431b  jz      short loc_180024356
0x18002431d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024324  lea     rsi, WPP_GLOBAL_Control
0x18002432b  cmp     rcx, rsi
0x18002432e  jz      short loc_18002435D
0x180024330  test    [rcx+1Ch], r13d
0x180024334  jz      short loc_18002435D
0x180024336  cmp     [rcx+19h], dil
0x18002433a  jb      short loc_18002435D
0x18002433c  mov     rcx, [rcx+10h]
0x180024340  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180024347  mov     edx, 1A5h
0x18002434c  mov     r9d, eax
0x18002434f  call    WPP_SF_d
0x180024354  jmp     short loc_18002435D
0x180024356  lea     rsi, WPP_GLOBAL_Control
0x18002435d  call    cs:__imp_RpcRevertToSelf
0x180024363  jmp     loc_18002446F
0x180024368  mov     rcx, cs:WPP_GLOBAL_Control
0x18002436f  cmp     rcx, rbx
0x180024372  jz      short loc_180024395
0x180024374  test    [rcx+1Ch], r13d
0x180024378  jz      short loc_180024395
0x18002437a  cmp     byte ptr [rcx+19h], 4
0x18002437e  jb      short loc_180024395
0x180024380  mov     rcx, [rcx+10h]
0x180024384  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002438b  mov     edx, 1A6h
0x180024390  call    WPP_SF_
0x180024395  call    cs:__imp_RpcRevertToSelf
0x18002439b  mov     rdx, [rbp+TokenHandle]
0x18002439f  mov     rcx, rsi
0x1800243a2  call    ApplyPostConnectionActions
0x1800243a7  mov     ebx, eax
0x1800243a9  test    eax, eax
0x1800243ab  jz      loc_180024468
0x1800243b1  cmp     cs:g_RasMobileCore, 0
0x1800243b8  jnz     short loc_180024406
0x1800243ba  test    dword ptr [rsi+70h], 100h
0x1800243c1  jz      short loc_180024406
0x1800243c3  mov     r9d, 5
0x1800243c9  cmp     eax, r9d
0x1800243cc  jnz     short loc_180024406
0x1800243ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243d5  lea     rsi, WPP_GLOBAL_Control
0x1800243dc  cmp     rcx, rsi
0x1800243df  jz      short loc_180024402
0x1800243e1  test    [rcx+1Ch], r13d
0x1800243e5  jz      short loc_180024402
0x1800243e7  cmp     [rcx+19h], dil
0x1800243eb  jb      short loc_180024402
0x1800243ed  mov     rcx, [rcx+10h]
0x1800243f1  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800243f8  mov     edx, 1A7h
0x1800243fd  call    WPP_SF_d
0x180024402  xor     ebx, ebx
0x180024404  jmp     short loc_18002446F
0x180024406  mov     rcx, cs:WPP_GLOBAL_Control
0x18002440d  lea     rsi, WPP_GLOBAL_Control
0x180024414  cmp     rcx, rsi
0x180024417  jz      short loc_18002446F
0x180024419  test    [rcx+1Ch], r13d
0x18002441d  jz      short loc_18002446F
0x18002441f  cmp     [rcx+19h], dil
0x180024423  jb      short loc_18002446F
0x180024425  mov     edx, 1A8h
0x18002442a  mov     r9d, eax
0x18002442d  jmp     loc_1800242E8
0x180024432  mov     ebx, 29Ch
0x180024437  mov     rcx, cs:WPP_GLOBAL_Control
0x18002443e  lea     rsi, WPP_GLOBAL_Control
0x180024445  cmp     rcx, rsi
0x180024448  jz      short loc_18002446F
0x18002444a  test    [rcx+1Ch], r13d
0x18002444e  jz      short loc_18002446F
0x180024450  mov     edi, 2
0x180024455  cmp     [rcx+19h], dil
0x180024459  jb      short loc_18002446F
0x18002445b  mov     edx, 19Eh
0x180024460  mov     r9d, ebx
0x180024463  jmp     loc_1800242E8
  ... truncated ...
```
