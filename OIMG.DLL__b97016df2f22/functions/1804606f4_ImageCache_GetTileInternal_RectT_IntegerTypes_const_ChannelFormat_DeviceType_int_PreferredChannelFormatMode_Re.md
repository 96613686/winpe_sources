# ImageCache::GetTileInternal(RectT<IntegerTypes> const &,ChannelFormat,DeviceType,int,PreferredChannelFormatMode,RectT<IntegerTypes> const &,TileStatus,IImageBuffer * *)

- ea: `0x1804606f4`
- end: `0x18046109d`
- name: `?GetTileInternal@ImageCache@@AEAAXAEBU?$RectT@UIntegerTypes@@@@W4ChannelFormat@@W4DeviceType@@HW4PreferredChannelFormatMode@@0W4TileStatus@@PEAPEAUIImageBuffer@@@Z`
- size: `2473`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18046160c`

## callees

- `0x18001db0c`
- `0x1801cecd0`
- `0x1802268ec`
- `0x18045fcb8`
- `0x18045fdac`
- `0x18045fe68`
- `0x18045ff6c`
- `0x1804606f4`
- `0x1804610a0`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180460a9b`
- `OLEAUT32!__imp_VariantInit` at `0x180460a9b`
- `OLEAUT32!__imp_VariantClear` at `0x180460b22`
- `OLEAUT32!__imp_VariantClear` at `0x180460b22`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804608ba`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804608ba`
- `GDI32!CombineRgn` at `0x180460ce1`
- `GDI32!CombineRgn` at `0x180460ec8`
- `GDI32!CombineRgn` at `0x180460ce1`
- `GDI32!CombineRgn` at `0x180460ec8`
- `GDI32!GetRgnBox` at `0x180460d45`
- `GDI32!GetRgnBox` at `0x180460d45`
- `GDI32!RectInRegion` at `0x180460bbd`
- `GDI32!RectInRegion` at `0x180460bbd`
- `GDI32!CreateRectRgn` at `0x180460db8`
- `GDI32!CreateRectRgn` at `0x180460db8`
- `GDI32!DeleteObject` at `0x180460cef`
- `GDI32!DeleteObject` at `0x180460ed8`
- `GDI32!DeleteObject` at `0x180460f90`
- `GDI32!DeleteObject` at `0x180460fb2`
- `GDI32!DeleteObject` at `0x180460cef`
- `GDI32!DeleteObject` at `0x180460ed8`
- `GDI32!DeleteObject` at `0x180460f90`
- `GDI32!DeleteObject` at `0x180460fb2`
- `GDI32!CreateRectRgnIndirect` at `0x180460b2b`
- `GDI32!CreateRectRgnIndirect` at `0x180460cc9`
- `GDI32!CreateRectRgnIndirect` at `0x180460eae`
- `GDI32!CreateRectRgnIndirect` at `0x180460b2b`
- `GDI32!CreateRectRgnIndirect` at `0x180460cc9`
- `GDI32!CreateRectRgnIndirect` at `0x180460eae`

## string_xrefs

