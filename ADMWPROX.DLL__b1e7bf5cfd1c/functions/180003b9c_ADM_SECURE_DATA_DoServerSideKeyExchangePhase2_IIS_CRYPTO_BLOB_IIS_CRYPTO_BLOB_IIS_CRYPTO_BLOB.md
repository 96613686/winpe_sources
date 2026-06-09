# ADM_SECURE_DATA::DoServerSideKeyExchangePhase2(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *)

- ea: `0x180003b9c`
- end: `0x180003d4d`
- name: `?DoServerSideKeyExchangePhase2@ADM_SECURE_DATA@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@@Z`
- size: `433`
- prototype: `__int64 __fastcall(IIS_CRYPTO_EXCHANGE_SERVER **this, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180002240`

## callees

- `0x180001130`
- `0x180003298`
- `0x180003b9c`
- `0x180005900`
- `0x180005aac`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180003bbb`
- `KERNEL32!GetCurrentThread` at `0x180003bbb`
- `KERNEL32!GetLastError` at `0x180003c32`
- `KERNEL32!GetLastError` at `0x180003c3f`
- `KERNEL32!GetLastError` at `0x180003d20`
- `KERNEL32!GetLastError` at `0x180003c32`
- `KERNEL32!GetLastError` at `0x180003c3f`
- `KERNEL32!GetLastError` at `0x180003d20`
- `KERNEL32!CloseHandle` at `0x180003d3a`
- `KERNEL32!CloseHandle` at `0x180003d3a`
- `ADVAPI32!OpenThreadToken` at `0x180003bd2`
- `ADVAPI32!OpenThreadToken` at `0x180003bd2`
- `ADVAPI32!RevertToSelf` at `0x180003bdc`
- `ADVAPI32!RevertToSelf` at `0x180003bdc`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003d16`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003d16`

## pseudocode

```c
__int64 __fastcall ADM_SECURE_DATA::DoServerSideKeyExchangePhase2(
        IIS_CRYPTO_EXCHANGE_SERVER **this,
        struct _IIS_CRYPTO_BLOB *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        struct _IIS_CRYPTO_BLOB **a4)
{
  HANDLE CurrentThread; // rax
  signed int v9; // ebx
  IIS_CRYPTO_STORAGE *v10; // rax
  unsigned __int64 v11; // r9
  IIS_CRYPTO_STORAGE *v12; // rcx
  signed int LastError; // eax
  IIS_CRYPTO_EXCHANGE_SERVER *v14; // rax
  unsigned __int64 v15; // r8
  IIS_CRYPTO_STORAGE *v16; // rax
  IIS_CRYPTO_STORAGE *v17; // rcx
  IIS_CRYPTO_EXCHANGE_SERVER *v18; // rax
  unsigned __int64 v19; // r9
  IIS_CRYPTO_EXCHANGE_SERVER *v20; // rax
  unsigned __int64 v21; // r8
  signed int v22; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    RevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    if ( v9 >= 0 )
      goto LABEL_20;
    goto LABEL_19;
  }
  v9 = IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase2(this[5], a2, a3, a4);
  if ( v9 >= 0 )
  {
    v10 = (IIS_CRYPTO_STORAGE *)operator new(0x30u);
    v12 = v10;
    if ( v10 )
    {
      *((_QWORD *)v10 + 1) = 0;
      *((_DWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 4) = 0;
      *(_QWORD *)v10 = &IIS_CRYPTO_STORAGE::`vftable';
      *((_QWORD *)v10 + 5) = 0;
    }
    else
    {
      v12 = 0;
    }
    this[6] = v12;
    if ( v12 )
    {
      v14 = this[5];
      v15 = *((_QWORD *)v14 + 4);
      *((_QWORD *)v14 + 4) = 0;
      v9 = IIS_CRYPTO_STORAGE::Initialize(v12, *(_QWORD *)this[5], v15, v11, 0, 0);
      if ( v9 < 0 )
        goto LABEL_19;
      v16 = (IIS_CRYPTO_STORAGE *)operator new(0x30u);
      v17 = v16;
      if ( v16 )
      {
        *((_QWORD *)v16 + 1) = 0;
        *((_DWORD *)v16 + 4) = 0;
        *((_QWORD *)v16 + 3) = 0;
        *((_QWORD *)v16 + 4) = 0;
        *(_QWORD *)v16 = &IIS_CRYPTO_STORAGE::`vftable';
        *((_QWORD *)v16 + 5) = 0;
      }
      else
      {
        v17 = 0;
      }
      this[7] = v17;
      if ( v17 )
      {
        v18 = this[5];
        v19 = *((_QWORD *)v18 + 7);
        *((_QWORD *)v18 + 7) = 0;
        v20 = this[5];
        v21 = *((_QWORD *)v20 + 5);
        *((_QWORD *)v20 + 5) = 0;
        v9 = IIS_CRYPTO_STORAGE::Initialize(v17, *(_QWORD *)this[5], v21, v19, v19, 0);
        goto LABEL_18;
      }
    }
    v9 = -2147024888;
  }
