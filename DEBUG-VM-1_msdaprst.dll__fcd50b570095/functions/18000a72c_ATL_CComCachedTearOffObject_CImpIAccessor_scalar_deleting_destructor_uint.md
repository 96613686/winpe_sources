# ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(uint)

- ea: `0x18000a72c`
- end: `0x18000a750`
- name: `??_G?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ad40`
- `0x18000c4f0`

## callees

- `0x180001dd8`
- `0x18000a2d8`
- `0x18000a72c`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a72c  push    rbx
0x18000a72e  sub     rsp, 20h
0x18000a732  mov     rbx, rcx
0x18000a735  call    ??1?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(void)
0x18000a73a  test    rbx, rbx
0x18000a73d  jz      short loc_18000A747
0x18000a73f  mov     rcx, rbx; unsigned __int8 *
0x18000a742  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a747  mov     rax, rbx
0x18000a74a  add     rsp, 20h
0x18000a74e  pop     rbx
0x18000a74f  retn
```
