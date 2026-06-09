# BitmapWidth

- ea: `0x180001840`
- end: `0x180001871`
- name: `BitmapWidth`
- size: `49`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001840`

## pseudocode

```c
__int64 __fastcall BitmapWidth(unsigned int a1, unsigned int a2, unsigned int *a3)
{
  unsigned __int64 v3; // r9

  v3 = a2 * (unsigned __int64)a1;
  if ( v3 <= 0xFFFFFFFF && (int)v3 + 31 >= (unsigned int)v3 )
  {
    *a3 = (((int)v3 + 31) >> 3) & 0xFFFFFFFC;
    return 1;
  }
  else
  {
    *a3 = -1;
    return 0;
  }
}

```

## disassembly

```asm
0x180001840  mov     r9d, ecx
0x180001843  mov     ecx, 0FFFFFFFFh
0x180001848  mov     eax, edx
0x18000184a  imul    r9, rax
0x18000184e  cmp     r9, rcx
0x180001851  ja      short loc_18000185C
0x180001853  lea     eax, [r9+1Fh]
0x180001857  cmp     eax, r9d
0x18000185a  jnb     short loc_180001862
0x18000185c  mov     [r8], ecx
0x18000185f  xor     eax, eax
0x180001861  retn
0x180001862  sar     eax, 3
0x180001865  and     eax, 0FFFFFFFCh
0x180001868  mov     [r8], eax
0x18000186b  mov     eax, 1
0x180001870  retn
```
