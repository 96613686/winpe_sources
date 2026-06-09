# MergeContext::MergeInternalAndExternalRangeSets(ulong,SharedRefPtr<ICoreFragment> &,ulong &,SyncIdCache *)

- ea: `0x18000efa0`
- end: `0x18000f45d`
- name: `?MergeInternalAndExternalRangeSets@MergeContext@@QEAAJKAEAV?$SharedRefPtr@UICoreFragment@@@@AEAKPEAVSyncIdCache@@@Z`
- size: `1213`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18000d6e0`

## callees

- `0x1800087fc`
- `0x18000a0f0`
- `0x18000c920`
- `0x18000c958`
- `0x18000e81c`
- `0x18000eaf4`
- `0x18000ebf8`
- `0x18000efa0`
- `0x18000f65c`
- `0x18000f810`
- `0x180013950`
- `0x180014f00`
- `0x180015128`
- `0x18001a038`
- `0x18001ae20`
- `0x18001d690`
- `0x18001f530`
- `0x18008adf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f13f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f13f`

## pseudocode

```c
__int64 __fastcall MergeContext::MergeInternalAndExternalRangeSets(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rax
  _DWORD *v7; // r13
  __int64 v9; // r15
  bool v11; // zf
  RangeSet *v12; // rax
  RangeSet *v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 *v16; // rdx
  _DWORD *v17; // r14
  RangeSet **v18; // r14
  unsigned int *v19; // rbp
  int v20; // r8d
  unsigned int i; // edx
  __int64 v22; // rax
  unsigned int v23; // r14d
  __int64 v24; // r8
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  bool v27; // cf
  SIZE_T v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // r12
  _QWORD *k; // r13
  unsigned __int64 v33; // r11
  unsigned __int64 v34; // r9
  unsigned int j; // r10d
  __int64 v36; // rax
  unsigned __int64 v37; // r9
  __int64 v38; // r11
  unsigned int v39; // r8d
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdx
  __int64 v42; // rcx
  char v43; // al
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 *v48; // rdx
  unsigned int NextPrimeNumber; // eax
  __int64 v50; // r14
  RangeSet *v51; // rax
  RangeSet *v52; // rax
  char v53; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v54[2]; // [rsp+38h] [rbp-50h] BYREF
  _DWORD *v55; // [rsp+40h] [rbp-48h]
  _DWORD *v56; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 80);
  v7 = (_DWORD *)*a3;
  v9 = a2;
  v54[0] = a2;
  v11 = (*(_BYTE *)(v5 + 72) & 1) == 0;
  v55 = v7;
  if ( v11 )
  {
    v12 = (RangeSet *)SeAlloc(0x38u);
    if ( !v12 )
      return (unsigned int)-2147024882;
    v13 = RangeSet::RangeSet(v12);
    v14 = v13 == 0 ? 0x8007000E : 0;
    if ( v13 )
    {
      v15 = *(_QWORD *)(a1 + 72);
      if ( (_DWORD)v9 )
        v16 = (__int64 *)(*(_QWORD *)(v15 + 32) + 8 * v9);
      else
        v16 = (__int64 *)(v15 + 8);
      v14 = RangeSet::InitializeByMergingWithCoreFragment((__int64)v13, *v16, a3, a1, 0);
      if ( v14 )
        goto LABEL_29;
      v17 = *(_DWORD **)(a1 + 80);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_e65626ae806d36e8966776faf765a664_Traceguids,
          "RangeSetManager::InitializeWithScopeRangeSet");
      }
      v17[4] = 0;
      v17[6] = 1;
      HashTable<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::FreeHashTable(v17 + 10);
      v17[10] = GetNextPrimeNumber(1u);
      v17[18] |= 1u;
      v18 = (RangeSet **)(v17 + 2);
      if ( v18 != (RangeSet **)&v53 )
      {
        if ( *v18 )
          RangeSet::Release(*v18);
        *v18 = v13;
        ++*((_DWORD *)v13 + 1);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
          (unsigned int)"RangeSetManager::InitializeWithScopeRangeSet",
          0);
      }
      v19 = (unsigned int *)(a1 + 160);
      v20 = 0;
      v56 = v7;
      for ( i = 0; i < 2; ++i )
      {
        v22 = (int)i;
        v20 ^= *((unsigned __int16 *)&v56 + 2 * v22 + 1) | (*((unsigned __int16 *)&v56 + 2 * v22) << 16);
      }
      v23 = v20 ^ (WORD1(v9) | ((unsigned __int16)v9 << 16));
      v24 = *((_QWORD *)v19 + 1);
      if ( v24 )
      {
        v33 = *v19;
        v34 = v23;
        for ( j = 0; j < (unsigned int)v33; ++j )
        {
          v36 = 32 * (v34 % v33);
          if ( (*(_BYTE *)(v36 + v24 + 24) & 1) != 0 )
          {
            if ( *(_DWORD *)(v36 + v24) == (_DWORD)v9 && *(_DWORD **)(v36 + v24 + 8) == v7 )
            {
              v14 = -2147024809;
              goto LABEL_29;
            }
          }
          else if ( (*(_BYTE *)(v36 + v24 + 24) & 2) == 0 )
          {
            break;
          }
          v34 = ((v23 >> 5) + 1) % ((int)v33 - 1) + 1 + v34 % v33;
        }
        if ( v19[4] + 1 <= 72 * (int)v33 / 0x64u )
          goto LABEL_48;
        NextPrimeNumber = GetNextPrimeNumber(2 * (int)v33);
        v14 = HashTable<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::Resize(v19, NextPrimeNumber);
      }
      else
      {
        v25 = *v19;
        v26 = 32 * v25;
        if ( !is_mul_ok(v25, 0x20u) )
          v26 = -1;
        v27 = __CFADD__(v26, 8);
        v28 = v26 + 8;
        if ( v27 )
          v28 = -1;
        v29 = HeapAlloc(hHeap, 0, v28);
        if ( v29 )
        {
          *v29 = v25;
          v30 = v29 + 1;
          for ( k = v29 + 1; v25; --v25 )
          {
            TableBucket<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::TableBucket<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>(k);
            k += 4;
          }
          v7 = v55;
        }
        else
        {
          v30 = 0;
        }
        *((_QWORD *)v19 + 1) = v30;
        v14 = -2147024882;
        if ( v30 )
          v14 = 0;
      }
      if ( (v14 & 0x80000000) != 0 )
      {
LABEL_29:
        v11 = (*((_DWORD *)v13 + 1))-- == 1;
        if ( v11 )
        {
          Vector<Range,1>::~Vector<Range,1>((char *)v13 + 8);
          SeFree(v13);
        }
        return v14;
      }
