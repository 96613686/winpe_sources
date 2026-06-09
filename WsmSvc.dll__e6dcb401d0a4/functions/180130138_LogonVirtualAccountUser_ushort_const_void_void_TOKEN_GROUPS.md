# LogonVirtualAccountUser(ushort const *,void *,void * *,_TOKEN_GROUPS *)

- ea: `0x180130138`
- end: `0x1801303e7`
- name: `?LogonVirtualAccountUser@@YAJPEBGPEAXPEAPEAXPEAU_TOKEN_GROUPS@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, void **, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18012fbc4`

## callees

- `0x18005d800`
- `0x1800621e0`
- `0x18012fff4`
- `0x180130138`
- `0x180130480`
- `0x1801304a4`
- `0x1801ba152`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801302a2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801302fe`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801302a2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801302fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180130387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180130387`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801301b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801301b9`
- `ntdll!RtlFreeSid` at `0x18013039c`
- `ntdll!RtlFreeSid` at `0x18013039c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180130225`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180130225`
- `SspiCli!LogonUserExExW` at `0x180130362`
- `SspiCli!LogonUserExExW` at `0x180130362`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogonVirtualAccountUser(const unsigned __int16 *a1, void *a2, void **a3, struct _TOKEN_GROUPS *a4)
{
  void **v5; // r15
  struct _TOKEN_GROUPS *v6; // r12
  DWORD v7; // r14d
  PSID v8; // rsi
  unsigned int Error; // eax
  unsigned int v10; // ebx
  int v11; // r15d
  NTSTATUS v12; // eax
  __int64 v13; // r13
  struct _TOKEN_GROUPS *v14; // rax
  DWORD cbSid; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  PSID DomainSid; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  void *v20; // [rsp+80h] [rbp-80h]
  void **v21; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v22; // [rsp+90h] [rbp-70h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  char v25; // [rsp+1BAh] [rbp+BAh]
  _BYTE pSid[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v27[80]; // [rsp+210h] [rbp+110h] BYREF

  v5 = a3;
  v21 = a3;
  v20 = a2;
  v22 = a1;
  hObject = 0;
  Sid = 0;
  v6 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 512;
  v7 = 2;
  v8 = 0;
  DomainSid = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_2;
  v10 = 0;
  if ( !a4 )
  {
    if ( v25 == 2 )
    {
      v11 = 1;
      v7 = 3;
    }
    else
    {
      v11 = 0;
    }
    v12 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v12 < 0 )
    {
      Error = ResultFromWin32FromStatus(v12);
      goto LABEL_3;
    }
    v13 = 16LL * v7;
    v14 = (struct _TOKEN_GROUPS *)WSManMemory::Alloc(v13 + 24, 0, 0);
    a4 = v14;
    v6 = v14;
    if ( !v14 )
    {
      v10 = -2147024882;
      goto LABEL_20;
    }
    memset_0(v14, 0, v13 + 24);
    a4->GroupCount = v7;
    a4->Groups[0].Sid = Sid;
    a4->Groups[0].Attributes = 7;
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
    {
      *(_QWORD *)&a4[1].GroupCount = pSid;
      LODWORD(a4[1].Groups[0].Sid) = 7;
      if ( !v11 )
      {
LABEL_17:
        v5 = v21;
        goto LABEL_18;
      }
      v10 = GetDomainSid(v20, &DomainSid);
      v8 = DomainSid;
      if ( v10 )
        goto LABEL_20;
      cbSid = 68;
      if ( CreateWellKnownSid(WinAccountDomainAdminsSid, DomainSid, v27, &cbSid) )
      {
        *(_QWORD *)&a4[1].Groups[0].Attributes = v27;
        a4[2].GroupCount = 7;
        goto LABEL_17;
      }
    }
LABEL_2:
    Error = ResultFromLastError();
LABEL_3:
    v10 = Error;
    goto LABEL_20;
  }
LABEL_18:
  if ( !(unsigned int)LogonUserExExW(v22, L"WinRM Virtual Users", &Class, 5, 4, a4, &hObject, 0, 0, 0, 0) )
    goto LABEL_2;
  *v5 = hObject;
  hObject = 0;
LABEL_20:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v8 )
    WSManMemory::Free(v8, 0);
  if ( v6 )
    WSManMemory::Free(v6, 0);
  return v10;
}

