# ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000a834`
- end: `0x18000a858`
- name: `??_G?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b290`
- `0x18000c670`

## callees

- `0x180001dd8`
- `0x18000a3b0`
- `0x18000a834`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIRowset>::~CComCachedTearOffObject<CImpIRowset>();
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a834  push    rbx
0x18000a836  sub     rsp, 20h
0x18000a83a  mov     rbx, rcx
0x18000a83d  call    ??1?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIRowset>::~CComCachedTearOffObject<CImpIRowset>(void)
0x18000a842  test    rbx, rbx
0x18000a845  jz      short loc_18000A84F
0x18000a847  mov     rcx, rbx; unsigned __int8 *
0x18000a84a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a84f  mov     rax, rbx
0x18000a852  add     rsp, 20h
0x18000a856  pop     rbx
0x18000a857  retn
```
