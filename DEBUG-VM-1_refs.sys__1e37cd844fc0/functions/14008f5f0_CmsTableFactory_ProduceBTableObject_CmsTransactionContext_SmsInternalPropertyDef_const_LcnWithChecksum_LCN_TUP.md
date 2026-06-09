# CmsTableFactory::ProduceBTableObject(CmsTransactionContext *,SmsInternalPropertyDef const &,LcnWithChecksum *,_LCN_TUPLE const *,ulong,uchar,CmsBPlusTable * *)

- ea: `0x14008f5f0`
- end: `0x14008fd06`
- name: `?ProduceBTableObject@CmsTableFactory@@SAJPEAVCmsTransactionContext@@AEBUSmsInternalPropertyDef@@PEAULcnWithChecksum@@PEBT_LCN_TUPLE@@KEPEAPEAVCmsBPlusTable@@@Z`
- size: `1814`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, const struct SmsInternalPropertyDef *, struct LcnWithChecksum *, const union _LCN_TUPLE *, unsigned int, char, struct CmsBPlusTable **)`
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006cb10`
- `0x140097104`
- `0x1400bdd04`
- `0x140131a08`
- `0x1401403f0`
- `0x140140534`
- `0x1401665c4`

## callees

- `0x14008f5f0`
- `0x14008fd0c`
- `0x1400ceda0`
- `0x1400cf828`
- `0x1401f40a0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14008faba`
- `ntoskrnl!KeSetEvent` at `0x14008faba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008fcc3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008fcc3`
- `ntoskrnl!ExAllocatePool2` at `0x14008f64d`
- `ntoskrnl!ExAllocatePool2` at `0x14008f64d`
- `ntoskrnl!ExInitializeFastResource` at `0x14008facf`
- `ntoskrnl!ExInitializeFastResource` at `0x14008facf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008f610`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008f610`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14008f7cb`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14008f7cb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402017d4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402017d4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008fce0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008fce0`
- `ntoskrnl!KeInitializeEvent` at `0x14008faa2`
- `ntoskrnl!KeInitializeEvent` at `0x14008faa2`

## string_xrefs

- `0x14008f664`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsTableFactory::ProduceBTableObject(
        struct CmsTransactionContext *a1,
        const struct SmsInternalPropertyDef *a2,
        struct LcnWithChecksum *a3,
        const union _LCN_TUPLE *a4,
        unsigned int a5,
        char a6,
        struct CmsBPlusTable **a7)
{
  __int64 v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 Pool2; // rax
  char *v14; // rdi
  int v15; // ecx
  struct CmsBPlusTable *v16; // rbx
  unsigned int v17; // ebp
  char *v18; // r14
  __int64 v19; // r13
  unsigned int v20; // r8d
  struct CmsBPlusTable **v21; // r15
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  char v23; // al
  __int64 v24; // rax
  struct _NPAGED_LOOKASIDE_LIST *v26; // rcx
  char *v27; // rax
  int v28; // [rsp+24h] [rbp-34h]

  v10 = qword_140269478 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v10 < 0x5E8u )
  {
    v10 = 0;
    v12 = 1528;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v10 + 8) )
  {
    v26 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
    if ( *(_BYTE *)(v10 + 9) )
      v27 = (char *)ExAllocateFromNPagedLookasideList(v26);
    else
      v27 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v26);
LABEL_10:
    v14 = v27;
    if ( v27 )
      goto LABEL_11;
    goto LABEL_9;
  }
  if ( (int)*(_QWORD *)(v10 + 88) > (int)HIDWORD(*(_QWORD *)(v10 + 88)) )
  {
    v15 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 88));
    if ( v15 >= *(_DWORD *)(v10 + 92) && v15 >= 0 )
    {
      v27 = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v10 + 64));
      goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
  }
LABEL_9:
  v12 = *(unsigned int *)(v10 + 4);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v12, 1766871885, v11);
  v14 = (char *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    goto LABEL_29;
LABEL_11:
  *(_QWORD *)v14 = v10;
  v16 = (struct CmsBPlusTable *)(v14 + 16);
  if ( v14 == (char *)-16LL )
  {
LABEL_29:
    v17 = -1073741670;
    v16 = 0;
    goto LABEL_23;
  }
  v17 = 0;
  v18 = v14 + 232;
  if ( v14 == (char *)-232LL )
  {
    v18 = 0;
  }
  else
  {
    v19 = *((_QWORD *)a1 + 1);
    *(_QWORD *)v18 = &CmsCompositeBase::`vftable';
    *((_DWORD *)v14 + 60) = 0x1000000;
    v14[244] = 0;
    *((_QWORD *)v14 + 31) = v19;
    v14[256] = 0;
    *((_DWORD *)v14 + 65) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
    *(_QWORD *)v18 = &CmsCowRootComposite::`vftable';
    *((_QWORD *)v14 + 42) = 0;
    *((_QWORD *)v14 + 43) = 0;
    *((_QWORD *)v14 + 44) = 0;
    *((_QWORD *)v14 + 45) = 0;
    *((_QWORD *)v14 + 46) = 0;
    *((_DWORD *)v14 + 100) = a5;
    *((_QWORD *)v14 + 47) = 0;
    *((_OWORD *)v14 + 24) = 0;
    memset(v14 + 264, 0, 0x48u);
    if ( a3 )
    {
      *(_OWORD *)(v14 + 264) = *(_OWORD *)a3;
      *(_OWORD *)(v14 + 280) = *((_OWORD *)a3 + 1);
      SmsChecksumBlob::CopyFrom((SmsChecksumBlob *)(v14 + 296), (struct LcnWithChecksum *)((char *)a3 + 32), v20);
    }
    else
    {
      *(_OWORD *)(v14 + 264) = *(_OWORD *)a4;
      *(_OWORD *)(v14 + 280) = *((_OWORD *)a4 + 1);
      CmsChecksum::InitChecksumBlob(
        *(CmsChecksum **)(v19 + 3536),
        a5 << *(_DWORD *)(v19 + 64),
        (struct SmsChecksumBlob *)(v14 + 296));
    }
  }
  v18[12] |= 2u;
  ExInitializeAutoExpandPushLock(v14 + 408, 1);
  *((_QWORD *)v14 + 58) = 0;
  v21 = (struct CmsBPlusTable **)(v14 + 552);
  *((_QWORD *)v14 + 54) = 0;
  *((_QWORD *)v14 + 56) = 0;
  *((_DWORD *)v14 + 115) = 0;
  *((_QWORD *)v14 + 63) = v14 + 496;
  *((_QWORD *)v14 + 62) = v14 + 496;
  *((_QWORD *)v14 + 65) = v14 + 512;
  *((_QWORD *)v14 + 64) = v14 + 512;
  *((_QWORD *)v14 + 66) = 0;
  *((_QWORD *)v14 + 67) = 0;
  *((_QWORD *)v14 + 68) = 0;
  *((_QWORD *)v14 + 60) = 0;
  *((_QWORD *)v14 + 59) = 0;
  *((_QWORD *)v14 + 53) = 0;
  *((_QWORD *)v14 + 55) = 0;
  *((_DWORD *)v14 + 114) = 0;
  *((_QWORD *)v14 + 83) = 0;
  *((_OWORD *)v14 + 49) = 0;
  *((_OWORD *)v14 + 50) = 0;
  v14[836] = 0;
  *((_DWORD *)v14 + 208) = 0;
  *((_QWORD *)v14 + 102) = 0;
  v14[838] = 0;
  *((_QWORD *)v14 + 103) = 0;
  *((_OWORD *)v14 + 53) = 0;
  *((_OWORD *)v14 + 54) = 0;
  v14[900] = 0;
  *((_DWORD *)v14 + 224) = 0;
  *((_QWORD *)v14 + 110) = 0;
  v14[902] = 0;
  *((_QWORD *)v14 + 111) = 0;
  *((_DWORD *)v14 + 229) = 0;
  *((_QWORD *)v14 + 123) = v14 + 552;
  *((_QWORD *)v14 + 137) = 0;
  *((_QWORD *)v14 + 138) = 0;
  *((_QWORD *)v14 + 139) = 0;
  *((_QWORD *)v14 + 127) = 0;
  *((_QWORD *)v14 + 125) = 0;
  v14[1024] = 0;
  *((_QWORD *)v14 + 131) = 0;
  *((_QWORD *)v14 + 129) = 0;
  v14[1056] = 1;
  *((_QWORD *)v14 + 133) = 0;
  *((_QWORD *)v14 + 134) = 1;
  *((_QWORD *)v14 + 135) = 0;
  *((_QWORD *)v14 + 136) = 0;
  *((_QWORD *)v14 + 141) = ML_LSN_NULL;
  *((_DWORD *)v14 + 290) = 0;
  *((_QWORD *)v14 + 144) = v14 + 1144;
  *((_QWORD *)v14 + 143) = v14 + 1144;
  *((_QWORD *)v14 + 147) = v14 + 1168;
  *((_QWORD *)v14 + 146) = v14 + 1168;
  *((_DWORD *)v14 + 300) = 0;
  *((_DWORD *)v14 + 306) = 3;
  *((_QWORD *)v14 + 155) = 0;
  *((_DWORD *)v14 + 304) = 0;
  *((_QWORD *)v14 + 148) = 0;
  *((_DWORD *)v14 + 312) = 0;
  *((_QWORD *)v14 + 157) = 0;
  *(_OWORD *)(v14 + 1272) = 0;
  *(_OWORD *)(v14 + 1288) = 0;
  v14[1324] = 0;
  *((_DWORD *)v14 + 330) = 0;
  *((_QWORD *)v14 + 163) = 0;
  v14[1326] = 0;
  *((_QWORD *)v14 + 164) = 0;
  *(_OWORD *)(v14 + 1336) = 0;
  *(_OWORD *)(v14 + 1352) = 0;
  v14[1388] = 0;
  *((_DWORD *)v14 + 346) = 0;
  *((_QWORD *)v14 + 171) = 0;
  v14[1390] = 0;
  *((_QWORD *)v14 + 172) = 0;
  *((_QWORD *)v14 + 179) = v14 + 1448;
  *((_DWORD *)v14 + 355) = v28;
  *((_DWORD *)v14 + 361) = 32;
  *(_OWORD *)(v14 + 1400) = 0;
  *((_DWORD *)v14 + 354) = 0;
  *((_QWORD *)v14 + 178) = 0;
  v14[1440] = 0;
  *((_DWORD *)v14 + 370) = 0;
  *((_QWORD *)v14 + 186) = 0;
  *((_QWORD *)v14 + 88) = 0;
  *((_QWORD *)v14 + 89) = 0;
  *((_QWORD *)v14 + 87) = 0;
  *((_QWORD *)v14 + 86) = v14 + 552;
  *((_QWORD *)v14 + 95) = 0;
  *((_QWORD *)v14 + 96) = 0;
  *((_DWORD *)v14 + 194) = 0;
  *((_QWORD *)v14 + 105) = 0;
  *((_QWORD *)v14 + 166) = 0;
  *((_DWORD *)v14 + 228) = 0;
  *((_QWORD *)v14 + 115) = 0;
  *((_OWORD *)v14 + 58) = 0;
  *((_DWORD *)v14 + 284) = 0;
  *((_QWORD *)v14 + 113) = 0;
  *((_QWORD *)v14 + 174) = 0;
  *((_QWORD *)v14 + 85) = v14 + 672;
  *((_QWORD *)v14 + 84) = v14 + 672;
  *((_QWORD *)v14 + 94) = v14 + 744;
  *((_QWORD *)v14 + 93) = v14 + 744;
  *((_DWORD *)v14 + 290) |= 1u;
  KeInitializeEvent((PRKEVENT)v14 + 30, NotificationEvent, 0);
  KeSetEvent((PRKEVENT)v14 + 30, 0, 0);
  ExInitializeFastResource(v14 + 560, 9);
  *((_QWORD *)v14 + 83) = 0;
  *((_QWORD *)v14 + 120) = 0;
  *((_QWORD *)v14 + 190) = 0;
  *((_QWORD *)v14 + 157) = 0;
  *((_DWORD *)v14 + 312) = 0;
  *((_DWORD *)v14 + 316) = 0;
  *((_QWORD *)v14 + 187) = 0;
  *((_QWORD *)v14 + 186) = 0;
  *((_DWORD *)v14 + 370) = 0;
  *((_QWORD *)v14 + 121) = 0;
  *((_QWORD *)v14 + 3) = 1;
  v14[32] = 0;
  *((_QWORD *)v14 + 5) = a2;
  *(_QWORD *)v16 = &CmsBPlusTable::`vftable';
  *((_QWORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 13) = 0;
  *((_QWORD *)v14 + 14) = 0;
  *((_QWORD *)v14 + 15) = 0;
  *((_QWORD *)v14 + 16) = 0;
  *((_QWORD *)v14 + 17) = 0;
  *((_DWORD *)v14 + 36) = 0;
  *((_QWORD *)v14 + 19) = 4;
  *((_QWORD *)v14 + 20) = 4;
  *((_QWORD *)v14 + 21) = 4;
  *((_QWORD *)v14 + 22) = 4;
  *((_QWORD *)v14 + 23) = 4;
  *((_QWORD *)v14 + 24) = 4;
  *((_DWORD *)v14 + 50) = 4;
  *((_QWORD *)v14 + 26) = 0;
  *((_QWORD *)v14 + 27) = 0;
  *((_WORD *)v14 + 112) = *(unsigned __int8 *)(*((_QWORD *)v18 + 2) + 88LL);
  *((_WORD *)v14 + 113) = -1;
  v14[228] = 0;
  *((_DWORD *)v14 + 51) = 0;
  *((_QWORD *)v14 + 7) = v14 + 408;
  *((_QWORD *)v14 + 10) = v14 + 16;
  *((_QWORD *)v14 + 6) = v14 + 16;
  if ( v14 != (char *)-552LL )
  {
    *((_QWORD *)v14 + 11) = v21;
    *v21 = v16;
    *((_QWORD *)v14 + 87) = v14 + 16;
  }
  v14[32] = v14[32] & 0xFB | (*(_DWORD *)(*((_QWORD *)v14 + 5) + 44LL) >> 6) & 4;
  v22 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v14 + 16);
  *((_QWORD *)v14 + 16) = v18;
  if ( v22 )
    (**v22)(v22, 1);
  v23 = v14[29];
  *((_QWORD *)v14 + 12) = 0;
  v14[29] = v23 & 0xFE | (a6 != 0);
  v14[28] |= 9u;
  v24 = *((_QWORD *)v14 + 5);
  if ( v24 && (*(_DWORD *)(v24 + 44) & 0x200) != 0 )
    v14[32] |= 2u;
