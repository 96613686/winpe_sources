# CXgcPath::SendXgcVisual(xgc::GDIExporter *)

- ea: `0x1800192f0`
- end: `0x180019674`
- name: `?SendXgcVisual@CXgcPath@@UEAAXPEAVGDIExporter@xgc@@@Z`
- size: `900`
- prototype: `void __fastcall(CXgcPath *__hidden this, struct xgc::GDIExporter *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180009de0`
- `0x18000d7f8`
- `0x18000e15c`
- `0x18000e990`
- `0x180011b0c`
- `0x1800169f4`
- `0x180016afc`
- `0x1800184e8`
- `0x1800192f0`
- `0x180019a40`
- `0x180026c28`
- `0x180026c5c`
- `0x18002a560`
- `0x18002a588`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CXgcPath::SendXgcVisual(CXgcPath *this, struct D2D_MATRIX_3X2_F **a2)
{
  char *v4; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  PVOID *v7; // rcx
  _QWORD *v8; // rsi
  __int64 v9; // rdi
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  _QWORD *v18; // rdi
  __int64 v19; // r14
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  char v28; // r14
  _QWORD *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  int v34; // r9d
  int v35; // eax
  int v36; // edx
  const char *v37; // r8
  int v38; // r9d
  _QWORD v39[2]; // [rsp+38h] [rbp-29h] BYREF
  _QWORD v40[2]; // [rsp+48h] [rbp-19h] BYREF
  _BYTE v41[16]; // [rsp+58h] [rbp-9h] BYREF
  __int128 v42; // [rsp+68h] [rbp+7h] BYREF
  __int64 v43; // [rsp+78h] [rbp+17h]
  int v44; // [rsp+C8h] [rbp+67h] BYREF
  int v45; // [rsp+D8h] [rbp+77h] BYREF

  v4 = (char *)this + 216;
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 216) )
    return;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v40);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v39);
  v44 = 1065353216;
  v45 = 1065353216;
  if ( *((_DWORD *)this + 3) != 1 || *((_BYTE *)this + 31) )
    goto LABEL_7;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
    {
LABEL_8:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 228) & 8) != 0 )
        WPP_SF_qq(v7[27], v5, v6, *((_QWORD *)this + 21), *((_QWORD *)this + 23));
      goto LABEL_11;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_990c7c55e5c43c2ce52177515884c160_Traceguids);
LABEL_7:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
LABEL_11:
  v8 = (_QWORD *)((char *)this + 168);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168) )
  {
    std::shared_ptr<ID2D1Brush>::operator=(v40, *v8);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v40) )
    {
      if ( !*((_BYTE *)this + 31) && (*((float *)this + 2) < 1.0 || *(_DWORD *)(*v8 + 24LL) != 2) )
      {
        v9 = v40[0];
        v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v40[0] + 40LL))(v40[0], &v44);
        if ( v10 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 48LL))(v9);
        if ( v14 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
      }
    }
  }
  v18 = (_QWORD *)((char *)this + 184);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 184) )
  {
    std::shared_ptr<ID2D1Brush>::operator=(v39, *v18);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v39) )
    {
      if ( !*((_BYTE *)this + 31) && (*((float *)this + 2) < 1.0 || *(_DWORD *)(*v18 + 24LL) != 2) )
      {
        v19 = v39[0];
        v20 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v39[0] + 40LL))(v39[0], &v45);
        if ( v20 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
        v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 48LL))(v19);
        if ( v24 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
      }
    }
  }
  v28 = std::operator!=<ID3D11Device>(v40);
  if ( v28 || (unsigned __int8)std::operator!=<ID3D11Device>(v39) )
  {
    if ( *((_BYTE *)this + 31) )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v41);
      if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 40) )
        std::shared_ptr<ID2D1Brush>::operator=(v41, *v29 + 16LL);
      v42 = *(_OWORD *)((char *)this + 104);
      v43 = *((_QWORD *)this + 15);
      xgc::GDIExporter::AddtoSolidPathCluster(a2, this, v41, &v42);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v41);
    }
    else
    {
      xgc::CDeviceContext::PushTransform(a2[1], (const struct D2D_MATRIX_3X2_F *)((char *)this + 104));
      CXgcVisual::PushClip(this, (struct xgc::GDIExporter *)a2);
      v30 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>((__int64)v4);
      xgc::GDIExporter::DrawGeometry((__int64)a2, v30 + 16);
      CXgcVisual::PopClip(this, (struct xgc::GDIExporter *)a2);
      xgc::CDeviceContext::PopTransform((xgc::CDeviceContext *)a2[1]);
    }
    if ( v28 && !*((_BYTE *)this + 31) && (*((float *)this + 2) < 1.0 || *(_DWORD *)(*v8 + 24LL) != 2) )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 48LL))(v40[0]);
      if ( v31 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v31, v32, v33, v34);
    }
  }
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v39)
    && !*((_BYTE *)this + 31)
    && (*((float *)this + 2) < 1.0 || *(_DWORD *)(*v18 + 24LL) != 2) )
  {
    v35 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v39[0] + 48LL))(v39[0]);
    if ( v35 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v36, v37, v38);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v39);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v40);
}

