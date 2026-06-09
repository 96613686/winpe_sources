# CClientsMap::OpenClientConnection(CClientID const &)

- ea: `0x14005a86c`
- end: `0x14005adae`
- name: `?OpenClientConnection@CClientsMap@@QEAAKAEBVCClientID@@@Z`
- size: `1346`
- prototype: `__int64 __fastcall(CClientsMap *this, const struct CClientID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140059870`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14001034c`
- `0x140059b70`
- `0x14005a86c`
- `0x14005af4c`
- `0x140085204`
- `0x140085250`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005a902`
- `KERNEL32!GetLastError` at `0x14005a902`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005ac1a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005ac1a`
- `KERNEL32!EnterCriticalSection` at `0x14005a98d`
- `KERNEL32!EnterCriticalSection` at `0x14005ad1f`
- `KERNEL32!EnterCriticalSection` at `0x14005a98d`
- `KERNEL32!EnterCriticalSection` at `0x14005ad1f`
- `KERNEL32!LeaveCriticalSection` at `0x14005a9b6`
- `KERNEL32!LeaveCriticalSection` at `0x14005ad3b`
- `KERNEL32!LeaveCriticalSection` at `0x14005a9b6`
- `KERNEL32!LeaveCriticalSection` at `0x14005ad3b`
- `RPCRT4!I_RpcExceptionFilter` at `0x14008852c`
- `RPCRT4!I_RpcExceptionFilter` at `0x14008854e`
- `RPCRT4!I_RpcExceptionFilter` at `0x14008852c`
- `RPCRT4!I_RpcExceptionFilter` at `0x14008854e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14005aaaa`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14005aaaa`

## pseudocode

