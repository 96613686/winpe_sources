# GetCallingAppIdUsingImpersonation

- ea: `0x180051830`
- end: `0x180051957`
- name: `GetCallingAppIdUsingImpersonation`
- size: `295`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051960`

## callees

- `0x180016154`
- `0x180019e9c`
- `0x180020cc4`
- `0x18002ac50`
- `0x1800511a0`
- `0x180051830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518b4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180051840`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180051840`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800518aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800518aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051894`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051894`

## string_xrefs

- `0x18005185d`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x1800518e0`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x18005192a`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCallingAppIdUsingImpersonation(void *a1)
{
  HRESULT v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  signed int v10; // ebx
  unsigned __int16 **v11; // r8
  int ThreadTokenAppId; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  unsigned int *v16; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+18h] BYREF
  int v18; // [rsp+60h] [rbp+20h] BYREF
  int v19; // [rsp+68h] [rbp+28h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 >= 0 )
  {
    TokenHandle = 0;
    LOBYTE(v17) = 0;
    v16 = &v17;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___::_ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___(&v16);
      ThreadTokenAppId = CallerIdentity::GetThreadTokenAppId(TokenHandle, a1, v11);
      if ( ThreadTokenAppId >= 0 )
      {
        v10 = 0;
      }
      else
      {
        v18 = ThreadTokenAppId;
        v19 = 46;
        Log<long &,char const (&)[40],int>(v14, v13, &v18, "..\\cdpcomstrongauthenticationhelper.cpp", &v19);
        v10 = v18;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v18 = v10;
      if ( v10 < 0 )
      {
        v19 = 42;
        Log<long &,char const (&)[40],int>(v9, v8, &v18, "..\\cdpcomstrongauthenticationhelper.cpp", &v19);
        v10 = v18;
      }
      ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___::_ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___(&v16);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(&TokenHandle);
    return (unsigned int)v10;
  }
  else
  {
    v17 = v2;
    v18 = 30;
    Log<long &,char const (&)[40],int>(v4, v3, &v17, "..\\cdpcomstrongauthenticationhelper.cpp", &v18);
    return v17;
  }
}

```

## disassembly

```asm
0x180051830  mov     [rsp-8+arg_0], rbx
0x180051835  push    rbp
0x180051836  mov     rbp, rsp
0x180051839  sub     rsp, 40h
0x18005183d  mov     rbx, rcx
0x180051840  call    cs:__imp_CoImpersonateClient
0x180051846  test    eax, eax
0x180051848  jns     short loc_180051875
0x18005184a  mov     [rbp+arg_8], eax
0x18005184d  mov     [rbp+arg_10], 1Eh
0x180051854  lea     rax, [rbp+arg_10]
0x180051858  mov     [rsp+40h+var_20], rax
0x18005185d  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180051864  lea     r8, [rbp+arg_8]
0x180051868  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18005186d  mov     eax, [rbp+arg_8]
0x180051870  jmp     loc_18005194C
0x180051875  mov     [rbp+TokenHandle], 0
0x18005187d  mov     byte ptr [rbp+arg_8], 0
0x180051881  lea     rax, [rbp+arg_8]
0x180051885  mov     [rbp+var_8], rax
0x180051889  xor     edx, edx
0x18005188b  lea     rcx, [rbp+TokenHandle]
0x18005188f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180051894  call    cs:__imp_GetCurrentThread
0x18005189a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005189e  mov     edx, 0Ch; DesiredAccess
0x1800518a3  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800518a7  mov     rcx, rax; ThreadHandle
0x1800518aa  call    cs:__imp_OpenThreadToken
0x1800518b0  test    eax, eax
0x1800518b2  jnz     short loc_1800518FE
0x1800518b4  call    cs:__imp_GetLastError
0x1800518ba  mov     ebx, eax
0x1800518bc  test    eax, eax
0x1800518be  jle     short loc_1800518C9
0x1800518c0  movzx   ebx, ax
0x1800518c3  or      ebx, 80070000h
0x1800518c9  mov     [rbp+arg_10], ebx
0x1800518cc  test    ebx, ebx
0x1800518ce  jns     short loc_1800518F3
0x1800518d0  mov     [rbp+arg_18], 2Ah ; '*'
0x1800518d7  lea     rax, [rbp+arg_18]
0x1800518db  mov     [rsp+40h+var_20], rax
0x1800518e0  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800518e7  lea     r8, [rbp+arg_10]
0x1800518eb  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800518f0  mov     ebx, [rbp+arg_10]
0x1800518f3  lea     rcx, [rbp+var_8]
0x1800518f7  call    ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700______ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___
0x1800518fc  jmp     short loc_180051941
0x1800518fe  lea     rcx, [rbp+var_8]
0x180051902  call    ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700______ScopeWarden__lambda_2f195021c3e4f06419ba28e66d91f700___
0x180051907  mov     rdx, rbx; void *
0x18005190a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005190e  call    ?GetThreadTokenAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetThreadTokenAppId(void *,ushort * *)
0x180051913  test    eax, eax
0x180051915  jns     short loc_18005193F
0x180051917  mov     [rbp+arg_10], eax
0x18005191a  mov     [rbp+arg_18], 2Eh ; '.'
0x180051921  lea     rax, [rbp+arg_18]
0x180051925  mov     [rsp+40h+var_20], rax
0x18005192a  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180051931  lea     r8, [rbp+arg_10]
0x180051935  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18005193a  mov     ebx, [rbp+arg_10]
0x18005193d  jmp     short loc_180051941
0x18005193f  xor     ebx, ebx
0x180051941  lea     rcx, [rbp+TokenHandle]
0x180051945  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18005194a  mov     eax, ebx
0x18005194c  mov     rbx, [rsp+40h+arg_0]
0x180051951  add     rsp, 40h
0x180051955  pop     rbp
0x180051956  retn
```
