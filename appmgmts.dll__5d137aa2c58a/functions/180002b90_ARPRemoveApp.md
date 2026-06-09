# ARPRemoveApp

- ea: `0x180002b90`
- end: `0x180002d2d`
- name: `ARPRemoveApp`
- size: `413`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000239c`
- `0x180002b90`
- `0x1800129c4`
- `0x180012bc4`
- `0x18001af7c`
- `0x18001b1a0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180002be3`
- `RPCRT4!RpcImpersonateClient` at `0x180002be3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002c08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002c1e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002bfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ce1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ce1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002cff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002cff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d12`

## pseudocode

```c
__int64 __fastcall ARPRemoveApp(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  unsigned int v10; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  HMODULE hLibModule; // [rsp+48h] [rbp-8h] BYREF
  int v14; // [rsp+88h] [rbp+38h] BYREF

  v10 = 0;
  TokenHandle = 0;
  phkResult = 0;
  v14 = 0;
  CLoadMsi::CLoadMsi((CLoadMsi *)&hLibModule, &v10);
  LastError = v10;
  if ( v10 )
    goto LABEL_22;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_22;
  LastError = RegOpenCurrentUser(0x10000000u, &phkResult);
  if ( !LastError )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      RegCloseKey(phkResult);
    }
  }
  RevertToSelf();
  if ( LastError )
  {
LABEL_22:
    if ( hLibModule )
      FreeLibrary(hLibModule);
    return LastError;
  }
  else
  {
    LogTime();
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xBF3u, a2);
    v7 = RemoveAppHelper(a2, TokenHandle, phkResult, a3, &v14);
    if ( v14 || !(unsigned int)IsMemberOfAdminGroup(TokenHandle) )
    {
      v8 = v7;
    }
    else
    {
      v7 = RemoveAppHelper(a2, 0, HKEY_LOCAL_MACHINE, a3, &v14);
      v8 = v7;
    }
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xBF4u, v7);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hLibModule )
      FreeLibrary(hLibModule);
    return v8;
  }
}

