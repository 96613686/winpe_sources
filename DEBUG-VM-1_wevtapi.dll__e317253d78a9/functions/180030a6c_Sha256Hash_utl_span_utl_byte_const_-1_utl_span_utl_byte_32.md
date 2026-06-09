# Sha256Hash(utl::span<utl::byte const,-1>,utl::span<utl::byte,32>)

- ea: `0x180030a6c`
- end: `0x180030c1b`
- name: `?Sha256Hash@@YAJV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0CA@@2@@Z`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dff8`
- `0x180030c24`

## callees

- `0x1800249f0`
- `0x180030a6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030be2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030be2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030b28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030b28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bf0`
- `bcrypt!BCryptDestroyHash` at `0x180030bd7`
- `bcrypt!BCryptDestroyHash` at `0x180030bd7`
- `bcrypt!BCryptHashData` at `0x180030b88`
- `bcrypt!BCryptHashData` at `0x180030ba3`
- `bcrypt!BCryptHashData` at `0x180030b88`
- `bcrypt!BCryptHashData` at `0x180030ba3`
- `bcrypt!BCryptCreateHash` at `0x180030aca`
- `bcrypt!BCryptCreateHash` at `0x180030b69`
- `bcrypt!BCryptCreateHash` at `0x180030aca`
- `bcrypt!BCryptCreateHash` at `0x180030b69`
- `bcrypt!BCryptGetProperty` at `0x180030b06`
- `bcrypt!BCryptGetProperty` at `0x180030b06`
- `bcrypt!BCryptFinishHash` at `0x180030bbe`
- `bcrypt!BCryptFinishHash` at `0x180030bbe`

## pseudocode

```c
__int64 __fastcall Sha256Hash(__int64 a1, UCHAR *a2)
{
  UCHAR *v2; // rsi
  NTSTATUS Property; // edi
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  UCHAR *v8; // rax
  HANDLE v9; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult[4]; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbHashObject[384]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  phHash = 0;
  Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, pbHashObject, 0x180u, 0, 0, 0);
  if ( Property == -1073741789 )
  {
    *(_DWORD *)pbOutput = 0;
    pcbResult[0] = 0;
    Property = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"ObjectLength", pbOutput, 4u, pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_11;
    v6 = *(_DWORD *)pbOutput;
    ProcessHeap = GetProcessHeap();
    v8 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v6);
    v2 = v8;
    if ( !v8 )
    {
      Property = -1073741801;
      goto LABEL_11;
    }
    Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, v8, *(ULONG *)pbOutput, 0, 0, 0);
  }
  if ( Property >= 0 )
  {
    Property = BCryptHashData(phHash, (PUCHAR)"MS-WEVT", 8u, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, *(PUCHAR *)a1, *(_DWORD *)(a1 + 8), 0);
      if ( Property >= 0 )
      {
        Property = BCryptFinishHash(phHash, a2, 0x20u, 0);
        if ( Property >= 0 )
          Property = 0;
      }
    }
  }
