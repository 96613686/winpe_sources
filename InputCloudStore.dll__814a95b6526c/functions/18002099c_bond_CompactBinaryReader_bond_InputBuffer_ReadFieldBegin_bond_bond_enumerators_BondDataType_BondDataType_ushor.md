# bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)

- ea: `0x18002099c`
- end: `0x180020a1f`
- name: `?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `48`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009cb0`
- `0x180009d50`
- `0x180009df0`
- `0x180009e90`
- `0x180009f30`
- `0x18000d8e4`
- `0x18000d9c4`
- `0x18000daa8`
- `0x18000db90`
- `0x18000dc54`
- `0x18000dd18`
- `0x18000de00`
- `0x18000ded8`
- `0x18000df8c`
- `0x18000e060`
- `0x18000e134`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000e3a4`
- `0x18000e564`
- `0x18000e728`
- `0x18000e7fc`
- `0x18000e9c0`
- `0x18000ea94`
- `0x18000eb64`
- `0x18000ec38`
- `0x18000ed0c`
- `0x18000ede0`
- `0x18000ef58`
- `0x18000f194`
- `0x18000f334`
- `0x18000f4c8`
- `0x18000f590`
- `0x18000f61c`
- `0x18000f6ec`
- `0x18000f7c0`
- `0x18001be18`
- `0x18001beec`
- `0x18001bfc0`
- `0x18001c088`
- `0x18001c15c`
- `0x18001c224`
- `0x18001c36c`
- `0x18001c420`
- `0x18001c4c8`
- `0x18001c5c0`
- `0x18001c694`
- `0x180022000`

## callees

- `0x18000ce44`
- `0x180020960`
- `0x18002099c`

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
    bond::InputBuffer::Read<unsigned short>((__int64)this, a3);
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
0x18002099c  mov     rax, rsp
0x18002099f  mov     [rax+10h], rbx
0x1800209a3  mov     [rax+18h], rsi
0x1800209a7  push    rdi
0x1800209a8  sub     rsp, 20h
0x1800209ac  mov     rbx, rdx
0x1800209af  mov     byte ptr [rax+8], 0
0x1800209b3  lea     rdx, [rax+8]; unsigned __int8 *
0x1800209b7  mov     rdi, r8
0x1800209ba  mov     rsi, rcx
0x1800209bd  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x1800209c2  movzx   r9d, [rsp+28h+arg_0]
0x1800209c8  mov     ecx, 0E0h
0x1800209cd  mov     eax, r9d
0x1800209d0  and     r9b, cl
0x1800209d3  and     eax, 1Fh
0x1800209d6  mov     [rbx], eax
0x1800209d8  movzx   eax, r9b
0x1800209dc  mov     [rdi], ax
0x1800209df  cmp     ax, cx
0x1800209e2  jnz     short loc_1800209F1
0x1800209e4  mov     rdx, rdi
0x1800209e7  mov     rcx, rsi
0x1800209ea  call    ??$Read@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::Read<ushort>(ushort &)
0x1800209ef  jmp     short loc_180020A0F
0x1800209f1  mov     ecx, 0C0h
0x1800209f6  cmp     ax, cx
0x1800209f9  jnz     short loc_180020A08
0x1800209fb  mov     rdx, rdi; unsigned __int8 *
0x1800209fe  mov     rcx, rsi; this
0x180020a01  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180020a06  jmp     short loc_180020A0F
0x180020a08  shr     ax, 5
0x180020a0c  mov     [rdi], ax
0x180020a0f  mov     rbx, [rsp+28h+arg_8]
0x180020a14  mov     rsi, [rsp+28h+arg_10]
0x180020a19  add     rsp, 20h
0x180020a1d  pop     rdi
0x180020a1e  retn
```