```

## disassembly

```asm
0x180002b90  mov     [rsp-18h+arg_0], rbx
0x180002b95  mov     [rsp-18h+arg_8], rsi
0x180002b9a  push    rbp
0x180002b9b  push    rdi
0x180002b9c  push    r14
0x180002b9e  mov     rbp, rsp
0x180002ba1  sub     rsp, 50h
0x180002ba5  mov     rsi, rdx
0x180002ba8  mov     [rbp+var_20], 0
0x180002baf  lea     rdx, [rbp+var_20]; unsigned int *
0x180002bb3  mov     [rbp+TokenHandle], 0
0x180002bbb  lea     rcx, [rbp+hLibModule]; this
0x180002bbf  mov     [rbp+phkResult], 0
0x180002bc7  mov     r14d, r8d
0x180002bca  mov     [rbp+arg_18], 0
0x180002bd1  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x180002bd6  mov     ebx, [rbp+var_20]
0x180002bd9  test    ebx, ebx
0x180002bdb  jnz     loc_180002D09
0x180002be1  xor     ecx, ecx; BindingHandle
0x180002be3  call    cs:__imp_RpcImpersonateClient
0x180002be9  mov     ebx, eax
0x180002beb  test    eax, eax
0x180002bed  jnz     loc_180002D09
0x180002bf3  lea     rdx, [rbp+phkResult]; phkResult
0x180002bf7  mov     ecx, 10000000h; samDesired
0x180002bfc  call    cs:__imp_RegOpenCurrentUser
0x180002c02  mov     ebx, eax
0x180002c04  test    eax, eax
0x180002c06  jnz     short loc_180002C3A
0x180002c08  call    cs:__imp_GetCurrentThread
0x180002c0e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180002c12  mov     edx, 2000Eh; DesiredAccess
0x180002c17  mov     rcx, rax; ThreadHandle
0x180002c1a  lea     r8d, [rbx+1]; OpenAsSelf
0x180002c1e  call    cs:__imp_OpenThreadToken
0x180002c24  test    eax, eax
0x180002c26  jnz     short loc_180002C3A
0x180002c28  call    cs:__imp_GetLastError
0x180002c2e  mov     rcx, [rbp+phkResult]; hKey
0x180002c32  mov     ebx, eax
0x180002c34  call    cs:__imp_RegCloseKey
0x180002c3a  mov     edi, ebx
0x180002c3c  call    cs:__imp_RevertToSelf
0x180002c42  test    ebx, ebx
0x180002c44  jnz     loc_180002D09
0x180002c4a  call    ?LogTime@@YAXXZ; LogTime(void)
0x180002c4f  cmp     cs:?gDebugLevel@@3KA, ebx; ulong gDebugLevel
0x180002c55  jz      short loc_180002C67
0x180002c57  mov     r8, rsi
0x180002c5a  lea     ecx, [rbx+4]; unsigned int
0x180002c5d  mov     edx, 0BF3h; unsigned int
0x180002c62  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180002c67  mov     r8, [rbp+phkResult]; HKEY
0x180002c6b  lea     rax, [rbp+arg_18]
0x180002c6f  mov     rdx, [rbp+TokenHandle]; void *
0x180002c73  mov     r9d, r14d; unsigned int
0x180002c76  mov     rcx, rsi; lpString2
0x180002c79  mov     [rsp+50h+var_30], rax; int *
0x180002c7e  call    ?RemoveAppHelper@@YAKPEBGPEAXPEAUHKEY__@@KPEAH@Z; RemoveAppHelper(ushort const *,void *,HKEY__ *,ulong,int *)
0x180002c83  cmp     [rbp+arg_18], 0
0x180002c87  mov     ebx, eax
0x180002c89  jnz     short loc_180002CBB
0x180002c8b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180002c8f  call    ?IsMemberOfAdminGroup@@YAHPEAX@Z; IsMemberOfAdminGroup(void *)
0x180002c94  test    eax, eax
0x180002c96  jz      short loc_180002CBB
0x180002c98  lea     rax, [rbp+arg_18]
0x180002c9c  mov     r9d, r14d; unsigned int
0x180002c9f  xor     edx, edx; void *
0x180002ca1  mov     [rsp+50h+var_30], rax; int *
0x180002ca6  mov     r8, 0FFFFFFFF80000002h; HKEY
0x180002cad  mov     rcx, rsi; lpString2
0x180002cb0  call    ?RemoveAppHelper@@YAKPEBGPEAXPEAUHKEY__@@KPEAH@Z; RemoveAppHelper(ushort const *,void *,HKEY__ *,ulong,int *)
0x180002cb5  mov     ebx, eax
0x180002cb7  mov     edi, eax
0x180002cb9  jmp     short loc_180002CBD
0x180002cbb  mov     edi, ebx
0x180002cbd  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180002cc4  jz      short loc_180002CD8
0x180002cc6  mov     r8d, ebx
0x180002cc9  mov     edx, 0BF4h; unsigned int
0x180002cce  mov     ecx, 4; unsigned int
0x180002cd3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180002cd8  mov     rcx, [rbp+TokenHandle]; hObject
0x180002cdc  test    rcx, rcx
0x180002cdf  jz      short loc_180002CE7
0x180002ce1  call    cs:__imp_CloseHandle
0x180002ce7  mov     rcx, [rbp+phkResult]; hKey
0x180002ceb  test    rcx, rcx
0x180002cee  jz      short loc_180002CF6
0x180002cf0  call    cs:__imp_RegCloseKey
0x180002cf6  mov     rcx, [rbp+hLibModule]; hLibModule
0x180002cfa  test    rcx, rcx
0x180002cfd  jz      short loc_180002D05
0x180002cff  call    cs:__imp_FreeLibrary
0x180002d05  mov     eax, edi
0x180002d07  jmp     short loc_180002D1A
0x180002d09  mov     rcx, [rbp+hLibModule]; hLibModule
0x180002d0d  test    rcx, rcx
0x180002d10  jz      short loc_180002D18
0x180002d12  call    cs:__imp_FreeLibrary
0x180002d18  mov     eax, ebx
0x180002d1a  mov     rbx, [rsp+50h+arg_0]
0x180002d1f  mov     rsi, [rsp+50h+arg_8]
0x180002d24  add     rsp, 50h
0x180002d28  pop     r14
0x180002d2a  pop     rdi
0x180002d2b  pop     rbp
0x180002d2c  retn
```
