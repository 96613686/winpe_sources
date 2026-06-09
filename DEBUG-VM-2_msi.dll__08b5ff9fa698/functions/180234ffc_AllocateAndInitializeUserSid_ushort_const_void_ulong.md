# AllocateAndInitializeUserSid(ushort const *,void * *,ulong &)

- ea: `0x180234ffc`
- end: `0x180235394`
- name: `?AllocateAndInitializeUserSid@@YAHPEBGPEAPEAXAEAK@Z`
- size: `920`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1802383f4`

## callees

- `0x18000a150`
- `0x18004295c`
- `0x180061334`
- `0x180083178`
- `0x1800833ec`
- `0x180234ffc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x180235289`
- `ADVAPI32!GetSidLengthRequired` at `0x180235289`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180235281`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180235281`
- `ADVAPI32!LookupAccountNameW` at `0x180235264`
- `ADVAPI32!LookupAccountNameW` at `0x1802352ff`
- `ADVAPI32!LookupAccountNameW` at `0x180235264`
- `ADVAPI32!LookupAccountNameW` at `0x1802352ff`
- `ADVAPI32!CopySid` at `0x1802352b8`
- `ADVAPI32!CopySid` at `0x1802352b8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180235115`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180235115`
- `ADVAPI32!GetLengthSid` at `0x180235226`
- `ADVAPI32!GetLengthSid` at `0x180235226`
- `ADVAPI32!FreeSid` at `0x180235316`
- `ADVAPI32!FreeSid` at `0x180235316`
- `KERNEL32!GetLastError` at `0x18023526c`
- `KERNEL32!GetLastError` at `0x18023526c`
- `KERNEL32!SetLastError` at `0x1802352c7`
- `KERNEL32!SetLastError` at `0x1802352c7`

## string_xrefs

- `0x1802350b2`: `Using well known SID for System`
- `0x18023516a`: `Using well known SID for Administrators`
- `0x18023532a`: `Finished allocating new user SID`
- `0x1802351d9`: `Using well known SID for Everyone`

## pseudocode

```c
__int64 __fastcall AllocateAndInitializeUserSid(const unsigned __int16 *a1, void **a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  DWORD v7; // r9d
  BYTE v8; // dl
  DWORD v9; // r8d
  struct _SID_IDENTIFIER_AUTHORITY *p_pIdentifierAuthority; // rcx
  int v12; // r14d
  DWORD LastError; // esi
  bool v14; // cl
  UCHAR *SidSubAuthorityCount; // rax
  void *v16; // rax
  bool v17; // cl
  unsigned int pSid; // [rsp+50h] [rbp-B0h]
  void *v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp-98h] BYREF
  PSID pSourceSid; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+7Ch] [rbp-84h] BYREF
  int v25; // [rsp+84h] [rbp-7Ch] BYREF
  __int16 v26; // [rsp+88h] [rbp-78h]
  _BYTE Sid[80]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+E0h] [rbp-20h] BYREF

  cchReferencedDomainName = 260;
  peUse = SidTypeUnknown;
  *a3 = 80;
  pSourceSid = Sid;
  MsiString::MsiString((MsiString *)&v20, a1);
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v6 = 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v20 + 200LL))(
         v20,
         1,
         L"SYSTEM") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for System",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 0;
    v8 = 1;
    v9 = 18;
LABEL_5:
    p_pIdentifierAuthority = &pIdentifierAuthority;
LABEL_6:
    if ( !AllocateAndInitializeSid(p_pIdentifierAuthority, v8, v9, v7, 0, 0, 0, 0, 0, 0, &pSourceSid) )
    {
LABEL_7:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      return 0;
    }
    *a3 = GetLengthSid(pSourceSid);
    v12 = 1;
    goto LABEL_19;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v20 + 200LL))(
         v20,
         1,
         L"Administrators") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for Administrators",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 544;
    v9 = 32;
    v8 = 2;
    goto LABEL_5;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v20 + 200LL))(v20, 1, L"Everyone") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for Everyone",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 0;
    v25 = 0;
    v9 = 0;
    v26 = 256;
    v8 = 1;
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v25;
    goto LABEL_6;
  }
  v12 = 0;
  StartImpersonating();
  v6 = LookupAccountNameW(0, a1, Sid, a3, ReferencedDomainName, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  StopImpersonating(v14);
  if ( v6 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(Sid);
    *a3 = GetSidLengthRequired(*SidSubAuthorityCount);
  }
  else if ( LastError != 122 )
  {
    SetLastError(LastError);
    goto LABEL_7;
  }
LABEL_19:
  v16 = operator new(*a3);
  *a2 = v16;
  cchReferencedDomainName = 260;
  if ( v6 )
  {
    CopySid(*a3, v16, pSourceSid);
  }
  else
  {
    StartImpersonating();
    v6 = LookupAccountNameW(0, a1, *a2, a3, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    StopImpersonating(v17);
  }
  if ( v12 )
    FreeSid(pSourceSid);
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Finished allocating new user SID",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      pSid,
      v19);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v6;
}

```

