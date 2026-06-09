# IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(_IIS_CRYPTO_BLOB * *,int)

- ea: `0x180005bd8`
- end: `0x180005d63`
- name: `?CreateHashWorker@IIS_CRYPTO_EXCHANGE_BASE@@AEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@H@Z`
- size: `395`
- prototype: `__int64 __fastcall(HCRYPTPROV *this, struct _IIS_CRYPTO_BLOB **, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180003538`
- `0x180004f68`
- `0x180005aac`

## callees

- `0x180004870`
- `0x180005bd8`
- `0x180006a3c`
- `0x180006a98`
- `0x180006ad8`

## import_xrefs

- `ADVAPI32!CryptHashData` at `0x180005d01`
- `ADVAPI32!CryptHashData` at `0x180005d01`
- `ADVAPI32!CryptHashSessionKey` at `0x180005c7c`
- `ADVAPI32!CryptHashSessionKey` at `0x180005cbb`
- `ADVAPI32!CryptHashSessionKey` at `0x180005c7c`
- `ADVAPI32!CryptHashSessionKey` at `0x180005cbb`
- `ole32!CoTaskMemFree` at `0x180005d3c`
- `ole32!CoTaskMemFree` at `0x180005d3c`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(HCRYPTPROV *this, struct _IIS_CRYPTO_BLOB **a2, int a3)
{
  HCRYPTPROV v4; // rdx
  struct _IIS_CRYPTO_BLOB *v6; // rdi
  int LastError; // ebx
  int v9; // eax
  HCRYPTKEY v10; // rdx
  HCRYPTKEY v12; // rdx
  const BYTE *v13; // rdx
  struct _IIS_CRYPTO_BLOB *v14; // [rsp+20h] [rbp-10h] BYREF
  HCRYPTHASH hHash; // [rsp+78h] [rbp+48h] BYREF

  hHash = 0;
  v4 = *this;
  v6 = 0;
  v14 = 0;
  LastError = IISCryptoCreateHash(&hHash, v4);
  if ( LastError < 0 )
    goto LABEL_8;
  if ( !hHash )
    return (unsigned int)-2147467259;
  v9 = dword_18000FC34;
  v10 = this[5];
  if ( dword_18000FC34 )
  {
    if ( !CryptHashSessionKey(hHash, v10, 0) )
    {
      LastError = IcpGetLastError();
      if ( LastError < 0 )
        goto LABEL_8;
    }
    v9 = dword_18000FC34;
  }
  else if ( hHash != 1750294856 || v10 != 1800627539 )
  {
    goto LABEL_7;
  }
  if ( a3 )
  {
    v12 = this[4];
    if ( v9 )
    {
      if ( !CryptHashSessionKey(hHash, v12, 0) )
      {
        LastError = IcpGetLastError();
        if ( LastError < 0 )
          goto LABEL_8;
      }
      v9 = dword_18000FC34;
    }
    else if ( hHash != 1750294856 || v12 != 1800627539 )
    {
LABEL_7:
      LastError = -2147024809;
LABEL_8:
      if ( hHash )
        IISCryptoDestroyHash();
      return (unsigned int)LastError;
    }
    v13 = (const BYTE *)"IIS Key Exchange Phase 3";
  }
  else
  {
    v13 = "IIS Key Exchange Phase 4";
  }
  if ( v9 )
  {
    if ( !CryptHashData(hHash, v13, 0x19u, 0) )
    {
      LastError = IcpGetLastError();
      if ( LastError < 0 )
      {
LABEL_31:
        if ( v6 )
        {
          *(_BYTE *)v6 = 88;
          CoTaskMemFree(v6);
        }
        goto LABEL_8;
      }
    }
  }
  else if ( hHash != 1750294856 )
  {
    LastError = -2147024809;
    goto LABEL_31;
  }
  LastError = IISCryptoExportHashBlob(&v14, hHash);
  if ( LastError < 0 )
  {
    v6 = v14;
    goto LABEL_31;
  }
  if ( hHash )
    IISCryptoDestroyHash();
  *a2 = v14;
  return 0;
}

