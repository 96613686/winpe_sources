# CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::RemoveValue(ulong)

- ea: `0x180020cb0`
- end: `0x180020e29`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020b30`

## callees

- `0x180020cb0`
- `0x180021764`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  char j; // r11
  unsigned __int8 v16; // si

  for ( i = a1; i; i = *(_QWORD *)(i + 192) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 200);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 208);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 208) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 24)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::SetValue(
               a1,
               v9 - 1,
               *(_QWORD *)(i + 32));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 8 * (v11 + 4LL)), (const void *)(i + 8 * (v11 + 1 + 4LL)), 8LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 24); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 24) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 24) < 0 )
        *(_BYTE *)(v13 + i + 24) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A248 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::s_bLeftBitMasks
                                + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 192) == *(_QWORD *)(a1 + 200) )
    {
      *(_QWORD *)(a1 + 200) = i;
      *(_DWORD *)(a1 + 208) = 19;
    }
    i = *(_QWORD *)(i + 192);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020cb0  push    rbx
0x180020cb2  push    rbp
0x180020cb3  push    rsi
0x180020cb4  push    rdi
0x180020cb5  push    r12
0x180020cb7  push    r14
0x180020cb9  push    r15
0x180020cbb  sub     rsp, 20h
0x180020cbf  mov     ebp, edx
0x180020cc1  mov     rdi, rcx
0x180020cc4  mov     rbx, rcx
0x180020cc7  test    rcx, rcx
0x180020cca  jz      short loc_180020CE2
0x180020ccc  mov     eax, [rbx+8]
0x180020ccf  add     eax, 14h
0x180020cd2  cmp     ebp, eax
0x180020cd4  jb      short loc_180020CE2
0x180020cd6  mov     rbx, [rbx+0C0h]
0x180020cdd  test    rbx, rbx
0x180020ce0  jnz     short loc_180020CCC
0x180020ce2  mov     rax, [rcx+0C8h]
0x180020ce9  xor     r12d, r12d
0x180020cec  test    rax, rax
0x180020cef  jz      short loc_180020D13
0x180020cf1  mov     edx, [rcx+0D0h]
0x180020cf7  mov     ecx, [rax+8]
0x180020cfa  add     ecx, edx
0x180020cfc  cmp     ebp, ecx
0x180020cfe  jnb     short loc_180020D13
0x180020d00  test    edx, edx
0x180020d02  jnz     short loc_180020D0A
0x180020d04  lea     r12d, [rdx+1]
0x180020d08  jmp     short loc_180020D13
0x180020d0a  lea     eax, [rdx-1]
0x180020d0d  mov     [rdi+0D0h], eax
0x180020d13  xor     r14d, r14d
0x180020d16  jmp     loc_180020E0E
0x180020d1b  mov     edx, [rbx+8]
0x180020d1e  cmp     ebp, edx
0x180020d20  jb      short loc_180020D2E
0x180020d22  mov     esi, ebp
0x180020d24  mov     r15d, 1
0x180020d2a  sub     esi, edx
0x180020d2c  jmp     short loc_180020D57
0x180020d2e  mov     al, [rbx+18h]
0x180020d31  xor     r15d, r15d
0x180020d34  xor     esi, esi
0x180020d36  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::s_bSingleBitMasks
0x180020d3c  jz      short loc_180020D57
0x180020d3e  mov     r8, [rbx+20h]
0x180020d42  dec     edx
0x180020d44  mov     rcx, rdi
0x180020d47  call    ?SetValue@?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@QEAAJKPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::SetValue(ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *)
0x180020d4c  mov     r14d, eax
0x180020d4f  test    eax, eax
0x180020d51  js      loc_180020E17
0x180020d57  mov     r8d, 13h
0x180020d5d  mov     ecx, esi
0x180020d5f  add     rcx, 4
0x180020d63  lea     edx, [rsi+1]
0x180020d66  sub     r8d, esi
0x180020d69  lea     rdx, [rdx+4]
0x180020d6d  shl     r8, 3; Size
0x180020d71  lea     rdx, [rbx+rdx*8]; Src
0x180020d75  lea     rcx, [rbx+rcx*8]; void *
0x180020d79  call    memmove_0
0x180020d7e  mov     eax, esi
0x180020d80  shr     eax, 3
0x180020d83  mov     edx, eax
0x180020d85  lea     r10, [rax+rbx]
0x180020d89  mov     r11b, [r10+18h]
0x180020d8d  cmp     eax, 3
0x180020d90  jnb     short loc_180020DB1
0x180020d92  shl     byte ptr [rdx+rbx+18h], 1
0x180020d96  cmp     edx, 2
0x180020d99  jnb     short loc_180020DAA
0x180020d9b  lea     eax, [rdx+1]
0x180020d9e  cmp     byte ptr [rax+rbx+18h], 0
0x180020da3  jge     short loc_180020DAA
0x180020da5  or      byte ptr [rdx+rbx+18h], 1
0x180020daa  inc     edx
0x180020dac  cmp     edx, 3
0x180020daf  jb      short loc_180020D92
0x180020db1  test    r15d, r15d
0x180020db4  jz      short loc_180020DE1
0x180020db6  and     sil, 7
0x180020dba  jbe     short loc_180020DE1
0x180020dbc  movzx   ecx, sil
0x180020dc0  lea     rax, qword_18004A248
0x180020dc7  sub     rax, rcx
0x180020dca  mov     al, [rax]
0x180020dcc  and     [r10+18h], al
0x180020dd0  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::s_bLeftBitMasks
0x180020dd7  mov     al, [rcx+rax]
0x180020dda  and     al, r11b
0x180020ddd  or      [r10+18h], al
0x180020de1  test    r12d, r12d
0x180020de4  jz      short loc_180020E07
0x180020de6  mov     rax, [rdi+0C8h]
0x180020ded  cmp     [rbx+0C0h], rax
0x180020df4  jnz     short loc_180020E07
0x180020df6  mov     [rdi+0C8h], rbx
0x180020dfd  mov     dword ptr [rdi+0D0h], 13h
0x180020e07  mov     rbx, [rbx+0C0h]
0x180020e0e  test    rbx, rbx
0x180020e11  jnz     loc_180020D1B
0x180020e17  mov     eax, r14d
0x180020e1a  add     rsp, 20h
0x180020e1e  pop     r15
0x180020e20  pop     r14
0x180020e22  pop     r12
0x180020e24  pop     rdi
0x180020e25  pop     rsi
0x180020e26  pop     rbp
0x180020e27  pop     rbx
0x180020e28  retn
```
