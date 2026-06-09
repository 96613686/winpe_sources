# PageAllocator::AllocPagesForBytes(unsigned __int64)

- ea: `0x18000f7c4`
- end: `0x18000fb4b`
- name: `?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z`
- size: `903`
- prototype: `struct PageAllocation *__fastcall(PageAllocator *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fb60`
- `0x180010504`
- `0x180082510`
- `0x18010725c`

## callees

- `0x1800052bc`
- `0x18000ef2c`
- `0x18000f7c4`
- `0x180010e48`
- `0x18006a5f0`
- `0x180255a38`
- `0x180255c94`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18000faec`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000faec`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000faa2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000faa2`

## pseudocode

```c
struct PageAllocation *__fastcall PageAllocator::AllocPagesForBytes(PSLIST_HEADER *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v4; // r15
  bool v5; // zf
  PSLIST_HEADER *v6; // r12
  PSLIST_HEADER *v7; // r14
  struct PageSegment *v8; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r10d
  unsigned int v12; // edx
  unsigned int v13; // r9d
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  char *v16; // rbx
  unsigned __int64 v17; // rcx
  signed __int64 v18; // rax
  union _SLIST_HEADER *v20; // rcx
  PageAllocator *v21; // r8
  PSLIST_HEADER v22; // rcx
  int v23; // edx
  PSLIST_HEADER v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  signed __int64 v27; // rax
  PSLIST_ENTRY v28; // rax
  PSLIST_ENTRY v29; // r14
  int Next; // ebx
  int v31; // ebx
  struct Segment *v32; // rax
  struct PageSegment *v33; // [rsp+28h] [rbp-30h] BYREF

  if ( a2 + 4111 >= a2 && a2 != -4112 )
  {
    v2 = *((unsigned int *)this + 22);
    v4 = (a2 + 4111) >> 12;
    v33 = 0;
    if ( v4 > v2 )
    {
      v32 = PageAllocator::AllocSegment((PageAllocator *)this, v4);
      v8 = v32;
      if ( v32 )
      {
        v16 = (char *)*((_QWORD *)v32 + 2);
        *(_QWORD *)v16 = *((_QWORD *)v32 + 3) - *((unsigned int *)v32 + 8);
        goto LABEL_30;
      }
      return 0;
    }
    v5 = *((_DWORD *)this + 38) == 0;
    *((_BYTE *)this + 139) = 1;
    if ( v5 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(this + 25));
    v6 = this + 1;
    if ( (unsigned __int64)this[13] < (unsigned int)v4 )
      goto LABEL_34;
    v7 = this + 1;
LABEL_8:
    while ( 1 )
    {
      v7 = (PSLIST_HEADER *)*v7;
      if ( v7 == v6 )
        break;
      v8 = (struct PageSegment *)(v7 + 2);
      v9 = *((_DWORD *)v7 + 18);
      if ( v9 >= (unsigned int)v4 )
      {
        v10 = *((_DWORD *)v7 + 16);
        v11 = -1;
        v5 = !_BitScanForward(&v12, v10);
        if ( !v5 )
          v11 = v12;
        v13 = 0xFFFFFFFF >> (32 - v4);
        while ( v11 != -1 )
        {
          v14 = (unsigned __int64)v7[5] - *((unsigned int *)v7 + 12) - v11;
          if ( v14 < (unsigned int)v4 )
            break;
          if ( (_DWORD)v4 == 1 || (v14 = v13 << v11, ((unsigned int)v14 & v10) == (_DWORD)v14) )
          {
            *((_DWORD *)v7 + 16) = v10 & ~(v13 << v11);
            *((_DWORD *)v7 + 18) = v9 - v4;
            v16 = (char *)&v7[4][256 * v11];
            if ( !v16 )
              goto LABEL_8;
            v17 = (unsigned int)((_DWORD)v4 << 12);
            this[20] = (PSLIST_HEADER)((char *)this[20] + v17);
            v18 = _InterlockedExchangeAdd64(&qword_18043D988, v17);
            if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              McTemplateU0x_EventWriteTransfer(v17, v14, v17 + v18);
            if ( !*((_DWORD *)v7 + 18) )
            {
              v7[1]->Alignment = (ULONGLONG)*v7;
              (*v7)->Region = (ULONGLONG)v7[1];
              v22 = this[3];
              v7[1] = (PSLIST_HEADER)v22->Region;
              *v7 = v22;
              *(_QWORD *)v22->Region = v7;
              v22->Region = (ULONGLONG)v7;
            }
            goto LABEL_25;
          }
          v5 = !_BitScanForward(&v15, v10 & (-1 << (v11 + 1)));
          v11 = -1;
          if ( !v5 )
            v11 = v15;
        }
      }
    }
    if ( (_DWORD)v4 != 1 )
      goto LABEL_34;
    v20 = this[16];
    if ( !v20 )
      goto LABEL_34;
    v28 = InterlockedPopEntrySList(v20);
    v29 = v28;
    if ( !v28 )
      goto LABEL_34;
    v8 = (struct PageSegment *)*((_QWORD *)&v28->Next + 1);
    Next = (int)v28[1].Next;
    v33 = v8;
    if ( Next == 1 )
    {
      v16 = (char *)v28;
      *v28 = 0;
      v28[1] = 0;
    }
    else
    {
      v31 = Next - 1;
      LODWORD(v28[1].Next) = v31;
      InterlockedPushEntrySList(this[16], v28);
      v16 = (char *)v29 + (unsigned int)(v31 << 12);
    }
    if ( !v16 )
    {
LABEL_34:
      v21 = (PageAllocator *)this[5];
      if ( v21 == (PageAllocator *)(this + 5) )
      {
        v16 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)this, v4, &v33);
        if ( v16 )
        {
LABEL_36:
          v8 = v33;
          goto LABEL_26;
        }
        v8 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)this);
        if ( !v8 )
        {
          v16 = 0;
          goto LABEL_36;
        }
      }
      else
      {
        v8 = (PageAllocator *)((char *)v21 + 16);
        v23 = *((_DWORD *)this + 22);
        **((_QWORD **)v21 + 1) = *(_QWORD *)v21;
        *(_QWORD *)(*(_QWORD *)v21 + 8LL) = *((_QWORD *)v21 + 1);
        if ( (_DWORD)v4 == v23 )
          v24 = this[3];
        else
          v24 = *v6;
        *((_QWORD *)v21 + 1) = v24->Region;
        *(_QWORD *)v21 = v24;
        *(_QWORD *)v24->Region = v21;
        v24->Region = (ULONGLONG)v21;
      }
      v16 = PageSegment::AllocPages(v8, v4);
      v26 = (unsigned int)((_DWORD)v4 << 12);
      this[20] = (PSLIST_HEADER)((char *)this[20] + v26);
      v27 = _InterlockedExchangeAdd64(&qword_18043D988, v26);
      if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
        McTemplateU0x_EventWriteTransfer(v26, v25, v26 + v27);
