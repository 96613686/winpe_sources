# DIGEST_SSPI_SECURITY_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x180001c30`
- end: `0x180001c67`
- name: `??_EDIGEST_SSPI_SECURITY_CONTEXT@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(DIGEST_SSPI_SECURITY_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001a38`
- `0x180001c30`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001c53`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001c53`

## pseudocode

```c
DIGEST_SSPI_SECURITY_CONTEXT *__fastcall DIGEST_SSPI_SECURITY_CONTEXT::`vector deleting destructor'(
        DIGEST_SSPI_SECURITY_CONTEXT *this,
        char a2)
{
  DIGEST_SSPI_SECURITY_CONTEXT::~DIGEST_SSPI_SECURITY_CONTEXT(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext, this);
  return this;
}

```

## disassembly

```asm
0x180001c30  mov     [rsp+arg_0], rbx
0x180001c35  push    rdi
0x180001c36  sub     rsp, 20h
0x180001c3a  mov     ebx, edx
0x180001c3c  mov     rdi, rcx
0x180001c3f  call    ??1DIGEST_SSPI_SECURITY_CONTEXT@@UEAA@XZ; DIGEST_SSPI_SECURITY_CONTEXT::~DIGEST_SSPI_SECURITY_CONTEXT(void)
0x180001c44  test    bl, 1
0x180001c47  jz      short loc_180001C59
0x180001c49  mov     rcx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180001c50  mov     rdx, rdi
0x180001c53  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180001c59  mov     rbx, [rsp+28h+arg_0]
0x180001c5e  mov     rax, rdi
0x180001c61  add     rsp, 20h
0x180001c65  pop     rdi
0x180001c66  retn
```
