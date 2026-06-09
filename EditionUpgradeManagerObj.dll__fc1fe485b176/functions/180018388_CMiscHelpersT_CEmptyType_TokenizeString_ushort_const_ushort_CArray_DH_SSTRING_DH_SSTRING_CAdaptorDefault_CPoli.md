# CMiscHelpersT<CEmptyType>::TokenizeString(ushort const *,ushort,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int)

- ea: `0x180018388`
- end: `0x1800185f9`
- name: `?TokenizeString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGGPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@H@Z`
- size: `625`
- prototype: `__int64 __fastcall(wchar_t *Src, __int16, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180022088`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x18000b68c`
- `0x180018044`
- `0x1800181a8`
- `0x1800182ec`
- `0x180018388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001841b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001841b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018404`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018404`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001859a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800185ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001859a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800185ca`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::TokenizeString(wchar_t *Src, __int16 a2, __int64 a3)
{
  wchar_t *v4; // rsi
  int v5; // edi
  wchar_t *v6; // rbx
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v9; // rax
  __int64 v10; // rax
  unsigned int v11; // r14d
  int v12; // ecx
  int v13; // eax
  int v14; // eax
  int v15; // ecx
  int StringCch; // eax
  void *v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  void *v21; // rbx
  HANDLE v22; // rax
  __int64 v24; // [rsp+20h] [rbp-20h] BYREF
  LPVOID v25; // [rsp+28h] [rbp-18h]
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h]
  __int64 v28; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v29; // [rsp+78h] [rbp+38h] BYREF

  LOWORD(v29) = a2;
  v24 = 0;
  v4 = Src;
  v25 = 0;
  v28 = 0;
  if ( !Src || !*Src || !a3 )
  {
    v15 = -2147024809;
    v5 = -2147024809;
LABEL_37:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    goto LABEL_38;
  }
  v5 = 0;
  v6 = Src;
  while ( *v6 )
  {
    v7 = v28;
    if ( v28 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v28 = 0;
    }
    v9 = wcschr(v4, 0x2Eu);
    if ( !v9 )
    {
      if ( !v4 )
        goto LABEL_34;
      break;
    }
    v6 = v9 + 1;
    if ( v9 != (wchar_t *)-2LL )
    {
      do
      {
        if ( *v6 != 46 )
          break;
        ++v6;
      }
      while ( v6 );
    }
    if ( v4 != v9 )
    {
      v10 = v9 - v4;
      v11 = v10;
      if ( v10 == (unsigned int)v10 )
      {
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v5 = 0;
      }
      else
      {
        v5 = -2147024362;
        v11 = 0;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
      if ( v5 < 0 )
      {
        v12 = v5;
        goto LABEL_20;
      }
      v13 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v4, v11, &v28);
      v5 = v13;
      if ( v13 < 0 )
      {
        v12 = v13;
LABEL_20:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
      if ( v5 < 0 )
        goto LABEL_26;
      v14 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v24, &v28);
      v5 = v14;
      if ( v14 < 0 )
        goto LABEL_25;
    }
    v4 = v6;
    if ( !v6 )
      goto LABEL_34;
  }
  if ( *v4 )
  {
    v29 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v4, &v29);
    v5 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v4, v29, &v28),
          v5 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
    if ( v5 < 0 )
    {
LABEL_26:
      v15 = v5;
      goto LABEL_37;
    }
    v14 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v24, &v28);
    v5 = v14;
    if ( v14 < 0 )
    {
LABEL_25:
      v15 = v14;
      goto LABEL_37;
    }
  }
LABEL_34:
  v26 = 0;
  lpMem = 0;
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(&v26, &v24);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(&v26, a3);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v26, 0);
  v17 = lpMem;
  if ( lpMem )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v17);
  }
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  v19 = v28;
  if ( v28 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, (LPVOID)(v19 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v24, 0);
  v21 = v25;
  if ( v25 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018388  mov     [rsp-28h+arg_10], rbx
0x18001838d  mov     [rsp-28h+arg_18], rsi
0x180018392  mov     word ptr [rsp-28h+arg_8], dx
0x180018397  push    rbp
0x180018398  push    rdi
0x180018399  push    r12
0x18001839b  push    r14
0x18001839d  push    r15
0x18001839f  mov     rbp, rsp
0x1800183a2  sub     rsp, 40h
0x1800183a6  xor     r12d, r12d
0x1800183a9  mov     r15, r8
0x1800183ac  mov     [rbp+var_20], r12
0x1800183b0  mov     rsi, rcx
0x1800183b3  mov     [rbp+var_18], r12
0x1800183b7  mov     [rbp+arg_0], r12
0x1800183bb  test    rcx, rcx
0x1800183be  jz      loc_18001857E
0x1800183c4  cmp     [rcx], r12w
0x1800183c8  jz      loc_18001857E
0x1800183ce  test    r8, r8
0x1800183d1  jz      loc_18001857E
0x1800183d7  mov     edi, r12d
0x1800183da  lea     r14d, [r12+2Eh]
0x1800183df  mov     rbx, rcx
0x1800183e2  cmp     [rbx], r12w
0x1800183e6  jz      loc_1800184DD
0x1800183ec  mov     rbx, [rbp+arg_0]
0x1800183f0  test    rbx, rbx
0x1800183f3  jz      short loc_180018415
0x1800183f5  call    cs:__imp_GetProcessHeap
0x1800183fb  lea     r8, [rbx-4]; lpMem
0x1800183ff  xor     edx, edx; dwFlags
0x180018401  mov     rcx, rax; hHeap
0x180018404  call    cs:__imp_HeapFree
0x18001840a  xor     ecx, ecx
0x18001840c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018411  mov     [rbp+arg_0], r12
0x180018415  mov     edx, r14d; Ch
0x180018418  mov     rcx, rsi; Str
0x18001841b  call    cs:__imp_wcschr
0x180018421  test    rax, rax
0x180018424  jz      loc_1800184D8
0x18001842a  lea     rbx, [rax+2]
0x18001842e  test    rbx, rbx
0x180018431  jz      short loc_18001843F
0x180018433  cmp     [rbx], r14w
0x180018437  jnz     short loc_18001843F
0x180018439  add     rbx, 2
0x18001843d  jnz     short loc_180018433
0x18001843f  cmp     rsi, rax
0x180018442  jz      short loc_1800184BC
0x180018444  sub     rax, rsi
0x180018447  sar     rax, 1
0x18001844a  mov     r14d, eax
0x18001844d  cmp     rax, r14
0x180018450  jz      short loc_180018463
0x180018452  mov     edi, 80070216h
0x180018457  mov     r14d, r12d
0x18001845a  mov     ecx, edi
0x18001845c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018461  jmp     short loc_18001846D
0x180018463  xor     ecx, ecx
0x180018465  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001846a  mov     edi, r12d
0x18001846d  mov     ecx, edi
0x18001846f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018474  test    edi, edi
0x180018476  jns     short loc_18001847C
0x180018478  mov     ecx, edi
0x18001847a  jmp     short loc_180018493
0x18001847c  lea     r8, [rbp+arg_0]
0x180018480  mov     edx, r14d
0x180018483  mov     rcx, rsi; Src
0x180018486  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001848b  mov     edi, eax
0x18001848d  test    eax, eax
0x18001848f  jns     short loc_180018498
0x180018491  mov     ecx, eax
0x180018493  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018498  mov     ecx, edi
0x18001849a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001849f  test    edi, edi
0x1800184a1  js      short loc_1800184D1
0x1800184a3  lea     rdx, [rbp+arg_0]
0x1800184a7  lea     rcx, [rbp+var_20]
0x1800184ab  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x1800184b0  mov     edi, eax
0x1800184b2  test    eax, eax
0x1800184b4  js      short loc_1800184CA
0x1800184b6  mov     r14d, 2Eh ; '.'
0x1800184bc  mov     rsi, rbx
0x1800184bf  test    rbx, rbx
0x1800184c2  jnz     loc_1800183E2
0x1800184c8  jmp     short loc_180018533
0x1800184ca  mov     ecx, eax
0x1800184cc  jmp     loc_180018585
0x1800184d1  mov     ecx, edi
0x1800184d3  jmp     loc_180018585
0x1800184d8  test    rsi, rsi
0x1800184db  jz      short loc_180018533
0x1800184dd  cmp     [rsi], r12w
0x1800184e1  jz      short loc_180018533
0x1800184e3  lea     rdx, [rbp+arg_8]
0x1800184e7  mov     [rbp+arg_8], r12d
0x1800184eb  mov     rcx, rsi
0x1800184ee  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800184f3  mov     edi, eax
0x1800184f5  test    eax, eax
0x1800184f7  js      short loc_18001850E
0x1800184f9  mov     edx, [rbp+arg_8]
0x1800184fc  lea     r8, [rbp+arg_0]
0x180018500  mov     rcx, rsi; Src
0x180018503  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180018508  mov     edi, eax
0x18001850a  test    eax, eax
0x18001850c  jns     short loc_180018515
0x18001850e  mov     ecx, eax
0x180018510  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018515  mov     ecx, edi
0x180018517  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001851c  test    edi, edi
0x18001851e  js      short loc_1800184D1
0x180018520  lea     rdx, [rbp+arg_0]
0x180018524  lea     rcx, [rbp+var_20]
0x180018528  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x18001852d  mov     edi, eax
0x18001852f  test    eax, eax
0x180018531  js      short loc_1800184CA
0x180018533  lea     rdx, [rbp+var_20]
0x180018537  mov     [rbp+var_10], r12
0x18001853b  lea     rcx, [rbp+var_10]
0x18001853f  mov     [rbp+lpMem], r12
0x180018543  call    ?Swap@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x180018548  mov     rdx, r15
0x18001854b  lea     rcx, [rbp+var_10]
0x18001854f  call    ?Swap@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x180018554  xor     edx, edx
0x180018556  lea     rcx, [rbp+var_10]
0x18001855a  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001855f  mov     rbx, [rbp+lpMem]
0x180018563  test    rbx, rbx
0x180018566  jz      short loc_18001858A
0x180018568  call    cs:__imp_GetProcessHeap
0x18001856e  mov     r8, rbx; lpMem
0x180018571  xor     edx, edx; dwFlags
0x180018573  mov     rcx, rax; hHeap
0x180018576  call    cs:__imp_HeapFree
0x18001857c  jmp     short loc_18001858A
0x18001857e  mov     ecx, 80070057h
0x180018583  mov     edi, ecx
0x180018585  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001858a  mov     ecx, edi
0x18001858c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018591  mov     rbx, [rbp+arg_0]
0x180018595  test    rbx, rbx
0x180018598  jz      short loc_1800185B6
0x18001859a  call    cs:__imp_GetProcessHeap
0x1800185a0  lea     r8, [rbx-4]; lpMem
0x1800185a4  xor     edx, edx; dwFlags
0x1800185a6  mov     rcx, rax; hHeap
0x1800185a9  call    cs:__imp_HeapFree
0x1800185af  xor     ecx, ecx
0x1800185b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800185b6  xor     edx, edx
0x1800185b8  lea     rcx, [rbp+var_20]
0x1800185bc  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800185c1  mov     rbx, [rbp+var_18]
0x1800185c5  test    rbx, rbx
0x1800185c8  jz      short loc_1800185DE
0x1800185ca  call    cs:__imp_GetProcessHeap
0x1800185d0  mov     r8, rbx; lpMem
0x1800185d3  xor     edx, edx; dwFlags
0x1800185d5  mov     rcx, rax; hHeap
0x1800185d8  call    cs:__imp_HeapFree
0x1800185de  lea     r11, [rsp+40h+var_s0]
0x1800185e3  mov     eax, edi
0x1800185e5  mov     rbx, [r11+40h]
0x1800185e9  mov     rsi, [r11+48h]
0x1800185ed  mov     rsp, r11
0x1800185f0  pop     r15
0x1800185f2  pop     r14
0x1800185f4  pop     r12
0x1800185f6  pop     rdi
0x1800185f7  pop     rbp
0x1800185f8  retn
```
