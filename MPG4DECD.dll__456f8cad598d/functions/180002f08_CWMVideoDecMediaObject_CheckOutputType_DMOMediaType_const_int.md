# CWMVideoDecMediaObject::CheckOutputType(_DMOMediaType const *,int)

- ea: `0x180002f08`
- end: `0x1800031ef`
- name: `?CheckOutputType@CWMVideoDecMediaObject@@IEAAJPEBU_DMOMediaType@@H@Z`
- size: `743`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, const struct _DMOMediaType *, LONG)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007fe0`

## callees

- `0x180001450`
- `0x180002f08`
- `0x1800031f8`
- `0x1800035f4`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180003109`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18000313b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180003109`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18000313b`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::CheckOutputType(
        CWMVideoDecMediaObject *this,
        const struct _DMOMediaType *a2,
        LONG a3)
{
  struct tagVIDEOINFOHEADER *v3; // r15
  RECT *v4; // r14
  int v6; // ebx
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rdx
  __int64 v9; // r13
  __int64 v10; // rcx
  int v11; // eax
  RECT *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  BITMAPINFOHEADER *p_bmiHeader; // rbp
  __int64 v17; // rax
  __int64 v18; // rbp
  int *p_right; // r10
  LONG *p_top; // rax
  int biHeight; // edi
  LONG v22; // eax
  int v23; // r13d
  LONG biWidth; // r12d
  int v25; // eax
  RECT *lprc; // [rsp+68h] [rbp+10h] BYREF
  LONG v28; // [rsp+70h] [rbp+18h]
  struct tagVIDEOINFOHEADER *v29; // [rsp+78h] [rbp+20h] BYREF

  v28 = a3;
  v3 = 0;
  v4 = 0;
  v29 = 0;
  lprc = 0;
  if ( !a2 )
    return (unsigned int)-2147467261;
  v7 = ((unsigned __int64)this + 64) & -(__int64)(*((_DWORD *)this + 14) != 0);
  if ( !v7 )
    return (unsigned int)-2147220989;
  v6 = CheckType(a2, (const struct _GUID *const *)&off_180027030, 9u);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v8 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  v9 = 0;
  v10 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( *(_QWORD *)((char *)a2 + 44) != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
    || *(_QWORD *)((char *)a2 + 52) != *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v14 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    v13 = *(_QWORD *)FORMAT_VideoInfo.Data4;
    if ( *(_QWORD *)((char *)a2 + 44) == *(_QWORD *)&FORMAT_VideoInfo.Data1
      && *(_QWORD *)((char *)a2 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
    {
      v12 = (RECT *)*((_QWORD *)a2 + 10);
    }
    else
    {
      if ( *(_QWORD *)((char *)a2 + 44) != *(_QWORD *)&FORMAT_VideoInfo2.Data1
        || *(_QWORD *)((char *)a2 + 52) != *(_QWORD *)FORMAT_VideoInfo2.Data4 )
      {
        goto LABEL_64;
      }
      v9 = *((_QWORD *)a2 + 10);
      v12 = 0;
    }
LABEL_16:
    if ( *(_QWORD *)(v7 + 44) == v8 && *(_QWORD *)(v7 + 52) == v10 )
    {
      v15 = ConvertMFVideoFormatToVIH2(&v29, *(struct _MFVIDEOFORMAT **)(v7 + 80));
      v3 = v29;
      v6 = v15;
      if ( v15 < 0 )
        goto LABEL_65;
      v10 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
      p_bmiHeader = &v29->bmiHeader;
      v8 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
      v13 = *(_QWORD *)FORMAT_VideoInfo.Data4;
      v14 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    }
    else
    {
      v17 = *(_QWORD *)(v7 + 44) - v14;
      if ( !v17 )
        v17 = *(_QWORD *)(v7 + 52) - v13;
      v18 = *(_QWORD *)(v7 + 80);
      if ( v17 )
        p_bmiHeader = (BITMAPINFOHEADER *)(v18 + 72);
      else
        p_bmiHeader = (BITMAPINFOHEADER *)(v18 + 48);
    }
    if ( *(_QWORD *)((char *)a2 + 44) == v8 && *(_QWORD *)((char *)a2 + 52) == v10
      || *(_QWORD *)((char *)a2 + 44) == v14 && *(_QWORD *)((char *)a2 + 52) == v13 )
    {
      lprc = v12 + 4;
      p_right = &v12[3].right;
      p_top = &v12[3].top;
    }
    else
    {
      lprc = (RECT *)(v9 + 88);
      p_right = (int *)(v9 + 80);
      p_top = (LONG *)(v9 + 76);
    }
    if ( (*(_QWORD *)((char *)a2 + 44) != v8 || *(_QWORD *)((char *)a2 + 52) != v10)
      && (*(_QWORD *)((char *)a2 + 44) != v14 || *(_QWORD *)((char *)a2 + 52) != v13) )
    {
      v12 = (RECT *)v9;
    }
    biHeight = -p_bmiHeader->biHeight;
    v22 = *p_top;
    if ( p_bmiHeader->biHeight > 0 )
      biHeight = p_bmiHeader->biHeight;
    v23 = -*p_right;
    biWidth = p_bmiHeader->biWidth;
    if ( *p_right > 0 )
      v23 = *p_right;
    v28 = v22;
    if ( !IsRectEmpty(v12) && (biWidth != v12->right || v12->left || biHeight != v12->bottom || v12->top)
      || !IsRectEmpty(v12 + 1) && (biWidth != v12[1].right || v12[1].left || biHeight != v12[1].bottom || v12[1].top)
      || v28 < biWidth
      || v23 < biHeight )
    {
      goto LABEL_64;
    }
    if ( lprc->left != 1498831189 && lprc->left != 844715353 && lprc->left != 1431918169 )
    {
      if ( lprc->left != 842094169 && lprc->left != 825316942 && lprc->left != 842094158 )
        goto LABEL_65;
      v25 = -p_bmiHeader->biHeight;
      if ( p_bmiHeader->biHeight > 0 )
        v25 = p_bmiHeader->biHeight;
      if ( v25 < 2 || (v25 & 1) != 0 )
        goto LABEL_64;
    }
    if ( p_bmiHeader->biWidth < 2 || (p_bmiHeader->biWidth & 1) != 0 )
LABEL_64:
      v6 = -2147220987;
LABEL_65:
    if ( v3 )
      operator delete(v3, v8);
    goto LABEL_67;
  }
  v11 = ConvertMFVideoFormatToVIH2((struct tagVIDEOINFOHEADER **)&lprc, *((struct _MFVIDEOFORMAT **)a2 + 10));
  v4 = lprc;
  v6 = v11;
  if ( v11 >= 0 )
  {
    v10 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    v12 = lprc;
    v8 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    v13 = *(_QWORD *)FORMAT_VideoInfo.Data4;
    v14 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    goto LABEL_16;
  }
LABEL_67:
  if ( v4 )
    operator delete(v4, v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002f08  mov     rax, rsp
0x180002f0b  mov     [rax+8], rbx
0x180002f0f  mov     [rax+18h], r8d
0x180002f13  push    rbp
0x180002f14  push    rsi
0x180002f15  push    rdi
0x180002f16  push    r12
0x180002f18  push    r13
0x180002f1a  push    r14
0x180002f1c  push    r15
0x180002f1e  sub     rsp, 20h
0x180002f22  xor     r15d, r15d
0x180002f25  xor     r14d, r14d
0x180002f28  mov     [rax+20h], r15
0x180002f2c  mov     rdi, rdx
0x180002f2f  mov     [rax+10h], r14
0x180002f33  test    rdx, rdx
0x180002f36  jnz     short loc_180002F42
0x180002f38  mov     ebx, 80004003h
0x180002f3d  jmp     loc_1800031D8
0x180002f42  mov     eax, [rcx+38h]
0x180002f45  add     rcx, 40h ; '@'
0x180002f49  neg     eax
0x180002f4b  sbb     rbp, rbp
0x180002f4e  and     rbp, rcx
0x180002f51  jnz     short loc_180002F5D
0x180002f53  mov     ebx, 80040203h
0x180002f58  jmp     loc_1800031D8
0x180002f5d  mov     r8d, 9; unsigned int
0x180002f63  lea     rdx, off_180027030; struct _GUID **
0x180002f6a  mov     rcx, rdi; struct _DMOMediaType *
0x180002f6d  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x180002f72  mov     ebx, eax
0x180002f74  test    eax, eax
0x180002f76  js      loc_1800031D8
0x180002f7c  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180002f83  xor     r13d, r13d
0x180002f86  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180002f8d  cmp     [rdi+2Ch], rdx
0x180002f91  jnz     short loc_180002FD7
0x180002f93  cmp     [rdi+34h], rcx
0x180002f97  jnz     short loc_180002FD7
0x180002f99  mov     rdx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x180002f9d  lea     rcx, [rsp+58h+lprc]; struct tagVIDEOINFOHEADER **
0x180002fa2  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180002fa7  mov     r14, [rsp+58h+lprc]
0x180002fac  mov     ebx, eax
0x180002fae  test    eax, eax
0x180002fb0  js      loc_1800031CB
0x180002fb6  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180002fbd  mov     rsi, r14
0x180002fc0  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180002fc7  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180002fce  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180002fd5  jmp     short loc_18000301F
0x180002fd7  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180002fde  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180002fe5  cmp     [rdi+2Ch], r9
0x180002fe9  jnz     short loc_180002FF7
0x180002feb  cmp     [rdi+34h], r8
0x180002fef  jnz     short loc_180002FF7
0x180002ff1  mov     rsi, [rdi+50h]
0x180002ff5  jmp     short loc_18000301F
0x180002ff7  mov     rax, [rdi+2Ch]
0x180002ffb  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180003002  jnz     loc_1800031B9
0x180003008  mov     rax, [rdi+34h]
0x18000300c  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180003013  jnz     loc_1800031B9
0x180003019  mov     r13, [rdi+50h]
0x18000301d  xor     esi, esi
0x18000301f  cmp     [rbp+2Ch], rdx
0x180003023  jnz     short loc_18000306A
0x180003025  cmp     [rbp+34h], rcx
0x180003029  jnz     short loc_18000306A
0x18000302b  mov     rdx, [rbp+50h]; struct _MFVIDEOFORMAT *
0x18000302f  lea     rcx, [rsp+58h+arg_18]; struct tagVIDEOINFOHEADER **
0x180003034  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180003039  mov     r15, [rsp+58h+arg_18]
0x18000303e  mov     ebx, eax
0x180003040  test    eax, eax
0x180003042  js      loc_1800031BE
0x180003048  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000304f  lea     rbp, [r15+30h]
0x180003053  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000305a  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180003061  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180003068  jmp     short loc_180003092
0x18000306a  mov     rax, [rbp+2Ch]
0x18000306e  sub     rax, r9
0x180003071  jnz     short loc_18000307A
0x180003073  mov     rax, [rbp+34h]
0x180003077  sub     rax, r8
0x18000307a  mov     rbp, [rbp+50h]
0x18000307e  test    rax, rax
0x180003081  setz    al
0x180003084  test    al, al
0x180003086  jz      short loc_18000308E
0x180003088  add     rbp, 30h ; '0'
0x18000308c  jmp     short loc_180003092
0x18000308e  add     rbp, 48h ; 'H'
0x180003092  cmp     [rdi+2Ch], rdx
0x180003096  jnz     short loc_18000309E
0x180003098  cmp     [rdi+34h], rcx
0x18000309c  jz      short loc_1800030AA
0x18000309e  cmp     [rdi+2Ch], r9
0x1800030a2  jnz     short loc_1800030BD
0x1800030a4  cmp     [rdi+34h], r8
0x1800030a8  jnz     short loc_1800030BD
0x1800030aa  lea     rax, [rsi+40h]
0x1800030ae  mov     [rsp+58h+lprc], rax
0x1800030b3  lea     r10, [rsi+38h]
0x1800030b7  lea     rax, [rsi+34h]
0x1800030bb  jmp     short loc_1800030CE
0x1800030bd  lea     rax, [r13+58h]
0x1800030c1  mov     [rsp+58h+lprc], rax
0x1800030c6  lea     r10, [r13+50h]
0x1800030ca  lea     rax, [r13+4Ch]
0x1800030ce  cmp     [rdi+2Ch], rdx
0x1800030d2  jnz     short loc_1800030DA
0x1800030d4  cmp     [rdi+34h], rcx
0x1800030d8  jz      short loc_1800030E9
0x1800030da  cmp     [rdi+2Ch], r9
0x1800030de  jnz     short loc_1800030E6
0x1800030e0  cmp     [rdi+34h], r8
0x1800030e4  jz      short loc_1800030E9
0x1800030e6  mov     rsi, r13
0x1800030e9  mov     edi, [rbp+8]
0x1800030ec  mov     rcx, rsi; lprc
0x1800030ef  mov     r13d, [r10]
0x1800030f2  neg     edi
0x1800030f4  mov     eax, [rax]
0x1800030f6  cmovs   edi, [rbp+8]
0x1800030fa  neg     r13d
0x1800030fd  mov     r12d, [rbp+4]
0x180003101  cmovs   r13d, [r10]
0x180003105  mov     [rsp+58h+arg_10], eax
0x180003109  call    cs:__imp_IsRectEmpty
0x18000310f  test    eax, eax
0x180003111  jnz     short loc_180003137
0x180003113  cmp     r12d, [rsi+8]
0x180003117  jnz     loc_1800031B9
0x18000311d  cmp     [rsi], eax
0x18000311f  jnz     loc_1800031B9
0x180003125  cmp     edi, [rsi+0Ch]
0x180003128  jnz     loc_1800031B9
0x18000312e  cmp     [rsi+4], eax
0x180003131  jnz     loc_1800031B9
0x180003137  lea     rcx, [rsi+10h]; lprc
0x18000313b  call    cs:__imp_IsRectEmpty
0x180003141  test    eax, eax
0x180003143  jnz     short loc_18000315A
0x180003145  cmp     r12d, [rsi+18h]
0x180003149  jnz     short loc_1800031B9
0x18000314b  cmp     [rsi+10h], eax
0x18000314e  jnz     short loc_1800031B9
0x180003150  cmp     edi, [rsi+1Ch]
0x180003153  jnz     short loc_1800031B9
0x180003155  cmp     [rsi+14h], eax
0x180003158  jnz     short loc_1800031B9
0x18000315a  cmp     [rsp+58h+arg_10], r12d
0x18000315f  jl      short loc_1800031B9
0x180003161  cmp     r13d, edi
0x180003164  jl      short loc_1800031B9
0x180003166  mov     rax, [rsp+58h+lprc]
0x18000316b  cmp     dword ptr [rax], 59565955h
0x180003171  jz      short loc_1800031AD
0x180003173  cmp     dword ptr [rax], 32595559h
0x180003179  jz      short loc_1800031AD
0x18000317b  cmp     dword ptr [rax], 55595659h
0x180003181  jz      short loc_1800031AD
0x180003183  cmp     dword ptr [rax], 32315659h
0x180003189  jz      short loc_18000319B
0x18000318b  cmp     dword ptr [rax], 3131564Eh
0x180003191  jz      short loc_18000319B
0x180003193  cmp     dword ptr [rax], 3231564Eh
0x180003199  jnz     short loc_1800031BE
0x18000319b  mov     eax, [rbp+8]
0x18000319e  neg     eax
0x1800031a0  cmovs   eax, [rbp+8]
0x1800031a4  cmp     eax, 2
0x1800031a7  jl      short loc_1800031B9
0x1800031a9  test    al, 1
0x1800031ab  jnz     short loc_1800031B9
0x1800031ad  cmp     dword ptr [rbp+4], 2
0x1800031b1  jl      short loc_1800031B9
0x1800031b3  test    byte ptr [rbp+4], 1
0x1800031b7  jz      short loc_1800031BE
0x1800031b9  mov     ebx, 80040205h
0x1800031be  test    r15, r15
0x1800031c1  jz      short loc_1800031CB
0x1800031c3  mov     rcx, r15; void *
0x1800031c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800031cb  test    r14, r14
0x1800031ce  jz      short loc_1800031D8
0x1800031d0  mov     rcx, r14; void *
0x1800031d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800031d8  mov     eax, ebx
0x1800031da  mov     rbx, [rsp+58h+arg_0]
0x1800031df  add     rsp, 20h
0x1800031e3  pop     r15
0x1800031e5  pop     r14
0x1800031e7  pop     r13
0x1800031e9  pop     r12
0x1800031eb  pop     rdi
0x1800031ec  pop     rsi
0x1800031ed  pop     rbp
0x1800031ee  retn
```
