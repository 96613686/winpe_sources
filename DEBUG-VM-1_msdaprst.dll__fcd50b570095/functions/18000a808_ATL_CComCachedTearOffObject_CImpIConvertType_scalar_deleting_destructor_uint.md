# ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(uint)

- ea: `0x18000a808`
- end: `0x18000a82c`
- name: `??_G?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b1b0`
- `0x18000c630`

## callees

- `0x180001dd8`
- `0x18000a38c`
- `0x18000a808`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a808  push    rbx
0x18000a80a  sub     rsp, 20h
0x18000a80e  mov     rbx, rcx
0x18000a811  call    ??1?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(void)
0x18000a816  test    rbx, rbx
0x18000a819  jz      short loc_18000A823
0x18000a81b  mov     rcx, rbx; unsigned __int8 *
0x18000a81e  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a823  mov     rax, rbx
0x18000a826  add     rsp, 20h
0x18000a82a  pop     rbx
0x18000a82b  retn
```
