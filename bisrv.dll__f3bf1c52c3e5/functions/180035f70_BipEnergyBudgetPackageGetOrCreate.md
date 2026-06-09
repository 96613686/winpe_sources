# BipEnergyBudgetPackageGetOrCreate

- ea: `0x180035f70`
- end: `0x180036475`
- name: `BipEnergyBudgetPackageGetOrCreate`
- size: `1285`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035d28`
- `0x180035e2c`
- `0x18004b890`
- `0x180062998`

## callees

- `0x180024240`
- `0x1800250d0`
- `0x1800251f8`
- `0x180026544`
- `0x18002b320`
- `0x180035f70`
- `0x18003a5b8`
- `0x18004c35c`
- `0x180061660`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x1800362c9`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x1800362c9`
- `ntdll!RtlInsertEntryHashTable` at `0x1800360fd`
- `ntdll!RtlInsertEntryHashTable` at `0x1800360fd`
- `ntdll!RtlFreeHeap` at `0x18003622c`
- `ntdll!RtlFreeHeap` at `0x180036247`
- `ntdll!RtlFreeHeap` at `0x180036264`
- `ntdll!RtlFreeHeap` at `0x18003622c`
- `ntdll!RtlFreeHeap` at `0x180036247`
- `ntdll!RtlFreeHeap` at `0x180036264`
- `ntdll!RtlAllocateHeap` at `0x180036031`
- `ntdll!RtlAllocateHeap` at `0x180036139`
- `ntdll!RtlAllocateHeap` at `0x180036200`
- `ntdll!RtlAllocateHeap` at `0x180036031`
- `ntdll!RtlAllocateHeap` at `0x180036139`
- `ntdll!RtlAllocateHeap` at `0x180036200`
- `ntdll!RtlLengthSid` at `0x1800361ec`
- `ntdll!RtlLengthSid` at `0x1800361ec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180036430`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180036430`

## pseudocode

