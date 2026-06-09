# CmsVolume::ScrubMetaData(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)

- ea: `0x14012885c`
- end: `0x14012915f`
- name: `?ScrubMetaData@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z`
- size: `2307`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14011adf4`

## callees

- `0x14011ac78`
- `0x14012885c`
- `0x140129168`
- `0x140129218`
- `0x1401292a4`
- `0x140136200`
- `0x14013e4e4`
- `0x140140d24`
- `0x1401423cc`
- `0x140144268`
- `0x140168c04`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x140128950`
- `ntoskrnl!PsIsThreadTerminating` at `0x1401289fb`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128abb`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128b78`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128c35`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128cf2`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128daf`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128e5a`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128f1b`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128fcb`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012907b`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128950`
- `ntoskrnl!PsIsThreadTerminating` at `0x1401289fb`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128abb`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128b78`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128c35`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128cf2`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128daf`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128e5a`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128f1b`
- `ntoskrnl!PsIsThreadTerminating` at `0x140128fcb`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012907b`

## pseudocode

```c
__int64 __fastcall CmsVolume::ScrubMetaData(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        struct _SmsCancelScrub *a3,
        struct _SmsScrubContext *a4)
{
  unsigned int v5; // r9d
  unsigned int v9; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  CmsObjectTable *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // eax
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  int v49; // eax
  CmsVolumeContainer *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // eax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  int v64; // eax
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  int v69; // eax
  unsigned int v70; // r9d
  unsigned int v71; // r9d
  unsigned int v72; // r9d
  unsigned int v73; // r9d
  unsigned int v74; // r9d
  unsigned int v75; // r9d

  v5 = *((unsigned __int8 *)a4 + 4);
  v9 = 0;
  if ( v5 <= 8 )
  {
    if ( v5 == 8 )
    {
LABEL_58:
      if ( *((_QWORD *)this + 407) )
      {
        *((_BYTE *)a4 + 841) = 8;
        v40 = CmsAllocator::Scrub(*((CmsAllocator **)this + 407), a2, a3, a4);
        *((_BYTE *)a4 + 841) = 0;
        v9 = v40;
        if ( v40 < 0 )
          return v9;
      }
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4, v41, v42, v43)
        || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 9;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v44 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v44;
      *((_DWORD *)a4 + 194) = v44;
      goto LABEL_67;
    }
    if ( v5 && (v10 = v5 - 2) != 0 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return v9;
LABEL_49:
              if ( *((_QWORD *)this + 408) )
              {
                *((_BYTE *)a4 + 841) = 7;
                v35 = CmsAllocator::Scrub(*((CmsAllocator **)this + 408), a2, a3, a4);
                *((_BYTE *)a4 + 841) = 0;
                v9 = v35;
                if ( v35 < 0 )
                  return v9;
              }
              if ( *((int *)a4 + 2) <= 0
                || **(_BYTE **)a3
                || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(a4, v36, v37, v38)
                || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
              {
                return (unsigned int)-2147483643;
              }
              *((_DWORD *)a4 + 3) = 16;
              *((_WORD *)a4 + 2) = 8;
              *(_OWORD *)((char *)a4 + 104) = 0;
              v39 = *((_DWORD *)a4 + 3);
              *((_DWORD *)a4 + 190) = v39;
              *((_DWORD *)a4 + 194) = v39;
              goto LABEL_58;
            }
LABEL_40:
            if ( *((_QWORD *)this + 406) )
            {
              *((_BYTE *)a4 + 841) = 6;
              v30 = CmsAllocator::Scrub(*((CmsAllocator **)this + 406), a2, a3, a4);
              *((_BYTE *)a4 + 841) = 0;
              v9 = v30;
              if ( v30 < 0 )
                return v9;
            }
            if ( *((int *)a4 + 2) <= 0
              || **(_BYTE **)a3
              || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
              || PsIsThreadTerminating(KeGetCurrentThread())
              || (unsigned __int8)MsScrubContextFoundError(a4, v31, v32, v33)
              || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
            {
              return (unsigned int)-2147483643;
            }
            *((_DWORD *)a4 + 3) = 16;
            *((_WORD *)a4 + 2) = 7;
            *(_OWORD *)((char *)a4 + 104) = 0;
            v34 = *((_DWORD *)a4 + 3);
            *((_DWORD *)a4 + 190) = v34;
            *((_DWORD *)a4 + 194) = v34;
            goto LABEL_49;
          }
LABEL_31:
          if ( *((_QWORD *)this + 423) )
          {
            *((_BYTE *)a4 + 841) = 5;
            v25 = CmsFailoverBPlusTable::ScrubTable(**((CmsFailoverBPlusTable ***)this + 423), a2, a3, a4);
            *((_BYTE *)a4 + 841) = 0;
            v9 = v25;
            if ( v25 < 0 )
              return v9;
          }
          if ( *((int *)a4 + 2) <= 0
            || **(_BYTE **)a3
            || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(a4, v26, v27, v28)
            || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
          {
            return (unsigned int)-2147483643;
          }
          *((_DWORD *)a4 + 3) = 16;
          *((_WORD *)a4 + 2) = 6;
          *(_OWORD *)((char *)a4 + 104) = 0;
          v29 = *((_DWORD *)a4 + 3);
          *((_DWORD *)a4 + 190) = v29;
          *((_DWORD *)a4 + 194) = v29;
          goto LABEL_40;
        }
      }
    }
    else
    {
      if ( (*((_DWORD *)a4 + 198) & 1) == 0 )
      {
        *((_BYTE *)a4 + 841) = 2;
        v9 = CmsVolume::ScrubSuperblock(this, a2, a3, a4);
        *((_BYTE *)a4 + 841) = 0;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v15 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v15;
      *((_DWORD *)a4 + 194) = v15;
      if ( (v9 & 0x80000000) != 0 )
        return v9;
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4, v16, v17, v18)
        || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v19 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v19;
      *((_DWORD *)a4 + 194) = v19;
    }
    v20 = (CmsObjectTable *)*((_QWORD *)this + 418);
    if ( v20 )
      v9 = CmsObjectTable::Scrub(v20, a2, a3, a4);
    if ( (v9 & 0x80000000) != 0 )
      return v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4, v21, v22, v23)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 5;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v24 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v24;
    *((_DWORD *)a4 + 194) = v24;
    goto LABEL_31;
  }
  v70 = v5 - 9;
  if ( v70 )
  {
    v71 = v70 - 1;
    if ( v71 )
    {
      v72 = v71 - 1;
      if ( v72 )
      {
        v73 = v72 - 1;
        if ( v73 )
        {
          v74 = v73 - 1;
          if ( v74 )
          {
            v75 = v74 - 1;
            if ( v75 )
            {
              if ( v75 != 1 )
                return v9;
              goto LABEL_111;
            }
LABEL_103:
            *((_BYTE *)a4 + 841) = 14;
            v65 = CmsVolume::ScrubUpcaseTable(this, a2, a3, a4);
            *((_BYTE *)a4 + 841) = 0;
            v9 = v65;
            if ( v65 < 0 )
              return v9;
            if ( *((int *)a4 + 2) > 0
              && !**(_BYTE **)a3
              && (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) == 0
              && !PsIsThreadTerminating(KeGetCurrentThread())
              && !(unsigned __int8)MsScrubContextFoundError(a4, v66, v67, v68)
              && *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) < *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
            {
              *((_DWORD *)a4 + 3) = 16;
              *((_WORD *)a4 + 2) = 15;
              *(_OWORD *)((char *)a4 + 104) = 0;
              v69 = *((_DWORD *)a4 + 3);
              *((_DWORD *)a4 + 190) = v69;
              *((_DWORD *)a4 + 194) = v69;
LABEL_111:
              if ( *((_QWORD *)this + 425) )
              {
                *((_BYTE *)a4 + 841) = 15;
                v9 = CmsTrashTable::Scrub(*((CmsTrashTable **)this + 425), a2, a3, a4);
                *((_BYTE *)a4 + 841) = 0;
              }
              return v9;
            }
            return (unsigned int)-2147483643;
          }
LABEL_95:
          *((_BYTE *)a4 + 841) = 13;
          v60 = CmsVolume::ScrubVolumeRedoLog(this, a2, a3, a4);
          *((_BYTE *)a4 + 841) = 0;
          v9 = v60;
          if ( v60 < 0 )
            return v9;
          if ( *((int *)a4 + 2) <= 0
            || **(_BYTE **)a3
            || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(a4, v61, v62, v63)
            || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
          {
            return (unsigned int)-2147483643;
          }
          *((_DWORD *)a4 + 3) = 16;
          *((_WORD *)a4 + 2) = 14;
          *(_OWORD *)((char *)a4 + 104) = 0;
          v64 = *((_DWORD *)a4 + 3);
          *((_DWORD *)a4 + 190) = v64;
          *((_DWORD *)a4 + 194) = v64;
          goto LABEL_103;
        }
LABEL_86:
        if ( *((_QWORD *)this + 410) )
        {
          *((_BYTE *)a4 + 841) = 12;
          v55 = CmsAllocator::Scrub(*(CmsAllocator **)(*((_QWORD *)this + 410) + 8LL), a2, a3, a4);
          *((_BYTE *)a4 + 841) = 0;
          v9 = v55;
          if ( v55 < 0 )
            return v9;
        }
        if ( *((int *)a4 + 2) <= 0
          || **(_BYTE **)a3
          || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
          || PsIsThreadTerminating(KeGetCurrentThread())
          || (unsigned __int8)MsScrubContextFoundError(a4, v56, v57, v58)
          || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
        {
          return (unsigned int)-2147483643;
        }
        *((_DWORD *)a4 + 3) = 16;
        *((_WORD *)a4 + 2) = 13;
        *(_OWORD *)((char *)a4 + 104) = 0;
        v59 = *((_DWORD *)a4 + 3);
        *((_DWORD *)a4 + 190) = v59;
        *((_DWORD *)a4 + 194) = v59;
        goto LABEL_95;
      }
    }
    goto LABEL_76;
  }
LABEL_67:
  if ( *((_QWORD *)this + 413) )
  {
    *((_BYTE *)a4 + 841) = 9;
    v45 = CmsBlockRefcount::Scrub(*((CmsBlockRefcount **)this + 413), a2, a3, a4);
    *((_BYTE *)a4 + 841) = 0;
    v9 = v45;
    if ( v45 < 0 )
      return v9;
  }
  if ( *((int *)a4 + 2) <= 0
    || **(_BYTE **)a3
    || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
    || PsIsThreadTerminating(KeGetCurrentThread())
    || (unsigned __int8)MsScrubContextFoundError(a4, v46, v47, v48)
    || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
  {
    return (unsigned int)-2147483643;
  }
  *((_DWORD *)a4 + 3) = 16;
  *((_WORD *)a4 + 2) = 10;
  *(_OWORD *)((char *)a4 + 104) = 0;
  v49 = *((_DWORD *)a4 + 3);
  *((_DWORD *)a4 + 190) = v49;
  *((_DWORD *)a4 + 194) = v49;
LABEL_76:
  v50 = (CmsVolumeContainer *)*((_QWORD *)this + 409);
  if ( v50 )
    v9 = CmsVolumeContainer::Scrub(v50, a2, a3, a4);
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4, v51, v52, v53)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 12;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v54 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v54;
    *((_DWORD *)a4 + 194) = v54;
    goto LABEL_86;
  }
  return v9;
}

```