```

## disassembly

```asm
0x1800192f0  mov     rax, rsp
0x1800192f3  mov     [rax+10h], rbx
0x1800192f7  mov     [rax+20h], rsi
0x1800192fb  push    rbp
0x1800192fc  push    rdi
0x1800192fd  push    r12
0x1800192ff  push    r14
0x180019301  push    r15
0x180019303  lea     rbp, [rax-5Fh]
0x180019307  sub     rsp, 90h
0x18001930e  movaps  xmmword ptr [rax-38h], xmm6
0x180019312  mov     r15, rdx
0x180019315  mov     rbx, rcx
0x180019318  lea     r12, [rcx+0D8h]
0x18001931f  mov     rcx, r12
0x180019322  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019327  test    al, al
0x180019329  jz      loc_180019653
0x18001932f  lea     rcx, [rbp+57h+var_70]
0x180019333  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019338  nop
0x180019339  lea     rcx, [rbp+57h+var_80]
0x18001933d  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019342  nop
0x180019343  movss   xmm6, cs:__real@3f800000
0x18001934b  mov     [rbp+57h+arg_0], 3F800000h
0x180019352  mov     [rbp+57h+arg_10], 3F800000h
0x180019359  lea     rdi, WPP_GLOBAL_Control
0x180019360  cmp     dword ptr [rbx+0Ch], 1
0x180019364  jnz     short loc_180019399
0x180019366  cmp     byte ptr [rbx+1Fh], 0
0x18001936a  jnz     short loc_180019399
0x18001936c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019373  cmp     rcx, rdi
0x180019376  jz      short loc_1800193CD
0x180019378  test    byte ptr [rcx+0E4h], 4
0x18001937f  jz      short loc_1800193A0
0x180019381  mov     edx, 0Bh
0x180019386  lea     r8, WPP_990c7c55e5c43c2ce52177515884c160_Traceguids
0x18001938d  mov     rcx, [rcx+0D8h]
0x180019394  call    WPP_SF_
0x180019399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193a0  cmp     rcx, rdi
0x1800193a3  jz      short loc_1800193CD
0x1800193a5  test    byte ptr [rcx+0E4h], 8
0x1800193ac  jz      short loc_1800193CD
0x1800193ae  mov     rax, [rbx+0B8h]
0x1800193b5  mov     [rsp+0B0h+var_90], rax
0x1800193ba  mov     r9, [rbx+0A8h]
0x1800193c1  mov     rcx, [rcx+0D8h]
0x1800193c8  call    WPP_SF_qq
0x1800193cd  lea     rsi, [rbx+0A8h]
0x1800193d4  mov     rcx, rsi
0x1800193d7  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800193dc  test    al, al
0x1800193de  jz      short loc_18001945E
0x1800193e0  mov     rdx, [rsi]
0x1800193e3  lea     rcx, [rbp+57h+var_70]
0x1800193e7  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800193ec  lea     rcx, [rbp+57h+var_70]
0x1800193f0  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800193f5  test    al, al
0x1800193f7  jz      short loc_18001945E
0x1800193f9  cmp     byte ptr [rbx+1Fh], 0
0x1800193fd  jnz     short loc_18001945E
0x1800193ff  comiss  xmm6, dword ptr [rbx+8]
0x180019403  ja      short loc_18001940E
0x180019405  mov     rax, [rsi]
0x180019408  cmp     dword ptr [rax+18h], 2
0x18001940c  jz      short loc_18001945E
0x18001940e  mov     rdi, [rbp+57h+var_70]
0x180019412  mov     rax, [rdi]
0x180019415  lea     rdx, [rbp+57h+arg_0]
0x180019419  mov     rcx, rdi
0x18001941c  mov     rax, [rax+28h]
0x180019420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019425  test    eax, eax
0x180019427  jns     short loc_180019431
0x180019429  mov     ecx, eax; this
0x18001942b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180019431  mov     rax, [rdi]
0x180019434  movss   xmm1, [rbp+57h+arg_0]
0x180019439  mulss   xmm1, dword ptr [rbx+8]
0x18001943e  mulss   xmm1, cs:__real@3f000000
0x180019446  mov     rcx, rdi
0x180019449  mov     rax, [rax+30h]
0x18001944d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019452  test    eax, eax
0x180019454  jns     short loc_18001945E
0x180019456  mov     ecx, eax; this
0x180019458  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001945e  lea     rdi, [rbx+0B8h]
0x180019465  mov     rcx, rdi
0x180019468  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18001946d  test    al, al
0x18001946f  jz      short loc_1800194EF
0x180019471  mov     rdx, [rdi]
0x180019474  lea     rcx, [rbp+57h+var_80]
0x180019478  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18001947d  lea     rcx, [rbp+57h+var_80]
0x180019481  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019486  test    al, al
0x180019488  jz      short loc_1800194EF
0x18001948a  cmp     byte ptr [rbx+1Fh], 0
0x18001948e  jnz     short loc_1800194EF
0x180019490  comiss  xmm6, dword ptr [rbx+8]
0x180019494  ja      short loc_18001949F
0x180019496  mov     rax, [rdi]
0x180019499  cmp     dword ptr [rax+18h], 2
0x18001949d  jz      short loc_1800194EF
0x18001949f  mov     r14, [rbp+57h+var_80]
0x1800194a3  mov     rax, [r14]
0x1800194a6  lea     rdx, [rbp+57h+arg_10]
0x1800194aa  mov     rcx, r14
0x1800194ad  mov     rax, [rax+28h]
0x1800194b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194b6  test    eax, eax
0x1800194b8  jns     short loc_1800194C2
0x1800194ba  mov     ecx, eax; this
0x1800194bc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800194c2  mov     rax, [r14]
0x1800194c5  movss   xmm1, [rbp+57h+arg_10]
0x1800194ca  mulss   xmm1, dword ptr [rbx+8]
0x1800194cf  mulss   xmm1, cs:__real@3f000000
0x1800194d7  mov     rcx, r14
0x1800194da  mov     rax, [rax+30h]
0x1800194de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194e3  test    eax, eax
0x1800194e5  jns     short loc_1800194EF
0x1800194e7  mov     ecx, eax; this
0x1800194e9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800194ef  lea     rcx, [rbp+57h+var_70]
0x1800194f3  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800194f8  mov     r14b, al
0x1800194fb  test    al, al
0x1800194fd  jnz     short loc_180019510
0x1800194ff  lea     rcx, [rbp+57h+var_80]
0x180019503  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019508  test    al, al
0x18001950a  jz      loc_1800195FD
0x180019510  cmp     byte ptr [rbx+1Fh], 0
0x180019514  jz      short loc_18001956E
0x180019516  lea     rcx, [rbp+57h+var_60]
0x18001951a  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18001951f  nop
0x180019520  lea     rcx, [rbx+28h]
0x180019524  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019529  test    al, al
0x18001952b  jz      short loc_18001953D
0x18001952d  mov     rdx, [rcx]
0x180019530  add     rdx, 10h
0x180019534  lea     rcx, [rbp+57h+var_60]
0x180019538  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18001953d  movups  xmm0, xmmword ptr [rbx+68h]
0x180019541  movaps  [rbp+57h+var_50], xmm0
0x180019545  movsd   xmm1, qword ptr [rbx+78h]
0x18001954a  movsd   [rbp+57h+var_40], xmm1
0x18001954f  lea     r9, [rbp+57h+var_50]
0x180019553  lea     r8, [rbp+57h+var_60]
0x180019557  mov     rdx, rbx
0x18001955a  mov     rcx, r15
0x18001955d  call    ?AddtoSolidPathCluster@GDIExporter@xgc@@QEAAXPEAVCXgcPath@@AEAV?$shared_ptr@UID2D1Geometry@@@std@@UD2D_MATRIX_3X2_F@@@Z; xgc::GDIExporter::AddtoSolidPathCluster(CXgcPath *,std::shared_ptr<ID2D1Geometry> &,D2D_MATRIX_3X2_F)
0x180019562  nop
0x180019563  lea     rcx, [rbp+57h+var_60]
0x180019567  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001956c  jmp     short loc_1800195C2
0x18001956e  lea     rdx, [rbx+68h]; struct D2D_MATRIX_3X2_F *
0x180019572  mov     rcx, [r15+8]; this
0x180019576  call    ?PushTransform@CDeviceContext@xgc@@QEAAXAEBUD2D_MATRIX_3X2_F@@@Z; xgc::CDeviceContext::PushTransform(D2D_MATRIX_3X2_F const &)
0x18001957b  mov     rdx, r15; struct xgc::GDIExporter *
0x18001957e  mov     rcx, rbx; this
0x180019581  call    ?PushClip@CXgcVisual@@QEAAXPEAVGDIExporter@xgc@@@Z; CXgcVisual::PushClip(xgc::GDIExporter *)
0x180019586  mov     rcx, r12
0x180019589  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18001958e  add     rax, 10h
0x180019592  lea     r9, [rbx+0C8h]
0x180019599  mov     [rsp+0B0h+var_90], rax; __int64
0x18001959e  lea     r8, [rbp+57h+var_80]
0x1800195a2  lea     rdx, [rbp+57h+var_70]
0x1800195a6  mov     rcx, r15; __int64
0x1800195a9  call    ?DrawGeometry@GDIExporter@xgc@@QEAAXAEBV?$shared_ptr@UIXpsOMBrush@@@std@@0AEBV?$shared_ptr@VCXgcPenStyle@@@4@AEBV?$shared_ptr@UID2D1Geometry@@@4@@Z; xgc::GDIExporter::DrawGeometry(std::shared_ptr<IXpsOMBrush> const &,std::shared_ptr<IXpsOMBrush> const &,std::shared_ptr<CXgcPenStyle> const &,std::shared_ptr<ID2D1Geometry> const &)
0x1800195ae  mov     rdx, r15; struct xgc::GDIExporter *
0x1800195b1  mov     rcx, rbx; this
0x1800195b4  call    ?PopClip@CXgcVisual@@QEAAXPEAVGDIExporter@xgc@@@Z; CXgcVisual::PopClip(xgc::GDIExporter *)
0x1800195b9  mov     rcx, [r15+8]; this
0x1800195bd  call    ?PopTransform@CDeviceContext@xgc@@QEAAXXZ; xgc::CDeviceContext::PopTransform(void)
0x1800195c2  test    r14b, r14b
0x1800195c5  jz      short loc_1800195FD
0x1800195c7  cmp     byte ptr [rbx+1Fh], 0
0x1800195cb  jnz     short loc_1800195FD
0x1800195cd  comiss  xmm6, dword ptr [rbx+8]
0x1800195d1  ja      short loc_1800195DC
0x1800195d3  mov     rax, [rsi]
0x1800195d6  cmp     dword ptr [rax+18h], 2
0x1800195da  jz      short loc_1800195FD
0x1800195dc  mov     rcx, [rbp+57h+var_70]
0x1800195e0  mov     rax, [rcx]
0x1800195e3  movss   xmm1, [rbp+57h+arg_0]
0x1800195e8  mov     rax, [rax+30h]
0x1800195ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f1  test    eax, eax
0x1800195f3  jns     short loc_1800195FD
0x1800195f5  mov     ecx, eax; this
0x1800195f7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800195fd  lea     rcx, [rbp+57h+var_80]
0x180019601  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019606  test    al, al
0x180019608  jz      short loc_180019640
0x18001960a  cmp     byte ptr [rbx+1Fh], 0
0x18001960e  jnz     short loc_180019640
0x180019610  comiss  xmm6, dword ptr [rbx+8]
0x180019614  ja      short loc_18001961F
0x180019616  mov     rax, [rdi]
0x180019619  cmp     dword ptr [rax+18h], 2
0x18001961d  jz      short loc_180019640
0x18001961f  mov     rcx, [rbp+57h+var_80]
0x180019623  mov     rax, [rcx]
0x180019626  movss   xmm1, [rbp+57h+arg_10]
0x18001962b  mov     rax, [rax+30h]
0x18001962f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019634  test    eax, eax
0x180019636  jns     short loc_180019640
0x180019638  mov     ecx, eax; this
0x18001963a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180019640  lea     rcx, [rbp+57h+var_80]
0x180019644  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019649  nop
0x18001964a  lea     rcx, [rbp+57h+var_70]
0x18001964e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019653  lea     r11, [rsp+0B0h+var_20]
0x18001965b  mov     rbx, [r11+38h]
0x18001965f  mov     rsi, [r11+48h]
0x180019663  movaps  xmm6, xmmword ptr [r11-10h]
0x180019668  mov     rsp, r11
0x18001966b  pop     r15
0x18001966d  pop     r14
0x18001966f  pop     r12
0x180019671  pop     rdi
0x180019672  pop     rbp
0x180019673  retn
```
