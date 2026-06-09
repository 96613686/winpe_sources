# CreateWorkingDirectorySecurityDescriptor

- ea: `0x180065100`
- end: `0x1800654c0`
- name: `CreateWorkingDirectorySecurityDescriptor`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c034`

## callees

- `0x180065100`
- `0x180068398`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180065376`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180065376`
- `ADVAPI32!GetAce` at `0x18006527f`
- `ADVAPI32!GetAce` at `0x1800652b8`
- `ADVAPI32!GetAce` at `0x1800652ec`
- `ADVAPI32!GetAce` at `0x18006527f`
- `ADVAPI32!GetAce` at `0x1800652b8`
- `ADVAPI32!GetAce` at `0x1800652ec`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180065342`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180065342`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180065182`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800651c6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180065182`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800651c6`
- `ADVAPI32!FreeSid` at `0x18006546e`
- `ADVAPI32!FreeSid` at `0x180065478`
- `ADVAPI32!FreeSid` at `0x18006546e`
- `ADVAPI32!FreeSid` at `0x180065478`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18006535b`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18006535b`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800653ac`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800653ed`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800653ac`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800653ed`
- `ADVAPI32!AddAccessAllowedAce` at `0x180065268`
- `ADVAPI32!AddAccessAllowedAce` at `0x18006529c`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800652d5`
- `ADVAPI32!AddAccessAllowedAce` at `0x180065268`
- `ADVAPI32!AddAccessAllowedAce` at `0x18006529c`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800652d5`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180065390`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180065390`
- `ADVAPI32!GetLengthSid` at `0x1800651ec`
- `ADVAPI32!GetLengthSid` at `0x1800651f9`
- `ADVAPI32!GetLengthSid` at `0x180065206`
- `ADVAPI32!GetLengthSid` at `0x1800651ec`
- `ADVAPI32!GetLengthSid` at `0x1800651f9`
- `ADVAPI32!GetLengthSid` at `0x180065206`
- `ADVAPI32!InitializeAcl` at `0x18006524b`
- `ADVAPI32!InitializeAcl` at `0x18006524b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180065329`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180065329`
- `KERNEL32!SetLastError` at `0x18006548a`
- `KERNEL32!SetLastError` at `0x18006548a`
- `KERNEL32!GetLastError` at `0x1800653b6`
- `KERNEL32!GetLastError` at `0x1800653fd`
- `KERNEL32!GetLastError` at `0x180065422`
- `KERNEL32!GetLastError` at `0x180065433`
- `KERNEL32!GetLastError` at `0x180065480`
- `KERNEL32!GetLastError` at `0x1800653b6`
- `KERNEL32!GetLastError` at `0x1800653fd`
- `KERNEL32!GetLastError` at `0x180065422`
- `KERNEL32!GetLastError` at `0x180065433`
- `KERNEL32!GetLastError` at `0x180065480`
- `KERNEL32!HeapFree` at `0x180065413`
- `KERNEL32!HeapFree` at `0x180065449`
- `KERNEL32!HeapFree` at `0x180065464`
- `KERNEL32!HeapFree` at `0x180065413`
- `KERNEL32!HeapFree` at `0x180065449`
- `KERNEL32!HeapFree` at `0x180065464`
- `KERNEL32!HeapAlloc` at `0x180065220`
- `KERNEL32!HeapAlloc` at `0x1800653d4`
- `KERNEL32!HeapAlloc` at `0x180065220`
- `KERNEL32!HeapAlloc` at `0x1800653d4`
- `KERNEL32!GetProcessHeap` at `0x180065211`
- `KERNEL32!GetProcessHeap` at `0x1800653c4`
- `KERNEL32!GetProcessHeap` at `0x180065405`
- `KERNEL32!GetProcessHeap` at `0x18006543b`
- `KERNEL32!GetProcessHeap` at `0x180065455`
- `KERNEL32!GetProcessHeap` at `0x180065211`
- `KERNEL32!GetProcessHeap` at `0x1800653c4`
- `KERNEL32!GetProcessHeap` at `0x180065405`
- `KERNEL32!GetProcessHeap` at `0x18006543b`
- `KERNEL32!GetProcessHeap` at `0x180065455`

## pseudocode

```c
_BOOL8 __fastcall CreateWorkingDirectorySecurityDescriptor(_QWORD *a1)
{
  DWORD LastError; // edi
  DWORD LengthSid; // r15d
  DWORD v4; // r15d
  DWORD v5; // r15d
  HANDLE ProcessHeap; // rax
  struct _ACL *v7; // rax
  struct _ACL *v8; // rsi
  DWORD v9; // ebx
  HANDLE v10; // rax
  void *v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  DWORD dwBufferLength; // [rsp+60h] [rbp-39h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-31h] BYREF
  PSID lpMem; // [rsp+70h] [rbp-29h] BYREF
  PSID pSid; // [rsp+78h] [rbp-21h] BYREF
  LPVOID pAce; // [rsp+80h] [rbp-19h] BYREF
  LPVOID v22; // [rsp+88h] [rbp-11h] BYREF
  LPVOID v23; // [rsp+90h] [rbp-9h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-1h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pOwner = 0;
  pSid = 0;
  lpMem = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &pSid)
    && (unsigned int)GetCurrentUserSID(&lpMem) )
  {
    LastError = 0;
    LengthSid = GetLengthSid(lpMem);
    v4 = GetLengthSid(pSid) + LengthSid;
    v5 = GetLengthSid(pOwner) + 32 + v4;
    ProcessHeap = GetProcessHeap();
    v7 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v5);
    v8 = v7;
    if ( v7 )
    {
      pAce = 0;
      v22 = 0;
      v23 = 0;
      if ( InitializeAcl(v7, v5, 2u)
        && AddAccessAllowedAce(v8, 2u, 0x10000000u, pOwner)
        && GetAce(v8, 0, &pAce)
        && AddAccessAllowedAce(v8, 2u, 0xA0000000, pSid)
        && GetAce(v8, 1u, &v22)
        && AddAccessAllowedAce(v8, 2u, 0xA0000000, lpMem)
        && GetAce(v8, 2u, &v23)
        && (v25 = 0,
            memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor)),
            *((_BYTE *)pAce + 1) |= 3u,
            *((_BYTE *)v22 + 1) |= 3u,
            *((_BYTE *)v23 + 1) |= 3u,
            InitializeSecurityDescriptor(pSecurityDescriptor, 1u))
        && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v8, 0)
        && SetSecurityDescriptorControl(pSecurityDescriptor, 0x3000u, 0x3000u) )
      {
        dwBufferLength = 0;
        if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength) || GetLastError() != 122 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
        else
        {
          v9 = dwBufferLength;
          v10 = GetProcessHeap();
          v11 = HeapAlloc(v10, 8u, v9);
          v12 = v11;
          if ( v11 )
          {
            if ( MakeSelfRelativeSD(pSecurityDescriptor, v11, &dwBufferLength) )
            {
              *a1 = v12;
            }
            else
            {
              LastError = GetLastError();
              v13 = GetProcessHeap();
              HeapFree(v13, 0, v12);
            }
          }
          else
          {
            LastError = 14;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v8);
    }
    if ( lpMem )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, lpMem);
    }
    FreeSid(pSid);
    FreeSid(pOwner);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180065100  mov     [rsp-8+arg_8], rbx
