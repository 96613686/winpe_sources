# IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase2(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)

- ea: `0x180004f68`
- end: `0x18000508c`
- name: `?ClientPhase2@IIS_CRYPTO_EXCHANGE_CLIENT@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@00PEAPEFAU2@1@Z`
- size: `292`
- prototype: `__int64 __usercall@<rax>(IIS_CRYPTO_EXCHANGE_CLIENT *__hidden this@<rcx>, struct _IIS_CRYPTO_BLOB *@<rdx>, struct _IIS_CRYPTO_BLOB *@<r8>, struct _IIS_CRYPTO_BLOB *@<r9>, struct _IIS_CRYPTO_BLOB **, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003538`

## callees

- `0x180004f68`
- `0x180005480`
- `0x180005528`
- `0x180005bd8`
- `0x1800063b4`
- `0x180006460`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000505c`
- `ole32!CoTaskMemFree` at `0x18000506d`
- `ole32!CoTaskMemFree` at `0x18000505c`
- `ole32!CoTaskMemFree` at `0x18000506d`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase2(
        HCRYPTKEY *this,
        struct _IIS_CRYPTO_BLOB *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        struct _IIS_CRYPTO_BLOB *a4,
        struct _IIS_CRYPTO_BLOB **a5,
        struct _IIS_CRYPTO_BLOB **a6)
{
  HCRYPTPROV v7; // r8
  struct _IIS_CRYPTO_BLOB *v9; // rsi
  int SessionKey; // ebx
  void *v13; // rcx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  struct _IIS_CRYPTO_BLOB *v15; // [rsp+60h] [rbp+8h] BYREF

  pv = 0;
  v7 = *this;
  v9 = 0;
  v15 = 0;
  SessionKey = IISCryptoImportPublicKeyBlob(this + 6, (__int64)a2, v7);
  if ( SessionKey >= 0 )
  {
    SessionKey = IISCryptoImportPublicKeyBlob(this + 7, (__int64)a3, *this);
    if ( SessionKey >= 0 )
    {
      SessionKey = IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(this + 4, a4);
      if ( SessionKey >= 0 )
      {
        SessionKey = IISCryptoGenerateSessionKey(this + 5, *this);
        if ( SessionKey >= 0 )
        {
          SessionKey = IIS_CRYPTO_BASE::SafeExportSessionKeyBlob((struct _IIS_CRYPTO_BLOB **)&pv);
          if ( SessionKey >= 0 )
          {
            SessionKey = IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(this, &v15, 1);
            if ( SessionKey >= 0 )
            {
              *a5 = (struct _IIS_CRYPTO_BLOB *)pv;
              *a6 = v15;
              return 0;
            }
            v9 = v15;
          }
          v13 = pv;
          if ( pv )
          {
            *(_BYTE *)pv = 88;
            CoTaskMemFree(v13);
          }
          if ( v9 )
          {
            *(_BYTE *)v9 = 88;
            CoTaskMemFree(v9);
          }
        }
      }
    }
  }
  return (unsigned int)SessionKey;
}

```

## disassembly

