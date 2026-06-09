# AResample<float,float>::readSamplesNoBuf(int)

- ea: `0x18007ec20`
- end: `0x18007ec3c`
- name: `?readSamplesNoBuf@?$AResample@MM@@IEAAHH@Z`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall AResample<float,float>::readSamplesNoBuf(__int64 a1, int a2)
{
  __int64 result; // rax
  int v3; // r8d

  result = 0;
  v3 = *(_DWORD *)(a1 + 92) - *(_DWORD *)(a1 + 88);
  if ( a2 >= 0 )
    result = (unsigned int)a2;
  if ( v3 < a2 )
    return (unsigned int)v3;
  return result;
}

```

## disassembly

```asm
0x18007ec20  mov     r8d, [rcx+5Ch]
0x18007ec24  xor     eax, eax
0x18007ec26  sub     r8d, [rcx+58h]
0x18007ec2a  mov     ecx, edx
0x18007ec2c  shr     ecx, 1Fh
0x18007ec2f  test    cl, cl
0x18007ec31  cmovz   eax, edx
0x18007ec34  cmp     r8d, edx
0x18007ec37  cmovl   eax, r8d
0x18007ec3b  retn
```
