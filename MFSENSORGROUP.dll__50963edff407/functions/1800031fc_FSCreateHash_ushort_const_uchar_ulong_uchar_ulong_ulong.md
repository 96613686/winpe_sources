# FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800031fc`
- end: `0x18000345c`
- name: `?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800019d0`
- `0x180002474`
- `0x18003aab0`
- `0x180073240`

## callees

- `0x1800031fc`
- `0x180005fa0`
- `0x180031920`
- `0x18003491c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003263`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003263`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000338e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000338e`
- `bcrypt!BCryptFinishHash` at `0x18000335a`
- `bcrypt!BCryptFinishHash` at `0x18000335a`
- `bcrypt!BCryptHashData` at `0x180003336`
- `bcrypt!BCryptHashData` at `0x180003336`
- `bcrypt!BCryptGetProperty` at `0x1800032a9`
- `bcrypt!BCryptGetProperty` at `0x1800032a9`
- `bcrypt!BCryptCreateHash` at `0x18000330f`
- `bcrypt!BCryptCreateHash` at `0x18000330f`
- `bcrypt!BCryptDestroyHash` at `0x18000337d`
- `bcrypt!BCryptDestroyHash` at `0x180003413`
- `bcrypt!BCryptDestroyHash` at `0x18000337d`
- `bcrypt!BCryptDestroyHash` at `0x180003413`

## pseudocode

