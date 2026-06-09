# IcpGetHashLength(ulong *,unsigned __int64)

- ea: `0x180006918`
- end: `0x180006a33`
- name: `?IcpGetHashLength@@YAJPEAK_K@Z`
- size: `283`
- prototype: `int(unsigned int *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180006104`
- `0x180006704`

## callees

- `0x180004870`
- `0x180006918`
- `0x180006a3c`
- `0x180006a98`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000694b`
- `KERNEL32!EnterCriticalSection` at `0x18000694b`
- `KERNEL32!LeaveCriticalSection` at `0x180006964`
- `KERNEL32!LeaveCriticalSection` at `0x1800069ce`
- `KERNEL32!LeaveCriticalSection` at `0x180006a1e`
- `KERNEL32!LeaveCriticalSection` at `0x180006964`
- `KERNEL32!LeaveCriticalSection` at `0x1800069ce`
- `KERNEL32!LeaveCriticalSection` at `0x180006a1e`
- `ADVAPI32!CryptSignHashA` at `0x180006a05`
- `ADVAPI32!CryptSignHashA` at `0x180006a05`
- `ADVAPI32!CryptHashData` at `0x1800069a7`
- `ADVAPI32!CryptHashData` at `0x1800069a7`

## pseudocode

```c
__int64 __fastcall IcpGetHashLength(unsigned int *a1, HCRYPTPROV a2)
{
  signed int LastError; // ebx
  HCRYPTHASH hHash; // [rsp+50h] [rbp+18h] BYREF

  hHash = 0;
  if ( pdwSigLen )
  {
    *a1 = pdwSigLen;
    return 0;
  }
  EnterCriticalSection(&IcpGlobals);
  if ( pdwSigLen )
  {
    *a1 = pdwSigLen;
    LeaveCriticalSection(&IcpGlobals);
    return 0;
  }
  hHash = 0;
  LastError = IISCryptoCreateHash(&hHash, a2);
  if ( LastError < 0 )
    goto LABEL_11;
  if ( hHash )
  {
    if ( CryptHashData(hHash, "IIS", 4u, 0) && CryptSignHashA(hHash, 2u, 0, 0, 0, &pdwSigLen) )
    {
      *a1 = pdwSigLen;
      LeaveCriticalSection(&IcpGlobals);
      IISCryptoDestroyHash(hHash);
      return 0;
    }
    LastError = IcpGetLastError();
LABEL_11:
    if ( hHash )
      IISCryptoDestroyHash(hHash);
    goto LABEL_13;
  }
  LastError = -2147467259;
LABEL_13:
  LeaveCriticalSection(&IcpGlobals);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180006918  mov     [rsp+arg_0], rbx
0x18000691d  push    rdi
0x18000691e  sub     rsp, 30h
0x180006922  mov     eax, cs:pdwSigLen
0x180006928  mov     rbx, rdx
0x18000692b  mov     [rsp+38h+hHash], 0
0x180006934  mov     rdi, rcx
0x180006937  test    eax, eax
0x180006939  jz      short loc_180006944
0x18000693b  mov     [rcx], eax
0x18000693d  xor     eax, eax
0x18000693f  jmp     loc_1800069D6
0x180006944  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18000694b  call    cs:__imp_EnterCriticalSection
0x180006951  mov     eax, cs:pdwSigLen
0x180006957  test    eax, eax
0x180006959  jz      short loc_18000696C
0x18000695b  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180006962  mov     [rdi], eax
0x180006964  call    cs:__imp_LeaveCriticalSection
0x18000696a  jmp     short loc_18000693D
0x18000696c  mov     rdx, rbx; hProv
0x18000696f  mov     [rsp+38h+hHash], 0
0x180006978  lea     rcx, [rsp+38h+hHash]; phHash
0x18000697d  call    IISCryptoCreateHash
0x180006982  mov     ebx, eax
0x180006984  test    eax, eax
0x180006986  js      short loc_1800069B8
0x180006988  mov     rcx, [rsp+38h+hHash]; hHash
0x18000698d  test    rcx, rcx
0x180006990  jnz     short loc_180006999
0x180006992  mov     ebx, 80004005h
0x180006997  jmp     short loc_1800069C7
0x180006999  xor     r9d, r9d; dwFlags
0x18000699c  lea     rdx, aIis; "IIS"
0x1800069a3  lea     r8d, [r9+4]; dwDataLen
0x1800069a7  call    cs:__imp_CryptHashData
0x1800069ad  test    eax, eax
0x1800069af  jnz     short loc_1800069E1
0x1800069b1  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800069b6  mov     ebx, eax
0x1800069b8  mov     rcx, [rsp+38h+hHash]
0x1800069bd  test    rcx, rcx
0x1800069c0  jz      short loc_1800069C7
0x1800069c2  call    IISCryptoDestroyHash
0x1800069c7  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x1800069ce  call    cs:__imp_LeaveCriticalSection
0x1800069d4  mov     eax, ebx
0x1800069d6  mov     rbx, [rsp+38h+arg_0]
0x1800069db  add     rsp, 30h
0x1800069df  pop     rdi
0x1800069e0  retn
0x1800069e1  mov     rcx, [rsp+38h+hHash]; hHash
0x1800069e6  lea     rax, pdwSigLen
0x1800069ed  xor     r9d, r9d; dwFlags
0x1800069f0  mov     [rsp+38h+pdwSigLen], rax; pdwSigLen
0x1800069f5  xor     r8d, r8d; szDescription
0x1800069f8  mov     [rsp+38h+pbSignature], 0; pbSignature
0x180006a01  lea     edx, [r9+2]; dwKeySpec
0x180006a05  call    cs:__imp_CryptSignHashA
0x180006a0b  test    eax, eax
0x180006a0d  jz      short loc_1800069B1
0x180006a0f  mov     eax, cs:pdwSigLen
0x180006a15  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180006a1c  mov     [rdi], eax
0x180006a1e  call    cs:__imp_LeaveCriticalSection
0x180006a24  mov     rcx, [rsp+38h+hHash]
0x180006a29  call    IISCryptoDestroyHash
0x180006a2e  jmp     loc_18000693D
```
