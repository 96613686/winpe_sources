# CertCompareHashes

- ea: `0x18000b924`
- end: `0x18000b9e5`
- name: `CertCompareHashes`
- size: `193`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, void *Buf2, DWORD dwPropId)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b9ec`

## callees

- `0x1800014b0`
- `0x18000b924`
- `0x180012564`
- `0x1800125d4`
- `0x180013f0d`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b996`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000b98c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000b98c`

## pseudocode

```c
__int64 __fastcall CertCompareHashes(PCCERT_CONTEXT pCertContext, void *Buf2, DWORD dwPropId)
{
  void *v3; // rbx
  unsigned int v4; // esi
  unsigned int i; // edi
  void *v9; // rax
  DWORD pcbData; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v4 = 0;
  pcbData = 0;
  if ( pCertContext && Buf2 )
  {
    for ( i = 0; i <= 1; ++i )
    {
      Dns_Free(v3);
      v9 = (void *)Dns_Allocate(pcbData);
      v3 = v9;
      if ( !v9 )
        break;
      if ( CertGetCertificateContextProperty(pCertContext, dwPropId, v9, &pcbData) )
      {
        LOBYTE(v4) = memcmp_0(v3, Buf2, pcbData) == 0;
        break;
      }
      if ( GetLastError() != 234 )
        break;
    }
  }
  Dns_Free(v3);
  return v4;
}

```

## disassembly

```asm
0x18000b924  mov     [rsp+arg_8], rbx
0x18000b929  push    rbp
0x18000b92a  push    rsi
0x18000b92b  push    rdi
0x18000b92c  push    r14
0x18000b92e  push    r15
0x18000b930  sub     rsp, 30h
0x18000b934  mov     rax, cs:__security_cookie
0x18000b93b  xor     rax, rsp
0x18000b93e  mov     [rsp+58h+var_30], rax
0x18000b943  xor     ebx, ebx
0x18000b945  xor     esi, esi
0x18000b947  mov     [rsp+58h+pcbData], ebx
0x18000b94b  mov     r15d, r8d
0x18000b94e  mov     rbp, rdx
0x18000b951  mov     r14, rcx
0x18000b954  test    rcx, rcx
0x18000b957  jz      short loc_18000B9BD
0x18000b959  test    rdx, rdx
0x18000b95c  jz      short loc_18000B9BD
0x18000b95e  xor     edi, edi
0x18000b960  cmp     edi, 1
0x18000b963  ja      short loc_18000B9BD
0x18000b965  mov     rcx, rbx; lpMem
0x18000b968  call    Dns_Free
0x18000b96d  mov     ecx, [rsp+58h+pcbData]
0x18000b971  call    Dns_Allocate
0x18000b976  mov     rbx, rax
0x18000b979  test    rax, rax
0x18000b97c  jz      short loc_18000B9BD
0x18000b97e  lea     r9, [rsp+58h+pcbData]; pcbData
0x18000b983  mov     r8, rax; pvData
0x18000b986  mov     edx, r15d; dwPropId
0x18000b989  mov     rcx, r14; pCertContext
0x18000b98c  call    cs:__imp_CertGetCertificateContextProperty
0x18000b992  test    eax, eax
0x18000b994  jnz     short loc_18000B9A7
0x18000b996  call    cs:__imp_GetLastError
0x18000b99c  cmp     eax, 0EAh
0x18000b9a1  jnz     short loc_18000B9BD
0x18000b9a3  inc     edi
0x18000b9a5  jmp     short loc_18000B960
0x18000b9a7  mov     r8d, [rsp+58h+pcbData]; Size
0x18000b9ac  mov     rdx, rbp; Buf2
0x18000b9af  mov     rcx, rbx; Buf1
0x18000b9b2  call    memcmp_0
0x18000b9b7  test    eax, eax
0x18000b9b9  setz    sil
0x18000b9bd  mov     rcx, rbx; lpMem
0x18000b9c0  call    Dns_Free
0x18000b9c5  mov     eax, esi
0x18000b9c7  mov     rcx, [rsp+58h+var_30]
0x18000b9cc  xor     rcx, rsp; StackCookie
0x18000b9cf  call    __security_check_cookie
0x18000b9d4  mov     rbx, [rsp+58h+arg_8]
0x18000b9d9  add     rsp, 30h
0x18000b9dd  pop     r15
0x18000b9df  pop     r14
0x18000b9e1  pop     rdi
0x18000b9e2  pop     rsi
0x18000b9e3  pop     rbp
0x18000b9e4  retn
```
