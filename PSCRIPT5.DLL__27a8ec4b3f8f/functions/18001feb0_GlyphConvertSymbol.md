# GlyphConvertSymbol

- ea: `0x18001feb0`
- end: `0x18002006e`
- name: `GlyphConvertSymbol`
- size: `446`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020c68`

## callees

- `0x18001feb0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180020051`
- `KERNEL32!GlobalFree` at `0x180020051`
- `KERNEL32!LocalAlloc` at `0x18001ff94`
- `KERNEL32!LocalAlloc` at `0x18001ff94`
- `GDI32!EngGetCurrentCodePage` at `0x18001fed8`
- `GDI32!EngGetCurrentCodePage` at `0x18001fed8`
- `GDI32!EngComputeGlyphSet` at `0x18001ff2b`
- `GDI32!EngComputeGlyphSet` at `0x18001ff2b`

## pseudocode

```c
_DWORD *__fastcall GlyphConvertSymbol(__int64 a1)
{
  _DWORD *v1; // rdi
  unsigned int v2; // eax
  int v3; // ecx
  unsigned __int16 v4; // ax
  FD_GLYPHSET *v5; // rax
  FD_GLYPHSET *v6; // rbx
  unsigned __int64 v7; // rax
  unsigned int v8; // ecx
  unsigned int cGlyphsSupported; // eax
  unsigned __int64 v10; // rax
  unsigned int v11; // esi
  _DWORD *v12; // rax
  ULONG v13; // r8d
  __int64 cRuns; // rcx
  ULONG *v15; // r9
  unsigned int *v16; // rdx
  unsigned int v17; // r10d
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int i; // eax
  __int64 v22; // [rsp+40h] [rbp+8h] BYREF
  USHORT v23; // [rsp+48h] [rbp+10h] BYREF

  v22 = a1;
  v23 = 0;
  LOWORD(v22) = 0;
  v1 = 0;
  EngGetCurrentCodePage(&v23, (PUSHORT)&v22);
  v2 = (unsigned __int16)v22;
  if ( (unsigned __int16)(v22 - 932) <= 0x12u && (v3 = 393233, LOWORD(v2) = v22 - 932, _bittest(&v3, v2))
    || (_WORD)v22 == 1361 )
  {
    v4 = 1252;
  }
  else
  {
    v4 = 0;
  }
  LOWORD(v22) = v4;
  v5 = EngComputeGlyphSet(v4, 31, 225);
  v6 = v5;
  if ( v5 )
  {
    v7 = 16LL * v5->cRuns;
    if ( v7 <= 0xFFFFFFFF )
    {
      v8 = v7 + 32;
      if ( (unsigned int)v7 < 0xFFFFFFE0 )
      {
        cGlyphsSupported = v6->cGlyphsSupported;
        if ( cGlyphsSupported + 225 >= cGlyphsSupported )
        {
          v10 = 4LL * (cGlyphsSupported + 225);
          if ( v10 <= 0xFFFFFFFF )
          {
            v11 = v10 + v8;
            if ( (unsigned int)v10 + v8 >= v8 )
            {
              v12 = LocalAlloc(0, v11);
              v1 = v12;
              if ( v12 )
              {
                *v12 = v11;
                v13 = 0;
                v12[1] = v6->flAccel;
                v12[2] = v6->cGlyphsSupported + 225;
                v12[3] = v6->cRuns + 1;
                cRuns = v6->cRuns;
                v15 = &v6[1].cjThis + 4 * (unsigned int)(cRuns - 1);
                v16 = &v12[4 * cRuns + 8];
                if ( (_DWORD)cRuns )
                {
                  do
                  {
                    v17 = 0;
                    v18 = 2LL * v13;
                    *(WCRUN *)&v12[2 * v18 + 4] = v6->awcrun[v13];
                    for ( *(_QWORD *)&v12[2 * v18 + 6] = v16; v17 < v6->awcrun[v13].cGlyphs; ++v16 )
                    {
                      ++v17;
                      *v16 = *v15++;
                    }
                    ++v13;
                  }
                  while ( v13 < v6->cRuns );
                }
                v19 = 2LL * v13;
                v1[2 * v19 + 4] = 14807071;
                *(_QWORD *)&v1[2 * v19 + 6] = v16;
                for ( i = 0; i < 0xE1; ++i )
                  *v16++ = i;
              }
            }
          }
        }
      }
    }
    GlobalFree(v6);
  }
  return v1;
}

