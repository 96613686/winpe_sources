# SpSignIsSignerNt5

- ea: `0x14002cad0`
- end: `0x14002cc25`
- name: `SpSignIsSignerNt5`
- size: `341`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d158`

## callees

- `0x14002cad0`
- `0x140045ec6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002cb62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002cb62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cb51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cbfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cb51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cbfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002cc0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002cc0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cb94`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002caeb`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002caeb`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002cb15`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002cbb5`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002cb15`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002cbb5`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002cb31`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002cb8a`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002cb31`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002cb8a`

## string_xrefs

- `0x14002cba5`: `Unable to read EKU data.`

## pseudocode

```c
__int64 __fastcall SpSignIsSignerNt5(PCCERT_CONTEXT pCertContext)
{
  unsigned int v1; // ebp
  __int64 ThreadLogToken; // rdi
  __int64 v4; // r9
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  struct _CTL_USAGE *v7; // rax
  struct _CTL_USAGE *v8; // r14
  DWORD LastError; // eax
  __int64 i; // rbx
  const char *v11; // rcx
  __int64 v12; // rax
  HANDLE v13; // rax
  DWORD pcbUsage; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  pcbUsage = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( pCertContext )
  {
    pcbUsage = 0;
    if ( CertGetEnhancedKeyUsage(pCertContext, 0, 0, &pcbUsage) )
    {
      v5 = pcbUsage;
      ProcessHeap = GetProcessHeap();
      v7 = (struct _CTL_USAGE *)HeapAlloc(ProcessHeap, 8u, v5);
      v8 = v7;
      if ( v7 )
      {
        if ( CertGetEnhancedKeyUsage(pCertContext, 0, v7, &pcbUsage) )
        {
          for ( i = 0; (unsigned int)i < v8->cUsageIdentifier; i = (unsigned int)(i + 1) )
          {
            v11 = v8->rgpszUsageIdentifier[i];
            v12 = -1;
            do
              ++v12;
            while ( v11[v12] );
            if ( v12 == 22 && !strcmp(v11, "1.3.6.1.4.1.311.10.3.6") )
            {
              v1 = 1;
              break;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          DevRtlWriteTextLogError(ThreadLogToken, 32, 2, LastError, "Unable to read EKU data.");
        }
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v8);
      }
      else
      {
        DevRtlWriteTextLogError(ThreadLogToken, 32, 2, 14, "Unable to allocate EKU.");
      }
    }
    else
    {
      v4 = GetLastError();
      DevRtlWriteTextLogError(ThreadLogToken, 32, 2, v4, "Unable to get certificate EKU.");
    }
  }
  else
  {
    DevRtlWriteTextLogError(ThreadLogToken, 32, 2, 87, "Certificate context is missing.");
  }
  return v1;
}

```

## disassembly

```asm
0x14002cad0  mov     [rsp+arg_8], rbx
0x14002cad5  mov     [rsp+arg_10], rbp
0x14002cada  push    rsi
0x14002cadb  push    rdi
0x14002cadc  push    r14
0x14002cade  sub     rsp, 30h
0x14002cae2  xor     ebp, ebp
0x14002cae4  mov     rsi, rcx
0x14002cae7  mov     [rsp+48h+pcbUsage], ebp
0x14002caeb  call    cs:__imp_DevRtlGetThreadLogToken
0x14002caf1  mov     rdi, rax
0x14002caf4  test    rsi, rsi
0x14002caf7  jnz     short loc_14002CB20
0x14002caf9  lea     rax, aCertificateCon; "Certificate context is missing."
0x14002cb00  lea     r9d, [rbp+57h]
0x14002cb04  mov     edx, 20h ; ' '
0x14002cb09  mov     [rsp+48h+var_28], rax
0x14002cb0e  mov     rcx, rdi
0x14002cb11  lea     r8d, [rdx-1Eh]
0x14002cb15  call    cs:__imp_DevRtlWriteTextLogError
0x14002cb1b  jmp     loc_14002CC10
0x14002cb20  lea     r9, [rsp+48h+pcbUsage]; pcbUsage
0x14002cb25  mov     [rsp+48h+pcbUsage], ebp
0x14002cb29  xor     r8d, r8d; pUsage
0x14002cb2c  xor     edx, edx; dwFlags
0x14002cb2e  mov     rcx, rsi; pCertContext
0x14002cb31  call    cs:__imp_CertGetEnhancedKeyUsage
0x14002cb37  test    eax, eax
0x14002cb39  jnz     short loc_14002CB4D
0x14002cb3b  call    cs:__imp_GetLastError
0x14002cb41  mov     r9d, eax
0x14002cb44  lea     rax, aUnableToGetCer; "Unable to get certificate EKU."
0x14002cb4b  jmp     short loc_14002CB04
0x14002cb4d  mov     ebx, [rsp+48h+pcbUsage]
0x14002cb51  call    cs:__imp_GetProcessHeap
0x14002cb57  mov     r8d, ebx; dwBytes
0x14002cb5a  mov     edx, 8; dwFlags
0x14002cb5f  mov     rcx, rax; hHeap
0x14002cb62  call    cs:__imp_HeapAlloc
0x14002cb68  mov     r14, rax
0x14002cb6b  test    rax, rax
0x14002cb6e  jnz     short loc_14002CB7D
0x14002cb70  lea     rax, aUnableToAlloca; "Unable to allocate EKU."
0x14002cb77  lea     r9d, [r14+0Eh]
0x14002cb7b  jmp     short loc_14002CB04
0x14002cb7d  lea     r9, [rsp+48h+pcbUsage]; pcbUsage
0x14002cb82  mov     r8, r14; pUsage
0x14002cb85  xor     edx, edx; dwFlags
0x14002cb87  mov     rcx, rsi; pCertContext
0x14002cb8a  call    cs:__imp_CertGetEnhancedKeyUsage
0x14002cb90  test    eax, eax
0x14002cb92  jnz     short loc_14002CBBD
0x14002cb94  call    cs:__imp_GetLastError
0x14002cb9a  mov     edx, 20h ; ' '
0x14002cb9f  mov     rcx, rdi
0x14002cba2  mov     r9d, eax
0x14002cba5  lea     rax, aUnableToReadEk; "Unable to read EKU data."
0x14002cbac  mov     [rsp+48h+var_28], rax
0x14002cbb1  lea     r8d, [rdx-1Eh]
0x14002cbb5  call    cs:__imp_DevRtlWriteTextLogError
0x14002cbbb  jmp     short loc_14002CBFC
0x14002cbbd  xor     ebx, ebx
0x14002cbbf  cmp     ebx, [r14]
0x14002cbc2  jnb     short loc_14002CBFC
0x14002cbc4  mov     rax, [r14+8]
0x14002cbc8  mov     rcx, [rax+rbx*8]; Buf1
0x14002cbcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002cbd0  inc     rax
0x14002cbd3  cmp     [rcx+rax], bpl
0x14002cbd7  jnz     short loc_14002CBD0
0x14002cbd9  cmp     rax, 16h
0x14002cbdd  jnz     short loc_14002CBF3
0x14002cbdf  lea     r8d, [rax+1]; Size
0x14002cbe3  lea     rdx, a1361413111036; "1.3.6.1.4.1.311.10.3.6"
0x14002cbea  call    memcmp_0
0x14002cbef  test    eax, eax
0x14002cbf1  jz      short loc_14002CBF7
0x14002cbf3  inc     ebx
0x14002cbf5  jmp     short loc_14002CBBF
0x14002cbf7  mov     ebp, 1
0x14002cbfc  call    cs:__imp_GetProcessHeap
0x14002cc02  mov     r8, r14; lpMem
0x14002cc05  xor     edx, edx; dwFlags
0x14002cc07  mov     rcx, rax; hHeap
0x14002cc0a  call    cs:__imp_HeapFree
0x14002cc10  mov     rbx, [rsp+48h+arg_8]
0x14002cc15  mov     eax, ebp
0x14002cc17  mov     rbp, [rsp+48h+arg_10]
0x14002cc1c  add     rsp, 30h
0x14002cc20  pop     r14
0x14002cc22  pop     rdi
0x14002cc23  pop     rsi
0x14002cc24  retn
```
