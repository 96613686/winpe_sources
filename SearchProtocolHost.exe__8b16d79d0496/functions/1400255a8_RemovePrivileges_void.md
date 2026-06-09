# RemovePrivileges(void)

- ea: `0x1400255a8`
- end: `0x14002575a`
- name: `?RemovePrivileges@@YAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x140005924`
- `0x14000f1c4`
- `0x14000f208`
- `0x1400255a8`
- `0x140037ca8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002561d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140025683`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002561d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140025683`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400256f1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400256f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400255e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400256fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400255e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400256fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400255c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400255c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400255d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400255d7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400256a2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400256a2`

## string_xrefs

- `0x140025699`: `SeChangeNotifyPrivilege`

## pseudocode

```c
__int64 RemovePrivileges(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v2; // ebx
  signed int v3; // eax
  struct _TOKEN_PRIVILEGES *v4; // rbx
  __int64 i; // rcx
  signed int v6; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF
  struct _TOKEN_PRIVILEGES *v10; // [rsp+60h] [rbp+28h] BYREF
  _LUID Luid; // [rsp+68h] [rbp+30h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v2;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v3 = GetLastError();
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v2 = v3;
    goto LABEL_20;
  }
  v10 = (struct _TOKEN_PRIVILEGES *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v10;
  if ( v10 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenPrivileges, v10, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_17;
    Luid = 0;
    LookupPrivilegeValueW(0, L"SeChangeNotifyPrivilege", &Luid);
    for ( i = 0; (unsigned int)i < v4->PrivilegeCount; i = (unsigned int)(i + 1) )
    {
      if ( v4->Privileges[i].Luid.LowPart != Luid.LowPart || v4->Privileges[i].Luid.HighPart != Luid.HighPart )
        v4->Privileges[i].Attributes = 4;
    }
    if ( !AdjustTokenPrivileges(TokenHandle, 0, v4, TokenInformationLength, 0, 0) )
    {
LABEL_17:
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      SecUtil::CSID::~CSID((SecUtil::CSID *)&v10);
      goto LABEL_20;
    }
    SecUtil::CSID::~CSID((SecUtil::CSID *)&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  else
  {
    SecUtil::CSID::~CSID((SecUtil::CSID *)&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1400255a8  push    rbp
0x1400255aa  push    rbx
0x1400255ab  mov     rbp, rsp
0x1400255ae  sub     rsp, 38h
0x1400255b2  xor     edx, edx
0x1400255b4  mov     [rbp+TokenHandle], 0
0x1400255bc  lea     rcx, [rbp+TokenHandle]
0x1400255c0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400255c5  call    cs:__imp_GetCurrentProcess
0x1400255cb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400255cf  mov     edx, 28h ; '('; DesiredAccess
0x1400255d4  mov     rcx, rax; ProcessHandle
0x1400255d7  call    cs:__imp_OpenProcessToken
0x1400255dd  test    eax, eax
0x1400255df  jnz     short loc_1400255FF
0x1400255e1  call    cs:__imp_GetLastError
0x1400255e7  mov     ebx, eax
0x1400255e9  test    eax, eax
0x1400255eb  jle     loc_140025719
0x1400255f1  movzx   ebx, ax
0x1400255f4  or      ebx, 80070000h
0x1400255fa  jmp     loc_140025719
0x1400255ff  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140025603  lea     rax, [rbp+TokenInformationLength]
0x140025607  xor     r9d, r9d; TokenInformationLength
0x14002560a  mov     [rbp+TokenInformationLength], 0
0x140025611  xor     r8d, r8d; TokenInformation
0x140025614  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140025619  lea     edx, [r9+3]; TokenInformationClass
0x14002561d  call    cs:__imp_GetTokenInformation
0x140025623  test    eax, eax
0x140025625  jnz     short loc_14002564B
0x140025627  call    cs:__imp_GetLastError
0x14002562d  cmp     eax, 7Ah ; 'z'
0x140025630  jz      short loc_14002564B
0x140025632  call    cs:__imp_GetLastError
0x140025638  test    eax, eax
0x14002563a  jle     short loc_140025644
0x14002563c  movzx   eax, ax
0x14002563f  or      eax, 80070000h
0x140025644  mov     ebx, eax
0x140025646  jmp     loc_140025719
0x14002564b  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14002564e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140025655  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002565a  mov     [rbp+arg_10], rax
0x14002565e  mov     rbx, rax
0x140025661  test    rax, rax
0x140025664  jz      loc_14002573C
0x14002566a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14002566e  lea     rax, [rbp+TokenInformationLength]
0x140025672  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140025676  mov     r8, rbx; TokenInformation
0x140025679  mov     edx, 3; TokenInformationClass
0x14002567e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140025683  call    cs:__imp_GetTokenInformation
0x140025689  test    eax, eax
0x14002568b  jz      short loc_1400256FB
0x14002568d  lea     r8, [rbp+Luid]; lpLuid
0x140025691  mov     qword ptr [rbp+Luid.LowPart], 0
0x140025699  lea     rdx, Name; "SeChangeNotifyPrivilege"
0x1400256a0  xor     ecx, ecx; lpSystemName
0x1400256a2  call    cs:__imp_LookupPrivilegeValueW
0x1400256a8  xor     ecx, ecx
0x1400256aa  cmp     [rbx], ecx
0x1400256ac  jbe     short loc_1400256D2
0x1400256ae  mov     eax, [rbp+Luid.LowPart]
0x1400256b1  lea     rdx, [rcx+rcx*2]
0x1400256b5  cmp     [rbx+rdx*4+4], eax
0x1400256b9  jnz     short loc_1400256C4
0x1400256bb  mov     eax, [rbp+Luid.HighPart]
0x1400256be  cmp     [rbx+rdx*4+8], eax
0x1400256c2  jz      short loc_1400256CC
0x1400256c4  mov     dword ptr [rbx+rdx*4+0Ch], 4
0x1400256cc  inc     ecx
0x1400256ce  cmp     ecx, [rbx]
0x1400256d0  jb      short loc_1400256AE
0x1400256d2  mov     r9d, [rbp+TokenInformationLength]; BufferLength
0x1400256d6  mov     r8, rbx; NewState
0x1400256d9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400256dd  xor     edx, edx; DisableAllPrivileges
0x1400256df  mov     [rsp+38h+var_10], 0; ReturnLength
0x1400256e8  mov     [rsp+38h+ReturnLength], 0; PreviousState
0x1400256f1  call    cs:__imp_AdjustTokenPrivileges
0x1400256f7  test    eax, eax
0x1400256f9  jnz     short loc_140025726
0x1400256fb  call    cs:__imp_GetLastError
0x140025701  mov     ebx, eax
0x140025703  test    eax, eax
0x140025705  jle     short loc_140025710
0x140025707  movzx   ebx, ax
0x14002570a  or      ebx, 80070000h
0x140025710  lea     rcx, [rbp+arg_10]; this
0x140025714  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140025719  lea     rcx, [rbp+TokenHandle]
0x14002571d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025722  mov     eax, ebx
0x140025724  jmp     short loc_140025753
0x140025726  lea     rcx, [rbp+arg_10]; this
0x14002572a  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x14002572f  lea     rcx, [rbp+TokenHandle]
0x140025733  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025738  xor     eax, eax
0x14002573a  jmp     short loc_140025753
0x14002573c  lea     rcx, [rbp+arg_10]; this
0x140025740  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140025745  lea     rcx, [rbp+TokenHandle]
0x140025749  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002574e  mov     eax, 8007000Eh
0x140025753  add     rsp, 38h
0x140025757  pop     rbx
0x140025758  pop     rbp
0x140025759  retn
```
