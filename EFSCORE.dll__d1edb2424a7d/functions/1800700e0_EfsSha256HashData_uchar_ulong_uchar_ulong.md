# EfsSha256HashData(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800700e0`
- end: `0x18007040a`
- name: `?EfsSha256HashData@@YAKPEAEKPEAPEAEPEAK@Z`
- size: `810`
- prototype: `unsigned int(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033c5c`
- `0x18007fb90`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x180063698`
- `0x1800700e0`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007038d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007038d`
- `bcrypt!BCryptGetProperty` at `0x1800701a2`
- `bcrypt!BCryptGetProperty` at `0x1800701dd`
- `bcrypt!BCryptGetProperty` at `0x1800701a2`
- `bcrypt!BCryptGetProperty` at `0x1800701dd`
- `bcrypt!BCryptDestroyHash` at `0x18007037c`
- `bcrypt!BCryptDestroyHash` at `0x18007037c`
- `bcrypt!BCryptFinishHash` at `0x180070345`
- `bcrypt!BCryptFinishHash` at `0x180070345`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070141`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070141`
- `bcrypt!BCryptHashData` at `0x180070318`
- `bcrypt!BCryptHashData` at `0x180070318`
- `bcrypt!BCryptCreateHash` at `0x1800702eb`
- `bcrypt!BCryptCreateHash` at `0x1800702eb`
- `ntdll!RtlNtStatusToDosError` at `0x18007014d`
- `ntdll!RtlNtStatusToDosError` at `0x1800701ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800701e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800702f7`
- `ntdll!RtlNtStatusToDosError` at `0x180070324`
- `ntdll!RtlNtStatusToDosError` at `0x180070351`
- `ntdll!RtlNtStatusToDosError` at `0x18007014d`
- `ntdll!RtlNtStatusToDosError` at `0x1800701ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800701e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800702f7`
- `ntdll!RtlNtStatusToDosError` at `0x180070324`
- `ntdll!RtlNtStatusToDosError` at `0x180070351`

## pseudocode

```c
__int64 __fastcall EfsSha256HashData(unsigned __int8 *a1, ULONG a2, unsigned __int8 **a3, unsigned int *a4)
{
  UCHAR *v7; // rbx
  UCHAR *v8; // r14
  int v9; // eax
  ULONG v10; // eax
  unsigned int v11; // edi
  __int64 *v12; // rdx
  ULONG v13; // r8d
  int Property; // eax
  int v15; // eax
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  UCHAR *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  UCHAR *v27; // rcx
  __int64 v28; // rax
  UCHAR *v29; // rcx
  __int64 v31; // [rsp+0h] [rbp-40h] BYREF
  ULONG *pcbResult; // [rsp+20h] [rbp-20h]
  UCHAR v33[4]; // [rsp+40h] [rbp+0h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp+4h] BYREF
  ULONG v35; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp+10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp+18h] BYREF
  PUCHAR pbInput; // [rsp+60h] [rbp+20h]

  pbInput = a1;
  *(_DWORD *)v33 = 0;
  *(_DWORD *)pbOutput = 0;
  v35 = 0;
  phAlgorithm = 0;
  phHash = 0;
  v7 = 0;
  v8 = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( v9 < 0 )
  {
    v10 = RtlNtStatusToDosError(v9);
    LODWORD(pcbResult) = 853;
LABEL_3:
    v11 = v10;
    v12 = (__int64 *)&EFS_API_ERROR;
    v13 = v10;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (_DWORD)v12, v13, 24, (char)pcbResult);
    goto LABEL_32;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v35, 0);
  if ( Property < 0 )
  {
    v10 = RtlNtStatusToDosError(Property);
    LODWORD(pcbResult) = 864;
    goto LABEL_3;
  }
  v15 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v33, 4u, &v35, 0);
  if ( v15 < 0 )
  {
    v10 = RtlNtStatusToDosError(v15);
    LODWORD(pcbResult) = 875;
    goto LABEL_3;
  }
  v16 = *(unsigned int *)pbOutput;
  v11 = 8;
  if ( !*(_DWORD *)pbOutput
    || *(unsigned int *)pbOutput > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)*(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8 < *(unsigned int *)pbOutput
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_48;
  }
  v17 = v16 + 23;
  if ( v16 + 23 <= v16 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  v7 = v33;
  if ( &v31 == (__int64 *)-64LL || (*(_DWORD *)v33 = 1801679955, (v7 = (UCHAR *)&v35) == 0) )
  {
LABEL_48:
    if ( v16 + 8 >= v16 )
    {
      v21 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v7 = v21;
      if ( v21 )
      {
        *(_DWORD *)v21 = 1885431112;
        v7 = v21 + 8;
      }
    }
  }
  if ( !v7 )
  {
    v13 = *(_DWORD *)pbOutput;
    LODWORD(pcbResult) = 880;
LABEL_22:
    v12 = EFS_ERROR_MEMORY;
    goto LABEL_4;
  }
  v8 = (UCHAR *)wil::details::heap_allocator::allocate(*(unsigned int *)v33);
  if ( !v8 )
  {
    v13 = *(_DWORD *)v33;
    LODWORD(pcbResult) = 886;
    goto LABEL_22;
  }
  v22 = BCryptCreateHash(phAlgorithm, &phHash, v7, *(ULONG *)pbOutput, 0, 0, 0);
  if ( v22 < 0 )
  {
    v10 = RtlNtStatusToDosError(v22);
    LODWORD(pcbResult) = 899;
    goto LABEL_3;
  }
  v23 = BCryptHashData(phHash, pbInput, a2, 0);
  if ( v23 < 0 )
  {
    v10 = RtlNtStatusToDosError(v23);
    LODWORD(pcbResult) = 908;
    goto LABEL_3;
  }
  v24 = BCryptFinishHash(phHash, v8, *(ULONG *)v33, 0);
  if ( v24 < 0 )
  {
    v10 = RtlNtStatusToDosError(v24);
    LODWORD(pcbResult) = 917;
    goto LABEL_3;
  }
  v25 = *(_DWORD *)v33;
  v11 = 0;
  *a3 = v8;
  v8 = 0;
  *a4 = v25;
LABEL_32:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v7 )
  {
    v26 = *(unsigned int *)pbOutput;
    v27 = v7;
    if ( *(_DWORD *)pbOutput )
    {
      do
      {
        *v27++ = 0;
        --v26;
      }
      while ( v26 );
    }
    if ( *((_DWORD *)v7 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( v8 )
  {
    v28 = *(unsigned int *)v33;
    v29 = v8;
    if ( *(_DWORD *)v33 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    EfsFreeHeap(v8);
  }
  return v11;
}

```

