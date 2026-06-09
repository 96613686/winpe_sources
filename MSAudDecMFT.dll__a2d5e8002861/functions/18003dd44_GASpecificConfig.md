# GASpecificConfig

- ea: `0x18003dd44`
- end: `0x18003df31`
- name: `GASpecificConfig`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003df38`

## callees

- `0x18003dd44`
- `0x18003e3ec`
- `0x18004dd14`
- `0x18005d730`

## pseudocode

```c
__int64 __fastcall GASpecificConfig(unsigned int *a1, int *a2, int a3, unsigned int a4)
{
  unsigned int v8; // eax
  bool v9; // zf
  int v10; // eax
  int v11; // eax

  memset_0(a2, 0, 0xE0u);
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v8 = a1[1];
  *a2 = (v8 >> --*a1) & 1;
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v9 = ((a1[1] >> --*a1) & 1) == 0;
  a2[1] = (a1[1] >> *a1) & 1;
  if ( !v9 )
  {
    if ( *a1 < 0xE )
      FillBitCache(a1, 0xEu);
    *a1 -= 14;
    a2[2] = (a1[1] >> *a1) & 0x3FFF;
  }
  if ( !*a1 )
    FillBitCache(a1, 1u);
  a2[3] = (a1[1] >> --*a1) & 1;
  if ( !a3 )
    CProgramCfg_Read((_BYTE *)a2 + 44, a1);
  if ( a4 == 6 || a4 == 20 )
  {
    if ( *a1 < 3 )
      FillBitCache(a1, 3u);
    *a1 -= 3;
    a2[5] = (a1[1] >> *a1) & 7;
  }
  if ( !a2[3] )
    return 0;
  if ( a4 == 22 )
  {
    if ( *a1 < 5 )
      FillBitCache(a1, 5u);
    *a1 -= 5;
    a2[6] = (a1[1] >> *a1) & 0x1F;
    if ( *a1 < 0xB )
      FillBitCache(a1, 0xBu);
    *a1 -= 11;
    a2[7] = (a1[1] >> *a1) & 0x7FF;
  }
  else if ( a4 <= 0x17 )
  {
    v10 = 10092544;
    if ( _bittest(&v10, a4) )
    {
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[8] = (a1[1] >> --*a1) & 1;
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[9] = (a1[1] >> --*a1) & 1;
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[10] = (a1[1] >> --*a1) & 1;
    }
  }
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v11 = (a1[1] >> --*a1) & 1;
  a2[4] = v11;
  return v11 != 0 ? 0xFFFFFFF3 : 0;
}

