# NcbRegistrarpGetApplicationParams

- ea: `0x18000c3f0`
- end: `0x18000c76f`
- name: `NcbRegistrarpGetApplicationParams`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000add0`

## callees

- `0x180003ed0`
- `0x1800043f0`
- `0x180004dc0`
- `0x18000a0a0`
- `0x18000a160`
- `0x18000c3f0`
- `0x18000d2b4`
- `0x18000e40c`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c45a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c45a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c470`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c470`
- `RPCRT4!RpcRevertToSelf` at `0x18000c4d0`
- `RPCRT4!RpcRevertToSelf` at `0x18000c4d0`
- `RPCRT4!RpcImpersonateClient` at `0x18000c44c`
- `RPCRT4!RpcImpersonateClient` at `0x18000c44c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4c1`

## string_xrefs

- `0x18000c6b3`: `NcbReg: Failed to impersonate app`
- `0x18000c705`: `NcbReg: Failed to open app's thread`

## pseudocode

```c
__int64 __fastcall NcbRegistrarpGetApplicationParams(__int64 a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int ClientUserSid; // ebx
  void *v7; // rcx
  void *v8; // rcx
  unsigned int ApplicationPackageSid; // eax
  _QWORD *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rdx
  DWORD v15; // eax
  __int64 v16; // rdx
  PVOID v17; // rcx
  DWORD LastError; // eax
  __int64 v19; // rdx
  PVOID v20; // rcx
  PVOID v21; // rcx
  _BYTE v22[8]; // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v25[16]; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v26; // [rsp+58h] [rbp-28h]
  __int64 v27; // [rsp+60h] [rbp-20h]
  int *v28; // [rsp+68h] [rbp-18h]
  __int64 v29; // [rsp+70h] [rbp-10h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  TokenHandle = (void *)-1LL;
  v22[0] = 0;
  if ( !RpcImpersonateClient(0) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      ClientUserSid = LastError;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, LastError);
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v20, v19, L"NcbReg: Failed to open app's thread", ClientUserSid);
      goto LABEL_7;
    }
    v3 = HasModernIdentity(TokenHandle, v22);
    ClientUserSid = v3;
    if ( v3 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v3);
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v21,
          v4,
          L"NcbReg: Failed to query if the caller has modern identity",
          ClientUserSid);
      goto LABEL_7;
    }
    v7 = TokenHandle;
    *(_BYTE *)(a1 + 232) = v22[0];
    ClientUserSid = NcbUtilsGetClientUserSid(v7, (void **)(a1 + 272));
    if ( ClientUserSid )
    {
LABEL_7:
      v8 = TokenHandle;
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v24 = ClientUserSid;
        v26 = L"NcbReg: ApplicationParams were obtained with";
        v27 = 90;
        v28 = (int *)&v24;
        v29 = 4;
        McGenEventWrite_EventWriteTransfer(v8, NcbApiStatus, v5, 3, v25);
      }
      RpcRevertToSelf();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
          ClientUserSid);
      }
      return ClientUserSid;
    }
    ApplicationPackageSid = NcbRegistrarpGetApplicationPackageSid(a1, TokenHandle);
    ClientUserSid = ApplicationPackageSid;
    if ( ApplicationPackageSid )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 98;
        goto LABEL_29;
      }
    }
    else
    {
      ApplicationPackageSid = NcbUtilsGetPackageFullNameAndAppName(TokenHandle, a1 + 240, a1 + 248);
      ClientUserSid = ApplicationPackageSid;
      if ( !ApplicationPackageSid )
        goto LABEL_7;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 99;
LABEL_29:
        WPP_SF_d(v11[2], v14, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, ApplicationPackageSid);
      }
    }
    if ( *(_BYTE *)(a1 + 232) )
    {
      v12 = *(void **)(a1 + 272);
      if ( v12 )
      {
        VpnFree(v12);
        *(_QWORD *)(a1 + 272) = 0;
      }
      v13 = *(void **)(a1 + 256);
      if ( v13 )
      {
        VpnFree(v13);
        *(_QWORD *)(a1 + 256) = 0;
        *(_DWORD *)(a1 + 264) = 0;
      }
    }
    goto LABEL_7;
  }
  v15 = GetLastError();
  ClientUserSid = v15;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v15);
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v17, v16, L"NcbReg: Failed to impersonate app", ClientUserSid);
  return ClientUserSid;
}

```

## disassembly

