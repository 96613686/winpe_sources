# CBitStream::Rewind(int)

- ea: `0x180006700`
- end: `0x180006729`
- name: `?Rewind@CBitStream@@QEAA_NH@Z`
- size: `41`
- prototype: `char __fastcall(CBitStream *this, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006068`
- `0x180006574`
- `0x180006628`
- `0x18000de5c`

## callees

- `0x180006700`

## pseudocode

```c
char __fastcall CBitStream::Rewind(CBitStream *this, int a2)
{
  int v2; // r8d
  int v3; // r8d
  char v4; // dl

  if ( a2 <= 0 )
    return 0;
  v2 = *((_DWORD *)this + 9);
  *((_DWORD *)this + 8) -= a2;
  v3 = v2 - a2;
  *((_DWORD *)this + 6) += a2;
  v4 = 1;
  *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v3;
  return v4;
}

```

## disassembly

```asm
0x180006700  test    edx, edx
0x180006702  jle     short loc_180006725
0x180006704  mov     r8d, [rcx+24h]
0x180006708  sub     [rcx+20h], edx
0x18000670b  sub     r8d, edx
0x18000670e  add     [rcx+18h], edx
0x180006711  mov     edx, 1
0x180006716  mov     eax, [rcx+14h]
0x180006719  sub     eax, edx
0x18000671b  and     r8d, eax
0x18000671e  mov     [rcx+24h], r8d
0x180006722  mov     al, dl
0x180006724  retn
0x180006725  xor     dl, dl
0x180006727  jmp     short loc_180006722
```