## disassembly

```asm
0x180234ffc  mov     [rsp-8+arg_18], rbx
0x180235001  push    rbp
0x180235002  push    rsi
0x180235003  push    rdi
0x180235004  push    r12
0x180235006  push    r13
0x180235008  push    r14
0x18023500a  push    r15
0x18023500c  lea     rbp, [rsp-200h]
0x180235014  sub     rsp, 300h
0x18023501b  mov     rax, cs:__security_cookie
0x180235022  xor     rax, rsp
0x180235025  mov     [rbp+230h+var_40], rax
0x18023502c  mov     r15, rdx
0x18023502f  mov     [rsp+330h+cchReferencedDomainName], 104h
0x180235037  mov     rdx, rcx; unsigned __int16 *
0x18023503a  mov     [rsp+330h+peUse], 8
0x180235042  mov     r12, rcx
0x180235045  mov     dword ptr [r8], 50h ; 'P'
0x18023504c  lea     rax, [rbp+230h+Sid]
0x180235050  mov     rdi, r8
0x180235053  lea     rcx, [rsp+330h+var_2D0]; this
0x180235058  mov     [rsp+330h+pSourceSid], rax
0x18023505d  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180235062  mov     rcx, [rsp+330h+var_2D0]
0x180235067  lea     r8, aSystem; "SYSTEM"
0x18023506e  xor     r13d, r13d
0x180235071  mov     word ptr [rbp+230h+pIdentifierAuthority.Value+4], 500h
0x180235077  mov     dword ptr [rsp+330h+pIdentifierAuthority.Value], r13d
0x18023507c  mov     rax, [rcx]
0x18023507f  lea     ebx, [r13+1]
0x180235083  mov     edx, ebx
0x180235085  mov     rax, [rax+0C8h]
0x18023508c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235091  lea     rsi, aNull_0; "(NULL)"
0x180235098  lea     r14d, [r13+9]
0x18023509c  test    eax, eax
0x18023509e  jz      loc_18023513B
0x1802350a4  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1802350ab  jz      short loc_1802350DF
0x1802350ad  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x1802350b2  lea     r9, aUsingWellKnown_0; "Using well known SID for System"
0x1802350b9  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x1802350be  xor     edx, edx; unsigned __int16
0x1802350c0  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x1802350c5  xor     r8d, r8d; int
0x1802350c8  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x1802350cd  mov     ecx, r14d; int
0x1802350d0  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x1802350d5  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x1802350da  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1802350df  xor     r9d, r9d; nSubAuthority1
0x1802350e2  mov     dl, bl; nSubAuthorityCount
0x1802350e4  lea     r8d, [r9+12h]; nSubAuthority0
0x1802350e8  lea     rcx, [rsp+330h+pIdentifierAuthority]; pIdentifierAuthority
0x1802350ed  lea     rax, [rsp+330h+pSourceSid]
0x1802350f2  mov     [rsp+330h+pSid], rax; pSid
0x1802350f7  mov     [rsp+330h+nSubAuthority7], r13d; nSubAuthority7
0x1802350fc  mov     [rsp+330h+nSubAuthority6], r13d; nSubAuthority6
0x180235101  mov     [rsp+330h+nSubAuthority5], r13d; nSubAuthority5
0x180235106  mov     [rsp+330h+nSubAuthority4], r13d; nSubAuthority4
0x18023510b  mov     [rsp+330h+nSubAuthority3], r13d; nSubAuthority3
0x180235110  mov     [rsp+330h+nSubAuthority2], r13d; nSubAuthority2
0x180235115  call    cs:__imp_AllocateAndInitializeSid
0x18023511b  test    eax, eax
0x18023511d  jnz     loc_180235221
0x180235123  mov     rcx, [rsp+330h+var_2D0]
0x180235128  mov     rax, [rcx]
0x18023512b  mov     rax, [rax+10h]
0x18023512f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235134  xor     eax, eax
0x180235136  jmp     loc_18023536A
0x18023513b  mov     rcx, [rsp+330h+var_2D0]
0x180235140  lea     r8, aAdministrators; "Administrators"
0x180235147  mov     edx, ebx
0x180235149  mov     rax, [rcx]
0x18023514c  mov     rax, [rax+0C8h]
0x180235153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235158  test    eax, eax
0x18023515a  jz      short loc_1802351AA
0x18023515c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180235163  jz      short loc_180235197
0x180235165  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023516a  lea     r9, aUsingWellKnown_1; "Using well known SID for Administrators"
0x180235171  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x180235176  xor     edx, edx; unsigned __int16
0x180235178  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023517d  xor     r8d, r8d; int
0x180235180  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x180235185  mov     ecx, r14d; int
0x180235188  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023518d  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x180235192  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180235197  mov     r9d, 220h
0x18023519d  mov     r8d, 20h ; ' '
0x1802351a3  mov     dl, 2
0x1802351a5  jmp     loc_1802350E8
0x1802351aa  mov     rcx, [rsp+330h+var_2D0]
0x1802351af  lea     r8, aEveryone; "Everyone"
0x1802351b6  mov     edx, ebx
0x1802351b8  mov     rax, [rcx]
0x1802351bb  mov     rax, [rax+0C8h]
0x1802351c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802351c7  test    eax, eax
0x1802351c9  jz      short loc_180235233
0x1802351cb  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1802351d2  jz      short loc_180235206
0x1802351d4  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x1802351d9  lea     r9, aUsingWellKnown; "Using well known SID for Everyone"
0x1802351e0  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x1802351e5  xor     edx, edx; unsigned __int16
0x1802351e7  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x1802351ec  xor     r8d, r8d; int
0x1802351ef  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x1802351f4  mov     ecx, r14d; int
0x1802351f7  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x1802351fc  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x180235201  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180235206  xor     r9d, r9d
0x180235209  mov     [rbp+230h+var_2AC], r13d
0x18023520d  xor     r8d, r8d
0x180235210  mov     [rbp+230h+var_2A8], 100h
0x180235216  mov     dl, bl
0x180235218  lea     rcx, [rbp+230h+var_2AC]
0x18023521c  jmp     loc_1802350ED
0x180235221  mov     rcx, [rsp+330h+pSourceSid]; pSid
0x180235226  call    cs:__imp_GetLengthSid
0x18023522c  mov     [rdi], eax
0x18023522e  mov     r14d, ebx
0x180235231  jmp     short loc_180235298
0x180235233  mov     r14d, r13d
0x180235236  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18023523b  lea     rax, [rsp+330h+peUse]
0x180235240  mov     r9, rdi; cbSid
0x180235243  mov     qword ptr [rsp+330h+nSubAuthority4], rax; peUse
0x180235248  lea     r8, [rbp+230h+Sid]; Sid
0x18023524c  lea     rax, [rsp+330h+cchReferencedDomainName]
0x180235251  mov     rdx, r12; lpAccountName
0x180235254  mov     qword ptr [rsp+330h+nSubAuthority3], rax; cchReferencedDomainName
0x180235259  xor     ecx, ecx; lpSystemName
0x18023525b  lea     rax, [rbp+230h+ReferencedDomainName]
0x18023525f  mov     qword ptr [rsp+330h+nSubAuthority2], rax; ReferencedDomainName
0x180235264  call    cs:__imp_LookupAccountNameW
0x18023526a  mov     ebx, eax
0x18023526c  call    cs:__imp_GetLastError
0x180235272  mov     esi, eax
0x180235274  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180235279  test    ebx, ebx
0x18023527b  jz      short loc_1802352C0
0x18023527d  lea     rcx, [rbp+230h+Sid]; pSid
0x180235281  call    cs:__imp_GetSidSubAuthorityCount
0x180235287  mov     cl, [rax]; nSubAuthorityCount
0x180235289  call    cs:__imp_GetSidLengthRequired
0x18023528f  mov     [rdi], eax
0x180235291  lea     rsi, aNull_0; "(NULL)"
0x180235298  mov     ecx, [rdi]; unsigned __int64
0x18023529a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023529f  mov     [r15], rax
0x1802352a2  mov     [rsp+330h+cchReferencedDomainName], 104h
0x1802352aa  test    ebx, ebx
0x1802352ac  jz      short loc_1802352D2
0x1802352ae  mov     r8, [rsp+330h+pSourceSid]; pSourceSid
0x1802352b3  mov     rdx, rax; pDestinationSid
0x1802352b6  mov     ecx, [rdi]; nDestinationSidLength
0x1802352b8  call    cs:__imp_CopySid
0x1802352be  jmp     short loc_18023530C
0x1802352c0  cmp     esi, 7Ah ; 'z'
0x1802352c3  jz      short loc_180235291
0x1802352c5  mov     ecx, esi; dwErrCode
0x1802352c7  call    cs:__imp_SetLastError
0x1802352cd  jmp     loc_180235123
0x1802352d2  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1802352d7  mov     r8, [r15]; Sid
0x1802352da  lea     rax, [rsp+330h+peUse]
0x1802352df  mov     qword ptr [rsp+330h+nSubAuthority4], rax; peUse
0x1802352e4  mov     r9, rdi; cbSid
0x1802352e7  lea     rax, [rsp+330h+cchReferencedDomainName]
0x1802352ec  mov     rdx, r12; lpAccountName
0x1802352ef  mov     qword ptr [rsp+330h+nSubAuthority3], rax; cchReferencedDomainName
0x1802352f4  xor     ecx, ecx; lpSystemName
0x1802352f6  lea     rax, [rbp+230h+ReferencedDomainName]
0x1802352fa  mov     qword ptr [rsp+330h+nSubAuthority2], rax; ReferencedDomainName
0x1802352ff  call    cs:__imp_LookupAccountNameW
0x180235305  mov     ebx, eax
0x180235307  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18023530c  test    r14d, r14d
0x18023530f  jz      short loc_18023531C
0x180235311  mov     rcx, [rsp+330h+pSourceSid]; pSid
0x180235316  call    cs:__imp_FreeSid
0x18023531c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180235323  jz      short loc_180235357
0x180235325  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023532a  lea     r9, aFinishedAlloca; "Finished allocating new user SID"
0x180235331  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x180235336  xor     edx, edx; unsigned __int16
0x180235338  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023533d  xor     r8d, r8d; int
0x180235340  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x180235345  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023534a  lea     ecx, [rdx+9]; int
0x18023534d  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x180235352  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180235357  mov     rcx, [rsp+330h+var_2D0]
0x18023535c  mov     rax, [rcx]
0x18023535f  mov     rax, [rax+10h]
0x180235363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235368  mov     eax, ebx
0x18023536a  mov     rcx, [rbp+230h+var_40]
0x180235371  xor     rcx, rsp; StackCookie
0x180235374  call    __security_check_cookie
0x180235379  mov     rbx, [rsp+330h+arg_18]
0x180235381  add     rsp, 300h
0x180235388  pop     r15
0x18023538a  pop     r14
0x18023538c  pop     r13
0x18023538e  pop     r12
0x180235390  pop     rdi
0x180235391  pop     rsi
0x180235392  pop     rbp
0x180235393  retn
```
