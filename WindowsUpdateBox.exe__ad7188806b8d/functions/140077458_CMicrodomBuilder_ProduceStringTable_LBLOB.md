# CMicrodomBuilder::ProduceStringTable(_LBLOB *)

- ea: `0x140077458`
- end: `0x14007787c`
- name: `?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400754c0`

## callees

- `0x140002116`
- `0x140002326`
- `0x140072764`
- `0x14007411c`
- `0x14007729c`
- `0x140077458`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14007759c`
- `KERNEL32!HeapFree` at `0x140077691`
- `KERNEL32!HeapFree` at `0x140077849`
- `KERNEL32!HeapFree` at `0x14007759c`
- `KERNEL32!HeapFree` at `0x140077691`
- `KERNEL32!HeapFree` at `0x140077849`
- `KERNEL32!HeapAlloc` at `0x140077506`
- `KERNEL32!HeapAlloc` at `0x140077506`
- `KERNEL32!GetProcessHeap` at `0x1400774f2`
- `KERNEL32!GetProcessHeap` at `0x140077588`
- `KERNEL32!GetProcessHeap` at `0x14007767d`
- `KERNEL32!GetProcessHeap` at `0x140077835`
- `KERNEL32!GetProcessHeap` at `0x1400774f2`
- `KERNEL32!GetProcessHeap` at `0x140077588`
- `KERNEL32!GetProcessHeap` at `0x14007767d`
- `KERNEL32!GetProcessHeap` at `0x140077835`
- `ntdll!RtlRaiseStatus` at `0x140077823`
- `ntdll!RtlRaiseStatus` at `0x140077823`

## string_xrefs

- `0x14007754b`: `onecore\base\xml\udom_builder.cpp`
- `0x140077643`: `onecore\base\xml\udom_builder.cpp`
- `0x14007776f`: `onecore\base\xml\udom_builder.cpp`
- `0x1400777e2`: `onecore\base\xml\udom_builder.cpp`
- `0x140077661`: `BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)`
- `0x140077800`: `BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ProduceStringTable(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  const char *v2; // rax
  char *v3; // r13
  const char *v5; // rbx
  const char *v6; // rsi
  const char *v7; // rcx
  size_t **v9; // rdi
  unsigned __int64 v10; // r15
  SIZE_T v11; // r14
  HANDLE ProcessHeap; // rax
  size_t **v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  HANDLE v16; // rax
  const char *v18; // rax
  const char *v19; // rcx
  size_t **v20; // r11
  const char *v21; // rcx
  __int64 v22; // r11
  int v23; // ebx
  const char *v24; // rax
  HANDLE v25; // rax
  unsigned __int64 v26; // r13
  char *v27; // r15
  __int64 v28; // rax
  char *v29; // rsi
  size_t **v30; // rbx
  size_t *v31; // rax
  size_t v32; // rax
  int v33; // ecx
  unsigned __int64 v34; // rsi
  int v35; // ecx
  HANDLE v36; // rax
  int v37; // [rsp+20h] [rbp-40h] BYREF
  int v38; // [rsp+24h] [rbp-3Ch]
  __int64 v39; // [rsp+28h] [rbp-38h]
  const char *v40; // [rsp+30h] [rbp-30h] BYREF
  __int64 v41; // [rsp+38h] [rbp-28h]
  __int64 v42; // [rsp+40h] [rbp-20h]
  const char *v43; // [rsp+48h] [rbp-18h]
  const char *v44; // [rsp+50h] [rbp-10h]

  v2 = (const char *)*((_QWORD *)this + 2);
  v3 = (char *)this + 8;
  v40 = (char *)this + 8;
  v5 = 0;
  v6 = 0;
  v7 = &v2[32 * *((_QWORD *)this + 4)];
  v43 = 0;
  v44 = 0;
  while ( v2 < v7 )
  {
    if ( *(const char **)v2 != v2 )
    {
      v6 = *(const char **)v2;
      v5 = v2;
      v44 = *(const char **)v2;
      v43 = v2;
      break;
    }
    v2 += 32;
  }
  v9 = 0;
  v10 = *((_QWORD *)this + 5);
  v41 = (__int64)&v2[-*((_QWORD *)v3 + 1)] >> 5;
  LOBYTE(v42) = 0;
  if ( v10 )
  {
    v11 = 16 * v10;
    if ( !is_mul_ok(v10, 0x10u) )
      v11 = -1;
    ProcessHeap = GetProcessHeap();
    v13 = (size_t **)HeapAlloc(ProcessHeap, 0, v11);
    v9 = v13;
    if ( v13 )
      memset_0(v13, 0, v11);
    else
      v9 = 0;
  }
  v14 = (__int64)v9;
  v15 = v10 & -(__int64)(v9 != 0);
  if ( !v10 )
    v14 = 8;
  if ( !v14 )
  {
    v42 = 454;
    v40 = "onecore\\base\\xml\\udom_builder.cpp";
    v41 = (__int64)"CMicrodomBuilder::ProduceStringTable";
    v43 = "Pairs.Allocate(m_StringTable.GetEntryCount())";
    RtlReportErrorOrigination(&v40, a2, 3221225495LL);
    if ( v9 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v9);
    }
    return 3221225495LL;
  }
  v18 = (const char *)*((_QWORD *)v3 + 1);
  v19 = &v18[32 * *((_QWORD *)v3 + 3)];
  while ( v18 < v19 )
  {
    if ( *(const char **)v18 != v18 )
    {
      v6 = *(const char **)v18;
      v5 = v18;
      v44 = *(const char **)v18;
      v43 = v18;
      break;
    }
    v18 += 32;
  }
  v20 = v9;
  v41 = (__int64)&v18[-*((_QWORD *)v3 + 1)] >> 5;
  while ( v5 )
  {
    v21 = 0;
    if ( v6 != v5 )
      v21 = v6;
    *(_DWORD *)v20 = *((_DWORD *)v21 + 16);
    v20[1] = (size_t *)(v21 + 40);
    BUCL::HashTable::CConstIterator<CMicrodomBuilder::CIntermediateStringTableTraits>::Next(&v40);
    v6 = v44;
    v20 = (size_t **)(v22 + 16);
    v5 = v43;
  }
  BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(
    &v37,
    v9,
    (__int64)(16 * v15) >> 4);
  v23 = v37;
  if ( v37 < 0 )
  {
    v42 = 462;
    v40 = "onecore\\base\\xml\\udom_builder.cpp";
    v41 = (__int64)"CMicrodomBuilder::ProduceStringTable";
    v24 = "BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)";
LABEL_32:
    v43 = v24;
    RtlReportErrorOrigination(&v40, 0, (unsigned int)v23);
    if ( v9 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v9);
    }
    return (unsigned int)v23;
  }
  v26 = 0;
  v27 = (char *)(*((_QWORD *)a2 + 2) + *(_QWORD *)a2);
  v28 = *((_QWORD *)a2 + 2) + *((_QWORD *)a2 + 1);
  v39 = v28;
  v29 = v27 + 12;
  if ( v15 )
  {
    v30 = v9 + 1;
    while ( v28 - (__int64)v29 > **v30 )
    {
      memcpy_0(v29, (const void *)(*v30)[2], **v30);
      v31 = *v30;
      ++v26;
      v30 += 2;
      v32 = *v31;
      v29[v32] = 0;
      v29 += v32 + 1;
      v28 = v39;
      if ( v26 >= v15 )
        goto LABEL_39;
    }
    goto LABEL_54;
  }
