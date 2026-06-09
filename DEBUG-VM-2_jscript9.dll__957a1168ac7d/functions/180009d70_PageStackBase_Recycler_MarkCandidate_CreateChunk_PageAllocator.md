# PageStackBase<Recycler::MarkCandidate>::CreateChunk(PageAllocator *)

- ea: `0x180009d70`
- end: `0x18000a0ac`
- name: `?CreateChunk@?$PageStackBase@UMarkCandidate@Recycler@@@@QEAAPEAUChunk@1@PEAVPageAllocator@@@Z`
- size: `828`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005890`
- `0x180005a10`
- `0x180007310`
- `0x1800077e0`
- `0x180008e4c`
- `0x1800095f4`
- `0x180009a10`
- `0x180009cc0`
- `0x18000a9f0`
- `0x180126bc0`
- `0x18014b16c`
- `0x1801ae8f4`

## callees

- `0x1800052bc`
- `0x180009d70`
- `0x180010e48`
- `0x18006a5f0`
- `0x180255c94`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18000a07a`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000a07a`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a029`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a029`

## pseudocode

```c
char *__fastcall PageStackBase<Recycler::MarkCandidate>::CreateChunk(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 *v4; // r15
  __int64 *v5; // r14
  struct PageSegment *v6; // rsi
  int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // edx
  unsigned int v10; // ecx
  __int64 v11; // rcx
  int v12; // r9d
  __int64 v13; // rdx
  char *v14; // rbx
  signed __int64 v15; // r8
  union _SLIST_HEADER *v17; // rcx
  _QWORD **v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  int v22; // r9d
  unsigned int v23; // r8d
  int v24; // r8d
  signed __int64 v25; // r8
  PSLIST_ENTRY v26; // rax
  PSLIST_ENTRY v27; // rbp
  int Next; // ebx
  int v29; // ebx
  struct PageSegment *v30; // [rsp+28h] [rbp-30h] BYREF

  v2 = *(_DWORD *)(a2 + 152) == 0;
  v30 = 0;
  *(_BYTE *)(a2 + 139) = 1;
  if ( v2 )
    AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(a2 + 200));
  v4 = (__int64 *)(a2 + 8);
  if ( *(_QWORD *)(a2 + 104) )
  {
    v5 = (__int64 *)(a2 + 8);
    while ( 1 )
    {
      v5 = (__int64 *)*v5;
      if ( v5 == v4 )
        break;
      v6 = (struct PageSegment *)(v5 + 2);
      v7 = *((_DWORD *)v5 + 18);
      if ( v7 )
      {
        v8 = *((_DWORD *)v5 + 16);
        v9 = -1;
        v2 = !_BitScanForward(&v10, v8);
        if ( !v2 )
          v9 = v10;
        if ( v9 != -1 )
        {
          v11 = v5[5] - *((unsigned int *)v5 + 12) - v9;
          if ( v5[5] - *((unsigned int *)v5 + 12) != v9 )
          {
            v12 = v8 & ~(1 << v9);
            v13 = v9 << 12;
            *((_DWORD *)v5 + 16) = v12;
            *((_DWORD *)v5 + 18) = v7 - 1;
            v14 = (char *)(v5[4] + (unsigned int)v13);
            if ( v14 )
            {
              *(_QWORD *)(a2 + 160) += 4096LL;
              v15 = _InterlockedExchangeAdd64(&qword_18043D988, 0x1000u);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
                McTemplateU0x_EventWriteTransfer(v11, v13, v15 + 4096);
              if ( !*((_DWORD *)v5 + 18) )
              {
                *(_QWORD *)v5[1] = *v5;
                *(_QWORD *)(*v5 + 8) = v5[1];
                v19 = *(_QWORD *)(a2 + 24);
                v5[1] = *(_QWORD *)(v19 + 8);
                *v5 = v19;
                **(_QWORD **)(v19 + 8) = v5;
                *(_QWORD *)(v19 + 8) = v5;
              }
              goto LABEL_16;
            }
          }
        }
      }
    }
    v17 = *(union _SLIST_HEADER **)(a2 + 128);
    if ( v17 )
    {
      v26 = InterlockedPopEntrySList(v17);
      v27 = v26;
      if ( v26 )
      {
        v6 = (struct PageSegment *)*((_QWORD *)&v26->Next + 1);
        Next = (int)v26[1].Next;
        v30 = v6;
        if ( Next == 1 )
        {
          v14 = (char *)v26;
          *v26 = 0;
          v26[1] = 0;
        }
        else
        {
          v29 = Next - 1;
          LODWORD(v26[1].Next) = v29;
          InterlockedPushEntrySList(*(PSLIST_HEADER *)(a2 + 128), v26);
          v14 = (char *)v27 + (unsigned int)(v29 << 12);
        }
        if ( v14 )
          goto LABEL_17;
      }
    }
  }
  v18 = *(_QWORD ***)(a2 + 40);
  if ( v18 == (_QWORD **)(a2 + 40) )
  {
    v14 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)a2, 1u, &v30);
    if ( v14 )
    {
LABEL_24:
      v6 = v30;
      goto LABEL_17;
    }
    v6 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)a2);
    if ( !v6 )
    {
      v14 = 0;
      goto LABEL_24;
    }
  }
  else
  {
    v6 = (struct PageSegment *)(v18 + 2);
    v20 = *(unsigned int *)(a2 + 88);
    *v18[1] = *v18;
    (*v18)[1] = v18[1];
    if ( (_DWORD)v20 == 1 )
      v21 = *(_QWORD **)(a2 + 24);
    else
      v21 = (_QWORD *)*v4;
    v18[1] = (_QWORD *)v21[1];
    *v18 = v21;
    *(_QWORD *)v21[1] = v18;
    v21[1] = v18;
  }
  v22 = *((_DWORD *)v6 + 14);
  if ( !v22 )
    goto LABEL_41;
  v23 = *((_DWORD *)v6 + 12);
  v2 = !_BitScanForward((unsigned int *)&v21, v23);
  v20 = 0xFFFFFFFFLL;
  if ( !v2 )
    v20 = (unsigned int)v21;
  if ( (_DWORD)v20 == -1
    || (v21 = (_QWORD *)(*((_QWORD *)v6 + 3) - *((unsigned int *)v6 + 8) - (unsigned int)v20),
        *((_QWORD *)v6 + 3) - *((unsigned int *)v6 + 8) == (unsigned int)v20) )
  {
LABEL_41:
    v14 = 0;
  }
  else
  {
    v24 = v23 & ~(1 << v20);
    v20 = (unsigned int)((_DWORD)v20 << 12);
    *((_DWORD *)v6 + 12) = v24;
    v14 = (char *)(*((_QWORD *)v6 + 2) + (unsigned int)v20);
    *((_DWORD *)v6 + 14) = v22 - 1;
  }
  *(_QWORD *)(a2 + 160) += 4096LL;
  v25 = _InterlockedExchangeAdd64(&qword_18043D988, 0x1000u);
  if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
    McTemplateU0x_EventWriteTransfer(v21, v20, v25 + 4096);
