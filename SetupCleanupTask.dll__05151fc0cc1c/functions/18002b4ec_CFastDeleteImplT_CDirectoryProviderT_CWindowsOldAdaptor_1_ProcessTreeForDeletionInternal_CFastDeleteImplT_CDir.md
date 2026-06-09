# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const *,ushort const *,uint,int,int,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *,double *)

- ea: `0x18002b4ec`
- end: `0x18002b842`
- name: `?ProcessTreeForDeletionInternal@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBUCFastNtfsEntry@1@PEBGIHHPEAV?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAN@Z`
- size: `854`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64, int, unsigned int, __int64, double *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b224`
- `0x18002b4ec`

## callees

- `0x180025124`
- `0x18002620c`
- `0x180027008`
- `0x180027028`
- `0x1800275b8`
- `0x1800293a4`
- `0x18002b4ec`
- `0x1800322c6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b7ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b7eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b80c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b7ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b7eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b80c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b81b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b81b`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(
        __int64 a1,
        _WORD *a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        double *a7)
{
  char *v7; // rsi
  _DWORD *v8; // r14
  _DWORD *v9; // r15
  int v12; // eax
  int v13; // edi
  int v14; // eax
  unsigned int v15; // edx
  int StringCch; // eax
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  const void *v20; // rbx
  unsigned int v21; // r12d
  unsigned int v22; // edi
  BOOL v23; // ebx
  __int64 v24; // r8
  unsigned int v25; // ebx
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ebx
  int Internal; // eax
  int v30; // eax
  int v31; // ebx
  __int64 v32; // r12
  unsigned int v33; // edx
  int v34; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v36; // rax
  HANDLE v37; // rax
  void *v39; // [rsp+40h] [rbp-20h] BYREF
  double v40; // [rsp+48h] [rbp-18h] BYREF
  _DWORD *v41; // [rsp+50h] [rbp-10h] BYREF
  void *Src; // [rsp+A0h] [rbp+40h] BYREF
  int v43; // [rsp+B0h] [rbp+50h]
  int v44; // [rsp+B8h] [rbp+58h]

  v44 = a4;
  v43 = a3;
  v7 = 0;
  v8 = 0;
  Src = 0;
  v9 = 0;
  v39 = 0;
  v40 = *a7;
  v41 = 0;
  if ( !a5 )
  {
    v12 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)a2, *(_QWORD *)(a1 + 8), a3);
    v13 = v12;
    if ( v12 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      v7 = (char *)Src;
      goto LABEL_56;
    }
    v7 = (char *)Src;
    goto LABEL_5;
  }
  v15 = 0;
  a5 = 0;
  if ( a2 )
  {
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a2, &a5);
    v13 = StringCch;
    if ( StringCch < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
      goto LABEL_14;
    }
    v15 = a5;
  }
  v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a2, v15, &Src);
  v13 = v17;
  if ( v17 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
  v7 = (char *)Src;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( v13 < 0 )
    goto LABEL_15;
LABEL_5:
  a5 = 0;
  v14 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"\\\\?\\", &a5);
  v13 = v14;
  if ( v14 >= 0 )
  {
    v19 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"\\\\?\\", a5, &v41);
    v13 = v19;
    if ( v19 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
    v9 = v41;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( v13 < 0 )
    goto LABEL_15;
  if ( v7 )
  {
    v20 = v7;
    v21 = *((_DWORD *)v7 - 1);
  }
  else
  {
    v20 = 0;
    v21 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v9 )
    v22 = *(v9 - 1);
  else
    v22 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v23 = v21 >= v22 && memcmp_0(v20, v9, 2LL * v22) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v23 )
  {
    if ( v7 )
    {
      v25 = *((_DWORD *)v7 - 1);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v26 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v7, v25, &v39);
      v13 = v26;
      if ( v26 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
      v8 = v39;
    }
    else
    {
      v13 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
    if ( v13 < 0 )
      goto LABEL_15;
  }
  else
  {
    v27 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)v9, (__int64)v7, v24);
    v13 = v27;
    if ( v27 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
      v8 = v39;
      goto LABEL_56;
    }
    v8 = v39;
  }
  if ( v8 )
  {
    v28 = *(v8 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                 v8,
                 v28,
                 (_QWORD *)(a1 + 8));
    v13 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Internal);
  }
  else
  {
    v13 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( v13 < 0 )
  {
LABEL_15:
    v18 = v13;
LABEL_16:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
    goto LABEL_56;
  }
  v30 = v43;
  v31 = 0;
  v32 = a6;
  *(_DWORD *)(a1 + 40) = v43;
  if ( *(int *)(a1 + 52) > 0 )
  {
    v33 = v30 + 1;
    a5 = v30 + 1;
    do
    {
      v34 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(
              *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL * v31),
              (_DWORD)v7,
              v33,
              v44,
              0,
              v32,
              (__int64)&v40);
      v13 = v34;
      if ( v34 < 0 )
        goto LABEL_52;
      v33 = a5;
    }
    while ( ++v31 < *(_DWORD *)(a1 + 52) );
  }
  if ( !*(_DWORD *)(a1 + 16) )
  {
    v40 = v40 + *(double *)(a1 + 32);
    goto LABEL_54;
  }
  if ( v44 )
  {
LABEL_54:
    v34 = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Append(
            v32,
            a1);
    v13 = v34;
    if ( v34 < 0 )
    {
LABEL_52:
      v18 = v34;
      goto LABEL_16;
    }
  }
  *a7 = v40;
LABEL_56:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v8 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v7 - 4);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002b4ec  mov     [rsp-38h+arg_8], rbx
0x18002b4f1  mov     [rsp-38h+arg_18], r9d
0x18002b4f6  mov     [rsp-38h+arg_10], r8d
0x18002b4fb  push    rbp
0x18002b4fc  push    rsi
0x18002b4fd  push    rdi
0x18002b4fe  push    r12
0x18002b500  push    r13
0x18002b502  push    r14
0x18002b504  push    r15
0x18002b506  mov     rbp, rsp
0x18002b509  sub     rsp, 60h
0x18002b50d  mov     rax, [rbp+arg_30]
0x18002b511  xor     esi, esi
0x18002b513  xor     r14d, r14d
0x18002b516  mov     [rbp+Src], rsi
0x18002b51a  xor     r15d, r15d
0x18002b51d  mov     [rbp+var_20], r14
0x18002b521  mov     rbx, rdx
0x18002b524  mov     r13, rcx
0x18002b527  movsd   xmm0, qword ptr [rax]
0x18002b52b  movsd   [rbp+var_18], xmm0
0x18002b530  mov     [rbp+var_10], r15
0x18002b534  cmp     [rbp+arg_20], esi
0x18002b537  jnz     short loc_18002B589
0x18002b539  mov     rdx, [rcx+8]
0x18002b53d  lea     r9, [rbp+Src]
0x18002b541  mov     rcx, rbx
0x18002b544  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18002b549  mov     edi, eax
0x18002b54b  test    eax, eax
0x18002b54d  jns     short loc_18002B55F
0x18002b54f  mov     ecx, eax
0x18002b551  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b556  mov     rsi, [rbp+Src]
0x18002b55a  jmp     loc_18002B7BE
0x18002b55f  mov     rsi, [rbp+Src]
0x18002b563  lea     rdx, [rbp+arg_20]
0x18002b567  mov     [rbp+arg_20], r14d
0x18002b56b  lea     rcx, asc_18003D740; "\\\\?\\"
0x18002b572  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002b577  mov     edi, eax
0x18002b579  test    eax, eax
0x18002b57b  jns     short loc_18002B5E5
0x18002b57d  mov     ecx, eax
0x18002b57f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b584  jmp     loc_18002B609
0x18002b589  xor     edx, edx
0x18002b58b  mov     [rbp+arg_20], edx
0x18002b58e  test    rbx, rbx
0x18002b591  jz      short loc_18002B5B1
0x18002b593  lea     rdx, [rbp+arg_20]
0x18002b597  mov     rcx, rbx
0x18002b59a  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002b59f  mov     edi, eax
0x18002b5a1  test    eax, eax
0x18002b5a3  jns     short loc_18002B5AE
0x18002b5a5  mov     ecx, eax
0x18002b5a7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b5ac  jmp     short loc_18002B5CE
0x18002b5ae  mov     edx, [rbp+arg_20]
0x18002b5b1  lea     r8, [rbp+Src]
0x18002b5b5  mov     rcx, rbx; Src
0x18002b5b8  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b5bd  mov     edi, eax
0x18002b5bf  test    eax, eax
0x18002b5c1  jns     short loc_18002B5CA
0x18002b5c3  mov     ecx, eax
0x18002b5c5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b5ca  mov     rsi, [rbp+Src]
0x18002b5ce  mov     ecx, edi
0x18002b5d0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b5d5  test    edi, edi
0x18002b5d7  jns     short loc_18002B563
0x18002b5d9  mov     ecx, edi
0x18002b5db  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b5e0  jmp     loc_18002B7BE
0x18002b5e5  mov     edx, [rbp+arg_20]
0x18002b5e8  lea     r8, [rbp+var_10]
0x18002b5ec  lea     rcx, asc_18003D740; "\\\\?\\"
0x18002b5f3  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b5f8  mov     edi, eax
0x18002b5fa  test    eax, eax
0x18002b5fc  jns     short loc_18002B605
0x18002b5fe  mov     ecx, eax
0x18002b600  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b605  mov     r15, [rbp+var_10]
0x18002b609  mov     ecx, edi
0x18002b60b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b610  test    edi, edi
0x18002b612  js      short loc_18002B5D9
0x18002b614  test    rsi, rsi
0x18002b617  jnz     short loc_18002B630
0x18002b619  xor     ebx, ebx
0x18002b61b  xor     r12d, r12d
0x18002b61e  xor     ecx, ecx
0x18002b620  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b625  test    r15, r15
0x18002b628  jz      short loc_18002B63E
0x18002b62a  mov     edi, [r15-4]
0x18002b62e  jmp     short loc_18002B640
0x18002b630  mov     rbx, rsi
0x18002b633  test    rsi, rsi
0x18002b636  jz      short loc_18002B61B
0x18002b638  mov     r12d, [rsi-4]
0x18002b63c  jmp     short loc_18002B61E
0x18002b63e  xor     edi, edi
0x18002b640  xor     ecx, ecx
0x18002b642  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b647  cmp     r12d, edi
0x18002b64a  jb      short loc_18002B666
0x18002b64c  mov     r8d, edi
0x18002b64f  mov     rdx, r15; Buf2
0x18002b652  add     r8, r8; Size
0x18002b655  mov     rcx, rbx; Buf1
0x18002b658  call    memcmp_0
0x18002b65d  xor     ebx, ebx
0x18002b65f  test    eax, eax
0x18002b661  setz    bl
0x18002b664  jmp     short loc_18002B668
0x18002b666  xor     ebx, ebx
0x18002b668  xor     ecx, ecx
0x18002b66a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b66f  test    ebx, ebx
0x18002b671  jz      short loc_18002B6B5
0x18002b673  test    rsi, rsi
0x18002b676  jz      short loc_18002B6A3
0x18002b678  mov     ebx, [rsi-4]
0x18002b67b  xor     ecx, ecx
0x18002b67d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b682  lea     r8, [rbp+var_20]
0x18002b686  mov     edx, ebx
0x18002b688  mov     rcx, rsi; Src
0x18002b68b  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b690  mov     edi, eax
0x18002b692  test    eax, eax
0x18002b694  jns     short loc_18002B69D
0x18002b696  mov     ecx, eax
0x18002b698  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b69d  mov     r14, [rbp+var_20]
0x18002b6a1  jmp     short loc_18002B6A5
0x18002b6a3  xor     edi, edi
0x18002b6a5  mov     ecx, edi
0x18002b6a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b6ac  test    edi, edi
0x18002b6ae  jns     short loc_18002B6DE
0x18002b6b0  jmp     loc_18002B5D9
0x18002b6b5  lea     r9, [rbp+var_20]
0x18002b6b9  mov     rdx, rsi
0x18002b6bc  mov     rcx, r15
0x18002b6bf  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18002b6c4  mov     edi, eax
0x18002b6c6  test    eax, eax
0x18002b6c8  jns     short loc_18002B6DA
0x18002b6ca  mov     ecx, eax
0x18002b6cc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b6d1  mov     r14, [rbp+var_20]
0x18002b6d5  jmp     loc_18002B7BE
0x18002b6da  mov     r14, [rbp+var_20]
0x18002b6de  test    r14, r14
0x18002b6e1  jz      short loc_18002B70B
0x18002b6e3  mov     ebx, [r14-4]
0x18002b6e7  xor     ecx, ecx
0x18002b6e9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b6ee  lea     r8, [r13+8]
0x18002b6f2  mov     edx, ebx
0x18002b6f4  mov     rcx, r14; Src
0x18002b6f7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b6fc  mov     edi, eax
0x18002b6fe  test    eax, eax
0x18002b700  jns     short loc_18002B711
0x18002b702  mov     ecx, eax
0x18002b704  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b709  jmp     short loc_18002B711
0x18002b70b  xor     edi, edi
0x18002b70d  mov     [r13+8], rdi
0x18002b711  mov     ecx, edi
0x18002b713  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b718  test    edi, edi
0x18002b71a  js      loc_18002B5D9
0x18002b720  mov     eax, [rbp+arg_10]
0x18002b723  xor     ebx, ebx
0x18002b725  mov     r12, [rbp+arg_28]
0x18002b729  mov     [r13+28h], eax
0x18002b72d  cmp     [r13+34h], ebx
0x18002b731  jle     short loc_18002B77A
0x18002b733  lea     edx, [rax+1]
0x18002b736  mov     [rbp+arg_20], edx
0x18002b739  mov     rax, [r13+38h]
0x18002b73d  lea     r8, [rbp+var_18]
0x18002b741  mov     r9d, [rbp+arg_18]
0x18002b745  mov     [rsp+60h+var_30], r8
0x18002b74a  mov     r8d, edx
0x18002b74d  movsxd  rcx, ebx
0x18002b750  mov     rdx, rsi
0x18002b753  mov     [rsp+60h+var_38], r12
0x18002b758  mov     [rsp+60h+var_40], 0
0x18002b760  mov     rcx, [rax+rcx*8]
0x18002b764  call    ?ProcessTreeForDeletionInternal@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBUCFastNtfsEntry@1@PEBGIHHPEAV?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAN@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const *,ushort const *,uint,int,int,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *,double *)
0x18002b769  mov     edi, eax
0x18002b76b  test    eax, eax
0x18002b76d  js      short loc_18002B793
0x18002b76f  mov     edx, [rbp+arg_20]
0x18002b772  inc     ebx
0x18002b774  cmp     ebx, [r13+34h]
0x18002b778  jl      short loc_18002B739
0x18002b77a  cmp     dword ptr [r13+10h], 0
0x18002b77f  jnz     short loc_18002B79A
0x18002b781  movsd   xmm0, [rbp+var_18]
0x18002b786  addsd   xmm0, qword ptr [r13+20h]
0x18002b78c  movsd   [rbp+var_18], xmm0
0x18002b791  jmp     short loc_18002B7A0
0x18002b793  mov     ecx, eax
0x18002b795  jmp     loc_18002B5DB
0x18002b79a  cmp     [rbp+arg_18], 0
0x18002b79e  jz      short loc_18002B7B1
0x18002b7a0  mov     rdx, r13
0x18002b7a3  mov     rcx, r12
0x18002b7a6  call    ?Append@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJPEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Append(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *)
0x18002b7ab  mov     edi, eax
0x18002b7ad  test    eax, eax
0x18002b7af  js      short loc_18002B793
0x18002b7b1  mov     rax, [rbp+arg_30]
0x18002b7b5  movsd   xmm0, [rbp+var_18]
0x18002b7ba  movsd   qword ptr [rax], xmm0
0x18002b7be  mov     ecx, edi
0x18002b7c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b7c5  test    r15, r15
0x18002b7c8  jz      short loc_18002B7E6
0x18002b7ca  call    cs:__imp_GetProcessHeap
0x18002b7d0  lea     r8, [r15-4]; lpMem
0x18002b7d4  xor     edx, edx; dwFlags
0x18002b7d6  mov     rcx, rax; hHeap
0x18002b7d9  call    cs:__imp_HeapFree
0x18002b7df  xor     ecx, ecx
0x18002b7e1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b7e6  test    r14, r14
0x18002b7e9  jz      short loc_18002B807
0x18002b7eb  call    cs:__imp_GetProcessHeap
0x18002b7f1  lea     r8, [r14-4]; lpMem
0x18002b7f5  xor     edx, edx; dwFlags
0x18002b7f7  mov     rcx, rax; hHeap
0x18002b7fa  call    cs:__imp_HeapFree
0x18002b800  xor     ecx, ecx
0x18002b802  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b807  test    rsi, rsi
0x18002b80a  jz      short loc_18002B828
0x18002b80c  call    cs:__imp_GetProcessHeap
0x18002b812  lea     r8, [rsi-4]; lpMem
0x18002b816  xor     edx, edx; dwFlags
0x18002b818  mov     rcx, rax; hHeap
0x18002b81b  call    cs:__imp_HeapFree
0x18002b821  xor     ecx, ecx
0x18002b823  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b828  mov     rbx, [rsp+60h+arg_8]
0x18002b830  mov     eax, edi
0x18002b832  add     rsp, 60h
0x18002b836  pop     r15
0x18002b838  pop     r14
0x18002b83a  pop     r13
0x18002b83c  pop     r12
0x18002b83e  pop     rdi
0x18002b83f  pop     rsi
0x18002b840  pop     rbp
0x18002b841  retn
```
