# WkstDecryptDataWithAES

- ea: `0x18002f4f8`
- end: `0x18002f72a`
- name: `WkstDecryptDataWithAES`
- size: `562`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f730`

## callees

- `0x18001e420`
- `0x18002f4f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6db`
- `bcrypt!BCryptDestroyKey` at `0x18002f6ea`
- `bcrypt!BCryptDestroyKey` at `0x18002f6ea`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002f60e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002f60e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f6fb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f6fb`
- `bcrypt!BCryptGetProperty` at `0x18002f5a8`
- `bcrypt!BCryptGetProperty` at `0x18002f5a8`
- `bcrypt!BCryptDecrypt` at `0x18002f652`
- `bcrypt!BCryptDecrypt` at `0x18002f6b4`
- `bcrypt!BCryptDecrypt` at `0x18002f652`
- `bcrypt!BCryptDecrypt` at `0x18002f6b4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f578`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f578`
- `bcrypt!BCryptSetProperty` at `0x18002f5dc`
- `bcrypt!BCryptSetProperty` at `0x18002f5dc`

## pseudocode

```c
__int64 __fastcall WkstDecryptDataWithAES(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbIV,
        __int64 a4,
        UCHAR *a5,
        ULONG cbSecret,
        UCHAR **a7,
        ULONG *a8)
{
  __int128 v11; // xmm0
  UCHAR *v12; // rdi
  NTSTATUS Property; // ebx
  ULONG cbOutput; // [rsp+50h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-45h] BYREF
  ULONG v17; // [rsp+58h] [rbp-41h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-29h] BYREF
  PUCHAR pbSecret; // [rsp+78h] [rbp-21h]
  UCHAR pbIVa[16]; // [rsp+80h] [rbp-19h] BYREF

  pbSecret = a5;
  *(_DWORD *)pbOutput = 16;
  *a8 = 0;
  *a7 = 0;
  v11 = *(_OWORD *)pbIV;
  phAlgorithm = 0;
  phKey = 0;
  v12 = 0;
  *(_OWORD *)pbIVa = v11;
  pcbResult = 0;
  cbOutput = 0;
  v17 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 && *(_DWORD *)pbOutput == 16 )
    {
      Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIV, 0x10u, 0, 0, &cbOutput, 1u);
          if ( Property >= 0 )
          {
            v12 = (UCHAR *)LocalAlloc(0x40u, cbOutput);
            if ( v12 )
            {
              Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIVa, 0x10u, v12, cbOutput, &v17, 1u);
              if ( Property >= 0 )
              {
                if ( v17 <= cbOutput )
                {
                  *a8 = v17;
                  *a7 = v12;
                  v12 = 0;
                }
                else
                {
                  Property = -1073741811;
                }
              }
            }
            else
            {
              Property = -1073741670;
            }
          }
        }
      }
    }
  }
  LocalFree(v12);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18002f4f8  mov     [rsp-8+arg_18], rbx