```

## disassembly

```asm
0x18001feb0  mov     r11, rsp
0x18001feb3  mov     [r11+18h], rbx
0x18001feb7  mov     [r11+8], rcx
0x18001febb  push    rbp
0x18001febc  push    rsi
0x18001febd  push    rdi
0x18001febe  sub     rsp, 20h
0x18001fec2  xor     eax, eax
0x18001fec4  lea     rdx, [r11+8]; AnsiCodePage
0x18001fec8  lea     rcx, [r11+10h]; OemCodePage
0x18001fecc  mov     [rsp+38h+arg_8], ax
0x18001fed1  mov     word ptr [rsp+38h+arg_0], ax
0x18001fed6  xor     edi, edi
0x18001fed8  call    cs:__imp_EngGetCurrentCodePage
0x18001fedf  nop     dword ptr [rax+rax+00h]
0x18001fee4  movzx   eax, word ptr [rsp+38h+arg_0]
0x18001fee9  mov     ecx, 3A4h
0x18001feee  sub     ax, cx
0x18001fef1  cmp     ax, 12h
0x18001fef5  ja      short loc_18001FF01
0x18001fef7  mov     ecx, 60011h
0x18001fefc  bt      ecx, eax
0x18001feff  jb      short loc_18001FF11
0x18001ff01  mov     eax, 551h
0x18001ff06  cmp     word ptr [rsp+38h+arg_0], ax
0x18001ff0b  jz      short loc_18001FF11
0x18001ff0d  xor     eax, eax
0x18001ff0f  jmp     short loc_18001FF16
0x18001ff11  mov     eax, 4E4h
0x18001ff16  mov     ebp, 0E1h
0x18001ff1b  movzx   ecx, ax; nCodePage
0x18001ff1e  mov     r8d, ebp; cChars
0x18001ff21  mov     word ptr [rsp+38h+arg_0], ax
0x18001ff26  mov     edx, 1Fh; nFirstChar
0x18001ff2b  call    cs:__imp_EngComputeGlyphSet
0x18001ff32  nop     dword ptr [rax+rax+00h]
0x18001ff37  mov     rbx, rax
0x18001ff3a  test    rax, rax
0x18001ff3d  jz      loc_18002005D
0x18001ff43  mov     eax, [rax+0Ch]
0x18001ff46  mov     r8d, 0FFFFFFFFh
0x18001ff4c  shl     rax, 4
0x18001ff50  cmp     rax, r8
0x18001ff53  ja      loc_18002004E
0x18001ff59  lea     ecx, [rax+20h]
0x18001ff5c  cmp     ecx, 20h ; ' '
0x18001ff5f  jb      loc_18002004E
0x18001ff65  mov     eax, [rbx+8]
0x18001ff68  lea     edx, [rax+0E1h]
0x18001ff6e  cmp     edx, eax
0x18001ff70  jb      loc_18002004E
0x18001ff76  mov     eax, edx
0x18001ff78  shl     rax, 2
0x18001ff7c  cmp     rax, r8
0x18001ff7f  ja      loc_18002004E
0x18001ff85  lea     esi, [rax+rcx]
0x18001ff88  cmp     esi, ecx
0x18001ff8a  jb      loc_18002004E
0x18001ff90  mov     edx, esi; uBytes
0x18001ff92  xor     ecx, ecx; uFlags
0x18001ff94  call    cs:__imp_LocalAlloc
0x18001ff9b  nop     dword ptr [rax+rax+00h]
0x18001ffa0  mov     rdi, rax
0x18001ffa3  test    rax, rax
0x18001ffa6  jz      loc_18002004E
0x18001ffac  mov     [rax], esi
0x18001ffae  xor     r8d, r8d
0x18001ffb1  mov     eax, [rbx+4]
0x18001ffb4  mov     [rdi+4], eax
0x18001ffb7  mov     eax, [rbx+8]
0x18001ffba  add     eax, ebp
0x18001ffbc  mov     [rdi+8], eax
0x18001ffbf  mov     eax, [rbx+0Ch]
0x18001ffc2  inc     eax
0x18001ffc4  mov     [rdi+0Ch], eax
0x18001ffc7  mov     ecx, [rbx+0Ch]
0x18001ffca  lea     r9d, [rcx-1]
0x18001ffce  add     r9, 2
0x18001ffd2  lea     rdx, [rcx+2]
0x18001ffd6  shl     r9, 4
0x18001ffda  shl     rdx, 4
0x18001ffde  add     r9, rbx
0x18001ffe1  add     rdx, rdi
0x18001ffe4  test    ecx, ecx
0x18001ffe6  jz      short loc_18002002D
0x18001ffe8  mov     ecx, r8d
0x18001ffeb  xor     r10d, r10d
0x18001ffee  add     rcx, rcx
0x18001fff1  xor     eax, eax
0x18001fff3  movups  xmm0, xmmword ptr [rbx+rcx*8+10h]
0x18001fff8  movdqu  xmmword ptr [rdi+rcx*8+10h], xmm0
0x18001fffe  mov     [rdi+rcx*8+18h], rdx
0x180020003  cmp     ax, [rbx+rcx*8+12h]
0x180020008  jnb     short loc_180020024
0x18002000a  mov     eax, [r9]
0x18002000d  inc     r10d
0x180020010  mov     [rdx], eax
0x180020012  add     r9, 4
0x180020016  movzx   eax, word ptr [rbx+rcx*8+12h]
0x18002001b  add     rdx, 4
0x18002001f  cmp     r10d, eax
0x180020022  jb      short loc_18002000A
0x180020024  inc     r8d
0x180020027  cmp     r8d, [rbx+0Ch]
0x18002002b  jb      short loc_18001FFE8
0x18002002d  mov     eax, r8d
0x180020030  add     rax, rax
0x180020033  mov     dword ptr [rdi+rax*8+10h], 0E1F01Fh
0x18002003b  mov     [rdi+rax*8+18h], rdx
0x180020040  xor     eax, eax
0x180020042  mov     [rdx], eax
0x180020044  inc     eax
0x180020046  lea     rdx, [rdx+4]
0x18002004a  cmp     eax, ebp
0x18002004c  jb      short loc_180020042
0x18002004e  mov     rcx, rbx; hMem
0x180020051  call    cs:__imp_GlobalFree
0x180020058  nop     dword ptr [rax+rax+00h]
0x18002005d  mov     rbx, [rsp+38h+arg_10]
0x180020062  mov     rax, rdi
0x180020065  add     rsp, 20h
0x180020069  pop     rdi
0x18002006a  pop     rsi
0x18002006b  pop     rbp
0x18002006c  retn
```
