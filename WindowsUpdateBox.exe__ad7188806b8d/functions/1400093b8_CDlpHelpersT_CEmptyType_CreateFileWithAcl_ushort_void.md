# CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)

- ea: `0x1400093b8`
- end: `0x1400096f9`
- name: `?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z`
- size: `833`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001c624`
- `0x140041ad0`

## callees

- `0x1400076c8`
- `0x1400093b8`
- `0x1400135b8`
- `0x140023ac4`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x140009577`
- `ADVAPI32!AddAccessAllowedAce` at `0x140009599`
- `ADVAPI32!AddAccessAllowedAce` at `0x140009577`
- `ADVAPI32!AddAccessAllowedAce` at `0x140009599`
- `ADVAPI32!GetLengthSid` at `0x1400094ed`
- `ADVAPI32!GetLengthSid` at `0x1400094fe`
- `ADVAPI32!GetLengthSid` at `0x1400094ed`
- `ADVAPI32!GetLengthSid` at `0x1400094fe`
- `ADVAPI32!SetSecurityInfo` at `0x140009614`
- `ADVAPI32!SetSecurityInfo` at `0x140009614`
- `ADVAPI32!InitializeAcl` at `0x14000954f`
- `ADVAPI32!InitializeAcl` at `0x14000954f`
- `ADVAPI32!FreeSid` at `0x14000969a`
- `ADVAPI32!FreeSid` at `0x14000969a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140009467`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140009467`
- `KERNEL32!CloseHandle` at `0x14000965e`
- `KERNEL32!CloseHandle` at `0x14000965e`
- `KERNEL32!HeapFree` at `0x140009684`
- `KERNEL32!HeapFree` at `0x1400096c3`
- `KERNEL32!HeapFree` at `0x140009684`
- `KERNEL32!HeapFree` at `0x1400096c3`
- `KERNEL32!HeapAlloc` at `0x140009523`
- `KERNEL32!HeapAlloc` at `0x140009523`
- `KERNEL32!GetProcessHeap` at `0x14000950f`
- `KERNEL32!GetProcessHeap` at `0x140009670`
- `KERNEL32!GetProcessHeap` at `0x1400096af`
- `KERNEL32!GetProcessHeap` at `0x14000950f`
- `KERNEL32!GetProcessHeap` at `0x140009670`
- `KERNEL32!GetProcessHeap` at `0x1400096af`
- `KERNEL32!GetLastError` at `0x140009477`
- `KERNEL32!GetLastError` at `0x1400094ae`
- `KERNEL32!GetLastError` at `0x140009477`
- `KERNEL32!GetLastError` at `0x1400094ae`
- `KERNEL32!CreateFileW` at `0x1400095d4`
- `KERNEL32!CreateFileW` at `0x1400095d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateFileWithAcl(LPCWSTR lpFileName, __int64 *a2)
{
  struct _ACL *v4; // rdi
  PSID v5; // r14
  __int64 FileW; // rbx
  __int64 v7; // rcx
  DWORD v8; // esi
  signed int LastError; // eax
  signed int v10; // eax
  PSID v11; // rsi
  DWORD LengthSid; // edi
  DWORD v13; // esi
  HANDLE ProcessHeap; // rax
  struct _ACL *v15; // rax
  __int64 v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  PSID pSid; // [rsp+68h] [rbp-19h] BYREF
  PSID lpMem[4]; // [rsp+70h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+Fh] BYREF

  lpMem[1] = (PSID)-2LL;
  v4 = 0;
  lpMem[2] = 0;
  pSid = 0;
  v5 = 0;
  lpMem[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  FileW = -1;
  lpMem[3] = (PSID)-1LL;
  if ( !lpFileName || !a2 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_28:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_29;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_5;
  if ( (unsigned int)GetCurrentUserSID(lpMem) )
  {
    v11 = pSid;
    v5 = lpMem[0];
    LengthSid = GetLengthSid(lpMem[0]);
    v13 = LengthSid + GetLengthSid(v11) + 24;
    ProcessHeap = GetProcessHeap();
    v15 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v13);
    v4 = v15;
    if ( !v15 )
    {
      v4 = 0;
      v8 = -2147024882;
      goto LABEL_27;
    }
    if ( InitializeAcl(v15, v13, 2u)
      && AddAccessAllowedAce(v4, 2u, 0x10000000u, pSid)
      && AddAccessAllowedAce(v4, 2u, 0x10000000u, v5) )
    {
      FileW = (__int64)CreateFileW(lpFileName, 0xC0040000, 1u, 0, 4u, 0x8200000u, 0);
      if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v8 = SetSecurityInfo((HANDLE)FileW, SE_FILE_OBJECT, 0x80000004, 0, 0, v4, 0);
        if ( !v8 )
        {
          v8 = 0;
          v16 = FileW;
          FileW = -1;
          *a2 = v16;
          goto LABEL_29;
        }
        if ( (int)v8 <= 0 )
          goto LABEL_27;
        v8 = (unsigned __int16)v8;
        goto LABEL_26;
      }
      FileW = -1;
    }
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( !LastError )
    {
      v8 = -2147467259;
LABEL_27:
      v7 = v8;
      goto LABEL_28;
    }
    if ( LastError <= 0 )
      goto LABEL_27;
    v8 = (unsigned __int16)LastError;
LABEL_26:
    v8 |= 0x80070000;
    goto LABEL_27;
  }
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
  v5 = lpMem[0];
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
  return v8;
}

