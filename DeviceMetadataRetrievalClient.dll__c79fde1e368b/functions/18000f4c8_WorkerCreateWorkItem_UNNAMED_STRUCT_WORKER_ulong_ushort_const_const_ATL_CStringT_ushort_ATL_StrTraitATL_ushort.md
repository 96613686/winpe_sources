# WorkerCreateWorkItem(UNNAMED_STRUCT_WORKER *,ulong,ushort const * const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_WORKITEM * &)

- ea: `0x18000f4c8`
- end: `0x18000f6b4`
- name: `?WorkerCreateWorkItem@@YAKPEAUUNNAMED_STRUCT_WORKER@@KPEBQEBGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG2AEAPEAU_WORKITEM@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const unsigned __int16 **, unsigned __int16 *, const unsigned __int16 **, struct _WORKITEM **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011fb0`

## callees

- `0x18000ede8`
- `0x18000eed0`
- `0x18000f3bc`
- `0x18000f4c8`
- `0x1800135cc`
- `0x1800136c6`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000f503`
- `KERNEL32!HeapAlloc` at `0x18000f55d`
- `KERNEL32!HeapAlloc` at `0x18000f503`
- `KERNEL32!HeapAlloc` at `0x18000f55d`
- `KERNEL32!GetProcessHeap` at `0x18000f4f0`
- `KERNEL32!GetProcessHeap` at `0x18000f54f`
- `KERNEL32!GetProcessHeap` at `0x18000f646`
- `KERNEL32!GetProcessHeap` at `0x18000f660`
- `KERNEL32!GetProcessHeap` at `0x18000f4f0`
- `KERNEL32!GetProcessHeap` at `0x18000f54f`
- `KERNEL32!GetProcessHeap` at `0x18000f646`
- `KERNEL32!GetProcessHeap` at `0x18000f660`
- `KERNEL32!HeapFree` at `0x18000f654`
- `KERNEL32!HeapFree` at `0x18000f66e`
- `KERNEL32!HeapFree` at `0x18000f654`
- `KERNEL32!HeapFree` at `0x18000f66e`
- `KERNEL32!EnterCriticalSection` at `0x18000f67a`
- `KERNEL32!EnterCriticalSection` at `0x18000f67a`
- `KERNEL32!LeaveCriticalSection` at `0x18000f695`
- `KERNEL32!LeaveCriticalSection` at `0x18000f695`

## pseudocode

```c
__int64 __fastcall WorkerCreateWorkItem(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 **a4,
        unsigned __int16 *a5,
        const unsigned __int16 **a6,
        struct _WORKITEM **a7)
{
  unsigned int v7; // edi
  __int64 v8; // rbp
  HANDLE ProcessHeap; // rax
  struct _WORKITEM *v13; // rax
  HANDLE v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // r14
  unsigned __int16 *v17; // rax
  __int64 v18; // rbx
  void *v19; // r15
  HANDLE v20; // rax
  HANDLE v21; // rax
  int v22; // r8d

  v7 = 0;
  v8 = (unsigned int)a2;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  ProcessHeap = GetProcessHeap();
  v13 = (struct _WORKITEM *)HeapAlloc(ProcessHeap, 0, 0x40u);
  *a7 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0x40u);
    if ( a3 && (_DWORD)v8 && *((_DWORD *)*a4 - 4) )
    {
      v14 = GetProcessHeap();
      v15 = HeapAlloc(v14, 0, 8 * v8);
      v16 = v15;
      if ( !v15 )
        goto LABEL_16;
      memset_0(v15, 0, 8 * v8);
      do
      {
        v17 = MemMallocAndCat(L"DOID:", *(_QWORD *)(a3 + 8LL * v7), 0);
        v16[v7] = v17;
        if ( !v17 )
        {
          v7 = 8;
          v18 = 0;
          do
          {
            v19 = (void *)v16[v18];
            if ( !v19 )
              break;
            v20 = GetProcessHeap();
            HeapFree(v20, 0, v19);
            v18 = (unsigned int)(v18 + 1);
          }
          while ( (unsigned int)v18 < (unsigned int)v8 );
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v16);
          goto LABEL_17;
        }
        ++v7;
      }
      while ( v7 < (unsigned int)v8 );
      *((_QWORD *)*a7 + 2) = v16;
      *((_DWORD *)*a7 + 2) = v8;
      v7 = 0;
      *((_QWORD *)*a7 + 6) = MemMallocAndCopy(*a4);
      if ( !*((_QWORD *)*a7 + 6) )
        goto LABEL_16;
    }
    if ( !a5
      || !*((_DWORD *)*a6 - 4)
      || (*((_QWORD *)*a7 + 3) = MemMallocAndCopy(a5), *((_QWORD *)*a7 + 7) = MemMallocAndCopy(*a6),
                                                       *((_QWORD *)*a7 + 3))
      && *((_QWORD *)*a7 + 7) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
      v22 = (*(_DWORD *)a1)++;
      *((_DWORD *)*a7 + 8) = v22;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
      *(_QWORD *)*a7 = a1;
      return v7;
    }
  }