LABEL_48:
      v37 = *v19;
      v38 = *((_QWORD *)v19 + 1);
      v39 = 0;
      v40 = v23;
      while ( v39 < (unsigned int)v37 )
      {
        v41 = v40 % v37;
        v42 = 32 * (v40 % v37);
        v43 = *(_BYTE *)(v42 + v38 + 24);
        if ( (v43 & 1) == 0 )
        {
          v44 = *((_QWORD *)v19 + 1);
          v14 = 0;
          v45 = v54[1];
          v46 = 32LL * (unsigned int)v41;
          *(_BYTE *)(v46 + v44 + 24) |= 1u;
          *(_DWORD *)(v46 + v44) = v9;
          *(_DWORD *)(v46 + v44 + 4) = v45;
          *(_QWORD *)(v46 + v44 + 8) = v7;
          *(_DWORD *)(v46 + v44 + 16) = 0;
          ++v19[4];
          goto LABEL_29;
        }
        *(_BYTE *)(v42 + v38 + 24) = v43 | 2;
        v40 = v41 + ((v23 >> 5) + 1) % ((int)v37 - 1) + 1;
        ++v39;
      }
      v14 = -2147418113;
      goto LABEL_29;
    }
  }
  else
  {
    v50 = a1 + 160;
    v14 = 0;
    if ( !(unsigned __int8)HashTable<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::LookupItem(
                             a1 + 160,
                             v54,
                             a4) )
    {
      v56 = 0;
      v51 = (RangeSet *)SeAlloc(0x38u);
      if ( v51 )
        v52 = RangeSet::RangeSet(v51);
      else
        v52 = 0;
      v14 = SharedRefPtr<RangeSet>::Attach(&v56, v52);
      if ( !v14 )
      {
        v47 = *(_QWORD *)(a1 + 72);
        v48 = (__int64 *)((_DWORD)v9 ? *(_QWORD *)(v47 + 32) + 8 * v9 : v47 + 8);
        v14 = RangeSet::InitializeByMergingWithCoreFragment((__int64)v56, *v48, a3, a1, a5);
        if ( !v14 )
        {
          v14 = RangeSetManager::FindByKeyOrAdd(*(_QWORD *)(a1 + 80), &v56, a4);
          if ( !v14 )
            v14 = HashTable<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::AddItem(v50, v54, a4);
        }
      }
      TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::~TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>(&v56);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000efa0  mov     [rsp+arg_10], rbx
0x18000efa5  push    rbp
0x18000efa6  push    rsi
0x18000efa7  push    rdi
0x18000efa8  push    r12
0x18000efaa  push    r13
0x18000efac  push    r14
0x18000efae  push    r15
0x18000efb0  sub     rsp, 50h
0x18000efb4  mov     rax, [rcx+50h]
0x18000efb8  mov     rsi, r9
0x18000efbb  mov     r13, [r8]
0x18000efbe  mov     r12, r8
0x18000efc1  mov     r15d, edx
0x18000efc4  mov     rbp, rcx
0x18000efc7  mov     [rsp+88h+var_50], r15d
0x18000efcc  test    byte ptr [rax+48h], 1
0x18000efd0  mov     [rsp+88h+var_48], r13
0x18000efd5  jnz     loc_18000F3F9
0x18000efdb  mov     ecx, 38h ; '8'; unsigned __int64
0x18000efe0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18000efe5  xor     edi, edi
0x18000efe7  test    rax, rax
0x18000efea  jz      loc_18000F240
0x18000eff0  mov     rcx, rax; this
0x18000eff3  call    ??0RangeSet@@QEAA@XZ; RangeSet::RangeSet(void)
0x18000eff8  mov     rsi, rax
0x18000effb  neg     rax
0x18000effe  sbb     ebx, ebx
0x18000f000  not     ebx
0x18000f002  and     ebx, 8007000Eh
0x18000f008  test    rsi, rsi
0x18000f00b  jz      loc_18000F19A
0x18000f011  mov     rax, [rbp+48h]
0x18000f015  test    r15d, r15d
0x18000f018  jz      loc_18000F1B4
0x18000f01e  mov     rax, [rax+20h]
0x18000f022  lea     rdx, [rax+r15*8]
0x18000f026  mov     rdx, [rdx]
0x18000f029  mov     r9, rbp
0x18000f02c  mov     r8, r12
0x18000f02f  mov     [rsp+88h+var_68], rdi
0x18000f034  mov     rcx, rsi
0x18000f037  call    ?InitializeByMergingWithCoreFragment@RangeSet@@QEAAJAEBV1@AEAV?$SharedRefPtr@UICoreFragment@@@@AEAVMergeContext@@PEAVSyncIdCache@@@Z; RangeSet::InitializeByMergingWithCoreFragment(RangeSet const &,SharedRefPtr<ICoreFragment> &,MergeContext &,SyncIdCache *)
0x18000f03c  mov     ebx, eax
0x18000f03e  test    eax, eax
0x18000f040  jnz     loc_18000F190
0x18000f046  mov     r14, [rbp+50h]
0x18000f04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f051  lea     r12, WPP_GLOBAL_Control
0x18000f058  cmp     rcx, r12
0x18000f05b  jz      short loc_18000F067
0x18000f05d  test    byte ptr [rcx+1Ch], 1
0x18000f061  jnz     loc_18000F24A
0x18000f067  lea     rcx, [r14+28h]
0x18000f06b  mov     [r14+10h], edi
0x18000f06f  mov     dword ptr [r14+18h], 1
0x18000f077  call    ?FreeHashTable@?$HashTable@V?$SharedRefPtr@VRangeSet@@@@KVSimpleHashTableContext@@@@AEAAXXZ; HashTable<SharedRefPtr<RangeSet>,ulong,SimpleHashTableContext>::FreeHashTable(void)
0x18000f07c  mov     ecx, 1; unsigned int
0x18000f081  call    ?GetNextPrimeNumber@@YAKK@Z; GetNextPrimeNumber(ulong)
0x18000f086  mov     [r14+28h], eax
0x18000f08a  lea     rax, [rsp+88h+var_58]
0x18000f08f  or      dword ptr [r14+48h], 1
0x18000f094  add     r14, 8
0x18000f098  cmp     r14, rax
0x18000f09b  jz      short loc_18000F0AC
0x18000f09d  cmp     [r14], rdi
0x18000f0a0  jnz     loc_18000F3C8
0x18000f0a6  mov     [r14], rsi
0x18000f0a9  inc     dword ptr [rsi+4]
0x18000f0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0b3  cmp     rcx, r12
0x18000f0b6  jz      short loc_18000F0C2
0x18000f0b8  test    byte ptr [rcx+1Ch], 1
0x18000f0bc  jnz     loc_18000F275
0x18000f0c2  movzx   r14d, r15w
0x18000f0c6  mov     eax, r15d
0x18000f0c9  shl     r14d, 10h
0x18000f0cd  add     rbp, 0A0h
0x18000f0d4  shr     eax, 10h
0x18000f0d7  mov     r8d, edi
0x18000f0da  or      r14d, eax
0x18000f0dd  mov     [rsp+88h+arg_0], r13
0x18000f0e5  mov     edx, edi
0x18000f0e7  movsxd  rax, edx
0x18000f0ea  inc     edx
0x18000f0ec  movzx   ecx, word ptr [rsp+rax*4+88h+arg_0]
0x18000f0f4  movzx   eax, word ptr [rsp+rax*4+88h+arg_0+2]
0x18000f0fc  shl     ecx, 10h
0x18000f0ff  or      ecx, eax
0x18000f101  xor     r8d, ecx
0x18000f104  cmp     edx, 2
0x18000f107  jb      short loc_18000F0E7
0x18000f109  xor     r14d, r8d
0x18000f10c  mov     r8, [rbp+8]
0x18000f110  test    r8, r8
0x18000f113  jnz     loc_18000F1BD
0x18000f119  mov     ebx, [rbp+0]
0x18000f11c  lea     rcx, [r8-1]
0x18000f120  lea     eax, [r8+20h]
0x18000f124  mul     rbx
0x18000f127  cmovb   rax, rcx
0x18000f12b  add     rax, 8
0x18000f12f  cmovb   rax, rcx
0x18000f133  mov     rcx, cs:hHeap; hHeap
0x18000f13a  mov     r8, rax; dwBytes
0x18000f13d  xor     edx, edx; dwFlags
0x18000f13f  call    cs:__imp_HeapAlloc
0x18000f145  test    rax, rax
0x18000f148  jz      loc_18000F2A4
0x18000f14e  mov     [rax], rbx
0x18000f151  lea     r12, [rax+8]
0x18000f155  mov     r13, r12
0x18000f158  test    rbx, rbx
0x18000f15b  jz      short loc_18000F16F
0x18000f15d  mov     rcx, r13
0x18000f160  call    ??0?$TableBucket@U?$Tuple@KPEAX@@KVDefaultHashTableContext@@@@QEAA@XZ; TableBucket<Tuple<ulong,void *>,ulong,DefaultHashTableContext>::TableBucket<Tuple<ulong,void *>,ulong,DefaultHashTableContext>(void)
0x18000f165  add     r13, 20h ; ' '
0x18000f169  sub     rbx, 1
0x18000f16d  jnz     short loc_18000F15D
0x18000f16f  mov     r13, [rsp+88h+var_48]
0x18000f174  test    r12, r12
0x18000f177  mov     [rbp+8], r12
0x18000f17b  mov     ebx, 8007000Eh
0x18000f180  cmovnz  ebx, edi
0x18000f183  test    ebx, ebx
0x18000f185  jns     loc_18000F2CA
0x18000f18b  test    rsi, rsi
0x18000f18e  jz      short loc_18000F19A
0x18000f190  add     dword ptr [rsi+4], 0FFFFFFFFh
0x18000f194  jz      loc_18000F22A
0x18000f19a  mov     eax, ebx
0x18000f19c  mov     rbx, [rsp+88h+arg_10]
0x18000f1a4  add     rsp, 50h
0x18000f1a8  pop     r15
0x18000f1aa  pop     r14
0x18000f1ac  pop     r13
0x18000f1ae  pop     r12
0x18000f1b0  pop     rdi
0x18000f1b1  pop     rsi
0x18000f1b2  pop     rbp
0x18000f1b3  retn
0x18000f1b4  lea     rdx, [rax+8]
0x18000f1b8  jmp     loc_18000F026
0x18000f1bd  mov     r11d, [rbp+0]
0x18000f1c1  mov     eax, r14d
0x18000f1c4  shr     eax, 5
0x18000f1c7  xor     edx, edx
0x18000f1c9  inc     eax
0x18000f1cb  mov     r9d, r14d
0x18000f1ce  mov     r10d, edi
0x18000f1d1  lea     ecx, [r11-1]
0x18000f1d5  div     ecx
0x18000f1d7  lea     ebx, [rdx+1]
0x18000f1da  cmp     r10d, r11d
0x18000f1dd  jnb     loc_18000F2AC
0x18000f1e3  xor     edx, edx
0x18000f1e5  mov     rax, r9
0x18000f1e8  div     r11
0x18000f1eb  mov     rax, rdx
0x18000f1ee  mov     r9, rdx
0x18000f1f1  shl     rax, 5
0x18000f1f5  test    byte ptr [rax+r8+18h], 1
0x18000f1fb  jz      short loc_18000F214
0x18000f1fd  cmp     [rax+r8], r15d
0x18000f201  jnz     short loc_18000F220
0x18000f203  cmp     [rax+r8+8], r13
0x18000f208  jnz     short loc_18000F220
0x18000f20a  mov     ebx, 80070057h
0x18000f20f  jmp     loc_18000F18B
0x18000f214  test    byte ptr [rax+r8+18h], 2
0x18000f21a  jz      loc_18000F2AC
0x18000f220  mov     eax, ebx
0x18000f222  add     r9, rax
0x18000f225  inc     r10d
0x18000f228  jmp     short loc_18000F1DA
0x18000f22a  lea     rcx, [rsi+8]
0x18000f22e  call    ??1?$Vector@URange@@$00@@QEAA@XZ; Vector<Range,1>::~Vector<Range,1>(void)
0x18000f233  mov     rcx, rsi; void *
0x18000f236  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18000f23b  jmp     loc_18000F19A
0x18000f240  mov     ebx, 8007000Eh
0x18000f245  jmp     loc_18000F19A
0x18000f24a  cmp     byte ptr [rcx+19h], 5
0x18000f24e  jb      loc_18000F067
0x18000f254  mov     rcx, [rcx+10h]
0x18000f258  lea     r9, aRangesetmanage_5; "RangeSetManager::InitializeWithScopeRan"...
0x18000f25f  mov     edx, 0Ah
0x18000f264  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000f26b  call    WPP_SF_s
0x18000f270  jmp     loc_18000F067
0x18000f275  cmp     byte ptr [rcx+19h], 5
0x18000f279  jb      loc_18000F0C2
0x18000f27f  mov     rcx, [rcx+10h]
0x18000f283  lea     r9, aRangesetmanage_5; "RangeSetManager::InitializeWithScopeRan"...
0x18000f28a  mov     edx, 0Bh
0x18000f28f  mov     dword ptr [rsp+88h+var_68], edi
0x18000f293  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000f29a  call    WPP_SF_sD
0x18000f29f  jmp     loc_18000F0C2
0x18000f2a4  mov     r12, rdi
0x18000f2a7  jmp     loc_18000F174
0x18000f2ac  lea     ecx, [r11+r11*8]
0x18000f2b0  mov     eax, 51EB851Fh
0x18000f2b5  shl     ecx, 3
0x18000f2b8  mul     ecx
0x18000f2ba  mov     eax, [rbp+10h]
0x18000f2bd  shr     edx, 5
0x18000f2c0  inc     eax
0x18000f2c2  cmp     eax, edx
0x18000f2c4  ja      loc_18000F3D5
0x18000f2ca  mov     r9d, [rbp+0]
0x18000f2ce  mov     eax, r14d
0x18000f2d1  mov     r11, [rbp+8]
0x18000f2d5  xor     edx, edx
0x18000f2d7  shr     eax, 5
0x18000f2da  mov     r8d, edi
0x18000f2dd  inc     eax
0x18000f2df  lea     ecx, [r9-1]
0x18000f2e3  div     ecx
0x18000f2e5  mov     eax, r14d
0x18000f2e8  lea     r10d, [rdx+1]
0x18000f2ec  cmp     r8d, r9d
0x18000f2ef  jnb     loc_18000F3EF
0x18000f2f5  xor     edx, edx
0x18000f2f7  div     r9
0x18000f2fa  mov     rcx, rdx
0x18000f2fd  shl     rcx, 5
0x18000f301  mov     al, [rcx+r11+18h]
0x18000f306  test    al, 1
0x18000f308  jnz     short loc_18000F338
0x18000f30a  mov     rcx, [rbp+8]
0x18000f30e  mov     ebx, edi
0x18000f310  mov     eax, [rsp+88h+var_4C]
0x18000f314  mov     edx, edx
0x18000f316  shl     rdx, 5
0x18000f31a  or      byte ptr [rdx+rcx+18h], 1
0x18000f31f  mov     [rdx+rcx], r15d
0x18000f323  mov     [rdx+rcx+4], eax
0x18000f327  mov     [rdx+rcx+8], r13
0x18000f32c  mov     [rdx+rcx+10h], edi
0x18000f330  inc     dword ptr [rbp+10h]
0x18000f333  jmp     loc_18000F18B
0x18000f338  or      al, 2
0x18000f33a  mov     [rcx+r11+18h], al
0x18000f33f  mov     eax, r10d
0x18000f342  add     rax, rdx
0x18000f345  inc     r8d
0x18000f348  jmp     short loc_18000F2EC
0x18000f34a  mov     rax, [rbp+48h]
0x18000f34e  test    r15d, r15d
0x18000f351  jz      short loc_18000F3C2
0x18000f353  mov     rax, [rax+20h]
0x18000f357  lea     rdx, [rax+r15*8]
0x18000f35b  mov     rax, [rsp+88h+arg_20]
0x18000f363  mov     r9, rbp
0x18000f366  mov     rdx, [rdx]
0x18000f369  mov     r8, r12
0x18000f36c  mov     rcx, [rsp+88h+arg_0]
0x18000f374  mov     [rsp+88h+var_68], rax
0x18000f379  call    ?InitializeByMergingWithCoreFragment@RangeSet@@QEAAJAEBV1@AEAV?$SharedRefPtr@UICoreFragment@@@@AEAVMergeContext@@PEAVSyncIdCache@@@Z; RangeSet::InitializeByMergingWithCoreFragment(RangeSet const &,SharedRefPtr<ICoreFragment> &,MergeContext &,SyncIdCache *)
0x18000f37e  mov     ebx, eax
0x18000f380  test    eax, eax
0x18000f382  jnz     short loc_18000F3B0
0x18000f384  mov     rcx, [rbp+50h]
0x18000f388  lea     rdx, [rsp+88h+arg_0]
0x18000f390  mov     r8, rsi
0x18000f393  call    ?FindByKeyOrAdd@RangeSetManager@@QEAAJAEBV?$SharedRefPtr@VRangeSet@@@@AEAK@Z; RangeSetManager::FindByKeyOrAdd(SharedRefPtr<RangeSet> const &,ulong &)
0x18000f398  mov     ebx, eax
0x18000f39a  test    eax, eax
0x18000f39c  jnz     short loc_18000F3B0
0x18000f39e  mov     r8, rsi
0x18000f3a1  lea     rdx, [rsp+88h+var_50]
0x18000f3a6  mov     rcx, r14
0x18000f3a9  call    ?AddItem@?$HashTable@U?$Tuple@KPEAX@@KVDefaultHashTableContext@@@@QEAAJAEBU?$Tuple@KPEAX@@AEBK@Z; HashTable<Tuple<ulong,void *>,ulong,DefaultHashTableContext>::AddItem(Tuple<ulong,void *> const &,ulong const &)
0x18000f3ae  mov     ebx, eax
0x18000f3b0  lea     rcx, [rsp+88h+arg_0]; void *
0x18000f3b8  call    ??1?$TableBucket@V?$SharedRefPtr@VRangeSet@@@@KVSimpleHashTableContext@@@@QEAA@XZ; TableBucket<SharedRefPtr<RangeSet>,ulong,SimpleHashTableContext>::~TableBucket<SharedRefPtr<RangeSet>,ulong,SimpleHashTableContext>(void)
0x18000f3bd  jmp     loc_18000F19A
0x18000f3c2  lea     rdx, [rax+8]
0x18000f3c6  jmp     short loc_18000F35B
0x18000f3c8  mov     rcx, [r14]; this
0x18000f3cb  call    ?Release@RangeSet@@QEAAKXZ; RangeSet::Release(void)
0x18000f3d0  jmp     loc_18000F0A6
0x18000f3d5  lea     ecx, [r11+r11]; unsigned int
0x18000f3d9  call    ?GetNextPrimeNumber@@YAKK@Z; GetNextPrimeNumber(ulong)
0x18000f3de  mov     edx, eax
0x18000f3e0  mov     rcx, rbp
0x18000f3e3  call    ?Resize@?$HashTable@U?$Tuple@KPEAX@@KVDefaultHashTableContext@@@@AEAAJK@Z; HashTable<Tuple<ulong,void *>,ulong,DefaultHashTableContext>::Resize(ulong)
0x18000f3e8  mov     ebx, eax
0x18000f3ea  jmp     loc_18000F183
0x18000f3ef  mov     ebx, 8000FFFFh
0x18000f3f4  jmp     loc_18000F18B
0x18000f3f9  lea     r14, [rcx+0A0h]
0x18000f400  xor     edi, edi
0x18000f402  mov     rcx, r14
0x18000f405  lea     rdx, [rsp+88h+var_50]
0x18000f40a  mov     r8, rsi
0x18000f40d  mov     ebx, edi
0x18000f40f  call    ?LookupItem@?$HashTable@U?$Tuple@KPEAX@@KVDefaultHashTableContext@@@@QEBA_NAEBU?$Tuple@KPEAX@@AEAK@Z; HashTable<Tuple<ulong,void *>,ulong,DefaultHashTableContext>::LookupItem(Tuple<ulong,void *> const &,ulong &)
  ... truncated ...
```