```

## disassembly

```asm
0x1400093b8  mov     rax, rsp
0x1400093bb  push    rbp
0x1400093bc  push    rsi
0x1400093bd  push    rdi
0x1400093be  push    r12
0x1400093c0  push    r13
0x1400093c2  push    r14
0x1400093c4  push    r15
0x1400093c6  lea     rbp, [rax-5Fh]
0x1400093ca  sub     rsp, 0A0h
0x1400093d1  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1400093d9  mov     [rax+18h], rbx
0x1400093dd  mov     rax, cs:__security_cookie
0x1400093e4  xor     rax, rsp
0x1400093e7  mov     [rbp+57h+var_40], rax
0x1400093eb  mov     r15, rdx
0x1400093ee  mov     r12, rcx
0x1400093f1  xor     r13d, r13d
0x1400093f4  mov     edi, r13d
0x1400093f7  mov     [rbp+57h+var_58], r13
0x1400093fb  mov     [rbp+57h+pSid], r13
0x1400093ff  mov     r14d, r13d
0x140009402  mov     [rbp+57h+lpMem], r13
0x140009406  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x14000940a  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140009410  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140009414  mov     [rbp+57h+var_50], rbx
0x140009418  test    rcx, rcx
0x14000941b  jnz     short loc_140009429
0x14000941d  mov     ecx, 80070057h
0x140009422  mov     esi, ecx
0x140009424  jmp     loc_140009644
0x140009429  test    r15, r15
0x14000942c  jz      short loc_14000941D
0x14000942e  lea     rax, [rbp+57h+pSid]
0x140009432  mov     [rsp+50h], rax; pSid
0x140009437  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x14000943c  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x140009441  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x140009446  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x14000944b  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x140009450  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x140009455  mov     r9d, 220h; nSubAuthority1
0x14000945b  mov     r8d, 20h ; ' '; nSubAuthority0
0x140009461  mov     dl, 2; nSubAuthorityCount
0x140009463  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140009467  call    cs:__imp_AllocateAndInitializeSid
0x14000946e  nop     dword ptr [rax+rax+00h]
0x140009473  test    eax, eax
0x140009475  jnz     short loc_1400094A1
0x140009477  call    cs:__imp_GetLastError
0x14000947e  nop     dword ptr [rax+rax+00h]
0x140009483  mov     esi, eax
0x140009485  test    eax, eax
0x140009487  jnz     short loc_140009493
0x140009489  mov     esi, 80004005h
0x14000948e  jmp     loc_140009642
0x140009493  jle     loc_140009642
0x140009499  movzx   esi, ax
0x14000949c  jmp     loc_14000963C
0x1400094a1  lea     rcx, [rbp+57h+lpMem]
0x1400094a5  call    GetCurrentUserSID
0x1400094aa  test    eax, eax
0x1400094ac  jnz     short loc_1400094E2
0x1400094ae  call    cs:__imp_GetLastError
0x1400094b5  nop     dword ptr [rax+rax+00h]
0x1400094ba  mov     esi, eax
0x1400094bc  test    eax, eax
0x1400094be  jnz     short loc_1400094C7
0x1400094c0  mov     esi, 80004005h
0x1400094c5  jmp     short loc_1400094D2
0x1400094c7  jle     short loc_1400094D2
0x1400094c9  movzx   esi, ax
0x1400094cc  or      esi, 80070000h
0x1400094d2  mov     ecx, esi
0x1400094d4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400094d9  mov     r14, [rbp+57h+lpMem]
0x1400094dd  jmp     loc_140009649
0x1400094e2  mov     rsi, [rbp+57h+pSid]
0x1400094e6  mov     r14, [rbp+57h+lpMem]
0x1400094ea  mov     rcx, r14; pSid
0x1400094ed  call    cs:__imp_GetLengthSid
0x1400094f4  nop     dword ptr [rax+rax+00h]
0x1400094f9  mov     edi, eax
0x1400094fb  mov     rcx, rsi; pSid
0x1400094fe  call    cs:__imp_GetLengthSid
0x140009505  nop     dword ptr [rax+rax+00h]
0x14000950a  lea     esi, [rax+18h]
0x14000950d  add     esi, edi
0x14000950f  call    cs:__imp_GetProcessHeap
0x140009516  nop     dword ptr [rax+rax+00h]
0x14000951b  mov     rcx, rax; hHeap
0x14000951e  mov     r8d, esi; dwBytes
0x140009521  xor     edx, edx; dwFlags
0x140009523  call    cs:__imp_HeapAlloc
0x14000952a  nop     dword ptr [rax+rax+00h]
0x14000952f  mov     rdi, rax
0x140009532  test    rax, rax
0x140009535  jnz     short loc_140009544
0x140009537  mov     rdi, r13
0x14000953a  mov     esi, 8007000Eh
0x14000953f  jmp     loc_140009642
0x140009544  mov     r8d, 2; dwAclRevision
0x14000954a  mov     edx, esi; nAclLength
0x14000954c  mov     rcx, rdi; pAcl
0x14000954f  call    cs:__imp_InitializeAcl
0x140009556  nop     dword ptr [rax+rax+00h]
0x14000955b  test    eax, eax
0x14000955d  jz      loc_140009477
0x140009563  mov     r9, [rbp+57h+pSid]; pSid
0x140009567  mov     esi, 2
0x14000956c  mov     r8d, 10000000h; AccessMask
0x140009572  mov     edx, esi; dwAceRevision
0x140009574  mov     rcx, rdi; pAcl
0x140009577  call    cs:__imp_AddAccessAllowedAce
0x14000957e  nop     dword ptr [rax+rax+00h]
0x140009583  test    eax, eax
0x140009585  jz      loc_140009477
0x14000958b  mov     r9, r14; pSid
0x14000958e  mov     r8d, 10000000h; AccessMask
0x140009594  mov     edx, esi; dwAceRevision
0x140009596  mov     rcx, rdi; pAcl
0x140009599  call    cs:__imp_AddAccessAllowedAce
0x1400095a0  nop     dword ptr [rax+rax+00h]
0x1400095a5  test    eax, eax
0x1400095a7  jz      loc_140009477
0x1400095ad  mov     qword ptr [rsp+0D0h+nSubAuthority4], r13; hTemplateFile
0x1400095b2  mov     [rsp+0D0h+nSubAuthority3], 8200000h; dwFlagsAndAttributes
0x1400095ba  mov     [rsp+0D0h+nSubAuthority2], 4; dwCreationDisposition
0x1400095c2  xor     r9d, r9d; lpSecurityAttributes
0x1400095c5  lea     esi, [r9+1]
0x1400095c9  mov     r8d, esi; dwShareMode
0x1400095cc  mov     edx, 0C0040000h; dwDesiredAccess
0x1400095d1  mov     rcx, r12; lpFileName
0x1400095d4  call    cs:__imp_CreateFileW
0x1400095db  nop     dword ptr [rax+rax+00h]
0x1400095e0  mov     rbx, rax
0x1400095e3  inc     rax
0x1400095e6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400095ec  jnz     short loc_1400095F7
0x1400095ee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400095f2  jmp     loc_140009477
0x1400095f7  mov     qword ptr [rsp+0D0h+nSubAuthority4], r13; pSacl
0x1400095fc  mov     qword ptr [rsp+0D0h+nSubAuthority3], rdi; pDacl
0x140009601  mov     qword ptr [rsp+0D0h+nSubAuthority2], r13; psidGroup
0x140009606  xor     r9d, r9d; psidOwner
0x140009609  mov     r8d, 80000004h; SecurityInfo
0x14000960f  mov     edx, esi; ObjectType
0x140009611  mov     rcx, rbx; handle
0x140009614  call    cs:__imp_SetSecurityInfo
0x14000961b  nop     dword ptr [rax+rax+00h]
0x140009620  mov     esi, eax
0x140009622  test    eax, eax
0x140009624  jnz     short loc_140009635
0x140009626  mov     esi, r13d
0x140009629  mov     rax, rbx
0x14000962c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140009630  mov     [r15], rax
0x140009633  jmp     short loc_140009649
0x140009635  test    esi, esi
0x140009637  jle     short loc_140009642
0x140009639  movzx   esi, si
0x14000963c  or      esi, 80070000h
0x140009642  mov     ecx, esi
0x140009644  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140009649  mov     ecx, esi
0x14000964b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009650  nop
0x140009651  lea     rax, [rbx-1]
0x140009655  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140009659  ja      short loc_14000966B
0x14000965b  mov     rcx, rbx; hObject
0x14000965e  call    cs:__imp_CloseHandle
0x140009665  nop     dword ptr [rax+rax+00h]
0x14000966a  nop
0x14000966b  test    r14, r14
0x14000966e  jz      short loc_140009691
0x140009670  call    cs:__imp_GetProcessHeap
0x140009677  nop     dword ptr [rax+rax+00h]
0x14000967c  mov     rcx, rax; hHeap
0x14000967f  mov     r8, r14; lpMem
0x140009682  xor     edx, edx; dwFlags
0x140009684  call    cs:__imp_HeapFree
0x14000968b  nop     dword ptr [rax+rax+00h]
0x140009690  nop
0x140009691  mov     rcx, [rbp+57h+pSid]; pSid
0x140009695  test    rcx, rcx
0x140009698  jz      short loc_1400096AA
0x14000969a  call    cs:__imp_FreeSid
0x1400096a1  nop     dword ptr [rax+rax+00h]
0x1400096a6  mov     [rbp+57h+pSid], r13
0x1400096aa  test    rdi, rdi
0x1400096ad  jz      short loc_1400096CF
0x1400096af  call    cs:__imp_GetProcessHeap
0x1400096b6  nop     dword ptr [rax+rax+00h]
0x1400096bb  mov     rcx, rax; hHeap
0x1400096be  mov     r8, rdi; lpMem
0x1400096c1  xor     edx, edx; dwFlags
0x1400096c3  call    cs:__imp_HeapFree
0x1400096ca  nop     dword ptr [rax+rax+00h]
0x1400096cf  mov     eax, esi
0x1400096d1  mov     rcx, [rbp+57h+var_40]
0x1400096d5  xor     rcx, rsp; StackCookie
0x1400096d8  call    __security_check_cookie
0x1400096dd  mov     rbx, [rsp+0D0h+arg_10]
0x1400096e5  add     rsp, 0A0h
0x1400096ec  pop     r15
0x1400096ee  pop     r14
0x1400096f0  pop     r13
0x1400096f2  pop     r12
0x1400096f4  pop     rdi
0x1400096f5  pop     rsi
0x1400096f6  pop     rbp
0x1400096f7  retn
```
