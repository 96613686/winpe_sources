# winreSetACL

- ea: `0x180032728`
- end: `0x18003291e`
- name: `winreSetACL`
- size: `502`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c8f0`
- `0x180026158`
- `0x180026a40`
- `0x180028e30`
- `0x180039b38`
- `0x180039dd4`
- `0x18003aac0`

## callees

- `0x1800059fc`
- `0x180032728`
- `0x180032dc8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800327bb`
- `KERNEL32!GetLastError` at `0x180032897`
- `KERNEL32!GetLastError` at `0x1800327bb`
- `KERNEL32!GetLastError` at `0x180032897`
- `KERNEL32!HeapFree` at `0x1800328ee`
- `KERNEL32!HeapFree` at `0x1800328ee`
- `KERNEL32!HeapAlloc` at `0x1800327e9`
- `KERNEL32!HeapAlloc` at `0x1800327e9`
- `KERNEL32!GetProcessHeap` at `0x1800327d6`
- `KERNEL32!GetProcessHeap` at `0x1800328e0`
- `KERNEL32!GetProcessHeap` at `0x1800327d6`
- `KERNEL32!GetProcessHeap` at `0x1800328e0`
- `KERNEL32!SetFileAttributesW` at `0x18003288d`
- `KERNEL32!SetFileAttributesW` at `0x18003288d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800327ae`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800327ae`
- `ADVAPI32!GetLengthSid` at `0x1800327cc`
- `ADVAPI32!GetLengthSid` at `0x1800327cc`
- `ADVAPI32!InitializeAcl` at `0x180032814`
- `ADVAPI32!InitializeAcl` at `0x180032814`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180032839`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180032839`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180032868`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180032868`
- `ADVAPI32!FreeSid` at `0x1800328d5`
- `ADVAPI32!FreeSid` at `0x1800328d5`

## string_xrefs

- `0x1800328ae`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x18003275e`: `SeTakeOwnershipPrivilege`
- `0x1800328b8`: `winreSetACL %s (0x%x) in file %S line %d`
- `0x18003287c`: `failed to set named security info`

## pseudocode

```c
__int64 __fastcall winreSetACL(WCHAR *lpFileName)
{
  struct _ACL *v2; // rdi
  DWORD LastError; // ebx
  DWORD v4; // r14d
  HANDLE ProcessHeap; // rax
  struct _ACL *v6; // rax
  const wchar_t *v7; // r8
  DWORD v8; // eax
  HANDLE v9; // rax
  DWORD nSubAuthority3[2]; // [rsp+28h] [rbp-58h]
  PSID psidOwner; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  psidOwner = 0;
  winreSetPriviledge(L"SeTakeOwnershipPrivilege");
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    v2 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_13;
  }
  v4 = GetLengthSid(psidOwner) + 16;
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v6 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v4);
  v2 = v6;
  if ( v6 )
  {
    if ( !InitializeAcl(v6, v4, 2u) || !AddAccessAllowedAceEx(v2, 2u, 3u, 0x10000000u, psidOwner) )
      goto LABEL_3;
    LastError = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, 0x80000005, psidOwner, 0, v2, 0);
    if ( LastError )
    {
      nSubAuthority3[0] = 566;
      v7 = L"failed to set named security info";
    }
    else
    {
      if ( SetFileAttributesW(lpFileName, 0x2006u) )
        goto LABEL_13;
      v8 = GetLastError();
      nSubAuthority3[0] = 570;
      v7 = L"failed to set file attributes";
      LastError = v8;
    }
  }
  else
  {
    nSubAuthority3[0] = 532;
    v7 = L"failed to allocate memory";
  }
  UnattendLogW(
    2,
    L"winreSetACL %s (0x%x) in file %S line %d",
    v7,
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
    *(_QWORD *)nSubAuthority3);
LABEL_13:
  if ( psidOwner )
    FreeSid(psidOwner);
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  return LastError;
}

