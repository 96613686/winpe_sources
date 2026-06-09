# DmEnumUsers(_DmUserProfile * *,ulong *)

- ea: `0x180069b30`
- end: `0x180069ee4`
- name: `?DmEnumUsers@@YAJPEAPEAU_DmUserProfile@@PEAK@Z`
- size: `948`
- prototype: `__int64 __fastcall(struct _DmUserProfile **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800527b4`
- `0x180052ac4`
- `0x1800583e8`
- `0x180058420`
- `0x180069ae8`
- `0x180069b30`
- `0x18006c7c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069e8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069eac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069bd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069d56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069bd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069d56`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069cb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069e11`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069cb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069e11`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180069ec1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180069ec1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180069c40`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180069c40`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180069b8d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180069b8d`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180069de6`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180069de6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180069db9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180069db9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180069d2a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180069d2a`

## pseudocode

```c
__int64 __fastcall DmEnumUsers(struct _DmUserProfile **a1, unsigned int *a2)
{
  signed int UserSidFromToken; // ebx
  signed int v5; // eax
  __int64 v6; // rax
  struct _DmUserProfile *v7; // rax
  __int64 i; // rsi
  __int64 v9; // r15
  signed int LastError; // eax
  __int64 v11; // r9
  __int64 v12; // rax
  struct _DmUserProfile *v13; // rax
  unsigned int j; // esi
  __int64 v15; // r15
  __int64 v16; // rcx
  unsigned int v17; // r12d
  int v18; // edx
  void *v19; // rcx
  signed int v20; // eax
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-28h] BYREF
  void *phToken; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+50h] [rbp-10h] BYREF
  DWORD pCount; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+48h] BYREF

  UserSidFromToken = 0;
  Sid = 0;
  StringSid = 0;
  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      v6 = pCount;
      *a2 = pCount;
      if ( (_DWORD)v6 )
      {
        v7 = (struct _DmUserProfile *)LocalAlloc(0, 136 * v6);
        *a1 = v7;
        if ( v7 )
        {
          for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
          {
            v9 = 136LL * (unsigned int)i;
            *(_DWORD *)((char *)*a1 + v9 + 128) = ppSessionInfo[i].SessionId;
            *(_DWORD *)((char *)*a1 + v9 + 132) = ppSessionInfo[i].State;
            if ( WTSQueryUserToken(ppSessionInfo[i].SessionId, &phToken) )
            {
              UserSidFromToken = GetUserSidFromToken(phToken);
              if ( UserSidFromToken < 0 )
                break;
              if ( !ConvertSidToStringSidW(Sid, &StringSid) )
                goto LABEL_4;
              UserSidFromToken = StringCchCopyW((unsigned __int16 *)((char *)*a1 + v9), 0x40u, StringSid);
              if ( UserSidFromToken < 0 )
                break;
              LocalFree(StringSid);
              StringSid = 0;
            }
            else
            {
              LastError = GetLastError();
              v11 = (unsigned int)LastError;
              if ( LastError > 0 )
                v11 = (unsigned __int16)LastError | 0x80070000;
              UserSidFromToken = StringCchPrintfW((unsigned __int16 *)((char *)*a1 + v9), 0x40u, L"0x%08x", v11);
              if ( UserSidFromToken < 0 )
                break;
            }
          }
        }
        else
        {
          UserSidFromToken = -2147024882;
        }
      }
    }
    else
    {
LABEL_4:
      v5 = GetLastError();
      UserSidFromToken = v5;
      if ( v5 > 0 )
        UserSidFromToken = (unsigned __int16)v5 | 0x80070000;
    }
  }
  else if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
         && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v28 = 0;
    v22 = 0;
    UserSidFromToken = UMgrEnumerateSessionUsers(&v28, &v22);
    if ( UserSidFromToken >= 0 )
    {
      v12 = v28;
      *a2 = v28;
      if ( (_DWORD)v12 )
      {
        v13 = (struct _DmUserProfile *)LocalAlloc(0, 136 * v12);
        *a1 = v13;
        if ( v13 )
        {
          for ( j = 0; j < v28; ++j )
          {
            v15 = 136LL * j;
            v16 = *(_QWORD *)(v22 + 16LL * j);
            v17 = *(_DWORD *)(v22 + 16LL * j + 8);
            v18 = *(_DWORD *)(v22 + 16LL * j + 12);
            *(_DWORD *)((char *)*a1 + v15 + 128) = v17;
            *(_DWORD *)((char *)*a1 + v15 + 132) = v18;
            UserSidFromToken = UMgrQueryUserToken(v16, &phToken);
            if ( UserSidFromToken < 0 )
              break;
            v19 = phToken;
            if ( (((unsigned __int64)phToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            {
              if ( !(unsigned int)QueryUserToken(v17, &phToken) )
                goto LABEL_37;
              v19 = phToken;
            }
            UserSidFromToken = GetUserSidFromToken(v19);
            if ( UserSidFromToken < 0 )
              break;
            if ( !ConvertSidToStringSidW(Sid, &StringSid) )
            {
LABEL_37:
              v20 = GetLastError();
              UserSidFromToken = v20;
              if ( v20 > 0 )
                UserSidFromToken = (unsigned __int16)v20 | 0x80070000;
              break;
            }
            UserSidFromToken = StringCchCopyW((unsigned __int16 *)((char *)*a1 + v15), 0x40u, StringSid);
            if ( UserSidFromToken < 0 )
              break;
            LocalFree(StringSid);
            StringSid = 0;
          }
        }
        else
        {
          UserSidFromToken = -2147024882;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
  }
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  LocalFree(StringSid);
  LocalFree(Sid);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)UserSidFromToken;
}

```

## disassembly

```asm
0x180069b30  mov     [rsp-28h+arg_0], rbx
0x180069b35  push    rbp
0x180069b36  push    rsi
0x180069b37  push    rdi
0x180069b38  push    r12
0x180069b3a  push    r15
0x180069b3c  mov     rbp, rsp
0x180069b3f  sub     rsp, 60h
0x180069b43  xor     ebx, ebx
0x180069b45  mov     rsi, rdx
0x180069b48  mov     [rbp+Sid], rbx
0x180069b4c  mov     rdi, rcx
0x180069b4f  mov     [rbp+StringSid], rbx
0x180069b53  mov     [rbp+ppSessionInfo], rbx
0x180069b57  mov     [rbp+arg_10], ebx
0x180069b5a  mov     [rbp+phToken], rbx
0x180069b5e  call    IsWTSEnumerateSessionsWPresent
0x180069b63  test    al, al
0x180069b65  jz      loc_180069D01
0x180069b6b  call    IsWTSEnumerateSessionsWPresent
0x180069b70  test    al, al
0x180069b72  jz      loc_180069D01
0x180069b78  lea     rax, [rbp+arg_10]
0x180069b7c  xor     edx, edx; Reserved
0x180069b7e  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180069b82  mov     [rsp+60h+pCount], rax; pCount
0x180069b87  xor     ecx, ecx; hServer
0x180069b89  lea     r8d, [rbx+1]; Version
0x180069b8d  call    cs:__imp_WTSEnumerateSessionsW
0x180069b94  nop     dword ptr [rax+rax+00h]
0x180069b99  test    eax, eax
0x180069b9b  jnz     short loc_180069BC1
0x180069b9d  call    cs:__imp_GetLastError
0x180069ba4  nop     dword ptr [rax+rax+00h]
0x180069ba9  mov     ebx, eax
0x180069bab  test    eax, eax
0x180069bad  jle     loc_180069E7E
0x180069bb3  movzx   ebx, ax
0x180069bb6  or      ebx, 80070000h
0x180069bbc  jmp     loc_180069E7E
0x180069bc1  mov     eax, [rbp+arg_10]
0x180069bc4  mov     [rsi], eax
0x180069bc6  test    eax, eax
0x180069bc8  jz      loc_180069E7E
0x180069bce  imul    rdx, rax, 88h; uBytes
0x180069bd5  xor     ecx, ecx; uFlags
0x180069bd7  call    cs:__imp_LocalAlloc
0x180069bde  nop     dword ptr [rax+rax+00h]
0x180069be3  mov     [rdi], rax
0x180069be6  test    rax, rax
0x180069be9  jnz     short loc_180069BF5
0x180069beb  mov     ebx, 8007000Eh
0x180069bf0  jmp     loc_180069E7E
0x180069bf5  xor     esi, esi
0x180069bf7  cmp     esi, [rbp+arg_10]
0x180069bfa  jnb     loc_180069E7E
0x180069c00  mov     rdx, [rdi]
0x180069c03  lea     r8, [rsi+rsi*2]
0x180069c07  mov     eax, esi
0x180069c09  imul    r15, rax, 88h
0x180069c10  mov     rax, [rbp+ppSessionInfo]
0x180069c14  mov     ecx, [rax+r8*8]
0x180069c18  mov     [r15+rdx+80h], ecx
0x180069c20  mov     rax, [rbp+ppSessionInfo]
0x180069c24  mov     rdx, [rdi]
0x180069c27  mov     ecx, [rax+r8*8+10h]
0x180069c2c  mov     [r15+rdx+84h], ecx
0x180069c34  lea     rdx, [rbp+phToken]; phToken
0x180069c38  mov     rcx, [rbp+ppSessionInfo]
0x180069c3c  mov     ecx, [rcx+r8*8]; SessionId
0x180069c40  call    cs:__imp_WTSQueryUserToken
0x180069c47  nop     dword ptr [rax+rax+00h]
0x180069c4c  test    eax, eax
0x180069c4e  jnz     short loc_180069C91
0x180069c50  call    cs:__imp_GetLastError
0x180069c57  nop     dword ptr [rax+rax+00h]
0x180069c5c  mov     r9d, eax
0x180069c5f  test    eax, eax
0x180069c61  jle     short loc_180069C6E
0x180069c63  movzx   r9d, ax
0x180069c67  or      r9d, 80070000h
0x180069c6e  mov     rcx, [rdi]
0x180069c71  lea     r8, a0x08x_0; "0x%08x"
0x180069c78  add     rcx, r15; unsigned __int16 *
0x180069c7b  mov     edx, 40h ; '@'; unsigned __int64
0x180069c80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180069c85  mov     ebx, eax
0x180069c87  test    eax, eax
0x180069c89  js      loc_180069E7E
0x180069c8f  jmp     short loc_180069CFA
0x180069c91  mov     rcx, [rbp+phToken]; TokenHandle
0x180069c95  lea     rdx, [rbp+Sid]
0x180069c99  call    GetUserSidFromToken
0x180069c9e  mov     ebx, eax
0x180069ca0  test    eax, eax
0x180069ca2  js      loc_180069E7E
0x180069ca8  mov     rcx, [rbp+Sid]; Sid
0x180069cac  lea     rdx, [rbp+StringSid]; StringSid
0x180069cb0  call    cs:__imp_ConvertSidToStringSidW
0x180069cb7  nop     dword ptr [rax+rax+00h]
0x180069cbc  test    eax, eax
0x180069cbe  jz      loc_180069B9D
0x180069cc4  mov     rcx, [rdi]
0x180069cc7  mov     edx, 40h ; '@'; unsigned __int64
0x180069ccc  mov     r8, [rbp+StringSid]; unsigned __int16 *
0x180069cd0  add     rcx, r15; unsigned __int16 *
0x180069cd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069cd8  mov     ebx, eax
0x180069cda  test    eax, eax
0x180069cdc  js      loc_180069E7E
0x180069ce2  mov     rcx, [rbp+StringSid]; hMem
0x180069ce6  call    cs:__imp_LocalFree
0x180069ced  nop     dword ptr [rax+rax+00h]
0x180069cf2  mov     [rbp+StringSid], 0
0x180069cfa  inc     esi
0x180069cfc  jmp     loc_180069BF7
0x180069d01  call    IsUMgrEnumerateSessionUsersPresent
0x180069d06  test    al, al
0x180069d08  jz      loc_180069E7E
0x180069d0e  call    IsUMgrEnumerateSessionUsersPresent
0x180069d13  test    al, al
0x180069d15  jz      loc_180069E7E
0x180069d1b  lea     rdx, [rbp+var_30]
0x180069d1f  mov     [rbp+arg_18], ebx
0x180069d22  lea     rcx, [rbp+arg_18]
0x180069d26  mov     [rbp+var_30], rbx
0x180069d2a  call    cs:__imp_UMgrEnumerateSessionUsers
0x180069d31  nop     dword ptr [rax+rax+00h]
0x180069d36  mov     ebx, eax
0x180069d38  test    eax, eax
0x180069d3a  js      loc_180069E75
0x180069d40  mov     eax, [rbp+arg_18]
0x180069d43  mov     [rsi], eax
0x180069d45  test    eax, eax
0x180069d47  jz      loc_180069E75
0x180069d4d  imul    rdx, rax, 88h; uBytes
0x180069d54  xor     ecx, ecx; uFlags
0x180069d56  call    cs:__imp_LocalAlloc
0x180069d5d  nop     dword ptr [rax+rax+00h]
0x180069d62  mov     [rdi], rax
0x180069d65  test    rax, rax
0x180069d68  jnz     short loc_180069D74
0x180069d6a  mov     ebx, 8007000Eh
0x180069d6f  jmp     loc_180069E75
0x180069d74  xor     esi, esi
0x180069d76  cmp     esi, [rbp+arg_18]
0x180069d79  jnb     loc_180069E75
0x180069d7f  mov     rax, [rbp+var_30]
0x180069d83  mov     r8d, esi
0x180069d86  imul    r15, r8, 88h
0x180069d8d  mov     edx, esi
0x180069d8f  add     rdx, rdx
0x180069d92  mov     rcx, [rax+rdx*8]
0x180069d96  mov     r12d, [rax+rdx*8+8]
0x180069d9b  mov     edx, [rax+rdx*8+0Ch]
0x180069d9f  mov     rax, [rdi]
0x180069da2  mov     [r15+rax+80h], r12d
0x180069daa  mov     rax, [rdi]
0x180069dad  mov     [r15+rax+84h], edx
0x180069db5  lea     rdx, [rbp+phToken]
0x180069db9  call    cs:__imp_UMgrQueryUserToken
0x180069dc0  nop     dword ptr [rax+rax+00h]
0x180069dc5  mov     ebx, eax
0x180069dc7  test    eax, eax
0x180069dc9  js      loc_180069E75
0x180069dcf  mov     rcx, [rbp+phToken]
0x180069dd3  lea     rax, [rcx+1]
0x180069dd7  test    rax, 0FFFFFFFFFFFFFFFEh
0x180069ddd  jnz     short loc_180069DFA
0x180069ddf  lea     rdx, [rbp+phToken]
0x180069de3  mov     ecx, r12d
0x180069de6  call    cs:__imp_QueryUserToken
0x180069ded  nop     dword ptr [rax+rax+00h]
0x180069df2  test    eax, eax
0x180069df4  jz      short loc_180069E5A
0x180069df6  mov     rcx, [rbp+phToken]; TokenHandle
0x180069dfa  lea     rdx, [rbp+Sid]
0x180069dfe  call    GetUserSidFromToken
0x180069e03  mov     ebx, eax
0x180069e05  test    eax, eax
0x180069e07  js      short loc_180069E75
0x180069e09  mov     rcx, [rbp+Sid]; Sid
0x180069e0d  lea     rdx, [rbp+StringSid]; StringSid
0x180069e11  call    cs:__imp_ConvertSidToStringSidW
0x180069e18  nop     dword ptr [rax+rax+00h]
0x180069e1d  test    eax, eax
0x180069e1f  jz      short loc_180069E5A
0x180069e21  mov     rcx, [rdi]
0x180069e24  mov     edx, 40h ; '@'; unsigned __int64
0x180069e29  mov     r8, [rbp+StringSid]; unsigned __int16 *
0x180069e2d  add     rcx, r15; unsigned __int16 *
0x180069e30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069e35  mov     ebx, eax
0x180069e37  test    eax, eax
0x180069e39  js      short loc_180069E75
0x180069e3b  mov     rcx, [rbp+StringSid]; hMem
0x180069e3f  call    cs:__imp_LocalFree
0x180069e46  nop     dword ptr [rax+rax+00h]
0x180069e4b  inc     esi
0x180069e4d  mov     [rbp+StringSid], 0
0x180069e55  jmp     loc_180069D76
0x180069e5a  call    cs:__imp_GetLastError
0x180069e61  nop     dword ptr [rax+rax+00h]
0x180069e66  mov     ebx, eax
0x180069e68  test    eax, eax
0x180069e6a  jle     short loc_180069E75
0x180069e6c  movzx   ebx, ax
0x180069e6f  or      ebx, 80070000h
0x180069e75  lea     rcx, [rbp+var_30]
0x180069e79  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180069e7e  mov     rcx, [rbp+phToken]; hObject
0x180069e82  lea     rax, [rcx-1]
0x180069e86  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180069e8a  ja      short loc_180069E98
0x180069e8c  call    cs:__imp_CloseHandle
0x180069e93  nop     dword ptr [rax+rax+00h]
0x180069e98  mov     rcx, [rbp+StringSid]; hMem
0x180069e9c  call    cs:__imp_LocalFree
0x180069ea3  nop     dword ptr [rax+rax+00h]
0x180069ea8  mov     rcx, [rbp+Sid]; hMem
0x180069eac  call    cs:__imp_LocalFree
0x180069eb3  nop     dword ptr [rax+rax+00h]
0x180069eb8  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180069ebc  test    rcx, rcx
0x180069ebf  jz      short loc_180069ECD
0x180069ec1  call    cs:__imp_WTSFreeMemory
0x180069ec8  nop     dword ptr [rax+rax+00h]
0x180069ecd  mov     eax, ebx
0x180069ecf  mov     rbx, [rsp+60h+arg_0]
0x180069ed7  add     rsp, 60h
0x180069edb  pop     r15
0x180069edd  pop     r12
0x180069edf  pop     rdi
0x180069ee0  pop     rsi
0x180069ee1  pop     rbp
0x180069ee2  retn
```
