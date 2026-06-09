# transportDec_AdjustEndOfAccessUnit

- ea: `0x18000a1a0`
- end: `0x18000a331`
- name: `transportDec_AdjustEndOfAccessUnit`
- size: `401`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a338`
- `0x1800113bc`
- `0x18003c338`

## callees

- `0x18000a1a0`
- `0x18000e9b0`
- `0x1800110c0`
- `0x18001115c`
- `0x180012264`
- `0x18002ce0c`

## pseudocode

```c
__int64 __fastcall transportDec_AdjustEndOfAccessUnit(__int64 a1, __int64 a2, __int64 a3)
{
  int *v4; // rsi
  unsigned int v5; // ebp
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 v10; // rdx
  int *v11; // rcx
  int v12; // ebx
  __int64 v13; // rdx

  v4 = (int *)(a1 + 136);
  v5 = 0;
  v6 = *(_DWORD *)a1 - 2;
  if ( v6 )
  {
    v7 = v6 - 4;
    if ( (!v7 || (v8 = v7 - 1) == 0 || v8 == 3) && !*(_DWORD *)(a1 + 3844) )
    {
      CDKbyteAlign_0(v4, *(unsigned int *)(a1 + 3832));
      if ( *(_DWORD *)a1 == 10 )
      {
        if ( *(_DWORD *)(a1 + 216) )
        {
          CDKsyncCache_0(v4);
          v10 = (unsigned int)(v4[2] + 8 * *(_DWORD *)(a1 + 216) - *(_DWORD *)(a1 + 3832));
          if ( (_DWORD)v10 )
          {
            v11 = v4;
            if ( (int)v10 < 0 )
            {
              CDKpushBack(v4, (unsigned int)(*(_DWORD *)(a1 + 3832) - (v4[2] + 8 * *(_DWORD *)(a1 + 216))));
              return 1025;
            }
            goto LABEL_14;
          }
        }
      }
    }
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 194) )
    {
      v12 = 8 * *(unsigned __int16 *)(a1 + 2LL * (*(unsigned __int8 *)(a1 + 208) - *(_DWORD *)(a1 + 3844)) + 298);
      CDKsyncCache_0(v4);
      v13 = v12 + v4[2] - (unsigned int)*(unsigned __int8 *)(a1 + 209) - *(_DWORD *)(a1 + 3836) - 16;
      if ( (int)v13 < 0 )
        CDKpushBack(v4, (unsigned int)-(int)v13);
      else
        CDKpushFor(v4, v13);
    }
    if ( *(_BYTE *)(a1 + 208) && !*(_BYTE *)(a1 + 194) )
      *(_WORD *)(a1 + 296) = CDKreadBits(v4, 16, a3);
    if ( !*(_DWORD *)(a1 + 3844) && !*(_BYTE *)(a1 + 194) )
    {
      CDKsyncCache_0(v4);
      v10 = 8 * (unsigned int)*(unsigned __int16 *)(a1 + 204) - *(_DWORD *)(a1 + 3832) + v4[2] - 12;
      if ( (_DWORD)v10 )
      {
        v11 = v4;
        if ( (int)v10 >= 0 )
        {
LABEL_14:
          CDKpushFor(v11, v10);
          return v5;
        }
        CDKpushBack(v4, (unsigned int)-(int)v10);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000a1a0  push    rbx
0x18000a1a2  push    rbp
0x18000a1a3  push    rsi
0x18000a1a4  push    rdi
0x18000a1a5  sub     rsp, 28h
0x18000a1a9  mov     rdi, rcx
0x18000a1ac  lea     rsi, [rcx+88h]
0x18000a1b3  mov     ecx, [rcx]
0x18000a1b5  xor     ebp, ebp
0x18000a1b7  sub     ecx, 2
0x18000a1ba  jz      short loc_18000A1E3
0x18000a1bc  sub     ecx, 4
0x18000a1bf  jz      loc_18000A29A
0x18000a1c5  sub     ecx, 1
0x18000a1c8  jz      loc_18000A29A
0x18000a1ce  cmp     ecx, 3
0x18000a1d1  jz      loc_18000A29A
0x18000a1d7  mov     eax, ebp
0x18000a1d9  add     rsp, 28h
0x18000a1dd  pop     rdi
0x18000a1de  pop     rsi
0x18000a1df  pop     rbp
0x18000a1e0  pop     rbx
0x18000a1e1  retn
0x18000a1e3  cmp     [rdi+0C2h], bpl
0x18000a1ea  jz      short loc_18000A24E
0x18000a1ec  cmp     [rdi+0D0h], bpl
0x18000a1f3  ja      loc_18000A30B
0x18000a1f9  cmp     [rdi+0F04h], ebp
0x18000a1ff  jnz     short loc_18000A1D7
0x18000a201  cmp     [rdi+0C2h], bpl
0x18000a208  jnz     short loc_18000A1D7
0x18000a20a  mov     rcx, rsi
0x18000a20d  call    CDKsyncCache_0
0x18000a212  movzx   ecx, word ptr [rdi+0CCh]
0x18000a219  mov     edx, [rsi+8]
0x18000a21c  shl     ecx, 3
0x18000a21f  add     edx, 0FFFFFFF4h
0x18000a222  sub     ecx, [rdi+0EF8h]
0x18000a228  add     edx, ecx
0x18000a22a  jz      short loc_18000A1D7
0x18000a22c  mov     rcx, rsi
0x18000a22f  test    edx, edx
0x18000a231  jns     short loc_18000A247
0x18000a233  neg     edx
0x18000a235  call    CDKpushBack
0x18000a23a  jmp     short loc_18000A1D7
0x18000a23c  mov     rcx, rsi
0x18000a23f  test    edx, edx
0x18000a241  js      loc_18000A2EE
0x18000a247  call    CDKpushFor
0x18000a24c  jmp     short loc_18000A1D7
0x18000a24e  movzx   eax, byte ptr [rdi+0D0h]
0x18000a255  sub     eax, [rdi+0F04h]
0x18000a25b  cdqe
0x18000a25d  movzx   ecx, word ptr [rdi+rax*2+12Ah]
0x18000a265  lea     ebx, ds:0[rcx*8]
0x18000a26c  mov     rcx, rsi
0x18000a26f  call    CDKsyncCache_0
0x18000a274  movzx   eax, byte ptr [rdi+0D1h]
0x18000a27b  mov     rcx, rsi
0x18000a27e  mov     edx, [rsi+8]
0x18000a281  sub     edx, eax
0x18000a283  sub     edx, [rdi+0EFCh]
0x18000a289  add     edx, 0FFFFFFF0h
0x18000a28c  add     edx, ebx
0x18000a28e  js      short loc_18000A2FF
0x18000a290  call    CDKpushFor
0x18000a295  jmp     loc_18000A1EC
0x18000a29a  cmp     [rdi+0F04h], ebp
0x18000a2a0  jnz     loc_18000A1D7
0x18000a2a6  mov     edx, [rdi+0EF8h]
0x18000a2ac  mov     rcx, rsi
0x18000a2af  call    CDKbyteAlign_0
0x18000a2b4  cmp     dword ptr [rdi], 0Ah
0x18000a2b7  jnz     loc_18000A1D7
0x18000a2bd  cmp     [rdi+0D8h], ebp
0x18000a2c3  jbe     loc_18000A1D7
0x18000a2c9  mov     rcx, rsi
0x18000a2cc  call    CDKsyncCache_0
0x18000a2d1  mov     edx, [rdi+0D8h]
0x18000a2d7  mov     eax, [rsi+8]
0x18000a2da  lea     edx, [rax+rdx*8]
0x18000a2dd  sub     edx, [rdi+0EF8h]
0x18000a2e3  jz      loc_18000A1D7
0x18000a2e9  jmp     loc_18000A23C
0x18000a2ee  neg     edx
0x18000a2f0  call    CDKpushBack
0x18000a2f5  mov     ebp, 401h
0x18000a2fa  jmp     loc_18000A1D7
0x18000a2ff  neg     edx
0x18000a301  call    CDKpushBack
0x18000a306  jmp     loc_18000A1EC
0x18000a30b  cmp     [rdi+0C2h], bpl
0x18000a312  jnz     loc_18000A1F9
0x18000a318  mov     edx, 10h
0x18000a31d  mov     rcx, rsi
0x18000a320  call    CDKreadBits
0x18000a325  mov     [rdi+128h], ax
0x18000a32c  jmp     loc_18000A1F9
```
