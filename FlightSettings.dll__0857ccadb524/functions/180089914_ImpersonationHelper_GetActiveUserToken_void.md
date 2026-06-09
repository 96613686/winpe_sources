# ImpersonationHelper::GetActiveUserToken(void * *)

- ea: `0x180089914`
- end: `0x180089b62`
- name: `?GetActiveUserToken@ImpersonationHelper@@CAJPEAPEAX@Z`
- size: `590`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008a2fc`

## callees

- `0x180006690`
- `0x1800067a8`
- `0x180006938`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001b2c0`
- `0x18002aaa0`
- `0x18002ae34`
- `0x18002b1f4`
- `0x180089914`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180089ad0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180089ad0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180089971`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180089971`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800899f0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800899f0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800899d2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800899d2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180089aa0`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180089aa0`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180089b20`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180089b20`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x180089aec`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x180089aec`

## string_xrefs

- `0x18008997f`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x180089a23`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x180089a49`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x180089ab3`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x180089b3c`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`

## pseudocode

```c
__int64 __fastcall ImpersonationHelper::GetActiveUserToken(void **a1)
{
  int LastError; // ebx
  const char *v3; // r9
  __int64 i; // rsi
  const char *v5; // r9
  const char *v6; // r9
  __int64 v7; // rdx
  int pCount; // [rsp+20h] [rbp-10h]
  int pCounta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD v12; // [rsp+60h] [rbp+30h] BYREF
  DWORD pBytesReturned; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR ppBuffer; // [rsp+70h] [rbp+40h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+78h] [rbp+48h] BYREF

  *a1 = 0;
  LastError = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent()
    && (unsigned __int8)IsWTSEnumerateSessionsWPresent()
    && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v12 = 0;
    ppSessionInfo = 0;
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v12) )
    {
      for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
      {
        pBytesReturned = 0;
        ppBuffer = 0;
        if ( !WTSQuerySessionInformationW(0, ppSessionInfo[i].SessionId, WTSConnectState, &ppBuffer, &pBytesReturned) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xD5,
                        (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
                        v5);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
          goto LABEL_18;
        }
        if ( !*(_DWORD *)ppBuffer )
        {
          if ( WTSQueryUserToken(ppSessionInfo[i].SessionId, a1)
            || (LastError = ResultFromKnownLastError(), LastError >= 0) )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
            LastError = 0;
            goto LABEL_18;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
      }
      if ( LastError >= 0 )
        LastError = -2146698748;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE3,
          (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
          (const char *)(unsigned int)LastError,
          pCounta);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD0,
                    (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
                    v3);
    }
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
    return (unsigned int)LastError;
  }
  if ( (unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent()
    && (unsigned __int8)IsQueryActiveSessionPresent()
    && (unsigned __int8)IsQueryActiveSessionPresent() )
  {
    v12 = 0;
    if ( !(unsigned int)QueryActiveSession(&v12) )
    {
      v7 = 234;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
               v6);
    }
    pBytesReturned = 0;
    RtlGetDeviceFamilyInfoEnum(0, &pBytesReturned, 0);
    if ( pBytesReturned != 5 && pBytesReturned - 11 > 1 )
    {
      LODWORD(ppBuffer) = UMgrGetSessionActiveShellUserToken(v12, a1);
      if ( (int)ppBuffer >= 0 )
        return 0;
      if ( (unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent() )
      {
        LODWORD(ppBuffer) = ImpersonationHelper::GetActiveUserTokenFromUserManager(a1);
        if ( (int)ppBuffer >= 0 )
          return 0;
      }
      FlightSettingsAPITelemetryClass::UMgrGetSessionActiveShellUserTokenFailed<long &>(&ppBuffer);
    }
    if ( !(unsigned int)QueryUserToken(v12, a1) )
    {
      v7 = 261;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
               v6);
    }
    return 0;
  }
  LastError = -2146698749;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10A,
    (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
    (const char *)0x800BFA03LL,
    pCount);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180089914  push    rbp
