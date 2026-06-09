# PageAllocator::AllocPages(uint,PageSegment * *)

- ea: `0x1800101e8`
- end: `0x1800104fc`
- name: `?AllocPages@PageAllocator@@QEAAPEADIPEAPEAVPageSegment@@@Z`
- size: `788`
- prototype: `char *__fastcall(PageAllocator *__hidden this, unsigned int, struct PageSegment **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f304`
- `0x18003cca0`
- `0x18003e970`

## callees

- `0x1800052bc`
- `0x18000ef2c`
- `0x1800101e8`
- `0x180010e48`
- `0x18006a5f0`
- `0x180255c94`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1800103a4`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800103a4`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800104ad`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800104ad`

## pseudocode

```c
char *__fastcall PageAllocator::AllocPages(PageAllocator *this, unsigned int a2, struct PageSegment **a3)
{
  bool v3; // zf
  char *v5; // r15
  char *v6; // r14
  PageSegment *v7; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r9d
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  char *v15; // rbx
  __int64 v16; // rsi
  signed __int64 v17; // rcx
  union _SLIST_HEADER *v18; // rcx
  PageAllocator *v19; // r8
  int v20; // ebx
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rdx
  signed __int64 v27; // rcx
  PSLIST_ENTRY v28; // rax
  PSLIST_ENTRY v29; // rbp
  int Next; // ebx

  v3 = *((_DWORD *)this + 38) == 0;
  *((_BYTE *)this + 139) = 1;
  if ( v3 )
    AsymetricCriticalSection::FastEnter((PageAllocator *)((char *)this + 200));
  v5 = (char *)this + 8;
  if ( *((_QWORD *)this + 13) < (unsigned __int64)a2 )
    goto LABEL_25;
  v6 = (char *)this + 8;
LABEL_5:
  while ( 1 )
  {
    v6 = *(char **)v6;
    if ( v6 == v5 )
      break;
    v7 = (PageSegment *)(v6 + 16);
    v8 = *((_DWORD *)v6 + 18);
    if ( v8 >= a2 )
    {
      v9 = *((_DWORD *)v6 + 16);
      v10 = -1;
      v3 = !_BitScanForward(&v11, v9);
      if ( !v3 )
        v10 = v11;
      v12 = 0xFFFFFFFF >> (32 - a2);
      while ( v10 != -1 )
      {
        v13 = *((_QWORD *)v6 + 5) - v10 - *((unsigned int *)v6 + 12);
        if ( v13 < a2 )
          break;
        if ( a2 == 1 || (v13 = v12 << v10, (v9 & (v12 << v10)) == (_DWORD)v13) )
        {
          *((_DWORD *)v6 + 16) = v9 & ~(v12 << v10);
          *((_DWORD *)v6 + 18) = v8 - a2;
          v15 = (char *)(*((_QWORD *)v6 + 4) + (v10 << 12));
          if ( !v15 )
            goto LABEL_5;
          v16 = a2 << 12;
          *((_QWORD *)this + 20) += (unsigned int)v16;
          v17 = _InterlockedExchangeAdd64(&qword_18043D988, (unsigned int)v16);
          if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
            McTemplateU0x_EventWriteTransfer(v17, v13, v16 + v17);
          if ( !*((_DWORD *)v6 + 18) )
          {
            **((_QWORD **)v6 + 1) = *(_QWORD *)v6;
            *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *((_QWORD *)v6 + 1);
            v22 = *((_QWORD *)this + 3);
            *((_QWORD *)v6 + 1) = *(_QWORD *)(v22 + 8);
            *(_QWORD *)v6 = v22;
            **(_QWORD **)(v22 + 8) = v6;
            *(_QWORD *)(v22 + 8) = v6;
          }
          goto LABEL_22;
        }
        v3 = !_BitScanForward(&v14, v9 & (-1 << (v10 + 1)));
        v10 = -1;
        if ( !v3 )
          v10 = v14;
      }
    }
  }
  if ( a2 != 1 )
    goto LABEL_25;
  v18 = (union _SLIST_HEADER *)*((_QWORD *)this + 16);
  if ( !v18 )
    goto LABEL_25;
  v28 = InterlockedPopEntrySList(v18);
  v29 = v28;
  if ( !v28 )
    goto LABEL_25;
  *a3 = (struct PageSegment *)*((_QWORD *)&v28->Next + 1);
  Next = (int)v28[1].Next;
  if ( Next == 1 )
  {
    v15 = (char *)v28;
    *v28 = 0;
    v28[1] = 0;
  }
  else
  {
    v20 = Next - 1;
    LODWORD(v28[1].Next) = v20;
    InterlockedPushEntrySList(*((PSLIST_HEADER *)this + 16), v28);
    v15 = (char *)v29 + (unsigned int)(v20 << 12);
  }
  if ( !v15 )
  {
LABEL_25:
    v19 = (PageAllocator *)*((_QWORD *)this + 5);
    if ( v19 == (PageAllocator *)((char *)this + 40) )
    {
      v15 = PageAllocator::TryAllocDecommitedPages(this, a2, a3);
      if ( v15 )
        goto LABEL_31;
      v7 = (PageSegment *)PageAllocator::AddPageSegment(this);
      if ( !v7 )
        goto LABEL_31;
    }
    else
    {
      v7 = (PageAllocator *)((char *)v19 + 16);
      v23 = *((_DWORD *)this + 22);
      **((_QWORD **)v19 + 1) = *(_QWORD *)v19;
      *(_QWORD *)(*(_QWORD *)v19 + 8LL) = *((_QWORD *)v19 + 1);
      if ( a2 == v23 )
        v24 = *((_QWORD *)this + 3);
      else
        v24 = *(_QWORD *)v5;
      *((_QWORD *)v19 + 1) = *(_QWORD *)(v24 + 8);
      *(_QWORD *)v19 = v24;
      **(_QWORD **)(v24 + 8) = v19;
      *(_QWORD *)(v24 + 8) = v19;
    }
    v25 = a2 << 12;
    v15 = PageSegment::AllocPages(v7, a2);
    *((_QWORD *)this + 20) += (unsigned int)v25;
    v27 = _InterlockedExchangeAdd64(&qword_18043D988, (unsigned int)v25);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(v27, v26, v25 + v27);
LABEL_22:
    *((_QWORD *)this + 13) -= a2;
    *a3 = v7;
  }
LABEL_31:
  if ( !*((_DWORD *)this + 38) )
    *((_DWORD *)this + 60) = 0;
  return v15;
}

```

