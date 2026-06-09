# RpcClientProcessSessionId(void *,ulong *,ulong *)

- ea: `0x180009e60`
- end: `0x18000a06f`
- name: `?RpcClientProcessSessionId@@YAJPEAXPEAK1@Z`
- size: `527`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned int *, unsigned int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024410`
- `0x180025750`
- `0x180027110`
- `0x180040940`
- `0x180040c60`
- `0x1800410c0`

## callees

- `0x180009e60`
- `0x18000a080`
- `0x18000a384`
- `0x18000f040`
- `0x180012844`
- `0x18002acfc`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009f1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009f1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a064`
- `RPCRT4!RpcRevertToSelf` at `0x180009f66`
- `RPCRT4!RpcRevertToSelf` at `0x180009ff7`
- `RPCRT4!RpcRevertToSelf` at `0x18000a057`
- `RPCRT4!RpcRevertToSelf` at `0x180009f66`
- `RPCRT4!RpcRevertToSelf` at `0x180009ff7`
- `RPCRT4!RpcRevertToSelf` at `0x18000a057`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009ec8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009ec8`
- `RPCRT4!RpcImpersonateClient` at `0x180009ee3`
- `RPCRT4!RpcImpersonateClient` at `0x180009ee3`

## pseudocode

```c
__int64 __fastcall RpcClientProcessSessionId(RPC_BINDING_HANDLE BindingHandle, unsigned int *a2, unsigned int *a3)
{
  RPC_STATUS v6; // eax
  unsigned int v7; // ebx
  RPC_STATUS v8; // eax
  unsigned int v9; // ebx
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  unsigned int TokenInformation; // eax
  char *v13; // rcx
  unsigned int LastError; // ebx
  unsigned int v16; // ebx
  int v17; // [rsp+20h] [rbp-B8h]
  unsigned int v18; // [rsp+20h] [rbp-B8h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-98h] BYREF
  __int128 v21; // [rsp+48h] [rbp-90h]
  __int128 v22; // [rsp+58h] [rbp-80h]
  __int128 v23; // [rsp+68h] [rbp-70h]
  __int128 v24; // [rsp+78h] [rbp-60h]
  __int128 v25; // [rsp+88h] [rbp-50h]
  __int128 v26; // [rsp+98h] [rbp-40h]
  __int64 v27; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v6 = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)v7,
      v17);
    return v7;
  }
  else
  {
    v8 = RpcImpersonateClient(BindingHandle);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)v9,
        v17);
      return v9;
    }
    else
    {
      TokenHandle[0] = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
      {
        TokenInformation = GetTokenInformation(TokenHandle[0], 0, 0, 0, a3);
        if ( TokenInformation )
        {
          v16 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  (const char *)TokenInformation,
                  v18);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
          RpcRevertToSelf();
          return v16;
        }
        else
        {
          v13 = (char *)TokenHandle[0];
          *a2 = DWORD2(v24);
          if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v13);
          RpcRevertToSelf();
          return 0;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x128,
                      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                      v11);
        if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(TokenHandle[0]);
        RpcRevertToSelf();
        return LastError;
      }
    }
  }
}

