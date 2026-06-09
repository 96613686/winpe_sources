# ADM_SECURE_DATA::DoServerSideKeyExchangePhase1(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)

- ea: `0x1800039d4`
- end: `0x180003b93`
- name: `?DoServerSideKeyExchangePhase1@ADM_SECURE_DATA@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@11@Z`
- size: `447`
- prototype: `__int64 __fastcall(ADM_SECURE_DATA *__hidden this, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB **, struct _IIS_CRYPTO_BLOB **, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002170`

## callees

- `0x180001124`
- `0x180001130`
- `0x1800039d4`
- `0x1800041ac`
- `0x180004e6c`
- `0x1800053bc`
- `0x180005988`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800039ff`
- `KERNEL32!GetCurrentThread` at `0x1800039ff`
- `KERNEL32!GetLastError` at `0x180003b11`
- `KERNEL32!GetLastError` at `0x180003b22`
- `KERNEL32!GetLastError` at `0x180003b64`
- `KERNEL32!GetLastError` at `0x180003b11`
- `KERNEL32!GetLastError` at `0x180003b22`
- `KERNEL32!GetLastError` at `0x180003b64`
- `KERNEL32!CloseHandle` at `0x180003b7e`
- `KERNEL32!CloseHandle` at `0x180003b7e`
- `ADVAPI32!OpenThreadToken` at `0x180003a18`
- `ADVAPI32!OpenThreadToken` at `0x180003a18`
- `ADVAPI32!RevertToSelf` at `0x180003a26`
- `ADVAPI32!RevertToSelf` at `0x180003a26`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003b5a`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003b5a`

## string_xrefs

- `0x180003a38`: `MS IIS DCOM Server`

## pseudocode

```c
__int64 __fastcall ADM_SECURE_DATA::DoServerSideKeyExchangePhase1(
        ADM_SECURE_DATA *this,
        struct _IIS_CRYPTO_BLOB *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        struct _IIS_CRYPTO_BLOB **a4,
        struct _IIS_CRYPTO_BLOB **a5,
        struct _IIS_CRYPTO_BLOB **a6)
{
  HANDLE CurrentThread; // rax
  unsigned __int64 v11; // rbx
  signed int CryptoProviderHelper; // ebx
  IIS_CRYPTO_EXCHANGE_SERVER *v13; // rax
  unsigned __int64 v14; // r8
  IIS_CRYPTO_EXCHANGE_SERVER *v15; // rdi
  signed int LastError; // eax
  signed int v17; // eax
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v20[8]; // [rsp+38h] [rbp-40h] BYREF

