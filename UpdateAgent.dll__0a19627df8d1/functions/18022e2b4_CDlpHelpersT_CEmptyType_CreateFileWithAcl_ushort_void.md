# CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)

- ea: `0x18022e2b4`
- end: `0x18022e5f9`
- name: `?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z`
- size: `837`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18023f3b0`
- `0x180240f70`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x180221ce8`
- `0x18022e2b4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022e4d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022e4d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e408`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e56f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e5ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e408`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e56f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e5ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e5c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e5c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e41c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e3a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e3a5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18022e360`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18022e360`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18022e599`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18022e599`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18022e453`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18022e453`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18022e3e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18022e3f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18022e3e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18022e3f5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18022e47b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18022e49f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18022e47b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18022e49f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022e55d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022e55d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18022e516`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18022e516`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateFileWithAcl(LPCWSTR lpFileName, __int64 *a2)
{
  struct _ACL *v4; // rbx
  PSID v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // esi
  signed int LastError; // eax
  signed int v10; // eax
  PSID v11; // rsi
  DWORD LengthSid; // ebx
  DWORD v13; // r13d
  HANDLE ProcessHeap; // rax
  struct _ACL *v15; // rax
  HANDLE FileW; // rax
  __int64 v17; // r15
  signed int v18; // eax
  HANDLE v19; // rax
  HANDLE v20; // rax
  PSID pSid; // [rsp+68h] [rbp-9h] BYREF
  PSID v23[2]; // [rsp+70h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+Fh] BYREF

  v23[1] = (PSID)-2LL;
  v4 = 0;
  pSid = 0;
  v5 = 0;
  v23[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v6 = -1;
  if ( !lpFileName || !a2 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_28;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
LABEL_6:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    v7 = v8;
    goto LABEL_3;
  }
  if ( (unsigned int)GetCurrentUserSID(v23) )
  {
    v11 = pSid;
    v5 = v23[0];
    LengthSid = GetLengthSid(v23[0]);
    v13 = LengthSid + GetLengthSid(v11) + 24;
    ProcessHeap = GetProcessHeap();
    v15 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v13);
    v4 = v15;
    if ( v15 )
    {
      if ( !InitializeAcl(v15, v13, 2u) )
        goto LABEL_6;
      if ( !AddAccessAllowedAce(v4, 2u, 0x10000000u, pSid) )
        goto LABEL_6;
      if ( !AddAccessAllowedAce(v4, 2u, 0x10000000u, v5) )
        goto LABEL_6;
      FileW = CreateFileW(lpFileName, 0xC0040000, 1u, 0, 4u, 0x8200000u, 0);
      v17 = (__int64)FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        goto LABEL_6;
      v18 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 0x80000004, 0, 0, v4, 0);
      v8 = v18;
      if ( v18 )
      {
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
        v6 = v17;
      }
      else
      {
        *a2 = v17;
        v8 = 0;
      }
    }
    else
    {
      v8 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
      v4 = 0;
    }
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    v5 = v23[0];
  }
LABEL_28:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18022e2b4  mov     rax, rsp
0x18022e2b7  push    rbp
0x18022e2b8  push    rsi
0x18022e2b9  push    rdi
0x18022e2ba  push    r12
0x18022e2bc  push    r13
0x18022e2be  push    r14
0x18022e2c0  push    r15
0x18022e2c2  lea     rbp, [rax-5Fh]
0x18022e2c6  sub     rsp, 90h
0x18022e2cd  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18022e2d5  mov     [rax+18h], rbx
0x18022e2d9  mov     rax, cs:__security_cookie
0x18022e2e0  xor     rax, rsp
0x18022e2e3  mov     [rbp+57h+var_40], rax
0x18022e2e7  mov     r12, rdx
0x18022e2ea  mov     r15, rcx
0x18022e2ed  xor     r13d, r13d
0x18022e2f0  mov     ebx, r13d
0x18022e2f3  mov     [rbp+57h+pSid], r13
0x18022e2f7  mov     r14d, r13d
0x18022e2fa  mov     [rbp+57h+var_58], r13
0x18022e2fe  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18022e302  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18022e308  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18022e30c  test    rcx, rcx
0x18022e30f  jnz     short loc_18022E322
0x18022e311  mov     ecx, 80070057h
0x18022e316  mov     esi, ecx
0x18022e318  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18022e31d  jmp     loc_18022E548
0x18022e322  test    r12, r12
0x18022e325  jz      short loc_18022E311
0x18022e327  lea     rax, [rbp+57h+pSid]
0x18022e32b  mov     [rsp+50h], rax; pSid
0x18022e330  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x18022e335  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x18022e33a  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x18022e33f  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x18022e344  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x18022e349  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x18022e34e  mov     r9d, 220h; nSubAuthority1
0x18022e354  mov     r8d, 20h ; ' '; nSubAuthority0
0x18022e35a  mov     dl, 2; nSubAuthorityCount
0x18022e35c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18022e360  call    cs:__imp_AllocateAndInitializeSid
0x18022e367  nop     dword ptr [rax+rax+00h]
0x18022e36c  test    eax, eax
0x18022e36e  jnz     short loc_18022E398
0x18022e370  call    cs:__imp_GetLastError
0x18022e377  nop     dword ptr [rax+rax+00h]
0x18022e37c  mov     esi, eax
0x18022e37e  test    eax, eax
0x18022e380  jnz     short loc_18022E389
0x18022e382  mov     esi, 80004005h
0x18022e387  jmp     short loc_18022E394
0x18022e389  jle     short loc_18022E394
0x18022e38b  movzx   esi, ax
0x18022e38e  or      esi, 80070000h
0x18022e394  mov     ecx, esi
0x18022e396  jmp     short loc_18022E318
0x18022e398  lea     rcx, [rbp+57h+var_58]
0x18022e39c  call    GetCurrentUserSID
0x18022e3a1  test    eax, eax
0x18022e3a3  jnz     short loc_18022E3D9
0x18022e3a5  call    cs:__imp_GetLastError
0x18022e3ac  nop     dword ptr [rax+rax+00h]
0x18022e3b1  mov     esi, eax
0x18022e3b3  test    eax, eax
0x18022e3b5  jnz     short loc_18022E3BE
0x18022e3b7  mov     esi, 80004005h
0x18022e3bc  jmp     short loc_18022E3C9
0x18022e3be  jle     short loc_18022E3C9
0x18022e3c0  movzx   esi, ax
0x18022e3c3  or      esi, 80070000h
0x18022e3c9  mov     ecx, esi
0x18022e3cb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18022e3d0  mov     r14, [rbp+57h+var_58]
0x18022e3d4  jmp     loc_18022E548
0x18022e3d9  mov     rsi, [rbp+57h+pSid]
0x18022e3dd  mov     r14, [rbp+57h+var_58]
0x18022e3e1  mov     rcx, r14; pSid
0x18022e3e4  call    cs:__imp_GetLengthSid
0x18022e3eb  nop     dword ptr [rax+rax+00h]
0x18022e3f0  mov     ebx, eax
0x18022e3f2  mov     rcx, rsi; pSid
0x18022e3f5  call    cs:__imp_GetLengthSid
0x18022e3fc  nop     dword ptr [rax+rax+00h]
0x18022e401  lea     r13d, [rax+18h]
0x18022e405  add     r13d, ebx
0x18022e408  call    cs:__imp_GetProcessHeap
0x18022e40f  nop     dword ptr [rax+rax+00h]
0x18022e414  mov     rcx, rax; hHeap
0x18022e417  mov     r8d, r13d; dwBytes
0x18022e41a  xor     edx, edx; dwFlags
0x18022e41c  call    cs:__imp_HeapAlloc
0x18022e423  nop     dword ptr [rax+rax+00h]
0x18022e428  mov     rbx, rax
0x18022e42b  test    rax, rax
0x18022e42e  jnz     short loc_18022E447
0x18022e430  mov     esi, 8007000Eh
0x18022e435  mov     ecx, esi
0x18022e437  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18022e43c  xor     r13d, r13d
0x18022e43f  mov     ebx, r13d
0x18022e442  jmp     loc_18022E548
0x18022e447  mov     r8d, 2; dwAclRevision
0x18022e44d  mov     edx, r13d; nAclLength
0x18022e450  mov     rcx, rbx; pAcl
0x18022e453  call    cs:__imp_InitializeAcl
0x18022e45a  nop     dword ptr [rax+rax+00h]
0x18022e45f  xor     r13d, r13d
0x18022e462  test    eax, eax
0x18022e464  jz      loc_18022E370
0x18022e46a  mov     r9, [rbp+57h+pSid]; pSid
0x18022e46e  lea     edx, [r13+2]; dwAceRevision
0x18022e472  mov     r8d, 10000000h; AccessMask
0x18022e478  mov     rcx, rbx; pAcl
0x18022e47b  call    cs:__imp_AddAccessAllowedAce
0x18022e482  nop     dword ptr [rax+rax+00h]
0x18022e487  test    eax, eax
0x18022e489  jz      loc_18022E370
0x18022e48f  mov     r9, r14; pSid
0x18022e492  lea     edx, [r13+2]; dwAceRevision
0x18022e496  mov     r8d, 10000000h; AccessMask
0x18022e49c  mov     rcx, rbx; pAcl
0x18022e49f  call    cs:__imp_AddAccessAllowedAce
0x18022e4a6  nop     dword ptr [rax+rax+00h]
0x18022e4ab  test    eax, eax
0x18022e4ad  jz      loc_18022E370
0x18022e4b3  mov     qword ptr [rsp+0C0h+nSubAuthority4], r13; hTemplateFile
0x18022e4b8  mov     [rsp+0C0h+nSubAuthority3], 8200000h; dwFlagsAndAttributes
0x18022e4c0  mov     [rsp+0C0h+nSubAuthority2], 4; dwCreationDisposition
0x18022e4c8  xor     r9d, r9d; lpSecurityAttributes
0x18022e4cb  mov     edx, 0C0040000h; dwDesiredAccess
0x18022e4d0  lea     r8d, [r13+1]; dwShareMode
0x18022e4d4  mov     rcx, r15; lpFileName
0x18022e4d7  call    cs:__imp_CreateFileW
0x18022e4de  nop     dword ptr [rax+rax+00h]
0x18022e4e3  mov     r15, rax
0x18022e4e6  lea     rcx, [rax+1]
0x18022e4ea  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18022e4f1  jz      loc_18022E370
0x18022e4f7  mov     rcx, rax; handle
0x18022e4fa  mov     qword ptr [rsp+0C0h+nSubAuthority4], r13; pSacl
0x18022e4ff  mov     qword ptr [rsp+0C0h+nSubAuthority3], rbx; pDacl
0x18022e504  mov     qword ptr [rsp+0C0h+nSubAuthority2], r13; psidGroup
0x18022e509  xor     r9d, r9d; psidOwner
0x18022e50c  lea     edx, [r13+1]; ObjectType
0x18022e510  mov     r8d, 80000004h; SecurityInfo
0x18022e516  call    cs:__imp_SetSecurityInfo
0x18022e51d  nop     dword ptr [rax+rax+00h]
0x18022e522  mov     esi, eax
0x18022e524  test    eax, eax
0x18022e526  jz      short loc_18022E541
0x18022e528  test    eax, eax
0x18022e52a  jle     short loc_18022E535
0x18022e52c  movzx   esi, si
0x18022e52f  or      esi, 80070000h
0x18022e535  mov     ecx, esi
0x18022e537  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18022e53c  mov     rdi, r15
0x18022e53f  jmp     short loc_18022E548
0x18022e541  mov     [r12], r15
0x18022e545  mov     esi, r13d
0x18022e548  mov     ecx, esi
0x18022e54a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18022e54f  nop
0x18022e550  lea     rax, [rdi-1]
0x18022e554  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18022e558  ja      short loc_18022E56A
0x18022e55a  mov     rcx, rdi; hObject
0x18022e55d  call    cs:__imp_CloseHandle
0x18022e564  nop     dword ptr [rax+rax+00h]
0x18022e569  nop
0x18022e56a  test    r14, r14
0x18022e56d  jz      short loc_18022E590
0x18022e56f  call    cs:__imp_GetProcessHeap
0x18022e576  nop     dword ptr [rax+rax+00h]
0x18022e57b  mov     rcx, rax; hHeap
0x18022e57e  mov     r8, r14; lpMem
0x18022e581  xor     edx, edx; dwFlags
0x18022e583  call    cs:__imp_HeapFree
0x18022e58a  nop     dword ptr [rax+rax+00h]
0x18022e58f  nop
0x18022e590  mov     rcx, [rbp+57h+pSid]; pSid
0x18022e594  test    rcx, rcx
0x18022e597  jz      short loc_18022E5A9
0x18022e599  call    cs:__imp_FreeSid
0x18022e5a0  nop     dword ptr [rax+rax+00h]
0x18022e5a5  mov     [rbp+57h+pSid], r13
0x18022e5a9  test    rbx, rbx
0x18022e5ac  jz      short loc_18022E5CF
0x18022e5ae  call    cs:__imp_GetProcessHeap
0x18022e5b5  nop     dword ptr [rax+rax+00h]
0x18022e5ba  mov     rcx, rax; hHeap
0x18022e5bd  mov     r8, rbx; lpMem
0x18022e5c0  xor     edx, edx; dwFlags
0x18022e5c2  call    cs:__imp_HeapFree
0x18022e5c9  nop     dword ptr [rax+rax+00h]
0x18022e5ce  nop
0x18022e5cf  mov     eax, esi
0x18022e5d1  mov     rcx, [rbp+57h+var_40]
0x18022e5d5  xor     rcx, rsp; StackCookie
0x18022e5d8  call    __security_check_cookie
0x18022e5dd  mov     rbx, [rsp+0C0h+arg_10]
0x18022e5e5  add     rsp, 90h
0x18022e5ec  pop     r15
0x18022e5ee  pop     r14
0x18022e5f0  pop     r13
0x18022e5f2  pop     r12
0x18022e5f4  pop     rdi
0x18022e5f5  pop     rsi
0x18022e5f6  pop     rbp
0x18022e5f7  retn
```
