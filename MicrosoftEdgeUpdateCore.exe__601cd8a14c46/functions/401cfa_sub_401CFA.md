# sub_401CFA

- ea: `0x401cfa`
- end: `0x401d46`
- name: `sub_401CFA`
- size: `76`
- prototype: `void *__thiscall(void *this, wchar_t *String)`
- caller_count: `30`
- callee_count: `6`
- tags: ``

## callers

- `0x4013c0`
- `0x4013e0`
- `0x402675`
- `0x4026d7`
- `0x40284a`
- `0x402c60`
- `0x402d9e`
- `0x404a78`
- `0x405120`
- `0x405df0`
- `0x40616a`
- `0x406b17`
- `0x407712`
- `0x4078b3`
- `0x407ea3`
- `0x407f70`
- `0x40878e`
- `0x4087f6`
- `0x40885e`
- `0x4098ce`
- `0x409aee`
- `0x409dbf`
- `0x40a243`
- `0x40a4a5`
- `0x40a55e`
- `0x40a8e0`
- `0x40abe5`
- `0x40b905`
- `0x40bb5b`
- `0x40bba1`

## callees

- `0x4015fb`
- `0x401cfa`
- `0x401ef9`
- `0x401fbb`
- `0x401ff4`
- `0x4163ef`

## pseudocode

```c
void *__thiscall sub_401CFA(void *this, wchar_t *String)
{
  int *v3; // eax
  size_t v4; // eax

  v3 = sub_4015FB();
  sub_401FBB(v3);
  if ( !String )
  {
    v4 = 0;
    goto LABEL_6;
  }
  if ( ((unsigned int)String & 0xFFFF0000) != 0 )
  {
    v4 = wcslen(String);
LABEL_6:
    sub_401EF9(String, v4);
    return this;
  }
  sub_401FF4((unsigned __int16)String);
  return this;
}

```

## disassembly

```asm
0x401cfa  push    ebp
0x401cfb  mov     ebp, esp
0x401cfd  push    esi
0x401cfe  push    edi
0x401cff  mov     edi, ecx
0x401d01  call    sub_4015FB
0x401d06  push    eax
0x401d07  mov     ecx, edi
0x401d09  call    sub_401FBB
0x401d0e  mov     esi, [ebp+String]
0x401d11  test    esi, esi
0x401d13  jz      short loc_401D33
0x401d15  test    esi, 0FFFF0000h
0x401d1b  jnz     short loc_401D2A
0x401d1d  movzx   eax, si
0x401d20  mov     ecx, edi
0x401d22  push    eax
0x401d23  call    sub_401FF4
0x401d28  jmp     short loc_401D3E
0x401d2a  push    esi; String
0x401d2b  call    _wcslen
0x401d30  pop     ecx
0x401d31  jmp     short loc_401D35
0x401d33  xor     eax, eax
0x401d35  push    eax; int
0x401d36  push    esi; Src
0x401d37  mov     ecx, edi
0x401d39  call    sub_401EF9
0x401d3e  mov     eax, edi
0x401d40  pop     edi
0x401d41  pop     esi
0x401d42  pop     ebp
0x401d43  retn    4
```
