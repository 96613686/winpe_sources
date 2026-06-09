# Em_AmrNB_Dec_norm_l

- ea: `0x18000698c`
- end: `0x1800069b8`
- name: `Em_AmrNB_Dec_norm_l`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180004bb4`
- `0x180006eb4`
- `0x1800085b4`

## callees

- `0x18000698c`

## pseudocode

```c
__int16 __fastcall Em_AmrNB_Dec_norm_l(int a1)
{
  int v1; // eax
  int v2; // ecx

  v1 = a1;
  if ( a1 )
  {
    if ( a1 == -1 )
    {
      LOWORD(v1) = 31;
    }
    else
    {
      v2 = ~a1;
      if ( v1 >= 0 )
        v2 = v1;
      LOWORD(v1) = 0;
      while ( v2 < 0x40000000 )
      {
        v2 *= 2;
        LOWORD(v1) = v1 + 1;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000698c  mov     eax, ecx
0x18000698e  test    ecx, ecx
0x180006990  jnz     short loc_180006993
0x180006992  retn
0x180006993  cmp     eax, 0FFFFFFFFh
0x180006996  jnz     short loc_18000699E
0x180006998  mov     eax, 1Fh
0x18000699d  retn
0x18000699e  test    eax, eax
0x1800069a0  not     ecx
0x1800069a2  mov     edx, 40000000h
0x1800069a7  cmovns  ecx, eax
0x1800069aa  xor     eax, eax
0x1800069ac  jmp     short loc_1800069B3
0x1800069ae  add     ecx, ecx
0x1800069b0  inc     ax
0x1800069b3  cmp     ecx, edx
0x1800069b5  jl      short loc_1800069AE
0x1800069b7  retn
```
