# CommandParamReceiver::GetKcv(std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x140009fa4`
- end: `0x14000a37f`
- name: `?GetKcv@CommandParamReceiver@@AEAA?AV?$vector@EU?$secure_allocator@E@wil@@@std@@AEBV23@@Z`
- size: `987`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140008784`

## callees

- `0x140002462`
- `0x1400076e8`
- `0x140007c8c`
- `0x140007d04`
- `0x140008454`
- `0x140009dd8`
- `0x140009fa4`
- `0x14000b16c`
- `0x14000bbb8`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x14000a232`
- `bcrypt!BCryptEncrypt` at `0x14000a232`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x14000a142`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x14000a142`
- `bcrypt!BCryptGetProperty` at `0x14000a0c6`
- `bcrypt!BCryptGetProperty` at `0x14000a1ab`
- `bcrypt!BCryptGetProperty` at `0x14000a0c6`
- `bcrypt!BCryptGetProperty` at `0x14000a1ab`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140009ff6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140009ff6`
- `bcrypt!BCryptDestroyKey` at `0x14000a285`
- `bcrypt!BCryptDestroyKey` at `0x14000a285`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000a2a1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000a2a1`
- `bcrypt!BCryptSetProperty` at `0x14000a059`
- `bcrypt!BCryptSetProperty` at `0x14000a059`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::GetKcv(__int64 a1, __int64 a2, __int64 a3)
{
  Output *v5; // rcx
  Output *v6; // rcx
  Output *v7; // rcx
  UCHAR *v8; // rdx
  Output *v9; // rcx
  Output *v10; // rcx
  Output *v11; // rcx
  unsigned int v12; // edx
  unsigned int v14; // [rsp+58h] [rbp-39h] BYREF
  int v15; // [rsp+5Ch] [rbp-35h]
  NTSTATUS Property; // [rsp+60h] [rbp-31h] BYREF
  UCHAR v17[4]; // [rsp+64h] [rbp-2Dh] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-21h] BYREF
  int v20; // [rsp+78h] [rbp-19h]
  PUCHAR pbKeyObject; // [rsp+80h] [rbp-11h] BYREF
  int v22; // [rsp+88h] [rbp-9h]
  _BYTE pExceptionObject[72]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 pcbResult; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v25; // [rsp+100h] [rbp+6Fh]
  unsigned int pbOutput; // [rsp+110h] [rbp+7Fh] BYREF

  v25 = a2;
  pcbResult = a1;
  v20 = 0;
  v14 = 0;
  v15 = 1;
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"3DES", L"Microsoft Primitive Provider", 0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v5, 0x12Cu);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      &pbKeyObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)&pbKeyObject;
  }
  Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v6, 0x12Eu);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      &pbKeyObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)&pbKeyObject;
  }
  LODWORD(pcbResult) = 0;
  pbOutput = 0;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v7, 0x12Fu);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      &pbKeyObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)&pbKeyObject;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    &pbKeyObject,
    pbOutput);
  v8 = *(UCHAR **)a3;
  phKey = 0;
  Property = BCryptGenerateSymmetricKey(
               phAlgorithm,
               &phKey,
               pbKeyObject,
               v22 - (_DWORD)pbKeyObject,
               v8,
               *(_DWORD *)(a3 + 8) - (_DWORD)v8,
               0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v9, 0x130u);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      pExceptionObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)pExceptionObject;
  }
  *(_DWORD *)v17 = 0;
  Property = BCryptGetProperty(phKey, L"BlockLength", v17, 4u, (ULONG *)&pcbResult, 0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v10, 0x12Fu);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      pExceptionObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)pExceptionObject;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    a2,
    *(unsigned int *)v17);
  v20 = 1;
  Property = BCryptEncrypt(
               phKey,
               *(PUCHAR *)a2,
               *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
               0,
               0,
               0,
               *(PUCHAR *)a2,
               *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
               (ULONG *)&pcbResult,
               0);
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v14, &Property);
  v15 = 3;
  if ( (v14 >> 30) - 1 <= 2 )
  {
    Output::DisplayErrorResource(v11, 0x132u);
    v15 = 3;
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      pExceptionObject,
      &v14);
    throw (errorlib::specific_error_exception<ntstatus_error::tag> *)pExceptionObject;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(a2, 3);
  if ( phKey )
    BCryptDestroyKey(phKey);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&pbKeyObject);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v14, v12);
  return a2;
}

