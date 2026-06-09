# FindCacheMatch

- ea: `0x140002390`
- end: `0x140002722`
- name: `FindCacheMatch`
- size: `914`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400016d0`
- `0x14000418c`

## callees

- `0x140002390`
- `0x140002730`
- `0x140002750`
- `0x140002900`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400026f1`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400026f1`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000250e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000250e`

## string_xrefs

- `0x1400025cf`: `FindCacheMatch`

## pseudocode

```c
__int64 __fastcall FindCacheMatch(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PRTL_DYNAMIC_HASH_TABLE_ENTRY *a5,
        _BYTE *a6)
{
  __int64 v6; // r15
  __int64 v7; // rsi
  __int64 v8; // r9
  unsigned int v10; // r12d
  unsigned int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 i; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  bool v17; // zf
  ULONG_PTR v18; // rdi
  int v19; // ebp
  int v20; // r14d
  struct _RTL_DYNAMIC_HASH_TABLE *v21; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY k; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v23; // rbx
  __int64 v24; // rbx
  PDEVICE_OBJECT v25; // rcx
  bool v26; // zf
  unsigned int v28; // esi
  __int64 v29; // rbx
  unsigned int v30; // edi
  __int64 v31; // rsi
  __int64 j; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-74h]
  __int64 v38; // [rsp+48h] [rbp-70h] BYREF
  __int64 v39; // [rsp+50h] [rbp-68h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+58h] [rbp-60h] BYREF
  __int64 v41; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v42; // [rsp+C8h] [rbp+10h]
  int v43; // [rsp+D0h] [rbp+18h]
  __int64 v44; // [rsp+D8h] [rbp+20h]

  v44 = a4;
  v42 = a2;
  v38 = 0;
  v6 = 0;
  v41 = 0;
  v7 = a4;
  v8 = a2;
  memset(&Context, 0, sizeof(Context));
  if ( !a3 || (v43 = 1, GetEpochCacheContextFromMetadata(a3, &v41, a3), (v6 = v41) == 0) )
    v43 = 0;
  v10 = *(_DWORD *)(a1 + 36);
  if ( *(_DWORD *)(a1 + 32) == 4 )
  {
    v11 = *(_DWORD *)(v7 + 24);
    v12 = 0;
    v13 = HIBYTE(v10);
    for ( i = 0; (unsigned int)i < v11; v12 = v15 + 37 * v12 )
    {
      v15 = *(unsigned __int8 *)(i + *(_QWORD *)(v7 + 32));
      i = (unsigned int)(i + 1);
    }
    _mm_lfence();
    v16 = 37
        * (BYTE2(v10)
         + 37
         * (BYTE1(v10)
          + 37
          * ((unsigned __int8)v10
           + 37
           * (*(unsigned __int8 *)(v7 + 19)
            + 37
            * (*(unsigned __int8 *)(v7 + 18)
             + 37
             * (*(unsigned __int8 *)(v7 + 17)
              + 37
              * (*(unsigned __int8 *)(v7 + 16)
               + 37
               * (*(unsigned __int8 *)(v7 + 15)
                + 37
                * (*(unsigned __int8 *)(v7 + 14)
                 + 37 * (*(unsigned __int8 *)(v7 + 13) + 37 * (37 * v12 + *(unsigned __int8 *)(v7 + 12))))))))))));
    v17 = v16 + v13 == 0;
    v18 = v16 + v13;
  }
  else
  {
    LODWORD(v41) = 0;
    v28 = HIBYTE(v10);
    v29 = 0;
    v30 = 0;
    v37 = HIBYTE(v10);
    v39 = 0;
    v36 = 0;
    if ( *(_DWORD *)(v8 + 160) )
    {
      v31 = v42;
      do
      {
        GetValueInfo(*(int **)(v31 + 16LL * v30 + 8), &v39, &v41, &v36);
        for ( j = 0; (unsigned int)j < (unsigned int)v41; v29 = v33 + 37 * v29 )
        {
          v33 = *(unsigned __int8 *)(j + v39);
          j = (unsigned int)(j + 1);
        }
        ++v30;
      }
      while ( v30 < *(_DWORD *)(v31 + 160) );
      v28 = v37;
    }
    v34 = BYTE2(v10) + 37 * (BYTE1(v10) + 37 * ((unsigned __int8)v10 + 37 * v29));
    v35 = v28;
    v7 = v44;
    v17 = v35 + 37 * v34 == 0;
    v18 = v35 + 37 * v34;
  }
  if ( v17 )
    v18 = -1;
  _mm_lfence();
  v19 = v42;
  v20 = v43;
LABEL_11:
  v21 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
  memset(&Context, 0, sizeof(Context));
  for ( k = RtlLookupEntryHashTable(v21, v18, &Context);
        ;
        k = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Context) )
  {
    v23 = k;
    if ( !k )
    {
      if ( v20 )
      {
        v20 = 0;
        goto LABEL_11;
      }
      v24 = v38;
      *a6 = 0;
      if ( !v24 )
        return v24;
      v25 = WPP_GLOBAL_Control;
      v26 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
      goto LABEL_20;
    }
    if ( (unsigned __int8)IsMatchingEntry(a1, v19, v6, v20, (__int64)k, v7, (__int64)&v38) )
      break;
  }
  *a5 = v23;
  *a6 = 1;
  if ( v6 && *(_QWORD *)(v6 + 8) != -1 )
    *(_QWORD *)(v6 + 8) = v23[2].Linkage.Blink;
  v24 = v38;
  if ( v38 )
  {
    v25 = WPP_GLOBAL_Control;
    v26 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_20:
    if ( !v26 && BYTE1(v25->Timer) >= 2u && (HIDWORD(v25->Timer) & 0x1000) != 0 )
      WPP_SF_sd(
        v25->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"FindCacheMatch",
        v24);
  }
  return v24;
}

```

