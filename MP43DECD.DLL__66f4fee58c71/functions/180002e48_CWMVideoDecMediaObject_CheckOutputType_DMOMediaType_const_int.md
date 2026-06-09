# CWMVideoDecMediaObject::CheckOutputType(_DMOMediaType const *,int)

- ea: `0x180002e48`
- end: `0x18000312f`
- name: `?CheckOutputType@CWMVideoDecMediaObject@@IEAAJPEBU_DMOMediaType@@H@Z`
- size: `743`
- prototype: `int(CWMVideoDecMediaObject *__hidden this, const struct _DMOMediaType *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007f20`

## callees

- `0x180001420`
- `0x180002e48`
- `0x180003138`
- `0x180003534`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180003049`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18000307b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180003049`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18000307b`

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
  v6 = CheckType(a2, (const struct _GUID *const *)&off_180027020, 9u);
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
0x180002e48  mov     rax, rsp
0x180002e4b  mov     [rax+8], rbx
0x180002e4f  mov     [rax+18h], r8d
0x180002e53  push    rbp
0x180002e54  push    rsi
0x180002e55  push    rdi
0x180002e56  push    r12
0x180002e58  push    r13
0x180002e5a  push    r14
0x180002e5c  push    r15
0x180002e5e  sub     rsp, 20h
0x180002e62  xor     r15d, r15d
0x180002e65  xor     r14d, r14d
0x180002e68  mov     [rax+20h], r15
0x180002e6c  mov     rdi, rdx
0x180002e6f  mov     [rax+10h], r14
0x180002e73  test    rdx, rdx
0x180002e76  jnz     short loc_180002E82
0x180002e78  mov     ebx, 80004003h
0x180002e7d  jmp     loc_180003118
0x180002e82  mov     eax, [rcx+38h]
0x180002e85  add     rcx, 40h ; '@'
0x180002e89  neg     eax
0x180002e8b  sbb     rbp, rbp
0x180002e8e  and     rbp, rcx
0x180002e91  jnz     short loc_180002E9D
0x180002e93  mov     ebx, 80040203h
0x180002e98  jmp     loc_180003118
0x180002e9d  mov     r8d, 9; unsigned int
0x180002ea3  lea     rdx, off_180027020; struct _GUID **
0x180002eaa  mov     rcx, rdi; struct _DMOMediaType *
0x180002ead  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x180002eb2  mov     ebx, eax
0x180002eb4  test    eax, eax
0x180002eb6  js      loc_180003118
0x180002ebc  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180002ec3  xor     r13d, r13d
0x180002ec6  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180002ecd  cmp     [rdi+2Ch], rdx
0x180002ed1  jnz     short loc_180002F17
0x180002ed3  cmp     [rdi+34h], rcx
0x180002ed7  jnz     short loc_180002F17
0x180002ed9  mov     rdx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x180002edd  lea     rcx, [rsp+58h+lprc]; struct tagVIDEOINFOHEADER **
0x180002ee2  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180002ee7  mov     r14, [rsp+58h+lprc]
0x180002eec  mov     ebx, eax
0x180002eee  test    eax, eax
0x180002ef0  js      loc_18000310B
0x180002ef6  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180002efd  mov     rsi, r14
0x180002f00  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180002f07  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180002f0e  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180002f15  jmp     short loc_180002F5F
0x180002f17  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180002f1e  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180002f25  cmp     [rdi+2Ch], r9
0x180002f29  jnz     short loc_180002F37
0x180002f2b  cmp     [rdi+34h], r8
0x180002f2f  jnz     short loc_180002F37
0x180002f31  mov     rsi, [rdi+50h]
0x180002f35  jmp     short loc_180002F5F
0x180002f37  mov     rax, [rdi+2Ch]
0x180002f3b  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180002f42  jnz     loc_1800030F9
0x180002f48  mov     rax, [rdi+34h]
0x180002f4c  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180002f53  jnz     loc_1800030F9
0x180002f59  mov     r13, [rdi+50h]
0x180002f5d  xor     esi, esi
0x180002f5f  cmp     [rbp+2Ch], rdx
0x180002f63  jnz     short loc_180002FAA
0x180002f65  cmp     [rbp+34h], rcx
0x180002f69  jnz     short loc_180002FAA
0x180002f6b  mov     rdx, [rbp+50h]; struct _MFVIDEOFORMAT *
0x180002f6f  lea     rcx, [rsp+58h+arg_18]; struct tagVIDEOINFOHEADER **
0x180002f74  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180002f79  mov     r15, [rsp+58h+arg_18]
0x180002f7e  mov     ebx, eax
0x180002f80  test    eax, eax
0x180002f82  js      loc_1800030FE
0x180002f88  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180002f8f  lea     rbp, [r15+30h]
0x180002f93  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180002f9a  mov     r8, qword ptr cs:FORMAT_VideoInfo.Data4
0x180002fa1  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180002fa8  jmp     short loc_180002FD2
0x180002faa  mov     rax, [rbp+2Ch]
0x180002fae  sub     rax, r9
0x180002fb1  jnz     short loc_180002FBA
0x180002fb3  mov     rax, [rbp+34h]
0x180002fb7  sub     rax, r8
0x180002fba  mov     rbp, [rbp+50h]
0x180002fbe  test    rax, rax
0x180002fc1  setz    al
0x180002fc4  test    al, al
0x180002fc6  jz      short loc_180002FCE
0x180002fc8  add     rbp, 30h ; '0'
0x180002fcc  jmp     short loc_180002FD2
0x180002fce  add     rbp, 48h ; 'H'
0x180002fd2  cmp     [rdi+2Ch], rdx
0x180002fd6  jnz     short loc_180002FDE
0x180002fd8  cmp     [rdi+34h], rcx
0x180002fdc  jz      short loc_180002FEA
0x180002fde  cmp     [rdi+2Ch], r9
0x180002fe2  jnz     short loc_180002FFD
0x180002fe4  cmp     [rdi+34h], r8
0x180002fe8  jnz     short loc_180002FFD
0x180002fea  lea     rax, [rsi+40h]
0x180002fee  mov     [rsp+58h+lprc], rax
0x180002ff3  lea     r10, [rsi+38h]
0x180002ff7  lea     rax, [rsi+34h]
0x180002ffb  jmp     short loc_18000300E
0x180002ffd  lea     rax, [r13+58h]
0x180003001  mov     [rsp+58h+lprc], rax
0x180003006  lea     r10, [r13+50h]
0x18000300a  lea     rax, [r13+4Ch]
0x18000300e  cmp     [rdi+2Ch], rdx
0x180003012  jnz     short loc_18000301A
0x180003014  cmp     [rdi+34h], rcx
0x180003018  jz      short loc_180003029
0x18000301a  cmp     [rdi+2Ch], r9
0x18000301e  jnz     short loc_180003026
0x180003020  cmp     [rdi+34h], r8
0x180003024  jz      short loc_180003029
0x180003026  mov     rsi, r13
0x180003029  mov     edi, [rbp+8]
0x18000302c  mov     rcx, rsi; lprc
0x18000302f  mov     r13d, [r10]
0x180003032  neg     edi
0x180003034  mov     eax, [rax]
0x180003036  cmovs   edi, [rbp+8]
0x18000303a  neg     r13d
0x18000303d  mov     r12d, [rbp+4]
0x180003041  cmovs   r13d, [r10]
0x180003045  mov     [rsp+58h+arg_10], eax
0x180003049  call    cs:__imp_IsRectEmpty
0x18000304f  test    eax, eax
0x180003051  jnz     short loc_180003077
0x180003053  cmp     r12d, [rsi+8]
0x180003057  jnz     loc_1800030F9
0x18000305d  cmp     [rsi], eax
0x18000305f  jnz     loc_1800030F9
0x180003065  cmp     edi, [rsi+0Ch]
0x180003068  jnz     loc_1800030F9
0x18000306e  cmp     [rsi+4], eax
0x180003071  jnz     loc_1800030F9
0x180003077  lea     rcx, [rsi+10h]; lprc
0x18000307b  call    cs:__imp_IsRectEmpty
0x180003081  test    eax, eax
0x180003083  jnz     short loc_18000309A
0x180003085  cmp     r12d, [rsi+18h]
0x180003089  jnz     short loc_1800030F9
0x18000308b  cmp     [rsi+10h], eax
0x18000308e  jnz     short loc_1800030F9
0x180003090  cmp     edi, [rsi+1Ch]
0x180003093  jnz     short loc_1800030F9
0x180003095  cmp     [rsi+14h], eax
0x180003098  jnz     short loc_1800030F9
0x18000309a  cmp     [rsp+58h+arg_10], r12d
0x18000309f  jl      short loc_1800030F9
0x1800030a1  cmp     r13d, edi
0x1800030a4  jl      short loc_1800030F9
0x1800030a6  mov     rax, [rsp+58h+lprc]
0x1800030ab  cmp     dword ptr [rax], 59565955h
0x1800030b1  jz      short loc_1800030ED
0x1800030b3  cmp     dword ptr [rax], 32595559h
0x1800030b9  jz      short loc_1800030ED
0x1800030bb  cmp     dword ptr [rax], 55595659h
0x1800030c1  jz      short loc_1800030ED
0x1800030c3  cmp     dword ptr [rax], 32315659h
0x1800030c9  jz      short loc_1800030DB
0x1800030cb  cmp     dword ptr [rax], 3131564Eh
0x1800030d1  jz      short loc_1800030DB
0x1800030d3  cmp     dword ptr [rax], 3231564Eh
0x1800030d9  jnz     short loc_1800030FE
0x1800030db  mov     eax, [rbp+8]
0x1800030de  neg     eax
0x1800030e0  cmovs   eax, [rbp+8]
0x1800030e4  cmp     eax, 2
0x1800030e7  jl      short loc_1800030F9
0x1800030e9  test    al, 1
0x1800030eb  jnz     short loc_1800030F9
0x1800030ed  cmp     dword ptr [rbp+4], 2
0x1800030f1  jl      short loc_1800030F9
0x1800030f3  test    byte ptr [rbp+4], 1
0x1800030f7  jz      short loc_1800030FE
0x1800030f9  mov     ebx, 80040205h
0x1800030fe  test    r15, r15
0x180003101  jz      short loc_18000310B
0x180003103  mov     rcx, r15; void *
0x180003106  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000310b  test    r14, r14
0x18000310e  jz      short loc_180003118
0x180003110  mov     rcx, r14; void *
0x180003113  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003118  mov     eax, ebx
0x18000311a  mov     rbx, [rsp+58h+arg_0]
0x18000311f  add     rsp, 20h
0x180003123  pop     r15
0x180003125  pop     r14
0x180003127  pop     r13
0x180003129  pop     r12
0x18000312b  pop     rdi
0x18000312c  pop     rsi
0x18000312d  pop     rbp
0x18000312e  retn
```
