# IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase2(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *)

- ea: `0x180005aac`
- end: `0x180005b88`
- name: `?ServerPhase2@IIS_CRYPTO_EXCHANGE_SERVER@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@0PEAPEFAU2@@Z`
- size: `220`
- prototype: `__int64 __fastcall(IIS_CRYPTO_EXCHANGE_SERVER *__hidden this, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB *, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003b9c`

## callees

- `0x180005528`
- `0x180005aac`
- `0x180005bd8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005b48`
- `ole32!CoTaskMemFree` at `0x180005b62`
- `ole32!CoTaskMemFree` at `0x180005b73`
- `ole32!CoTaskMemFree` at `0x180005b48`
- `ole32!CoTaskMemFree` at `0x180005b62`
- `ole32!CoTaskMemFree` at `0x180005b73`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_EXCHANGE_SERVER::ServerPhase2(
        IIS_CRYPTO_EXCHANGE_SERVER *this,
        struct _IIS_CRYPTO_BLOB *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        struct _IIS_CRYPTO_BLOB **a4)
{
  struct _IIS_CRYPTO_BLOB *v7; // rsi
  int v8; // edi
  int HashWorker; // eax
  _BYTE *v10; // rbx
  LPVOID pv; // [rsp+20h] [rbp-48h] BYREF
  struct _IIS_CRYPTO_BLOB *v13; // [rsp+70h] [rbp+8h] BYREF

  pv = 0;
  v7 = 0;
  v13 = 0;
  v8 = IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(
         (unsigned __int64 *)this + 5,
         a2,
         *(_QWORD *)this,
         *((_QWORD *)this + 7));
  if ( v8 < 0 )
    return (unsigned int)v8;
  HashWorker = IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(this, (struct _IIS_CRYPTO_BLOB **)&pv, 1);
  v10 = pv;
  v8 = HashWorker;
  if ( HashWorker < 0 )
  {
LABEL_10:
    if ( v10 )
    {
      *v10 = 88;
      CoTaskMemFree(v10);
    }
    if ( v7 )
    {
      *(_BYTE *)v7 = 88;
      CoTaskMemFree(v7);
    }
    return (unsigned int)v8;
  }
  if ( pv )
  {
    if ( *(_QWORD *)a3 == *(_QWORD *)pv )
    {
      v8 = IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(this, &v13, 0);
      if ( v8 >= 0 )
      {
        *a4 = v13;
        *v10 = 88;
        CoTaskMemFree(v10);
        return 0;
      }
      v7 = v13;
    }
    else
    {
      v8 = 13;
    }
    goto LABEL_10;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180005aac  push    rbx
0x180005aae  push    rbp
0x180005aaf  push    rsi
0x180005ab0  push    rdi
0x180005ab1  push    r14
0x180005ab3  push    r15
0x180005ab5  sub     rsp, 38h
0x180005ab9  mov     r14, rcx
0x180005abc  mov     [rsp+68h+pv], 0
0x180005ac5  mov     r15, r9
0x180005ac8  mov     rbp, r8
0x180005acb  xor     esi, esi
0x180005acd  add     rcx, 28h ; '('; unsigned __int64 *
0x180005ad1  mov     [rsp+68h+arg_0], rsi
0x180005ad6  mov     r9, [r14+38h]; unsigned __int64
0x180005ada  mov     r8, [r14]; unsigned __int64
0x180005add  call    ?SafeImportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEA_KPEFAU_IIS_CRYPTO_BLOB@@_K2@Z; IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(unsigned __int64 *,_IIS_CRYPTO_BLOB *,unsigned __int64,unsigned __int64)
0x180005ae2  mov     edi, eax
0x180005ae4  test    eax, eax
0x180005ae6  js      loc_180005B79
0x180005aec  lea     r8d, [rsi+1]; int
0x180005af0  mov     rcx, r14; this
0x180005af3  lea     rdx, [rsp+68h+pv]; struct _IIS_CRYPTO_BLOB **
0x180005af8  call    ?CreateHashWorker@IIS_CRYPTO_EXCHANGE_BASE@@AEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(_IIS_CRYPTO_BLOB * *,int)
0x180005afd  mov     rbx, [rsp+68h+pv]
0x180005b02  mov     edi, eax
0x180005b04  test    eax, eax
0x180005b06  js      short loc_180005B57
0x180005b08  test    rbx, rbx
0x180005b0b  jnz     short loc_180005B14
0x180005b0d  mov     edi, 80004005h
0x180005b12  jmp     short loc_180005B79
0x180005b14  mov     rax, [rbp+0]
0x180005b18  cmp     rax, [rbx]
0x180005b1b  jz      short loc_180005B24
0x180005b1d  mov     edi, 0Dh
0x180005b22  jmp     short loc_180005B57
0x180005b24  xor     r8d, r8d; int
0x180005b27  lea     rdx, [rsp+68h+arg_0]; struct _IIS_CRYPTO_BLOB **
0x180005b2c  mov     rcx, r14; this
0x180005b2f  call    ?CreateHashWorker@IIS_CRYPTO_EXCHANGE_BASE@@AEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(_IIS_CRYPTO_BLOB * *,int)
0x180005b34  mov     edi, eax
0x180005b36  test    eax, eax
0x180005b38  js      short loc_180005B52
0x180005b3a  mov     rax, [rsp+68h+arg_0]
0x180005b3f  mov     rcx, rbx; pv
0x180005b42  mov     [r15], rax
0x180005b45  mov     byte ptr [rbx], 58h ; 'X'
0x180005b48  call    cs:__imp_CoTaskMemFree
0x180005b4e  xor     eax, eax
0x180005b50  jmp     short loc_180005B7B
0x180005b52  mov     rsi, [rsp+68h+arg_0]
0x180005b57  test    rbx, rbx
0x180005b5a  jz      short loc_180005B68
0x180005b5c  mov     rcx, rbx; pv
0x180005b5f  mov     byte ptr [rbx], 58h ; 'X'
0x180005b62  call    cs:__imp_CoTaskMemFree
0x180005b68  test    rsi, rsi
0x180005b6b  jz      short loc_180005B79
0x180005b6d  mov     rcx, rsi; pv
0x180005b70  mov     byte ptr [rsi], 58h ; 'X'
0x180005b73  call    cs:__imp_CoTaskMemFree
0x180005b79  mov     eax, edi
0x180005b7b  add     rsp, 38h
0x180005b7f  pop     r15
0x180005b81  pop     r14
0x180005b83  pop     rdi
0x180005b84  pop     rsi
0x180005b85  pop     rbp
0x180005b86  pop     rbx
0x180005b87  retn
```
