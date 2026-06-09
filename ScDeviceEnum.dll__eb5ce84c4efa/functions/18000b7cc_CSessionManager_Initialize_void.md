# CSessionManager::Initialize(void)

- ea: `0x18000b7cc`
- end: `0x18000ba8c`
- name: `?Initialize@CSessionManager@@SAJXZ`
- size: `704`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180006670`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x180007248`
- `0x18000abb0`
- `0x18000acf0`
- `0x18000b004`
- `0x18000b43c`
- `0x18000b4a0`
- `0x18000b7cc`
- `0x18000ba94`
- `0x18000c4c8`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b95f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b87c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b87c`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000b955`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000b955`

## pseudocode

```c
__int64 CSessionManager::Initialize(void)
{
  struct CSessionManager *v0; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rbx
  signed int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rbx
  struct CSessionManager *v6; // rax
  PVOID v7; // rcx
  signed int LastError; // eax
  DWORD i; // ebx
  DWORD SessionId; // esi
  int v11; // r8d
  int v13; // [rsp+30h] [rbp-39h] BYREF
  char v14; // [rsp+34h] [rbp-35h] BYREF
  __int16 v15; // [rsp+35h] [rbp-34h]
  DWORD pCount; // [rsp+38h] [rbp-31h] BYREF
  int v17; // [rsp+3Ch] [rbp-2Dh] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v19; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-19h] BYREF
  char v21[32]; // [rsp+68h] [rbp-1h] BYREF

  v13 = 0;
  v17 = 0;
  strcpy(v21, "CSessionManager::Initialize");
  v20[0] = v21;
  v20[1] = &v17;
  v20[2] = &v13;
  lambda_2480b09bc7830462697ac3c2f50968b0_::operator()(v20);
  v17 = 1;
  v19 = v20;
  v0 = CSessionManager::Instance();
  *((_DWORD *)v0 + 14) = 3;
  *((_QWORD *)v0 + 8) = 0;
  *((_QWORD *)v0 + 9) = 0;
  *((_QWORD *)v0 + 10) = 0;
  *((_QWORD *)v0 + 11) = 0;
  *((_QWORD *)v0 + 12) = 0;
  *((_QWORD *)v0 + 13) = 0;
  *((_DWORD *)v0 + 28) = 0;
  *((_DWORD *)v0 + 29) = 1;
  *((_DWORD *)v0 + 30) = 72;
  v15 = 256;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)CSessionManager::Instance() + 16) = ThreadpoolCleanupGroup;
  if ( *((_QWORD *)CSessionManager::Instance() + 16) )
  {
    v5 = *((_QWORD *)CSessionManager::Instance() + 16);
    v6 = CSessionManager::Instance();
    *((_QWORD *)v6 + 9) = v5;
    *((_QWORD *)v6 + 10) = 0;
    HIBYTE(v15) = 0;
    wil::details::ScopeExitFnGuard__lambda_20f54e449266fb51b668b0b6e9685cd3___::operator()(&v14);
    pCount = 0;
    ppSessionInfo = 0;
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      for ( i = 0; i < pCount; ++i )
      {
        SessionId = ppSessionInfo[i].SessionId;
        if ( !SessionId || ppSessionInfo[i].State )
        {
          WppTraceIndent(v7, 2);
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sdL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              ppSessionInfo[i].State,
              v11,
              (_DWORD)WPP_pszIndent,
              SessionId,
              ppSessionInfo[i].State);
          }
        }
        else
        {
          v13 = CSessionManager::Add(SessionId);
          if ( v13 < 0 )
          {
            WppTraceIndent(v7, 2);
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_sdd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids,
                (_DWORD)WPP_pszIndent,
                SessionId,
                v13);
            }
            v13 = 0;
          }
        }
      }
      v4 = v13;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v13 = v4;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
  }
  else
  {
    v2 = GetLastError();
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    v13 = v2;
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids,
        (_DWORD)WPP_pszIndent,
        v13);
    }
    v4 = v13;
    wil::details::ScopeExitFnGuard__lambda_20f54e449266fb51b668b0b6e9685cd3___::operator()(&v14);
  }
  WppTraceUnwinder__lambda_2480b09bc7830462697ac3c2f50968b0____::_WppTraceUnwinder__lambda_2480b09bc7830462697ac3c2f50968b0____(&v19);
  return v4;
}

