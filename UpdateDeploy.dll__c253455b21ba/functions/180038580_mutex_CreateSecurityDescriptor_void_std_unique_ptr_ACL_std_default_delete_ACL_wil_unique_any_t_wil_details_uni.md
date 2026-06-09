# mutex::CreateSecurityDescriptor(void *,std::unique_ptr<_ACL,std::default_delete<_ACL>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180038580`
- end: `0x180038747`
- name: `?CreateSecurityDescriptor@mutex@@YAJPEAXAEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180038914`
- `0x180038d40`

## callees

- `0x180002214`
- `0x1800110fc`
- `0x180038580`
- `0x180061d54`
- `0x180062534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003872e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003872e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038630`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038630`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003865e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038726`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003865e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038726`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800385bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800385bc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180038596`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180038596`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800385f3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800385f3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180038617`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180038617`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180038651`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180038651`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800386b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800386b5`

## string_xrefs

- `0x18003868c`: `InitializeSecurityDescriptor`
- `0x1800385a8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x1800386ee`: `SetSecurityDescriptorDacl`

## pseudocode

```c
__int64 __fastcall mutex::CreateSecurityDescriptor(PSID pSid, PACL *a2, void **a3)
{
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD v9; // esi
  struct _ACL *v10; // rax
  PACL v11; // rcx
  _OWORD *v12; // rdi
  signed int LastError; // eax
  signed int v14; // ecx
  signed int v15; // eax
  signed int v16; // ecx
  void *v17; // rsi
  DWORD v18; // ebx
  PSID pSida; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !IsValidSid(pSid) )
  {
    v7 = 51;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
             v6);
  }
  v9 = GetLengthSid(pSid) + 20;
  v10 = (struct _ACL *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = *a2;
  *a2 = v10;
  if ( v11 )
    operator delete(v11, (const struct std::nothrow_t *)8);
  if ( !InitializeAcl(*a2, v9, 2u) )
  {
    v7 = 64;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
             v6);
  }
  if ( !AddAccessAllowedAceEx(*a2, 2u, 0, 0x10000000u, pSid) )
  {
    v7 = 70;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
             v6);
  }
  v12 = LocalAlloc(0, 0x28u);
  *v12 = 0;
  v12[1] = 0;
  *((_QWORD *)v12 + 4) = 0;
  if ( !InitializeSecurityDescriptor(v12, 1u) )
  {
    LocalFree(v12);
    LastError = GetLastError();
    v14 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v14 = LastError;
    if ( v14 >= 0 )
      v14 = -2147418113;
    LODWORD(pSida) = v14;
    WUTrace(0, 0, 0x1000000, 3, pSida, L"InitializeSecurityDescriptor");
    v7 = 82;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
             v6);
  }
  if ( !SetSecurityDescriptorDacl(v12, 1, *a2, 0) )
  {
    LocalFree(v12);
    v15 = GetLastError();
    v16 = (unsigned __int16)v15 | 0x80070000;
    if ( v15 <= 0 )
      v16 = v15;
    if ( v16 >= 0 )
      v16 = -2147418113;
    LODWORD(pSida) = v16;
    WUTrace(0, 0, 0x1000000, 3, pSida, L"SetSecurityDescriptorDacl");
    v7 = 92;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
             v6);
  }
  v17 = *a3;
  if ( *a3 )
  {
    v18 = GetLastError();
    LocalFree(v17);
    SetLastError(v18);
  }
  *a3 = v12;
  return 0;
}

```

## disassembly

