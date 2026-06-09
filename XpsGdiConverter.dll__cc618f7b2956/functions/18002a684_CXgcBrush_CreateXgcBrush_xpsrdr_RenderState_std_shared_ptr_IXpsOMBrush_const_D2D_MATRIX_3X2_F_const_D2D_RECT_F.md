# CXgcBrush::CreateXgcBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,bool)

- ea: `0x18002a684`
- end: `0x18002ab80`
- name: `?CreateXgcBrush@CXgcBrush@@SA?AV?$shared_ptr@VCXgcBrush@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@_N@Z`
- size: `1276`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800185f0`
- `0x180019c1c`

## callees

- `0x180008854`
- `0x18000937c`
- `0x180009de0`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002a5bc`
- `0x18002a684`
- `0x18002ab88`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CXgcBrush::CreateXgcBrush(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ****a3)(__int64, GUID *, __int64 *),
        __int64 a4,
        float *a5,
        char a6)
{
  double XpsBrushOpacity; // xmm0_8
  int v9; // xmm10_4
  int v10; // eax
  const char *v11; // rdx
  const char *v12; // r8
  int v13; // r9d
  bool v14; // bl
  int v15; // edi
  __int64 (__fastcall ***v16)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v17)(__int64, GUID *, __int64 *); // rax
  int v18; // esi
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v22; // eax
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  int v30; // eax
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  int v34; // eax
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  float v38; // xmm9_4
  float v39; // xmm0_4
  float v40; // xmm6_4
  float v41; // xmm0_4
  float v42; // xmm2_4
  float v43; // xmm3_4
  float v44; // xmm0_4
  float v45; // xmm8_4
  float v46; // xmm7_4
  float v47; // xmm0_4
  __int64 (__fastcall ***v48)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v49)(__int64, GUID *, __int64 *); // rax
  int v50; // edi
  int v51; // edx
  const char *v52; // r8
  int v53; // r9d
  int v54; // eax
  int v55; // edx
  const char *v56; // r8
  int v57; // r9d
  int v58; // eax
  int v59; // edx
  const char *v60; // r8
  int v61; // r9d
  int v62; // edx
  float v63; // xmm0_4
  _QWORD *v64; // rcx
  __int64 v65; // rcx
  int v66; // r8d
  xpsrdr *v68; // [rsp+28h] [rbp-A9h] BYREF
  float v69; // [rsp+30h] [rbp-A1h] BYREF
  int v70; // [rsp+34h] [rbp-9Dh] BYREF
  _QWORD v71[2]; // [rsp+38h] [rbp-99h] BYREF
  __int64 v72; // [rsp+48h] [rbp-89h] BYREF
  __int64 v73; // [rsp+50h] [rbp-81h] BYREF
  __int64 v74; // [rsp+58h] [rbp-79h] BYREF
  xpsrdr **v75; // [rsp+60h] [rbp-71h]
  _QWORD *v76; // [rsp+68h] [rbp-69h]
  void *v77; // [rsp+138h] [rbp+67h] BYREF

  v69 = 0.0;
  XpsBrushOpacity = GetXpsBrushOpacity(a2, a3, a4, &v69);
  v9 = LODWORD(XpsBrushOpacity);
  v70 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), int *))(**a3)[4])(*a3, &v70);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, (int)v11, v12, v13);
  v14 = 0;
  v15 = 0;
  if ( v70 != 6 )
  {
    switch ( v70 )
    {
      case 7:
        LODWORD(v77) = 0;
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v71);
        LODWORD(v68) = 0;
        v48 = *a3;
        v49 = **a3;
        v74 = 0;
        v75 = &v68;
        v76 = v71;
        v50 = (*v49)((__int64)v48, &GUID_3df0b466_d382_49ef_8550_dd94c80242e4, &v74);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v74);
        if ( (int)v68 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v68, v51, v52, v53);
        if ( v50 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v50, v51, v52, v53);
        v54 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v71[0] + 128LL))(v71[0], &v77);
        if ( v54 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v54, v55, v56, v57);
        if ( a6 )
        {
          if ( (_DWORD)v77 != 1 )
          {
            LODWORD(v77) = 1;
            v58 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v71[0] + 136LL))(v71[0], 1);
            if ( v58 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v58, v59, v60, v61);
          }
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v71);
        v62 = (int)v77;
        if ( (_DWORD)v77 != 1 && v69 > 6.1847529e11 )
        {
          v14 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_f8f8585922d0359fe11623de1fb173cd_Traceguids);
            v62 = (int)v77;
          }
        }
        v69 = v69 / (float)((float)(a5[3] - a5[1]) * (float)(a5[2] - *a5));
        v15 = (v62 != 1) + 1;
        break;
      case 8:
        v14 = *(float *)&XpsBrushOpacity < 1.0;
        break;
      case 9:
        v14 = *(float *)&XpsBrushOpacity < 1.0;
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v71);
        LODWORD(v68) = 0;
        v16 = *a3;
        v17 = **a3;
        v74 = 0;
        v75 = &v68;
        v76 = v71;
        v18 = (*v17)((__int64)v16, &GUID_75f207e5_08bf_413c_96b1_b82b4064176b, &v74);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v74);
        if ( (int)v68 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v68, v19, v20, v21);
        if ( v18 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
        if ( *(float *)&XpsBrushOpacity >= 1.0 )
        {
          LODWORD(v68) = 0;
          v22 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(*(_QWORD *)v71[0] + 104LL))(v71[0], &v68);
          if ( v22 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
          if ( (_DWORD)v68 == 1 )
          {
            v68 = 0;
            v73 = 0;
            v72 = 0;
            v26 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(*(_QWORD *)v71[0] + 136LL))(v71[0], &v68);
            if ( v26 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
            v30 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v71[0] + 168LL))(v71[0], &v73);
            if ( v30 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
            v34 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v71[0] + 152LL))(v71[0], &v72);
            if ( v34 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v35, v36, v37);
            if ( *(float *)&v72 <= *((float *)&v72 + 1) )
            {
              v38 = *((float *)&v72 + 1);
              v40 = *(float *)&v68;
              v44 = o_sqrtf_0((float)(*((float *)&v72 + 1) * *((float *)&v72 + 1)) - (float)(*(float *)&v72
                                                                                           * *(float *)&v72));
              v41 = v44 + *((float *)&v68 + 1);
              v43 = (float)(*((float *)&v68 + 1) * 2.0) - v41;
              v42 = v40;
            }
            else
            {
              v38 = *(float *)&v72;
              v39 = o_sqrtf_0((float)(*(float *)&v72 * *(float *)&v72) - (float)(*((float *)&v72 + 1)
                                                                               * *((float *)&v72 + 1)));
              v40 = v39 + *(float *)&v68;
              v41 = *((float *)&v68 + 1);
              v42 = (float)(*(float *)&v68 * 2.0) - v40;
              v43 = *((float *)&v68 + 1);
            }
            v45 = *((float *)&v73 + 1) - v41;
            v46 = *(float *)&v73 - v40;
            v47 = o_sqrtf_0(
                    (float)((float)(*(float *)&v73 - v42) * (float)(*(float *)&v73 - v42))
                  + (float)((float)(*((float *)&v73 + 1) - v43) * (float)(*((float *)&v73 + 1) - v43)));
            v14 = (float)(v47 + o_sqrtf_0((float)(v46 * v46) + (float)(v45 * v45))) > (float)(v38 + v38);
          }
          else
          {
            v14 = 1;
          }
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v71);
        break;
      case 10:
        v14 = 1;
        break;
      default:
        xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v70 - 9), v11, (int)v12);
    }
  }
  v77 = operator new(0x28u);
  v63 = v69;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v77);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v64, a3);
  *(_DWORD *)(v65 + 16) = v9;
  *(_BYTE *)(v65 + 20) = v14;
  *(_DWORD *)(v65 + 24) = v66;
  *(_DWORD *)(v65 + 28) = v15;
  *(float *)(v65 + 32) = v63;
  std::shared_ptr<CXgcBrush>::shared_ptr<CXgcBrush>(a1, v65);
  return a1;
}

