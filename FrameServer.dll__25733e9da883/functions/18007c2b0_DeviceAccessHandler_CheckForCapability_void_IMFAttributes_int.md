# DeviceAccessHandler::CheckForCapability(void *,IMFAttributes *,int *)

- ea: `0x18007c2b0`
- end: `0x18007c6eb`
- name: `?CheckForCapability@DeviceAccessHandler@@UEAAJPEAXPEAUIMFAttributes@@PEAH@Z`
- size: `1083`
- prototype: `int(DeviceAccessHandler *__hidden this, void *, struct IMFAttributes *, int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009608`
- `0x180009f50`
- `0x18000a600`
- `0x18000a648`
- `0x18000a91c`
- `0x180017a3c`
- `0x180017a64`
- `0x180017ab8`
- `0x18007c074`
- `0x18007c2b0`
- `0x18008009c`
- `0x180080290`
- `0x18008075c`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCheckProcessCapabilities` at `0x18007c54d`
- `MFSENSORGROUP!MFCheckProcessCapabilities` at `0x18007c54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c575`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007c3ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007c3ff`
- `RPCRT4!RpcImpersonateClient` at `0x18007c3aa`
- `RPCRT4!RpcImpersonateClient` at `0x18007c5c6`
- `RPCRT4!RpcImpersonateClient` at `0x18007c3aa`
- `RPCRT4!RpcImpersonateClient` at `0x18007c5c6`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007c6ae`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007c6ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c4e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c4e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c466`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c4ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c466`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c4ba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007c3c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007c3c6`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::CheckForCapability(DWORD *this, void *a2, struct IMFAttributes *a3, int *a4)
{
  char v4; // r12
  signed int v9; // ebx
  __int64 v10; // rdx
  const wchar_t *v11; // rsi
  HRESULT (__stdcall *GetAllocatedString)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rbx
  HANDLE v13; // rax
  HANDLE v14; // rbx
  signed int LastError; // eax
  __int64 v16; // rdx
  const struct std::nothrow_t *unique; // rax
  PSID *v18; // r14
  unsigned int i; // ebx
  int v20; // r8d
  int v21; // eax
  signed int v22; // eax
  int v23; // edx
  const wchar_t *v24; // rcx
  int v26; // [rsp+40h] [rbp-38h] BYREF
  const wchar_t *v27; // [rsp+48h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-28h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-20h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp-18h] BYREF
  HANDLE ProcessHandle[2]; // [rsp+68h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+D0h] [rbp+58h] BYREF

  v4 = 0;
  v27 = 0;
  v26 = 0;
  ProcessHandle[0] = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( !a3 )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_5:
      v11 = L"null";
      goto LABEL_40;
    }
    v10 = 61;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v9);
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_5;
    v10 = 62;
    goto LABEL_4;
  }
  v11 = L"null";
  if ( this[14]
    && (GetAllocatedString = a3->lpVtbl->GetAllocatedString,
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &v27,
          0),
        ((int (__fastcall *)(struct IMFAttributes *, __int64 *, const wchar_t **, int *))GetAllocatedString)(
          a3,
          MF_DEVICESTREAM_REQUIRED_CAPABILITIES,
          &v27,
          &v26) >= 0) )
  {
    *a4 = 0;
    if ( RpcImpersonateClient(a2) )
    {
      v9 = RpcImpersonateClient(a2) | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_40;
      v16 = 64;
      goto LABEL_39;
    }
    v13 = OpenProcess(0x400u, 0, this[58]);
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      ProcessHandle,
      v13);
    v14 = ProcessHandle[0];
    if ( ProcessHandle[0] )
    {
      v4 = 1;
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      if ( !OpenProcessToken(v14, 8u, &TokenHandle) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_40;
          v16 = 66;
LABEL_39:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v16,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v9);
          goto LABEL_40;
        }
      }
      if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
      {
        TokenInformationLength = 0;
        GetTokenInformation(TokenHandle, TokenCapabilities, 0, 0, &TokenInformationLength);
        if ( TokenInformationLength )
        {
          unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(
                                                    &StringSid,
                                                    TokenInformationLength);
          wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(
            &TokenInformation,
            unique);
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&StringSid);
          v18 = (PSID *)TokenInformation;
          if ( TokenInformation )
          {
            if ( GetTokenInformation(
                   TokenHandle,
                   TokenCapabilities,
                   TokenInformation,
                   TokenInformationLength,
                   &TokenInformationLength) )
            {
              for ( i = 0; i < *(_DWORD *)v18; ++i )
              {
                StringSid = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &StringSid,
                  0);
                if ( ConvertSidToStringSidW(v18[1], &StringSid) && (unsigned __int8)byte_18010EC4D >= 8u )
                  WPP_SF_qDDS(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    67,
                    v20,
                    (_DWORD)this,
                    this[58],
                    i,
                    (__int64)StringSid);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
              }
            }
          }
        }
      }
      v21 = MFCheckProcessCapabilities(TokenHandle, v27, (unsigned int)(v26 + 1), a4);
      v9 = v21;
      if ( v21 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v21);
        goto LABEL_40;
      }
    }
    else
    {
      v22 = GetLastError();
      v9 = v22;
      if ( v22 > 0 )
        v9 = (unsigned __int16)v22 | 0x80070000;
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v9);
      v4 = 1;
      if ( v9 < 0 )
      {
LABEL_40:
        if ( byte_18010EC4D )
        {
          v23 = 69;
LABEL_48:
          if ( v27 )
            v11 = v27;
          WPP_SF_qDDS(*((_QWORD *)WPP_GLOBAL_Control + 27), v23, (_DWORD)a3, (_DWORD)this, v9, this[58], (__int64)v11);
          goto LABEL_51;
        }
        goto LABEL_51;
      }
    }
  }
  else
  {
    v9 = 0;
    *a4 = 1;
    if ( (unsigned __int8)byte_18010EC4D < 8u )
      goto LABEL_53;
    v24 = L"null";
    if ( v27 )
      v24 = v27;
    WPP_SF_qDdS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)this,
      this[58],
      this[14],
      (__int64)v24);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v23 = 70;
    goto LABEL_48;
  }
