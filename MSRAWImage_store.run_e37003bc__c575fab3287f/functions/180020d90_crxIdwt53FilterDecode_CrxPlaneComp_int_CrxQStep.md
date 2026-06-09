# crxIdwt53FilterDecode(CrxPlaneComp *,int,CrxQStep *)

- ea: `0x180020d90`
- end: `0x180020ea2`
- name: `?crxIdwt53FilterDecode@@YAHPEAUCrxPlaneComp@@HPEAUCrxQStep@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct CrxPlaneComp *, int, struct CrxQStep *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020d90`
- `0x180020eb0`
- `0x180021a40`

## callees

- `0x18001c700`
- `0x180020d90`

## pseudocode

```c
__int64 __fastcall crxIdwt53FilterDecode(struct CrxPlaneComp *a1, int a2, struct CrxQStep *a3)
{
  __int16 *v3; // r11
  __int64 v5; // rdi
  struct CrxQStep *v6; // rbx
  int v7; // r9d
  int v8; // eax
  int v9; // eax

  v3 = (__int16 *)(*((_QWORD *)a1 + 2) + 112LL * a2);
  if ( v3[49] )
    return 0;
  v5 = *((_QWORD *)a1 + 1) + 264LL * a2;
  if ( a3 )
    v6 = (struct CrxQStep *)((char *)a3 + 16 * a2);
  else
    v6 = 0;
  v7 = v3[51];
  if ( v7 - 3 > v3[48] || (*((_BYTE *)a1 + 52) & 4) != 0 )
  {
    if ( a2 )
      v9 = crxIdwt53FilterDecode(a1, a2 - 1, a3);
    else
      v9 = crxDecodeLineWithIQuantization((struct CrxSubband *)v5, v6);
    if ( !v9
      && !(unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v5 + 88), v6)
      && !(unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v5 + 176), v6) )
    {
      return (unsigned int)-((unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v5 + 264), v6) != 0);
    }
  }
  else
  {
    if ( (v7 & 1) == 0 )
      return 0;
    v8 = a2 ? crxIdwt53FilterDecode(a1, a2 - 1, a3) : crxDecodeLineWithIQuantization((struct CrxSubband *)v5, v6);
    if ( !v8 && !(unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v5 + 88), v6) )
      return 0;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180020d90  push    rbx
0x180020d92  sub     rsp, 20h
0x180020d96  movsxd  rbx, edx
0x180020d99  mov     r10, rcx
0x180020d9c  imul    r11, rbx, 70h ; 'p'
0x180020da0  add     r11, [rcx+10h]
0x180020da4  cmp     word ptr [r11+62h], 0
0x180020daa  jz      short loc_180020DB4
0x180020dac  xor     eax, eax
0x180020dae  add     rsp, 20h
0x180020db2  pop     rbx
0x180020db3  retn
0x180020db4  mov     [rsp+28h+arg_0], rdi
0x180020db9  lea     eax, [rdx+rdx*2]
0x180020dbc  movsxd  rcx, eax
0x180020dbf  imul    rdi, rcx, 58h ; 'X'
0x180020dc3  add     rdi, [r10+8]
0x180020dc7  test    r8, r8
0x180020dca  jz      short loc_180020DD5
0x180020dcc  shl     rbx, 4
0x180020dd0  add     rbx, r8
0x180020dd3  jmp     short loc_180020DD7
0x180020dd5  xor     ebx, ebx
0x180020dd7  movsx   r9d, word ptr [r11+66h]
0x180020ddc  movsx   eax, word ptr [r11+60h]
0x180020de1  lea     ecx, [r9-3]
0x180020de5  cmp     ecx, eax
0x180020de7  jg      short loc_180020E32
0x180020de9  test    byte ptr [r10+34h], 4
0x180020dee  jnz     short loc_180020E32
0x180020df0  test    r9b, 1
0x180020df4  jz      short loc_180020E25
0x180020df6  test    edx, edx
0x180020df8  jz      short loc_180020E06
0x180020dfa  dec     edx; int
0x180020dfc  mov     rcx, r10; struct CrxPlaneComp *
0x180020dff  call    ?crxIdwt53FilterDecode@@YAHPEAUCrxPlaneComp@@HPEAUCrxQStep@@@Z; crxIdwt53FilterDecode(CrxPlaneComp *,int,CrxQStep *)
0x180020e04  jmp     short loc_180020E11
0x180020e06  mov     rdx, rbx; struct CrxQStep *
0x180020e09  mov     rcx, rdi; struct CrxSubband *
0x180020e0c  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e11  test    eax, eax
0x180020e13  jnz     short loc_180020E92
0x180020e15  lea     rcx, [rdi+58h]; struct CrxSubband *
0x180020e19  mov     rdx, rbx; struct CrxQStep *
0x180020e1c  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e21  test    eax, eax
0x180020e23  jnz     short loc_180020E92
0x180020e25  mov     rdi, [rsp+28h+arg_0]
0x180020e2a  xor     eax, eax
0x180020e2c  add     rsp, 20h
0x180020e30  pop     rbx
0x180020e31  retn
0x180020e32  test    edx, edx
0x180020e34  jz      short loc_180020E42
0x180020e36  dec     edx; int
0x180020e38  mov     rcx, r10; struct CrxPlaneComp *
0x180020e3b  call    ?crxIdwt53FilterDecode@@YAHPEAUCrxPlaneComp@@HPEAUCrxQStep@@@Z; crxIdwt53FilterDecode(CrxPlaneComp *,int,CrxQStep *)
0x180020e40  jmp     short loc_180020E4D
0x180020e42  mov     rdx, rbx; struct CrxQStep *
0x180020e45  mov     rcx, rdi; struct CrxSubband *
0x180020e48  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e4d  test    eax, eax
0x180020e4f  jnz     short loc_180020E92
0x180020e51  lea     rcx, [rdi+58h]; struct CrxSubband *
0x180020e55  mov     rdx, rbx; struct CrxQStep *
0x180020e58  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e5d  test    eax, eax
0x180020e5f  jnz     short loc_180020E92
0x180020e61  lea     rcx, [rdi+0B0h]; struct CrxSubband *
0x180020e68  mov     rdx, rbx; struct CrxQStep *
0x180020e6b  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e70  test    eax, eax
0x180020e72  jnz     short loc_180020E92
0x180020e74  lea     rcx, [rdi+108h]; struct CrxSubband *
0x180020e7b  mov     rdx, rbx; struct CrxQStep *
0x180020e7e  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020e83  mov     rdi, [rsp+28h+arg_0]
0x180020e88  neg     eax
0x180020e8a  sbb     eax, eax
0x180020e8c  add     rsp, 20h
0x180020e90  pop     rbx
0x180020e91  retn
0x180020e92  mov     rdi, [rsp+28h+arg_0]
0x180020e97  mov     eax, 0FFFFFFFFh
0x180020e9c  add     rsp, 20h
0x180020ea0  pop     rbx
0x180020ea1  retn
```
