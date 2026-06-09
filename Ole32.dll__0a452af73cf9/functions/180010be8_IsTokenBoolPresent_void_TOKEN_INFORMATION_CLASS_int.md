# IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)

- ea: `0x180010be8`
- end: `0x180010d6b`
- name: `?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z`
- size: `387`
- prototype: `HRESULT __fastcall(void *hToken, _TOKEN_INFORMATION_CLASS isPresent, int *hToken)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010afc`
- `0x180010bc0`
- `0x18003ca70`

## callees

- `0x180010be8`
- `0x180036864`
- `0x1800475b0`
- `0x180059088`
- `0x18008be08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c38`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010c4a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010c4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010cd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010cd3`

## string_xrefs

- `0x180010ca3`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x180010d2c`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x180010c9c`: `IsTokenBoolPresent`
- `0x180010d25`: `IsTokenBoolPresent`

## pseudocode

```c
HRESULT __fastcall IsTokenBoolPresent(void *hToken, _TOKEN_INFORMATION_CLASS isPresent, int *a3)
{
  HRESULT file; // ebx
  HRESULT result; // eax
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  TraceLevel v8; // r9d
  void *v9; // rcx
  signed int LastError; // eax
  TraceLevel v11; // r9d
  unsigned int size; // [rsp+50h] [rbp+20h] BYREF
  unsigned int tokenBoolValue; // [rsp+58h] [rbp+28h] BYREF
  void *hLocalProcessToken; // [rsp+60h] [rbp+30h] BYREF
  void *hImpersonationToken; // [rsp+68h] [rbp+38h] BYREF

  file = 0;
  hImpersonationToken = 0;
  hLocalProcessToken = 0;
  tokenBoolValue = 0;
  size = 0;
  *a3 = 0;
  if ( hToken )
  {
LABEL_12:
    if ( GetTokenInformation(hToken, TokenIsAppContainer, &tokenBoolValue, 4u, &size) )
    {
      *a3 = tokenBoolValue != 0;
    }
    else
    {
      LastError = GetLastError();
      file = LastError;
      if ( LastError > 0 )
        file = (unsigned __int16)LastError | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
          "IsTokenBoolPresent",
          58,
          v11,
          L"hr:%!HRESULT!",
          file);
    }
    if ( hLocalProcessToken )
      CloseHandle(hLocalProcessToken);
    v9 = hImpersonationToken;
    if ( !hImpersonationToken )
      return file;
    goto LABEL_23;
  }
  result = SuspendImpersonate(&hImpersonationToken);
  file = result;
  if ( result < 0 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hLocalProcessToken) )
  {
    hToken = hLocalProcessToken;
    goto LABEL_12;
  }
  v7 = GetLastError();
  file = v7;
  if ( v7 > 0 )
    file = (unsigned __int16)v7 | 0x80070000;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
      "IsTokenBoolPresent",
      42,
      v8,
      L"hr:%!HRESULT!",
      file);
  v9 = hImpersonationToken;
LABEL_23:
  ResumeImpersonate(v9);
  return file;
}

