# SSPI_SECURITY_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x180001c70`
- end: `0x180001cb1`
- name: `??_ESSPI_SECURITY_CONTEXT@@MEAAPEAXI@Z`
- size: `65`
- prototype: `void *__fastcall(SSPI_SECURITY_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c70`
- `0x18000445c`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001c9d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001c9d`

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
0x180001c70  mov     [rsp+arg_0], rbx
0x180001c75  push    rdi
0x180001c76  sub     rsp, 20h
0x180001c7a  lea     rax, ??_7SSPI_SECURITY_CONTEXT@@6B@; const SSPI_SECURITY_CONTEXT::`vftable'
0x180001c81  mov     ebx, edx
0x180001c83  mov     [rcx], rax
0x180001c86  mov     rdi, rcx
0x180001c89  call    ?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ; SSPI_SECURITY_CONTEXT::Reset(void)
0x180001c8e  test    bl, 1
0x180001c91  jz      short loc_180001CA3
0x180001c93  mov     rcx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180001c9a  mov     rdx, rdi
0x180001c9d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180001ca3  mov     rbx, [rsp+28h+arg_0]
0x180001ca8  mov     rax, rdi
0x180001cab  add     rsp, 20h
0x180001caf  pop     rdi
0x180001cb0  retn
```
