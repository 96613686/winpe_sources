# NtfsConvertToNonresident

- ea: `0x140158130`
- end: `0x140158b30`
- name: `NtfsConvertToNonresident`
- size: `2560`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, void *)`
- caller_count: `23`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140024338`
- `0x1400c0ca8`
- `0x1400c1808`
- `0x1400c8204`
- `0x1400d2740`
- `0x1400d7558`
- `0x1400da814`
- `0x140109ea8`
- `0x140110248`
- `0x140134aa8`
- `0x140143730`
- `0x1401451bc`
- `0x140151b18`
- `0x1401e7e78`
- `0x1401ea0a8`
- `0x14020d880`
- `0x14025ccec`
- `0x140265594`
- `0x140268658`
- `0x14026fb38`
- `0x14027af58`
- `0x14028a2ec`
- `0x14029135c`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400410a8`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x140125100`
- `0x140143730`
- `0x140150c10`
- `0x1401578f0`
- `0x140158130`
- `0x1401597b8`
- `0x14015a5c0`
- `0x140162110`
- `0x140163fc8`
- `0x14019a768`
- `0x1401e06b0`

## import_xrefs

- `ntoskrnl!CcSetFileSizesEx` at `0x1401583a7`
- `ntoskrnl!CcSetFileSizesEx` at `0x1401583a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140158a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8632`
- `ntoskrnl!ExFreePoolWithTag` at `0x140158a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8632`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401587a8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401587a8`
- `ntoskrnl!CcUnpinData` at `0x1401584a6`
- `ntoskrnl!CcUnpinData` at `0x1401584c2`
- `ntoskrnl!CcUnpinData` at `0x1401584db`
- `ntoskrnl!CcUnpinData` at `0x140158a6b`
- `ntoskrnl!CcUnpinData` at `0x140158a86`
- `ntoskrnl!CcUnpinData` at `0x140158a9f`
- `ntoskrnl!CcUnpinData` at `0x1401584a6`
- `ntoskrnl!CcUnpinData` at `0x1401584c2`
- `ntoskrnl!CcUnpinData` at `0x1401584db`
- `ntoskrnl!CcUnpinData` at `0x140158a6b`
- `ntoskrnl!CcUnpinData` at `0x140158a86`
- `ntoskrnl!CcUnpinData` at `0x140158a9f`
- `ntoskrnl!CcMdlReadComplete` at `0x140158ac3`
- `ntoskrnl!CcMdlReadComplete` at `0x1402a866c`
- `ntoskrnl!CcMdlReadComplete` at `0x140158ac3`
- `ntoskrnl!CcMdlReadComplete` at `0x1402a866c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401587e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401587e7`
- `ntoskrnl!CcMdlRead` at `0x140158704`
- `ntoskrnl!CcMdlRead` at `0x140158704`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140158315`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140158315`
- `ntoskrnl!ExRaiseStatus` at `0x140158966`
- `ntoskrnl!ExRaiseStatus` at `0x140158966`

## pseudocode

```c
void __fastcall NtfsConvertToNonresident(__int64 a1, __int64 a2, __int64 a3, unsigned __int8 a4, _QWORD *a5)
{
  __int64 v5; // rdi
  _QWORD *v9; // rsi
  __int16 *v10; // r14
  bool v11; // al
  USHORT Length; // cx
  unsigned int v13; // r13d
  int v14; // r9d
  __int16 *v15; // rax
  int v16; // r8d
  __int64 v17; // rax
  struct _FILE_OBJECT *v18; // r9
  int v19; // eax
  ULONG v20; // r12d
  int v21; // edi
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  int v25; // r9d
  const void *v26; // rdx
  char *Pointer; // rbx
  __int64 v28; // rax
  int v29; // ecx
  PVOID MappedSystemVa; // rax
  int v31; // ecx
  __int64 v32; // rax
  struct _IO_STATUS_BLOCK v33; // xmm1
  __int64 v34; // rax
  unsigned int v35; // ecx
  int v36; // r8d
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  PIO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-188h]
  ULONG Priority; // [rsp+28h] [rbp-180h]
  int v42; // [rsp+30h] [rbp-178h]
  char v43; // [rsp+60h] [rbp-148h]
  char v44; // [rsp+61h] [rbp-147h]
  char v45[2]; // [rsp+62h] [rbp-146h] BYREF
  __int16 v46; // [rsp+64h] [rbp-144h]
  unsigned int v47; // [rsp+68h] [rbp-140h]
  UNICODE_STRING v48; // [rsp+70h] [rbp-138h] BYREF
  __int64 v49; // [rsp+80h] [rbp-128h]
  PMDL MdlChain; // [rsp+88h] [rbp-120h] BYREF
  unsigned int v51; // [rsp+90h] [rbp-118h]
  int v52; // [rsp+94h] [rbp-114h]
  ULONG v53; // [rsp+98h] [rbp-110h]
  ULONG v54; // [rsp+9Ch] [rbp-10Ch]
  PVOID P; // [rsp+A0h] [rbp-108h]
  __int64 v56; // [rsp+A8h] [rbp-100h]
  _BYTE *v57; // [rsp+B0h] [rbp-F8h]
  __int16 *v58; // [rsp+B8h] [rbp-F0h]
  struct _FILE_OBJECT *v59; // [rsp+C0h] [rbp-E8h]
  __int64 v60; // [rsp+C8h] [rbp-E0h]
  _BYTE v61[96]; // [rsp+D0h] [rbp-D8h] BYREF
  struct _IO_STATUS_BLOCK v62; // [rsp+130h] [rbp-78h] BYREF
  __int64 v63; // [rsp+140h] [rbp-68h]
  _BYTE v64[32]; // [rsp+148h] [rbp-60h] BYREF

  v5 = a4;
  v56 = a2;
  v9 = a5;
  v57 = a5;
  P = 0;
  memset(v61, 0, 0x58u);
  v10 = (__int16 *)*(unsigned int *)a3;
  v54 = *(_DWORD *)a3;
  v46 = *(_WORD *)(a3 + 12);
  v49 = 0;
  v58 = 0;
  MdlChain = 0;
  v44 = 0;
  v45[0] = 0;
  v11 = (_BYTE)v5 && (_DWORD)v10 == 128;
  v43 = v11;
  LOBYTE(v5) = 0;
  v48 = 0;
  if ( *(_QWORD *)(a1 + 400) && (_DWORD)v10 == 128 && !v11 )
  {
    v43 = 1;
    LOBYTE(v5) = 1;
  }
  Length = 2 * *(unsigned __int8 *)(a3 + 9);
  v48.Length = Length;
  v48.MaximumLength = Length;
  v48.Buffer = (PWSTR)(a3 + *(unsigned __int16 *)(a3 + 10));
  if ( a5 )
  {
LABEL_7:
    v13 = Length;
    v51 = Length;
    v15 = NtfsCreateScb(a1, a2, (int)v10, &v48, 0, 0, v45);
    v10 = v15;
    v58 = v15;
    if ( !(_BYTE)v5 )
      goto LABEL_8;
    goto LABEL_76;
  }
  v9 = v61;
  v57 = v61;
  v44 = 1;
  v13 = a2 + 8;
  if ( (unsigned __int8)NtfsLookupInFileRecord(a1, a2, a2 + 8, (unsigned int)v10, &v48, 0, 0, 0, 0, v61) )
  {
    Length = v48.Length;
    goto LABEL_7;
  }
  a3 = 0x37000317D9LL;
  NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 202713, v14, a2 + 8, a2, 0);
  NtfsAttachRepairInfoPriv(a1, 256, 0, 0x37000317D9LL);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 202713);
  v15 = (__int16 *)NtfsRaiseStatusInternal(a1, -1073741566, (int)a2 + 8, a2, 202713);