LABEL_16:
  v7 = 8;
LABEL_17:
  FreeWorkitem(*a7);
  *a7 = 0;
  return v7;
}

```

## disassembly

```asm
0x18000f4c8  push    rbx
0x18000f4ca  push    rbp
0x18000f4cb  push    rsi
0x18000f4cc  push    rdi
0x18000f4cd  push    r12
0x18000f4cf  push    r13
0x18000f4d1  push    r14
0x18000f4d3  push    r15
0x18000f4d5  sub     rsp, 28h
0x18000f4d9  xor     edi, edi
0x18000f4db  mov     ebp, edx
0x18000f4dd  mov     r12, r9
0x18000f4e0  mov     r13, r8
0x18000f4e3  mov     r15, rcx
0x18000f4e6  test    rcx, rcx
0x18000f4e9  jnz     short loc_18000F4F0
0x18000f4eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f4f0  call    cs:__imp_GetProcessHeap
0x18000f4f6  mov     ebx, 40h ; '@'
0x18000f4fb  xor     edx, edx; dwFlags
0x18000f4fd  mov     rcx, rax; hHeap
0x18000f500  mov     r8d, ebx; dwBytes
0x18000f503  call    cs:__imp_HeapAlloc
0x18000f509  mov     rsi, [rsp+68h+arg_30]
0x18000f511  mov     [rsi], rax
0x18000f514  test    rax, rax
0x18000f517  jz      loc_18000F620
0x18000f51d  mov     r8d, ebx; Size
0x18000f520  xor     edx, edx; Val
0x18000f522  mov     rcx, rax; void *
0x18000f525  call    memset_0
0x18000f52a  test    r13, r13
0x18000f52d  jz      loc_18000F5D1
0x18000f533  test    ebp, ebp
0x18000f535  jz      loc_18000F5D1
0x18000f53b  mov     rax, [r12]
0x18000f53f  cmp     [rax-10h], edi
0x18000f542  jz      loc_18000F5D1
0x18000f548  mov     rbx, rbp
0x18000f54b  shl     rbx, 3
0x18000f54f  call    cs:__imp_GetProcessHeap
0x18000f555  mov     r8, rbx; dwBytes
0x18000f558  xor     edx, edx; dwFlags
0x18000f55a  mov     rcx, rax; hHeap
0x18000f55d  call    cs:__imp_HeapAlloc
0x18000f563  mov     r14, rax
0x18000f566  test    rax, rax
0x18000f569  jz      loc_18000F620
0x18000f56f  mov     r8, rbx; Size
0x18000f572  xor     edx, edx; Val
0x18000f574  mov     rcx, rax; void *
0x18000f577  call    memset_0
0x18000f57c  test    ebp, ebp
0x18000f57e  jz      short loc_18000F5A9
0x18000f580  mov     ebx, edi
0x18000f582  lea     rcx, aDoid; "DOID:"
0x18000f589  xor     r8d, r8d
0x18000f58c  mov     rdx, [r13+rbx*8+0]
0x18000f591  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000f596  mov     [r14+rbx*8], rax
0x18000f59a  test    rax, rax
0x18000f59d  jz      loc_18000F636
0x18000f5a3  inc     edi
0x18000f5a5  cmp     edi, ebp
0x18000f5a7  jb      short loc_18000F580
0x18000f5a9  mov     rax, [rsi]
0x18000f5ac  mov     [rax+10h], r14
0x18000f5b0  mov     rax, [rsi]
0x18000f5b3  mov     [rax+8], ebp
0x18000f5b6  mov     rcx, [r12]; unsigned __int16 *
0x18000f5ba  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000f5bf  mov     rcx, [rsi]
0x18000f5c2  xor     edi, edi
0x18000f5c4  mov     [rcx+30h], rax
0x18000f5c8  mov     rax, [rsi]
0x18000f5cb  cmp     [rax+30h], rdi
0x18000f5cf  jz      short loc_18000F620
0x18000f5d1  mov     rcx, [rsp+68h+arg_20]; unsigned __int16 *
0x18000f5d9  test    rcx, rcx
0x18000f5dc  jz      loc_18000F676
0x18000f5e2  mov     rbx, [rsp+68h+arg_28]
0x18000f5ea  mov     rax, [rbx]
0x18000f5ed  cmp     [rax-10h], edi
0x18000f5f0  jz      loc_18000F676
0x18000f5f6  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000f5fb  mov     rdx, [rsi]
0x18000f5fe  mov     [rdx+18h], rax
0x18000f602  mov     rcx, [rbx]; unsigned __int16 *
0x18000f605  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000f60a  mov     rcx, [rsi]
0x18000f60d  mov     [rcx+38h], rax
0x18000f611  mov     rax, [rsi]
0x18000f614  cmp     [rax+18h], rdi
0x18000f618  jz      short loc_18000F620
0x18000f61a  cmp     [rax+38h], rdi
0x18000f61e  jnz     short loc_18000F676
0x18000f620  mov     edi, 8
0x18000f625  mov     rcx, [rsi]; struct _WORKITEM *
0x18000f628  call    ?FreeWorkitem@@YAXPEAU_WORKITEM@@@Z; FreeWorkitem(_WORKITEM *)
0x18000f62d  mov     qword ptr [rsi], 0
0x18000f634  jmp     short loc_18000F6A1
0x18000f636  mov     edi, 8
0x18000f63b  xor     ebx, ebx
0x18000f63d  mov     r15, [r14+rbx*8]
0x18000f641  test    r15, r15
0x18000f644  jz      short loc_18000F660
0x18000f646  call    cs:__imp_GetProcessHeap
0x18000f64c  mov     r8, r15; lpMem
0x18000f64f  xor     edx, edx; dwFlags
0x18000f651  mov     rcx, rax; hHeap
0x18000f654  call    cs:__imp_HeapFree
0x18000f65a  inc     ebx
0x18000f65c  cmp     ebx, ebp
0x18000f65e  jb      short loc_18000F63D
0x18000f660  call    cs:__imp_GetProcessHeap
0x18000f666  mov     r8, r14; lpMem
0x18000f669  xor     edx, edx; dwFlags
0x18000f66b  mov     rcx, rax; hHeap
0x18000f66e  call    cs:__imp_HeapFree
0x18000f674  jmp     short loc_18000F625
0x18000f676  lea     rcx, [r15+8]; lpCriticalSection
0x18000f67a  call    cs:__imp_EnterCriticalSection
0x18000f680  mov     r8d, [r15]
0x18000f683  lea     rcx, [r15+8]; lpCriticalSection
0x18000f687  lea     edx, [r8+1]
0x18000f68b  mov     [r15], edx
0x18000f68e  mov     rdx, [rsi]
0x18000f691  mov     [rdx+20h], r8d
0x18000f695  call    cs:__imp_LeaveCriticalSection
0x18000f69b  mov     rcx, [rsi]
0x18000f69e  mov     [rcx], r15
0x18000f6a1  mov     eax, edi
0x18000f6a3  add     rsp, 28h
0x18000f6a7  pop     r15
0x18000f6a9  pop     r14
0x18000f6ab  pop     r13
0x18000f6ad  pop     r12
0x18000f6af  pop     rdi
0x18000f6b0  pop     rsi
0x18000f6b1  pop     rbp
0x18000f6b2  pop     rbx
0x18000f6b3  retn
```
