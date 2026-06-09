# IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase1(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)

- ea: `0x180005988`
- end: `0x180005aa6`
- name: `?ServerPhase1@IIS_CRYPTO_EXCHANGE_SERVER@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@11@Z`
- size: `286`
- prototype: `__int64 __fastcall(HCRYPTKEY *this, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB *, LPVOID *, struct _IIS_CRYPTO_BLOB **, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800039d4`

## callees

- `0x180005480`
- `0x180005988`
- `0x180005f7c`
- `0x1800063b4`
- `0x180006460`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005a4c`
- `ole32!CoTaskMemFree` at `0x180005a5e`
- `ole32!CoTaskMemFree` at `0x180005a70`
- `ole32!CoTaskMemFree` at `0x180005a4c`
- `ole32!CoTaskMemFree` at `0x180005a5e`
- `ole32!CoTaskMemFree` at `0x180005a70`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase1(
        HCRYPTKEY *this,
        struct _IIS_CRYPTO_BLOB *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        LPVOID *a4,
        struct _IIS_CRYPTO_BLOB **a5,
        struct _IIS_CRYPTO_BLOB **a6)
{
  int SessionKey; // ebx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  struct _IIS_CRYPTO_BLOB **v13; // rcx
  LPVOID v14; // [rsp+20h] [rbp-18h] BYREF
  LPVOID v15[2]; // [rsp+28h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+38h] BYREF

  v15[0] = 0;
  v14 = 0;
  pv = 0;
  SessionKey = IISCryptoImportPublicKeyBlob(this + 6);
  if ( SessionKey < 0 )
    return (unsigned int)SessionKey;
  SessionKey = IISCryptoImportPublicKeyBlob(this + 7);
  if ( SessionKey < 0 )
    return (unsigned int)SessionKey;
  SessionKey = IISCryptoExportPublicKeyBlob(v15, *this, this[2]);
  if ( SessionKey < 0 )
  {
LABEL_11:
    v11 = v15[0];
    if ( v15[0] )
    {
      *(_BYTE *)v15[0] = 88;
      CoTaskMemFree(v11);
    }
    return (unsigned int)SessionKey;
  }
  SessionKey = IISCryptoExportPublicKeyBlob(&v14, *this, this[3]);
  if ( SessionKey < 0 || (SessionKey = IISCryptoGenerateSessionKey(this + 4, *this), SessionKey < 0) )
  {
LABEL_9:
    v10 = v14;
    if ( v14 )
    {
      *(_BYTE *)v14 = 88;
      CoTaskMemFree(v10);
    }
    goto LABEL_11;
  }
  SessionKey = IIS_CRYPTO_BASE::SafeExportSessionKeyBlob((struct _IIS_CRYPTO_BLOB **)&pv, *this, this[4], this[6]);
  if ( SessionKey < 0 )
  {
    v9 = pv;
    if ( pv )
    {
      *(_BYTE *)pv = 88;
      CoTaskMemFree(v9);
    }
    goto LABEL_9;
  }
  v13 = a5;
  *a4 = v15[0];
  *v13 = (struct _IIS_CRYPTO_BLOB *)v14;
  *a6 = (struct _IIS_CRYPTO_BLOB *)pv;
  return 0;
}

```

## disassembly

