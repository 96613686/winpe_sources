# SIDKeyCopyString(ushort *,ushort * *)

- ea: `0x180010850`
- end: `0x180010911`
- name: `?SIDKeyCopyString@@YAJPEAGPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180009ba4`
- `0x180009e04`

## callees

- `0x180010850`
- `0x180010920`
- `0x180010950`

## pseudocode

```c
__int64 __fastcall SIDKeyCopyString(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  unsigned __int16 *v4; // rsi
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdx
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  signed int v11; // eax

  *a2 = 0;
  v3 = -1;
  v4 = a1;
  do
    ++v3;
  while ( a1[v3] );
  v5 = v3 + 1;
  v6 = (unsigned __int16 *)SIDKeyProvAlloc(2 * v5);
  v7 = v6;
  if ( v6 )
  {
    v8 = -2147024809;
    if ( v5 )
    {
      if ( v5 > 0x7FFFFFFF )
      {
        *v6 = 0;
        goto LABEL_16;
      }
      v9 = 2147483646;
      do
      {
        if ( !v9 )
          break;
        if ( !*v4 )
          break;
        *v6++ = *v4++;
        --v9;
        --v5;
      }
      while ( v5 );
      v10 = v6 - 1;
      if ( v5 )
        v10 = v6;
      v11 = v5 == 0 ? 0x8007007A : 0;
      *v10 = 0;
    }
    else
    {
      v11 = -2147024809;
    }
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a2 = v7;
      v7 = 0;
    }
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_16:
  SIDKeyProvFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180010850  push    rbx
0x180010852  push    rbp
0x180010853  push    rsi
0x180010854  push    rdi
0x180010855  push    r14
0x180010857  sub     rsp, 20h
0x18001085b  xor     ebp, ebp
0x18001085d  mov     r14, rdx
0x180010860  mov     [rdx], rbp
0x180010863  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010867  mov     rsi, rcx
0x18001086a  inc     rbx
0x18001086d  cmp     [rcx+rbx*2], bp
0x180010871  jnz     short loc_18001086A
0x180010873  inc     rbx
0x180010876  lea     rcx, [rbx+rbx]; unsigned __int64
0x18001087a  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001087f  mov     rdx, rax
0x180010882  test    rax, rax
0x180010885  jnz     short loc_18001088E
0x180010887  mov     edi, 8007000Eh
0x18001088c  jmp     short loc_1800108F0
0x18001088e  mov     edi, 80070057h
0x180010893  test    rbx, rbx
0x180010896  jz      short loc_180010905
0x180010898  cmp     rbx, 7FFFFFFFh
0x18001089f  ja      short loc_18001090C
0x1800108a1  mov     ecx, 7FFFFFFEh
0x1800108a6  test    rcx, rcx
0x1800108a9  jz      short loc_1800108CA
0x1800108ab  movzx   r8d, word ptr [rsi]
0x1800108af  test    r8w, r8w
0x1800108b3  jz      short loc_1800108CA
0x1800108b5  mov     [rax], r8w
0x1800108b9  add     rsi, 2
0x1800108bd  add     rax, 2
0x1800108c1  dec     rcx
0x1800108c4  sub     rbx, 1
0x1800108c8  jnz     short loc_1800108A6
0x1800108ca  lea     rcx, [rax-2]
0x1800108ce  test    rbx, rbx
0x1800108d1  cmovnz  rcx, rax
0x1800108d5  neg     rbx
0x1800108d8  sbb     eax, eax
0x1800108da  not     eax
0x1800108dc  and     eax, 8007007Ah
0x1800108e1  mov     [rcx], bp
0x1800108e4  mov     edi, eax
0x1800108e6  test    eax, eax
0x1800108e8  js      short loc_1800108F0
0x1800108ea  mov     [r14], rdx
0x1800108ed  mov     rdx, rbp
0x1800108f0  mov     rcx, rdx; lpMem
0x1800108f3  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800108f8  mov     eax, edi
0x1800108fa  add     rsp, 20h
0x1800108fe  pop     r14
0x180010900  pop     rdi
0x180010901  pop     rsi
0x180010902  pop     rbp
0x180010903  pop     rbx
0x180010904  retn
0x180010905  mov     eax, edi
0x180010907  test    rbx, rbx
0x18001090a  jz      short loc_1800108E4
0x18001090c  mov     [rdx], bp
0x18001090f  jmp     short loc_1800108F0
```