## disassembly

```asm
0x1800700e0  push    rbp
0x1800700e2  push    rbx
0x1800700e3  push    rsi
0x1800700e4  push    rdi
0x1800700e5  push    r12
0x1800700e7  push    r13
0x1800700e9  push    r14
0x1800700eb  push    r15
0x1800700ed  sub     rsp, 88h
0x1800700f4  lea     rbp, [rsp+40h]
0x1800700f9  mov     rax, cs:__security_cookie
0x180070100  xor     rax, rbp
0x180070103  mov     [rbp+80h+var_50], rax
0x180070107  xor     esi, esi
0x180070109  mov     [rbp+80h+pbInput], rcx
0x18007010d  mov     r15, r9
0x180070110  mov     dword ptr [rbp+80h+var_80], esi
0x180070113  mov     r12, r8
0x180070116  mov     dword ptr [rbp+80h+pbOutput], esi
0x180070119  mov     r13d, edx
0x18007011c  mov     [rbp+80h+var_78], esi
0x18007011f  xor     r9d, r9d; dwFlags
0x180070122  mov     [rbp+80h+phAlgorithm], rsi
0x180070126  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18007012d  mov     [rbp+80h+phHash], rsi
0x180070131  lea     rdx, aSha256; "SHA256"
0x180070138  mov     ebx, esi
0x18007013a  lea     rcx, [rbp+80h+phAlgorithm]; phAlgorithm
0x18007013e  mov     r14d, esi
0x180070141  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180070147  test    eax, eax
0x180070149  jns     short loc_18007017E
0x18007014b  mov     ecx, eax; Status
0x18007014d  call    cs:__imp_RtlNtStatusToDosError
0x180070153  mov     dword ptr [rsp+0C0h+pcbResult], 355h
0x18007015b  mov     edi, eax
0x18007015d  lea     rdx, EFS_API_ERROR
0x180070164  mov     r8d, eax
0x180070167  mov     rcx, cs:g_hPublisher
0x18007016e  mov     r9d, 18h
0x180070174  call    fnEfsLogTrace1
0x180070179  jmp     loc_180070373
0x18007017e  mov     rcx, [rbp+80h+phAlgorithm]; hObject
0x180070182  lea     rax, [rbp+80h+var_78]
0x180070186  mov     edi, 4
0x18007018b  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18007018f  mov     r9d, edi; cbOutput
0x180070192  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180070197  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x18007019b  lea     rdx, aObjectlength; "ObjectLength"
0x1800701a2  call    cs:__imp_BCryptGetProperty
0x1800701a8  test    eax, eax
0x1800701aa  jns     short loc_1800701BE
0x1800701ac  mov     ecx, eax; Status
0x1800701ae  call    cs:__imp_RtlNtStatusToDosError
0x1800701b4  mov     dword ptr [rsp+0C0h+pcbResult], 360h
0x1800701bc  jmp     short loc_18007015B
0x1800701be  mov     rcx, [rbp+80h+phAlgorithm]; hObject
0x1800701c2  lea     rax, [rbp+80h+var_78]
0x1800701c6  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x1800701ca  lea     r8, [rbp+80h+var_80]; pbOutput
0x1800701ce  mov     r9d, edi; cbOutput
0x1800701d1  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x1800701d6  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800701dd  call    cs:__imp_BCryptGetProperty
0x1800701e3  test    eax, eax
0x1800701e5  jns     short loc_1800701FC
0x1800701e7  mov     ecx, eax; Status
0x1800701e9  call    cs:__imp_RtlNtStatusToDosError
0x1800701ef  mov     dword ptr [rsp+0C0h+pcbResult], 36Bh
0x1800701f7  jmp     loc_18007015B
0x1800701fc  mov     esi, dword ptr [rbp+80h+pbOutput]
0x1800701ff  mov     edi, 8
0x180070204  test    rsi, rsi
0x180070207  jz      short loc_180070268
0x180070209  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180070210  ja      short loc_180070268
0x180070212  mov     rcx, cs:g_ulAdditionalProbeSize
0x180070219  add     rcx, rdi
0x18007021c  add     rcx, rsi
0x18007021f  cmp     rcx, rsi
0x180070222  jb      short loc_180070268
0x180070224  call    VerifyStackAvailable
0x180070229  test    eax, eax
0x18007022b  jz      short loc_180070268
0x18007022d  lea     rax, [rsi+8]
0x180070231  lea     rcx, [rax+0Fh]
0x180070235  cmp     rcx, rax
0x180070238  ja      short loc_180070244
0x18007023a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180070244  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180070248  mov     rax, rcx
0x18007024b  call    _alloca_probe
0x180070250  sub     rsp, rcx
0x180070253  lea     rbx, [rsp+0C0h+var_80]
0x180070258  test    rbx, rbx
0x18007025b  jz      short loc_180070268
0x18007025d  mov     dword ptr [rbx], 6B637453h
0x180070263  add     rbx, rdi
0x180070266  jnz     short loc_180070292
0x180070268  lea     rcx, [rsi+8]
0x18007026c  cmp     rcx, rsi
0x18007026f  jb      short loc_180070292
0x180070271  mov     rax, cs:g_pfnAllocate
0x180070278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007027d  xor     esi, esi
0x18007027f  mov     rbx, rax
0x180070282  test    rax, rax
0x180070285  jz      short loc_180070294
0x180070287  mov     dword ptr [rax], 70616548h
0x18007028d  add     rbx, rdi
0x180070290  jmp     short loc_180070294
0x180070292  xor     esi, esi
0x180070294  test    rbx, rbx
0x180070297  jnz     short loc_1800702B1
0x180070299  mov     r8d, dword ptr [rbp+80h+pbOutput]
0x18007029d  mov     dword ptr [rsp+0C0h+pcbResult], 370h
0x1800702a5  lea     rdx, EFS_ERROR_MEMORY
0x1800702ac  jmp     loc_180070167
0x1800702b1  mov     ecx, dword ptr [rbp+80h+var_80]; unsigned __int64
0x1800702b4  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800702b9  mov     r14, rax
0x1800702bc  test    rax, rax
0x1800702bf  jnz     short loc_1800702CF
0x1800702c1  mov     r8d, dword ptr [rbp+80h+var_80]
0x1800702c5  mov     dword ptr [rsp+0C0h+pcbResult], 376h
0x1800702cd  jmp     short loc_1800702A5
0x1800702cf  mov     r9d, dword ptr [rbp+80h+pbOutput]; cbHashObject
0x1800702d3  lea     rdx, [rbp+80h+phHash]; phHash
0x1800702d7  mov     rcx, [rbp+80h+phAlgorithm]; hAlgorithm
0x1800702db  mov     r8, rbx; pbHashObject
0x1800702de  mov     [rsp+0C0h+var_90], esi; dwFlags
0x1800702e2  mov     [rsp+0C0h+dwFlags], esi; cbSecret
0x1800702e6  mov     [rsp+0C0h+pcbResult], rsi; pbSecret
0x1800702eb  call    cs:__imp_BCryptCreateHash
0x1800702f1  test    eax, eax
0x1800702f3  jns     short loc_18007030A
0x1800702f5  mov     ecx, eax; Status
0x1800702f7  call    cs:__imp_RtlNtStatusToDosError
0x1800702fd  mov     dword ptr [rsp+0C0h+pcbResult], 383h
0x180070305  jmp     loc_18007015B
0x18007030a  mov     rdx, [rbp+80h+pbInput]; pbInput
0x18007030e  xor     r9d, r9d; dwFlags
0x180070311  mov     rcx, [rbp+80h+phHash]; hHash
0x180070315  mov     r8d, r13d; cbInput
0x180070318  call    cs:__imp_BCryptHashData
0x18007031e  test    eax, eax
0x180070320  jns     short loc_180070337
0x180070322  mov     ecx, eax; Status
0x180070324  call    cs:__imp_RtlNtStatusToDosError
0x18007032a  mov     dword ptr [rsp+0C0h+pcbResult], 38Ch
0x180070332  jmp     loc_18007015B
0x180070337  mov     r8d, dword ptr [rbp+80h+var_80]; cbOutput
0x18007033b  xor     r9d, r9d; dwFlags
0x18007033e  mov     rcx, [rbp+80h+phHash]; hHash
0x180070342  mov     rdx, r14; pbOutput
0x180070345  call    cs:__imp_BCryptFinishHash
0x18007034b  test    eax, eax
0x18007034d  jns     short loc_180070364
0x18007034f  mov     ecx, eax; Status
0x180070351  call    cs:__imp_RtlNtStatusToDosError
0x180070357  mov     dword ptr [rsp+0C0h+pcbResult], 395h
0x18007035f  jmp     loc_18007015B
0x180070364  mov     eax, dword ptr [rbp+80h+var_80]
0x180070367  mov     edi, esi
0x180070369  mov     [r12], r14
0x18007036d  mov     r14, rsi
0x180070370  mov     [r15], eax
0x180070373  mov     rcx, [rbp+80h+phHash]; hHash
0x180070377  test    rcx, rcx
0x18007037a  jz      short loc_180070382
0x18007037c  call    cs:__imp_BCryptDestroyHash
0x180070382  mov     rcx, [rbp+80h+phAlgorithm]; hAlgorithm
0x180070386  test    rcx, rcx
0x180070389  jz      short loc_180070393
0x18007038b  xor     edx, edx; dwFlags
0x18007038d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180070393  test    rbx, rbx
0x180070396  jz      short loc_1800703C7
0x180070398  mov     eax, dword ptr [rbp+80h+pbOutput]
0x18007039b  mov     rcx, rbx
0x18007039e  test    rax, rax
0x1800703a1  jz      short loc_1800703AF
0x1800703a3  mov     [rcx], sil
0x1800703a6  inc     rcx
0x1800703a9  sub     rax, 1
0x1800703ad  jnz     short loc_1800703A3
0x1800703af  lea     rcx, [rbx-8]
0x1800703b3  cmp     dword ptr [rcx], 70616548h
0x1800703b9  jnz     short loc_1800703C7
0x1800703bb  mov     rax, cs:g_pfnFree
0x1800703c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703c7  test    r14, r14
0x1800703ca  jz      short loc_1800703EB
0x1800703cc  mov     eax, dword ptr [rbp+80h+var_80]
0x1800703cf  mov     rcx, r14
0x1800703d2  test    rax, rax
0x1800703d5  jz      short loc_1800703E3
0x1800703d7  mov     [rcx], sil
0x1800703da  inc     rcx
0x1800703dd  sub     rax, 1
0x1800703e1  jnz     short loc_1800703D7
0x1800703e3  mov     rcx, r14; lpMem
0x1800703e6  call    EfsFreeHeap
0x1800703eb  mov     eax, edi
0x1800703ed  mov     rcx, [rbp+80h+var_50]
0x1800703f1  xor     rcx, rbp; StackCookie
0x1800703f4  call    __security_check_cookie
0x1800703f9  lea     rsp, [rbp+48h]
0x1800703fd  pop     r15
0x1800703ff  pop     r14
0x180070401  pop     r13
0x180070403  pop     r12
0x180070405  pop     rdi
0x180070406  pop     rsi
0x180070407  pop     rbx
0x180070408  pop     rbp
0x180070409  retn
```