LABEL_76:
  if ( (*((_DWORD *)v15 + 50) & 0x200) != 0 )
  {
    v36 = *((_DWORD *)v15 + 8);
    if ( v36 != *(_DWORD *)(a3 + 16) )
    {
      LODWORD(IoStatus) = 0;
      NtfsChangeAttributeValue(a1, a2, v36, 0, (SIZE_T)IoStatus, 1, 1, 1, 1, v9);
    }
  }
LABEL_8:
  NtfsUpdateScbFromAttribute(a1, v10, a3);
  *((_DWORD *)v10 + 128) |= 0x4000u;
  v17 = *((_QWORD *)v10 + 62);
  if ( v17 )
    *(_QWORD *)(v17 + 96) = a1;
  if ( *((_DWORD *)v10 + 64) == 128
    && (v43 || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v10 + 36) + 16LL), 0)) )
  {
    v28 = *(_QWORD *)(a2 + 96);
    v20 = *(_DWORD *)(a3 + 16);
    v21 = *(_DWORD *)(v28 + 484) & (v20 + *(_DWORD *)(v28 + 480));
    v47 = v21;
    v52 = v21;
    v13 += v21;
    v51 = v13;
    v53 = v20;
    if ( v20 )
    {
      if ( *(_BYTE *)(a1 + 32) == 4 )
      {
        v31 = *(_DWORD *)(a1 + 12);
        if ( (v31 & 0x100) == 0 )
        {
          v32 = *(_QWORD *)(a1 + 112);
          if ( v32 )
          {
            if ( (*(_DWORD *)(v32 + 16) & 2) == 0 && *((_QWORD *)v10 + 2) )
            {
              *(_DWORD *)(a1 + 12) = v31 | 0x100;
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 202809);
              goto LABEL_26;
            }
          }
        }
      }
    }
    v43 = 1;
  }
  else
  {
    v47 = 0;
    v52 = 0;
    LOBYTE(v16) = 1;
    NtfsCreateInternalAttributeStream(a1, (_DWORD)v10, v16, 0, (__int64)L",.", 0);
    v18 = (struct _FILE_OBJECT *)*((_QWORD *)v10 + 35);
    v59 = v18;
    if ( v18 && v18->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v10 + 36) + 16LL) )
      goto LABEL_70;
    while ( 1 )
    {
      if ( *(_QWORD *)(*((_QWORD *)v10 + 36) + 24LL) )
      {
        if ( (*((_DWORD *)v10 + 128) & 1) != 0 )
        {
          v33 = *(struct _IO_STATUS_BLOCK *)(v10 + 12);
          v62 = v33;
          v63 = *((_QWORD *)v10 + 5);
          v62.Pointer = (char *)v33.Pointer - *(_QWORD *)(*((_QWORD *)v10 + 24) + 1952LL);
          v62.Information = v33.Information - *(_QWORD *)(*((_QWORD *)v10 + 24) + 1952LL);
          NtfsSetCcFileSizes(v18, v10, &v62);
        }
        else
        {
          v19 = CcSetFileSizesEx(v18, (PCC_FILE_SIZES)v10 + 1);
          if ( v19 < 0 && *((_DWORD *)v10 + 55) )
            ExRaiseStatus(v19);
          if ( NtfsStatusDebugFlags
            && v19
            && v19 != 294
            && (unsigned int)(v19 - 298) > 1
            && (unsigned int)v19 < 0xFFFFFFED
            && v19 != -1073741608
            && v19 != -1073741802
            && v19 != -1073741807
            && (unsigned int)(v19 + 2147483643) > 1
            && v19 != 259 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)v19, 333485);
          }
        }
      }
      v20 = *((_DWORD *)v10 + 10);
      v53 = v20;
      if ( !v20 )
        break;
      v62 = 0;
      if ( *(_BYTE *)(a1 + 32) != 4
        || (v29 = *(_DWORD *)(a1 + 12), (v29 & 0x100) != 0)
        || (v34 = *(_QWORD *)(a1 + 112)) == 0
        || (*(_DWORD *)(v34 + 16) & 2) != 0
        || !*((_QWORD *)v10 + 2) )
      {
        CcMdlRead(*((PFILE_OBJECT *)v10 + 35), &NtfsLarge0, v20, &MdlChain, &v62);
        if ( (MdlChain->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlChain->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
        v49 = (__int64)MappedSystemVa;
        v60 = (__int64)MappedSystemVa;
        if ( !MappedSystemVa )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 202901);
          NtfsRaiseStatusInternal(a1, -1073741670, 0, v56, 202901);
          goto LABEL_55;
        }
        break;
      }
      v35 = v29 & 0xFFFFFFFE;
      *(_DWORD *)(a1 + 12) = v35;
      *(_DWORD *)(a1 + 12) = v35 | 0x100;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 202888);
