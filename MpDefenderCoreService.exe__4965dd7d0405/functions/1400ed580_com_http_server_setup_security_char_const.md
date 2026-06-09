# com::http::server::setup_security(char const *)

- ea: `0x1400ed580`
- end: `0x1400ed8b9`
- name: `?setup_security@server@http@com@@YAJPEBD@Z`
- size: `825`
- prototype: `__int64 __fastcall(com::http::server *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ed28c`

## callees

- `0x14003a5c0`
- `0x1400ec130`
- `0x1400ec23c`
- `0x1400ecc64`
- `0x1400ed580`
- `0x140166990`

## import_xrefs

- `ole32!CoInitializeSecurity` at `0x1400ed7df`
- `ole32!CoInitializeSecurity` at `0x1400ed7df`
- `KERNEL32!LocalFree` at `0x1400ed603`
- `KERNEL32!LocalFree` at `0x1400ed634`
- `KERNEL32!LocalFree` at `0x1400ed7f0`
- `KERNEL32!LocalFree` at `0x1400ed7fc`
- `KERNEL32!LocalFree` at `0x1400ed80d`
- `KERNEL32!LocalFree` at `0x1400ed820`
- `KERNEL32!LocalFree` at `0x1400ed84a`
- `KERNEL32!LocalFree` at `0x1400ed877`
- `KERNEL32!LocalFree` at `0x1400ed885`
- `KERNEL32!LocalFree` at `0x1400ed603`
- `KERNEL32!LocalFree` at `0x1400ed634`
- `KERNEL32!LocalFree` at `0x1400ed7f0`
- `KERNEL32!LocalFree` at `0x1400ed7fc`
- `KERNEL32!LocalFree` at `0x1400ed80d`
- `KERNEL32!LocalFree` at `0x1400ed820`
- `KERNEL32!LocalFree` at `0x1400ed84a`
- `KERNEL32!LocalFree` at `0x1400ed877`
- `KERNEL32!LocalFree` at `0x1400ed885`
- `KERNEL32!GetCurrentProcess` at `0x1400ed5c1`
- `KERNEL32!GetCurrentProcess` at `0x1400ed5c1`
- `KERNEL32!CloseHandle` at `0x1400ed642`
- `KERNEL32!CloseHandle` at `0x1400ed642`
- `KERNEL32!GetLastError` at `0x1400ed826`
- `KERNEL32!GetLastError` at `0x1400ed85a`
- `KERNEL32!GetLastError` at `0x1400ed826`
- `KERNEL32!GetLastError` at `0x1400ed85a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400ed7a8`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400ed7a8`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400ed6e6`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400ed6e6`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400ed76c`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400ed76c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1400ed6b2`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1400ed6b2`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1400ed71e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1400ed71e`
- `ADVAPI32!OpenProcessToken` at `0x1400ed5d3`
- `ADVAPI32!OpenProcessToken` at `0x1400ed5d3`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400ed751`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400ed751`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400ed787`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400ed787`

## pseudocode

```c
__int64 __fastcall com::http::server::setup_security(com::http::server *this, const char *a2)
{
  unsigned __int64 v2; // rbx
  void *v3; // rsi
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void **single_token_sid_28; // rax
  void **single_token_sid_4; // rax
  unsigned int v8; // edi
  PSECURITY_DESCRIPTOR v9; // rdi
  unsigned int v10; // r14d
  signed int v12; // eax
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+58h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-A0h] BYREF
  PSID pOwner; // [rsp+70h] [rbp-98h] BYREF
  _BYTE bDaclPresent[48]; // [rsp+78h] [rbp-90h] BYREF
  CHAR StringSecurityDescriptor[272]; // [rsp+A8h] [rbp-60h] BYREF

  v2 = 0;
  TokenHandle = 0;
  v3 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_35;
  v5 = TokenHandle;
  single_token_sid_28 = (void **)anonymous_namespace_::get_single_token_sid_28_(&hMem, TokenHandle);
  v2 = (unsigned __int64)*single_token_sid_28;
  *single_token_sid_28 = 0;
  if ( hMem )
    LocalFree(hMem);
  single_token_sid_4 = (void **)anonymous_namespace_::get_single_token_sid_4_(&hMem, TokenHandle);
  v3 = *single_token_sid_4;
  *single_token_sid_4 = 0;
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    CloseHandle(v5);
  if ( (v2 & -(__int64)(v2 != 0)) == 0 || !v3 )
  {
LABEL_35:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( !v3 )
    {
LABEL_39:
      if ( !v2 )
        return v8;
LABEL_40:
      LocalFree((HLOCAL)v2);
      return v8;
    }
LABEL_38:
    LocalFree(v3);
    goto LABEL_39;
  }
  memset(StringSecurityDescriptor, 0, 0x104u);
  v8 = StringCchPrintfA(
         StringSecurityDescriptor,
         0x104u,
         "O:%sG:%sD:(A;;CC;;;%s)",
         (const char *)v3,
         (const char *)v3,
         (const char *)(v2 & -(__int64)(v2 != 0)));
  if ( (v8 & 0x80000000) != 0 )
  {
    _mm_lfence();
    goto LABEL_38;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorA(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
LABEL_29:
    v12 = GetLastError();
    v8 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v8 = -2147418113;
    }
    _mm_lfence();
    LocalFree(v3);
    if ( !v2 )
      return v8;
    _mm_lfence();
    goto LABEL_40;
  }
  v9 = SecurityDescriptor;
  hMem = 0;
  *(_DWORD *)&bDaclPresent[4] = 0;
  *(_DWORD *)bDaclPresent = 0;
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, (LPBOOL)&bDaclPresent[4], (PACL *)&hMem, (LPBOOL)bDaclPresent)
    || !*(_DWORD *)&bDaclPresent[4]
    || *(_DWORD *)bDaclPresent
    || (pOwner = 0, !GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, (LPBOOL)bDaclPresent))
    || *(_DWORD *)bDaclPresent
    || (memset(&bDaclPresent[8], 0, 40), !InitializeSecurityDescriptor(&bDaclPresent[8], 1u))
    || !SetSecurityDescriptorOwner(&bDaclPresent[8], pOwner, 0)
    || !SetSecurityDescriptorGroup(&bDaclPresent[8], pOwner, 0)
    || !SetSecurityDescriptorDacl(&bDaclPresent[8], *(BOOL *)&bDaclPresent[4], (PACL)hMem, *(BOOL *)bDaclPresent) )
  {
    if ( v9 )
      LocalFree(v9);
    goto LABEL_29;
  }
  v10 = CoInitializeSecurity(&bDaclPresent[8], -1, 0, 0, 6u, 2u, 0, 0, 0);
  if ( v9 )
    LocalFree(v9);
  _mm_lfence();
  LocalFree(v3);
  if ( v2 )
  {
    _mm_lfence();
    LocalFree((HLOCAL)v2);
  }
  return v10;
}