```

## disassembly

```asm
0x180130138  push    rbp
0x18013013a  push    rbx
0x18013013b  push    rsi
0x18013013c  push    rdi
0x18013013d  push    r12
0x18013013f  push    r13
0x180130141  push    r14
0x180130143  push    r15
0x180130145  lea     rbp, [rsp-178h]
0x18013014d  sub     rsp, 278h
0x180130154  mov     rax, cs:__security_cookie
0x18013015b  xor     rax, rsp
0x18013015e  mov     [rbp+1B0h+var_50], rax
0x180130165  mov     rdi, r9
0x180130168  mov     r15, r8
0x18013016b  mov     [rbp+1B0h+var_228], r8
0x18013016f  mov     [rbp+1B0h+var_230], rdx
0x180130173  mov     [rbp+1B0h+var_220], rcx
0x180130177  xor     r13d, r13d
0x18013017a  mov     [rsp+2B0h+hObject], r13
0x18013017f  mov     [rsp+2B0h+var_238], r13
0x180130184  mov     r12d, r13d
0x180130187  mov     dword ptr [rbp+1B0h+IdentifierAuthority.Value], r13d
0x18013018b  mov     word ptr [rbp+1B0h+IdentifierAuthority.Value+4], 200h
0x180130191  lea     r14d, [r13+2]
0x180130195  mov     esi, r13d
0x180130198  mov     [rsp+2B0h+DomainSid], r13
0x18013019d  xor     edx, edx; Val
0x18013019f  mov     r8d, 118h; Size
0x1801301a5  lea     rcx, [rbp+1B0h+VersionInformation.dwMajorVersion]; void *
0x1801301a9  call    memset_0
0x1801301ae  mov     [rbp+1B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1801301b5  lea     rcx, [rbp+1B0h+VersionInformation]; lpVersionInformation
0x1801301b9  call    cs:__imp_GetVersionExW
0x1801301bf  test    eax, eax
0x1801301c1  jnz     short loc_1801301CF
0x1801301c3  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801301c8  mov     ebx, eax
0x1801301ca  jmp     loc_18013037D
0x1801301cf  mov     ebx, r13d
0x1801301d2  test    rdi, rdi
0x1801301d5  jnz     loc_18013031F
0x1801301db  cmp     [rbp+1B0h+var_F6], r14b
0x1801301e2  jnz     short loc_1801301EE
0x1801301e4  lea     r15d, [rdi+1]
0x1801301e8  lea     r14d, [rdi+3]
0x1801301ec  jmp     short loc_1801301F1
0x1801301ee  mov     r15d, r13d
0x1801301f1  lea     rax, [rsp+2B0h+var_238]
0x1801301f6  mov     [rsp+2B0h+Sid], rax; Sid
0x1801301fb  mov     [rsp+2B0h+SubAuthority7], r13d; SubAuthority7
0x180130200  mov     [rsp+2B0h+SubAuthority6], r13d; SubAuthority6
0x180130205  mov     [rsp+2B0h+SubAuthority5], r13d; SubAuthority5
0x18013020a  mov     [rsp+2B0h+SubAuthority4], r13d; SubAuthority4
0x18013020f  mov     [rsp+2B0h+SubAuthority3], r13d; SubAuthority3
0x180130214  mov     [rsp+2B0h+SubAuthority2], r13d; SubAuthority2
0x180130219  xor     r9d, r9d; SubAuthority1
0x18013021c  xor     r8d, r8d; SubAuthority0
0x18013021f  mov     dl, 1; SubAuthorityCount
0x180130221  lea     rcx, [rbp+1B0h+IdentifierAuthority]; IdentifierAuthority
0x180130225  call    cs:__imp_RtlAllocateAndInitializeSid
0x18013022b  test    eax, eax
0x18013022d  jns     short loc_180130238
0x18013022f  mov     ecx, eax; int
0x180130231  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180130236  jmp     short loc_1801301C8
0x180130238  mov     r13d, r14d
0x18013023b  shl     r13, 4
0x18013023f  xor     r8d, r8d
0x180130242  xor     edx, edx
0x180130244  lea     rcx, [r13+18h]
0x180130248  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18013024d  mov     rdi, rax
0x180130250  mov     r12, rax
0x180130253  test    rax, rax
0x180130256  jnz     short loc_180130265
0x180130258  mov     ebx, 8007000Eh
0x18013025d  xor     r13d, r13d
0x180130260  jmp     loc_18013037D
0x180130265  lea     r8, [r13+18h]; Size
0x180130269  xor     edx, edx; Val
0x18013026b  mov     rcx, rdi; void *
0x18013026e  call    memset_0
0x180130273  mov     [rdi], r14d
0x180130276  mov     rax, [rsp+2B0h+var_238]
0x18013027b  mov     [rdi+8], rax
0x18013027f  mov     r14d, 7
0x180130285  mov     [rdi+10h], r14d
0x180130289  mov     [rsp+2B0h+cbSid], 44h ; 'D'
0x180130291  lea     r9, [rsp+2B0h+cbSid]; cbSid
0x180130296  lea     r8, [rbp+1B0h+pSid]; pSid
0x18013029d  xor     edx, edx; DomainSid
0x18013029f  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1801302a2  call    cs:__imp_CreateWellKnownSid
0x1801302a8  xor     r13d, r13d
0x1801302ab  test    eax, eax
0x1801302ad  jz      loc_1801301C3
0x1801302b3  lea     rax, [rbp+1B0h+pSid]
0x1801302ba  mov     [rdi+18h], rax
0x1801302be  mov     [rdi+20h], r14d
0x1801302c2  test    r15d, r15d
0x1801302c5  jz      short loc_18013031B
0x1801302c7  lea     rdx, [rsp+2B0h+DomainSid]; void **
0x1801302cc  mov     rcx, [rbp+1B0h+var_230]; void *
0x1801302d0  call    ?GetDomainSid@@YAJPEAXPEAPEAX@Z; GetDomainSid(void *,void * *)
0x1801302d5  mov     ebx, eax
0x1801302d7  mov     rsi, [rsp+2B0h+DomainSid]
0x1801302dc  test    eax, eax
0x1801302de  jnz     loc_18013037D
0x1801302e4  mov     [rsp+2B0h+cbSid], 44h ; 'D'
0x1801302ec  lea     r9, [rsp+2B0h+cbSid]; cbSid
0x1801302f1  lea     r8, [rbp+1B0h+var_A0]; pSid
0x1801302f8  mov     rdx, rsi; DomainSid
0x1801302fb  lea     ecx, [rax+29h]; WellKnownSidType
0x1801302fe  call    cs:__imp_CreateWellKnownSid
0x180130304  test    eax, eax
0x180130306  jz      loc_1801301C3
0x18013030c  lea     rax, [rbp+1B0h+var_A0]
0x180130313  mov     [rdi+28h], rax
0x180130317  mov     [rdi+30h], r14d
0x18013031b  mov     r15, [rbp+1B0h+var_228]
0x18013031f  mov     [rsp+2B0h+Sid], r13
0x180130324  mov     qword ptr [rsp+2B0h+SubAuthority7], r13
0x180130329  mov     qword ptr [rsp+2B0h+SubAuthority6], r13
0x18013032e  mov     qword ptr [rsp+2B0h+SubAuthority5], r13
0x180130333  lea     rax, [rsp+2B0h+hObject]
0x180130338  mov     qword ptr [rsp+2B0h+SubAuthority4], rax
0x18013033d  mov     qword ptr [rsp+2B0h+SubAuthority3], rdi
0x180130342  mov     [rsp+2B0h+SubAuthority2], 4
0x18013034a  mov     r9d, 5
0x180130350  lea     r8, Class
0x180130357  lea     rdx, aWinrmVirtualUs; "WinRM Virtual Users"
0x18013035e  mov     rcx, [rbp+1B0h+var_220]
0x180130362  call    cs:__imp_LogonUserExExW
0x180130368  test    eax, eax
0x18013036a  jz      loc_1801301C3
0x180130370  mov     rax, [rsp+2B0h+hObject]
0x180130375  mov     [r15], rax
0x180130378  mov     [rsp+2B0h+hObject], r13
0x18013037d  mov     rcx, [rsp+2B0h+hObject]; hObject
0x180130382  test    rcx, rcx
0x180130385  jz      short loc_180130392
0x180130387  call    cs:__imp_CloseHandle
0x18013038d  mov     [rsp+2B0h+hObject], r13
0x180130392  mov     rcx, [rsp+2B0h+var_238]; Sid
0x180130397  test    rcx, rcx
0x18013039a  jz      short loc_1801303A2
0x18013039c  call    cs:__imp_RtlFreeSid
0x1801303a2  test    rsi, rsi
0x1801303a5  jz      short loc_1801303B2
0x1801303a7  xor     edx, edx; int
0x1801303a9  mov     rcx, rsi; void *
0x1801303ac  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x1801303b1  nop
0x1801303b2  test    r12, r12
0x1801303b5  jz      short loc_1801303C2
0x1801303b7  xor     edx, edx; int
0x1801303b9  mov     rcx, r12; void *
0x1801303bc  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x1801303c1  nop
0x1801303c2  mov     eax, ebx
0x1801303c4  mov     rcx, [rbp+1B0h+var_50]
0x1801303cb  xor     rcx, rsp; StackCookie
0x1801303ce  call    __security_check_cookie
0x1801303d3  add     rsp, 278h
0x1801303da  pop     r15
0x1801303dc  pop     r14
0x1801303de  pop     r13
0x1801303e0  pop     r12
0x1801303e2  pop     rdi
0x1801303e3  pop     rsi
0x1801303e4  pop     rbx
0x1801303e5  pop     rbp
0x1801303e6  retn
```