LABEL_70:
      NtfsCreateInternalAttributeStream(a1, (_DWORD)v10, 0, 0, 0, 0);
      v18 = (struct _FILE_OBJECT *)*((_QWORD *)v10 + 35);
      v59 = v18;
    }
  }
  if ( v13 > 8 )
  {
    P = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v13, 0x4146744Eu);
    v5 = (__int64)P;
    v62.Pointer = P;
  }
  else
  {
    v5 = (__int64)v64;
    v62.Pointer = v64;
  }
  v48.Buffer = (PWSTR)(v5 + v47);
  memmove(v48.Buffer, (const void *)(a3 + *(unsigned __int16 *)(a3 + 10)), v48.Length);
  if ( v43 )
    goto LABEL_33;
  while ( 1 )
  {
    a3 = v56;
    NtfsDeleteAttributeRecord(a1, v56, 15, v9);
    Priority = v20;
    v20 = v54;
    NtfsCreateNonresidentWithValue(a1, a3, v54, (unsigned int)&v48, v49, Priority, v46, (_DWORD)v10, 1, 1, (__int64)v9);
    LOBYTE(v21) = v44;
    if ( v44 )
      break;
    v22 = (void *)v9[2];
    if ( v22 )
    {
      CcUnpinData(v22);
      v9[2] = 0;
    }
LABEL_26:
    v23 = (void *)v9[5];
    if ( v23 )
    {
      CcUnpinData(v23);
      v9[5] = 0;
    }
    v24 = (void *)v9[9];
    if ( v24 )
    {
      CcUnpinData(v24);
      v9[9] = 0;
    }
    memset(v9, 0, 0x58u);
    v13 = a3 + 8;
    LOBYTE(v42) = 0;
    if ( (unsigned __int8)NtfsLookupInFileRecord(a1, a3, a3 + 8, v20, &v48, 0, v42, 0, 0, v9) )
      break;
    v5 = 0x38000318FCLL;
    NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 203004, v25, a3 + 8, a3, 0);
    NtfsAttachRepairInfoPriv(a1, 256, 0, 0x38000318FCLL);
    if ( NtfsStatusDebugFlags )