```

## disassembly

```asm
0x18000b7cc  push    rbp
0x18000b7ce  push    rbx
0x18000b7cf  push    rsi
0x18000b7d0  push    rdi
0x18000b7d1  push    r14
0x18000b7d3  push    r15
0x18000b7d5  lea     rbp, [rsp-2Fh]
0x18000b7da  sub     rsp, 98h
0x18000b7e1  mov     rax, cs:__security_cookie
0x18000b7e8  xor     rax, rsp
0x18000b7eb  mov     [rbp+57h+var_38], rax
0x18000b7ef  xor     r15d, r15d
0x18000b7f2  mov     [rbp+57h+var_90], r15d
0x18000b7f6  mov     [rbp+57h+var_84], r15d
0x18000b7fa  movups  xmm0, xmmword ptr cs:aCsessionmanage_0; "CSessionManager::Initialize"
0x18000b801  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18000b805  movups  xmm1, xmmword ptr cs:aCsessionmanage_0+0Ch; "ger::Initialize"
0x18000b80c  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm1
0x18000b810  lea     rax, [rbp+57h+var_58]
0x18000b814  mov     [rbp+57h+var_70], rax
0x18000b818  lea     rax, [rbp+57h+var_84]
0x18000b81c  mov     [rbp+57h+var_68], rax
0x18000b820  lea     rax, [rbp+57h+var_90]
0x18000b824  mov     [rbp+57h+var_60], rax
0x18000b828  lea     rcx, [rbp+57h+var_70]
0x18000b82c  call    _lambda_2480b09bc7830462697ac3c2f50968b0___operator__
0x18000b831  mov     [rbp+57h+var_84], 1
0x18000b838  lea     rax, [rbp+57h+var_70]
0x18000b83c  mov     [rbp+57h+var_78], rax
0x18000b840  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b845  mov     dword ptr [rax+38h], 3
0x18000b84c  mov     [rax+40h], r15
0x18000b850  mov     [rax+48h], r15
0x18000b854  mov     [rax+50h], r15
0x18000b858  mov     [rax+58h], r15
0x18000b85c  mov     [rax+60h], r15
0x18000b860  mov     [rax+68h], r15
0x18000b864  mov     [rax+70h], r15d
0x18000b868  mov     dword ptr [rax+74h], 1
0x18000b86f  mov     dword ptr [rax+78h], 48h ; 'H'
0x18000b876  mov     [rbp+57h+var_8B], 100h
0x18000b87c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000b882  mov     rbx, rax
0x18000b885  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b88a  mov     [rax+80h], rbx
0x18000b891  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b896  cmp     [rax+80h], r15
0x18000b89d  jnz     short loc_18000B911
0x18000b89f  call    cs:__imp_GetLastError
0x18000b8a5  test    eax, eax
0x18000b8a7  jle     short loc_18000B8B1
0x18000b8a9  movzx   eax, ax
0x18000b8ac  or      eax, 80070000h
0x18000b8b1  mov     [rbp+57h+var_90], eax
0x18000b8b4  mov     edx, 2
0x18000b8b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b8be  lea     rdi, WPP_GLOBAL_Control
0x18000b8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8cc  cmp     rcx, rdi
0x18000b8cf  jz      short loc_18000B900
0x18000b8d1  test    byte ptr [rcx+1Ch], 1
0x18000b8d5  jz      short loc_18000B900
0x18000b8d7  cmp     byte ptr [rcx+19h], 2
0x18000b8db  jb      short loc_18000B900
0x18000b8dd  mov     edx, 0Dh
0x18000b8e2  mov     eax, [rbp+57h+var_90]
0x18000b8e5  mov     dword ptr [rsp+0C0h+pCount], eax
0x18000b8e9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b8f0  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000b8f7  mov     rcx, [rcx+10h]
0x18000b8fb  call    WPP_SF_sd
0x18000b900  mov     ebx, [rbp+57h+var_90]
0x18000b903  lea     rcx, [rbp+57h+var_8C]
0x18000b907  call    wil__details__ScopeExitFnGuard__lambda_20f54e449266fb51b668b0b6e9685cd3_____operator__
0x18000b90c  jmp     loc_18000BA65
0x18000b911  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b916  mov     rbx, [rax+80h]
0x18000b91d  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b922  mov     [rax+48h], rbx
0x18000b926  mov     [rax+50h], r15
0x18000b92a  mov     byte ptr [rbp+57h+var_8B+1], r15b
0x18000b92e  lea     rcx, [rbp+57h+var_8C]
0x18000b932  call    wil__details__ScopeExitFnGuard__lambda_20f54e449266fb51b668b0b6e9685cd3_____operator__
0x18000b937  nop
0x18000b938  mov     [rbp+57h+var_88], r15d
0x18000b93c  mov     [rbp+57h+ppSessionInfo], r15
0x18000b940  lea     rax, [rbp+57h+var_88]
0x18000b944  mov     [rsp+0C0h+pCount], rax; pCount
0x18000b949  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18000b94d  xor     edx, edx; Reserved
0x18000b94f  xor     ecx, ecx; hServer
0x18000b951  lea     r8d, [rdx+1]; Version
0x18000b955  call    cs:__imp_WTSEnumerateSessionsW
0x18000b95b  test    eax, eax
0x18000b95d  jnz     short loc_18000B97C
0x18000b95f  call    cs:__imp_GetLastError
0x18000b965  mov     ebx, eax
0x18000b967  test    eax, eax
0x18000b969  jle     short loc_18000B974
0x18000b96b  movzx   ebx, ax
0x18000b96e  or      ebx, 80070000h
0x18000b974  mov     [rbp+57h+var_90], ebx
0x18000b977  jmp     loc_18000BA5B
0x18000b97c  mov     ebx, r15d
0x18000b97f  cmp     [rbp+57h+var_88], r15d
0x18000b983  jbe     loc_18000BA58
0x18000b989  lea     rdi, WPP_GLOBAL_Control
0x18000b990  mov     eax, ebx
0x18000b992  lea     r14, [rax+rax*2]
0x18000b996  mov     rax, [rbp+57h+ppSessionInfo]
0x18000b99a  mov     esi, [rax+r14*8]
0x18000b99e  test    esi, esi
0x18000b9a0  jz      short loc_18000BA0A
0x18000b9a2  cmp     [rax+r14*8+10h], r15d
0x18000b9a7  jnz     short loc_18000BA0A
0x18000b9a9  mov     ecx, esi; unsigned int
0x18000b9ab  call    ?Add@CSessionManager@@SAJK@Z; CSessionManager::Add(ulong)
0x18000b9b0  mov     [rbp+57h+var_90], eax
0x18000b9b3  test    eax, eax
0x18000b9b5  jns     loc_18000BA4D
0x18000b9bb  mov     edx, 2
0x18000b9c0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9cc  cmp     rcx, rdi
0x18000b9cf  jz      short loc_18000BA04
0x18000b9d1  test    byte ptr [rcx+1Ch], 1
0x18000b9d5  jz      short loc_18000BA04
0x18000b9d7  cmp     byte ptr [rcx+19h], 3
0x18000b9db  jb      short loc_18000BA04
0x18000b9dd  mov     edx, 0Eh
0x18000b9e2  mov     eax, [rbp+57h+var_90]
0x18000b9e5  mov     [rsp+0C0h+var_98], eax
0x18000b9e9  mov     dword ptr [rsp+0C0h+pCount], esi
0x18000b9ed  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b9f4  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000b9fb  mov     rcx, [rcx+10h]
0x18000b9ff  call    WPP_SF_sdd
0x18000ba04  mov     [rbp+57h+var_90], r15d
0x18000ba08  jmp     short loc_18000BA4D
0x18000ba0a  mov     edx, 2
0x18000ba0f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ba14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba1b  cmp     rcx, rdi
0x18000ba1e  jz      short loc_18000BA4D
0x18000ba20  test    byte ptr [rcx+1Ch], 1
0x18000ba24  jz      short loc_18000BA4D
0x18000ba26  cmp     byte ptr [rcx+19h], 4
0x18000ba2a  jb      short loc_18000BA4D
0x18000ba2c  mov     rax, [rbp+57h+ppSessionInfo]
0x18000ba30  mov     edx, [rax+r14*8+10h]
0x18000ba35  mov     [rsp+0C0h+var_98], edx
0x18000ba39  mov     dword ptr [rsp+0C0h+pCount], esi
0x18000ba3d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000ba44  mov     rcx, [rcx+10h]
0x18000ba48  call    WPP_SF_sdL
0x18000ba4d  inc     ebx
0x18000ba4f  cmp     ebx, [rbp+57h+var_88]
0x18000ba52  jb      loc_18000B990
0x18000ba58  mov     ebx, [rbp+57h+var_90]
0x18000ba5b  lea     rcx, [rbp+57h+ppSessionInfo]
0x18000ba5f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ba64  nop
0x18000ba65  lea     rcx, [rbp+57h+var_78]
0x18000ba69  call    WppTraceUnwinder__lambda_2480b09bc7830462697ac3c2f50968b0_______WppTraceUnwinder__lambda_2480b09bc7830462697ac3c2f50968b0____
0x18000ba6e  mov     eax, ebx
0x18000ba70  mov     rcx, [rbp+57h+var_38]
0x18000ba74  xor     rcx, rsp; StackCookie
0x18000ba77  call    __security_check_cookie
0x18000ba7c  add     rsp, 98h
0x18000ba83  pop     r15
0x18000ba85  pop     r14
0x18000ba87  pop     rdi
0x18000ba88  pop     rsi
0x18000ba89  pop     rbx
0x18000ba8a  pop     rbp
0x18000ba8b  retn
```
