# bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)

- ea: `0x180011cac`
- end: `0x180011d56`
- name: `??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a018`
- `0x18000a0b8`
- `0x18000a158`
- `0x18000a2d0`
- `0x18000c6a8`
- `0x18000ce80`
- `0x18000d334`
- `0x18000d4b8`
- `0x18000d66c`
- `0x180011d68`
- `0x18001bce4`

## callees

- `0x18000ca6c`
- `0x180011cac`

## pseudocode

```c
__int64 __fastcall bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(
        __int64 a1,
        unsigned int a2)
{
  __int64 v3; // r9
  __int64 result; // rax
  unsigned int v5; // ecx
  unsigned int v6; // r8d
  unsigned int v7; // edx
  int v8; // ecx

  v3 = *(unsigned int *)(a1 + 28);
  if ( v3 + (unsigned __int64)*(unsigned int *)(a1 + 32) + 4 >= *(unsigned int *)(a1 + 24) )
    return bond::GenericWriteVariableUnsigned<bond::OutputMemoryStream<std::allocator<char>>,unsigned int>(a1, a2);
  result = *(_QWORD *)(a1 + 48);
  v5 = a2 >> 7;
  if ( a2 >> 7 )
  {
    v6 = a2 >> 14;
    *(_BYTE *)(result + v3) = a2 | 0x80;
    if ( a2 >> 14 )
    {
      v7 = a2 >> 21;
      *(_BYTE *)(result + v3 + 1) = v5 | 0x80;
      if ( v5 >> 14 )
      {
        *(_BYTE *)(result + v3 + 2) = v6 | 0x80;
        if ( v6 >> 14 )
        {
          *(_BYTE *)(result + v3 + 4) = v6 >> 14;
          LOBYTE(v7) = v7 | 0x80;
          v8 = 5;
        }
        else
        {
          v8 = 4;
        }
        *(_BYTE *)(result + v3 + 3) = v7;
      }
      else
      {
        *(_BYTE *)(result + v3 + 2) = v6;
        v8 = 3;
      }
    }
    else
    {
      *(_BYTE *)(result + v3 + 1) = v5;
      v8 = 2;
    }
  }
  else
  {
    *(_BYTE *)(result + v3) = a2;
    v8 = 1;
  }
  *(_DWORD *)(a1 + 28) += v8;
  return result;
}

```

## disassembly

```asm
0x180011cac  mov     r8d, [rcx+20h]
0x180011cb0  mov     r10, rcx
0x180011cb3  mov     r9d, [rcx+1Ch]
0x180011cb7  add     r8, 4
0x180011cbb  mov     eax, [rcx+18h]
0x180011cbe  add     r8, r9
0x180011cc1  cmp     r8, rax
0x180011cc4  jnb     loc_180011D51
0x180011cca  mov     rax, [rcx+30h]
0x180011cce  mov     ecx, edx
0x180011cd0  shr     ecx, 7
0x180011cd3  test    ecx, ecx
0x180011cd5  jz      short loc_180011D43
0x180011cd7  mov     r11b, 80h
0x180011cda  mov     r8d, ecx
0x180011cdd  or      dl, r11b
0x180011ce0  shr     r8d, 7
0x180011ce4  mov     [rax+r9], dl
0x180011ce8  test    r8d, r8d
0x180011ceb  jz      short loc_180011D37
0x180011ced  or      cl, r11b
0x180011cf0  mov     edx, r8d
0x180011cf3  shr     edx, 7
0x180011cf6  mov     [rax+r9+1], cl
0x180011cfb  test    edx, edx
0x180011cfd  jz      short loc_180011D2B
0x180011cff  or      r8b, r11b
0x180011d02  mov     ecx, edx
0x180011d04  shr     ecx, 7
0x180011d07  mov     [rax+r9+2], r8b
0x180011d0c  test    ecx, ecx
0x180011d0e  jz      short loc_180011D1F
0x180011d10  mov     [rax+r9+4], cl
0x180011d15  or      dl, r11b
0x180011d18  mov     ecx, 5
0x180011d1d  jmp     short loc_180011D24
0x180011d1f  mov     ecx, 4
0x180011d24  mov     [rax+r9+3], dl
0x180011d29  jmp     short loc_180011D4C
0x180011d2b  mov     [rax+r9+2], r8b
0x180011d30  mov     ecx, 3
0x180011d35  jmp     short loc_180011D4C
0x180011d37  mov     [rax+r9+1], cl
0x180011d3c  mov     ecx, 2
0x180011d41  jmp     short loc_180011D4C
0x180011d43  mov     [rax+r9], dl
0x180011d47  mov     ecx, 1
0x180011d4c  add     [r10+1Ch], ecx
0x180011d50  retn
0x180011d51  jmp     ??$GenericWriteVariableUnsigned@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@I@bond@@YAXAEAV?$OutputMemoryStream@V?$allocator@D@std@@@0@I@Z; bond::GenericWriteVariableUnsigned<bond::OutputMemoryStream<std::allocator<char>>,uint>(bond::OutputMemoryStream<std::allocator<char>> &,uint)
```