LABEL_55:
      NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 203004);
    NtfsRaiseStatusInternal(a1, -1073741566, v13, a3, 203004);
LABEL_33:
    v49 = v5;
    v60 = v5;
    if ( v20 )
    {
      v26 = (const void *)(a3 + *(unsigned __int16 *)(a3 + 20));
      Pointer = (char *)v62.Pointer;
      memmove(v62.Pointer, v26, v20);
      memset(&Pointer[v20], 0, v13 - v48.Length - v20);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( (_BYTE)v21 )
  {
    v37 = (void *)v9[2];
    if ( v37 )
    {
      CcUnpinData(v37);
      v9[2] = 0;
    }
    v38 = (void *)v9[5];
    if ( v38 )
    {
      CcUnpinData(v38);
      v9[5] = 0;
    }
    v39 = (void *)v9[9];
    if ( v39 )
    {
      CcUnpinData(v39);
      v9[9] = 0;
    }
  }
  if ( MdlChain )
    CcMdlReadComplete(*((PFILE_OBJECT *)v10 + 35), MdlChain);
}

```

## disassembly

```asm
0x140158130  push    rbx
0x140158132  push    rsi
0x140158133  push    rdi
0x140158134  push    r12
0x140158136  push    r13
0x140158138  push    r14
0x14015813a  push    r15
0x14015813c  sub     rsp, 170h
0x140158143  mov     rax, cs:__security_cookie
0x14015814a  xor     rax, rsp
0x14015814d  mov     [rsp+1A8h+var_40], rax
0x140158155  movzx   edi, r9b
0x140158159  mov     rbx, r8
0x14015815c  mov     r12, rdx
0x14015815f  mov     [rsp+1A8h+var_100], rdx
0x140158167  mov     r15, rcx
0x14015816a  mov     rsi, [rsp+1A8h+arg_20]
0x140158172  mov     [rsp+1A8h+var_F8], rsi
0x14015817a  xor     r13d, r13d
0x14015817d  mov     [rsp+1A8h+P], r13
0x140158185  xor     edx, edx; Val
0x140158187  mov     r8d, 58h ; 'X'; Size
0x14015818d  lea     rcx, [rsp+1A8h+var_D8]; void *
0x140158195  call    memset
0x14015819a  mov     r14d, [rbx]
0x14015819d  mov     [rsp+1A8h+var_10C], r14d
0x1401581a5  movzx   eax, word ptr [rbx+0Ch]
0x1401581a9  mov     [rsp+1A8h+var_144], ax
0x1401581ae  mov     [rsp+1A8h+var_128], r13
0x1401581b6  mov     [rsp+1A8h+var_F0], r13
0x1401581be  mov     [rsp+1A8h+MdlChain], r13
0x1401581c6  mov     [rsp+1A8h+var_147], r13b
0x1401581cb  mov     [rsp+1A8h+var_146], r13b
0x1401581d0  test    dil, dil
0x1401581d3  jnz     loc_140158AF3
0x1401581d9  xor     al, al
0x1401581db  mov     [rsp+1A8h+var_148], al
0x1401581df  xor     dil, dil
0x1401581e2  xorps   xmm0, xmm0
0x1401581e5  movups  [rsp+1A8h+var_138], xmm0
0x1401581ea  cmp     [r15+190h], r13
0x1401581f1  jnz     loc_140158B0E
0x1401581f7  movzx   ecx, byte ptr [rbx+9]
0x1401581fb  add     cx, cx
0x1401581fe  mov     word ptr [rsp+1A8h+var_138], cx
0x140158203  mov     word ptr [rsp+1A8h+var_138+2], cx
0x140158208  movzx   eax, word ptr [rbx+0Ah]
0x14015820c  add     rax, rbx
0x14015820f  mov     qword ptr [rsp+1A8h+var_138+8], rax
0x140158214  test    rsi, rsi
0x140158217  jnz     short loc_14015827C
0x140158219  lea     rsi, [rsp+1A8h+var_D8]
0x140158221  mov     [rsp+1A8h+var_F8], rsi
0x140158229  mov     [rsp+1A8h+var_147], 1
0x14015822e  lea     r13, [r12+8]
0x140158233  lea     rax, [rsp+1A8h+var_D8]
0x14015823b  mov     [rsp+1A8h+var_160], rax
0x140158240  xor     eax, eax
0x140158242  mov     dword ptr [rsp+1A8h+var_168], eax
0x140158246  mov     qword ptr [rsp+1A8h+var_170], rax
0x14015824b  mov     [rsp+1A8h+var_178], al
0x14015824f  mov     qword ptr [rsp+1A8h+Priority], rax
0x140158254  lea     rax, [rsp+1A8h+var_138]
0x140158259  mov     [rsp+1A8h+IoStatus], rax
0x14015825e  mov     r9d, r14d
0x140158261  mov     r8, r13
0x140158264  mov     rdx, r12
0x140158267  mov     rcx, r15
0x14015826a  call    NtfsLookupInFileRecord
0x14015826f  test    al, al
0x140158271  jz      loc_140158973
0x140158277  movzx   ecx, word ptr [rsp+1A8h+var_138]
0x14015827c  movzx   r13d, cx
0x140158280  mov     [rsp+1A8h+var_118], r13d
0x140158288  lea     rax, [rsp+1A8h+var_146]
0x14015828d  mov     qword ptr [rsp+1A8h+var_178], rax
0x140158292  mov     qword ptr [rsp+1A8h+Priority], 0
0x14015829b  mov     byte ptr [rsp+1A8h+IoStatus], 0
0x1401582a0  lea     r9, [rsp+1A8h+var_138]
0x1401582a5  mov     r8d, r14d
0x1401582a8  mov     rdx, r12
0x1401582ab  mov     rcx, r15
0x1401582ae  call    NtfsCreateScb
0x1401582b3  mov     r14, rax
0x1401582b6  mov     [rsp+1A8h+var_F0], rax
0x1401582be  test    dil, dil
0x1401582c1  jnz     loc_1401589E9
0x1401582c7  mov     r8, rbx
0x1401582ca  mov     rdx, r14
0x1401582cd  mov     rcx, r15
0x1401582d0  call    NtfsUpdateScbFromAttribute
0x1401582d5  or      dword ptr [r14+200h], 4000h
0x1401582e0  mov     rax, [r14+1F0h]
0x1401582e7  test    rax, rax
0x1401582ea  jz      short loc_1401582F0
0x1401582ec  mov     [rax+60h], r15
0x1401582f0  cmp     dword ptr [r14+100h], 80h
0x1401582fb  jnz     short loc_140158329
0x1401582fd  cmp     [rsp+1A8h+var_148], 0
0x140158302  jnz     loc_140158675
0x140158308  mov     rcx, [r14+120h]
0x14015830f  add     rcx, 10h; SectionPointer
0x140158313  xor     edx, edx; NewFileSize
0x140158315  call    cs:__imp_MmCanFileBeTruncated
0x14015831c  nop     dword ptr [rax+rax+00h]
0x140158321  test    al, al
0x140158323  jz      loc_140158675
0x140158329  xor     eax, eax
0x14015832b  mov     [rsp+1A8h+var_140], eax
0x14015832f  mov     [rsp+1A8h+var_114], eax
0x140158336  mov     qword ptr [rsp+1A8h+Priority], rax
0x14015833b  lea     rax, asc_140062070; ",."
0x140158342  mov     [rsp+1A8h+IoStatus], rax
0x140158347  xor     r9d, r9d
0x14015834a  mov     r8b, 1
0x14015834d  mov     rdx, r14
0x140158350  mov     rcx, r15
0x140158353  call    NtfsCreateInternalAttributeStream
0x140158358  mov     r9, [r14+118h]
0x14015835f  mov     [rsp+1A8h+var_E8], r9
0x140158367  test    r9, r9
0x14015836a  jz      short loc_140158381
0x14015836c  mov     rax, [r14+120h]
0x140158373  add     rax, 10h
0x140158377  cmp     [r9+28h], rax
0x14015837b  jnz     loc_14015891E
0x140158381  mov     rax, [r14+120h]
0x140158388  mov     rcx, [rax+18h]
0x14015838c  test    rcx, rcx
0x14015838f  jz      short loc_1401583CC
0x140158391  mov     eax, [r14+200h]
0x140158398  mov     rcx, r9; FileObject
0x14015839b  test    al, 1
0x14015839d  jnz     loc_140158867
0x1401583a3  lea     rdx, [r14+18h]; FileSizes
0x1401583a7  call    cs:__imp_CcSetFileSizesEx
0x1401583ae  nop     dword ptr [rax+rax+00h]
0x1401583b3  mov     edx, eax
0x1401583b5  test    eax, eax
0x1401583b7  js      loc_14015894F
0x1401583bd  movzx   eax, cs:NtfsStatusDebugFlags
0x1401583c4  test    al, al
0x1401583c6  jnz     loc_1401585F8
0x1401583cc  mov     r12d, [r14+28h]
0x1401583d0  mov     [rsp+1A8h+var_110], r12d
0x1401583d8  test    r12d, r12d
0x1401583db  jnz     loc_1401586BE
0x1401583e1  cmp     r13d, 8
0x1401583e5  ja      loc_140158796
0x1401583eb  lea     rdi, [rsp+1A8h+var_60]
0x1401583f3  mov     qword ptr [rsp+1A8h+var_78], rdi
0x1401583fb  mov     ecx, [rsp+1A8h+var_140]
0x1401583ff  add     rcx, rdi; void *
0x140158402  mov     qword ptr [rsp+1A8h+var_138+8], rcx
0x140158407  movzx   r8d, word ptr [rsp+1A8h+var_138]; Size
0x14015840d  movzx   edx, word ptr [rbx+0Ah]
0x140158411  add     rdx, rbx; Src
0x140158414  call    memmove
0x140158419  cmp     [rsp+1A8h+var_148], 0
0x14015841e  jnz     loc_1401585A1
0x140158424  mov     r9, rsi
0x140158427  mov     r8d, 0Fh
0x14015842d  mov     rbx, [rsp+1A8h+var_100]
0x140158435  mov     rdx, rbx
0x140158438  mov     rcx, r15
0x14015843b  call    NtfsDeleteAttributeRecord
0x140158440  mov     [rsp+1A8h+var_158], rsi
0x140158445  mov     byte ptr [rsp+1A8h+var_160], 1
0x14015844a  mov     [rsp+1A8h+var_168], 1
0x14015844f  mov     qword ptr [rsp+1A8h+var_170], r14
0x140158454  movzx   eax, [rsp+1A8h+var_144]
0x140158459  mov     word ptr [rsp+1A8h+var_178], ax
0x14015845e  mov     [rsp+1A8h+Priority], r12d
0x140158463  mov     rax, [rsp+1A8h+var_128]
0x14015846b  mov     [rsp+1A8h+IoStatus], rax
0x140158470  lea     r9, [rsp+1A8h+var_138]
0x140158475  mov     r12d, [rsp+1A8h+var_10C]
0x14015847d  mov     r8d, r12d
0x140158480  mov     rdx, rbx
0x140158483  mov     rcx, r15
0x140158486  call    NtfsCreateNonresidentWithValue
0x14015848b  movzx   edi, [rsp+1A8h+var_147]
0x140158490  test    dil, dil
0x140158493  jnz     loc_140158A3B
0x140158499  mov     rcx, [rsi+10h]; Bcb
0x14015849d  test    rcx, rcx
0x1401584a0  jz      loc_14015885F
0x1401584a6  call    cs:__imp_CcUnpinData
0x1401584ad  nop     dword ptr [rax+rax+00h]
0x1401584b2  xor     r13d, r13d
0x1401584b5  mov     [rsi+10h], r13
0x1401584b9  mov     rcx, [rsi+28h]; Bcb
0x1401584bd  test    rcx, rcx
0x1401584c0  jz      short loc_1401584D2
0x1401584c2  call    cs:__imp_CcUnpinData
0x1401584c9  nop     dword ptr [rax+rax+00h]
0x1401584ce  mov     [rsi+28h], r13
0x1401584d2  mov     rcx, [rsi+48h]; Bcb
0x1401584d6  test    rcx, rcx
0x1401584d9  jz      short loc_1401584EB
0x1401584db  call    cs:__imp_CcUnpinData
0x1401584e2  nop     dword ptr [rax+rax+00h]
0x1401584e7  mov     [rsi+48h], r13
0x1401584eb  xor     edx, edx; Val
0x1401584ed  mov     r8d, 58h ; 'X'; Size
0x1401584f3  mov     rcx, rsi; void *
0x1401584f6  call    memset
0x1401584fb  lea     r13, [rbx+8]
0x1401584ff  mov     [rsp+1A8h+var_160], rsi
0x140158504  xor     eax, eax
0x140158506  mov     dword ptr [rsp+1A8h+var_168], eax
0x14015850a  mov     qword ptr [rsp+1A8h+var_170], rax
0x14015850f  mov     [rsp+1A8h+var_178], al
0x140158513  mov     qword ptr [rsp+1A8h+Priority], rax
0x140158518  lea     rax, [rsp+1A8h+var_138]
0x14015851d  mov     [rsp+1A8h+IoStatus], rax
0x140158522  mov     r9d, r12d
0x140158525  mov     r8, r13
0x140158528  mov     rdx, rbx
0x14015852b  mov     rcx, r15
0x14015852e  call    NtfsLookupInFileRecord
0x140158533  test    al, al
0x140158535  jnz     loc_140158A3B
0x14015853b  mov     edx, 2
0x140158540  mov     [rsp+1A8h+var_178], al
0x140158544  mov     qword ptr [rsp+1A8h+Priority], rbx
0x140158549  mov     [rsp+1A8h+IoStatus], r13
0x14015854e  mov     rdi, 38000318FCh
0x140158558  mov     r8, rdi
0x14015855b  mov     rcx, r15
0x14015855e  call    NtfsAttachCorruption_BadOrOrphanFRS
0x140158563  mov     r9, rdi
0x140158566  xor     r8d, r8d
0x140158569  mov     edx, 100h
0x14015856e  mov     rcx, r15
0x140158571  call    NtfsAttachRepairInfoPriv
0x140158576  movzx   eax, cs:NtfsStatusDebugFlags
0x14015857d  test    al, al
0x14015857f  jnz     loc_14015877E
0x140158585  mov     [rsp+1A8h+IoStatus], 318FCh
0x14015858e  mov     r9, rbx
0x140158591  mov     r8, r13
0x140158594  mov     edx, 0C0000102h
0x140158599  mov     rcx, r15
0x14015859c  call    NtfsRaiseStatusInternal
0x1401585a1  mov     rax, rdi
0x1401585a4  mov     [rsp+1A8h+var_128], rax
0x1401585ac  mov     [rsp+1A8h+var_E0], rax
0x1401585b4  test    r12d, r12d
0x1401585b7  jz      loc_140158424
0x1401585bd  mov     edi, r12d
0x1401585c0  movzx   edx, word ptr [rbx+14h]
0x1401585c4  add     rdx, rbx; Src
0x1401585c7  mov     r8d, r12d; Size
0x1401585ca  mov     rbx, qword ptr [rsp+1A8h+var_78]
0x1401585d2  mov     rcx, rbx; void *
0x1401585d5  call    memmove
0x1401585da  movzx   eax, word ptr [rsp+1A8h+var_138]
0x1401585df  sub     r13d, eax
0x1401585e2  sub     r13d, r12d
0x1401585e5  mov     r8d, r13d; Size
0x1401585e8  lea     rcx, [rdi+rbx]; void *
0x1401585ec  xor     edx, edx; Val
0x1401585ee  call    memset
0x1401585f3  jmp     loc_140158424
0x1401585f8  test    edx, edx
0x1401585fa  jz      loc_1401583CC
0x140158600  cmp     edx, 126h
0x140158606  jz      loc_1401583CC
0x14015860c  lea     eax, [rdx-12Ah]
0x140158612  cmp     eax, 1
0x140158615  jbe     loc_1401583CC
0x14015861b  cmp     edx, 0FFFFFFEDh
0x14015861e  jnb     loc_1401583CC
0x140158624  cmp     edx, 0C00000D8h
0x14015862a  jz      loc_1401583CC
0x140158630  cmp     edx, 0C0000016h
0x140158636  jz      loc_1401583CC
0x14015863c  cmp     edx, 0C0000011h
0x140158642  jz      loc_1401583CC
0x140158648  lea     eax, [rdx+7FFFFFFBh]
0x14015864e  cmp     eax, 1
0x140158651  jbe     loc_1401583CC
0x140158657  cmp     edx, 103h
0x14015865d  jz      loc_1401583CC
0x140158663  xor     ecx, ecx
0x140158665  mov     r8d, 516ADh
0x14015866b  call    NtfsStatusTraceAndDebugInternal
0x140158670  jmp     loc_1401583CC
0x140158675  mov     rax, [r12+60h]
0x14015867a  mov     r12d, [rbx+10h]
0x14015867e  mov     edi, [rax+1E0h]
0x140158684  add     edi, r12d
0x140158687  and     edi, [rax+1E4h]
0x14015868d  mov     [rsp+1A8h+var_140], edi
0x140158691  mov     [rsp+1A8h+var_114], edi
0x140158698  add     r13d, edi
0x14015869b  mov     [rsp+1A8h+var_118], r13d
0x1401586a3  mov     [rsp+1A8h+var_110], r12d
0x1401586ab  test    r12d, r12d
  ... truncated ...
```
