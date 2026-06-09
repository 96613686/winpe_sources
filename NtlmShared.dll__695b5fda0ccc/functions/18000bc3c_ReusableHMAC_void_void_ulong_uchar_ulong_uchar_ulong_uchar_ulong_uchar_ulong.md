# ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x18000bc3c`
- end: `0x18000bd51`
- name: `?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z`
- size: `277`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR pbInput, ULONG cbInput, PUCHAR pbHashObject, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be54`
- `0x18000c13c`

## callees

- `0x18000bc3c`
- `0x18000bf2c`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000bd04`
- `bcrypt!BCryptHashData` at `0x18000bd04`
- `bcrypt!BCryptCreateHash` at `0x18000bce2`
- `bcrypt!BCryptCreateHash` at `0x18000bce2`
- `bcrypt!BCryptDestroyHash` at `0x18000bd40`
- `bcrypt!BCryptDestroyHash` at `0x18000bd40`
- `bcrypt!BCryptFinishHash` at `0x18000bd21`
- `bcrypt!BCryptFinishHash` at `0x18000bd21`

## pseudocode

```c
__int64 __fastcall ReusableHMAC(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE a2,
        int a3,
        unsigned __int8 *a4,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        unsigned __int8 *pbOutput,
        ULONG a11)
{
  unsigned int v11; // edi
  int v14; // ecx
  unsigned int v16; // eax
  ULONG v17; // esi
  BCRYPT_HASH_HANDLE v18; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF

  v11 = 0;
  phHash = 0;
  v14 = 32772;
  if ( a3 != 32777 )
    v14 = a3;
  if ( v14 == 32772 )
  {
    v16 = 20;
  }
  else
  {
    if ( v14 != 32782 )
      return v11;
    v16 = 64;
  }
  v17 = a11;
  if ( a11 > v16 )
    v17 = v16;
  if ( hAlgorithm || (hAlgorithm = GetBCryptProviderHandle(v14, (__int64)a2, 0x28u)) != 0 )
  {
    if ( a2 )
    {
      v18 = a2;
      phHash = a2;
LABEL_15:
      if ( BCryptHashData(v18, pbInput, cbInput, 0) >= 0 && BCryptFinishHash(phHash, pbOutput, v17, 0) >= 0 )
        v11 = 1;
      goto LABEL_18;
    }
    if ( BCryptCreateHash(hAlgorithm, &phHash, pbHashObject, cbHashObject, a4, cbSecret, 0) >= 0 )
    {
      v18 = phHash;
      goto LABEL_15;
    }
  }
LABEL_18:
  if ( phHash && a2 != phHash )
    BCryptDestroyHash(phHash);
  return v11;
}

```

## disassembly

```asm
0x18000bc3c  push    rbx
0x18000bc3e  push    rbp
0x18000bc3f  push    rsi
0x18000bc40  push    rdi
0x18000bc41  sub     rsp, 58h
0x18000bc45  xor     edi, edi
0x18000bc47  mov     eax, 8004h
0x18000bc4c  cmp     r8d, 8009h
0x18000bc53  mov     [rsp+78h+phHash], rdi
0x18000bc58  mov     r10, rcx
0x18000bc5b  mov     rbp, r9
0x18000bc5e  mov     ecx, eax
0x18000bc60  mov     rbx, rdx
0x18000bc63  cmovnz  ecx, r8d
0x18000bc67  cmp     ecx, eax
0x18000bc69  jnz     short loc_18000BC70
0x18000bc6b  lea     eax, [rdi+14h]
0x18000bc6e  jmp     short loc_18000BC81
0x18000bc70  cmp     ecx, 800Eh
0x18000bc76  jnz     loc_18000BD46
0x18000bc7c  mov     eax, 40h ; '@'
0x18000bc81  mov     esi, [rsp+78h+arg_50]
0x18000bc88  cmp     esi, eax
0x18000bc8a  cmova   esi, eax
0x18000bc8d  test    r10, r10
0x18000bc90  jnz     short loc_18000BCA7
0x18000bc92  lea     r8d, [r10+28h]
0x18000bc96  call    GetBCryptProviderHandle
0x18000bc9b  mov     r10, rax
0x18000bc9e  test    rax, rax
0x18000bca1  jz      loc_18000BD31
0x18000bca7  test    rbx, rbx
0x18000bcaa  jz      short loc_18000BCB6
0x18000bcac  mov     rcx, rbx
0x18000bcaf  mov     [rsp+78h+phHash], rbx
0x18000bcb4  jmp     short loc_18000BCF1
0x18000bcb6  mov     eax, [rsp+78h+arg_20]
0x18000bcbd  lea     rdx, [rsp+78h+phHash]; phHash
0x18000bcc2  mov     r9d, [rsp+78h+cbHashObject]; cbHashObject
0x18000bcca  mov     rcx, r10; hAlgorithm
0x18000bccd  mov     r8, [rsp+78h+pbHashObject]; pbHashObject
0x18000bcd5  mov     [rsp+78h+dwFlags], edi; dwFlags
0x18000bcd9  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18000bcdd  mov     [rsp+78h+pbSecret], rbp; pbSecret
0x18000bce2  call    cs:__imp_BCryptCreateHash
0x18000bce8  test    eax, eax
0x18000bcea  js      short loc_18000BD31
0x18000bcec  mov     rcx, [rsp+78h+phHash]; hHash
0x18000bcf1  mov     r8d, [rsp+78h+cbInput]; cbInput
0x18000bcf9  xor     r9d, r9d; dwFlags
0x18000bcfc  mov     rdx, [rsp+78h+pbInput]; pbInput
0x18000bd04  call    cs:__imp_BCryptHashData
0x18000bd0a  test    eax, eax
0x18000bd0c  js      short loc_18000BD31
0x18000bd0e  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x18000bd16  xor     r9d, r9d; dwFlags
0x18000bd19  mov     rcx, [rsp+78h+phHash]; hHash
0x18000bd1e  mov     r8d, esi; cbOutput
0x18000bd21  call    cs:__imp_BCryptFinishHash
0x18000bd27  test    eax, eax
0x18000bd29  mov     ecx, 1
0x18000bd2e  cmovns  edi, ecx
0x18000bd31  mov     rcx, [rsp+78h+phHash]; hHash
0x18000bd36  test    rcx, rcx
0x18000bd39  jz      short loc_18000BD46
0x18000bd3b  cmp     rbx, rcx
0x18000bd3e  jz      short loc_18000BD46
0x18000bd40  call    cs:__imp_BCryptDestroyHash
0x18000bd46  mov     eax, edi
0x18000bd48  add     rsp, 58h
0x18000bd4c  pop     rdi
0x18000bd4d  pop     rsi
0x18000bd4e  pop     rbp
0x18000bd4f  pop     rbx
0x18000bd50  retn
```
