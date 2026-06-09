# sub_401EBE

- ea: `0x401ebe`
- end: `0x401ef8`
- name: `sub_401EBE`
- size: `58`
- prototype: `int __thiscall(void *this, int)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x401ef9`
- `0x401ff4`
- `0x404ba2`
- `0x405281`
- `0x4052e7`
- `0x40530a`
- `0x405337`
- `0x405407`
- `0x40580a`
- `0x405967`
- `0x405bfc`
- `0x4060c5`
- `0x40616a`
- `0x406257`
- `0x40878e`
- `0x4087f6`
- `0x40885e`
- `0x4089a2`
- `0x409593`

## callees

- `0x401aa5`
- `0x401ebe`
- `0x4020b5`

## pseudocode

```c
int __thiscall sub_401EBE(void *this, int a2)
{
  if ( a2 < 0 )
    sub_401AA5(-2147024809);
  if ( ((*(_DWORD *)(*(_DWORD *)this - 8) - a2) | (1 - *(_DWORD *)(*(_DWORD *)this - 4))) < 0 )
  {
    _mm_lfence();
    sub_4020B5(a2);
  }
  return *(_DWORD *)this;
}

```

## disassembly

```asm
0x401ebe  push    ebp
0x401ebf  mov     ebp, esp
0x401ec1  mov     edx, [ebp+arg_0]
0x401ec4  push    esi
0x401ec5  mov     esi, ecx
0x401ec7  test    edx, edx
0x401ec9  js      short loc_401EEE
0x401ecb  mov     eax, [esi]
0x401ecd  xor     ecx, ecx
0x401ecf  inc     ecx
0x401ed0  sub     ecx, [eax-4]
0x401ed3  mov     eax, [eax-8]
0x401ed6  sub     eax, edx
0x401ed8  or      ecx, eax
0x401eda  jge     short loc_401EE7
0x401edc  push    edx
0x401edd  mov     ecx, esi
0x401edf  lfence
0x401ee2  call    sub_4020B5
0x401ee7  mov     eax, [esi]
0x401ee9  pop     esi
0x401eea  pop     ebp
0x401eeb  retn    4
0x401eee  push    80070057h
0x401ef3  call    sub_401AA5
```