LABEL_19:
  ADM_SECURE_DATA::CleanupCryptoData((ADM_SECURE_DATA *)this);
LABEL_20:
  if ( TokenHandle )
  {
    if ( !ImpersonateLoggedOnUser(TokenHandle) )
    {
      v22 = GetLastError();
      v9 = v22;
      if ( v22 > 0 )
        v9 = (unsigned __int16)v22 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003b9c  push    rbx
0x180003b9e  push    rbp
0x180003b9f  push    rsi
0x180003ba0  push    rdi
0x180003ba1  push    r14
0x180003ba3  sub     rsp, 40h
0x180003ba7  xor     r14d, r14d
0x180003baa  mov     rbx, r9
0x180003bad  mov     [rsp+68h+TokenHandle], r14
0x180003bb2  mov     rsi, r8
0x180003bb5  mov     rbp, rdx
0x180003bb8  mov     rdi, rcx
0x180003bbb  call    cs:__imp_GetCurrentThread
0x180003bc1  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180003bc6  mov     edx, 2000000h; DesiredAccess
0x180003bcb  mov     rcx, rax; ThreadHandle
0x180003bce  lea     r8d, [r14+1]; OpenAsSelf
0x180003bd2  call    cs:__imp_OpenThreadToken
0x180003bd8  test    eax, eax
0x180003bda  jz      short loc_180003C32
0x180003bdc  call    cs:__imp_RevertToSelf
0x180003be2  mov     rcx, [rdi+28h]; this
0x180003be6  mov     r9, rbx; struct _IIS_CRYPTO_BLOB **
0x180003be9  mov     r8, rsi; struct _IIS_CRYPTO_BLOB *
0x180003bec  mov     rdx, rbp; struct _IIS_CRYPTO_BLOB *
0x180003bef  call    ?ServerPhase2@IIS_CRYPTO_EXCHANGE_SERVER@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@@Z; IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase2(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *)
0x180003bf4  mov     ebx, eax
0x180003bf6  test    eax, eax
0x180003bf8  js      loc_180003D04
0x180003bfe  mov     esi, 30h ; '0'
0x180003c03  mov     ecx, esi; Size
0x180003c05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c0a  lea     rbp, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180003c11  mov     rcx, rax
0x180003c14  test    rax, rax
0x180003c17  jz      short loc_180003C5D
0x180003c19  mov     [rax+8], r14
0x180003c1d  mov     [rax+10h], r14d
0x180003c21  mov     [rax+18h], r14
0x180003c25  mov     [rax+20h], r14
0x180003c29  mov     [rax], rbp
0x180003c2c  mov     [rax+28h], r14
0x180003c30  jmp     short loc_180003C60
0x180003c32  call    cs:__imp_GetLastError
0x180003c38  cmp     eax, 3F0h
0x180003c3d  jz      short loc_180003BE2
0x180003c3f  call    cs:__imp_GetLastError
0x180003c45  mov     ebx, eax
0x180003c47  test    eax, eax
0x180003c49  jle     loc_180003D00
0x180003c4f  movzx   ebx, ax
0x180003c52  or      ebx, 80070000h
0x180003c58  jmp     loc_180003D00
0x180003c5d  mov     rcx, r14; this
0x180003c60  mov     [rdi+30h], rcx
0x180003c64  test    rcx, rcx
0x180003c67  jnz     short loc_180003C73
0x180003c69  mov     ebx, 80070008h
0x180003c6e  jmp     loc_180003D04
0x180003c73  mov     rax, [rdi+28h]
0x180003c77  mov     [rsp+68h+var_40], r14d; int
0x180003c7c  mov     [rsp+68h+var_48], r14; unsigned __int64
0x180003c81  mov     r8, [rax+20h]; unsigned __int64
0x180003c85  mov     [rax+20h], r14
0x180003c89  mov     rdx, [rdi+28h]
0x180003c8d  mov     rdx, [rdx]; unsigned __int64
0x180003c90  call    ?Initialize@IIS_CRYPTO_STORAGE@@QEAAJ_K000H@Z; IIS_CRYPTO_STORAGE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int)
0x180003c95  mov     ebx, eax
0x180003c97  test    eax, eax
0x180003c99  js      short loc_180003D04
0x180003c9b  mov     rcx, rsi; Size
0x180003c9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ca3  mov     rcx, rax
0x180003ca6  test    rax, rax
0x180003ca9  jz      short loc_180003CC4
0x180003cab  mov     [rax+8], r14
0x180003caf  mov     [rax+10h], r14d
0x180003cb3  mov     [rax+18h], r14
0x180003cb7  mov     [rax+20h], r14
0x180003cbb  mov     [rax], rbp
0x180003cbe  mov     [rax+28h], r14
0x180003cc2  jmp     short loc_180003CC7
0x180003cc4  mov     rcx, r14; this
0x180003cc7  mov     [rdi+38h], rcx
0x180003ccb  test    rcx, rcx
0x180003cce  jz      short loc_180003C69
0x180003cd0  mov     rax, [rdi+28h]
0x180003cd4  mov     [rsp+68h+var_40], r14d; int
0x180003cd9  mov     r9, [rax+38h]; unsigned __int64
0x180003cdd  mov     [rax+38h], r14
0x180003ce1  mov     rax, [rdi+28h]
0x180003ce5  mov     [rsp+68h+var_48], r9; unsigned __int64
0x180003cea  mov     r8, [rax+28h]; unsigned __int64
0x180003cee  mov     [rax+28h], r14
0x180003cf2  mov     rdx, [rdi+28h]
0x180003cf6  mov     rdx, [rdx]; unsigned __int64
0x180003cf9  call    ?Initialize@IIS_CRYPTO_STORAGE@@QEAAJ_K000H@Z; IIS_CRYPTO_STORAGE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int)
0x180003cfe  mov     ebx, eax
0x180003d00  test    ebx, ebx
0x180003d02  jns     short loc_180003D0C
0x180003d04  mov     rcx, rdi; this
0x180003d07  call    ?CleanupCryptoData@ADM_SECURE_DATA@@AEAAXXZ; ADM_SECURE_DATA::CleanupCryptoData(void)
0x180003d0c  mov     rcx, [rsp+68h+TokenHandle]; hToken
0x180003d11  test    rcx, rcx
0x180003d14  jz      short loc_180003D40
0x180003d16  call    cs:__imp_ImpersonateLoggedOnUser
0x180003d1c  test    eax, eax
0x180003d1e  jnz     short loc_180003D35
0x180003d20  call    cs:__imp_GetLastError
0x180003d26  mov     ebx, eax
0x180003d28  test    eax, eax
0x180003d2a  jle     short loc_180003D35
0x180003d2c  movzx   ebx, ax
0x180003d2f  or      ebx, 80070000h
0x180003d35  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180003d3a  call    cs:__imp_CloseHandle
0x180003d40  mov     eax, ebx
0x180003d42  add     rsp, 40h
0x180003d46  pop     r14
0x180003d48  pop     rdi
0x180003d49  pop     rsi
0x180003d4a  pop     rbp
0x180003d4b  pop     rbx
0x180003d4c  retn
```