## disassembly

```asm
0x140002390  mov     r11, rsp
0x140002393  mov     [r11+20h], r9
0x140002397  mov     [r11+10h], rdx
0x14000239b  push    rbx
0x14000239c  push    rbp
0x14000239d  push    rsi
0x14000239e  push    rdi
0x14000239f  push    r12
0x1400023a1  push    r13
0x1400023a3  push    r14
0x1400023a5  push    r15
0x1400023a7  sub     rsp, 78h
0x1400023ab  xor     eax, eax
0x1400023ad  mov     qword ptr [r11-70h], 0
0x1400023b5  xor     r15d, r15d
0x1400023b8  xorps   xmm0, xmm0
0x1400023bb  mov     [r11+8], r15
0x1400023bf  mov     rsi, r9
0x1400023c2  mov     r9, rdx
0x1400023c5  mov     r13, rcx
0x1400023c8  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x1400023cd  mov     [r11-50h], rax
0x1400023d1  test    r8, r8
0x1400023d4  jz      short loc_1400023FA
0x1400023d6  lea     rdx, [r11+8]
0x1400023da  mov     [rsp+0B8h+arg_10], 1
0x1400023e5  mov     rcx, r8
0x1400023e8  call    GetEpochCacheContextFromMetadata
0x1400023ed  mov     r15, [rsp+0B8h+arg_0]
0x1400023f5  test    r15, r15
0x1400023f8  jnz     short loc_140002405
0x1400023fa  mov     [rsp+0B8h+arg_10], 0
0x140002405  cmp     dword ptr [r13+20h], 4
0x14000240a  mov     r12d, [r13+24h]
0x14000240e  jnz     loc_140002600
0x140002414  mov     r9d, [rsi+18h]
0x140002418  mov     r11d, r12d
0x14000241b  mov     r10, [rsi+20h]
0x14000241f  mov     ebx, r12d
0x140002422  mov     edi, r12d
0x140002425  shr     r11d, 8
0x140002429  shr     ebx, 10h
0x14000242c  xor     eax, eax
0x14000242e  shr     edi, 18h
0x140002431  xor     ecx, ecx
0x140002433  test    r9d, r9d
0x140002436  jz      short loc_140002453
0x140002438  nop     dword ptr [rax+rax+00000000h]
0x140002440  movzx   r8d, byte ptr [rcx+r10]
0x140002445  inc     ecx
0x140002447  imul    rax, 25h ; '%'
0x14000244b  add     rax, r8
0x14000244e  cmp     ecx, r9d
0x140002451  jb      short loc_140002440
0x140002453  lfence
0x140002456  movzx   edx, byte ptr [rsi+0Ch]
0x14000245a  imul    rcx, rax, 25h ; '%'
0x14000245e  movzx   eax, byte ptr [rsi+0Dh]
0x140002462  add     rdx, rcx
0x140002465  imul    rcx, rdx, 25h ; '%'
0x140002469  add     rcx, rax
0x14000246c  movzx   eax, byte ptr [rsi+0Eh]
0x140002470  imul    rdx, rcx, 25h ; '%'
0x140002474  add     rdx, rax
0x140002477  movzx   eax, byte ptr [rsi+0Fh]
0x14000247b  imul    rcx, rdx, 25h ; '%'
0x14000247f  add     rcx, rax
0x140002482  movzx   eax, byte ptr [rsi+10h]
0x140002486  imul    rdx, rcx, 25h ; '%'
0x14000248a  add     rdx, rax
0x14000248d  movzx   eax, byte ptr [rsi+11h]
0x140002491  imul    rcx, rdx, 25h ; '%'
0x140002495  add     rcx, rax
0x140002498  movzx   eax, byte ptr [rsi+12h]
0x14000249c  imul    rdx, rcx, 25h ; '%'
0x1400024a0  add     rdx, rax
0x1400024a3  movzx   eax, byte ptr [rsi+13h]
0x1400024a7  imul    rdx, 25h ; '%'
0x1400024ab  add     rdx, rax
0x1400024ae  movzx   eax, r12b
0x1400024b2  imul    rcx, rdx, 25h ; '%'
0x1400024b6  add     rcx, rax
0x1400024b9  movzx   eax, r11b
0x1400024bd  imul    rdx, rcx, 25h ; '%'
0x1400024c1  add     rdx, rax
0x1400024c4  movzx   eax, bl
0x1400024c7  imul    rcx, rdx, 25h ; '%'
0x1400024cb  add     rcx, rax
0x1400024ce  imul    rcx, 25h ; '%'
0x1400024d2  add     rdi, rcx
0x1400024d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400024dc  cmovz   rdi, rax
0x1400024e0  lfence
0x1400024e3  mov     rbp, [rsp+0B8h+arg_8]
0x1400024eb  mov     r14d, [rsp+0B8h+arg_10]
0x1400024f3  mov     rcx, [r13+8]; HashTable
0x1400024f7  lea     r8, [rsp+0B8h+Context]; Context
0x1400024fc  xorps   xmm0, xmm0
0x1400024ff  xor     eax, eax
0x140002501  mov     rdx, rdi; Signature
0x140002504  mov     [rsp+0B8h+Context.Signature], rax
0x140002509  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x14000250e  call    cs:__imp_RtlLookupEntryHashTable
0x140002515  nop     dword ptr [rax+rax+00h]
0x14000251a  mov     rbx, rax
0x14000251d  test    rax, rax
0x140002520  jz      short loc_14000258B
0x140002522  lea     rax, [rsp+0B8h+var_70]
0x140002527  mov     r9d, r14d
0x14000252a  mov     [rsp+0B8h+var_88], rax
0x14000252f  mov     r8, r15
0x140002532  mov     [rsp+0B8h+var_90], rsi
0x140002537  mov     rdx, rbp
0x14000253a  mov     rcx, r13
0x14000253d  mov     [rsp+0B8h+var_98], rbx
0x140002542  call    IsMatchingEntry
0x140002547  test    al, al
0x140002549  jz      loc_1400026E8
0x14000254f  mov     rax, [rsp+0B8h+arg_20]
0x140002557  mov     [rax], rbx
0x14000255a  mov     rax, [rsp+0B8h+arg_28]
0x140002562  mov     byte ptr [rax], 1
0x140002565  test    r15, r15
0x140002568  jnz     loc_14000270A
0x14000256e  mov     rbx, [rsp+0B8h+var_70]
0x140002573  test    rbx, rbx
0x140002576  jz      short loc_1400025EB
0x140002578  mov     rcx, cs:WPP_GLOBAL_Control
0x14000257f  lea     rax, WPP_GLOBAL_Control
0x140002586  cmp     rcx, rax
0x140002589  jmp     short loc_1400025BA
0x14000258b  test    r14d, r14d
0x14000258e  jnz     loc_140002702
0x140002594  mov     rax, [rsp+0B8h+arg_28]
0x14000259c  mov     rbx, [rsp+0B8h+var_70]
0x1400025a1  mov     [rax], r14b
0x1400025a4  test    rbx, rbx
0x1400025a7  jz      short loc_1400025EB
0x1400025a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025b0  lea     rax, WPP_GLOBAL_Control
0x1400025b7  cmp     rcx, rax
0x1400025ba  jz      short loc_1400025EB
0x1400025bc  cmp     byte ptr [rcx+29h], 2
0x1400025c0  jb      short loc_1400025EB
0x1400025c2  test    dword ptr [rcx+2Ch], 1000h
0x1400025c9  jz      short loc_1400025EB
0x1400025cb  mov     rcx, [rcx+18h]
0x1400025cf  lea     r9, aFindcachematch; "FindCacheMatch"
0x1400025d6  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400025dd  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1400025e1  mov     edx, 0Fh
0x1400025e6  call    WPP_SF_sd
0x1400025eb  mov     rax, rbx
0x1400025ee  add     rsp, 78h
0x1400025f2  pop     r15
0x1400025f4  pop     r14
0x1400025f6  pop     r13
0x1400025f8  pop     r12
0x1400025fa  pop     rdi
0x1400025fb  pop     rsi
0x1400025fc  pop     rbp
0x1400025fd  pop     rbx
0x1400025fe  retn
0x140002600  mov     esi, r12d
0x140002603  mov     dword ptr [rsp+0B8h+arg_0], 0
0x14000260e  shr     esi, 18h
0x140002611  mov     ebp, r12d
0x140002614  mov     r14d, r12d
0x140002617  shr     ebp, 8
0x14000261a  shr     r14d, 10h
0x14000261e  xor     ebx, ebx
0x140002620  xor     edi, edi
0x140002622  mov     [rsp+0B8h+var_74], esi
0x140002626  mov     [rsp+0B8h+var_68], 0
0x14000262f  mov     [rsp+0B8h+var_78], 0
0x140002637  cmp     [r9+0A0h], ebx
0x14000263e  jbe     short loc_1400026B1
0x140002640  mov     rsi, [rsp+0B8h+arg_8]
0x140002648  nop     dword ptr [rax+rax+00000000h]
0x140002650  mov     ecx, edi
0x140002652  lea     r9, [rsp+0B8h+var_78]
0x140002657  add     rcx, rcx
0x14000265a  lea     r8, [rsp+0B8h+arg_0]
0x140002662  lea     rdx, [rsp+0B8h+var_68]
0x140002667  mov     rcx, [rsi+rcx*8+8]
0x14000266c  call    GetValueInfo
0x140002671  mov     r8d, dword ptr [rsp+0B8h+arg_0]
0x140002679  xor     edx, edx
0x14000267b  mov     r9, [rsp+0B8h+var_68]
0x140002680  test    r8d, r8d
0x140002683  jz      short loc_1400026A3
0x140002685  nop     word ptr [rax+rax+00000000h]
0x140002690  movzx   ecx, byte ptr [rdx+r9]
0x140002695  inc     edx
0x140002697  imul    rbx, 25h ; '%'
0x14000269b  add     rbx, rcx
0x14000269e  cmp     edx, r8d
0x1400026a1  jb      short loc_140002690
0x1400026a3  inc     edi
0x1400026a5  cmp     edi, [rsi+0A0h]
0x1400026ab  jb      short loc_140002650
0x1400026ad  mov     esi, [rsp+0B8h+var_74]
0x1400026b1  imul    rcx, rbx, 25h ; '%'
0x1400026b5  movzx   eax, r12b
0x1400026b9  add     rcx, rax
0x1400026bc  movzx   eax, bpl
0x1400026c0  imul    rdx, rcx, 25h ; '%'
0x1400026c4  add     rdx, rax
0x1400026c7  movzx   eax, r14b
0x1400026cb  imul    rcx, rdx, 25h ; '%'
0x1400026cf  add     rcx, rax
0x1400026d2  mov     eax, esi
0x1400026d4  mov     rsi, [rsp+0B8h+arg_18]
0x1400026dc  imul    rdi, rcx, 25h ; '%'
0x1400026e0  add     rdi, rax
0x1400026e3  jmp     loc_1400024D5
0x1400026e8  mov     rcx, [r13+8]; HashTable
0x1400026ec  lea     rdx, [rsp+0B8h+Context]; Context
0x1400026f1  call    cs:__imp_RtlGetNextEntryHashTable
0x1400026f8  nop     dword ptr [rax+rax+00h]
0x1400026fd  jmp     loc_14000251A
0x140002702  xor     r14d, r14d
0x140002705  jmp     loc_1400024F3
0x14000270a  cmp     qword ptr [r15+8], 0FFFFFFFFFFFFFFFFh
0x14000270f  jz      loc_14000256E
0x140002715  mov     rax, [rbx+38h]
0x140002719  mov     [r15+8], rax
0x14000271d  jmp     loc_14000256E
```
