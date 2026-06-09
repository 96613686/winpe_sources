# silk_PLC_update

- ea: `0x180017ba0`
- end: `0x180017d84`
- name: `silk_PLC_update`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016f60`

## callees

- `0x180017ba0`
- `0x18001b024`

## pseudocode

```c
__int64 __fastcall silk_PLC_update(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // r9
  int v6; // r11d
  int v7; // r8d
  int v8; // r10d
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // rax
  int v12; // ecx
  __int64 result; // rax

  v4 = *(char *)(a1 + 2789);
  *(_DWORD *)(a1 + 4188) = v4;
  if ( (_BYTE)v4 == 2 )
  {
    v5 = *(int *)(a1 + 2324);
    v6 = 0;
    if ( *(int *)(a2 + 4 * v5 - 4) > 0 )
    {
      v7 = 0;
      v8 = *(_DWORD *)(a1 + 2324);
      do
      {
        if ( v7 == (_DWORD)v5 )
          break;
        v9 = 5 * ((int)v5 - v7);
        v10 = *(__int16 *)(a2 + 2 * v9 + 88)
            + *(__int16 *)(a2 + 2 * v9 + 90)
            + *(__int16 *)(a2 + 2 * v9 + 92)
            + *(__int16 *)(a2 + 2 * v9 + 94)
            + *(__int16 *)(a2 + 2 * v9 + 86);
        if ( v10 > v6 )
        {
          v6 = v10;
          v11 = 5 * (__int16)(v5 - v7 - 1);
          *(_QWORD *)(a1 + 4200) = *(_QWORD *)(a2 + 2 * v11 + 96);
          *(_WORD *)(a1 + 4208) = *(_WORD *)(a2 + 2 * v11 + 104);
          v8 = *(_DWORD *)(a1 + 2324);
          *(_DWORD *)(a1 + 4196) = *(_DWORD *)(a2 + 4LL * (v8 - v7) - 4) << 8;
        }
        ++v7;
        LODWORD(v5) = v8;
      }
      while ( *(_DWORD *)(a1 + 2332) * v7 < *(_DWORD *)(a2 + 4LL * v8 - 4) );
    }
    *(_QWORD *)(a1 + 4200) = 0;
    *(_WORD *)(a1 + 4208) = 0;
    *(_WORD *)(a1 + 4204) = v6;
    if ( v6 >= 11469 )
    {
      if ( v6 > 15565 )
      {
        *(_WORD *)(a1 + 4204) = ((__int16)v6 * (__int16)(255016960 / v6)) >> 14;
        *(_DWORD *)(a1 + 4206) = 0;
      }
    }
    else
    {
      v12 = 1;
      if ( v6 > 1 )
        v12 = v6;
      *(_WORD *)(a1 + 4204) = ((__int16)v6 * (__int16)(11744256 / v12)) >> 10;
      *(_DWORD *)(a1 + 4206) = 0;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 4196) = 4608 * *(__int16 *)(a1 + 2316);
    *(_QWORD *)(a1 + 4200) = 0;
    *(_WORD *)(a1 + 4208) = 0;
  }
  memcpy_0((void *)(a1 + 4210), (const void *)(a2 + 64), 2LL * *(int *)(a1 + 2340));
  *(_WORD *)(a1 + 4264) = *(_WORD *)(a2 + 136);
  *(_QWORD *)(a1 + 4268) = *(_QWORD *)(a2 + 4LL * *(int *)(a1 + 2324) + 8);
  *(_DWORD *)(a1 + 4284) = *(_DWORD *)(a1 + 2332);
  result = *(unsigned int *)(a1 + 2324);
  *(_DWORD *)(a1 + 4280) = result;
  return result;
}

