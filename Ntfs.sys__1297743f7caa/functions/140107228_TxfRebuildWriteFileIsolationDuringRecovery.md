# TxfRebuildWriteFileIsolationDuringRecovery

- ea: `0x140107228`
- end: `0x1401077d4`
- name: `TxfRebuildWriteFileIsolationDuringRecovery`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1401032b0`

## callees

- `0x14000cb00`
- `0x1400592c0`
- `0x140059740`
- `0x14010038c`
- `0x140100e88`
- `0x140107228`
- `0x140294b6c`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1401073eb`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140107664`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1401073eb`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140107664`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401077b7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401077b7`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x1401073ac`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x1401073ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140107483`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5497`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140107483`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5497`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401072ff`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401072ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x140107350`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010743a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5426`
- `ntoskrnl!ExReleaseResourceLite` at `0x140107350`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010743a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5426`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010736b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010736b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140107466`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c547a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140107466`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c547a`

## pseudocode

```c
__int64 __fastcall TxfRebuildWriteFileIsolationDuringRecovery(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v8; // rsi
  __int64 v9; // r15
  __int64 v10; // rdi
  ULONG i; // r9d
  __m128i *v12; // rax
  __int64 *v13; // rbx
  _BYTE *v14; // rax
  char v15; // cl
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // esi
  __m128i v21; // xmm6
  __m128i v22; // xmm7
  __m128i v23; // xmm8
  int v24; // r9d
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // edx
  _BYTE *inserted; // rax
  char v30; // cl
  __int64 v31; // r9
  __int64 v32; // r8
  unsigned int v33; // edi
  __int64 j; // rdx
  unsigned int v35; // ecx
  int RestartKey; // [rsp+20h] [rbp-268h]
  unsigned __int8 NewElement; // [rsp+41h] [rbp-247h] BYREF
  char v38; // [rsp+42h] [rbp-246h]
  unsigned int v39; // [rsp+44h] [rbp-244h]
  PVOID Entry; // [rsp+48h] [rbp-240h] BYREF
  __int64 v41; // [rsp+50h] [rbp-238h] BYREF
  ULONG DeleteCount; // [rsp+58h] [rbp-230h] BYREF
  __int64 v43; // [rsp+60h] [rbp-228h]
  PVOID v44; // [rsp+68h] [rbp-220h] BYREF
  __int64 v45; // [rsp+70h] [rbp-218h]
  __m128i *v46; // [rsp+78h] [rbp-210h]
  __int64 v47; // [rsp+80h] [rbp-208h]
  __m128i v48; // [rsp+88h] [rbp-200h]
  __m128i v49; // [rsp+98h] [rbp-1F0h]
  _BYTE v50[20]; // [rsp+A8h] [rbp-1E0h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-1C8h]
  unsigned int *v52; // [rsp+C8h] [rbp-1C0h]
  __m128i *v53; // [rsp+D0h] [rbp-1B8h]
  _QWORD v54[38]; // [rsp+E0h] [rbp-1A8h] BYREF

  v51 = a2;
  memset(v54, 0, 0x124u);
  v8 = *(_QWORD *)(a2 + 208);
  v43 = v8;
  DeleteCount = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v48 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  v38 = 0;
  NewElement = 0;
  v41 = 0;
  v47 = 0;
  Entry = ExAllocateFromLookasideListEx(&TxfTopsRangeEntryLookasideList);
  NtfsAcquireExclusiveScbEx(a1, a3, 0);
  TxfRebuildTxfStructuresForRecovery(a1, a3, a2, &v41);
  v47 = *(_QWORD *)(*(_QWORD *)(a3 + 528) + 56LL);
  v9 = v47;
  ExReleaseResourceLite(*(PERESOURCE *)(v41 + 136));
  v10 = 0;
  v41 = 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v9 + 256));
  v38 = 1;
  for ( i = 0; ; i = 1 )
  {
    v12 = (__m128i *)RtlEnumerateGenericTableLikeADirectory(
                       (PRTL_AVL_TABLE)(v9 + 152),
                       TxfMatchPageRange,
                       a4,
                       i,
                       &v44,
                       &DeleteCount,
                       a4);
    v13 = (__int64 *)v12;
    v46 = v12;
    if ( !v12 )
      break;
    v17 = *a4;
    v18 = v12->m128i_i64[0];
    if ( v12->m128i_i64[0] >= (unsigned __int64)*a4 )
    {
      v31 = *((unsigned int *)a4 + 6);
      v32 = v12->m128i_i64[1];
      if ( v17 + v31 >= v18 + (unsigned __int64)v12[1].m128i_u32[2] )
      {
        if ( v32 != a4[1] )
        {
          TxfInsertNewTopsRange(*(_QWORD *)(v8 + 16), v9, v32, v12[1].m128i_i32[2], (__int64)&Entry, 0);
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v9 + 152), v13);
        }
      }
      else
      {
        v33 = v31 + v17 - v18;
        TxfInsertNewTopsRange(*(_QWORD *)(v8 + 16), v9, v32, v33, (__int64)&Entry, 0);
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v39 = j;
          v35 = *((_DWORD *)v13 + 6) - v33;
          if ( (unsigned int)j >= 8 * v35 )
            break;
          *((_WORD *)&v54[4] + j + 2) = *((_WORD *)&v13[2 * v33 + 4] + (unsigned int)j + 2);
        }
        v13[1] += v33;
        *v13 += v33;
        *((_DWORD *)v13 + 6) = v35;
        *((_DWORD *)v13 + 8) -= v33 << 12;
      }
    }
    else
    {
      v19 = v12[1].m128i_u32[2];
      v52 = &v12[1].m128i_u32[2];
      v53 = v12 + 2;
      v20 = v17 - v18;
      if ( v17 + (unsigned __int64)*((unsigned int *)a4 + 6) >= v18 + v19 )
      {
        TxfInsertNewTopsRange(*(_QWORD *)(v43 + 16), v9, v12->m128i_i32[2] + v20, v19 - v20, (__int64)&Entry, 0);
        *v52 = v20;
        v53->m128i_i32[0] = v20 << 12;
        v8 = v43;
      }
      else
      {
        v48 = *v12;
        v21 = v48;
        v49 = v12[1];
        v22 = v49;
        *(__m128i *)v50 = v12[2];
        v23 = *(__m128i *)v50;
        v45 = v12[3].m128i_u32[0];
        *(_DWORD *)&v50[16] = v45;
        v12[1].m128i_i32[2] = v20;
        v12[2].m128i_i32[0] = v20 << 12;
        v54[0] = v21.m128i_i64[0];
        v54[1] = _mm_srli_si128(v21, 8).m128i_u64[0];
        v54[2] = v49.m128i_i64[0];
        v24 = _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
        LODWORD(v54[3]) = v24;
        HIDWORD(v54[3]) = _mm_srli_si128(v22, 8).m128i_i32[1];
        LODWORD(v54[4]) = _mm_cvtsi128_si32(v23);
        *(_OWORD *)((char *)&v54[4] + 4) = *(_OWORD *)&v50[4];
        v25 = *((unsigned int *)a4 + 6);
        v26 = v24 - v25 - v12[1].m128i_i32[2];
        LODWORD(v54[3]) = v26;
        LODWORD(v54[4]) = LODWORD(v54[4]) - ((_DWORD)v25 << 12) - (v12[1].m128i_i32[2] << 12);
        v54[0] = v25 + *a4;
        v54[1] = v12->m128i_i64[1] + v25 + v12[1].m128i_u32[2];
        v27 = v24 - v26;
        v28 = 0;
        v39 = 0;
        while ( v28 < 8 * v26 )
        {
          *((_WORD *)&v54[4] + v28 + 2) = v12[v27 + 2].m128i_i16[v28 + 2];
          v39 = ++v28;
          v26 = v54[3];
        }
        inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v9 + 152), v54, 16 * (v26 - 1) + 52, &NewElement);
        inserted[30] |= 1u;
        v30 = inserted[30] | 8;
        inserted[30] = v30;
        inserted[30] = v30 | 0x20;
        v8 = v43;
        TxfInsertNewTopsRange(
          *(_QWORD *)(v43 + 16),
          v9,
          *((_DWORD *)v13 + 2) + *((_DWORD *)v13 + 6),
          *((_DWORD *)a4 + 6),
          (__int64)&Entry,
          0);
      }
    }
    v10 = v41;
  }
  v44 = 0;
  v14 = RtlInsertElementGenericTableAvl(
          (PRTL_AVL_TABLE)(v9 + 152),
          a4,
          16 * (*((_DWORD *)a4 + 6) - 1) + 52,
          &NewElement);
  v14[30] |= 1u;
  v15 = v14[30] | 0x10;
  v14[30] = v15;
  v14[30] = v15 | 0x20;
  LOBYTE(RestartKey) = 0;
  TxfDirectlyAllocateTopsRange(*(_QWORD *)(v51 + 208), v9, *((_QWORD *)v14 + 1), *((unsigned int *)v14 + 6), RestartKey);
  if ( v10 )
    ExReleaseResourceLite(*(PERESOURCE *)(v10 + 136));
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v9 + 256));
  if ( Entry )
    ExFreeToLookasideListEx(&TxfTopsRangeEntryLookasideList, Entry);
  return 0;
}

```

