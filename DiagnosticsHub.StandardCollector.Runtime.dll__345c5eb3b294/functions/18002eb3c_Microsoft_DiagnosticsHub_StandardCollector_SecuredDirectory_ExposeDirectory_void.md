# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::ExposeDirectory(void)

- ea: `0x18002eb3c`
- end: `0x18002f0f9`
- name: `?ExposeDirectory@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJXZ`
- size: `1469`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002a80c`

## callees

- `0x18002d5d4`
- `0x18002eb3c`
- `0x18002f63c`
- `0x18002fb2c`
- `0x18002fc38`
- `0x18003070c`
- `0x180031284`
- `0x1800315c8`
- `0x1800316c4`
- `0x180043394`
- `0x180049b50`
- `0x18004ad26`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002eff3`
- `KERNEL32!SetLastError` at `0x18002eff3`
- `KERNEL32!GetCurrentThread` at `0x18002ebc4`
- `KERNEL32!GetCurrentThread` at `0x18002ebc4`
- `KERNEL32!CreateFileW` at `0x18002ef4b`
- `KERNEL32!CreateFileW` at `0x18002ef4b`
- `KERNEL32!LeaveCriticalSection` at `0x18002f0c0`
- `KERNEL32!LeaveCriticalSection` at `0x18002f0c0`
- `KERNEL32!EnterCriticalSection` at `0x18002eb97`
- `KERNEL32!EnterCriticalSection` at `0x18002eb97`
- `KERNEL32!CloseHandle` at `0x18002ee3c`
- `KERNEL32!CloseHandle` at `0x18002efab`
- `KERNEL32!CloseHandle` at `0x18002f00b`
- `KERNEL32!CloseHandle` at `0x18002f024`
- `KERNEL32!CloseHandle` at `0x18002f05a`
- `KERNEL32!CloseHandle` at `0x18002f0b3`
- `KERNEL32!CloseHandle` at `0x18002ee3c`
- `KERNEL32!CloseHandle` at `0x18002efab`
- `KERNEL32!CloseHandle` at `0x18002f00b`
- `KERNEL32!CloseHandle` at `0x18002f024`
- `KERNEL32!CloseHandle` at `0x18002f05a`
- `KERNEL32!CloseHandle` at `0x18002f0b3`
- `KERNEL32!GetLastError` at `0x18002ebe0`
- `KERNEL32!GetLastError` at `0x18002ec37`
- `KERNEL32!GetLastError` at `0x18002ec42`
- `KERNEL32!GetLastError` at `0x18002eca0`
- `KERNEL32!GetLastError` at `0x18002ef5a`
- `KERNEL32!GetLastError` at `0x18002f03b`
- `KERNEL32!GetLastError` at `0x18002ebe0`
- `KERNEL32!GetLastError` at `0x18002ec37`
- `KERNEL32!GetLastError` at `0x18002ec42`
- `KERNEL32!GetLastError` at `0x18002eca0`
- `KERNEL32!GetLastError` at `0x18002ef5a`
- `KERNEL32!GetLastError` at `0x18002f03b`
- `ole32!CoImpersonateClient` at `0x18002ebaf`
- `ole32!CoImpersonateClient` at `0x18002ebaf`
- `ole32!CoRevertToSelf` at `0x18002ebe8`
- `ole32!CoRevertToSelf` at `0x18002ebe8`
- `ADVAPI32!OpenThreadToken` at `0x18002ebd8`
- `ADVAPI32!OpenThreadToken` at `0x18002ebd8`
- `ADVAPI32!GetTokenInformation` at `0x18002ec31`
- `ADVAPI32!GetTokenInformation` at `0x18002ec96`
- `ADVAPI32!GetTokenInformation` at `0x18002ec31`
- `ADVAPI32!GetTokenInformation` at `0x18002ec96`
- `ADVAPI32!IsValidSid` at `0x18002ed04`
- `ADVAPI32!IsValidSid` at `0x18002ed1f`
- `ADVAPI32!IsValidSid` at `0x18002ede5`
- `ADVAPI32!IsValidSid` at `0x18002ee01`
- `ADVAPI32!IsValidSid` at `0x18002ed04`
- `ADVAPI32!IsValidSid` at `0x18002ed1f`
- `ADVAPI32!IsValidSid` at `0x18002ede5`
- `ADVAPI32!IsValidSid` at `0x18002ee01`
- `ADVAPI32!EqualSid` at `0x18002ed37`
- `ADVAPI32!EqualSid` at `0x18002ee1a`
- `ADVAPI32!EqualSid` at `0x18002ed37`
- `ADVAPI32!EqualSid` at `0x18002ee1a`
- `ADVAPI32!SetSecurityInfo` at `0x18002efe9`
- `ADVAPI32!SetSecurityInfo` at `0x18002efe9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f0a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f0a3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002ec61`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002ec61`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::ExposeDirectory(
        Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *this)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  int v4; // r14d
  HANDLE CurrentThread; // rax
  BOOL v6; // esi
  signed int LastError; // ebx
  signed int v8; // eax
  const struct _SID **v9; // rbx
  signed int v10; // eax
  const unsigned __int16 *v11; // r8
  int AppContainerSid; // eax
  bool v13; // r13
  HANDLE *v14; // rsi
  int v15; // eax
  int v16; // r12d
  HANDLE v17; // rax
  unsigned __int8 v18; // r9
  bool v19; // si
  unsigned __int8 v20; // r9
  unsigned __int8 v21; // r9
  unsigned __int8 v22; // r9
  HANDLE FileW; // rax
  void *v24; // r12
  signed int v25; // eax
  void *v26; // rcx
  bool v27; // si
  ACL *PACL; // rax
  DWORD v29; // esi
  void *v30; // rcx
  void *v31; // rcx
  signed int v32; // eax
  PDWORD ReturnLength; // [rsp+28h] [rbp-E0h]
  _BYTE v34[128]; // [rsp+68h] [rbp-A0h] BYREF
  DWORD TokenInformationLength; // [rsp+E8h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v37[3]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v38; // [rsp+110h] [rbp+8h]
  __int64 v39; // [rsp+120h] [rbp+18h]
  __int64 v40; // [rsp+128h] [rbp+20h]
  _BYTE v41[8]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE pSid2[120]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v43[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE pSid1[120]; // [rsp+1C0h] [rbp+B8h] BYREF
  _BYTE v45[8]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE pSid[120]; // [rsp+240h] [rbp+138h] BYREF

  if ( !*((_BYTE *)this + 8) )
    return 1;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  if ( *((_BYTE *)this + 8) )
  {
    v4 = CoImpersonateClient();
    if ( v4 >= 0 )
    {
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      v6 = OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle);
      LastError = GetLastError();
      v4 = CoRevertToSelf();
      if ( v4 >= 0 )
      {
        if ( v6 )
        {
          TokenInformationLength = 0;
          GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
          if ( GetLastError() == 122 )
          {
            v9 = (const struct _SID **)malloc(TokenInformationLength);
            if ( v9 )
            {
              if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
              {
                memset_0(v45, 0, 0x78u);
                ATL::CSid::CSid((ATL::CSid *)v45, *v9, v11);
                if ( this != (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)-32LL
                  && pSid[68]
                  && IsValidSid(pSid)
                  && *((_BYTE *)this + 100)
                  && IsValidSid((char *)this + 32)
                  && EqualSid(pSid, (char *)this + 32) )
                {
                  memset_0(v43, 0, 0x78u);
                  ATL::CSid::CSid((ATL::CSid *)v43);
                  AppContainerSid = DiagHubCommon::Security::GetAppContainerSid(
                                      (struct ATL::CHandle *)&TokenHandle,
                                      (struct ATL::CSid *)v43);
                  if ( AppContainerSid >= 0 )
                  {
                    v13 = AppContainerSid == 0;
                    memset_0(v41, 0, 0x78u);
                    ATL::CSid::CSid((ATL::CSid *)v41);
                    v14 = (HANDLE *)((char *)this + 16);
                    v15 = DiagHubCommon::Security::GetAppContainerSid(
                            (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)((char *)this + 16),
                            (struct ATL::CSid *)v41);
                    v16 = v15;
                    if ( v15 >= 0 )
                    {
                      if ( v13 == (v15 == 0)
                        && (v15
                         || pSid1[68] && IsValidSid(pSid1) && pSid2[68] && IsValidSid(pSid2) && EqualSid(pSid1, pSid2)) )
                      {
                        if ( v14 != &TokenHandle )
                        {
                          _mm_lfence();
                          if ( *v14 )
                            CloseHandle(*v14);
                          v17 = TokenHandle;
                          TokenHandle = 0;
                          *v14 = v17;
                        }
                        v37[1] = 0;
                        v37[2] = 0x200000000LL;
                        v37[0] = &ATL::CDacl::`vftable';
                        v38 = 0;
                        v39 = 0;
                        v40 = 0;
                        LODWORD(ReturnLength) = 544;
                        ATL::CSid::CSid(
                          (ATL::CSid *)v34,
                          (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
                          2u,
                          32,
                          ReturnLength);
                        v19 = ATL::CDacl::AddAllowedAce(
                                (ATL::CDacl *)v37,
                                (const struct ATL::CSid *)v34,
                                0x10000000u,
                                v18);
                        ATL::CSid::~CSid((ATL::CSid *)v34);
                        if ( v19
                          && ATL::CDacl::AddAllowedAce(
                               (ATL::CDacl *)v37,
                               (const struct ATL::CSid *)&qword_180077070,
                               0x10000000u,
                               v20)
                          && (_mm_lfence(),
                              ATL::CDacl::AddAllowedAce(
                                (ATL::CDacl *)v37,
                                (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)((char *)this + 24),
                                0xE01301EF,
                                v21))
                          && (v16
                           || ATL::CDacl::AddAllowedAce(
                                (ATL::CDacl *)v37,
                                (const struct ATL::CSid *)v41,
                                0x10000000u,
                                v22))
                          && (_mm_lfence(),
                              *((_BYTE *)this + 8) = 0,
                              FileW = CreateFileW(*(LPCWSTR *)this, 0x60000u, 1u, 0, 3u, 0x2000000u, 0),
                              v24 = FileW,
                              FileW != (HANDLE)-1LL) )
                        {
                          _mm_lfence();
                          if ( (unsigned int)anonymous_namespace_::ValidateSamePath(*((_QWORD *)this + 20), FileW) )
                          {
                            v4 = -2147024891;
                          }
                          else
                          {
                            _mm_lfence();
                            v26 = (void *)*((_QWORD *)this + 20);
                            if ( v26 )
                            {
                              CloseHandle(v26);
                              *((_QWORD *)this + 20) = 0;
                            }
                            if ( v24 )
                            {
                              PACL = (ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)v37);
                              v29 = SetSecurityInfo(v24, SE_FILE_OBJECT, 0x20000004u, 0, 0, PACL, 0);
                              SetLastError(v29);
                              v27 = v29 == 0;
                            }
                            else
                            {
                              v27 = 0;
                            }
                            v30 = (void *)*((_QWORD *)this + 18);
                            if ( v30 )
                            {
                              CloseHandle(v30);
                              *((_QWORD *)this + 18) = 0;
                            }
                            v31 = (void *)*((_QWORD *)this + 19);
                            if ( v31 )
                            {
                              CloseHandle(v31);
                              *((_QWORD *)this + 19) = 0;
                            }
                            if ( v27 )
                            {
                              v4 = 0;
                            }
                            else
                            {
                              v32 = GetLastError();
                              v4 = (unsigned __int16)v32 | 0x80070000;
                              if ( v32 <= 0 )
                                v4 = v32;
                            }
                          }
                          if ( v24 )
                            CloseHandle(v24);
                        }
                        else
                        {
                          v25 = GetLastError();
                          v4 = (unsigned __int16)v25 | 0x80070000;
                          if ( v25 <= 0 )
                            v4 = v25;
                        }
                        ATL::CDacl::~CDacl((ATL::CDacl *)v37);
                      }
                      else
                      {
                        v4 = -2147024891;
                      }
                    }
                    else
                    {
                      v4 = v15;
                    }
                    ATL::CSid::~CSid((ATL::CSid *)v41);
                  }
                  else
                  {
                    v4 = AppContainerSid;
                  }
                  ATL::CSid::~CSid((ATL::CSid *)v43);
                }
                else
                {
                  v4 = -2147024891;
                }
                ATL::CSid::~CSid((ATL::CSid *)v45);
              }
              else
              {
                v10 = GetLastError();
                v4 = (unsigned __int16)v10 | 0x80070000;
                if ( v10 <= 0 )
                  v4 = v10;
              }
            }
            else
            {
              v4 = -2147024882;
            }
            free(v9);
          }
          else
          {
            v8 = GetLastError();
            v4 = (unsigned __int16)v8 | 0x80070000;
            if ( v8 <= 0 )
              v4 = v8;
          }
        }
        else
        {
          v4 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v4 = LastError;
        }
      }
      if ( TokenHandle )
      {
        CloseHandle(TokenHandle);
        TokenHandle = 0;
      }
    }
  }
  else
  {
    v4 = 1;
  }
  LeaveCriticalSection(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002eb3c  mov     rax, rsp
0x18002eb3f  mov     [rax+10h], rbx
0x18002eb43  mov     [rax+18h], rsi
0x18002eb47  mov     [rax+20h], rdi
0x18002eb4b  push    rbp
0x18002eb4c  push    r12
0x18002eb4e  push    r13
0x18002eb50  push    r14
0x18002eb52  push    r15
0x18002eb54  lea     rbp, [rax-1E8h]
0x18002eb5b  sub     rsp, 2C0h
0x18002eb62  mov     rax, cs:__security_cookie
0x18002eb69  xor     rax, rsp
0x18002eb6c  mov     [rbp+1E0h+var_30], rax
0x18002eb73  mov     r15, rcx
0x18002eb76  xor     r13d, r13d
0x18002eb79  cmp     [rcx+8], r13b
0x18002eb7d  jnz     short loc_18002EB88
0x18002eb7f  lea     eax, [r13+1]
0x18002eb83  jmp     loc_18002F0C9
0x18002eb88  lea     rdi, [rcx+0A8h]
0x18002eb8f  mov     [rsp+2E0h+var_2A0], rdi
0x18002eb94  mov     rcx, rdi; lpCriticalSection
0x18002eb97  call    cs:__imp_EnterCriticalSection
0x18002eb9d  nop
0x18002eb9e  cmp     [r15+8], r13b
0x18002eba2  jnz     short loc_18002EBAF
0x18002eba4  mov     r14d, 1
0x18002ebaa  jmp     loc_18002F0BD
0x18002ebaf  call    cs:__imp_CoImpersonateClient
0x18002ebb5  mov     r14d, eax
0x18002ebb8  test    eax, eax
0x18002ebba  js      loc_18002F0BD
0x18002ebc0  mov     [rbp+1E0h+TokenHandle], r13
0x18002ebc4  call    cs:__imp_GetCurrentThread
0x18002ebca  mov     rcx, rax; ThreadHandle
0x18002ebcd  lea     r9, [rbp+1E0h+TokenHandle]; TokenHandle
0x18002ebd1  xor     r8d, r8d; OpenAsSelf
0x18002ebd4  lea     edx, [r8+0Ch]; DesiredAccess
0x18002ebd8  call    cs:__imp_OpenThreadToken
0x18002ebde  mov     esi, eax
0x18002ebe0  call    cs:__imp_GetLastError
0x18002ebe6  mov     ebx, eax
0x18002ebe8  call    cs:__imp_CoRevertToSelf
0x18002ebee  mov     r14d, eax
0x18002ebf1  test    eax, eax
0x18002ebf3  js      loc_18002F0AA
0x18002ebf9  test    esi, esi
0x18002ebfb  jnz     short loc_18002EC13
0x18002ebfd  movzx   r14d, bx
0x18002ec01  or      r14d, 80070000h
0x18002ec08  test    ebx, ebx
0x18002ec0a  cmovle  r14d, ebx
0x18002ec0e  jmp     loc_18002F0AA
0x18002ec13  mov     [rbp+1E0h+TokenInformationLength], r13d
0x18002ec17  lea     rax, [rbp+1E0h+TokenInformationLength]
0x18002ec1b  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x18002ec20  xor     r9d, r9d; TokenInformationLength
0x18002ec23  xor     r8d, r8d; TokenInformation
0x18002ec26  lea     r14d, [r9+1]
0x18002ec2a  mov     edx, r14d; TokenInformationClass
0x18002ec2d  mov     rcx, [rbp+1E0h+TokenHandle]; TokenHandle
0x18002ec31  call    cs:__imp_GetTokenInformation
0x18002ec37  call    cs:__imp_GetLastError
0x18002ec3d  cmp     eax, 7Ah ; 'z'
0x18002ec40  jz      short loc_18002EC5E
0x18002ec42  call    cs:__imp_GetLastError
0x18002ec48  movzx   r14d, ax
0x18002ec4c  or      r14d, 80070000h
0x18002ec53  test    eax, eax
0x18002ec55  cmovle  r14d, eax
0x18002ec59  jmp     loc_18002F0AA
0x18002ec5e  mov     ecx, [rbp+1E0h+TokenInformationLength]; Size
0x18002ec61  call    cs:__imp_malloc
0x18002ec67  mov     rbx, rax
0x18002ec6a  mov     [rsp+2E0h+var_298], rax
0x18002ec6f  test    rax, rax
0x18002ec72  jnz     short loc_18002EC7F
0x18002ec74  mov     r14d, 8007000Eh
0x18002ec7a  jmp     loc_18002F0A0
0x18002ec7f  lea     rax, [rbp+1E0h+TokenInformationLength]
0x18002ec83  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x18002ec88  mov     r9d, [rbp+1E0h+TokenInformationLength]; TokenInformationLength
0x18002ec8c  mov     r8, rbx; TokenInformation
0x18002ec8f  mov     edx, r14d; TokenInformationClass
0x18002ec92  mov     rcx, [rbp+1E0h+TokenHandle]; TokenHandle
0x18002ec96  call    cs:__imp_GetTokenInformation
0x18002ec9c  test    eax, eax
0x18002ec9e  jnz     short loc_18002ECBC
0x18002eca0  call    cs:__imp_GetLastError
0x18002eca6  movzx   r14d, ax
0x18002ecaa  or      r14d, 80070000h
0x18002ecb1  test    eax, eax
0x18002ecb3  cmovle  r14d, eax
0x18002ecb7  jmp     loc_18002F0A0
0x18002ecbc  mov     r12d, 78h ; 'x'
0x18002ecc2  mov     r8d, r12d; Size
0x18002ecc5  xor     edx, edx; Val
0x18002ecc7  lea     rcx, [rbp+1E0h+var_B0]; void *
0x18002ecce  call    memset_0
0x18002ecd3  mov     rdx, [rbx]; struct _SID *
0x18002ecd6  lea     rcx, [rbp+1E0h+var_B0]; this
0x18002ecdd  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18002ece2  nop
0x18002ece3  lea     rsi, [r15+20h]
0x18002ece7  test    rsi, rsi
0x18002ecea  jz      loc_18002F08D
0x18002ecf0  cmp     [rbp+1E0h+var_64], r13b
0x18002ecf7  jz      loc_18002F08D
0x18002ecfd  lea     rcx, [rbp+1E0h+pSid]; pSid
0x18002ed04  call    cs:__imp_IsValidSid
0x18002ed0a  test    eax, eax
0x18002ed0c  jz      loc_18002F08D
0x18002ed12  cmp     [r15+64h], r13b
0x18002ed16  jz      loc_18002F08D
0x18002ed1c  mov     rcx, rsi; pSid
0x18002ed1f  call    cs:__imp_IsValidSid
0x18002ed25  test    eax, eax
0x18002ed27  jz      loc_18002F08D
0x18002ed2d  mov     rdx, rsi; pSid2
0x18002ed30  lea     rcx, [rbp+1E0h+pSid]; pSid1
0x18002ed37  call    cs:__imp_EqualSid
0x18002ed3d  test    eax, eax
0x18002ed3f  jz      loc_18002F08D
0x18002ed45  mov     r8d, r12d; Size
0x18002ed48  xor     edx, edx; Val
0x18002ed4a  lea     rcx, [rbp+1E0h+var_130]; void *
0x18002ed51  call    memset_0
0x18002ed56  lea     rcx, [rbp+1E0h+var_130]; this
0x18002ed5d  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002ed62  nop
0x18002ed63  lea     rdx, [rbp+1E0h+var_130]; struct ATL::CSid *
0x18002ed6a  lea     rcx, [rbp+1E0h+TokenHandle]; struct ATL::CHandle *
0x18002ed6e  call    ?GetAppContainerSid@Security@DiagHubCommon@@SAJAEAVCHandle@ATL@@AEAVCSid@4@@Z; DiagHubCommon::Security::GetAppContainerSid(ATL::CHandle &,ATL::CSid &)
0x18002ed73  test    eax, eax
0x18002ed75  jns     short loc_18002ED7F
0x18002ed77  mov     r14d, eax
0x18002ed7a  jmp     loc_18002F07F
0x18002ed7f  setz    r13b
0x18002ed83  mov     r8, r12; Size
0x18002ed86  xor     edx, edx; Val
0x18002ed88  lea     rcx, [rbp+1E0h+var_1B0]; void *
0x18002ed8c  call    memset_0
0x18002ed91  lea     rcx, [rbp+1E0h+var_1B0]; this
0x18002ed95  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002ed9a  nop
0x18002ed9b  lea     rsi, [r15+10h]
0x18002ed9f  lea     rdx, [rbp+1E0h+var_1B0]; struct ATL::CSid *
0x18002eda3  mov     rcx, rsi; struct ATL::CHandle *
0x18002eda6  call    ?GetAppContainerSid@Security@DiagHubCommon@@SAJAEAVCHandle@ATL@@AEAVCSid@4@@Z; DiagHubCommon::Security::GetAppContainerSid(ATL::CHandle &,ATL::CSid &)
0x18002edab  mov     r12d, eax
0x18002edae  test    eax, eax
0x18002edb0  jns     short loc_18002EDBA
0x18002edb2  mov     r14d, eax
0x18002edb5  jmp     loc_18002F072
0x18002edba  test    r12d, r12d
0x18002edbd  setz    al
0x18002edc0  cmp     r13b, al
0x18002edc3  jnz     loc_18002F06C
0x18002edc9  xor     r13d, r13d
0x18002edcc  test    r12d, r12d
0x18002edcf  jnz     short loc_18002EE28
0x18002edd1  cmp     [rbp+1E0h+var_E4], r13b
0x18002edd8  jz      loc_18002F06C
0x18002edde  lea     rcx, [rbp+1E0h+pSid1]; pSid
0x18002ede5  call    cs:__imp_IsValidSid
0x18002edeb  test    eax, eax
0x18002eded  jz      loc_18002F06C
0x18002edf3  cmp     [rbp+1E0h+var_164], r13b
0x18002edf7  jz      loc_18002F06C
0x18002edfd  lea     rcx, [rbp+1E0h+pSid2]; pSid
0x18002ee01  call    cs:__imp_IsValidSid
0x18002ee07  test    eax, eax
0x18002ee09  jz      loc_18002F06C
0x18002ee0f  lea     rdx, [rbp+1E0h+pSid2]; pSid2
0x18002ee13  lea     rcx, [rbp+1E0h+pSid1]; pSid1
0x18002ee1a  call    cs:__imp_EqualSid
0x18002ee20  test    eax, eax
0x18002ee22  jz      loc_18002F06C
0x18002ee28  lea     rax, [rbp+1E0h+TokenHandle]
0x18002ee2c  cmp     rsi, rax
0x18002ee2f  jz      short loc_18002EE4D
0x18002ee31  lfence
0x18002ee34  mov     rcx, [rsi]; hObject
0x18002ee37  test    rcx, rcx
0x18002ee3a  jz      short loc_18002EE42
0x18002ee3c  call    cs:__imp_CloseHandle
0x18002ee42  mov     rax, [rbp+1E0h+TokenHandle]
0x18002ee46  mov     [rbp+1E0h+TokenHandle], r13
0x18002ee4a  mov     [rsi], rax
0x18002ee4d  xorps   xmm0, xmm0
0x18002ee50  xor     eax, eax
0x18002ee52  movups  [rbp+1E0h+var_1F0], xmm0
0x18002ee56  movups  [rbp+1E0h+var_1E0], xmm0
0x18002ee5a  movups  [rbp+1E0h+var_1D0], xmm0
0x18002ee5e  mov     [rbp+1E0h+var_1C0], rax
0x18002ee62  mov     qword ptr [rbp+1E0h+var_1F0+8], r13
0x18002ee66  mov     byte ptr [rbp+1E0h+var_1E0], r13b
0x18002ee6a  lea     r8d, [rax+2]; unsigned __int8
0x18002ee6e  mov     dword ptr [rbp+1E0h+var_1E0+4], r8d
0x18002ee72  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18002ee79  mov     qword ptr [rbp+1E0h+var_1F0], rax
0x18002ee7d  movdqu  [rbp+1E0h+var_1E0+8], xmm0
0x18002ee82  mov     qword ptr [rbp+1E0h+var_1D0+8], r13
0x18002ee86  mov     dword ptr [rbp+1E0h+var_1C0], r13d
0x18002ee8a  mov     dword ptr [rsp+2E0h+ReturnLength], 220h
0x18002ee92  lea     r9d, [r8+1Eh]
0x18002ee96  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x18002ee9d  lea     rcx, [rsp+2E0h+var_280]; this
0x18002eea2  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x18002eea7  nop
0x18002eea8  mov     r8d, 10000000h; unsigned int
0x18002eeae  lea     rdx, [rsp+2E0h+var_280]; struct ATL::CSid *
0x18002eeb3  lea     rcx, [rbp+1E0h+var_1F0]; this
0x18002eeb7  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002eebc  mov     sil, al
0x18002eebf  lea     rcx, [rsp+2E0h+var_280]; this
0x18002eec4  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002eec9  test    sil, sil
0x18002eecc  jz      loc_18002EF5A
0x18002eed2  mov     esi, 10000000h
0x18002eed7  mov     r8d, esi; unsigned int
0x18002eeda  lea     rdx, qword_180077070; struct ATL::CSid *
0x18002eee1  lea     rcx, [rbp+1E0h+var_1F0]; this
0x18002eee5  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002eeea  test    al, al
0x18002eeec  jz      short loc_18002EF5A
0x18002eeee  lfence
0x18002eef1  mov     r8d, 0E01301EFh; unsigned int
0x18002eef7  lea     rdx, [r15+18h]; struct ATL::CSid *
0x18002eefb  lea     rcx, [rbp+1E0h+var_1F0]; this
0x18002eeff  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002ef04  test    al, al
0x18002ef06  jz      short loc_18002EF5A
0x18002ef08  test    r12d, r12d
0x18002ef0b  jnz     short loc_18002EF21
0x18002ef0d  mov     r8d, esi; unsigned int
0x18002ef10  lea     rdx, [rbp+1E0h+var_1B0]; struct ATL::CSid *
0x18002ef14  lea     rcx, [rbp+1E0h+var_1F0]; this
0x18002ef18  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002ef1d  test    al, al
0x18002ef1f  jz      short loc_18002EF5A
0x18002ef21  lfence
0x18002ef24  mov     [r15+8], r13b
0x18002ef28  mov     [rsp+2E0h+hTemplateFile], r13; hTemplateFile
0x18002ef2d  mov     [rsp+2E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002ef35  mov     dword ptr [rsp+2E0h+ReturnLength], 3; dwCreationDisposition
0x18002ef3d  xor     r9d, r9d; lpSecurityAttributes
0x18002ef40  mov     r8d, r14d; dwShareMode
0x18002ef43  mov     edx, 60000h; dwDesiredAccess
0x18002ef48  mov     rcx, [r15]; lpFileName
0x18002ef4b  call    cs:__imp_CreateFileW
0x18002ef51  mov     r12, rax
0x18002ef54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef58  jnz     short loc_18002EF76
0x18002ef5a  call    cs:__imp_GetLastError
0x18002ef60  movzx   r14d, ax
0x18002ef64  or      r14d, 80070000h
0x18002ef6b  test    eax, eax
0x18002ef6d  cmovle  r14d, eax
0x18002ef71  jmp     loc_18002F061
0x18002ef76  lfence
0x18002ef79  mov     [rsp+2E0h+var_290], r12
0x18002ef7e  mov     rdx, r12
0x18002ef81  mov     rcx, [r15+0A0h]
0x18002ef88  call    _anonymous_namespace___ValidateSamePath
0x18002ef8d  test    eax, eax
0x18002ef8f  jz      short loc_18002EF9C
0x18002ef91  mov     r14d, 80070005h
0x18002ef97  jmp     loc_18002F052
0x18002ef9c  lfence
0x18002ef9f  mov     rcx, [r15+0A0h]; hObject
0x18002efa6  test    rcx, rcx
0x18002efa9  jz      short loc_18002EFB8
0x18002efab  call    cs:__imp_CloseHandle
0x18002efb1  mov     [r15+0A0h], r13
0x18002efb8  test    r12, r12
0x18002efbb  jnz     short loc_18002EFC2
0x18002efbd  mov     sil, r13b
0x18002efc0  jmp     short loc_18002EFFF
0x18002efc2  lea     rcx, [rbp+1E0h+var_1F0]; this
0x18002efc6  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18002efcb  mov     [rsp+2E0h+hTemplateFile], r13; pSacl
0x18002efd0  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; pDacl
0x18002efd5  mov     [rsp+2E0h+ReturnLength], r13; psidGroup
0x18002efda  xor     r9d, r9d; psidOwner
0x18002efdd  mov     r8d, 20000004h; SecurityInfo
0x18002efe3  mov     edx, r14d; ObjectType
0x18002efe6  mov     rcx, r12; handle
0x18002efe9  call    cs:__imp_SetSecurityInfo
0x18002efef  mov     esi, eax
0x18002eff1  mov     ecx, eax; dwErrCode
0x18002eff3  call    cs:__imp_SetLastError
0x18002eff9  test    esi, esi
0x18002effb  setz    sil
0x18002efff  mov     rcx, [r15+90h]; hObject
0x18002f006  test    rcx, rcx
0x18002f009  jz      short loc_18002F018
0x18002f00b  call    cs:__imp_CloseHandle
0x18002f011  mov     [r15+90h], r13
  ... truncated ...
```
