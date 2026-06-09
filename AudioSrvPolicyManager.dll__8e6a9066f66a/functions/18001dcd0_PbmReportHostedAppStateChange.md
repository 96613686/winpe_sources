# PbmReportHostedAppStateChange

- ea: `0x18001dcd0`
- end: `0x18001ded0`
- name: `PbmReportHostedAppStateChange`
- size: `512`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000a080`
- `0x18000a384`
- `0x18000f040`
- `0x180012844`
- `0x18001dcd0`
- `0x18001ded8`
- `0x18002acfc`
- `0x180031960`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ddab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ddab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dd95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dd95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dec5`
- `RPCRT4!RpcRevertToSelf` at `0x18001dde9`
- `RPCRT4!RpcRevertToSelf` at `0x18001de16`
- `RPCRT4!RpcRevertToSelf` at `0x18001dde9`
- `RPCRT4!RpcRevertToSelf` at `0x18001de16`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001dd5a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001dd5a`
- `RPCRT4!RpcImpersonateClient` at `0x18001dd75`
- `RPCRT4!RpcImpersonateClient` at `0x18001dd75`

## pseudocode

```c
__int64 __fastcall PbmReportHostedAppStateChange(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  signed int LastError; // ebx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  HANDLE CurrentThread; // rax
  const char *v14; // r9
  unsigned int TokenInformation; // eax
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-81h]
  unsigned int v18; // [rsp+20h] [rbp-81h]
  unsigned int v19; // [rsp+30h] [rbp-71h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-69h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v22[104]; // [rsp+48h] [rbp-59h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v19 = 0;
  if ( !a5 )
    return (unsigned int)-2147024809;
  memset_0(v22, 0, sizeof(v22));
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v11 = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes);
  LastError = v11;
  if ( v11 > 0 )
    LastError = (unsigned __int16)v11 | 0x80070000;
  if ( LastError < 0 )
  {
    v16 = 290;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)LastError,
      v17);
    return (unsigned int)LastError;
  }
  v12 = RpcImpersonateClient(BindingHandle);
  LastError = v12;
  if ( v12 > 0 )
    LastError = (unsigned __int16)v12 | 0x80070000;
  if ( LastError < 0 )
  {
    v16 = 292;
    goto LABEL_20;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    TokenInformation = GetTokenInformation(TokenHandle, 0, 0, 0, &v19);
    if ( !TokenInformation )
    {
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      RpcRevertToSelf();
      return (unsigned int)PickerHostContextManager::OnHostedAppStateChanged(a2, a3, v19, a4, a5);
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  (const char *)TokenInformation,
                  v18);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  v14);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  RpcRevertToSelf();
  if ( !LastError )
    return (unsigned int)PickerHostContextManager::OnHostedAppStateChanged(a2, a3, v19, a4, a5);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001dcd0  push    rbp