```asm
0x180005988  push    rbp
0x18000598a  push    rbx
0x18000598b  push    rsi
0x18000598c  push    rdi
0x18000598d  push    r14
0x18000598f  push    r15
0x180005991  mov     rbp, rsp
0x180005994  sub     rsp, 38h
0x180005998  mov     rsi, r8
0x18000599b  mov     [rbp+var_10], 0
0x1800059a3  mov     r8, [rcx]
0x1800059a6  mov     rdi, rcx
0x1800059a9  add     rcx, 30h ; '0'; phKey
0x1800059ad  mov     [rbp+var_18], 0
0x1800059b5  mov     r14, r9
0x1800059b8  mov     [rbp+pv], 0
0x1800059c0  call    IISCryptoImportPublicKeyBlob
0x1800059c5  mov     ebx, eax
0x1800059c7  test    eax, eax
0x1800059c9  js      loc_180005A76
0x1800059cf  mov     r8, [rdi]
0x1800059d2  lea     rcx, [rdi+38h]; phKey
0x1800059d6  mov     rdx, rsi
0x1800059d9  call    IISCryptoImportPublicKeyBlob
0x1800059de  mov     ebx, eax
0x1800059e0  test    eax, eax
0x1800059e2  js      loc_180005A76
0x1800059e8  mov     r8, [rdi+10h]
0x1800059ec  lea     rcx, [rbp+var_10]
0x1800059f0  mov     rdx, [rdi]
0x1800059f3  call    IISCryptoExportPublicKeyBlob
0x1800059f8  mov     ebx, eax
0x1800059fa  test    eax, eax
0x1800059fc  js      short loc_180005A64
0x1800059fe  mov     r8, [rdi+18h]
0x180005a02  lea     rcx, [rbp+var_18]
0x180005a06  mov     rdx, [rdi]
0x180005a09  call    IISCryptoExportPublicKeyBlob
0x180005a0e  mov     ebx, eax
0x180005a10  test    eax, eax
0x180005a12  js      short loc_180005A52
0x180005a14  mov     rdx, [rdi]; hProv
0x180005a17  lea     rcx, [rdi+20h]; phKey
0x180005a1b  call    IISCryptoGenerateSessionKey
0x180005a20  mov     ebx, eax
0x180005a22  test    eax, eax
0x180005a24  js      short loc_180005A52
0x180005a26  mov     r9, [rdi+30h]; unsigned __int64
0x180005a2a  lea     rcx, [rbp+pv]; struct _IIS_CRYPTO_BLOB **
0x180005a2e  mov     r8, [rdi+20h]; unsigned __int64
0x180005a32  mov     rdx, [rdi]; unsigned __int64
0x180005a35  call    ?SafeExportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEAPEFAU_IIS_CRYPTO_BLOB@@_K11@Z; IIS_CRYPTO_BASE::SafeExportSessionKeyBlob(_IIS_CRYPTO_BLOB * *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180005a3a  mov     ebx, eax
0x180005a3c  test    eax, eax
0x180005a3e  jns     short loc_180005A85
0x180005a40  mov     rcx, [rbp+pv]; pv
0x180005a44  test    rcx, rcx
0x180005a47  jz      short loc_180005A52
0x180005a49  mov     byte ptr [rcx], 58h ; 'X'
0x180005a4c  call    cs:__imp_CoTaskMemFree
0x180005a52  mov     rcx, [rbp+var_18]; pv
0x180005a56  test    rcx, rcx
0x180005a59  jz      short loc_180005A64
0x180005a5b  mov     byte ptr [rcx], 58h ; 'X'
0x180005a5e  call    cs:__imp_CoTaskMemFree
0x180005a64  mov     rcx, [rbp+var_10]; pv
0x180005a68  test    rcx, rcx
0x180005a6b  jz      short loc_180005A76
0x180005a6d  mov     byte ptr [rcx], 58h ; 'X'
0x180005a70  call    cs:__imp_CoTaskMemFree
0x180005a76  mov     eax, ebx
0x180005a78  add     rsp, 38h
0x180005a7c  pop     r15
0x180005a7e  pop     r14
0x180005a80  pop     rdi
0x180005a81  pop     rsi
0x180005a82  pop     rbx
0x180005a83  pop     rbp
0x180005a84  retn
0x180005a85  mov     rax, [rbp+var_10]
0x180005a89  mov     rcx, [rbp+arg_20]
0x180005a8d  mov     [r14], rax
0x180005a90  mov     rax, [rbp+var_18]
0x180005a94  mov     [rcx], rax
0x180005a97  mov     rax, [rbp+pv]
0x180005a9b  mov     rcx, [rbp+arg_28]
0x180005a9f  mov     [rcx], rax
0x180005aa2  xor     eax, eax
0x180005aa4  jmp     short loc_180005A78
```
