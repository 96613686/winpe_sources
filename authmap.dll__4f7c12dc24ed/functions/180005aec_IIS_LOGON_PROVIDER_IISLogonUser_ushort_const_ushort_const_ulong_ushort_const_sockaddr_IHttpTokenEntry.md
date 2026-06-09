# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x180005aec`
- end: `0x180005eb8`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001da0`

## callees

- `0x180001008`
- `0x180004ef8`
- `0x180004fc4`
- `0x180005aec`
- `0x180006d92`
- `0x180006dd0`
- `0x180008010`

## import_xrefs

- `msvcrt!wcschr` at `0x180005c0c`
- `msvcrt!wcschr` at `0x180005c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e04`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b76`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b9e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b76`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b9e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d7e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d8b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d7e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d8b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005dfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e5c`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180005cee`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180005cee`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180005c88`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180005c88`
- `SspiCli!SeciFreeCallContext` at `0x180005e79`
- `SspiCli!SeciFreeCallContext` at `0x180005e79`
- `SspiCli!LsaFreeReturnBuffer` at `0x180005e6c`
- `SspiCli!LsaFreeReturnBuffer` at `0x180005e6c`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::IISLogonUser(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        struct sockaddr *a6,
        struct IHttpTokenEntry **a7)
{
  int CacheKey; // ebx
  int v11; // esi
  const WCHAR *v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r12
  __int64 v16; // rbx
  signed int v17; // eax
  signed int v18; // eax
  _QWORD *v19; // rax
  struct IHttpTokenEntry *v20; // rdi
  HANDLE v21; // rcx
  int v22; // eax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pdwProfileLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszDomain; // [rsp+68h] [rbp-98h]
  const WCHAR *v30; // [rsp+70h] [rbp-90h]
  PVOID Buffer; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpszPassword; // [rsp+80h] [rbp-80h]
  struct IHttpTokenEntry **v33; // [rsp+88h] [rbp-78h]
  _BYTE v34[32]; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v35; // [rsp+B0h] [rbp-50h]
  _BYTE v36[32]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *Str; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v38[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v39[256]; // [rsp+300h] [rbp+200h] BYREF

  lpszPassword = a3;
  v33 = a7;
  TokenHandle = 0;
  Buffer = 0;
  pdwProfileLength = 0;
  v30 = 0;
  memset_0(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v36, v38, 0x100u);
  memset_0(v39, 0, sizeof(v39));
  STRU::STRU((STRU *)v34, v39, 0x100u);
  ReturnLength = 0;
  v26 = 0;
  if ( !a7 )
  {
    CacheKey = -2147024809;
    goto LABEL_49;
  }
  CacheKey = IIS_LOGON_PROVIDER::DetermineUserAndDomain(
               this,
               a2,
               a5,
               (struct STRU *)v36,
               (struct STRU *)v34,
               (int *)&ReturnLength);
  if ( CacheKey < 0 )
    goto LABEL_43;
  v11 = 2;
  if ( ReturnLength )
  {
LABEL_10:
    v12 = v35;
    goto LABEL_11;
  }
  v12 = v35;
  if ( *v35 )
  {
    if ( wcschr(Str, 0x40u) )
    {
      v13 = 2;
      if ( *((_DWORD *)this + 641) )
      {
        lpszDomain = v35;
        v30 = 0;
      }
      else
      {
        lpszDomain = 0;
        v30 = v35;
      }
      goto LABEL_12;
    }
    goto LABEL_10;
  }
LABEL_11:
  v13 = 1;
  lpszDomain = (LPCWSTR)((unsigned __int64)v12 & -(__int64)(*v12 != 0));
LABEL_12:
  if ( !a6 )
    goto LABEL_18;
  if ( a6->sa_family == 2 )
  {
    v14 = 16;
  }
  else
  {
    if ( a6->sa_family != 23 )
      goto LABEL_18;
    v14 = 28;
  }
  CacheKey = SeciAllocateAndSetIPAddress(a6, v14, &v26);
  if ( CacheKey >= 0 )
  {
LABEL_18:
    v15 = lpszPassword;
    v16 = 0;
    do
    {
      if ( LogonUserExW(Str, (&lpszDomain)[v16], v15, a4, 0, &TokenHandle, 0, &Buffer, &pdwProfileLength, 0) )
      {
        v19 = operator new(0x108u);
        v20 = (struct IHttpTokenEntry *)v19;
        if ( !v19 )
        {
          CacheKey = -2147024888;
          goto LABEL_43;
        }
        v19[2] = 0;
        *v19 = &TOKEN_ENTRY::`vftable';
        *((_DWORD *)v19 + 3) = 1;
        v19[15] = &TOKEN_KEY::`vftable';
        v19[3] = 0;
        *((_DWORD *)v19 + 29) = 0;
        STRU::STRU((STRU *)(v19 + 16));
        STRU::STRU((struct IHttpTokenEntry *)((char *)v20 + 184));
        *((_DWORD *)v20 + 65) &= 0xFFFFFFFC;
        *((_DWORD *)v20 + 62) = 0;
        *((_DWORD *)v20 + 63) = 0;
        *((_DWORD *)v20 + 64) = 2;
        *((_DWORD *)v20 + 2) = 1313558356;
        v21 = TokenHandle;
        if ( a4 == 3 || (v22 = 0, a4 == 8) )
          v22 = 1;
        if ( v22 )
        {
          *((_QWORD *)v20 + 2) = TokenHandle;
          v11 = 1;
        }
        else
        {
          *((_QWORD *)v20 + 3) = TokenHandle;
        }
        *((_DWORD *)v20 + 65) |= v11;
        ReturnLength = 84;
        if ( GetTokenInformation(v21, TokenUser, (char *)v20 + 32, 0x54u, &ReturnLength) )
        {
          CacheKey = TOKEN_KEY::CreateCacheKey((wchar_t **)v20 + 15, a2, v15, a4);
        }
        else
        {
          LastError = GetLastError();
          CacheKey = LastError;
          if ( LastError > 0 )
            CacheKey = (unsigned __int16)LastError | 0x80070000;
        }
        if ( CacheKey < 0 )
        {
          (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        *v33 = v20;
        goto LABEL_45;
      }
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      if ( v17 != -2147023570 )
        break;
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < v13 );
    v18 = GetLastError();
    CacheKey = v18;
    if ( v18 > 0 )
      CacheKey = (unsigned __int16)v18 | 0x80070000;
    if ( CacheKey >= 0 )
      goto LABEL_45;
  }
LABEL_43:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_45:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v26 )
    SeciFreeCallContext();
LABEL_49:
  STRU::~STRU((STRU *)v34);
  STRU::~STRU((STRU *)v36);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x180005aec  push    rbp
0x180005aee  push    rbx
0x180005aef  push    rsi
0x180005af0  push    rdi
0x180005af1  push    r12
0x180005af3  push    r13
0x180005af5  push    r14
0x180005af7  push    r15
0x180005af9  lea     rbp, [rsp-418h]
0x180005b01  sub     rsp, 518h
0x180005b08  mov     rax, cs:__security_cookie
0x180005b0f  xor     rax, rsp
0x180005b12  mov     [rbp+450h+var_50], rax
0x180005b19  mov     rsi, [rbp+450h+arg_30]
0x180005b20  xor     eax, eax
0x180005b22  mov     rdi, [rbp+450h+arg_28]
0x180005b29  mov     r13, rdx
0x180005b2c  mov     rbx, [rbp+450h+arg_20]
0x180005b33  mov     r12, rcx
0x180005b36  mov     [rbp+450h+lpszPassword], r8
0x180005b3a  lea     rcx, [rbp+450h+var_450]; void *
0x180005b3e  xor     edx, edx; Val
0x180005b40  mov     [rbp+450h+var_4C8], rsi
0x180005b44  mov     r8d, 200h; Size
0x180005b4a  mov     [rsp+550h+TokenHandle], rax
0x180005b4f  mov     [rsp+550h+Buffer], rax
0x180005b54  mov     r15d, r9d
0x180005b57  mov     [rsp+550h+var_4F8], eax
0x180005b5b  mov     [rsp+550h+var_4E0], rax
0x180005b60  call    memset_0
0x180005b65  mov     r14d, 100h
0x180005b6b  lea     rdx, [rbp+450h+var_450]
0x180005b6f  mov     r8d, r14d
0x180005b72  lea     rcx, [rbp+450h+var_488]
0x180005b76  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005b7c  xor     edx, edx; Val
0x180005b7e  lea     rcx, [rbp+450h+var_250]; void *
0x180005b85  mov     r8d, 200h; Size
0x180005b8b  call    memset_0
0x180005b90  mov     r8d, r14d
0x180005b93  lea     rdx, [rbp+450h+var_250]
0x180005b9a  lea     rcx, [rbp+450h+var_4C0]
0x180005b9e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005ba4  xor     r14d, r14d
0x180005ba7  mov     [rsp+550h+ReturnLength], r14d
0x180005bac  mov     [rsp+550h+var_4FC], r14d
0x180005bb1  test    rsi, rsi
0x180005bb4  jnz     short loc_180005BC0
0x180005bb6  mov     ebx, 80070057h
0x180005bbb  jmp     loc_180005E7F
0x180005bc0  lea     rax, [rsp+550h+ReturnLength]
0x180005bc5  mov     r8, rbx; unsigned __int16 *
0x180005bc8  mov     [rsp+550h+phToken], rax; int *
0x180005bcd  lea     r9, [rbp+450h+var_488]; struct STRU *
0x180005bd1  lea     rax, [rbp+450h+var_4C0]
0x180005bd5  mov     rdx, r13; unsigned __int16 *
0x180005bd8  mov     rcx, r12; this
0x180005bdb  mov     qword ptr [rsp+550h+dwLogonProvider], rax; struct STRU *
0x180005be0  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x180005be5  mov     ebx, eax
0x180005be7  test    eax, eax
0x180005be9  js      loc_180005E52
0x180005bef  mov     esi, 2
0x180005bf4  cmp     [rsp+550h+ReturnLength], r14d
0x180005bf9  jnz     short loc_180005C49
0x180005bfb  mov     rcx, [rbp+450h+var_4A0]
0x180005bff  cmp     [rcx], r14w
0x180005c03  jz      short loc_180005C4D
0x180005c05  mov     rcx, [rbp+450h+Str]; Str
0x180005c09  lea     edx, [rsi+3Eh]; Ch
0x180005c0c  call    cs:__imp_wcschr
0x180005c12  test    rax, rax
0x180005c15  jz      short loc_180005C49
0x180005c17  cmp     dword ptr [r12+0A04h], 0
0x180005c20  mov     r14d, esi
0x180005c23  mov     rax, [rbp+450h+var_4A0]
0x180005c27  jz      short loc_180005C39
0x180005c29  mov     [rsp+550h+lpszDomain], rax
0x180005c2e  mov     [rsp+550h+var_4E0], 0
0x180005c37  jmp     short loc_180005C64
0x180005c39  mov     [rsp+550h+lpszDomain], 0
0x180005c42  mov     [rsp+550h+var_4E0], rax
0x180005c47  jmp     short loc_180005C64
0x180005c49  mov     rcx, [rbp+450h+var_4A0]
0x180005c4d  movzx   eax, word ptr [rcx]
0x180005c50  mov     r14d, 1
0x180005c56  neg     ax
0x180005c59  sbb     rdx, rdx
0x180005c5c  and     rdx, rcx
0x180005c5f  mov     [rsp+550h+lpszDomain], rdx
0x180005c64  test    rdi, rdi
0x180005c67  jz      short loc_180005C9C
0x180005c69  cmp     [rdi], si
0x180005c6c  jnz     short loc_180005C75
0x180005c6e  mov     edx, 10h
0x180005c73  jmp     short loc_180005C80
0x180005c75  cmp     word ptr [rdi], 17h
0x180005c79  jnz     short loc_180005C9C
0x180005c7b  mov     edx, 1Ch
0x180005c80  lea     r8, [rsp+550h+var_4FC]
0x180005c85  mov     rcx, rdi
0x180005c88  call    cs:__imp_SeciAllocateAndSetIPAddress
0x180005c8e  mov     ebx, eax
0x180005c90  test    eax, eax
0x180005c92  jns     short loc_180005C9C
0x180005c94  xor     r14d, r14d
0x180005c97  jmp     loc_180005E52
0x180005c9c  mov     r12, [rbp+450h+lpszPassword]
0x180005ca0  xor     ebx, ebx
0x180005ca2  mov     edi, 80070000h
0x180005ca7  mov     rdx, [rsp+rbx*8+550h+lpszDomain]; lpszDomain
0x180005cac  lea     rax, [rsp+550h+var_4F8]
0x180005cb1  mov     rcx, [rbp+450h+Str]; lpszUsername
0x180005cb5  mov     r9d, r15d; dwLogonType
0x180005cb8  mov     [rsp+550h+pQuotaLimits], 0; pQuotaLimits
0x180005cc1  mov     r8, r12; lpszPassword
0x180005cc4  mov     [rsp+550h+pdwProfileLength], rax; pdwProfileLength
0x180005cc9  lea     rax, [rsp+550h+Buffer]
0x180005cce  mov     [rsp+550h+ppProfileBuffer], rax; ppProfileBuffer
0x180005cd3  lea     rax, [rsp+550h+TokenHandle]
0x180005cd8  mov     [rsp+550h+ppLogonSid], 0; ppLogonSid
0x180005ce1  mov     [rsp+550h+phToken], rax; phToken
0x180005ce6  mov     [rsp+550h+dwLogonProvider], 0; dwLogonProvider
0x180005cee  call    cs:__imp_LogonUserExW
0x180005cf4  test    eax, eax
0x180005cf6  jnz     short loc_180005D36
0x180005cf8  call    cs:__imp_GetLastError
0x180005cfe  test    eax, eax
0x180005d00  jle     short loc_180005D07
0x180005d02  movzx   eax, ax
0x180005d05  or      eax, edi
0x180005d07  cmp     eax, 8007052Eh
0x180005d0c  jnz     short loc_180005D15
0x180005d0e  inc     ebx
0x180005d10  cmp     ebx, r14d
0x180005d13  jb      short loc_180005CA7
0x180005d15  call    cs:__imp_GetLastError
0x180005d1b  xor     r14d, r14d
0x180005d1e  mov     ebx, eax
0x180005d20  test    eax, eax
0x180005d22  jle     short loc_180005D29
0x180005d24  movzx   ebx, ax
0x180005d27  or      ebx, edi
0x180005d29  test    ebx, ebx
0x180005d2b  jns     loc_180005E62
0x180005d31  jmp     loc_180005E52
0x180005d36  mov     ecx, 108h; Size
0x180005d3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d40  xor     r14d, r14d
0x180005d43  mov     rdi, rax
0x180005d46  test    rax, rax
0x180005d49  jz      loc_180005E4D
0x180005d4f  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180005d56  mov     [rdi+10h], r14
0x180005d5a  mov     [rdi], rax
0x180005d5d  lea     ebx, [r14+1]
0x180005d61  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x180005d68  mov     [rdi+0Ch], ebx
0x180005d6b  lea     rcx, [rdi+80h]
0x180005d72  mov     [rdi+78h], rax
0x180005d76  mov     [rdi+18h], r14
0x180005d7a  mov     [rdi+74h], r14d
0x180005d7e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005d84  lea     rcx, [rdi+0B8h]
0x180005d8b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005d91  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x180005d98  mov     [rdi+0F8h], r14d
0x180005d9f  mov     [rdi+0FCh], r14d
0x180005da6  mov     [rdi+100h], esi
0x180005dac  mov     dword ptr [rdi+8], 4E4B4F54h
0x180005db3  mov     rcx, [rsp+550h+TokenHandle]; TokenHandle
0x180005db8  cmp     r15d, 3
0x180005dbc  jz      short loc_180005DC7
0x180005dbe  mov     eax, r14d
0x180005dc1  cmp     r15d, 8
0x180005dc5  jnz     short loc_180005DC9
0x180005dc7  mov     eax, ebx
0x180005dc9  test    eax, eax
0x180005dcb  jz      short loc_180005DD5
0x180005dcd  mov     [rdi+10h], rcx
0x180005dd1  mov     esi, ebx
0x180005dd3  jmp     short loc_180005DD9
0x180005dd5  mov     [rdi+18h], rcx
0x180005dd9  or      [rdi+104h], esi
0x180005ddf  lea     rax, [rsp+550h+ReturnLength]
0x180005de4  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180005dea  mov     qword ptr [rsp+550h+dwLogonProvider], rax; ReturnLength
0x180005def  lea     r8, [rdi+20h]; TokenInformation
0x180005df3  mov     [rsp+550h+ReturnLength], r9d
0x180005df8  mov     edx, ebx; TokenInformationClass
0x180005dfa  call    cs:__imp_GetTokenInformation
0x180005e00  test    eax, eax
0x180005e02  jnz     short loc_180005E1B
0x180005e04  call    cs:__imp_GetLastError
0x180005e0a  mov     ebx, eax
0x180005e0c  test    eax, eax
0x180005e0e  jle     short loc_180005E2F
0x180005e10  movzx   ebx, ax
0x180005e13  or      ebx, 80070000h
0x180005e19  jmp     short loc_180005E2F
0x180005e1b  lea     rcx, [rdi+78h]; this
0x180005e1f  mov     r9d, r15d; unsigned int
0x180005e22  mov     r8, r12; unsigned __int16 *
0x180005e25  mov     rdx, r13; unsigned __int16 *
0x180005e28  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180005e2d  mov     ebx, eax
0x180005e2f  test    ebx, ebx
0x180005e31  jns     short loc_180005E44
0x180005e33  mov     rax, [rdi]
0x180005e36  mov     rcx, rdi
0x180005e39  mov     rax, [rax+10h]
0x180005e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e42  jmp     short loc_180005E52
0x180005e44  mov     rax, [rbp+450h+var_4C8]
0x180005e48  mov     [rax], rdi
0x180005e4b  jmp     short loc_180005E62
0x180005e4d  mov     ebx, 80070008h
0x180005e52  mov     rcx, [rsp+550h+TokenHandle]; hObject
0x180005e57  test    rcx, rcx
0x180005e5a  jz      short loc_180005E62
0x180005e5c  call    cs:__imp_CloseHandle
0x180005e62  mov     rcx, [rsp+550h+Buffer]; Buffer
0x180005e67  test    rcx, rcx
0x180005e6a  jz      short loc_180005E72
0x180005e6c  call    cs:__imp_LsaFreeReturnBuffer
0x180005e72  cmp     [rsp+550h+var_4FC], r14d
0x180005e77  jz      short loc_180005E7F
0x180005e79  call    cs:__imp_SeciFreeCallContext
0x180005e7f  lea     rcx, [rbp+450h+var_4C0]
0x180005e83  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e89  lea     rcx, [rbp+450h+var_488]
0x180005e8d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e93  mov     eax, ebx
0x180005e95  mov     rcx, [rbp+450h+var_50]
0x180005e9c  xor     rcx, rsp; StackCookie
0x180005e9f  call    __security_check_cookie
0x180005ea4  add     rsp, 518h
0x180005eab  pop     r15
0x180005ead  pop     r14
0x180005eaf  pop     r13
0x180005eb1  pop     r12
0x180005eb3  pop     rdi
0x180005eb4  pop     rsi
0x180005eb5  pop     rbx
0x180005eb6  pop     rbp
0x180005eb7  retn
```
