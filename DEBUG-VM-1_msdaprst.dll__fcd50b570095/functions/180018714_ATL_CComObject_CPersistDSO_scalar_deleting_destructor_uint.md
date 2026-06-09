# ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(uint)

- ea: `0x180018714`
- end: `0x180018738`
- name: `??_G?$CComObject@VCPersistDSO@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018e60`
- `0x1800193b0`

## callees

- `0x180001dd8`
- `0x1800184f8`
- `0x180018714`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(unsigned __int8 *a1)
{
  ATL::CComObject<CPersistDSO>::~CComObject<CPersistDSO>();
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x180018714  push    rbx
0x180018716  sub     rsp, 20h
0x18001871a  mov     rbx, rcx
0x18001871d  call    ??1?$CComObject@VCPersistDSO@@@ATL@@QEAA@XZ; ATL::CComObject<CPersistDSO>::~CComObject<CPersistDSO>(void)
0x180018722  test    rbx, rbx
0x180018725  jz      short loc_18001872F
0x180018727  mov     rcx, rbx; unsigned __int8 *
0x18001872a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001872f  mov     rax, rbx
0x180018732  add     rsp, 20h
0x180018736  pop     rbx
0x180018737  retn
```
