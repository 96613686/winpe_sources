# CDumpWriter::SetupKeys(void)

- ea: `0x1800025cc`
- end: `0x1800027d9`
- name: `?SetupKeys@CDumpWriter@@AEAAJXZ`
- size: `525`
- prototype: `int __fastcall(CDumpWriter *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002440`

## callees

- `0x180001400`
- `0x1800025cc`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18000276f`
- `bcrypt!BCryptGetProperty` at `0x1800027a3`
- `bcrypt!BCryptGetProperty` at `0x18000276f`
- `bcrypt!BCryptGetProperty` at `0x1800027a3`
- `bcrypt!BCryptImportKeyPair` at `0x180002737`
- `bcrypt!BCryptImportKeyPair` at `0x180002737`
- `bcrypt!BCryptImportKey` at `0x1800026dd`
- `bcrypt!BCryptImportKey` at `0x1800026dd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180002649`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800026fc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180002649`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800026fc`
- `bcrypt!BCryptGenRandom` at `0x18000260c`
- `bcrypt!BCryptGenRandom` at `0x180002627`
- `bcrypt!BCryptGenRandom` at `0x18000260c`
- `bcrypt!BCryptGenRandom` at `0x180002627`
- `bcrypt!BCryptSetProperty` at `0x180002673`
- `bcrypt!BCryptSetProperty` at `0x180002673`

## pseudocode

```c
int __fastcall CDumpWriter::SetupKeys(CDumpWriter *this)
{
  NTSTATUS Property; // eax
  BCRYPT_HANDLE *v3; // rdi
  BCRYPT_HANDLE v4; // rcx
  __int128 v5; // xmm1
  void *v6; // rcx
  void *v7; // rcx
  ULONG pcbResult; // [rsp+50h] [rbp+7h] BYREF
  UCHAR pbInput[4]; // [rsp+58h] [rbp+Fh] BYREF
  int v11; // [rsp+5Ch] [rbp+13h]
  int v12; // [rsp+60h] [rbp+17h]
  __int128 v13; // [rsp+64h] [rbp+1Bh]
  __int128 v14; // [rsp+74h] [rbp+2Bh]

  Property = BCryptGenRandom(0, (PUCHAR)this + 24, 0x20u, 2u);
  if ( Property < 0 )
    return Property | 0x10000000;
  Property = BCryptGenRandom(0, (PUCHAR)this + 56, 0x10u, 2u);
  if ( Property < 0 )
    return Property | 0x10000000;
  v3 = (BCRYPT_HANDLE *)((char *)this + 80);
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 10, L"AES", 0, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  Property = BCryptSetProperty(*v3, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  v4 = *v3;
  v5 = *(_OWORD *)((char *)this + 40);
  v13 = *(_OWORD *)((char *)this + 24);
  v14 = v5;
  *(_DWORD *)pbInput = 1296188491;
  v11 = 1;
  v12 = 32;
  Property = BCryptImportKey(v4, 0, L"KeyDataBlob", (BCRYPT_KEY_HANDLE *)this + 11, 0, 0, pbInput, 0x2Cu, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 9, L"RSA", 0, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  Property = BCryptImportKeyPair(
               *((BCRYPT_ALG_HANDLE *)this + 9),
               0,
               L"RSAPUBLICBLOB",
               (BCRYPT_KEY_HANDLE *)this + 12,
               (PUCHAR)"RSA1",
               0x21Bu,
               0);
  if ( Property < 0 )
    return Property | 0x10000000;
  v6 = (void *)*((_QWORD *)this + 12);
  pcbResult = 0;
  Property = BCryptGetProperty(v6, L"BlockLength", (PUCHAR)this + 104, 4u, &pcbResult, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  v7 = (void *)*((_QWORD *)this + 11);
  pcbResult = 0;
  Property = BCryptGetProperty(v7, L"BlockLength", (PUCHAR)this + 108, 4u, &pcbResult, 0);
  if ( Property < 0 )
    return Property | 0x10000000;
  else
    return 0;
}

```

## disassembly

```asm
0x1800025cc  mov     [rsp-8+arg_8], rbx
0x1800025d1  mov     [rsp-8+arg_10], rsi
0x1800025d6  push    rbp
0x1800025d7  push    rdi
0x1800025d8  push    r14
0x1800025da  lea     rbp, [rsp-47h]
0x1800025df  sub     rsp, 90h
0x1800025e6  mov     rax, cs:__security_cookie
0x1800025ed  xor     rax, rsp
0x1800025f0  mov     [rbp+57h+var_18], rax
0x1800025f4  mov     edi, 2
0x1800025f9  lea     rdx, [rcx+18h]; pbBuffer
0x1800025fd  mov     rbx, rcx
0x180002600  mov     r9d, edi; dwFlags
0x180002603  xor     ecx, ecx; hAlgorithm
0x180002605  lea     r14d, [rdi+1Eh]
0x180002609  mov     r8d, r14d; cbBuffer
0x18000260c  call    cs:__imp_BCryptGenRandom
0x180002612  test    eax, eax
0x180002614  js      loc_1800027B1
0x18000261a  lea     rdx, [rbx+38h]; pbBuffer
0x18000261e  mov     r9d, edi; dwFlags
0x180002621  xor     ecx, ecx; hAlgorithm
0x180002623  lea     r8d, [rdi+0Eh]; cbBuffer
0x180002627  call    cs:__imp_BCryptGenRandom
0x18000262d  test    eax, eax
0x18000262f  js      loc_1800027B1
0x180002635  lea     rdi, [rbx+50h]
0x180002639  xor     r9d, r9d; dwFlags
0x18000263c  mov     rcx, rdi; phAlgorithm
0x18000263f  lea     rdx, pszAlgId; "AES"
0x180002646  xor     r8d, r8d; pszImplementation
0x180002649  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000264f  test    eax, eax
0x180002651  js      loc_1800027B1
0x180002657  mov     rcx, [rdi]; hObject
0x18000265a  lea     r8, pbInput; "ChainingModeCBC"
0x180002661  mov     r9d, r14d; cbInput
0x180002664  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18000266c  lea     rdx, pszProperty; "ChainingMode"
0x180002673  call    cs:__imp_BCryptSetProperty
0x180002679  test    eax, eax
0x18000267b  js      loc_1800027B1
0x180002681  movups  xmm0, xmmword ptr [rbx+18h]
0x180002685  mov     rcx, [rdi]; hAlgorithm
0x180002688  lea     rax, [rbp+57h+var_48]
0x18000268c  movups  xmm1, xmmword ptr [rbx+28h]
0x180002690  mov     [rsp+0A0h+var_60], 0; dwFlags
0x180002698  lea     r9, [rbx+58h]; phKey
0x18000269c  mov     [rsp+0A0h+cbInput], 2Ch ; ','; cbInput
0x1800026a4  lea     r8, pszBlobType; "KeyDataBlob"
0x1800026ab  mov     [rsp+0A0h+pbInput], rax; pbInput
0x1800026b0  xor     edx, edx; hImportKey
0x1800026b2  mov     [rsp+0A0h+cbKeyObject], 0; cbKeyObject
0x1800026ba  movups  [rbp+57h+var_3C], xmm0
0x1800026be  mov     qword ptr [rsp+0A0h+dwFlags], 0; pbKeyObject
0x1800026c7  movups  [rbp+57h+var_2C], xmm1
0x1800026cb  mov     dword ptr [rbp+57h+var_48], 4D42444Bh
0x1800026d2  mov     [rbp+57h+var_44], 1
0x1800026d9  mov     [rbp+57h+var_40], r14d
0x1800026dd  call    cs:__imp_BCryptImportKey
0x1800026e3  test    eax, eax
0x1800026e5  js      loc_1800027B1
0x1800026eb  xor     r9d, r9d; dwFlags
0x1800026ee  lea     rdx, aRsa; "RSA"
0x1800026f5  xor     r8d, r8d; pszImplementation
0x1800026f8  lea     rcx, [rbx+48h]; phAlgorithm
0x1800026fc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180002702  test    eax, eax
0x180002704  js      loc_1800027B1
0x18000270a  mov     rcx, [rbx+48h]; hAlgorithm
0x18000270e  lea     rax, aRsa1; "RSA1"
0x180002715  mov     dword ptr [rsp+0A0h+pbInput], 0; dwFlags
0x18000271d  lea     r9, [rbx+60h]; phKey
0x180002721  mov     [rsp+0A0h+cbKeyObject], 21Bh; cbInput
0x180002729  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180002730  xor     edx, edx; hImportKey
0x180002732  mov     qword ptr [rsp+0A0h+dwFlags], rax; pbInput
0x180002737  call    cs:__imp_BCryptImportKeyPair
0x18000273d  test    eax, eax
0x18000273f  js      short loc_1800027B1
0x180002741  mov     rcx, [rbx+60h]; hObject
0x180002745  lea     rax, [rbp+57h+pcbResult]
0x180002749  lea     edi, [r14-1Ch]
0x18000274d  mov     [rsp+0A0h+cbKeyObject], 0; dwFlags
0x180002755  mov     r9d, edi; cbOutput
0x180002758  mov     [rbp+57h+pcbResult], 0
0x18000275f  lea     r8, [rbx+68h]; pbOutput
0x180002763  mov     qword ptr [rsp+0A0h+dwFlags], rax; pcbResult
0x180002768  lea     rdx, aBlocklength; "BlockLength"
0x18000276f  call    cs:__imp_BCryptGetProperty
0x180002775  test    eax, eax
0x180002777  js      short loc_1800027B1
0x180002779  mov     rcx, [rbx+58h]; hObject
0x18000277d  lea     rax, [rbp+57h+pcbResult]
0x180002781  lea     r8, [rbx+6Ch]; pbOutput
0x180002785  mov     [rsp+0A0h+cbKeyObject], 0; dwFlags
0x18000278d  mov     r9d, edi; cbOutput
0x180002790  mov     qword ptr [rsp+0A0h+dwFlags], rax; pcbResult
0x180002795  lea     rdx, aBlocklength; "BlockLength"
0x18000279c  mov     [rbp+57h+pcbResult], 0
0x1800027a3  call    cs:__imp_BCryptGetProperty
0x1800027a9  test    eax, eax
0x1800027ab  js      short loc_1800027B1
0x1800027ad  xor     eax, eax
0x1800027af  jmp     short loc_1800027B5
0x1800027b1  bts     eax, 1Ch
0x1800027b5  mov     rcx, [rbp+57h+var_18]
0x1800027b9  xor     rcx, rsp; StackCookie
0x1800027bc  call    __security_check_cookie
0x1800027c1  lea     r11, [rsp+0A0h+var_10]
0x1800027c9  mov     rbx, [r11+28h]
0x1800027cd  mov     rsi, [r11+30h]
0x1800027d1  mov     rsp, r11
0x1800027d4  pop     r14
0x1800027d6  pop     rdi
0x1800027d7  pop     rbp
0x1800027d8  retn
```
