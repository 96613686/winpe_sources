# ImpersonationHelper::GetActiveUserToken(void * *,bool &)

- ea: `0x18001d048`
- end: `0x18001d2c2`
- name: `?GetActiveUserToken@ImpersonationHelper@@CAJPEAPEAXAEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(void **, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001e200`
- `0x18002fd70`

## callees

- `0x18000b3d0`
- `0x18000b4e8`
- `0x18000b5dc`
- `0x18001206c`
- `0x18001208c`
- `0x180019ef0`
- `0x18001d048`
- `0x18001d2c8`
- `0x18001fab8`
- `0x180042c8c`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001d21b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001d21b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001d0b3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001d0b3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18001d118`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18001d118`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001d136`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001d136`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18001d1e7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18001d1e7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001d278`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001d278`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18001d237`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18001d237`

## string_xrefs

- `0x18001d0c1`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d179`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d19f`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d1fa`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d29a`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`

## pseudocode

```c
__int64 __fastcall ImpersonationHelper::GetActiveUserToken(void **a1, bool *a2)
{
  const char *v4; // r9
  int LastError; // ebx
  __int64 i; // r14
  const char *v7; // r9
  const char *v8; // r9
  __int64 v9; // rdx
  int SessionActiveShellUserToken; // ebx
  int pCount; // [rsp+20h] [rbp-18h]
  int pCounta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  DWORD v15; // [rsp+70h] [rbp+38h] BYREF
  DWORD pBytesReturned; // [rsp+78h] [rbp+40h] BYREF
  LPWSTR ppBuffer; // [rsp+80h] [rbp+48h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+88h] [rbp+50h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent()
    && (unsigned __int8)IsWTSEnumerateSessionsWPresent()
    && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v15 = 0;
    ppSessionInfo = 0;
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v15) )
    {
      LastError = 0;
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
      {
        pBytesReturned = 0;
        ppBuffer = 0;
        if ( !WTSQuerySessionInformationW(0, ppSessionInfo[i].SessionId, WTSConnectState, &ppBuffer, &pBytesReturned) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x8B,
                        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
                        v7);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
          goto LABEL_15;
        }
        if ( !*(_DWORD *)ppBuffer )
        {
          if ( WTSQueryUserToken(ppSessionInfo[i].SessionId, a1)
            || (LastError = ResultFromKnownLastError(), LastError >= 0) )
          {
            *a2 = 1;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
LABEL_14:
            LastError = 0;
            goto LABEL_15;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
      }
      if ( LastError >= 0 )
        goto LABEL_14;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
        (const char *)(unsigned int)LastError,
        pCounta);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x86,
                    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
                    v4);
    }
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
    return (unsigned int)LastError;
  }
  if ( (unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent()
    && (unsigned __int8)IsQueryActiveSessionPresent()
    && (unsigned __int8)IsQueryActiveSessionPresent() )
  {
    v15 = 0;
    if ( !(unsigned int)QueryActiveSession(&v15) )
    {
      v9 = 162;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
               v8);
    }
    pBytesReturned = 0;
    RtlGetDeviceFamilyInfoEnum(0, &pBytesReturned, 0);
    if ( pBytesReturned != 5 && pBytesReturned - 11 > 1 )
    {
      SessionActiveShellUserToken = UMgrGetSessionActiveShellUserToken(v15, a1);
      if ( SessionActiveShellUserToken >= 0 )
      {
LABEL_35:
        *a2 = a1 != 0;
        return 0;
      }
      if ( (unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent() )
      {
        SessionActiveShellUserToken = ImpersonationHelper::GetActiveUserTokenFromUserManager(a1, a2);
        if ( SessionActiveShellUserToken >= 0 && *a2 )
          return 0;
      }
      MitigationExecutionContext::DispatchEvent(16, (unsigned int)SessionActiveShellUserToken);
    }
    if ( !(unsigned int)QueryUserToken(v15, a1) )
    {
      v9 = 189;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
               v8);
    }
    goto LABEL_35;
  }
  LastError = -2135164413;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC3,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
    (const char *)0x80BBFA03LL,
    pCount);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001d048  push    rbp