```c
__int64 __fastcall FSCreateHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbOutput,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int *v6; // rdi
  BCRYPT_ALG_HANDLE v8; // rcx
  const WCHAR *v12; // rdx
  int v13; // ebx
  NTSTATUS v14; // ecx
  NTSTATUS Property; // ecx
  unsigned int v16; // eax
  BCRYPT_HASH_HANDLE v17; // rbx
  NTSTATUS v18; // ecx
  NTSTATUS v19; // ecx
  NTSTATUS v20; // ecx
  __int64 v22; // rdx
  UCHAR pbOutputa[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-1Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF

  v6 = a6;
  v8 = 0;
  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutputa = 0;
  pcbResult = 0;
  if ( !a6 )
  {
    v13 = -2147467261;
    goto LABEL_27;
  }
  *a6 = 0;
  if ( !pbInput || !cbInput )
  {
    v13 = -2147024809;
    goto LABEL_27;
  }
  v12 = L"SHA256";
  if ( pszAlgId )
    v12 = pszAlgId;
  v13 = 0;
  v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, v12, 0, 0);
  if ( v14 < 0 )
    v13 = v14 | 0x10000000;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v22 = 10;
LABEL_45:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v13);
    }
  }
  else
  {
    v13 = 0;
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutputa, 4u, &pcbResult, 0);
    if ( Property < 0 )
      v13 = Property | 0x10000000;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 11;
        goto LABEL_45;
      }
    }
    else
    {
      v16 = *(_DWORD *)pbOutputa;
      *v6 = *(_DWORD *)pbOutputa;
      if ( a5 < v16 )
      {
        if ( pbOutput || a5 )
          v13 = -1072860816;
        goto LABEL_24;
      }
      v17 = phHash;
      if ( phHash )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a6);
        BCryptDestroyHash(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a6);
      }
      phHash = 0;
      v13 = 0;
      v18 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
      if ( v18 < 0 )
        v13 = v18 | 0x10000000;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v22 = 12;
          goto LABEL_45;
        }
      }
      else
      {
        v13 = 0;
        v19 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v19 < 0 )
          v13 = v19 | 0x10000000;
        if ( v13 >= 0 )
        {
          v13 = 0;
          v20 = BCryptFinishHash(phHash, pbOutput, *(ULONG *)pbOutputa, 0);
          if ( v20 < 0 )
            v13 = v20 | 0x10000000;
          if ( v13 >= 0 || !g_wppLevels )
            goto LABEL_24;
          v22 = 14;
          goto LABEL_45;
        }
        if ( g_wppLevels )
        {
          v22 = 13;
          goto LABEL_45;
        }
      }
    }
  }
LABEL_24:
  if ( phHash )
    BCryptDestroyHash(phHash);
  v8 = phAlgorithm;
LABEL_27:
  if ( v8 )
    BCryptCloseAlgorithmProvider(v8, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800031fc  push    rbp
0x1800031fe  push    rbx
0x1800031ff  push    rsi
0x180003200  push    rdi
0x180003201  push    r13
0x180003203  push    r14
0x180003205  push    r15
0x180003207  mov     rbp, rsp
0x18000320a  sub     rsp, 60h
0x18000320e  mov     rdi, [rbp+arg_28]
0x180003212  mov     rax, rcx
0x180003215  xor     ecx, ecx
0x180003217  mov     rsi, r9
0x18000321a  mov     [rbp+phAlgorithm], rcx
0x18000321e  mov     r14d, r8d
0x180003221  mov     [rbp+phHash], rcx
0x180003225  mov     r15, rdx
0x180003228  mov     dword ptr [rbp+pbOutput], ecx
0x18000322b  mov     [rbp+var_1C], ecx
0x18000322e  test    rdi, rdi
0x180003231  jz      loc_1800033A5
0x180003237  mov     [rdi], ecx
0x180003239  test    rdx, rdx
0x18000323c  jz      loc_1800033DC
0x180003242  test    r8d, r8d
0x180003245  jz      loc_1800033DC
0x18000324b  test    rax, rax
0x18000324e  lea     rdx, pszAlgId; "SHA256"
0x180003255  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180003259  cmovnz  rdx, rax; pszAlgId
0x18000325d  xor     r9d, r9d; dwFlags
0x180003260  xor     r8d, r8d; pszImplementation
0x180003263  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180003269  xor     ebx, ebx
0x18000326b  mov     r13d, 10000000h
0x180003271  mov     ecx, eax
0x180003273  or      eax, r13d
0x180003276  test    ecx, ecx
0x180003278  cmovs   ebx, eax
0x18000327b  test    ebx, ebx
0x18000327d  js      loc_1800033AC
0x180003283  mov     rcx, [rbp+phAlgorithm]; hObject
0x180003287  lea     rax, [rbp+var_1C]
0x18000328b  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180003293  lea     r8, [rbp+pbOutput]; pbOutput
0x180003297  mov     r9d, 4; cbOutput
0x18000329d  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800032a2  lea     rdx, pszProperty; "HashDigestLength"
0x1800032a9  call    cs:__imp_BCryptGetProperty
0x1800032af  xor     ebx, ebx
0x1800032b1  mov     ecx, eax
0x1800032b3  or      eax, r13d
0x1800032b6  test    ecx, ecx
0x1800032b8  cmovs   ebx, eax
0x1800032bb  test    ebx, ebx
0x1800032bd  js      loc_1800033E3
0x1800032c3  mov     eax, dword ptr [rbp+pbOutput]
0x1800032c6  mov     ecx, [rbp+arg_20]
0x1800032c9  mov     [rdi], eax
0x1800032cb  cmp     ecx, eax
0x1800032cd  jb      loc_1800033CC
0x1800032d3  mov     rbx, [rbp+phHash]
0x1800032d7  test    rbx, rbx
0x1800032da  jnz     loc_180003407
0x1800032e0  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800032e4  lea     rdx, [rbp+phHash]; phHash
0x1800032e8  mov     [rsp+60h+var_30], 0; dwFlags
0x1800032f0  xor     r9d, r9d; cbHashObject
0x1800032f3  mov     [rsp+60h+dwFlags], 0; cbSecret
0x1800032fb  xor     r8d, r8d; pbHashObject
0x1800032fe  mov     [rsp+60h+pcbResult], 0; pbSecret
0x180003307  mov     [rbp+phHash], 0
0x18000330f  call    cs:__imp_BCryptCreateHash
0x180003315  xor     ebx, ebx
0x180003317  mov     ecx, eax
0x180003319  or      eax, r13d
0x18000331c  test    ecx, ecx
0x18000331e  cmovs   ebx, eax
0x180003321  test    ebx, ebx
0x180003323  js      loc_1800033F3
0x180003329  mov     rcx, [rbp+phHash]; hHash
0x18000332d  xor     r9d, r9d; dwFlags
0x180003330  mov     r8d, r14d; cbInput
0x180003333  mov     rdx, r15; pbInput
0x180003336  call    cs:__imp_BCryptHashData
0x18000333c  xor     ebx, ebx
0x18000333e  mov     ecx, eax
0x180003340  or      eax, r13d
0x180003343  test    ecx, ecx
0x180003345  cmovs   ebx, eax
0x180003348  test    ebx, ebx
0x18000334a  js      short loc_1800033BC
0x18000334c  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x180003350  xor     r9d, r9d; dwFlags
0x180003353  mov     rcx, [rbp+phHash]; hHash
0x180003357  mov     rdx, rsi; pbOutput
0x18000335a  call    cs:__imp_BCryptFinishHash
0x180003360  xor     ebx, ebx
0x180003362  mov     ecx, eax
0x180003364  or      eax, r13d
0x180003367  test    ecx, ecx
0x180003369  cmovs   ebx, eax
0x18000336c  test    ebx, ebx
0x18000336e  js      loc_180003427
0x180003374  mov     rcx, [rbp+phHash]; hHash
0x180003378  test    rcx, rcx
0x18000337b  jz      short loc_180003383
0x18000337d  call    cs:__imp_BCryptDestroyHash
0x180003383  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180003387  test    rcx, rcx
0x18000338a  jz      short loc_180003394
0x18000338c  xor     edx, edx; dwFlags
0x18000338e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180003394  mov     eax, ebx
0x180003396  add     rsp, 60h
0x18000339a  pop     r15
0x18000339c  pop     r14
0x18000339e  pop     r13
0x1800033a0  pop     rdi
0x1800033a1  pop     rsi
0x1800033a2  pop     rbx
0x1800033a3  pop     rbp
0x1800033a4  retn
0x1800033a5  mov     ebx, 80004003h
0x1800033aa  jmp     short loc_180003387
0x1800033ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800033b3  jb      short loc_180003374
0x1800033b5  mov     edx, 0Ah
0x1800033ba  jmp     short loc_180003439
0x1800033bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800033c3  jb      short loc_180003374
0x1800033c5  mov     edx, 0Dh
0x1800033ca  jmp     short loc_180003439
0x1800033cc  test    rsi, rsi
0x1800033cf  jnz     short loc_1800033D5
0x1800033d1  test    ecx, ecx
0x1800033d3  jz      short loc_180003374
0x1800033d5  mov     ebx, 0C00D7170h
0x1800033da  jmp     short loc_180003374
0x1800033dc  mov     ebx, 80070057h
0x1800033e1  jmp     short loc_180003387
0x1800033e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800033ea  jb      short loc_180003374
0x1800033ec  mov     edx, 0Bh
0x1800033f1  jmp     short loc_180003439
0x1800033f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800033fa  jb      loc_180003374
0x180003400  mov     edx, 0Ch
0x180003405  jmp     short loc_180003439
0x180003407  lea     rcx, [rbp+arg_28]; this
0x18000340b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180003410  mov     rcx, rbx; hHash
0x180003413  call    cs:__imp_BCryptDestroyHash
0x180003419  lea     rcx, [rbp+arg_28]; this
0x18000341d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180003422  jmp     loc_1800032E0
0x180003427  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000342e  jb      loc_180003374
0x180003434  mov     edx, 0Eh
0x180003439  mov     rcx, cs:WPP_GLOBAL_Control
0x180003440  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180003447  xor     r9d, r9d
0x18000344a  mov     dword ptr [rsp+60h+pcbResult], ebx
0x18000344e  mov     rcx, [rcx+10h]
0x180003452  call    WPP_SF_qD
0x180003457  jmp     loc_180003374
```