```asm
0x18000c3f0  mov     [rsp-18h+arg_8], rbx
0x18000c3f5  mov     [rsp-18h+arg_10], rdi
0x18000c3fa  push    rbp
0x18000c3fb  push    r12
0x18000c3fd  push    r15
0x18000c3ff  mov     rbp, rsp
0x18000c402  sub     rsp, 80h
0x18000c409  mov     rax, cs:__security_cookie
0x18000c410  xor     rax, rsp
0x18000c413  mov     [rbp+var_8], rax
0x18000c417  mov     rdi, rcx
0x18000c41a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c421  lea     r15, WPP_GLOBAL_Control
0x18000c428  lea     r12, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000c42f  cmp     rcx, r15
0x18000c432  jz      short loc_18000C43E
0x18000c434  test    byte ptr [rcx+1Ch], 1
0x18000c438  jnz     loc_18000C64F
0x18000c43e  xor     ecx, ecx; BindingHandle
0x18000c440  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000c448  mov     [rbp+var_50], 0
0x18000c44c  call    cs:__imp_RpcImpersonateClient
0x18000c452  test    eax, eax
0x18000c454  jnz     loc_18000C66F
0x18000c45a  call    cs:__imp_GetCurrentThread
0x18000c460  mov     edx, 8; DesiredAccess
0x18000c465  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000c469  mov     rcx, rax; ThreadHandle
0x18000c46c  lea     r8d, [rdx-7]; OpenAsSelf
0x18000c470  call    cs:__imp_OpenThreadToken
0x18000c476  test    eax, eax
0x18000c478  jz      loc_18000C6C4
0x18000c47e  mov     rcx, [rbp+TokenHandle]
0x18000c482  lea     rdx, [rbp+var_50]
0x18000c486  call    HasModernIdentity
0x18000c48b  mov     ebx, eax
0x18000c48d  test    eax, eax
0x18000c48f  jnz     loc_18000C70E
0x18000c495  mov     al, [rbp+var_50]
0x18000c498  lea     rdx, [rdi+110h]
0x18000c49f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c4a3  mov     [rdi+0E8h], al
0x18000c4a9  call    NcbUtilsGetClientUserSid
0x18000c4ae  mov     ebx, eax
0x18000c4b0  test    eax, eax
0x18000c4b2  jz      loc_18000C571
0x18000c4b8  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c4bc  test    rcx, rcx
0x18000c4bf  jz      short loc_18000C4C7
0x18000c4c1  call    cs:__imp_CloseHandle
0x18000c4c7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000c4ce  jnz     short loc_18000C509
0x18000c4d0  call    cs:__imp_RpcRevertToSelf
0x18000c4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4dd  cmp     rcx, r15
0x18000c4e0  jnz     short loc_18000C54C
0x18000c4e2  mov     eax, ebx
0x18000c4e4  mov     rcx, [rbp+var_8]
0x18000c4e8  xor     rcx, rsp; StackCookie
0x18000c4eb  call    __security_check_cookie
0x18000c4f0  lea     r11, [rsp+80h+var_s0]
0x18000c4f8  mov     rbx, [r11+28h]
0x18000c4fc  mov     rdi, [r11+30h]
0x18000c500  mov     rsp, r11
0x18000c503  pop     r15
0x18000c505  pop     r12
0x18000c507  pop     rbp
0x18000c508  retn
0x18000c509  lea     rax, aNcbregApplicat; "NcbReg: ApplicationParams were obtained"...
0x18000c510  mov     [rbp+var_40], ebx
0x18000c513  mov     [rbp+var_28], rax
0x18000c517  lea     rdx, NcbApiStatus
0x18000c51e  lea     rax, [rbp+var_40]
0x18000c522  mov     [rbp+var_20], 5Ah ; 'Z'
0x18000c52a  mov     [rbp+var_18], rax
0x18000c52e  mov     r9d, 3
0x18000c534  lea     rax, [rbp+var_38]
0x18000c538  mov     [rbp+var_10], 4
0x18000c540  mov     [rsp+80h+var_60], rax
0x18000c545  call    McGenEventWrite_EventWriteTransfer
0x18000c54a  jmp     short loc_18000C4D0
0x18000c54c  test    byte ptr [rcx+1Ch], 1
0x18000c550  jz      short loc_18000C4E2
0x18000c552  cmp     byte ptr [rcx+19h], 6
0x18000c556  jb      short loc_18000C4E2
0x18000c558  mov     rcx, [rcx+10h]
0x18000c55c  mov     edx, 64h ; 'd'
0x18000c561  mov     r9d, ebx
0x18000c564  mov     r8, r12
0x18000c567  call    WPP_SF_d
0x18000c56c  jmp     loc_18000C4E2
0x18000c571  mov     rdx, [rbp+TokenHandle]
0x18000c575  mov     rcx, rdi
0x18000c578  call    NcbRegistrarpGetApplicationPackageSid
0x18000c57d  mov     ebx, eax
0x18000c57f  test    eax, eax
0x18000c581  jz      short loc_18000C5F1
0x18000c583  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c58a  cmp     rcx, r15
0x18000c58d  jz      short loc_18000C599
0x18000c58f  test    byte ptr [rcx+1Ch], 1
0x18000c593  jnz     loc_18000C75B
0x18000c599  cmp     byte ptr [rdi+0E8h], 0
0x18000c5a0  jz      loc_18000C4B8
0x18000c5a6  mov     rcx, [rdi+110h]; lpMem
0x18000c5ad  test    rcx, rcx
0x18000c5b0  jz      short loc_18000C5C2
0x18000c5b2  call    VpnFree
0x18000c5b7  mov     qword ptr [rdi+110h], 0
0x18000c5c2  mov     rcx, [rdi+100h]; lpMem
0x18000c5c9  test    rcx, rcx
0x18000c5cc  jz      loc_18000C4B8
0x18000c5d2  call    VpnFree
0x18000c5d7  mov     qword ptr [rdi+100h], 0
0x18000c5e2  mov     dword ptr [rdi+108h], 0
0x18000c5ec  jmp     loc_18000C4B8
0x18000c5f1  mov     rcx, [rbp+TokenHandle]
0x18000c5f5  lea     r8, [rdi+0F8h]
0x18000c5fc  lea     rdx, [rdi+0F0h]
0x18000c603  call    NcbUtilsGetPackageFullNameAndAppName
0x18000c608  mov     ebx, eax
0x18000c60a  test    eax, eax
0x18000c60c  jz      loc_18000C4B8
0x18000c612  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c619  cmp     rcx, r15
0x18000c61c  jz      loc_18000C599
0x18000c622  test    byte ptr [rcx+1Ch], 1
0x18000c626  jz      loc_18000C599
0x18000c62c  cmp     byte ptr [rcx+19h], 2
0x18000c630  jb      loc_18000C599
0x18000c636  mov     edx, 63h ; 'c'
0x18000c63b  mov     rcx, [rcx+10h]
0x18000c63f  mov     r9d, eax
0x18000c642  mov     r8, r12
0x18000c645  call    WPP_SF_d
0x18000c64a  jmp     loc_18000C599
0x18000c64f  cmp     byte ptr [rcx+19h], 6
0x18000c653  jb      loc_18000C43E
0x18000c659  mov     rcx, [rcx+10h]
0x18000c65d  mov     edx, 5Eh ; '^'
0x18000c662  mov     r8, r12
0x18000c665  call    WPP_SF_
0x18000c66a  jmp     loc_18000C43E
0x18000c66f  call    cs:__imp_GetLastError
0x18000c675  mov     ebx, eax
0x18000c677  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c67e  cmp     rcx, r15
0x18000c681  jz      short loc_18000C6A3
0x18000c683  test    byte ptr [rcx+1Ch], 1
0x18000c687  jz      short loc_18000C6A3
0x18000c689  cmp     byte ptr [rcx+19h], 2
0x18000c68d  jb      short loc_18000C6A3
0x18000c68f  mov     rcx, [rcx+10h]
0x18000c693  mov     edx, 5Fh ; '_'
0x18000c698  mov     r9d, eax
0x18000c69b  mov     r8, r12
0x18000c69e  call    WPP_SF_d
0x18000c6a3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000c6aa  jz      loc_18000C4E2
0x18000c6b0  mov     r9d, ebx
0x18000c6b3  lea     r8, aNcbregFailedTo_3; "NcbReg: Failed to impersonate app"
0x18000c6ba  call    McTemplateU0zq_EventWriteTransfer
0x18000c6bf  jmp     loc_18000C4E2
0x18000c6c4  call    cs:__imp_GetLastError
0x18000c6ca  mov     ebx, eax
0x18000c6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6d3  cmp     rcx, r15
0x18000c6d6  jz      short loc_18000C6F8
0x18000c6d8  test    byte ptr [rcx+1Ch], 1
0x18000c6dc  jz      short loc_18000C6F8
0x18000c6de  cmp     byte ptr [rcx+19h], 2
0x18000c6e2  jb      short loc_18000C6F8
0x18000c6e4  mov     rcx, [rcx+10h]
0x18000c6e8  mov     edx, 60h ; '`'
0x18000c6ed  mov     r9d, eax
0x18000c6f0  mov     r8, r12
0x18000c6f3  call    WPP_SF_d
0x18000c6f8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000c6ff  jz      loc_18000C4B8
0x18000c705  lea     r8, aNcbregFailedTo_2; "NcbReg: Failed to open app's thread"
0x18000c70c  jmp     short loc_18000C74E
0x18000c70e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c715  cmp     rcx, r15
0x18000c718  jz      short loc_18000C73A
0x18000c71a  test    byte ptr [rcx+1Ch], 1
0x18000c71e  jz      short loc_18000C73A
0x18000c720  cmp     byte ptr [rcx+19h], 2
0x18000c724  jb      short loc_18000C73A
0x18000c726  mov     rcx, [rcx+10h]
0x18000c72a  mov     edx, 61h ; 'a'
0x18000c72f  mov     r9d, ebx
0x18000c732  mov     r8, r12
0x18000c735  call    WPP_SF_d
0x18000c73a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000c741  jz      loc_18000C4B8
0x18000c747  lea     r8, aNcbregFailedTo_4; "NcbReg: Failed to query if the caller h"...
0x18000c74e  mov     r9d, ebx
0x18000c751  call    McTemplateU0zq_EventWriteTransfer
0x18000c756  jmp     loc_18000C4B8
0x18000c75b  cmp     byte ptr [rcx+19h], 2
0x18000c75f  jb      loc_18000C599
0x18000c765  mov     edx, 62h ; 'b'
0x18000c76a  jmp     loc_18000C63B
```
