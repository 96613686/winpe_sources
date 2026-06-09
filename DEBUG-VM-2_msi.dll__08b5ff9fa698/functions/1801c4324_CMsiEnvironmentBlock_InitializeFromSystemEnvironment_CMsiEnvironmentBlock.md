# CMsiEnvironmentBlock::InitializeFromSystemEnvironment(CMsiEnvironmentBlock *)

- ea: `0x1801c4324`
- end: `0x1801c488b`
- name: `?InitializeFromSystemEnvironment@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z`
- size: `1383`
- prototype: `bool __fastcall(CMsiEnvironmentBlock *__hidden this, struct CMsiEnvironmentBlock *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801c3f68`

## callees

- `0x18000a150`
- `0x180022120`
- `0x180025a18`
- `0x18004295c`
- `0x180082fc8`
- `0x1800a9d48`
- `0x1800e853c`
- `0x18012f694`
- `0x180138aec`
- `0x1801c40b8`
- `0x1801c4324`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x1801c442a`
- `ADVAPI32!LookupAccountSidW` at `0x1801c442a`
- `ADVAPI32!GetTokenInformation` at `0x1801c43c9`
- `ADVAPI32!GetTokenInformation` at `0x1801c43c9`
- `KERNEL32!GetLastError` at `0x1801c43d3`
- `KERNEL32!GetLastError` at `0x1801c4434`
- `KERNEL32!GetLastError` at `0x1801c4461`
- `KERNEL32!GetLastError` at `0x1801c43d3`
- `KERNEL32!GetLastError` at `0x1801c4434`
- `KERNEL32!GetLastError` at `0x1801c4461`
- `KERNEL32!GlobalFree` at `0x1801c47d0`
- `KERNEL32!GlobalFree` at `0x1801c4835`
- `KERNEL32!GlobalFree` at `0x1801c47d0`
- `KERNEL32!GlobalFree` at `0x1801c4835`
- `KERNEL32!GetSystemDirectoryW` at `0x1801c4457`
- `KERNEL32!GetSystemDirectoryW` at `0x1801c4457`

## string_xrefs

- `0x1801c43e5`: `ERROR: GetTokenInformation failed with error %d`
- `0x1801c4442`: `ERROR: LookupAccountSid failed with error %d`
- `0x1801c446f`: `ERROR: GetSystemDirectory failed with error %d`
- `0x1801c45cd`: `ERROR: Failed to set environment variable: USERPROFILE when it is remote path`
- `0x1801c46b9`: `ERROR: Failed to set environment variable: TMP when it is remote path`
- `0x1801c46ec`: `ERROR: Failed to set environment variable: TEMP when it is remote path`
- `0x1801c4718`: `%c:\Windows\SystemTemp`
- `0x1801c473c`: `ERROR: StringCchPrintf failure in CMsiEnvironmentBlock::InitializeFromSystemEnvironment`
- `0x1801c47fd`: `ERROR: Failed to set environment variable: TEMP`

## pseudocode

```c
char __fastcall CMsiEnvironmentBlock::InitializeFromSystemEnvironment(
        CMsiEnvironmentBlock *this,
        struct CMsiEnvironmentBlock *a2)
{
  void *UserToken; // rax
  void *v5; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v7; // r9
  const char *v9; // r9
  const char *v10; // r9
  unsigned int v11; // [rsp+50h] [rbp-B0h]
  void *v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+68h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-84h] BYREF
  HGLOBAL hMem; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+8Ch] [rbp-74h]
  char v22; // [rsp+90h] [rbp-70h] BYREF
  PSID TokenInformation[12]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v24; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v25[798]; // [rsp+302h] [rbp+202h] BYREF
  WCHAR Buffer[264]; // [rsp+620h] [rbp+520h] BYREF
  WCHAR ReferencedDomainName[400]; // [rsp+830h] [rbp+730h] BYREF
  WCHAR Name[504]; // [rsp+B50h] [rbp+A50h] BYREF

  if ( !CMsiEnvironmentBlock::InitializeFromEnvironment(this, 1) )
    return 0;
  UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
  if ( !IsLocalSystemToken(UserToken) )
  {
    v5 = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    if ( v5 )
    {
      cchName = 500;
      cchReferencedDomainName = 400;
      ReturnLength = 0;
      if ( !GetTokenInformation(v5, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: GetTokenInformation failed with error %d";
LABEL_13:
          DebugString(
            9,
            0,
            0,
            v7,
            (const unsigned __int16 *)LastError,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          return 0;
        }
        return 0;
      }
      peUse = 0;
      if ( !LookupAccountSidW(
              0,
              TokenInformation[0],
              Name,
              &cchName,
              ReferencedDomainName,
              &cchReferencedDomainName,
              &peUse) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: LookupAccountSid failed with error %d";
          goto LABEL_13;
        }
        return 0;
      }
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: GetSystemDirectory failed with error %d";
          goto LABEL_13;
        }
        return 0;
      }
      v20 = 261;
      hMem = &v22;
      v21 = 261;
      if ( !(unsigned __int8)CMsiEnvironmentBlock::Get(a2, L"USERPROFILE", &hMem) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            "ERROR: Failed to get environment variable: USERPROFILE",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            v11,
            v12);
        goto LABEL_44;
      }
      MsiString::MsiString((MsiString *)&v13, (const unsigned __int16 *)hMem);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 200LL))(v13, 3, L"\\\\") == 1
        && !(*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 200LL))(
              v13,
              3,
              L"\\\\?\\")
        && !CMsiEnvironmentBlock::Set(this, L"USERPROFILE", (const unsigned __int16 *)hMem) )
      {
        if ( g_dmDiagnosticMode )
        {
          v9 = "ERROR: Failed to set environment variable: USERPROFILE when it is remote path";
LABEL_26:
          DebugString(9, 0, 0, v9, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v11, v12);
          goto LABEL_43;
        }
        goto LABEL_43;
      }
      v21 = 261;
      if ( !(unsigned __int8)CMsiEnvironmentBlock::Get(a2, L"TMP", &hMem) )
      {
        if ( g_dmDiagnosticMode )
        {
          v9 = "ERROR: Failed to get environment variable: TMP";
          goto LABEL_26;
        }
LABEL_43:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_44:
        if ( v20 > 261 )
          GlobalFree(hMem);
        return 0;
      }
      MsiString::MsiString((MsiString *)&v14, (const unsigned __int16 *)hMem);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v14 + 200LL))(v14, 3, L"\\\\") != 1
        || (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v14 + 200LL))(
             v14,
             3,
             L"\\\\?\\") )
      {
        v24 = 0;
        memset_0(v25, 0, sizeof(v25));
        if ( (int)StringCchPrintfW(&v24, 0x190u, L"%c:\\Windows\\SystemTemp", Buffer[0]) < 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: StringCchPrintf failure in CMsiEnvironmentBlock::InitializeFromSystemEnvironment";
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TMP", &v24) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TMP";
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TEMP", &v24) )
        {
          if ( !g_dmDiagnosticMode )
            goto LABEL_42;
          v10 = "ERROR: Failed to set environment variable: TEMP";
          goto LABEL_41;
        }
      }
      else
      {
        if ( !CMsiEnvironmentBlock::Set(this, L"TMP", (const unsigned __int16 *)hMem) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TMP when it is remote path";
LABEL_41:
            DebugString(9, 0, 0, v10, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v11, v12);
            goto LABEL_42;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TEMP", (const unsigned __int16 *)hMem) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TEMP when it is remote path";
            goto LABEL_41;
          }
LABEL_42:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          goto LABEL_43;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v20 > 261 )
        GlobalFree(hMem);
    }
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Current environment block after setting user environment variables",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v11,
      v12);
  DumpEnvironment(*(const unsigned __int16 **)this);
  return 1;
}

