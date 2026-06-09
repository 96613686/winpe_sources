# PCreateFeatureItem

- ea: `0x18005cd68`
- end: `0x18005cf42`
- name: `PCreateFeatureItem`
- size: `474`
- prototype: `_QWORD *__fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18005a990`
- `0x18005aa20`
- `0x18005aa50`
- `0x18005b334`
- `0x18005bb50`
- `0x18005d0e0`

## callees

- `0x18005c1b4`
- `0x18005cd68`
- `0x18005d030`

## pseudocode

```c
_QWORD *__fastcall PCreateFeatureItem(__int64 a1, int a2)
{
  int v2; // r8d
  char v5; // al
  char v6; // cl
  char *v7; // rdx
  char *v8; // rcx
  signed __int64 v9; // r10
  int v10; // r9d
  int v11; // eax
  __int64 v12; // rbp
  _QWORD *ListItem; // rbx
  __int128 v14; // xmm6
  __int64 v15; // rax
  int v16; // eax

  v2 = 0;
  if ( a2 == 0xFFFF )
  {
    v5 = *(_BYTE *)(a1 + 692);
    if ( v5 == 42 )
      v6 = *(_BYTE *)(a1 + 693);
    else
      v6 = *(_BYTE *)(a1 + 692);
    v7 = (char *)((a1 + 693LL - (v5 != 42)) & -(__int64)(v6 != 0));
    if ( !v7 )
      return 0;
    if ( off_1800740A0 )
    {
      do
      {
        v8 = (&off_1800740A0)[2 * v2];
        v9 = v7 - v8;
        do
        {
          v10 = (unsigned __int8)v8[v9];
          v11 = (unsigned __int8)*v8 - v10;
          if ( v11 )
            break;
          ++v8;
        }
        while ( v10 );
        if ( !v11 )
          break;
        ++v2;
      }
      while ( (&off_1800740A0)[2 * v2] );
    }
    if ( (&off_1800740A0)[2 * v2] )
      *(_BYTE *)(LODWORD((&off_1800740A0)[2 * v2 + 1]) + a1 + 540) = 1;
  }
  else
  {
    if ( off_1800740A0 )
    {
      do
      {
        if ( a2 == LODWORD((&off_1800740A0)[2 * v2 + 1]) )
          break;
        ++v2;
      }
      while ( (&off_1800740A0)[2 * v2] );
    }
    v7 = (&off_1800740A0)[2 * v2];
    if ( !v7 )
      return 0;
  }
  v12 = 2LL * v2;
  if ( LODWORD((&off_1800740A0)[2 * v2 + 1]) == 0xFFFF || (ListItem = *(_QWORD **)(a1 + 152)) == 0 )
  {
LABEL_22:
    v14 = *(_OWORD *)(a1 + 576);
    *(_QWORD *)(a1 + 584) = v7;
    v15 = -1;
    do
      ++v15;
    while ( v7[v15] );
    *(_DWORD *)(a1 + 580) = v15;
    ListItem = PvCreateListItem(a1, (_QWORD *)(a1 + 152), 0x60u);
    *(_OWORD *)(a1 + 576) = v14;
    if ( !ListItem )
      return ListItem;
  }
  else
  {
    while ( *((_DWORD *)ListItem + 12) != LODWORD((&off_1800740A0)[2 * v2 + 1]) )
    {
      ListItem = (_QWORD *)*ListItem;
      if ( !ListItem )
        goto LABEL_22;
    }
  }
  if ( a2 != 0xFFFF
    || !*(_DWORD *)(a1 + 596)
    || ListItem[4]
    || !(unsigned int)IParseXlation(a1, (__int64)(ListItem + 3)) )
  {
    if ( !*((_DWORD *)ListItem + 21) )
    {
      *((_DWORD *)ListItem + 21) = *((_DWORD *)&off_1800740A0 + 2 * v12 + 3);
      v16 = (int)(&off_1800740A0)[v12 + 1];
      *((_DWORD *)ListItem + 12) = v16;
      if ( v16 == 6 || v16 == 0xFFFF && *(_DWORD *)(a1 + 60) )
        *((_DWORD *)ListItem + 13) = 1;
    }
    return ListItem;
  }
  return 0;
}

```

