# CERTMAP_USER_CONTEXT::Create(void *,_EXPLICIT_ACCESS_W *)

- ea: `0x180001ad8`
- end: `0x180001e00`
- name: `?Create@CERTMAP_USER_CONTEXT@@QEAAJPEAXPEAU_EXPLICIT_ACCESS_W@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(CERTMAP_USER_CONTEXT *this, void *, struct _EXPLICIT_ACCESS_W *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x180001ad8`
- `0x180003ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d38`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d9a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180001c61`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180001c61`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180001c45`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180001c45`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180001bf8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180001bf8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001dbd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001dbd`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001b71`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001bbd`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001b71`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001bbd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001ca8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001cc8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001ca8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001dcc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180001c21`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180001c21`
- `iisutil!PuDbgPrint` at `0x180001d1f`
- `iisutil!PuDbgPrint` at `0x180001d1f`
- `iisutil!DisableTokenBackupPrivilege` at `0x180001d2d`
- `iisutil!DisableTokenBackupPrivilege` at `0x180001d2d`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001d79`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001d79`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180001db7`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180001db7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001b8d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001b8d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001dde`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001dde`
- `SspiCli!GetUserNameExW` at `0x180001d59`
- `SspiCli!GetUserNameExW` at `0x180001d90`
- `SspiCli!GetUserNameExW` at `0x180001d59`
- `SspiCli!GetUserNameExW` at `0x180001d90`

## string_xrefs

- `0x180001cfb`: `DuplicateTokenEx failed, hr = 0x%x\n`
- `0x180001d06`: `CERTMAP_USER_CONTEXT::Create`
- `0x180001d18`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\certmap_auth\certmap_auth.cxx`

## pseudocode

