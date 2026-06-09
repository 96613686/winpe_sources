# ArenaAllocatorBase<InPlaceFreeListPolicy>::RealAlloc(unsigned __int64)

- ea: `0x18000fb60`
- end: `0x1800101e2`
- name: `?RealAlloc@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@AEAAPEAD_K@Z`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f910`

## callees

- `0x180004d60`
- `0x1800052bc`
- `0x18000ef2c`
- `0x18000f7c4`
- `0x18000fb60`
- `0x180010e48`
- `0x18006a5f0`
- `0x1801b10e0`
- `0x180255a38`
- `0x180255c94`
- `0x18035e010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18000fcd3`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000fcd3`
- `KERNEL32!InterlockedPopEntrySList` at `0x18001011b`
- `KERNEL32!InterlockedPopEntrySList` at `0x18001011b`

## pseudocode

```c
_QWORD *__fastcall ArenaAllocatorBase<InPlaceFreeListPolicy>::RealAlloc(__int64 a1, unsigned __int64 a2)
{
  _QWORD *result; // rax
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r15
  PageAllocator **v7; // r12
  void (*v8)(void); // rax
  char *v9; // rbx
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  _QWORD *v15; // r9
  _QWORD *v16; // r8
  unsigned __int64 v17; // r10
  _QWORD *v18; // r11
  int v19; // r9d
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  int v23; // ebx
  _QWORD *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rax
  unsigned __int64 *v31; // r9
  _QWORD **v32; // r8
  struct PageSegment *v33; // r13
  int v34; // edx
  _QWORD *v35; // rcx
  signed __int64 v36; // rax
  _QWORD *v37; // rcx
  unsigned __int64 *v38; // rcx
  signed __int64 v39; // rax
  __int64 v40; // rbp
  unsigned __int64 v41; // r14
  bool v42; // zf
  unsigned int v43; // r11d
  unsigned int v44; // eax
  unsigned int v45; // r9d
  unsigned int v46; // edx
  unsigned int v47; // r10d
  int v48; // edx
  unsigned int v49; // r8d
  __int64 v50; // r9
  PSLIST_ENTRY v51; // rax
  int Next; // ebx
  struct Segment *v53; // rax
  unsigned __int64 *v54; // r8
  unsigned __int64 *v55; // [rsp+28h] [rbp-50h]
  PSLIST_ENTRY v56; // [rsp+28h] [rbp-50h]
  struct PageSegment *v57; // [rsp+30h] [rbp-48h] BYREF

  result = *(_QWORD **)(a1 + 48);
  v4 = a2;
  v5 = *(_QWORD *)(a1 + 64) - (_QWORD)result;
  if ( v5 >= a2 )
  {
    *(_QWORD *)(a1 + 48) = (char *)result + a2;
    return result;
  }
  if ( a2 > *(_QWORD *)(a1 + 72) )
  {
LABEL_4:
    v6 = v4 + 32;
    if ( v4 + 32 < v4 )
    {
      v6 = -1;
LABEL_6:
      v7 = (PageAllocator **)(a1 + 40);
      goto LABEL_7;
    }
    if ( v4 + 4143 < v4 + 32 || v4 == -4144 )
      goto LABEL_6;
    v40 = *(_QWORD *)(a1 + 40);
    v7 = (PageAllocator **)(a1 + 40);
    v41 = (v4 + 4143) >> 12;
    v57 = 0;
    if ( v41 > *(unsigned int *)(v40 + 88) )
    {
      v53 = PageAllocator::AllocSegment((PageAllocator *)v40, v41);
      v33 = v53;
      if ( !v53 )
        goto LABEL_7;
      v9 = (char *)*((_QWORD *)v53 + 2);
      v5 = *((_QWORD *)v53 + 3) - *((unsigned int *)v53 + 8);
      *(_QWORD *)v9 = v5;
      goto LABEL_27;
    }
    v42 = *(_DWORD *)(v40 + 152) == 0;
    *(_BYTE *)(v40 + 139) = 1;
    if ( v42 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v40 + 200));
    if ( *(_QWORD *)(v40 + 104) < (unsigned __int64)(unsigned int)v41 )
    {
      v31 = (unsigned __int64 *)(v40 + 8);
    }
    else
    {
      v38 = (unsigned __int64 *)(v40 + 8);
      v54 = (unsigned __int64 *)(v40 + 8);
LABEL_59:
      while ( 1 )
      {
        v54 = (unsigned __int64 *)*v54;
        v55 = v54;
        if ( v54 == v38 )
          break;
        v43 = *((_DWORD *)v54 + 18);
        v33 = (struct PageSegment *)(v54 + 2);
        if ( v43 >= (unsigned int)v41 )
        {
          v44 = *((_DWORD *)v54 + 16);
          v45 = -1;
          v42 = !_BitScanForward(&v46, v44);
          if ( !v42 )
            v45 = v46;
          v47 = 0xFFFFFFFF >> (32 - v41);
          while ( 1 )
          {
            v54 = v55;
            v38 = (unsigned __int64 *)(v40 + 8);
            if ( v45 == -1 )
              break;
            a2 = *((_QWORD *)v33 + 3) - *((unsigned int *)v33 + 8) - v45;
            v38 = (unsigned __int64 *)(v40 + 8);
            if ( a2 < (unsigned int)v41 )
              break;
            if ( (_DWORD)v41 == 1 || (a2 = v47 << v45, (v44 & (v47 << v45)) == (_DWORD)a2) )
            {
              v38 = (unsigned __int64 *)(v40 + 8);
              *((_DWORD *)v33 + 12) = v44 & ~(v47 << v45);
              *((_DWORD *)v33 + 14) = v43 - v41;
              v9 = (char *)(*((_QWORD *)v33 + 2) + (v45 << 12));
              if ( !v9 )
                goto LABEL_59;
              v5 = (unsigned int)((_DWORD)v41 << 12);
              *(_QWORD *)(v40 + 160) += v5;
              v39 = _InterlockedExchangeAdd64(&qword_18043D988, v5);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              {
                McTemplateU0x_EventWriteTransfer(v5, a2, v39 + v5);
                v54 = v55;
              }
              if ( !*((_DWORD *)v33 + 14) )
              {
                *(_QWORD *)v54[1] = *v54;
                *(_QWORD *)(*v54 + 8) = v54[1];
                v5 = *(_QWORD *)(v40 + 24);
                v54[1] = *(_QWORD *)(v5 + 8);
                *v54 = v5;
                **(_QWORD **)(v5 + 8) = v54;
                *(_QWORD *)(v5 + 8) = v54;
                *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
                goto LABEL_23;
              }
              goto LABEL_50;
            }
            v48 = -1 << (v45 + 1);
            v45 = -1;
            v42 = !_BitScanForward(&v49, v44 & v48);
            if ( !v42 )
              v45 = v49;
          }
        }
      }
      if ( (_DWORD)v41 != 1 || !*(_QWORD *)(v40 + 128) )
        goto LABEL_73;
      v51 = InterlockedPopEntrySList(*(PSLIST_HEADER *)(v40 + 128));
      v56 = v51;
      if ( !v51 )
      {
        v38 = (unsigned __int64 *)(v40 + 8);
LABEL_73:
        v31 = v38;
        goto LABEL_36;
      }
      v33 = (struct PageSegment *)*((_QWORD *)&v51->Next + 1);
      Next = (int)v51[1].Next;
      v57 = v33;
      if ( Next == 1 )
      {
        v9 = (char *)v51;
        *v51 = 0;
        v51[1] = 0;
      }
      else
      {
        v23 = Next - 1;
        LODWORD(v51[1].Next) = v23;
        InterlockedPushEntrySList(*(PSLIST_HEADER *)(v40 + 128), v51);
        v9 = (char *)v56 + (unsigned int)(v23 << 12);
      }
      if ( v9 )
        goto LABEL_23;
      v31 = (unsigned __int64 *)(v40 + 8);
    }
LABEL_36:
    v32 = *(_QWORD ***)(v40 + 40);
    if ( v32 == (_QWORD **)(v40 + 40) )
    {
      v9 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v40, v41, &v57);
      if ( v9 )
      {
        v33 = v57;
LABEL_23:
        if ( !*(_DWORD *)(v40 + 152) )
          *(_DWORD *)(v40 + 240) = 0;
        v7 = (PageAllocator **)(a1 + 40);
        if ( !v9 )
        {
LABEL_7:
          v8 = *(void (**)(void))(a1 + 8);
          if ( !v8 || (v8(), (v9 = (char *)PageAllocator::AllocPagesForBytes(*v7, v6)) == 0) )
          {
            v10 = v4 + 16;
            if ( v4 + 16 < v4 )
              v10 = -1;
            v11 = (_QWORD *)AllocateArray<HeapAllocator,char,1>(v5, a2, v10);
            if ( v11 )
            {
              v11[1] = v4;
              *v11 = *(_QWORD *)(a1 + 32);
              *(_QWORD *)(a1 + 32) = v11;
              v15 = v11 + 2;
              *(_DWORD *)(a1 + 80) = 2;
            }
            else
            {
              if ( *(_QWORD *)a1 )
                (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))a1)(v13, v12, v14, 0);
              return 0;
            }
            return v15;
          }
LABEL_28:
          v24 = v9 + 16;
          *((_QWORD *)v9 + 4) = v9;
          v25 = (*(_QWORD *)v9 << 12) - 48LL;
          *((_QWORD *)v9 + 5) = 0;
          *((_QWORD *)v9 + 3) = v25;
          ++*(_DWORD *)(a1 + 80);
          v26 = *(_QWORD *)(a1 + 16);
          if ( v26 )
          {
            *(_QWORD *)(v26 + 24) = *(_QWORD *)(a1 + 48) - v26 - 32;
            v27 = *(_DWORD *)(a1 + 64) - *(_DWORD *)(a1 + 48);
            if ( v27 >= 0x10 || *(_BYTE *)(a1 + 56) )
            {
              v28 = v27;
              v29 = *(_QWORD *)(a1 + 72);
              if ( v29 <= v28 )
                v29 = v28;
              *(_QWORD *)(a1 + 72) = v29;
            }
            else
            {
              v37 = *(_QWORD **)(a1 + 16);
              *(_QWORD *)(a1 + 16) = *v37;
              *v37 = *(_QWORD *)(a1 + 24);
              *(_QWORD *)(a1 + 24) = v37;
            }
          }
          v30 = *(_QWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 48) = &v9[*((_QWORD *)v9 + 5) + 48];
          *(_QWORD *)(a1 + 64) = (char *)v24 + *((_QWORD *)v9 + 3) + 32;
          *v24 = v30;
          v15 = *(_QWORD **)(a1 + 48);
          *(_QWORD *)(a1 + 16) = v24;
          *(_QWORD *)(a1 + 48) = (char *)v15 + v4;
          return v15;
        }
        *(_QWORD *)v9 = v41;
LABEL_27:
        *((_QWORD *)v9 + 1) = v33;
        if ( v9 )
          goto LABEL_28;
        goto LABEL_7;
      }
      v33 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)v40);
      if ( !v33 )
      {
        v33 = v57;
        v9 = 0;
        goto LABEL_23;
      }
    }
    else
    {
      v33 = (struct PageSegment *)(v32 + 2);
      v34 = *(_DWORD *)(v40 + 88);
      *v32[1] = *v32;
      (*v32)[1] = v32[1];
      if ( (_DWORD)v41 == v34 )
        v35 = *(_QWORD **)(v40 + 24);
      else
        v35 = (_QWORD *)*v31;
      v32[1] = (_QWORD *)v35[1];
      *v32 = v35;
      *(_QWORD *)v35[1] = v32;
      v35[1] = v32;
    }
    v9 = PageSegment::AllocPages(v33, v41);
    v5 = (unsigned int)((_DWORD)v41 << 12);
    *(_QWORD *)(v40 + 160) += v5;
    v36 = _InterlockedExchangeAdd64(&qword_18043D988, v5);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(v5, a2, v36 + v5);
LABEL_50:
    *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
    goto LABEL_23;
  }
  v16 = *(_QWORD **)(a1 + 16);
  v17 = 0;
  v18 = v16;
  v19 = 10;
  a2 = *v16;
  while ( 1 )
  {
    v20 = *(_QWORD *)(a2 + 24);
    v5 = *(_QWORD *)(a2 + 8) - v20;
    if ( v5 >= v4 )
      break;
    if ( v17 <= v5 )
      v17 = *(_QWORD *)(a2 + 8) - v20;
    if ( --v19 )
    {
      v18 = (_QWORD *)a2;
      a2 = *(_QWORD *)a2;
      if ( a2 )
        continue;
    }
    goto LABEL_4;
  }
  v15 = (_QWORD *)(v20 + a2 + 32);
  *(_QWORD *)(a2 + 24) = v4 + v20;
  v21 = *(_QWORD *)(a1 + 72);
  if ( v5 == v21 || v17 > v21 )
    *(_QWORD *)(a1 + 72) = v17;
  v22 = v5 - v4;
  if ( v22 <= v16[1] - v16[3] )
  {
    if ( v22 < 0x10 && !*(_BYTE *)(a1 + 56) )
    {
      *v18 = *(_QWORD *)a2;
      *(_QWORD *)a2 = *(_QWORD *)(a1 + 24);
      result = v15;
      *(_QWORD *)(a1 + 24) = a2;
      return result;
    }
    return v15;
  }
  *v18 = *(_QWORD *)a2;
  ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(a1, a2, v16, v15);
  return (_QWORD *)v50;
}

```

