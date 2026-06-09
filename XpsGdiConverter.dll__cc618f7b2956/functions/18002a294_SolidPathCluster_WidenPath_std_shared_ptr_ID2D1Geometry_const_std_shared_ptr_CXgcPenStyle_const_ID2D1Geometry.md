# SolidPathCluster::WidenPath(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<CXgcPenStyle> const &,ID2D1Geometry * *)

- ea: `0x18002a294`
- end: `0x18002a49f`
- name: `?WidenPath@SolidPathCluster@@AEAAJAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@VCXgcPenStyle@@@3@PEAPEAUID2D1Geometry@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180028acc`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002a294`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SolidPathCluster::WidenPath(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  float v7; // xmm7_4
  __int64 v8; // r10
  __int64 v9; // r9
  int v10; // ebx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  int v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  __int64 v22; // rcx
  _QWORD v24[2]; // [rsp+48h] [rbp-19h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-9h] BYREF
  __int64 v26; // [rsp+68h] [rbp+7h] BYREF
  xpsrdr **v27; // [rsp+70h] [rbp+Fh]
  _QWORD *v28; // [rsp+78h] [rbp+17h]
  xpsrdr *v29; // [rsp+C8h] [rbp+67h] BYREF

  v7 = *(float *)(a1 + 36);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v25);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v24);
  if ( v9 )
  {
    if ( COERCE_FLOAT(LODWORD(v7) & _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0]) < 0.00000011920929 )
      v7 = FLOAT_1_0;
    LODWORD(v29) = 0;
    v11 = *(__int64 **)(*(_QWORD *)v8 + 16LL);
    v12 = *v11;
    v26 = 0;
    v27 = &v29;
    v28 = v24;
    v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 80))(v11, &v26);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
    if ( (int)v29 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    LODWORD(v29) = 0;
    v17 = *(_QWORD *)v24[0];
    v26 = 0;
    v27 = &v29;
    v28 = v25;
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v17 + 136))(v24[0], &v26);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
    if ( (int)v29 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v19, v20, v21);
    if ( v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(*(_QWORD *)*a2 + 128LL))(
            *a2,
            v25[0],
            *(_QWORD *)(*(_QWORD *)a3 + 80LL),
            0,
            0.050000001 / v7,
            v25[0]);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 72LL))(v25[0]);
      if ( v10 >= 0 )
      {
        v22 = v24[0];
        *a4 = v24[0];
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v24);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002a294  mov     rax, rsp
0x18002a297  mov     [rax+10h], rbx
0x18002a29b  mov     [rax+18h], rsi
0x18002a29f  push    rbp
0x18002a2a0  push    rdi
0x18002a2a1  push    r14
0x18002a2a3  lea     rbp, [rax-5Fh]
0x18002a2a7  sub     rsp, 0A0h
0x18002a2ae  movaps  xmmword ptr [rax-28h], xmm6
0x18002a2b2  movaps  xmmword ptr [rax-38h], xmm7
0x18002a2b6  mov     rsi, r9
0x18002a2b9  mov     rdi, r8
0x18002a2bc  mov     r14, rdx
0x18002a2bf  mov     r10, rcx
0x18002a2c2  movss   xmm1, dword ptr [rcx+20h]
0x18002a2c7  movss   xmm7, dword ptr [rcx+24h]
0x18002a2cc  mov     rax, [r8]
0x18002a2cf  movss   xmm6, dword ptr [rax+10h]
0x18002a2d4  lea     rcx, [rbp+57h+var_60]
0x18002a2d8  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a2dd  nop
0x18002a2de  lea     rcx, [rbp+57h+var_70]
0x18002a2e2  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a2e7  nop
0x18002a2e8  test    r9, r9
0x18002a2eb  jnz     short loc_18002A2F7
0x18002a2ed  mov     ebx, 80070057h
0x18002a2f2  jmp     loc_18002A468
0x18002a2f7  mov     rax, [r8]
0x18002a2fa  movdqa  xmm3, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18002a302  movss   xmm4, cs:__real@34000000
0x18002a30a  cmp     byte ptr [rax+38h], 0
0x18002a30e  jz      short loc_18002A337
0x18002a310  movaps  xmm0, xmm1
0x18002a313  andps   xmm0, xmm3
0x18002a316  comiss  xmm0, xmm4
0x18002a319  jbe     short loc_18002A337
0x18002a31b  movd    xmm2, dword ptr [r10+28h]
0x18002a321  cvtdq2ps xmm2, xmm2
0x18002a324  movaps  xmm0, xmm1
0x18002a327  mulss   xmm0, xmm6
0x18002a32b  comiss  xmm2, xmm0
0x18002a32e  jbe     short loc_18002A337
0x18002a330  movaps  xmm6, xmm2
0x18002a333  divss   xmm6, xmm1
0x18002a337  movaps  xmm0, xmm7
0x18002a33a  andps   xmm0, xmm3
0x18002a33d  comiss  xmm4, xmm0
0x18002a340  jbe     short loc_18002A34A
0x18002a342  movss   xmm7, cs:__real@3f800000
0x18002a34a  mov     dword ptr [rbp+57h+arg_0], 0
0x18002a351  mov     rax, [r10]
0x18002a354  mov     rcx, [rax+10h]
0x18002a358  mov     rax, [rcx]
0x18002a35b  mov     [rbp+57h+var_50], 0
0x18002a363  lea     rdx, [rbp+57h+arg_0]
0x18002a367  mov     [rbp+57h+var_48], rdx
0x18002a36b  lea     rdx, [rbp+57h+var_70]
0x18002a36f  mov     [rbp+57h+var_40], rdx
0x18002a373  lea     rdx, [rbp+57h+var_50]
0x18002a377  mov     rax, [rax+50h]
0x18002a37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a380  mov     ebx, eax
0x18002a382  lea     rcx, [rbp+57h+var_50]
0x18002a386  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002a38b  mov     ecx, dword ptr [rbp+57h+arg_0]; this
0x18002a38e  test    ecx, ecx
0x18002a390  jns     short loc_18002A398
0x18002a392  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a398  test    ebx, ebx
0x18002a39a  jns     short loc_18002A3A4
0x18002a39c  mov     ecx, ebx; this
0x18002a39e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a3a4  mov     dword ptr [rbp+57h+arg_0], 0
0x18002a3ab  mov     rcx, [rbp+57h+var_70]
0x18002a3af  mov     rax, [rcx]
0x18002a3b2  mov     [rbp+57h+var_50], 0
0x18002a3ba  lea     rdx, [rbp+57h+arg_0]
0x18002a3be  mov     [rbp+57h+var_48], rdx
0x18002a3c2  lea     rdx, [rbp+57h+var_60]
0x18002a3c6  mov     [rbp+57h+var_40], rdx
0x18002a3ca  lea     rdx, [rbp+57h+var_50]
0x18002a3ce  mov     rax, [rax+88h]
0x18002a3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3da  mov     ebx, eax
0x18002a3dc  lea     rcx, [rbp+57h+var_50]
0x18002a3e0  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002a3e5  mov     ecx, dword ptr [rbp+57h+arg_0]; this
0x18002a3e8  test    ecx, ecx
0x18002a3ea  jns     short loc_18002A3F2
0x18002a3ec  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a3f2  test    ebx, ebx
0x18002a3f4  jns     short loc_18002A3FE
0x18002a3f6  mov     ecx, ebx; this
0x18002a3f8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a3fe  mov     rcx, [r14]
0x18002a401  mov     rdx, [rbp+57h+var_60]
0x18002a405  mov     rax, [rcx]
0x18002a408  movss   xmm0, cs:__real@3d4ccccd
0x18002a410  divss   xmm0, xmm7
0x18002a414  mov     r8, [rdi]
0x18002a417  mov     [rsp+0B0h+var_88], rdx
0x18002a41c  movss   dword ptr [rsp+0B0h+var_90], xmm0
0x18002a422  xor     r9d, r9d
0x18002a425  mov     r8, [r8+50h]
0x18002a429  movaps  xmm1, xmm6
0x18002a42c  mov     rax, [rax+80h]
0x18002a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a438  mov     ebx, eax
0x18002a43a  test    eax, eax
0x18002a43c  js      short loc_18002A468
0x18002a43e  mov     rcx, [rbp+57h+var_60]
0x18002a442  mov     rax, [rcx]
0x18002a445  mov     rax, [rax+48h]
0x18002a449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a44e  mov     ebx, eax
0x18002a450  test    eax, eax
0x18002a452  js      short loc_18002A468
0x18002a454  mov     rcx, [rbp+57h+var_70]
0x18002a458  mov     [rsi], rcx
0x18002a45b  mov     rax, [rcx]
0x18002a45e  mov     rax, [rax+8]
0x18002a462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a467  nop
0x18002a468  lea     rcx, [rbp+57h+var_70]
0x18002a46c  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a471  nop
0x18002a472  lea     rcx, [rbp+57h+var_60]
0x18002a476  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a47b  mov     eax, ebx
0x18002a47d  lea     r11, [rsp+0B0h+var_10]
0x18002a485  mov     rbx, [r11+28h]
0x18002a489  mov     rsi, [r11+30h]
0x18002a48d  movaps  xmm6, xmmword ptr [r11-10h]
0x18002a492  movaps  xmm7, xmmword ptr [r11-20h]
0x18002a497  mov     rsp, r11
0x18002a49a  pop     r14
0x18002a49c  pop     rdi
0x18002a49d  pop     rbp
0x18002a49e  retn
```