```

## disassembly

```asm
0x180017ba0  mov     [rsp+arg_0], rbx
0x180017ba5  push    rdi
0x180017ba6  sub     rsp, 20h
0x180017baa  mov     rbx, rcx
0x180017bad  mov     rdi, rdx
0x180017bb0  movsx   ecx, byte ptr [rcx+0AE5h]
0x180017bb7  mov     [rbx+105Ch], ecx
0x180017bbd  cmp     cl, 2
0x180017bc0  jnz     loc_180017D03
0x180017bc6  movsxd  r9, dword ptr [rbx+914h]
0x180017bcd  xor     r11d, r11d
0x180017bd0  cmp     [rdx+r9*4-4], r11d
0x180017bd5  jle     loc_180017C80
0x180017bdb  xor     r8d, r8d
0x180017bde  mov     r10d, r9d
0x180017be1  cmp     r8d, r9d
0x180017be4  jz      loc_180017C80
0x180017bea  mov     eax, r9d
0x180017bed  sub     eax, r8d
0x180017bf0  lea     eax, [rax+rax*4]
0x180017bf3  movsxd  rcx, eax
0x180017bf6  movsx   eax, word ptr [rdi+rcx*2+5Ch]
0x180017bfb  movsx   edx, word ptr [rdi+rcx*2+5Eh]
0x180017c00  add     edx, eax
0x180017c02  movsx   eax, word ptr [rdi+rcx*2+5Ah]
0x180017c07  add     edx, eax
0x180017c09  movsx   eax, word ptr [rdi+rcx*2+58h]
0x180017c0e  movsx   ecx, word ptr [rdi+rcx*2+56h]
0x180017c13  add     edx, eax
0x180017c15  add     ecx, edx
0x180017c17  cmp     ecx, r11d
0x180017c1a  jle     short loc_180017C63
0x180017c1c  sub     r9w, r8w
0x180017c20  mov     r11d, ecx
0x180017c23  lea     eax, [r9-1]
0x180017c27  cwde
0x180017c28  lea     eax, [rax+rax*4]
0x180017c2b  cdqe
0x180017c2d  movsd   xmm0, qword ptr [rdi+rax*2+60h]
0x180017c33  movsd   qword ptr [rbx+1068h], xmm0
0x180017c3b  movzx   eax, word ptr [rdi+rax*2+68h]
0x180017c40  mov     [rbx+1070h], ax
0x180017c47  mov     r10d, [rbx+914h]
0x180017c4e  mov     eax, r10d
0x180017c51  sub     eax, r8d
0x180017c54  cdqe
0x180017c56  mov     ecx, [rdi+rax*4-4]
0x180017c5a  shl     ecx, 8
0x180017c5d  mov     [rbx+1064h], ecx
0x180017c63  inc     r8d
0x180017c66  movsxd  rcx, r10d
0x180017c69  mov     eax, r8d
0x180017c6c  mov     r9d, r10d
0x180017c6f  imul    eax, [rbx+91Ch]
0x180017c76  cmp     eax, [rdi+rcx*4-4]
0x180017c7a  jl      loc_180017BE1
0x180017c80  xor     eax, eax
0x180017c82  mov     [rbx+1068h], rax
0x180017c89  mov     [rbx+1070h], ax
0x180017c90  mov     [rbx+106Ch], r11w
0x180017c98  cmp     r11d, 2CCDh
0x180017c9f  jge     short loc_180017CD3
0x180017ca1  mov     ecx, 1
0x180017ca6  mov     eax, 0B33400h
0x180017cab  cmp     r11d, ecx
0x180017cae  cdq
0x180017caf  cmovg   ecx, r11d
0x180017cb3  idiv    ecx
0x180017cb5  movsx   ecx, ax
0x180017cb8  movsx   eax, r11w
0x180017cbc  imul    ecx, eax
0x180017cbf  sar     ecx, 0Ah
0x180017cc2  xor     eax, eax
0x180017cc4  mov     [rbx+106Ch], cx
0x180017ccb  mov     [rbx+106Eh], eax
0x180017cd1  jmp     short loc_180017D26
0x180017cd3  cmp     r11d, 3CCDh
0x180017cda  jle     short loc_180017D26
0x180017cdc  mov     eax, 0F334000h
0x180017ce1  cdq
0x180017ce2  idiv    r11d
0x180017ce5  movsx   ecx, ax
0x180017ce8  movsx   eax, r11w
0x180017cec  imul    ecx, eax
0x180017cef  sar     ecx, 0Eh
0x180017cf2  xor     eax, eax
0x180017cf4  mov     [rbx+106Ch], cx
0x180017cfb  mov     [rbx+106Eh], eax
0x180017d01  jmp     short loc_180017D26
0x180017d03  movsx   eax, word ptr [rbx+90Ch]
0x180017d0a  lea     ecx, [rax+rax*8]
0x180017d0d  shl     ecx, 9
0x180017d10  xor     eax, eax
0x180017d12  mov     [rbx+1064h], ecx
0x180017d18  mov     [rbx+1068h], rax
0x180017d1f  mov     [rbx+1070h], ax
0x180017d26  movsxd  r8, dword ptr [rbx+924h]
0x180017d2d  lea     rdx, [rdi+40h]; Src
0x180017d31  add     r8, r8; Size
0x180017d34  lea     rcx, [rbx+1072h]; void *
0x180017d3b  call    memcpy_0
0x180017d40  movzx   eax, word ptr [rdi+88h]
0x180017d47  mov     [rbx+10A8h], ax
0x180017d4e  movsxd  rax, dword ptr [rbx+914h]
0x180017d55  mov     rcx, [rdi+rax*4+8]
0x180017d5a  mov     [rbx+10ACh], rcx
0x180017d61  mov     eax, [rbx+91Ch]
0x180017d67  mov     [rbx+10BCh], eax
0x180017d6d  mov     eax, [rbx+914h]
0x180017d73  mov     [rbx+10B8h], eax
0x180017d79  mov     rbx, [rsp+28h+arg_0]
0x180017d7e  add     rsp, 20h
0x180017d82  pop     rdi
0x180017d83  retn
```
