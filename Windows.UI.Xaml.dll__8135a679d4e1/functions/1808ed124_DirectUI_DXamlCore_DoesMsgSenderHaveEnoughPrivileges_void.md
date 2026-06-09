# DirectUI::DXamlCore::DoesMsgSenderHaveEnoughPrivileges(void)

- ea: `0x1808ed124`
- end: `0x1808ed552`
- name: `?DoesMsgSenderHaveEnoughPrivileges@DXamlCore@DirectUI@@AEAAJXZ`
- size: `1070`
- prototype: `HRESULT __fastcall(DirectUI::DXamlCore *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1808ee660`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18001c368`
- `0x180131190`
- `0x1803cf970`
- `0x1803cfa14`
- `0x180511a34`
- `0x180511a98`
- `0x180645094`
- `0x180687a78`
- `0x1806c50ac`
- `0x18076e110`
- `0x1808ed124`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed1e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed1e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1808ed4d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1808ed3c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1808ed3c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1808ed30c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1808ed30c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1808ed24f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1808ed24f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1808ed33e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1808ed33e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1808ed3e4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1808ed3e4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1808ed28a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1808ed28a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1808ed213`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1808ed278`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1808ed213`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1808ed278`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1808ed463`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1808ed4b2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1808ed463`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1808ed4b2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1808ed298`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1808ed298`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1808ed1c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1808ed31c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1808ed1c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1808ed31c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1808ed377`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1808ed377`

## pseudocode

```c
__int64 __fastcall DirectUI::DXamlCore::DoesMsgSenderHaveEnoughPrivileges(DirectUI::DXamlCore *this)
{
  IMessageSession *m_pMessageSession; // rdi
  HRESULT v2; // ebx
  HRESULT (__fastcall *GetMessageInfo)(IMessageSession *, IMessageInfo **); // rbx
  HRESULT v4; // eax
  HANDLE v5; // rdi
  signed int LastError; // esi
  signed int v7; // eax
  PSID *v8; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  HRESULT v10; // ecx
  DWORD CurrentProcessId; // eax
  HANDLE v12; // rax
  void *m_ptr; // rsi
  void *v14; // rbx
  signed int v15; // eax
  signed int v16; // eax
  _PRIVILEGE_SET *FailFast; // rdi
  signed int v18; // eax
  unsigned int dwLength; // [rsp+40h] [rbp-69h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > sd; // [rsp+48h] [rbp-61h] BYREF
  unsigned int PrivilegeSetLength; // [rsp+50h] [rbp-59h] BYREF
  int accessStatus; // [rsp+54h] [rbp-55h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > hSenderProcess; // [rsp+58h] [rbp-51h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > tokenData; // [rsp+60h] [rbp-49h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > hSenderProcessDupToken; // [rsp+68h] [rbp-41h] BYREF
  ctl::ComPtr<IMessageInfo> spMessageInfo; // [rsp+70h] [rbp-39h] BYREF
  unsigned int grantedAccess; // [rsp+78h] [rbp-31h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > hSenderProcessToken; // [rsp+80h] [rbp-29h] BYREF
  wil::last_error_context v30; // [rsp+88h] [rbp-21h] BYREF
  _GENERIC_MAPPING mapping; // [rsp+90h] [rbp-19h] BYREF
  MsgSenderInfo senderInfo; // [rsp+A0h] [rbp-9h] BYREF

  m_pMessageSession = this->m_pMessageSession;
  spMessageInfo.ptr_ = 0;
  if ( !m_pMessageSession )
  {
    OnFailure_977_((HRESULT)this);
    v2 = -2147467259;
    goto LABEL_49;
  }
  GetMessageInfo = m_pMessageSession->GetMessageInfo;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMessageInfo);
  v4 = GetMessageInfo(m_pMessageSession, &spMessageInfo.ptr_);
  v2 = v4;
  if ( v4 < 0
    || (memset(&senderInfo, 0, sizeof(senderInfo)),
        v4 = spMessageInfo.ptr_->GetCurrentSenderInfo(spMessageInfo.ptr_, &senderInfo),
        v2 = v4,
        v4 < 0) )
  {
    OnFailure_2990_(v4);
    goto LABEL_49;
  }
  v5 = OpenProcess(0x1000u, 0, senderInfo.ProcessID);
  hSenderProcess.m_ptr = v5;
  if ( (((unsigned __int64)v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_24;
  LastError = GetLastError();
  if ( LastError != 5 )
  {
    if ( LastError <= 0 )
    {
      v2 = LastError;
LABEL_20:
      if ( v2 < 0 )
      {
LABEL_12:
        OnFailure_2990_(v2);
LABEL_46:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSenderProcess);
        goto LABEL_49;
      }
LABEL_24:
      sd.m_ptr = 0;
      CurrentProcessId = GetCurrentProcessId();
      v12 = OpenProcess(0x20000u, 0, CurrentProcessId);
      m_ptr = sd.m_ptr;
      v14 = v12;
      tokenData.m_ptr = v12;
      if ( sd.m_ptr )
      {
        wil::last_error_context::last_error_context(&v30);
        LocalFree(m_ptr);
        wil::last_error_context::~last_error_context(&v30);
      }
      sd.m_ptr = 0;
      if ( !GetSecurityInfo(v14, SE_KERNEL_OBJECT, 7u, 0, 0, 0, 0, &sd.m_ptr) )
        goto LABEL_31;
      v15 = GetLastError();
      v2 = v15;
      if ( v15 > 0 )
        v2 = (unsigned __int16)v15 | 0x80070000;
      if ( v2 < 0 )
      {
        OnFailure_2990_(v2);
      }
      else
      {
LABEL_31:
        hSenderProcessToken.m_ptr = 0;
        hSenderProcessDupToken.m_ptr = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hSenderProcessToken,
          0);
        if ( OpenProcessToken(v5, 0x2000Au, &hSenderProcessToken.m_ptr) )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hSenderProcessDupToken,
            0);
          if ( DuplicateToken(hSenderProcessToken.m_ptr, SecurityImpersonation, &hSenderProcessDupToken.m_ptr) )
            goto LABEL_36;
        }
        v16 = GetLastError();
        v2 = v16;
        if ( v16 > 0 )
          v2 = (unsigned __int16)v16 | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_36:
          grantedAccess = 0;
          accessStatus = 0;
          v2 = 0;
          PrivilegeSetLength = 0;
          mapping.GenericRead = 132112;
          mapping.GenericWrite = 132074;
          mapping.GenericExecute = 1183745;
          mapping.GenericAll = 0x1FFFFF;
          if ( !AccessCheck(
                  sd.m_ptr,
                  hSenderProcessDupToken.m_ptr,
                  0x1FFFFFu,
                  &mapping,
                  0,
                  &PrivilegeSetLength,
                  &grantedAccess,
                  &accessStatus) )
          {
            if ( GetLastError() == 122 )
            {
              FailFast = (_PRIVILEGE_SET *)XcpAllocation::OSMemoryAllocateFailFast(PrivilegeSetLength);
              if ( !AccessCheck(
                      sd.m_ptr,
                      hSenderProcessDupToken.m_ptr,
                      0x1FFFFFu,
                      &mapping,
                      FailFast,
                      &PrivilegeSetLength,
                      &grantedAccess,
                      &accessStatus)
                || !accessStatus )
              {
                v2 = -2147024891;
              }
              operator delete(FailFast);
            }
            else
            {
              v18 = GetLastError();
              v2 = v18;
              if ( v18 > 0 )
                v2 = (unsigned __int16)v18 | 0x80070000;
            }
          }
        }
        else
        {
          OnFailure_2990_(v2);
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSenderProcessDupToken);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSenderProcessToken);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&tokenData);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sd);
      goto LABEL_46;
    }
