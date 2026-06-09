# CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(ushort const *,int,void * *,int *)

- ea: `0x14000a21c`
- end: `0x14000a55d`
- name: `?CreateMutexWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGHPEAPEAXPEAH@Z`
- size: `833`
- prototype: `__int64 __fastcall(LPCWSTR lpName, __int64, _QWORD *, BOOL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x1400076c8`
- `0x14000a21c`
- `0x1400135b8`
- `0x140023ac4`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x14000a3d2`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000a3f5`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000a3d2`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000a3f5`
- `ADVAPI32!GetLengthSid` at `0x14000a349`
- `ADVAPI32!GetLengthSid` at `0x14000a35a`
- `ADVAPI32!GetLengthSid` at `0x14000a349`
- `ADVAPI32!GetLengthSid` at `0x14000a35a`
- `ADVAPI32!InitializeAcl` at `0x14000a3ac`
- `ADVAPI32!InitializeAcl` at `0x14000a3ac`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000a410`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000a410`
- `ADVAPI32!FreeSid` at `0x14000a4fe`
- `ADVAPI32!FreeSid` at `0x14000a4fe`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000a2dc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000a2dc`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000a431`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000a431`
- `KERNEL32!HeapFree` at `0x14000a4e8`
- `KERNEL32!HeapFree` at `0x14000a527`
- `KERNEL32!HeapFree` at `0x14000a4e8`
- `KERNEL32!HeapFree` at `0x14000a527`
- `KERNEL32!HeapAlloc` at `0x14000a37f`
- `KERNEL32!HeapAlloc` at `0x14000a37f`
- `KERNEL32!GetProcessHeap` at `0x14000a36b`
- `KERNEL32!GetProcessHeap` at `0x14000a4d4`
- `KERNEL32!GetProcessHeap` at `0x14000a513`
- `KERNEL32!GetProcessHeap` at `0x14000a36b`
- `KERNEL32!GetProcessHeap` at `0x14000a4d4`
- `KERNEL32!GetProcessHeap` at `0x14000a513`
- `KERNEL32!GetLastError` at `0x14000a2ec`
- `KERNEL32!GetLastError` at `0x14000a30a`
- `KERNEL32!GetLastError` at `0x14000a474`
- `KERNEL32!GetLastError` at `0x14000a49a`
- `KERNEL32!GetLastError` at `0x14000a2ec`
- `KERNEL32!GetLastError` at `0x14000a30a`
- `KERNEL32!GetLastError` at `0x14000a474`
- `KERNEL32!GetLastError` at `0x14000a49a`
- `KERNEL32!CreateMutexW` at `0x14000a460`
- `KERNEL32!CreateMutexW` at `0x14000a460`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(LPCWSTR lpName, __int64 a2, _QWORD *a3, BOOL *a4)
{
  struct _ACL *v7; // rbx
  PSID v8; // r14
  unsigned int v9; // esi
  int v10; // ecx
  signed int v11; // eax
  PSID v12; // rdi
  DWORD LengthSid; // ebx
  DWORD v14; // edi
  HANDLE ProcessHeap; // rax
  struct _ACL *v16; // rax
  HANDLE v17; // rdi
  BOOL v18; // ecx
  signed int LastError; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  PSID pSid; // [rsp+68h] [rbp-59h] BYREF
  PSID lpMem; // [rsp+70h] [rbp-51h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+78h] [rbp-49h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-11h]
  __int64 v28; // [rsp+B8h] [rbp-9h]
  __int64 v29; // [rsp+C0h] [rbp-1h]
  __int64 v30; // [rsp+C8h] [rbp+7h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+Fh] BYREF

  v28 = -2;
  v7 = 0;
  v29 = 0;
  pSid = 0;
  v8 = 0;
  lpMem = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v27 = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  v30 = 0;
  v9 = 0;
  if ( !lpName || !a3 )
  {
    v10 = -2147024809;
    v9 = -2147024809;
LABEL_27:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_28;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_22;
  if ( (unsigned int)GetCurrentUserSID(&lpMem) )
  {
    v12 = pSid;
    v8 = lpMem;
    LengthSid = GetLengthSid(lpMem);
    v14 = LengthSid + GetLengthSid(v12) + 24;
    ProcessHeap = GetProcessHeap();
    v16 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v14);
    v7 = v16;
    if ( !v16 )
    {
      v7 = 0;
      v9 = -2147024882;
LABEL_26:
      v10 = v9;
      goto LABEL_27;
    }
    if ( !InitializeAcl(v16, v14, 2u)
      || !AddAccessAllowedAce(v7, 2u, 0x10000000u, pSid)
      || !AddAccessAllowedAce(v7, 2u, 0x10000000u, v8)
      || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v7, 0)
      || (MutexAttributes.nLength = 24,
          MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor,
          MutexAttributes.bInheritHandle = 0,
          (v17 = CreateMutexW(&MutexAttributes, 0, lpName)) == 0) )
    {
LABEL_22:
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      goto LABEL_26;
    }
    v18 = GetLastError() == 183;
    *a3 = v17;
    if ( a4 )
      *a4 = v18;
  }
  else
  {
    v11 = GetLastError();
    v9 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    v8 = lpMem;
  }
LABEL_28:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v8 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v8);
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v7 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v7);
  }
  return v9;
}

```

