# MULTI_WORK_ITEM::`scalar deleting destructor'(uint)

- ea: `0x1800087e0`
- end: `0x180008818`
- name: `??_GMULTI_WORK_ITEM@@UEAAPEAXI@Z`
- size: `56`
- prototype: `void *__fastcall(MULTI_WORK_ITEM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000879c`
- `0x1800087e0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180008803`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180008803`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
MULTI_WORK_ITEM *__fastcall MULTI_WORK_ITEM::`scalar deleting destructor'(MULTI_WORK_ITEM *this, char a2)
{
  MULTI_WORK_ITEM::~MULTI_WORK_ITEM(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler, this);
  return this;
}

```

## disassembly

```asm
0x1800087e0  mov     [rsp+arg_0], rbx
0x1800087e5  push    rdi
0x1800087e6  sub     rsp, 20h
0x1800087ea  mov     ebx, edx
0x1800087ec  mov     rdi, rcx
0x1800087ef  call    ??1MULTI_WORK_ITEM@@UEAA@XZ; MULTI_WORK_ITEM::~MULTI_WORK_ITEM(void)
0x1800087f4  test    bl, 1
0x1800087f7  jz      short loc_18000880A
0x1800087f9  mov     rdx, rdi
0x1800087fc  mov     rcx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x180008803  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180008809  nop
0x18000880a  mov     rax, rdi
0x18000880d  mov     rbx, [rsp+28h+arg_0]
0x180008812  add     rsp, 20h
0x180008816  pop     rdi
0x180008817  retn
```