LABEL_25:
      this[13] = (PSLIST_HEADER)((char *)this[13] - (unsigned int)v4);
    }
LABEL_26:
    if ( !*((_DWORD *)this + 38) )
      *((_DWORD *)this + 60) = 0;
    if ( v16 )
    {
      *(_QWORD *)v16 = v4;
LABEL_30:
      *((_QWORD *)v16 + 1) = v8;
      return (struct PageAllocation *)v16;
    }
    return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f7c4  mov     r11, rsp
0x18000f7c7  mov     [r11+18h], rbx
0x18000f7cb  mov     [r11+20h], rbp
0x18000f7cf  mov     [r11+10h], rdx
0x18000f7d3  mov     [r11+8], rcx
0x18000f7d7  push    rsi
0x18000f7d8  push    rdi
0x18000f7d9  push    r12
0x18000f7db  push    r14
0x18000f7dd  push    r15
0x18000f7df  sub     rsp, 30h
0x18000f7e3  mov     rax, rdx
0x18000f7e6  lea     r15, [rdx+100Fh]
0x18000f7ed  cmp     r15, rax
0x18000f7f0  jb      loc_18000FB44
0x18000f7f6  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000f7fa  jz      loc_18000FB44
0x18000f800  mov     eax, [rcx+58h]
0x18000f803  mov     rdi, rcx
0x18000f806  shr     r15, 0Ch
0x18000f80a  mov     qword ptr [r11-30h], 0
0x18000f812  cmp     r15, rax
0x18000f815  ja      loc_18000FB06
0x18000f81b  cmp     dword ptr [rcx+98h], 0
0x18000f822  mov     byte ptr [rcx+8Bh], 1
0x18000f829  jz      loc_18000FA91
0x18000f82f  mov     ebp, r15d
0x18000f832  lea     r12, [rdi+8]
0x18000f836  cmp     [rdi+68h], rbp
0x18000f83a  jb      loc_18000F97B
0x18000f840  mov     r11d, 20h ; ' '
0x18000f846  mov     r14, r12
0x18000f849  sub     r11d, ebp
0x18000f84c  or      r8d, 0FFFFFFFFh
0x18000f850  mov     r14, [r14]
0x18000f853  cmp     r14, r12
0x18000f856  jz      loc_18000F966
0x18000f85c  lea     rsi, [r14+10h]
0x18000f860  mov     ebx, [rsi+38h]
0x18000f863  cmp     ebx, ebp
0x18000f865  jb      short loc_18000F850
0x18000f867  mov     eax, [rsi+30h]
0x18000f86a  mov     r10d, r8d
0x18000f86d  bsf     edx, eax
0x18000f870  mov     r9d, r8d
0x18000f873  setnz   cl
0x18000f876  test    cl, cl
0x18000f878  mov     ecx, r11d
0x18000f87b  cmovnz  r10d, edx
0x18000f87f  shr     r9d, cl
0x18000f882  mov     [rsp+58h+var_38], 0
0x18000f88a  cmp     r10d, r8d
0x18000f88d  jz      short loc_18000F850
0x18000f88f  mov     ecx, [rsi+20h]
0x18000f892  mov     rdx, [rsi+18h]
0x18000f896  sub     rdx, rcx
0x18000f899  mov     ecx, r10d
0x18000f89c  sub     rdx, rcx
0x18000f89f  cmp     rdx, rbp
0x18000f8a2  jb      short loc_18000F850
0x18000f8a4  cmp     ebp, 1
0x18000f8a7  jz      short loc_18000F8DB
0x18000f8a9  mov     ecx, r10d
0x18000f8ac  mov     edx, r9d
0x18000f8af  shl     edx, cl
0x18000f8b1  mov     ecx, eax
0x18000f8b3  and     ecx, edx
0x18000f8b5  cmp     ecx, edx
0x18000f8b7  jz      short loc_18000F8DB
0x18000f8b9  lea     ecx, [r10+1]
0x18000f8bd  mov     edx, r8d
0x18000f8c0  shl     edx, cl
0x18000f8c2  and     edx, eax
0x18000f8c4  bsf     r8d, edx
0x18000f8c8  setnz   cl
0x18000f8cb  or      r10d, 0FFFFFFFFh
0x18000f8cf  test    cl, cl
0x18000f8d1  cmovnz  r10d, r8d
0x18000f8d5  or      r8d, 0FFFFFFFFh
0x18000f8d9  jmp     short loc_18000F882
0x18000f8db  sub     ebx, ebp
0x18000f8dd  mov     ecx, r10d
0x18000f8e0  shl     r9d, cl
0x18000f8e3  shl     r10d, 0Ch
0x18000f8e7  not     r9d
0x18000f8ea  and     r9d, eax
0x18000f8ed  mov     [rsi+30h], r9d
0x18000f8f1  mov     [rsi+38h], ebx
0x18000f8f4  mov     ebx, r10d
0x18000f8f7  add     rbx, [rsi+10h]
0x18000f8fb  jz      loc_18000F850
0x18000f901  mov     eax, ebp
0x18000f903  shl     eax, 0Ch
0x18000f906  mov     ecx, eax
0x18000f908  add     [rdi+0A0h], rcx
0x18000f90f  lock xadd cs:qword_18043D988, rax
0x18000f918  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000f91f  jnz     loc_18000FB36
0x18000f925  cmp     dword ptr [rsi+38h], 0
0x18000f929  jz      short loc_18000F9A9
0x18000f92b  sub     [rdi+68h], rbp
0x18000f92f  cmp     dword ptr [rdi+98h], 0
0x18000f936  jz      loc_18000FA5A
0x18000f93c  test    rbx, rbx
0x18000f93f  jz      loc_18000FB2F
0x18000f945  mov     [rbx], r15
0x18000f948  mov     [rbx+8], rsi
0x18000f94c  mov     rax, rbx
0x18000f94f  mov     rbx, [rsp+58h+arg_10]
0x18000f954  mov     rbp, [rsp+58h+arg_18]
0x18000f959  add     rsp, 30h
0x18000f95d  pop     r15
0x18000f95f  pop     r14
0x18000f961  pop     r12
0x18000f963  pop     rdi
0x18000f964  pop     rsi
0x18000f965  retn
0x18000f966  cmp     ebp, 1
0x18000f969  jnz     short loc_18000F97B
0x18000f96b  mov     rcx, [rdi+80h]; ListHead
0x18000f972  test    rcx, rcx
0x18000f975  jnz     loc_18000FAA2
0x18000f97b  lea     rax, [rdi+28h]
0x18000f97f  mov     r8, [rax]
0x18000f982  cmp     r8, rax
0x18000f985  jnz     short loc_18000F9DD
0x18000f987  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x18000f98c  mov     edx, ebp; unsigned int
0x18000f98e  mov     rcx, rdi; this
0x18000f991  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x18000f996  mov     rbx, rax
0x18000f999  test    rax, rax
0x18000f99c  jz      loc_18000FA69
0x18000f9a2  mov     rsi, [rsp+58h+var_30]
0x18000f9a7  jmp     short loc_18000F92F
0x18000f9a9  mov     rcx, [r14+8]
0x18000f9ad  mov     rax, [r14]
0x18000f9b0  mov     [rcx], rax
0x18000f9b3  mov     rcx, [r14]
0x18000f9b6  mov     rax, [r14+8]
0x18000f9ba  mov     [rcx+8], rax
0x18000f9be  mov     rcx, [rdi+18h]
0x18000f9c2  mov     rax, [rcx+8]
0x18000f9c6  mov     [r14+8], rax
0x18000f9ca  mov     [r14], rcx
0x18000f9cd  mov     rax, [rcx+8]
0x18000f9d1  mov     [rax], r14
0x18000f9d4  mov     [rcx+8], r14
0x18000f9d8  jmp     loc_18000F92B
0x18000f9dd  mov     rcx, [r8+8]
0x18000f9e1  lea     rsi, [r8+10h]
0x18000f9e5  mov     rax, [r8]
0x18000f9e8  mov     edx, [rdi+58h]
0x18000f9eb  mov     [rcx], rax
0x18000f9ee  mov     rcx, [r8]
0x18000f9f1  mov     rax, [r8+8]
0x18000f9f5  mov     [rcx+8], rax
0x18000f9f9  cmp     ebp, edx
0x18000f9fb  jz      loc_18000FAD4
0x18000fa01  mov     rcx, [r12]
0x18000fa05  mov     rax, [rcx+8]
0x18000fa09  mov     [r8+8], rax
0x18000fa0d  mov     [r8], rcx
0x18000fa10  mov     rax, [rcx+8]
0x18000fa14  mov     [rax], r8
0x18000fa17  mov     [rcx+8], r8
0x18000fa1b  mov     edx, ebp; unsigned int
0x18000fa1d  mov     rcx, rsi; this
0x18000fa20  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x18000fa25  mov     rbx, rax
0x18000fa28  mov     eax, ebp
0x18000fa2a  shl     eax, 0Ch
0x18000fa2d  mov     ecx, eax
0x18000fa2f  add     [rdi+0A0h], rcx
0x18000fa36  lock xadd cs:qword_18043D988, rax
0x18000fa3f  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000fa46  jz      loc_18000F92B
0x18000fa4c  lea     r8, [rcx+rax]
0x18000fa50  call    McTemplateU0x_EventWriteTransfer
0x18000fa55  jmp     loc_18000F92B
0x18000fa5a  mov     dword ptr [rdi+0F0h], 0
0x18000fa64  jmp     loc_18000F93C
0x18000fa69  cmp     ebp, [rdi+58h]
0x18000fa6c  mov     edx, 18h
0x18000fa71  mov     rcx, rdi; this
0x18000fa74  lea     eax, [rdx-10h]
0x18000fa77  cmovnz  edx, eax
0x18000fa7a  add     rdx, rdi
0x18000fa7d  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x18000fa82  mov     rsi, rax
0x18000fa85  test    rax, rax
0x18000fa88  jnz     short loc_18000FA1B
0x18000fa8a  xor     ebx, ebx
0x18000fa8c  jmp     loc_18000F9A2
0x18000fa91  lea     rcx, [rdi+0C8h]; this
0x18000fa98  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x18000fa9d  jmp     loc_18000F82F
0x18000faa2  call    cs:__imp_InterlockedPopEntrySList
0x18000faa8  mov     r14, rax
0x18000faab  test    rax, rax
0x18000faae  jz      loc_18000F97B
0x18000fab4  mov     rsi, [rax+8]
0x18000fab8  mov     ebx, [rax+10h]
0x18000fabb  mov     [rsp+58h+var_30], rsi
0x18000fac0  cmp     ebx, 1
0x18000fac3  jnz     short loc_18000FADD
0x18000fac5  xorps   xmm0, xmm0
0x18000fac8  mov     rbx, rax
0x18000facb  movups  xmmword ptr [rax], xmm0
0x18000face  movups  xmmword ptr [rax+10h], xmm0
0x18000fad2  jmp     short loc_18000FAF8
0x18000fad4  mov     rcx, [rdi+18h]
0x18000fad8  jmp     loc_18000FA05
0x18000fadd  dec     ebx
0x18000fadf  mov     rdx, r14; ListEntry
0x18000fae2  mov     [rax+10h], ebx
0x18000fae5  mov     rcx, [rdi+80h]; ListHead
0x18000faec  call    cs:__imp_InterlockedPushEntrySList
0x18000faf2  shl     ebx, 0Ch
0x18000faf5  add     rbx, r14
0x18000faf8  test    rbx, rbx
0x18000fafb  jnz     loc_18000F92F
0x18000fb01  jmp     loc_18000F97B
0x18000fb06  mov     rdx, r15; unsigned __int64
0x18000fb09  mov     rcx, rdi; this
0x18000fb0c  call    ?AllocSegment@PageAllocator@@IEAAPEAVSegment@@_K@Z; PageAllocator::AllocSegment(unsigned __int64)
0x18000fb11  mov     rsi, rax
0x18000fb14  test    rax, rax
0x18000fb17  jz      short loc_18000FB2F
0x18000fb19  mov     rbx, [rax+10h]
0x18000fb1d  mov     eax, [rax+20h]
0x18000fb20  mov     rcx, [rsi+18h]
0x18000fb24  sub     rcx, rax
0x18000fb27  mov     [rbx], rcx
0x18000fb2a  jmp     loc_18000F948
0x18000fb2f  xor     ebx, ebx
0x18000fb31  jmp     loc_18000F94C
0x18000fb36  lea     r8, [rcx+rax]
0x18000fb3a  call    McTemplateU0x_EventWriteTransfer
0x18000fb3f  jmp     loc_18000F925
0x18000fb44  xor     eax, eax
0x18000fb46  jmp     loc_18000F94F
```
