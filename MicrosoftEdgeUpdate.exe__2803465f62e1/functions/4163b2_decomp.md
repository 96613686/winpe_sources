# __decomp

- ea: `0x4163b2`
- end: `0x416484`
- name: `__decomp`
- size: `210`
- prototype: `double __cdecl(double, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x415ddf`

## callees

- `0x4163b2`
- `0x416484`

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
0x4163b2  mov     edi, edi
0x4163b4  push    ebp
0x4163b5  mov     ebp, esp
0x4163b7  fld     [ebp+arg_0]
0x4163ba  fldz
0x4163bc  fucom   st(1)
0x4163be  fnstsw  ax
0x4163c0  push    esi
0x4163c1  test    ah, 44h
0x4163c4  jp      short loc_4163CF
0x4163c6  fstp    st(1)
0x4163c8  xor     esi, esi
0x4163ca  jmp     loc_41647C
0x4163cf  push    edi
0x4163d0  mov     di, word ptr [ebp+arg_0+6]
0x4163d4  movzx   eax, di
0x4163d7  test    eax, 7FF0h
0x4163dc  jnz     short loc_416458
0x4163de  mov     ecx, dword ptr [ebp+arg_0+4]
0x4163e1  mov     edx, dword ptr [ebp+arg_0]
0x4163e4  test    ecx, 0FFFFFh
0x4163ea  jnz     short loc_4163F0
0x4163ec  test    edx, edx
0x4163ee  jz      short loc_416458
0x4163f0  fcompp
0x4163f2  mov     esi, 0FFFFFC03h
0x4163f7  fnstsw  ax
0x4163f9  push    ebx
0x4163fa  xor     ebx, ebx
0x4163fc  test    ah, 41h
0x4163ff  jnz     short loc_416402
0x416401  inc     ebx
0x416402  test    byte ptr [ebp+arg_0+6], 10h
0x416406  jnz     short loc_416427
0x416408  add     ecx, ecx
0x41640a  mov     dword ptr [ebp+arg_0+4], ecx
0x41640d  test    edx, edx
0x41640f  jns     short loc_416417
0x416411  or      ecx, 1
0x416414  mov     dword ptr [ebp+arg_0+4], ecx
0x416417  add     edx, edx
0x416419  dec     esi
0x41641a  test    byte ptr [ebp+arg_0+6], 10h
0x41641e  jz      short loc_416408
0x416420  mov     di, word ptr [ebp+arg_0+6]
0x416424  mov     dword ptr [ebp+arg_0], edx
0x416427  mov     eax, 0FFEFh
0x41642c  and     di, ax
0x41642f  test    ebx, ebx
0x416431  movzx   eax, di
0x416434  mov     word ptr [ebp+arg_0+6], di
0x416438  pop     ebx
0x416439  jz      short loc_416444
0x41643b  or      eax, 8000h
0x416440  mov     word ptr [ebp+arg_0+6], ax
0x416444  fld     [ebp+arg_0]
0x416447  push    0
0x416449  push    ecx
0x41644a  push    ecx
0x41644b  fstp    [esp+14h+var_14]
0x41644e  call    __set_exp
0x416453  add     esp, 0Ch
0x416456  jmp     short loc_41647B
0x416458  push    0
0x41645a  push    ecx
0x41645b  fstp    st
0x41645d  push    ecx
0x41645e  fstp    [esp+14h+var_14]
0x416461  call    __set_exp
0x416466  movzx   esi, di
0x416469  add     esp, 0Ch
0x41646c  shr     esi, 4
0x41646f  and     esi, 7FFh
0x416475  sub     esi, 3FEh
0x41647b  pop     edi
0x41647c  mov     eax, [ebp+arg_8]
0x41647f  mov     [eax], esi
0x416481  pop     esi
0x416482  pop     ebp
0x416483  retn
```
