# PhotoDocument::CreateImageLayerFromThumbnail(ISharedBitmap *,IImageLayer * *,uint,uint)

- ea: `0x180037d38`
- end: `0x18003815d`
- name: `?CreateImageLayerFromThumbnail@PhotoDocument@@AEAAXPEAUISharedBitmap@@PEAPEAUIImageLayer@@II@Z`
- size: `1061`
- prototype: `void __fastcall(PhotoDocument *__hidden this, struct ISharedBitmap *, struct IImageLayer **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cf20`

## callees

- `0x18000bb44`
- `0x18000cb74`
- `0x18002790c`
- `0x180028b64`
- `0x1800334e8`
- `0x1800348ec`
- `0x18003492c`
- `0x180037d38`
- `0x180038404`
- `0x18003f800`
- `0x180040264`
- `0x180080010`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x180037f1d`
- `USER32!GetDesktopWindow` at `0x180037f1d`
- `GDI32!GetObjectW` at `0x180037ea4`
- `GDI32!GetObjectW` at `0x180037ea4`
- `GDI32!GetDIBits` at `0x180037f54`
- `GDI32!GetDIBits` at `0x180037f54`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x1800380f7`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x1800380f7`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180037f10`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180037f10`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037db0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037def`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e1b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e86`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037f91`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037fbb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800380a1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800380c6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180038156`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037db0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037def`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e1b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037e86`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037f91`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180037fbb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800380a1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800380c6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180038156`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180037eae`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180037f5e`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180037eae`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180037f5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall PhotoDocument::CreateImageLayerFromThumbnail(
        PhotoDocument *this,
        struct ISharedBitmap *a2,
        struct IImageLayer **a3,
        int a4,
        signed int a5)
{
  struct IEngine *Engine; // rax
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  HBITMAP v17; // rbx
  int v18; // eax
  int v19; // edx
  Base *v20; // rcx
  unsigned __int64 v21; // rdx
  HDC lpvBits; // rdi
  HWND DesktopWindow; // rax
  Base *v24; // rcx
  int v25; // eax
  int v26; // edx
  int v27; // eax
  int v28; // edx
  const unsigned __int16 *v29; // rcx
  int v30; // ebx
  int RangedIntRegValue; // esi
  int v32; // r14d
  int v33; // eax
  int v34; // edx
  int v35; // eax
  int v36; // edx
  void *v37; // rdx
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  HANDLE h; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  __int128 pv; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h]
  HDC hdc[4]; // [rsp+A8h] [rbp-58h] BYREF
  struct tagBITMAPINFO bmi; // [rsp+C8h] [rbp-38h] BYREF
  float v51[5]; // [rsp+100h] [rbp+0h] BYREF
  float v52; // [rsp+114h] [rbp+14h]
  int v53; // [rsp+128h] [rbp+28h]
  int v54; // [rsp+13Ch] [rbp+3Ch]

  if ( !a2 || !a3 )
  {
    Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
    JUMPOUT(0x18003815CLL);
  }
  v44 = 0;
  Engine = PhotoEngine::GetEngine(this);
  v9 = (*(__int64 (__fastcall **)(struct IEngine *, GUID *, __int64, __int64 *))(*(_QWORD *)Engine + 88LL))(
         Engine,
         &GUID_2aedea54_4502_4b00_b594_d9b502f669d1,
         1,
         &v44);
  if ( v9 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v9, v10);
    __debugbreak();
  }
  ATL::CComQIPtr<IImageLayer,&__s_GUID const _GUID_2aedea54_4502_4b00_b594_d9b502f669d1>::CComQIPtr<IImageLayer,&__s_GUID const _GUID_2aedea54_4502_4b00_b594_d9b502f669d1>(
    &v39,
    v44);
  v43 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 136LL))(v39, &v43);
  if ( v11 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v11, v12);
    __debugbreak();
  }
  v42 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 48LL))(v43, &v42);
  if ( v13 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v13, v14);
    __debugbreak();
  }
  ATL::CComQIPtr<IImageEffect,&__s_GUID const _GUID_ba06dedc_f049_4d3e_a8dd_ef2d74d104be>::CComQIPtr<IImageEffect,&__s_GUID const _GUID_ba06dedc_f049_4d3e_a8dd_ef2d74d104be>(
    &v46,
    v42);
  h = 0;
  v15 = ((__int64 (__fastcall *)(struct ISharedBitmap *, HANDLE *))a2->lpVtbl->GetSharedBitmap)(a2, &h);
  if ( v15 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v15, v16);
    __debugbreak();
  }
  v17 = (HBITMAP)h;
  hdc[2] = (HDC)h;
  v40 = 0;
  v18 = ((__int64 (__fastcall *)(struct ISharedBitmap *, int *))a2->lpVtbl->GetFormat)(a2, &v40);
  if ( v18 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v18, v19);
    __debugbreak();
  }
  pv = 0;
  v48 = 0;
  if ( !GetObjectW(v17, 32, &pv) )
  {
    Base::ThrowLastError(v20);
    __debugbreak();
  }
  bmi.bmiHeader.biSize = 40;
  bmi.bmiHeader.biWidth = DWORD1(pv);
  bmi.bmiHeader.biHeight = -DWORD2(pv);
  *(_DWORD *)&bmi.bmiHeader.biPlanes = v48;
  memset(&bmi.bmiHeader.biCompression, 0, 28);
  v21 = (unsigned int)((DWORD1(pv) * WORD1(v48)) >> 31);
  LODWORD(v21) = DWORD1(pv) * WORD1(v48) % 8;
  LOBYTE(v21) = 1;
  lpvBits = (HDC)BasePrivate::New(
                   (BasePrivate *)(DWORD2(pv) * ((DWORD1(pv) * WORD1(v48) / 8 + 3) & 0xFFFFFFFC) * (unsigned __int16)v48),
                   v21,
                   v48);
  hdc[3] = lpvBits;
  DesktopWindow = GetDesktopWindow();
  WTL::CClientDC::CClientDC((WTL::CClientDC *)hdc, DesktopWindow);
  if ( !GetDIBits(hdc[0], v17, 0, DWORD2(pv), lpvBits, &bmi, 0) )
  {
    Base::ThrowLastError(v24);
    __debugbreak();
  }
  v25 = (*(__int64 (__fastcall **)(__int64, HDC, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v46 + 136LL))(
          v46,
          lpvBits,
          DWORD1(pv),
          DWORD2(pv),
          0);
  if ( v25 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v25, v26);
    __debugbreak();
  }
  v38 = 0;
  v27 = ((__int64 (__fastcall *)(struct ISharedBitmap *, __int64 *))a2->lpVtbl->GetSize)(a2, &v38);
  if ( v27 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v27, v28);
    __debugbreak();
  }
  v30 = v38;
  if ( (int)v38 <= 256 || (RangedIntRegValue = 0, v32 = HIDWORD(v38), SHIDWORD(v38) <= 256) )
  {
    RangedIntRegValue = GetRangedIntRegValue(v29, L"StretchThumbnail", 0, 0, 5);
    if ( RangedIntRegValue == 1 )
      goto LABEL_32;
    v30 = v38;
    v32 = HIDWORD(v38);
  }
  memset_0(v51, 0, 0x40u);
  v54 = 1065353216;
  v53 = 1065353216;
  v51[0] = (float)a4 / (float)v30;
  v52 = (float)a5 / (float)v32;
  if ( RangedIntRegValue > 0 )
  {
    v51[0] = fminf((float)a4 / (float)v30, (float)RangedIntRegValue);
    v52 = fminf((float)a5 / (float)v32, (float)RangedIntRegValue);
  }
  v41 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 96LL))(v39, &v41);
  if ( v33 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v33, v34);
    __debugbreak();
  }
  v35 = (*(__int64 (__fastcall **)(__int64, float *))(*(_QWORD *)v41 + 128LL))(v41, v51);
  if ( v35 < 0 )
    Base::Throw((Base *)(unsigned int)v35, v36);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v41);
