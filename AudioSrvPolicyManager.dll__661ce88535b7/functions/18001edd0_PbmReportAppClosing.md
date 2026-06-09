# PbmReportAppClosing

- ea: `0x18001edd0`
- end: `0x18001efb7`
- name: `PbmReportAppClosing`
- size: `487`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000a080`
- `0x18000a384`
- `0x18000f040`
- `0x180012844`
- `0x18001edd0`
- `0x18001efc0`
- `0x18002acfc`
- `0x180031960`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ee89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ee89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ee73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ee73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001efac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001efac`
- `RPCRT4!RpcRevertToSelf` at `0x18001eec7`
- `RPCRT4!RpcRevertToSelf` at `0x18001eef8`
- `RPCRT4!RpcRevertToSelf` at `0x18001eec7`
- `RPCRT4!RpcRevertToSelf` at `0x18001eef8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ee38`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ee38`
- `RPCRT4!RpcImpersonateClient` at `0x18001ee53`
- `RPCRT4!RpcImpersonateClient` at `0x18001ee53`

## pseudocode

```c
__int64 __fastcall PbmReportAppClosing(
        RPC_BINDING_HANDLE BindingHandle,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  signed int LastError; // ebx
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  HANDLE CurrentThread; // rax
  const char *v10; // r9
  unsigned int TokenInformation; // eax
  CPlaybackManager *v12; // rcx
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-69h]
  unsigned int v16; // [rsp+20h] [rbp-69h]
  unsigned int v17; // [rsp+30h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[104]; // [rsp+48h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v17 = 0;
  LastError = -2147418113;
  if ( !g_PlaybackManager )
    return (unsigned int)LastError;
  memset_0(v20, 0, sizeof(v20));
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v7 = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes);
  LastError = v7;
  if ( v7 > 0 )
    LastError = (unsigned __int16)v7 | 0x80070000;
  if ( LastError < 0 )
  {
    v14 = 290;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)LastError,
      v15);
    return (unsigned int)LastError;
  }
  v8 = RpcImpersonateClient(BindingHandle);
  LastError = v8;
  if ( v8 > 0 )
    LastError = (unsigned __int16)v8 | 0x80070000;
  if ( LastError < 0 )
  {
    v14 = 292;
    goto LABEL_19;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    TokenInformation = GetTokenInformation(TokenHandle, 0, 0, 0, &v17);
    if ( !TokenInformation )
    {
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      RpcRevertToSelf();
      return (unsigned int)CPlaybackManager::OnAppClosed(v12, a2, a3, v17);
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  (const char *)TokenInformation,
                  v16);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  v10);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  RpcRevertToSelf();
  if ( !LastError )
    return (unsigned int)CPlaybackManager::OnAppClosed(v12, a2, a3, v17);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001edd0  push    rbp
