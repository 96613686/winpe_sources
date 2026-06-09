# xpsrdr::VisualsRasterizer::CopyToOutputBuffer(D2D_RECT_U &,std::shared_ptr<IWICBitmap> &)

- ea: `0x180037c20`
- end: `0x180037e10`
- name: `?CopyToOutputBuffer@VisualsRasterizer@xpsrdr@@AEAAJAEAUD2D_RECT_U@@AEAV?$shared_ptr@UIWICBitmap@@@std@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003890c`

## callees

- `0x180008830`
- `0x1800093ac`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x1800333f0`
- `0x180033f38`
- `0x180037278`
- `0x180037c20`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall xpsrdr::VisualsRasterizer::CopyToOutputBuffer(__int64 a1, int *a2)
{
  __int64 **v3; // r8
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  int v7; // edx
  const char *v8; // r8
  int v9; // r9d
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // r10
  struct _GUID *v19; // rdx
  int v20; // r14d
  char *v21; // rbx
  char *v22; // rdi
  unsigned __int64 i; // rsi
  __int16 BytesPerPixel; // ax
  int v26; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-65h] BYREF
  int v28; // [rsp+48h] [rbp-61h] BYREF
  void *v29; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v31; // [rsp+70h] [rbp-39h] BYREF
  _QWORD *v32; // [rsp+80h] [rbp-29h]
  _QWORD v33[3]; // [rsp+90h] [rbp-19h] BYREF
  void *Src; // [rsp+A8h] [rbp-1h] BYREF
  unsigned int v35; // [rsp+B0h] [rbp+7h]
  char v36; // [rsp+B8h] [rbp+Fh]
  int v37; // [rsp+C0h] [rbp+17h] BYREF
  int v38; // [rsp+C4h] [rbp+1Bh]
  int v39; // [rsp+C8h] [rbp+1Fh]
  unsigned int v40; // [rsp+CCh] [rbp+23h]

  v37 = *a2;
  v38 = a2[1];
  v39 = a2[2] - v37;
  v40 = a2[3] - v38;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
  v26 = 0;
  v4 = *v3;
  v5 = **v3;
  *(_QWORD *)&v31 = 0;
  *((_QWORD *)&v31 + 1) = &v26;
  v32 = v30;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64, __int128 *))(v5 + 64))(v4, &v37, 2, &v31);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
  if ( v26 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v7, v8, v9);
  if ( v6 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v7, v8, v9);
  v27 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v30[0] + 32LL))(v30[0], &v27);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  v29 = 0;
  v28 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, int *, void **))(*(_QWORD *)v30[0] + 40LL))(v30[0], &v28, &v29);
  if ( v14 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v33);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v33, (_QWORD *)(*(_QWORD *)a1 + 64LL));
  v33[2] = v18;
  v36 = 1;
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, void **))(*(_QWORD *)v33[0] + 112LL))(
          v33[0],
          v18,
          0,
          1,
          0,
          &Src);
  if ( v20 >= 0 )
  {
    v21 = (char *)Src;
    v22 = (char *)v29;
    for ( i = 0; i < v40; ++i )
    {
      v31 = *(_OWORD *)(*(_QWORD *)a1 + 100LL);
      BytesPerPixel = xpsrdr::GetBytesPerPixel((xpsrdr *)&v31, v19);
      memcpy_0(v22, v21, v39 * BytesPerPixel);
      v21 += v35;
      v22 += v27;
    }
  }
  xpsrdr::D3D11TextureMapUnmapHelper::~D3D11TextureMapUnmapHelper((xpsrdr::D3D11TextureMapUnmapHelper *)v33);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180037c20  mov     [rsp-8+arg_18], rbx
0x180037c25  push    rbp
0x180037c26  push    rsi
0x180037c27  push    rdi
0x180037c28  push    r14
0x180037c2a  push    r15
0x180037c2c  lea     rbp, [rsp-37h]
0x180037c31  sub     rsp, 0E0h
0x180037c38  mov     rax, cs:__security_cookie
0x180037c3f  xor     rax, rsp
0x180037c42  mov     [rbp+57h+var_30], rax
0x180037c46  mov     r15, rcx
0x180037c49  mov     r9d, [rdx]
0x180037c4c  mov     [rbp+57h+var_40], r9d
0x180037c50  mov     r10d, [rdx+4]
0x180037c54  mov     [rbp+57h+var_3C], r10d
0x180037c58  mov     eax, [rdx+8]
0x180037c5b  sub     eax, r9d
0x180037c5e  mov     [rbp+57h+var_38], eax
0x180037c61  mov     eax, [rdx+0Ch]
0x180037c64  sub     eax, r10d
0x180037c67  mov     [rbp+57h+var_34], eax
0x180037c6a  lea     rcx, [rbp+57h+var_A8]
0x180037c6e  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180037c73  nop
0x180037c74  mov     dword ptr [rbp+57h+var_C0], 0
0x180037c7b  mov     rcx, [r8]
0x180037c7e  mov     rax, [rcx]
0x180037c81  mov     qword ptr [rbp+57h+var_90], 0
0x180037c89  lea     rdx, [rbp+57h+var_C0]
0x180037c8d  mov     qword ptr [rbp+57h+var_90+8], rdx
0x180037c91  lea     rdx, [rbp+57h+var_A8]
0x180037c95  mov     [rbp+57h+var_80], rdx
0x180037c99  lea     r9, [rbp+57h+var_90]
0x180037c9d  mov     r8d, 2
0x180037ca3  lea     rdx, [rbp+57h+var_40]
0x180037ca7  mov     rax, [rax+40h]
0x180037cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cb0  mov     ebx, eax
0x180037cb2  lea     rcx, [rbp+57h+var_90]
0x180037cb6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180037cbb  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x180037cbe  test    ecx, ecx
0x180037cc0  jns     short loc_180037CC8
0x180037cc2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180037cc8  test    ebx, ebx
0x180037cca  jns     short loc_180037CD4
0x180037ccc  mov     ecx, ebx; this
0x180037cce  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180037cd4  mov     dword ptr [rbp+57h+var_C0+4], 0
0x180037cdb  mov     rcx, [rbp+57h+var_A8]
0x180037cdf  mov     rax, [rcx]
0x180037ce2  lea     rdx, [rbp+57h+var_C0+4]
0x180037ce6  mov     rax, [rax+20h]
0x180037cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cef  test    eax, eax
0x180037cf1  jns     short loc_180037CFB
0x180037cf3  mov     ecx, eax; this
0x180037cf5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180037cfb  mov     [rbp+57h+var_B0], 0
0x180037d03  mov     [rbp+57h+var_B8], 0
0x180037d0a  mov     rcx, [rbp+57h+var_A8]
0x180037d0e  mov     rax, [rcx]
0x180037d11  lea     r8, [rbp+57h+var_B0]
0x180037d15  lea     rdx, [rbp+57h+var_B8]
0x180037d19  mov     rax, [rax+28h]
0x180037d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d22  test    eax, eax
0x180037d24  jns     short loc_180037D2E
0x180037d26  mov     ecx, eax; this
0x180037d28  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180037d2e  mov     r10, [r15+58h]
0x180037d32  lea     rcx, [rbp+57h+var_70]
0x180037d36  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180037d3b  mov     rdx, [r15]
0x180037d3e  add     rdx, 40h ; '@'
0x180037d42  lea     rcx, [rbp+57h+var_70]
0x180037d46  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180037d4b  mov     [rbp+57h+var_60], r10
0x180037d4f  mov     [rbp+57h+var_48], 1
0x180037d53  mov     rcx, [rbp+57h+var_70]
0x180037d57  mov     rax, [rcx]
0x180037d5a  lea     rdx, [rbp+57h+Src]
0x180037d5e  mov     [rsp+100h+var_D8], rdx
0x180037d63  mov     [rsp+100h+var_E0], 0
0x180037d6b  mov     r9d, 1
0x180037d71  xor     r8d, r8d
0x180037d74  mov     rdx, r10
0x180037d77  mov     rax, [rax+70h]
0x180037d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d80  mov     r14d, eax
0x180037d83  test    eax, eax
0x180037d85  js      short loc_180037DD7
0x180037d87  mov     rbx, [rbp+57h+Src]
0x180037d8b  mov     rdi, [rbp+57h+var_B0]
0x180037d8f  xor     esi, esi
0x180037d91  cmp     [rbp+57h+var_34], esi
0x180037d94  jbe     short loc_180037DD7
0x180037d96  mov     rcx, [r15]
0x180037d99  movups  xmm0, xmmword ptr [rcx+64h]
0x180037d9d  movdqu  [rbp+57h+var_90], xmm0
0x180037da2  lea     rcx, [rbp+57h+var_90]; this
0x180037da6  call    ?GetBytesPerPixel@xpsrdr@@YAFU_GUID@@@Z; xpsrdr::GetBytesPerPixel(_GUID)
0x180037dab  movsx   ecx, ax
0x180037dae  imul    ecx, [rbp+57h+var_38]
0x180037db2  movsxd  r8, ecx; Size
0x180037db5  mov     rdx, rbx; Src
0x180037db8  mov     rcx, rdi; void *
0x180037dbb  call    memcpy_0
0x180037dc0  mov     eax, [rbp+57h+var_50]
0x180037dc3  add     rbx, rax
0x180037dc6  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x180037dc9  add     rdi, rax
0x180037dcc  inc     rsi
0x180037dcf  mov     eax, [rbp+57h+var_34]
0x180037dd2  cmp     rsi, rax
0x180037dd5  jb      short loc_180037D96
0x180037dd7  lea     rcx, [rbp+57h+var_70]; this
0x180037ddb  call    ??1D3D11TextureMapUnmapHelper@xpsrdr@@QEAA@XZ; xpsrdr::D3D11TextureMapUnmapHelper::~D3D11TextureMapUnmapHelper(void)
0x180037de0  nop
0x180037de1  lea     rcx, [rbp+57h+var_A8]
0x180037de5  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180037dea  mov     eax, r14d
0x180037ded  mov     rcx, [rbp+57h+var_30]
0x180037df1  xor     rcx, rsp; StackCookie
0x180037df4  call    __security_check_cookie
0x180037df9  mov     rbx, [rsp+100h+arg_18]
0x180037e01  add     rsp, 0E0h
0x180037e08  pop     r15
0x180037e0a  pop     r14
0x180037e0c  pop     rdi
0x180037e0d  pop     rsi
0x180037e0e  pop     rbp
0x180037e0f  retn
```