```c
__int64 __fastcall CClientsMap::OpenClientConnection(CClientsMap *this, const struct CClientID *a2)
{
  CClientsMap *v3; // rbx
  struct CClient *Client; // r15
  DWORD LastError; // eax
  DWORD v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  void *v9; // r14
  __int64 v10; // r12
  unsigned int Pointer; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  CMapDeviceId *v14; // rcx
  unsigned int v15; // eax
  CClientsMap *v16; // r12
  unsigned int v17; // r14d
  __int64 v19; // [rsp+48h] [rbp-B0h] BYREF
  int v20; // [rsp+50h] [rbp-A8h]
  int v21; // [rsp+54h] [rbp-A4h]
  unsigned int v22; // [rsp+58h] [rbp-A0h]
  struct CClient *v23; // [rsp+60h] [rbp-98h]
  CClientsMap *v24; // [rsp+68h] [rbp-90h]
  const struct CClientID *v25; // [rsp+70h] [rbp-88h]
  CClientsMap *v26; // [rsp+78h] [rbp-80h]
  RPC_SECURITY_QOS v27; // [rsp+80h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-68h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-48h]

  v25 = a2;
  v3 = g_pClientsMap;
  v26 = g_pClientsMap;
  v24 = g_pClientsMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  v19 = 0;
  Client = CClientsMap::FindClient(v3, a2);
  v23 = Client;
  if ( !Client )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 1168 )
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
          *(_QWORD *)a2);
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 66;
LABEL_53:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, LastError);
        return v6;
      }
    }
    return v6;
  }
  EnterCriticalSection(&g_CsClients);
  v9 = *(void **)Client;
  v10 = *((_QWORD *)Client + 19);
  v20 = *((_DWORD *)Client + 2);
  v21 = v20;
  LeaveCriticalSection(&g_CsClients);
  Pointer = (unsigned int)FAX_OpenConnection((__int64)v9, v10, (__int64)&v19).Pointer;
  v6 = Pointer;
  if ( !Pointer )
    goto LABEL_35;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, Pointer);
  }
  v12 = (unsigned int)FAX_OpenConnection((__int64)v9, v10, (__int64)&v19).Pointer;
  v6 = v12;
  if ( !v12 )
    goto LABEL_35;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v12);
  }
  *(_QWORD *)&SecurityQOS.Version = 1;
  SecurityQOS.IdentityTracking = 0;
  SecurityQOS.ImpersonationType = 2;
  v13 = RpcBindingSetAuthInfoExW(v9, 0, 1u, 0xAu, 0, 0, &SecurityQOS);
  v6 = v13;
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v13);
LABEL_35:
      v14 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v15 = (unsigned int)FAX_OpenConnection((__int64)v9, v10, (__int64)&v19).Pointer;
    v6 = v15;
    if ( !v15 )
      goto LABEL_35;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v15);
      goto LABEL_35;
    }
  }
  v16 = v26;
  if ( v6 )
  {
    if ( v14 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v14 + 2), 73, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v6);
  }
  else
  {
    if ( !v20 )
    {
      SecurityQOS = 0;
      v30 = 0;
      SecurityQOS.Version = 24;
      GetSystemTimeAsFileTime((LPFILETIME)&SecurityQOS.Capabilities);
      v30 = -4294967269LL;
      SecurityQOS.ImpersonationType = 0;
      v27 = SecurityQOS;
      v28 = -4294967269LL;
      v17 = (unsigned int)FAX_ClientEventQueue(v19, (__int128 *)&v27).Pointer;
      v22 = v17;
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v17);
        }
      }
    }
    EnterCriticalSection(&g_CsClients);
    *((_QWORD *)Client + 10) = v19;
    LeaveCriticalSection(&g_CsClients);
  }
  LastError = CClientsMap::ReleaseClient(v16, a2, 0);
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 76;
      goto LABEL_53;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14005a86c  push    rbx
0x14005a86e  push    rsi
0x14005a86f  push    r12
0x14005a871  push    r13
0x14005a873  push    r14
0x14005a875  push    r15
0x14005a877  sub     rsp, 0C8h
0x14005a87e  mov     rax, cs:__security_cookie
0x14005a885  xor     rax, rsp
0x14005a888  mov     [rsp+0F8h+var_40], rax
0x14005a890  mov     r13, rdx
0x14005a893  mov     [rsp+0F8h+var_88], rdx
0x14005a898  mov     rbx, cs:?g_pClientsMap@@3PEAVCClientsMap@@EA; CClientsMap * g_pClientsMap
0x14005a89f  mov     [rsp+0F8h+var_80], rbx
0x14005a8a4  mov     [rsp+0F8h+var_90], rbx
0x14005a8a9  lea     rsi, WPP_GLOBAL_Control
0x14005a8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a8b7  cmp     rcx, rsi
0x14005a8ba  jz      short loc_14005A8DD
0x14005a8bc  test    byte ptr [rcx+1Ch], 4
0x14005a8c0  jz      short loc_14005A8DD
0x14005a8c2  cmp     byte ptr [rcx+19h], 5
0x14005a8c6  jb      short loc_14005A8DD
0x14005a8c8  mov     edx, 41h ; 'A'
0x14005a8cd  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005a8d4  mov     rcx, [rcx+10h]
0x14005a8d8  call    WPP_SF_
0x14005a8dd  mov     [rsp+0F8h+var_B0], 0
0x14005a8e6  mov     rdx, r13; struct CClientID *
0x14005a8e9  mov     rcx, rbx; this
0x14005a8ec  call    ?FindClient@CClientsMap@@QEAAPEAVCClient@@AEBVCClientID@@@Z; CClientsMap::FindClient(CClientID const &)
0x14005a8f1  mov     r15, rax
0x14005a8f4  mov     [rsp+0F8h+var_98], rax
0x14005a8f9  test    rax, rax
0x14005a8fc  jnz     loc_14005A986
0x14005a902  call    cs:__imp_GetLastError
0x14005a909  nop     dword ptr [rax+rax+00h]
0x14005a90e  mov     ebx, eax
0x14005a910  cmp     eax, 490h
0x14005a915  jz      short loc_14005A944
0x14005a917  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a91e  cmp     rcx, rsi
0x14005a921  jz      loc_14005AD89
0x14005a927  test    byte ptr [rcx+1Ch], 4
0x14005a92b  jz      loc_14005AD89
0x14005a931  cmp     byte ptr [rcx+19h], 2
0x14005a935  jb      loc_14005AD89
0x14005a93b  lea     edx, [r15+42h]
0x14005a93f  jmp     loc_14005AD76
0x14005a944  xor     ebx, ebx
0x14005a946  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a94d  cmp     rcx, rsi
0x14005a950  jz      loc_14005AD89
0x14005a956  test    byte ptr [rcx+1Ch], 4
0x14005a95a  jz      loc_14005AD89
0x14005a960  cmp     byte ptr [rcx+19h], 3
0x14005a964  jb      loc_14005AD89
0x14005a96a  lea     edx, [rbx+43h]
0x14005a96d  mov     r9, [r13+0]
0x14005a971  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005a978  mov     rcx, [rcx+10h]
0x14005a97c  call    WPP_SF_i
0x14005a981  jmp     loc_14005AD89
0x14005a986  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005a98d  call    cs:__imp_EnterCriticalSection
0x14005a994  nop     dword ptr [rax+rax+00h]
0x14005a999  mov     r14, [r15]
0x14005a99c  mov     r12, [r15+98h]
0x14005a9a3  mov     eax, [r15+8]
0x14005a9a7  mov     [rsp+0F8h+var_A8], eax
0x14005a9ab  mov     [rsp+0F8h+var_A4], eax
0x14005a9af  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005a9b6  call    cs:__imp_LeaveCriticalSection
0x14005a9bd  nop     dword ptr [rax+rax+00h]
0x14005a9c2  nop
0x14005a9c3  lea     r8, [rsp+0F8h+var_B0]
0x14005a9c8  mov     rdx, r12
0x14005a9cb  mov     rcx, r14
0x14005a9ce  call    FAX_OpenConnection
0x14005a9d3  mov     ebx, eax
0x14005a9d5  mov     [rsp+0F8h+var_B8], eax
0x14005a9d9  test    eax, eax
0x14005a9db  jz      loc_14005AB3C
0x14005a9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9e8  cmp     rcx, rsi
0x14005a9eb  jz      short loc_14005AA11
0x14005a9ed  test    byte ptr [rcx+1Ch], 4
0x14005a9f1  jz      short loc_14005AA11
0x14005a9f3  cmp     byte ptr [rcx+19h], 3
0x14005a9f7  jb      short loc_14005AA11
0x14005a9f9  mov     edx, 44h ; 'D'
0x14005a9fe  mov     r9d, eax
0x14005aa01  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005aa08  mov     rcx, [rcx+10h]
0x14005aa0c  call    WPP_SF_d
0x14005aa11  lea     r8, [rsp+0F8h+var_B0]
0x14005aa16  mov     rdx, r12
0x14005aa19  mov     rcx, r14
0x14005aa1c  call    FAX_OpenConnection
0x14005aa21  mov     ebx, eax
0x14005aa23  mov     [rsp+0F8h+var_B8], eax
0x14005aa27  test    eax, eax
0x14005aa29  jz      loc_14005AB3C
0x14005aa2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa36  cmp     rcx, rsi
0x14005aa39  jz      short loc_14005AA5F
0x14005aa3b  test    byte ptr [rcx+1Ch], 4
0x14005aa3f  jz      short loc_14005AA5F
0x14005aa41  cmp     byte ptr [rcx+19h], 3
0x14005aa45  jb      short loc_14005AA5F
0x14005aa47  mov     edx, 45h ; 'E'
0x14005aa4c  mov     r9d, eax
0x14005aa4f  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005aa56  mov     rcx, [rcx+10h]
0x14005aa5a  call    WPP_SF_d
0x14005aa5f  mov     r8d, 1; AuthnLevel
0x14005aa65  mov     qword ptr [rsp+0F8h+var_58.Version], r8
0x14005aa6d  mov     [rsp+0F8h+var_58.IdentityTracking], 0
0x14005aa78  mov     [rsp+0F8h+var_58.ImpersonationType], 2
0x14005aa83  lea     rax, [rsp+0F8h+var_58]
0x14005aa8b  mov     [rsp+0F8h+SecurityQOS], rax; SecurityQOS
0x14005aa90  mov     [rsp+0F8h+AuthzSvc], 0; AuthzSvc
0x14005aa98  mov     [rsp+0F8h+AuthIdentity], 0; AuthIdentity
0x14005aaa1  xor     edx, edx; ServerPrincName
0x14005aaa3  lea     r9d, [r8+9]; AuthnSvc
0x14005aaa7  mov     rcx, r14; Binding
0x14005aaaa  call    cs:__imp_RpcBindingSetAuthInfoExW
0x14005aab1  nop     dword ptr [rax+rax+00h]
0x14005aab6  mov     ebx, eax
0x14005aab8  mov     [rsp+0F8h+var_B8], eax
0x14005aabc  test    eax, eax
0x14005aabe  jz      short loc_14005AAF2
0x14005aac0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aac7  cmp     rcx, rsi
0x14005aaca  jz      short loc_14005AB43
0x14005aacc  test    byte ptr [rcx+1Ch], 4
0x14005aad0  jz      short loc_14005AB43
0x14005aad2  cmp     byte ptr [rcx+19h], 2
0x14005aad6  jb      short loc_14005AB43
0x14005aad8  mov     edx, 46h ; 'F'
0x14005aadd  mov     r9d, eax
0x14005aae0  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005aae7  mov     rcx, [rcx+10h]
0x14005aaeb  call    WPP_SF_d
0x14005aaf0  jmp     short loc_14005AB3C
0x14005aaf2  lea     r8, [rsp+0F8h+var_B0]
0x14005aaf7  mov     rdx, r12
0x14005aafa  mov     rcx, r14
0x14005aafd  call    FAX_OpenConnection
0x14005ab02  mov     ebx, eax
0x14005ab04  mov     [rsp+0F8h+var_B8], eax
0x14005ab08  test    eax, eax
0x14005ab0a  jz      short loc_14005AB3C
0x14005ab0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab13  cmp     rcx, rsi
0x14005ab16  jz      short loc_14005AB43
0x14005ab18  test    byte ptr [rcx+1Ch], 4
0x14005ab1c  jz      short loc_14005AB43
0x14005ab1e  cmp     byte ptr [rcx+19h], 2
0x14005ab22  jb      short loc_14005AB43
0x14005ab24  mov     edx, 47h ; 'G'
0x14005ab29  mov     r9d, eax
0x14005ab2c  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005ab33  mov     rcx, [rcx+10h]
0x14005ab37  call    WPP_SF_d
0x14005ab3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab43  mov     eax, [rsp+0F8h+var_A8]
0x14005ab47  mov     r12, [rsp+0F8h+var_80]
0x14005ab4c  jmp     short loc_14005ABAC
0x14005ab4e  mov     ebx, eax
0x14005ab50  mov     [rsp+0F8h+var_B8], eax
0x14005ab54  lea     rax, WPP_GLOBAL_Control
0x14005ab5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab62  cmp     rcx, rax
0x14005ab65  jz      short loc_14005AB92
0x14005ab67  test    byte ptr [rcx+1Ch], 4
0x14005ab6b  jz      short loc_14005AB92
0x14005ab6d  cmp     byte ptr [rcx+19h], 2
0x14005ab71  jb      short loc_14005AB92
0x14005ab73  mov     edx, 48h ; 'H'
0x14005ab78  mov     r9d, ebx
0x14005ab7b  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005ab82  mov     rcx, [rcx+10h]
0x14005ab86  call    WPP_SF_d
0x14005ab8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab92  lea     rsi, WPP_GLOBAL_Control
0x14005ab99  mov     r15, [rsp+0F8h+var_98]
0x14005ab9e  mov     r12, [rsp+0F8h+var_90]
0x14005aba3  mov     r13, [rsp+0F8h+var_88]
0x14005aba8  mov     eax, [rsp+0F8h+var_A4]
0x14005abac  test    ebx, ebx
0x14005abae  jz      short loc_14005ABEA
0x14005abb0  cmp     rcx, rsi
0x14005abb3  jz      loc_14005AD47
0x14005abb9  test    byte ptr [rcx+1Ch], 4
0x14005abbd  jz      loc_14005AD47
0x14005abc3  cmp     byte ptr [rcx+19h], 2
0x14005abc7  jb      loc_14005AD47
0x14005abcd  mov     edx, 49h ; 'I'
0x14005abd2  mov     r9d, ebx
0x14005abd5  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005abdc  mov     rcx, [rcx+10h]
0x14005abe0  call    WPP_SF_d
0x14005abe5  jmp     loc_14005AD47
0x14005abea  test    eax, eax
0x14005abec  jnz     loc_14005AD18
0x14005abf2  xorps   xmm0, xmm0
0x14005abf5  xor     eax, eax
0x14005abf7  movups  xmmword ptr [rsp+0F8h+var_58.Version], xmm0
0x14005abff  mov     [rsp+0F8h+var_48], rax
0x14005ac07  mov     [rsp+0F8h+var_58.Version], 18h
0x14005ac12  lea     rcx, [rsp+0F8h+var_58.Capabilities]; lpSystemTimeAsFileTime
0x14005ac1a  call    cs:__imp_GetSystemTimeAsFileTime
0x14005ac21  nop     dword ptr [rax+rax+00h]
0x14005ac26  mov     dword ptr [rsp+0F8h+var_48], 1Bh
0x14005ac31  mov     [rsp+0F8h+var_58.ImpersonationType], 0
0x14005ac3c  mov     dword ptr [rsp+0F8h+var_48+4], 0FFFFFFFFh
0x14005ac47  movups  xmm0, xmmword ptr [rsp+0F8h+var_58.Version]
0x14005ac4f  movaps  [rsp+0F8h+var_78], xmm0
0x14005ac57  movsd   xmm1, [rsp+0F8h+var_48]
0x14005ac60  movsd   [rsp+0F8h+var_68], xmm1
0x14005ac69  lea     rdx, [rsp+0F8h+var_78]
0x14005ac71  mov     rcx, [rsp+0F8h+var_B0]
0x14005ac76  call    FAX_ClientEventQueue
0x14005ac7b  mov     r14d, eax
0x14005ac7e  mov     [rsp+0F8h+var_A0], eax
0x14005ac82  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac89  jmp     short loc_14005ACEA
0x14005ac8b  mov     r14d, eax
0x14005ac8e  mov     [rsp+0F8h+var_A0], eax
0x14005ac92  lea     rax, WPP_GLOBAL_Control
0x14005ac99  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aca0  cmp     rcx, rax
0x14005aca3  jz      short loc_14005ACD0
0x14005aca5  test    byte ptr [rcx+1Ch], 4
0x14005aca9  jz      short loc_14005ACD0
0x14005acab  cmp     byte ptr [rcx+19h], 2
0x14005acaf  jb      short loc_14005ACD0
0x14005acb1  mov     edx, 4Ah ; 'J'
0x14005acb6  mov     r9d, r14d
0x14005acb9  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005acc0  mov     rcx, [rcx+10h]
0x14005acc4  call    WPP_SF_d
0x14005acc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005acd0  lea     rsi, WPP_GLOBAL_Control
0x14005acd7  mov     ebx, [rsp+0F8h+var_B8]
0x14005acdb  mov     r15, [rsp+0F8h+var_98]
0x14005ace0  mov     r12, [rsp+0F8h+var_90]
0x14005ace5  mov     r13, [rsp+0F8h+var_88]
0x14005acea  test    r14d, r14d
0x14005aced  jz      short loc_14005AD18
0x14005acef  cmp     rcx, rsi
0x14005acf2  jz      short loc_14005AD18
0x14005acf4  test    byte ptr [rcx+1Ch], 4
0x14005acf8  jz      short loc_14005AD18
0x14005acfa  cmp     byte ptr [rcx+19h], 2
0x14005acfe  jb      short loc_14005AD18
0x14005ad00  mov     edx, 4Bh ; 'K'
0x14005ad05  mov     r9d, r14d
0x14005ad08  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005ad0f  mov     rcx, [rcx+10h]
0x14005ad13  call    WPP_SF_d
0x14005ad18  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005ad1f  call    cs:__imp_EnterCriticalSection
0x14005ad26  nop     dword ptr [rax+rax+00h]
0x14005ad2b  mov     rax, [rsp+0F8h+var_B0]
0x14005ad30  mov     [r15+50h], rax
0x14005ad34  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005ad3b  call    cs:__imp_LeaveCriticalSection
0x14005ad42  nop     dword ptr [rax+rax+00h]
0x14005ad47  xor     r8d, r8d; int
0x14005ad4a  mov     rdx, r13; struct CClientID *
0x14005ad4d  mov     rcx, r12; this
0x14005ad50  call    ?ReleaseClient@CClientsMap@@QEAAKAEBVCClientID@@H@Z; CClientsMap::ReleaseClient(CClientID const &,int)
0x14005ad55  test    eax, eax
0x14005ad57  jz      short loc_14005AD89
0x14005ad59  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad60  cmp     rcx, rsi
0x14005ad63  jz      short loc_14005AD89
0x14005ad65  test    byte ptr [rcx+1Ch], 4
0x14005ad69  jz      short loc_14005AD89
0x14005ad6b  cmp     byte ptr [rcx+19h], 2
0x14005ad6f  jb      short loc_14005AD89
0x14005ad71  mov     edx, 4Ch ; 'L'
0x14005ad76  mov     r9d, eax
0x14005ad79  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005ad80  mov     rcx, [rcx+10h]
0x14005ad84  call    WPP_SF_d
0x14005ad89  mov     eax, ebx
0x14005ad8b  mov     rcx, [rsp+0F8h+var_40]
0x14005ad93  xor     rcx, rsp; StackCookie
0x14005ad96  call    __security_check_cookie
0x14005ad9b  add     rsp, 0C8h
0x14005ada2  pop     r15
0x14005ada4  pop     r14
0x14005ada6  pop     r13
0x14005ada8  pop     r12
0x14005adaa  pop     rsi
0x14005adab  pop     rbx
0x14005adac  retn
  ... truncated ...
```