LABEL_16:
  --*(_QWORD *)(a2 + 104);
LABEL_17:
  if ( !*(_DWORD *)(a2 + 152) )
    *(_DWORD *)(a2 + 240) = 0;
  if ( !v14 )
    return 0;
  *((_QWORD *)v14 + 1) = v6;
  *((_QWORD *)v14 + 3) = v14 + 4096;
  return v14;
}

```

## disassembly

```asm
0x180009d70  mov     rax, rsp
0x180009d73  mov     [rax+18h], rbx
0x180009d77  mov     [rax+10h], rdx
0x180009d7b  mov     [rax+8], rcx
0x180009d7f  push    rbp
0x180009d80  push    rsi
0x180009d81  push    rdi
0x180009d82  push    r14
0x180009d84  push    r15
0x180009d86  sub     rsp, 30h
0x180009d8a  cmp     dword ptr [rdx+98h], 0
0x180009d91  mov     rdi, rdx
0x180009d94  mov     qword ptr [rax-30h], 0
0x180009d9c  mov     byte ptr [rdx+8Bh], 1
0x180009da3  jz      loc_18000A018
0x180009da9  or      r10d, 0FFFFFFFFh
0x180009dad  lea     r15, [rdi+8]
0x180009db1  cmp     qword ptr [rdi+68h], 1
0x180009db6  jb      loc_180009E9E
0x180009dbc  mov     r14, r15
0x180009dbf  mov     r14, [r14]
0x180009dc2  cmp     r14, r15
0x180009dc5  jz      loc_180009E8E
0x180009dcb  lea     rsi, [r14+10h]
0x180009dcf  mov     r8d, [rsi+38h]
0x180009dd3  cmp     r8d, 1
0x180009dd7  jb      short loc_180009DBF
0x180009dd9  mov     r9d, [rsi+30h]
0x180009ddd  mov     edx, r10d
0x180009de0  bsf     ecx, r9d
0x180009de4  mov     [rsp+58h+var_38], 0
0x180009dec  setnz   al
0x180009def  test    al, al
0x180009df1  cmovnz  edx, ecx
0x180009df4  cmp     edx, r10d
0x180009df7  jz      short loc_180009DBF
0x180009df9  mov     eax, [rsi+20h]
0x180009dfc  mov     rcx, [rsi+18h]
0x180009e00  sub     rcx, rax
0x180009e03  mov     eax, edx
0x180009e05  sub     rcx, rax
0x180009e08  cmp     rcx, 1
0x180009e0c  jb      short loc_180009DBF
0x180009e0e  btr     r9d, edx
0x180009e12  shl     edx, 0Ch
0x180009e15  mov     [rsi+30h], r9d
0x180009e19  lea     eax, [r8-1]
0x180009e1d  mov     ebx, edx
0x180009e1f  mov     [rsi+38h], eax
0x180009e22  add     rbx, [rsi+10h]
0x180009e26  jz      short loc_180009DBF
0x180009e28  mov     r8d, 1000h
0x180009e2e  add     [rdi+0A0h], r8
0x180009e35  lock xadd cs:qword_18043D988, r8
0x180009e3e  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180009e45  jnz     loc_18000A094
0x180009e4b  cmp     dword ptr [rsi+38h], 0
0x180009e4f  jz      short loc_180009ECF
0x180009e51  dec     qword ptr [rdi+68h]
0x180009e55  cmp     dword ptr [rdi+98h], 0
0x180009e5c  jz      loc_180009FDC
0x180009e62  test    rbx, rbx
0x180009e65  jz      loc_18000A0A5
0x180009e6b  lea     rcx, [rbx+1000h]
0x180009e72  mov     [rbx+8], rsi
0x180009e76  mov     [rbx+18h], rcx
0x180009e7a  mov     rax, rbx
0x180009e7d  mov     rbx, [rsp+58h+arg_10]
0x180009e82  add     rsp, 30h
0x180009e86  pop     r15
0x180009e88  pop     r14
0x180009e8a  pop     rdi
0x180009e8b  pop     rsi
0x180009e8c  pop     rbp
0x180009e8d  retn
0x180009e8e  mov     rcx, [rdi+80h]; ListHead
0x180009e95  test    rcx, rcx
0x180009e98  jnz     loc_18000A029
0x180009e9e  lea     rax, [rdi+28h]
0x180009ea2  mov     r8, [rax]
0x180009ea5  cmp     r8, rax
0x180009ea8  jnz     short loc_180009F03
0x180009eaa  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x180009eaf  mov     edx, 1; unsigned int
0x180009eb4  mov     rcx, rdi; this
0x180009eb7  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180009ebc  mov     rbx, rax
0x180009ebf  test    rax, rax
0x180009ec2  jz      loc_180009FEB
0x180009ec8  mov     rsi, [rsp+58h+var_30]
0x180009ecd  jmp     short loc_180009E55
0x180009ecf  mov     rcx, [r14+8]
0x180009ed3  mov     rax, [r14]
0x180009ed6  mov     [rcx], rax
0x180009ed9  mov     rcx, [r14]
0x180009edc  mov     rax, [r14+8]
0x180009ee0  mov     [rcx+8], rax
0x180009ee4  mov     rcx, [rdi+18h]
0x180009ee8  mov     rax, [rcx+8]
0x180009eec  mov     [r14+8], rax
0x180009ef0  mov     [r14], rcx
0x180009ef3  mov     rax, [rcx+8]
0x180009ef7  mov     [rax], r14
0x180009efa  mov     [rcx+8], r14
0x180009efe  jmp     loc_180009E51
0x180009f03  mov     rcx, [r8+8]
0x180009f07  lea     rsi, [r8+10h]
0x180009f0b  mov     rax, [r8]
0x180009f0e  mov     edx, [rdi+58h]
0x180009f11  mov     [rcx], rax
0x180009f14  mov     rcx, [r8]
0x180009f17  mov     rax, [r8+8]
0x180009f1b  mov     [rcx+8], rax
0x180009f1f  cmp     edx, 1
0x180009f22  jz      loc_18000A062
0x180009f28  mov     rcx, [r15]
0x180009f2b  mov     rax, [rcx+8]
0x180009f2f  mov     [r8+8], rax
0x180009f33  mov     [r8], rcx
0x180009f36  mov     rax, [rcx+8]
0x180009f3a  mov     [rax], r8
0x180009f3d  mov     [rcx+8], r8
0x180009f41  mov     r9d, [rsi+38h]
0x180009f45  cmp     r9d, 1
0x180009f49  jb      loc_18000A05B
0x180009f4f  mov     r8d, [rsi+30h]
0x180009f53  bsf     ecx, r8d
0x180009f57  mov     [rsp+58h+var_38], 0
0x180009f5f  setnz   al
0x180009f62  or      r10d, 0FFFFFFFFh
0x180009f66  test    al, al
0x180009f68  mov     edx, r10d
0x180009f6b  cmovnz  edx, ecx
0x180009f6e  cmp     edx, r10d
0x180009f71  jz      loc_18000A05B
0x180009f77  mov     eax, [rsi+20h]
0x180009f7a  mov     rcx, [rsi+18h]
0x180009f7e  sub     rcx, rax
0x180009f81  mov     eax, edx
0x180009f83  sub     rcx, rax
0x180009f86  cmp     rcx, 1
0x180009f8a  jb      loc_18000A05B
0x180009f90  btr     r8d, edx
0x180009f94  shl     edx, 0Ch
0x180009f97  mov     [rsi+30h], r8d
0x180009f9b  lea     eax, [r9-1]
0x180009f9f  mov     ebx, edx
0x180009fa1  add     rbx, [rsi+10h]
0x180009fa5  mov     [rsi+38h], eax
0x180009fa8  mov     r8d, 1000h
0x180009fae  add     [rdi+0A0h], r8
0x180009fb5  lock xadd cs:qword_18043D988, r8
0x180009fbe  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180009fc5  jz      loc_180009E51
0x180009fcb  add     r8, 1000h
0x180009fd2  call    McTemplateU0x_EventWriteTransfer
0x180009fd7  jmp     loc_180009E51
0x180009fdc  mov     dword ptr [rdi+0F0h], 0
0x180009fe6  jmp     loc_180009E62
0x180009feb  cmp     dword ptr [rdi+58h], 1
0x180009fef  mov     edx, 18h
0x180009ff4  mov     rcx, rdi; this
0x180009ff7  lea     eax, [rdx-10h]
0x180009ffa  cmovnz  edx, eax
0x180009ffd  add     rdx, rdi
0x18000a000  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x18000a005  mov     rsi, rax
0x18000a008  test    rax, rax
0x18000a00b  jnz     loc_180009F41
0x18000a011  xor     ebx, ebx
0x18000a013  jmp     loc_180009EC8
0x18000a018  lea     rcx, [rdi+0C8h]; this
0x18000a01f  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x18000a024  jmp     loc_180009DA9
0x18000a029  call    cs:__imp_InterlockedPopEntrySList
0x18000a02f  mov     rbp, rax
0x18000a032  test    rax, rax
0x18000a035  jz      loc_180009E9E
0x18000a03b  mov     rsi, [rax+8]
0x18000a03f  mov     ebx, [rax+10h]
0x18000a042  mov     [rsp+58h+var_30], rsi
0x18000a047  cmp     ebx, 1
0x18000a04a  jnz     short loc_18000A06B
0x18000a04c  xorps   xmm0, xmm0
0x18000a04f  mov     rbx, rax
0x18000a052  movups  xmmword ptr [rax], xmm0
0x18000a055  movups  xmmword ptr [rax+10h], xmm0
0x18000a059  jmp     short loc_18000A086
0x18000a05b  xor     ebx, ebx
0x18000a05d  jmp     loc_180009FA8
0x18000a062  mov     rcx, [rdi+18h]
0x18000a066  jmp     loc_180009F2B
0x18000a06b  dec     ebx
0x18000a06d  mov     rdx, rbp; ListEntry
0x18000a070  mov     [rax+10h], ebx
0x18000a073  mov     rcx, [rdi+80h]; ListHead
0x18000a07a  call    cs:__imp_InterlockedPushEntrySList
0x18000a080  shl     ebx, 0Ch
0x18000a083  add     rbx, rbp
0x18000a086  test    rbx, rbx
0x18000a089  jnz     loc_180009E55
0x18000a08f  jmp     loc_180009E9E
0x18000a094  add     r8, 1000h
0x18000a09b  call    McTemplateU0x_EventWriteTransfer
0x18000a0a0  jmp     loc_180009E4B
0x18000a0a5  xor     eax, eax
0x18000a0a7  jmp     loc_180009E7D
```