## disassembly

```asm
0x18000fb60  mov     r11, rsp
0x18000fb63  mov     [r11+10h], rdx
0x18000fb67  mov     [r11+8], rcx
0x18000fb6b  push    rsi
0x18000fb6c  push    rdi
0x18000fb6d  sub     rsp, 68h
0x18000fb71  mov     rax, [rcx+30h]
0x18000fb75  mov     rdi, rcx
0x18000fb78  mov     rcx, [rcx+40h]
0x18000fb7c  mov     rsi, rdx
0x18000fb7f  sub     rcx, rax
0x18000fb82  cmp     rcx, rdx
0x18000fb85  jb      short loc_18000FB96
0x18000fb87  lea     rcx, [rax+rdx]
0x18000fb8b  mov     [rdi+30h], rcx
0x18000fb8f  add     rsp, 68h
0x18000fb93  pop     rdi
0x18000fb94  pop     rsi
0x18000fb95  retn
0x18000fb96  cmp     rsi, [rdi+48h]
0x18000fb9a  jbe     loc_18000FC3D
0x18000fba0  mov     [rsp+78h+arg_10], rbx
0x18000fba8  mov     [rsp+78h+var_18], rbp
0x18000fbad  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000fbb4  mov     [rsp+78h+var_20], r12
0x18000fbb9  mov     [rsp+78h+var_28], r13
0x18000fbbe  mov     [rsp+78h+var_30], r14
0x18000fbc3  mov     [rsp+78h+var_38], r15
0x18000fbc8  lea     r15, [rsi+20h]
0x18000fbcc  cmp     r15, rsi
0x18000fbcf  jnb     loc_18000FF3D
0x18000fbd5  mov     r15, rbp
0x18000fbd8  lea     r12, [rdi+28h]
0x18000fbdc  mov     rax, [rdi+8]
0x18000fbe0  test    rax, rax
0x18000fbe3  jz      short loc_18000FC02
0x18000fbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbea  mov     rcx, [r12]; this
0x18000fbee  mov     rdx, r15; unsigned __int64
0x18000fbf1  call    ?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z; PageAllocator::AllocPagesForBytes(unsigned __int64)
0x18000fbf6  mov     rbx, rax
0x18000fbf9  test    rax, rax
0x18000fbfc  jnz     loc_18000FD14
0x18000fc02  lea     r8, [rsi+10h]
0x18000fc06  cmp     r8, rsi
0x18000fc09  cmovb   r8, rbp
0x18000fc0d  call    ??$AllocateArray@UHeapAllocator@@D$00@@YAPEADPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,char,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18000fc12  mov     r9, rax
0x18000fc15  test    rax, rax
0x18000fc18  jz      loc_1800101CD
0x18000fc1e  mov     [rax+8], rsi
0x18000fc22  mov     rax, [rdi+20h]
0x18000fc26  mov     [r9], rax
0x18000fc29  mov     [rdi+20h], r9
0x18000fc2d  add     r9, 10h
0x18000fc31  mov     dword ptr [rdi+50h], 2
0x18000fc38  jmp     loc_18000FDA3
0x18000fc3d  mov     r8, [rdi+10h]
0x18000fc41  xor     r10d, r10d
0x18000fc44  mov     r11, r8
0x18000fc47  mov     r9d, 0Ah
0x18000fc4d  mov     rdx, [r8]
0x18000fc50  mov     rax, [rdx+18h]
0x18000fc54  mov     rcx, [rdx+8]
0x18000fc58  sub     rcx, rax
0x18000fc5b  cmp     rcx, rsi
0x18000fc5e  jb      loc_180010089
0x18000fc64  lea     r9, [rdx+20h]
0x18000fc68  add     r9, rax
0x18000fc6b  add     rax, rsi
0x18000fc6e  mov     [rdx+18h], rax
0x18000fc72  mov     rax, [rdi+48h]
0x18000fc76  cmp     rcx, rax
0x18000fc79  jnz     loc_18001007B
0x18000fc7f  mov     [rdi+48h], r10
0x18000fc83  mov     rax, [r8+8]
0x18000fc87  sub     rcx, rsi
0x18000fc8a  sub     rax, [r8+18h]
0x18000fc8e  cmp     rcx, rax
0x18000fc91  ja      loc_180010102
0x18000fc97  cmp     rcx, 10h
0x18000fc9b  jnb     loc_18000FDC4
0x18000fca1  cmp     byte ptr [rdi+38h], 0
0x18000fca5  jnz     loc_18000FDC4
0x18000fcab  mov     rax, [rdx]
0x18000fcae  mov     [r11], rax
0x18000fcb1  mov     rax, [rdi+18h]
0x18000fcb5  mov     [rdx], rax
0x18000fcb8  mov     rax, r9
0x18000fcbb  mov     [rdi+18h], rdx
0x18000fcbf  jmp     loc_18000FB8F
0x18000fcc4  dec     ebx
0x18000fcc6  mov     rdx, rax; ListEntry
0x18000fcc9  mov     [rax+10h], ebx
0x18000fccc  mov     rcx, [rbp+80h]; ListHead
0x18000fcd3  call    cs:__imp_InterlockedPushEntrySList
0x18000fcd9  shl     ebx, 0Ch
0x18000fcdc  add     rbx, [rsp+78h+var_50]
0x18000fce1  test    rbx, rbx
0x18000fce4  jz      loc_18000FDCC
0x18000fcea  cmp     dword ptr [rbp+98h], 0
0x18000fcf1  jz      loc_1800100AE
0x18000fcf7  lea     r12, [rdi+28h]
0x18000fcfb  test    rbx, rbx
0x18000fcfe  jz      loc_1800101C1
0x18000fd04  mov     [rbx], r14
0x18000fd07  mov     [rbx+8], r13
0x18000fd0b  test    rbx, rbx
0x18000fd0e  jz      loc_180010164
0x18000fd14  lea     rdx, [rbx+10h]
0x18000fd18  mov     [rdx+10h], rbx
0x18000fd1c  mov     rax, [rbx]
0x18000fd1f  shl     rax, 0Ch
0x18000fd23  sub     rax, 30h ; '0'
0x18000fd27  mov     qword ptr [rdx+18h], 0
0x18000fd2f  mov     [rdx+8], rax
0x18000fd33  inc     dword ptr [rdi+50h]
0x18000fd36  mov     rcx, [rdi+10h]
0x18000fd3a  test    rcx, rcx
0x18000fd3d  jz      short loc_18000FD6E
0x18000fd3f  mov     rax, [rdi+30h]
0x18000fd43  sub     rax, rcx
0x18000fd46  sub     rax, 20h ; ' '
0x18000fd4a  mov     [rcx+18h], rax
0x18000fd4e  mov     eax, [rdi+40h]
0x18000fd51  sub     eax, [rdi+30h]
0x18000fd54  cmp     eax, 10h
0x18000fd57  jb      loc_18000FE7F
0x18000fd5d  mov     ecx, eax
0x18000fd5f  mov     rax, [rdi+48h]
0x18000fd63  cmp     rax, rcx
0x18000fd66  cmovbe  rax, rcx
0x18000fd6a  mov     [rdi+48h], rax
0x18000fd6e  mov     rcx, [rdx+18h]
0x18000fd72  mov     rax, [rdi+10h]
0x18000fd76  add     rcx, 20h ; ' '
0x18000fd7a  add     rcx, rdx
0x18000fd7d  mov     [rdi+30h], rcx
0x18000fd81  mov     rcx, [rdx+8]
0x18000fd85  add     rcx, 20h ; ' '
0x18000fd89  add     rcx, rdx
0x18000fd8c  mov     [rdi+40h], rcx
0x18000fd90  mov     [rdx], rax
0x18000fd93  mov     r9, [rdi+30h]
0x18000fd97  mov     [rdi+10h], rdx
0x18000fd9b  lea     rax, [r9+rsi]
0x18000fd9f  mov     [rdi+30h], rax
0x18000fda3  mov     r14, [rsp+78h+var_30]
0x18000fda8  mov     r13, [rsp+78h+var_28]
0x18000fdad  mov     r12, [rsp+78h+var_20]
0x18000fdb2  mov     rbp, [rsp+78h+var_18]
0x18000fdb7  mov     rbx, [rsp+78h+arg_10]
0x18000fdbf  mov     r15, [rsp+78h+var_38]
0x18000fdc4  mov     rax, r9
0x18000fdc7  jmp     loc_18000FB8F
0x18000fdcc  lea     r9, [rbp+8]
0x18000fdd0  mov     r8, [rbp+28h]
0x18000fdd4  lea     rax, [rbp+28h]
0x18000fdd8  cmp     r8, rax
0x18000fddb  jnz     short loc_18000FE03
0x18000fddd  lea     r8, [rsp+78h+var_48]; struct PageSegment **
0x18000fde2  mov     edx, r12d; unsigned int
0x18000fde5  mov     rcx, rbp; this
0x18000fde8  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x18000fded  mov     rbx, rax
0x18000fdf0  test    rax, rax
0x18000fdf3  jz      loc_1800100BD
0x18000fdf9  mov     r13, [rsp+78h+var_48]
0x18000fdfe  jmp     loc_18000FCEA
0x18000fe03  mov     rcx, [r8+8]
0x18000fe07  lea     r13, [r8+10h]
0x18000fe0b  mov     rax, [r8]
0x18000fe0e  mov     edx, [rbp+58h]
0x18000fe11  mov     [rcx], rax
0x18000fe14  mov     rcx, [r8]
0x18000fe17  mov     rax, [r8+8]
0x18000fe1b  mov     [rcx+8], rax
0x18000fe1f  cmp     r12d, edx
0x18000fe22  jz      loc_180010134
0x18000fe28  mov     rcx, [r9]
0x18000fe2b  mov     rax, [rcx+8]
0x18000fe2f  mov     [r8+8], rax
0x18000fe33  mov     [r8], rcx
0x18000fe36  mov     rax, [rcx+8]
0x18000fe3a  mov     [rax], r8
0x18000fe3d  mov     [rcx+8], r8
0x18000fe41  mov     edx, r12d; unsigned int
0x18000fe44  mov     rcx, r13; this
0x18000fe47  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x18000fe4c  mov     rbx, rax
0x18000fe4f  mov     eax, r12d
0x18000fe52  shl     eax, 0Ch
0x18000fe55  mov     ecx, eax
0x18000fe57  add     [rbp+0A0h], rcx
0x18000fe5e  lock xadd cs:qword_18043D988, rax
0x18000fe67  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000fe6e  jz      loc_18000FEFC
0x18000fe74  lea     r8, [rax+rcx]
0x18000fe78  call    McTemplateU0x_EventWriteTransfer
0x18000fe7d  jmp     short loc_18000FEFC
0x18000fe7f  cmp     byte ptr [rdi+38h], 0
0x18000fe83  jnz     loc_18000FD5D
0x18000fe89  mov     rcx, [rdi+10h]
0x18000fe8d  mov     rax, [rcx]
0x18000fe90  mov     [rdi+10h], rax
0x18000fe94  mov     rax, [rdi+18h]
0x18000fe98  mov     [rcx], rax
0x18000fe9b  mov     [rdi+18h], rcx
0x18000fe9f  jmp     loc_18000FD6E
0x18000fea4  mov     ecx, r9d
0x18000fea7  sub     r11d, r12d
0x18000feaa  shl     r10d, cl
0x18000fead  lea     rcx, [rbp+8]
0x18000feb1  shl     r9d, 0Ch
0x18000feb5  not     r10d
0x18000feb8  and     r10d, eax
0x18000febb  mov     ebx, r9d
0x18000febe  mov     [r13+30h], r10d
0x18000fec2  mov     [r13+38h], r11d
0x18000fec6  add     rbx, [r13+10h]
0x18000feca  jz      loc_18000FFAB
0x18000fed0  mov     eax, r12d
0x18000fed3  shl     eax, 0Ch
0x18000fed6  mov     ecx, eax
0x18000fed8  add     [rbp+0A0h], rcx
0x18000fedf  lock xadd cs:qword_18043D988, rax
0x18000fee8  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000feef  jnz     loc_1800101AE
0x18000fef5  cmp     dword ptr [r13+38h], 0
0x18000fefa  jz      short loc_18000FF05
0x18000fefc  sub     [rbp+68h], r12
0x18000ff00  jmp     loc_18000FCEA
0x18000ff05  mov     rcx, [r8+8]
0x18000ff09  mov     rax, [r8]
0x18000ff0c  mov     [rcx], rax
0x18000ff0f  mov     rcx, [r8]
0x18000ff12  mov     rax, [r8+8]
0x18000ff16  mov     [rcx+8], rax
0x18000ff1a  mov     rcx, [rbp+18h]
0x18000ff1e  mov     rax, [rcx+8]
0x18000ff22  mov     [r8+8], rax
0x18000ff26  mov     [r8], rcx
0x18000ff29  mov     rax, [rcx+8]
0x18000ff2d  mov     [rax], r8
0x18000ff30  mov     [rcx+8], r8
0x18000ff34  sub     [rbp+68h], r12
0x18000ff38  jmp     loc_18000FCEA
0x18000ff3d  lea     r14, [r15+100Fh]
0x18000ff44  cmp     r14, r15
0x18000ff47  jb      loc_18000FBD8
0x18000ff4d  cmp     r14, rbp
0x18000ff50  jz      loc_18000FBD8
0x18000ff56  mov     rbp, [rdi+28h]
0x18000ff5a  lea     r12, [rdi+28h]
0x18000ff5e  shr     r14, 0Ch
0x18000ff62  mov     [rsp+78h+var_48], 0
0x18000ff6b  mov     eax, [rbp+58h]
0x18000ff6e  cmp     r14, rax
0x18000ff71  ja      loc_180010170
0x18000ff77  cmp     dword ptr [rbp+98h], 0
0x18000ff7e  mov     byte ptr [rbp+8Bh], 1
0x18000ff85  jz      loc_1800100F1
0x18000ff8b  mov     r12d, r14d
0x18000ff8e  cmp     [rbp+68h], r12
0x18000ff92  jb      loc_1800101A5
0x18000ff98  mov     eax, 20h ; ' '
0x18000ff9d  lea     rcx, [rbp+8]
0x18000ffa1  sub     eax, r12d
0x18000ffa4  mov     r8, rcx
0x18000ffa7  mov     [rsp+78h+var_58], eax
0x18000ffab  mov     r8, [r8]
0x18000ffae  mov     [rsp+78h+var_50], r8
0x18000ffb3  cmp     r8, rcx
0x18000ffb6  jz      loc_18001005D
0x18000ffbc  mov     r11d, [r8+48h]
0x18000ffc0  lea     r13, [r8+10h]
0x18000ffc4  cmp     r11d, r12d
0x18000ffc7  jb      short loc_18000FFAB
0x18000ffc9  mov     eax, [r13+30h]
0x18000ffcd  mov     r9d, 0FFFFFFFFh
0x18000ffd3  bsf     edx, eax
0x18000ffd6  mov     r10d, 0FFFFFFFFh
0x18000ffdc  setnz   cl
0x18000ffdf  test    cl, cl
0x18000ffe1  mov     ecx, [rsp+78h+var_58]
0x18000ffe5  cmovnz  r9d, edx
0x18000ffe9  shr     r10d, cl
0x18000ffec  mov     r8, [rsp+78h+var_50]
0x18000fff1  lea     rcx, [rbp+8]
0x18000fff5  mov     [rsp+78h+var_54], 0
0x18000fffd  cmp     r9d, 0FFFFFFFFh
0x180010001  jz      short loc_18000FFAB
0x180010003  mov     ecx, [r13+20h]
0x180010007  mov     rdx, [r13+18h]
0x18001000b  sub     rdx, rcx
0x18001000e  mov     ecx, r9d
0x180010011  sub     rdx, rcx
0x180010014  lea     rcx, [rbp+8]
0x180010018  cmp     rdx, r12
0x18001001b  jb      short loc_18000FFAB
  ... truncated ...
```