0x180089916  push    rbx
0x180089917  push    rsi
0x180089918  push    rdi
0x180089919  push    r14
0x18008991b  mov     rbp, rsp
0x18008991e  sub     rsp, 30h
0x180089922  mov     rdi, rcx
0x180089925  mov     qword ptr [rcx], 0
0x18008992c  xor     ebx, ebx
0x18008992e  call    IsWTSEnumerateSessionsWPresent
0x180089933  test    al, al
0x180089935  jz      loc_180089A72
0x18008993b  call    IsWTSEnumerateSessionsWPresent
0x180089940  test    al, al
0x180089942  jz      loc_180089A72
0x180089948  call    IsWTSEnumerateSessionsWPresent
0x18008994d  test    al, al
0x18008994f  jz      loc_180089A72
0x180089955  lea     rax, [rbp+arg_0]
0x180089959  mov     [rbp+arg_0], ebx
0x18008995c  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180089960  mov     qword ptr [rsp+30h+pCount], rax; int
0x180089965  xor     edx, edx; Reserved
0x180089967  mov     [rbp+ppSessionInfo], rbx
0x18008996b  xor     ecx, ecx; hServer
0x18008996d  lea     r8d, [rbx+1]; Version
0x180089971  call    cs:__imp_WTSEnumerateSessionsW
0x180089977  test    eax, eax
0x180089979  jnz     short loc_180089997
0x18008997b  mov     rcx, [rbp+28h]; this
0x18008997f  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x180089986  mov     edx, 0D0h; void *
0x18008998b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180089990  mov     ebx, eax
0x180089992  jmp     loc_180089A64
0x180089997  xor     esi, esi
0x180089999  cmp     esi, [rbp+arg_0]
0x18008999c  jnb     loc_180089A41
0x1800899a2  mov     rdx, [rbp+ppSessionInfo]
0x1800899a6  lea     rax, [rbp+pBytesReturned]
0x1800899aa  mov     [rbp+pBytesReturned], 0
0x1800899b1  lea     r14, [rsi+rsi*2]
0x1800899b5  mov     [rbp+ppBuffer], 0
0x1800899bd  lea     r9, [rbp+ppBuffer]; ppBuffer
0x1800899c1  mov     r8d, 8; WTSInfoClass
0x1800899c7  mov     qword ptr [rsp+30h+pCount], rax; pBytesReturned
0x1800899cc  mov     edx, [rdx+r14*8]; SessionId
0x1800899d0  xor     ecx, ecx; hServer
0x1800899d2  call    cs:__imp_WTSQuerySessionInformationW
0x1800899d8  test    eax, eax
0x1800899da  jz      short loc_180089A1F
0x1800899dc  mov     rax, [rbp+ppBuffer]
0x1800899e0  cmp     dword ptr [rax], 0
0x1800899e3  jnz     short loc_180089A05
0x1800899e5  mov     rcx, [rbp+ppSessionInfo]
0x1800899e9  mov     rdx, rdi; phToken
0x1800899ec  mov     ecx, [rcx+r14*8]; SessionId
0x1800899f0  call    cs:__imp_WTSQueryUserToken
0x1800899f6  test    eax, eax
0x1800899f8  jnz     short loc_180089A12
0x1800899fa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800899ff  mov     ebx, eax
0x180089a01  test    eax, eax
0x180089a03  jns     short loc_180089A12
0x180089a05  lea     rcx, [rbp+ppBuffer]
0x180089a09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089a0e  inc     esi
0x180089a10  jmp     short loc_180089999
0x180089a12  lea     rcx, [rbp+ppBuffer]
0x180089a16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089a1b  xor     ebx, ebx
0x180089a1d  jmp     short loc_180089A64
0x180089a1f  mov     rcx, [rbp+28h]; this
0x180089a23  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x180089a2a  mov     edx, 0D5h; void *
0x180089a2f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180089a34  lea     rcx, [rbp+ppBuffer]
0x180089a38  mov     ebx, eax
0x180089a3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089a3f  jmp     short loc_180089A64
0x180089a41  test    ebx, ebx
0x180089a43  jns     short loc_180089A5F
0x180089a45  mov     rcx, [rbp+28h]; this
0x180089a49  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x180089a50  mov     r9d, ebx; char *
0x180089a53  mov     edx, 0E3h; void *
0x180089a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089a5d  jmp     short loc_180089A64
0x180089a5f  mov     ebx, 800BFA04h
0x180089a64  lea     rcx, [rbp+ppSessionInfo]
0x180089a68  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089a6d  jmp     loc_180089B55
0x180089a72  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x180089a77  test    al, al
0x180089a79  jz      loc_180089B38
0x180089a7f  call    IsQueryActiveSessionPresent
0x180089a84  test    al, al
0x180089a86  jz      loc_180089B38
0x180089a8c  call    IsQueryActiveSessionPresent
0x180089a91  test    al, al
0x180089a93  jz      loc_180089B38
0x180089a99  lea     rcx, [rbp+arg_0]
0x180089a9d  mov     [rbp+arg_0], ebx
0x180089aa0  call    cs:__imp_QueryActiveSession
0x180089aa6  test    eax, eax
0x180089aa8  jnz     short loc_180089AC4
0x180089aaa  mov     edx, 0EAh; void *
0x180089aaf  mov     rcx, [rbp+28h]; this
0x180089ab3  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x180089aba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180089abf  jmp     loc_180089B57
0x180089ac4  xor     r8d, r8d
0x180089ac7  mov     [rbp+pBytesReturned], ebx
0x180089aca  lea     rdx, [rbp+pBytesReturned]
0x180089ace  xor     ecx, ecx
0x180089ad0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180089ad6  mov     eax, [rbp+pBytesReturned]
0x180089ad9  cmp     eax, 5
0x180089adc  jz      short loc_180089B1A
0x180089ade  add     eax, 0FFFFFFF5h
0x180089ae1  cmp     eax, 1
0x180089ae4  jbe     short loc_180089B1A
0x180089ae6  mov     ecx, [rbp+arg_0]
0x180089ae9  mov     rdx, rdi
0x180089aec  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x180089af2  mov     dword ptr [rbp+ppBuffer], eax
0x180089af5  test    eax, eax
0x180089af7  jns     short loc_180089B34
0x180089af9  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x180089afe  test    al, al
0x180089b00  jz      short loc_180089B11
0x180089b02  mov     rcx, rdi; void **
0x180089b05  call    ?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAX@Z; ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *)
0x180089b0a  mov     dword ptr [rbp+ppBuffer], eax
0x180089b0d  test    eax, eax
0x180089b0f  jns     short loc_180089B34
0x180089b11  lea     rcx, [rbp+ppBuffer]
0x180089b15  call    ??$UMgrGetSessionActiveShellUserTokenFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::UMgrGetSessionActiveShellUserTokenFailed<long &>(long &)
0x180089b1a  mov     ecx, [rbp+arg_0]
0x180089b1d  mov     rdx, rdi
0x180089b20  call    cs:__imp_QueryUserToken
0x180089b26  test    eax, eax
0x180089b28  jnz     short loc_180089B34
0x180089b2a  mov     edx, 105h
0x180089b2f  jmp     loc_180089AAF
0x180089b34  xor     eax, eax
0x180089b36  jmp     short loc_180089B57
0x180089b38  mov     rcx, [rbp+28h]; this
0x180089b3c  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x180089b43  mov     ebx, 800BFA03h
0x180089b48  mov     edx, 10Ah; void *
0x180089b4d  mov     r9d, ebx; char *
0x180089b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089b55  mov     eax, ebx
0x180089b57  add     rsp, 30h
0x180089b5b  pop     r14
0x180089b5d  pop     rdi
0x180089b5e  pop     rsi
0x180089b5f  pop     rbx
0x180089b60  pop     rbp
0x180089b61  retn
```
