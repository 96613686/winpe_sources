# TpmAttiShaHash

- ea: `0x180098550`
- end: `0x180098969`
- name: `TpmAttiShaHash`
- size: `1049`
- prototype: `__int64 __fastcall(wchar_t *String1, PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG cbOutput, __int64)`
- caller_count: `10`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180063cdc`
- `0x1800928b8`
- `0x18009481c`
- `0x180095824`
- `0x180095f84`
- `0x1800960f4`
- `0x180096564`
- `0x180097028`
- `0x1800996f0`
- `0x18009a040`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x18003bad0`
- `0x180098550`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800988b1`
- `bcrypt!BCryptFinishHash` at `0x1800988b1`
- `bcrypt!BCryptCreateHash` at `0x1800987da`
- `bcrypt!BCryptCreateHash` at `0x1800987da`
- `bcrypt!BCryptGetProperty` at `0x180098731`
- `bcrypt!BCryptGetProperty` at `0x180098731`
- `bcrypt!BCryptHashData` at `0x18009884b`
- `bcrypt!BCryptHashData` at `0x18009884b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800986f8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800986f8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180098688`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180098688`
- `bcrypt!BCryptDestroyHash` at `0x18009892d`
- `bcrypt!BCryptDestroyHash` at `0x18009892d`

## pseudocode

