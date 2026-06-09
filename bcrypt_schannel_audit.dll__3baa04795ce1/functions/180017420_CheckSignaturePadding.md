# CheckSignaturePadding

- ea: `0x180017420`
- end: `0x18001778d`
- name: `CheckSignaturePadding`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010680`

## callees

- `0x180004200`
- `0x180005060`
- `0x1800066f0`
- `0x180009430`
- `0x180012a70`
- `0x18001620c`
- `0x180016298`
- `0x1800171b4`
- `0x180017420`

## string_xrefs

- `0x180017478`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800174aa`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800175a7`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180017751`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckSignaturePadding(char a1, __int64 a2, __int64 a3, int a4, __int64 a5, int a6)
{
  BCRYPT_HANDLE v6; // rsi
  UCHAR *v7; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  NTSTATUS Property; // eax
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-10h] BYREF
  UCHAR v22[4]; // [rsp+44h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+80h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v22 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) != 0 )
    {
      if ( !a2 || !*(_QWORD *)a2 )
        goto LABEL_3;
      v13 = CachedOpenAlgorithmProvider(&hObject);
      v11 = v13;
      if ( v13 < 0 )
        goto LABEL_7;
      v6 = hObject;
      Property = BCryptGetProperty(hObject, L"ObjectLength", v22, 4u, &cbOutput, 0);
      v11 = Property;
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
        v11 = Property;
        if ( Property >= 0 )
        {
          Property = CheckPSSPadding(
                       v6,
                       *(unsigned int *)pbOutput,
                       *(unsigned int *)v22,
                       *(unsigned int *)(a2 + 8),
                       a3,
                       a4,
                       a5,
                       a6);
          v11 = Property;
          if ( Property >= 0 )
            goto LABEL_30;
        }
      }
      goto LABEL_9;
    }