  v20[0] = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    RevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    LastError = GetLastError();
    CryptoProviderHelper = LastError;
    if ( LastError > 0 )
      CryptoProviderHelper = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
  v11 = ADM_SECURE_DATA::sm_ServerCryptoProvider;
  if ( !ADM_SECURE_DATA::sm_ServerCryptoProvider )
  {
    CryptoProviderHelper = ADM_SECURE_DATA::GetCryptoProviderHelper(
                             this,
                             v20,
                             &ADM_SECURE_DATA::sm_ServerCryptoProvider,
                             "MS IIS DCOM Server",
                             0x20u);
    if ( CryptoProviderHelper < 0 )
      goto LABEL_15;
    v11 = v20[0];
  }
  v13 = (IIS_CRYPTO_EXCHANGE_SERVER *)operator new(0x40u);
  v15 = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = 0;
    *((_DWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 3) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    CryptoProviderHelper = IIS_CRYPTO_BASE::Initialize(v13, v11, v14, 0, 0);
    if ( CryptoProviderHelper < 0
      || (CryptoProviderHelper = IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase1(v15, a2, a3, a4, a5, a6),
          CryptoProviderHelper < 0) )
    {
      IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(v15);
      operator delete(v15);
    }
    else
    {
      *((_QWORD *)this + 5) = v15;
    }
  }
  else
  {
    CryptoProviderHelper = -2147024888;
  }
LABEL_15:
  if ( TokenHandle )
  {
    if ( !ImpersonateLoggedOnUser(TokenHandle) )
    {
      v17 = GetLastError();
      CryptoProviderHelper = v17;
      if ( v17 > 0 )
        CryptoProviderHelper = (unsigned __int16)v17 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)CryptoProviderHelper;
}

```

## disassembly

```asm
0x1800039d4  push    rbx
0x1800039d6  push    rbp
0x1800039d7  push    rsi
0x1800039d8  push    rdi
0x1800039d9  push    r14
0x1800039db  push    r15
0x1800039dd  sub     rsp, 48h
0x1800039e1  mov     rbp, r9
0x1800039e4  mov     [rsp+78h+var_40], 0
0x1800039ed  mov     r14, r8
0x1800039f0  mov     [rsp+78h+TokenHandle], 0
0x1800039f9  mov     r15, rdx
0x1800039fc  mov     rsi, rcx
0x1800039ff  call    cs:__imp_GetCurrentThread
0x180003a05  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180003a0a  mov     edx, 2000000h; DesiredAccess
0x180003a0f  mov     rcx, rax; ThreadHandle
0x180003a12  mov     r8d, 1; OpenAsSelf
0x180003a18  call    cs:__imp_OpenThreadToken
0x180003a1e  test    eax, eax
0x180003a20  jz      loc_180003B11
0x180003a26  call    cs:__imp_RevertToSelf
0x180003a2c  mov     rbx, cs:?sm_ServerCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 ADM_SECURE_DATA::sm_ServerCryptoProvider
0x180003a33  test    rbx, rbx
0x180003a36  jnz     short loc_180003A6A
0x180003a38  lea     r9, aMsIisDcomServe; "MS IIS DCOM Server"
0x180003a3f  mov     dword ptr [rsp+78h+var_58], 20h ; ' '; unsigned int
0x180003a47  lea     r8, ?sm_ServerCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 *
0x180003a4e  mov     rcx, rsi; this
0x180003a51  lea     rdx, [rsp+78h+var_40]; unsigned __int64 *
0x180003a56  call    ?GetCryptoProviderHelper@ADM_SECURE_DATA@@AEAAJPEA_K0PEADK@Z; ADM_SECURE_DATA::GetCryptoProviderHelper(unsigned __int64 *,unsigned __int64 *,char *,ulong)
0x180003a5b  mov     ebx, eax
0x180003a5d  test    eax, eax
0x180003a5f  js      loc_180003B50
0x180003a65  mov     rbx, [rsp+78h+var_40]
0x180003a6a  mov     ecx, 40h ; '@'; Size
0x180003a6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a74  mov     rdi, rax
0x180003a77  test    rax, rax
0x180003a7a  jz      loc_180003B4B
0x180003a80  xor     r9d, r9d; unsigned __int64
0x180003a83  mov     qword ptr [rax], 0
0x180003a8a  mov     rdx, rbx; unsigned __int64
0x180003a8d  mov     dword ptr [rax+8], 0
0x180003a94  mov     rcx, rax; this
0x180003a97  mov     qword ptr [rax+10h], 0
0x180003a9f  mov     qword ptr [rax+18h], 0
0x180003aa7  mov     qword ptr [rax+20h], 0
0x180003aaf  mov     qword ptr [rax+28h], 0
0x180003ab7  mov     qword ptr [rax+30h], 0
0x180003abf  mov     qword ptr [rax+38h], 0
0x180003ac7  mov     dword ptr [rsp+78h+var_58], 0; int
0x180003acf  call    ?Initialize@IIS_CRYPTO_BASE@@QEAAJ_K00H@Z; IIS_CRYPTO_BASE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,int)
0x180003ad4  mov     ebx, eax
0x180003ad6  test    eax, eax
0x180003ad8  js      short loc_180003B39
0x180003ada  mov     rax, [rsp+78h+arg_28]
0x180003ae2  mov     r9, rbp; struct _IIS_CRYPTO_BLOB **
0x180003ae5  mov     [rsp+78h+var_50], rax; struct _IIS_CRYPTO_BLOB **
0x180003aea  mov     r8, r14; struct _IIS_CRYPTO_BLOB *
0x180003aed  mov     rax, [rsp+78h+arg_20]
0x180003af5  mov     rdx, r15; struct _IIS_CRYPTO_BLOB *
0x180003af8  mov     rcx, rdi; this
0x180003afb  mov     [rsp+78h+var_58], rax; struct _IIS_CRYPTO_BLOB **
0x180003b00  call    ?ServerPhase1@IIS_CRYPTO_EXCHANGE_SERVER@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@11@Z; IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase1(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)
0x180003b05  mov     ebx, eax
0x180003b07  test    eax, eax
0x180003b09  js      short loc_180003B39
0x180003b0b  mov     [rsi+28h], rdi
0x180003b0f  jmp     short loc_180003B50
0x180003b11  call    cs:__imp_GetLastError
0x180003b17  cmp     eax, 3F0h
0x180003b1c  jz      loc_180003A2C
0x180003b22  call    cs:__imp_GetLastError
0x180003b28  mov     ebx, eax
0x180003b2a  test    eax, eax
0x180003b2c  jle     short loc_180003B50
0x180003b2e  movzx   ebx, ax
0x180003b31  or      ebx, 80070000h
0x180003b37  jmp     short loc_180003B50
0x180003b39  mov     rcx, rdi; this
0x180003b3c  call    ??1IIS_CRYPTO_EXCHANGE_SERVER@@QEAA@XZ; IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(void)
0x180003b41  mov     rcx, rdi; Block
0x180003b44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b49  jmp     short loc_180003B50
0x180003b4b  mov     ebx, 80070008h
0x180003b50  mov     rcx, [rsp+78h+TokenHandle]; hToken
0x180003b55  test    rcx, rcx
0x180003b58  jz      short loc_180003B84
0x180003b5a  call    cs:__imp_ImpersonateLoggedOnUser
0x180003b60  test    eax, eax
0x180003b62  jnz     short loc_180003B79
0x180003b64  call    cs:__imp_GetLastError
0x180003b6a  mov     ebx, eax
0x180003b6c  test    eax, eax
0x180003b6e  jle     short loc_180003B79
0x180003b70  movzx   ebx, ax
0x180003b73  or      ebx, 80070000h
0x180003b79  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180003b7e  call    cs:__imp_CloseHandle
0x180003b84  mov     eax, ebx
0x180003b86  add     rsp, 48h
0x180003b8a  pop     r15
0x180003b8c  pop     r14
0x180003b8e  pop     rdi
0x180003b8f  pop     rsi
0x180003b90  pop     rbp
0x180003b91  pop     rbx
0x180003b92  retn
```