LABEL_11:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x180030a6c  push    rbp
0x180030a6e  push    rbx
0x180030a6f  push    rsi
0x180030a70  push    rdi
0x180030a71  push    r12
0x180030a73  push    r14
0x180030a75  lea     rbp, [rsp-0F8h]
0x180030a7d  sub     rsp, 1F8h
0x180030a84  mov     rax, cs:__security_cookie
0x180030a8b  xor     rax, rsp
0x180030a8e  mov     [rbp+120h+var_40], rax
0x180030a95  xor     esi, esi
0x180030a97  mov     [rsp+220h+phHash], 0
0x180030aa0  mov     rbx, rdx
0x180030aa3  mov     [rsp+220h+dwFlags], esi; dwFlags
0x180030aa7  mov     r14, rcx
0x180030aaa  mov     [rsp+220h+cbSecret], esi; cbSecret
0x180030aae  mov     r9d, 180h; cbHashObject
0x180030ab4  mov     [rsp+220h+pbSecret], rsi; pbSecret
0x180030ab9  lea     r12d, [rsi+41h]
0x180030abd  mov     ecx, r12d; hAlgorithm
0x180030ac0  lea     r8, [rsp+220h+pbHashObject]; pbHashObject
0x180030ac5  lea     rdx, [rsp+220h+phHash]; phHash
0x180030aca  call    cs:__imp_BCryptCreateHash
0x180030ad0  mov     edi, eax
0x180030ad2  cmp     eax, 0C0000023h
0x180030ad7  jnz     loc_180030B71
0x180030add  lea     rax, [rsp+220h+pcbResult]
0x180030ae2  mov     [rsp+220h+cbSecret], esi; dwFlags
0x180030ae6  lea     r9d, [rsi+4]; cbOutput
0x180030aea  mov     [rsp+220h+pbSecret], rax; pcbResult
0x180030aef  lea     r8, [rsp+220h+pbOutput]; pbOutput
0x180030af4  mov     dword ptr [rsp+220h+pbOutput], esi
0x180030af8  lea     rdx, pszProperty; "ObjectLength"
0x180030aff  mov     [rsp+220h+pcbResult], esi
0x180030b03  mov     ecx, r12d; hObject
0x180030b06  call    cs:__imp_BCryptGetProperty
0x180030b0c  mov     edi, eax
0x180030b0e  test    eax, eax
0x180030b10  js      loc_180030BCD
0x180030b16  mov     edi, dword ptr [rsp+220h+pbOutput]
0x180030b1a  call    cs:__imp_GetProcessHeap
0x180030b20  mov     r8d, edi; dwBytes
0x180030b23  xor     edx, edx; dwFlags
0x180030b25  mov     rcx, rax; hHeap
0x180030b28  call    cs:__imp_HeapAlloc
0x180030b2e  mov     rsi, rax
0x180030b31  test    rax, rax
0x180030b34  jnz     short loc_180030B40
0x180030b36  mov     edi, 0C0000017h
0x180030b3b  jmp     loc_180030BCD
0x180030b40  mov     r9d, dword ptr [rsp+220h+pbOutput]; cbHashObject
0x180030b45  lea     rdx, [rsp+220h+phHash]; phHash
0x180030b4a  mov     [rsp+220h+dwFlags], 0; dwFlags
0x180030b52  mov     r8, rax; pbHashObject
0x180030b55  mov     [rsp+220h+cbSecret], 0; cbSecret
0x180030b5d  mov     rcx, r12; hAlgorithm
0x180030b60  mov     [rsp+220h+pbSecret], 0; pbSecret
0x180030b69  call    cs:__imp_BCryptCreateHash
0x180030b6f  mov     edi, eax
0x180030b71  test    edi, edi
0x180030b73  js      short loc_180030BCD
0x180030b75  mov     rcx, [rsp+220h+phHash]; hHash
0x180030b7a  lea     rdx, pbInput; "MS-WEVT"
0x180030b81  xor     r9d, r9d; dwFlags
0x180030b84  lea     r8d, [r9+8]; cbInput
0x180030b88  call    cs:__imp_BCryptHashData
0x180030b8e  mov     edi, eax
0x180030b90  test    eax, eax
0x180030b92  js      short loc_180030BCD
0x180030b94  mov     r8d, [r14+8]; cbInput
0x180030b98  xor     r9d, r9d; dwFlags
0x180030b9b  mov     rdx, [r14]; pbInput
0x180030b9e  mov     rcx, [rsp+220h+phHash]; hHash
0x180030ba3  call    cs:__imp_BCryptHashData
0x180030ba9  mov     edi, eax
0x180030bab  test    eax, eax
0x180030bad  js      short loc_180030BCD
0x180030baf  mov     rcx, [rsp+220h+phHash]; hHash
0x180030bb4  xor     r9d, r9d; dwFlags
0x180030bb7  mov     rdx, rbx; pbOutput
0x180030bba  lea     r8d, [r9+20h]; cbOutput
0x180030bbe  call    cs:__imp_BCryptFinishHash
0x180030bc4  mov     edi, eax
0x180030bc6  xor     eax, eax
0x180030bc8  test    edi, edi
0x180030bca  cmovns  edi, eax
0x180030bcd  mov     rcx, [rsp+220h+phHash]; hHash
0x180030bd2  test    rcx, rcx
0x180030bd5  jz      short loc_180030BDD
0x180030bd7  call    cs:__imp_BCryptDestroyHash
0x180030bdd  test    rsi, rsi
0x180030be0  jz      short loc_180030BF6
0x180030be2  call    cs:__imp_GetProcessHeap
0x180030be8  mov     r8, rsi; lpMem
0x180030beb  xor     edx, edx; dwFlags
0x180030bed  mov     rcx, rax; hHeap
0x180030bf0  call    cs:__imp_HeapFree
0x180030bf6  bts     edi, 1Ch
0x180030bfa  mov     eax, edi
0x180030bfc  mov     rcx, [rbp+120h+var_40]
0x180030c03  xor     rcx, rsp; StackCookie
0x180030c06  call    __security_check_cookie
0x180030c0b  add     rsp, 1F8h
0x180030c12  pop     r14
0x180030c14  pop     r12
0x180030c16  pop     rdi
0x180030c17  pop     rsi
0x180030c18  pop     rbx
0x180030c19  pop     rbp
0x180030c1a  retn
```
