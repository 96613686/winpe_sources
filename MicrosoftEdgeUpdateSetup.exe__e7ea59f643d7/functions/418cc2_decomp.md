# __decomp

- ea: `0x418cc2`
- end: `0x418d94`
- name: `__decomp`
- size: `210`
- prototype: `double __cdecl(double, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4186ef`

## callees

- `0x418cc2`
- `0x418d94`

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
0x418cc2  mov     edi, edi
0x418cc4  push    ebp
0x418cc5  mov     ebp, esp
0x418cc7  fld     [ebp+arg_0]
0x418cca  fldz
0x418ccc  fucom   st(1)
0x418cce  fnstsw  ax
0x418cd0  push    esi
0x418cd1  test    ah, 44h
0x418cd4  jp      short loc_418CDF
0x418cd6  fstp    st(1)
0x418cd8  xor     esi, esi
0x418cda  jmp     loc_418D8C
0x418cdf  push    edi
0x418ce0  mov     di, word ptr [ebp+arg_0+6]
0x418ce4  movzx   eax, di
0x418ce7  test    eax, 7FF0h
0x418cec  jnz     short loc_418D68
0x418cee  mov     ecx, dword ptr [ebp+arg_0+4]
0x418cf1  mov     edx, dword ptr [ebp+arg_0]
0x418cf4  test    ecx, 0FFFFFh
0x418cfa  jnz     short loc_418D00
0x418cfc  test    edx, edx
0x418cfe  jz      short loc_418D68
0x418d00  fcompp
0x418d02  mov     esi, 0FFFFFC03h
0x418d07  fnstsw  ax
0x418d09  push    ebx
0x418d0a  xor     ebx, ebx
0x418d0c  test    ah, 41h
0x418d0f  jnz     short loc_418D12
0x418d11  inc     ebx
0x418d12  test    byte ptr [ebp+arg_0+6], 10h
0x418d16  jnz     short loc_418D37
0x418d18  add     ecx, ecx
0x418d1a  mov     dword ptr [ebp+arg_0+4], ecx
0x418d1d  test    edx, edx
0x418d1f  jns     short loc_418D27
0x418d21  or      ecx, 1
0x418d24  mov     dword ptr [ebp+arg_0+4], ecx
0x418d27  add     edx, edx
0x418d29  dec     esi
0x418d2a  test    byte ptr [ebp+arg_0+6], 10h
0x418d2e  jz      short loc_418D18
0x418d30  mov     di, word ptr [ebp+arg_0+6]
0x418d34  mov     dword ptr [ebp+arg_0], edx
0x418d37  mov     eax, 0FFEFh
0x418d3c  and     di, ax
0x418d3f  test    ebx, ebx
0x418d41  movzx   eax, di
0x418d44  mov     word ptr [ebp+arg_0+6], di
0x418d48  pop     ebx
0x418d49  jz      short loc_418D54
0x418d4b  or      eax, 8000h
0x418d50  mov     word ptr [ebp+arg_0+6], ax
0x418d54  fld     [ebp+arg_0]
0x418d57  push    0
0x418d59  push    ecx
0x418d5a  push    ecx
0x418d5b  fstp    [esp+14h+var_14]
0x418d5e  call    __set_exp
0x418d63  add     esp, 0Ch
0x418d66  jmp     short loc_418D8B
0x418d68  push    0
0x418d6a  push    ecx
0x418d6b  fstp    st
0x418d6d  push    ecx
0x418d6e  fstp    [esp+14h+var_14]
0x418d71  call    __set_exp
0x418d76  movzx   esi, di
0x418d79  add     esp, 0Ch
0x418d7c  shr     esi, 4
0x418d7f  and     esi, 7FFh
0x418d85  sub     esi, 3FEh
0x418d8b  pop     edi
0x418d8c  mov     eax, [ebp+arg_8]
0x418d8f  mov     [eax], esi
0x418d91  pop     esi
0x418d92  pop     ebp
0x418d93  retn
```
