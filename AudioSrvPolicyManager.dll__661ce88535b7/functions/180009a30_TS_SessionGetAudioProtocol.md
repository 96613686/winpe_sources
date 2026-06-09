# TS_SessionGetAudioProtocol

- ea: `0x180009a30`
- end: `0x180009e54`
- name: `TS_SessionGetAudioProtocol`
- size: `1060`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009a30`
- `0x18000a080`
- `0x18000a384`
- `0x18000a3a8`
- `0x18000f040`
- `0x180012844`
- `0x18002acfc`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009cce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b15`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009afc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e3e`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009b68`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009b7a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009b68`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009b7a`
- `RPCRT4!RpcRevertToSelf` at `0x180009b5a`
- `RPCRT4!RpcRevertToSelf` at `0x180009d91`
- `RPCRT4!RpcRevertToSelf` at `0x180009b5a`
- `RPCRT4!RpcRevertToSelf` at `0x180009d91`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009ac4`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009ac4`
- `RPCRT4!RpcImpersonateClient` at `0x180009adf`
- `RPCRT4!RpcImpersonateClient` at `0x180009adf`

## pseudocode

```c
__int64 __fastcall TS_SessionGetAudioProtocol(RPC_BINDING_HANDLE BindingHandle, DWORD a2, _DWORD *a3, _DWORD *a4)
{
  RPC_STATUS v8; // eax
  signed int LastError; // esi
  RPC_STATUS v10; // eax
  HANDLE CurrentThread; // rax
  const char *v12; // r9
  unsigned int TokenInformation; // eax
  int CurrentServiceSessionId; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v20; // rbx
  unsigned int v21; // [rsp+20h] [rbp-D8h]
  DWORD SessionId; // [rsp+30h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C0h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B0h]
  __int128 v26; // [rsp+58h] [rbp-A0h]
  __int128 v27; // [rsp+68h] [rbp-90h]
  __int128 v28; // [rsp+78h] [rbp-80h]
  __int128 v29; // [rsp+88h] [rbp-70h]
  __int128 v30; // [rsp+98h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x944,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x945,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  v25 = 0;
  v26 = 0;
  *a3 = 0xFFFF;
  v27 = 0;
  *a4 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  SessionId = 0;
  v30 = 0;
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v8 = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes);
  LastError = v8;
  if ( v8 > 0 )
    LastError = (unsigned __int16)v8 | 0x80070000;
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)LastError,
      v21);
    goto LABEL_37;
  }
  v10 = RpcImpersonateClient(BindingHandle);
  LastError = v10;
  if ( v10 > 0 )
    LastError = (unsigned __int16)v10 | 0x80070000;
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)LastError,
      v21);
    goto LABEL_37;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  v12);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
LABEL_36:
    RpcRevertToSelf();
    if ( LastError >= 0 )
      goto LABEL_14;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94D,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)LastError,
      v21);
    return (unsigned int)LastError;
  }
  TokenInformation = GetTokenInformation(TokenHandle, 0, 0, 0, &SessionId);
  if ( TokenInformation )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  (const char *)TokenInformation,
                  v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_36;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  RpcRevertToSelf();
LABEL_14:
  if ( a2 == -1 )
    a2 = SessionId;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  if ( a2 == SessionId || SessionId == CurrentServiceSessionId )
  {
    if ( a2 == (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      *a3 = 0;
      *a4 = 0;
    }
    else
    {
      *a3 = 0xFFFF;
      EnterCriticalSection(&stru_180064458);
      EnterCriticalSection(&stru_180064458);
      v15 = HIBYTE(a2);
      _mm_lfence();
      v16 = *(_QWORD *)(qword_180064498
                      + 16
                      * (qword_1800644B0
                       & (0x100000001B3LL
                        * (v15
                         ^ (0x100000001B3LL
                          * (BYTE2(a2)
                           ^ (0x100000001B3LL
                            * (BYTE1(a2) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL)))))))))
                      + 8);
      if ( v16 == qword_180064488 )
      {
LABEL_23:
        v16 = 0;
      }
      else
      {
        v17 = *(_QWORD *)(qword_180064498
                        + 16
                        * (qword_1800644B0
                         & (0x100000001B3LL
                          * (v15
                           ^ (0x100000001B3LL
                            * (BYTE2(a2)
                             ^ (0x100000001B3LL
                              * (BYTE1(a2) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL))))))))));
        while ( a2 != *(_DWORD *)(v16 + 16) )
        {
          if ( v16 == v17 )
            goto LABEL_23;
          v16 = *(_QWORD *)(v16 + 8);
        }
      }
      v18 = qword_180064488;
      if ( v16 )
        v18 = v16;
      if ( v18 == qword_180064488 )
      {
        LeaveCriticalSection(&stru_180064458);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
          (const char *)0x80070490LL,
          v21);
        LeaveCriticalSection(&stru_180064458);
        *a3 = GetTsAudioProtocol(a2);
        *a4 = 0;
      }
      else
      {
        v20 = *(_QWORD *)(v18 + 24);
        LeaveCriticalSection(&stru_180064458);
        *a3 = *(_DWORD *)(v20 + 4);
        *a4 = *(_DWORD *)(v20 + 8);
        LeaveCriticalSection(&stru_180064458);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x957,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)0x80070005LL,
      v21);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180009a30  mov     r11, rsp
0x180009a33  push    rbx
0x180009a34  push    rbp
0x180009a35  push    rdi
0x180009a36  push    r14
0x180009a38  sub     rsp, 0D8h
0x180009a3f  mov     rax, cs:__security_cookie
0x180009a46  xor     rax, rsp
0x180009a49  mov     [rsp+0F8h+var_48], rax
0x180009a51  mov     r14, r9
0x180009a54  mov     rdi, r8
0x180009a57  mov     ebx, edx
0x180009a59  mov     rbp, rcx
0x180009a5c  test    r8, r8
0x180009a5f  jz      loc_180009CD6
0x180009a65  test    r9, r9
0x180009a68  jz      loc_180009DC2
0x180009a6e  xorps   xmm0, xmm0
0x180009a71  mov     [r11-28h], rsi
0x180009a75  movups  [rsp+0F8h+var_B0], xmm0
0x180009a7a  mov     [r11-30h], r15
0x180009a7e  xor     eax, eax
0x180009a80  movups  [rsp+0F8h+var_A0], xmm0
0x180009a85  xor     r15d, r15d
0x180009a88  mov     dword ptr [r8], 0FFFFh
0x180009a8f  movups  [rsp+0F8h+var_90], xmm0
0x180009a94  lea     rdx, [rsp+0F8h+RpcCallAttributes]; RpcCallAttributes
0x180009a99  mov     [r9], r15d
0x180009a9c  movups  [rsp+0F8h+var_80], xmm0
0x180009aa1  mov     [r11-50h], rax
0x180009aa5  movups  xmmword ptr [r11-70h], xmm0
0x180009aaa  mov     [rsp+0F8h+SessionId], r15d
0x180009aaf  movups  xmmword ptr [r11-60h], xmm0
0x180009ab4  mov     [rsp+0F8h+RpcCallAttributes], 2
0x180009abc  mov     [rsp+0F8h+var_B4], 10h
0x180009ac4  call    cs:__imp_RpcServerInqCallAttributesW
0x180009aca  mov     esi, eax
0x180009acc  test    eax, eax
0x180009ace  jg      loc_180009D2D
0x180009ad4  test    esi, esi
0x180009ad6  js      loc_180009D49
0x180009adc  mov     rcx, rbp; BindingHandle
0x180009adf  call    cs:__imp_RpcImpersonateClient
0x180009ae5  mov     esi, eax
0x180009ae7  test    eax, eax
0x180009ae9  jg      loc_180009D3B
0x180009aef  test    esi, esi
0x180009af1  js      loc_180009DEB
0x180009af7  mov     [rsp+0F8h+TokenHandle], r15
0x180009afc  call    cs:__imp_GetCurrentThread
0x180009b02  lea     r9, [rsp+0F8h+TokenHandle]; TokenHandle
0x180009b07  mov     edx, 8; DesiredAccess
0x180009b0c  mov     rcx, rax; ThreadHandle
0x180009b0f  mov     r8d, 1; OpenAsSelf
0x180009b15  call    cs:__imp_OpenThreadToken
0x180009b1b  test    eax, eax
0x180009b1d  jz      loc_180009D67
0x180009b23  mov     rcx, [rsp+0F8h+TokenHandle]; TokenHandle
0x180009b28  lea     rax, [rsp+0F8h+SessionId]
0x180009b2d  xor     r9d, r9d; unsigned __int16 **
0x180009b30  mov     qword ptr [rsp+0F8h+var_D8], rax; unsigned int
0x180009b35  xor     r8d, r8d; unsigned int *
0x180009b38  xor     edx, edx; unsigned __int16 **
0x180009b3a  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x180009b3f  test    eax, eax
0x180009b41  jnz     loc_180009E11
0x180009b47  mov     rcx, [rsp+0F8h+TokenHandle]; hObject
0x180009b4c  lea     rax, [rcx-1]
0x180009b50  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009b54  jbe     loc_180009E3E
0x180009b5a  call    cs:__imp_RpcRevertToSelf
0x180009b60  cmp     ebx, 0FFFFFFFFh
0x180009b63  cmovz   ebx, [rsp+0F8h+SessionId]
0x180009b68  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180009b6e  mov     ecx, [rsp+0F8h+SessionId]
0x180009b72  cmp     ebx, ecx
0x180009b74  jnz     loc_180009CFC
0x180009b7a  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180009b80  cmp     ebx, eax
0x180009b82  jz      loc_180009E49
0x180009b88  lea     rcx, stru_180064458; lpCriticalSection
0x180009b8f  mov     dword ptr [rdi], 0FFFFh
0x180009b95  call    cs:__imp_EnterCriticalSection
0x180009b9b  lea     rcx, stru_180064458; lpCriticalSection
0x180009ba2  call    cs:__imp_EnterCriticalSection
0x180009ba8  mov     eax, ebx
0x180009baa  movzx   r9d, bl
0x180009bae  shr     eax, 10h
0x180009bb1  mov     r8d, ebx
0x180009bb4  movzx   edx, al
0x180009bb7  mov     eax, ebx
0x180009bb9  shr     r8d, 18h
0x180009bbd  shr     eax, 8
0x180009bc0  movzx   ecx, al
0x180009bc3  lfence
0x180009bc6  mov     rax, 0CBF29CE484222325h
0x180009bd0  xor     r9, rax
0x180009bd3  mov     rax, 100000001B3h
0x180009bdd  imul    r9, rax
0x180009be1  xor     r9, rcx
0x180009be4  imul    r9, rax
0x180009be8  xor     r9, rdx
0x180009beb  mov     rdx, cs:qword_180064488
0x180009bf2  imul    r9, rax
0x180009bf6  xor     r9, r8
0x180009bf9  imul    r9, rax
0x180009bfd  mov     rax, cs:qword_180064498
0x180009c04  and     r9, cs:qword_1800644B0
0x180009c0b  add     r9, r9
0x180009c0e  mov     rcx, [rax+r9*8+8]
0x180009c13  cmp     rcx, rdx
0x180009c16  jz      short loc_180009C2C
0x180009c18  mov     r8, [rax+r9*8]
0x180009c1c  cmp     ebx, [rcx+10h]
0x180009c1f  jz      short loc_180009C2F
0x180009c21  cmp     rcx, r8
0x180009c24  jz      short loc_180009C2C
0x180009c26  mov     rcx, [rcx+8]
0x180009c2a  jmp     short loc_180009C1C
0x180009c2c  mov     rcx, r15
0x180009c2f  test    rcx, rcx
0x180009c32  mov     rax, rdx
0x180009c35  cmovnz  rax, rcx
0x180009c39  lea     rcx, stru_180064458; lpCriticalSection
0x180009c40  cmp     rax, rdx
0x180009c43  jnz     short loc_180009CB2
0x180009c45  call    cs:__imp_LeaveCriticalSection
0x180009c4b  mov     rcx, [rsp+0F8h]; this
0x180009c53  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009c5a  mov     r9d, 80070490h; char *
0x180009c60  mov     edx, 471h; void *
0x180009c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c6a  lea     rcx, stru_180064458; lpCriticalSection
0x180009c71  call    cs:__imp_LeaveCriticalSection
0x180009c77  mov     ecx, ebx; SessionId
0x180009c79  call    ?GetTsAudioProtocol@@YAIK@Z; GetTsAudioProtocol(ulong)
0x180009c7e  mov     [rdi], eax
0x180009c80  mov     [r14], r15d
0x180009c83  xor     eax, eax
0x180009c85  mov     rsi, [rsp+0F8h+var_28]
0x180009c8d  mov     r15, [rsp+0F8h+var_30]
0x180009c95  mov     rcx, [rsp+0F8h+var_48]
0x180009c9d  xor     rcx, rsp; StackCookie
0x180009ca0  call    __security_check_cookie
0x180009ca5  add     rsp, 0D8h
0x180009cac  pop     r14
0x180009cae  pop     rdi
0x180009caf  pop     rbp
0x180009cb0  pop     rbx
0x180009cb1  retn
0x180009cb2  mov     rbx, [rax+18h]
0x180009cb6  call    cs:__imp_LeaveCriticalSection
0x180009cbc  mov     eax, [rbx+4]
0x180009cbf  lea     rcx, stru_180064458; lpCriticalSection
0x180009cc6  mov     [rdi], eax
0x180009cc8  mov     eax, [rbx+8]
0x180009ccb  mov     [r14], eax
0x180009cce  call    cs:__imp_LeaveCriticalSection
0x180009cd4  jmp     short loc_180009C83
0x180009cd6  mov     rcx, [rsp+0F8h]; this
0x180009cde  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009ce5  mov     r9d, 80070057h; char *
0x180009ceb  mov     edx, 944h; void *
0x180009cf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cf5  mov     eax, 80070057h
0x180009cfa  jmp     short loc_180009C95
0x180009cfc  cmp     ecx, eax
0x180009cfe  jz      loc_180009B7A
0x180009d04  mov     rcx, [rsp+0F8h]; this
0x180009d0c  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009d13  mov     r9d, 80070005h; char *
0x180009d19  mov     edx, 957h; void *
0x180009d1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d23  mov     eax, 80070005h
0x180009d28  jmp     loc_180009C85
0x180009d2d  movzx   esi, ax
0x180009d30  or      esi, 80070000h
0x180009d36  jmp     loc_180009AD4
0x180009d3b  movzx   esi, ax
0x180009d3e  or      esi, 80070000h
0x180009d44  jmp     loc_180009AEF
0x180009d49  mov     rcx, [rsp+0F8h]; this
0x180009d51  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009d58  mov     r9d, esi; char *
0x180009d5b  mov     edx, 122h; void *
0x180009d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d65  jmp     short loc_180009D9F
0x180009d67  mov     rcx, [rsp+0F8h]; this
0x180009d6f  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009d76  mov     edx, 128h; void *
0x180009d7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d80  mov     rcx, [rsp+0F8h+TokenHandle]; hObject
0x180009d85  mov     esi, eax
0x180009d87  lea     rax, [rcx-1]
0x180009d8b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009d8f  jbe     short loc_180009E09
0x180009d91  call    cs:__imp_RpcRevertToSelf
0x180009d97  test    esi, esi
0x180009d99  jns     loc_180009B60
0x180009d9f  mov     rcx, [rsp+0F8h]; this
0x180009da7  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009dae  mov     r9d, esi; char *
0x180009db1  mov     edx, 94Dh; void *
0x180009db6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dbb  mov     eax, esi
0x180009dbd  jmp     loc_180009C85
0x180009dc2  mov     rcx, [rsp+0F8h]; this
0x180009dca  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009dd1  mov     r9d, 80070057h; char *
0x180009dd7  mov     edx, 945h; void *
0x180009ddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009de1  mov     eax, 80070057h
0x180009de6  jmp     loc_180009C95
0x180009deb  mov     rcx, [rsp+0F8h]; this
0x180009df3  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009dfa  mov     r9d, esi; char *
0x180009dfd  mov     edx, 124h; void *
0x180009e02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e07  jmp     short loc_180009D9F
0x180009e09  call    cs:__imp_CloseHandle
0x180009e0f  jmp     short loc_180009D91
0x180009e11  mov     rcx, [rsp+0F8h]; this
0x180009e19  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009e20  mov     r9d, eax; char *
0x180009e23  mov     edx, 12Ah; void *
0x180009e28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009e2d  lea     rcx, [rsp+0F8h+TokenHandle]
0x180009e32  mov     esi, eax
0x180009e34  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009e39  jmp     loc_180009D91
0x180009e3e  call    cs:__imp_CloseHandle
0x180009e44  jmp     loc_180009B5A
0x180009e49  mov     [rdi], r15d
0x180009e4c  mov     [r14], r15d
0x180009e4f  jmp     loc_180009C83
```