LABEL_51:
  if ( v4 )
    RpcRevertToSelfEx(a2);
LABEL_53:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(ProcessHandle);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007c2b0  push    rbp
0x18007c2b2  push    rbx
0x18007c2b3  push    rsi
0x18007c2b4  push    rdi
0x18007c2b5  push    r12
0x18007c2b7  push    r13
0x18007c2b9  push    r14
0x18007c2bb  push    r15
0x18007c2bd  mov     rbp, rsp
0x18007c2c0  sub     rsp, 78h
0x18007c2c4  xor     r12b, r12b
0x18007c2c7  mov     [rbp+var_30], 0
0x18007c2cf  mov     [rbp+var_38], 0
0x18007c2d6  mov     r15, r9
0x18007c2d9  mov     [rbp+ProcessHandle], 0
0x18007c2e1  mov     r14, r8
0x18007c2e4  mov     [rbp+TokenHandle], 0
0x18007c2ec  mov     r13, rdx
0x18007c2ef  mov     [rbp+TokenInformation], 0
0x18007c2f7  mov     rdi, rcx
0x18007c2fa  mov     [rbp+TokenInformationLength], 0
0x18007c301  test    r8, r8
0x18007c304  jnz     short loc_18007C342
0x18007c306  mov     ebx, 80070057h
0x18007c30b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c312  jb      short loc_18007C336
0x18007c314  lea     edx, [r8+3Dh]
0x18007c318  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c31f  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007c326  mov     r9, rdi
0x18007c329  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x18007c32d  mov     rcx, [rcx+10h]
0x18007c331  call    WPP_SF_qD
0x18007c336  lea     rsi, aNull; "null"
0x18007c33d  jmp     loc_18007C600
0x18007c342  test    r15, r15
0x18007c345  jnz     short loc_18007C35B
0x18007c347  mov     ebx, 80004003h
0x18007c34c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c353  jb      short loc_18007C336
0x18007c355  lea     edx, [r15+3Eh]
0x18007c359  jmp     short loc_18007C318
0x18007c35b  cmp     dword ptr [rcx+38h], 0
0x18007c35f  lea     rsi, aNull; "null"
0x18007c366  jz      loc_18007C614
0x18007c36c  mov     rax, [r8]
0x18007c36f  lea     rcx, [rbp+var_30]
0x18007c373  xor     edx, edx
0x18007c375  mov     rbx, [rax+68h]
0x18007c379  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18007c37e  lea     r9, [rbp+var_38]
0x18007c382  mov     rcx, r14
0x18007c385  lea     r8, [rbp+var_30]
0x18007c389  mov     rax, rbx
0x18007c38c  lea     rdx, MF_DEVICESTREAM_REQUIRED_CAPABILITIES
0x18007c393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c398  test    eax, eax
0x18007c39a  js      loc_18007C614
0x18007c3a0  mov     rcx, r13; BindingHandle
0x18007c3a3  mov     dword ptr [r15], 0
0x18007c3aa  call    cs:__imp_RpcImpersonateClient
0x18007c3b0  test    eax, eax
0x18007c3b2  jnz     loc_18007C5C3
0x18007c3b8  mov     r8d, [rdi+0E8h]; dwProcessId
0x18007c3bf  xor     edx, edx; bInheritHandle
0x18007c3c1  mov     ecx, 400h; dwDesiredAccess
0x18007c3c6  call    cs:__imp_OpenProcess
0x18007c3cc  mov     rdx, rax
0x18007c3cf  lea     rcx, [rbp+ProcessHandle]
0x18007c3d3  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007c3d8  mov     rbx, [rbp+ProcessHandle]
0x18007c3dc  test    rbx, rbx
0x18007c3df  jz      loc_18007C575
0x18007c3e5  xor     edx, edx
0x18007c3e7  lea     rcx, [rbp+TokenHandle]
0x18007c3eb  mov     r12b, 1
0x18007c3ee  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007c3f3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007c3f7  mov     edx, 8; DesiredAccess
0x18007c3fc  mov     rcx, rbx; ProcessHandle
0x18007c3ff  call    cs:__imp_OpenProcessToken
0x18007c405  test    eax, eax
0x18007c407  jnz     short loc_18007C439
0x18007c409  call    cs:__imp_GetLastError
0x18007c40f  mov     ebx, eax
0x18007c411  test    eax, eax
0x18007c413  jle     short loc_18007C41E
0x18007c415  movzx   ebx, ax
0x18007c418  or      ebx, 80070000h
0x18007c41e  test    ebx, ebx
0x18007c420  jns     short loc_18007C439
0x18007c422  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18007c429  jb      loc_18007C600
0x18007c42f  mov     edx, 42h ; 'B'
0x18007c434  jmp     loc_18007C5E2
0x18007c439  cmp     cs:byte_18010EC4D, 10h
0x18007c440  jb      loc_18007C53B
0x18007c446  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007c44a  lea     rax, [rbp+TokenInformationLength]
0x18007c44e  xor     r9d, r9d; TokenInformationLength
0x18007c451  mov     [rbp+TokenInformationLength], 0
0x18007c458  xor     r8d, r8d; TokenInformation
0x18007c45b  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18007c460  lea     ebx, [r9+1Eh]
0x18007c464  mov     edx, ebx; TokenInformationClass
0x18007c466  call    cs:__imp_GetTokenInformation
0x18007c46c  mov     eax, [rbp+TokenInformationLength]
0x18007c46f  test    eax, eax
0x18007c471  jz      loc_18007C53B
0x18007c477  mov     edx, eax
0x18007c479  lea     rcx, [rbp+StringSid]
0x18007c47d  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18007c482  mov     rdx, rax
0x18007c485  lea     rcx, [rbp+TokenInformation]
0x18007c489  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18007c48e  lea     rcx, [rbp+StringSid]
0x18007c492  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007c497  mov     r14, [rbp+TokenInformation]
0x18007c49b  test    r14, r14
0x18007c49e  jz      loc_18007C53B
0x18007c4a4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18007c4a8  lea     rax, [rbp+TokenInformationLength]
0x18007c4ac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007c4b0  mov     r8, r14; TokenInformation
0x18007c4b3  mov     edx, ebx; TokenInformationClass
0x18007c4b5  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18007c4ba  call    cs:__imp_GetTokenInformation
0x18007c4c0  test    eax, eax
0x18007c4c2  jz      short loc_18007C53B
0x18007c4c4  xor     ebx, ebx
0x18007c4c6  cmp     [r14], ebx
0x18007c4c9  jbe     short loc_18007C53B
0x18007c4cb  xor     edx, edx
0x18007c4cd  mov     [rbp+StringSid], 0
0x18007c4d5  lea     rcx, [rbp+StringSid]
0x18007c4d9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007c4de  mov     rcx, [r14+8]; Sid
0x18007c4e2  lea     rdx, [rbp+StringSid]; StringSid
0x18007c4e6  call    cs:__imp_ConvertSidToStringSidW
0x18007c4ec  test    eax, eax
0x18007c4ee  jz      short loc_18007C52B
0x18007c4f0  cmp     cs:byte_18010EC4D, 8
0x18007c4f7  jb      short loc_18007C52B
0x18007c4f9  mov     rax, [rbp+StringSid]
0x18007c4fd  mov     edx, 43h ; 'C'
0x18007c502  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c509  mov     r9, rdi
0x18007c50c  mov     [rsp+78h+var_48], rax
0x18007c511  mov     eax, [rdi+0E8h]
0x18007c517  mov     [rsp+78h+var_50], ebx
0x18007c51b  mov     rcx, [rcx+0D8h]
0x18007c522  mov     dword ptr [rsp+78h+ReturnLength], eax
0x18007c526  call    WPP_SF_qDDS
0x18007c52b  lea     rcx, [rbp+StringSid]
0x18007c52f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007c534  inc     ebx
0x18007c536  cmp     ebx, [r14]
0x18007c539  jb      short loc_18007C4CB
0x18007c53b  mov     r8d, [rbp+var_38]
0x18007c53f  mov     r9, r15
0x18007c542  mov     rdx, [rbp+var_30]
0x18007c546  inc     r8d
0x18007c549  mov     rcx, [rbp+TokenHandle]
0x18007c54d  call    cs:__imp_MFCheckProcessCapabilities
0x18007c553  mov     ebx, eax
0x18007c555  test    eax, eax
0x18007c557  jns     loc_18007C664
0x18007c55d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18007c564  jb      loc_18007C600
0x18007c56a  mov     edx, 44h ; 'D'
0x18007c56f  mov     dword ptr [rsp+78h+ReturnLength], eax
0x18007c573  jmp     short loc_18007C5E6
0x18007c575  call    cs:__imp_GetLastError
0x18007c57b  mov     ebx, eax
0x18007c57d  test    eax, eax
0x18007c57f  jle     short loc_18007C58A
0x18007c581  movzx   ebx, ax
0x18007c584  or      ebx, 80070000h
0x18007c58a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c591  jb      short loc_18007C5B6
0x18007c593  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c59a  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007c5a1  mov     edx, 41h ; 'A'
0x18007c5a6  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x18007c5aa  mov     r9, rdi
0x18007c5ad  mov     rcx, [rcx+10h]
0x18007c5b1  call    WPP_SF_qD
0x18007c5b6  mov     r12b, 1
0x18007c5b9  test    ebx, ebx
0x18007c5bb  jns     loc_18007C664
0x18007c5c1  jmp     short loc_18007C600
0x18007c5c3  mov     rcx, r13; BindingHandle
0x18007c5c6  call    cs:__imp_RpcImpersonateClient
0x18007c5cc  mov     ebx, eax
0x18007c5ce  or      ebx, 80010000h
0x18007c5d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c5db  jb      short loc_18007C600
0x18007c5dd  mov     edx, 40h ; '@'
0x18007c5e2  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x18007c5e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c5ed  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007c5f4  mov     r9, rdi
0x18007c5f7  mov     rcx, [rcx+10h]
0x18007c5fb  call    WPP_SF_qD
0x18007c600  cmp     cs:byte_18010EC4D, 1
0x18007c607  jb      loc_18007C6A6
0x18007c60d  mov     edx, 45h ; 'E'
0x18007c612  jmp     short loc_18007C672
0x18007c614  xor     ebx, ebx
0x18007c616  mov     dword ptr [r15], 1
0x18007c61d  cmp     cs:byte_18010EC4D, 8
0x18007c624  jb      loc_18007C6B4
0x18007c62a  mov     rax, [rbp+var_30]
0x18007c62e  mov     rcx, rsi
0x18007c631  test    rax, rax
0x18007c634  mov     r9, rdi
0x18007c637  cmovnz  rcx, rax
0x18007c63b  mov     eax, [rdi+38h]
0x18007c63e  mov     [rsp+78h+var_48], rcx
0x18007c643  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c64a  mov     [rsp+78h+var_50], eax
0x18007c64e  mov     eax, [rdi+0E8h]
0x18007c654  mov     dword ptr [rsp+78h+ReturnLength], eax
0x18007c658  mov     rcx, [rcx+0D8h]
0x18007c65f  call    WPP_SF_qDdS
0x18007c664  cmp     cs:byte_18010EC4D, 8
0x18007c66b  jb      short loc_18007C6A6
0x18007c66d  mov     edx, 46h ; 'F'
0x18007c672  mov     rax, [rbp+var_30]
0x18007c676  mov     r9, rdi
0x18007c679  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c680  test    rax, rax
0x18007c683  cmovnz  rsi, rax
0x18007c687  mov     eax, [rdi+0E8h]
0x18007c68d  mov     [rsp+78h+var_48], rsi
0x18007c692  mov     rcx, [rcx+0D8h]
0x18007c699  mov     [rsp+78h+var_50], eax
0x18007c69d  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x18007c6a1  call    WPP_SF_qDDS
0x18007c6a6  test    r12b, r12b
0x18007c6a9  jz      short loc_18007C6B4
0x18007c6ab  mov     rcx, r13; BindingHandle
0x18007c6ae  call    cs:__imp_RpcRevertToSelfEx
0x18007c6b4  lea     rcx, [rbp+TokenInformation]
0x18007c6b8  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007c6bd  lea     rcx, [rbp+TokenHandle]
0x18007c6c1  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007c6c6  lea     rcx, [rbp+ProcessHandle]
0x18007c6ca  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007c6cf  lea     rcx, [rbp+var_30]
0x18007c6d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007c6d8  mov     eax, ebx
0x18007c6da  add     rsp, 78h
0x18007c6de  pop     r15
0x18007c6e0  pop     r14
0x18007c6e2  pop     r13
0x18007c6e4  pop     r12
0x18007c6e6  pop     rdi
0x18007c6e7  pop     rsi
0x18007c6e8  pop     rbx
0x18007c6e9  pop     rbp
0x18007c6ea  retn
```