## disassembly

```asm
0x1800101e8  mov     rax, rsp
0x1800101eb  mov     [rax+20h], rbx
0x1800101ef  mov     [rax+18h], r8
0x1800101f3  mov     [rax+10h], edx
0x1800101f6  mov     [rax+8], rcx
0x1800101fa  push    rbp
0x1800101fb  push    rsi
0x1800101fc  push    rdi
0x1800101fd  push    r12
0x1800101ff  push    r13
0x180010201  push    r14
0x180010203  push    r15
0x180010205  sub     rsp, 30h
0x180010209  cmp     dword ptr [rcx+98h], 0
0x180010210  mov     rdi, rcx
0x180010213  mov     byte ptr [rcx+8Bh], 1
0x18001021a  jz      loc_18001049C
0x180010220  mov     esi, [rsp+68h+arg_8]
0x180010224  lea     r15, [rdi+8]
0x180010228  mov     r13d, esi
0x18001022b  mov     r12, [rsp+68h+arg_10]
0x180010233  cmp     [rdi+68h], rsi
0x180010237  jb      loc_18001034B
0x18001023d  mov     r11d, 20h ; ' '
0x180010243  mov     r14, r15
0x180010246  sub     r11d, esi
0x180010249  or      r8d, 0FFFFFFFFh
0x18001024d  mov     r14, [r14]
0x180010250  cmp     r14, r15
0x180010253  jz      loc_180010336
0x180010259  lea     rbp, [r14+10h]
0x18001025d  mov     ebx, [rbp+38h]
0x180010260  cmp     ebx, esi
0x180010262  jb      short loc_18001024D
0x180010264  mov     eax, [rbp+30h]
0x180010267  mov     r10d, r8d
0x18001026a  bsf     edx, eax
0x18001026d  mov     r9d, r8d
0x180010270  setnz   cl
0x180010273  test    cl, cl
0x180010275  mov     ecx, r11d
0x180010278  cmovnz  r10d, edx
0x18001027c  shr     r9d, cl
0x18001027f  mov     [rsp+68h+var_48], 0
0x180010287  cmp     r10d, r8d
0x18001028a  jz      short loc_18001024D
0x18001028c  mov     rdx, [rbp+18h]
0x180010290  mov     ecx, r10d
0x180010293  sub     rdx, rcx
0x180010296  mov     ecx, [rbp+20h]
0x180010299  sub     rdx, rcx
0x18001029c  cmp     rdx, r13
0x18001029f  jb      short loc_18001024D
0x1800102a1  cmp     esi, 1
0x1800102a4  jz      short loc_1800102D8
0x1800102a6  mov     ecx, r10d
0x1800102a9  mov     edx, r9d
0x1800102ac  shl     edx, cl
0x1800102ae  mov     ecx, edx
0x1800102b0  and     ecx, eax
0x1800102b2  cmp     ecx, edx
0x1800102b4  jz      short loc_1800102D8
0x1800102b6  lea     ecx, [r10+1]
0x1800102ba  mov     edx, r8d
0x1800102bd  shl     edx, cl
0x1800102bf  and     edx, eax
0x1800102c1  bsf     r8d, edx
0x1800102c5  setnz   cl
0x1800102c8  or      r10d, 0FFFFFFFFh
0x1800102cc  test    cl, cl
0x1800102ce  cmovnz  r10d, r8d
0x1800102d2  or      r8d, 0FFFFFFFFh
0x1800102d6  jmp     short loc_18001027F
0x1800102d8  sub     ebx, esi
0x1800102da  mov     ecx, r10d
0x1800102dd  shl     r9d, cl
0x1800102e0  shl     r10d, 0Ch
0x1800102e4  not     r9d
0x1800102e7  and     r9d, eax
0x1800102ea  mov     [rbp+30h], r9d
0x1800102ee  mov     [rbp+38h], ebx
0x1800102f1  mov     ebx, r10d
0x1800102f4  add     rbx, [rbp+10h]
0x1800102f8  jz      loc_18001024D
0x1800102fe  shl     esi, 0Ch
0x180010301  mov     eax, esi
0x180010303  add     [rdi+0A0h], rax
0x18001030a  mov     ecx, esi
0x18001030c  lock xadd cs:qword_18043D988, rcx
0x180010315  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18001031c  jnz     loc_1800104EE
0x180010322  cmp     dword ptr [rbp+38h], 0
0x180010326  jz      loc_1800103DD
0x18001032c  sub     [rdi+68h], r13
0x180010330  mov     [r12], rbp
0x180010334  jmp     short loc_1800103B5
0x180010336  cmp     esi, 1
0x180010339  jnz     short loc_18001034B
0x18001033b  mov     rcx, [rdi+80h]; ListHead
0x180010342  test    rcx, rcx
0x180010345  jnz     loc_1800104AD
0x18001034b  lea     rax, [rdi+28h]
0x18001034f  mov     r8, [rax]
0x180010352  cmp     r8, rax
0x180010355  jnz     loc_180010411
0x18001035b  mov     r8, r12; struct PageSegment **
0x18001035e  mov     edx, esi; unsigned int
0x180010360  mov     rcx, rdi; this
0x180010363  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180010368  mov     rbx, rax
0x18001036b  test    rax, rax
0x18001036e  jnz     short loc_1800103B5
0x180010370  cmp     esi, [rdi+58h]
0x180010373  lea     edx, [rax+18h]
0x180010376  lea     eax, [rbx+8]
0x180010379  mov     rcx, rdi; this
0x18001037c  cmovnz  edx, eax
0x18001037f  add     rdx, rdi
0x180010382  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x180010387  mov     rbp, rax
0x18001038a  test    rax, rax
0x18001038d  jnz     loc_18001044E
0x180010393  jmp     short loc_1800103B5
0x180010395  dec     ebx
0x180010397  mov     rdx, rbp; ListEntry
0x18001039a  mov     [rax+10h], ebx
0x18001039d  mov     rcx, [rdi+80h]; ListHead
0x1800103a4  call    cs:__imp_InterlockedPushEntrySList
0x1800103aa  shl     ebx, 0Ch
0x1800103ad  add     rbx, rbp
0x1800103b0  test    rbx, rbx
0x1800103b3  jz      short loc_18001034B
0x1800103b5  cmp     dword ptr [rdi+98h], 0
0x1800103bc  jz      loc_18001048D
0x1800103c2  mov     rax, rbx
0x1800103c5  mov     rbx, [rsp+68h+arg_18]
0x1800103cd  add     rsp, 30h
0x1800103d1  pop     r15
0x1800103d3  pop     r14
0x1800103d5  pop     r13
0x1800103d7  pop     r12
0x1800103d9  pop     rdi
0x1800103da  pop     rsi
0x1800103db  pop     rbp
0x1800103dc  retn
0x1800103dd  mov     rcx, [r14+8]
0x1800103e1  mov     rax, [r14]
0x1800103e4  mov     [rcx], rax
0x1800103e7  mov     rcx, [r14]
0x1800103ea  mov     rax, [r14+8]
0x1800103ee  mov     [rcx+8], rax
0x1800103f2  mov     rcx, [rdi+18h]
0x1800103f6  mov     rax, [rcx+8]
0x1800103fa  mov     [r14+8], rax
0x1800103fe  mov     [r14], rcx
0x180010401  mov     rax, [rcx+8]
0x180010405  mov     [rax], r14
0x180010408  mov     [rcx+8], r14
0x18001040c  jmp     loc_18001032C
0x180010411  mov     rcx, [r8+8]
0x180010415  lea     rbp, [r8+10h]
0x180010419  mov     rax, [r8]
0x18001041c  mov     edx, [rdi+58h]
0x18001041f  mov     [rcx], rax
0x180010422  mov     rcx, [r8]
0x180010425  mov     rax, [r8+8]
0x180010429  mov     [rcx+8], rax
0x18001042d  cmp     esi, edx
0x18001042f  jz      loc_1800104E5
0x180010435  mov     rcx, [r15]
0x180010438  mov     rax, [rcx+8]
0x18001043c  mov     [r8+8], rax
0x180010440  mov     [r8], rcx
0x180010443  mov     rax, [rcx+8]
0x180010447  mov     [rax], r8
0x18001044a  mov     [rcx+8], r8
0x18001044e  mov     edx, esi; unsigned int
0x180010450  mov     rcx, rbp; this
0x180010453  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180010458  shl     esi, 0Ch
0x18001045b  mov     rbx, rax
0x18001045e  mov     eax, esi
0x180010460  add     [rdi+0A0h], rax
0x180010467  mov     ecx, esi
0x180010469  lock xadd cs:qword_18043D988, rcx
0x180010472  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180010479  jz      loc_18001032C
0x18001047f  lea     r8, [rsi+rcx]
0x180010483  call    McTemplateU0x_EventWriteTransfer
0x180010488  jmp     loc_18001032C
0x18001048d  mov     dword ptr [rdi+0F0h], 0
0x180010497  jmp     loc_1800103C2
0x18001049c  lea     rcx, [rdi+0C8h]; this
0x1800104a3  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x1800104a8  jmp     loc_180010220
0x1800104ad  call    cs:__imp_InterlockedPopEntrySList
0x1800104b3  mov     rbp, rax
0x1800104b6  test    rax, rax
0x1800104b9  jz      loc_18001034B
0x1800104bf  mov     rcx, [rax+8]
0x1800104c3  mov     [r12], rcx
0x1800104c7  mov     ebx, [rax+10h]
0x1800104ca  cmp     ebx, 1
0x1800104cd  jnz     loc_180010395
0x1800104d3  xorps   xmm0, xmm0
0x1800104d6  mov     rbx, rax
0x1800104d9  movups  xmmword ptr [rax], xmm0
0x1800104dc  movups  xmmword ptr [rax+10h], xmm0
0x1800104e0  jmp     loc_1800103B0
0x1800104e5  mov     rcx, [rdi+18h]
0x1800104e9  jmp     loc_180010438
0x1800104ee  lea     r8, [rsi+rcx]
0x1800104f2  call    McTemplateU0x_EventWriteTransfer
0x1800104f7  jmp     loc_180010322
```
