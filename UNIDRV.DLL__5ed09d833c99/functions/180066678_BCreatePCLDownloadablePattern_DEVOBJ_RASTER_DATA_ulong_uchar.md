# BCreatePCLDownloadablePattern(_DEVOBJ *,_RASTER_DATA *,ulong *,uchar * *)

- ea: `0x180066678`
- end: `0x18006683b`
- name: `?BCreatePCLDownloadablePattern@@YAHPEAU_DEVOBJ@@PEAU_RASTER_DATA@@PEAKPEAPEAE@Z`
- size: `451`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _RASTER_DATA *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180066844`

## callees

- `0x180066678`
- `0x18006cda8`
- `0x18006cec0`
- `0x18006cf14`
- `0x18006cf48`
- `0x18006cf7c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180066769`
- `KERNEL32!LocalAlloc` at `0x180066769`

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
0x180066678  push    rbx
0x18006667a  push    rbp
0x18006667b  push    rsi
0x18006667c  push    rdi
0x18006667d  push    r12
0x18006667f  push    r13
0x180066681  push    r14
0x180066683  push    r15
0x180066685  sub     rsp, 58h
0x180066689  xor     eax, eax
0x18006668b  xor     edi, edi
0x18006668d  mov     [rsp+98h+var_58], rax
0x180066692  xorps   xmm0, xmm0
0x180066695  mov     [rsp+98h+arg_0], rdi
0x18006669d  mov     r15, r9
0x1800666a0  mov     r12, r8
0x1800666a3  mov     r11, rdx
0x1800666a6  movups  [rsp+98h+var_78], xmm0
0x1800666ab  movups  [rsp+98h+var_68], xmm0
0x1800666b0  test    rcx, rcx
0x1800666b3  jz      loc_180066827
0x1800666b9  test    rdx, rdx
0x1800666bc  jz      loc_180066827
0x1800666c2  test    r8, r8
0x1800666c5  jz      loc_180066827
0x1800666cb  test    r9, r9
0x1800666ce  jz      loc_180066827
0x1800666d4  xor     r9d, r9d; unsigned int
0x1800666d7  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x1800666dc  xor     r8d, r8d; struct _RECTL *
0x1800666df  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x1800666e4  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x1800666e9  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x1800666ee  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x1800666f3  mov     ebp, eax
0x1800666f5  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x1800666fa  mov     [r12], edi
0x1800666fe  mov     r14d, eax
0x180066701  mov     [r15], rdi
0x180066704  test    ebp, ebp
0x180066706  js      loc_180066827
0x18006670c  test    eax, eax
0x18006670e  js      loc_180066827
0x180066714  mov     esi, [r11+20h]
0x180066718  cmp     esi, 1
0x18006671b  jz      short loc_180066726
0x18006671d  cmp     esi, 8
0x180066720  jnz     loc_180066827
0x180066726  test    ebp, ebp
0x180066728  jz      loc_180066820
0x18006672e  test    r14d, r14d
0x180066731  jz      loc_180066820
0x180066737  cmp     esi, 1
0x18006673a  jnz     short loc_18006674C
0x18006673c  mov     eax, ebp
0x18006673e  and     eax, 7
0x180066741  jz      short loc_18006674C
0x180066743  mov     ebx, ebp
0x180066745  sub     ebx, eax
0x180066747  add     ebx, 8
0x18006674a  jmp     short loc_180066751
0x18006674c  mov     ebx, esi
0x18006674e  imul    ebx, ebp
0x180066751  shr     ebx, 3
0x180066754  imul    ebx, r14d
0x180066758  cmp     ebx, [r11+10h]
0x18006675c  ja      loc_180066827
0x180066762  mov     edx, ebx; uBytes
0x180066764  mov     ecx, 40h ; '@'; uFlags
0x180066769  call    cs:__imp_LocalAlloc
0x180066770  nop     dword ptr [rax+rax+00h]
0x180066775  mov     r13, rax
0x180066778  test    rax, rax
0x18006677b  jz      loc_180066827
0x180066781  mov     [r15], rax
0x180066784  xor     r15d, r15d
0x180066787  mov     [r12], ebx
0x18006678b  test    r14d, r14d
0x18006678e  jz      loc_180066820
0x180066794  mov     edx, r15d; int
0x180066797  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x18006679c  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x1800667a1  cmp     esi, 1
0x1800667a4  jnz     short loc_1800667B4
0x1800667a6  mov     ecx, edi
0x1800667a8  and     ecx, 7
0x1800667ab  jz      short loc_1800667B4
0x1800667ad  lea     eax, [rsi+7]
0x1800667b0  sub     eax, ecx
0x1800667b2  add     edi, eax
0x1800667b4  xor     ebx, ebx
0x1800667b6  test    ebp, ebp
0x1800667b8  jz      short loc_180066814
0x1800667ba  lea     r8, [rsp+98h+arg_0]; struct _PIXEL *
0x1800667c2  mov     edx, ebx; int
0x1800667c4  lea     rcx, [rsp+98h+var_78]; struct _RASTER_ITERATOR *
0x1800667c9  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x1800667ce  mov     ecx, dword ptr [rsp+98h+arg_0+4]
0x1800667d5  test    ecx, ecx
0x1800667d7  jz      short loc_18006680C
0x1800667d9  mov     eax, esi
0x1800667db  sub     eax, 1
0x1800667de  jz      short loc_1800667ED
0x1800667e0  cmp     eax, 7
0x1800667e3  jnz     short loc_18006680C
0x1800667e5  mov     eax, edi
0x1800667e7  mov     [rax+r13], cl
0x1800667eb  jmp     short loc_18006680C
0x1800667ed  mov     r8d, edi
0x1800667f0  mov     ecx, edi
0x1800667f2  shr     r8, 3
0x1800667f6  and     ecx, 7
0x1800667f9  mov     eax, 7
0x1800667fe  sub     eax, ecx
0x180066800  movzx   edx, byte ptr [r8+r13]
0x180066805  bts     edx, eax
0x180066808  mov     [r8+r13], dl
0x18006680c  inc     edi
0x18006680e  inc     ebx
0x180066810  cmp     ebx, ebp
0x180066812  jb      short loc_1800667BA
0x180066814  inc     r15d
0x180066817  cmp     r15d, r14d
0x18006681a  jb      loc_180066794
0x180066820  mov     eax, 1
0x180066825  jmp     short loc_180066829
0x180066827  xor     eax, eax
0x180066829  add     rsp, 58h
0x18006682d  pop     r15
0x18006682f  pop     r14
0x180066831  pop     r13
0x180066833  pop     r12
0x180066835  pop     rdi
0x180066836  pop     rsi
0x180066837  pop     rbp
0x180066838  pop     rbx
0x180066839  retn
```
