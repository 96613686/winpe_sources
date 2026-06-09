# bitsset

- ea: `0x180007df0`
- end: `0x180007e22`
- name: `bitsset`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000629c`
- `0x180007030`
- `0x180007d94`
- `0x180013990`
- `0x18007a00c`
- `0x18007ab24`
- `0x18007af50`
- `0x18007afd8`
- `0x18007b908`

## callees

- `0x180007df0`

## pseudocode

```c
__int64 __fastcall bitsset(int a1)
{
  __int64 result; // rax
  int v2; // edx
  int v3; // r9d
  unsigned int v4; // r8d

  LODWORD(result) = 0;
  v2 = 1;
  v3 = 16;
  do
  {
    v4 = result + 1;
    if ( (v2 & a1) == 0 )
      v4 = result;
    result = v4 + 1;
    if ( (__ROL4__(v2, 1) & a1) == 0 )
      result = v4;
    v2 = __ROL4__(v2, 2);
    --v3;
  }
  while ( v3 );
  return result;
}

```

## disassembly

```asm
0x180007df0  xor     eax, eax
0x180007df2  mov     edx, 1
0x180007df7  mov     r9d, 10h
0x180007dfd  nop     dword ptr [rax]
0x180007e00  lea     r8d, [rax+1]
0x180007e04  test    ecx, edx
0x180007e06  cmovz   r8d, eax
0x180007e0a  mov     eax, edx
0x180007e0c  rol     eax, 1
0x180007e0e  test    ecx, eax
0x180007e10  lea     eax, [r8+1]
0x180007e14  cmovz   eax, r8d
0x180007e18  rol     edx, 2
0x180007e1b  sub     r9d, 1
0x180007e1f  jnz     short loc_180007E00
0x180007e21  retn
```