```

## disassembly

```asm
0x18003dd44  push    rbx
0x18003dd46  push    rbp
0x18003dd47  push    rsi
0x18003dd48  push    rdi
0x18003dd49  push    r14
0x18003dd4b  push    r15
0x18003dd4d  sub     rsp, 28h
0x18003dd51  mov     rdi, rdx
0x18003dd54  mov     ebp, r8d
0x18003dd57  mov     rbx, rcx
0x18003dd5a  xor     edx, edx; Val
0x18003dd5c  mov     rcx, rdi; void *
0x18003dd5f  mov     r8d, 0E0h; Size
0x18003dd65  mov     esi, r9d
0x18003dd68  call    memset_0
0x18003dd6d  mov     r14d, 1
0x18003dd73  cmp     [rbx], r14d
0x18003dd76  jnb     short loc_18003DD83
0x18003dd78  mov     edx, r14d
0x18003dd7b  mov     rcx, rbx
0x18003dd7e  call    FillBitCache
0x18003dd83  mov     eax, [rbx+4]
0x18003dd86  or      r15d, 0FFFFFFFFh
0x18003dd8a  add     [rbx], r15d
0x18003dd8d  mov     ecx, [rbx]
0x18003dd8f  shr     eax, cl
0x18003dd91  and     eax, r14d
0x18003dd94  mov     [rdi], eax
0x18003dd96  cmp     [rbx], r14d
0x18003dd99  jnb     short loc_18003DDA6
0x18003dd9b  mov     edx, r14d
0x18003dd9e  mov     rcx, rbx
0x18003dda1  call    FillBitCache
0x18003dda6  add     [rbx], r15d
0x18003dda9  mov     eax, [rbx+4]
0x18003ddac  mov     ecx, [rbx]
0x18003ddae  shr     eax, cl
0x18003ddb0  and     eax, r14d
0x18003ddb3  mov     [rdi+4], eax
0x18003ddb6  jz      short loc_18003DDDB
0x18003ddb8  mov     edx, 0Eh
0x18003ddbd  cmp     [rbx], edx
0x18003ddbf  jnb     short loc_18003DDC9
0x18003ddc1  mov     rcx, rbx
0x18003ddc4  call    FillBitCache
0x18003ddc9  add     dword ptr [rbx], 0FFFFFFF2h
0x18003ddcc  mov     eax, [rbx+4]
0x18003ddcf  mov     ecx, [rbx]
0x18003ddd1  shr     eax, cl
0x18003ddd3  and     eax, 3FFFh
0x18003ddd8  mov     [rdi+8], eax
0x18003dddb  cmp     [rbx], r14d
0x18003ddde  jnb     short loc_18003DDEB
0x18003dde0  mov     edx, r14d
0x18003dde3  mov     rcx, rbx
0x18003dde6  call    FillBitCache
0x18003ddeb  add     [rbx], r15d
0x18003ddee  mov     eax, [rbx+4]
0x18003ddf1  mov     ecx, [rbx]
0x18003ddf3  shr     eax, cl
0x18003ddf5  and     eax, r14d
0x18003ddf8  mov     [rdi+0Ch], eax
0x18003ddfb  test    ebp, ebp
0x18003ddfd  jnz     short loc_18003DE0B
0x18003ddff  lea     rcx, [rdi+2Ch]
0x18003de03  mov     rdx, rbx
0x18003de06  call    CProgramCfg_Read
0x18003de0b  cmp     esi, 6
0x18003de0e  jz      short loc_18003DE15
0x18003de10  cmp     esi, 14h
0x18003de13  jnz     short loc_18003DE36
0x18003de15  mov     edx, 3
0x18003de1a  cmp     [rbx], edx
0x18003de1c  jnb     short loc_18003DE26
0x18003de1e  mov     rcx, rbx
0x18003de21  call    FillBitCache
0x18003de26  add     dword ptr [rbx], 0FFFFFFFDh
0x18003de29  mov     eax, [rbx+4]
0x18003de2c  mov     ecx, [rbx]
0x18003de2e  shr     eax, cl
0x18003de30  and     eax, 7
0x18003de33  mov     [rdi+14h], eax
0x18003de36  cmp     dword ptr [rdi+0Ch], 0
0x18003de3a  jz      loc_18003DF21
0x18003de40  cmp     esi, 16h
0x18003de43  jnz     short loc_18003DE89
0x18003de45  lea     edx, [rsi-11h]
0x18003de48  cmp     [rbx], edx
0x18003de4a  jnb     short loc_18003DE54
0x18003de4c  mov     rcx, rbx
0x18003de4f  call    FillBitCache
0x18003de54  add     dword ptr [rbx], 0FFFFFFFBh
0x18003de57  mov     edx, 0Bh
0x18003de5c  mov     eax, [rbx+4]
0x18003de5f  mov     ecx, [rbx]
0x18003de61  shr     eax, cl
0x18003de63  and     eax, 1Fh
0x18003de66  mov     [rdi+18h], eax
0x18003de69  cmp     [rbx], edx
0x18003de6b  jnb     short loc_18003DE75
0x18003de6d  mov     rcx, rbx
0x18003de70  call    FillBitCache
0x18003de75  add     dword ptr [rbx], 0FFFFFFF5h
0x18003de78  mov     eax, [rbx+4]
0x18003de7b  mov     ecx, [rbx]
0x18003de7d  shr     eax, cl
0x18003de7f  and     eax, 7FFh
0x18003de84  mov     [rdi+1Ch], eax
0x18003de87  jmp     short loc_18003DEF8
0x18003de89  cmp     esi, 17h
0x18003de8c  ja      short loc_18003DEF8
0x18003de8e  mov     eax, 9A0000h
0x18003de93  bt      eax, esi
0x18003de96  jnb     short loc_18003DEF8
0x18003de98  cmp     [rbx], r14d
0x18003de9b  jnb     short loc_18003DEA8
0x18003de9d  mov     edx, r14d
0x18003dea0  mov     rcx, rbx
0x18003dea3  call    FillBitCache
0x18003dea8  add     [rbx], r15d
0x18003deab  mov     eax, [rbx+4]
0x18003deae  mov     ecx, [rbx]
0x18003deb0  shr     eax, cl
0x18003deb2  and     eax, r14d
0x18003deb5  mov     [rdi+20h], eax
0x18003deb8  cmp     [rbx], r14d
0x18003debb  jnb     short loc_18003DEC8
0x18003debd  mov     edx, r14d
0x18003dec0  mov     rcx, rbx
0x18003dec3  call    FillBitCache
0x18003dec8  add     [rbx], r15d
0x18003decb  mov     eax, [rbx+4]
0x18003dece  mov     ecx, [rbx]
0x18003ded0  shr     eax, cl
0x18003ded2  and     eax, r14d
0x18003ded5  mov     [rdi+24h], eax
0x18003ded8  cmp     [rbx], r14d
0x18003dedb  jnb     short loc_18003DEE8
0x18003dedd  mov     edx, r14d
0x18003dee0  mov     rcx, rbx
0x18003dee3  call    FillBitCache
0x18003dee8  add     [rbx], r15d
0x18003deeb  mov     eax, [rbx+4]
0x18003deee  mov     ecx, [rbx]
0x18003def0  shr     eax, cl
0x18003def2  and     eax, r14d
0x18003def5  mov     [rdi+28h], eax
0x18003def8  cmp     [rbx], r14d
0x18003defb  jnb     short loc_18003DF08
0x18003defd  mov     edx, r14d
0x18003df00  mov     rcx, rbx
0x18003df03  call    FillBitCache
0x18003df08  add     [rbx], r15d
0x18003df0b  mov     eax, [rbx+4]
0x18003df0e  mov     ecx, [rbx]
0x18003df10  shr     eax, cl
0x18003df12  and     eax, r14d
0x18003df15  mov     [rdi+10h], eax
0x18003df18  neg     eax
0x18003df1a  sbb     eax, eax
0x18003df1c  and     eax, 0FFFFFFF3h
0x18003df1f  jmp     short loc_18003DF23
0x18003df21  xor     eax, eax
0x18003df23  add     rsp, 28h
0x18003df27  pop     r15
0x18003df29  pop     r14
0x18003df2b  pop     rdi
0x18003df2c  pop     rsi
0x18003df2d  pop     rbp
0x18003df2e  pop     rbx
0x18003df2f  retn
```