```

## disassembly

```asm
0x180005bd8  mov     [rsp-28h+arg_0], rbx
0x180005bdd  mov     [rsp-28h+arg_8], rsi
0x180005be2  push    rbp
0x180005be3  push    rdi
0x180005be4  push    r12
0x180005be6  push    r14
0x180005be8  push    r15
0x180005bea  mov     rbp, rsp
0x180005bed  sub     rsp, 30h
0x180005bf1  mov     r15, rdx
0x180005bf4  mov     [rbp+hHash], 0
0x180005bfc  mov     rdx, [rcx]; hProv
0x180005bff  mov     rsi, rcx
0x180005c02  xor     edi, edi
0x180005c04  lea     rcx, [rbp+hHash]; phHash
0x180005c08  mov     r14d, r8d
0x180005c0b  mov     [rbp+var_10], rdi
0x180005c0f  call    IISCryptoCreateHash
0x180005c14  mov     ebx, eax
0x180005c16  test    eax, eax
0x180005c18  js      short loc_180005C52
0x180005c1a  cmp     [rbp+hHash], rdi
0x180005c1e  jnz     short loc_180005C27
0x180005c20  mov     ebx, 80004005h
0x180005c25  jmp     short loc_180005C60
0x180005c27  mov     eax, cs:dword_18000FC34
0x180005c2d  mov     r12d, 68536148h
0x180005c33  mov     rdx, [rsi+28h]; hKey
0x180005c37  mov     rcx, [rbp+hHash]; hHash
0x180005c3b  test    eax, eax
0x180005c3d  jnz     short loc_180005C79
0x180005c3f  cmp     rcx, r12
0x180005c42  jnz     short loc_180005C4D
0x180005c44  cmp     rdx, 6B536553h
0x180005c4b  jz      short loc_180005C97
0x180005c4d  mov     ebx, 80070057h
0x180005c52  mov     rcx, [rbp+hHash]
0x180005c56  test    rcx, rcx
0x180005c59  jz      short loc_180005C60
0x180005c5b  call    IISCryptoDestroyHash
0x180005c60  mov     eax, ebx
0x180005c62  mov     rbx, [rsp+30h+arg_0]
0x180005c67  mov     rsi, [rsp+30h+arg_8]
0x180005c6c  add     rsp, 30h
0x180005c70  pop     r15
0x180005c72  pop     r14
0x180005c74  pop     r12
0x180005c76  pop     rdi
0x180005c77  pop     rbp
0x180005c78  retn
0x180005c79  xor     r8d, r8d; dwFlags
0x180005c7c  call    cs:__imp_CryptHashSessionKey
0x180005c82  test    eax, eax
0x180005c84  jnz     short loc_180005C91
0x180005c86  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180005c8b  mov     ebx, eax
0x180005c8d  test    eax, eax
0x180005c8f  js      short loc_180005C52
0x180005c91  mov     eax, cs:dword_18000FC34
0x180005c97  test    r14d, r14d
0x180005c9a  jz      short loc_180005CDF
0x180005c9c  mov     rdx, [rsi+20h]; hKey
0x180005ca0  mov     rcx, [rbp+hHash]; hHash
0x180005ca4  test    eax, eax
0x180005ca6  jnz     short loc_180005CB8
0x180005ca8  cmp     rcx, r12
0x180005cab  jnz     short loc_180005C4D
0x180005cad  cmp     rdx, 6B536553h
0x180005cb4  jz      short loc_180005CD6
0x180005cb6  jmp     short loc_180005C4D
0x180005cb8  xor     r8d, r8d; dwFlags
0x180005cbb  call    cs:__imp_CryptHashSessionKey
0x180005cc1  test    eax, eax
0x180005cc3  jnz     short loc_180005CD0
0x180005cc5  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180005cca  mov     ebx, eax
0x180005ccc  test    eax, eax
0x180005cce  js      short loc_180005C52
0x180005cd0  mov     eax, cs:dword_18000FC34
0x180005cd6  lea     rdx, aIisKeyExchange_0; "IIS Key Exchange Phase 3"
0x180005cdd  jmp     short loc_180005CE6
0x180005cdf  lea     rdx, pbData; "IIS Key Exchange Phase 4"
0x180005ce6  mov     rcx, [rbp+hHash]; hHash
0x180005cea  test    eax, eax
0x180005cec  jnz     short loc_180005CFA
0x180005cee  cmp     rcx, r12
0x180005cf1  jz      short loc_180005D16
0x180005cf3  mov     ebx, 80070057h
0x180005cf8  jmp     short loc_180005D2D
0x180005cfa  xor     r9d, r9d; dwFlags
0x180005cfd  lea     r8d, [r9+19h]; dwDataLen
0x180005d01  call    cs:__imp_CryptHashData
0x180005d07  test    eax, eax
0x180005d09  jnz     short loc_180005D16
0x180005d0b  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180005d10  mov     ebx, eax
0x180005d12  test    eax, eax
0x180005d14  js      short loc_180005D2D
0x180005d16  mov     rdx, [rbp+hHash]
0x180005d1a  lea     rcx, [rbp+var_10]
0x180005d1e  call    IISCryptoExportHashBlob
0x180005d23  mov     ebx, eax
0x180005d25  test    eax, eax
0x180005d27  jns     short loc_180005D47
0x180005d29  mov     rdi, [rbp+var_10]
0x180005d2d  test    rdi, rdi
0x180005d30  jz      loc_180005C52
0x180005d36  mov     rcx, rdi; pv
0x180005d39  mov     byte ptr [rdi], 58h ; 'X'
0x180005d3c  call    cs:__imp_CoTaskMemFree
0x180005d42  jmp     loc_180005C52
0x180005d47  mov     rcx, [rbp+hHash]
0x180005d4b  test    rcx, rcx
0x180005d4e  jz      short loc_180005D55
0x180005d50  call    IISCryptoDestroyHash
0x180005d55  mov     rax, [rbp+var_10]
0x180005d59  mov     [r15], rax
0x180005d5c  xor     eax, eax
0x180005d5e  jmp     loc_180005C62
```