```asm
0x180004f68  mov     rax, rsp
0x180004f6b  mov     [rax+10h], rbx
0x180004f6f  mov     [rax+18h], rbp
0x180004f73  push    rsi
0x180004f74  push    rdi
0x180004f75  push    r12
0x180004f77  push    r14
0x180004f79  push    r15
0x180004f7b  sub     rsp, 30h
0x180004f7f  mov     rbp, r8
0x180004f82  mov     qword ptr [rax-38h], 0
0x180004f8a  mov     r8, [rcx]
0x180004f8d  mov     rdi, rcx
0x180004f90  xor     esi, esi
0x180004f92  add     rcx, 30h ; '0'; phKey
0x180004f96  mov     r12, r9
0x180004f99  mov     [rax+8], rsi
0x180004f9d  call    IISCryptoImportPublicKeyBlob
0x180004fa2  mov     ebx, eax
0x180004fa4  test    eax, eax
0x180004fa6  js      loc_180005073
0x180004fac  mov     r8, [rdi]
0x180004faf  lea     rcx, [rdi+38h]; phKey
0x180004fb3  mov     rdx, rbp
0x180004fb6  call    IISCryptoImportPublicKeyBlob
0x180004fbb  mov     ebx, eax
0x180004fbd  test    eax, eax
0x180004fbf  js      loc_180005073
0x180004fc5  mov     r9, [rdi+38h]; unsigned __int64
0x180004fc9  lea     rcx, [rdi+20h]; unsigned __int64 *
0x180004fcd  mov     r8, [rdi]; unsigned __int64
0x180004fd0  mov     rdx, r12; struct _IIS_CRYPTO_BLOB *
0x180004fd3  call    ?SafeImportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEA_KPEFAU_IIS_CRYPTO_BLOB@@_K2@Z; IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(unsigned __int64 *,_IIS_CRYPTO_BLOB *,unsigned __int64,unsigned __int64)
0x180004fd8  mov     ebx, eax
0x180004fda  test    eax, eax
0x180004fdc  js      loc_180005073
0x180004fe2  mov     rdx, [rdi]; hProv
0x180004fe5  lea     rcx, [rdi+28h]; phKey
0x180004fe9  call    IISCryptoGenerateSessionKey
0x180004fee  mov     ebx, eax
0x180004ff0  test    eax, eax
0x180004ff2  js      short loc_180005073
0x180004ff4  mov     r9, [rdi+30h]; unsigned __int64
0x180004ff8  lea     rcx, [rsp+58h+pv]; struct _IIS_CRYPTO_BLOB **
0x180004ffd  mov     r8, [rdi+28h]; unsigned __int64
0x180005001  mov     rdx, [rdi]; unsigned __int64
0x180005004  call    ?SafeExportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEAPEFAU_IIS_CRYPTO_BLOB@@_K11@Z; IIS_CRYPTO_BASE::SafeExportSessionKeyBlob(_IIS_CRYPTO_BLOB * *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180005009  mov     ebx, eax
0x18000500b  test    eax, eax
0x18000500d  js      short loc_18000504F
0x18000500f  lea     r8d, [rsi+1]; int
0x180005013  mov     rcx, rdi; this
0x180005016  lea     rdx, [rsp+58h+arg_0]; struct _IIS_CRYPTO_BLOB **
0x18000501b  call    ?CreateHashWorker@IIS_CRYPTO_EXCHANGE_BASE@@AEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(_IIS_CRYPTO_BLOB * *,int)
0x180005020  mov     ebx, eax
0x180005022  test    eax, eax
0x180005024  js      short loc_18000504A
0x180005026  mov     rcx, [rsp+58h+arg_20]
0x18000502e  mov     rax, [rsp+58h+pv]
0x180005033  mov     [rcx], rax
0x180005036  mov     rax, [rsp+58h+arg_0]
0x18000503b  mov     rcx, [rsp+58h+arg_28]
0x180005043  mov     [rcx], rax
0x180005046  xor     eax, eax
0x180005048  jmp     short loc_180005075
0x18000504a  mov     rsi, [rsp+58h+arg_0]
0x18000504f  mov     rcx, [rsp+58h+pv]; pv
0x180005054  test    rcx, rcx
0x180005057  jz      short loc_180005062
0x180005059  mov     byte ptr [rcx], 58h ; 'X'
0x18000505c  call    cs:__imp_CoTaskMemFree
0x180005062  test    rsi, rsi
0x180005065  jz      short loc_180005073
0x180005067  mov     rcx, rsi; pv
0x18000506a  mov     byte ptr [rsi], 58h ; 'X'
0x18000506d  call    cs:__imp_CoTaskMemFree
0x180005073  mov     eax, ebx
0x180005075  mov     rbx, [rsp+58h+arg_8]
0x18000507a  mov     rbp, [rsp+58h+arg_10]
0x18000507f  add     rsp, 30h
0x180005083  pop     r15
0x180005085  pop     r14
0x180005087  pop     r12
0x180005089  pop     rdi
0x18000508a  pop     rsi
0x18000508b  retn
```
