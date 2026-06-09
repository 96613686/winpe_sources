# ATL::CComObject<CPersistDSO>::Release(void)

- ea: `0x1800193b0`
- end: `0x1800193dd`
- name: `?Release@?$CComObject@VCPersistDSO@@@ATL@@UEAAKXZ`
- size: `45`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800193f0`
- `0x180019400`
- `0x180019410`
- `0x180019430`
- `0x180019450`
- `0x180019470`
- `0x180019490`
- `0x1800194a0`
- `0x1800194b0`

## callees

- `0x18000c848`
- `0x180018714`
- `0x1800193b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPersistDSO>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned __int8 *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((int *)(a1 + 48));
  if ( !v1 && v2 )
    ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(v2);
  return v1;
}

```

## disassembly

```asm
0x1800193b0  push    rbx
0x1800193b2  sub     rsp, 20h
0x1800193b6  mov     r10, rcx
0x1800193b9  add     rcx, 30h ; '0'; int *
0x1800193bd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x1800193c2  mov     ebx, eax
0x1800193c4  test    eax, eax
0x1800193c6  jnz     short loc_1800193D5
0x1800193c8  test    r10, r10
0x1800193cb  jz      short loc_1800193D5
0x1800193cd  mov     rcx, r10; unsigned __int8 *
0x1800193d0  call    ??_G?$CComObject@VCPersistDSO@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(uint)
0x1800193d5  mov     eax, ebx
0x1800193d7  add     rsp, 20h
0x1800193db  pop     rbx
0x1800193dc  retn
```