```

## disassembly

```asm
0x18002a684  mov     rax, rsp
0x18002a687  push    rbp
0x18002a688  push    rbx
0x18002a689  push    rsi
0x18002a68a  push    rdi
0x18002a68b  push    r14
0x18002a68d  push    r15
0x18002a68f  lea     rbp, [rax-4Fh]
0x18002a693  sub     rsp, 0E8h
0x18002a69a  movaps  xmmword ptr [rax-48h], xmm6
0x18002a69e  movaps  xmmword ptr [rax-58h], xmm7
0x18002a6a2  movaps  xmmword ptr [rax-68h], xmm8
0x18002a6a7  movaps  xmmword ptr [rax-78h], xmm9
0x18002a6ac  movaps  xmmword ptr [rax-88h], xmm10
0x18002a6b4  movaps  xmmword ptr [rax-98h], xmm11
0x18002a6bc  movaps  [rsp+110h+var_A8+8], xmm12
0x18002a6c2  mov     rax, r9
0x18002a6c5  mov     r14, r8
0x18002a6c8  mov     r10, rdx
0x18002a6cb  mov     r15, rcx
0x18002a6ce  xorps   xmm12, xmm12
0x18002a6d2  mov     dword ptr [rsp+110h+var_E8], 0
0x18002a6da  lea     r9, [rsp+110h+var_E8]
0x18002a6df  mov     r8, rax
0x18002a6e2  mov     rdx, r14
0x18002a6e5  mov     rcx, r10
0x18002a6e8  call    ?GetXpsBrushOpacity@@YAMAEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@std@@AEBUD2D_MATRIX_3X2_F@@PEAM@Z; GetXpsBrushOpacity(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,float *)
0x18002a6ed  movaps  xmm10, xmm0
0x18002a6f1  mov     dword ptr [rsp+110h+var_E8+4], 0
0x18002a6f9  mov     rcx, [r14]
0x18002a6fc  mov     rax, [rcx]
0x18002a6ff  lea     rdx, [rsp+110h+var_E8+4]
0x18002a704  mov     rax, [rax+20h]
0x18002a708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a70d  test    eax, eax
0x18002a70f  jns     short loc_18002A719
0x18002a711  mov     ecx, eax; this
0x18002a713  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a719  xor     bl, bl
0x18002a71b  xor     edi, edi
0x18002a71d  mov     ecx, dword ptr [rsp+110h+var_E8+4]
0x18002a721  movss   xmm11, cs:__real@3f800000
0x18002a72a  sub     ecx, 6
0x18002a72d  jz      loc_18002AAEE
0x18002a733  sub     ecx, 1
0x18002a736  jz      loc_18002A994
0x18002a73c  sub     ecx, 1
0x18002a73f  jz      loc_18002A988
0x18002a745  sub     ecx, 1; this
0x18002a748  jz      short loc_18002A75C
0x18002a74a  cmp     ecx, 1
0x18002a74d  jz      short loc_18002A755
0x18002a74f  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002a755  mov     bl, 1
0x18002a757  jmp     loc_18002AAEE
0x18002a75c  comiss  xmm11, xmm10
0x18002a760  setnbe  bl
0x18002a763  lea     rcx, [rsp+110h+var_E0]
0x18002a768  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a76d  nop
0x18002a76e  mov     dword ptr [rsp+110h+var_F0], 0
0x18002a776  mov     rcx, [r14]
0x18002a779  mov     rax, [rcx]
0x18002a77c  mov     [rbp+47h+var_C0], 0
0x18002a784  lea     rdx, [rsp+110h+var_F0]
0x18002a789  mov     [rbp+47h+var_B8], rdx
0x18002a78d  lea     rdx, [rsp+110h+var_E0]
0x18002a792  mov     [rbp+47h+var_B0], rdx
0x18002a796  lea     r8, [rbp+47h+var_C0]
0x18002a79a  lea     rdx, _GUID_75f207e5_08bf_413c_96b1_b82b4064176b
0x18002a7a1  mov     rax, [rax]
0x18002a7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7a9  mov     esi, eax
0x18002a7ab  lea     rcx, [rbp+47h+var_C0]
0x18002a7af  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002a7b4  mov     ecx, dword ptr [rsp+110h+var_F0]; this
0x18002a7b8  test    ecx, ecx
0x18002a7ba  jns     short loc_18002A7C2
0x18002a7bc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a7c2  test    esi, esi
0x18002a7c4  jns     short loc_18002A7CE
0x18002a7c6  mov     ecx, esi; this
0x18002a7c8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a7ce  test    bl, bl
0x18002a7d0  jnz     loc_18002A979
0x18002a7d6  mov     dword ptr [rsp+110h+var_F0], 0
0x18002a7de  mov     rcx, [rsp+110h+var_E0]
0x18002a7e3  mov     rax, [rcx]
0x18002a7e6  lea     rdx, [rsp+110h+var_F0]
0x18002a7eb  mov     rax, [rax+68h]
0x18002a7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7f4  test    eax, eax
0x18002a7f6  jns     short loc_18002A800
0x18002a7f8  mov     ecx, eax; this
0x18002a7fa  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a800  cmp     dword ptr [rsp+110h+var_F0], 1
0x18002a805  jz      short loc_18002A80E
0x18002a807  mov     bl, 1
0x18002a809  jmp     loc_18002A979
0x18002a80e  mov     [rsp+110h+var_F0], 0
0x18002a817  mov     qword ptr [rsp+48h], 0
0x18002a820  mov     [rsp+110h+var_D0], 0
0x18002a829  mov     rcx, [rsp+110h+var_E0]
0x18002a82e  mov     rax, [rcx]
0x18002a831  lea     rdx, [rsp+110h+var_F0]
0x18002a836  mov     rax, [rax+88h]
0x18002a83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a842  test    eax, eax
0x18002a844  jns     short loc_18002A84E
0x18002a846  mov     ecx, eax; this
0x18002a848  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a84e  mov     rcx, [rsp+110h+var_E0]
0x18002a853  mov     rax, [rcx]
0x18002a856  lea     rdx, [rsp+110h+var_C8]
0x18002a85b  mov     rax, [rax+0A8h]
0x18002a862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a867  test    eax, eax
0x18002a869  jns     short loc_18002A873
0x18002a86b  mov     ecx, eax; this
0x18002a86d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a873  mov     rcx, [rsp+110h+var_E0]
0x18002a878  mov     rax, [rcx]
0x18002a87b  lea     rdx, [rsp+110h+var_D0]
0x18002a880  mov     rax, [rax+98h]
0x18002a887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a88c  test    eax, eax
0x18002a88e  jns     short loc_18002A898
0x18002a890  mov     ecx, eax; this
0x18002a892  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a898  movss   xmm1, dword ptr [rsp+110h+var_D0]
0x18002a89e  movss   xmm2, dword ptr [rsp+110h+var_D0+4]
0x18002a8a4  comiss  xmm1, xmm2
0x18002a8a7  jbe     short loc_18002A8E5
0x18002a8a9  movaps  xmm9, xmm1
0x18002a8ad  movaps  xmm0, xmm1
0x18002a8b0  mulss   xmm0, xmm1
0x18002a8b4  mulss   xmm2, xmm2
0x18002a8b8  subss   xmm0, xmm2; X
0x18002a8bc  call    _o_sqrtf_0
0x18002a8c1  movaps  xmm6, xmm0
0x18002a8c4  movss   xmm2, dword ptr [rsp+110h+var_F0]
0x18002a8ca  addss   xmm6, xmm2
0x18002a8ce  movss   xmm0, dword ptr [rsp+110h+var_F0+4]
0x18002a8d4  mulss   xmm2, cs:__real@40000000
0x18002a8dc  subss   xmm2, xmm6
0x18002a8e0  movaps  xmm3, xmm0
0x18002a8e3  jmp     short loc_18002A91C
0x18002a8e5  movaps  xmm9, xmm2
0x18002a8e9  movss   xmm6, dword ptr [rsp+110h+var_F0]
0x18002a8ef  movaps  xmm0, xmm2
0x18002a8f2  mulss   xmm0, xmm2
0x18002a8f6  mulss   xmm1, xmm1
0x18002a8fa  subss   xmm0, xmm1; X
0x18002a8fe  call    _o_sqrtf_0
0x18002a903  movss   xmm3, dword ptr [rsp+110h+var_F0+4]
0x18002a909  addss   xmm0, xmm3
0x18002a90d  mulss   xmm3, cs:__real@40000000
0x18002a915  subss   xmm3, xmm0
0x18002a919  movaps  xmm2, xmm6
0x18002a91c  movss   xmm1, [rbp+47h+var_C4]
0x18002a921  movaps  xmm8, xmm1
0x18002a925  subss   xmm8, xmm0
0x18002a92a  movss   xmm0, [rsp+110h+var_C8]
0x18002a930  movaps  xmm7, xmm0
0x18002a933  subss   xmm7, xmm6
0x18002a937  subss   xmm1, xmm3
0x18002a93b  subss   xmm0, xmm2
0x18002a93f  mulss   xmm0, xmm0
0x18002a943  mulss   xmm1, xmm1
0x18002a947  addss   xmm0, xmm1; X
0x18002a94b  call    _o_sqrtf_0
0x18002a950  movaps  xmm6, xmm0
0x18002a953  mulss   xmm7, xmm7
0x18002a957  mulss   xmm8, xmm8
0x18002a95c  addss   xmm7, xmm8
0x18002a961  movaps  xmm0, xmm7; X
0x18002a964  call    _o_sqrtf_0
0x18002a969  addss   xmm6, xmm0
0x18002a96d  addss   xmm9, xmm9
0x18002a972  comiss  xmm6, xmm9
0x18002a976  setnbe  bl
0x18002a979  lea     rcx, [rsp+110h+var_E0]
0x18002a97e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a983  jmp     loc_18002AAEE
0x18002a988  comiss  xmm11, xmm10
0x18002a98c  setnbe  bl
0x18002a98f  jmp     loc_18002AAEE
0x18002a994  mov     dword ptr [rbp+47h+arg_10], edi
0x18002a997  lea     rcx, [rsp+110h+var_E0]
0x18002a99c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a9a1  nop
0x18002a9a2  mov     dword ptr [rsp+110h+var_F0], 0
0x18002a9aa  mov     rcx, [r14]
0x18002a9ad  mov     rax, [rcx]
0x18002a9b0  mov     [rbp+47h+var_C0], 0
0x18002a9b8  lea     rdx, [rsp+110h+var_F0]
0x18002a9bd  mov     [rbp+47h+var_B8], rdx
0x18002a9c1  lea     rdx, [rsp+110h+var_E0]
0x18002a9c6  mov     [rbp+47h+var_B0], rdx
0x18002a9ca  lea     r8, [rbp+47h+var_C0]
0x18002a9ce  lea     rdx, _GUID_3df0b466_d382_49ef_8550_dd94c80242e4
0x18002a9d5  mov     rax, [rax]
0x18002a9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9dd  mov     edi, eax
0x18002a9df  lea     rcx, [rbp+47h+var_C0]
0x18002a9e3  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002a9e8  mov     ecx, dword ptr [rsp+110h+var_F0]; this
0x18002a9ec  test    ecx, ecx
0x18002a9ee  jns     short loc_18002A9F6
0x18002a9f0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002a9f6  test    edi, edi
0x18002a9f8  jns     short loc_18002AA02
0x18002a9fa  mov     ecx, edi; this
0x18002a9fc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002aa02  mov     rcx, [rsp+110h+var_E0]
0x18002aa07  mov     rax, [rcx]
0x18002aa0a  lea     rdx, [rbp+47h+arg_10]
0x18002aa0e  mov     rax, [rax+80h]
0x18002aa15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa1a  test    eax, eax
0x18002aa1c  jns     short loc_18002AA26
0x18002aa1e  mov     ecx, eax; this
0x18002aa20  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002aa26  cmp     [rbp+47h+arg_28], 0
0x18002aa2a  jz      short loc_18002AA5E
0x18002aa2c  cmp     dword ptr [rbp+47h+arg_10], 1
0x18002aa30  jz      short loc_18002AA5E
0x18002aa32  mov     dword ptr [rbp+47h+arg_10], 1
0x18002aa39  mov     rcx, [rsp+110h+var_E0]
0x18002aa3e  mov     rax, [rcx]
0x18002aa41  mov     edx, 1
0x18002aa46  mov     rax, [rax+88h]
0x18002aa4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa52  test    eax, eax
0x18002aa54  jns     short loc_18002AA5E
0x18002aa56  mov     ecx, eax; this
0x18002aa58  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002aa5e  lea     rcx, [rsp+110h+var_E0]
0x18002aa63  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002aa68  mov     edx, dword ptr [rbp+47h+arg_10]
0x18002aa6b  cmp     edx, 1
0x18002aa6e  jz      short loc_18002AAB8
0x18002aa70  movss   xmm0, dword ptr [rsp+110h+var_E8]
0x18002aa76  comiss  xmm0, cs:__real@53100000
0x18002aa7d  jbe     short loc_18002AAB8
0x18002aa7f  mov     bl, 1
0x18002aa81  lea     rax, WPP_GLOBAL_Control
0x18002aa88  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa8f  cmp     rcx, rax
0x18002aa92  jz      short loc_18002AAB8
0x18002aa94  test    byte ptr [rcx+0E4h], 8
0x18002aa9b  jz      short loc_18002AAB8
0x18002aa9d  mov     edx, 0Ah
0x18002aaa2  lea     r8, WPP_f8f8585922d0359fe11623de1fb173cd_Traceguids
0x18002aaa9  mov     rcx, [rcx+0D8h]
0x18002aab0  call    WPP_SF_
0x18002aab5  mov     edx, dword ptr [rbp+47h+arg_10]
0x18002aab8  mov     rax, [rbp+47h+arg_20]
0x18002aabc  movss   xmm1, dword ptr [rax+0Ch]
0x18002aac1  subss   xmm1, dword ptr [rax+4]
0x18002aac6  movss   xmm0, dword ptr [rax+8]
0x18002aacb  subss   xmm0, dword ptr [rax]
0x18002aacf  mulss   xmm1, xmm0
0x18002aad3  movss   xmm0, dword ptr [rsp+110h+var_E8]
0x18002aad9  divss   xmm0, xmm1
0x18002aadd  movss   dword ptr [rsp+110h+var_E8], xmm0
0x18002aae3  xor     edi, edi
0x18002aae5  cmp     edx, 1
0x18002aae8  setnz   dil
0x18002aaec  inc     edi
0x18002aaee  mov     ecx, 28h ; '('; Size
0x18002aaf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002aaf8  mov     rcx, rax
0x18002aafb  mov     [rbp+47h+arg_10], rax
0x18002aaff  xor     r8d, r8d
0x18002ab02  comiss  xmm12, xmm10
0x18002ab06  jnb     short loc_18002AB13
0x18002ab08  comiss  xmm11, xmm10
0x18002ab0c  setbe   r8b
0x18002ab10  inc     r8d
0x18002ab13  movss   xmm0, dword ptr [rsp+110h+var_E8]
0x18002ab19  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002ab1e  mov     rdx, r14
0x18002ab21  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002ab26  movss   dword ptr [rcx+10h], xmm10
0x18002ab2c  mov     [rcx+14h], bl
0x18002ab2f  mov     [rcx+18h], r8d
0x18002ab33  mov     [rcx+1Ch], edi
0x18002ab36  movss   dword ptr [rcx+20h], xmm0
0x18002ab3b  mov     rdx, rcx
0x18002ab3e  mov     rcx, r15
0x18002ab41  call    ??$?0VCXgcBrush@@$0A@@?$shared_ptr@VCXgcBrush@@@std@@QEAA@PEAVCXgcBrush@@@Z; std::shared_ptr<CXgcBrush>::shared_ptr<CXgcBrush>(CXgcBrush *)
0x18002ab46  mov     rax, r15
0x18002ab49  lea     r11, [rsp+110h+var_28]
0x18002ab51  movaps  xmm6, xmmword ptr [r11-18h]
0x18002ab56  movaps  xmm7, xmmword ptr [r11-28h]
0x18002ab5b  movaps  xmm8, xmmword ptr [r11-38h]
0x18002ab60  movaps  xmm9, xmmword ptr [r11-48h]
0x18002ab65  movaps  xmm10, xmmword ptr [r11-58h]
0x18002ab6a  movaps  xmm11, xmmword ptr [r11-68h]
  ... truncated ...
```
