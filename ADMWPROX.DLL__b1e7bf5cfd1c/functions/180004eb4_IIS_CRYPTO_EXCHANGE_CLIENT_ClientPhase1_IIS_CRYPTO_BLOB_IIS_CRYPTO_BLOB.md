# IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase1(_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)

- ea: `0x180004eb4`
- end: `0x180004f5f`
- name: `?ClientPhase1@IIS_CRYPTO_EXCHANGE_CLIENT@@QEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@0@Z`
- size: `171`
- prototype: `__int64 __fastcall(IIS_CRYPTO_EXCHANGE_CLIENT *__hidden this, struct _IIS_CRYPTO_BLOB **, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003538`

## callees

- `0x180004eb4`
- `0x180005f7c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004f32`
- `ole32!CoTaskMemFree` at `0x180004f43`
- `ole32!CoTaskMemFree` at `0x180004f32`
- `ole32!CoTaskMemFree` at `0x180004f43`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase1(
        IIS_CRYPTO_EXCHANGE_CLIENT *this,
        LPVOID *a2,
        struct _IIS_CRYPTO_BLOB **a3)
{
  __int64 v4; // r8
  __int64 v6; // rdx
  struct _IIS_CRYPTO_BLOB *v8; // rbx
  int v9; // edi
  void *v11; // rcx
  struct _IIS_CRYPTO_BLOB *v12; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  pv = 0;
  v4 = *((_QWORD *)this + 2);
  v6 = *(_QWORD *)this;
  v8 = 0;
  v12 = 0;
  v9 = IISCryptoExportPublicKeyBlob(&pv, v6, v4);
  if ( v9 >= 0 )
  {
    v9 = IISCryptoExportPublicKeyBlob(&v12, *(_QWORD *)this, *((_QWORD *)this + 3));
    if ( v9 >= 0 )
    {
      *a2 = pv;
      *a3 = v12;
      return 0;
    }
    v8 = v12;
  }
  v11 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v11);
  }
  if ( v8 )
  {
    *(_BYTE *)v8 = 88;
    CoTaskMemFree(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004eb4  mov     rax, rsp
0x180004eb7  mov     [rax+10h], rbx
0x180004ebb  mov     [rax+18h], rsi
0x180004ebf  push    rdi
0x180004ec0  push    r14
0x180004ec2  push    r15
0x180004ec4  sub     rsp, 20h
0x180004ec8  mov     r14, r8
0x180004ecb  mov     qword ptr [rax+20h], 0
0x180004ed3  mov     r8, [rcx+10h]
0x180004ed7  mov     r15, rdx
0x180004eda  mov     rdx, [rcx]
0x180004edd  mov     rsi, rcx
0x180004ee0  xor     ebx, ebx
0x180004ee2  lea     rcx, [rax+20h]
0x180004ee6  mov     [rax+8], rbx
0x180004eea  call    IISCryptoExportPublicKeyBlob
0x180004eef  mov     edi, eax
0x180004ef1  test    eax, eax
0x180004ef3  js      short loc_180004F25
0x180004ef5  mov     r8, [rsi+18h]
0x180004ef9  lea     rcx, [rsp+38h+arg_0]
0x180004efe  mov     rdx, [rsi]
0x180004f01  call    IISCryptoExportPublicKeyBlob
0x180004f06  mov     edi, eax
0x180004f08  test    eax, eax
0x180004f0a  js      short loc_180004F20
0x180004f0c  mov     rax, [rsp+38h+pv]
0x180004f11  mov     [r15], rax
0x180004f14  mov     rax, [rsp+38h+arg_0]
0x180004f19  mov     [r14], rax
0x180004f1c  xor     eax, eax
0x180004f1e  jmp     short loc_180004F4B
0x180004f20  mov     rbx, [rsp+38h+arg_0]
0x180004f25  mov     rcx, [rsp+38h+pv]; pv
0x180004f2a  test    rcx, rcx
0x180004f2d  jz      short loc_180004F38
0x180004f2f  mov     byte ptr [rcx], 58h ; 'X'
0x180004f32  call    cs:__imp_CoTaskMemFree
0x180004f38  test    rbx, rbx
0x180004f3b  jz      short loc_180004F49
0x180004f3d  mov     rcx, rbx; pv
0x180004f40  mov     byte ptr [rbx], 58h ; 'X'
0x180004f43  call    cs:__imp_CoTaskMemFree
0x180004f49  mov     eax, edi
0x180004f4b  mov     rbx, [rsp+38h+arg_8]
0x180004f50  mov     rsi, [rsp+38h+arg_10]
0x180004f55  add     rsp, 20h
0x180004f59  pop     r15
0x180004f5b  pop     r14
0x180004f5d  pop     rdi
0x180004f5e  retn
```
