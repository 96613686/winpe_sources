# GlyphConvertSymbol

- ea: `0x18001f31c`
- end: `0x18001f4c1`
- name: `GlyphConvertSymbol`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002002c`

## callees

- `0x18001f31c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18001f4ab`
- `KERNEL32!GlobalFree` at `0x18001f4ab`
- `KERNEL32!LocalAlloc` at `0x18001f3f4`
- `KERNEL32!LocalAlloc` at `0x18001f3f4`
- `GDI32!EngGetCurrentCodePage` at `0x18001f344`
- `GDI32!EngGetCurrentCodePage` at `0x18001f344`
- `GDI32!EngComputeGlyphSet` at `0x18001f391`
- `GDI32!EngComputeGlyphSet` at `0x18001f391`

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
0x18001f31c  mov     r11, rsp
0x18001f31f  mov     [r11+18h], rbx
0x18001f323  mov     [r11+8], rcx
0x18001f327  push    rbp
0x18001f328  push    rsi
0x18001f329  push    rdi
0x18001f32a  sub     rsp, 20h
0x18001f32e  xor     eax, eax
0x18001f330  lea     rdx, [r11+8]; AnsiCodePage
0x18001f334  lea     rcx, [r11+10h]; OemCodePage
0x18001f338  mov     [rsp+38h+arg_8], ax
0x18001f33d  mov     word ptr [rsp+38h+arg_0], ax
0x18001f342  xor     edi, edi
0x18001f344  call    cs:__imp_EngGetCurrentCodePage
0x18001f34a  movzx   eax, word ptr [rsp+38h+arg_0]
0x18001f34f  mov     ecx, 3A4h
0x18001f354  sub     ax, cx
0x18001f357  cmp     ax, 12h
0x18001f35b  ja      short loc_18001F367
0x18001f35d  mov     ecx, 60011h
0x18001f362  bt      ecx, eax
0x18001f365  jb      short loc_18001F377
0x18001f367  mov     eax, 551h
0x18001f36c  cmp     word ptr [rsp+38h+arg_0], ax
0x18001f371  jz      short loc_18001F377
0x18001f373  xor     eax, eax
0x18001f375  jmp     short loc_18001F37C
0x18001f377  mov     eax, 4E4h
0x18001f37c  mov     ebp, 0E1h
0x18001f381  movzx   ecx, ax; nCodePage
0x18001f384  mov     r8d, ebp; cChars
0x18001f387  mov     word ptr [rsp+38h+arg_0], ax
0x18001f38c  mov     edx, 1Fh; nFirstChar
0x18001f391  call    cs:__imp_EngComputeGlyphSet
0x18001f397  mov     rbx, rax
0x18001f39a  test    rax, rax
0x18001f39d  jz      loc_18001F4B1
0x18001f3a3  mov     eax, [rax+0Ch]
0x18001f3a6  mov     r8d, 0FFFFFFFFh
0x18001f3ac  shl     rax, 4
0x18001f3b0  cmp     rax, r8
0x18001f3b3  ja      loc_18001F4A8
0x18001f3b9  lea     ecx, [rax+20h]
0x18001f3bc  cmp     ecx, 20h ; ' '
0x18001f3bf  jb      loc_18001F4A8
0x18001f3c5  mov     eax, [rbx+8]
0x18001f3c8  lea     edx, [rax+0E1h]
0x18001f3ce  cmp     edx, eax
0x18001f3d0  jb      loc_18001F4A8
0x18001f3d6  mov     eax, edx
0x18001f3d8  shl     rax, 2
0x18001f3dc  cmp     rax, r8
0x18001f3df  ja      loc_18001F4A8
0x18001f3e5  lea     esi, [rax+rcx]
0x18001f3e8  cmp     esi, ecx
0x18001f3ea  jb      loc_18001F4A8
0x18001f3f0  mov     edx, esi; uBytes
0x18001f3f2  xor     ecx, ecx; uFlags
0x18001f3f4  call    cs:__imp_LocalAlloc
0x18001f3fa  mov     rdi, rax
0x18001f3fd  test    rax, rax
0x18001f400  jz      loc_18001F4A8
0x18001f406  mov     [rax], esi
0x18001f408  xor     r8d, r8d
0x18001f40b  mov     eax, [rbx+4]
0x18001f40e  mov     [rdi+4], eax
0x18001f411  mov     eax, [rbx+8]
0x18001f414  add     eax, ebp
0x18001f416  mov     [rdi+8], eax
0x18001f419  mov     eax, [rbx+0Ch]
0x18001f41c  inc     eax
0x18001f41e  mov     [rdi+0Ch], eax
0x18001f421  mov     ecx, [rbx+0Ch]
0x18001f424  lea     r9d, [rcx-1]
0x18001f428  add     r9, 2
0x18001f42c  lea     rdx, [rcx+2]
0x18001f430  shl     r9, 4
0x18001f434  shl     rdx, 4
0x18001f438  add     r9, rbx
0x18001f43b  add     rdx, rdi
0x18001f43e  test    ecx, ecx
0x18001f440  jz      short loc_18001F487
0x18001f442  mov     ecx, r8d
0x18001f445  xor     r10d, r10d
0x18001f448  add     rcx, rcx
0x18001f44b  xor     eax, eax
0x18001f44d  movups  xmm0, xmmword ptr [rbx+rcx*8+10h]
0x18001f452  movdqu  xmmword ptr [rdi+rcx*8+10h], xmm0
0x18001f458  mov     [rdi+rcx*8+18h], rdx
0x18001f45d  cmp     ax, [rbx+rcx*8+12h]
0x18001f462  jnb     short loc_18001F47E
0x18001f464  mov     eax, [r9]
0x18001f467  inc     r10d
0x18001f46a  mov     [rdx], eax
0x18001f46c  add     r9, 4
0x18001f470  movzx   eax, word ptr [rbx+rcx*8+12h]
0x18001f475  add     rdx, 4
0x18001f479  cmp     r10d, eax
0x18001f47c  jb      short loc_18001F464
0x18001f47e  inc     r8d
0x18001f481  cmp     r8d, [rbx+0Ch]
0x18001f485  jb      short loc_18001F442
0x18001f487  mov     eax, r8d
0x18001f48a  add     rax, rax
0x18001f48d  mov     dword ptr [rdi+rax*8+10h], 0E1F01Fh
0x18001f495  mov     [rdi+rax*8+18h], rdx
0x18001f49a  xor     eax, eax
0x18001f49c  mov     [rdx], eax
0x18001f49e  inc     eax
0x18001f4a0  lea     rdx, [rdx+4]
0x18001f4a4  cmp     eax, ebp
0x18001f4a6  jb      short loc_18001F49C
0x18001f4a8  mov     rcx, rbx; hMem
0x18001f4ab  call    cs:__imp_GlobalFree
0x18001f4b1  mov     rbx, [rsp+38h+arg_10]
0x18001f4b6  mov     rax, rdi
0x18001f4b9  add     rsp, 20h
0x18001f4bd  pop     rdi
0x18001f4be  pop     rsi
0x18001f4bf  pop     rbp
0x18001f4c0  retn
```
