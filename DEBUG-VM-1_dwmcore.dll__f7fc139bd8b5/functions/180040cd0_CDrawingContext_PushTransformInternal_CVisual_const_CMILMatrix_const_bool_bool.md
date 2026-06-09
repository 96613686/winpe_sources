# CDrawingContext::PushTransformInternal(CVisual const *,CMILMatrix const *,bool,bool)

- ea: `0x180040cd0`
- end: `0x180041613`
- name: `?PushTransformInternal@CDrawingContext@@IEAAJPEBVCVisual@@PEBVCMILMatrix@@_N2@Z`
- size: `2371`
- prototype: `int(CDrawingContext *__hidden this, const struct CVisual *, const struct CMILMatrix *, bool, bool)`
- caller_count: `22`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800134dc`
- `0x180065104`
- `0x180073c50`
- `0x18009f24c`
- `0x1800a1dc4`
- `0x1800a2be4`
- `0x1800bb4d4`
- `0x1800bd3e0`
- `0x1800c0e30`
- `0x1800c1d84`
- `0x1800c2690`
- `0x1800d0ca0`
- `0x18011a44c`
- `0x180121010`
- `0x18013d08c`
- `0x18015b3b8`
- `0x1801b1da0`
- `0x1801c6340`
- `0x1802213ac`
- `0x1802329f0`
- `0x180236e54`
- `0x18024b5e0`

## callees

- `0x180040cd0`
- `0x180042854`
- `0x180042de0`
- `0x1800441f0`
- `0x180044220`
- `0x180063e10`
- `0x180088280`
- `0x180229424`

## string_xrefs

- `0x180040eca`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180040ee1`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180041030`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180041047`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x1800411fc`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180041213`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x1800414a6`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x1800414ff`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180041516`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`

## pseudocode