```

## disassembly

```asm
0x140009fa4  mov     rax, rsp
0x140009fa7  mov     [rax+18h], rbx
0x140009fab  mov     [rax+10h], rdx
0x140009faf  mov     [rax+8], rcx
0x140009fb3  push    rbp
0x140009fb4  push    rsi
0x140009fb5  push    rdi
0x140009fb6  push    r14
0x140009fb8  push    r15
0x140009fba  lea     rbp, [rax-5Fh]
0x140009fbe  sub     rsp, 0C0h
0x140009fc5  mov     rsi, r8
0x140009fc8  mov     rbx, rdx
0x140009fcb  xor     r15d, r15d
0x140009fce  mov     [rbp+57h+var_70], r15d
0x140009fd2  mov     [rbp+57h+var_90], r15d
0x140009fd6  mov     [rbp+57h+var_8C], 1
0x140009fdd  mov     [rbp+57h+phAlgorithm], r15
0x140009fe1  xor     r9d, r9d; dwFlags
0x140009fe4  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140009feb  lea     rdx, pszAlgId; "3DES"
0x140009ff2  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x140009ff6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140009ffc  mov     [rbp+57h+var_88], eax
0x140009fff  lea     rdx, [rbp+57h+var_88]
0x14000a003  lea     rcx, [rbp+57h+var_90]
0x14000a007  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a00c  lea     r14d, [r15+3]
0x14000a010  mov     [rbp+57h+var_8C], r14d
0x14000a014  mov     edi, [rbp+57h+var_90]
0x14000a017  shr     edi, 1Eh
0x14000a01a  lea     eax, [rdi-1]
0x14000a01d  cmp     eax, 2
0x14000a020  ja      short loc_14000A03C
0x14000a022  mov     edx, 12Ch; int
0x14000a027  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a02c  mov     [rbp+57h+var_8C], r14d
0x14000a030  lea     eax, [rdi-1]
0x14000a033  cmp     eax, 2
0x14000a036  jbe     loc_14000A2E9
0x14000a03c  mov     [rsp+0E0h+dwFlags], r15d; dwFlags
0x14000a041  mov     r9d, 20h ; ' '; cbInput
0x14000a047  lea     r8, pbInput; "ChainingModeCBC"
0x14000a04e  lea     rdx, pszProperty; "ChainingMode"
0x14000a055  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14000a059  call    cs:__imp_BCryptSetProperty
0x14000a05f  mov     [rbp+57h+var_88], eax
0x14000a062  lea     rdx, [rbp+57h+var_88]
0x14000a066  lea     rcx, [rbp+57h+var_90]
0x14000a06a  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a06f  mov     [rbp+57h+var_8C], r14d
0x14000a073  mov     edi, [rbp+57h+var_90]
0x14000a076  shr     edi, 1Eh
0x14000a079  lea     eax, [rdi-1]
0x14000a07c  cmp     eax, 2
0x14000a07f  ja      short loc_14000A09B
0x14000a081  mov     edx, 12Eh; int
0x14000a086  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a08b  mov     [rbp+57h+var_8C], r14d
0x14000a08f  lea     eax, [rdi-1]
0x14000a092  cmp     eax, 2
0x14000a095  jbe     loc_14000A307
0x14000a09b  mov     dword ptr [rbp+57h+pcbResult], r15d
0x14000a09f  mov     [rbp+57h+pbOutput], r15d
0x14000a0a3  mov     [rsp+0E0h+cbSecret], r15d; dwFlags
0x14000a0a8  lea     rax, [rbp+57h+pcbResult]
0x14000a0ac  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcbResult
0x14000a0b1  mov     r9d, 4; cbOutput
0x14000a0b7  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14000a0bb  lea     rdx, aObjectlength; "ObjectLength"
0x14000a0c2  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14000a0c6  call    cs:__imp_BCryptGetProperty
0x14000a0cc  mov     [rbp+57h+var_88], eax
0x14000a0cf  lea     rdx, [rbp+57h+var_88]
0x14000a0d3  lea     rcx, [rbp+57h+var_90]
0x14000a0d7  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a0dc  mov     [rbp+57h+var_8C], r14d
0x14000a0e0  mov     edi, [rbp+57h+var_90]
0x14000a0e3  shr     edi, 1Eh
0x14000a0e6  lea     eax, [rdi-1]
0x14000a0e9  cmp     eax, 2
0x14000a0ec  ja      short loc_14000A108
0x14000a0ee  mov     edx, 12Fh; int
0x14000a0f3  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a0f8  mov     [rbp+57h+var_8C], r14d
0x14000a0fc  lea     eax, [rdi-1]
0x14000a0ff  cmp     eax, 2
0x14000a102  jbe     loc_14000A325
0x14000a108  mov     edx, [rbp+57h+pbOutput]
0x14000a10b  lea     rcx, [rbp+57h+pbKeyObject]
0x14000a10f  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x14000a114  nop
0x14000a115  mov     rdx, [rsi]
0x14000a118  mov     r8, [rbp+57h+pbKeyObject]; pbKeyObject
0x14000a11c  mov     [rbp+57h+phKey], r15
0x14000a120  mov     eax, [rsi+8]
0x14000a123  sub     eax, edx
0x14000a125  mov     r9d, [rbp+57h+var_60]
0x14000a129  sub     r9d, r8d; cbKeyObject
0x14000a12c  mov     [rsp+0E0h+var_B0], r15d; dwFlags
0x14000a131  mov     [rsp+0E0h+cbSecret], eax; cbSecret
0x14000a135  mov     qword ptr [rsp+0E0h+dwFlags], rdx; pbSecret
0x14000a13a  lea     rdx, [rbp+57h+phKey]; phKey
0x14000a13e  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000a142  call    cs:__imp_BCryptGenerateSymmetricKey
0x14000a148  mov     [rbp+57h+var_88], eax
0x14000a14b  lea     rdx, [rbp+57h+var_88]
0x14000a14f  lea     rcx, [rbp+57h+var_90]
0x14000a153  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a158  mov     [rbp+57h+var_8C], r14d
0x14000a15c  mov     edi, [rbp+57h+var_90]
0x14000a15f  shr     edi, 1Eh
0x14000a162  lea     eax, [rdi-1]
0x14000a165  cmp     eax, 2
0x14000a168  ja      short loc_14000A184
0x14000a16a  mov     edx, 130h; int
0x14000a16f  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a174  mov     [rbp+57h+var_8C], r14d
0x14000a178  lea     eax, [rdi-1]
0x14000a17b  cmp     eax, 2
0x14000a17e  jbe     loc_14000A343
0x14000a184  mov     dword ptr [rbp+57h+var_84], r15d
0x14000a188  mov     [rsp+0E0h+cbSecret], r15d; dwFlags
0x14000a18d  lea     rax, [rbp+57h+pcbResult]
0x14000a191  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcbResult
0x14000a196  mov     r9d, 4; cbOutput
0x14000a19c  lea     r8, [rbp+57h+var_84]; pbOutput
0x14000a1a0  lea     rdx, aBlocklength; "BlockLength"
0x14000a1a7  mov     rcx, [rbp+57h+phKey]; hObject
0x14000a1ab  call    cs:__imp_BCryptGetProperty
0x14000a1b1  mov     [rbp+57h+var_88], eax
0x14000a1b4  lea     rdx, [rbp+57h+var_88]
0x14000a1b8  lea     rcx, [rbp+57h+var_90]
0x14000a1bc  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a1c1  mov     [rbp+57h+var_8C], r14d
0x14000a1c5  mov     edi, [rbp+57h+var_90]
0x14000a1c8  shr     edi, 1Eh
0x14000a1cb  lea     eax, [rdi-1]
0x14000a1ce  cmp     eax, 2
0x14000a1d1  ja      short loc_14000A1ED
0x14000a1d3  mov     edx, 12Fh; int
0x14000a1d8  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a1dd  mov     [rbp+57h+var_8C], r14d
0x14000a1e1  lea     eax, [rdi-1]
0x14000a1e4  cmp     eax, 2
0x14000a1e7  jbe     loc_14000A361
0x14000a1ed  mov     edx, dword ptr [rbp+57h+var_84]
0x14000a1f0  mov     rcx, rbx
0x14000a1f3  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x14000a1f8  mov     [rbp+57h+var_70], 1
0x14000a1ff  mov     r8d, [rbx+8]
0x14000a203  sub     r8d, [rbx]; cbInput
0x14000a206  mov     rdx, [rbx]; pbInput
0x14000a209  mov     [rsp+48h], r15d; dwFlags
0x14000a20e  lea     rax, [rbp+57h+pcbResult]
0x14000a212  mov     [rsp+0E0h+var_A0], rax; pcbResult
0x14000a217  mov     [rsp+0E0h+cbOutput], r8d; cbOutput
0x14000a21c  mov     qword ptr [rsp+0E0h+var_B0], rdx; pbOutput
0x14000a221  mov     [rsp+0E0h+cbSecret], r15d; cbIV
0x14000a226  mov     qword ptr [rsp+0E0h+dwFlags], r15; pbIV
0x14000a22b  xor     r9d, r9d; pPaddingInfo
0x14000a22e  mov     rcx, [rbp+57h+phKey]; hKey
0x14000a232  call    cs:__imp_BCryptEncrypt
0x14000a238  mov     [rbp+57h+var_88], eax
0x14000a23b  lea     rdx, [rbp+57h+var_88]
0x14000a23f  lea     rcx, [rbp+57h+var_90]
0x14000a243  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x14000a248  mov     [rbp+57h+var_8C], r14d
0x14000a24c  mov     edi, [rbp+57h+var_90]
0x14000a24f  shr     edi, 1Eh
0x14000a252  lea     eax, [rdi-1]
0x14000a255  cmp     eax, 2
0x14000a258  ja      short loc_14000A270
0x14000a25a  mov     edx, 132h; int
0x14000a25f  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000a264  mov     [rbp+57h+var_8C], r14d
0x14000a268  lea     eax, [rdi-1]
0x14000a26b  cmp     eax, 2
0x14000a26e  jbe     short loc_14000A2CB
0x14000a270  mov     rdx, r14
0x14000a273  mov     rcx, rbx
0x14000a276  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x14000a27b  nop
0x14000a27c  mov     rcx, [rbp+57h+phKey]; hKey
0x14000a280  test    rcx, rcx
0x14000a283  jz      short loc_14000A28C
0x14000a285  call    cs:__imp_BCryptDestroyKey
0x14000a28b  nop
0x14000a28c  lea     rcx, [rbp+57h+pbKeyObject]
0x14000a290  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x14000a295  nop
0x14000a296  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000a29a  test    rcx, rcx
0x14000a29d  jz      short loc_14000A2A8
0x14000a29f  xor     edx, edx; dwFlags
0x14000a2a1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a2a7  nop
0x14000a2a8  lea     rcx, [rbp+57h+var_90]
0x14000a2ac  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a2b1  mov     rax, rbx
0x14000a2b4  mov     rbx, [rsp+0E0h+arg_10]
0x14000a2bc  add     rsp, 0C0h
0x14000a2c3  pop     r15
0x14000a2c5  pop     r14
0x14000a2c7  pop     rdi
0x14000a2c8  pop     rsi
0x14000a2c9  pop     rbp
0x14000a2ca  retn
0x14000a2cb  lea     rdx, [rbp+57h+var_90]
0x14000a2cf  lea     rcx, [rbp+57h+pExceptionObject]
0x14000a2d3  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a2d8  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a2df  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000a2e3  call    _CxxThrowException_0
0x14000a2e9  lea     rdx, [rbp+57h+var_90]
0x14000a2ed  lea     rcx, [rbp+57h+pbKeyObject]
0x14000a2f1  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a2f6  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a2fd  lea     rcx, [rbp+57h+pbKeyObject]; pExceptionObject
0x14000a301  call    _CxxThrowException_0
0x14000a307  lea     rdx, [rbp+57h+var_90]
0x14000a30b  lea     rcx, [rbp+57h+pbKeyObject]
0x14000a30f  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a314  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a31b  lea     rcx, [rbp+57h+pbKeyObject]; pExceptionObject
0x14000a31f  call    _CxxThrowException_0
0x14000a325  lea     rdx, [rbp+57h+var_90]
0x14000a329  lea     rcx, [rbp+57h+pbKeyObject]
0x14000a32d  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a332  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a339  lea     rcx, [rbp+57h+pbKeyObject]; pExceptionObject
0x14000a33d  call    _CxxThrowException_0
0x14000a343  lea     rdx, [rbp+57h+var_90]
0x14000a347  lea     rcx, [rbp+57h+pExceptionObject]
0x14000a34b  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a350  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a357  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000a35b  call    _CxxThrowException_0
0x14000a361  lea     rdx, [rbp+57h+var_90]
0x14000a365  lea     rcx, [rbp+57h+pExceptionObject]
0x14000a369  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000a36e  lea     rdx, _TI4?AV?$specific_error_exception@Utag@ntstatus_error@@@errorlib@@; pThrowInfo
0x14000a375  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000a379  call    _CxxThrowException_0
```