LABEL_39:
  *(_QWORD *)a2 = &v29[-*((_QWORD *)a2 + 2)];
  v38 = 0;
  if ( v15 > 0xFFFFFFFF )
  {
    v38 = -1073741675;
    v33 = 0;
    BYTE4(v39) = -107;
  }
  else
  {
    v33 = v15;
    if ( v15 == (unsigned int)v15 )
    {
      v38 = 0;
      BYTE4(v39) = 0;
    }
    else
    {
      v38 = -1073741595;
      BYTE4(v39) = -27;
    }
  }
  *(_WORD *)((char *)&v39 + 5) = *(_WORD *)((char *)&v38 + 1);
  HIBYTE(v39) = HIBYTE(v38);
  v23 = HIDWORD(v39);
  *((_DWORD *)v27 + 2) = v33;
  if ( v23 < 0 )
  {
    v42 = 491;
    v40 = "onecore\\base\\xml\\udom_builder.cpp";
    v41 = (__int64)"CMicrodomBuilder::ProduceStringTable";
    v24 = "BUCL::Rtl::ConvertInteger(Pairs.Length, pHeader->TotalCount)";
    goto LABEL_32;
  }
  v34 = v29 - v27;
  HIDWORD(v39) = 0;
  v35 = 0;
  if ( v34 > 0xFFFFFFFF )
  {
    HIDWORD(v39) = -1073741675;
    LOBYTE(v38) = -107;
  }
  else
  {
    v35 = v34;
    if ( v34 == (unsigned int)v34 )
    {
      HIDWORD(v39) = 0;
      LOBYTE(v38) = 0;
    }
    else
    {
      HIDWORD(v39) = -1073741595;
      LOBYTE(v38) = -27;
    }
  }
  *(_WORD *)((char *)&v38 + 1) = *(_WORD *)((char *)&v39 + 5);
  HIBYTE(v38) = HIBYTE(v39);
  v23 = v38;
  *((_DWORD *)v27 + 1) = v35;
  if ( v23 < 0 )
  {
    v42 = 496;
    v40 = "onecore\\base\\xml\\udom_builder.cpp";
    v41 = (__int64)"CMicrodomBuilder::ProduceStringTable";
    v24 = "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)";
    goto LABEL_32;
  }
  *(_DWORD *)v27 = 1884513357;
  if ( *(_QWORD *)a2 > *((_QWORD *)a2 + 1) )
