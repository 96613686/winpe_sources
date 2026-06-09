# BCreatePCLDownloadablePattern(_DEVOBJ *,_RASTER_DATA *,ulong *,uchar * *)

- ea: `0x180064f64`
- end: `0x180065120`
- name: `?BCreatePCLDownloadablePattern@@YAHPEAU_DEVOBJ@@PEAU_RASTER_DATA@@PEAKPEAPEAE@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _RASTER_DATA *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180065128`

## callees

- `0x180064f64`
- `0x18006b418`
- `0x18006b52c`
- `0x18006b57c`
- `0x18006b5b0`
- `0x18006b5e4`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180065055`
- `KERNEL32!LocalAlloc` at `0x180065055`

## pseudocode

```c
__int64 __fastcall BCreatePCLDownloadablePattern(
        struct _DEVOBJ *a1,
        struct _RASTER_DATA *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int v4; // edi
  int v7; // ebp
  int v8; // eax
  __int64 v9; // r11
  unsigned int v10; // r14d
  int v11; // esi
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // r13
  unsigned int v16; // r15d
  unsigned int i; // ebx
  _OWORD v19[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+A0h] [rbp+8h] BYREF

  v4 = 0;
  v20 = 0;
  v21 = 0;
  memset(v19, 0, sizeof(v19));
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          RI_Init((struct _RASTER_ITERATOR *)v19, a2, 0, 0);
          v7 = RI_NumCols((struct _RASTER_ITERATOR *)v19);
          v8 = RI_NumRows((struct _RASTER_ITERATOR *)v19);
          *a3 = 0;
          v10 = v8;
          *a4 = 0;
          if ( v7 >= 0 && v8 >= 0 )
          {
            v11 = *(_DWORD *)(v9 + 32);
            if ( v11 == 1 || v11 == 8 )
            {
              if ( !v7 || !v8 )
                return 1;
              if ( v11 == 1 && (v7 & 7) != 0 )
                v12 = v7 - (v7 & 7) + 8;
              else
                v12 = v7 * v11;
              v13 = v8 * (v12 >> 3);
              if ( v13 <= *(_DWORD *)(v9 + 16) )
              {
                v14 = (unsigned __int8 *)LocalAlloc(0x40u, v13);
                v15 = v14;
                if ( v14 )
                {
                  *a4 = v14;
                  v16 = 0;
                  *a3 = v13;
                  do
                  {
                    RI_SelectRow((struct _RASTER_ITERATOR *)v19, v16);
                    if ( v11 == 1 && (v4 & 7) != 0 )
                      v4 += 8 - (v4 & 7);
                    for ( i = 0; i < v7; ++i )
                    {
                      RI_GetPixel((struct _RASTER_ITERATOR *)v19, i, (struct _PIXEL *)&v21);
                      if ( HIDWORD(v21) )
                      {
                        if ( v11 == 1 )
                          v15[(unsigned __int64)v4 >> 3] |= 1 << (7 - (v4 & 7));
                        else
                          v15[v4] = BYTE4(v21);
                      }
                      ++v4;
                    }
                    ++v16;
                  }
                  while ( v16 < v10 );
                  return 1;
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180064f64  push    rbx
0x180064f66  push    rbp
0x180064f67  push    rsi
0x180064f68  push    rdi
0x180064f69  push    r12
0x180064f6b  push    r13
0x180064f6d  push    r14
0x180064f6f  push    r15
0x180064f71  sub     rsp, 58h
0x180064f75  xor     eax, eax
0x180064f77  xor     edi, edi
0x180064f79  mov     [rsp+98h+var_58], rax
0x180064f7e  xorps   xmm0, xmm0
0x180064f81  mov     [rsp+98h+arg_0], rdi
0x180064f89  mov     r15, r9
0x180064f8c  mov     r12, r8
0x180064f8f  mov     r11, rdx
0x180064f92  movups  [rsp+98h+var_78], xmm0
0x180064f97  movups  [rsp+98h+var_68], xmm0
0x180064f9c  test    rcx, rcx
0x180064f9f  jz      loc_18006510D
0x180064fa5  test    rdx, rdx
0x180064fa8  jz      loc_18006510D
0x180064fae  test    r8, r8
0x180064fb1  jz      loc_18006510D
0x180064fb7  test    r9, r9
0x180064fba  jz      loc_18006510D
0x180064fc0  xor     r9d, r9d; unsigned int
0x180064fc3  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x180064fc8  xor     r8d, r8d; struct _RECTL *
0x180064fcb  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x180064fd0  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x180064fd5  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x180064fda  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x180064fdf  mov     ebp, eax
0x180064fe1  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x180064fe6  mov     [r12], edi
0x180064fea  mov     r14d, eax
0x180064fed  mov     [r15], rdi
0x180064ff0  test    ebp, ebp
0x180064ff2  js      loc_18006510D
0x180064ff8  test    eax, eax
0x180064ffa  js      loc_18006510D
0x180065000  mov     esi, [r11+20h]
0x180065004  cmp     esi, 1
0x180065007  jz      short loc_180065012
0x180065009  cmp     esi, 8
0x18006500c  jnz     loc_18006510D
0x180065012  test    ebp, ebp
0x180065014  jz      loc_180065106
0x18006501a  test    r14d, r14d
0x18006501d  jz      loc_180065106
0x180065023  cmp     esi, 1
0x180065026  jnz     short loc_180065038
0x180065028  mov     eax, ebp
0x18006502a  and     eax, 7
0x18006502d  jz      short loc_180065038
0x18006502f  mov     ebx, ebp
0x180065031  sub     ebx, eax
0x180065033  add     ebx, 8
0x180065036  jmp     short loc_18006503D
0x180065038  mov     ebx, esi
0x18006503a  imul    ebx, ebp
0x18006503d  shr     ebx, 3
0x180065040  imul    ebx, r14d
0x180065044  cmp     ebx, [r11+10h]
0x180065048  ja      loc_18006510D
0x18006504e  mov     edx, ebx; uBytes
0x180065050  mov     ecx, 40h ; '@'; uFlags
0x180065055  call    cs:__imp_LocalAlloc
0x18006505b  mov     r13, rax
0x18006505e  test    rax, rax
0x180065061  jz      loc_18006510D
0x180065067  mov     [r15], rax
0x18006506a  xor     r15d, r15d
0x18006506d  mov     [r12], ebx
0x180065071  test    r14d, r14d
0x180065074  jz      loc_180065106
0x18006507a  mov     edx, r15d; int
0x18006507d  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x180065082  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x180065087  cmp     esi, 1
0x18006508a  jnz     short loc_18006509A
0x18006508c  mov     ecx, edi
0x18006508e  and     ecx, 7
0x180065091  jz      short loc_18006509A
0x180065093  lea     eax, [rsi+7]
0x180065096  sub     eax, ecx
0x180065098  add     edi, eax
0x18006509a  xor     ebx, ebx
0x18006509c  test    ebp, ebp
0x18006509e  jz      short loc_1800650FA
0x1800650a0  lea     r8, [rsp+98h+arg_0]; struct _PIXEL *
0x1800650a8  mov     edx, ebx; int
0x1800650aa  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x1800650af  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x1800650b4  mov     ecx, dword ptr [rsp+98h+arg_0+4]
0x1800650bb  test    ecx, ecx
0x1800650bd  jz      short loc_1800650F2
0x1800650bf  mov     eax, esi
0x1800650c1  sub     eax, 1
0x1800650c4  jz      short loc_1800650D3
0x1800650c6  cmp     eax, 7
0x1800650c9  jnz     short loc_1800650F2
0x1800650cb  mov     eax, edi
0x1800650cd  mov     [rax+r13], cl
0x1800650d1  jmp     short loc_1800650F2
0x1800650d3  mov     r8d, edi
0x1800650d6  mov     ecx, edi
0x1800650d8  shr     r8, 3
0x1800650dc  and     ecx, 7
0x1800650df  mov     eax, 7
0x1800650e4  sub     eax, ecx
0x1800650e6  movzx   edx, byte ptr [r8+r13]
0x1800650eb  bts     edx, eax
0x1800650ee  mov     [r8+r13], dl
0x1800650f2  inc     edi
0x1800650f4  inc     ebx
0x1800650f6  cmp     ebx, ebp
0x1800650f8  jb      short loc_1800650A0
0x1800650fa  inc     r15d
0x1800650fd  cmp     r15d, r14d
0x180065100  jb      loc_18006507A
0x180065106  mov     eax, 1
0x18006510b  jmp     short loc_18006510F
0x18006510d  xor     eax, eax
0x18006510f  add     rsp, 58h
0x180065113  pop     r15
0x180065115  pop     r14
0x180065117  pop     r13
0x180065119  pop     r12
0x18006511b  pop     rdi
0x18006511c  pop     rsi
0x18006511d  pop     rbp
0x18006511e  pop     rbx
0x18006511f  retn
```