- `0x180460a28`: `CacheTexture`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ImageCache::GetTileInternal(
        int *a1,
        const RECT *a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6,
        int *a7,
        int a8,
        struct IImageBuffer **a9)
{
  ImageCache *v11; // r10
  __int64 v12; // r14
  _DWORD *v13; // r13
  unsigned __int64 v14; // r15
  __int64 v15; // rsi
  _DWORD *v16; // rdx
  __int64 v17; // r11
  __int64 v18; // r10
  __int64 v19; // r9
  __int64 v20; // r8
  int bottom; // r15d
  int right; // ecx
  LONG top; // r13d
  LONG left; // eax
  int v26; // eax
  void *v27; // rbx
  unsigned __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // esi
  int v31; // ecx
  __int64 v32; // r8
  _DWORD *v33; // rdx
  int v34; // eax
  int v35; // eax
  __int64 (__fastcall *v36)(struct IImageBuffer *, _QWORD, unsigned __int64, RECT *); // r10
  __int64 v37; // r8
  __int64 v38; // rdx
  int v39; // eax
  HRGN RectRgnIndirect; // rdi
  int v41; // esi
  LONG *v42; // rbx
  __int64 v43; // rdx
  __int64 v44; // r8
  LONG v45; // ecx
  LONG v46; // edx
  LONG v47; // eax
  LONG v48; // r8d
  int v49; // eax
  __int64 (__fastcall *v50)(struct IImageBuffer *, __int64, _QWORD, unsigned __int64); // r10
  __int64 v51; // r9
  __int64 v52; // r8
  int v53; // eax
  HRGN v54; // r13
  int v55; // eax
  double v56; // xmm6_8
  HRGN RectRgn; // rbx
  ImageCache *v58; // rax
  int v59; // esi
  unsigned __int64 v60; // r13
  __int64 v61; // r14
  __int64 v62; // rax
  LONG v63; // r10d
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // rdx
  LONG v67; // r8d
  int v68; // r11d
  int v69; // ecx
  LONG v70; // eax
  LONG v71; // eax
  char v73; // al
  struct IImageBuffer *v74; // rax
  struct IImageBuffer *v75; // rcx
  struct IImageBuffer *v77; // [rsp+40h] [rbp-C8h] BYREF
  HGDIOBJ v78; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v79; // [rsp+50h] [rbp-B8h] BYREF
  ImageCache *v80; // [rsp+58h] [rbp-B0h]
  __int64 v81; // [rsp+60h] [rbp-A8h]
  HGDIOBJ ho; // [rsp+68h] [rbp-A0h]
  struct IImageBuffer **v83; // [rsp+70h] [rbp-98h]
  void *Block; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v85; // [rsp+80h] [rbp-88h]
  __int64 v86; // [rsp+88h] [rbp-80h]
  int v87; // [rsp+90h] [rbp-78h]
  HRGN v88; // [rsp+98h] [rbp-70h]
  RECT rect; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *pRecInfo; // [rsp+B8h] [rbp-50h]
  RECT v91; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-30h] BYREF
  _DWORD v93[3]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v94; // [rsp+FCh] [rbp-Ch]
  int v95; // [rsp+104h] [rbp-4h]
  int v96; // [rsp+108h] [rbp+0h]
  int v97; // [rsp+118h] [rbp+10h] BYREF
  wchar_t v98[70]; // [rsp+11Ch] [rbp+14h] BYREF

  v11 = (ImageCache *)a1;
  v80 = (ImageCache *)a1;
  v83 = a9;
  v12 = 0;
  v13 = 0;
  Block = 0;
  v14 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  if ( a1[32] > 0 )
  {
    v81 = a1[32];
    v15 = 0;
    while ( 1 )
    {
      if ( v12 < 0 )
        goto LABEL_139;
      if ( (unsigned __int64)v15 >= *((_QWORD *)v11 + 16) )
        goto LABEL_141;
      v16 = (_DWORD *)(v12 + *((_QWORD *)v11 + 15));
      v17 = (int)v16[7];
      v18 = (int)v16[8];
      v19 = v17 + (int)v16[9];
      if ( (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_137;
      v20 = v18 + (int)v16[10];
      if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_137;
      bottom = a2->bottom;
      if ( bottom >= (int)v20 )
        bottom = v18 + v16[10];
      right = a2->right;
      if ( right >= (int)v19 )
        right = v17 + v16[9];
      top = v16[8];
      if ( a2->top > (int)v18 )
        top = a2->top;
      left = v16[7];
      if ( a2->left > (int)v17 )
        left = a2->left;
      if ( left < right && top < bottom )
      {
        if ( *(_OWORD *)a2 == __PAIR128__(__PAIR64__(v20, v19), __PAIR64__(v18, v17))
          && a3 == v16[4]
          && a4 == v16[5]
          && a5 == v16[6] )
        {
          v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IImageBuffer **))(**(_QWORD **)v16 + 56LL))(
                  *(_QWORD *)v16,
                  1,
                  v83);
          if ( v26 < 0 )
            ATL::BaseAtlThrow(v26);
          if ( *v83 )
          {
            v27 = Block;
            if ( !Block )
              return;
            v28 = v85;
LABEL_28:
            ATL::CAtlArray<ImageBufferInUseInfo,ATL::CElementTraits<ImageBufferInUseInfo>>::CallDestructors(v27, v28);
            free(v27);
            return;
          }
        }
        else
        {
          ImageCache::InsertTile(&Block, v16, a2, a4);
        }
      }
      ++v15;
      v12 += 48;
      v11 = v80;
      if ( v15 >= v81 )
      {
        v14 = v85;
        v13 = Block;
        LOBYTE(v12) = 0;
        break;
      }
    }
  }
  v93[0] = a3;
  v93[1] = a4;
  v93[2] = a5;
  v94 = *(_QWORD *)&a2->left;
  v29 = a2->bottom - (__int64)a2->top;
  if ( (unsigned __int64)(v29 + 0x80000000LL) > 0xFFFFFFFF
    || (unsigned __int64)(a2->right - (__int64)a2->left + 0x80000000LL) > 0xFFFFFFFF )
  {
LABEL_137:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v95 = a2->right - a2->left;
  v96 = v29;
  if ( !a6 )
  {
    if ( (_DWORD)v14 )
    {
      if ( !v14 )
LABEL_141:
        ATL::BaseAtlThrow(-2147024809);
      v30 = v13[4];
      v31 = 1;
      if ( (int)v14 > 1LL )
      {
        v32 = 1;
        v33 = v13 + 16;
        while ( v31 >= 0 )
        {
          if ( v31 >= v14 )
            goto LABEL_141;
          if ( *v33 != v30 )
            goto LABEL_48;
          ++v31;
          ++v32;
          v33 += 12;
          if ( v32 >= (int)v14 )
            goto LABEL_44;
        }
LABEL_139:
        ATL::BaseAtlThrow(-2147024809);
      }
LABEL_44:
      if ( v30 != 2 )
        goto LABEL_47;
      LODWORD(v79) = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v11 + 19) + 216LL))(
              *((_QWORD *)v11 + 19),
              2,
              &v79);
      if ( v34 < 0 )
        ATL::BaseAtlThrow(v34);
      if ( (_DWORD)v79 )