```c
__int64 __fastcall CDrawingContext::PushTransformInternal(
        CDrawingContext *this,
        const struct CVisual *a2,
        const struct CMILMatrix *a3,
        char a4,
        unsigned int a5)
{
  char v5; // si
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // r12
  unsigned __int64 v13; // rax
  unsigned int v14; // esi
  unsigned __int64 v15; // r12
  void *v16; // rax
  void *v17; // r13
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // edx
  unsigned int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  _BYTE *v29; // rdx
  char v30; // cl
  char v31; // bp
  __int64 v32; // rdx
  unsigned int v33; // edi
  __int64 result; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int64 v40; // rax
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int64 v44; // rdx
  unsigned int v45; // eax
  char v46; // al
  unsigned int v47; // r9d
  unsigned int v48; // eax
  __int64 v49; // rax
  int v50; // edi
  __int64 v51; // rcx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // r12
  const void *v54; // r15
  void *v55; // rax
  void *v56; // rbp
  unsigned int v57; // ecx
  __int64 v58; // rdx
  int v59; // eax
  int v60; // eax
  int v61; // ecx
  unsigned int v62; // ebp
  const void *v63; // r13
  void *v64; // r12
  __int32 v65; // xmm2_4
  int v66; // eax
  __int64 v67; // rcx
  unsigned __int64 v68; // rax
  __int64 v69; // rdx
  unsigned int v70; // ebp
  unsigned int v71; // edi
  const void *v72; // r13
  void *v73; // rax
  void *v74; // r12
  int v75; // [rsp+20h] [rbp-118h]
  int v76; // [rsp+20h] [rbp-118h]
  int v77; // [rsp+20h] [rbp-118h]
  int v78; // [rsp+20h] [rbp-118h]
  int v79; // [rsp+20h] [rbp-118h]
  void *Src; // [rsp+40h] [rbp-F8h] BYREF
  size_t Size; // [rsp+48h] [rbp-F0h]
  _OWORD v82[4]; // [rsp+50h] [rbp-E8h] BYREF
  int v83; // [rsp+90h] [rbp-A8h]
  _OWORD v84[4]; // [rsp+A0h] [rbp-98h] BYREF
  int v85; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = 0;
  v10 = 64;
  if ( !(_BYTE)a5 )
    goto LABEL_14;
  Size = 0;
  v11 = *((unsigned int *)this + 67);
  if ( *((_DWORD *)this + 66) == (_DWORD)v11 )
  {
    v12 = (unsigned int)v11;
    v13 = 2 * v11;
    if ( v13 > 0xFFFFFFFF )
    {
      v32 = 95;
    }
    else
    {
      v14 = 64;
      if ( (unsigned int)v13 > 0x40 )
        v14 = v13;
      v15 = 16 * v12;
      if ( v15 <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v14 <= 0x10 )
        {
          v33 = -2147024809;
        }
        else
        {
          Src = (void *)*((_QWORD *)this + 32);
          v16 = MIDL_user_allocate(16LL * v14);
          v17 = v16;
          if ( v16 )
          {
            if ( Src && (_DWORD)v15 )
              memcpy_0(v16, Src, (unsigned int)v15);
            operator delete(*((void **)this + 32));
            *((_QWORD *)this + 32) = v17;
            *((_DWORD *)this + 67) = v14;
            goto LABEL_11;
          }
          v33 = -2147024882;
        }
        v32 = 101;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v75);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v76);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xCF7u, 0);
        return v33;
      }
      v32 = 98;
    }
    v33 = -2147024362;
    goto LABEL_27;
  }
LABEL_11:
  v5 = 1;
  v18 = *((_QWORD *)this + 32);
  v19 = 2LL * *((unsigned int *)this + 66);
  v20 = Size;
  *(_DWORD *)(v18 + 8 * v19) = 5;
  *(_DWORD *)(v18 + 8 * v19 + 4) = v20;
  *(_QWORD *)(v18 + 8 * v19 + 8) = a2;
  v21 = *((_DWORD *)this + 69);
  if ( v21 <= ++*((_DWORD *)this + 66) )
    v21 = *((_DWORD *)this + 66);
  *((_DWORD *)this + 69) = v21;
LABEL_14:
  v22 = *((_DWORD *)this + 72);
  if ( v22 && a4 )
  {
    v83 = 0;
    v35 = (unsigned int)(v22 - 1);
    v36 = *((_QWORD *)this + 35);
    v37 = *(_OWORD *)(68 * v35 + v36 + 16);
    v84[0] = *(_OWORD *)(68 * v35 + v36);
    v38 = *(_OWORD *)(68 * v35 + v36 + 32);
    v84[1] = v37;
    v39 = *(_OWORD *)(68 * v35 + v36 + 48);
    LODWORD(v36) = *(_DWORD *)(68 * v35 + v36 + 64);
    v84[2] = v38;
    v84[3] = v39;
    v85 = v36;
    CMILMatrix::Multiply(a3, (const struct CMILMatrix *)v84, (struct CMILMatrix *)v82);
    v40 = *((unsigned int *)this + 73);
    if ( *((_DWORD *)this + 72) != (_DWORD)v40 )
    {
LABEL_34:
      v24 = *((_QWORD *)this + 35);
      v41 = v82[1];
      v25 = 68LL * *((unsigned int *)this + 72);
      v26 = v83;
      *(_OWORD *)(v25 + v24) = v82[0];
      v42 = v82[2];
      *(_OWORD *)(v25 + v24 + 16) = v41;
      v43 = v82[3];
      *(_OWORD *)(v25 + v24 + 32) = v42;
      *(_OWORD *)(v25 + v24 + 48) = v43;
      goto LABEL_18;
    }
    v67 = *((unsigned int *)this + 73);
    v68 = 2 * v40;
    if ( v68 <= 0xFFFFFFFF )
    {
      v70 = 8;
      if ( (unsigned int)v68 > 8 )
        v70 = v68;
      v71 = 68 * v67;
      if ( (unsigned __int64)(68 * v67) <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v70 <= 0x44 )
        {
          v33 = -2147024809;
        }
        else
        {
          v72 = (const void *)*((_QWORD *)this + 35);
          v73 = MIDL_user_allocate(68LL * v70);
          v74 = v73;
          if ( v73 )
          {
            if ( v72 && v71 )
              memcpy_0(v73, v72, v71);
            operator delete(*((void **)this + 35));
            *((_QWORD *)this + 35) = v74;
            *((_DWORD *)this + 73) = v70;
            goto LABEL_34;
          }
          v33 = -2147024882;
        }
        v69 = 101;
LABEL_97:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v69,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v75);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v79);
        v45 = 69;
        goto LABEL_39;
      }
      v69 = 98;
    }
    else
    {
      v69 = 95;
    }
    v33 = -2147024362;
    goto LABEL_97;
  }
  v23 = *((unsigned int *)this + 73);
  if ( v22 == (_DWORD)v23 )
  {
    if ( (unsigned __int64)(2 * v23) <= 0xFFFFFFFF )
    {
      v62 = 8;
      if ( (unsigned int)(2 * v23) > 8 )
        v62 = 2 * v23;
      Size = 68 * v23;
      if ( (unsigned __int64)(68 * v23) <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v62 <= 0x44 )
        {
          v33 = -2147024809;
        }
        else
        {
          v63 = (const void *)*((_QWORD *)this + 35);
          v64 = MIDL_user_allocate(68LL * v62);
          if ( v64 )
          {
            if ( v63 && (_DWORD)Size )
              memcpy_0(v64, v63, (unsigned int)Size);
            operator delete(*((void **)this + 35));
            *((_QWORD *)this + 35) = v64;
            *((_DWORD *)this + 73) = v62;
            goto LABEL_17;
          }
          v33 = -2147024882;
        }
        v44 = 101;
        goto LABEL_38;
      }
      v44 = 98;
    }
    else
    {
      v44 = 95;
    }
    v33 = -2147024362;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v75);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v77);
    v45 = 54;
LABEL_39:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, v45, 0);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xCFCu, 0);
    goto LABEL_65;
  }
LABEL_17:
  v24 = *((_QWORD *)this + 35);
  v25 = 68LL * *((unsigned int *)this + 72);
  *(_OWORD *)(v25 + v24) = *(_OWORD *)a3;
  *(_OWORD *)(v25 + v24 + 16) = *((_OWORD *)a3 + 1);
  *(_OWORD *)(v25 + v24 + 32) = *((_OWORD *)a3 + 2);
  *(_OWORD *)(v25 + v24 + 48) = *((_OWORD *)a3 + 3);
  v26 = *((_DWORD *)a3 + 16);
LABEL_18:
  *(_DWORD *)(v25 + v24 + 64) = v26;
  ++*((_DWORD *)this + 72);
  v27 = *((_DWORD *)this + 75);
  if ( v27 <= *((_DWORD *)this + 72) )
    v27 = *((_DWORD *)this + 72);
  *((_DWORD *)this + 75) = v27;
  v28 = *((_DWORD *)this + 72);
  if ( v28 )
    v29 = (_BYTE *)(*((_QWORD *)this + 35) + 68LL * (unsigned int)(v28 - 1));
  else
    v29 = &CMILMatrix::Identity;
  v30 = v29[65];
  if ( (v30 & 0x20) == 0 && 4 * (v30 & 0xF0) != 0 )
    goto LABEL_69;
  if ( (v30 & 0x20) != 0 )
  {
    v31 = 1;
    goto LABEL_42;
  }
  COERCE_FLOAT(v65 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
  if ( COERCE_FLOAT(
         COERCE_UNSIGNED_INT(
           (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v29 + 7) & v65) * 61440.0)
                         + (float)(COERCE_FLOAT(*((_DWORD *)v29 + 3) & v65) * 61440.0))
                 + COERCE_FLOAT(*((_DWORD *)v29 + 15) & v65))
         - 1.0)
       & v65) < 0.000081380211 )
  {
    v31 = 1;
    v46 = -16;
  }
  else
  {
    v31 = 0;
    v46 = 16;
  }
  v29[65] = v46 ^ (v46 ^ v30) & 0xCF;
  if ( !v31 )
LABEL_69:
    v31 = 0;
LABEL_42:
  v47 = *((_DWORD *)this + 79);
  if ( *((_DWORD *)this + 78) != v47 )
    goto LABEL_43;
  a5 = 0;
  Src = 0;
  v66 = Grow(1u, 0x40u, (unsigned int)a3, v47, *((void **)this + 38), &a5, &Src);
  v33 = v66;
  if ( v66 >= 0 )
  {
    operator delete(*((void **)this + 38));
    *((_QWORD *)this + 38) = Src;
    *((_DWORD *)this + 79) = a5;
LABEL_43:
    *(_BYTE *)((unsigned int)(*((_DWORD *)this + 78))++ + *((_QWORD *)this + 38)) = v31 ^ 1;
    v48 = *((_DWORD *)this + 81);
    if ( v48 <= *((_DWORD *)this + 78) )
      v48 = *((_DWORD *)this + 78);
    *((_DWORD *)this + 81) = v48;
    if ( !a2 )
      return 0;
    v49 = *((unsigned int *)this + 85);
    v50 = *((_DWORD *)this + 72);
    if ( *((_DWORD *)this + 84) != (_DWORD)v49 )
    {
LABEL_55:
      *(_DWORD *)(*((_QWORD *)this + 41) + 4LL * *((unsigned int *)this + 84)) = v50;
      v57 = *((_DWORD *)this + 87);
      if ( v57 <= ++*((_DWORD *)this + 84) )
        v57 = *((_DWORD *)this + 84);
      *((_DWORD *)this + 87) = v57;
      return 0;
    }
    v51 = (unsigned int)v49;
    v52 = 2 * v49;
    if ( v52 > 0xFFFFFFFF )
    {
      v58 = 95;
    }
    else
    {
      v53 = 4 * v51;
      if ( (unsigned int)v52 > 0x40 )
        v10 = (unsigned int)v52;
      if ( v53 <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v10 <= 4 )
        {
          v33 = -2147024809;
        }
        else
        {
          v54 = (const void *)*((_QWORD *)this + 41);
          v55 = MIDL_user_allocate(4 * v10);
          v56 = v55;
          if ( v55 )
          {
            if ( v54 && (_DWORD)v53 )
              memcpy_0(v55, v54, (unsigned int)v53);
            operator delete(*((void **)this + 41));
            *((_QWORD *)this + 41) = v56;
            *((_DWORD *)this + 85) = v10;
            goto LABEL_55;
          }
          v33 = -2147024882;
        }
        v58 = 101;
        goto LABEL_61;
      }
      v58 = 98;
    }
    v33 = -2147024362;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v75);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v78);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xD06u, 0);
    v59 = *((_DWORD *)this + 78);
    if ( v59 )
      *((_DWORD *)this + 78) = v59 - 1;
    goto LABEL_63;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
    (const char *)(unsigned int)v66,
    v75);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xD00u, 0);
LABEL_63:
  v60 = *((_DWORD *)this + 72);
  if ( v60 )
    *((_DWORD *)this + 72) = v60 - 1;
LABEL_65:
  if ( !v5 )
    return v33;
  v61 = *((_DWORD *)this + 66);
  result = v33;
  if ( v61 )
    *((_DWORD *)this + 66) = v61 - 1;
  return result;
}

```

