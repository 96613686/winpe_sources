# ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000a758`
- end: `0x18000a77c`
- name: `??_G?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ae20`
- `0x18000c530`

## callees

- `0x180001dd8`
- `0x18000a2fc`
- `0x18000a758`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a758  push    rbx
0x18000a75a  sub     rsp, 20h
0x18000a75e  mov     rbx, rcx
0x18000a761  call    ??1?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(void)
0x18000a766  test    rbx, rbx
0x18000a769  jz      short loc_18000A773
0x18000a76b  mov     rcx, rbx; unsigned __int8 *
0x18000a76e  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a773  mov     rax, rbx
0x18000a776  add     rsp, 20h
0x18000a77a  pop     rbx
0x18000a77b  retn
```