## disassembly

```asm
0x14000a21c  mov     rax, rsp
0x14000a21f  push    rbp
0x14000a220  push    rsi
0x14000a221  push    rdi
0x14000a222  push    r12
0x14000a224  push    r13
0x14000a226  push    r14
0x14000a228  push    r15
0x14000a22a  lea     rbp, [rax-5Fh]
0x14000a22e  sub     rsp, 0E0h
0x14000a235  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x14000a23d  mov     [rax+10h], rbx
0x14000a241  mov     rax, cs:__security_cookie
0x14000a248  xor     rax, rsp
0x14000a24b  mov     [rbp+57h+var_40], rax
0x14000a24f  mov     r15, r9
0x14000a252  mov     r12, r8
0x14000a255  mov     r13, rcx
0x14000a258  xor     edi, edi
0x14000a25a  mov     ebx, edi
0x14000a25c  mov     [rbp+57h+var_58], rbx
0x14000a260  mov     [rbp+57h+pSid], rdi
0x14000a264  mov     r14d, edi
0x14000a267  mov     [rbp+57h+lpMem], rdi
0x14000a26b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14000a26e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14000a274  xorps   xmm0, xmm0
0x14000a277  xor     eax, eax
0x14000a279  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x14000a27d  movups  [rbp+57h+var_78], xmm0
0x14000a281  mov     [rbp+57h+var_68], rax
0x14000a285  movups  xmmword ptr [rbp+57h+MutexAttributes.nLength], xmm0
0x14000a289  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], rax
0x14000a28d  mov     [rbp+57h+var_50], rdi
0x14000a291  mov     esi, edi
0x14000a293  test    rcx, rcx
0x14000a296  jnz     short loc_14000A2A4
0x14000a298  mov     ecx, 80070057h
0x14000a29d  mov     esi, ecx
0x14000a29f  jmp     loc_14000A4C2
0x14000a2a4  test    r12, r12
0x14000a2a7  jz      short loc_14000A298
0x14000a2a9  lea     rax, [rbp+57h+pSid]
0x14000a2ad  mov     [rsp+50h], rax; pSid
0x14000a2b2  mov     [rsp+110h+nSubAuthority7], edi; nSubAuthority7
0x14000a2b6  mov     [rsp+110h+nSubAuthority6], edi; nSubAuthority6
0x14000a2ba  mov     [rsp+110h+nSubAuthority5], edi; nSubAuthority5
0x14000a2be  mov     [rsp+110h+nSubAuthority4], edi; nSubAuthority4
0x14000a2c2  mov     [rsp+110h+nSubAuthority3], edi; nSubAuthority3
0x14000a2c6  mov     [rsp+110h+nSubAuthority2], edi; nSubAuthority2
0x14000a2ca  mov     r9d, 220h; nSubAuthority1
0x14000a2d0  mov     r8d, 20h ; ' '; nSubAuthority0
0x14000a2d6  mov     dl, 2; nSubAuthorityCount
0x14000a2d8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000a2dc  call    cs:__imp_AllocateAndInitializeSid
0x14000a2e3  nop     dword ptr [rax+rax+00h]
0x14000a2e8  test    eax, eax
0x14000a2ea  jnz     short loc_14000A2FD
0x14000a2ec  call    cs:__imp_GetLastError
0x14000a2f3  nop     dword ptr [rax+rax+00h]
0x14000a2f8  jmp     loc_14000A4A8
0x14000a2fd  lea     rcx, [rbp+57h+lpMem]
0x14000a301  call    GetCurrentUserSID
0x14000a306  test    eax, eax
0x14000a308  jnz     short loc_14000A33E
0x14000a30a  call    cs:__imp_GetLastError
0x14000a311  nop     dword ptr [rax+rax+00h]
0x14000a316  mov     esi, eax
0x14000a318  test    eax, eax
0x14000a31a  jnz     short loc_14000A323
0x14000a31c  mov     esi, 80004005h
0x14000a321  jmp     short loc_14000A32E
0x14000a323  jle     short loc_14000A32E
0x14000a325  movzx   esi, ax
0x14000a328  or      esi, 80070000h
0x14000a32e  mov     ecx, esi
0x14000a330  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a335  mov     r14, [rbp+57h+lpMem]
0x14000a339  jmp     loc_14000A4C7
0x14000a33e  mov     rdi, [rbp+57h+pSid]
0x14000a342  mov     r14, [rbp+57h+lpMem]
0x14000a346  mov     rcx, r14; pSid
0x14000a349  call    cs:__imp_GetLengthSid
0x14000a350  nop     dword ptr [rax+rax+00h]
0x14000a355  mov     ebx, eax
0x14000a357  mov     rcx, rdi; pSid
0x14000a35a  call    cs:__imp_GetLengthSid
0x14000a361  nop     dword ptr [rax+rax+00h]
0x14000a366  lea     edi, [rax+18h]
0x14000a369  add     edi, ebx
0x14000a36b  call    cs:__imp_GetProcessHeap
0x14000a372  nop     dword ptr [rax+rax+00h]
0x14000a377  mov     rcx, rax; hHeap
0x14000a37a  mov     r8d, edi; dwBytes
0x14000a37d  xor     edx, edx; dwFlags
0x14000a37f  call    cs:__imp_HeapAlloc
0x14000a386  nop     dword ptr [rax+rax+00h]
0x14000a38b  mov     rbx, rax
0x14000a38e  test    rax, rax
0x14000a391  jnz     short loc_14000A3A1
0x14000a393  xor     edi, edi
0x14000a395  mov     ebx, edi
0x14000a397  mov     esi, 8007000Eh
0x14000a39c  jmp     loc_14000A4C0
0x14000a3a1  mov     r8d, 2; dwAclRevision
0x14000a3a7  mov     edx, edi; nAclLength
0x14000a3a9  mov     rcx, rbx; pAcl
0x14000a3ac  call    cs:__imp_InitializeAcl
0x14000a3b3  nop     dword ptr [rax+rax+00h]
0x14000a3b8  xor     edi, edi
0x14000a3ba  test    eax, eax
0x14000a3bc  jz      loc_14000A2EC
0x14000a3c2  mov     r9, [rbp+57h+pSid]; pSid
0x14000a3c6  lea     edx, [rdi+2]; dwAceRevision
0x14000a3c9  mov     r8d, 10000000h; AccessMask
0x14000a3cf  mov     rcx, rbx; pAcl
0x14000a3d2  call    cs:__imp_AddAccessAllowedAce
0x14000a3d9  nop     dword ptr [rax+rax+00h]
0x14000a3de  test    eax, eax
0x14000a3e0  jz      loc_14000A2EC
0x14000a3e6  mov     r9, r14; pSid
0x14000a3e9  lea     edx, [rdi+2]; dwAceRevision
0x14000a3ec  mov     r8d, 10000000h; AccessMask
0x14000a3f2  mov     rcx, rbx; pAcl
0x14000a3f5  call    cs:__imp_AddAccessAllowedAce
0x14000a3fc  nop     dword ptr [rax+rax+00h]
0x14000a401  test    eax, eax
0x14000a403  jz      loc_14000A2EC
0x14000a409  lea     edx, [rdi+1]; dwRevision
0x14000a40c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14000a410  call    cs:__imp_InitializeSecurityDescriptor
0x14000a417  nop     dword ptr [rax+rax+00h]
0x14000a41c  test    eax, eax
0x14000a41e  jz      loc_14000A2EC
0x14000a424  xor     r9d, r9d; bDaclDefaulted
0x14000a427  mov     r8, rbx; pDacl
0x14000a42a  lea     edx, [rdi+1]; bDaclPresent
0x14000a42d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14000a431  call    cs:__imp_SetSecurityDescriptorDacl
0x14000a438  nop     dword ptr [rax+rax+00h]
0x14000a43d  test    eax, eax
0x14000a43f  jz      loc_14000A2EC
0x14000a445  mov     [rbp+57h+MutexAttributes.nLength], 18h
0x14000a44c  lea     rax, [rbp+57h+pSecurityDescriptor]
0x14000a450  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x14000a454  mov     [rbp+57h+MutexAttributes.bInheritHandle], edi
0x14000a457  mov     r8, r13; lpName
0x14000a45a  xor     edx, edx; bInitialOwner
0x14000a45c  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x14000a460  call    cs:__imp_CreateMutexW
0x14000a467  nop     dword ptr [rax+rax+00h]
0x14000a46c  mov     rdi, rax
0x14000a46f  test    rax, rax
0x14000a472  jz      short loc_14000A49A
0x14000a474  call    cs:__imp_GetLastError
0x14000a47b  nop     dword ptr [rax+rax+00h]
0x14000a480  xor     ecx, ecx
0x14000a482  cmp     eax, 0B7h
0x14000a487  setz    cl
0x14000a48a  mov     [r12], rdi
0x14000a48e  xor     edi, edi
0x14000a490  test    r15, r15
0x14000a493  jz      short loc_14000A4C7
0x14000a495  mov     [r15], ecx
0x14000a498  jmp     short loc_14000A4C7
0x14000a49a  call    cs:__imp_GetLastError
0x14000a4a1  nop     dword ptr [rax+rax+00h]
0x14000a4a6  xor     edi, edi
0x14000a4a8  mov     esi, eax
0x14000a4aa  test    eax, eax
0x14000a4ac  jnz     short loc_14000A4B5
0x14000a4ae  mov     esi, 80004005h
0x14000a4b3  jmp     short loc_14000A4C0
0x14000a4b5  jle     short loc_14000A4C0
0x14000a4b7  movzx   esi, ax
0x14000a4ba  or      esi, 80070000h
0x14000a4c0  mov     ecx, esi
0x14000a4c2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a4c7  mov     ecx, esi
0x14000a4c9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000a4ce  nop
0x14000a4cf  test    r14, r14
0x14000a4d2  jz      short loc_14000A4F5
0x14000a4d4  call    cs:__imp_GetProcessHeap
0x14000a4db  nop     dword ptr [rax+rax+00h]
0x14000a4e0  mov     rcx, rax; hHeap
0x14000a4e3  mov     r8, r14; lpMem
0x14000a4e6  xor     edx, edx; dwFlags
0x14000a4e8  call    cs:__imp_HeapFree
0x14000a4ef  nop     dword ptr [rax+rax+00h]
0x14000a4f4  nop
0x14000a4f5  mov     rcx, [rbp+57h+pSid]; pSid
0x14000a4f9  test    rcx, rcx
0x14000a4fc  jz      short loc_14000A50E
0x14000a4fe  call    cs:__imp_FreeSid
0x14000a505  nop     dword ptr [rax+rax+00h]
0x14000a50a  mov     [rbp+57h+pSid], rdi
0x14000a50e  test    rbx, rbx
0x14000a511  jz      short loc_14000A533
0x14000a513  call    cs:__imp_GetProcessHeap
0x14000a51a  nop     dword ptr [rax+rax+00h]
0x14000a51f  mov     rcx, rax; hHeap
0x14000a522  mov     r8, rbx; lpMem
0x14000a525  xor     edx, edx; dwFlags
0x14000a527  call    cs:__imp_HeapFree
0x14000a52e  nop     dword ptr [rax+rax+00h]
0x14000a533  mov     eax, esi
0x14000a535  mov     rcx, [rbp+57h+var_40]
0x14000a539  xor     rcx, rsp; StackCookie
0x14000a53c  call    __security_check_cookie
0x14000a541  mov     rbx, [rsp+110h+arg_8]
0x14000a549  add     rsp, 0E0h
0x14000a550  pop     r15
0x14000a552  pop     r14
0x14000a554  pop     r13
0x14000a556  pop     r12
0x14000a558  pop     rdi
0x14000a559  pop     rsi
0x14000a55a  pop     rbp
0x14000a55b  retn
```
