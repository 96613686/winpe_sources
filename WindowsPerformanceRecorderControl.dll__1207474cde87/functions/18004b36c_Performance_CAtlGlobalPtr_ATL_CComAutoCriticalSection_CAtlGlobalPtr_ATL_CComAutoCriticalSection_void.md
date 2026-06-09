# Performance::CAtlGlobalPtr<ATL::CComAutoCriticalSection>::~CAtlGlobalPtr<ATL::CComAutoCriticalSection>(void)

- ea: `0x18004b36c`
- end: `0x18004b396`
- name: `??1?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@Performance@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(LPCRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008b220`

## callees

- `0x18004b36c`
- `0x18004f1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b37d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b37d`

## pseudocode

```c
void __fastcall Performance::CAtlGlobalPtr<ATL::CComAutoCriticalSection>::~CAtlGlobalPtr<ATL::CComAutoCriticalSection>(
        LPCRITICAL_SECTION *a1)
{
  LPCRITICAL_SECTION v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    DeleteCriticalSection(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18004b36c  push    rbx
0x18004b36e  sub     rsp, 20h
0x18004b372  mov     rbx, [rcx]
0x18004b375  test    rbx, rbx
0x18004b378  jz      short loc_18004B390
0x18004b37a  mov     rcx, rbx; lpCriticalSection
0x18004b37d  call    cs:__imp_DeleteCriticalSection
0x18004b383  mov     edx, 28h ; '('
0x18004b388  mov     rcx, rbx; Block
0x18004b38b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b390  add     rsp, 20h
0x18004b394  pop     rbx
0x18004b395  retn
```
