# xgc::GDIExporter::StrokePath(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<IXpsOMBrush> const &,std::shared_ptr<CXgcPenStyle> const &)

- ea: `0x180028098`
- end: `0x180028331`
- name: `?StrokePath@GDIExporter@xgc@@AEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@UIXpsOMBrush@@@4@AEBV?$shared_ptr@VCXgcPenStyle@@@4@@Z`
- size: `665`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180016afc`

## callees

- `0x180008830`
- `0x18000d428`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180025488`
- `0x180027cd4`
- `0x180027d3c`
- `0x180028098`
- `0x180028338`
- `0x180031ebc`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
double __fastcall xgc::GDIExporter::StrokePath(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ****a3)(__int64, GUID *, __int64 *),
        __int64 a4)
{
  int v8; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 (__fastcall ***v12)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v13)(__int64, GUID *, __int64 *); // rax
  int v14; // edi
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // rax
  int v19; // edi
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  double result; // xmm0_8
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  xpsrdr *v29; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  xpsrdr **v31; // [rsp+48h] [rbp-B8h]
  _BYTE *v32; // [rsp+50h] [rbp-B0h]
  _BYTE v33[16]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v34[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v35[24]; // [rsp+80h] [rbp-80h] BYREF
  xpsrdr *v36; // [rsp+98h] [rbp-68h]
  _OWORD v37[3]; // [rsp+100h] [rbp+0h] BYREF

  v28 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), unsigned int *))(**a3)[4])(
         *a3,
         &v28);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_7e58419596e83e61fd1446f073f22ec0_Traceguids, v28);
  if ( v28 == 6 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v34);
    LODWORD(v29) = 0;
    v12 = *a3;
    v13 = **a3;
    v30 = 0;
    v31 = &v29;
    v32 = v34;
    v14 = (*v13)((__int64)v12, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v30);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v30);
    if ( (int)v29 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v15, v16, v17);
    if ( v14 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
    memset(v37, 0, 44);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v33);
    LODWORD(v29) = 0;
    v18 = *(_QWORD *)v34[0];
    v30 = 0;
    v31 = &v29;
    v32 = v33;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64 *))(v18 + 56))(v34[0], v37, &v30);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v30);
    if ( (int)v29 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v20, v21, v22);
    if ( v19 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
    if ( (unsigned __int8)xgc::CDeviceContext::SelectPen(*(xgc::CDeviceContext **)(a1 + 8), (__int64)a2, a1) )
    {
      xgc::CGDIPathData::CGDIPathData(v35, *(_QWORD *)(a1 + 8), 0, a1 + 4);
      xgc::CDeviceContext::CurrentScale(*(_QWORD *)(a1 + 8), &v29);
      v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 72LL))(*a2, 0, 0);
      if ( v23 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
      if ( (int)v36 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v36, v24, v25, v26);
      xgc::CGDIPathData::~CGDIPathData((xgc::CGDIPathData *)v35);
    }
    else
    {
      xgc::GDIExporter::WidenAndFill(a1, a2, a3, a4);
    }
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v33);
    return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v34);
  }
  else
  {
    xgc::GDIExporter::WidenAndFill(a1, a2, a3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180028098  push    rbp
0x18002809a  push    rbx
0x18002809b  push    rsi
0x18002809c  push    rdi
0x18002809d  push    r14
0x18002809f  push    r15
0x1800280a1  lea     rbp, [rsp-48h]
0x1800280a6  sub     rsp, 148h
0x1800280ad  mov     rax, cs:__security_cookie
0x1800280b4  xor     rax, rsp
0x1800280b7  mov     [rbp+70h+var_40], rax
0x1800280bb  mov     r14, r9
0x1800280be  mov     r15, r8
0x1800280c1  mov     rsi, rdx
0x1800280c4  mov     rbx, rcx
0x1800280c7  mov     [rsp+170h+var_140], 0
0x1800280cf  mov     rcx, [r8]
0x1800280d2  mov     rax, [rcx]
0x1800280d5  lea     rdx, [rsp+170h+var_140]
0x1800280da  mov     rax, [rax+20h]
0x1800280de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e3  test    eax, eax
0x1800280e5  jns     short loc_1800280EF
0x1800280e7  mov     ecx, eax; this
0x1800280e9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800280ef  lea     rax, WPP_GLOBAL_Control
0x1800280f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280fd  cmp     rcx, rax
0x180028100  jz      short loc_180028128
0x180028102  test    byte ptr [rcx+0E4h], 8
0x180028109  jz      short loc_180028128
0x18002810b  mov     edx, 0Ah
0x180028110  mov     r9d, [rsp+170h+var_140]
0x180028115  lea     r8, WPP_7e58419596e83e61fd1446f073f22ec0_Traceguids
0x18002811c  mov     rcx, [rcx+0D8h]
0x180028123  call    WPP_SF_d
0x180028128  cmp     [rsp+170h+var_140], 6
0x18002812d  jz      short loc_180028145
0x18002812f  mov     r9, r14
0x180028132  mov     r8, r15
0x180028135  mov     rdx, rsi
0x180028138  mov     rcx, rbx
0x18002813b  call    ?WidenAndFill@GDIExporter@xgc@@AEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@UIXpsOMBrush@@@4@AEBV?$shared_ptr@VCXgcPenStyle@@@4@@Z; xgc::GDIExporter::WidenAndFill(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<IXpsOMBrush> const &,std::shared_ptr<CXgcPenStyle> const &)
0x180028140  jmp     loc_180028315
0x180028145  lea     rcx, [rsp+170h+var_108]
0x18002814a  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002814f  nop
0x180028150  mov     dword ptr [rsp+170h+var_13C], 0
0x180028158  mov     rcx, [r15]
0x18002815b  mov     rax, [rcx]
0x18002815e  mov     [rsp+170h+var_130], 0
0x180028167  lea     rdx, [rsp+170h+var_13C]
0x18002816c  mov     [rsp+170h+var_128], rdx
0x180028171  lea     rdx, [rsp+170h+var_108]
0x180028176  mov     [rsp+170h+var_120], rdx
0x18002817b  lea     r8, [rsp+170h+var_130]
0x180028180  lea     rdx, _GUID_a06f9f05_3be9_4763_98a8_094fc672e488
0x180028187  mov     rax, [rax]
0x18002818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002818f  mov     edi, eax
0x180028191  lea     rcx, [rsp+170h+var_130]
0x180028196  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002819b  mov     ecx, dword ptr [rsp+170h+var_13C]; this
0x18002819f  test    ecx, ecx
0x1800281a1  jns     short loc_1800281A9
0x1800281a3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800281a9  test    edi, edi
0x1800281ab  jns     short loc_1800281B5
0x1800281ad  mov     ecx, edi; this
0x1800281af  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800281b5  xorps   xmm0, xmm0
0x1800281b8  movups  [rbp+70h+var_70], xmm0
0x1800281bc  movups  xmmword ptr [rbp+70h+var_60], xmm0
0x1800281c0  movups  xmmword ptr [rbp+70h+var_60+0Ch], xmm0
0x1800281c4  lea     rcx, [rsp+170h+var_118]
0x1800281c9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800281ce  nop
0x1800281cf  mov     dword ptr [rsp+170h+var_13C], 0
0x1800281d7  mov     rcx, [rsp+170h+var_108]
0x1800281dc  mov     rax, [rcx]
0x1800281df  mov     [rsp+170h+var_130], 0
0x1800281e8  lea     rdx, [rsp+170h+var_13C]
0x1800281ed  mov     [rsp+170h+var_128], rdx
0x1800281f2  lea     rdx, [rsp+170h+var_118]
0x1800281f7  mov     [rsp+170h+var_120], rdx
0x1800281fc  lea     r8, [rsp+170h+var_130]
0x180028201  lea     rdx, [rbp+70h+var_70]
0x180028205  mov     rax, [rax+38h]
0x180028209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002820e  mov     edi, eax
0x180028210  lea     rcx, [rsp+170h+var_130]
0x180028215  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002821a  mov     ecx, dword ptr [rsp+170h+var_13C]; this
0x18002821e  test    ecx, ecx
0x180028220  jns     short loc_180028228
0x180028222  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028228  test    edi, edi
0x18002822a  jns     short loc_180028234
0x18002822c  mov     ecx, edi; this
0x18002822e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028234  mov     [rsp+170h+var_148], rbx; __int64
0x180028239  mov     [rsp+170h+var_150], rsi; __int64
0x18002823e  lea     r9, [rsp+170h+var_118]
0x180028243  lea     r8, [rbp+70h+var_70]
0x180028247  mov     rdx, r14
0x18002824a  mov     rcx, [rbx+8]; this
0x18002824e  call    ?SelectPen@CDeviceContext@xgc@@QEAA_NAEBV?$shared_ptr@VCXgcPenStyle@@@std@@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@4@AEBV?$shared_ptr@UID2D1Geometry@@@4@AEAUSqmDWordCounter@2@@Z; xgc::CDeviceContext::SelectPen(std::shared_ptr<CXgcPenStyle> const &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &,std::shared_ptr<ID2D1Geometry> const &,xgc::SqmDWordCounter &)
0x180028253  test    al, al
0x180028255  jnz     short loc_18002826D
0x180028257  mov     r9, r14
0x18002825a  mov     r8, r15
0x18002825d  mov     rdx, rsi
0x180028260  mov     rcx, rbx
0x180028263  call    ?WidenAndFill@GDIExporter@xgc@@AEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@UIXpsOMBrush@@@4@AEBV?$shared_ptr@VCXgcPenStyle@@@4@@Z; xgc::GDIExporter::WidenAndFill(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<IXpsOMBrush> const &,std::shared_ptr<CXgcPenStyle> const &)
0x180028268  jmp     loc_180028300
0x18002826d  lea     r9, [rbx+4]
0x180028271  xor     r8d, r8d
0x180028274  mov     rdx, [rbx+8]
0x180028278  lea     rcx, [rbp+70h+var_F0]
0x18002827c  call    ??0CGDIPathData@xgc@@QEAA@AEAVCDeviceContext@1@W4Enum@PathDataPurpose@1@AEAUSqmDWordCounter@1@@Z; xgc::CGDIPathData::CGDIPathData(xgc::CDeviceContext &,xgc::PathDataPurpose::Enum,xgc::SqmDWordCounter &)
0x180028281  nop
0x180028282  lea     rdx, [rsp+170h+var_13C]
0x180028287  mov     rcx, [rbx+8]
0x18002828b  call    ?CurrentScale@CDeviceContext@xgc@@QEBA?AUMinMaxScaling@xpsrdr@@XZ; xgc::CDeviceContext::CurrentScale(void)
0x180028290  movss   xmm2, dword ptr [rax+4]
0x180028295  movaps  xmm1, xmm2
0x180028298  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18002829f  movss   xmm0, cs:__real@34000000
0x1800282a7  comiss  xmm0, xmm1
0x1800282aa  jbe     short loc_1800282B4
0x1800282ac  movss   xmm2, cs:__real@3f800000
0x1800282b4  mov     rcx, [rsi]
0x1800282b7  mov     rax, [rcx]
0x1800282ba  movss   xmm3, cs:__real@3d4ccccd
0x1800282c2  divss   xmm3, xmm2
0x1800282c6  lea     rdx, [rbp+70h+var_F0]
0x1800282ca  mov     [rsp+170h+var_150], rdx
0x1800282cf  xor     r8d, r8d
0x1800282d2  xor     edx, edx
0x1800282d4  mov     rax, [rax+48h]
0x1800282d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282dd  test    eax, eax
0x1800282df  jns     short loc_1800282E9
0x1800282e1  mov     ecx, eax; this
0x1800282e3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800282e9  mov     ecx, dword ptr [rbp+70h+var_D8]; this
0x1800282ec  test    ecx, ecx
0x1800282ee  jns     short loc_1800282F6
0x1800282f0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800282f6  lea     rcx, [rbp+70h+var_F0]; this
0x1800282fa  call    ??1CGDIPathData@xgc@@UEAA@XZ; xgc::CGDIPathData::~CGDIPathData(void)
0x1800282ff  nop
0x180028300  lea     rcx, [rsp+170h+var_118]
0x180028305  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002830a  nop
0x18002830b  lea     rcx, [rsp+170h+var_108]
0x180028310  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028315  mov     rcx, [rbp+70h+var_40]
0x180028319  xor     rcx, rsp; StackCookie
0x18002831c  call    __security_check_cookie
0x180028321  add     rsp, 148h
0x180028328  pop     r15
0x18002832a  pop     r14
0x18002832c  pop     rdi
0x18002832d  pop     rsi
0x18002832e  pop     rbx
0x18002832f  pop     rbp
0x180028330  retn
```
