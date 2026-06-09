# ImpersonationHelper::GetActiveUserSession(ulong &,bool &)

- ea: `0x18002f9c4`
- end: `0x18002fb66`
- name: `?GetActiveUserSession@ImpersonationHelper@@SAJAEAKAEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002ffe4`

## callees

- `0x18000b3d0`
- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x180019ef0`
- `0x18001fab8`
- `0x180024518`
- `0x18002f9c4`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002fa33`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002fa33`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18002fa94`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18002fa94`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18002fabe`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18002fabe`

## string_xrefs

- `0x18002fa41`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18002fafa`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18002fb20`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`

## pseudocode

```c
__int64 __fastcall ImpersonationHelper::GetActiveUserSession(unsigned int *a1, bool *a2)
{
  const char *v4; // r9
  int LastError; // ebx
  __int64 i; // rdi
  const char *v7; // r9
  int pCount; // [rsp+20h] [rbp-20h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+30h] [rbp-10h] BYREF
  void *phToken; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD v13; // [rsp+78h] [rbp+38h] BYREF
  DWORD pBytesReturned; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR ppBuffer; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  phToken = 0;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent()
    || !(unsigned __int8)IsWTSEnumerateSessionsWPresent()
    || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    goto LABEL_19;
  }
  v13 = 0;
  ppSessionInfo = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v13) )
  {
    LastError = 0;
    for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
    {
      pBytesReturned = 0;
      ppBuffer = 0;
      if ( !WTSQuerySessionInformationW(0, ppSessionInfo[i].SessionId, WTSConnectState, &ppBuffer, &pBytesReturned) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x63,
                      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
                      v7);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
        goto LABEL_17;
      }
      if ( !*(_DWORD *)ppBuffer )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &phToken,
          0);
        if ( WTSQueryUserToken(ppSessionInfo[i].SessionId, &phToken)
          || (LastError = ResultFromKnownLastError(), LastError >= 0) )
        {
          *a1 = i;
          *a2 = 1;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
          LastError = 0;
          goto LABEL_17;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
    }
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
        (const char *)(unsigned int)LastError,
        pCount);
      goto LABEL_17;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
LABEL_19:
    LastError = 0;
    goto LABEL_20;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x5E,
                (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
                v4);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
LABEL_20:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002f9c4  mov     [rsp-28h+arg_0], rbx
0x18002f9c9  push    rbp
0x18002f9ca  push    rsi
0x18002f9cb  push    rdi
0x18002f9cc  push    r14
0x18002f9ce  push    r15
0x18002f9d0  mov     rbp, rsp
0x18002f9d3  sub     rsp, 40h
0x18002f9d7  mov     rsi, rdx
0x18002f9da  mov     byte ptr [rdx], 0
0x18002f9dd  mov     r14, rcx
0x18002f9e0  mov     [rbp+phToken], 0
0x18002f9e8  call    IsWTSEnumerateSessionsWPresent
0x18002f9ed  test    al, al
0x18002f9ef  jz      loc_18002FB48
0x18002f9f5  call    IsWTSEnumerateSessionsWPresent
0x18002f9fa  test    al, al
0x18002f9fc  jz      loc_18002FB48
0x18002fa02  call    IsWTSEnumerateSessionsWPresent
0x18002fa07  test    al, al
0x18002fa09  jz      loc_18002FB48
0x18002fa0f  xor     edx, edx; Reserved
0x18002fa11  mov     [rbp+arg_8], 0
0x18002fa18  lea     rax, [rbp+arg_8]
0x18002fa1c  mov     [rbp+ppSessionInfo], 0
0x18002fa24  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18002fa28  mov     qword ptr [rsp+40h+pCount], rax; int
0x18002fa2d  xor     ecx, ecx; hServer
0x18002fa2f  lea     r8d, [rdx+1]; Version
0x18002fa33  call    cs:__imp_WTSEnumerateSessionsW
0x18002fa39  test    eax, eax
0x18002fa3b  jnz     short loc_18002FA57
0x18002fa3d  mov     rcx, [rbp+28h]; this
0x18002fa41  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002fa48  lea     edx, [rax+5Eh]; void *
0x18002fa4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fa50  mov     ebx, eax
0x18002fa52  jmp     loc_18002FB34
0x18002fa57  xor     ebx, ebx
0x18002fa59  xor     edi, edi
0x18002fa5b  cmp     edi, [rbp+arg_8]
0x18002fa5e  jnb     loc_18002FB18
0x18002fa64  mov     rdx, [rbp+ppSessionInfo]
0x18002fa68  lea     rax, [rbp+pBytesReturned]
0x18002fa6c  mov     [rbp+pBytesReturned], 0
0x18002fa73  lea     r15, [rdi+rdi*2]
0x18002fa77  mov     [rbp+ppBuffer], 0
0x18002fa7f  lea     r9, [rbp+ppBuffer]; ppBuffer
0x18002fa83  mov     r8d, 8; WTSInfoClass
0x18002fa89  mov     qword ptr [rsp+40h+pCount], rax; pBytesReturned
0x18002fa8e  mov     edx, [rdx+r15*8]; SessionId
0x18002fa92  xor     ecx, ecx; hServer
0x18002fa94  call    cs:__imp_WTSQuerySessionInformationW
0x18002fa9a  test    eax, eax
0x18002fa9c  jz      short loc_18002FAF6
0x18002fa9e  mov     rax, [rbp+ppBuffer]
0x18002faa2  cmp     dword ptr [rax], 0
0x18002faa5  jnz     short loc_18002FAD3
0x18002faa7  xor     edx, edx
0x18002faa9  lea     rcx, [rbp+phToken]
0x18002faad  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002fab2  mov     rcx, [rbp+ppSessionInfo]
0x18002fab6  lea     rdx, [rbp+phToken]; phToken
0x18002faba  mov     ecx, [rcx+r15*8]; SessionId
0x18002fabe  call    cs:__imp_WTSQueryUserToken
0x18002fac4  test    eax, eax
0x18002fac6  jnz     short loc_18002FAE3
0x18002fac8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002facd  mov     ebx, eax
0x18002facf  test    eax, eax
0x18002fad1  jns     short loc_18002FAE3
0x18002fad3  lea     rcx, [rbp+ppBuffer]
0x18002fad7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002fadc  inc     edi
0x18002fade  jmp     loc_18002FA5B
0x18002fae3  mov     [r14], edi
0x18002fae6  lea     rcx, [rbp+ppBuffer]
0x18002faea  mov     byte ptr [rsi], 1
0x18002faed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002faf2  xor     ebx, ebx
0x18002faf4  jmp     short loc_18002FB34
0x18002faf6  mov     rcx, [rbp+28h]; this
0x18002fafa  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002fb01  mov     edx, 63h ; 'c'; void *
0x18002fb06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fb0b  lea     rcx, [rbp+ppBuffer]
0x18002fb0f  mov     ebx, eax
0x18002fb11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002fb16  jmp     short loc_18002FB34
0x18002fb18  test    ebx, ebx
0x18002fb1a  jns     short loc_18002FB3F
0x18002fb1c  mov     rcx, [rbp+28h]; this
0x18002fb20  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002fb27  mov     r9d, ebx; char *
0x18002fb2a  mov     edx, 73h ; 's'; void *
0x18002fb2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb34  lea     rcx, [rbp+ppSessionInfo]
0x18002fb38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002fb3d  jmp     short loc_18002FB4A
0x18002fb3f  lea     rcx, [rbp+ppSessionInfo]
0x18002fb43  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002fb48  xor     ebx, ebx
0x18002fb4a  lea     rcx, [rbp+phToken]
0x18002fb4e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002fb53  mov     eax, ebx
0x18002fb55  mov     rbx, [rsp+40h+arg_0]
0x18002fb5a  add     rsp, 40h
0x18002fb5e  pop     r15
0x18002fb60  pop     r14
0x18002fb62  pop     rdi
0x18002fb63  pop     rsi
0x18002fb64  pop     rbp
0x18002fb65  retn
```
