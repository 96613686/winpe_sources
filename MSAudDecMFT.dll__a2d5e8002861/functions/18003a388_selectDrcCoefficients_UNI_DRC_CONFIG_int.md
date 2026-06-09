# selectDrcCoefficients(UNI_DRC_CONFIG *,int)

- ea: `0x18003a388`
- end: `0x18003a3eb`
- name: `?selectDrcCoefficients@@YAPEAUDRC_COEFFICIENTS_UNI_DRC@@PEAUUNI_DRC_CONFIG@@H@Z`
- size: `99`
- prototype: `struct DRC_COEFFICIENTS_UNI_DRC *__fastcall(struct UNI_DRC_CONFIG *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003a0d8`
- `0x18003a218`
- `0x18003b360`
- `0x18004b66c`
- `0x180074200`
- `0x18007461c`
- `0x180075394`
- `0x180076aa8`

## callees

- `0x18003a388`

## pseudocode

```c
struct DRC_COEFFICIENTS_UNI_DRC *__fastcall selectDrcCoefficients(struct UNI_DRC_CONFIG *a1, int a2)
{
  int v2; // r11d
  int v3; // r8d
  int v4; // r10d
  int v7; // ecx

  v2 = *((unsigned __int8 *)a1 + 13);
  v3 = -1;
  v4 = 0;
  if ( !*((_BYTE *)a1 + 13) )
    return 0;
  do
  {
    v7 = v4;
    if ( *((unsigned __int8 *)a1 + 1924 * (unsigned int)v4 + 1612) != a2 )
      v7 = v3;
    ++v4;
    v3 = v7;
  }
  while ( v4 < v2 );
  if ( v7 >= 0 )
    return (struct UNI_DRC_CONFIG *)((char *)a1 + 1924 * v7 + 1612);
  else
    return 0;
}

```

## disassembly

```asm
0x18003a388  mov     [rsp+arg_0], rbx
0x18003a38d  movzx   r11d, byte ptr [rcx+0Dh]
0x18003a392  or      r8d, 0FFFFFFFFh
0x18003a396  xor     r10d, r10d
0x18003a399  mov     ebx, edx
0x18003a39b  mov     r9, rcx
0x18003a39e  test    r11d, r11d
0x18003a3a1  jnz     short loc_18003A3C2
0x18003a3a3  xor     eax, eax
0x18003a3a5  mov     rbx, [rsp+arg_0]
0x18003a3aa  retn
0x18003a3ac  test    ecx, ecx
0x18003a3ae  js      short loc_18003A3A3
0x18003a3b0  imul    rax, r8, 784h
0x18003a3b7  add     rax, 64Ch
0x18003a3bd  add     rax, r9
0x18003a3c0  jmp     short loc_18003A3A5
0x18003a3c2  mov     eax, r10d
0x18003a3c5  mov     ecx, r10d
0x18003a3c8  imul    rdx, rax, 784h
0x18003a3cf  movzx   eax, byte ptr [rdx+r9+64Ch]
0x18003a3d8  cmp     eax, ebx
0x18003a3da  cmovnz  ecx, r8d
0x18003a3de  inc     r10d
0x18003a3e1  movsxd  r8, ecx
0x18003a3e4  cmp     r10d, r11d
0x18003a3e7  jl      short loc_18003A3C2
0x18003a3e9  jmp     short loc_18003A3AC
```
