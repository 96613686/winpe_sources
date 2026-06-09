# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180018740`
- end: `0x180018764`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018f10`
- `0x1800194c0`

## callees

- `0x180001dd8`
- `0x18001858c`
- `0x180018740`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x180018740  push    rbx
0x180018742  sub     rsp, 20h
0x180018746  mov     rbx, rcx
0x180018749  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x18001874e  test    rbx, rbx
0x180018751  jz      short loc_18001875B
0x180018753  mov     rcx, rbx; unsigned __int8 *
0x180018756  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001875b  mov     rax, rbx
0x18001875e  add     rsp, 20h
0x180018762  pop     rbx
0x180018763  retn
```
