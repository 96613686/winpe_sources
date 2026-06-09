# Microsoft::Windows::Performance::CryptographicHasher::CryptographicHasher(ushort const *)

- ea: `0x18004c690`
- end: `0x18004c7d7`
- name: `??0CryptographicHasher@Performance@Windows@Microsoft@@QEAA@PEBG@Z`
- size: `327`
- prototype: `Microsoft::Windows::Performance::CryptographicHasher *__fastcall(Microsoft::Windows::Performance::CryptographicHasher *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004c370`

## callees

- `0x18004c690`
- `0x180080b4c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18004c7b4`
- `bcrypt!BCryptCreateHash` at `0x18004c7b4`
- `bcrypt!BCryptGetProperty` at `0x18004c71c`
- `bcrypt!BCryptGetProperty` at `0x18004c76b`
- `bcrypt!BCryptGetProperty` at `0x18004c71c`
- `bcrypt!BCryptGetProperty` at `0x18004c76b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c6d7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c6d7`

## pseudocode

```c
Microsoft::Windows::Performance::CryptographicHasher *__fastcall Microsoft::Windows::Performance::CryptographicHasher::CryptographicHasher(
        Microsoft::Windows::Performance::CryptographicHasher *this,
        const unsigned __int16 *a2)
{
  PUCHAR *v2; // rsi
  BCRYPT_HANDLE *v3; // rdi
  BCRYPT_HANDLE v5; // rcx
  ULONG pbOutput; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *pcbResult; // [rsp+68h] [rbp+10h] BYREF

  pcbResult = a2;
  *(_BYTE *)this = 0;
  v2 = (PUCHAR *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v3 = (BCRYPT_HANDLE *)((char *)this + 8);
  *((_QWORD *)this + 4) = 0;
  if ( BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 1, L"SHA256", 0, 0x20u) >= 0 )
  {
    v5 = *v3;
    pbOutput = 0;
    LODWORD(pcbResult) = 0;
    if ( BCryptGetProperty(v5, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0) >= 0
      && (_DWORD)pcbResult == 4
      && (unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v2, pbOutput)
      && BCryptGetProperty(*v3, L"HashDigestLength", (PUCHAR)this + 40, 4u, (ULONG *)&pcbResult, 0) >= 0
      && (_DWORD)pcbResult == 4
      && (unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(
                            (char *)this + 32,
                            *((unsigned int *)this + 10))
      && BCryptCreateHash(*v3, (BCRYPT_HASH_HANDLE *)this + 2, *v2, pbOutput, 0, 0, 0x20u) >= 0 )
    {
      *(_BYTE *)this = 1;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18004c690  mov     [rsp+arg_10], rbx
0x18004c695  mov     [rsp+arg_18], rbp
0x18004c69a  mov     [rsp+arg_8], rdx
0x18004c69f  push    rsi
0x18004c6a0  push    rdi
0x18004c6a1  push    r14
0x18004c6a3  sub     rsp, 40h
0x18004c6a7  mov     byte ptr [rcx], 0
0x18004c6aa  lea     rsi, [rcx+18h]
0x18004c6ae  mov     qword ptr [rsi], 0
0x18004c6b5  lea     rdi, [rcx+8]
0x18004c6b9  mov     qword ptr [rcx+20h], 0
0x18004c6c1  lea     rdx, pszAlgId; "SHA256"
0x18004c6c8  mov     rbx, rcx
0x18004c6cb  mov     r9d, 20h ; ' '; dwFlags
0x18004c6d1  mov     rcx, rdi; phAlgorithm
0x18004c6d4  xor     r8d, r8d; pszImplementation
0x18004c6d7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004c6dd  test    eax, eax
0x18004c6df  js      loc_18004C7C1
0x18004c6e5  mov     rcx, [rdi]; hObject
0x18004c6e8  lea     rax, [rsp+58h+arg_8]
0x18004c6ed  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18004c6f5  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x18004c6fa  mov     r9d, 4; cbOutput
0x18004c700  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18004c705  lea     rdx, pszProperty; "ObjectLength"
0x18004c70c  mov     [rsp+58h+pbOutput], 0
0x18004c714  mov     dword ptr [rsp+58h+arg_8], 0
0x18004c71c  call    cs:__imp_BCryptGetProperty
0x18004c722  test    eax, eax
0x18004c724  js      loc_18004C7C1
0x18004c72a  cmp     dword ptr [rsp+58h+arg_8], 4
0x18004c72f  jnz     loc_18004C7C1
0x18004c735  mov     edx, [rsp+58h+pbOutput]
0x18004c739  mov     rcx, rsi
0x18004c73c  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18004c741  test    al, al
0x18004c743  jz      short loc_18004C7C1
0x18004c745  mov     rcx, [rdi]; hObject
0x18004c748  lea     rax, [rsp+58h+arg_8]
0x18004c74d  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18004c755  lea     r8, [rbx+28h]; pbOutput
0x18004c759  mov     r9d, 4; cbOutput
0x18004c75f  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18004c764  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18004c76b  call    cs:__imp_BCryptGetProperty
0x18004c771  test    eax, eax
0x18004c773  js      short loc_18004C7C1
0x18004c775  cmp     dword ptr [rsp+58h+arg_8], 4
0x18004c77a  jnz     short loc_18004C7C1
0x18004c77c  mov     edx, [rbx+28h]
0x18004c77f  lea     rcx, [rbx+20h]
0x18004c783  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18004c788  test    al, al
0x18004c78a  jz      short loc_18004C7C1
0x18004c78c  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x18004c791  lea     rdx, [rbx+10h]; phHash
0x18004c795  mov     r8, [rsi]; pbHashObject
0x18004c798  mov     rcx, [rdi]; hAlgorithm
0x18004c79b  mov     [rsp+58h+var_28], 20h ; ' '; dwFlags
0x18004c7a3  mov     [rsp+58h+dwFlags], 0; cbSecret
0x18004c7ab  mov     [rsp+58h+pcbResult], 0; pbSecret
0x18004c7b4  call    cs:__imp_BCryptCreateHash
0x18004c7ba  test    eax, eax
0x18004c7bc  js      short loc_18004C7C1
0x18004c7be  mov     byte ptr [rbx], 1
0x18004c7c1  mov     rbp, [rsp+58h+arg_18]
0x18004c7c6  mov     rax, rbx
0x18004c7c9  mov     rbx, [rsp+58h+arg_10]
0x18004c7ce  add     rsp, 40h
0x18004c7d2  pop     r14
0x18004c7d4  pop     rdi
0x18004c7d5  pop     rsi
0x18004c7d6  retn
```
