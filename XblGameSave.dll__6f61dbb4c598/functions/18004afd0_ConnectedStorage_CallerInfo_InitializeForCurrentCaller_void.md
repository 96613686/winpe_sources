# ConnectedStorage::CallerInfo::InitializeForCurrentCaller(void)

- ea: `0x18004afd0`
- end: `0x18004b1dd`
- name: `?InitializeForCurrentCaller@CallerInfo@ConnectedStorage@@AEAAXXZ`
- size: `525`
- prototype: `void __fastcall(HSTRING *newString)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ae14`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x180011c0c`
- `0x18001265c`
- `0x180012ed8`
- `0x18004afd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b090`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b09a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004b00b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004b00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b18b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b18b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18004b0c5`
- `RPCRT4!RpcRevertToSelfEx` at `0x18004b0c5`
- `RPCRT4!RpcImpersonateClient` at `0x18004b036`
- `RPCRT4!RpcImpersonateClient` at `0x18004b036`
- `ntdll!NtQueryInformationToken` at `0x18004b05e`
- `ntdll!NtQueryInformationToken` at `0x18004b05e`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004b145`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004b145`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18004b0e1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18004b0e1`

## string_xrefs

- `0x18004b015`: `CoCreateGuid(&_instanceGuid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
void __fastcall ConnectedStorage::CallerInfo::InitializeForCurrentCaller(HSTRING *newString)
{
  HRESULT Guid; // eax
  const unsigned __int16 *v3; // r8
  RPC_STATUS v4; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const unsigned __int16 *v7; // r8
  bool v8; // sf
  int ApplicationUserModelIdFromToken; // eax
  const unsigned __int16 *v10; // r8
  int v11; // eax
  const unsigned __int16 *v12; // r8
  bool v13; // sf
  int TokenInformation; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+44h] [rbp-BCh] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+4Ch] [rbp-B4h] BYREF
  HSTRING string[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+200h] [rbp+100h] BYREF

  TokenHandle = (void *)-1LL;
  Guid = CoCreateGuid((GUID *)(newString + 5));
  if ( Guid < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)Guid,
      (int)L"CoCreateGuid(&_instanceGuid)",
      v3);
  TokenInformation = 0;
  ReturnLength = 0;
  v4 = RpcImpersonateClient(0);
  if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) >= 0 )
    *((_DWORD *)newString + 6) = TokenInformation;
  ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError < 0;
    }
    if ( v8 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)LastError,
        (int)L"HRESULT_FROM_WIN32(GetLastError())",
        v7);
  }
  if ( !v4 )
    RpcRevertToSelfEx(0);
  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      TokenHandle,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
  {
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)ApplicationUserModelIdFromToken,
      (int)L"GetApplicationUserModelId",
      v10);
  }
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, applicationUserModelId);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString + 1);
  WindowsDeleteString(string[0]);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 66;
  v11 = ParseApplicationUserModelId(
          applicationUserModelId,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          packageRelativeApplicationId);
  v13 = v11 < 0;
  if ( v11 > 0 )
  {
    v11 = (unsigned __int16)v11 | 0x80070000;
    v13 = v11 < 0;
  }
  if ( v13 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v11,
      (int)L"ParseApplicationUserModelId",
      v12);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, packageFamilyName);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString);
  WindowsDeleteString(string[0]);
  ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
}