LABEL_19:
    v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_20;
  }
  dwLength = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, 0, 0, &dwLength) && GetLastError() != 122 )
  {
    v7 = GetLastError();
    v2 = v7;
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    if ( v2 < 0 )
      goto LABEL_12;
  }
  v8 = (PSID *)LocalAlloc(0, dwLength);
  tokenData.m_ptr = v8;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, v8, dwLength, &dwLength) || !v8 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&tokenData);
    goto LABEL_19;
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v8);
  if ( *GetSidSubAuthority(*v8, (unsigned int)*SidSubAuthorityCount - 1) > 0x1000 )
  {
    OnFailure_1030_(v10);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&tokenData);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSenderProcess);
    v2 = -2147024891;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&tokenData);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSenderProcess);
    v2 = 0;
  }
LABEL_49:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMessageInfo);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1808ed124  push    rbp
0x1808ed126  push    rbx
0x1808ed127  push    rsi
0x1808ed128  push    rdi
0x1808ed129  push    r14
0x1808ed12b  push    r15
0x1808ed12d  lea     rbp, [rsp-2Fh]
0x1808ed132  sub     rsp, 0D8h
0x1808ed139  mov     rax, cs:__security_cookie
0x1808ed140  xor     rax, rsp
0x1808ed143  mov     [rbp+57h+var_40], rax
0x1808ed147  mov     rdi, [this+290h]
0x1808ed14e  xor     r14d, r14d
0x1808ed151  mov     [rbp+57h+spMessageInfo.ptr_], r14
0x1808ed155  test    rdi, rdi
0x1808ed158  jnz     short loc_1808ED169
0x1808ed15a  call    OnFailure_977_
0x1808ed15f  mov     ebx, 80004005h
0x1808ed164  jmp     loc_1808ED52B
0x1808ed169  mov     rax, [rdi]
0x1808ed16c  lea     this, [rbp+57h+spMessageInfo]; this
0x1808ed170  mov     rbx, [rax+20h]
0x1808ed174  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1808ed179  lea     rdx, [rbp+57h+spMessageInfo]
0x1808ed17d  mov     this, rdi
0x1808ed180  mov     rax, rbx
0x1808ed183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808ed188  mov     ebx, eax
0x1808ed18a  test    eax, eax
0x1808ed18c  js      loc_1808ED524
0x1808ed192  mov     this, [rbp+57h+spMessageInfo.ptr_]
0x1808ed196  lea     rdx, [rbp+57h+senderInfo]
0x1808ed19a  xorps   xmm0, xmm0
0x1808ed19d  movups  xmmword ptr [rbp+57h+senderInfo.VmID.Data1], xmm0
0x1808ed1a1  movups  xmmword ptr [rbp+57h+senderInfo.VmID.Data4+4], xmm0
0x1808ed1a5  mov     rax, [this]
0x1808ed1a8  mov     rax, [rax+18h]
0x1808ed1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808ed1b1  mov     ebx, eax
0x1808ed1b3  test    eax, eax
0x1808ed1b5  js      loc_1808ED51B
0x1808ed1bb  mov     r8d, [rbp+57h+senderInfo.ProcessID]; dwProcessId
0x1808ed1bf  xor     edx, edx; bInheritHandle
0x1808ed1c1  mov     ecx, 1000h; dwDesiredAccess
0x1808ed1c6  call    cs:__imp_OpenProcess
0x1808ed1cc  mov     rdi, rax
0x1808ed1cf  mov     [rbp+57h+hSenderProcess.m_ptr], rax
0x1808ed1d3  inc     rax
0x1808ed1d6  mov     r15d, 80070000h
0x1808ed1dc  test    rax, 0FFFFFFFFFFFFFFFEh
0x1808ed1e2  jnz     loc_1808ED308
0x1808ed1e8  call    cs:__imp_GetLastError
0x1808ed1ee  mov     esi, eax
0x1808ed1f0  cmp     eax, 5
0x1808ed1f3  jnz     loc_1808ED300
0x1808ed1f9  xor     r9d, r9d; TokenInformationLength
0x1808ed1fc  mov     [rbp+57h+dwLength], r14d
0x1808ed200  lea     rax, [rbp+57h+dwLength]
0x1808ed204  xor     r8d, r8d; TokenInformation
0x1808ed207  lea     edx, [rsi+14h]; TokenInformationClass
0x1808ed20a  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1808ed20f  lea     this, [r9-4]; TokenHandle
0x1808ed213  call    cs:__imp_GetTokenInformation
0x1808ed219  test    eax, eax
0x1808ed21b  jnz     short loc_1808ED24A
0x1808ed21d  call    cs:__imp_GetLastError
0x1808ed223  cmp     eax, 7Ah ; 'z'
0x1808ed226  jz      short loc_1808ED24A
0x1808ed228  call    cs:__imp_GetLastError
0x1808ed22e  mov     ebx, eax
0x1808ed230  test    eax, eax
0x1808ed232  jle     short loc_1808ED23A
0x1808ed234  movzx   ebx, ax
0x1808ed237  or      ebx, r15d
0x1808ed23a  test    ebx, ebx
0x1808ed23c  jns     short loc_1808ED24A
0x1808ed23e  mov     ecx, ebx; failedFrameHR
0x1808ed240  call    OnFailure_2990_
0x1808ed245  jmp     loc_1808ED507
0x1808ed24a  mov     edx, [rbp+57h+dwLength]; uBytes
0x1808ed24d  xor     ecx, ecx; uFlags
0x1808ed24f  call    cs:__imp_LocalAlloc
0x1808ed255  mov     r9d, [rbp+57h+dwLength]; TokenInformationLength
0x1808ed259  mov     edx, 19h; TokenInformationClass
0x1808ed25e  mov     rbx, rax
0x1808ed261  mov     [rbp+57h+tokenData.m_ptr], rax
0x1808ed265  lea     rax, [rbp+57h+dwLength]
0x1808ed269  mov     r8, rbx; TokenInformation
0x1808ed26c  mov     this, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1808ed273  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1808ed278  call    cs:__imp_GetTokenInformation
0x1808ed27e  test    eax, eax
0x1808ed280  jz      short loc_1808ED2E1
0x1808ed282  test    rbx, rbx
0x1808ed285  jz      short loc_1808ED2E1
0x1808ed287  mov     this, [rbx]; pSid
0x1808ed28a  call    cs:__imp_GetSidSubAuthorityCount
0x1808ed290  mov     this, [rbx]; pSid
0x1808ed293  movzx   edx, byte ptr [rax]
0x1808ed296  dec     edx; nSubAuthority
0x1808ed298  call    cs:__imp_GetSidSubAuthority
0x1808ed29e  cmp     dword ptr [rax], 1000h
0x1808ed2a4  ja      short loc_1808ED2C0
0x1808ed2a6  lea     this, [rbp+57h+tokenData]; this
0x1808ed2aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1808ed2af  lea     this, [rbp+57h+hSenderProcess]; this
0x1808ed2b3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed2b8  mov     ebx, r14d
0x1808ed2bb  jmp     loc_1808ED52B
0x1808ed2c0  call    OnFailure_1030_
0x1808ed2c5  lea     this, [rbp+57h+tokenData]; this
0x1808ed2c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1808ed2ce  lea     this, [rbp+57h+hSenderProcess]; this
0x1808ed2d2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed2d7  mov     ebx, 80070005h
0x1808ed2dc  jmp     loc_1808ED52B
0x1808ed2e1  lea     this, [rbp+57h+tokenData]; this
0x1808ed2e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1808ed2ea  movzx   ebx, si
0x1808ed2ed  or      ebx, r15d
0x1808ed2f0  test    ebx, ebx
0x1808ed2f2  jns     short loc_1808ED308
0x1808ed2f4  mov     ecx, ebx; failedFrameHR
0x1808ed2f6  call    OnFailure_2990_
0x1808ed2fb  jmp     loc_1808ED507
0x1808ed300  test    esi, esi
0x1808ed302  jg      short loc_1808ED2EA
0x1808ed304  mov     ebx, esi
0x1808ed306  jmp     short loc_1808ED2F0
0x1808ed308  mov     [rbp+57h+sd.m_ptr], r14
0x1808ed30c  call    cs:__imp_GetCurrentProcessId
0x1808ed312  xor     edx, edx; bInheritHandle
0x1808ed314  mov     ecx, 20000h; dwDesiredAccess
0x1808ed319  mov     r8d, eax; dwProcessId
0x1808ed31c  call    cs:__imp_OpenProcess
0x1808ed322  mov     rsi, [rbp+57h+sd.m_ptr]
0x1808ed326  mov     rbx, rax
0x1808ed329  mov     [rbp+57h+tokenData.m_ptr], rax
0x1808ed32d  test    rsi, rsi
0x1808ed330  jz      short loc_1808ED34D
0x1808ed332  lea     this, [rbp+57h+var_78]; this
0x1808ed336  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1808ed33b  mov     this, rsi; hMem
0x1808ed33e  call    cs:__imp_LocalFree
0x1808ed344  lea     this, [rbp+57h+var_78]; this
0x1808ed348  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1808ed34d  xor     r9d, r9d; ppsidOwner
0x1808ed350  mov     [rbp+57h+sd.m_ptr], r14
0x1808ed354  lea     rax, [rbp+57h+sd]
0x1808ed358  mov     this, rbx; handle
0x1808ed35b  mov     [rsp+100h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1808ed360  mov     [rsp+100h+ppSacl], r14; ppSacl
0x1808ed365  lea     edx, [r9+6]; ObjectType
0x1808ed369  mov     [rsp+100h+ppDacl], r14; ppDacl
0x1808ed36e  lea     r8d, [r9+7]; SecurityInfo
0x1808ed372  mov     [rsp+100h+ReturnLength], r14; ppsidGroup
0x1808ed377  call    cs:__imp_GetSecurityInfo
0x1808ed37d  test    eax, eax
0x1808ed37f  jz      short loc_1808ED3A3
0x1808ed381  call    cs:__imp_GetLastError
0x1808ed387  mov     ebx, eax
0x1808ed389  test    eax, eax
0x1808ed38b  jle     short loc_1808ED393
0x1808ed38d  movzx   ebx, ax
0x1808ed390  or      ebx, r15d
0x1808ed393  test    ebx, ebx
0x1808ed395  jns     short loc_1808ED3A3
0x1808ed397  mov     ecx, ebx; failedFrameHR
0x1808ed399  call    OnFailure_2990_
0x1808ed39e  jmp     loc_1808ED4F5
0x1808ed3a3  xor     edx, edx; ptr
0x1808ed3a5  mov     [rbp+57h+hSenderProcessToken.m_ptr], r14
0x1808ed3a9  lea     this, [rbp+57h+hSenderProcessToken]; this
0x1808ed3ad  mov     [rbp+57h+hSenderProcessDupToken.m_ptr], r14
0x1808ed3b1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1808ed3b6  lea     r8, [rbp+57h+hSenderProcessToken]; TokenHandle
0x1808ed3ba  mov     edx, 2000Ah; DesiredAccess
0x1808ed3bf  mov     this, rdi; ProcessHandle
0x1808ed3c2  call    cs:__imp_OpenProcessToken
0x1808ed3c8  test    eax, eax
0x1808ed3ca  jz      short loc_1808ED3EE
0x1808ed3cc  xor     edx, edx; ptr
0x1808ed3ce  lea     this, [rbp+57h+hSenderProcessDupToken]; this
0x1808ed3d2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1808ed3d7  mov     this, [rbp+57h+hSenderProcessToken.m_ptr]; ExistingTokenHandle
0x1808ed3db  lea     r8, [rbp+57h+hSenderProcessDupToken]; DuplicateTokenHandle
0x1808ed3df  mov     edx, 2; ImpersonationLevel
0x1808ed3e4  call    cs:__imp_DuplicateToken
0x1808ed3ea  test    eax, eax
0x1808ed3ec  jnz     short loc_1808ED408
0x1808ed3ee  call    cs:__imp_GetLastError
0x1808ed3f4  mov     ebx, eax
0x1808ed3f6  test    eax, eax
0x1808ed3f8  jle     short loc_1808ED400
0x1808ed3fa  movzx   ebx, ax
0x1808ed3fd  or      ebx, r15d
0x1808ed400  test    ebx, ebx
0x1808ed402  js      loc_1808ED512
0x1808ed408  mov     rdx, [rbp+57h+hSenderProcessDupToken.m_ptr]; ClientToken
0x1808ed40c  lea     rax, [rbp+57h+accessStatus]
0x1808ed410  mov     this, [rbp+57h+sd.m_ptr]; pSecurityDescriptor
0x1808ed414  lea     r9, [rbp+57h+mapping]; GenericMapping
0x1808ed418  mov     [rsp+100h+ppSecurityDescriptor], rax; AccessStatus
0x1808ed41d  mov     esi, 1FFFFFh
0x1808ed422  lea     rax, [rbp+57h+grantedAccess]
0x1808ed426  mov     [rbp+57h+grantedAccess], r14d
0x1808ed42a  mov     [rsp+100h+ppSacl], rax; GrantedAccess
0x1808ed42f  mov     r8d, esi; DesiredAccess
0x1808ed432  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1808ed436  mov     [rbp+57h+accessStatus], r14d
0x1808ed43a  mov     [rsp+100h+ppDacl], rax; PrivilegeSetLength
0x1808ed43f  mov     ebx, r14d
0x1808ed442  mov     [rsp+100h+ReturnLength], r14; PrivilegeSet
0x1808ed447  mov     [rbp+57h+PrivilegeSetLength], r14d
0x1808ed44b  mov     [rbp+57h+mapping.GenericRead], 20410h
0x1808ed452  mov     [rbp+57h+mapping.GenericWrite], 203EAh
0x1808ed459  mov     [rbp+57h+mapping.GenericExecute], 121001h
0x1808ed460  mov     [rbp+57h+mapping.GenericAll], esi
0x1808ed463  call    cs:__imp_AccessCheck
0x1808ed469  test    eax, eax
0x1808ed46b  jnz     short loc_1808ED4E3
0x1808ed46d  call    cs:__imp_GetLastError
0x1808ed473  cmp     eax, 7Ah ; 'z'
0x1808ed476  jnz     short loc_1808ED4D1
0x1808ed478  mov     ecx, [rbp+57h+PrivilegeSetLength]; cSize
0x1808ed47b  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1808ed480  mov     rdx, [rbp+57h+hSenderProcessDupToken.m_ptr]; ClientToken
0x1808ed484  lea     r9, [rbp+57h+mapping]; GenericMapping
0x1808ed488  mov     this, [rbp+57h+sd.m_ptr]; pSecurityDescriptor
0x1808ed48c  mov     rdi, rax
0x1808ed48f  lea     rax, [rbp+57h+accessStatus]
0x1808ed493  mov     r8d, esi; DesiredAccess
0x1808ed496  mov     [rsp+100h+ppSecurityDescriptor], rax; AccessStatus
0x1808ed49b  lea     rax, [rbp+57h+grantedAccess]
0x1808ed49f  mov     [rsp+100h+ppSacl], rax; GrantedAccess
0x1808ed4a4  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1808ed4a8  mov     [rsp+100h+ppDacl], rax; PrivilegeSetLength
0x1808ed4ad  mov     [rsp+100h+ReturnLength], rdi; PrivilegeSet
0x1808ed4b2  call    cs:__imp_AccessCheck
0x1808ed4b8  test    eax, eax
0x1808ed4ba  jz      short loc_1808ED4C2
0x1808ed4bc  cmp     [rbp+57h+accessStatus], r14d
0x1808ed4c0  jnz     short loc_1808ED4C7
0x1808ed4c2  mov     ebx, 80070005h
0x1808ed4c7  mov     this, rdi; pAddress
0x1808ed4ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1808ed4cf  jmp     short loc_1808ED4E3
0x1808ed4d1  call    cs:__imp_GetLastError
0x1808ed4d7  mov     ebx, eax
0x1808ed4d9  test    eax, eax
0x1808ed4db  jle     short loc_1808ED4E3
0x1808ed4dd  movzx   ebx, ax
0x1808ed4e0  or      ebx, r15d
0x1808ed4e3  lea     this, [rbp+57h+hSenderProcessDupToken]; this
0x1808ed4e7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed4ec  lea     this, [rbp+57h+hSenderProcessToken]; this
0x1808ed4f0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed4f5  lea     this, [rbp+57h+tokenData]; this
0x1808ed4f9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed4fe  lea     this, [rbp+57h+sd]; this
0x1808ed502  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1808ed507  lea     this, [rbp+57h+hSenderProcess]; this
0x1808ed50b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1808ed510  jmp     short loc_1808ED52B
0x1808ed512  mov     ecx, ebx; failedFrameHR
0x1808ed514  call    OnFailure_2990_
0x1808ed519  jmp     short loc_1808ED4E3
0x1808ed51b  mov     ecx, eax; failedFrameHR
0x1808ed51d  call    OnFailure_2990_
0x1808ed522  jmp     short loc_1808ED52B
0x1808ed524  mov     ecx, ebx; failedFrameHR
0x1808ed526  call    OnFailure_2990_
0x1808ed52b  lea     this, [rbp+57h+spMessageInfo]; this
0x1808ed52f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1808ed534  mov     eax, ebx
0x1808ed536  mov     this, [rbp+57h+var_40]
0x1808ed53a  xor     this, rsp; StackCookie
0x1808ed53d  call    __security_check_cookie
0x1808ed542  add     rsp, 0D8h
0x1808ed549  pop     r15
0x1808ed54b  pop     r14
0x1808ed54d  pop     rdi
0x1808ed54e  pop     rsi
0x1808ed54f  pop     rbx
0x1808ed550  pop     rbp
0x1808ed551  retn
```