LABEL_32:
  ATL::CComPtrBase<IImageEffect>::CopyTo(&v39, a3);
  WTL::CClientDC::~CClientDC((WTL::CClientDC *)hdc);
  if ( lpvBits )
    BasePrivate::Delete((BasePrivate *)lpvBits, v37);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v46);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v42);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v43);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v39);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v44);
}

```

## disassembly

```asm
0x180037d38  push    rbp
0x180037d3a  push    rbx
0x180037d3b  push    rsi
0x180037d3c  push    rdi
0x180037d3d  push    r12
0x180037d3f  push    r14
0x180037d41  push    r15
0x180037d43  lea     rbp, [rsp-50h]
0x180037d48  sub     rsp, 150h
0x180037d4f  mov     rax, cs:__security_cookie
0x180037d56  xor     rax, rsp
0x180037d59  mov     [rbp+80h+var_40], rax
0x180037d5d  mov     r12d, r9d
0x180037d60  mov     r15, r8
0x180037d63  mov     rsi, rdx
0x180037d66  test    rdx, rdx
0x180037d69  jz      loc_180038151
0x180037d6f  test    r8, r8
0x180037d72  jz      loc_180038151
0x180037d78  mov     [rsp+180h+var_110], 0
0x180037d81  call    ?GetEngine@PhotoEngine@@QEAAPEAUIEngine@@XZ; PhotoEngine::GetEngine(void)
0x180037d86  mov     r10, rax
0x180037d89  mov     rcx, [rax]
0x180037d8c  mov     rax, [rcx+58h]
0x180037d90  lea     r9, [rsp+180h+var_110]
0x180037d95  mov     r8d, 1
0x180037d9b  lea     rdx, _GUID_2aedea54_4502_4b00_b594_d9b502f669d1
0x180037da2  mov     rcx, r10
0x180037da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037daa  test    eax, eax
0x180037dac  jns     short loc_180037DB7
0x180037dae  mov     ecx, eax
0x180037db0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037db6  int     3; Trap to Debugger
0x180037db7  mov     rdx, [rsp+180h+var_110]
0x180037dbc  lea     rcx, [rsp+180h+var_138]
0x180037dc1  call    ??0?$CComQIPtr@UIImageLayer@@$1?_GUID_2aedea54_4502_4b00_b594_d9b502f669d1@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IImageLayer,&__s_GUID const _GUID_2aedea54_4502_4b00_b594_d9b502f669d1>::CComQIPtr<IImageLayer,&__s_GUID const _GUID_2aedea54_4502_4b00_b594_d9b502f669d1>(IUnknown *)
0x180037dc6  nop
0x180037dc7  mov     [rsp+180h+var_118], 0
0x180037dd0  mov     rcx, [rsp+180h+var_138]
0x180037dd5  mov     rax, [rcx]
0x180037dd8  lea     rdx, [rsp+180h+var_118]
0x180037ddd  mov     rax, [rax+88h]
0x180037de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037de9  test    eax, eax
0x180037deb  jns     short loc_180037DF6
0x180037ded  mov     ecx, eax
0x180037def  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037df5  int     3; Trap to Debugger
0x180037df6  mov     [rsp+180h+var_120], 0
0x180037dff  mov     rcx, [rsp+180h+var_118]
0x180037e04  mov     rax, [rcx]
0x180037e07  lea     rdx, [rsp+180h+var_120]
0x180037e0c  mov     rax, [rax+30h]
0x180037e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e15  test    eax, eax
0x180037e17  jns     short loc_180037E22
0x180037e19  mov     ecx, eax
0x180037e1b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037e21  int     3; Trap to Debugger
0x180037e22  mov     rdx, [rsp+180h+var_120]
0x180037e27  lea     rcx, [rbp+80h+var_100]
0x180037e2b  call    ??0?$CComQIPtr@UIImageEffect@@$1?_GUID_ba06dedc_f049_4d3e_a8dd_ef2d74d104be@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IImageEffect,&__s_GUID const _GUID_ba06dedc_f049_4d3e_a8dd_ef2d74d104be>::CComQIPtr<IImageEffect,&__s_GUID const _GUID_ba06dedc_f049_4d3e_a8dd_ef2d74d104be>(IUnknown *)
0x180037e30  nop
0x180037e31  mov     [rsp+180h+h], 0
0x180037e3a  mov     rax, [rsi]
0x180037e3d  lea     rdx, [rsp+180h+h]
0x180037e42  mov     rcx, rsi
0x180037e45  mov     rax, [rax+18h]
0x180037e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e4e  test    eax, eax
0x180037e50  jns     short loc_180037E5B
0x180037e52  mov     ecx, eax
0x180037e54  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037e5a  int     3; Trap to Debugger
0x180037e5b  mov     rbx, [rsp+180h+h]
0x180037e60  mov     [rbp+80h+var_C8], rbx
0x180037e64  mov     [rsp+180h+var_130], 0
0x180037e6c  mov     rax, [rsi]
0x180037e6f  lea     rdx, [rsp+180h+var_130]
0x180037e74  mov     rcx, rsi
0x180037e77  mov     rax, [rax+28h]
0x180037e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e80  test    eax, eax
0x180037e82  jns     short loc_180037E8D
0x180037e84  mov     ecx, eax
0x180037e86  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037e8c  int     3; Trap to Debugger
0x180037e8d  xorps   xmm0, xmm0
0x180037e90  movups  [rbp+80h+pv], xmm0
0x180037e94  movups  [rbp+80h+var_E8], xmm0
0x180037e98  lea     r8, [rbp+80h+pv]; pv
0x180037e9c  mov     edx, 20h ; ' '; c
0x180037ea1  mov     rcx, rbx; h
0x180037ea4  call    cs:__imp_GetObjectW
0x180037eaa  test    eax, eax
0x180037eac  jnz     short loc_180037EB5
0x180037eae  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180037eb4  int     3; Trap to Debugger
0x180037eb5  xorps   xmm0, xmm0
0x180037eb8  movdqu  xmmword ptr [rbp+80h+bmi.bmiHeader.biSizeImage], xmm0
0x180037ebd  mov     qword ptr [rbp+80h+bmi.bmiHeader.biClrImportant], 0
0x180037ec5  mov     [rbp+80h+bmi.bmiHeader.biSize], 28h ; '('
0x180037ecc  mov     ecx, dword ptr [rbp+80h+pv+4]
0x180037ecf  mov     [rbp+80h+bmi.bmiHeader.biWidth], ecx
0x180037ed2  mov     eax, dword ptr [rbp+80h+pv+8]
0x180037ed5  neg     eax
0x180037ed7  mov     [rbp+80h+bmi.bmiHeader.biHeight], eax
0x180037eda  movzx   r8d, word ptr [rbp+80h+var_E8]
0x180037edf  mov     [rbp+80h+bmi.bmiHeader.biPlanes], r8w
0x180037ee4  movzx   eax, word ptr [rbp+80h+var_E8+2]
0x180037ee8  mov     [rbp+80h+bmi.bmiHeader.biBitCount], ax
0x180037eec  mov     [rbp+80h+bmi.bmiHeader.biCompression], 0
0x180037ef3  imul    eax, ecx
0x180037ef6  cdq
0x180037ef7  mov     ecx, 8
0x180037efc  idiv    ecx
0x180037efe  add     eax, 3
0x180037f01  and     eax, 0FFFFFFFCh
0x180037f04  mov     ecx, r8d
0x180037f07  imul    ecx, eax
0x180037f0a  imul    ecx, dword ptr [rbp+80h+pv+8]
0x180037f0e  mov     dl, 1
0x180037f10  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180037f16  mov     rdi, rax
0x180037f19  mov     [rbp+80h+var_C0], rax
0x180037f1d  call    cs:__imp_GetDesktopWindow
0x180037f23  mov     rdx, rax; HWND
0x180037f26  lea     rcx, [rbp+80h+hdc]; this
0x180037f2a  call    ??0CClientDC@WTL@@QEAA@PEAUHWND__@@@Z; WTL::CClientDC::CClientDC(HWND__ *)
0x180037f2f  nop
0x180037f30  mov     [rsp+180h+usage], 0; usage
0x180037f38  lea     rax, [rbp+80h+bmi]
0x180037f3c  mov     [rsp+180h+lpbmi], rax; lpbmi
0x180037f41  mov     [rsp+180h+lpvBits], rdi; lpvBits
0x180037f46  mov     r9d, dword ptr [rbp+80h+pv+8]; cLines
0x180037f4a  xor     r8d, r8d; start
0x180037f4d  mov     rdx, rbx; hbm
0x180037f50  mov     rcx, [rbp+80h+hdc]; hdc
0x180037f54  call    cs:__imp_GetDIBits
0x180037f5a  test    eax, eax
0x180037f5c  jnz     short loc_180037F65
0x180037f5e  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180037f64  int     3; Trap to Debugger
0x180037f65  mov     rcx, [rbp+80h+var_100]
0x180037f69  mov     rax, [rcx]
0x180037f6c  mov     dword ptr [rsp+180h+lpvBits], 0
0x180037f74  mov     r9d, dword ptr [rbp+80h+pv+8]
0x180037f78  mov     r8d, dword ptr [rbp+80h+pv+4]
0x180037f7c  mov     rdx, rdi
0x180037f7f  mov     rax, [rax+88h]
0x180037f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f8b  test    eax, eax
0x180037f8d  jns     short loc_180037F98
0x180037f8f  mov     ecx, eax
0x180037f91  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037f97  int     3; Trap to Debugger
0x180037f98  mov     [rsp+180h+var_140], 0
0x180037fa1  mov     rax, [rsi]
0x180037fa4  lea     rdx, [rsp+180h+var_140]
0x180037fa9  mov     rcx, rsi
0x180037fac  mov     rax, [rax+20h]
0x180037fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fb5  test    eax, eax
0x180037fb7  jns     short loc_180037FC2
0x180037fb9  mov     ecx, eax
0x180037fbb  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180037fc1  int     3; Trap to Debugger
0x180037fc2  mov     rbx, [rsp+180h+var_140]
0x180037fc7  mov     eax, 100h
0x180037fcc  cmp     ebx, eax
0x180037fce  jle     short loc_180037FDC
0x180037fd0  xor     esi, esi
0x180037fd2  mov     r14d, dword ptr [rsp+180h+var_140+4]
0x180037fd7  cmp     r14d, eax
0x180037fda  jg      short loc_18003800B
0x180037fdc  mov     dword ptr [rsp+180h+lpvBits], 5; int
0x180037fe4  xor     r9d, r9d; int
0x180037fe7  xor     r8d, r8d; int
0x180037fea  lea     rdx, aStretchthumbna; "StretchThumbnail"
0x180037ff1  call    ?GetRangedIntRegValue@@YAHPEBG0HHH@Z; GetRangedIntRegValue(ushort const *,ushort const *,int,int,int)
0x180037ff6  mov     esi, eax
0x180037ff8  cmp     eax, 1
0x180037ffb  jz      loc_1800380D7
0x180038001  mov     rbx, [rsp+180h+var_140]
0x180038006  mov     r14d, dword ptr [rsp+180h+var_140+4]
0x18003800b  xor     edx, edx; Val
0x18003800d  lea     r8d, [rdx+40h]; Size
0x180038011  lea     rcx, [rbp+80h+var_80]; void *
0x180038015  call    memset_0
0x18003801a  mov     [rbp+80h+var_44], 3F800000h
0x180038021  mov     [rbp+80h+var_58], 3F800000h
0x180038028  xorps   xmm1, xmm1
0x18003802b  cvtsi2ss xmm1, r12
0x180038030  movd    xmm0, ebx
0x180038034  cvtdq2ps xmm0, xmm0
0x180038037  divss   xmm1, xmm0
0x18003803b  movss   [rbp+80h+var_80], xmm1
0x180038040  mov     eax, [rbp+80h+arg_20]
0x180038046  xorps   xmm2, xmm2
0x180038049  cvtsi2ss xmm2, rax
0x18003804e  movd    xmm0, r14d
0x180038053  cvtdq2ps xmm0, xmm0
0x180038056  divss   xmm2, xmm0
0x18003805a  movss   [rbp+80h+var_6C], xmm2
0x18003805f  test    esi, esi
0x180038061  jle     short loc_18003807C
0x180038063  movd    xmm0, esi
0x180038067  cvtdq2ps xmm0, xmm0
0x18003806a  minss   xmm1, xmm0
0x18003806e  movss   [rbp+80h+var_80], xmm1
0x180038073  minss   xmm2, xmm0
0x180038077  movss   [rbp+80h+var_6C], xmm2
0x18003807c  mov     [rsp+180h+var_128], 0
0x180038085  mov     rcx, [rsp+180h+var_138]
0x18003808a  mov     rax, [rcx]
0x18003808d  lea     rdx, [rsp+180h+var_128]
0x180038092  mov     rax, [rax+60h]
0x180038096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003809b  test    eax, eax
0x18003809d  jns     short loc_1800380A8
0x18003809f  mov     ecx, eax
0x1800380a1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800380a7  int     3; Trap to Debugger
0x1800380a8  mov     rcx, [rsp+180h+var_128]
0x1800380ad  mov     rax, [rcx]
0x1800380b0  lea     rdx, [rbp+80h+var_80]
0x1800380b4  mov     rax, [rax+80h]
0x1800380bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380c0  test    eax, eax
0x1800380c2  jns     short loc_1800380CD
0x1800380c4  mov     ecx, eax
0x1800380c6  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800380cc  nop
0x1800380cd  lea     rcx, [rsp+180h+var_128]
0x1800380d2  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800380d7  mov     rdx, r15
0x1800380da  lea     rcx, [rsp+180h+var_138]
0x1800380df  call    ?CopyTo@?$CComPtrBase@UIImageEffect@@@ATL@@QEAAJPEAPEAUIImageEffect@@@Z; ATL::CComPtrBase<IImageEffect>::CopyTo(IImageEffect * *)
0x1800380e4  nop
0x1800380e5  lea     rcx, [rbp+80h+hdc]; this
0x1800380e9  call    ??1CClientDC@WTL@@QEAA@XZ; WTL::CClientDC::~CClientDC(void)
0x1800380ee  nop
0x1800380ef  test    rdi, rdi
0x1800380f2  jz      short loc_1800380FE
0x1800380f4  mov     rcx, rdi
0x1800380f7  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x1800380fd  nop
0x1800380fe  lea     rcx, [rbp+80h+var_100]
0x180038102  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180038107  nop
0x180038108  lea     rcx, [rsp+180h+var_120]
0x18003810d  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180038112  nop
0x180038113  lea     rcx, [rsp+180h+var_118]
0x180038118  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003811d  nop
0x18003811e  lea     rcx, [rsp+180h+var_138]
0x180038123  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180038128  nop
0x180038129  lea     rcx, [rsp+180h+var_110]
0x18003812e  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180038133  mov     rcx, [rbp+80h+var_40]
0x180038137  xor     rcx, rsp; StackCookie
0x18003813a  call    __security_check_cookie
0x18003813f  add     rsp, 150h
0x180038146  pop     r15
0x180038148  pop     r14
0x18003814a  pop     r12
0x18003814c  pop     rdi
0x18003814d  pop     rsi
0x18003814e  pop     rbx
0x18003814f  pop     rbp
0x180038150  retn
0x180038151  mov     ecx, 80004003h
0x180038156  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
```