0x18001edd2  push    rbx
0x18001edd3  push    rsi
0x18001edd4  push    rdi
0x18001edd5  push    r14
0x18001edd7  lea     rbp, [rsp-37h]
0x18001eddc  sub     rsp, 0C0h
0x18001ede3  mov     rax, cs:__security_cookie
0x18001edea  xor     rax, rsp
0x18001eded  mov     [rbp+57h+var_30], rax
0x18001edf1  cmp     cs:?g_PlaybackManager@@3PEAVCPlaybackManager@@EA, 0; CPlaybackManager * g_PlaybackManager
0x18001edf9  mov     r14, r8
0x18001edfc  mov     rsi, rdx
0x18001edff  mov     [rbp+57h+var_B0], 0
0x18001ee06  mov     rdi, rcx
0x18001ee09  mov     ebx, 8000FFFFh
0x18001ee0e  jz      loc_18001EF13
0x18001ee14  xor     edx, edx; Val
0x18001ee16  lea     rcx, [rbp+57h+var_98]; void *
0x18001ee1a  lea     r8d, [rdx+68h]; Size
0x18001ee1e  call    memset_0
0x18001ee23  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18001ee27  mov     [rbp+57h+RpcCallAttributes], 2
0x18001ee2e  mov     rcx, rdi; ClientBinding
0x18001ee31  mov     [rbp+57h+var_9C], 10h
0x18001ee38  call    cs:__imp_RpcServerInqCallAttributesW
0x18001ee3e  mov     ebx, eax
0x18001ee40  test    eax, eax
0x18001ee42  jg      loc_18001EF2F
0x18001ee48  test    ebx, ebx
0x18001ee4a  js      loc_18001EF4B
0x18001ee50  mov     rcx, rdi; BindingHandle
0x18001ee53  call    cs:__imp_RpcImpersonateClient
0x18001ee59  mov     ebx, eax
0x18001ee5b  test    eax, eax
0x18001ee5d  jg      loc_18001EF3D
0x18001ee63  test    ebx, ebx
0x18001ee65  js      loc_18001EF72
0x18001ee6b  mov     [rbp+57h+TokenHandle], 0
0x18001ee73  call    cs:__imp_GetCurrentThread
0x18001ee79  mov     edx, 8; DesiredAccess
0x18001ee7e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001ee82  mov     rcx, rax; ThreadHandle
0x18001ee85  lea     r8d, [rdx-7]; OpenAsSelf
0x18001ee89  call    cs:__imp_OpenThreadToken
0x18001ee8f  test    eax, eax
0x18001ee91  jz      short loc_18001EECF
0x18001ee93  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001ee97  lea     rax, [rbp+57h+var_B0]
0x18001ee9b  xor     r9d, r9d; unsigned __int16 **
0x18001ee9e  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x18001eea3  xor     r8d, r8d; unsigned int *
0x18001eea6  xor     edx, edx; unsigned __int16 **
0x18001eea8  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x18001eead  test    eax, eax
0x18001eeaf  jnz     loc_18001EF84
0x18001eeb5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001eeb9  lea     rax, [rcx-1]
0x18001eebd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001eec1  jbe     loc_18001EFAC
0x18001eec7  call    cs:__imp_RpcRevertToSelf
0x18001eecd  jmp     short loc_18001EF02
0x18001eecf  mov     rcx, [rbp+5Fh]; this
0x18001eed3  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001eeda  mov     edx, 128h; void *
0x18001eedf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001eee4  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001eee8  mov     ebx, eax
0x18001eeea  lea     rax, [rcx-1]
0x18001eeee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001eef2  jbe     loc_18001EF79
0x18001eef8  call    cs:__imp_RpcRevertToSelf
0x18001eefe  test    ebx, ebx
0x18001ef00  jnz     short loc_18001EF65
0x18001ef02  mov     r9d, [rbp+57h+var_B0]; unsigned int
0x18001ef06  mov     r8, r14; unsigned __int64
0x18001ef09  mov     rdx, rsi; unsigned __int16 *
0x18001ef0c  call    ?OnAppClosed@CPlaybackManager@@QEAAJPEBG_KK@Z; CPlaybackManager::OnAppClosed(ushort const *,unsigned __int64,ulong)
0x18001ef11  mov     ebx, eax
0x18001ef13  mov     eax, ebx
0x18001ef15  mov     rcx, [rbp+57h+var_30]
0x18001ef19  xor     rcx, rsp; StackCookie
0x18001ef1c  call    __security_check_cookie
0x18001ef21  add     rsp, 0C0h
0x18001ef28  pop     r14
0x18001ef2a  pop     rdi
0x18001ef2b  pop     rsi
0x18001ef2c  pop     rbx
0x18001ef2d  pop     rbp
0x18001ef2e  retn
0x18001ef2f  movzx   ebx, ax
0x18001ef32  or      ebx, 80070000h
0x18001ef38  jmp     loc_18001EE48
0x18001ef3d  movzx   ebx, ax
0x18001ef40  or      ebx, 80070000h
0x18001ef46  jmp     loc_18001EE63
0x18001ef4b  mov     edx, 122h; void *
0x18001ef50  mov     rcx, [rbp+5Fh]; this
0x18001ef54  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001ef5b  mov     r9d, ebx; char *
0x18001ef5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef63  jmp     short loc_18001EF13
0x18001ef65  jle     short loc_18001EF13
0x18001ef67  movzx   ebx, bx
0x18001ef6a  or      ebx, 80070000h
0x18001ef70  jmp     short loc_18001EF13
0x18001ef72  mov     edx, 124h
0x18001ef77  jmp     short loc_18001EF50
0x18001ef79  call    cs:__imp_CloseHandle
0x18001ef7f  jmp     loc_18001EEF8
0x18001ef84  mov     rcx, [rbp+5Fh]; this
0x18001ef88  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001ef8f  mov     r9d, eax; char *
0x18001ef92  mov     edx, 12Ah; void *
0x18001ef97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ef9c  lea     rcx, [rbp+57h+TokenHandle]
0x18001efa0  mov     ebx, eax
0x18001efa2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001efa7  jmp     loc_18001EEF8
0x18001efac  call    cs:__imp_CloseHandle
0x18001efb2  jmp     loc_18001EEC7
```