```asm
0x180038580  mov     [rsp+arg_18], rbx
0x180038585  push    rsi
0x180038586  push    rdi
0x180038587  push    r14
0x180038589  sub     rsp, 30h
0x18003858d  mov     r14, r8
0x180038590  mov     rbx, rdx
0x180038593  mov     rdi, rcx
0x180038596  call    cs:__imp_IsValidSid
0x18003859c  test    eax, eax
0x18003859e  jnz     short loc_1800385B9
0x1800385a0  lea     edx, [rax+33h]; void *
0x1800385a3  mov     rcx, [rsp+48h]; this
0x1800385a8  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800385af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800385b4  jmp     loc_180038739
0x1800385b9  mov     rcx, rdi; pSid
0x1800385bc  call    cs:__imp_GetLengthSid
0x1800385c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800385c9  lea     esi, [rax+14h]
0x1800385cc  mov     ecx, esi; unsigned __int64
0x1800385ce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800385d3  mov     rcx, [rbx]; void *
0x1800385d6  mov     [rbx], rax
0x1800385d9  test    rcx, rcx
0x1800385dc  jz      short loc_1800385E8
0x1800385de  mov     edx, 8; struct std::nothrow_t *
0x1800385e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800385e8  mov     rcx, [rbx]; pAcl
0x1800385eb  mov     r8d, 2; dwAclRevision
0x1800385f1  mov     edx, esi; nAclLength
0x1800385f3  call    cs:__imp_InitializeAcl
0x1800385f9  test    eax, eax
0x1800385fb  jnz     short loc_180038602
0x1800385fd  lea     edx, [rax+40h]
0x180038600  jmp     short loc_1800385A3
0x180038602  mov     rcx, [rbx]; pAcl
0x180038605  xor     r8d, r8d; AceFlags
0x180038608  mov     r9d, 10000000h; AccessMask
0x18003860e  mov     [rsp+48h+pSid], rdi; pSid
0x180038613  lea     edx, [r8+2]; dwAceRevision
0x180038617  call    cs:__imp_AddAccessAllowedAceEx
0x18003861d  test    eax, eax
0x18003861f  jnz     short loc_180038629
0x180038621  lea     edx, [rax+46h]
0x180038624  jmp     loc_1800385A3
0x180038629  mov     edx, 28h ; '('; uBytes
0x18003862e  xor     ecx, ecx; uFlags
0x180038630  call    cs:__imp_LocalAlloc
0x180038636  mov     rdi, rax
0x180038639  xorps   xmm0, xmm0
0x18003863c  xor     eax, eax
0x18003863e  mov     rcx, rdi; pSecurityDescriptor
0x180038641  movups  xmmword ptr [rdi], xmm0
0x180038644  lea     esi, [rax+1]
0x180038647  movups  xmmword ptr [rdi+10h], xmm0
0x18003864b  mov     edx, esi; dwRevision
0x18003864d  mov     [rdi+20h], rax
0x180038651  call    cs:__imp_InitializeSecurityDescriptor
0x180038657  mov     rcx, rdi; pSecurityDescriptor
0x18003865a  test    eax, eax
0x18003865c  jnz     short loc_1800386AD
0x18003865e  call    cs:__imp_LocalFree
0x180038664  call    cs:__imp_GetLastError
0x18003866a  movzx   ecx, ax
0x18003866d  lea     r9d, [rsi+2]
0x180038671  or      ecx, 80070000h
0x180038677  mov     r8d, 1000000h
0x18003867d  test    eax, eax
0x18003867f  cmovle  ecx, eax
0x180038682  mov     eax, 8000FFFFh
0x180038687  test    ecx, ecx
0x180038689  cmovns  ecx, eax
0x18003868c  lea     rax, aInitializesecu_0; "InitializeSecurityDescriptor"
0x180038693  mov     [rsp+48h+var_20], rax
0x180038698  xor     edx, edx
0x18003869a  mov     dword ptr [rsp+48h+pSid], ecx
0x18003869e  xor     ecx, ecx
0x1800386a0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800386a5  lea     edx, [rsi+51h]
0x1800386a8  jmp     loc_1800385A3
0x1800386ad  mov     r8, [rbx]; pDacl
0x1800386b0  xor     r9d, r9d; bDaclDefaulted
0x1800386b3  mov     edx, esi; bDaclPresent
0x1800386b5  call    cs:__imp_SetSecurityDescriptorDacl
0x1800386bb  test    eax, eax
0x1800386bd  jnz     short loc_180038713
0x1800386bf  mov     rcx, rdi; hMem
0x1800386c2  call    cs:__imp_LocalFree
0x1800386c8  call    cs:__imp_GetLastError
0x1800386ce  movzx   ecx, ax
0x1800386d1  mov     r8d, 1000000h
0x1800386d7  or      ecx, 80070000h
0x1800386dd  test    eax, eax
0x1800386df  cmovle  ecx, eax
0x1800386e2  mov     eax, 8000FFFFh
0x1800386e7  test    ecx, ecx
0x1800386e9  cmovns  ecx, eax
0x1800386ec  xor     edx, edx
0x1800386ee  lea     rax, aSetsecuritydes_0; "SetSecurityDescriptorDacl"
0x1800386f5  mov     [rsp+48h+var_20], rax
0x1800386fa  mov     dword ptr [rsp+48h+pSid], ecx
0x1800386fe  xor     ecx, ecx
0x180038700  lea     r9d, [rdx+3]
0x180038704  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180038709  mov     edx, 5Ch ; '\'
0x18003870e  jmp     loc_1800385A3
0x180038713  mov     rsi, [r14]
0x180038716  test    rsi, rsi
0x180038719  jz      short loc_180038734
0x18003871b  call    cs:__imp_GetLastError
0x180038721  mov     rcx, rsi; hMem
0x180038724  mov     ebx, eax
0x180038726  call    cs:__imp_LocalFree
0x18003872c  mov     ecx, ebx; dwErrCode
0x18003872e  call    cs:__imp_SetLastError
0x180038734  mov     [r14], rdi
0x180038737  xor     eax, eax
0x180038739  mov     rbx, [rsp+48h+arg_18]
0x18003873e  add     rsp, 30h
0x180038742  pop     r14
0x180038744  pop     rdi
0x180038745  pop     rsi
0x180038746  retn
```