LABEL_33:
    v15 = 3221225485LL;
    v11 = -1073741811;
    goto LABEL_34;
  }
  if ( !a2 )
  {
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_4:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    return v11;
  }
  if ( !*(_QWORD *)a2 )
  {
    v19 = VerifyPKCS1SigningFormat(0, 0);
    v11 = v19;
    if ( v19 < 0 )
    {
      v12 = (unsigned int)v19;
      goto LABEL_4;
    }
    goto LABEL_30;
  }
  v13 = CachedOpenAlgorithmProvider(&hObject);
  v11 = v13;
  if ( v13 < 0 )
  {
LABEL_7:
    DebugTraceError((unsigned int)v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    v6 = hObject;
    goto LABEL_35;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v11 = Property;
  if ( Property < 0 )
    goto LABEL_9;
  if ( *(_DWORD *)pbOutput != a4 )
    goto LABEL_33;
  Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
  v11 = Property;
  if ( Property >= 0 )
  {
    v7 = (UCHAR *)SafeAllocaAllocateFromHeap(cbOutput);
    if ( !v7 )
    {
      v11 = -1073741801;
      v15 = 3221225495LL;
      goto LABEL_34;
    }
    v16 = BCryptGetProperty(v6, L"HashOIDList", v7, cbOutput, &cbOutput, 0);
    v11 = v16;
    if ( v16 < 0 )
      goto LABEL_15;
    v18 = *(unsigned int *)v7;
    if ( !(_DWORD)v18 )
    {
      v11 = -1073741595;
      v17 = 3221225701LL;
      goto LABEL_16;
    }
    v16 = VerifyPKCS1SigningFormat(v18, *((_QWORD *)v7 + 1));
    v11 = v16;
    if ( v16 < 0 )
    {
LABEL_15:
      v17 = (unsigned int)v16;
LABEL_16:
      DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
LABEL_31:
      MSCryptFree(v7);
      goto LABEL_35;
    }
LABEL_30:
    v11 = 0;
    if ( !v7 )
      goto LABEL_35;
    goto LABEL_31;
  }
LABEL_9:
  v15 = (unsigned int)Property;
LABEL_34:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
LABEL_35:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v11;
}

```

## disassembly

```asm
0x180017420  mov     [rsp-28h+arg_8], rbx
0x180017425  mov     [rsp-28h+arg_10], rsi
0x18001742a  push    rbp
0x18001742b  push    rdi
0x18001742c  push    r12
0x18001742e  push    r14
0x180017430  push    r15
0x180017432  mov     rbp, rsp
0x180017435  sub     rsp, 50h
0x180017439  xor     esi, esi
0x18001743b  xor     edi, edi
0x18001743d  mov     [rbp+hObject], rsi
0x180017441  mov     r15d, r9d
0x180017444  mov     dword ptr [rbp+var_C], esi
0x180017447  mov     r12, r8
0x18001744a  mov     dword ptr [rbp+pbOutput], esi
0x18001744d  mov     r14, rdx
0x180017450  mov     [rbp+cbOutput], esi
0x180017453  test    cl, 2
0x180017456  jz      loc_18001763D
0x18001745c  test    rdx, rdx
0x18001745f  jnz     short loc_180017489
0x180017461  mov     r9d, 60Dh
0x180017467  mov     ebx, 0C000000Dh
0x18001746c  mov     ecx, 0C000000Dh
0x180017471  lea     rdx, aStatus; "Status"
0x180017478  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001747f  call    DebugTraceError
0x180017484  jmp     loc_180017771
0x180017489  mov     rdx, [rdx]
0x18001748c  test    rdx, rdx
0x18001748f  jz      loc_180017609
0x180017495  lea     rcx, [rbp+hObject]
0x180017499  call    CachedOpenAlgorithmProvider
0x18001749e  mov     ebx, eax
0x1800174a0  test    eax, eax
0x1800174a2  jns     short loc_1800174C8
0x1800174a4  mov     r9d, 61Ah
0x1800174aa  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800174b1  mov     ecx, eax
0x1800174b3  lea     rdx, aStatus; "Status"
0x1800174ba  call    DebugTraceError
0x1800174bf  mov     rsi, [rbp+hObject]
0x1800174c3  jmp     loc_180017764
0x1800174c8  mov     [rsp+50h+dwFlags], esi; dwFlags
0x1800174cc  lea     rax, [rbp+cbOutput]
0x1800174d0  mov     rsi, [rbp+hObject]
0x1800174d4  lea     r8, [rbp+pbOutput]; pbOutput
0x1800174d8  mov     rcx, rsi; hObject
0x1800174db  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800174e0  mov     r9d, 4; cbOutput
0x1800174e6  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800174ed  call    BCryptGetProperty
0x1800174f2  mov     ebx, eax
0x1800174f4  test    eax, eax
0x1800174f6  jns     short loc_180017505
0x1800174f8  mov     r9d, 626h
0x1800174fe  mov     ecx, eax
0x180017500  jmp     loc_180017751
0x180017505  cmp     dword ptr [rbp+pbOutput], r15d
0x180017509  jz      short loc_180017516
0x18001750b  mov     r9d, 62Ch
0x180017511  jmp     loc_180017747
0x180017516  lea     rax, [rbp+cbOutput]
0x18001751a  mov     [rsp+50h+dwFlags], edi; dwFlags
0x18001751e  xor     r9d, r9d; cbOutput
0x180017521  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180017526  xor     r8d, r8d; pbOutput
0x180017529  lea     rdx, aHashoidlist; "HashOIDList"
0x180017530  mov     rcx, rsi; hObject
0x180017533  call    BCryptGetProperty
0x180017538  mov     ebx, eax
0x18001753a  test    eax, eax
0x18001753c  jns     short loc_180017546
0x18001753e  mov     r9d, 638h
0x180017544  jmp     short loc_1800174FE
0x180017546  mov     ecx, [rbp+cbOutput]
0x180017549  call    SafeAllocaAllocateFromHeap
0x18001754e  mov     rdi, rax
0x180017551  test    rax, rax
0x180017554  jnz     short loc_18001756B
0x180017556  mov     ebx, 0C0000017h
0x18001755b  mov     r9d, 642h
0x180017561  mov     ecx, 0C0000017h
0x180017566  jmp     loc_180017751
0x18001756b  mov     r9d, [rbp+cbOutput]; cbOutput
0x18001756f  lea     rax, [rbp+cbOutput]
0x180017573  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18001757b  lea     rdx, aHashoidlist; "HashOIDList"
0x180017582  mov     r8, rdi; pbOutput
0x180017585  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001758a  mov     rcx, rsi; hObject
0x18001758d  call    BCryptGetProperty
0x180017592  mov     ebx, eax
0x180017594  test    eax, eax
0x180017596  jns     short loc_1800175B8
0x180017598  mov     r9d, 64Eh
0x18001759e  mov     ecx, eax
0x1800175a0  lea     rdx, aStatus; "Status"
0x1800175a7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800175ae  call    DebugTraceError
0x1800175b3  jmp     loc_18001772C
0x1800175b8  mov     ecx, [rdi]
0x1800175ba  test    ecx, ecx
0x1800175bc  jnz     short loc_1800175D0
0x1800175be  mov     ebx, 0C00000E5h
0x1800175c3  mov     r9d, 657h
0x1800175c9  mov     ecx, 0C00000E5h
0x1800175ce  jmp     short loc_1800175A0
0x1800175d0  mov     eax, [rbp+arg_28]
0x1800175d3  mov     r9d, r15d
0x1800175d6  mov     rdx, [rdi+8]
0x1800175da  mov     r8, r12
0x1800175dd  mov     dword ptr [rsp+50h+var_20], 1
0x1800175e5  mov     [rsp+50h+dwFlags], eax
0x1800175e9  mov     rax, [rbp+arg_20]
0x1800175ed  mov     [rsp+50h+pcbResult], rax
0x1800175f2  call    VerifyPKCS1SigningFormat
0x1800175f7  mov     ebx, eax
0x1800175f9  test    eax, eax
0x1800175fb  jns     loc_180017725
0x180017601  mov     r9d, 665h
0x180017607  jmp     short loc_18001759E
0x180017609  mov     eax, [rbp+arg_28]
0x18001760c  xor     edx, edx
0x18001760e  mov     dword ptr [rsp+50h+var_20], esi
0x180017612  xor     ecx, ecx
0x180017614  mov     [rsp+50h+dwFlags], eax
0x180017618  mov     rax, [rbp+arg_20]
0x18001761c  mov     [rsp+50h+pcbResult], rax
0x180017621  call    VerifyPKCS1SigningFormat
0x180017626  mov     ebx, eax
0x180017628  test    eax, eax
0x18001762a  jns     loc_180017725
0x180017630  mov     r9d, 675h
0x180017636  mov     ecx, eax
0x180017638  jmp     loc_180017471
0x18001763d  test    cl, 8
0x180017640  jz      loc_180017741
0x180017646  test    r14, r14
0x180017649  jz      loc_180017736
0x18001764f  mov     rdx, [rdx]
0x180017652  test    rdx, rdx
0x180017655  jz      loc_180017736
0x18001765b  lea     rcx, [rbp+hObject]
0x18001765f  call    CachedOpenAlgorithmProvider
0x180017664  mov     ebx, eax
0x180017666  test    eax, eax
0x180017668  jns     short loc_180017675
0x18001766a  mov     r9d, 68Ch
0x180017670  jmp     loc_1800174AA
0x180017675  mov     [rsp+50h+dwFlags], esi; dwFlags
0x180017679  lea     rax, [rbp+cbOutput]
0x18001767d  mov     rsi, [rbp+hObject]
0x180017681  lea     r8, [rbp+var_C]; pbOutput
0x180017685  mov     rcx, rsi; hObject
0x180017688  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001768d  mov     r9d, 4; cbOutput
0x180017693  lea     rdx, aObjectlength; "ObjectLength"
0x18001769a  call    BCryptGetProperty
0x18001769f  mov     ebx, eax
0x1800176a1  test    eax, eax
0x1800176a3  jns     short loc_1800176B0
0x1800176a5  mov     r9d, 698h
0x1800176ab  jmp     loc_1800174FE
0x1800176b0  lea     rax, [rbp+cbOutput]
0x1800176b4  mov     [rsp+50h+dwFlags], edi; dwFlags
0x1800176b8  mov     r9d, 4; cbOutput
0x1800176be  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800176c3  lea     r8, [rbp+pbOutput]; pbOutput
0x1800176c7  mov     rcx, rsi; hObject
0x1800176ca  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800176d1  call    BCryptGetProperty
0x1800176d6  mov     ebx, eax
0x1800176d8  test    eax, eax
0x1800176da  jns     short loc_1800176E7
0x1800176dc  mov     r9d, 6A4h
0x1800176e2  jmp     loc_1800174FE
0x1800176e7  mov     eax, [rbp+arg_28]
0x1800176ea  mov     rcx, rsi
0x1800176ed  mov     r9d, [r14+8]
0x1800176f1  mov     r8d, dword ptr [rbp+var_C]
0x1800176f5  mov     edx, dword ptr [rbp+pbOutput]
0x1800176f8  mov     [rsp+50h+var_18], eax
0x1800176fc  mov     rax, [rbp+arg_20]
0x180017700  mov     [rsp+50h+var_20], rax
0x180017705  mov     [rsp+50h+dwFlags], r15d
0x18001770a  mov     [rsp+50h+pcbResult], r12
0x18001770f  call    CheckPSSPadding
0x180017714  mov     ebx, eax
0x180017716  test    eax, eax
0x180017718  jns     short loc_180017725
0x18001771a  mov     r9d, 6B2h
0x180017720  jmp     loc_1800174FE
0x180017725  xor     ebx, ebx
0x180017727  test    rdi, rdi
0x18001772a  jz      short loc_180017764
0x18001772c  mov     rcx, rdi
0x18001772f  call    MSCryptFree
0x180017734  jmp     short loc_180017764
0x180017736  mov     r9d, 681h
0x18001773c  jmp     loc_180017467
0x180017741  mov     r9d, 6B9h
0x180017747  mov     ecx, 0C000000Dh
0x18001774c  mov     ebx, 0C000000Dh
0x180017751  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017758  lea     rdx, aStatus; "Status"
0x18001775f  call    DebugTraceError
0x180017764  test    rsi, rsi
0x180017767  jz      short loc_180017771
0x180017769  mov     rcx, rsi; hAlgorithm
0x18001776c  call    CachedCloseAlgorithmProvider
0x180017771  lea     r11, [rsp+50h+var_s0]
0x180017776  mov     eax, ebx
0x180017778  mov     rbx, [r11+38h]
0x18001777c  mov     rsi, [r11+40h]
0x180017780  mov     rsp, r11
0x180017783  pop     r15
0x180017785  pop     r14
0x180017787  pop     r12
0x180017789  pop     rdi
0x18001778a  pop     rbp
0x18001778b  retn
```