```

## disassembly

```asm
0x1801c4324  mov     [rsp-8+arg_10], rbx
0x1801c4329  mov     [rsp-8+arg_18], rsi
0x1801c432e  push    rbp
0x1801c432f  push    rdi
0x1801c4330  push    r14
0x1801c4332  lea     rbp, [rsp-0E50h]
0x1801c433a  sub     rsp, 0F50h
0x1801c4341  mov     rax, cs:__security_cookie
0x1801c4348  xor     rax, rsp
0x1801c434b  mov     [rbp+0E60h+var_20], rax
0x1801c4352  mov     rdi, rdx
0x1801c4355  mov     rbx, rcx
0x1801c4358  mov     dl, 1; bool
0x1801c435a  call    ?InitializeFromEnvironment@CMsiEnvironmentBlock@@AEAA_N_N@Z; CMsiEnvironmentBlock::InitializeFromEnvironment(bool)
0x1801c435f  xor     esi, esi
0x1801c4361  test    al, al
0x1801c4363  jz      loc_1801C44B3
0x1801c4369  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801c4370  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1801c4375  mov     rcx, rax; void *
0x1801c4378  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801c437d  test    al, al
0x1801c437f  jnz     loc_1801C483B
0x1801c4385  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801c438c  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1801c4391  test    rax, rax
0x1801c4394  jz      loc_1801C483B
0x1801c439a  lea     rcx, [rsp+0F60h+var_EF0]
0x1801c439f  mov     [rsp+0F60h+cchName], 1F4h
0x1801c43a7  mov     [rsp+0F60h+ReturnLength], rcx; ReturnLength
0x1801c43ac  lea     r9d, [rsi+58h]; TokenInformationLength
0x1801c43b0  mov     rcx, rax; TokenHandle
0x1801c43b3  mov     [rsp+0F60h+var_EE8], 190h
0x1801c43bb  lea     r8, [rbp+0E60h+TokenInformation]; TokenInformation
0x1801c43c2  mov     [rsp+0F60h+var_EF0], esi
0x1801c43c6  lea     edx, [rsi+1]; TokenInformationClass
0x1801c43c9  call    cs:__imp_GetTokenInformation
0x1801c43cf  test    eax, eax
0x1801c43d1  jnz     short loc_1801C43F1
0x1801c43d3  call    cs:__imp_GetLastError
0x1801c43d9  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c43df  jz      loc_1801C44B3
0x1801c43e5  lea     r9, aErrorGettokeni; "ERROR: GetTokenInformation failed with "...
0x1801c43ec  jmp     loc_1801C4476
0x1801c43f1  mov     rdx, [rbp+0E60h+TokenInformation]; Sid
0x1801c43f8  lea     rax, [rsp+0F60h+var_EEC]
0x1801c43fd  mov     [rsp+0F60h+peUse], rax; peUse
0x1801c4402  lea     r9, [rsp+0F60h+cchName]; cchName
0x1801c4407  lea     rax, [rsp+0F60h+var_EE8]
0x1801c440c  mov     [rsp+0F60h+var_EEC], esi
0x1801c4410  mov     [rsp+0F60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1801c4415  lea     r8, [rbp+0E60h+Name]; Name
0x1801c441c  lea     rax, [rbp+0E60h+ReferencedDomainName]
0x1801c4423  xor     ecx, ecx; lpSystemName
0x1801c4425  mov     [rsp+0F60h+ReturnLength], rax; ReferencedDomainName
0x1801c442a  call    cs:__imp_LookupAccountSidW
0x1801c4430  test    eax, eax
0x1801c4432  jnz     short loc_1801C444B
0x1801c4434  call    cs:__imp_GetLastError
0x1801c443a  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c4440  jz      short loc_1801C44B3
0x1801c4442  lea     r9, aErrorLookupacc; "ERROR: LookupAccountSid failed with err"...
0x1801c4449  jmp     short loc_1801C4476
0x1801c444b  mov     edx, 104h; uSize
0x1801c4450  lea     rcx, [rbp+0E60h+Buffer]; lpBuffer
0x1801c4457  call    cs:__imp_GetSystemDirectoryW
0x1801c445d  test    eax, eax
0x1801c445f  jnz     short loc_1801C44DC
0x1801c4461  call    cs:__imp_GetLastError
0x1801c4467  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c446d  jz      short loc_1801C44B3
0x1801c446f  lea     r9, aErrorGetsystem; "ERROR: GetSystemDirectory failed with e"...
0x1801c4476  mov     [rsp+0F60h+var_F08], rsi; void *
0x1801c447b  lea     rcx, aNull; "(NULL)"
0x1801c4482  mov     [rsp+0F60h+var_F10], esi; unsigned int
0x1801c4486  xor     edx, edx; unsigned __int16
0x1801c4488  mov     [rsp+0F60h+var_F18], rcx; unsigned __int16 *
0x1801c448d  xor     r8d, r8d; int
0x1801c4490  mov     [rsp+0F60h+var_F20], rcx; unsigned __int16 *
0x1801c4495  mov     [rsp+0F60h+var_F28], rcx; unsigned __int16 *
0x1801c449a  mov     [rsp+0F60h+peUse], rcx; unsigned __int16 *
0x1801c449f  mov     [rsp+0F60h+cchReferencedDomainName], rcx; unsigned __int16 *
0x1801c44a4  lea     ecx, [rdx+9]; int
0x1801c44a7  mov     eax, eax
0x1801c44a9  mov     [rsp+0F60h+ReturnLength], rax; unsigned __int16 *
0x1801c44ae  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801c44b3  xor     al, al
0x1801c44b5  mov     rcx, [rbp+0E60h+var_20]
0x1801c44bc  xor     rcx, rsp; StackCookie
0x1801c44bf  call    __security_check_cookie
0x1801c44c4  lea     r11, [rsp+0F60h+var_10]
0x1801c44cc  mov     rbx, [r11+30h]
0x1801c44d0  mov     rsi, [r11+38h]
0x1801c44d4  mov     rsp, r11
0x1801c44d7  pop     r14
0x1801c44d9  pop     rdi
0x1801c44da  pop     rbp
0x1801c44db  retn
0x1801c44dc  mov     r14d, 105h
0x1801c44e2  lea     rax, [rbp+0E60h+var_ED0]
0x1801c44e6  lea     r8, [rbp+0E60h+hMem]
0x1801c44ea  mov     [rbp+0E60h+var_ED8], r14d
0x1801c44ee  lea     rdx, aUserprofile_0; "USERPROFILE"
0x1801c44f5  mov     [rbp+0E60h+hMem], rax
0x1801c44f9  mov     rcx, rdi
0x1801c44fc  mov     [rbp+0E60h+var_ED4], r14d
0x1801c4500  call    ?Get@CMsiEnvironmentBlock@@QEBA_NPEBGAEAV?$CAPITempBufferRef@G@@@Z; CMsiEnvironmentBlock::Get(ushort const *,CAPITempBufferRef<ushort> &)
0x1801c4505  test    al, al
0x1801c4507  jnz     short loc_1801C4553
0x1801c4509  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c450f  jz      loc_1801C47C2
0x1801c4515  lea     rax, aNull_0; "(NULL)"
0x1801c451c  xor     edx, edx; unsigned __int16
0x1801c451e  mov     [rsp+0F60h+var_F18], rax; char *
0x1801c4523  lea     r9, aErrorFailedToG; "ERROR: Failed to get environment variab"...
0x1801c452a  mov     [rsp+0F60h+var_F20], rax; char *
0x1801c452f  xor     r8d, r8d; int
0x1801c4532  mov     [rsp+0F60h+var_F28], rax; char *
0x1801c4537  mov     [rsp+0F60h+peUse], rax; char *
0x1801c453c  lea     ecx, [rdx+9]; int
0x1801c453f  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801c4544  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801c4549  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c454e  jmp     loc_1801C47C2
0x1801c4553  mov     rdx, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801c4557  lea     rcx, [rsp+0F60h+var_F00]; this
0x1801c455c  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801c4561  mov     rcx, [rsp+0F60h+var_F00]
0x1801c4566  lea     r8, asc_1802AED68; "\\\\"
0x1801c456d  mov     edx, 3
0x1801c4572  mov     rax, [rcx]
0x1801c4575  mov     rax, [rax+0C8h]
0x1801c457c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4581  cmp     eax, 1
0x1801c4584  jnz     short loc_1801C45D6
0x1801c4586  mov     rcx, [rsp+0F60h+var_F00]
0x1801c458b  lea     r8, asc_1802AED70; "\\\\?\\"
0x1801c4592  mov     edx, 3
0x1801c4597  mov     rax, [rcx]
0x1801c459a  mov     rax, [rax+0C8h]
0x1801c45a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c45a6  test    eax, eax
0x1801c45a8  jnz     short loc_1801C45D6
0x1801c45aa  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801c45ae  lea     rdx, aUserprofile_0; "USERPROFILE"
0x1801c45b5  mov     rcx, rbx; this
0x1801c45b8  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c45bd  test    al, al
0x1801c45bf  jnz     short loc_1801C45D6
0x1801c45c1  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c45c7  jz      loc_1801C47B1
0x1801c45cd  lea     r9, aErrorFailedToS_3; "ERROR: Failed to set environment variab"...
0x1801c45d4  jmp     short loc_1801C4604
0x1801c45d6  lea     r8, [rbp+0E60h+hMem]
0x1801c45da  mov     [rbp+0E60h+var_ED4], r14d
0x1801c45de  lea     rdx, aTmp; "TMP"
0x1801c45e5  mov     rcx, rdi
0x1801c45e8  call    ?Get@CMsiEnvironmentBlock@@QEBA_NPEBGAEAV?$CAPITempBufferRef@G@@@Z; CMsiEnvironmentBlock::Get(ushort const *,CAPITempBufferRef<ushort> &)
0x1801c45ed  test    al, al
0x1801c45ef  jnz     short loc_1801C463B
0x1801c45f1  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c45f7  jz      loc_1801C47B1
0x1801c45fd  lea     r9, aErrorFailedToG_1; "ERROR: Failed to get environment variab"...
0x1801c4604  lea     rax, aNull_0; "(NULL)"
0x1801c460b  xor     edx, edx; unsigned __int16
0x1801c460d  mov     [rsp+0F60h+var_F18], rax; char *
0x1801c4612  xor     r8d, r8d; int
0x1801c4615  mov     [rsp+0F60h+var_F20], rax; char *
0x1801c461a  mov     [rsp+0F60h+var_F28], rax; char *
0x1801c461f  mov     [rsp+0F60h+peUse], rax; char *
0x1801c4624  lea     ecx, [rdx+9]; int
0x1801c4627  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801c462c  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801c4631  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c4636  jmp     loc_1801C47B1
0x1801c463b  mov     rdx, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801c463f  lea     rcx, [rsp+0F60h+var_EF8]; this
0x1801c4644  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801c4649  mov     rcx, [rsp+0F60h+var_EF8]
0x1801c464e  lea     r8, asc_1802AED68; "\\\\"
0x1801c4655  mov     edx, 3
0x1801c465a  mov     rax, [rcx]
0x1801c465d  mov     rax, [rax+0C8h]
0x1801c4664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4669  cmp     eax, 1
0x1801c466c  jnz     loc_1801C46F5
0x1801c4672  mov     rcx, [rsp+0F60h+var_EF8]
0x1801c4677  lea     r8, asc_1802AED70; "\\\\?\\"
0x1801c467e  mov     edx, 3
0x1801c4683  mov     rax, [rcx]
0x1801c4686  mov     rax, [rax+0C8h]
0x1801c468d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4692  test    eax, eax
0x1801c4694  jnz     short loc_1801C46F5
0x1801c4696  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801c469a  lea     rdx, aTmp; "TMP"
0x1801c46a1  mov     rcx, rbx; this
0x1801c46a4  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c46a9  test    al, al
0x1801c46ab  jnz     short loc_1801C46C5
0x1801c46ad  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c46b3  jz      loc_1801C47A0
0x1801c46b9  lea     r9, aErrorFailedToS; "ERROR: Failed to set environment variab"...
0x1801c46c0  jmp     loc_1801C476E
0x1801c46c5  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801c46c9  lea     rdx, aTemp; "TEMP"
0x1801c46d0  mov     rcx, rbx; this
0x1801c46d3  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c46d8  test    al, al
0x1801c46da  jnz     loc_1801C4809
0x1801c46e0  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c46e6  jz      loc_1801C47A0
0x1801c46ec  lea     r9, aErrorFailedToS_0; "ERROR: Failed to set environment variab"...
0x1801c46f3  jmp     short loc_1801C476E
0x1801c46f5  xor     edx, edx; Val
0x1801c46f7  mov     [rbp+0E60h+var_C60], si
0x1801c46fe  mov     r8d, 31Eh; Size
0x1801c4704  lea     rcx, [rbp+0E60h+var_C5E]; void *
0x1801c470b  call    memset_0
0x1801c4710  movzx   r9d, [rbp+0E60h+Buffer]
0x1801c4718  lea     r8, aCWindowsSystem; "%c:\\Windows\\SystemTemp"
0x1801c471f  mov     edx, 190h; unsigned __int64
0x1801c4724  lea     rcx, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801c472b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801c4730  test    eax, eax
0x1801c4732  jns     short loc_1801C4745
0x1801c4734  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c473a  jz      short loc_1801C47A0
0x1801c473c  lea     r9, aErrorStringcch_0; "ERROR: StringCchPrintf failure in CMsiE"...
0x1801c4743  jmp     short loc_1801C476E
0x1801c4745  lea     r8, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801c474c  mov     rcx, rbx; this
0x1801c474f  lea     rdx, aTmp; "TMP"
0x1801c4756  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c475b  test    al, al
0x1801c475d  jnz     short loc_1801C47DB
0x1801c475f  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c4765  jz      short loc_1801C47A0
0x1801c4767  lea     r9, aErrorFailedToS_2; "ERROR: Failed to set environment variab"...
0x1801c476e  lea     rax, aNull_0; "(NULL)"
0x1801c4775  xor     edx, edx; unsigned __int16
0x1801c4777  mov     [rsp+0F60h+var_F18], rax; char *
0x1801c477c  xor     r8d, r8d; int
0x1801c477f  mov     [rsp+0F60h+var_F20], rax; char *
0x1801c4784  mov     [rsp+0F60h+var_F28], rax; char *
0x1801c4789  mov     [rsp+0F60h+peUse], rax; char *
0x1801c478e  lea     ecx, [rdx+9]; int
0x1801c4791  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801c4796  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801c479b  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c47a0  mov     rcx, [rsp+0F60h+var_EF8]
0x1801c47a5  mov     rax, [rcx]
0x1801c47a8  mov     rax, [rax+10h]
0x1801c47ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c47b1  mov     rcx, [rsp+0F60h+var_F00]
0x1801c47b6  mov     rax, [rcx]
0x1801c47b9  mov     rax, [rax+10h]
0x1801c47bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c47c2  cmp     [rbp+0E60h+var_ED8], r14d
0x1801c47c6  jle     loc_1801C44B3
0x1801c47cc  mov     rcx, [rbp+0E60h+hMem]; hMem
0x1801c47d0  call    cs:__imp_GlobalFree
0x1801c47d6  jmp     loc_1801C44B3
0x1801c47db  lea     r8, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801c47e2  mov     rcx, rbx; this
0x1801c47e5  lea     rdx, aTemp; "TEMP"
0x1801c47ec  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c47f1  test    al, al
0x1801c47f3  jnz     short loc_1801C4809
0x1801c47f5  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c47fb  jz      short loc_1801C47A0
0x1801c47fd  lea     r9, aErrorFailedToS_1; "ERROR: Failed to set environment variab"...
0x1801c4804  jmp     loc_1801C476E
0x1801c4809  mov     rcx, [rsp+0F60h+var_EF8]
0x1801c480e  mov     rax, [rcx]
0x1801c4811  mov     rax, [rax+10h]
0x1801c4815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c481a  mov     rcx, [rsp+0F60h+var_F00]
0x1801c481f  mov     rax, [rcx]
0x1801c4822  mov     rax, [rax+10h]
0x1801c4826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c482b  cmp     [rbp+0E60h+var_ED8], r14d
0x1801c482f  jle     short loc_1801C483B
0x1801c4831  mov     rcx, [rbp+0E60h+hMem]; hMem
0x1801c4835  call    cs:__imp_GlobalFree
0x1801c483b  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801c4841  jz      short loc_1801C487C
0x1801c4843  lea     rax, aNull_0; "(NULL)"
0x1801c484a  xor     edx, edx; unsigned __int16
0x1801c484c  mov     [rsp+0F60h+var_F18], rax; char *
0x1801c4851  lea     r9, aCurrentEnviron; "Current environment block after setting"...
0x1801c4858  mov     [rsp+0F60h+var_F20], rax; char *
0x1801c485d  xor     r8d, r8d; int
0x1801c4860  mov     [rsp+0F60h+var_F28], rax; char *
0x1801c4865  mov     [rsp+0F60h+peUse], rax; char *
0x1801c486a  lea     ecx, [rdx+9]; int
0x1801c486d  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801c4872  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801c4877  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c487c  mov     rcx, [rbx]; unsigned __int16 *
  ... truncated ...
```