## disassembly

```asm
0x18005cd68  push    rbx
0x18005cd6a  push    rbp
0x18005cd6b  push    rsi
0x18005cd6c  push    rdi
0x18005cd6d  push    r12
0x18005cd6f  push    r14
0x18005cd71  sub     rsp, 38h
0x18005cd75  xor     r8d, r8d
0x18005cd78  movaps  [rsp+68h+var_48], xmm6
0x18005cd7d  mov     r12d, 0FFFFh
0x18005cd83  mov     r14d, edx
0x18005cd86  mov     rsi, rcx
0x18005cd89  cmp     edx, r12d
0x18005cd8c  jnz     loc_18005CE28
0x18005cd92  mov     al, [rcx+2B4h]
0x18005cd98  cmp     al, 2Ah ; '*'
0x18005cd9a  jnz     short loc_18005CDA4
0x18005cd9c  mov     cl, [rcx+2B5h]
0x18005cda2  jmp     short loc_18005CDA6
0x18005cda4  mov     cl, al
0x18005cda6  sub     al, 2Ah ; '*'
0x18005cda8  neg     al
0x18005cdaa  sbb     rax, rax
0x18005cdad  add     rax, 2B5h
0x18005cdb3  add     rax, rsi
0x18005cdb6  neg     cl
0x18005cdb8  sbb     rdx, rdx
0x18005cdbb  and     rdx, rax
0x18005cdbe  jz      loc_18005CF2D
0x18005cdc4  cmp     cs:off_1800740A0, r8; "PageSize"
0x18005cdcb  lea     rdi, off_1800740A0; "PageSize"
0x18005cdd2  jz      short loc_18005CE0D
0x18005cdd4  movsxd  rax, r8d
0x18005cdd7  mov     r10, rdx
0x18005cdda  add     rax, rax
0x18005cddd  mov     rcx, [rdi+rax*8]
0x18005cde1  sub     r10, rcx
0x18005cde4  movzx   eax, byte ptr [rcx]
0x18005cde7  movzx   r9d, byte ptr [rcx+r10]
0x18005cdec  sub     eax, r9d
0x18005cdef  jnz     short loc_18005CDF9
0x18005cdf1  inc     rcx
0x18005cdf4  test    r9d, r9d
0x18005cdf7  jnz     short loc_18005CDE4
0x18005cdf9  test    eax, eax
0x18005cdfb  jz      short loc_18005CE0D
0x18005cdfd  inc     r8d
0x18005ce00  movsxd  rax, r8d
0x18005ce03  add     rax, rax
0x18005ce06  cmp     qword ptr [rdi+rax*8], 0
0x18005ce0b  jnz     short loc_18005CDD4
0x18005ce0d  movsxd  rax, r8d
0x18005ce10  add     rax, rax
0x18005ce13  cmp     qword ptr [rdi+rax*8], 0
0x18005ce18  jz      short loc_18005CE68
0x18005ce1a  mov     eax, [rdi+rax*8+8]
0x18005ce1e  mov     byte ptr [rax+rsi+21Ch], 1
0x18005ce26  jmp     short loc_18005CE68
0x18005ce28  cmp     cs:off_1800740A0, r8; "PageSize"
0x18005ce2f  lea     rdi, off_1800740A0; "PageSize"
0x18005ce36  jz      short loc_18005CE55
0x18005ce38  movsxd  rax, r8d
0x18005ce3b  add     rax, rax
0x18005ce3e  cmp     r14d, [rdi+rax*8+8]
0x18005ce43  jz      short loc_18005CE55
0x18005ce45  inc     r8d
0x18005ce48  movsxd  rax, r8d
0x18005ce4b  add     rax, rax
0x18005ce4e  cmp     qword ptr [rdi+rax*8], 0
0x18005ce53  jnz     short loc_18005CE38
0x18005ce55  movsxd  rax, r8d
0x18005ce58  add     rax, rax
0x18005ce5b  mov     rdx, [rdi+rax*8]
0x18005ce5f  test    rdx, rdx
0x18005ce62  jz      loc_18005CF2D
0x18005ce68  movsxd  rbp, r8d
0x18005ce6b  add     rbp, rbp
0x18005ce6e  cmp     [rdi+rbp*8+8], r12d
0x18005ce73  jz      short loc_18005CE92
0x18005ce75  mov     rbx, [rsi+98h]
0x18005ce7c  test    rbx, rbx
0x18005ce7f  jz      short loc_18005CE92
0x18005ce81  mov     eax, [rdi+rbp*8+8]
0x18005ce85  cmp     [rbx+30h], eax
0x18005ce88  jz      short loc_18005CED8
0x18005ce8a  mov     rbx, [rbx]
0x18005ce8d  test    rbx, rbx
0x18005ce90  jnz     short loc_18005CE85
0x18005ce92  movups  xmm6, xmmword ptr [rsi+240h]
0x18005ce99  mov     [rsi+248h], rdx
0x18005cea0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005cea4  inc     rax
0x18005cea7  cmp     byte ptr [rdx+rax], 0
0x18005ceab  jnz     short loc_18005CEA4
0x18005cead  lea     rdx, [rsi+98h]
0x18005ceb4  mov     [rsi+244h], eax
0x18005ceba  mov     r8d, 60h ; '`'
0x18005cec0  mov     rcx, rsi
0x18005cec3  call    PvCreateListItem
0x18005cec8  mov     rbx, rax
0x18005cecb  movdqu  xmmword ptr [rsi+240h], xmm6
0x18005ced3  test    rax, rax
0x18005ced6  jz      short loc_18005CF28
0x18005ced8  cmp     r14d, r12d
0x18005cedb  jnz     short loc_18005CEFD
0x18005cedd  cmp     dword ptr [rsi+254h], 0
0x18005cee4  jz      short loc_18005CEFD
0x18005cee6  cmp     qword ptr [rbx+20h], 0
0x18005ceeb  jnz     short loc_18005CEFD
0x18005ceed  lea     rdx, [rbx+18h]
0x18005cef1  mov     rcx, rsi
0x18005cef4  call    IParseXlation
0x18005cef9  test    eax, eax
0x18005cefb  jnz     short loc_18005CF2D
0x18005cefd  cmp     dword ptr [rbx+54h], 0
0x18005cf01  jnz     short loc_18005CF28
0x18005cf03  mov     eax, [rdi+rbp*8+0Ch]
0x18005cf07  mov     [rbx+54h], eax
0x18005cf0a  mov     eax, [rdi+rbp*8+8]
0x18005cf0e  mov     [rbx+30h], eax
0x18005cf11  cmp     eax, 6
0x18005cf14  jz      short loc_18005CF21
0x18005cf16  cmp     eax, r12d
0x18005cf19  jnz     short loc_18005CF28
0x18005cf1b  cmp     dword ptr [rsi+3Ch], 0
0x18005cf1f  jz      short loc_18005CF28
0x18005cf21  mov     dword ptr [rbx+34h], 1
0x18005cf28  mov     rax, rbx
0x18005cf2b  jmp     short loc_18005CF2F
0x18005cf2d  xor     eax, eax
0x18005cf2f  movaps  xmm6, [rsp+68h+var_48]
0x18005cf34  add     rsp, 38h
0x18005cf38  pop     r14
0x18005cf3a  pop     r12
0x18005cf3c  pop     rdi
0x18005cf3d  pop     rsi
0x18005cf3e  pop     rbp
0x18005cf3f  pop     rbx
0x18005cf40  retn
```
