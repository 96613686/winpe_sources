# SmallHeapBlock::ReassignPages(Recycler *)

- ea: `0x180011c88`
- end: `0x180012223`
- name: `?ReassignPages@SmallHeapBlock@@QEAAHPEAVRecycler@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(SmallHeapBlock *__hidden this, struct Recycler *)`
- caller_count: `10`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800114e8`
- `0x180011820`
- `0x1800125a4`
- `0x180012fc8`
- `0x1800132d0`
- `0x180013570`
- `0x18002b78c`
- `0x180049420`
- `0x18005e680`
- `0x18013089c`

## callees

- `0x1800052bc`
- `0x18000b9e4`
- `0x18000ec34`
- `0x18000ef2c`
- `0x180010e48`
- `0x180011c88`
- `0x18006a5f0`
- `0x1801616b4`
- `0x18016d008`
- `0x180174cb8`
- `0x1801c989b`
- `0x180255c94`

## import_xrefs

- `msvcrt!free` at `0x1800121db`
- `msvcrt!free` at `0x1800121db`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800120e3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800120e3`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800120b2`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800120b2`

## pseudocode

```c
__int64 __fastcall SmallHeapBlock::ReassignPages(SmallHeapBlock *this, struct Recycler *a2)
{
  bool v2; // zf
  char *v5; // rbx
  char *v6; // r15
  char *v7; // rdi
  struct PageSegment *v8; // rsi
  int v9; // r9d
  unsigned int v10; // r8d
  unsigned int v11; // edx
  unsigned int v12; // ecx
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rdx
  char *v16; // rbp
  signed __int64 v17; // r8
  unsigned __int64 v18; // r15
  unsigned int v19; // ebx
  void **v20; // r14
  char *i; // rdi
  _DWORD *v22; // rcx
  unsigned int v23; // edi
  unsigned int v24; // r14d
  __int64 v25; // rdx
  unsigned int v26; // esi
  volatile signed __int32 *v27; // rdx
  char *v29; // rdi
  char *v30; // rcx
  PageAllocator *v31; // rcx
  union _SLIST_HEADER *v32; // rcx
  char *v33; // rdi
  int v34; // edx
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  signed __int64 v37; // r8
  __int64 v38; // rcx
  PSLIST_ENTRY v39; // rax
  PSLIST_ENTRY v40; // r14
  int Next; // edi
  int v42; // edi
  char *v43; // rax
  void *v44; // rax
  void *v45; // rdi
  struct PageSegment *v46; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v47; // [rsp+28h] [rbp-50h]
  _DWORD *v48; // [rsp+30h] [rbp-48h]

  v2 = *((_BYTE *)this + 24) == 2;
  v46 = 0;
  if ( v2 )
    v5 = (char *)*((_QWORD *)a2 + 1);
  else
    v5 = (char *)a2 + 16;
  v2 = *((_DWORD *)v5 + 38) == 0;
  v5[139] = 1;
  if ( v2 )
    AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v5 + 200));
  v6 = v5 + 8;
  if ( *((_QWORD *)v5 + 13) )
  {
    v7 = v5 + 8;
    while ( 1 )
    {
      v7 = *(char **)v7;
      if ( v7 == v6 )
        break;
      v8 = (struct PageSegment *)(v7 + 16);
      v9 = *((_DWORD *)v7 + 18);
      if ( v9 )
      {
        v10 = *((_DWORD *)v7 + 16);
        v11 = -1;
        v2 = !_BitScanForward(&v12, v10);
        v47 = 0;
        if ( !v2 )
          v11 = v12;
        if ( v11 != -1 )
        {
          v13 = *((_QWORD *)v7 + 5) - *((unsigned int *)v7 + 12) - v11;
          if ( v13 )
          {
            v14 = v10 & ~(1 << v11);
            v15 = v11 << 12;
            *((_DWORD *)v7 + 16) = v14;
            *((_DWORD *)v7 + 18) = v9 - 1;
            v16 = (char *)(*((_QWORD *)v7 + 4) + (unsigned int)v15);
            if ( v16 )
            {
              *((_QWORD *)v5 + 20) += 4096LL;
              v17 = _InterlockedExchangeAdd64(&qword_18043D988, 0x1000u);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
                McTemplateU0x_EventWriteTransfer(v13, v15, v17 + 4096);
              if ( !*((_DWORD *)v7 + 18) )
              {
                **((_QWORD **)v7 + 1) = *(_QWORD *)v7;
                *(_QWORD *)(*(_QWORD *)v7 + 8LL) = *((_QWORD *)v7 + 1);
                v38 = *((_QWORD *)v5 + 3);
                *((_QWORD *)v7 + 1) = *(_QWORD *)(v38 + 8);
                *(_QWORD *)v7 = v38;
                **(_QWORD **)(v38 + 8) = v7;
                *(_QWORD *)(v38 + 8) = v7;
              }
              goto LABEL_18;
            }
          }
        }
      }
    }
    v32 = (union _SLIST_HEADER *)*((_QWORD *)v5 + 16);
    if ( v32 )
    {
      v39 = InterlockedPopEntrySList(v32);
      v40 = v39;
      if ( v39 )
      {
        v8 = (struct PageSegment *)*((_QWORD *)&v39->Next + 1);
        Next = (int)v39[1].Next;
        v46 = v8;
        if ( Next == 1 )
        {
          v16 = (char *)v39;
          *v39 = 0;
          v39[1] = 0;
        }
        else
        {
          v42 = Next - 1;
          LODWORD(v39[1].Next) = v42;
          InterlockedPushEntrySList(*((PSLIST_HEADER *)v5 + 16), v39);
          v16 = (char *)v40 + (unsigned int)(v42 << 12);
        }
        if ( v16 )
          goto LABEL_19;
      }
    }
  }
  v33 = (char *)*((_QWORD *)v5 + 5);
  if ( v33 != v5 + 40 )
  {
    v8 = (struct PageSegment *)(v33 + 16);
    v34 = *((_DWORD *)v5 + 22);
    **((_QWORD **)v33 + 1) = *(_QWORD *)v33;
    *(_QWORD *)(*(_QWORD *)v33 + 8LL) = *((_QWORD *)v33 + 1);
    if ( v34 == 1 )
      v35 = (_QWORD *)*((_QWORD *)v5 + 3);
    else
      v35 = *(_QWORD **)v6;
    *((_QWORD *)v33 + 1) = v35[1];
    *(_QWORD *)v33 = v35;
    *(_QWORD *)v35[1] = v33;
    v35[1] = v33;
    goto LABEL_53;
  }
  v16 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v5, 1u, &v46);
  if ( v16 )
  {
LABEL_61:
    v8 = v46;
    goto LABEL_19;
  }
  v8 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)v5);
  if ( !v8 )
  {
    v16 = 0;
    goto LABEL_61;
  }
LABEL_53:
  v16 = PageSegment::AllocPages(v8, 1u);
  *((_QWORD *)v5 + 20) += 4096LL;
  v37 = _InterlockedExchangeAdd64(&qword_18043D988, 0x1000u);
  if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
    McTemplateU0x_EventWriteTransfer(v36, v15, v37 + 4096);
LABEL_18:
  --*((_QWORD *)v5 + 13);
LABEL_19:
  if ( !*((_DWORD *)v5 + 38) )
    *((_DWORD *)v5 + 60) = 0;
  if ( v16 )
  {
    ++*((_QWORD *)a2 + 66);
    v18 = 1;
    v19 = 0x100000 - ((unsigned int)v16 >> 12);
    *((_QWORD *)this + 2) = v8;
    *((_QWORD *)this + 1) = v16;
    if ( v19 > 1 )
      v19 = 1;
    while ( 2 )
    {
      v20 = (void **)((char *)a2 + 360);
LABEL_25:
      for ( i = (char *)*v20; i; i = (char *)*((_QWORD *)i + 1) )
      {
        if ( *(_DWORD *)i == HIDWORD(v16) )
          goto LABEL_28;
      }
      v43 = (char *)operator new[]<HeapAllocator>(32800, v15, 1, HeapAllocator::NoThrowAllocZero);
      i = v43;
      if ( v43 )
      {
        memset_0(v43, 0, 0x8020u);
        *(_DWORD *)i = HIDWORD(v16);
        *((_QWORD *)i + 1) = *v20;
        *v20 = i;
LABEL_28:
        v22 = i + 16;
        v23 = (unsigned __int8)((unsigned int)v16 >> 12);
        v24 = v19;
        v25 = (unsigned int)v16 >> 20;
        v48 = v22;
        v26 = v19;
        if ( v19 >= 256 - v23 )
          v24 = 256 - v23;
        while ( 1 )
        {
          LODWORD(v46) = v25;
          v27 = *(volatile signed __int32 **)&v22[2 * v25 + 2];
          v47 = v23;
          if ( v27 )
          {
            if ( v23 < v24 + v23 )
            {
              memset64((void *)&v27[2 * v23 + 2], (unsigned __int64)this, v24);
              v22 = v48;
            }
            _InterlockedAdd(v27, v24);
            v15 = (unsigned int)v46;
          }
          else
          {
            v44 = (void *)operator new[]<HeapAllocator>(2056, 0, 1, HeapAllocator::NoThrowAllocZero);
            v45 = v44;
            if ( !v44 )
              goto LABEL_82;
            memset_0(v44, 0, 0x808u);
            if ( !HeapBlockMap32::L2MapChunk::Set((HeapBlockMap32::L2MapChunk *)v45, v47, v24, this) )
            {
              free(v45);
LABEL_82:
              if ( v19 != v26 )
                HeapBlockMap32::ClearHeapBlockImpl<0>(v48, v16, v19 - v26);
              v20 = (void **)((char *)a2 + 360);
              goto LABEL_85;
            }
            v22 = v48;
            v15 = (unsigned int)v46;
            *(_QWORD *)&v48[2 * (unsigned int)v46 + 2] = v45;
            ++*v22;
          }
          v26 -= v24;
          if ( !v26 )
            break;
          v24 = 256;
          v23 = 0;
          v25 = (unsigned int)(v15 + 1);
          if ( v26 < 0x100 )
            v24 = v26;
        }
        v18 -= v19;
        if ( !v18 )
          return 1;
        v20 = (void **)((char *)a2 + 360);
        v16 += 4096 * (unsigned __int64)v19;
        v19 = 0x100000;
        if ( v18 < 0x100000 )
        {
          v19 = v18;
          continue;
        }
        goto LABEL_25;
      }
      break;
    }
LABEL_85:
    if ( v18 != 1 )
      HeapBlockMap64::ClearHeapBlockImpl<0>(v20, v16, 1 - v18);
    v29 = (char *)a2 + 16;
    if ( *((_BYTE *)this + 24) == 2 )
      v30 = (char *)*((_QWORD *)a2 + 1);
    else
      v30 = (char *)a2 + 16;
    if ( !*((_DWORD *)v30 + 38) )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v30 + 200));
    if ( *((_BYTE *)this + 24) == 2 )
      v31 = (PageAllocator *)*((_QWORD *)a2 + 1);
    else
      v31 = (struct Recycler *)((char *)a2 + 16);
    PageAllocator::ReleasePages(v31, *((void **)this + 1), 1u, *((struct PageSegment **)this + 2));
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 1) = 0;
    if ( *((_BYTE *)this + 24) == 2 )
      v29 = (char *)*((_QWORD *)a2 + 1);
    if ( !*((_DWORD *)v29 + 38) )
      *((_DWORD *)v29 + 60) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180011c88  mov     rax, rsp
0x180011c8b  mov     [rax+18h], rbx
0x180011c8f  mov     [rax+10h], rdx
0x180011c93  mov     [rax+8], rcx
0x180011c97  push    rbp
0x180011c98  push    rsi
0x180011c99  push    rdi
0x180011c9a  push    r12
0x180011c9c  push    r13
0x180011c9e  push    r14
0x180011ca0  push    r15
0x180011ca2  sub     rsp, 40h
0x180011ca6  cmp     byte ptr [rcx+18h], 2
0x180011caa  mov     r13, rcx
0x180011cad  mov     qword ptr [rax-58h], 0
0x180011cb5  mov     r12, rdx
0x180011cb8  jz      loc_18001200B
0x180011cbe  lea     rbx, [rdx+10h]
0x180011cc2  cmp     dword ptr [rbx+98h], 0
0x180011cc9  mov     ebp, 1
0x180011cce  mov     [rbx+8Bh], bpl
0x180011cd5  jz      loc_180012096
0x180011cdb  lea     r15, [rbx+8]
0x180011cdf  cmp     [rbx+68h], rbp
0x180011ce3  jb      loc_180011EF7
0x180011ce9  mov     rdi, r15
0x180011cec  or      r10d, 0FFFFFFFFh
0x180011cf0  mov     rdi, [rdi]
0x180011cf3  cmp     rdi, r15
0x180011cf6  jz      loc_180011EE7
0x180011cfc  lea     rsi, [rdi+10h]
0x180011d00  mov     r9d, [rsi+38h]
0x180011d04  cmp     r9d, ebp
0x180011d07  jb      short loc_180011CF0
0x180011d09  mov     r8d, [rsi+30h]
0x180011d0d  mov     edx, r10d
0x180011d10  bsf     ecx, r8d
0x180011d14  mov     [rsp+78h+var_50], 0
0x180011d1c  setnz   al
0x180011d1f  test    al, al
0x180011d21  cmovnz  edx, ecx
0x180011d24  cmp     edx, r10d
0x180011d27  jz      short loc_180011CF0
0x180011d29  mov     eax, [rsi+20h]
0x180011d2c  mov     rcx, [rsi+18h]
0x180011d30  sub     rcx, rax
0x180011d33  mov     eax, edx
0x180011d35  sub     rcx, rax
0x180011d38  cmp     rcx, rbp
0x180011d3b  jb      short loc_180011CF0
0x180011d3d  btr     r8d, edx
0x180011d41  shl     edx, 0Ch
0x180011d44  mov     [rsi+30h], r8d
0x180011d48  lea     eax, [r9-1]
0x180011d4c  mov     ebp, edx
0x180011d4e  mov     [rsi+38h], eax
0x180011d51  add     rbp, [rsi+10h]
0x180011d55  jz      loc_180011FDD
0x180011d5b  mov     r8d, 1000h
0x180011d61  add     [rbx+0A0h], r8
0x180011d68  lock xadd cs:qword_18043D988, r8
0x180011d71  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180011d78  jnz     loc_180012128
0x180011d7e  cmp     dword ptr [rsi+38h], 0
0x180011d82  jz      loc_180011FA9
0x180011d88  dec     qword ptr [rbx+68h]
0x180011d8c  cmp     dword ptr [rbx+98h], 0
0x180011d93  jz      loc_18001205A
0x180011d99  test    rbp, rbp
0x180011d9c  jz      loc_180011ECD
0x180011da2  mov     r8d, 1
0x180011da8  mov     eax, ebp
0x180011daa  add     [r12+210h], r8
0x180011db2  mov     ebx, 100000h
0x180011db7  shr     eax, 0Ch
0x180011dba  mov     r15d, r8d
0x180011dbd  sub     ebx, eax
0x180011dbf  mov     [r13+10h], rsi
0x180011dc3  cmp     ebx, r8d
0x180011dc6  mov     [r13+8], rbp
0x180011dca  cmova   ebx, r8d
0x180011dce  lea     r14, [r12+168h]
0x180011dd6  mov     rdi, [r14]
0x180011dd9  mov     rsi, rbp
0x180011ddc  shr     rsi, 20h
0x180011de0  test    rdi, rdi
0x180011de3  jz      loc_180012139
0x180011de9  cmp     [rdi], esi
0x180011deb  jnz     loc_180011FA0
0x180011df1  lea     rcx, [rdi+10h]
0x180011df5  mov     eax, ebp
0x180011df7  shr     eax, 0Ch
0x180011dfa  mov     edx, ebp
0x180011dfc  movzx   edi, al
0x180011dff  mov     r14d, ebx
0x180011e02  mov     eax, 100h
0x180011e07  shr     edx, 14h
0x180011e0a  sub     eax, edi
0x180011e0c  mov     [rsp+78h+var_48], rcx
0x180011e11  cmp     ebx, eax
0x180011e13  mov     esi, ebx
0x180011e15  cmovnb  r14d, eax
0x180011e19  mov     dword ptr [rsp+78h+var_58], edx
0x180011e1d  mov     rdx, [rcx+rdx*8+8]
0x180011e22  mov     [rsp+78h+var_50], edi
0x180011e26  test    rdx, rdx
0x180011e29  jz      loc_18001217D
0x180011e2f  lea     eax, [r14+rdi]
0x180011e33  cmp     edi, eax
0x180011e35  jnb     short loc_180011E4E
0x180011e37  mov     eax, edi
0x180011e39  inc     rax
0x180011e3c  mov     ecx, r14d
0x180011e3f  lea     rdi, [rdx+rax*8]
0x180011e43  mov     rax, r13
0x180011e46  rep stosq
0x180011e49  mov     rcx, [rsp+78h+var_48]
0x180011e4e  lock add [rdx], r14d
0x180011e52  mov     edx, dword ptr [rsp+78h+var_58]
0x180011e56  sub     esi, r14d
0x180011e59  jnz     loc_180011F89
0x180011e5f  mov     eax, ebx
0x180011e61  sub     r15, rax
0x180011e64  jnz     loc_180012033
0x180011e6a  mov     eax, r8d
0x180011e6d  jmp     short loc_180011ECF
0x180011e6f  mov     bpl, 2
0x180011e72  lea     rdi, [r12+10h]
0x180011e77  cmp     [r13+18h], bpl
0x180011e7b  jz      loc_180012015
0x180011e81  mov     rcx, rdi
0x180011e84  xor     ebx, ebx
0x180011e86  cmp     [rcx+98h], ebx
0x180011e8c  jz      loc_1800120FF
0x180011e92  cmp     [r13+18h], bpl
0x180011e96  jz      loc_18001201F
0x180011e9c  mov     rcx, rdi; this
0x180011e9f  mov     r9, [r13+10h]; struct PageSegment *
0x180011ea3  mov     r8d, esi; unsigned int
0x180011ea6  mov     rdx, [r13+8]; void *
0x180011eaa  call    ?ReleasePages@PageAllocator@@QEAAXPEAXIPEAVPageSegment@@@Z; PageAllocator::ReleasePages(void *,uint,PageSegment *)
0x180011eaf  mov     [r13+10h], rbx
0x180011eb3  mov     [r13+8], rbx
0x180011eb7  cmp     [r13+18h], bpl
0x180011ebb  jz      loc_180012029
0x180011ec1  cmp     [rdi+98h], ebx
0x180011ec7  jz      loc_1800120A7
0x180011ecd  xor     eax, eax
0x180011ecf  mov     rbx, [rsp+78h+arg_10]
0x180011ed7  add     rsp, 40h
0x180011edb  pop     r15
0x180011edd  pop     r14
0x180011edf  pop     r13
0x180011ee1  pop     r12
0x180011ee3  pop     rdi
0x180011ee4  pop     rsi
0x180011ee5  pop     rbp
0x180011ee6  retn
0x180011ee7  mov     rcx, [rbx+80h]; ListHead
0x180011eee  test    rcx, rcx
0x180011ef1  jnz     loc_1800120B2
0x180011ef7  lea     rax, [rbx+28h]
0x180011efb  mov     rdi, [rax]
0x180011efe  cmp     rdi, rax
0x180011f01  jz      loc_180011FE7
0x180011f07  mov     rcx, [rdi+8]
0x180011f0b  lea     rsi, [rdi+10h]
0x180011f0f  mov     rax, [rdi]
0x180011f12  mov     edx, [rbx+58h]
0x180011f15  mov     [rcx], rax
0x180011f18  mov     rcx, [rdi]
0x180011f1b  mov     rax, [rdi+8]
0x180011f1f  mov     [rcx+8], rax
0x180011f23  cmp     edx, 1
0x180011f26  jz      loc_180012110
0x180011f2c  mov     rcx, [r15]
0x180011f2f  mov     rax, [rcx+8]
0x180011f33  mov     [rdi+8], rax
0x180011f37  mov     [rdi], rcx
0x180011f3a  mov     rax, [rcx+8]
0x180011f3e  mov     [rax], rdi
0x180011f41  mov     [rcx+8], rdi
0x180011f45  mov     edx, 1; unsigned int
0x180011f4a  mov     rcx, rsi; this
0x180011f4d  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180011f52  mov     r8d, 1000h
0x180011f58  mov     rbp, rax
0x180011f5b  add     [rbx+0A0h], r8
0x180011f62  lock xadd cs:qword_18043D988, r8
0x180011f6b  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180011f72  jz      loc_180011D88
0x180011f78  add     r8, 1000h
0x180011f7f  call    McTemplateU0x_EventWriteTransfer
0x180011f84  jmp     loc_180011D88
0x180011f89  mov     r14d, 100h
0x180011f8f  xor     edi, edi
0x180011f91  add     edx, r8d
0x180011f94  cmp     esi, r14d
0x180011f97  cmovb   r14d, esi
0x180011f9b  jmp     loc_180011E19
0x180011fa0  mov     rdi, [rdi+8]
0x180011fa4  jmp     loc_180011DE0
0x180011fa9  mov     rcx, [rdi+8]
0x180011fad  mov     rax, [rdi]
0x180011fb0  mov     [rcx], rax
0x180011fb3  mov     rcx, [rdi]
0x180011fb6  mov     rax, [rdi+8]
0x180011fba  mov     [rcx+8], rax
0x180011fbe  mov     rcx, [rbx+18h]
0x180011fc2  mov     rax, [rcx+8]
0x180011fc6  mov     [rdi+8], rax
0x180011fca  mov     [rdi], rcx
0x180011fcd  mov     rax, [rcx+8]
0x180011fd1  mov     [rax], rdi
0x180011fd4  mov     [rcx+8], rdi
0x180011fd8  jmp     loc_180011D88
0x180011fdd  mov     ebp, 1
0x180011fe2  jmp     loc_180011CF0
0x180011fe7  lea     r8, [rsp+78h+var_58]; struct PageSegment **
0x180011fec  mov     edx, 1; unsigned int
0x180011ff1  mov     rcx, rbx; this
0x180011ff4  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180011ff9  mov     rbp, rax
0x180011ffc  test    rax, rax
0x180011fff  jz      short loc_180012069
0x180012001  mov     rsi, [rsp+78h+var_58]
0x180012006  jmp     loc_180011D8C
0x18001200b  mov     rbx, [r12+8]
0x180012010  jmp     loc_180011CC2
0x180012015  mov     rcx, [r12+8]
0x18001201a  jmp     loc_180011E84
0x18001201f  mov     rcx, [r12+8]
0x180012024  jmp     loc_180011E9F
0x180012029  mov     rdi, [r12+8]
0x18001202e  jmp     loc_180011EC1
0x180012033  shl     rax, 0Ch
0x180012037  lea     r14, [r12+168h]
0x18001203f  add     rbp, rax
0x180012042  mov     eax, 100000h
0x180012047  mov     ebx, eax
0x180012049  cmp     r15, rax
0x18001204c  jnb     loc_180011DD6
0x180012052  mov     ebx, r15d
0x180012055  jmp     loc_180011DCE
0x18001205a  mov     dword ptr [rbx+0F0h], 0
0x180012064  jmp     loc_180011D99
0x180012069  cmp     dword ptr [rbx+58h], 1
0x18001206d  mov     edx, 18h
0x180012072  mov     rcx, rbx; this
0x180012075  lea     eax, [rdx-10h]
0x180012078  cmovnz  edx, eax
0x18001207b  add     rdx, rbx
0x18001207e  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x180012083  mov     rsi, rax
0x180012086  test    rax, rax
0x180012089  jnz     loc_180011F45
0x18001208f  xor     ebp, ebp
0x180012091  jmp     loc_180012001
0x180012096  lea     rcx, [rbx+0C8h]; this
0x18001209d  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x1800120a2  jmp     loc_180011CDB
0x1800120a7  mov     [rdi+0F0h], ebx
0x1800120ad  jmp     loc_180011ECD
0x1800120b2  call    cs:__imp_InterlockedPopEntrySList
0x1800120b8  mov     r14, rax
0x1800120bb  test    rax, rax
0x1800120be  jz      loc_180011EF7
0x1800120c4  mov     rsi, [rax+8]
0x1800120c8  mov     edi, [rax+10h]
0x1800120cb  mov     [rsp+78h+var_58], rsi
0x1800120d0  cmp     edi, ebp
0x1800120d2  jz      short loc_180012119
0x1800120d4  dec     edi
0x1800120d6  mov     rdx, rax; ListEntry
0x1800120d9  mov     [rax+10h], edi
0x1800120dc  mov     rcx, [rbx+80h]; ListHead
0x1800120e3  call    cs:__imp_InterlockedPushEntrySList
0x1800120e9  shl     edi, 0Ch
0x1800120ec  mov     ebp, edi
0x1800120ee  add     rbp, r14
0x1800120f1  test    rbp, rbp
0x1800120f4  jnz     loc_180011D8C
0x1800120fa  jmp     loc_180011EF7
0x1800120ff  add     rcx, 0C8h; this
0x180012106  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x18001210b  jmp     loc_180011E92
0x180012110  mov     rcx, [rbx+18h]
0x180012114  jmp     loc_180011F2F
0x180012119  xorps   xmm0, xmm0
0x18001211c  mov     rbp, r14
0x18001211f  movups  xmmword ptr [rax], xmm0
0x180012122  movups  xmmword ptr [rax+10h], xmm0
0x180012126  jmp     short loc_1800120F1
0x180012128  add     r8, 1000h
0x18001212f  call    McTemplateU0x_EventWriteTransfer
0x180012134  jmp     loc_180011D7E
0x180012139  lea     r9, ?NoThrowAllocZero@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAllocZero(unsigned __int64)
0x180012140  mov     ecx, 8020h
0x180012145  call    ??$?_UUHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@_NP80@EAAPEAD0@Z@Z; operator new[]<HeapAllocator>(unsigned __int64,HeapAllocator *,bool,char * (HeapAllocator::*)(unsigned __int64))
0x18001214a  mov     rdi, rax
  ... truncated ...
```