0x18001d04a  push    rbx
0x18001d04b  push    rsi
0x18001d04c  push    rdi
0x18001d04d  push    r14
0x18001d04f  push    r15
0x18001d051  mov     rbp, rsp
0x18001d054  sub     rsp, 38h
0x18001d058  mov     qword ptr [rcx], 0
0x18001d05f  mov     rsi, rdx
0x18001d062  mov     byte ptr [rdx], 0
0x18001d065  mov     rdi, rcx
0x18001d068  call    IsWTSEnumerateSessionsWPresent
0x18001d06d  test    al, al
0x18001d06f  jz      loc_18001D1B5
0x18001d075  call    IsWTSEnumerateSessionsWPresent
0x18001d07a  test    al, al
0x18001d07c  jz      loc_18001D1B5
0x18001d082  call    IsWTSEnumerateSessionsWPresent
0x18001d087  test    al, al
0x18001d089  jz      loc_18001D1B5
0x18001d08f  xor     edx, edx; Reserved
0x18001d091  mov     [rbp+arg_0], 0
0x18001d098  lea     rax, [rbp+arg_0]
0x18001d09c  mov     [rbp+ppSessionInfo], 0
0x18001d0a4  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18001d0a8  mov     qword ptr [rsp+38h+pCount], rax; int
0x18001d0ad  xor     ecx, ecx; hServer
0x18001d0af  lea     r8d, [rdx+1]; Version
0x18001d0b3  call    cs:__imp_WTSEnumerateSessionsW
0x18001d0b9  test    eax, eax
0x18001d0bb  jnz     short loc_18001D0D9
0x18001d0bd  mov     rcx, [rbp+30h]; this
0x18001d0c1  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d0c8  mov     edx, 86h; void *
0x18001d0cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d0d2  mov     ebx, eax
0x18001d0d4  jmp     loc_18001D167
0x18001d0d9  xor     ebx, ebx
0x18001d0db  xor     r14d, r14d
0x18001d0de  cmp     r14d, [rbp+arg_0]
0x18001d0e2  jnb     loc_18001D197
0x18001d0e8  mov     rdx, [rbp+ppSessionInfo]
0x18001d0ec  lea     rax, [rbp+pBytesReturned]
0x18001d0f0  mov     [rbp+pBytesReturned], 0
0x18001d0f7  lea     r15, [r14+r14*2]
0x18001d0fb  mov     [rbp+ppBuffer], 0
0x18001d103  lea     r9, [rbp+ppBuffer]; ppBuffer
0x18001d107  mov     r8d, 8; WTSInfoClass
0x18001d10d  mov     qword ptr [rsp+38h+pCount], rax; pBytesReturned
0x18001d112  mov     edx, [rdx+r15*8]; SessionId
0x18001d116  xor     ecx, ecx; hServer
0x18001d118  call    cs:__imp_WTSQuerySessionInformationW
0x18001d11e  test    eax, eax
0x18001d120  jz      short loc_18001D175
0x18001d122  mov     rax, [rbp+ppBuffer]
0x18001d126  cmp     dword ptr [rax], 0
0x18001d129  jnz     short loc_18001D14B
0x18001d12b  mov     rcx, [rbp+ppSessionInfo]
0x18001d12f  mov     rdx, rdi; phToken
0x18001d132  mov     ecx, [rcx+r15*8]; SessionId
0x18001d136  call    cs:__imp_WTSQueryUserToken
0x18001d13c  test    eax, eax
0x18001d13e  jnz     short loc_18001D159
0x18001d140  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d145  mov     ebx, eax
0x18001d147  test    eax, eax
0x18001d149  jns     short loc_18001D159
0x18001d14b  lea     rcx, [rbp+ppBuffer]
0x18001d14f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d154  inc     r14d
0x18001d157  jmp     short loc_18001D0DE
0x18001d159  lea     rcx, [rbp+ppBuffer]
0x18001d15d  mov     byte ptr [rsi], 1
0x18001d160  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d165  xor     ebx, ebx
0x18001d167  lea     rcx, [rbp+ppSessionInfo]
0x18001d16b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d170  jmp     loc_18001D2B3
0x18001d175  mov     rcx, [rbp+30h]; this
0x18001d179  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d180  mov     edx, 8Bh; void *
0x18001d185  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d18a  lea     rcx, [rbp+ppBuffer]
0x18001d18e  mov     ebx, eax
0x18001d190  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d195  jmp     short loc_18001D167
0x18001d197  test    ebx, ebx
0x18001d199  jns     short loc_18001D165
0x18001d19b  mov     rcx, [rbp+30h]; this
0x18001d19f  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d1a6  mov     r9d, ebx; char *
0x18001d1a9  mov     edx, 9Bh; void *
0x18001d1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1b3  jmp     short loc_18001D167
0x18001d1b5  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x18001d1ba  test    al, al
0x18001d1bc  jz      loc_18001D296
0x18001d1c2  call    IsQueryActiveSessionPresent
0x18001d1c7  test    al, al
0x18001d1c9  jz      loc_18001D296
0x18001d1cf  call    IsQueryActiveSessionPresent
0x18001d1d4  test    al, al
0x18001d1d6  jz      loc_18001D296
0x18001d1dc  lea     rcx, [rbp+arg_0]
0x18001d1e0  mov     [rbp+arg_0], 0
0x18001d1e7  call    cs:__imp_QueryActiveSession
0x18001d1ed  test    eax, eax
0x18001d1ef  jnz     short loc_18001D20B
0x18001d1f1  mov     edx, 0A2h; void *
0x18001d1f6  mov     rcx, [rbp+30h]; this
0x18001d1fa  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d201  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d206  jmp     loc_18001D2B5
0x18001d20b  xor     r8d, r8d
0x18001d20e  mov     [rbp+pBytesReturned], 0
0x18001d215  lea     rdx, [rbp+pBytesReturned]
0x18001d219  xor     ecx, ecx
0x18001d21b  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001d221  mov     eax, [rbp+pBytesReturned]
0x18001d224  cmp     eax, 5
0x18001d227  jz      short loc_18001D272
0x18001d229  add     eax, 0FFFFFFF5h
0x18001d22c  cmp     eax, 1
0x18001d22f  jbe     short loc_18001D272
0x18001d231  mov     ecx, [rbp+arg_0]
0x18001d234  mov     rdx, rdi
0x18001d237  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x18001d23d  mov     ebx, eax
0x18001d23f  test    eax, eax
0x18001d241  jns     short loc_18001D28C
0x18001d243  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x18001d248  test    al, al
0x18001d24a  jz      short loc_18001D266
0x18001d24c  mov     rdx, rsi; bool *
0x18001d24f  mov     rcx, rdi; void **
0x18001d252  call    ?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAXAEA_N@Z; ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *,bool &)
0x18001d257  mov     ebx, eax
0x18001d259  test    eax, eax
0x18001d25b  js      short loc_18001D266
0x18001d25d  cmp     byte ptr [rsi], 0
0x18001d260  jz      short loc_18001D266
0x18001d262  xor     eax, eax
0x18001d264  jmp     short loc_18001D2B5
0x18001d266  mov     edx, ebx
0x18001d268  mov     ecx, 10h
0x18001d26d  call    ?DispatchEvent@MitigationExecutionContext@@SAXW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(MitigationError,long)
0x18001d272  mov     ecx, [rbp+arg_0]
0x18001d275  mov     rdx, rdi
0x18001d278  call    cs:__imp_QueryUserToken
0x18001d27e  test    eax, eax
0x18001d280  jnz     short loc_18001D28C
0x18001d282  mov     edx, 0BDh
0x18001d287  jmp     loc_18001D1F6
0x18001d28c  test    rdi, rdi
0x18001d28f  setnz   al
0x18001d292  mov     [rsi], al
0x18001d294  jmp     short loc_18001D262
0x18001d296  mov     rcx, [rbp+30h]; this
0x18001d29a  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d2a1  mov     ebx, 80BBFA03h
0x18001d2a6  mov     edx, 0C3h; void *
0x18001d2ab  mov     r9d, ebx; char *
0x18001d2ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2b3  mov     eax, ebx
0x18001d2b5  add     rsp, 38h
0x18001d2b9  pop     r15
0x18001d2bb  pop     r14
0x18001d2bd  pop     rdi
0x18001d2be  pop     rsi
0x18001d2bf  pop     rbx
0x18001d2c0  pop     rbp
0x18001d2c1  retn
```