```

## disassembly

```asm
0x18004afd0  mov     [rsp-8+arg_8], rbx
0x18004afd5  mov     [rsp-8+arg_10], rdi
0x18004afda  push    rbp
0x18004afdb  lea     rbp, [rsp-1A0h]
0x18004afe3  sub     rsp, 2A0h
0x18004afea  mov     rax, cs:__security_cookie
0x18004aff1  xor     rax, rsp
0x18004aff4  mov     [rbp+1A0h+var_10], rax
0x18004affb  mov     rbx, rcx
0x18004affe  mov     [rsp+2A0h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004b007  add     rcx, 28h ; '('; pguid
0x18004b00b  call    cs:__imp_CoCreateGuid
0x18004b011  test    eax, eax
0x18004b013  jns     short loc_18004B024
0x18004b015  lea     rdx, aCocreateguidIn; "CoCreateGuid(&_instanceGuid)"
0x18004b01c  mov     ecx, eax; this
0x18004b01e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004b024  mov     [rsp+2A0h+TokenInformation], 0
0x18004b02c  mov     [rsp+2A0h+var_260], 0
0x18004b034  xor     ecx, ecx; BindingHandle
0x18004b036  call    cs:__imp_RpcImpersonateClient
0x18004b03c  mov     edi, eax
0x18004b03e  lea     rax, [rsp+2A0h+var_260]
0x18004b043  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18004b048  mov     r9d, 4; TokenInformationLength
0x18004b04e  lea     r8, [rsp+2A0h+TokenInformation]; TokenInformation
0x18004b053  lea     edx, [r9+8]; TokenInformationClass
0x18004b057  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18004b05e  call    cs:__imp_NtQueryInformationToken
0x18004b064  test    eax, eax
0x18004b066  js      short loc_18004B06F
0x18004b068  mov     ecx, [rsp+2A0h+TokenInformation]
0x18004b06c  mov     [rbx+18h], ecx
0x18004b06f  lea     rcx, [rsp+2A0h+TokenHandle]; this
0x18004b074  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x18004b079  call    cs:__imp_GetCurrentThread
0x18004b07f  lea     r9, [rsp+2A0h+TokenHandle]; TokenHandle
0x18004b084  mov     edx, 8; DesiredAccess
0x18004b089  lea     r8d, [rdx-7]; OpenAsSelf
0x18004b08d  mov     rcx, rax; ThreadHandle
0x18004b090  call    cs:__imp_OpenThreadToken
0x18004b096  test    eax, eax
0x18004b098  jnz     short loc_18004B0BF
0x18004b09a  call    cs:__imp_GetLastError
0x18004b0a0  test    eax, eax
0x18004b0a2  jle     short loc_18004B0AE
0x18004b0a4  movzx   eax, ax
0x18004b0a7  or      eax, 80070000h
0x18004b0ac  test    eax, eax
0x18004b0ae  jns     short loc_18004B0BF
0x18004b0b0  lea     rdx, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x18004b0b7  mov     ecx, eax; this
0x18004b0b9  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004b0bf  test    edi, edi
0x18004b0c1  jnz     short loc_18004B0CB
0x18004b0c3  xor     ecx, ecx; BindingHandle
0x18004b0c5  call    cs:__imp_RpcRevertToSelfEx
0x18004b0cb  mov     [rsp+2A0h+applicationUserModelIdLength], 82h
0x18004b0d3  lea     r8, [rbp+1A0h+applicationUserModelId]; applicationUserModelId
0x18004b0d7  lea     rdx, [rsp+2A0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18004b0dc  mov     rcx, [rsp+2A0h+TokenHandle]; token
0x18004b0e1  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18004b0e7  test    eax, eax
0x18004b0e9  jnz     loc_18004B1C0
0x18004b0ef  lea     rdx, [rbp+1A0h+applicationUserModelId]; sourceString
0x18004b0f3  lea     rcx, [rsp+2A0h+string]; string
0x18004b0f8  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18004b0fd  nop
0x18004b0fe  lea     rcx, [rbx+8]; newString
0x18004b102  mov     rdx, rax
0x18004b105  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18004b10a  nop
0x18004b10b  mov     rcx, [rsp+2A0h+string]; string
0x18004b110  call    cs:__imp_WindowsDeleteString
0x18004b116  mov     [rsp+2A0h+packageFamilyNameLength], 41h ; 'A'
0x18004b11e  mov     [rsp+2A0h+packageRelativeApplicationIdLength], 42h ; 'B'
0x18004b126  lea     rax, [rbp+1A0h+packageRelativeApplicationId]
0x18004b12d  mov     [rsp+2A0h+ReturnLength], rax; packageRelativeApplicationId
0x18004b132  lea     r9, [rsp+2A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004b137  lea     r8, [rsp+2A0h+packageFamilyName]; packageFamilyName
0x18004b13c  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18004b141  lea     rcx, [rbp+1A0h+applicationUserModelId]; applicationUserModelId
0x18004b145  call    cs:__imp_ParseApplicationUserModelId
0x18004b14b  test    eax, eax
0x18004b14d  jle     short loc_18004B159
0x18004b14f  movzx   eax, ax
0x18004b152  or      eax, 80070000h
0x18004b157  test    eax, eax
0x18004b159  jns     short loc_18004B16A
0x18004b15b  lea     rdx, aParseapplicati_0; "ParseApplicationUserModelId"
0x18004b162  mov     ecx, eax; this
0x18004b164  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004b16a  lea     rdx, [rsp+2A0h+packageFamilyName]; sourceString
0x18004b16f  lea     rcx, [rsp+2A0h+string]; string
0x18004b174  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18004b179  nop
0x18004b17a  mov     rdx, rax
0x18004b17d  mov     rcx, rbx; newString
0x18004b180  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18004b185  nop
0x18004b186  mov     rcx, [rsp+2A0h+string]; string
0x18004b18b  call    cs:__imp_WindowsDeleteString
0x18004b191  nop
0x18004b192  lea     rcx, [rsp+2A0h+TokenHandle]; this
0x18004b197  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x18004b19c  mov     rcx, [rbp+1A0h+var_10]
0x18004b1a3  xor     rcx, rsp; StackCookie
0x18004b1a6  call    __security_check_cookie
0x18004b1ab  lea     r11, [rsp+2A0h+var_s0]
0x18004b1b3  mov     rbx, [r11+18h]
0x18004b1b7  mov     rdi, [r11+20h]
0x18004b1bb  mov     rsp, r11
0x18004b1be  pop     rbp
0x18004b1bf  retn
0x18004b1c0  jle     short loc_18004B1CA
0x18004b1c2  movzx   eax, ax
0x18004b1c5  or      eax, 80070000h
0x18004b1ca  test    eax, eax
0x18004b1cc  jns     short loc_18004B192
0x18004b1ce  lea     rdx, aGetapplication_0; "GetApplicationUserModelId"
0x18004b1d5  mov     ecx, eax; this
0x18004b1d7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