```c
__int64 __fastcall BipEnergyBudgetPackageGetOrCreate(
        __int64 a1,
        __int64 *a2,
        void *a3,
        int a4,
        __int64 *a5,
        _QWORD *a6)
{
  _QWORD *v6; // rbx
  __int64 *v8; // r14
  char v10; // al
  __int64 BudgetForPackage; // r15
  __int64 v12; // rsi
  PVOID Heap; // rax
  int v14; // ebx
  char v15; // al
  __int64 v16; // r8
  bool v17; // zf
  __int64 v18; // rcx
  char *ImportanceScoreForPackage; // rdi
  char *v20; // rax
  __int64 v21; // rcx
  _WORD *v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rdx
  __int128 v25; // xmm0
  SIZE_T v26; // rbx
  PVOID v27; // rax
  void *v28; // r8
  void *v29; // r8
  __int64 v30; // rdx
  _QWORD *v31; // rdx
  int v32; // esi
  __int64 v33; // rax
  int v34; // ecx
  char v36; // [rsp+30h] [rbp-89h]
  unsigned int v37; // [rsp+34h] [rbp-85h] BYREF
  int v38; // [rsp+38h] [rbp-81h] BYREF
  __int64 v39; // [rsp+40h] [rbp-79h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-71h] BYREF
  __int64 *v41; // [rsp+58h] [rbp-61h]
  __int128 v42; // [rsp+60h] [rbp-59h] BYREF
  __int64 v43; // [rsp+70h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-39h] BYREF
  __int16 *v45; // [rsp+90h] [rbp-29h]
  int v46; // [rsp+98h] [rbp-21h]
  int v47; // [rsp+9Ch] [rbp-1Dh]
  __int64 *v48; // [rsp+A0h] [rbp-19h]
  int v49; // [rsp+A8h] [rbp-11h]
  int v50; // [rsp+ACh] [rbp-Dh]
  int *v51; // [rsp+B0h] [rbp-9h]
  __int64 v52; // [rsp+B8h] [rbp-1h]

  v6 = a6;
  v41 = a5;
  v8 = a2;
  v38 = a4;
  v43 = 0;
  v39 = 0;
  v10 = *(_BYTE *)(a1 + 176);
  *(_QWORD *)&EventDescriptor.Id = a6;
  v42 = 0;
  if ( (v10 & 4) != 0
    || !*(_WORD *)(a1 + 32)
    || !*(_WORD *)(a1 + 34)
    || *(_WORD *)(a1 + 36) >= 0x64u
    || (v10 & 0x40) != 0 )
  {
    return 0;
  }
  v36 = 0;
  BudgetForPackage = BipEnergyBudgetGetBudgetForPackage(a1, a2, &v39);
  v12 = -1;
  if ( !BudgetForPackage )
  {
    Heap = RtlAllocateHeap(BipHeap, 0, 0x190u);
    BudgetForPackage = (__int64)Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    if ( (memset_0(Heap, 0, 0x190u),
          *(_QWORD *)(BudgetForPackage + 360) = BudgetForPackage + 352,
          *(_QWORD *)(BudgetForPackage + 352) = BudgetForPackage + 352,
          v15 = *(_BYTE *)(a1 + 176),
          (v15 & 8) != 0)
      && v15 >= 0
      || !*(_DWORD *)(a1 + 76) )
    {
      *(_BYTE *)(BudgetForPackage + 308) = 1;
    }
    else
    {
      v37 = *(unsigned __int8 *)(a1 + 181) * (unsigned int)BipEnergyBudgetCalculateCreditsPerImportantPackage(a1);
      BipEnergyBudgetAdjustCreditsDuringRefillPeriod(a1, &v37);
      *(_DWORD *)(BudgetForPackage + 304) = v37;
    }
    v16 = -1;
    do
      v17 = *((_WORD *)v8 + ++v16) == 0;
    while ( !v17 );
    memcpy_0((void *)(BudgetForPackage + 40), v8, 2 * v16 + 2);
    v18 = *(_QWORD *)(a1 + 16);
    v42 = 0;
    v43 = 0;
    if ( !(unsigned __int8)RtlInsertEntryHashTable(v18, BudgetForPackage, v39, &v42) )
      return (unsigned int)-1073741801;
    v36 = 1;
  }
  ImportanceScoreForPackage = (char *)BipEnergyBudgetGetImportanceScoreForPackage(BudgetForPackage, v8, a3);
  if ( ImportanceScoreForPackage )
  {
LABEL_35:
    BipEnergyBudgetCacheImportanceScoreForBudget(a1, BudgetForPackage);
    if ( v36 && (unsigned int)dword_1800C3098 > 5 )
    {
      if ( v8 )
      {
        do
          v17 = *((_WORD *)v8 + ++v12) == 0;
        while ( !v17 );
        v32 = 2 * v12 + 2;
      }
      else
      {
        v8 = &qword_1800A1670;
        v32 = 2;
      }
      v33 = *(_QWORD *)(a1 + 16);
      v48 = v8;
      v49 = v32;
      v50 = 0;
      v34 = *(_DWORD *)(v33 + 20);
      v51 = &v38;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v38 = v34;
      v52 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v45 = &word_1800B177E;
      UserData.Reserved = 2;
      v46 = 68;
      v47 = 1;
      v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    if ( v41 )
      *v41 = BudgetForPackage;
    if ( v6 )
      *v6 = ImportanceScoreForPackage;
    return 0;
  }
  v20 = (char *)RtlAllocateHeap(BipHeap, 0, 0x1D8u);
  ImportanceScoreForPackage = v20;
  if ( !v20 )
    return (unsigned int)-1073741801;
  memset_0(v20, 0, 0x1D8u);
  LOBYTE(v21) = 7;
  v14 = BipUsageHistoryInitialize(v21, 864000000000LL, ImportanceScoreForPackage + 432);
  if ( v14 >= 0 )
  {
    *((_DWORD *)ImportanceScoreForPackage + 116) = -1;
    v22 = ImportanceScoreForPackage + 16;
    v23 = v8;
    v24 = 3;
    do
    {
      v22 += 64;
      v25 = *(_OWORD *)v23;
      v23 += 16;
      *((_OWORD *)v22 - 8) = v25;
      *((_OWORD *)v22 - 7) = *((_OWORD *)v23 - 7);
      *((_OWORD *)v22 - 6) = *((_OWORD *)v23 - 6);
      *((_OWORD *)v22 - 5) = *((_OWORD *)v23 - 5);
      *((_OWORD *)v22 - 4) = *((_OWORD *)v23 - 4);
      *((_OWORD *)v22 - 3) = *((_OWORD *)v23 - 3);
      *((_OWORD *)v22 - 2) = *((_OWORD *)v23 - 2);
      *((_OWORD *)v22 - 1) = *((_OWORD *)v23 - 1);
      --v24;
    }
    while ( v24 );
    *v22 = *(_WORD *)v23;
    v26 = RtlLengthSid(a3);
    v27 = RtlAllocateHeap(BipHeap, 0, v26);
    *((_QWORD *)ImportanceScoreForPackage + 51) = v27;
    if ( !v27 )
    {
      v14 = -1073741801;
      goto LABEL_25;
    }
    memcpy_0(v27, a3, v26);
    v30 = *((_QWORD *)ImportanceScoreForPackage + 51);
    *((_DWORD *)ImportanceScoreForPackage + 104) = v38;
    if ( (unsigned int)BipGetPackageImportanceInfoFromStore(
                         v8,
                         v30,
                         ImportanceScoreForPackage + 424,
                         ImportanceScoreForPackage + 432) == -1073741772 )
    {
      *(_BYTE *)(BudgetForPackage + 308) = 1;
      *((_QWORD *)ImportanceScoreForPackage + 53) = MEMORY[0x7FFE0014];
      RtlQueryUnbiasedInterruptTime(BudgetForPackage + 344);
      *(_QWORD *)(BudgetForPackage + 344) += 9000000000LL;
      BipSavePackageImportanceInfoInStore((PCWSTR)v8, *((PSID *)ImportanceScoreForPackage + 51));
    }
    ++*(_DWORD *)(BudgetForPackage + 296);
    v31 = *(_QWORD **)(BudgetForPackage + 360);
    if ( *v31 != BudgetForPackage + 352 )
      __fastfail(3u);
    v6 = *(_QWORD **)&EventDescriptor.Id;
    *(_QWORD *)ImportanceScoreForPackage = BudgetForPackage + 352;
    *((_QWORD *)ImportanceScoreForPackage + 1) = v31;
    *v31 = ImportanceScoreForPackage;
    *(_QWORD *)(BudgetForPackage + 360) = ImportanceScoreForPackage;
    goto LABEL_35;
  }
LABEL_25:
  v28 = (void *)*((_QWORD *)ImportanceScoreForPackage + 51);
  if ( v28 )
    RtlFreeHeap(BipHeap, 0, v28);
  v29 = (void *)*((_QWORD *)ImportanceScoreForPackage + 57);
  if ( v29 )
  {
    RtlFreeHeap(BipHeap, 0, v29);
    *((_QWORD *)ImportanceScoreForPackage + 57) = 0;
  }
  RtlFreeHeap(BipHeap, 0, ImportanceScoreForPackage);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180035f70  mov     [rsp-8+arg_18], rbx
0x180035f75  push    rbp
0x180035f76  push    rsi
0x180035f77  push    rdi
0x180035f78  push    r12
0x180035f7a  push    r13
0x180035f7c  push    r14
0x180035f7e  push    r15
0x180035f80  lea     rbp, [rsp-17h]
0x180035f85  sub     rsp, 0D0h
0x180035f8c  mov     rax, cs:__security_cookie
0x180035f93  xor     rax, rsp
0x180035f96  mov     [rbp+47h+var_40], rax
0x180035f9a  mov     rax, [rbp+47h+arg_20]
0x180035f9e  xorps   xmm0, xmm0
0x180035fa1  mov     rbx, [rbp+47h+arg_28]
0x180035fa5  mov     r12, r8
0x180035fa8  mov     [rbp+47h+var_A8], rax
0x180035fac  mov     r14, rdx
0x180035faf  xor     eax, eax
0x180035fb1  mov     [rsp+100h+var_C8], r9d
0x180035fb6  mov     [rbp+47h+var_90], rax
0x180035fba  mov     r13, rcx
0x180035fbd  mov     [rbp+47h+var_C0], rax
0x180035fc1  movzx   eax, byte ptr [rcx+0B0h]
0x180035fc8  mov     qword ptr [rbp+47h+EventDescriptor.Id], rbx
0x180035fcc  movups  [rbp+47h+var_A0], xmm0
0x180035fd0  test    al, 4
0x180035fd2  jnz     loc_18003644A
0x180035fd8  cmp     word ptr [rcx+20h], 0
0x180035fdd  jz      loc_18003644A
0x180035fe3  cmp     word ptr [rcx+22h], 0
0x180035fe8  jz      loc_18003644A
0x180035fee  cmp     word ptr [rcx+24h], 64h ; 'd'
0x180035ff3  jnb     loc_18003644A
0x180035ff9  test    al, 40h
0x180035ffb  jnz     loc_18003644A
0x180036001  lea     r8, [rbp+47h+var_C0]
0x180036005  mov     [rsp+100h+var_D0], 0
0x18003600a  call    BipEnergyBudgetGetBudgetForPackage
0x18003600f  mov     r15, rax
0x180036012  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180036019  test    rax, rax
0x18003601c  jnz     loc_180036110
0x180036022  mov     rcx, cs:BipHeap; HeapHandle
0x180036029  xor     edx, edx; Flags
0x18003602b  mov     r8d, 190h; Size
0x180036031  call    cs:__imp_RtlAllocateHeap
0x180036037  mov     r15, rax
0x18003603a  test    rax, rax
0x18003603d  jnz     short loc_180036049
0x18003603f  mov     ebx, 0C0000017h
0x180036044  jmp     loc_18003644C
0x180036049  xor     edx, edx; Val
0x18003604b  mov     r8d, 190h; Size
0x180036051  mov     rcx, r15; void *
0x180036054  call    memset_0
0x180036059  lea     rax, [r15+160h]
0x180036060  mov     [rax+8], rax
0x180036064  mov     [rax], rax
0x180036067  movzx   eax, byte ptr [r13+0B0h]
0x18003606f  test    al, 8
0x180036071  jz      short loc_180036077
0x180036073  test    al, al
0x180036075  jns     short loc_1800360AF
0x180036077  cmp     dword ptr [r13+4Ch], 0
0x18003607c  jz      short loc_1800360AF
0x18003607e  mov     rcx, r13
0x180036081  call    BipEnergyBudgetCalculateCreditsPerImportantPackage
0x180036086  movzx   ecx, byte ptr [r13+0B5h]
0x18003608e  lea     rdx, [rsp+100h+var_CC]
0x180036093  imul    eax, ecx
0x180036096  mov     rcx, r13
0x180036099  mov     [rsp+100h+var_CC], eax
0x18003609d  call    BipEnergyBudgetAdjustCreditsDuringRefillPeriod
0x1800360a2  mov     eax, [rsp+100h+var_CC]
0x1800360a6  mov     [r15+130h], eax
0x1800360ad  jmp     short loc_1800360B7
0x1800360af  mov     byte ptr [r15+134h], 1
0x1800360b7  mov     r8, rsi
0x1800360ba  nop     word ptr [rax+rax+00h]
0x1800360c0  cmp     word ptr [r14+r8*2+2], 0
0x1800360c7  lea     r8, [r8+1]
0x1800360cb  jnz     short loc_1800360C0
0x1800360cd  lea     r8, ds:2[r8*2]; Size
0x1800360d5  mov     rdx, r14; Src
0x1800360d8  lea     rcx, [r15+28h]; void *
0x1800360dc  call    memcpy_0
0x1800360e1  mov     r8, [rbp+47h+var_C0]
0x1800360e5  lea     r9, [rbp+47h+var_A0]
0x1800360e9  mov     rcx, [r13+10h]
0x1800360ed  xorps   xmm0, xmm0
0x1800360f0  xor     eax, eax
0x1800360f2  mov     rdx, r15
0x1800360f5  movups  [rbp+47h+var_A0], xmm0
0x1800360f9  mov     [rbp+47h+var_90], rax
0x1800360fd  call    cs:__imp_RtlInsertEntryHashTable
0x180036103  test    al, al
0x180036105  jz      loc_18003603F
0x18003610b  mov     [rsp+100h+var_D0], 1
0x180036110  mov     r8, r12
0x180036113  mov     rdx, r14
0x180036116  mov     rcx, r15
0x180036119  call    BipEnergyBudgetGetImportanceScoreForPackage
0x18003611e  mov     rdi, rax
0x180036121  test    rax, rax
0x180036124  jnz     loc_18003632D
0x18003612a  mov     rcx, cs:BipHeap; HeapHandle
0x180036131  xor     edx, edx; Flags
0x180036133  mov     r8d, 1D8h; Size
0x180036139  call    cs:__imp_RtlAllocateHeap
0x18003613f  mov     rdi, rax
0x180036142  test    rax, rax
0x180036145  jz      loc_18003603F
0x18003614b  xor     edx, edx; Val
0x18003614d  mov     r8d, 1D8h; Size
0x180036153  mov     rcx, rax; void *
0x180036156  call    memset_0
0x18003615b  lea     r8, [rdi+1B0h]
0x180036162  mov     rdx, 0C92A69C000h
0x18003616c  mov     cl, 7
0x18003616e  call    BipUsageHistoryInitialize
0x180036173  mov     ebx, eax
0x180036175  test    eax, eax
0x180036177  js      loc_180036217
0x18003617d  mov     [rdi+1D0h], esi
0x180036183  lea     rcx, [rdi+10h]
0x180036187  mov     rax, r14
0x18003618a  mov     edx, 3
0x18003618f  nop
0x180036190  lea     rcx, [rcx+80h]
0x180036197  movups  xmm0, xmmword ptr [rax]
0x18003619a  lea     rax, [rax+80h]
0x1800361a1  movups  xmmword ptr [rcx-80h], xmm0
0x1800361a5  movups  xmm1, xmmword ptr [rax-70h]
0x1800361a9  movups  xmmword ptr [rcx-70h], xmm1
0x1800361ad  movups  xmm0, xmmword ptr [rax-60h]
0x1800361b1  movups  xmmword ptr [rcx-60h], xmm0
0x1800361b5  movups  xmm1, xmmword ptr [rax-50h]
0x1800361b9  movups  xmmword ptr [rcx-50h], xmm1
0x1800361bd  movups  xmm0, xmmword ptr [rax-40h]
0x1800361c1  movups  xmmword ptr [rcx-40h], xmm0
0x1800361c5  movups  xmm1, xmmword ptr [rax-30h]
0x1800361c9  movups  xmmword ptr [rcx-30h], xmm1
0x1800361cd  movups  xmm0, xmmword ptr [rax-20h]
0x1800361d1  movups  xmmword ptr [rcx-20h], xmm0
0x1800361d5  movups  xmm1, xmmword ptr [rax-10h]
0x1800361d9  movups  xmmword ptr [rcx-10h], xmm1
0x1800361dd  sub     rdx, 1
0x1800361e1  jnz     short loc_180036190
0x1800361e3  movzx   eax, word ptr [rax]
0x1800361e6  mov     [rcx], ax
0x1800361e9  mov     rcx, r12; Sid
0x1800361ec  call    cs:__imp_RtlLengthSid
0x1800361f2  mov     rcx, cs:BipHeap; HeapHandle
0x1800361f9  xor     edx, edx; Flags
0x1800361fb  mov     r8d, eax; Size
0x1800361fe  mov     ebx, eax
0x180036200  call    cs:__imp_RtlAllocateHeap
0x180036206  mov     [rdi+198h], rax
0x18003620d  test    rax, rax
0x180036210  jnz     short loc_18003626F
0x180036212  mov     ebx, 0C0000017h
0x180036217  mov     r8, [rdi+198h]; P
0x18003621e  test    r8, r8
0x180036221  jz      short loc_180036232
0x180036223  mov     rcx, cs:BipHeap; HeapHandle
0x18003622a  xor     edx, edx; Flags
0x18003622c  call    cs:__imp_RtlFreeHeap
0x180036232  mov     r8, [rdi+1C8h]; P
0x180036239  test    r8, r8
0x18003623c  jz      short loc_180036258
0x18003623e  mov     rcx, cs:BipHeap; HeapHandle
0x180036245  xor     edx, edx; Flags
0x180036247  call    cs:__imp_RtlFreeHeap
0x18003624d  mov     qword ptr [rdi+1C8h], 0
0x180036258  mov     rcx, cs:BipHeap; HeapHandle
0x18003625f  mov     r8, rdi; P
0x180036262  xor     edx, edx; Flags
0x180036264  call    cs:__imp_RtlFreeHeap
0x18003626a  jmp     loc_18003644C
0x18003626f  mov     r8, rbx; Size
0x180036272  mov     rdx, r12; Src
0x180036275  mov     rcx, rax; void *
0x180036278  call    memcpy_0
0x18003627d  mov     eax, [rsp+100h+var_C8]
0x180036281  lea     r9, [rdi+1B0h]
0x180036288  mov     rdx, [rdi+198h]
0x18003628f  lea     r8, [rdi+1A8h]
0x180036296  mov     rcx, r14
0x180036299  mov     [rdi+1A0h], eax
0x18003629f  call    BipGetPackageImportanceInfoFromStore
0x1800362a4  cmp     eax, 0C0000034h
0x1800362a9  jnz     short loc_1800362FD
0x1800362ab  mov     byte ptr [r15+134h], 1
0x1800362b3  lea     rcx, [r15+158h]
0x1800362ba  mov     eax, 7FFE0014h
0x1800362bf  mov     rax, [rax]
0x1800362c2  mov     [rdi+1A8h], rax
0x1800362c9  call    cs:__imp_RtlQueryUnbiasedInterruptTime
0x1800362cf  mov     rax, 218711A00h
0x1800362d9  lea     r9, [rdi+1B0h]
0x1800362e0  add     [r15+158h], rax
0x1800362e7  mov     rcx, r14; Source
0x1800362ea  mov     r8, [rdi+1A8h]
0x1800362f1  mov     rdx, [rdi+198h]; Sid
0x1800362f8  call    BipSavePackageImportanceInfoInStore
0x1800362fd  inc     dword ptr [r15+128h]
0x180036304  lea     rax, [r15+160h]
0x18003630b  mov     rdx, [rax+8]
0x18003630f  cmp     [rdx], rax
0x180036312  jz      short loc_18003631B
0x180036314  mov     ecx, 3
0x180036319  int     29h; Win8: RtlFailFast(ecx)
0x18003631b  mov     rbx, qword ptr [rbp+47h+EventDescriptor.Id]
0x18003631f  mov     [rdi], rax
0x180036322  mov     [rdi+8], rdx
0x180036326  mov     [rdx], rdi
0x180036329  mov     [rax+8], rdi
0x18003632d  mov     rdx, r15
0x180036330  mov     rcx, r13
0x180036333  call    BipEnergyBudgetCacheImportanceScoreForBudget
0x180036338  cmp     [rsp+100h+var_D0], 0
0x18003633d  jz      loc_180036436
0x180036343  mov     eax, cs:dword_1800C3098
0x180036349  cmp     eax, 5
0x18003634c  jbe     loc_180036436
0x180036352  test    r14, r14
0x180036355  jz      short loc_180036376
0x180036357  nop     word ptr [rax+rax+00000000h]
0x180036360  cmp     word ptr [r14+rsi*2+2], 0
0x180036367  lea     rsi, [rsi+1]
0x18003636b  jnz     short loc_180036360
0x18003636d  lea     esi, ds:2[rsi*2]
0x180036374  jmp     short loc_180036382
0x180036376  lea     r14, qword_1800A1670
0x18003637d  mov     esi, 2
0x180036382  mov     rax, [r13+10h]
0x180036386  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18003638a  mov     [rbp+47h+var_60], r14
0x18003638e  xor     r9d, r9d; RelatedActivityId
0x180036391  mov     [rbp+47h+var_58], esi
0x180036394  xor     r8d, r8d; ActivityId
0x180036397  mov     [rbp+47h+var_54], 0
0x18003639e  mov     ecx, [rax+14h]
0x1800363a1  lea     rax, [rsp+100h+var_C8]
0x1800363a6  mov     [rbp+47h+var_50], rax
0x1800363aa  movzx   eax, cs:word_1800B1774
0x1800363b1  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x1800363b4  mov     rax, cs:off_1800C30A0
0x1800363bb  mov     [rbp+47h+var_80.Ptr], rax
0x1800363bf  mov     [rsp+100h+var_C8], ecx
0x1800363c3  lea     rcx, _TraceLoggingMetadata
0x1800363ca  mov     [rbp+47h+var_48], 4
0x1800363d2  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x1800363d9  mov     [rbp+47h+EventDescriptor.Keyword], 0
0x1800363e1  movzx   eax, word ptr [rax]
0x1800363e4  mov     [rbp+47h+var_80.Size], eax
0x1800363e7  lea     rax, word_1800B177E
0x1800363ee  mov     [rbp+47h+var_70], rax
0x1800363f2  lea     rax, _TraceLoggingMetadataEnd
0x1800363f9  sub     eax, ecx
0x1800363fb  mov     dword ptr [rbp+47h+var_80.0Ch], 2
0x180036402  mov     [rbp+47h+var_68], 44h ; 'D'
0x180036409  mov     [rbp+47h+var_64], 1
0x180036410  mov     [rsp+100h+var_CC], eax
0x180036414  mov     eax, [rsp+100h+var_CC]
0x180036418  mov     rcx, cs:RegHandle; RegHandle
0x18003641f  lea     rax, [rbp+47h+var_80]
0x180036423  mov     [rsp+100h+UserData], rax; UserData
0x180036428  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x180036430  call    cs:__imp_EventWriteTransfer
0x180036436  mov     rax, [rbp+47h+var_A8]
0x18003643a  test    rax, rax
0x18003643d  jz      short loc_180036442
0x18003643f  mov     [rax], r15
0x180036442  test    rbx, rbx
0x180036445  jz      short loc_18003644A
0x180036447  mov     [rbx], rdi
0x18003644a  xor     ebx, ebx
0x18003644c  mov     eax, ebx
0x18003644e  mov     rcx, [rbp+47h+var_40]
0x180036452  xor     rcx, rsp; StackCookie
0x180036455  call    __security_check_cookie
0x18003645a  mov     rbx, [rsp+100h+arg_18]
0x180036462  add     rsp, 0D0h
0x180036469  pop     r15
0x18003646b  pop     r14
0x18003646d  pop     r13
0x18003646f  pop     r12
0x180036471  pop     rdi
0x180036472  pop     rsi
0x180036473  pop     rbp
0x180036474  retn
```
