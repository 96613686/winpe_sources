# SSPI_SECURITY_CONTEXT::Terminate(void)

- ea: `0x180006078`
- end: `0x1800060ac`
- name: `?Terminate@SSPI_SECURITY_CONTEXT@@SAXXZ`
- size: `52`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800042d0`
- `0x180004650`

## callees

- `0x180001064`
- `0x180006078`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000608d`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000608d`

## pseudocode

```c
void SSPI_SECURITY_CONTEXT::Terminate(void)
{
  void *v0; // rbx

  v0 = SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext;
  if ( SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext);
    operator delete(v0);
  }
  SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext = 0;
}

```

## disassembly

```asm
0x180006078  push    rbx
0x18000607a  sub     rsp, 20h
0x18000607e  mov     rbx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180006085  test    rbx, rbx
0x180006088  jz      short loc_18000609B
0x18000608a  mov     rcx, rbx
0x18000608d  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180006093  mov     rcx, rbx; Block
0x180006096  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000609b  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x1800060a6  add     rsp, 20h
0x1800060aa  pop     rbx
0x1800060ab  retn
```
