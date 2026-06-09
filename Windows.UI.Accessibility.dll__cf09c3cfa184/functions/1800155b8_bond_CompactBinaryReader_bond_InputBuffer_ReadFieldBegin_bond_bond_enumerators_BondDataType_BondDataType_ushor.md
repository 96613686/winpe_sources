# bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)

- ea: `0x1800155b8`
- end: `0x18001563b`
- name: `?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `26`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f0c8`
- `0x18000fbc0`
- `0x18000fca4`
- `0x18000fd78`
- `0x18000fe4c`
- `0x180010080`
- `0x180015e78`
- `0x180017784`
- `0x180017dd8`
- `0x180017ebc`
- `0x180017f90`
- `0x180018064`
- `0x1800182a0`
- `0x180018374`
- `0x180019790`
- `0x18001a9d8`
- `0x18001aa78`
- `0x18001ab18`
- `0x18001bfdc`
- `0x18001c0a0`
- `0x18001c164`
- `0x18001c218`
- `0x18001c36c`
- `0x18001c450`
- `0x18001c504`
- `0x18001c768`

## callees

- `0x18000fab0`
- `0x180015508`
- `0x1800155b8`

## pseudocode

```c
void __fastcall bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(
        bond::InputBuffer *this,
        int *a2,
        unsigned __int8 *a3)
{
  unsigned __int8 v6; // r9
  unsigned __int8 v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = 0;
  bond::InputBuffer::Read(this, &v7);
  v6 = v7 & 0xE0;
  *a2 = v7 & 0x1F;
  *(_WORD *)a3 = v6;
  if ( v6 == 224 )
  {
    bond::InputBuffer::Read<unsigned short>(this, a3);
  }
  else if ( v6 == 192 )
  {
    bond::InputBuffer::Read(this, a3);
  }
  else
  {
    *(_WORD *)a3 = v6 >> 5;
  }
}

```

## disassembly

```asm
0x1800155b8  mov     rax, rsp
0x1800155bb  mov     [rax+10h], rbx
0x1800155bf  mov     [rax+18h], rsi
0x1800155c3  push    rdi
0x1800155c4  sub     rsp, 20h
0x1800155c8  mov     rbx, rdx
0x1800155cb  mov     byte ptr [rax+8], 0
0x1800155cf  lea     rdx, [rax+8]; unsigned __int8 *
0x1800155d3  mov     rdi, r8
0x1800155d6  mov     rsi, rcx
0x1800155d9  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x1800155de  movzx   r9d, [rsp+28h+arg_0]
0x1800155e4  mov     ecx, 0E0h
0x1800155e9  mov     eax, r9d
0x1800155ec  and     r9b, cl
0x1800155ef  and     eax, 1Fh
0x1800155f2  mov     [rbx], eax
0x1800155f4  movzx   eax, r9b
0x1800155f8  mov     [rdi], ax
0x1800155fb  cmp     ax, cx
0x1800155fe  jnz     short loc_18001560D
0x180015600  mov     rdx, rdi
0x180015603  mov     rcx, rsi
0x180015606  call    ??$Read@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::Read<ushort>(ushort &)
0x18001560b  jmp     short loc_18001562B
0x18001560d  mov     ecx, 0C0h
0x180015612  cmp     ax, cx
0x180015615  jnz     short loc_180015624
0x180015617  mov     rdx, rdi; unsigned __int8 *
0x18001561a  mov     rcx, rsi; this
0x18001561d  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180015622  jmp     short loc_18001562B
0x180015624  shr     ax, 5
0x180015628  mov     [rdi], ax
0x18001562b  mov     rbx, [rsp+28h+arg_8]
0x180015630  mov     rsi, [rsp+28h+arg_10]
0x180015635  add     rsp, 20h
0x180015639  pop     rdi
0x18001563a  retn
```
