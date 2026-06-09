# IISCryptoEncryptDataBlob

- ea: `0x180006704`
- end: `0x180006911`
- name: `IISCryptoEncryptDataBlob`
- size: `525`
- prototype: `__int64 __fastcall(BYTE **, const void *, __int64, int, HCRYPTPROV hProv, HCRYPTKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180005820`

## callees

- `0x18000478c`
- `0x180004808`
- `0x180004870`
- `0x180006704`
- `0x180006918`
- `0x180006a3c`
- `0x180006a98`
- `0x1800083d2`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800067b6`
- `KERNEL32!EnterCriticalSection` at `0x180006876`
- `KERNEL32!EnterCriticalSection` at `0x1800067b6`
- `KERNEL32!EnterCriticalSection` at `0x180006876`
- `KERNEL32!LeaveCriticalSection` at `0x1800067f2`
- `KERNEL32!LeaveCriticalSection` at `0x180006832`
- `KERNEL32!LeaveCriticalSection` at `0x1800068b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800067f2`
- `KERNEL32!LeaveCriticalSection` at `0x180006832`
- `KERNEL32!LeaveCriticalSection` at `0x1800068b1`
- `ADVAPI32!CryptEncrypt` at `0x1800067de`
- `ADVAPI32!CryptEncrypt` at `0x1800068a0`
- `ADVAPI32!CryptEncrypt` at `0x1800067de`
- `ADVAPI32!CryptEncrypt` at `0x1800068a0`
- `ADVAPI32!CryptSignHashA` at `0x1800068e8`
- `ADVAPI32!CryptSignHashA` at `0x1800068e8`
- `ole32!CoTaskMemFree` at `0x18000680e`
- `ole32!CoTaskMemFree` at `0x18000680e`

## pseudocode

```c
__int64 __fastcall IISCryptoEncryptDataBlob(
        BYTE **a1,
        const void *a2,
        __int64 a3,
        int a4,
        HCRYPTPROV hProv,
        HCRYPTKEY hKey)
{
  __int64 result; // rax
  BYTE *v10; // rdi
  int HashLength; // ebx
  struct _IC_BLOB *Blob; // rax
  BYTE *pbData; // rbx
  DWORD pdwDataLen; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwSigLen; // [rsp+44h] [rbp-Ch] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwBufLen; // [rsp+90h] [rbp+40h] BYREF

  dwBufLen = a3;
  pdwDataLen = 0;
  pdwSigLen = 0;
  if ( dword_18000FC34 )
  {
    v10 = 0;
    hHash = 0;
    HashLength = IISCryptoCreateHash(&hHash, hProv);
    if ( HashLength >= 0 )
    {
      if ( !hHash )
        return (unsigned int)HashLength;
      HashLength = IcpGetHashLength(&pdwSigLen, hProv);
      if ( HashLength >= 0 )
      {
        dwBufLen += 4;
        pdwDataLen = dwBufLen;
        EnterCriticalSection(&IcpGlobals);
        if ( CryptEncrypt(hKey, 0, 1, 0, 0, &pdwDataLen, dwBufLen) )
        {
          LeaveCriticalSection(&IcpGlobals);
          Blob = IcpCreateBlob(1648649033, pdwDataLen, pdwSigLen);
          v10 = (BYTE *)Blob;
          if ( !Blob )
          {
            HashLength = -2147024888;
            goto LABEL_11;
          }
          pbData = (BYTE *)Blob + 16;
          *((_DWORD *)Blob + 4) = a4;
          memcpy_0((char *)Blob + 20, a2, dwBufLen - 4LL);
          EnterCriticalSection(&IcpGlobals);
          if ( CryptEncrypt(hKey, hHash, 1, 0, pbData, &dwBufLen, pdwDataLen) )
          {
            LeaveCriticalSection(&IcpGlobals);
            if ( CryptSignHashA(hHash, 2u, 0, 0, &v10[((*((_DWORD *)v10 + 2) + 7) & 0xFFFFFFF8) + 16], &pdwSigLen) )
            {
              IISCryptoDestroyHash(hHash);
              result = 0;
              *a1 = v10;
              return result;
            }
            HashLength = IcpGetLastError();
            goto LABEL_11;
          }
        }
        HashLength = IcpGetLastError();
        LeaveCriticalSection(&IcpGlobals);
      }
    }
LABEL_11:
    if ( hHash )
      IISCryptoDestroyHash(hHash);
    if ( v10 )
      CoTaskMemFree(v10);
    return (unsigned int)HashLength;
  }
  if ( hProv == 1984918096 && hKey == 1800627539 )
    return IISCryptoCreateCleartextBlob(a1, a2, a3);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180006704  mov     [rsp-28h+arg_0], rbx
0x180006709  mov     [rsp-28h+arg_8], rsi
0x18000670e  mov     [rsp-28h+arg_10], r8d
0x180006713  push    rbp
0x180006714  push    rdi
0x180006715  push    r13
0x180006717  push    r14
0x180006719  push    r15
0x18000671b  mov     rbp, rsp
0x18000671e  sub     rsp, 50h
0x180006722  cmp     cs:dword_18000FC34, 0
0x180006729  mov     r15d, r9d
0x18000672c  mov     r14, rdx
0x18000672f  mov     [rbp+var_10], 0
0x180006736  mov     rsi, rcx
0x180006739  mov     [rbp+pdwSigLen], 0
0x180006740  jnz     short loc_18000676A
0x180006742  cmp     [rbp+hProv], 764F7250h
0x18000674a  jnz     short loc_180006760
0x18000674c  cmp     [rbp+hKey], 6B536553h
0x180006754  jnz     short loc_180006760
0x180006756  call    IISCryptoCreateCleartextBlob
0x18000675b  jmp     loc_180006816
0x180006760  mov     eax, 80070057h
0x180006765  jmp     loc_180006816
0x18000676a  mov     rdx, [rbp+hProv]; hProv
0x18000676e  lea     rcx, [rbp+hHash]; phHash
0x180006772  xor     edi, edi
0x180006774  mov     [rbp+hHash], rdi
0x180006778  call    IISCryptoCreateHash
0x18000677d  mov     ebx, eax
0x18000677f  test    eax, eax
0x180006781  js      short loc_1800067F8
0x180006783  cmp     [rbp+hHash], rdi
0x180006787  jz      loc_180006814
0x18000678d  mov     rdx, [rbp+hProv]; unsigned __int64
0x180006791  lea     rcx, [rbp+pdwSigLen]; unsigned int *
0x180006795  call    ?IcpGetHashLength@@YAJPEAK_K@Z; IcpGetHashLength(ulong *,unsigned __int64)
0x18000679a  mov     ebx, eax
0x18000679c  test    eax, eax
0x18000679e  js      short loc_1800067F8
0x1800067a0  mov     eax, [rbp+arg_10]
0x1800067a3  lea     r13, ?IcpGlobals@@3U_IC_GLOBALS@@A; _IC_GLOBALS IcpGlobals
0x1800067aa  add     eax, 4
0x1800067ad  mov     rcx, r13; lpCriticalSection
0x1800067b0  mov     [rbp+arg_10], eax
0x1800067b3  mov     [rbp+var_10], eax
0x1800067b6  call    cs:__imp_EnterCriticalSection
0x1800067bc  mov     eax, [rbp+arg_10]
0x1800067bf  lea     r8d, [rdi+1]; Final
0x1800067c3  mov     rcx, [rbp+hKey]; hKey
0x1800067c7  xor     r9d, r9d; dwFlags
0x1800067ca  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x1800067ce  xor     edx, edx; hHash
0x1800067d0  lea     rax, [rbp+var_10]
0x1800067d4  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x1800067d9  mov     [rsp+50h+pbData], rdi; pbData
0x1800067de  call    cs:__imp_CryptEncrypt
0x1800067e4  test    eax, eax
0x1800067e6  jnz     short loc_18000682F
0x1800067e8  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800067ed  mov     rcx, r13; lpCriticalSection
0x1800067f0  mov     ebx, eax
0x1800067f2  call    cs:__imp_LeaveCriticalSection
0x1800067f8  mov     rcx, [rbp+hHash]
0x1800067fc  test    rcx, rcx
0x1800067ff  jz      short loc_180006806
0x180006801  call    IISCryptoDestroyHash
0x180006806  test    rdi, rdi
0x180006809  jz      short loc_180006814
0x18000680b  mov     rcx, rdi; pv
0x18000680e  call    cs:__imp_CoTaskMemFree
0x180006814  mov     eax, ebx
0x180006816  lea     r11, [rsp+50h+var_s0]
0x18000681b  mov     rbx, [r11+30h]
0x18000681f  mov     rsi, [r11+38h]
0x180006823  mov     rsp, r11
0x180006826  pop     r15
0x180006828  pop     r14
0x18000682a  pop     r13
0x18000682c  pop     rdi
0x18000682d  pop     rbp
0x18000682e  retn
0x18000682f  mov     rcx, r13; lpCriticalSection
0x180006832  call    cs:__imp_LeaveCriticalSection
0x180006838  mov     r8d, [rbp+pdwSigLen]; unsigned int
0x18000683c  mov     ecx, 62446349h; unsigned int
0x180006841  mov     edx, [rbp+var_10]; unsigned int
0x180006844  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x180006849  mov     rdi, rax
0x18000684c  test    rax, rax
0x18000684f  jnz     short loc_180006858
0x180006851  mov     ebx, 80070008h
0x180006856  jmp     short loc_1800067F8
0x180006858  lea     rbx, [rax+10h]
0x18000685c  mov     rdx, r14; Src
0x18000685f  mov     [rbx], r15d
0x180006862  lea     rcx, [rbx+4]; void *
0x180006866  mov     r8d, [rbp+arg_10]
0x18000686a  sub     r8, 4; Size
0x18000686e  call    memcpy_0
0x180006873  mov     rcx, r13; lpCriticalSection
0x180006876  call    cs:__imp_EnterCriticalSection
0x18000687c  mov     eax, [rbp+var_10]
0x18000687f  xor     r9d, r9d; dwFlags
0x180006882  mov     rdx, [rbp+hHash]; hHash
0x180006886  mov     rcx, [rbp+hKey]; hKey
0x18000688a  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x18000688e  lea     rax, [rbp+arg_10]
0x180006892  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x180006897  lea     r8d, [r9+1]; Final
0x18000689b  mov     [rsp+50h+pbData], rbx; pbData
0x1800068a0  call    cs:__imp_CryptEncrypt
0x1800068a6  test    eax, eax
0x1800068a8  jz      loc_1800067E8
0x1800068ae  mov     rcx, r13; lpCriticalSection
0x1800068b1  call    cs:__imp_LeaveCriticalSection
0x1800068b7  mov     eax, [rdi+8]
0x1800068ba  mov     ecx, 0FFFFFFF8h
0x1800068bf  add     eax, 7
0x1800068c2  xor     r9d, r9d; dwFlags
0x1800068c5  and     rax, rcx
0x1800068c8  xor     r8d, r8d; szDescription
0x1800068cb  add     rax, 10h
0x1800068cf  lea     rcx, [rbp+pdwSigLen]
0x1800068d3  mov     [rsp+50h+pdwDataLen], rcx; pdwSigLen
0x1800068d8  add     rax, rdi
0x1800068db  mov     rcx, [rbp+hHash]; hHash
0x1800068df  lea     edx, [r9+2]; dwKeySpec
0x1800068e3  mov     [rsp+50h+pbData], rax; pbSignature
0x1800068e8  call    cs:__imp_CryptSignHashA
0x1800068ee  test    eax, eax
0x1800068f0  jnz     short loc_1800068FE
0x1800068f2  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800068f7  mov     ebx, eax
0x1800068f9  jmp     loc_1800067F8
0x1800068fe  mov     rcx, [rbp+hHash]
0x180006902  call    IISCryptoDestroyHash
0x180006907  xor     eax, eax
0x180006909  mov     [rsi], rdi
0x18000690c  jmp     loc_180006816
```
