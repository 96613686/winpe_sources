# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Successor(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)

- ea: `0x180006c78`
- end: `0x180006cc9`
- name: `?Successor@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000387c`
- `0x180005fbc`
- `0x180006388`

## callees

- `0x180006c78`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Successor(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 i; // rcx
  char v5; // dl

  if ( !a2 )
    return 0;
  result = *(_QWORD *)(a2 + 24);
  if ( result == *(_QWORD *)(a1 + 40) )
  {
    for ( i = *(_QWORD *)(a2 + 32); i != *(_QWORD *)(a1 + 40); i = *(_QWORD *)(i + 32) )
    {
      if ( a2 != *(_QWORD *)(i + 24) )
      {
        v5 = 0;
        goto LABEL_13;
      }
      a2 = i;
    }
    v5 = 1;
LABEL_13:
    result = 0;
    if ( !v5 )
      return i;
  }
  else
  {
    if ( !result )
      return 0;
    while ( *(_QWORD *)(result + 16) != *(_QWORD *)(a1 + 40) )
      result = *(_QWORD *)(result + 16);
  }
  return result;
}

```

## disassembly

```asm
0x180006c78  mov     r8, rcx
0x180006c7b  test    rdx, rdx
0x180006c7e  jnz     short loc_180006C83
0x180006c80  xor     eax, eax
0x180006c82  retn
0x180006c83  mov     rax, [rdx+18h]
0x180006c87  cmp     rax, [rcx+28h]
0x180006c8b  jz      short loc_180006CA1
0x180006c8d  test    rax, rax
0x180006c90  jz      short loc_180006C80
0x180006c92  mov     rcx, [rax+10h]
0x180006c96  cmp     rcx, [r8+28h]
0x180006c9a  jz      short locret_180006CC8
0x180006c9c  mov     rax, rcx
0x180006c9f  jmp     short loc_180006C92
0x180006ca1  mov     rcx, [rdx+20h]
0x180006ca5  cmp     rcx, [r8+28h]
0x180006ca9  jz      short loc_180006CBE
0x180006cab  cmp     rdx, [rcx+18h]
0x180006caf  jnz     short loc_180006CBA
0x180006cb1  mov     rdx, rcx
0x180006cb4  mov     rcx, [rcx+20h]
0x180006cb8  jmp     short loc_180006CA5
0x180006cba  xor     dl, dl
0x180006cbc  jmp     short loc_180006CC0
0x180006cbe  mov     dl, 1
0x180006cc0  xor     eax, eax
0x180006cc2  test    dl, dl
0x180006cc4  cmovz   rax, rcx
0x180006cc8  retn
```