LABEL_23:
  *a7 = v16;
  return v17;
}

```

## disassembly

```asm
0x14008f5f0  mov     [rsp+arg_18], rbx
0x14008f5f5  mov     [rsp+arg_8], rdx
0x14008f5fa  push    rbp
0x14008f5fb  push    rsi
0x14008f5fc  push    rdi
0x14008f5fd  push    r12
0x14008f5ff  push    r13
0x14008f601  sub     rsp, 30h
0x14008f605  mov     r13, rcx
0x14008f608  mov     r12, r9
0x14008f60b  xor     ecx, ecx; ProcNumber
0x14008f60d  mov     rsi, r8
0x14008f610  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008f617  nop     dword ptr [rax+rax+00h]
0x14008f61c  xor     edx, edx
0x14008f61e  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008f624  lea     rbx, [rdx+rdx*2]
0x14008f628  shl     rbx, 6
0x14008f62c  add     rbx, cs:qword_140269478
0x14008f633  cmp     dword ptr [rbx], 5E8h
0x14008f639  jnb     short loc_14008F671
0x14008f63b  xor     ebx, ebx
0x14008f63d  mov     edx, 5F8h
0x14008f642  mov     ecx, 42h ; 'B'
0x14008f647  mov     r8d, 6950534Dh
0x14008f64d  call    cs:__imp_ExAllocatePool2
0x14008f654  nop     dword ptr [rax+rax+00h]
0x14008f659  mov     rdi, rax
0x14008f65c  test    al, 0Fh
0x14008f65e  jz      loc_1402017E6
0x14008f664  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14008f66b  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14008f671  cmp     byte ptr [rbx+8], 0
0x14008f675  jnz     loc_14008FCB5
0x14008f67b  mov     rcx, [rbx+58h]
0x14008f67f  mov     rax, rcx
0x14008f682  shr     rax, 20h
0x14008f686  cmp     ecx, eax
0x14008f688  jle     short loc_14008F6A9
0x14008f68a  nop
0x14008f68b  mov     ecx, 0FFFFFFFFh
0x14008f690  lock xadd [rbx+58h], ecx
0x14008f695  nop
0x14008f696  dec     ecx
0x14008f698  mov     eax, [rbx+5Ch]
0x14008f69b  cmp     ecx, eax
0x14008f69d  jge     loc_14008FCD4
0x14008f6a3  nop
0x14008f6a4  lock inc dword ptr [rbx+58h]
0x14008f6a8  nop
0x14008f6a9  mov     edx, [rbx+4]
0x14008f6ac  jmp     short loc_14008F642
0x14008f6ae  mov     rdi, rax
0x14008f6b1  test    rax, rax
0x14008f6b4  jz      short loc_14008F6A9
0x14008f6b6  mov     [rdi], rbx
0x14008f6b9  lea     rbx, [rdi+10h]
0x14008f6bd  test    rbx, rbx
0x14008f6c0  jz      loc_14008FCFA
0x14008f6c6  mov     [rsp+58h+arg_0], r14
0x14008f6cb  xor     ebp, ebp
0x14008f6cd  lea     r14, [rbx+0D8h]
0x14008f6d4  mov     [rsp+58h+arg_10], r15
0x14008f6d9  test    r14, r14
0x14008f6dc  jz      loc_14008F7B1
0x14008f6e2  mov     r13, [r13+8]
0x14008f6e6  lea     rax, ??_7CmsCompositeBase@@6B@; const CmsCompositeBase::`vftable'
0x14008f6ed  mov     [r14], rax
0x14008f6f0  xor     eax, eax
0x14008f6f2  mov     dword ptr [r14+8], 1000000h
0x14008f6fa  mov     [r14+0Ch], al
0x14008f6fe  mov     [r14+10h], r13
0x14008f702  mov     [r14+18h], al
0x14008f706  mov     [r14+1Ch], eax
0x14008f70a  lock inc dword ptr [r13+8]
0x14008f70f  xor     ecx, ecx
0x14008f711  lea     rax, ??_7CmsCowRootComposite@@6B@; const CmsCowRootComposite::`vftable'
0x14008f718  mov     [r14], rax
0x14008f71b  xorps   xmm0, xmm0
0x14008f71e  mov     eax, [rsp+58h+arg_20]
0x14008f725  xor     edx, edx; Val
0x14008f727  mov     [rdi+150h], rcx
0x14008f72e  mov     r8d, 48h ; 'H'; Size
0x14008f734  mov     [rdi+158h], rcx
0x14008f73b  mov     [rdi+160h], rcx
0x14008f742  mov     [rdi+168h], rcx
0x14008f749  mov     [r14+88h], rcx
0x14008f750  lea     rcx, [r14+20h]; void *
0x14008f754  mov     [r14+0A8h], eax
0x14008f75b  xor     eax, eax
0x14008f75d  mov     [r14+90h], rax
0x14008f764  movups  xmmword ptr [r14+98h], xmm0
0x14008f76c  call    memset
0x14008f771  test    rsi, rsi
0x14008f774  jnz     loc_14008FC92
0x14008f77a  movups  xmm0, xmmword ptr [r12]
0x14008f77f  mov     edx, [rsp+58h+arg_20]
0x14008f786  lea     r8, [r14+40h]; struct SmsChecksumBlob *
0x14008f78a  movups  xmmword ptr [r14+20h], xmm0
0x14008f78f  movups  xmm1, xmmword ptr [r12+10h]
0x14008f795  movups  xmmword ptr [r14+30h], xmm1
0x14008f79a  mov     ecx, [r13+40h]
0x14008f79e  shl     edx, cl; unsigned int
0x14008f7a0  mov     rcx, [r13+0DD0h]; this
0x14008f7a7  call    ?InitChecksumBlob@CmsChecksum@@QEBAXKPEAUSmsChecksumBlob@@@Z; CmsChecksum::InitChecksumBlob(ulong,SmsChecksumBlob *)
0x14008f7ac  xor     r12d, r12d
0x14008f7af  jmp     short loc_14008F7B7
0x14008f7b1  xor     r12d, r12d
0x14008f7b4  mov     r14d, r12d
0x14008f7b7  or      byte ptr [r14+0Ch], 2
0x14008f7bc  lea     rsi, [rbx+188h]
0x14008f7c3  mov     rcx, rsi
0x14008f7c6  mov     edx, 1
0x14008f7cb  call    cs:__imp_ExInitializeAutoExpandPushLock
0x14008f7d2  nop     dword ptr [rax+rax+00h]
0x14008f7d7  mov     [rsi+38h], r12
0x14008f7db  lea     r15, [rbx+218h]
0x14008f7e2  mov     [rdi+1B0h], r12
0x14008f7e9  lea     rcx, [rsi+58h]
0x14008f7ed  mov     [rdi+1C0h], r12
0x14008f7f4  lea     rax, [rcx+10h]
0x14008f7f8  mov     [rsi+34h], r12d
0x14008f7fc  xorps   xmm0, xmm0
0x14008f7ff  mov     [rcx+8], rcx
0x14008f803  mov     [rcx], rcx
0x14008f806  mov     [rax+8], rax
0x14008f80a  mov     [rax], rax
0x14008f80d  mov     [rcx+20h], rbp
0x14008f811  mov     [rcx+28h], r12
0x14008f815  mov     [rcx+30h], r12
0x14008f819  lea     rcx, [r15+250h]
0x14008f820  mov     [rsi+48h], r12
0x14008f824  mov     [rsi+40h], r12
0x14008f828  mov     [rsi+10h], r12
0x14008f82c  mov     [rsi+20h], r12
0x14008f830  mov     [rsi+30h], r12d
0x14008f834  mov     [r15+70h], r12
0x14008f838  movups  xmmword ptr [r15+0E8h], xmm0
0x14008f840  mov     rax, cs:ML_LSN_NULL
0x14008f847  movups  xmmword ptr [r15+0F8h], xmm0
0x14008f84f  mov     [r15+11Ch], bpl
0x14008f856  mov     [r15+118h], r12d
0x14008f85d  mov     [r15+108h], r12
0x14008f864  mov     [r15+11Eh], bpl
0x14008f86b  mov     [r15+110h], r12
0x14008f872  movups  xmmword ptr [r15+128h], xmm0
0x14008f87a  movups  xmmword ptr [r15+138h], xmm0
0x14008f882  mov     [r15+15Ch], bpl
0x14008f889  mov     [r15+158h], r12d
0x14008f890  mov     [r15+148h], r12
0x14008f897  mov     [r15+15Eh], bpl
0x14008f89e  mov     [r15+150h], r12
0x14008f8a5  mov     [r15+16Ch], r12d
0x14008f8ac  mov     [r15+1B0h], r15
0x14008f8b3  mov     [r15+220h], r12
0x14008f8ba  mov     [r15+228h], r12
0x14008f8c1  mov     [r15+230h], rbp
0x14008f8c8  mov     [r15+1D0h], r12
0x14008f8cf  mov     [r15+1C0h], r12
0x14008f8d6  mov     [r15+1D8h], bpl
0x14008f8dd  mov     [r15+1F0h], r12
0x14008f8e4  mov     [r15+1E0h], r12
0x14008f8eb  mov     byte ptr [r15+1F8h], 1
0x14008f8f3  mov     [r15+200h], r12
0x14008f8fa  mov     qword ptr [r15+208h], 1
0x14008f905  mov     [r15+210h], r12
0x14008f90c  mov     [r15+218h], r12
0x14008f913  mov     [r15+240h], rax
0x14008f91a  xor     eax, eax
0x14008f91c  mov     [rcx+10h], eax
0x14008f91f  lea     rax, [rcx+18h]
0x14008f923  mov     [rcx+8], rcx
0x14008f927  mov     [rcx], rcx
0x14008f92a  mov     [rax+8], rax
0x14008f92e  mov     [rax], rax
0x14008f931  mov     [rcx+38h], r12d
0x14008f935  mov     dword ptr [rcx+50h], 3
0x14008f93c  mov     [rcx+60h], r12
0x14008f940  mov     [rcx+48h], r12d
0x14008f944  mov     [rcx+28h], r12
0x14008f948  mov     [r15+2B8h], r12d
0x14008f94f  mov     [r15+2C0h], r12
0x14008f956  movups  xmmword ptr [r15+2D0h], xmm0
0x14008f95e  movups  xmmword ptr [r15+2E0h], xmm0
0x14008f966  mov     [r15+304h], bpl
0x14008f96d  mov     [r15+300h], r12d
0x14008f974  mov     [r15+2F0h], r12
0x14008f97b  mov     [r15+306h], bpl
0x14008f982  mov     [r15+2F8h], r12
0x14008f989  movups  xmmword ptr [r15+310h], xmm0
0x14008f991  movups  xmmword ptr [r15+320h], xmm0
0x14008f999  mov     [r15+344h], bpl
0x14008f9a0  lea     rax, [r15+380h]
0x14008f9a7  mov     [r15+340h], r12d
0x14008f9ae  lea     rcx, [r15+0A8h]; Event
0x14008f9b5  mov     [r15+330h], r12
0x14008f9bc  xor     r8d, r8d; State
0x14008f9bf  mov     [r15+346h], bpl
0x14008f9c6  xor     edx, edx; Type
0x14008f9c8  mov     [r15+338h], r12
0x14008f9cf  mov     [r15+370h], rax
0x14008f9d6  mov     eax, [rsp+58h+var_34]
0x14008f9da  mov     [r15+364h], eax
0x14008f9e1  lea     rax, [r15+78h]
0x14008f9e5  mov     dword ptr [r15+37Ch], 20h ; ' '
0x14008f9f0  movups  xmmword ptr [r15+350h], xmm0
0x14008f9f8  mov     [r15+360h], r12d
0x14008f9ff  mov     [r15+368h], r12
0x14008fa06  mov     [r15+378h], bpl
0x14008fa0d  mov     [r15+3A0h], r12d
0x14008fa14  mov     [r15+3A8h], r12
0x14008fa1b  mov     [r15+98h], r12
0x14008fa22  mov     [r15+0A0h], r12
0x14008fa29  mov     [r15+90h], r12
0x14008fa30  mov     [r15+88h], r15
0x14008fa37  mov     [r15+0D0h], r12
0x14008fa3e  mov     [r15+0D8h], r12
0x14008fa45  mov     [r15+0E0h], r12d
0x14008fa4c  mov     [r15+120h], r12
0x14008fa53  mov     [r15+308h], r12
0x14008fa5a  mov     [r15+168h], r12d
0x14008fa61  mov     [r15+170h], rbp
0x14008fa68  movups  xmmword ptr [r15+178h], xmm0
0x14008fa70  mov     [r15+248h], r12d
0x14008fa77  mov     [r15+160h], r12
0x14008fa7e  mov     [r15+348h], r12
0x14008fa85  mov     [rax+8], rax
0x14008fa89  mov     [rax], rax
0x14008fa8c  lea     rax, [r15+0C0h]
0x14008fa93  mov     [rax+8], rax
0x14008fa97  mov     [rax], rax
0x14008fa9a  or      dword ptr [r15+260h], 1
0x14008faa2  call    cs:__imp_KeInitializeEvent
0x14008faa9  nop     dword ptr [rax+rax+00h]
0x14008faae  xor     r8d, r8d; Wait
0x14008fab1  lea     rcx, [r15+0A8h]; Event
0x14008fab8  xor     edx, edx; Increment
0x14008faba  call    cs:__imp_KeSetEvent
0x14008fac1  nop     dword ptr [rax+rax+00h]
0x14008fac6  lea     rcx, [r15+8]
0x14008faca  mov     edx, 9
0x14008facf  call    cs:__imp_ExInitializeFastResource
0x14008fad6  nop     dword ptr [rax+rax+00h]
0x14008fadb  mov     [r15+70h], r12
0x14008fadf  xor     eax, eax
0x14008fae1  mov     [r15+198h], r12
0x14008fae8  mov     [r15+3C8h], r12
0x14008faef  mov     [r15+2C0h], r12
0x14008faf6  mov     [r15+2B8h], r12d
0x14008fafd  mov     [r15+2C8h], r12d
0x14008fb04  mov     [r15+3B0h], rbp
0x14008fb0b  mov     [r15+3A8h], r12
0x14008fb12  mov     [r15+3A0h], r12d
0x14008fb19  mov     [r15+1A0h], r12
0x14008fb20  mov     qword ptr [rbx+8], 1
0x14008fb28  mov     [rbx+10h], al
0x14008fb2b  mov     rax, [rsp+58h+arg_8]
0x14008fb30  mov     [rbx+18h], rax
0x14008fb34  lea     rax, ??_7CmsBPlusTable@@6B@; const CmsBPlusTable::`vftable'
0x14008fb3b  mov     [rbx], rax
0x14008fb3e  mov     [rbx+30h], r12
0x14008fb42  mov     [rbx+38h], r12
0x14008fb46  mov     [rbx+48h], r12
0x14008fb4a  mov     [rbx+58h], r12
0x14008fb4e  mov     [rbx+60h], r12
0x14008fb52  mov     [rbx+68h], rbp
0x14008fb56  mov     [rbx+70h], r12
0x14008fb5a  mov     [rbx+78h], rbp
0x14008fb5e  mov     [rbx+80h], r12d
0x14008fb65  mov     qword ptr [rbx+88h], 4
0x14008fb70  mov     qword ptr [rbx+90h], 4
0x14008fb7b  mov     qword ptr [rbx+98h], 4
0x14008fb86  mov     qword ptr [rbx+0A0h], 4
0x14008fb91  mov     qword ptr [rbx+0A8h], 4
0x14008fb9c  mov     qword ptr [rbx+0B0h], 4
0x14008fba7  mov     dword ptr [rbx+0B8h], 4
0x14008fbb1  mov     [rbx+0C0h], r12
0x14008fbb8  mov     [rbx+0C8h], r12
0x14008fbbf  mov     rax, [r14+10h]
0x14008fbc3  movzx   ecx, byte ptr [rax+58h]
0x14008fbc7  mov     [rbx+0D0h], cx
0x14008fbce  mov     word ptr [rbx+0D2h], 0FFFFh
0x14008fbd7  mov     [rbx+0D4h], bpl
0x14008fbde  mov     [rbx+0BCh], r12d
0x14008fbe5  mov     [rbx+28h], rsi
0x14008fbe9  mov     [rbx+40h], rbx
0x14008fbed  mov     [rbx+20h], rbx
0x14008fbf1  test    r15, r15
0x14008fbf4  jz      short loc_14008FC04
0x14008fbf6  mov     [rbx+48h], r15
0x14008fbfa  mov     [r15], rbx
0x14008fbfd  mov     [r15+90h], rbx
0x14008fc04  mov     rax, [rbx+18h]
0x14008fc08  mov     r15, [rsp+58h+arg_10]
0x14008fc0d  mov     ecx, [rax+2Ch]
0x14008fc10  movzx   eax, byte ptr [rbx+10h]
0x14008fc14  shr     ecx, 6
0x14008fc17  and     al, 0FBh
0x14008fc19  and     cl, 4
0x14008fc1c  or      cl, al
  ... truncated ...
```