LABEL_54:
    RtlRaiseStatus(-1073741595);
  if ( v9 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x140077458  mov     [rsp-38h+arg_10], rbx
0x14007745d  push    rbp
0x14007745e  push    rsi
0x14007745f  push    rdi
0x140077460  push    r12
0x140077462  push    r13
0x140077464  push    r14
0x140077466  push    r15
0x140077468  mov     rbp, rsp
0x14007746b  sub     rsp, 60h
0x14007746f  mov     rax, cs:__security_cookie
0x140077476  xor     rax, rsp
0x140077479  mov     [rbp+var_8], rax
0x14007747d  mov     rax, [rcx+10h]
0x140077481  lea     r13, [rcx+8]
0x140077485  mov     r15, rcx
0x140077488  mov     [rbp+var_30], r13
0x14007748c  mov     rcx, [r13+18h]
0x140077490  xor     ebx, ebx
0x140077492  xor     esi, esi
0x140077494  shl     rcx, 5
0x140077498  add     rcx, rax
0x14007749b  mov     [rbp+var_18], rbx
0x14007749f  mov     r12, rdx
0x1400774a2  mov     [rbp+var_10], rsi
0x1400774a6  jmp     short loc_1400774B1
0x1400774a8  cmp     [rax], rax
0x1400774ab  jnz     short loc_1400774B8
0x1400774ad  add     rax, 20h ; ' '
0x1400774b1  cmp     rax, rcx
0x1400774b4  jb      short loc_1400774A8
0x1400774b6  jmp     short loc_1400774C6
0x1400774b8  mov     rsi, [rax]
0x1400774bb  mov     rbx, rax
0x1400774be  mov     [rbp+var_10], rsi
0x1400774c2  mov     [rbp+var_18], rax
0x1400774c6  sub     rax, [r13+8]
0x1400774ca  xor     edi, edi
0x1400774cc  mov     r15, [r15+28h]
0x1400774d0  sar     rax, 5
0x1400774d4  mov     [rbp+var_28], rax
0x1400774d8  mov     byte ptr [rbp+var_20], 0
0x1400774dc  test    r15, r15
0x1400774df  jz      short loc_14007752B
0x1400774e1  lea     eax, [rdi+10h]
0x1400774e4  mul     r15
0x1400774e7  mov     r14, rax
0x1400774ea  lea     rax, [rdi-1]
0x1400774ee  cmovb   r14, rax
0x1400774f2  call    cs:__imp_GetProcessHeap
0x1400774f9  nop     dword ptr [rax+rax+00h]
0x1400774fe  mov     r8, r14; dwBytes
0x140077501  xor     edx, edx; dwFlags
0x140077503  mov     rcx, rax; hHeap
0x140077506  call    cs:__imp_HeapAlloc
0x14007750d  nop     dword ptr [rax+rax+00h]
0x140077512  mov     rdi, rax
0x140077515  test    rax, rax
0x140077518  jz      short loc_140077529
0x14007751a  mov     r8, r14; Size
0x14007751d  xor     edx, edx; Val
0x14007751f  mov     rcx, rax; void *
0x140077522  call    memset_0
0x140077527  jmp     short loc_14007752B
0x140077529  xor     edi, edi
0x14007752b  mov     rax, rdi
0x14007752e  mov     ecx, 8
0x140077533  neg     rax
0x140077536  mov     rax, rdi
0x140077539  sbb     r14, r14
0x14007753c  and     r14, r15
0x14007753f  test    r15, r15
0x140077542  cmovz   rax, rcx
0x140077546  test    rax, rax
0x140077549  jnz     short loc_1400775B2
0x14007754b  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x140077552  mov     [rbp+var_20], 1C6h
0x14007755a  mov     [rbp+var_30], rax
0x14007755e  lea     rcx, [rbp+var_30]
0x140077562  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x140077569  mov     r8d, 0C0000017h
0x14007756f  mov     [rbp+var_28], rax
0x140077573  lea     rax, aPairsAllocateM; "Pairs.Allocate(m_StringTable.GetEntryCo"...
0x14007757a  mov     [rbp+var_18], rax
0x14007757e  call    RtlReportErrorOrigination
0x140077583  test    rdi, rdi
0x140077586  jz      short loc_1400775A8
0x140077588  call    cs:__imp_GetProcessHeap
0x14007758f  nop     dword ptr [rax+rax+00h]
0x140077594  mov     r8, rdi; lpMem
0x140077597  xor     edx, edx; dwFlags
0x140077599  mov     rcx, rax; hHeap
0x14007759c  call    cs:__imp_HeapFree
0x1400775a3  nop     dword ptr [rax+rax+00h]
0x1400775a8  mov     eax, 0C0000017h
0x1400775ad  jmp     loc_140077857
0x1400775b2  mov     rcx, [r13+18h]
0x1400775b6  mov     rax, [r13+8]
0x1400775ba  shl     rcx, 5
0x1400775be  add     rcx, rax
0x1400775c1  jmp     short loc_1400775CC
0x1400775c3  cmp     [rax], rax
0x1400775c6  jnz     short loc_1400775D3
0x1400775c8  add     rax, 20h ; ' '
0x1400775cc  cmp     rax, rcx
0x1400775cf  jb      short loc_1400775C3
0x1400775d1  jmp     short loc_1400775E1
0x1400775d3  mov     rsi, [rax]
0x1400775d6  mov     rbx, rax
0x1400775d9  mov     [rbp+var_10], rsi
0x1400775dd  mov     [rbp+var_18], rax
0x1400775e1  sub     rax, [r13+8]
0x1400775e5  mov     r11, rdi
0x1400775e8  sar     rax, 5
0x1400775ec  mov     [rbp+var_28], rax
0x1400775f0  test    rbx, rbx
0x1400775f3  jz      short loc_140077623
0x1400775f5  xor     ecx, ecx
0x1400775f7  cmp     rsi, rbx
0x1400775fa  cmovnz  rcx, rsi
0x1400775fe  mov     eax, [rcx+40h]
0x140077601  mov     [r11], eax
0x140077604  lea     rax, [rcx+28h]
0x140077608  lea     rcx, [rbp+var_30]
0x14007760c  mov     [r11+8], rax
0x140077610  call    ?Next@?$CConstIterator@VCIntermediateStringTableTraits@CMicrodomBuilder@@@HashTable@BUCL@@QEAAXXZ; BUCL::HashTable::CConstIterator<CMicrodomBuilder::CIntermediateStringTableTraits>::Next(void)
0x140077615  mov     rsi, [rbp+var_10]
0x140077619  add     r11, 10h
0x14007761d  mov     rbx, [rbp+var_18]
0x140077621  jmp     short loc_1400775F0
0x140077623  mov     r8, r14
0x140077626  lea     rcx, [rbp+var_40]
0x14007762a  shl     r8, 4
0x14007762e  mov     rdx, rdi
0x140077631  sar     r8, 4
0x140077635  call    ??$QuickSort@VCCallDisposition@Rtl@BUCL@@_KUStringTablePair@CMicrodomBuilder@@P6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@Implementation@3@AEBU45@0@Z@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@PEAUStringTablePair@CMicrodomBuilder@@_KP6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@01@AEBU45@2@Z@Z; BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(CMicrodomBuilder::StringTablePair *,unsigned __int64,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &))
0x14007763a  mov     ebx, [rbp+var_40]
0x14007763d  xor     edx, edx
0x14007763f  test    ebx, ebx
0x140077641  jns     short loc_1400776A4
0x140077643  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x14007764a  mov     [rbp+var_20], 1CEh
0x140077652  mov     [rbp+var_30], rax
0x140077656  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x14007765d  mov     [rbp+var_28], rax
0x140077661  lea     rax, aBuclRtlQuickso; "BUCL::Rtl::QuickSort(Pairs, CompareStri"...
0x140077668  mov     r8d, ebx
0x14007766b  mov     [rbp+var_18], rax
0x14007766f  lea     rcx, [rbp+var_30]
0x140077673  call    RtlReportErrorOrigination
0x140077678  test    rdi, rdi
0x14007767b  jz      short loc_14007769D
0x14007767d  call    cs:__imp_GetProcessHeap
0x140077684  nop     dword ptr [rax+rax+00h]
0x140077689  mov     r8, rdi; lpMem
0x14007768c  xor     edx, edx; dwFlags
0x14007768e  mov     rcx, rax; hHeap
0x140077691  call    cs:__imp_HeapFree
0x140077698  nop     dword ptr [rax+rax+00h]
0x14007769d  mov     eax, ebx
0x14007769f  jmp     loc_140077857
0x1400776a4  mov     r15, [r12]
0x1400776a8  mov     r13, rdx
0x1400776ab  add     r15, [r12+10h]
0x1400776b0  mov     rax, [r12+8]
0x1400776b5  add     rax, [r12+10h]
0x1400776ba  mov     [rbp+var_38], rax
0x1400776be  lea     rsi, [r15+0Ch]
0x1400776c2  test    r14, r14
0x1400776c5  jz      short loc_14007770A
0x1400776c7  lea     rbx, [rdi+8]
0x1400776cb  mov     rdx, [rbx]
0x1400776ce  sub     rax, rsi
0x1400776d1  cmp     rax, [rdx]
0x1400776d4  jbe     loc_14007781E
0x1400776da  mov     r8, [rdx]; Size
0x1400776dd  mov     rcx, rsi; void *
0x1400776e0  mov     rdx, [rdx+10h]; Src
0x1400776e4  call    memcpy_0
0x1400776e9  mov     rax, [rbx]
0x1400776ec  xor     edx, edx
0x1400776ee  inc     r13
0x1400776f1  add     rbx, 10h
0x1400776f5  mov     rax, [rax]
0x1400776f8  mov     [rax+rsi], dl
0x1400776fb  inc     rax
0x1400776fe  add     rsi, rax
0x140077701  mov     rax, [rbp+var_38]
0x140077705  cmp     r13, r14
0x140077708  jb      short loc_1400776CB
0x14007770a  mov     rax, rsi
0x14007770d  mov     r10d, 0FFFFFFFFh
0x140077713  sub     rax, [r12+10h]
0x140077718  mov     r8d, 0C0000095h
0x14007771e  mov     [r12], rax
0x140077722  mov     r9d, 0C00000E5h
0x140077728  xor     eax, eax
0x14007772a  mov     [rbp+var_3C], eax
0x14007772d  cmp     r14, r10
0x140077730  ja      short loc_14007774C
0x140077732  mov     ecx, r14d
0x140077735  cmp     r14, rcx
0x140077738  jz      short loc_140077744
0x14007773a  mov     [rbp+var_3C], r9d
0x14007773e  mov     byte ptr [rbp+var_38+4], 0E5h
0x140077742  jmp     short loc_140077756
0x140077744  mov     [rbp+var_3C], edx
0x140077747  mov     byte ptr [rbp+var_38+4], dl
0x14007774a  jmp     short loc_140077756
0x14007774c  mov     [rbp+var_3C], r8d
0x140077750  mov     ecx, edx
0x140077752  mov     byte ptr [rbp+var_38+4], 95h
0x140077756  movzx   eax, word ptr [rbp+var_3C+1]
0x14007775a  mov     word ptr [rbp+var_38+5], ax
0x14007775e  mov     al, byte ptr [rbp+var_3C+3]
0x140077761  mov     byte ptr [rbp+var_38+7], al
0x140077764  mov     ebx, dword ptr [rbp+var_38+4]
0x140077767  mov     [r15+8], ecx
0x14007776b  test    ebx, ebx
0x14007776d  jns     short loc_140077799
0x14007776f  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x140077776  mov     [rbp+var_20], 1EBh
0x14007777e  mov     [rbp+var_30], rax
0x140077782  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x140077789  mov     [rbp+var_28], rax
0x14007778d  lea     rax, aBuclRtlConvert; "BUCL::Rtl::ConvertInteger(Pairs.Length,"...
0x140077794  jmp     loc_140077668
0x140077799  xor     eax, eax
0x14007779b  sub     rsi, r15
0x14007779e  mov     dword ptr [rbp+var_38+4], eax
0x1400777a1  mov     ecx, edx
0x1400777a3  cmp     rsi, r10
0x1400777a6  ja      short loc_1400777C1
0x1400777a8  mov     ecx, esi
0x1400777aa  cmp     rsi, rcx
0x1400777ad  jz      short loc_1400777B9
0x1400777af  mov     dword ptr [rbp+var_38+4], r9d
0x1400777b3  mov     byte ptr [rbp+var_3C], 0E5h
0x1400777b7  jmp     short loc_1400777C9
0x1400777b9  mov     dword ptr [rbp+var_38+4], edx
0x1400777bc  mov     byte ptr [rbp+var_3C], dl
0x1400777bf  jmp     short loc_1400777C9
0x1400777c1  mov     dword ptr [rbp+var_38+4], r8d
0x1400777c5  mov     byte ptr [rbp+var_3C], 95h
0x1400777c9  movzx   eax, word ptr [rbp+var_38+5]
0x1400777cd  mov     word ptr [rbp+var_3C+1], ax
0x1400777d1  mov     al, byte ptr [rbp+var_38+7]
0x1400777d4  mov     byte ptr [rbp+var_3C+3], al
0x1400777d7  mov     ebx, [rbp+var_3C]
0x1400777da  mov     [r15+4], ecx
0x1400777de  test    ebx, ebx
0x1400777e0  jns     short loc_14007780C
0x1400777e2  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400777e9  mov     [rbp+var_20], 1F0h
0x1400777f1  mov     [rbp+var_30], rax
0x1400777f5  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x1400777fc  mov     [rbp+var_28], rax
0x140077800  lea     rax, aBuclRtlConvert_3; "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)"...
0x140077807  jmp     loc_140077668
0x14007780c  mov     dword ptr [r15], 7053644Dh
0x140077813  mov     rax, [r12+8]
0x140077818  cmp     [r12], rax
0x14007781c  jbe     short loc_140077830
0x14007781e  mov     ecx, 0C00000E5h; Status
0x140077823  call    cs:__imp_RtlRaiseStatus
0x14007782a  nop     dword ptr [rax+rax+00h]
0x14007782f  int     3; Trap to Debugger
0x140077830  test    rdi, rdi
0x140077833  jz      short loc_140077855
0x140077835  call    cs:__imp_GetProcessHeap
0x14007783c  nop     dword ptr [rax+rax+00h]
0x140077841  mov     r8, rdi; lpMem
0x140077844  xor     edx, edx; dwFlags
0x140077846  mov     rcx, rax; hHeap
0x140077849  call    cs:__imp_HeapFree
0x140077850  nop     dword ptr [rax+rax+00h]
0x140077855  xor     eax, eax
0x140077857  mov     rcx, [rbp+var_8]
0x14007785b  xor     rcx, rsp; StackCookie
0x14007785e  call    __security_check_cookie
0x140077863  mov     rbx, [rsp+60h+arg_10]
0x14007786b  add     rsp, 60h
0x14007786f  pop     r15
0x140077871  pop     r14
0x140077873  pop     r13
0x140077875  pop     r12
0x140077877  pop     rdi
0x140077878  pop     rsi
0x140077879  pop     rbp
0x14007787a  retn
```
