# SSPI_SECURITY_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x180001ea0`
- end: `0x180001ee1`
- name: `??_ESSPI_SECURITY_CONTEXT@@MEAAPEAXI@Z`
- size: `65`
- prototype: `void *__fastcall(SSPI_SECURITY_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ea0`
- `0x180005dc4`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001ecd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001ecd`

## pseudocode

```c
struct _SecHandle *__fastcall SSPI_SECURITY_CONTEXT::`vector deleting destructor'(struct _SecHandle *this, char a2)
{
  this->dwLower = (ULONG_PTR)&SSPI_SECURITY_CONTEXT::`vftable';
  SSPI_SECURITY_CONTEXT::Reset(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext, this);
  return this;
}

```

## disassembly

```asm
0x180001ea0  mov     [rsp+arg_0], rbx
0x180001ea5  push    rdi
0x180001ea6  sub     rsp, 20h
0x180001eaa  lea     rax, ??_7SSPI_SECURITY_CONTEXT@@6B@; const SSPI_SECURITY_CONTEXT::`vftable'
0x180001eb1  mov     ebx, edx
0x180001eb3  mov     [rcx], rax
0x180001eb6  mov     rdi, rcx
0x180001eb9  call    ?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ; SSPI_SECURITY_CONTEXT::Reset(void)
0x180001ebe  test    bl, 1
0x180001ec1  jz      short loc_180001ED3
0x180001ec3  mov     rcx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180001eca  mov     rdx, rdi
0x180001ecd  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180001ed3  mov     rbx, [rsp+28h+arg_0]
0x180001ed8  mov     rax, rdi
0x180001edb  add     rsp, 20h
0x180001edf  pop     rdi
0x180001ee0  retn
```
