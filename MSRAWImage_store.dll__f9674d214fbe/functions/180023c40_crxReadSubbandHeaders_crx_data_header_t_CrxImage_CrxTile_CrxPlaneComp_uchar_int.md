# crxReadSubbandHeaders(crx_data_header_t *,CrxImage *,CrxTile *,CrxPlaneComp *,uchar * *,int *)

- ea: `0x180023c40`
- end: `0x180023e7c`
- name: `?crxReadSubbandHeaders@@YAHPEAUcrx_data_header_t@@PEAUCrxImage@@PEAUCrxTile@@PEAUCrxPlaneComp@@PEAPEAEPEAH@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct crx_data_header_t *, struct CrxImage *, struct CrxTile *, struct CrxPlaneComp *, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022ba0`

## callees

- `0x180023c40`

## pseudocode

```c
__int64 __fastcall crxReadSubbandHeaders(
        struct crx_data_header_t *a1,
        struct CrxImage *a2,
        struct CrxTile *a3,
        struct CrxPlaneComp *a4,
        unsigned __int8 **a5,
        int *a6)
{
  __int64 v7; // rax
  int v8; // ebp
  int v9; // edi
  unsigned __int8 *v10; // rdx
  int v11; // r8d
  int v12; // r10d
  bool v13; // zf
  int v14; // r9d
  unsigned __int8 *v15; // r11
  int v16; // ecx
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // edx

  if ( !*((_BYTE *)a2 + 8) )
    return 0;
  v7 = *((_QWORD *)a4 + 1);
  v8 = 0;
  v9 = 0;
  while ( *a6 >= 4 )
  {
    v10 = *a5;
    v11 = (**a5 << 8) | (*a5)[1];
    v12 = (*a5)[3] | ((*a5)[2] << 8);
    if ( *a6 < v12 + 4 )
      break;
    if ( v11 == 65283 )
    {
      v13 = v12 == 8;
    }
    else
    {
      if ( v11 != 65299 )
        return 0xFFFFFFFFLL;
      v13 = v12 == 16;
    }
    if ( !v13 )
      break;
    v14 = v10[7] | ((v10[6] | ((v10[5] | (v10[4] << 8)) << 8)) << 8);
    if ( v9 != v10[8] >> 4 )
    {
      *(_QWORD *)(v7 + 56) = v14;
      return 0xFFFFFFFFLL;
    }
    *(_DWORD *)(v7 + 32) = 0;
    *(_QWORD *)v7 = 0;
    *(_QWORD *)(v7 + 16) = 0;
    *(_DWORD *)(v7 + 48) = 0;
    *(_QWORD *)(v7 + 64) = v8;
    v15 = *a5;
    v16 = (*a5)[9];
    v17 = (*a5)[8] << 8;
    if ( v11 == 65283 )
    {
      v18 = v15[11] | ((v15[10] | ((v17 | v16) << 8)) << 8);
      *(_DWORD *)(v7 + 36) = 0;
      v19 = 0;
      *(_QWORD *)(v7 + 56) = v14 - (v18 & 0x7FFFF);
      *(_BYTE *)(v7 + 44) = (v18 & 0x8000000) != 0;
      *(_DWORD *)(v7 + 28) = (unsigned __int8)(v18 >> 19);
    }
    else
    {
      if ( (((unsigned __int16)v17 | (unsigned __int16)v16) & 0xFFF) != 0 || (v15[18] << 8) | v15[19] )
        return 0xFFFFFFFFLL;
      *(_BYTE *)(v7 + 44) = 0;
      *(_DWORD *)(v7 + 28) = 0;
      *(_QWORD *)(v7 + 56) = v14 - (((*a5)[16] << 8) | (unsigned int)(*a5)[17]);
      *(_DWORD *)(v7 + 36) = (*a5)[15] | (((*a5)[14] | ((((*a5)[12] << 8) | (*a5)[13]) << 8)) << 8);
      v19 = ((*a5)[10] << 8) | (*a5)[11];
    }
    *(_DWORD *)(v7 + 40) = v19;
    v8 += v14;
    ++v9;
    *a5 += (unsigned int)(v12 + 4);
    v7 += 88;
    *a6 += -4 - v12;
    if ( v9 >= *((unsigned __int8 *)a2 + 8) )
      return 0;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180023c40  mov     [rsp+arg_0], rbx
0x180023c45  mov     [rsp+arg_8], rbp
0x180023c4a  mov     [rsp+arg_10], rsi
0x180023c4f  mov     [rsp+arg_18], rdi
0x180023c54  push    r12
0x180023c56  push    r14
0x180023c58  push    r15
0x180023c5a  movzx   ecx, byte ptr [rdx+8]
0x180023c5e  mov     r15, rdx
0x180023c61  test    cl, cl
0x180023c63  jz      loc_180023E51
0x180023c69  mov     rax, [r9+8]
0x180023c6d  xor     r12d, r12d
0x180023c70  mov     ebp, r12d
0x180023c73  mov     edi, r12d
0x180023c76  test    cl, cl
0x180023c78  jz      loc_180023E51
0x180023c7e  mov     rsi, [rsp+18h+arg_28]
0x180023c83  mov     rbx, [rsp+18h+arg_20]
0x180023c88  nop     dword ptr [rax+rax+00000000h]
0x180023c90  mov     r9d, [rsi]
0x180023c93  cmp     r9d, 4
0x180023c97  jl      loc_180023E75
0x180023c9d  mov     rdx, [rbx]
0x180023ca0  movzx   ecx, byte ptr [rdx]
0x180023ca3  movzx   r8d, byte ptr [rdx+1]
0x180023ca8  movzx   r10d, byte ptr [rdx+2]
0x180023cad  shl     ecx, 8
0x180023cb0  or      r8d, ecx
0x180023cb3  shl     r10d, 8
0x180023cb7  movzx   ecx, byte ptr [rdx+3]
0x180023cbb  or      r10d, ecx
0x180023cbe  lea     r14d, [r10+4]
0x180023cc2  cmp     r9d, r14d
0x180023cc5  jl      loc_180023E75
0x180023ccb  cmp     r8d, 0FF03h
0x180023cd2  jnz     short loc_180023CDA
0x180023cd4  cmp     r10d, 8
0x180023cd8  jmp     short loc_180023CEB
0x180023cda  cmp     r8d, 0FF13h
0x180023ce1  jnz     loc_180023E75
0x180023ce7  cmp     r10d, 10h
0x180023ceb  jnz     loc_180023E75
0x180023cf1  movzx   ecx, byte ptr [rdx+5]
0x180023cf5  movzx   r9d, byte ptr [rdx+4]
0x180023cfa  shl     r9d, 8
0x180023cfe  or      r9d, ecx
0x180023d01  movzx   ecx, byte ptr [rdx+6]
0x180023d05  shl     r9d, 8
0x180023d09  or      r9d, ecx
0x180023d0c  movzx   ecx, byte ptr [rdx+7]
0x180023d10  shl     r9d, 8
0x180023d14  or      r9d, ecx
0x180023d17  movzx   ecx, byte ptr [rdx+8]
0x180023d1b  shr     ecx, 4
0x180023d1e  cmp     edi, ecx
0x180023d20  jnz     loc_180023E6E
0x180023d26  mov     [rax+20h], r12d
0x180023d2a  mov     [rax], r12
0x180023d2d  mov     [rax+10h], r12
0x180023d31  mov     [rax+30h], r12d
0x180023d35  movsxd  rcx, ebp
0x180023d38  mov     [rax+40h], rcx
0x180023d3c  mov     r11, [rbx]
0x180023d3f  movzx   edx, byte ptr [r11+8]
0x180023d44  movzx   ecx, byte ptr [r11+9]
0x180023d49  shl     edx, 8
0x180023d4c  cmp     r8d, 0FF03h
0x180023d53  jnz     short loc_180023DA8
0x180023d55  mov     r8d, ecx
0x180023d58  movzx   ecx, byte ptr [r11+0Ah]
0x180023d5d  or      r8d, edx
0x180023d60  shl     r8d, 8
0x180023d64  or      r8d, ecx
0x180023d67  movzx   ecx, byte ptr [r11+0Bh]
0x180023d6c  shl     r8d, 8
0x180023d70  or      r8d, ecx
0x180023d73  mov     [rax+24h], r12d
0x180023d77  mov     edx, r8d
0x180023d7a  mov     ecx, r9d
0x180023d7d  and     edx, 7FFFFh
0x180023d83  sub     ecx, edx
0x180023d85  mov     edx, r12d
0x180023d88  mov     [rax+38h], rcx
0x180023d8c  mov     ecx, r8d
0x180023d8f  shr     ecx, 1Bh
0x180023d92  and     cl, 1
0x180023d95  shr     r8d, 13h
0x180023d99  mov     [rax+2Ch], cl
0x180023d9c  movzx   ecx, r8b
0x180023da0  mov     [rax+1Ch], ecx
0x180023da3  jmp     loc_180023E28
0x180023da8  or      ecx, edx
0x180023daa  test    ecx, 0FFFh
0x180023db0  jnz     loc_180023E75
0x180023db6  movzx   ecx, byte ptr [r11+12h]
0x180023dbb  movzx   edx, byte ptr [r11+13h]
0x180023dc0  shl     ecx, 8
0x180023dc3  or      edx, ecx
0x180023dc5  jnz     loc_180023E75
0x180023dcb  mov     [rax+2Ch], r12b
0x180023dcf  mov     [rax+1Ch], r12d
0x180023dd3  mov     rcx, [rbx]
0x180023dd6  movzx   edx, byte ptr [rcx+11h]
0x180023dda  movzx   ecx, byte ptr [rcx+10h]
0x180023dde  shl     ecx, 8
0x180023de1  or      edx, ecx
0x180023de3  mov     ecx, r9d
0x180023de6  sub     ecx, edx
0x180023de8  mov     [rax+38h], rcx
0x180023dec  mov     rdx, [rbx]
0x180023def  movzx   ecx, byte ptr [rdx+0Ch]
0x180023df3  movzx   r8d, byte ptr [rdx+0Dh]
0x180023df8  shl     ecx, 8
0x180023dfb  or      r8d, ecx
0x180023dfe  movzx   ecx, byte ptr [rdx+0Eh]
0x180023e02  shl     r8d, 8
0x180023e06  or      r8d, ecx
0x180023e09  movzx   ecx, byte ptr [rdx+0Fh]
0x180023e0d  shl     r8d, 8
0x180023e11  or      r8d, ecx
0x180023e14  mov     [rax+24h], r8d
0x180023e18  mov     rcx, [rbx]
0x180023e1b  movzx   edx, byte ptr [rcx+0Bh]
0x180023e1f  movzx   ecx, byte ptr [rcx+0Ah]
0x180023e23  shl     ecx, 8
0x180023e26  or      edx, ecx
0x180023e28  mov     [rax+28h], edx
0x180023e2b  add     ebp, r9d
0x180023e2e  mov     ecx, r14d
0x180023e31  inc     edi
0x180023e33  add     [rbx], rcx
0x180023e36  add     rax, 58h ; 'X'
0x180023e3a  mov     ecx, 0FFFFFFFCh
0x180023e3f  sub     ecx, r10d
0x180023e42  add     [rsi], ecx
0x180023e44  movzx   ecx, byte ptr [r15+8]
0x180023e49  cmp     edi, ecx
0x180023e4b  jl      loc_180023C90
0x180023e51  xor     eax, eax
0x180023e53  mov     rbx, [rsp+18h+arg_0]
0x180023e58  mov     rbp, [rsp+18h+arg_8]
0x180023e5d  mov     rsi, [rsp+18h+arg_10]
0x180023e62  mov     rdi, [rsp+18h+arg_18]
0x180023e67  pop     r15
0x180023e69  pop     r14
0x180023e6b  pop     r12
0x180023e6d  retn
0x180023e6e  movsxd  rcx, r9d
0x180023e71  mov     [rax+38h], rcx
0x180023e75  mov     eax, 0FFFFFFFFh
0x180023e7a  jmp     short loc_180023E53
```