## disassembly

```asm
0x180040cd0  push    rbx
0x180040cd2  push    rbp
0x180040cd3  push    rsi
0x180040cd4  push    rdi
0x180040cd5  push    r12
0x180040cd7  push    r13
0x180040cd9  push    r14
0x180040cdb  push    r15
0x180040cdd  sub     rsp, 0F8h
0x180040ce4  xor     sil, sil
0x180040ce7  movzx   ebp, r9b
0x180040ceb  mov     rdi, r8
0x180040cee  mov     r15, rdx
0x180040cf1  mov     rbx, rcx
0x180040cf4  mov     r13d, 0FFFFFFFFh
0x180040cfa  mov     r14d, 40h ; '@'
0x180040d00  cmp     byte ptr [rsp+138h+arg_20], sil
0x180040d08  jz      loc_180040DFF
0x180040d0e  xor     eax, eax
0x180040d10  mov     [rsp+138h+Size], rax
0x180040d15  mov     eax, [rcx+10Ch]
0x180040d1b  cmp     [rcx+108h], eax
0x180040d21  jnz     loc_180040DBA
0x180040d27  mov     r12d, eax
0x180040d2a  add     rax, rax
0x180040d2d  cmp     rax, r13
0x180040d30  ja      loc_180040EB8
0x180040d36  cmp     eax, r14d
0x180040d39  mov     esi, r14d
0x180040d3c  cmova   esi, eax
0x180040d3f  shl     r12, 4
0x180040d43  cmp     r12, r13
0x180040d46  ja      loc_180040F2E
0x180040d4c  test    esi, esi
0x180040d4e  jz      loc_180041377
0x180040d54  xor     edx, edx
0x180040d56  mov     ecx, esi
0x180040d58  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180040d5f  div     rcx
0x180040d62  cmp     rax, 10h
0x180040d66  jbe     loc_180041377
0x180040d6c  mov     rax, [rbx+100h]
0x180040d73  shl     rcx, 4; size
0x180040d77  mov     [rsp+138h+Src], rax
0x180040d7c  call    MIDL_user_allocate
0x180040d81  mov     r13, rax
0x180040d84  test    rax, rax
0x180040d87  jz      loc_180040F35
0x180040d8d  mov     rdx, [rsp+138h+Src]; Src
0x180040d92  test    rdx, rdx
0x180040d95  jnz     loc_18004135E
0x180040d9b  mov     rcx, [rbx+100h]; void *
0x180040da2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040da7  mov     [rbx+100h], r13
0x180040dae  mov     r13d, 0FFFFFFFFh
0x180040db4  mov     [rbx+10Ch], esi
0x180040dba  mov     ecx, [rbx+108h]
0x180040dc0  mov     sil, 1
0x180040dc3  mov     rax, [rbx+100h]
0x180040dca  add     rcx, rcx
0x180040dcd  mov     rdx, [rsp+138h+Size]
0x180040dd2  mov     dword ptr [rax+rcx*8], 5
0x180040dd9  mov     [rax+rcx*8+4], edx
0x180040ddd  mov     [rax+rcx*8+8], r15
0x180040de2  mov     eax, [rbx+114h]
0x180040de8  inc     dword ptr [rbx+108h]
0x180040dee  mov     ecx, [rbx+108h]
0x180040df4  cmp     eax, ecx
0x180040df6  cmovbe  eax, ecx
0x180040df9  mov     [rbx+114h], eax
0x180040dff  mov     eax, [rbx+120h]
0x180040e05  test    eax, eax
0x180040e07  jz      short loc_180040E12
0x180040e09  test    bpl, bpl
0x180040e0c  jnz     loc_180040F41
0x180040e12  mov     ecx, [rbx+124h]
0x180040e18  cmp     eax, ecx
0x180040e1a  jz      loc_18004100E
0x180040e20  mov     eax, [rbx+120h]
0x180040e26  movups  xmm0, xmmword ptr [rdi]
0x180040e29  mov     rcx, [rbx+118h]
0x180040e30  imul    rdx, rax, 44h ; 'D'
0x180040e34  movups  xmmword ptr [rdx+rcx], xmm0
0x180040e38  movups  xmm1, xmmword ptr [rdi+10h]
0x180040e3c  movups  xmmword ptr [rdx+rcx+10h], xmm1
0x180040e41  movups  xmm0, xmmword ptr [rdi+20h]
0x180040e45  movups  xmmword ptr [rdx+rcx+20h], xmm0
0x180040e4a  movups  xmm1, xmmword ptr [rdi+30h]
0x180040e4e  movups  xmmword ptr [rdx+rcx+30h], xmm1
0x180040e53  mov     eax, [rdi+40h]
0x180040e56  mov     [rdx+rcx+40h], eax
0x180040e5a  inc     dword ptr [rbx+120h]
0x180040e60  mov     ecx, [rbx+120h]
0x180040e66  mov     eax, [rbx+12Ch]
0x180040e6c  cmp     eax, ecx
0x180040e6e  cmovbe  eax, ecx
0x180040e71  mov     [rbx+12Ch], eax
0x180040e77  mov     eax, [rbx+120h]
0x180040e7d  test    eax, eax
0x180040e7f  jz      loc_18004138B
0x180040e85  lea     ecx, [rax-1]
0x180040e88  imul    rdx, rcx, 44h ; 'D'
0x180040e8c  add     rdx, [rbx+118h]
0x180040e93  movzx   ecx, byte ptr [rdx+41h]
0x180040e97  movzx   eax, cl
0x180040e9a  and     al, 0F0h
0x180040e9c  shl     al, 2
0x180040e9f  test    al, al
0x180040ea1  jg      loc_18004129E
0x180040ea7  test    cl, 20h
0x180040eaa  jz      loc_180041397
0x180040eb0  mov     bpl, 1
0x180040eb3  jmp     loc_1800410BF
0x180040eb8  mov     edx, 5Fh ; '_'; void *
0x180040ebd  mov     edi, 80070216h
0x180040ec2  mov     rcx, [rsp+138h]; this
0x180040eca  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180040ed1  mov     r9d, edi; char *
0x180040ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ed9  mov     rcx, [rsp+138h]; this
0x180040ee1  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180040ee8  mov     r9d, edi; char *
0x180040eeb  mov     edx, 8Bh; void *
0x180040ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ef5  mov     r9d, edi; int
0x180040ef8  mov     [rsp+138h+var_110], 0; void *
0x180040f01  xor     r8d, r8d; unsigned int
0x180040f04  mov     dword ptr [rsp+138h+var_118], 0CF7h; unsigned int
0x180040f0c  xor     edx, edx; int *
0x180040f0e  mov     ecx, 14h; unsigned int
0x180040f13  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180040f18  mov     eax, edi
0x180040f1a  add     rsp, 0F8h
0x180040f21  pop     r15
0x180040f23  pop     r14
0x180040f25  pop     r13
0x180040f27  pop     r12
0x180040f29  pop     rdi
0x180040f2a  pop     rsi
0x180040f2b  pop     rbp
0x180040f2c  pop     rbx
0x180040f2d  retn
0x180040f2e  mov     edx, 62h ; 'b'
0x180040f33  jmp     short loc_180040EBD
0x180040f35  mov     edi, 8007000Eh
0x180040f3a  mov     edx, 65h ; 'e'
0x180040f3f  jmp     short loc_180040EC2
0x180040f41  mov     [rsp+138h+var_A8], 0
0x180040f4c  test    eax, eax
0x180040f4e  jz      loc_180041604
0x180040f54  lea     ecx, [rax-1]
0x180040f57  mov     rax, [rbx+118h]
0x180040f5e  imul    rdx, rcx, 44h ; 'D'
0x180040f62  lea     r8, [rsp+138h+var_E8]; struct CMILMatrix *
0x180040f67  mov     rcx, rdi; struct CMILMatrix *
0x180040f6a  movups  xmm0, xmmword ptr [rdx+rax]
0x180040f6e  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x180040f73  movaps  [rsp+138h+var_98], xmm0
0x180040f7b  movups  xmm0, xmmword ptr [rdx+rax+20h]
0x180040f80  movaps  [rsp+138h+var_88], xmm1
0x180040f88  movups  xmm1, xmmword ptr [rdx+rax+30h]
0x180040f8d  mov     eax, [rdx+rax+40h]
0x180040f91  lea     rdx, [rsp+138h+var_98]; struct CMILMatrix *
0x180040f99  movaps  [rsp+138h+var_78], xmm0
0x180040fa1  movaps  [rsp+138h+var_68], xmm1
0x180040fa9  mov     [rsp+138h+var_58], eax
0x180040fb0  call    ?Multiply@CMILMatrix@@SAXAEBV1@0PEAV1@@Z; CMILMatrix::Multiply(CMILMatrix const &,CMILMatrix const &,CMILMatrix *)
0x180040fb5  mov     eax, [rbx+124h]
0x180040fbb  cmp     [rbx+120h], eax
0x180040fc1  jz      loc_1800414E2
0x180040fc7  mov     eax, [rbx+120h]
0x180040fcd  mov     rcx, [rbx+118h]
0x180040fd4  movaps  xmm0, [rsp+138h+var_E8]
0x180040fd9  movaps  xmm1, [rsp+138h+var_D8]
0x180040fde  imul    rdx, rax, 44h ; 'D'
0x180040fe2  mov     eax, [rsp+138h+var_A8]
0x180040fe9  movups  xmmword ptr [rdx+rcx], xmm0
0x180040fed  movaps  xmm0, [rsp+138h+var_C8]
0x180040ff2  movups  xmmword ptr [rdx+rcx+10h], xmm1
0x180040ff7  movaps  xmm1, [rsp+138h+var_B8]
0x180040fff  movups  xmmword ptr [rdx+rcx+20h], xmm0
0x180041004  movups  xmmword ptr [rdx+rcx+30h], xmm1
0x180041009  jmp     loc_180040E56
0x18004100e  lea     rax, [rcx+rcx]
0x180041012  mov     rdx, rcx
0x180041015  cmp     rax, r13
0x180041018  jbe     loc_1800412DF
0x18004101e  mov     edx, 5Fh ; '_'; void *
0x180041023  mov     edi, 80070216h
0x180041028  mov     rcx, [rsp+138h]; this
0x180041030  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180041037  mov     r9d, edi; char *
0x18004103a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004103f  mov     rcx, [rsp+138h]; this
0x180041047  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004104e  mov     r9d, edi; char *
0x180041051  mov     edx, 8Bh; void *
0x180041056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004105b  mov     eax, 36h ; '6'
0x180041060  mov     r9d, edi; int
0x180041063  mov     [rsp+138h+var_110], 0; void *
0x18004106c  xor     r8d, r8d; unsigned int
0x18004106f  mov     dword ptr [rsp+138h+var_118], eax; unsigned int
0x180041073  xor     edx, edx; int *
0x180041075  mov     ecx, 14h; unsigned int
0x18004107a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004107f  mov     r9d, edi; int
0x180041082  mov     [rsp+138h+var_110], 0; void *
0x18004108b  xor     r8d, r8d; unsigned int
0x18004108e  mov     dword ptr [rsp+138h+var_118], 0CFCh; unsigned int
0x180041096  xor     edx, edx; int *
0x180041098  mov     ecx, 14h; unsigned int
0x18004109d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800410a2  jmp     loc_18004126E
0x1800410a7  mov     bpl, 1
0x1800410aa  mov     al, 0F0h
0x1800410ac  xor     cl, al
0x1800410ae  and     cl, 0CFh
0x1800410b1  xor     cl, al
0x1800410b3  mov     [rdx+41h], cl
0x1800410b6  test    bpl, bpl
0x1800410b9  jz      loc_18004129E
0x1800410bf  mov     r9d, [rbx+13Ch]; unsigned int
0x1800410c6  cmp     [rbx+138h], r9d
0x1800410cd  jz      loc_1800413F5
0x1800410d3  mov     ecx, [rbx+138h]
0x1800410d9  xor     bpl, 1
0x1800410dd  mov     rax, [rbx+130h]
0x1800410e4  mov     [rcx+rax], bpl
0x1800410e8  inc     dword ptr [rbx+138h]
0x1800410ee  mov     eax, [rbx+144h]
0x1800410f4  mov     ecx, [rbx+138h]
0x1800410fa  cmp     eax, ecx
0x1800410fc  cmovbe  eax, ecx
0x1800410ff  mov     [rbx+144h], eax
0x180041105  test    r15, r15
0x180041108  jz      loc_1800411E3
0x18004110e  mov     eax, [rbx+154h]
0x180041114  mov     edi, [rbx+120h]
0x18004111a  cmp     [rbx+150h], eax
0x180041120  jnz     loc_1800411B6
0x180041126  mov     ecx, eax
0x180041128  mov     edx, 0FFFFFFFFh
0x18004112d  add     rax, rax
0x180041130  cmp     rax, rdx
0x180041133  ja      loc_1800411EA
0x180041139  cmp     eax, r14d
0x18004113c  lea     r12, ds:0[rcx*4]
0x180041144  cmova   r14d, eax
0x180041148  cmp     r12, rdx
0x18004114b  ja      loc_180041294
0x180041151  test    r14d, r14d
0x180041154  jz      loc_180041485
0x18004115a  xor     edx, edx
0x18004115c  mov     ecx, r14d
0x18004115f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180041166  div     rcx
0x180041169  cmp     rax, 4
0x18004116d  jbe     loc_180041485
0x180041173  mov     r15, [rbx+148h]
0x18004117a  lea     rcx, ds:0[r14*4]; size
0x180041182  call    MIDL_user_allocate
0x180041187  mov     rbp, rax
0x18004118a  test    rax, rax
0x18004118d  jz      loc_1800412D0
0x180041193  test    r15, r15
0x180041196  jnz     loc_180041469
0x18004119c  mov     rcx, [rbx+148h]; void *
0x1800411a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800411a8  mov     [rbx+148h], rbp
0x1800411af  mov     [rbx+154h], r14d
0x1800411b6  mov     edx, [rbx+150h]
0x1800411bc  mov     rcx, [rbx+148h]
0x1800411c3  mov     [rcx+rdx*4], edi
0x1800411c6  mov     ecx, [rbx+15Ch]
0x1800411cc  inc     dword ptr [rbx+150h]
0x1800411d2  mov     edx, [rbx+150h]
0x1800411d8  cmp     ecx, edx
0x1800411da  cmovbe  ecx, edx
0x1800411dd  mov     [rbx+15Ch], ecx
0x1800411e3  xor     eax, eax
0x1800411e5  jmp     loc_180040F1A
0x1800411ea  mov     edx, 5Fh ; '_'; void *
0x1800411ef  mov     edi, 80070216h
0x1800411f4  mov     rcx, [rsp+138h]; this
0x1800411fc  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180041203  mov     r9d, edi; char *
0x180041206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004120b  mov     rcx, [rsp+138h]; this
0x180041213  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004121a  mov     r9d, edi; char *
0x18004121d  mov     edx, 8Bh; void *
0x180041222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041227  mov     r9d, edi; int
0x18004122a  mov     [rsp+138h+var_110], 0; void *
0x180041233  xor     r8d, r8d; unsigned int
0x180041236  mov     dword ptr [rsp+138h+var_118], 0D06h; unsigned int
0x18004123e  xor     edx, edx; int *
0x180041240  mov     ecx, 14h; unsigned int
0x180041245  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
  ... truncated ...
```