```

## disassembly

```asm
0x180032728  mov     [rsp-28h+arg_8], rbx
0x18003272d  mov     [rsp-28h+arg_10], rsi
0x180032732  push    rbp
0x180032733  push    rdi
0x180032734  push    r12
0x180032736  push    r14
0x180032738  push    r15
0x18003273a  mov     rbp, rsp
0x18003273d  sub     rsp, 80h
0x180032744  mov     rax, cs:__security_cookie
0x18003274b  xor     rax, rsp
0x18003274e  mov     [rbp+var_10], rax
0x180032752  mov     rsi, rcx
0x180032755  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18003275b  xor     r15d, r15d
0x18003275e  lea     rcx, Name; "SeTakeOwnershipPrivilege"
0x180032765  mov     dword ptr [rbp+pIdentifierAuthority.Value], r15d
0x180032769  mov     [rbp+psidOwner], r15
0x18003276d  call    winreSetPriviledge
0x180032772  lea     rax, [rbp+psidOwner]
0x180032776  mov     r9d, 220h; nSubAuthority1
0x18003277c  mov     [rsp+80h+pSid], rax; pSid
0x180032781  lea     r12d, [r15+2]
0x180032785  mov     [rsp+80h+nSubAuthority7], r15d; nSubAuthority7
0x18003278a  lea     r8d, [r15+20h]; nSubAuthority0
0x18003278e  mov     [rsp+80h+nSubAuthority6], r15d; nSubAuthority6
0x180032793  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180032797  mov     [rsp+80h+nSubAuthority5], r15d; nSubAuthority5
0x18003279c  mov     dl, r12b; nSubAuthorityCount
0x18003279f  mov     [rsp+80h+nSubAuthority4], r15d; nSubAuthority4
0x1800327a4  mov     [rsp+80h+nSubAuthority3], r15d; nSubAuthority3
0x1800327a9  mov     [rsp+80h+nSubAuthority2], r15d; nSubAuthority2
0x1800327ae  call    cs:__imp_AllocateAndInitializeSid
0x1800327b4  test    eax, eax
0x1800327b6  jnz     short loc_1800327C8
0x1800327b8  mov     edi, r15d
0x1800327bb  call    cs:__imp_GetLastError
0x1800327c1  mov     ebx, eax
0x1800327c3  jmp     loc_1800328CC
0x1800327c8  mov     rcx, [rbp+psidOwner]; pSid
0x1800327cc  call    cs:__imp_GetLengthSid
0x1800327d2  lea     r14d, [rax+10h]
0x1800327d6  call    cs:__imp_GetProcessHeap
0x1800327dc  mov     ebx, 8
0x1800327e1  mov     r8d, r14d; dwBytes
0x1800327e4  mov     rcx, rax; hHeap
0x1800327e7  mov     edx, ebx; dwFlags
0x1800327e9  call    cs:__imp_HeapAlloc
0x1800327ef  mov     rdi, rax
0x1800327f2  test    rax, rax
0x1800327f5  jnz     short loc_18003280B
0x1800327f7  mov     [rsp+80h+nSubAuthority3], 214h
0x1800327ff  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180032806  jmp     loc_1800328AE
0x18003280b  mov     r8d, r12d; dwAclRevision
0x18003280e  mov     edx, r14d; nAclLength
0x180032811  mov     rcx, rdi; pAcl
0x180032814  call    cs:__imp_InitializeAcl
0x18003281a  test    eax, eax
0x18003281c  jz      short loc_1800327BB
0x18003281e  mov     rax, [rbp+psidOwner]
0x180032822  mov     r9d, 10000000h; AccessMask
0x180032828  mov     r8d, 3; AceFlags
0x18003282e  mov     qword ptr [rsp+80h+nSubAuthority2], rax; pSid
0x180032833  mov     edx, r12d; dwAceRevision
0x180032836  mov     rcx, rdi; pAcl
0x180032839  call    cs:__imp_AddAccessAllowedAceEx
0x18003283f  test    eax, eax
0x180032841  jz      loc_1800327BB
0x180032847  mov     r9, [rbp+psidOwner]; psidOwner
0x18003284b  mov     edx, 1; ObjectType
0x180032850  mov     qword ptr [rsp+80h+nSubAuthority4], r15; pSacl
0x180032855  mov     r8d, 80000005h; SecurityInfo
0x18003285b  mov     qword ptr [rsp+80h+nSubAuthority3], rdi; pDacl
0x180032860  mov     rcx, rsi; pObjectName
0x180032863  mov     qword ptr [rsp+80h+nSubAuthority2], r15; psidGroup
0x180032868  call    cs:__imp_SetNamedSecurityInfoW
0x18003286e  mov     ebx, eax
0x180032870  test    eax, eax
0x180032872  jz      short loc_180032885
0x180032874  mov     [rsp+80h+nSubAuthority3], 236h
0x18003287c  lea     r8, aFailedToSetNam_0; "failed to set named security info"
0x180032883  jmp     short loc_1800328AE
0x180032885  mov     edx, 2006h; dwFileAttributes
0x18003288a  mov     rcx, rsi; lpFileName
0x18003288d  call    cs:__imp_SetFileAttributesW
0x180032893  test    eax, eax
0x180032895  jnz     short loc_1800328CC
0x180032897  call    cs:__imp_GetLastError
0x18003289d  mov     [rsp+80h+nSubAuthority3], 23Ah
0x1800328a5  lea     r8, aFailedToSetFil; "failed to set file attributes"
0x1800328ac  mov     ebx, eax
0x1800328ae  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800328b5  mov     r9d, ebx
0x1800328b8  lea     rdx, aWinresetaclS0x; "winreSetACL %s (0x%x) in file %S line %"...
0x1800328bf  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x1800328c4  mov     ecx, r12d
0x1800328c7  call    UnattendLogW
0x1800328cc  mov     rcx, [rbp+psidOwner]; pSid
0x1800328d0  test    rcx, rcx
0x1800328d3  jz      short loc_1800328DB
0x1800328d5  call    cs:__imp_FreeSid
0x1800328db  test    rdi, rdi
0x1800328de  jz      short loc_1800328F4
0x1800328e0  call    cs:__imp_GetProcessHeap
0x1800328e6  mov     r8, rdi; lpMem
0x1800328e9  xor     edx, edx; dwFlags
0x1800328eb  mov     rcx, rax; hHeap
0x1800328ee  call    cs:__imp_HeapFree
0x1800328f4  mov     eax, ebx
0x1800328f6  mov     rcx, [rbp+var_10]
0x1800328fa  xor     rcx, rsp; StackCookie
0x1800328fd  call    __security_check_cookie
0x180032902  lea     r11, [rsp+80h+var_s0]
0x18003290a  mov     rbx, [r11+38h]
0x18003290e  mov     rsi, [r11+40h]
0x180032912  mov     rsp, r11
0x180032915  pop     r15
0x180032917  pop     r14
0x180032919  pop     r12
0x18003291b  pop     rdi
0x18003291c  pop     rbp
0x18003291d  retn
```