```

## disassembly

```asm
0x180010be8  mov     [rsp-18h+tokenBoolValue], edx
0x180010bec  push    rbp
0x180010bed  push    rbx
0x180010bee  push    rdi
0x180010bef  mov     rbp, rsp
0x180010bf2  sub     rsp, 30h
0x180010bf6  xor     ebx, ebx
0x180010bf8  mov     [rbp+hImpersonationToken], 0
0x180010c00  mov     [rbp+hLocalProcessToken], 0
0x180010c08  mov     rdi, isPresent
0x180010c0b  mov     [rbp+tokenBoolValue], 0
0x180010c12  mov     [rbp+size], 0
0x180010c19  mov     [isPresent], ebx
0x180010c1c  test    hToken, hToken
0x180010c1f  jnz     loc_180010CBC
0x180010c25  lea     hToken, [rbp+hImpersonationToken]; pHandle
0x180010c29  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180010c2e  mov     ebx, eax
0x180010c30  test    eax, eax
0x180010c32  js      loc_180010D63
0x180010c38  call    cs:__imp_GetCurrentProcess
0x180010c3e  lea     isPresent, [rbp+hLocalProcessToken]; TokenHandle
0x180010c42  mov     edx, 8; DesiredAccess
0x180010c47  mov     hToken, rax; ProcessHandle
0x180010c4a  call    cs:__imp_OpenProcessToken
0x180010c50  test    eax, eax
0x180010c52  jnz     short loc_180010CB8
0x180010c54  call    cs:__imp_GetLastError
0x180010c5a  mov     ebx, eax
0x180010c5c  test    eax, eax
0x180010c5e  jle     short loc_180010C69
0x180010c60  movzx   ebx, ax
0x180010c63  or      ebx, 80070000h
0x180010c69  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180010c6f  test    eax, eax
0x180010c71  jnz     short loc_180010C86
0x180010c73  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180010c79  jz      short loc_180010CAF
0x180010c7b  xor     ecx, ecx; level
0x180010c7d  call    IsWppLevelEnabled
0x180010c82  test    al, al
0x180010c84  jz      short loc_180010CAF
0x180010c86  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x180010c8d  mov     [rsp+30h+file], ebx; file
0x180010c91  mov     r8d, 2Ah ; '*'; line
0x180010c97  mov     [rsp+30h+ReturnLength], rax; <args_0>
0x180010c9c  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x180010ca3  lea     hToken, aOnecoreComComb; "onecore\\com\\combase\\common\\internal"...
0x180010caa  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180010caf  mov     hToken, [rbp+hImpersonationToken]
0x180010cb3  jmp     loc_180010D5C
0x180010cb8  mov     hToken, [rbp+hLocalProcessToken]; TokenHandle
0x180010cbc  mov     r9d, 4; TokenInformationLength
0x180010cc2  lea     rax, [rbp+size]
0x180010cc6  lea     isPresent, [rbp+tokenBoolValue]; TokenInformation
0x180010cca  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180010ccf  lea     edx, [r9+19h]; TokenInformationClass
0x180010cd3  call    cs:__imp_GetTokenInformation
0x180010cd9  test    eax, eax
0x180010cdb  jnz     short loc_180010D3A
0x180010cdd  call    cs:__imp_GetLastError
0x180010ce3  mov     ebx, eax
0x180010ce5  test    eax, eax
0x180010ce7  jle     short loc_180010CF2
0x180010ce9  movzx   ebx, ax
0x180010cec  or      ebx, 80070000h
0x180010cf2  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180010cf8  test    eax, eax
0x180010cfa  jnz     short loc_180010D0F
0x180010cfc  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180010d02  jz      short loc_180010D44
0x180010d04  xor     ecx, ecx; level
0x180010d06  call    IsWppLevelEnabled
0x180010d0b  test    al, al
0x180010d0d  jz      short loc_180010D44
0x180010d0f  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x180010d16  mov     [rsp+30h+file], ebx; file
0x180010d1a  mov     r8d, 3Ah ; ':'; line
0x180010d20  mov     [rsp+30h+ReturnLength], rax; <args_0>
0x180010d25  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x180010d2c  lea     hToken, aOnecoreComComb; "onecore\\com\\combase\\common\\internal"...
0x180010d33  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180010d38  jmp     short loc_180010D44
0x180010d3a  xor     eax, eax
0x180010d3c  cmp     [rbp+tokenBoolValue], eax
0x180010d3f  setnz   al
0x180010d42  mov     [rdi], eax
0x180010d44  mov     hToken, [rbp+hLocalProcessToken]; hObject
0x180010d48  test    hToken, hToken
0x180010d4b  jz      short loc_180010D53
0x180010d4d  call    cs:__imp_CloseHandle
0x180010d53  mov     hToken, [rbp+hImpersonationToken]; hToken
0x180010d57  test    hToken, hToken
0x180010d5a  jz      short loc_180010D61
0x180010d5c  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180010d61  mov     eax, ebx
0x180010d63  add     rsp, 30h
0x180010d67  pop     rdi
0x180010d68  pop     rbx
0x180010d69  pop     rbp
0x180010d6a  retn
```