LABEL_47:
        a3 = v30;
    }
LABEL_48:
    v93[0] = a3;
  }
  v77 = 0;
  v97 = -1;
  StringCchCopyW(v98, 0x40u, L"CacheTexture");
  v35 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, int *, _QWORD, struct IImageBuffer **))(**((_QWORD **)v80 + 19)
                                                                                           + 64LL))(
          *((_QWORD *)v80 + 19),
          v93,
          &v97,
          0,
          &v77);
  if ( v35 < 0 )
    ATL::BaseAtlThrow(v35);
  if ( *a7 < a7[2] && a7[1] < a7[3] )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v36 = *(__int64 (__fastcall **)(struct IImageBuffer *, _QWORD, unsigned __int64, RECT *))(*(_QWORD *)v77 + 96LL);
    v37 = a7[3] - (__int64)a7[1];
    if ( (unsigned __int64)(v37 + 0x80000000LL) > 0xFFFFFFFF
      || (v38 = a7[2] - (__int64)*a7, (unsigned __int64)(v38 + 0x80000000LL) > 0xFFFFFFFF) )
    {
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    v78 = (HGDIOBJ)__PAIR64__(v37, v38);
    rect = *(RECT *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v39 = v36(v77, *(_QWORD *)a7, __PAIR64__(v37, v38), &rect);
    if ( v39 < 0 )
      ATL::BaseAtlThrow(v39);
    LOBYTE(v12) = 1;
    VariantClear(&pvarg);
  }
  RectRgnIndirect = CreateRectRgnIndirect(a2);
  v88 = RectRgnIndirect;
  v41 = 0;
  if ( (int)v14 > 0 )
  {
    ho = (HGDIOBJ)(int)v14;
    v81 = 0;
    v42 = v13 + 8;
    do
    {
      if ( v41 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v41 >= v14 )
        ATL::BaseAtlThrow(-2147024809);
      rect.left = *(v42 - 1);
      v43 = *v42;
      rect.top = *v42;
      v44 = v42[2];
      if ( (unsigned __int64)(v42[1] + (__int64)rect.left + 0x80000000LL) > 0xFFFFFFFF
        || (rect.right = v42[1] + rect.left, (unsigned __int64)(v44 + v43 + 0x80000000LL) > 0xFFFFFFFF) )
      {
        safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
      }
      rect.bottom = v44 + v43;
      if ( RectInRegion(RectRgnIndirect, &rect) )
      {
        v45 = a2->left;
        v46 = a2->top;
        v47 = a2->right;
        v48 = a2->bottom;
        if ( a2->left <= rect.left )
          v45 = rect.left;
        v91.left = v45;
        if ( v46 <= rect.top )
          v46 = rect.top;
        v91.top = v46;
        if ( v47 >= rect.right )
          v47 = rect.right;
        v91.right = v47;
        if ( v48 >= rect.bottom )
          v48 = rect.bottom;
        v91.bottom = v48;
        if ( v45 > v47 || v46 > v48 )
        {
          *(_QWORD *)&v91.right = 0;
          *(_QWORD *)&v91.left = 0;
        }
        v79 = 0;
        if ( v41 >= v14 )
LABEL_148:
          ATL::BaseAtlThrow(-2147024809);
        v49 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v42 - 4) + 56LL))(
                *((_QWORD *)v42 - 4),
                1,
                &v79);
        if ( v49 < 0 )
          ATL::BaseAtlThrow(v49);
        v50 = *(__int64 (__fastcall **)(struct IImageBuffer *, __int64, _QWORD, unsigned __int64))(*(_QWORD *)v77 + 112LL);
        v51 = v91.bottom - (__int64)v91.top;
        if ( (unsigned __int64)(v51 + 0x80000000LL) > 0xFFFFFFFF
          || (v52 = v91.right - (__int64)v91.left, (unsigned __int64)(v52 + 0x80000000LL) > 0xFFFFFFFF) )
        {
          safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
        }
        v78 = (HGDIOBJ)__PAIR64__(v51, v52);
        v53 = v50(v77, v79, *(_QWORD *)&v91.left, __PAIR64__(v51, v52));
        if ( v53 < 0 )
          ATL::BaseAtlThrow(v53);
        v54 = CreateRectRgnIndirect(&v91);
        CombineRgn(RectRgnIndirect, RectRgnIndirect, v54, 4);
        if ( v54 )
          DeleteObject(v54);
        if ( (_BYTE)v12 )
          goto LABEL_84;
        if ( v41 >= v14 )
          goto LABEL_148;
        LOBYTE(v12) = 0;
        if ( *((_BYTE *)v42 + 12) )
LABEL_84:
          LOBYTE(v12) = 1;
        if ( v79 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      }
      else
      {
        *(_OWORD *)&pvarg.vt = 0u;
        GetRgnBox(RectRgnIndirect, (LPRECT)&pvarg);
        if ( *(int *)&pvarg.vt >= pvarg.lVal || (int)pvarg.decVal.Hi32 >= pvarg.cyVal.Hi )
          break;
      }
      ++v41;
      ++v81;
      v42 += 12;
    }
    while ( v81 < (__int64)ho );
  }
  if ( !(_BYTE)v12 )
  {
    v55 = (*(__int64 (__fastcall **)(struct IImageBuffer *, __int64))(*(_QWORD *)v77 + 80LL))(v77, 1);
    if ( v55 <= -1 )
      ATL::BaseAtlThrow(v55);
  }
  if ( !a8 )
  {
    v56 = 0.0;
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v78 = RectRgn;
    v58 = v80;
    v59 = *((_DWORD *)v80 + 32) - 1;
    if ( v59 >= 0 )
    {
      v60 = v59;
      v61 = 48LL * v59;
      while ( 1 )
      {
        if ( v60 >= *((_QWORD *)v58 + 16) )
          ATL::BaseAtlThrow(-2147024809);
        v62 = *((_QWORD *)v58 + 15);
        if ( *(_DWORD *)(v61 + v62 + 20) == a4 )
        {
          rect.left = *(_DWORD *)(v61 + v62 + 28);
          v63 = rect.left;
          v64 = *(int *)(v61 + v62 + 32);
          rect.top = *(_DWORD *)(v61 + v62 + 32);
          v65 = *(int *)(v61 + v62 + 40);
          v66 = rect.left + (__int64)*(int *)(v61 + v62 + 36);
          if ( (unsigned __int64)(v66 + 0x80000000LL) > 0xFFFFFFFF
            || (rect.right = rect.left + *(_DWORD *)(v61 + v62 + 36),
                v67 = v64 + v65,
                (unsigned __int64)(v64 + v65 + 0x80000000LL) > 0xFFFFFFFF) )
          {
            safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
          }
          rect.bottom = v64 + v65;
          v68 = a2->bottom;
          if ( v68 >= v67 )
            v68 = v64 + v65;
          v69 = a2->right;
          if ( v69 >= (int)v66 )
            v69 = v66;
          v70 = v64;
          if ( a2->top > (int)v64 )
            v70 = a2->top;
          LODWORD(v79) = v70;
          v71 = rect.left;
          if ( a2->left > rect.left )
            v71 = a2->left;
          if ( v71 < v69 && (int)v79 < v68 )
          {
            ho = CreateRectRgnIndirect(&rect);
            CombineRgn(RectRgn, RectRgn, (HRGN)ho, 2);
            if ( ho )
              DeleteObject(ho);
            v63 = rect.left;
            LODWORD(v64) = rect.top;
            LODWORD(v66) = rect.right;
            v67 = rect.bottom;
          }
          if ( v63 >= (int)v66
            || (int)v64 >= v67
            || a2->left <= v63 && a2->right >= (int)v66 && a2->top <= (int)v64 && a2->bottom >= v67 )
          {
            if ( (unsigned __int64)v59 >= *((_QWORD *)v80 + 16) )
              ATL::BaseAtlThrow(-2147024809);
            v56 = v56 + ImageBufferInUseInfo::GetByteSize((ImageBufferInUseInfo *)(*((_QWORD *)v80 + 15) + 48LL * v59));
          }
        }
        --v60;
        v61 -= 48;
        if ( --v59 < 0 )
          break;
        v58 = v80;
      }
    }
    if ( v56 >= ImageCache::GetByteSize(v77) || (v73 = RegionHandle::Contains(&v78, a2), RectRgn = (HRGN)v78, !v73) )
      ImageCache::AddTile(v80, v77);
    if ( RectRgn )
      DeleteObject(RectRgn);
  }
  v74 = v77;
  v75 = 0;
  v77 = 0;
  *v83 = v74;
  if ( RectRgnIndirect )
  {
    DeleteObject(RectRgnIndirect);
    v75 = v77;
  }
  if ( v75 )
    (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v75 + 16LL))(v75);
  v27 = Block;
  if ( Block )
  {
    v28 = v14;
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x1804606f4  mov     rax, rsp
0x1804606f7  push    rbp
0x1804606f8  push    rbx
0x1804606f9  push    rsi
0x1804606fa  push    rdi
0x1804606fb  push    r12
0x1804606fd  push    r13
0x1804606ff  push    r14
0x180460701  push    r15
0x180460703  lea     rbp, [rax-108h]
0x18046070a  sub     rsp, 1C8h
0x180460711  movaps  xmmword ptr [rax-58h], xmm6
0x180460715  mov     rax, cs:__security_cookie
0x18046071c  xor     rax, rsp
0x18046071f  mov     [rbp+100h+var_60], rax
0x180460726  mov     dword ptr [rsp+200h+var_1D0], r9d
0x18046072b  mov     ebx, r8d
0x18046072e  mov     r12, rdx
0x180460731  mov     r10, rcx
0x180460734  mov     [rsp+200h+var_1B0], rcx
0x180460739  mov     rdi, [rbp+100h+arg_30]
0x180460740  mov     rax, [rbp+100h+arg_40]
0x180460747  mov     [rsp+200h+var_198], rax
0x18046074c  xor     r14d, r14d
0x18046074f  mov     r13d, r14d
0x180460752  mov     [rsp+200h+Block], r14
0x180460757  mov     r15d, r14d
0x18046075a  mov     [rsp+200h+var_188], r14
0x18046075f  mov     [rbp+100h+var_180], r14
0x180460763  mov     [rbp+100h+var_178], r14d
0x180460767  movsxd  rax, dword ptr [rcx+80h]
0x18046076e  mov     esi, 80000000h
0x180460773  mov     r8d, 0FFFFFFFFh
0x180460779  test    eax, eax
0x18046077b  jle     loc_18046092A
0x180460781  mov     [rsp+200h+var_1A8], rax
0x180460786  mov     esi, r14d
0x180460789  test    r14, r14
0x18046078c  js      loc_180460FFF
0x180460792  cmp     rsi, [r10+80h]
0x180460799  jnb     loc_180461012
0x18046079f  mov     rdx, [r10+78h]
0x1804607a3  add     rdx, r14
0x1804607a6  movsxd  r11, dword ptr [rdx+1Ch]
0x1804607aa  movsxd  r10, dword ptr [rdx+20h]
0x1804607ae  movsxd  r9, dword ptr [rdx+24h]
0x1804607b2  add     r9, r11
0x1804607b5  mov     ecx, 80000000h
0x1804607ba  lea     rax, [rcx+r9]
0x1804607be  cmp     rax, r8
0x1804607c1  ja      loc_180460FF1
0x1804607c7  movsxd  r8, dword ptr [rdx+28h]
0x1804607cb  add     r8, r10
0x1804607ce  lea     rax, [r8+rcx]
0x1804607d2  mov     ecx, 0FFFFFFFFh
0x1804607d7  cmp     rax, rcx
0x1804607da  ja      loc_180460FF1
0x1804607e0  mov     r15d, [r12+0Ch]
0x1804607e5  cmp     r15d, r8d
0x1804607e8  cmovge  r15d, r8d
0x1804607ec  mov     ecx, [r12+8]
0x1804607f1  cmp     ecx, r9d
0x1804607f4  cmovge  ecx, r9d
0x1804607f8  mov     r13d, r10d
0x1804607fb  cmp     [r12+4], r10d
0x180460800  cmovg   r13d, [r12+4]
0x180460806  mov     eax, r11d
0x180460809  cmp     [r12], r11d
0x18046080d  cmovg   eax, [r12]
0x180460812  cmp     eax, ecx
0x180460814  jge     short loc_18046081F
0x180460816  cmp     r13d, r15d
0x180460819  jge     short loc_18046081F
0x18046081b  mov     al, 1
0x18046081d  jmp     short loc_180460821
0x18046081f  xor     al, al
0x180460821  test    al, al
0x180460823  jz      loc_1804608FB
0x180460829  mov     ecx, dword ptr [rsp+200h+var_1D0]
0x18046082d  cmp     [r12], r11d
0x180460831  jnz     loc_1804608EB
0x180460837  cmp     [r12+4], r10d
0x18046083c  jnz     loc_1804608EB
0x180460842  cmp     [r12+8], r9d
0x180460847  jnz     loc_1804608EB
0x18046084d  cmp     [r12+0Ch], r8d
0x180460852  jnz     loc_1804608EB
0x180460858  cmp     ebx, [rdx+10h]
0x18046085b  jnz     loc_1804608EB
0x180460861  cmp     ecx, [rdx+14h]
0x180460864  jnz     loc_1804608EB
0x18046086a  mov     eax, [rbp+100h+arg_20]
0x180460870  cmp     eax, [rdx+18h]
0x180460873  jnz     short loc_1804608EB
0x180460875  mov     rcx, [rdx]
0x180460878  mov     rax, [rcx]
0x18046087b  mov     r15, [rsp+200h+var_198]
0x180460880  mov     r8, r15
0x180460883  mov     edx, 1
0x180460888  mov     rax, [rax+38h]
0x18046088c  call    cs:__guard_dispatch_icall_fptr
0x180460892  test    eax, eax
0x180460894  js      loc_180460FF7
0x18046089a  cmp     qword ptr [r15], 0
0x18046089e  jz      short loc_1804608FB
0x1804608a0  mov     rbx, [rsp+200h+Block]
0x1804608a5  test    rbx, rbx
0x1804608a8  jz      short loc_1804608C0
0x1804608aa  mov     rdx, [rsp+200h+var_188]
0x1804608af  mov     rcx, rbx
0x1804608b2  call    ?CallDestructors@?$CAtlArray@UImageBufferInUseInfo@@V?$CElementTraits@UImageBufferInUseInfo@@@ATL@@@ATL@@CAXPEAUImageBufferInUseInfo@@_K@Z; ATL::CAtlArray<ImageBufferInUseInfo,ATL::CElementTraits<ImageBufferInUseInfo>>::CallDestructors(ImageBufferInUseInfo *,unsigned __int64)
0x1804608b7  mov     rcx, rbx; Block
0x1804608ba  call    cs:__imp_free
0x1804608c0  mov     rcx, [rbp+100h+var_60]
0x1804608c7  xor     rcx, rsp; StackCookie
0x1804608ca  call    __security_check_cookie
0x1804608cf  movaps  xmm6, [rsp+200h+var_58+8]
0x1804608d7  add     rsp, 1C8h
0x1804608de  pop     r15
0x1804608e0  pop     r14
0x1804608e2  pop     r13
0x1804608e4  pop     r12
0x1804608e6  pop     rdi
0x1804608e7  pop     rsi
0x1804608e8  pop     rbx
0x1804608e9  pop     rbp
0x1804608ea  retn
0x1804608eb  mov     r9d, ecx
0x1804608ee  mov     r8, r12
0x1804608f1  lea     rcx, [rsp+200h+Block]
0x1804608f6  call    ?InsertTile@ImageCache@@CAXPEAV?$Array@UImageBufferInUseInfo@@V?$CElementTraits@UImageBufferInUseInfo@@@ATL@@@Base@@AEBUImageBufferInUseInfo@@AEBU?$RectT@UIntegerTypes@@@@W4DeviceType@@@Z; ImageCache::InsertTile(Base::Array<ImageBufferInUseInfo,ATL::CElementTraits<ImageBufferInUseInfo>> *,ImageBufferInUseInfo const &,RectT<IntegerTypes> const &,DeviceType)
0x1804608fb  inc     rsi
0x1804608fe  add     r14, 30h ; '0'
0x180460902  mov     r10, [rsp+200h+var_1B0]
0x180460907  mov     r8d, 0FFFFFFFFh
0x18046090d  cmp     rsi, [rsp+200h+var_1A8]
0x180460912  jl      loc_180460789
0x180460918  mov     r15, [rsp+200h+var_188]
0x18046091d  mov     r13, [rsp+200h+Block]
0x180460922  xor     r14d, r14d
0x180460925  mov     esi, 80000000h
0x18046092a  mov     [rbp+100h+var_118], ebx
0x18046092d  mov     eax, dword ptr [rsp+200h+var_1D0]
0x180460931  mov     [rbp+100h+var_114], eax
0x180460934  mov     eax, [rbp+100h+arg_20]
0x18046093a  mov     [rbp+100h+var_110], eax
0x18046093d  mov     rax, [r12]
0x180460941  mov     [rbp+100h+var_10C], rax
0x180460945  movsxd  rdx, dword ptr [r12+0Ch]
0x18046094a  movsxd  rax, dword ptr [r12+4]
0x18046094f  sub     rdx, rax
0x180460952  lea     rax, [rsi+rdx]
0x180460956  cmp     rax, r8
0x180460959  ja      loc_180460FF1
0x18046095f  movsxd  rcx, dword ptr [r12+8]
0x180460964  movsxd  rax, dword ptr [r12]
0x180460968  sub     rcx, rax
0x18046096b  lea     rax, [rsi+rcx]
0x18046096f  cmp     rax, r8
0x180460972  ja      loc_180460FF1
0x180460978  mov     [rbp+100h+var_104], ecx
0x18046097b  mov     [rbp+100h+var_100], edx
0x18046097e  cmp     [rbp+100h+arg_28], r14d
0x180460985  jnz     loc_180460A1C
0x18046098b  test    r15d, r15d
0x18046098e  jz      loc_180460A19
0x180460994  test    r15, r15
0x180460997  jz      loc_180461012
0x18046099d  mov     esi, [r13+10h]
0x1804609a1  mov     ecx, 1
0x1804609a6  movsxd  r9, r15d
0x1804609a9  cmp     r9, rcx
0x1804609ac  jle     short loc_1804609DB
0x1804609ae  mov     r8d, ecx
0x1804609b1  lea     rdx, [r13+40h]
0x1804609b5  test    ecx, ecx
0x1804609b7  js      loc_180460FFF
0x1804609bd  movsxd  rax, ecx
0x1804609c0  cmp     rax, r15
0x1804609c3  jnb     loc_180461012
0x1804609c9  cmp     [rdx], esi
0x1804609cb  jnz     short loc_180460A14
0x1804609cd  inc     ecx
0x1804609cf  inc     r8
0x1804609d2  add     rdx, 30h ; '0'
0x1804609d6  cmp     r8, r9
0x1804609d9  jl      short loc_1804609B5
0x1804609db  cmp     esi, 2
0x1804609de  jnz     short loc_180460A12
0x1804609e0  mov     dword ptr [rsp+200h+var_1B8], r14d
0x1804609e5  mov     rcx, [r10+98h]
0x1804609ec  mov     rax, [rcx]
0x1804609ef  lea     r8, [rsp+200h+var_1B8]
0x1804609f4  mov     edx, esi
0x1804609f6  mov     rax, [rax+0D8h]
0x1804609fd  call    cs:__guard_dispatch_icall_fptr
0x180460a03  test    eax, eax
0x180460a05  js      loc_18046100A
0x180460a0b  cmp     dword ptr [rsp+200h+var_1B8], r14d
0x180460a10  jz      short loc_180460A14
0x180460a12  mov     ebx, esi
0x180460a14  mov     esi, 80000000h
0x180460a19  mov     [rbp+100h+var_118], ebx
0x180460a1c  mov     [rsp+200h+var_1C8], r14
0x180460a21  mov     [rbp+100h+var_F0], 0FFFFFFFFh
0x180460a28  lea     r8, aCachetexture; "CacheTexture"
0x180460a2f  mov     edx, 40h ; '@'; unsigned __int64
0x180460a34  lea     rcx, [rbp+100h+var_EC]; wchar_t *
0x180460a38  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180460a3d  mov     rax, [rsp+200h+var_1B0]
0x180460a42  mov     rcx, [rax+98h]
0x180460a49  mov     rax, [rcx]
0x180460a4c  lea     rdx, [rsp+200h+var_1C8]
0x180460a51  mov     [rsp+20h], rdx
0x180460a56  xor     r9d, r9d
0x180460a59  lea     r8, [rbp+100h+var_F0]
0x180460a5d  lea     rdx, [rbp+100h+var_118]
0x180460a61  mov     rax, [rax+40h]
0x180460a65  call    cs:__guard_dispatch_icall_fptr
0x180460a6b  test    eax, eax
0x180460a6d  js      loc_180460FE6
0x180460a73  mov     eax, [rdi+8]
0x180460a76  cmp     [rdi], eax
0x180460a78  jge     loc_180460B28
0x180460a7e  mov     eax, [rdi+0Ch]
0x180460a81  cmp     [rdi+4], eax
0x180460a84  jge     loc_180460B28
0x180460a8a  xorps   xmm0, xmm0
0x180460a8d  xor     eax, eax
0x180460a8f  movups  xmmword ptr [rbp+100h+pvarg], xmm0
0x180460a93  mov     qword ptr [rbp+100h+pvarg+10h], rax
0x180460a97  lea     rcx, [rbp+100h+pvarg]; pvarg
0x180460a9b  call    cs:__imp_VariantInit
0x180460aa1  nop
0x180460aa2  mov     rcx, [rsp+200h+var_1C8]
0x180460aa7  mov     rax, [rcx]
0x180460aaa  mov     r10, [rax+60h]
0x180460aae  movsxd  rax, dword ptr [rdi+4]
0x180460ab2  movsxd  r8, dword ptr [rdi+0Ch]
0x180460ab6  sub     r8, rax
0x180460ab9  lea     rax, [rsi+r8]
0x180460abd  mov     r9d, 0FFFFFFFFh
0x180460ac3  cmp     rax, r9
0x180460ac6  ja      loc_180461028
0x180460acc  movsxd  rdx, dword ptr [rdi+8]
0x180460ad0  movsxd  rax, dword ptr [rdi]
0x180460ad3  sub     rdx, rax
0x180460ad6  lea     rax, [rsi+rdx]
0x180460ada  cmp     rax, r9
0x180460add  ja      loc_180461028
0x180460ae3  mov     dword ptr [rsp+200h+var_1C0], edx
0x180460ae7  mov     dword ptr [rsp+200h+var_1C0+4], r8d
0x180460aec  movups  xmm0, xmmword ptr [rbp+100h+pvarg]
0x180460af0  movaps  xmmword ptr [rbp+100h+rect.left], xmm0
0x180460af4  movsd   xmm1, qword ptr [rbp+100h+pvarg+10h]
0x180460af9  movsd   [rbp+100h+var_150], xmm1
0x180460afe  lea     r9, [rbp+100h+rect]
0x180460b02  mov     r8, [rsp+200h+var_1C0]
0x180460b07  mov     rdx, [rdi]
0x180460b0a  mov     rax, r10
0x180460b0d  call    cs:__guard_dispatch_icall_fptr
0x180460b13  test    eax, eax
0x180460b15  js      loc_180461020
0x180460b1b  mov     r14b, 1
0x180460b1e  lea     rcx, [rbp+100h+pvarg]; pvarg
0x180460b22  call    cs:__imp_VariantClear
0x180460b28  mov     rcx, r12; lprect
0x180460b2b  call    cs:__imp_CreateRectRgnIndirect
0x180460b31  mov     rdi, rax
0x180460b34  mov     [rbp+100h+var_170], rax
0x180460b38  xor     esi, esi
0x180460b3a  test    r15d, r15d
0x180460b3d  jle     loc_180460D79
0x180460b43  movsxd  rax, r15d
0x180460b46  mov     [rsp+200h+ho], rax
0x180460b4b  mov     [rsp+200h+var_1A8], rsi
0x180460b50  lea     rbx, [r13+20h]
0x180460b54  xor     r13d, r13d
0x180460b57  test    esi, esi
0x180460b59  js      loc_180461072
0x180460b5f  movsxd  rax, esi
0x180460b62  cmp     rax, r15
0x180460b65  jnb     loc_180461067
0x180460b6b  movsxd  rax, dword ptr [rbx-4]
0x180460b6f  mov     [rbp+100h+rect.left], eax
0x180460b72  movsxd  rdx, dword ptr [rbx]
0x180460b75  mov     [rbp+100h+rect.top], edx
0x180460b78  movsxd  r8, dword ptr [rbx+8]
0x180460b7c  mov     rcx, rax
0x180460b7f  movsxd  rax, dword ptr [rbx+4]
0x180460b83  add     rcx, rax
0x180460b86  mov     r9d, 80000000h
0x180460b8c  lea     rax, [rcx+r9]
0x180460b90  mov     r10d, 0FFFFFFFFh
0x180460b96  cmp     rax, r10
0x180460b99  ja      loc_180461061
0x180460b9f  mov     [rbp+100h+rect.right], ecx
0x180460ba2  lea     rcx, [r8+rdx]
0x180460ba6  lea     rax, [rcx+r9]
0x180460baa  cmp     rax, r10
  ... truncated ...
```
