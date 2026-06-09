# CreateAndAclLogFile

- ea: `0x18000fcfc`
- end: `0x18000fe59`
- name: `CreateAndAclLogFile`
- size: `349`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800102c4`

## callees

- `0x180009174`
- `0x18000aea0`
- `0x18000fc58`
- `0x18000fcfc`
- `0x180010044`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000fdcd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000fdcd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000fd96`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000fd96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fd30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fd30`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000fe24`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000fe24`

## string_xrefs

- `0x18000fd49`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x18000fde0`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall CreateAndAclLogFile(LPWSTR pObjectName)
{
  const char *v2; // r9
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // rdx
  int LastError; // eax
  DWORD v7; // eax
  unsigned int v8; // r8d
  unsigned int psidGroup; // [rsp+20h] [rbp-40h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  HANDLE FileW; // [rsp+48h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  WINBOOL bDaclPresent; // [rsp+78h] [rbp+18h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp+20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+28h] BYREF

  FileW = CreateFileW(pObjectName, 0x80000000, 3u, 0, 4u, 0x8000080u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
    SecurityDescriptorSize = 0;
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;GRGW;;;LS)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        if ( !bDaclPresent
          || !pDacl
          || (v7 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0)) == 0 )
        {
          v3 = 0;
          goto LABEL_14;
        }
        LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xAC, v8, (const char *)v7, psidGroup);
LABEL_8:
        v3 = LastError;
LABEL_14:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
        return v3;
      }
      v5 = 160;
    }
    else
    {
      v5 = 151;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                  v4);
    goto LABEL_8;
  }
  v3 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x8B,
         (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
         v2);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  return v3;
}

```

## disassembly

```asm
0x18000fcfc  mov     rax, rsp
0x18000fcff  mov     [rax+8], rbx
0x18000fd03  push    rbp
0x18000fd04  mov     rbp, rsp
0x18000fd07  sub     rsp, 60h
0x18000fd0b  mov     qword ptr [rax-38h], 0
0x18000fd13  xor     r9d, r9d; lpSecurityAttributes
0x18000fd16  mov     dword ptr [rax-40h], 8000080h
0x18000fd1d  mov     edx, 80000000h; dwDesiredAccess
0x18000fd22  mov     rbx, rcx
0x18000fd25  mov     dword ptr [rax-48h], 4
0x18000fd2c  lea     r8d, [r9+3]; dwShareMode
0x18000fd30  call    cs:__imp_CreateFileW
0x18000fd36  mov     [rbp+var_18], rax
0x18000fd3a  inc     rax
0x18000fd3d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000fd43  jnz     short loc_18000FD6A
0x18000fd45  mov     rcx, [rbp+8]; this
0x18000fd49  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000fd50  mov     edx, 8Bh; void *
0x18000fd55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fd5a  lea     rcx, [rbp+var_18]
0x18000fd5e  mov     ebx, eax
0x18000fd60  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000fd65  jmp     loc_18000FE4C
0x18000fd6a  lea     rcx, [rbp+var_18]
0x18000fd6e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000fd73  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000fd77  mov     [rbp+SecurityDescriptorSize], 0
0x18000fd7e  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000fd82  mov     [rbp+SecurityDescriptor], 0
0x18000fd8a  mov     edx, 1; StringSDRevision
0x18000fd8f  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGW;;;LS)"
0x18000fd96  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000fd9c  test    eax, eax
0x18000fd9e  jnz     short loc_18000FDA7
0x18000fda0  mov     edx, 97h
0x18000fda5  jmp     short loc_18000FDDC
0x18000fda7  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18000fdab  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000fdaf  lea     r8, [rbp+pDacl]; pDacl
0x18000fdb3  mov     [rbp+pDacl], 0
0x18000fdbb  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000fdbf  mov     [rbp+bDaclPresent], 0
0x18000fdc6  mov     [rbp+bDaclDefaulted], 0
0x18000fdcd  call    cs:__imp_GetSecurityDescriptorDacl
0x18000fdd3  test    eax, eax
0x18000fdd5  jnz     short loc_18000FDF0
0x18000fdd7  mov     edx, 0A0h; void *
0x18000fddc  mov     rcx, [rbp+8]; this
0x18000fde0  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000fde7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fdec  mov     ebx, eax
0x18000fdee  jmp     short loc_18000FE43
0x18000fdf0  cmp     [rbp+bDaclPresent], 0
0x18000fdf4  jz      short loc_18000FE41
0x18000fdf6  mov     rax, [rbp+pDacl]
0x18000fdfa  test    rax, rax
0x18000fdfd  jz      short loc_18000FE41
0x18000fdff  xor     r9d, r9d; psidOwner
0x18000fe02  mov     [rsp+60h+pSacl], 0; pSacl
0x18000fe0b  mov     [rsp+60h+var_38], rax; pDacl
0x18000fe10  mov     rcx, rbx; pObjectName
0x18000fe13  mov     [rsp+60h+psidGroup], 0; unsigned int
0x18000fe1c  lea     edx, [r9+1]; ObjectType
0x18000fe20  lea     r8d, [r9+4]; SecurityInfo
0x18000fe24  call    cs:__imp_SetNamedSecurityInfoW
0x18000fe2a  test    eax, eax
0x18000fe2c  jz      short loc_18000FE41
0x18000fe2e  mov     rcx, [rbp+8]; this
0x18000fe32  mov     r9d, eax; char *
0x18000fe35  mov     edx, 0ACh; void *
0x18000fe3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000fe3f  jmp     short loc_18000FDEC
0x18000fe41  xor     ebx, ebx
0x18000fe43  lea     rcx, [rbp+SecurityDescriptor]
0x18000fe47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000fe4c  mov     eax, ebx
0x18000fe4e  mov     rbx, [rsp+60h+arg_0]
0x18000fe53  add     rsp, 60h
0x18000fe57  pop     rbp
0x18000fe58  retn
```
