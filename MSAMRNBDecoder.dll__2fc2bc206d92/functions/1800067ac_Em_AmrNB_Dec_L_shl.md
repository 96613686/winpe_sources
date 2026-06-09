# Em_AmrNB_Dec_L_shl

- ea: `0x1800067ac`
- end: `0x1800067ff`
- name: `Em_AmrNB_Dec_L_shl`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180003800`
- `0x180004dd0`
- `0x1800051e0`
- `0x180006808`
- `0x1800069c0`
- `0x180006eb4`
- `0x1800079f0`
- `0x180007b6c`
- `0x180007c54`
- `0x180007d60`
- `0x1800085b4`
- `0x180008928`
- `0x180009a74`

## callees

- `0x1800067ac`
- `0x180006808`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_L_shl(__int64 a1, __int16 a2)
{
  __int16 v2; // ax
  __int64 v3; // rdx

  v2 = a2;
  if ( a2 > 0 )
  {
    while ( (int)a1 <= 0x3FFFFFFF )
    {
      if ( (int)a1 < -1073741824 )
      {
        LODWORD(a1) = 0x80000000;
        return (unsigned int)a1;
      }
      LODWORD(a1) = 2 * a1;
      if ( --v2 <= 0 )
        return (unsigned int)a1;
    }
    LODWORD(a1) = 0x7FFFFFFF;
  }
  else
  {
    v3 = 4294967264LL;
    if ( v2 >= -32 )
      LOWORD(v3) = v2;
    LOWORD(v3) = -(__int16)v3;
    LODWORD(a1) = Em_AmrNB_Dec_L_shr(a1, v3);
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1800067ac  sub     rsp, 28h
0x1800067b0  movzx   eax, dx
0x1800067b3  test    dx, dx
0x1800067b6  jg      short loc_1800067D0
0x1800067b8  mov     edx, 0FFFFFFE0h
0x1800067bd  cmp     ax, dx
0x1800067c0  cmovge  dx, ax
0x1800067c4  neg     dx
0x1800067c7  call    Em_AmrNB_Dec_L_shr
0x1800067cc  mov     ecx, eax
0x1800067ce  jmp     short loc_1800067F8
0x1800067d0  cmp     ecx, 3FFFFFFFh
0x1800067d6  jg      short loc_1800067F3
0x1800067d8  cmp     ecx, 0C0000000h
0x1800067de  jl      short loc_1800067EC
0x1800067e0  add     ecx, ecx
0x1800067e2  dec     ax
0x1800067e5  test    ax, ax
0x1800067e8  jg      short loc_1800067D0
0x1800067ea  jmp     short loc_1800067F8
0x1800067ec  mov     ecx, 80000000h
0x1800067f1  jmp     short loc_1800067F8
0x1800067f3  mov     ecx, 7FFFFFFFh
0x1800067f8  mov     eax, ecx
0x1800067fa  add     rsp, 28h
0x1800067fe  retn
```