```

## disassembly

```asm
0x180009e60  mov     r11, rsp
0x180009e63  mov     [r11+20h], rbx
0x180009e67  push    rbp
0x180009e68  push    rsi
0x180009e69  push    rdi
0x180009e6a  sub     rsp, 0C0h
0x180009e71  mov     rax, cs:__security_cookie
0x180009e78  xor     rax, rsp
0x180009e7b  mov     [rsp+0D8h+var_28], rax
0x180009e83  xorps   xmm0, xmm0
0x180009e86  xor     eax, eax
0x180009e88  movups  [rsp+0D8h+var_90], xmm0
0x180009e8d  mov     rsi, rdx
0x180009e90  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x180009e95  movups  [rsp+0D8h+var_80], xmm0
0x180009e9a  mov     rbp, r8
0x180009e9d  mov     rdi, rcx
0x180009ea0  movups  [rsp+0D8h+var_70], xmm0
0x180009ea5  movups  [rsp+0D8h+var_60], xmm0
0x180009eaa  mov     [r11-30h], rax
0x180009eae  movups  xmmword ptr [r11-50h], xmm0
0x180009eb3  movups  xmmword ptr [r11-40h], xmm0
0x180009eb8  mov     [rsp+0D8h+RpcCallAttributes], 2
0x180009ec0  mov     [rsp+0D8h+var_94], 10h
0x180009ec8  call    cs:__imp_RpcServerInqCallAttributesW
0x180009ece  mov     ebx, eax
0x180009ed0  test    eax, eax
0x180009ed2  jg      loc_180009F91
0x180009ed8  test    ebx, ebx
0x180009eda  js      loc_180009FAD
0x180009ee0  mov     rcx, rdi; BindingHandle
0x180009ee3  call    cs:__imp_RpcImpersonateClient
0x180009ee9  mov     ebx, eax
0x180009eeb  test    eax, eax
0x180009eed  jg      loc_180009F9F
0x180009ef3  test    ebx, ebx
0x180009ef5  js      loc_18000A004
0x180009efb  mov     [rsp+0D8h+TokenHandle], 0
0x180009f04  call    cs:__imp_GetCurrentThread
0x180009f0a  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x180009f0f  mov     edx, 8; DesiredAccess
0x180009f14  mov     rcx, rax; ThreadHandle
0x180009f17  mov     r8d, 1; OpenAsSelf
0x180009f1d  call    cs:__imp_OpenThreadToken
0x180009f23  test    eax, eax
0x180009f25  jz      loc_180009FCD
0x180009f2b  mov     rcx, [rsp+0D8h+TokenHandle]; TokenHandle
0x180009f30  xor     r9d, r9d; unsigned __int16 **
0x180009f33  xor     r8d, r8d; unsigned int *
0x180009f36  mov     qword ptr [rsp+0D8h+var_B8], rbp; unsigned int
0x180009f3b  xor     edx, edx; unsigned __int16 **
0x180009f3d  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x180009f42  test    eax, eax
0x180009f44  jnz     loc_18000A02F
0x180009f4a  mov     eax, dword ptr [rsp+0D8h+var_60+8]
0x180009f51  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180009f56  mov     [rsi], eax
0x180009f58  lea     rax, [rcx-1]
0x180009f5c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009f60  jbe     loc_18000A064
0x180009f66  call    cs:__imp_RpcRevertToSelf
0x180009f6c  xor     eax, eax
0x180009f6e  mov     rcx, [rsp+0D8h+var_28]
0x180009f76  xor     rcx, rsp; StackCookie
0x180009f79  call    __security_check_cookie
0x180009f7e  mov     rbx, [rsp+0D8h+arg_18]
0x180009f86  add     rsp, 0C0h
0x180009f8d  pop     rdi
0x180009f8e  pop     rsi
0x180009f8f  pop     rbp
0x180009f90  retn
0x180009f91  movzx   ebx, ax
0x180009f94  or      ebx, 80070000h
0x180009f9a  jmp     loc_180009ED8
0x180009f9f  movzx   ebx, ax
0x180009fa2  or      ebx, 80070000h
0x180009fa8  jmp     loc_180009EF3
0x180009fad  mov     rcx, [rsp+0D8h]; this
0x180009fb5  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009fbc  mov     r9d, ebx; char *
0x180009fbf  mov     edx, 122h; void *
0x180009fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fc9  mov     eax, ebx
0x180009fcb  jmp     short loc_180009F6E
0x180009fcd  mov     rcx, [rsp+0D8h]; this
0x180009fd5  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180009fdc  mov     edx, 128h; void *
0x180009fe1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009fe6  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180009feb  mov     ebx, eax
0x180009fed  lea     rdx, [rcx-1]
0x180009ff1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180009ff5  jbe     short loc_18000A027
0x180009ff7  call    cs:__imp_RpcRevertToSelf
0x180009ffd  mov     eax, ebx
0x180009fff  jmp     loc_180009F6E
0x18000a004  mov     rcx, [rsp+0D8h]; this
0x18000a00c  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18000a013  mov     r9d, ebx; char *
0x18000a016  mov     edx, 124h; void *
0x18000a01b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a020  mov     eax, ebx
0x18000a022  jmp     loc_180009F6E
0x18000a027  call    cs:__imp_CloseHandle
0x18000a02d  jmp     short loc_180009FF7
0x18000a02f  mov     rcx, [rsp+0D8h]; this
0x18000a037  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18000a03e  mov     r9d, eax; char *
0x18000a041  mov     edx, 12Ah; void *
0x18000a046  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a04b  lea     rcx, [rsp+0D8h+TokenHandle]
0x18000a050  mov     ebx, eax
0x18000a052  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a057  call    cs:__imp_RpcRevertToSelf
0x18000a05d  mov     eax, ebx
0x18000a05f  jmp     loc_180009F6E
0x18000a064  call    cs:__imp_CloseHandle
0x18000a06a  jmp     loc_180009F66
```