```c
__int64 __fastcall CERTMAP_USER_CONTEXT::Create(CERTMAP_USER_CONTEXT *this, void *a2, struct _EXPLICIT_ACCESS_W *a3)
{
  signed int v6; // ebx
  _QWORD *v7; // rbx
  signed int v8; // eax
  bool v9; // cc
  struct _ACL *v10; // r8
  void **v11; // rbx
  signed int LastError; // eax
  WCHAR *v13; // rdx
  signed int v14; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-69h] BYREF
  ULONG nSize; // [rsp+34h] [rbp-65h] BYREF
  WINBOOL bDaclPresent; // [rsp+38h] [rbp-61h] BYREF
  PACL NewAcl; // [rsp+40h] [rbp-59h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-51h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-49h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+58h] [rbp-41h] BYREF
  __int128 v23; // [rsp+70h] [rbp-29h] BYREF
  __int128 v24; // [rsp+80h] [rbp-19h]
  __int64 v25; // [rsp+90h] [rbp-9h]
  _QWORD pSecurityDescriptor[4]; // [rsp+98h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR v27; // [rsp+B8h] [rbp+1Fh]
  int v28; // [rsp+C0h] [rbp+27h]
  __int16 v29; // [rsp+C4h] [rbp+2Bh]

  pSecurityDescriptor[0] = 0;
  v29 = 256;
  v27 = pSecurityDescriptor;
  v28 = 32;
  nLengthNeeded = 32;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  NewAcl = 0;
  v25 = 0;
  memset(&TokenAttributes, 0, sizeof(TokenAttributes));
  v23 = 0;
  v24 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_36;
  }
  if ( GetKernelObjectSecurity(a2, 4u, pSecurityDescriptor, 0x20u, &nLengthNeeded) )
  {
    v7 = pSecurityDescriptor;
  }
  else
  {
    if ( GetLastError() != 122 )
      goto LABEL_8;
    if ( !BUFFER::Resize((BUFFER *)pSecurityDescriptor, nLengthNeeded) )
    {
      v6 = -2147024888;
      goto LABEL_34;
    }
    v7 = v27;
    if ( !GetKernelObjectSecurity(a2, 4u, v27, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_8;
  }
  if ( !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    goto LABEL_8;
  if ( bDaclPresent )
  {
    v10 = pDacl;
  }
  else
  {
    v10 = 0;
    pDacl = 0;
  }
  v8 = SetEntriesInAclW(1u, a3, v10, &NewAcl);
  v6 = v8;
  v9 = v8 <= 0;
  if ( v8 )
  {
LABEL_9:
    if ( !v9 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_34;
  }
  v23 = 0;
  v25 = 0;
  v24 = 0;
  if ( !InitializeSecurityDescriptor(&v23, 1u) || !SetSecurityDescriptorDacl(&v23, 1, NewAcl, 0) )
    goto LABEL_8;
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_QWORD *)&TokenAttributes.bInheritHandle = 0;
  v11 = (void **)((char *)this + 72);
  TokenAttributes.lpSecurityDescriptor = &v23;
  if ( !DuplicateTokenEx(a2, 0, &TokenAttributes, SecurityDelegation, TokenImpersonation, (PHANDLE)this + 9)
    && !DuplicateTokenEx(a2, 0, &TokenAttributes, SecurityImpersonation, TokenImpersonation, (PHANDLE)this + 9) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\certmap_auth\\certmap_auth.cxx",
        688,
        "CERTMAP_USER_CONTEXT::Create",
        "DuplicateTokenEx failed, hr = 0x%x\n",
        v6);
    goto LABEL_34;
  }
  DisableTokenBackupPrivilege(*v11);
  if ( !SetThreadToken(0, *v11) )
  {
LABEL_8:
    v8 = GetLastError();
    v6 = v8;
    v9 = v8 <= 0;
    goto LABEL_9;
  }
  v13 = (WCHAR *)*((_QWORD *)this + 6);
  nSize = *((_DWORD *)this + 14) >> 1;
  if ( GetUserNameExW(NameSamCompatible, v13, &nSize) )
  {
LABEL_32:
    v6 = 0;
    STRU::SyncWithBuffer((CERTMAP_USER_CONTEXT *)((char *)this + 16));
    goto LABEL_33;
  }
  if ( GetLastError() != 234 )
    goto LABEL_30;
  v6 = STRU::Resize((CERTMAP_USER_CONTEXT *)((char *)this + 16), 2 * nSize);
  if ( v6 >= 0 )
  {
    if ( !GetUserNameExW(NameSamCompatible, *((LPWSTR *)this + 6), &nSize) )
    {
LABEL_30:
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
LABEL_33:
  RevertToSelf();
LABEL_34:
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
LABEL_36:
  BUFFER::~BUFFER((BUFFER *)pSecurityDescriptor);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001ad8  push    rbp
0x180001ada  push    rbx
0x180001adb  push    rsi
0x180001adc  push    rdi
0x180001add  push    r14
0x180001adf  lea     rbp, [rsp-37h]
0x180001ae4  sub     rsp, 0D0h
0x180001aeb  mov     rax, cs:__security_cookie
0x180001af2  xor     rax, rsp
0x180001af5  mov     [rbp+57h+var_28], rax
0x180001af9  xorps   xmm0, xmm0
0x180001afc  mov     [rbp+57h+pSecurityDescriptor], 0
0x180001b04  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180001b08  mov     [rbp+57h+var_2C], 100h
0x180001b0e  mov     r9d, 20h ; ' '; nLength
0x180001b14  mov     [rbp+57h+var_38], rax
0x180001b18  xor     eax, eax
0x180001b1a  mov     [rbp+57h+var_30], r9d
0x180001b1e  mov     [rbp+57h+nLengthNeeded], r9d
0x180001b22  mov     r14, r8
0x180001b25  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x180001b29  mov     rdi, rdx
0x180001b2c  mov     [rbp+57h+bDaclPresent], eax
0x180001b2f  mov     rsi, rcx
0x180001b32  mov     [rbp+57h+bDaclDefaulted], eax
0x180001b35  mov     [rbp+57h+pDacl], rax
0x180001b39  mov     [rbp+57h+NewAcl], rax
0x180001b3d  mov     [rbp+57h+var_60], rax
0x180001b41  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x180001b45  movups  [rbp+57h+var_80], xmm0
0x180001b49  movups  [rbp+57h+var_70], xmm0
0x180001b4d  test    rdx, rdx
0x180001b50  jnz     short loc_180001B5C
0x180001b52  mov     ebx, 80070057h
0x180001b57  jmp     loc_180001DDA
0x180001b5c  lea     rax, [rbp+57h+nLengthNeeded]
0x180001b60  mov     edx, 4; RequestedInformation
0x180001b65  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180001b69  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180001b6e  mov     rcx, rdi; Handle
0x180001b71  call    cs:__imp_GetKernelObjectSecurity
0x180001b77  test    eax, eax
0x180001b79  jnz     short loc_180001BE5
0x180001b7b  call    cs:__imp_GetLastError
0x180001b81  cmp     eax, 7Ah ; 'z'
0x180001b84  jnz     short loc_180001BC7
0x180001b86  mov     edx, [rbp+57h+nLengthNeeded]
0x180001b89  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180001b8d  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001b93  test    al, al
0x180001b95  jnz     short loc_180001BA1
0x180001b97  mov     ebx, 80070008h
0x180001b9c  jmp     loc_180001DC3
0x180001ba1  mov     rbx, [rbp+57h+var_38]
0x180001ba5  lea     rax, [rbp+57h+nLengthNeeded]
0x180001ba9  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180001bad  mov     r8, rbx; pSecurityDescriptor
0x180001bb0  mov     edx, 4; RequestedInformation
0x180001bb5  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180001bba  mov     rcx, rdi; Handle
0x180001bbd  call    cs:__imp_GetKernelObjectSecurity
0x180001bc3  test    eax, eax
0x180001bc5  jnz     short loc_180001BE9
0x180001bc7  call    cs:__imp_GetLastError
0x180001bcd  mov     ebx, eax
0x180001bcf  test    eax, eax
0x180001bd1  jle     loc_180001DC3
0x180001bd7  movzx   ebx, ax
0x180001bda  or      ebx, 80070000h
0x180001be0  jmp     loc_180001DC3
0x180001be5  lea     rbx, [rbp+57h+pSecurityDescriptor]
0x180001be9  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180001bed  mov     rcx, rbx; pSecurityDescriptor
0x180001bf0  lea     r8, [rbp+57h+pDacl]; pDacl
0x180001bf4  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180001bf8  call    cs:__imp_GetSecurityDescriptorDacl
0x180001bfe  test    eax, eax
0x180001c00  jz      short loc_180001BC7
0x180001c02  cmp     [rbp+57h+bDaclPresent], 0
0x180001c06  jnz     short loc_180001C11
0x180001c08  xor     r8d, r8d
0x180001c0b  mov     [rbp+57h+pDacl], r8
0x180001c0f  jmp     short loc_180001C15
0x180001c11  mov     r8, [rbp+57h+pDacl]; OldAcl
0x180001c15  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180001c19  mov     rdx, r14; pListOfExplicitEntries
0x180001c1c  mov     ecx, 1; cCountOfExplicitEntries
0x180001c21  call    cs:__imp_SetEntriesInAclW
0x180001c27  mov     ebx, eax
0x180001c29  test    eax, eax
0x180001c2b  jnz     short loc_180001BD1
0x180001c2d  xorps   xmm0, xmm0
0x180001c30  lea     edx, [rbx+1]; dwRevision
0x180001c33  xor     eax, eax
0x180001c35  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x180001c39  movups  [rbp+57h+var_80], xmm0
0x180001c3d  mov     [rbp+57h+var_60], rax
0x180001c41  movups  [rbp+57h+var_70], xmm0
0x180001c45  call    cs:__imp_InitializeSecurityDescriptor
0x180001c4b  test    eax, eax
0x180001c4d  jz      loc_180001BC7
0x180001c53  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180001c57  lea     edx, [rbx+1]; bDaclPresent
0x180001c5a  xor     r9d, r9d; bDaclDefaulted
0x180001c5d  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x180001c61  call    cs:__imp_SetSecurityDescriptorDacl
0x180001c67  test    eax, eax
0x180001c69  jz      loc_180001BC7
0x180001c6f  mov     r14d, 2
0x180001c75  mov     qword ptr [rbp+57h+TokenAttributes.nLength], 18h
0x180001c7d  lea     rax, [rbp+57h+var_80]
0x180001c81  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], 0
0x180001c89  lea     rbx, [rsi+48h]
0x180001c8d  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], rax
0x180001c91  mov     [rsp+0F0h+phNewToken], rbx; phNewToken
0x180001c96  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180001c9a  lea     r9d, [r14+1]; ImpersonationLevel
0x180001c9e  mov     dword ptr [rsp+0F0h+lpnLengthNeeded], r14d; TokenType
0x180001ca3  xor     edx, edx; dwDesiredAccess
0x180001ca5  mov     rcx, rdi; hExistingToken
0x180001ca8  call    cs:__imp_DuplicateTokenEx
0x180001cae  test    eax, eax
0x180001cb0  jnz     short loc_180001D2A
0x180001cb2  mov     [rsp+0F0h+phNewToken], rbx; phNewToken
0x180001cb7  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180001cbb  mov     r9d, r14d; ImpersonationLevel
0x180001cbe  mov     dword ptr [rsp+0F0h+lpnLengthNeeded], r14d; TokenType
0x180001cc3  xor     edx, edx; dwDesiredAccess
0x180001cc5  mov     rcx, rdi; hExistingToken
0x180001cc8  call    cs:__imp_DuplicateTokenEx
0x180001cce  test    eax, eax
0x180001cd0  jnz     short loc_180001D2A
0x180001cd2  call    cs:__imp_GetLastError
0x180001cd8  mov     ebx, eax
0x180001cda  test    eax, eax
0x180001cdc  jle     short loc_180001CE7
0x180001cde  movzx   ebx, ax
0x180001ce1  or      ebx, 80070000h
0x180001ce7  test    byte ptr cs:g_dwDebugFlags, 3
0x180001cee  jz      loc_180001DC3
0x180001cf4  mov     rcx, cs:g_pDebug
0x180001cfb  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, hr = 0x%x\n"
0x180001d02  mov     dword ptr [rsp+0F0h+phNewToken], ebx
0x180001d06  lea     r9, aCertmapUserCon_0; "CERTMAP_USER_CONTEXT::Create"
0x180001d0d  mov     r8d, 2B0h
0x180001d13  mov     [rsp+0F0h+lpnLengthNeeded], rax
0x180001d18  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001d1f  call    cs:__imp_PuDbgPrint
0x180001d25  jmp     loc_180001DC3
0x180001d2a  mov     rcx, [rbx]
0x180001d2d  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180001d33  mov     rdx, [rbx]; Token
0x180001d36  xor     ecx, ecx; Thread
0x180001d38  call    cs:__imp_SetThreadToken
0x180001d3e  test    eax, eax
0x180001d40  jz      loc_180001BC7
0x180001d46  mov     eax, [rsi+38h]
0x180001d49  lea     r8, [rbp+57h+nSize]; nSize
0x180001d4d  mov     rdx, [rsi+30h]; lpNameBuffer
0x180001d51  mov     ecx, r14d; NameFormat
0x180001d54  shr     eax, 1
0x180001d56  mov     [rbp+57h+nSize], eax
0x180001d59  call    cs:__imp_GetUserNameExW
0x180001d5f  test    al, al
0x180001d61  jnz     short loc_180001DB1
0x180001d63  call    cs:__imp_GetLastError
0x180001d69  cmp     eax, 0EAh
0x180001d6e  jnz     short loc_180001D9A
0x180001d70  mov     edx, [rbp+57h+nSize]
0x180001d73  lea     rcx, [rsi+10h]
0x180001d77  add     edx, edx
0x180001d79  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180001d7f  mov     ebx, eax
0x180001d81  test    eax, eax
0x180001d83  js      short loc_180001DBD
0x180001d85  mov     rdx, [rsi+30h]; lpNameBuffer
0x180001d89  lea     r8, [rbp+57h+nSize]; nSize
0x180001d8d  mov     ecx, r14d; NameFormat
0x180001d90  call    cs:__imp_GetUserNameExW
0x180001d96  test    al, al
0x180001d98  jnz     short loc_180001DB1
0x180001d9a  call    cs:__imp_GetLastError
0x180001da0  mov     ebx, eax
0x180001da2  test    eax, eax
0x180001da4  jle     short loc_180001DBD
0x180001da6  movzx   ebx, ax
0x180001da9  or      ebx, 80070000h
0x180001daf  jmp     short loc_180001DBD
0x180001db1  xor     ebx, ebx
0x180001db3  lea     rcx, [rsi+10h]
0x180001db7  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180001dbd  call    cs:__imp_RevertToSelf
0x180001dc3  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180001dc7  test    rcx, rcx
0x180001dca  jz      short loc_180001DDA
0x180001dcc  call    cs:__imp_LocalFree
0x180001dd2  mov     [rbp+57h+NewAcl], 0
0x180001dda  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180001dde  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001de4  mov     eax, ebx
0x180001de6  mov     rcx, [rbp+57h+var_28]
0x180001dea  xor     rcx, rsp; StackCookie
0x180001ded  call    __security_check_cookie
0x180001df2  add     rsp, 0D0h
0x180001df9  pop     r14
0x180001dfb  pop     rdi
0x180001dfc  pop     rsi
0x180001dfd  pop     rbx
0x180001dfe  pop     rbp
0x180001dff  retn
```