## disassembly

```asm
0x140107228  mov     rax, rsp
0x14010722b  push    rbx
0x14010722c  push    rsi
0x14010722d  push    rdi
0x14010722e  push    r12
0x140107230  push    r13
0x140107232  push    r14
0x140107234  push    r15
0x140107236  sub     rsp, 250h
0x14010723d  movaps  xmmword ptr [rax-48h], xmm6
0x140107241  movaps  xmmword ptr [rax-58h], xmm7
0x140107245  movaps  xmmword ptr [rax-68h], xmm8
0x14010724a  mov     rax, cs:__security_cookie
0x140107251  xor     rax, rsp
0x140107254  mov     [rsp+288h+var_78], rax
0x14010725c  mov     r14, r9
0x14010725f  mov     rbx, r8
0x140107262  mov     r15, rdx
0x140107265  mov     [rsp+288h+var_1C8], rdx
0x14010726d  mov     rdi, rcx
0x140107270  xor     edx, edx; Val
0x140107272  mov     r8d, 124h; Size
0x140107278  lea     rcx, [rsp+288h+var_1A8]; void *
0x140107280  call    memset
0x140107285  mov     rsi, [r15+0D0h]
0x14010728c  mov     [rsp+288h+var_228], rsi
0x140107291  xor     r12d, r12d
0x140107294  mov     [rsp+288h+var_230], r12d
0x140107299  mov     [rsp+288h+var_220], r12
0x14010729e  mov     [rsp+288h+var_210], r12
0x1401072a3  xorps   xmm6, xmm6
0x1401072a6  xor     eax, eax
0x1401072a8  mov     [rsp+288h+var_218], rax
0x1401072ad  movups  [rsp+288h+var_200], xmm6
0x1401072b5  xorps   xmm7, xmm7
0x1401072b8  movups  [rsp+288h+var_1F0], xmm7
0x1401072c0  xorps   xmm8, xmm8
0x1401072c4  movups  [rsp+288h+var_1E0], xmm8
0x1401072cd  mov     [rsp+288h+var_1D0], eax
0x1401072d4  mov     [rsp+288h+var_246], r12b
0x1401072d9  mov     r13b, r12b
0x1401072dc  mov     [rsp+288h+var_248], r12b
0x1401072e1  mov     [rsp+288h+NewElement], r12b
0x1401072e6  mov     [rsp+288h+var_238], r12
0x1401072eb  mov     [rsp+288h+var_208], r12
0x1401072f3  mov     [rsp+288h+Entry], r12
0x1401072f8  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x1401072ff  call    cs:__imp_ExAllocateFromLookasideListEx
0x140107306  nop     dword ptr [rax+rax+00h]
0x14010730b  mov     [rsp+288h+Entry], rax
0x140107310  xor     r8d, r8d
0x140107313  mov     rdx, rbx
0x140107316  mov     rcx, rdi
0x140107319  call    NtfsAcquireExclusiveScbEx
0x14010731e  lea     r9, [rsp+288h+var_238]
0x140107323  mov     r8, r15
0x140107326  mov     rdx, rbx
0x140107329  mov     rcx, rdi
0x14010732c  call    TxfRebuildTxfStructuresForRecovery
0x140107331  mov     rax, [rbx+210h]
0x140107338  mov     r15, [rax+38h]
0x14010733c  mov     [rsp+288h+var_208], r15
0x140107344  mov     rcx, [rsp+288h+var_238]
0x140107349  mov     rcx, [rcx+88h]; Resource
0x140107350  call    cs:__imp_ExReleaseResourceLite
0x140107357  nop     dword ptr [rax+rax+00h]
0x14010735c  mov     edi, r12d
0x14010735f  mov     [rsp+288h+var_238], r12
0x140107364  mov     rcx, [r15+100h]; FastMutex
0x14010736b  call    cs:__imp_ExAcquireFastMutex
0x140107372  nop     dword ptr [rax+rax+00h]
0x140107377  mov     [rsp+288h+var_246], 1
0x14010737c  mov     r9d, r12d; NextFlag
0x14010737f  lea     r12, [r15+98h]
0x140107386  mov     [rsp+288h+Buffer], r14; Buffer
0x14010738b  lea     rax, [rsp+288h+var_230]
0x140107390  mov     [rsp+288h+DeleteCount], rax; DeleteCount
0x140107395  lea     rax, [rsp+288h+var_220]
0x14010739a  mov     [rsp+288h+RestartKey], rax; RestartKey
0x14010739f  mov     r8, r14; MatchData
0x1401073a2  lea     rdx, TxfMatchPageRange; MatchFunction
0x1401073a9  mov     rcx, r12; Table
0x1401073ac  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x1401073b3  nop     dword ptr [rax+rax+00h]
0x1401073b8  mov     rbx, rax
0x1401073bb  mov     [rsp+288h+var_210], rax
0x1401073c0  xor     r11d, r11d
0x1401073c3  test    rax, rax
0x1401073c6  jnz     loc_1401074C8
0x1401073cc  mov     [rsp+288h+var_220], r11
0x1401073d1  mov     r8d, [r14+18h]
0x1401073d5  dec     r8d
0x1401073d8  shl     r8d, 4
0x1401073dc  add     r8d, 34h ; '4'; BufferSize
0x1401073e0  lea     r9, [rsp+288h+NewElement]; NewElement
0x1401073e5  mov     rdx, r14; Buffer
0x1401073e8  mov     rcx, r12; Table
0x1401073eb  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1401073f2  nop     dword ptr [rax+rax+00h]
0x1401073f7  or      byte ptr [rax+1Eh], 1
0x1401073fb  mov     cl, [rax+1Eh]
0x1401073fe  or      cl, 10h
0x140107401  mov     [rax+1Eh], cl
0x140107404  or      cl, 20h
0x140107407  mov     [rax+1Eh], cl
0x14010740a  mov     byte ptr [rsp+288h+RestartKey], bl
0x14010740e  mov     r9d, [rax+18h]
0x140107412  mov     r8, [rax+8]
0x140107416  mov     rdx, r15
0x140107419  mov     rcx, [rsp+288h+var_1C8]
0x140107421  mov     rcx, [rcx+0D0h]
0x140107428  call    TxfDirectlyAllocateTopsRange
0x14010742d  nop
0x14010742e  test    rdi, rdi
0x140107431  jz      short loc_140107446
0x140107433  mov     rcx, [rdi+88h]; Resource
0x14010743a  call    cs:__imp_ExReleaseResourceLite
0x140107441  nop     dword ptr [rax+rax+00h]
0x140107446  test    r13b, r13b
0x140107449  jz      short loc_14010745F
0x14010744b  movups  xmmword ptr [rbx], xmm6
0x14010744e  movups  xmmword ptr [rbx+10h], xmm7
0x140107452  movups  xmmword ptr [rbx+20h], xmm8
0x140107457  mov     rax, [rsp+288h+var_218]
0x14010745c  mov     [rbx+30h], eax
0x14010745f  mov     rcx, [r15+100h]; FastMutex
0x140107466  call    cs:__imp_ExReleaseFastMutex
0x14010746d  nop     dword ptr [rax+rax+00h]
0x140107472  mov     rdx, [rsp+288h+Entry]; Entry
0x140107477  test    rdx, rdx
0x14010747a  jz      short loc_14010748F
0x14010747c  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x140107483  call    cs:__imp_ExFreeToLookasideListEx
0x14010748a  nop     dword ptr [rax+rax+00h]
0x14010748f  xor     eax, eax
0x140107491  mov     rcx, [rsp+288h+var_78]
0x140107499  xor     rcx, rsp; StackCookie
0x14010749c  call    __security_check_cookie
0x1401074a1  lea     r11, [rsp+288h+var_38]
0x1401074a9  movaps  xmm6, xmmword ptr [r11-10h]
0x1401074ae  movaps  xmm7, xmmword ptr [r11-20h]
0x1401074b3  movaps  xmm8, xmmword ptr [r11-30h]
0x1401074b8  mov     rsp, r11
0x1401074bb  pop     r15
0x1401074bd  pop     r14
0x1401074bf  pop     r13
0x1401074c1  pop     r12
0x1401074c3  pop     rdi
0x1401074c4  pop     rsi
0x1401074c5  pop     rbx
0x1401074c6  retn
0x1401074c8  mov     rdi, [r14]
0x1401074cb  mov     rdx, [rax]
0x1401074ce  cmp     rdx, rdi
0x1401074d1  jnb     loc_14010770B
0x1401074d7  mov     r9d, [rax+18h]
0x1401074db  add     rax, 18h
0x1401074df  mov     [rsp+288h+var_1C0], rax
0x1401074e7  lea     r8, [rbx+20h]
0x1401074eb  mov     [rsp+288h+var_1B8], r8
0x1401074f3  mov     esi, edi
0x1401074f5  sub     esi, edx
0x1401074f7  mov     ecx, [r14+18h]
0x1401074fb  add     rcx, rdi
0x1401074fe  lea     rax, [rdx+r9]
0x140107502  cmp     rcx, rax
0x140107505  jnb     loc_1401076C0
0x14010750b  movups  xmm6, xmmword ptr [rbx]
0x14010750e  movups  [rsp+288h+var_200], xmm6
0x140107516  movups  xmm7, xmmword ptr [rbx+10h]
0x14010751a  movups  [rsp+288h+var_1F0], xmm7
0x140107522  movups  xmm8, xmmword ptr [rbx+20h]
0x140107527  movups  [rsp+288h+var_1E0], xmm8
0x140107530  mov     eax, [rbx+30h]
0x140107533  mov     [rsp+288h+var_218], rax
0x140107538  mov     [rsp+288h+var_1D0], eax
0x14010753f  mov     [rsp+288h+var_248], 1
0x140107544  mov     [rbx+18h], esi
0x140107547  shl     esi, 0Ch
0x14010754a  mov     [r8], esi
0x14010754d  movsd   [rsp+288h+var_1A8], xmm6
0x140107556  movdqa  xmm0, xmm6
0x14010755a  psrldq  xmm0, 8
0x14010755f  movq    [rsp+288h+var_1A0], xmm0
0x140107568  mov     rax, qword ptr [rsp+288h+var_1F0]
0x140107570  mov     [rsp+288h+var_198], rax
0x140107578  movdqa  xmm0, xmm7
0x14010757c  psrldq  xmm0, 8
0x140107581  movd    r9d, xmm0
0x140107586  mov     [rsp+288h+var_190], r9d
0x14010758e  movdqa  xmm1, xmm7
0x140107592  psrldq  xmm1, 8
0x140107597  movq    rax, xmm1
0x14010759c  shr     rax, 20h
0x1401075a0  mov     [rsp+288h+var_18C], eax
0x1401075a7  movd    ecx, xmm8
0x1401075ac  mov     [rsp+288h+var_188], ecx
0x1401075b3  movups  xmm0, [rsp+288h+var_1E0+4]
0x1401075bb  movdqu  [rsp+288h+var_184], xmm0
0x1401075c4  mov     edx, [r14+18h]
0x1401075c8  mov     r8d, r9d
0x1401075cb  sub     r8d, edx
0x1401075ce  sub     r8d, [rbx+18h]
0x1401075d2  mov     [rsp+288h+var_190], r8d
0x1401075da  mov     eax, edx
0x1401075dc  shl     eax, 0Ch
0x1401075df  sub     ecx, eax
0x1401075e1  mov     eax, [rbx+18h]
0x1401075e4  shl     eax, 0Ch
0x1401075e7  sub     ecx, eax
0x1401075e9  mov     [rsp+288h+var_188], ecx
0x1401075f0  mov     rcx, [r14]
0x1401075f3  add     rcx, rdx
0x1401075f6  mov     [rsp+288h+var_1A8], rcx
0x1401075fe  mov     eax, [rbx+18h]
0x140107601  add     rax, rdx
0x140107604  add     rax, [rbx+8]
0x140107608  mov     [rsp+288h+var_1A0], rax
0x140107610  sub     r9d, r8d
0x140107613  mov     edx, r11d
0x140107616  mov     [rsp+288h+var_244], edx
0x14010761a  lea     eax, ds:0[r8*8]
0x140107622  cmp     edx, eax
0x140107624  jnb     short loc_140107649
0x140107626  lea     eax, [rdx+r9*8]
0x14010762a  mov     ecx, edx
0x14010762c  movzx   eax, word ptr [rbx+rax*2+24h]
0x140107631  mov     word ptr [rsp+rcx*2+288h+var_184], ax
0x140107639  inc     edx
0x14010763b  mov     [rsp+288h+var_244], edx
0x14010763f  mov     r8d, [rsp+288h+var_190]
0x140107647  jmp     short loc_14010761A
0x140107649  dec     r8d
0x14010764c  shl     r8d, 4
0x140107650  add     r8d, 34h ; '4'; BufferSize
0x140107654  lea     r9, [rsp+288h+NewElement]; NewElement
0x140107659  lea     rdx, [rsp+288h+var_1A8]; Buffer
0x140107661  mov     rcx, r12; Table
0x140107664  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14010766b  nop     dword ptr [rax+rax+00h]
0x140107670  xor     r13b, r13b
0x140107673  mov     [rsp+288h+var_248], r13b
0x140107678  or      byte ptr [rax+1Eh], 1
0x14010767c  mov     cl, [rax+1Eh]
0x14010767f  or      cl, 8
0x140107682  mov     [rax+1Eh], cl
0x140107685  or      cl, 20h
0x140107688  mov     [rax+1Eh], cl
0x14010768b  mov     r8d, [rbx+18h]
0x14010768f  add     r8, [rbx+8]
0x140107693  mov     [rsp+288h+DeleteCount], 0
0x14010769c  lea     rax, [rsp+288h+Entry]
0x1401076a1  mov     [rsp+288h+RestartKey], rax
0x1401076a6  mov     r9d, [r14+18h]
0x1401076aa  mov     rdx, r15
0x1401076ad  mov     rsi, [rsp+288h+var_228]
0x1401076b2  mov     rcx, [rsi+10h]
0x1401076b6  call    TxfInsertNewTopsRange
0x1401076bb  jmp     loc_1401077C3
0x1401076c0  sub     r9d, esi
0x1401076c3  mov     r8d, esi
0x1401076c6  add     r8, [rbx+8]
0x1401076ca  mov     [rsp+288h+DeleteCount], r11
0x1401076cf  lea     rax, [rsp+288h+Entry]
0x1401076d4  mov     [rsp+288h+RestartKey], rax
0x1401076d9  mov     rdx, r15
0x1401076dc  mov     rcx, [rsp+288h+var_228]
0x1401076e1  mov     rcx, [rcx+10h]
0x1401076e5  call    TxfInsertNewTopsRange
0x1401076ea  mov     rax, [rsp+288h+var_1C0]
0x1401076f2  mov     [rax], esi
0x1401076f4  shl     esi, 0Ch
0x1401076f7  mov     rax, [rsp+288h+var_1B8]
0x1401076ff  mov     [rax], esi
0x140107701  mov     rsi, [rsp+288h+var_228]
0x140107706  jmp     loc_1401077C3
0x14010770b  mov     r9d, [r14+18h]
0x14010770f  mov     r8, [rax+8]
0x140107713  mov     ecx, [rax+18h]
0x140107716  add     rcx, rdx
0x140107719  lea     rax, [rdi+r9]
0x14010771d  cmp     rax, rcx
0x140107720  jnb     short loc_14010778C
0x140107722  sub     edi, edx
0x140107724  add     edi, r9d
0x140107727  mov     [rsp+288h+DeleteCount], r11
0x14010772c  lea     rax, [rsp+288h+Entry]
0x140107731  mov     [rsp+288h+RestartKey], rax
0x140107736  mov     r9d, edi
0x140107739  mov     rdx, r15
0x14010773c  mov     rcx, [rsi+10h]
0x140107740  call    TxfInsertNewTopsRange
0x140107745  lea     r8d, ds:0[rdi*8]
0x14010774d  xor     edx, edx
0x14010774f  mov     [rsp+288h+var_244], edx
0x140107753  mov     ecx, [rbx+18h]
0x140107756  sub     ecx, edi
0x140107758  lea     eax, ds:0[rcx*8]
0x14010775f  cmp     edx, eax
0x140107761  jnb     short loc_140107778
  ... truncated ...
```
