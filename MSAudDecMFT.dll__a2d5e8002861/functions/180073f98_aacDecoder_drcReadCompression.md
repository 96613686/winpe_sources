# aacDecoder_drcReadCompression

- ea: `0x180073f98`
- end: `0x1800740e2`
- name: `aacDecoder_drcReadCompression`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013718`

## callees

- `0x1800110c0`
- `0x180013550`
- `0x1800136a4`
- `0x180013ad0`
- `0x180073f98`

## pseudocode

```c
__int64 __fastcall aacDecoder_drcReadCompression(_DWORD *a1, __int64 a2, int a3)
{
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  unsigned int v11; // ebp
  int v12; // ebx
  int v13; // r14d
  __int64 v14; // r8
  char v15; // bl
  __int64 v16; // r8
  char v17; // al

  ((void (*)(void))CDKsyncCache_1)();
  CDKpushBiDirectional(a1, (unsigned int)(a1[2] - a3));
  CDKsyncCache_1(a1);
  if ( (int)a1[2] >= 24 && (unsigned int)CDKreadBits(a1, 8, v6) == 188 && (unsigned int)CDKreadBits(a1, 2, v7) == 3 )
  {
    CDKreadBits(a1, 2, v8);
    *(_BYTE *)(a2 + 5) = CDKreadBits(a1, 2, v9);
    CDKreadBit((__int64)a1);
    if ( !(unsigned int)CDKreadBit((__int64)a1) && !(unsigned int)CDKreadBits(a1, 3, v10) )
    {
      v11 = 0;
      v12 = CDKreadBit((__int64)a1);
      CDKreadBit((__int64)a1);
      v13 = CDKreadBit((__int64)a1);
      CDKreadBit((__int64)a1);
      CDKreadBit((__int64)a1);
      if ( v12 )
        CDKreadBits(a1, 8, v14);
      if ( !v13 )
        return v11;
      if ( !(unsigned int)CDKreadBits(a1, 7, v14) )
      {
        v15 = CDKreadBit((__int64)a1);
        v17 = CDKreadBits(a1, 8, v16);
        if ( v15 )
        {
          v11 = 1;
          *(_BYTE *)(a2 + 50) = v17;
          *(_DWORD *)(a2 + 12) = 1;
          *(_WORD *)(a2 + 16) = 255;
          *(_BYTE *)(a2 + 6) = -1;
          *(_BYTE *)(a2 + 4) = -1;
          *(_BYTE *)(a2 + 66) = 2;
        }
        return v11;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180073f98  push    rbx
0x180073f9a  push    rbp
0x180073f9b  push    rsi
0x180073f9c  push    rdi
0x180073f9d  push    r14
0x180073f9f  sub     rsp, 20h
0x180073fa3  mov     ebx, r8d
0x180073fa6  mov     rsi, rdx
0x180073fa9  mov     rdi, rcx
0x180073fac  call    CDKsyncCache_1
0x180073fb1  mov     edx, [rdi+8]
0x180073fb4  mov     rcx, rdi
0x180073fb7  sub     edx, ebx
0x180073fb9  call    CDKpushBiDirectional
0x180073fbe  mov     rcx, rdi
0x180073fc1  call    CDKsyncCache_1
0x180073fc6  cmp     dword ptr [rdi+8], 18h
0x180073fca  jl      loc_1800740D4
0x180073fd0  mov     edx, 8
0x180073fd5  mov     rcx, rdi
0x180073fd8  call    CDKreadBits
0x180073fdd  cmp     eax, 0BCh
0x180073fe2  jnz     loc_1800740D4
0x180073fe8  mov     edx, 2
0x180073fed  mov     rcx, rdi
0x180073ff0  call    CDKreadBits
0x180073ff5  cmp     eax, 3
0x180073ff8  jnz     loc_1800740D4
0x180073ffe  lea     edx, [rax-1]
0x180074001  mov     rcx, rdi
0x180074004  call    CDKreadBits
0x180074009  mov     edx, 2
0x18007400e  mov     rcx, rdi
0x180074011  call    CDKreadBits
0x180074016  mov     rcx, rdi
0x180074019  mov     [rsi+5], al
0x18007401c  call    CDKreadBit
0x180074021  mov     rcx, rdi
0x180074024  call    CDKreadBit
0x180074029  test    eax, eax
0x18007402b  jnz     loc_1800740D4
0x180074031  lea     edx, [rax+3]
0x180074034  mov     rcx, rdi
0x180074037  call    CDKreadBits
0x18007403c  test    eax, eax
0x18007403e  jnz     loc_1800740D4
0x180074044  mov     rcx, rdi
0x180074047  xor     ebp, ebp
0x180074049  call    CDKreadBit
0x18007404e  mov     rcx, rdi
0x180074051  mov     ebx, eax
0x180074053  call    CDKreadBit
0x180074058  mov     rcx, rdi
0x18007405b  call    CDKreadBit
0x180074060  mov     rcx, rdi
0x180074063  mov     r14d, eax
0x180074066  call    CDKreadBit
0x18007406b  mov     rcx, rdi
0x18007406e  call    CDKreadBit
0x180074073  test    ebx, ebx
0x180074075  jz      short loc_180074082
0x180074077  lea     edx, [rbp+8]
0x18007407a  mov     rcx, rdi
0x18007407d  call    CDKreadBits
0x180074082  test    r14d, r14d
0x180074085  jz      short loc_1800740D0
0x180074087  mov     edx, 7
0x18007408c  mov     rcx, rdi
0x18007408f  call    CDKreadBits
0x180074094  test    eax, eax
0x180074096  jnz     short loc_1800740D4
0x180074098  mov     rcx, rdi
0x18007409b  call    CDKreadBit
0x1800740a0  mov     edx, 8
0x1800740a5  mov     rcx, rdi
0x1800740a8  mov     ebx, eax
0x1800740aa  call    CDKreadBits
0x1800740af  test    bl, bl
0x1800740b1  jz      short loc_1800740D0
0x1800740b3  mov     ebp, 1
0x1800740b8  mov     [rsi+32h], al
0x1800740bb  mov     [rsi+0Ch], ebp
0x1800740be  mov     word ptr [rsi+10h], 0FFh
0x1800740c4  mov     byte ptr [rsi+6], 0FFh
0x1800740c8  mov     byte ptr [rsi+4], 0FFh
0x1800740cc  mov     byte ptr [rsi+42h], 2
0x1800740d0  mov     eax, ebp
0x1800740d2  jmp     short loc_1800740D6
0x1800740d4  xor     eax, eax
0x1800740d6  add     rsp, 20h
0x1800740da  pop     r14
0x1800740dc  pop     rdi
0x1800740dd  pop     rsi
0x1800740de  pop     rbp
0x1800740df  pop     rbx
0x1800740e0  retn
```