## disassembly

```asm
0x14012885c  push    rbx
0x14012885e  push    rbp
0x14012885f  push    rsi
0x140128860  push    rdi
0x140128861  push    r12
0x140128863  push    r14
0x140128865  push    r15
0x140128867  sub     rsp, 20h
0x14012886b  xor     r15d, r15d
0x14012886e  mov     rdi, r9
0x140128871  movzx   r9d, byte ptr [r9+4]
0x140128876  mov     rsi, r8
0x140128879  mov     r14, rdx
0x14012887c  mov     rbp, rcx
0x14012887f  mov     ebx, r15d
0x140128882  lea     r12d, [r15+10h]
0x140128886  cmp     r9d, 8
0x14012888a  ja      loc_140129104
0x140128890  jz      loc_140128C8E
0x140128896  test    r9d, r9d
0x140128899  jz      short loc_1401288D8
0x14012889b  sub     r9d, 2
0x14012889f  jz      short loc_1401288D8
0x1401288a1  sub     r9d, 1
0x1401288a5  jz      loc_1401289A9
0x1401288ab  sub     r9d, 1
0x1401288af  jz      loc_1401289A9
0x1401288b5  sub     r9d, 1
0x1401288b9  jz      loc_140128A54
0x1401288bf  sub     r9d, 1
0x1401288c3  jz      loc_140128B14
0x1401288c9  cmp     r9d, 1
0x1401288cd  jz      loc_140128BD1
0x1401288d3  jmp     loc_14012914D
0x1401288d8  mov     eax, [rdi+318h]
0x1401288de  test    al, 1
0x1401288e0  jnz     short loc_1401288FA
0x1401288e2  mov     r9, rdi; struct _SmsScrubContext *
0x1401288e5  mov     byte ptr [rdi+349h], 2
0x1401288ec  call    ?ScrubSuperblock@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsVolume::ScrubSuperblock(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1401288f1  mov     ebx, eax
0x1401288f3  mov     [rdi+349h], r15b
0x1401288fa  mov     [rdi+0Ch], r12d
0x1401288fe  xorps   xmm0, xmm0
0x140128901  mov     word ptr [rdi+4], 3
0x140128907  movups  xmmword ptr [rdi+68h], xmm0
0x14012890b  mov     ecx, [rdi+0Ch]
0x14012890e  mov     [rdi+2F8h], ecx
0x140128914  mov     [rdi+308h], ecx
0x14012891a  test    ebx, ebx
0x14012891c  js      loc_14012914D
0x140128922  cmp     [rdi+8], r15d
0x140128926  jle     loc_140129148
0x14012892c  mov     rax, [rsi]
0x14012892f  cmp     [rax], r15b
0x140128932  jnz     loc_140129148
0x140128938  mov     rax, [rsi+8]
0x14012893c  mov     ecx, [rax]
0x14012893e  test    [rsi+10h], ecx
0x140128941  jnz     loc_140129148
0x140128947  mov     rcx, gs:188h; Thread
0x140128950  call    cs:__imp_PsIsThreadTerminating
0x140128957  nop     dword ptr [rax+rax+00h]
0x14012895c  test    al, al
0x14012895e  jnz     loc_140129148
0x140128964  mov     rcx, rdi
0x140128967  call    MsScrubContextFoundError
0x14012896c  test    al, al
0x14012896e  jnz     loc_140129148
0x140128974  mov     rcx, [rdi+358h]
0x14012897b  movzx   eax, word ptr [rcx+6]
0x14012897f  cmp     [rcx+4], ax
0x140128983  jnb     loc_140129148
0x140128989  mov     [rdi+0Ch], r12d
0x14012898d  xorps   xmm0, xmm0
0x140128990  mov     word ptr [rdi+4], 3
0x140128996  movups  xmmword ptr [rdi+68h], xmm0
0x14012899a  mov     eax, [rdi+0Ch]
0x14012899d  mov     [rdi+2F8h], eax
0x1401289a3  mov     [rdi+308h], eax
0x1401289a9  mov     rcx, [rbp+0D10h]; this
0x1401289b0  test    rcx, rcx
0x1401289b3  jz      short loc_1401289C5
0x1401289b5  mov     r9, rdi; struct _SmsScrubContext *
0x1401289b8  mov     r8, rsi; struct _SmsCancelScrub *
0x1401289bb  mov     rdx, r14; struct CmsTransactionContext *
0x1401289be  call    ?Scrub@CmsObjectTable@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsObjectTable::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1401289c3  mov     ebx, eax
0x1401289c5  test    ebx, ebx
0x1401289c7  js      loc_14012914D
0x1401289cd  cmp     [rdi+8], r15d
0x1401289d1  jle     loc_140129148
0x1401289d7  mov     rax, [rsi]
0x1401289da  cmp     [rax], r15b
0x1401289dd  jnz     loc_140129148
0x1401289e3  mov     rax, [rsi+8]
0x1401289e7  mov     ecx, [rax]
0x1401289e9  test    [rsi+10h], ecx
0x1401289ec  jnz     loc_140129148
0x1401289f2  mov     rcx, gs:188h; Thread
0x1401289fb  call    cs:__imp_PsIsThreadTerminating
0x140128a02  nop     dword ptr [rax+rax+00h]
0x140128a07  test    al, al
0x140128a09  jnz     loc_140129148
0x140128a0f  mov     rcx, rdi
0x140128a12  call    MsScrubContextFoundError
0x140128a17  test    al, al
0x140128a19  jnz     loc_140129148
0x140128a1f  mov     rcx, [rdi+358h]
0x140128a26  movzx   eax, word ptr [rcx+6]
0x140128a2a  cmp     [rcx+4], ax
0x140128a2e  jnb     loc_140129148
0x140128a34  mov     [rdi+0Ch], r12d
0x140128a38  xorps   xmm0, xmm0
0x140128a3b  mov     word ptr [rdi+4], 5
0x140128a41  movups  xmmword ptr [rdi+68h], xmm0
0x140128a45  mov     eax, [rdi+0Ch]
0x140128a48  mov     [rdi+2F8h], eax
0x140128a4e  mov     [rdi+308h], eax
0x140128a54  cmp     [rbp+0D38h], r15
0x140128a5b  jz      short loc_140128A8D
0x140128a5d  mov     byte ptr [rdi+349h], 5
0x140128a64  mov     r9, rdi; struct _SmsScrubContext *
0x140128a67  mov     rcx, [rbp+0D38h]
0x140128a6e  mov     r8, rsi; struct _SmsCancelScrub *
0x140128a71  mov     rdx, r14; struct CmsTransactionContext *
0x140128a74  mov     rcx, [rcx]; this
0x140128a77  call    ?ScrubTable@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsFailoverBPlusTable::ScrubTable(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140128a7c  mov     [rdi+349h], r15b
0x140128a83  mov     ebx, eax
0x140128a85  test    eax, eax
0x140128a87  js      loc_14012914D
0x140128a8d  cmp     [rdi+8], r15d
0x140128a91  jle     loc_140129148
0x140128a97  mov     rax, [rsi]
0x140128a9a  cmp     [rax], r15b
0x140128a9d  jnz     loc_140129148
0x140128aa3  mov     rax, [rsi+8]
0x140128aa7  mov     ecx, [rax]
0x140128aa9  test    [rsi+10h], ecx
0x140128aac  jnz     loc_140129148
0x140128ab2  mov     rcx, gs:188h; Thread
0x140128abb  call    cs:__imp_PsIsThreadTerminating
0x140128ac2  nop     dword ptr [rax+rax+00h]
0x140128ac7  test    al, al
0x140128ac9  jnz     loc_140129148
0x140128acf  mov     rcx, rdi
0x140128ad2  call    MsScrubContextFoundError
0x140128ad7  test    al, al
0x140128ad9  jnz     loc_140129148
0x140128adf  mov     rcx, [rdi+358h]
0x140128ae6  movzx   eax, word ptr [rcx+6]
0x140128aea  cmp     [rcx+4], ax
0x140128aee  jnb     loc_140129148
0x140128af4  mov     [rdi+0Ch], r12d
0x140128af8  xorps   xmm0, xmm0
0x140128afb  mov     word ptr [rdi+4], 6
0x140128b01  movups  xmmword ptr [rdi+68h], xmm0
0x140128b05  mov     eax, [rdi+0Ch]
0x140128b08  mov     [rdi+2F8h], eax
0x140128b0e  mov     [rdi+308h], eax
0x140128b14  cmp     [rbp+0CB0h], r15
0x140128b1b  jz      short loc_140128B4A
0x140128b1d  mov     byte ptr [rdi+349h], 6
0x140128b24  mov     r9, rdi; struct _SmsScrubContext *
0x140128b27  mov     rcx, [rbp+0CB0h]; this
0x140128b2e  mov     r8, rsi; struct _SmsCancelScrub *
0x140128b31  mov     rdx, r14; struct CmsTransactionContext *
0x140128b34  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140128b39  mov     [rdi+349h], r15b
0x140128b40  mov     ebx, eax
0x140128b42  test    eax, eax
0x140128b44  js      loc_14012914D
0x140128b4a  cmp     [rdi+8], r15d
0x140128b4e  jle     loc_140129148
0x140128b54  mov     rax, [rsi]
0x140128b57  cmp     [rax], r15b
0x140128b5a  jnz     loc_140129148
0x140128b60  mov     rax, [rsi+8]
0x140128b64  mov     ecx, [rax]
0x140128b66  test    [rsi+10h], ecx
0x140128b69  jnz     loc_140129148
0x140128b6f  mov     rcx, gs:188h; Thread
0x140128b78  call    cs:__imp_PsIsThreadTerminating
0x140128b7f  nop     dword ptr [rax+rax+00h]
0x140128b84  test    al, al
0x140128b86  jnz     loc_140129148
0x140128b8c  mov     rcx, rdi
0x140128b8f  call    MsScrubContextFoundError
0x140128b94  test    al, al
0x140128b96  jnz     loc_140129148
0x140128b9c  mov     rcx, [rdi+358h]
0x140128ba3  movzx   eax, word ptr [rcx+6]
0x140128ba7  cmp     [rcx+4], ax
0x140128bab  jnb     loc_140129148
0x140128bb1  mov     [rdi+0Ch], r12d
0x140128bb5  xorps   xmm0, xmm0
0x140128bb8  mov     word ptr [rdi+4], 7
0x140128bbe  movups  xmmword ptr [rdi+68h], xmm0
0x140128bc2  mov     eax, [rdi+0Ch]
0x140128bc5  mov     [rdi+2F8h], eax
0x140128bcb  mov     [rdi+308h], eax
0x140128bd1  cmp     [rbp+0CC0h], r15
0x140128bd8  jz      short loc_140128C07
0x140128bda  mov     byte ptr [rdi+349h], 7
0x140128be1  mov     r9, rdi; struct _SmsScrubContext *
0x140128be4  mov     rcx, [rbp+0CC0h]; this
0x140128beb  mov     r8, rsi; struct _SmsCancelScrub *
0x140128bee  mov     rdx, r14; struct CmsTransactionContext *
0x140128bf1  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140128bf6  mov     [rdi+349h], r15b
0x140128bfd  mov     ebx, eax
0x140128bff  test    eax, eax
0x140128c01  js      loc_14012914D
0x140128c07  cmp     [rdi+8], r15d
0x140128c0b  jle     loc_140129148
0x140128c11  mov     rax, [rsi]
0x140128c14  cmp     [rax], r15b
0x140128c17  jnz     loc_140129148
0x140128c1d  mov     rax, [rsi+8]
0x140128c21  mov     ecx, [rax]
0x140128c23  test    [rsi+10h], ecx
0x140128c26  jnz     loc_140129148
0x140128c2c  mov     rcx, gs:188h; Thread
0x140128c35  call    cs:__imp_PsIsThreadTerminating
0x140128c3c  nop     dword ptr [rax+rax+00h]
0x140128c41  test    al, al
0x140128c43  jnz     loc_140129148
0x140128c49  mov     rcx, rdi
0x140128c4c  call    MsScrubContextFoundError
0x140128c51  test    al, al
0x140128c53  jnz     loc_140129148
0x140128c59  mov     rcx, [rdi+358h]
0x140128c60  movzx   eax, word ptr [rcx+6]
0x140128c64  cmp     [rcx+4], ax
0x140128c68  jnb     loc_140129148
0x140128c6e  mov     [rdi+0Ch], r12d
0x140128c72  xorps   xmm0, xmm0
0x140128c75  mov     word ptr [rdi+4], 8
0x140128c7b  movups  xmmword ptr [rdi+68h], xmm0
0x140128c7f  mov     eax, [rdi+0Ch]
0x140128c82  mov     [rdi+2F8h], eax
0x140128c88  mov     [rdi+308h], eax
0x140128c8e  cmp     [rbp+0CB8h], r15
0x140128c95  jz      short loc_140128CC4
0x140128c97  mov     byte ptr [rdi+349h], 8
0x140128c9e  mov     r9, rdi; struct _SmsScrubContext *
0x140128ca1  mov     rcx, [rbp+0CB8h]; this
0x140128ca8  mov     r8, rsi; struct _SmsCancelScrub *
0x140128cab  mov     rdx, r14; struct CmsTransactionContext *
0x140128cae  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140128cb3  mov     [rdi+349h], r15b
0x140128cba  mov     ebx, eax
0x140128cbc  test    eax, eax
0x140128cbe  js      loc_14012914D
0x140128cc4  cmp     [rdi+8], r15d
0x140128cc8  jle     loc_140129148
0x140128cce  mov     rax, [rsi]
0x140128cd1  cmp     [rax], r15b
0x140128cd4  jnz     loc_140129148
0x140128cda  mov     rax, [rsi+8]
0x140128cde  mov     ecx, [rax]
0x140128ce0  test    [rsi+10h], ecx
0x140128ce3  jnz     loc_140129148
0x140128ce9  mov     rcx, gs:188h; Thread
0x140128cf2  call    cs:__imp_PsIsThreadTerminating
0x140128cf9  nop     dword ptr [rax+rax+00h]
0x140128cfe  test    al, al
0x140128d00  jnz     loc_140129148
0x140128d06  mov     rcx, rdi
0x140128d09  call    MsScrubContextFoundError
0x140128d0e  test    al, al
0x140128d10  jnz     loc_140129148
0x140128d16  mov     rcx, [rdi+358h]
0x140128d1d  movzx   eax, word ptr [rcx+6]
0x140128d21  cmp     [rcx+4], ax
0x140128d25  jnb     loc_140129148
0x140128d2b  mov     [rdi+0Ch], r12d
0x140128d2f  xorps   xmm0, xmm0
0x140128d32  mov     word ptr [rdi+4], 9
0x140128d38  movups  xmmword ptr [rdi+68h], xmm0
0x140128d3c  mov     eax, [rdi+0Ch]
0x140128d3f  mov     [rdi+2F8h], eax
0x140128d45  mov     [rdi+308h], eax
0x140128d4b  cmp     [rbp+0CE8h], r15
0x140128d52  jz      short loc_140128D81
0x140128d54  mov     byte ptr [rdi+349h], 9
0x140128d5b  mov     r9, rdi; struct _SmsScrubContext *
0x140128d5e  mov     rcx, [rbp+0CE8h]; this
0x140128d65  mov     r8, rsi; struct _SmsCancelScrub *
0x140128d68  mov     rdx, r14; struct CmsTransactionContext *
0x140128d6b  call    ?Scrub@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsBlockRefcount::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140128d70  mov     [rdi+349h], r15b
0x140128d77  mov     ebx, eax
0x140128d79  test    eax, eax
0x140128d7b  js      loc_14012914D
0x140128d81  cmp     [rdi+8], r15d
0x140128d85  jle     loc_140129148
0x140128d8b  mov     rax, [rsi]
0x140128d8e  cmp     [rax], r15b
  ... truncated ...
```
