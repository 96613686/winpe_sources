# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x18000485c`
- end: `0x180004c28`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001c70`

## callees

- `0x180001008`
- `0x180003c68`
- `0x180003d34`
- `0x18000485c`
- `0x180005af6`
- `0x180005b30`
- `0x180006010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000497c`
- `msvcrt!wcschr` at `0x18000497c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b74`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048e6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000490e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048e6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000490e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004aee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004afb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004aee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004afb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004bf3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004bfd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004bf3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004bfd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcc`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180004a5e`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180004a5e`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800049f8`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800049f8`
- `SspiCli!SeciFreeCallContext` at `0x180004be9`
- `SspiCli!SeciFreeCallContext` at `0x180004be9`
- `SspiCli!LsaFreeReturnBuffer` at `0x180004bdc`
- `SspiCli!LsaFreeReturnBuffer` at `0x180004bdc`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::IISLogonUser(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct sockaddr *a6,
        struct IHttpTokenEntry **a7)
{
  signed int CacheKey; // ebx
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
          CacheKey = TOKEN_KEY::CreateCacheKey((struct IHttpTokenEntry *)((char *)v20 + 120), a2, v15, a4);
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
0x18000485c  push    rbp
0x18000485e  push    rbx
0x18000485f  push    rsi
0x180004860  push    rdi
0x180004861  push    r12
0x180004863  push    r13
0x180004865  push    r14
0x180004867  push    r15
0x180004869  lea     rbp, [rsp-418h]
0x180004871  sub     rsp, 518h
0x180004878  mov     rax, cs:__security_cookie
0x18000487f  xor     rax, rsp
0x180004882  mov     [rbp+450h+var_50], rax
0x180004889  mov     rsi, [rbp+450h+arg_30]
0x180004890  xor     eax, eax
0x180004892  mov     rdi, [rbp+450h+arg_28]
0x180004899  mov     r13, rdx
0x18000489c  mov     rbx, [rbp+450h+arg_20]
0x1800048a3  mov     r12, rcx
0x1800048a6  mov     [rbp+450h+lpszPassword], r8
0x1800048aa  lea     rcx, [rbp+450h+var_450]; void *
0x1800048ae  xor     edx, edx; Val
0x1800048b0  mov     [rbp+450h+var_4C8], rsi
0x1800048b4  mov     r8d, 200h; Size
0x1800048ba  mov     [rsp+550h+TokenHandle], rax
0x1800048bf  mov     [rsp+550h+Buffer], rax
0x1800048c4  mov     r15d, r9d
0x1800048c7  mov     [rsp+550h+var_4F8], eax
0x1800048cb  mov     [rsp+550h+var_4E0], rax
0x1800048d0  call    memset_0
0x1800048d5  mov     r14d, 100h
0x1800048db  lea     rdx, [rbp+450h+var_450]
0x1800048df  mov     r8d, r14d
0x1800048e2  lea     rcx, [rbp+450h+var_488]
0x1800048e6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800048ec  xor     edx, edx; Val
0x1800048ee  lea     rcx, [rbp+450h+var_250]; void *
0x1800048f5  mov     r8d, 200h; Size
0x1800048fb  call    memset_0
0x180004900  mov     r8d, r14d
0x180004903  lea     rdx, [rbp+450h+var_250]
0x18000490a  lea     rcx, [rbp+450h+var_4C0]
0x18000490e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004914  xor     r14d, r14d
0x180004917  mov     [rsp+550h+ReturnLength], r14d
0x18000491c  mov     [rsp+550h+var_4FC], r14d
0x180004921  test    rsi, rsi
0x180004924  jnz     short loc_180004930
0x180004926  mov     ebx, 80070057h
0x18000492b  jmp     loc_180004BEF
0x180004930  lea     rax, [rsp+550h+ReturnLength]
0x180004935  mov     r8, rbx; unsigned __int16 *
0x180004938  mov     [rsp+550h+phToken], rax; int *
0x18000493d  lea     r9, [rbp+450h+var_488]; struct STRU *
0x180004941  lea     rax, [rbp+450h+var_4C0]
0x180004945  mov     rdx, r13; unsigned __int16 *
0x180004948  mov     rcx, r12; this
0x18000494b  mov     qword ptr [rsp+550h+dwLogonProvider], rax; struct STRU *
0x180004950  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x180004955  mov     ebx, eax
0x180004957  test    eax, eax
0x180004959  js      loc_180004BC2
0x18000495f  mov     esi, 2
0x180004964  cmp     [rsp+550h+ReturnLength], r14d
0x180004969  jnz     short loc_1800049B9
0x18000496b  mov     rcx, [rbp+450h+var_4A0]
0x18000496f  cmp     [rcx], r14w
0x180004973  jz      short loc_1800049BD
0x180004975  mov     rcx, [rbp+450h+Str]; Str
0x180004979  lea     edx, [rsi+3Eh]; Ch
0x18000497c  call    cs:__imp_wcschr
0x180004982  test    rax, rax
0x180004985  jz      short loc_1800049B9
0x180004987  cmp     dword ptr [r12+0A04h], 0
0x180004990  mov     r14d, esi
0x180004993  mov     rax, [rbp+450h+var_4A0]
0x180004997  jz      short loc_1800049A9
0x180004999  mov     [rsp+550h+lpszDomain], rax
0x18000499e  mov     [rsp+550h+var_4E0], 0
0x1800049a7  jmp     short loc_1800049D4
0x1800049a9  mov     [rsp+550h+lpszDomain], 0
0x1800049b2  mov     [rsp+550h+var_4E0], rax
0x1800049b7  jmp     short loc_1800049D4
0x1800049b9  mov     rcx, [rbp+450h+var_4A0]
0x1800049bd  movzx   eax, word ptr [rcx]
0x1800049c0  mov     r14d, 1
0x1800049c6  neg     ax
0x1800049c9  sbb     rdx, rdx
0x1800049cc  and     rdx, rcx
0x1800049cf  mov     [rsp+550h+lpszDomain], rdx
0x1800049d4  test    rdi, rdi
0x1800049d7  jz      short loc_180004A0C
0x1800049d9  cmp     [rdi], si
0x1800049dc  jnz     short loc_1800049E5
0x1800049de  mov     edx, 10h
0x1800049e3  jmp     short loc_1800049F0
0x1800049e5  cmp     word ptr [rdi], 17h
0x1800049e9  jnz     short loc_180004A0C
0x1800049eb  mov     edx, 1Ch
0x1800049f0  lea     r8, [rsp+550h+var_4FC]
0x1800049f5  mov     rcx, rdi
0x1800049f8  call    cs:__imp_SeciAllocateAndSetIPAddress
0x1800049fe  mov     ebx, eax
0x180004a00  test    eax, eax
0x180004a02  jns     short loc_180004A0C
0x180004a04  xor     r14d, r14d
0x180004a07  jmp     loc_180004BC2
0x180004a0c  mov     r12, [rbp+450h+lpszPassword]
0x180004a10  xor     ebx, ebx
0x180004a12  mov     edi, 80070000h
0x180004a17  mov     rdx, [rsp+rbx*8+550h+lpszDomain]; lpszDomain
0x180004a1c  lea     rax, [rsp+550h+var_4F8]
0x180004a21  mov     rcx, [rbp+450h+Str]; lpszUsername
0x180004a25  mov     r9d, r15d; dwLogonType
0x180004a28  mov     [rsp+550h+pQuotaLimits], 0; pQuotaLimits
0x180004a31  mov     r8, r12; lpszPassword
0x180004a34  mov     [rsp+550h+pdwProfileLength], rax; pdwProfileLength
0x180004a39  lea     rax, [rsp+550h+Buffer]
0x180004a3e  mov     [rsp+550h+ppProfileBuffer], rax; ppProfileBuffer
0x180004a43  lea     rax, [rsp+550h+TokenHandle]
0x180004a48  mov     [rsp+550h+ppLogonSid], 0; ppLogonSid
0x180004a51  mov     [rsp+550h+phToken], rax; phToken
0x180004a56  mov     [rsp+550h+dwLogonProvider], 0; dwLogonProvider
0x180004a5e  call    cs:__imp_LogonUserExW
0x180004a64  test    eax, eax
0x180004a66  jnz     short loc_180004AA6
0x180004a68  call    cs:__imp_GetLastError
0x180004a6e  test    eax, eax
0x180004a70  jle     short loc_180004A77
0x180004a72  movzx   eax, ax
0x180004a75  or      eax, edi
0x180004a77  cmp     eax, 8007052Eh
0x180004a7c  jnz     short loc_180004A85
0x180004a7e  inc     ebx
0x180004a80  cmp     ebx, r14d
0x180004a83  jb      short loc_180004A17
0x180004a85  call    cs:__imp_GetLastError
0x180004a8b  xor     r14d, r14d
0x180004a8e  mov     ebx, eax
0x180004a90  test    eax, eax
0x180004a92  jle     short loc_180004A99
0x180004a94  movzx   ebx, ax
0x180004a97  or      ebx, edi
0x180004a99  test    ebx, ebx
0x180004a9b  jns     loc_180004BD2
0x180004aa1  jmp     loc_180004BC2
0x180004aa6  mov     ecx, 108h; Size
0x180004aab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ab0  xor     r14d, r14d
0x180004ab3  mov     rdi, rax
0x180004ab6  test    rax, rax
0x180004ab9  jz      loc_180004BBD
0x180004abf  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180004ac6  mov     [rdi+10h], r14
0x180004aca  mov     [rdi], rax
0x180004acd  lea     ebx, [r14+1]
0x180004ad1  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x180004ad8  mov     [rdi+0Ch], ebx
0x180004adb  lea     rcx, [rdi+80h]
0x180004ae2  mov     [rdi+78h], rax
0x180004ae6  mov     [rdi+18h], r14
0x180004aea  mov     [rdi+74h], r14d
0x180004aee  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004af4  lea     rcx, [rdi+0B8h]
0x180004afb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004b01  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x180004b08  mov     [rdi+0F8h], r14d
0x180004b0f  mov     [rdi+0FCh], r14d
0x180004b16  mov     [rdi+100h], esi
0x180004b1c  mov     dword ptr [rdi+8], 4E4B4F54h
0x180004b23  mov     rcx, [rsp+550h+TokenHandle]; TokenHandle
0x180004b28  cmp     r15d, 3
0x180004b2c  jz      short loc_180004B37
0x180004b2e  mov     eax, r14d
0x180004b31  cmp     r15d, 8
0x180004b35  jnz     short loc_180004B39
0x180004b37  mov     eax, ebx
0x180004b39  test    eax, eax
0x180004b3b  jz      short loc_180004B45
0x180004b3d  mov     [rdi+10h], rcx
0x180004b41  mov     esi, ebx
0x180004b43  jmp     short loc_180004B49
0x180004b45  mov     [rdi+18h], rcx
0x180004b49  or      [rdi+104h], esi
0x180004b4f  lea     rax, [rsp+550h+ReturnLength]
0x180004b54  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180004b5a  mov     qword ptr [rsp+550h+dwLogonProvider], rax; ReturnLength
0x180004b5f  lea     r8, [rdi+20h]; TokenInformation
0x180004b63  mov     [rsp+550h+ReturnLength], r9d
0x180004b68  mov     edx, ebx; TokenInformationClass
0x180004b6a  call    cs:__imp_GetTokenInformation
0x180004b70  test    eax, eax
0x180004b72  jnz     short loc_180004B8B
0x180004b74  call    cs:__imp_GetLastError
0x180004b7a  mov     ebx, eax
0x180004b7c  test    eax, eax
0x180004b7e  jle     short loc_180004B9F
0x180004b80  movzx   ebx, ax
0x180004b83  or      ebx, 80070000h
0x180004b89  jmp     short loc_180004B9F
0x180004b8b  lea     rcx, [rdi+78h]; this
0x180004b8f  mov     r9d, r15d; unsigned int
0x180004b92  mov     r8, r12; unsigned __int16 *
0x180004b95  mov     rdx, r13; unsigned __int16 *
0x180004b98  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180004b9d  mov     ebx, eax
0x180004b9f  test    ebx, ebx
0x180004ba1  jns     short loc_180004BB4
0x180004ba3  mov     rax, [rdi]
0x180004ba6  mov     rcx, rdi
0x180004ba9  mov     rax, [rax+10h]
0x180004bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb2  jmp     short loc_180004BC2
0x180004bb4  mov     rax, [rbp+450h+var_4C8]
0x180004bb8  mov     [rax], rdi
0x180004bbb  jmp     short loc_180004BD2
0x180004bbd  mov     ebx, 80070008h
0x180004bc2  mov     rcx, [rsp+550h+TokenHandle]; hObject
0x180004bc7  test    rcx, rcx
0x180004bca  jz      short loc_180004BD2
0x180004bcc  call    cs:__imp_CloseHandle
0x180004bd2  mov     rcx, [rsp+550h+Buffer]; Buffer
0x180004bd7  test    rcx, rcx
0x180004bda  jz      short loc_180004BE2
0x180004bdc  call    cs:__imp_LsaFreeReturnBuffer
0x180004be2  cmp     [rsp+550h+var_4FC], r14d
0x180004be7  jz      short loc_180004BEF
0x180004be9  call    cs:__imp_SeciFreeCallContext
0x180004bef  lea     rcx, [rbp+450h+var_4C0]
0x180004bf3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004bf9  lea     rcx, [rbp+450h+var_488]
0x180004bfd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004c03  mov     eax, ebx
0x180004c05  mov     rcx, [rbp+450h+var_50]
0x180004c0c  xor     rcx, rsp; StackCookie
0x180004c0f  call    __security_check_cookie
0x180004c14  add     rsp, 518h
0x180004c1b  pop     r15
0x180004c1d  pop     r14
0x180004c1f  pop     r13
0x180004c21  pop     r12
0x180004c23  pop     rdi
0x180004c24  pop     rsi
0x180004c25  pop     rbx
0x180004c26  pop     rbp
0x180004c27  retn
```
