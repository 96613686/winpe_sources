# DmGetAllActiveUserSids(ushort * * *,ulong *)

- ea: `0x18006a150`
- end: `0x18006a64f`
- name: `?DmGetAllActiveUserSids@@YAJPEAPEAPEAGPEAK@Z`
- size: `1279`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800527b4`
- `0x180052ac4`
- `0x18005b44c`
- `0x18005d7f8`
- `0x18006990c`
- `0x180069ac4`
- `0x180069ae8`
- `0x18006a150`
- `0x18006c63c`
- `0x18006c7c8`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a5ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a1e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a34d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a5ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a5f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a1e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a34d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a5ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a5f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a3ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a3ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a5e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a30f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a59b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a30f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a59b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a3a5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a44a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a4d4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a3a5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a44a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a4d4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18006a2cb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18006a2cb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18006a243`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18006a243`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006a548`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006a548`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006a507`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006a507`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DmGetAllActiveUserSids(unsigned __int16 ***a1, unsigned int *a2)
{
  signed int CurrentUserSid; // ebx
  unsigned __int16 **v5; // rcx
  HLOCAL v6; // rcx
  signed int LastError; // eax
  DWORD i; // edi
  ULONG SessionId; // ecx
  BOOL v10; // ebx
  __int64 v11; // rcx
  unsigned __int16 **v13; // rdx
  unsigned __int64 v14; // rbx
  __int64 j; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rcx
  __int64 k; // r8
  signed int v19; // eax
  unsigned __int16 **v20; // rcx
  __int128 v21; // [rsp+30h] [rbp-39h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-21h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-19h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-11h] BYREF
  PSID Sid; // [rsp+60h] [rbp-9h]
  char v27; // [rsp+68h] [rbp-1h]
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+70h] [rbp+7h] BYREF
  char v29; // [rsp+78h] [rbp+Fh]
  HANDLE *p_TokenHandle; // [rsp+80h] [rbp+17h] BYREF
  void *phToken; // [rsp+88h] [rbp+1Fh] BYREF
  char v32; // [rsp+90h] [rbp+27h]
  DWORD pCount; // [rsp+D0h] [rbp+67h] BYREF
  WINBOOL IsMember; // [rsp+E0h] [rbp+77h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( a1 && a2 )
  {
    ppSessionInfo = 0;
    pCount = 0;
    TokenHandle = 0;
    IsMember = 0;
    StringSid = 0;
    *a2 = 0;
    CurrentUserSid = IsRunningInSystemContext(&IsMember);
    if ( CurrentUserSid < 0 )
      goto LABEL_35;
    if ( !IsMember )
    {
      hMem = 0;
      CurrentUserSid = GetCurrentUserSid(&hMem);
      if ( CurrentUserSid >= 0 )
      {
        v5 = (unsigned __int16 **)CoTaskMemAlloc(8u);
        if ( !v5 )
        {
          v6 = hMem;
LABEL_8:
          LocalFree(v6);
LABEL_9:
          CurrentUserSid = -2147024882;
          goto LABEL_35;
        }
        *v5 = (unsigned __int16 *)hMem;
        *a1 = v5;
        *a2 = 1;
        goto LABEL_11;
      }
LABEL_35:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return (unsigned int)CurrentUserSid;
    }
    if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    {
      if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_17;
      }
      p_ppSessionInfo = &ppSessionInfo;
      v29 = 1;
      v21 = 0;
      v22 = 0;
      for ( i = 0; i < pCount; ++i )
      {
        SessionId = ppSessionInfo[i].SessionId;
        if ( SessionId )
        {
          if ( ppSessionInfo[i].State == WTSActive )
          {
            p_TokenHandle = &TokenHandle;
            phToken = 0;
            v32 = 1;
            v10 = WTSQueryUserToken(SessionId, &phToken);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
            if ( v10 )
            {
              hMem = 0;
              if ( (int)GetUserSidFromToken(TokenHandle) >= 0 )
              {
                Sid = &hMem;
                v27 = 1;
                if ( ConvertSidToStringSidW(hMem, &StringSid) )
                {
                  if ( *((_QWORD *)&v21 + 1) == v22 )
                  {
                    std::vector<unsigned short *>::_Emplace_reallocate<unsigned short * const &>(
                      &v21,
                      *((_QWORD *)&v21 + 1),
                      &StringSid);
                  }
                  else
                  {
                    **((_QWORD **)&v21 + 1) = StringSid;
                    *((_QWORD *)&v21 + 1) += 8LL;
                  }
                }
                v27 = 0;
                LocalFree(hMem);
              }
            }
          }
        }
      }
      v11 = (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3;
      if ( v11 )
      {
        v13 = (unsigned __int16 **)CoTaskMemAlloc(8 * v11);
        if ( !v13 )
        {
          v14 = 0;
          for ( j = v21; v14 < (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3; j = v21 )
            LocalFree(*(HLOCAL *)(j + 8 * v14++));
          if ( j )
          {
            std::_Deallocate<16>(j, (v22 - j) & 0xFFFFFFFFFFFFFFF8uLL);
            v21 = 0;
            v22 = 0;
          }
          if ( ppSessionInfo )
            WTSFreeMemory(ppSessionInfo);
          goto LABEL_9;
        }
        v16 = 0;
        v17 = *((_QWORD *)&v21 + 1);
        for ( k = v21; v16 < (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3; k = v21 )
        {
          v13[v16] = *(unsigned __int16 **)(k + 8 * v16);
          ++v16;
          v17 = *((_QWORD *)&v21 + 1);
        }
        *a1 = v13;
        *a2 = (v17 - k) >> 3;
        if ( k )
        {
          std::_Deallocate<16>(k, (v22 - k) & 0xFFFFFFFFFFFFFFF8uLL);
          v21 = 0;
          v22 = 0;
        }
        if ( ppSessionInfo )
          WTSFreeMemory(ppSessionInfo);
        goto LABEL_11;
      }
      if ( (_QWORD)v21 )
      {
        std::_Deallocate<16>(v21, (v22 - v21) & 0xFFFFFFFFFFFFFFF8uLL);
        v21 = 0;
        v22 = 0;
      }
      if ( ppSessionInfo )
        WTSFreeMemory(ppSessionInfo);
    }
    else
    {
      if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
        && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
      {
        LODWORD(hMem) = 0;
        p_ppSessionInfo = 0;
        CurrentUserSid = UMgrEnumerateSessionUsers(&hMem, &p_ppSessionInfo);
        if ( CurrentUserSid < 0
          || (_DWORD)hMem
          && (p_TokenHandle = &TokenHandle,
              phToken = 0,
              v32 = 1,
              CurrentUserSid = UMgrQueryUserToken(*p_ppSessionInfo, &phToken),
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle),
              CurrentUserSid < 0) )
        {
          wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&p_ppSessionInfo);
          goto LABEL_35;
        }
        wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&p_ppSessionInfo);
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        Sid = 0;
        LastError = GetUserSidFromToken(TokenHandle);
        if ( LastError >= 0 )
        {
          if ( !ConvertSidToStringSidW(Sid, &StringSid) )
          {
            v19 = GetLastError();
            CurrentUserSid = v19;
            if ( v19 > 0 )
              CurrentUserSid = (unsigned __int16)v19 | 0x80070000;
            LocalFree(Sid);
            goto LABEL_35;
          }
          v20 = (unsigned __int16 **)CoTaskMemAlloc(8u);
          if ( !v20 )
          {
            LocalFree(StringSid);
            v6 = Sid;
            goto LABEL_8;
          }
          *v20 = StringSid;
          *a1 = v20;
          *a2 = 1;
          LocalFree(Sid);
LABEL_11:
          CurrentUserSid = 0;
          goto LABEL_35;
        }
LABEL_17:
        CurrentUserSid = LastError;
        goto LABEL_35;
      }
    }
    CurrentUserSid = -2102788088;
    goto LABEL_35;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18006a150  mov     [rsp-8+arg_8], rbx
0x18006a155  push    rbp
0x18006a156  push    rsi
0x18006a157  push    rdi
0x18006a158  push    r14
0x18006a15a  push    r15
0x18006a15c  lea     rbp, [rsp-37h]
0x18006a161  sub     rsp, 0A0h
0x18006a168  mov     rsi, rdx
0x18006a16b  mov     r14, rcx
0x18006a16e  xor     r15d, r15d
0x18006a171  test    rcx, rcx
0x18006a174  jz      loc_18006A632
0x18006a17a  test    rdx, rdx
0x18006a17d  jz      loc_18006A632
0x18006a183  mov     [rbp+57h+ppSessionInfo], r15
0x18006a187  mov     [rbp+57h+arg_0], r15d
0x18006a18b  mov     [rbp+57h+TokenHandle], r15
0x18006a18f  mov     [rbp+57h+IsMember], r15d
0x18006a193  mov     [rbp+57h+StringSid], r15
0x18006a197  mov     [rdx], r15d
0x18006a19a  lea     rcx, [rbp+57h+IsMember]; IsMember
0x18006a19e  call    IsRunningInSystemContext
0x18006a1a3  mov     ebx, eax
0x18006a1a5  test    eax, eax
0x18006a1a7  js      loc_18006A3B6
0x18006a1ad  cmp     [rbp+57h+IsMember], r15d
0x18006a1b1  jnz     short loc_18006A214
0x18006a1b3  mov     [rbp+57h+hMem], r15
0x18006a1b7  lea     rcx, [rbp+57h+hMem]
0x18006a1bb  call    GetCurrentUserSid
0x18006a1c0  mov     ebx, eax
0x18006a1c2  test    eax, eax
0x18006a1c4  js      loc_18006A3B6
0x18006a1ca  lea     ecx, [r15+8]; cb
0x18006a1ce  call    cs:__imp_CoTaskMemAlloc
0x18006a1d5  nop     dword ptr [rax+rax+00h]
0x18006a1da  mov     rcx, rax
0x18006a1dd  test    rax, rax
0x18006a1e0  jnz     short loc_18006A1FC
0x18006a1e2  mov     rcx, [rbp+57h+hMem]; hMem
0x18006a1e6  call    cs:__imp_LocalFree
0x18006a1ed  nop     dword ptr [rax+rax+00h]
0x18006a1f2  mov     ebx, 8007000Eh
0x18006a1f7  jmp     loc_18006A3B6
0x18006a1fc  mov     rax, [rbp+57h+hMem]
0x18006a200  mov     [rcx], rax
0x18006a203  mov     [r14], rcx
0x18006a206  mov     dword ptr [rsi], 1
0x18006a20c  mov     ebx, r15d
0x18006a20f  jmp     loc_18006A3B6
0x18006a214  call    IsWTSEnumerateSessionsWPresent
0x18006a219  test    al, al
0x18006a21b  jz      loc_18006A4E5
0x18006a221  call    IsWTSEnumerateSessionsWPresent
0x18006a226  test    al, al
0x18006a228  jz      loc_18006A4E5
0x18006a22e  lea     rax, [rbp+57h+arg_0]
0x18006a232  mov     [rsp+0C0h+pCount], rax; pCount
0x18006a237  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18006a23b  xor     edx, edx; Reserved
0x18006a23d  xor     ecx, ecx; hServer
0x18006a23f  lea     r8d, [rdx+1]; Version
0x18006a243  call    cs:__imp_WTSEnumerateSessionsW
0x18006a24a  nop     dword ptr [rax+rax+00h]
0x18006a24f  test    eax, eax
0x18006a251  jnz     short loc_18006A272
0x18006a253  call    cs:__imp_GetLastError
0x18006a25a  nop     dword ptr [rax+rax+00h]
0x18006a25f  test    eax, eax
0x18006a261  jle     short loc_18006A26B
0x18006a263  movzx   eax, ax
0x18006a266  or      eax, 80070000h
0x18006a26b  mov     ebx, eax
0x18006a26d  jmp     loc_18006A3B6
0x18006a272  lea     rax, [rbp+57h+ppSessionInfo]
0x18006a276  mov     [rbp+57h+var_50], rax
0x18006a27a  mov     [rbp+57h+var_48], 1
0x18006a27e  xorps   xmm0, xmm0
0x18006a281  movdqu  [rbp+57h+var_90], xmm0
0x18006a286  mov     [rbp+57h+var_80], r15
0x18006a28a  mov     edi, r15d
0x18006a28d  cmp     [rbp+57h+arg_0], r15d
0x18006a291  jbe     loc_18006A364
0x18006a297  mov     eax, edi
0x18006a299  lea     rdx, [rax+rax*2]
0x18006a29d  mov     rax, [rbp+57h+ppSessionInfo]
0x18006a2a1  mov     ecx, [rax+rdx*8]; SessionId
0x18006a2a4  test    ecx, ecx
0x18006a2a6  jz      loc_18006A359
0x18006a2ac  cmp     [rax+rdx*8+10h], r15d
0x18006a2b1  jnz     loc_18006A359
0x18006a2b7  lea     rax, [rbp+57h+TokenHandle]
0x18006a2bb  mov     [rbp+57h+var_40], rax
0x18006a2bf  mov     [rbp+57h+phToken], r15
0x18006a2c3  mov     [rbp+57h+var_30], 1
0x18006a2c7  lea     rdx, [rbp+57h+phToken]; phToken
0x18006a2cb  call    cs:__imp_WTSQueryUserToken
0x18006a2d2  nop     dword ptr [rax+rax+00h]
0x18006a2d7  mov     ebx, eax
0x18006a2d9  lea     rcx, [rbp+57h+var_40]
0x18006a2dd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18006a2e2  test    ebx, ebx
0x18006a2e4  jz      short loc_18006A359
0x18006a2e6  mov     [rbp+57h+hMem], r15
0x18006a2ea  lea     rdx, [rbp+57h+hMem]
0x18006a2ee  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006a2f2  call    GetUserSidFromToken
0x18006a2f7  test    eax, eax
0x18006a2f9  js      short loc_18006A359
0x18006a2fb  lea     rax, [rbp+57h+hMem]
0x18006a2ff  mov     [rbp+57h+Sid], rax
0x18006a303  mov     [rbp+57h+var_58], 1
0x18006a307  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18006a30b  mov     rcx, [rbp+57h+hMem]; Sid
0x18006a30f  call    cs:__imp_ConvertSidToStringSidW
0x18006a316  nop     dword ptr [rax+rax+00h]
0x18006a31b  test    eax, eax
0x18006a31d  jz      short loc_18006A345
0x18006a31f  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18006a323  cmp     rdx, [rbp+57h+var_80]
0x18006a327  jz      short loc_18006A337
0x18006a329  mov     rax, [rbp+57h+StringSid]
0x18006a32d  mov     [rdx], rax
0x18006a330  add     qword ptr [rbp+57h+var_90+8], 8
0x18006a335  jmp     short loc_18006A345
0x18006a337  lea     r8, [rbp+57h+StringSid]
0x18006a33b  lea     rcx, [rbp+57h+var_90]
0x18006a33f  call    ??$_Emplace_reallocate@AEBQEAG@?$vector@PEAGV?$allocator@PEAG@std@@@std@@AEAAPEAPEAGQEAPEAGAEBQEAG@Z; std::vector<ushort *>::_Emplace_reallocate<ushort * const &>(ushort * * const,ushort * const &)
0x18006a344  nop
0x18006a345  mov     [rbp+57h+var_58], r15b
0x18006a349  mov     rcx, [rbp+57h+hMem]; hMem
0x18006a34d  call    cs:__imp_LocalFree
0x18006a354  nop     dword ptr [rax+rax+00h]
0x18006a359  inc     edi
0x18006a35b  cmp     edi, [rbp+57h+arg_0]
0x18006a35e  jb      loc_18006A297
0x18006a364  mov     rax, qword ptr [rbp+57h+var_90]
0x18006a368  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x18006a36c  sub     rcx, rax
0x18006a36f  sar     rcx, 3
0x18006a373  test    rcx, rcx
0x18006a376  jnz     short loc_18006A3C6
0x18006a378  test    rax, rax
0x18006a37b  jz      short loc_18006A39C
0x18006a37d  mov     rdx, [rbp+57h+var_80]
0x18006a381  sub     rdx, rax
0x18006a384  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006a388  mov     rcx, rax
0x18006a38b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006a390  xorps   xmm0, xmm0
0x18006a393  movdqu  [rbp+57h+var_90], xmm0
0x18006a398  mov     [rbp+57h+var_80], r15
0x18006a39c  mov     rcx, [rbp+57h+ppSessionInfo]; pMemory
0x18006a3a0  test    rcx, rcx
0x18006a3a3  jz      short loc_18006A3B1
0x18006a3a5  call    cs:__imp_WTSFreeMemory
0x18006a3ac  nop     dword ptr [rax+rax+00h]
0x18006a3b1  mov     ebx, 82AA0008h
0x18006a3b6  lea     rcx, [rbp+57h+TokenHandle]
0x18006a3ba  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006a3bf  mov     eax, ebx
0x18006a3c1  jmp     loc_18006A637
0x18006a3c6  shl     rcx, 3; cb
0x18006a3ca  call    cs:__imp_CoTaskMemAlloc
0x18006a3d1  nop     dword ptr [rax+rax+00h]
0x18006a3d6  mov     rdx, rax
0x18006a3d9  test    rax, rax
0x18006a3dc  jnz     short loc_18006A45B
0x18006a3de  mov     rbx, r15
0x18006a3e1  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18006a3e5  mov     rcx, qword ptr [rbp+57h+var_90]
0x18006a3e9  sub     rax, rcx
0x18006a3ec  sar     rax, 3
0x18006a3f0  test    rax, rax
0x18006a3f3  jz      short loc_18006A41C
0x18006a3f5  mov     rcx, [rcx+rbx*8]; hMem
0x18006a3f9  call    cs:__imp_LocalFree
0x18006a400  nop     dword ptr [rax+rax+00h]
0x18006a405  inc     rbx
0x18006a408  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18006a40c  mov     rcx, qword ptr [rbp+57h+var_90]
0x18006a410  sub     rax, rcx
0x18006a413  sar     rax, 3
0x18006a417  cmp     rbx, rax
0x18006a41a  jb      short loc_18006A3F5
0x18006a41c  test    rcx, rcx
0x18006a41f  jz      short loc_18006A43D
0x18006a421  mov     rdx, [rbp+57h+var_80]
0x18006a425  sub     rdx, rcx
0x18006a428  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006a42c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006a431  xorps   xmm0, xmm0
0x18006a434  movdqu  [rbp+57h+var_90], xmm0
0x18006a439  mov     [rbp+57h+var_80], r15
0x18006a43d  mov     rcx, [rbp+57h+ppSessionInfo]; pMemory
0x18006a441  test    rcx, rcx
0x18006a444  jz      loc_18006A1F2
0x18006a44a  call    cs:__imp_WTSFreeMemory
0x18006a451  nop     dword ptr [rax+rax+00h]
0x18006a456  jmp     loc_18006A1F2
0x18006a45b  mov     r9, r15
0x18006a45e  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x18006a462  mov     rax, rcx
0x18006a465  mov     r8, qword ptr [rbp+57h+var_90]
0x18006a469  sub     rax, r8
0x18006a46c  sar     rax, 3
0x18006a470  test    rax, rax
0x18006a473  jz      short loc_18006A497
0x18006a475  mov     rax, [r8+r9*8]
0x18006a479  mov     [rdx+r9*8], rax
0x18006a47d  inc     r9
0x18006a480  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x18006a484  mov     rax, rcx
0x18006a487  mov     r8, qword ptr [rbp+57h+var_90]
0x18006a48b  sub     rax, r8
0x18006a48e  sar     rax, 3
0x18006a492  cmp     r9, rax
0x18006a495  jb      short loc_18006A475
0x18006a497  mov     [r14], rdx
0x18006a49a  sub     rcx, r8
0x18006a49d  sar     rcx, 3
0x18006a4a1  mov     [rsi], ecx
0x18006a4a3  test    r8, r8
0x18006a4a6  jz      short loc_18006A4C7
0x18006a4a8  mov     rdx, [rbp+57h+var_80]
0x18006a4ac  sub     rdx, r8
0x18006a4af  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006a4b3  mov     rcx, r8
0x18006a4b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006a4bb  xorps   xmm0, xmm0
0x18006a4be  movdqu  [rbp+57h+var_90], xmm0
0x18006a4c3  mov     [rbp+57h+var_80], r15
0x18006a4c7  mov     rcx, [rbp+57h+ppSessionInfo]; pMemory
0x18006a4cb  test    rcx, rcx
0x18006a4ce  jz      loc_18006A20C
0x18006a4d4  call    cs:__imp_WTSFreeMemory
0x18006a4db  nop     dword ptr [rax+rax+00h]
0x18006a4e0  jmp     loc_18006A20C
0x18006a4e5  call    IsUMgrEnumerateSessionUsersPresent
0x18006a4ea  test    al, al
0x18006a4ec  jz      short loc_18006A56C
0x18006a4ee  call    IsUMgrEnumerateSessionUsersPresent
0x18006a4f3  test    al, al
0x18006a4f5  jz      short loc_18006A56C
0x18006a4f7  mov     dword ptr [rbp+57h+hMem], r15d
0x18006a4fb  mov     [rbp+57h+var_50], r15
0x18006a4ff  lea     rdx, [rbp+57h+var_50]
0x18006a503  lea     rcx, [rbp+57h+hMem]
0x18006a507  call    cs:__imp_UMgrEnumerateSessionUsers
0x18006a50e  nop     dword ptr [rax+rax+00h]
0x18006a513  mov     ebx, eax
0x18006a515  test    eax, eax
0x18006a517  jns     short loc_18006A527
0x18006a519  lea     rcx, [rbp+57h+var_50]
0x18006a51d  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006a522  jmp     loc_18006A3B6
0x18006a527  cmp     dword ptr [rbp+57h+hMem], r15d
0x18006a52b  jbe     short loc_18006A563
0x18006a52d  lea     rax, [rbp+57h+TokenHandle]
0x18006a531  mov     [rbp+57h+var_40], rax
0x18006a535  mov     [rbp+57h+phToken], r15
0x18006a539  mov     [rbp+57h+var_30], 1
0x18006a53d  lea     rdx, [rbp+57h+phToken]
0x18006a541  mov     rcx, [rbp+57h+var_50]
0x18006a545  mov     rcx, [rcx]
0x18006a548  call    cs:__imp_UMgrQueryUserToken
0x18006a54f  nop     dword ptr [rax+rax+00h]
0x18006a554  mov     ebx, eax
0x18006a556  lea     rcx, [rbp+57h+var_40]
0x18006a55a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18006a55f  test    ebx, ebx
0x18006a561  js      short loc_18006A519
0x18006a563  lea     rcx, [rbp+57h+var_50]
0x18006a567  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006a56c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006a570  lea     rax, [rcx-1]
0x18006a574  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006a578  ja      loc_18006A3B1
0x18006a57e  mov     [rbp+57h+Sid], r15
0x18006a582  lea     rdx, [rbp+57h+Sid]
0x18006a586  call    GetUserSidFromToken
0x18006a58b  test    eax, eax
0x18006a58d  js      loc_18006A26B
0x18006a593  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18006a597  mov     rcx, [rbp+57h+Sid]; Sid
0x18006a59b  call    cs:__imp_ConvertSidToStringSidW
0x18006a5a2  nop     dword ptr [rax+rax+00h]
0x18006a5a7  test    eax, eax
0x18006a5a9  jnz     short loc_18006A5DB
0x18006a5ab  call    cs:__imp_GetLastError
0x18006a5b2  nop     dword ptr [rax+rax+00h]
0x18006a5b7  mov     ebx, eax
0x18006a5b9  test    eax, eax
0x18006a5bb  jle     short loc_18006A5C6
0x18006a5bd  movzx   ebx, ax
0x18006a5c0  or      ebx, 80070000h
0x18006a5c6  mov     rcx, [rbp+57h+Sid]; hMem
0x18006a5ca  call    cs:__imp_LocalFree
0x18006a5d1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
