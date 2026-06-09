# ALLOC_CACHE_HANDLER::Initialize(void)

- ea: `0x18003366c`
- end: `0x1800336e1`
- name: `?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `117`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034558`

## callees

- `0x18003366c`
- `0x180034864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800336ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800336ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800336c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800336c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003367d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003367d`

## pseudocode

```c
__int64 ALLOC_CACHE_HANDLER::Initialize(void)
{
  unsigned int v0; // ebx

  ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = IsPageheapEnabled();
  ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
  qword_18005FAC0 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
  ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
  if ( InitializeCriticalSectionAndSpinCount(&ALLOC_CACHE_HANDLER::sm_csItems, 0x800003E8) )
  {
    v0 = 1;
    goto LABEL_5;
  }
  v0 = 0;
  if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
  {
    DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
LABEL_5:
    ALLOC_CACHE_HANDLER::sm_fInitCsItems = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x18003366c  push    rbx
0x18003366e  sub     rsp, 20h
0x180033672  call    ?IsPageheapEnabled@@YAHXZ; IsPageheapEnabled(void)
0x180033677  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x18003367d  call    cs:__imp_GetProcessHeap
0x180033683  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x18003368a  mov     edx, 800003E8h; dwSpinCount
0x18003368f  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033696  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18003369d  mov     cs:qword_18005FAC0, rax
0x1800336a4  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x1800336ab  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800336b1  test    eax, eax
0x1800336b3  jnz     short loc_1800336CE
0x1800336b5  xor     ebx, ebx
0x1800336b7  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x1800336bd  jz      short loc_1800336D9
0x1800336bf  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800336c6  call    cs:__imp_DeleteCriticalSection
0x1800336cc  jmp     short loc_1800336D3
0x1800336ce  mov     ebx, 1
0x1800336d3  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x1800336d9  mov     eax, ebx
0x1800336db  add     rsp, 20h
0x1800336df  pop     rbx
0x1800336e0  retn
```
