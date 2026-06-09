# Em_AmrNB_Dec_L_mac

- ea: `0x18000671c`
- end: `0x18000675b`
- name: `Em_AmrNB_Dec_L_mac`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180004afc`
- `0x180004dd0`
- `0x1800051e0`
- `0x180005fa0`
- `0x180006298`
- `0x1800069c0`
- `0x180008928`

## callees

- `0x18000671c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_L_mac(int a1, __int16 a2, __int16 a3)
{
  int v4; // ecx
  int v5; // eax
  unsigned int v6; // ecx

  v4 = a3 * a2;
  v5 = 2 * v4;
  if ( v4 == 0x40000000 )
    v5 = 0x7FFFFFFF;
  v6 = v5 + a1;
  if ( (a1 ^ v5) >= 0 && ((a1 ^ v6) & 0x80000000) != 0 )
  {
    v6 = 0x7FFFFFFF;
    if ( a1 < 0 )
      return 0x80000000;
  }
  return v6;
}

```

## disassembly

```asm
0x18000671c  mov     r9d, ecx
0x18000671f  movsx   eax, r8w
0x180006723  movsx   ecx, dx
0x180006726  mov     edx, 7FFFFFFFh
0x18000672b  imul    ecx, eax
0x18000672e  lea     eax, [rcx+rcx]
0x180006731  cmp     ecx, 40000000h
0x180006737  jnz     short loc_18000673B
0x180006739  mov     eax, edx
0x18000673b  lea     ecx, [rax+r9]
0x18000673f  xor     eax, r9d
0x180006742  jl      short loc_180006758
0x180006744  mov     eax, ecx
0x180006746  xor     eax, r9d
0x180006749  jge     short loc_180006758
0x18000674b  test    r9d, r9d
0x18000674e  mov     ecx, edx
0x180006750  mov     eax, 80000000h
0x180006755  cmovs   ecx, eax
0x180006758  mov     eax, ecx
0x18000675a  retn
```