0x18002f4fd  push    rbp
0x18002f4fe  push    rsi
0x18002f4ff  push    rdi
0x18002f500  push    r12
0x18002f502  push    r13
0x18002f504  push    r14
0x18002f506  push    r15
0x18002f508  lea     rbp, [rsp-7]
0x18002f50d  sub     rsp, 0A0h
0x18002f514  mov     rax, cs:__security_cookie
0x18002f51b  xor     rax, rsp
0x18002f51e  mov     [rbp+37h+var_40], rax
0x18002f522  mov     rax, [rbp+37h+arg_20]
0x18002f526  mov     r13, r8
0x18002f529  mov     r12, [rbp+37h+arg_38]
0x18002f52d  mov     r14d, edx
0x18002f530  mov     r15, [rbp+37h+arg_30]
0x18002f534  lea     rdx, pszAlgId; "AES"
0x18002f53b  mov     [rbp+37h+pbSecret], rax
0x18002f53f  mov     rsi, rcx
0x18002f542  xor     eax, eax
0x18002f544  mov     dword ptr [rbp+37h+pbOutput], 10h
0x18002f54b  mov     [r12], eax
0x18002f54f  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x18002f553  mov     [r15], rax
0x18002f556  xor     r9d, r9d; dwFlags
0x18002f559  movups  xmm0, xmmword ptr [r8]
0x18002f55d  xor     r8d, r8d; pszImplementation
0x18002f560  mov     [rbp+37h+phAlgorithm], rax
0x18002f564  mov     [rbp+37h+phKey], rax
0x18002f568  mov     edi, eax
0x18002f56a  movdqu  xmmword ptr [rbp+37h+pbIV], xmm0
0x18002f56f  mov     [rbp+37h+var_60], eax
0x18002f572  mov     [rbp+37h+var_80], eax
0x18002f575  mov     [rbp+37h+var_78], eax
0x18002f578  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002f57e  mov     ebx, eax
0x18002f580  test    eax, eax
0x18002f582  js      loc_18002F6D8
0x18002f588  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18002f58c  lea     rax, [rbp+37h+var_60]
0x18002f590  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x18002f594  lea     r9d, [rdi+4]; cbOutput
0x18002f598  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x18002f59c  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18002f5a1  lea     rdx, pszProperty; "BlockLength"
0x18002f5a8  call    cs:__imp_BCryptGetProperty
0x18002f5ae  mov     ebx, eax
0x18002f5b0  test    eax, eax
0x18002f5b2  js      loc_18002F6D8
0x18002f5b8  cmp     dword ptr [rbp+37h+pbOutput], 10h
0x18002f5bc  jnz     loc_18002F6D8
0x18002f5c2  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18002f5c6  lea     r9d, [rdi+20h]; cbInput
0x18002f5ca  lea     r8, pbInput; "ChainingModeCBC"
0x18002f5d1  mov     dword ptr [rsp+0D0h+pcbResult], edi; dwFlags
0x18002f5d5  lea     rdx, aChainingmode; "ChainingMode"
0x18002f5dc  call    cs:__imp_BCryptSetProperty
0x18002f5e2  mov     ebx, eax
0x18002f5e4  test    eax, eax
0x18002f5e6  js      loc_18002F6D8
0x18002f5ec  mov     eax, [rbp+37h+cbSecret]
0x18002f5ef  lea     rdx, [rbp+37h+phKey]; phKey
0x18002f5f3  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18002f5f7  xor     r9d, r9d; cbKeyObject
0x18002f5fa  mov     [rsp+0D0h+var_A0], edi; dwFlags
0x18002f5fe  xor     r8d, r8d; pbKeyObject
0x18002f601  mov     [rsp+0D0h+dwFlags], eax; cbSecret
0x18002f605  mov     rax, [rbp+37h+pbSecret]
0x18002f609  mov     [rsp+0D0h+pcbResult], rax; pbSecret
0x18002f60e  call    cs:__imp_BCryptGenerateSymmetricKey
0x18002f614  mov     ebx, eax
0x18002f616  test    eax, eax
0x18002f618  js      loc_18002F6D8
0x18002f61e  mov     rcx, [rbp+37h+phKey]; hKey
0x18002f622  lea     rax, [rbp+37h+var_80]
0x18002f626  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18002f62e  xor     r9d, r9d; pPaddingInfo
0x18002f631  mov     [rsp+0D0h+var_90], rax; pcbResult
0x18002f636  mov     r8d, r14d; cbInput
0x18002f639  mov     [rsp+0D0h+cbOutput], edi; cbOutput
0x18002f63d  mov     rdx, rsi; pbInput
0x18002f640  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x18002f645  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x18002f64d  mov     [rsp+0D0h+pcbResult], r13; pbIV
0x18002f652  call    cs:__imp_BCryptDecrypt
0x18002f658  mov     ebx, eax
0x18002f65a  test    eax, eax
0x18002f65c  js      short loc_18002F6D8
0x18002f65e  mov     edx, [rbp+37h+var_80]; uBytes
0x18002f661  lea     ecx, [rdi+40h]; uFlags
0x18002f664  call    cs:__imp_LocalAlloc
0x18002f66a  mov     rdi, rax
0x18002f66d  test    rax, rax
0x18002f670  jnz     short loc_18002F679
0x18002f672  mov     ebx, 0C000009Ah
0x18002f677  jmp     short loc_18002F6D8
0x18002f679  mov     rcx, [rbp+37h+phKey]; hKey
0x18002f67d  lea     rax, [rbp+37h+var_78]
0x18002f681  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18002f689  xor     r9d, r9d; pPaddingInfo
0x18002f68c  mov     [rsp+0D0h+var_90], rax; pcbResult
0x18002f691  mov     r8d, r14d; cbInput
0x18002f694  mov     eax, [rbp+37h+var_80]
0x18002f697  mov     rdx, rsi; pbInput
0x18002f69a  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x18002f69e  lea     rax, [rbp+37h+pbIV]
0x18002f6a2  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x18002f6a7  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x18002f6af  mov     [rsp+0D0h+pcbResult], rax; pbIV
0x18002f6b4  call    cs:__imp_BCryptDecrypt
0x18002f6ba  mov     ebx, eax
0x18002f6bc  test    eax, eax
0x18002f6be  js      short loc_18002F6D8
0x18002f6c0  mov     eax, [rbp+37h+var_78]
0x18002f6c3  cmp     eax, [rbp+37h+var_80]
0x18002f6c6  jbe     short loc_18002F6CF
0x18002f6c8  mov     ebx, 0C000000Dh
0x18002f6cd  jmp     short loc_18002F6D8
0x18002f6cf  mov     [r12], eax
0x18002f6d3  mov     [r15], rdi
0x18002f6d6  xor     edi, edi
0x18002f6d8  mov     rcx, rdi; hMem
0x18002f6db  call    cs:__imp_LocalFree
0x18002f6e1  mov     rcx, [rbp+37h+phKey]; hKey
0x18002f6e5  test    rcx, rcx
0x18002f6e8  jz      short loc_18002F6F0
0x18002f6ea  call    cs:__imp_BCryptDestroyKey
0x18002f6f0  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18002f6f4  test    rcx, rcx
0x18002f6f7  jz      short loc_18002F701
0x18002f6f9  xor     edx, edx; dwFlags
0x18002f6fb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002f701  mov     eax, ebx
0x18002f703  mov     rcx, [rbp+37h+var_40]
0x18002f707  xor     rcx, rsp; StackCookie
0x18002f70a  call    __security_check_cookie
0x18002f70f  mov     rbx, [rsp+0D0h+arg_18]
0x18002f717  add     rsp, 0A0h
0x18002f71e  pop     r15
0x18002f720  pop     r14
0x18002f722  pop     r13
0x18002f724  pop     r12
0x18002f726  pop     rdi
0x18002f727  pop     rsi
0x18002f728  pop     rbp
0x18002f729  retn
```
