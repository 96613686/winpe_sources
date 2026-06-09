# __decomp

- ea: `0x41d622`
- end: `0x41d6f4`
- name: `__decomp`
- size: `210`
- prototype: `double __cdecl(double, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x41d04f`

## callees

- `0x41d622`
- `0x41d6f4`

## pseudocode

```c
double __cdecl _decomp(double a1, int *a2)
{
  double result; // st7
  int v3; // esi
  int v4; // ecx
  int v5; // edx

  if ( 0.0 == a1 )
  {
    result = 0.0;
    v3 = 0;
  }
  else if ( (HIWORD(a1) & 0x7FF0) == 0
         && ((v4 = HIDWORD(a1), v5 = LODWORD(a1), (HIDWORD(a1) & 0xFFFFF) != 0) || LODWORD(a1)) )
  {
    v3 = -1021;
    if ( (BYTE6(a1) & 0x10) == 0 )
    {
      do
      {
        v4 *= 2;
        HIDWORD(a1) = v4;
        if ( v5 < 0 )
        {
          v4 |= 1u;
          HIDWORD(a1) = v4;
        }
        v5 *= 2;
        --v3;
      }
      while ( (BYTE6(a1) & 0x10) == 0 );
      LODWORD(a1) = v5;
    }
    result = _set_exp(LODWORD(a1), SWORD2(a1), 0);
  }
  else
  {
    result = _set_exp(LODWORD(a1), SWORD2(a1), 0);
    v3 = ((HIWORD(a1) >> 4) & 0x7FF) - 1022;
  }
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x41d622  mov     edi, edi
0x41d624  push    ebp
0x41d625  mov     ebp, esp
0x41d627  fld     [ebp+arg_0]
0x41d62a  fldz
0x41d62c  fucom   st(1)
0x41d62e  fnstsw  ax
0x41d630  push    esi
0x41d631  test    ah, 44h
0x41d634  jp      short loc_41D63F
0x41d636  fstp    st(1)
0x41d638  xor     esi, esi
0x41d63a  jmp     loc_41D6EC
0x41d63f  push    edi
0x41d640  mov     di, word ptr [ebp+arg_0+6]
0x41d644  movzx   eax, di
0x41d647  test    eax, 7FF0h
0x41d64c  jnz     short loc_41D6C8
0x41d64e  mov     ecx, dword ptr [ebp+arg_0+4]
0x41d651  mov     edx, dword ptr [ebp+arg_0]
0x41d654  test    ecx, 0FFFFFh
0x41d65a  jnz     short loc_41D660
0x41d65c  test    edx, edx
0x41d65e  jz      short loc_41D6C8
0x41d660  fcompp
0x41d662  mov     esi, 0FFFFFC03h
0x41d667  fnstsw  ax
0x41d669  push    ebx
0x41d66a  xor     ebx, ebx
0x41d66c  test    ah, 41h
0x41d66f  jnz     short loc_41D672
0x41d671  inc     ebx
0x41d672  test    byte ptr [ebp+arg_0+6], 10h
0x41d676  jnz     short loc_41D697
0x41d678  add     ecx, ecx
0x41d67a  mov     dword ptr [ebp+arg_0+4], ecx
0x41d67d  test    edx, edx
0x41d67f  jns     short loc_41D687
0x41d681  or      ecx, 1
0x41d684  mov     dword ptr [ebp+arg_0+4], ecx
0x41d687  add     edx, edx
0x41d689  dec     esi
0x41d68a  test    byte ptr [ebp+arg_0+6], 10h
0x41d68e  jz      short loc_41D678
0x41d690  mov     di, word ptr [ebp+arg_0+6]
0x41d694  mov     dword ptr [ebp+arg_0], edx
0x41d697  mov     eax, 0FFEFh
0x41d69c  and     di, ax
0x41d69f  test    ebx, ebx
0x41d6a1  movzx   eax, di
0x41d6a4  mov     word ptr [ebp+arg_0+6], di
0x41d6a8  pop     ebx
0x41d6a9  jz      short loc_41D6B4
0x41d6ab  or      eax, 8000h
0x41d6b0  mov     word ptr [ebp+arg_0+6], ax
0x41d6b4  fld     [ebp+arg_0]
0x41d6b7  push    0
0x41d6b9  push    ecx
0x41d6ba  push    ecx
0x41d6bb  fstp    [esp+14h+var_14]
0x41d6be  call    __set_exp
0x41d6c3  add     esp, 0Ch
0x41d6c6  jmp     short loc_41D6EB
0x41d6c8  push    0
0x41d6ca  push    ecx
0x41d6cb  fstp    st
0x41d6cd  push    ecx
0x41d6ce  fstp    [esp+14h+var_14]
0x41d6d1  call    __set_exp
0x41d6d6  movzx   esi, di
0x41d6d9  add     esp, 0Ch
0x41d6dc  shr     esi, 4
0x41d6df  and     esi, 7FFh
0x41d6e5  sub     esi, 3FEh
0x41d6eb  pop     edi
0x41d6ec  mov     eax, [ebp+arg_8]
0x41d6ef  mov     [eax], esi
0x41d6f1  pop     esi
0x41d6f2  pop     ebp
0x41d6f3  retn
```
