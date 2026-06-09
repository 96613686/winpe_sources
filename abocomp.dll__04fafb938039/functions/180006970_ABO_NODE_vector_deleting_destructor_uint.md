# ABO_NODE::`vector deleting destructor'(uint)

- ea: `0x180006970`
- end: `0x1800069a7`
- name: `??_EABO_NODE@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(ABO_NODE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800065f4`
- `0x180006970`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006993`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006993`

## pseudocode

```c
ABO_NODE *__fastcall ABO_NODE::`vector deleting destructor'(ABO_NODE *this, char a2)
{
  ABO_NODE::~ABO_NODE(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes, this);
  return this;
}

```

## disassembly

```asm
0x180006970  mov     [rsp+arg_0], rbx
0x180006975  push    rdi
0x180006976  sub     rsp, 20h
0x18000697a  mov     ebx, edx
0x18000697c  mov     rdi, rcx
0x18000697f  call    ??1ABO_NODE@@UEAA@XZ; ABO_NODE::~ABO_NODE(void)
0x180006984  test    bl, 1
0x180006987  jz      short loc_180006999
0x180006989  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180006990  mov     rdx, rdi
0x180006993  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180006999  mov     rbx, [rsp+28h+arg_0]
0x18000699e  mov     rax, rdi
0x1800069a1  add     rsp, 20h
0x1800069a5  pop     rdi
0x1800069a6  retn
```