0x18001dcd2  push    rbx
0x18001dcd3  push    rsi
0x18001dcd4  push    rdi
0x18001dcd5  push    r12
0x18001dcd7  push    r14
0x18001dcd9  push    r15
0x18001dcdb  lea     rbp, [rsp-1Fh]
0x18001dce0  sub     rsp, 0C0h
0x18001dce7  mov     rax, cs:__security_cookie
0x18001dcee  xor     rax, rsp
0x18001dcf1  mov     [rbp+4Fh+var_40], rax
0x18001dcf5  mov     rsi, [rbp+4Fh+arg_20]
0x18001dcf9  mov     r12d, r9d
0x18001dcfc  mov     [rbp+4Fh+var_C0], 0
0x18001dd03  mov     r15, r8
0x18001dd06  mov     r14, rdx
0x18001dd09  mov     rdi, rcx
0x18001dd0c  test    rsi, rsi
0x18001dd0f  jnz     short loc_18001DD36
0x18001dd11  mov     ebx, 80070057h
0x18001dd16  mov     eax, ebx
0x18001dd18  mov     rcx, [rbp+4Fh+var_40]
0x18001dd1c  xor     rcx, rsp; StackCookie
0x18001dd1f  call    __security_check_cookie
0x18001dd24  add     rsp, 0C0h
0x18001dd2b  pop     r15
0x18001dd2d  pop     r14
0x18001dd2f  pop     r12
0x18001dd31  pop     rdi
0x18001dd32  pop     rsi
0x18001dd33  pop     rbx
0x18001dd34  pop     rbp
0x18001dd35  retn
0x18001dd36  xor     edx, edx; Val
0x18001dd38  lea     rcx, [rbp+4Fh+var_A8]; void *
0x18001dd3c  lea     r8d, [rdx+68h]; Size
0x18001dd40  call    memset_0
0x18001dd45  lea     rdx, [rbp+4Fh+RpcCallAttributes]; RpcCallAttributes
0x18001dd49  mov     [rbp+4Fh+RpcCallAttributes], 2
0x18001dd50  mov     rcx, rdi; ClientBinding
0x18001dd53  mov     [rbp+4Fh+var_AC], 10h
0x18001dd5a  call    cs:__imp_RpcServerInqCallAttributesW
0x18001dd60  mov     ebx, eax
0x18001dd62  test    eax, eax
0x18001dd64  jg      loc_18001DE3E
0x18001dd6a  test    ebx, ebx
0x18001dd6c  js      loc_18001DE5A
0x18001dd72  mov     rcx, rdi; BindingHandle
0x18001dd75  call    cs:__imp_RpcImpersonateClient
0x18001dd7b  mov     ebx, eax
0x18001dd7d  test    eax, eax
0x18001dd7f  jg      loc_18001DE4C
0x18001dd85  test    ebx, ebx
0x18001dd87  js      loc_18001DE8B
0x18001dd8d  mov     [rbp+4Fh+TokenHandle], 0
0x18001dd95  call    cs:__imp_GetCurrentThread
0x18001dd9b  mov     edx, 8; DesiredAccess
0x18001dda0  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x18001dda4  mov     rcx, rax; ThreadHandle
0x18001dda7  lea     r8d, [rdx-7]; OpenAsSelf
0x18001ddab  call    cs:__imp_OpenThreadToken
0x18001ddb1  test    eax, eax
0x18001ddb3  jz      short loc_18001DDF1
0x18001ddb5  mov     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x18001ddb9  lea     rax, [rbp+4Fh+var_C0]
0x18001ddbd  xor     r9d, r9d; unsigned __int16 **
0x18001ddc0  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x18001ddc5  xor     r8d, r8d; unsigned int *
0x18001ddc8  xor     edx, edx; unsigned __int16 **
0x18001ddca  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x18001ddcf  test    eax, eax
0x18001ddd1  jnz     loc_18001DE9D
0x18001ddd7  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x18001dddb  lea     rax, [rcx-1]
0x18001dddf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001dde3  jbe     loc_18001DEC5
0x18001dde9  call    cs:__imp_RpcRevertToSelf
0x18001ddef  jmp     short loc_18001DE20
0x18001ddf1  mov     rcx, [rbp+57h]; this
0x18001ddf5  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001ddfc  mov     edx, 128h; void *
0x18001de01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001de06  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x18001de0a  mov     ebx, eax
0x18001de0c  lea     rax, [rcx-1]
0x18001de10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001de14  jbe     short loc_18001DE92
0x18001de16  call    cs:__imp_RpcRevertToSelf
0x18001de1c  test    ebx, ebx
0x18001de1e  jnz     short loc_18001DE77
0x18001de20  mov     r8d, [rbp+4Fh+var_C0]
0x18001de24  mov     r9d, r12d
0x18001de27  mov     rdx, r15
0x18001de2a  mov     qword ptr [rsp+0F0h+var_D0], rsi
0x18001de2f  mov     rcx, r14
0x18001de32  call    ?OnHostedAppStateChanged@PickerHostContextManager@@YAJPEBG_KKW4HOSTED_APP_CHANGED@@PEAPEAX@Z; PickerHostContextManager::OnHostedAppStateChanged(ushort const *,unsigned __int64,ulong,HOSTED_APP_CHANGED,void * *)
0x18001de37  mov     ebx, eax
0x18001de39  jmp     loc_18001DD16
0x18001de3e  movzx   ebx, ax
0x18001de41  or      ebx, 80070000h
0x18001de47  jmp     loc_18001DD6A
0x18001de4c  movzx   ebx, ax
0x18001de4f  or      ebx, 80070000h
0x18001de55  jmp     loc_18001DD85
0x18001de5a  mov     edx, 122h; void *
0x18001de5f  mov     rcx, [rbp+57h]; this
0x18001de63  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001de6a  mov     r9d, ebx; char *
0x18001de6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de72  jmp     loc_18001DD16
0x18001de77  jle     loc_18001DD16
0x18001de7d  movzx   ebx, bx
0x18001de80  or      ebx, 80070000h
0x18001de86  jmp     loc_18001DD16
0x18001de8b  mov     edx, 124h
0x18001de90  jmp     short loc_18001DE5F
0x18001de92  call    cs:__imp_CloseHandle
0x18001de98  jmp     loc_18001DE16
0x18001de9d  mov     rcx, [rbp+57h]; this
0x18001dea1  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001dea8  mov     r9d, eax; char *
0x18001deab  mov     edx, 12Ah; void *
0x18001deb0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001deb5  lea     rcx, [rbp+4Fh+TokenHandle]
0x18001deb9  mov     ebx, eax
0x18001debb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dec0  jmp     loc_18001DE16
0x18001dec5  call    cs:__imp_CloseHandle
0x18001decb  jmp     loc_18001DDE9
```