0x180065105  mov     [rsp-8+arg_10], rsi
0x18006510a  push    rbp
0x18006510b  push    rdi
0x18006510c  push    r12
0x18006510e  push    r13
0x180065110  push    r15
0x180065112  lea     rbp, [rsp-37h]
0x180065117  sub     rsp, 0D0h
0x18006511e  mov     rax, cs:__security_cookie
0x180065125  xor     rax, rsp
0x180065128  mov     [rbp+57h+var_28], rax
0x18006512c  xor     r13d, r13d
0x18006512f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180065135  lea     rax, [rbp+57h+pOwner]
0x180065139  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18006513d  mov     [rsp+0F0h+pSid], rax; pSid
0x180065142  mov     r12, rcx
0x180065145  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x18006514a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18006514e  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x180065153  lea     ebx, [r13+20h]
0x180065157  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x18006515c  mov     r8d, ebx; nSubAuthority0
0x18006515f  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x180065164  mov     r9d, 220h; nSubAuthority1
0x18006516a  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x18006516f  mov     dl, 2; nSubAuthorityCount
0x180065171  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x180065176  mov     [rbp+57h+pOwner], r13
0x18006517a  mov     [rbp+57h+var_78], r13
0x18006517e  mov     [rbp+57h+lpMem], r13
0x180065182  call    cs:__imp_AllocateAndInitializeSid
0x180065188  test    eax, eax
0x18006518a  jz      loc_180065480
0x180065190  lea     rax, [rbp+57h+var_78]
0x180065194  mov     r9d, 221h; nSubAuthority1
0x18006519a  mov     [rsp+0F0h+pSid], rax; pSid
0x18006519f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800651a3  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800651a8  mov     r8d, ebx; nSubAuthority0
0x1800651ab  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800651b0  mov     dl, 2; nSubAuthorityCount
0x1800651b2  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800651b7  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800651bc  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800651c1  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800651c6  call    cs:__imp_AllocateAndInitializeSid
0x1800651cc  test    eax, eax
0x1800651ce  jz      loc_180065480
0x1800651d4  lea     rcx, [rbp+57h+lpMem]
0x1800651d8  call    GetCurrentUserSID
0x1800651dd  test    eax, eax
0x1800651df  jz      loc_180065480
0x1800651e5  mov     rcx, [rbp+57h+lpMem]; pSid
0x1800651e9  mov     edi, r13d
0x1800651ec  call    cs:__imp_GetLengthSid
0x1800651f2  mov     rcx, [rbp+57h+var_78]; pSid
0x1800651f6  mov     r15d, eax
0x1800651f9  call    cs:__imp_GetLengthSid
0x1800651ff  mov     rcx, [rbp+57h+pOwner]; pSid
0x180065203  add     r15d, eax
0x180065206  call    cs:__imp_GetLengthSid
0x18006520c  add     eax, ebx
0x18006520e  add     r15d, eax
0x180065211  call    cs:__imp_GetProcessHeap
0x180065217  mov     r8d, r15d; dwBytes
0x18006521a  lea     edx, [rbx-18h]; dwFlags
0x18006521d  mov     rcx, rax; hHeap
0x180065220  call    cs:__imp_HeapAlloc
0x180065226  mov     rsi, rax
0x180065229  test    rax, rax
0x18006522c  jz      loc_18006544F
0x180065232  lea     ebx, [r13+2]
0x180065236  mov     [rbp+57h+pAce], r13
0x18006523a  mov     r8d, ebx; dwAclRevision
0x18006523d  mov     [rbp+57h+var_68], r13
0x180065241  mov     edx, r15d; nAclLength
0x180065244  mov     [rbp+57h+var_60], r13
0x180065248  mov     rcx, rax; pAcl
0x18006524b  call    cs:__imp_InitializeAcl
0x180065251  test    eax, eax
0x180065253  jz      loc_180065433
0x180065259  mov     r9, [rbp+57h+pOwner]; pSid
0x18006525d  mov     r8d, 10000000h; AccessMask
0x180065263  mov     edx, ebx; dwAceRevision
0x180065265  mov     rcx, rsi; pAcl
0x180065268  call    cs:__imp_AddAccessAllowedAce
0x18006526e  test    eax, eax
0x180065270  jz      loc_180065433
0x180065276  lea     r8, [rbp+57h+pAce]; pAce
0x18006527a  xor     edx, edx; dwAceIndex
0x18006527c  mov     rcx, rsi; pAcl
0x18006527f  call    cs:__imp_GetAce
0x180065285  test    eax, eax
0x180065287  jz      loc_180065433
0x18006528d  mov     r9, [rbp+57h+var_78]; pSid
0x180065291  mov     r8d, 0A0000000h; AccessMask
0x180065297  mov     edx, ebx; dwAceRevision
0x180065299  mov     rcx, rsi; pAcl
0x18006529c  call    cs:__imp_AddAccessAllowedAce
0x1800652a2  test    eax, eax
0x1800652a4  jz      loc_180065433
0x1800652aa  lea     r15d, [r13+1]
0x1800652ae  mov     rcx, rsi; pAcl
0x1800652b1  mov     edx, r15d; dwAceIndex
0x1800652b4  lea     r8, [rbp+57h+var_68]; pAce
0x1800652b8  call    cs:__imp_GetAce
0x1800652be  test    eax, eax
0x1800652c0  jz      loc_180065433
0x1800652c6  mov     r9, [rbp+57h+lpMem]; pSid
0x1800652ca  mov     r8d, 0A0000000h; AccessMask
0x1800652d0  mov     edx, ebx; dwAceRevision
0x1800652d2  mov     rcx, rsi; pAcl
0x1800652d5  call    cs:__imp_AddAccessAllowedAce
0x1800652db  test    eax, eax
0x1800652dd  jz      loc_180065433
0x1800652e3  lea     r8, [rbp+57h+var_60]; pAce
0x1800652e7  mov     edx, ebx; dwAceIndex
0x1800652e9  mov     rcx, rsi; pAcl
0x1800652ec  call    cs:__imp_GetAce
0x1800652f2  test    eax, eax
0x1800652f4  jz      loc_180065433
0x1800652fa  xor     eax, eax
0x1800652fc  mov     cl, 3
0x1800652fe  mov     [rbp+57h+var_38], rax
0x180065302  xorps   xmm0, xmm0
0x180065305  mov     rax, [rbp+57h+pAce]
0x180065309  mov     edx, r15d; dwRevision
0x18006530c  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180065310  movups  [rbp+57h+var_48], xmm0
0x180065314  or      [rax+1], cl
0x180065317  mov     rax, [rbp+57h+var_68]
0x18006531b  or      [rax+1], cl
0x18006531e  mov     rax, [rbp+57h+var_60]
0x180065322  or      [rax+1], cl
0x180065325  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180065329  call    cs:__imp_InitializeSecurityDescriptor
0x18006532f  test    eax, eax
0x180065331  jz      loc_180065433
0x180065337  mov     rdx, [rbp+57h+pOwner]; pOwner
0x18006533b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18006533f  xor     r8d, r8d; bOwnerDefaulted
0x180065342  call    cs:__imp_SetSecurityDescriptorOwner
0x180065348  test    eax, eax
0x18006534a  jz      loc_180065433
0x180065350  mov     rdx, [rbp+57h+pOwner]; pGroup
0x180065354  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180065358  xor     r8d, r8d; bGroupDefaulted
0x18006535b  call    cs:__imp_SetSecurityDescriptorGroup
0x180065361  test    eax, eax
0x180065363  jz      loc_180065433
0x180065369  xor     r9d, r9d; bDaclDefaulted
0x18006536c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180065370  mov     r8, rsi; pDacl
0x180065373  mov     edx, r15d; bDaclPresent
0x180065376  call    cs:__imp_SetSecurityDescriptorDacl
0x18006537c  test    eax, eax
0x18006537e  jz      loc_180065433
0x180065384  mov     edx, 3000h; ControlBitsOfInterest
0x180065389  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18006538d  mov     r8d, edx; ControlBitsToSet
0x180065390  call    cs:__imp_SetSecurityDescriptorControl
0x180065396  test    eax, eax
0x180065398  jz      loc_180065433
0x18006539e  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800653a2  mov     [rbp+57h+dwBufferLength], r13d
0x1800653a6  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800653a8  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800653ac  call    cs:__imp_MakeSelfRelativeSD
0x1800653b2  test    eax, eax
0x1800653b4  jnz     short loc_180065422
0x1800653b6  call    cs:__imp_GetLastError
0x1800653bc  cmp     eax, 7Ah ; 'z'
0x1800653bf  jnz     short loc_180065422
0x1800653c1  mov     ebx, [rbp+57h+dwBufferLength]
0x1800653c4  call    cs:__imp_GetProcessHeap
0x1800653ca  mov     r8d, ebx; dwBytes
0x1800653cd  lea     edx, [r13+8]; dwFlags
0x1800653d1  mov     rcx, rax; hHeap
0x1800653d4  call    cs:__imp_HeapAlloc
0x1800653da  mov     rbx, rax
0x1800653dd  test    rax, rax
0x1800653e0  jz      short loc_18006541B
0x1800653e2  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800653e6  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800653e9  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800653ed  call    cs:__imp_MakeSelfRelativeSD
0x1800653f3  test    eax, eax
0x1800653f5  jz      short loc_1800653FD
0x1800653f7  mov     [r12], rbx
0x1800653fb  jmp     short loc_18006543B
0x1800653fd  call    cs:__imp_GetLastError
0x180065403  mov     edi, eax
0x180065405  call    cs:__imp_GetProcessHeap
0x18006540b  mov     r8, rbx; lpMem
0x18006540e  xor     edx, edx; dwFlags
0x180065410  mov     rcx, rax; hHeap
0x180065413  call    cs:__imp_HeapFree
0x180065419  jmp     short loc_18006543B
0x18006541b  mov     edi, 0Eh
0x180065420  jmp     short loc_18006543B
0x180065422  call    cs:__imp_GetLastError
0x180065428  mov     edi, eax
0x18006542a  test    eax, eax
0x18006542c  jnz     short loc_18006543B
0x18006542e  lea     edi, [rax+1Fh]
0x180065431  jmp     short loc_18006543B
0x180065433  call    cs:__imp_GetLastError
0x180065439  mov     edi, eax
0x18006543b  call    cs:__imp_GetProcessHeap
0x180065441  mov     r8, rsi; lpMem
0x180065444  xor     edx, edx; dwFlags
0x180065446  mov     rcx, rax; hHeap
0x180065449  call    cs:__imp_HeapFree
0x18006544f  cmp     [rbp+57h+lpMem], r13
0x180065453  jz      short loc_18006546A
0x180065455  call    cs:__imp_GetProcessHeap
0x18006545b  mov     r8, [rbp+57h+lpMem]; lpMem
0x18006545f  xor     edx, edx; dwFlags
0x180065461  mov     rcx, rax; hHeap
0x180065464  call    cs:__imp_HeapFree
0x18006546a  mov     rcx, [rbp+57h+var_78]; pSid
0x18006546e  call    cs:__imp_FreeSid
0x180065474  mov     rcx, [rbp+57h+pOwner]; pSid
0x180065478  call    cs:__imp_FreeSid
0x18006547e  jmp     short loc_180065488
0x180065480  call    cs:__imp_GetLastError
0x180065486  mov     edi, eax
0x180065488  mov     ecx, edi; dwErrCode
0x18006548a  call    cs:__imp_SetLastError
0x180065490  test    edi, edi
0x180065492  mov     eax, r13d
0x180065495  setz    al
0x180065498  mov     rcx, [rbp+57h+var_28]
0x18006549c  xor     rcx, rsp; StackCookie
0x18006549f  call    __security_check_cookie
0x1800654a4  lea     r11, [rsp+0F0h+var_20]
0x1800654ac  mov     rbx, [r11+38h]
0x1800654b0  mov     rsi, [r11+40h]
0x1800654b4  mov     rsp, r11
0x1800654b7  pop     r15
0x1800654b9  pop     r13
0x1800654bb  pop     r12
0x1800654bd  pop     rdi
0x1800654be  pop     rbp
0x1800654bf  retn
```
