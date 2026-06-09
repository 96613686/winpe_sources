# CSessionAggregator::~CSessionAggregator(void)

- ea: `0x1800203e8`
- end: `0x18002049e`
- name: `??1CSessionAggregator@@AEAA@XZ`
- size: `182`
- prototype: `void __fastcall(CSessionAggregator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800113c8`

## callees

- `0x1800203e8`
- `0x1800213d4`
- `0x180023a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800203fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800203fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002047b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002047b`

## pseudocode

```c
void __fastcall CSessionAggregator::~CSessionAggregator(CSessionAggregator *this)
{
  __int64 v2; // rsi
  void **v3; // rdi
  _QWORD *v4; // r14
  void *v5; // rcx
  void *v6; // rcx
  _QWORD v7[7]; // [rsp+20h] [rbp-38h] BYREF

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  v2 = 0;
  v7[1] = 0;
  v3 = (void **)((char *)this + 320);
  for ( v7[0] = HashTable_DeleteCB<CItemAggregator>; (unsigned int)v2 < *((_DWORD *)this + 79); v2 = (unsigned int)(v2 + 1) )
  {
    v4 = (_QWORD *)*((_QWORD *)*v3 + v2);
    while ( v4 )
    {
      CHashTable<ITEM_PROGRESS_DATA,unsigned __int64>::s_DestroyCallback(
        (char *)v4 + *((unsigned int *)this + 83),
        *((unsigned int *)this + 82),
        v7);
      v5 = v4;
      v4 = (_QWORD *)*v4;
      LocalFree(v5);
    }
    *((_QWORD *)*v3 + v2) = 0;
  }
  v6 = *v3;
  *((_QWORD *)this + 39) = 0;
  LocalFree(v6);
  *v3 = 0;
  CStringPtrArray::~CStringPtrArray((CSessionAggregator *)((char *)this + 280));
}

```

## disassembly

```asm
0x1800203e8  push    rbx
0x1800203ea  push    rbp
0x1800203eb  push    rsi
0x1800203ec  push    rdi
0x1800203ed  push    r14
0x1800203ef  sub     rsp, 30h
0x1800203f3  mov     rbx, rcx
0x1800203f6  add     rcx, 158h; lpCriticalSection
0x1800203fd  call    cs:__imp_DeleteCriticalSection
0x180020403  xor     esi, esi
0x180020405  mov     [rsp+58h+var_30], 0
0x18002040e  lea     rax, ??$HashTable_DeleteCB@VCItemAggregator@@@@YAXPEAVCItemAggregator@@@Z; HashTable_DeleteCB<CItemAggregator>(CItemAggregator *)
0x180020415  lea     rdi, [rbx+140h]
0x18002041c  mov     [rsp+58h+var_38], rax
0x180020421  cmp     [rbx+13Ch], esi
0x180020427  jbe     short loc_18002046D
0x180020429  mov     rax, [rdi]
0x18002042c  mov     r14, [rax+rsi*8]
0x180020430  jmp     short loc_180020457
0x180020432  mov     ecx, [rbx+14Ch]
0x180020438  lea     r8, [rsp+58h+var_38]
0x18002043d  mov     edx, [rbx+148h]
0x180020443  add     rcx, r14
0x180020446  call    ?s_DestroyCallback@?$CHashTable@UITEM_PROGRESS_DATA@@_K@@CAXPEAEIPEAX@Z; CHashTable<ITEM_PROGRESS_DATA,unsigned __int64>::s_DestroyCallback(uchar *,uint,void *)
0x18002044b  mov     rcx, r14; hMem
0x18002044e  mov     r14, [r14]
0x180020451  call    cs:__imp_LocalFree
0x180020457  test    r14, r14
0x18002045a  jnz     short loc_180020432
0x18002045c  mov     rax, [rdi]
0x18002045f  mov     [rax+rsi*8], r14
0x180020463  inc     esi
0x180020465  cmp     esi, [rbx+13Ch]
0x18002046b  jb      short loc_180020429
0x18002046d  mov     rcx, [rdi]; hMem
0x180020470  mov     qword ptr [rbx+138h], 0
0x18002047b  call    cs:__imp_LocalFree
0x180020481  lea     rcx, [rbx+118h]; this
0x180020488  mov     qword ptr [rdi], 0
0x18002048f  add     rsp, 30h
0x180020493  pop     r14
0x180020495  pop     rdi
0x180020496  pop     rsi
0x180020497  pop     rbp
0x180020498  pop     rbx
0x180020499  jmp     ??1CStringPtrArray@@QEAA@XZ; CStringPtrArray::~CStringPtrArray(void)
```