```c
__int64 __fastcall TpmAttiShaHash(
        wchar_t *String1,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR a6,
        ULONG cbOutput,
        _DWORD *a8)
{
  void **v12; // rdi
  ULONG v13; // esi
  NTSTATUS v14; // eax
  int v15; // ebx
  NTSTATUS Property; // eax
  ULONG v17; // esi
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v26[24]; // [rsp+58h] [rbp-18h] BYREF
  int v27; // [rsp+B0h] [rbp+40h] BYREF

  v27 = -2147467259;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v26, L"TpmAttiShaHash", &v27);
  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( cbSecret && pbSecret )
  {
    if ( !wcscmp_0(String1, L"SHA1") )
    {
      v12 = &g_hSHA1HmacAlg;
LABEL_9:
      v13 = 8;
      goto LABEL_16;
    }
    if ( !wcscmp_0(String1, L"SHA256") )
    {
      v12 = &g_hSHA256HmacAlg;
      goto LABEL_9;
    }
    if ( !wcscmp_0(String1, L"SHA384") )
    {
      v12 = &g_hSHA384HmacAlg;
      goto LABEL_9;
    }
LABEL_68:
    KspDebugProvider::TraceLoggingError("Unknown algorithm: %ls", String1);
    v15 = -2147024809;
    goto LABEL_69;
  }
  v13 = 0;
  if ( !wcscmp_0(String1, L"SHA1") )
  {
    v12 = &g_hSHA1HashAlg;
  }
  else if ( !wcscmp_0(String1, L"SHA256") )
  {
    v12 = &g_hSHA256HashAlg;
  }
  else
  {
    if ( wcscmp_0(String1, L"SHA384") )
      goto LABEL_68;
    v12 = &g_hSHA384HashAlg;
  }
LABEL_16:
  if ( !*v12 )
  {
    v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, String1, L"Microsoft Primitive Provider", v13);
    if ( v14 )
    {
      if ( (v14 & 0xFFFF000) == 0x290000 )
      {
        v15 = v14 & 0xFFF | 0x80280000;
      }
      else if ( (v14 & 0xFFF0000) == 0x70000 )
      {
        v15 = (unsigned __int16)v14;
        if ( (_WORD)v14 )
          v15 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v15 = v14 | 0x10000000;
      }
      v27 = v15;
      if ( v15 < 0 )
        goto LABEL_70;
    }
    else
    {
      v27 = 0;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v12, (signed __int64)phAlgorithm, 0) )
    {
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      phAlgorithm = 0;
    }
  }
  Property = BCryptGetProperty(*v12, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    if ( (Property & 0xFFFF000) == 0x290000 )
    {
      v15 = Property & 0xFFF | 0x80280000;
    }
    else if ( (Property & 0xFFF0000) == 0x70000 )
    {
      v15 = (unsigned __int16)Property;
      if ( (_WORD)Property )
        v15 = (unsigned __int16)Property | 0x80070000;
    }
    else
    {
      v15 = Property | 0x10000000;
    }
    v27 = v15;
    if ( v15 < 0 )
      goto LABEL_70;
  }
  else
  {
    v27 = 0;
  }
  if ( !a6 || (v17 = cbOutput) == 0 )
  {
LABEL_67:
    v15 = 0;
    *a8 = *(_DWORD *)pbOutput;
    goto LABEL_69;
  }
  if ( cbOutput < *(_DWORD *)pbOutput )
  {
    v15 = -2147024774;
    *a8 = *(_DWORD *)pbOutput;
LABEL_69:
    v27 = v15;
    goto LABEL_70;
  }
  v18 = BCryptCreateHash(*v12, &phHash, 0, 0, pbSecret, cbSecret, 0);
  if ( v18 )
  {
    if ( (v18 & 0xFFFF000) == 0x290000 )
    {
      v15 = v18 & 0xFFF | 0x80280000;
    }
    else if ( (v18 & 0xFFF0000) == 0x70000 )
    {
      v15 = (unsigned __int16)v18;
      if ( (_WORD)v18 )
        v15 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v15 = v18 | 0x10000000;
    }
    v27 = v15;
    if ( v15 < 0 )
      goto LABEL_70;
  }
  else
  {
    v27 = 0;
  }
  v19 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v19 )
  {
    if ( (v19 & 0xFFFF000) == 0x290000 )
    {
      v15 = v19 & 0xFFF | 0x80280000;
    }
    else if ( (v19 & 0xFFF0000) == 0x70000 )
    {
      v15 = (unsigned __int16)v19;
      if ( (_WORD)v19 )
        v15 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v15 = v19 | 0x10000000;
    }
    v27 = v15;
    if ( v15 < 0 )
      goto LABEL_70;
  }
  else
  {
    v27 = 0;
  }
  v20 = BCryptFinishHash(phHash, a6, v17, 0);
  if ( !v20 )
    goto LABEL_67;
  if ( (v20 & 0xFFFF000) == 0x290000 )
  {
    v15 = v20 & 0xFFF | 0x80280000;
  }
  else if ( (v20 & 0xFFF0000) == 0x70000 )
  {
    v15 = (unsigned __int16)v20;
    if ( (_WORD)v20 )
      v15 = (unsigned __int16)v20 | 0x80070000;
  }
  else
  {
    v15 = v20 | 0x10000000;
  }
  v27 = v15;
  if ( v15 >= 0 )
    goto LABEL_67;
LABEL_70:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    v15 = v27;
    phHash = 0;
  }
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v26);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180098550  mov     [rsp-28h+arg_0], rbx
0x180098555  mov     [rsp-28h+arg_8], rsi
0x18009855a  push    rbp
0x18009855b  push    rdi
0x18009855c  push    r12
0x18009855e  push    r13
0x180098560  push    r15
0x180098562  mov     rbp, rsp
0x180098565  sub     rsp, 70h
0x180098569  mov     r12d, r8d
0x18009856c  mov     [rbp+arg_10], 80004005h
0x180098573  mov     r15, rdx
0x180098576  lea     r8, [rbp+arg_10]; int *
0x18009857a  mov     rbx, rcx
0x18009857d  lea     rdx, aTpmattishahash; "TpmAttiShaHash"
0x180098584  lea     rcx, [rbp+var_18]; this
0x180098588  mov     r13, r9
0x18009858b  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180098590  mov     [rbp+phAlgorithm], 0
0x180098598  mov     [rbp+phHash], 0
0x1800985a0  mov     dword ptr [rbp+pbOutput], 0
0x1800985a7  mov     [rbp+var_2C], 0
0x1800985ae  test    r12d, r12d
0x1800985b1  jz      short loc_180098615
0x1800985b3  test    r15, r15
0x1800985b6  jz      short loc_180098615
0x1800985b8  lea     rdx, aSha1_0; "SHA1"
0x1800985bf  mov     rcx, rbx; String1
0x1800985c2  call    wcscmp_0
0x1800985c7  test    eax, eax
0x1800985c9  jnz     short loc_1800985D4
0x1800985cb  lea     rdi, ?g_hSHA1HmacAlg@@3PEAXEA; void * g_hSHA1HmacAlg
0x1800985d2  jmp     short loc_18009860E
0x1800985d4  lea     rdx, aSha256_0; "SHA256"
0x1800985db  mov     rcx, rbx; String1
0x1800985de  call    wcscmp_0
0x1800985e3  test    eax, eax
0x1800985e5  jnz     short loc_1800985F0
0x1800985e7  lea     rdi, ?g_hSHA256HmacAlg@@3PEAXEA; void * g_hSHA256HmacAlg
0x1800985ee  jmp     short loc_18009860E
0x1800985f0  lea     rdx, aSha384; "SHA384"
0x1800985f7  mov     rcx, rbx; String1
0x1800985fa  call    wcscmp_0
0x1800985ff  test    eax, eax
0x180098601  jnz     loc_18009890D
0x180098607  lea     rdi, ?g_hSHA384HmacAlg@@3PEAXEA; void * g_hSHA384HmacAlg
0x18009860e  mov     esi, 8
0x180098613  jmp     short loc_18009866D
0x180098615  lea     rdx, aSha1_0; "SHA1"
0x18009861c  mov     rcx, rbx; String1
0x18009861f  xor     esi, esi
0x180098621  call    wcscmp_0
0x180098626  test    eax, eax
0x180098628  jnz     short loc_180098633
0x18009862a  lea     rdi, ?g_hSHA1HashAlg@@3PEAXEA; void * g_hSHA1HashAlg
0x180098631  jmp     short loc_18009866D
0x180098633  lea     rdx, aSha256_0; "SHA256"
0x18009863a  mov     rcx, rbx; String1
0x18009863d  call    wcscmp_0
0x180098642  test    eax, eax
0x180098644  jnz     short loc_18009864F
0x180098646  lea     rdi, ?g_hSHA256HashAlg@@3PEAXEA; void * g_hSHA256HashAlg
0x18009864d  jmp     short loc_18009866D
0x18009864f  lea     rdx, aSha384; "SHA384"
0x180098656  mov     rcx, rbx; String1
0x180098659  call    wcscmp_0
0x18009865e  test    eax, eax
0x180098660  jnz     loc_18009890D
0x180098666  lea     rdi, ?g_hSHA384HashAlg@@3PEAXEA; void * g_hSHA384HashAlg
0x18009866d  cmp     qword ptr [rdi], 0
0x180098671  jnz     loc_18009870C
0x180098677  mov     r9d, esi; dwFlags
0x18009867a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180098681  mov     rdx, rbx; pszAlgId
0x180098684  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180098688  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009868f  nop     dword ptr [rax+rax+00h]
0x180098694  mov     ebx, eax
0x180098696  test    eax, eax
0x180098698  jnz     short loc_18009869F
0x18009869a  mov     [rbp+arg_10], eax
0x18009869d  jmp     short loc_1800986E5
0x18009869f  and     eax, 0FFFF000h
0x1800986a4  cmp     eax, 290000h
0x1800986a9  jnz     short loc_1800986B9
0x1800986ab  and     ebx, 0FFFh
0x1800986b1  or      ebx, 80280000h
0x1800986b7  jmp     short loc_1800986DA
0x1800986b9  mov     eax, ebx
0x1800986bb  and     eax, 0FFF0000h
0x1800986c0  cmp     eax, 70000h
0x1800986c5  jnz     short loc_1800986D6
0x1800986c7  movzx   ebx, bx
0x1800986ca  test    ebx, ebx
0x1800986cc  jz      short loc_1800986DA
0x1800986ce  or      ebx, 80070000h
0x1800986d4  jmp     short loc_1800986DA
0x1800986d6  bts     ebx, 1Ch
0x1800986da  mov     [rbp+arg_10], ebx
0x1800986dd  test    ebx, ebx
0x1800986df  js      loc_180098924
0x1800986e5  mov     rcx, [rbp+phAlgorithm]
0x1800986e9  xor     eax, eax
0x1800986eb  lock cmpxchg [rdi], rcx
0x1800986f0  jz      short loc_18009870C
0x1800986f2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800986f6  xor     edx, edx; dwFlags
0x1800986f8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800986ff  nop     dword ptr [rax+rax+00h]
0x180098704  mov     [rbp+phAlgorithm], 0
0x18009870c  mov     rcx, [rdi]; hObject
0x18009870f  lea     rax, [rbp+var_2C]
0x180098713  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18009871b  lea     r8, [rbp+pbOutput]; pbOutput
0x18009871f  mov     r9d, 4; cbOutput
0x180098725  mov     [rsp+70h+pcbResult], rax; pcbResult
0x18009872a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180098731  call    cs:__imp_BCryptGetProperty
0x180098738  nop     dword ptr [rax+rax+00h]
0x18009873d  mov     ebx, eax
0x18009873f  test    eax, eax
0x180098741  jnz     short loc_180098748
0x180098743  mov     [rbp+arg_10], eax
0x180098746  jmp     short loc_18009878E
0x180098748  and     eax, 0FFFF000h
0x18009874d  cmp     eax, 290000h
0x180098752  jnz     short loc_180098762
0x180098754  and     ebx, 0FFFh
0x18009875a  or      ebx, 80280000h
0x180098760  jmp     short loc_180098783
0x180098762  mov     eax, ebx
0x180098764  and     eax, 0FFF0000h
0x180098769  cmp     eax, 70000h
0x18009876e  jnz     short loc_18009877F
0x180098770  movzx   ebx, bx
0x180098773  test    ebx, ebx
0x180098775  jz      short loc_180098783
0x180098777  or      ebx, 80070000h
0x18009877d  jmp     short loc_180098783
0x18009877f  bts     ebx, 1Ch
0x180098783  mov     [rbp+arg_10], ebx
0x180098786  test    ebx, ebx
0x180098788  js      loc_180098924
0x18009878e  cmp     [rbp+arg_28], 0
0x180098793  jz      loc_180098900
0x180098799  mov     esi, [rbp+cbOutput]
0x18009879c  test    esi, esi
0x18009879e  jz      loc_180098900
0x1800987a4  mov     ecx, dword ptr [rbp+pbOutput]
0x1800987a7  cmp     esi, ecx
0x1800987a9  jnb     short loc_1800987BB
0x1800987ab  mov     rax, [rbp+arg_38]
0x1800987af  mov     ebx, 8007007Ah
0x1800987b4  mov     [rax], ecx
0x1800987b6  jmp     loc_180098921
0x1800987bb  mov     rcx, [rdi]; hAlgorithm
0x1800987be  lea     rdx, [rbp+phHash]; phHash
0x1800987c2  mov     [rsp+70h+var_40], 0; dwFlags
0x1800987ca  xor     r9d, r9d; cbHashObject
0x1800987cd  mov     [rsp+70h+dwFlags], r12d; cbSecret
0x1800987d2  xor     r8d, r8d; pbHashObject
0x1800987d5  mov     [rsp+70h+pcbResult], r15; pbSecret
0x1800987da  call    cs:__imp_BCryptCreateHash
0x1800987e1  nop     dword ptr [rax+rax+00h]
0x1800987e6  mov     edi, 0FFFF000h
0x1800987eb  mov     r15d, 290000h
0x1800987f1  mov     ebx, eax
0x1800987f3  test    eax, eax
0x1800987f5  jnz     short loc_1800987FC
0x1800987f7  mov     [rbp+arg_10], eax
0x1800987fa  jmp     short loc_18009883D
0x1800987fc  and     eax, edi
0x1800987fe  cmp     eax, r15d
0x180098801  jnz     short loc_180098811
0x180098803  and     ebx, 0FFFh
0x180098809  or      ebx, 80280000h
0x18009880f  jmp     short loc_180098832
0x180098811  mov     eax, ebx
0x180098813  and     eax, 0FFF0000h
0x180098818  cmp     eax, 70000h
0x18009881d  jnz     short loc_18009882E
0x18009881f  movzx   ebx, bx
0x180098822  test    ebx, ebx
0x180098824  jz      short loc_180098832
0x180098826  or      ebx, 80070000h
0x18009882c  jmp     short loc_180098832
0x18009882e  bts     ebx, 1Ch
0x180098832  mov     [rbp+arg_10], ebx
0x180098835  test    ebx, ebx
0x180098837  js      loc_180098924
0x18009883d  mov     r8d, [rbp+cbInput]; cbInput
0x180098841  xor     r9d, r9d; dwFlags
0x180098844  mov     rcx, [rbp+phHash]; hHash
0x180098848  mov     rdx, r13; pbInput
0x18009884b  call    cs:__imp_BCryptHashData
0x180098852  nop     dword ptr [rax+rax+00h]
0x180098857  mov     ebx, eax
0x180098859  test    eax, eax
0x18009885b  jnz     short loc_180098862
0x18009885d  mov     [rbp+arg_10], eax
0x180098860  jmp     short loc_1800988A3
0x180098862  and     eax, edi
0x180098864  cmp     eax, r15d
0x180098867  jnz     short loc_180098877
0x180098869  and     ebx, 0FFFh
0x18009886f  or      ebx, 80280000h
0x180098875  jmp     short loc_180098898
0x180098877  mov     eax, ebx
0x180098879  and     eax, 0FFF0000h
0x18009887e  cmp     eax, 70000h
0x180098883  jnz     short loc_180098894
0x180098885  movzx   ebx, bx
0x180098888  test    ebx, ebx
0x18009888a  jz      short loc_180098898
0x18009888c  or      ebx, 80070000h
0x180098892  jmp     short loc_180098898
0x180098894  bts     ebx, 1Ch
0x180098898  mov     [rbp+arg_10], ebx
0x18009889b  test    ebx, ebx
0x18009889d  js      loc_180098924
0x1800988a3  mov     rdx, [rbp+arg_28]; pbOutput
0x1800988a7  xor     r9d, r9d; dwFlags
0x1800988aa  mov     rcx, [rbp+phHash]; hHash
0x1800988ae  mov     r8d, esi; cbOutput
0x1800988b1  call    cs:__imp_BCryptFinishHash
0x1800988b8  nop     dword ptr [rax+rax+00h]
0x1800988bd  mov     ebx, eax
0x1800988bf  test    eax, eax
0x1800988c1  jz      short loc_180098900
0x1800988c3  and     eax, edi
0x1800988c5  cmp     eax, r15d
0x1800988c8  jnz     short loc_1800988D8
0x1800988ca  and     ebx, 0FFFh
0x1800988d0  or      ebx, 80280000h
0x1800988d6  jmp     short loc_1800988F9
0x1800988d8  mov     eax, ebx
0x1800988da  and     eax, 0FFF0000h
0x1800988df  cmp     eax, 70000h
0x1800988e4  jnz     short loc_1800988F5
0x1800988e6  movzx   ebx, bx
0x1800988e9  test    ebx, ebx
0x1800988eb  jz      short loc_1800988F9
0x1800988ed  or      ebx, 80070000h
0x1800988f3  jmp     short loc_1800988F9
0x1800988f5  bts     ebx, 1Ch
0x1800988f9  mov     [rbp+arg_10], ebx
0x1800988fc  test    ebx, ebx
0x1800988fe  js      short loc_180098924
0x180098900  mov     rcx, [rbp+arg_38]
0x180098904  xor     ebx, ebx
0x180098906  mov     eax, dword ptr [rbp+pbOutput]
0x180098909  mov     [rcx], eax
0x18009890b  jmp     short loc_180098921
0x18009890d  mov     rdx, rbx
0x180098910  lea     rcx, aUnknownAlgorit; "Unknown algorithm: %ls"
0x180098917  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x18009891c  mov     ebx, 80070057h
0x180098921  mov     [rbp+arg_10], ebx
0x180098924  mov     rcx, [rbp+phHash]; hHash
0x180098928  test    rcx, rcx
0x18009892b  jz      short loc_180098944
0x18009892d  call    cs:__imp_BCryptDestroyHash
0x180098934  nop     dword ptr [rax+rax+00h]
0x180098939  mov     ebx, [rbp+arg_10]
0x18009893c  mov     [rbp+phHash], 0
0x180098944  lea     rcx, [rbp+var_18]; this
0x180098948  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18009894d  lea     r11, [rsp+70h+var_s0]
0x180098952  mov     eax, ebx
0x180098954  mov     rbx, [r11+30h]
0x180098958  mov     rsi, [r11+38h]
0x18009895c  mov     rsp, r11
0x18009895f  pop     r15
0x180098961  pop     r13
0x180098963  pop     r12
0x180098965  pop     rdi
0x180098966  pop     rbp
0x180098967  retn
```
