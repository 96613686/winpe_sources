# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Calculate_growth(unsigned __int64)

- ea: `0x1800100ec`
- end: `0x18001011e`
- name: `?_Calculate_growth@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEBA_K_K@Z`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee94`
- `0x180013be0`
- `0x180014158`

## callees

- `0x1800100ec`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(
        _QWORD *a1,
        unsigned __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // r9

  result = 0xFFFFFFFFFFFFFFFLL;
  v3 = (__int64)(a1[2] - *a1) >> 4;
  v4 = v3 >> 1;
  if ( v3 <= 0xFFFFFFFFFFFFFFFLL - (v3 >> 1) )
  {
    result = v4 + v3;
    if ( v4 + v3 < a2 )
      return a2;
  }
  return result;
}

```

## disassembly

```asm
0x1800100ec  mov     r8, [rcx+10h]
0x1800100f0  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800100fa  sub     r8, [rcx]
0x1800100fd  mov     rcx, rax
0x180010100  sar     r8, 4
0x180010104  mov     r9, r8
0x180010107  shr     r9, 1
0x18001010a  sub     rcx, r9
0x18001010d  cmp     r8, rcx
0x180010110  ja      short locret_18001011D
0x180010112  lea     rax, [r9+r8]
0x180010116  cmp     rax, rdx
0x180010119  cmovb   rax, rdx
0x18001011d  retn
```