```

## disassembly

```asm
0x1400ed580  mov     rax, rsp
0x1400ed583  mov     [rax+8], rbx
0x1400ed587  mov     [rax+10h], rsi
0x1400ed58b  mov     [rax+18h], rdi
0x1400ed58f  push    rbp
0x1400ed590  push    r14
0x1400ed592  push    r15
0x1400ed594  lea     rbp, [rax-0D8h]
0x1400ed59b  sub     rsp, 1C0h
0x1400ed5a2  mov     rax, cs:__security_cookie
0x1400ed5a9  xor     rax, rsp
0x1400ed5ac  mov     [rbp+0D0h+var_20], rax
0x1400ed5b3  xor     r15d, r15d
0x1400ed5b6  mov     ebx, r15d
0x1400ed5b9  mov     [rsp+1D0h+TokenHandle], r15
0x1400ed5be  mov     esi, r15d
0x1400ed5c1  call    cs:__imp_GetCurrentProcess
0x1400ed5c7  mov     rcx, rax; ProcessHandle
0x1400ed5ca  lea     r8, [rsp+1D0h+TokenHandle]; TokenHandle
0x1400ed5cf  lea     edx, [r15+8]; DesiredAccess
0x1400ed5d3  call    cs:__imp_OpenProcessToken
0x1400ed5d9  test    eax, eax
0x1400ed5db  jz      loc_1400ED85A
0x1400ed5e1  mov     rdi, [rsp+1D0h+TokenHandle]
0x1400ed5e6  lea     rcx, [rsp+1D0h+hMem]
0x1400ed5eb  mov     rdx, rdi
0x1400ed5ee  call    _anonymous_namespace___get_single_token_sid_28_
0x1400ed5f3  mov     rbx, [rax]
0x1400ed5f6  mov     [rax], r15
0x1400ed5f9  mov     rcx, [rsp+1D0h+hMem]; hMem
0x1400ed5fe  test    rcx, rcx
0x1400ed601  jz      short loc_1400ED609
0x1400ed603  call    cs:__imp_LocalFree
0x1400ed609  mov     rdx, [rsp+1D0h+TokenHandle]
0x1400ed60e  lea     rcx, [rsp+1D0h+hMem]
0x1400ed613  mov     rax, rbx
0x1400ed616  neg     rax
0x1400ed619  sbb     r14, r14
0x1400ed61c  and     r14, rbx
0x1400ed61f  call    _anonymous_namespace___get_single_token_sid_4_
0x1400ed624  mov     rsi, [rax]
0x1400ed627  mov     [rax], r15
0x1400ed62a  mov     rcx, [rsp+1D0h+hMem]; hMem
0x1400ed62f  test    rcx, rcx
0x1400ed632  jz      short loc_1400ED63A
0x1400ed634  call    cs:__imp_LocalFree
0x1400ed63a  test    rdi, rdi
0x1400ed63d  jz      short loc_1400ED648
0x1400ed63f  mov     rcx, rdi; hObject
0x1400ed642  call    cs:__imp_CloseHandle
0x1400ed648  test    r14, r14
0x1400ed64b  jz      loc_1400ED85A
0x1400ed651  test    rsi, rsi
0x1400ed654  jz      loc_1400ED85A
0x1400ed65a  mov     edi, 104h
0x1400ed65f  lea     rcx, [rbp+0D0h+StringSecurityDescriptor]; void *
0x1400ed663  mov     r8d, edi; Size
0x1400ed666  xor     edx, edx; Val
0x1400ed668  call    memset
0x1400ed66d  mov     r9, rsi
0x1400ed670  mov     qword ptr [rsp+1D0h+dwImpLevel], r14
0x1400ed675  lea     r8, aOSgSdACcS; "O:%sG:%sD:(A;;CC;;;%s)"
0x1400ed67c  mov     qword ptr [rsp+1D0h+dwAuthnLevel], rsi
0x1400ed681  mov     edx, edi; unsigned __int64
0x1400ed683  lea     rcx, [rbp+0D0h+StringSecurityDescriptor]; Buffer
0x1400ed687  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400ed68c  mov     edi, eax
0x1400ed68e  test    eax, eax
0x1400ed690  jns     short loc_1400ED69A
0x1400ed692  lfence
0x1400ed695  jmp     loc_1400ED874
0x1400ed69a  xor     r9d, r9d; SecurityDescriptorSize
0x1400ed69d  mov     [rsp+1D0h+SecurityDescriptor], r15
0x1400ed6a2  lea     r8, [rsp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x1400ed6a7  lea     rcx, [rbp+0D0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400ed6ab  lea     r14d, [r9+1]
0x1400ed6af  mov     edx, r14d; StringSDRevision
0x1400ed6b2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorA
0x1400ed6b8  test    eax, eax
0x1400ed6ba  jz      loc_1400ED826
0x1400ed6c0  mov     rdi, [rsp+1D0h+SecurityDescriptor]
0x1400ed6c5  lea     r9, [rsp+1D0h+bDaclPresent]; lpbDaclDefaulted
0x1400ed6ca  mov     rcx, rdi; pSecurityDescriptor
0x1400ed6cd  mov     [rsp+1D0h+hMem], r15
0x1400ed6d2  lea     r8, [rsp+1D0h+hMem]; pDacl
0x1400ed6d7  mov     [rsp+1D0h+bDaclPresent+4], r15d
0x1400ed6dc  lea     rdx, [rsp+1D0h+bDaclPresent+4]; lpbDaclPresent
0x1400ed6e1  mov     [rsp+1D0h+bDaclPresent], r15d
0x1400ed6e6  call    cs:__imp_GetSecurityDescriptorDacl
0x1400ed6ec  test    eax, eax
0x1400ed6ee  jz      loc_1400ED818
0x1400ed6f4  cmp     [rsp+1D0h+bDaclPresent+4], r15d
0x1400ed6f9  jz      loc_1400ED818
0x1400ed6ff  cmp     [rsp+1D0h+bDaclPresent], r15d
0x1400ed704  jnz     loc_1400ED818
0x1400ed70a  mov     rcx, [rsp+1D0h+SecurityDescriptor]; pSecurityDescriptor
0x1400ed70f  lea     r8, [rsp+1D0h+bDaclPresent]; lpbOwnerDefaulted
0x1400ed714  lea     rdx, [rsp+1D0h+pOwner]; pOwner
0x1400ed719  mov     [rsp+1D0h+pOwner], r15
0x1400ed71e  call    cs:__imp_GetSecurityDescriptorOwner
0x1400ed724  test    eax, eax
0x1400ed726  jz      loc_1400ED818
0x1400ed72c  cmp     [rsp+1D0h+bDaclPresent], r15d
0x1400ed731  jnz     loc_1400ED818
0x1400ed737  xorps   xmm0, xmm0
0x1400ed73a  lea     rcx, [rsp+1D0h+bDaclPresent+8]; pSecurityDescriptor
0x1400ed73f  xor     eax, eax
0x1400ed741  mov     edx, r14d; dwRevision
0x1400ed744  movups  xmmword ptr [rsp+1D0h+bDaclPresent+8], xmm0
0x1400ed749  mov     [rbp+0D0h+var_138], rax
0x1400ed74d  movups  [rbp+0D0h+var_148], xmm0
0x1400ed751  call    cs:__imp_InitializeSecurityDescriptor
0x1400ed757  test    eax, eax
0x1400ed759  jz      loc_1400ED818
0x1400ed75f  mov     rdx, [rsp+1D0h+pOwner]; pOwner
0x1400ed764  lea     rcx, [rsp+1D0h+bDaclPresent+8]; pSecurityDescriptor
0x1400ed769  xor     r8d, r8d; bOwnerDefaulted
0x1400ed76c  call    cs:__imp_SetSecurityDescriptorOwner
0x1400ed772  test    eax, eax
0x1400ed774  jz      loc_1400ED818
0x1400ed77a  mov     rdx, [rsp+1D0h+pOwner]; pGroup
0x1400ed77f  lea     rcx, [rsp+1D0h+bDaclPresent+8]; pSecurityDescriptor
0x1400ed784  xor     r8d, r8d; bGroupDefaulted
0x1400ed787  call    cs:__imp_SetSecurityDescriptorGroup
0x1400ed78d  test    eax, eax
0x1400ed78f  jz      loc_1400ED818
0x1400ed795  mov     r9d, [rsp+1D0h+bDaclPresent]; bDaclDefaulted
0x1400ed79a  lea     rcx, [rsp+1D0h+bDaclPresent+8]; pSecurityDescriptor
0x1400ed79f  mov     r8, [rsp+1D0h+hMem]; pDacl
0x1400ed7a4  mov     edx, [rsp+1D0h+bDaclPresent+4]; bDaclPresent
0x1400ed7a8  call    cs:__imp_SetSecurityDescriptorDacl
0x1400ed7ae  test    eax, eax
0x1400ed7b0  jz      short loc_1400ED818
0x1400ed7b2  mov     [rsp+1D0h+pReserved3], r15; pReserved3
0x1400ed7b7  lea     rcx, [rsp+1D0h+bDaclPresent+8]; pSecDesc
0x1400ed7bc  mov     [rsp+1D0h+dwCapabilities], r15d; dwCapabilities
0x1400ed7c1  xor     r9d, r9d; pReserved1
0x1400ed7c4  mov     [rsp+1D0h+pAuthList], r15; pAuthList
0x1400ed7c9  xor     r8d, r8d; asAuthSvc
0x1400ed7cc  mov     [rsp+1D0h+dwImpLevel], 2; dwImpLevel
0x1400ed7d4  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400ed7d7  mov     [rsp+1D0h+dwAuthnLevel], 6; dwAuthnLevel
0x1400ed7df  call    cs:__imp_CoInitializeSecurity
0x1400ed7e5  mov     r14d, eax
0x1400ed7e8  test    rdi, rdi
0x1400ed7eb  jz      short loc_1400ED7F6
0x1400ed7ed  mov     rcx, rdi; hMem
0x1400ed7f0  call    cs:__imp_LocalFree
0x1400ed7f6  lfence
0x1400ed7f9  mov     rcx, rsi; hMem
0x1400ed7fc  call    cs:__imp_LocalFree
0x1400ed802  test    rbx, rbx
0x1400ed805  jz      short loc_1400ED813
0x1400ed807  lfence
0x1400ed80a  mov     rcx, rbx; hMem
0x1400ed80d  call    cs:__imp_LocalFree
0x1400ed813  mov     eax, r14d
0x1400ed816  jmp     short loc_1400ED88D
0x1400ed818  test    rdi, rdi
0x1400ed81b  jz      short loc_1400ED826
0x1400ed81d  mov     rcx, rdi; hMem
0x1400ed820  call    cs:__imp_LocalFree
0x1400ed826  call    cs:__imp_GetLastError
0x1400ed82c  mov     edi, eax
0x1400ed82e  test    eax, eax
0x1400ed830  jz      short loc_1400ED83F
0x1400ed832  jle     short loc_1400ED844
0x1400ed834  movzx   edi, ax
0x1400ed837  or      edi, 80070000h
0x1400ed83d  jmp     short loc_1400ED844
0x1400ed83f  mov     edi, 8000FFFFh
0x1400ed844  lfence
0x1400ed847  mov     rcx, rsi; hMem
0x1400ed84a  call    cs:__imp_LocalFree
0x1400ed850  test    rbx, rbx
0x1400ed853  jz      short loc_1400ED88B
0x1400ed855  lfence
0x1400ed858  jmp     short loc_1400ED882
0x1400ed85a  call    cs:__imp_GetLastError
0x1400ed860  mov     edi, eax
0x1400ed862  test    eax, eax
0x1400ed864  jle     short loc_1400ED86F
0x1400ed866  movzx   edi, ax
0x1400ed869  or      edi, 80070000h
0x1400ed86f  test    rsi, rsi
0x1400ed872  jz      short loc_1400ED87D
0x1400ed874  mov     rcx, rsi; hMem
0x1400ed877  call    cs:__imp_LocalFree
0x1400ed87d  test    rbx, rbx
0x1400ed880  jz      short loc_1400ED88B
0x1400ed882  mov     rcx, rbx; hMem
0x1400ed885  call    cs:__imp_LocalFree
0x1400ed88b  mov     eax, edi
0x1400ed88d  mov     rcx, [rbp+0D0h+var_20]
0x1400ed894  xor     rcx, rsp; StackCookie
0x1400ed897  call    __security_check_cookie
0x1400ed89c  lea     r11, [rsp+1D0h+var_10]
0x1400ed8a4  mov     rbx, [r11+20h]
0x1400ed8a8  mov     rsi, [r11+28h]
0x1400ed8ac  mov     rdi, [r11+30h]
0x1400ed8b0  mov     rsp, r11
0x1400ed8b3  pop     r15
0x1400ed8b5  pop     r14
0x1400ed8b7  pop     rbp
0x1400ed8b8  retn
```
