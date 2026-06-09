# cdp::GetCurrentUserContextToken(unsigned __int64 &)

- ea: `0x18000a2c0`
- end: `0x18000a515`
- name: `?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z`
- size: `597`
- prototype: `__int64 __fastcall(cdp *__hidden this, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000a000`
- `0x18000a240`
- `0x18000afc0`
- `0x1800209c0`

## callees

- `0x18000a2c0`
- `0x180019e9c`
- `0x180039eb0`
- `0x18005c2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a366`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a366`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a313`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a354`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a354`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a2fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a2fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a50a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000a38a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000a38a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall cdp::GetCurrentUserContextToken(cdp *this, unsigned __int64 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v7; // ecx
  int v8; // r9d
  signed int v9; // edi
  void *v10; // rsi
  HANDLE CurrentProcess; // rax
  void *v12; // rdi
  int UserContext; // eax
  int v14; // ecx
  int v15; // r9d
  int v17; // ecx
  int v18; // r9d
  signed int v19; // eax
  int v20; // ecx
  int v21; // r9d
  signed int v22; // ebx
  DWORD v23; // edi
  int v24; // [rsp+60h] [rbp+30h] BYREF
  int v25; // [rsp+68h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  *(_QWORD *)this = 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent(this, a2) )
    return 0;
  TokenHandle = 0;
  if ( (NtCurrentPeb()->BitField & 0x20) != 0
    || (TokenHandle = 0, CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)) )
  {
LABEL_10:
    v12 = TokenHandle;
    *(_QWORD *)this = 0;
    if ( (unsigned __int8)IsUMgrQueryUserContextPresent(v4, v3) )
    {
      UserContext = UMgrQueryUserContext(v12, this);
      if ( UserContext == -2147023584 )
      {
        *(_QWORD *)this = 0;
      }
      else if ( UserContext < 0 )
      {
        v24 = UserContext;
        v25 = 115;
        Log<long &,char const (&)[20],int>(
          v14,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
          (unsigned int)&v24,
          v15,
          (__int64)&v25);
        if ( v24 < 0 )
        {
          v25 = 149;
          Log<long &,char const (&)[20],int>(
            v17,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v24,
            v18,
            (__int64)&v25);
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
          return (unsigned int)v24;
        }
      }
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 0;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 == -2147023888 )
  {
    v10 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v23 = GetLastError();
      CloseHandle(v10);
      SetLastError(v23);
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_10;
    v19 = GetLastError();
    v22 = v19;
    if ( v19 > 0 )
      v22 = (unsigned __int16)v19 | 0x80070000;
    v24 = v22;
    if ( v22 < 0 )
    {
      v25 = 144;
      Log<long &,char const (&)[20],int>(
        v20,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&v24,
        v21,
        (__int64)&v25);
      v22 = v24;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(&TokenHandle);
    return (unsigned int)v22;
  }
  else
  {
    v24 = v9;
    if ( v9 < 0 )
    {
      v25 = 140;
      Log<long &,char const (&)[20],int>(
        v7,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&v24,
        v8,
        (__int64)&v25);
      v9 = v24;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18000a2c0  push    rbp
0x18000a2c2  push    rbx
0x18000a2c3  push    rsi
0x18000a2c4  push    rdi
0x18000a2c5  push    r14
0x18000a2c7  mov     rbp, rsp
0x18000a2ca  sub     rsp, 30h
0x18000a2ce  mov     rbx, rcx
0x18000a2d1  xor     r14d, r14d
0x18000a2d4  mov     [rcx], r14
0x18000a2d7  call    IsUMgrQueryUserContextPresent
0x18000a2dc  test    al, al
0x18000a2de  jz      loc_18000A3B1
0x18000a2e4  mov     [rbp+TokenHandle], r14
0x18000a2e8  mov     rax, gs:60h
0x18000a2f1  test    byte ptr [rax+3], 20h
0x18000a2f5  jnz     short loc_18000A374
0x18000a2f7  mov     [rbp+TokenHandle], r14
0x18000a2fb  call    cs:__imp_GetCurrentThread
0x18000a301  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000a305  mov     edx, 8; DesiredAccess
0x18000a30a  mov     r8d, 1; OpenAsSelf
0x18000a310  mov     rcx, rax; ThreadHandle
0x18000a313  call    cs:__imp_OpenThreadToken
0x18000a319  test    eax, eax
0x18000a31b  jnz     short loc_18000A374
0x18000a31d  call    cs:__imp_GetLastError
0x18000a323  mov     edi, eax
0x18000a325  test    eax, eax
0x18000a327  jle     short loc_18000A332
0x18000a329  movzx   edi, ax
0x18000a32c  or      edi, 80070000h
0x18000a332  cmp     edi, 800703F0h
0x18000a338  jnz     loc_18000A3BE
0x18000a33e  mov     rsi, [rbp+TokenHandle]
0x18000a342  lea     rax, [rsi-1]
0x18000a346  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a34a  jbe     loc_18000A4D9
0x18000a350  mov     [rbp+TokenHandle], r14
0x18000a354  call    cs:__imp_GetCurrentProcess
0x18000a35a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000a35e  mov     edx, 8; DesiredAccess
0x18000a363  mov     rcx, rax; ProcessHandle
0x18000a366  call    cs:__imp_OpenProcessToken
0x18000a36c  test    eax, eax
0x18000a36e  jz      loc_18000A456
0x18000a374  mov     rdi, [rbp+TokenHandle]
0x18000a378  mov     [rbx], r14
0x18000a37b  call    IsUMgrQueryUserContextPresent
0x18000a380  test    al, al
0x18000a382  jz      short loc_18000A39F
0x18000a384  mov     rdx, rbx
0x18000a387  mov     rcx, rdi
0x18000a38a  call    cs:__imp_UMgrQueryUserContext
0x18000a390  cmp     eax, 80070520h
0x18000a395  jz      loc_18000A4F7
0x18000a39b  test    eax, eax
0x18000a39d  js      short loc_18000A3E8
0x18000a39f  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a3a3  lea     rax, [rcx-1]
0x18000a3a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a3ab  jbe     loc_18000A50A
0x18000a3b1  xor     eax, eax
0x18000a3b3  add     rsp, 30h
0x18000a3b7  pop     r14
0x18000a3b9  pop     rdi
0x18000a3ba  pop     rsi
0x18000a3bb  pop     rbx
0x18000a3bc  pop     rbp
0x18000a3bd  retn
0x18000a3be  mov     [rbp+arg_0], edi
0x18000a3c1  test    edi, edi
0x18000a3c3  js      loc_18000A4A6
0x18000a3c9  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a3cd  lea     rdx, [rcx-1]
0x18000a3d1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a3d5  jbe     loc_18000A4CE
0x18000a3db  mov     eax, edi
0x18000a3dd  add     rsp, 30h
0x18000a3e1  pop     r14
0x18000a3e3  pop     rdi
0x18000a3e4  pop     rsi
0x18000a3e5  pop     rbx
0x18000a3e6  pop     rbp
0x18000a3e7  retn
0x18000a3e8  mov     [rbp+arg_0], eax
0x18000a3eb  mov     [rbp+arg_8], 73h ; 's'
0x18000a3f2  lea     rax, [rbp+arg_8]
0x18000a3f6  mov     [rsp+30h+var_10], rax
0x18000a3fb  lea     r8, [rbp+arg_0]
0x18000a3ff  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000a406  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x18000a40b  mov     eax, [rbp+arg_0]
0x18000a40e  test    eax, eax
0x18000a410  jns     short loc_18000A39F
0x18000a412  mov     [rbp+arg_0], eax
0x18000a415  mov     [rbp+arg_8], 95h
0x18000a41c  lea     rax, [rbp+arg_8]
0x18000a420  mov     [rsp+30h+var_10], rax
0x18000a425  lea     r8, [rbp+arg_0]
0x18000a429  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000a430  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x18000a435  nop
0x18000a436  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a43a  lea     rdx, [rcx-1]
0x18000a43e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a442  jbe     loc_18000A4FF
0x18000a448  mov     eax, [rbp+arg_0]
0x18000a44b  add     rsp, 30h
0x18000a44f  pop     r14
0x18000a451  pop     rdi
0x18000a452  pop     rsi
0x18000a453  pop     rbx
0x18000a454  pop     rbp
0x18000a455  retn
0x18000a456  call    cs:__imp_GetLastError
0x18000a45c  nop
0x18000a45d  mov     ebx, eax
0x18000a45f  test    eax, eax
0x18000a461  jle     short loc_18000A46C
0x18000a463  movzx   ebx, ax
0x18000a466  or      ebx, 80070000h
0x18000a46c  mov     [rbp+arg_0], ebx
0x18000a46f  test    ebx, ebx
0x18000a471  jns     short loc_18000A496
0x18000a473  mov     [rbp+arg_8], 90h
0x18000a47a  lea     rax, [rbp+arg_8]
0x18000a47e  mov     [rsp+30h+var_10], rax
0x18000a483  lea     r8, [rbp+arg_0]
0x18000a487  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000a48e  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x18000a493  mov     ebx, [rbp+arg_0]
0x18000a496  lea     rcx, [rbp+TokenHandle]
0x18000a49a  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18000a49f  mov     eax, ebx
0x18000a4a1  jmp     loc_18000A3B3
0x18000a4a6  mov     [rbp+arg_8], 8Ch
0x18000a4ad  lea     rax, [rbp+arg_8]
0x18000a4b1  mov     [rsp+30h+var_10], rax
0x18000a4b6  lea     r8, [rbp+arg_0]
0x18000a4ba  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000a4c1  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x18000a4c6  mov     edi, [rbp+arg_0]
0x18000a4c9  jmp     loc_18000A3C9
0x18000a4ce  call    cs:__imp_CloseHandle
0x18000a4d4  jmp     loc_18000A3DB
0x18000a4d9  call    cs:__imp_GetLastError
0x18000a4df  mov     edi, eax
0x18000a4e1  mov     rcx, rsi; hObject
0x18000a4e4  call    cs:__imp_CloseHandle
0x18000a4ea  mov     ecx, edi; dwErrCode
0x18000a4ec  call    cs:__imp_SetLastError
0x18000a4f2  jmp     loc_18000A350
0x18000a4f7  mov     [rbx], r14
0x18000a4fa  jmp     loc_18000A39F
0x18000a4ff  call    cs:__imp_CloseHandle
0x18000a505  jmp     loc_18000A448
0x18000a50a  call    cs:__imp_CloseHandle
0x18000a510  jmp     loc_18000A3B1
```
