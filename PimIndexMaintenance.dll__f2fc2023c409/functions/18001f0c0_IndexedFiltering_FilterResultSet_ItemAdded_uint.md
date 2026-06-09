# IndexedFiltering::FilterResultSet::ItemAdded(uint)

- ea: `0x18001f0c0`
- end: `0x18001f1d9`
- name: `?ItemAdded@FilterResultSet@IndexedFiltering@@UEAAJI@Z`
- size: `281`
- prototype: `__int64 __fastcall(IndexedFiltering::FilterResultSet *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180002da8`
- `0x18001f0c0`
- `0x18001f3c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f102`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f1ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f1ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1c8`

## string_xrefs

- `0x18001f112`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`
- `0x18001f1a1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::FilterResultSet::ItemAdded(
        IndexedFiltering::FilterResultSet *this,
        unsigned int a2)
{
  unsigned int v3; // eax
  unsigned int v5; // esi
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r11
  int v14; // r10d
  __int64 v15; // r8
  int v16; // eax
  HANDLE v17; // rax

  v3 = *((_DWORD *)this + 8) + 1;
  if ( a2 >= v3 )
  {
    v10 = -2147024809;
    Log_HREvent(
      2147942487LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
      389);
    goto LABEL_13;
  }
  v5 = (v3 >> 5) + 1;
  if ( *((_DWORD *)this + 9) < v5 )
  {
    v6 = (void *)*((_QWORD *)this + 3);
    ProcessHeap = GetProcessHeap();
    v8 = HeapReAlloc(ProcessHeap, 8u, v6, 4LL * v5);
    if ( !v8 )
    {
      v10 = -2147024882;
      Log_HREvent_9(
        2147942414LL,
        v9,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
        404);
      goto LABEL_13;
    }
    *((_QWORD *)this + 3) = v8;
    *((_DWORD *)this + 9) = v5;
  }
  v11 = *((_QWORD *)this + 3);
  v12 = a2 >> 5;
  v13 = (unsigned int)(v12 + 1);
  v10 = 0;
  v14 = *(_DWORD *)(v11 + 4 * v12) >> 31;
  *(_DWORD *)(v11 + 4LL * (unsigned int)v12) = *(_DWORD *)(v11 + 4LL * (unsigned int)v12) & ~(-1 << (a2 & 0x1F))
                                             | (2 * ((-1 << (a2 & 0x1F)) & *(_DWORD *)(v11 + 4 * v12)));
  while ( (unsigned int)v13 < *((_DWORD *)this + 9) )
  {
    v15 = *((_QWORD *)this + 3);
    v16 = (2 * *(_DWORD *)(v15 + 4 * v13)) | 1;
    if ( !v14 )
      v16 = 2 * *(_DWORD *)(v15 + 4 * v13);
    v14 = *(_DWORD *)(v15 + 4 * v13) >> 31;
    *(_DWORD *)(v15 + 4 * v13) = v16;
    v13 = (unsigned int)(v13 + 1);
  }
  ++*((_DWORD *)this + 8);
LABEL_13:
  v17 = GetProcessHeap();
  HeapFree(v17, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x18001f0c0  push    rbx
0x18001f0c2  push    rbp
0x18001f0c3  push    rsi
0x18001f0c4  push    rdi
0x18001f0c5  sub     rsp, 38h
0x18001f0c9  mov     eax, [rcx+20h]
0x18001f0cc  mov     ebp, edx
0x18001f0ce  inc     eax
0x18001f0d0  mov     rdi, rcx
0x18001f0d3  cmp     edx, eax
0x18001f0d5  jnb     loc_18001F19C
0x18001f0db  shr     eax, 5
0x18001f0de  lea     esi, [rax+1]
0x18001f0e1  cmp     [rcx+24h], esi
0x18001f0e4  jnb     short loc_18001F132
0x18001f0e6  mov     rbx, [rcx+18h]
0x18001f0ea  call    cs:__imp_GetProcessHeap
0x18001f0f0  mov     r9d, esi
0x18001f0f3  mov     r8, rbx; lpMem
0x18001f0f6  shl     r9, 2; dwBytes
0x18001f0fa  mov     edx, 8; dwFlags
0x18001f0ff  mov     rcx, rax; hHeap
0x18001f102  call    cs:__imp_HeapReAlloc
0x18001f108  test    rax, rax
0x18001f10b  jnz     short loc_18001F12B
0x18001f10d  mov     ebx, 8007000Eh
0x18001f112  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001f119  mov     ecx, ebx
0x18001f11b  mov     r9d, 194h
0x18001f121  call    Log_HREvent_9
0x18001f126  jmp     loc_18001F1BA
0x18001f12b  mov     [rdi+18h], rax
0x18001f12f  mov     [rdi+24h], esi
0x18001f132  mov     r8, [rdi+18h]
0x18001f136  mov     eax, ebp
0x18001f138  and     ebp, 1Fh
0x18001f13b  shr     eax, 5
0x18001f13e  mov     cl, bpl
0x18001f141  mov     r9d, eax
0x18001f144  or      edx, 0FFFFFFFFh
0x18001f147  shl     edx, cl
0x18001f149  mov     r10d, [r8+rax*4]
0x18001f14d  lea     r11d, [r9+1]
0x18001f151  mov     eax, [r8+rax*4]
0x18001f155  xor     ebx, ebx
0x18001f157  and     eax, edx
0x18001f159  shr     r10d, 1Fh
0x18001f15d  not     edx
0x18001f15f  add     eax, eax
0x18001f161  and     edx, [r8+r9*4]
0x18001f165  or      eax, edx
0x18001f167  mov     [r8+r9*4], eax
0x18001f16b  jmp     short loc_18001F191
0x18001f16d  mov     r8, [rdi+18h]
0x18001f171  mov     edx, [r8+r11*4]
0x18001f175  lea     ecx, [rdx+rdx]
0x18001f178  mov     eax, ecx
0x18001f17a  or      eax, 1
0x18001f17d  test    r10d, r10d
0x18001f180  mov     r10d, edx
0x18001f183  cmovz   eax, ecx
0x18001f186  shr     r10d, 1Fh
0x18001f18a  mov     [r8+r11*4], eax
0x18001f18e  inc     r11d
0x18001f191  cmp     r11d, [rdi+24h]
0x18001f195  jb      short loc_18001F16D
0x18001f197  inc     dword ptr [rdi+20h]
0x18001f19a  jmp     short loc_18001F1BA
0x18001f19c  mov     ebx, 80070057h
0x18001f1a1  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001f1a8  mov     ecx, ebx
0x18001f1aa  mov     r9d, 185h
0x18001f1b0  mov     edx, 1
0x18001f1b5  call    Log_HREvent
0x18001f1ba  call    cs:__imp_GetProcessHeap
0x18001f1c0  xor     r8d, r8d; lpMem
0x18001f1c3  xor     edx, edx; dwFlags
0x18001f1c5  mov     rcx, rax; hHeap
0x18001f1c8  call    cs:__imp_HeapFree
0x18001f1ce  mov     eax, ebx
0x18001f1d0  add     rsp, 38h
0x18001f1d4  pop     rdi
0x18001f1d5  pop     rsi
0x18001f1d6  pop     rbp
0x18001f1d7  pop     rbx
0x18001f1d8  retn
```
