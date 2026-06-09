# LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::iterator::~iterator(void)

- ea: `0x180002f1c`
- end: `0x180002f4f`
- name: `??1iterator@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@QEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000abce`
- `0x18000abe0`
- `0x18000abf2`
- `0x18000ac28`

## callees

- `0x180002f1c`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::iterator::~iterator(
        __int64 a1)
{
  __int64 v1; // r8
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( *(_WORD *)(a1 + 28) != 0xFFFF )
      return (*(__int64 (__fastcall **)(_QWORD))(v1 + 56))(*(_QWORD *)(*(_QWORD *)(a1 + 16)
                                                                     + 8LL * *(__int16 *)(a1 + 28)
                                                                     + 24));
  }
  return result;
}

```

## disassembly

```asm
0x180002f1c  sub     rsp, 28h
0x180002f20  mov     r8, [rcx+8]
0x180002f24  test    r8, r8
0x180002f27  jz      short loc_180002F4A
0x180002f29  or      edx, 0FFFFFFFFh
0x180002f2c  cmp     [rcx+1Ch], dx
0x180002f30  jz      short loc_180002F4A
0x180002f32  movsx   rax, word ptr [rcx+1Ch]
0x180002f37  mov     rcx, [rcx+10h]
0x180002f3b  mov     rcx, [rcx+rax*8+18h]
0x180002f40  mov     rax, [r8+38h]
0x180002f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f49  nop
0x180002f4a  add     rsp, 28h
0x180002f4e  retn
```
