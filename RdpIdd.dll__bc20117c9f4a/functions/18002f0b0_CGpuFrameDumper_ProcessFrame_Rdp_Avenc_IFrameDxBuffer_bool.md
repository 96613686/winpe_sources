# CGpuFrameDumper::ProcessFrame(Rdp::Avenc::IFrameDxBuffer &,bool *)

- ea: `0x18002f0b0`
- end: `0x18002f4cb`
- name: `?ProcessFrame@CGpuFrameDumper@@UEAAJAEAUIFrameDxBuffer@Avenc@Rdp@@PEA_N@Z`
- size: `1051`
- prototype: `__int64 __fastcall(CGpuFrameDumper *__hidden this, struct Rdp::Avenc::IFrameDxBuffer *, bool *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006f60`
- `0x18000ead8`
- `0x18001072c`
- `0x1800107ec`
- `0x18001dd50`
- `0x18001ddf4`
- `0x180029870`
- `0x18002d998`
- `0x18002e3ec`
- `0x18002e860`
- `0x18002eb30`
- `0x18002f0b0`
- `0x18002f688`
- `0x18003f010`

## string_xrefs

- `0x18002f4b8`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x18002f1d0`: `Failed to get moves and dirties`
- `0x18002f3a6`: `CreateSharedBitmap failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CGpuFrameDumper::ProcessFrame(
        CGpuFrameDumper *this,
        struct Rdp::Avenc::IFrameDxBuffer *a2,
        bool *a3,
        const char *a4)
{
  bool *v4; // rsi
  struct Rdp::Avenc::IFrameDxBuffer *v5; // rdi
  CGpuFrameDumper *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int128 *v11; // rcx
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  int v18; // eax
  __int64 v19; // r8
  __int64 *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 FileName; // rax
  __int64 result; // rax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-138h]
  const char *v27; // [rsp+28h] [rbp-130h]
  unsigned int v28; // [rsp+30h] [rbp-128h] BYREF
  __int64 v29; // [rsp+38h] [rbp-120h] BYREF
  __int64 v30; // [rsp+40h] [rbp-118h] BYREF
  __int128 v31; // [rsp+48h] [rbp-110h] BYREF
  __int128 *v32; // [rsp+58h] [rbp-100h] BYREF
  __int64 v33; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE v34[8]; // [rsp+68h] [rbp-F0h] BYREF
  CGpuFrameDumper *v35; // [rsp+70h] [rbp-E8h]
  bool *v36; // [rsp+78h] [rbp-E0h]
  struct Rdp::Avenc::IFrameDxBuffer *v37; // [rsp+80h] [rbp-D8h]
  _QWORD v38[8]; // [rsp+88h] [rbp-D0h] BYREF
  __int128 v39; // [rsp+C8h] [rbp-90h] BYREF
  int v40[4]; // [rsp+D8h] [rbp-80h] BYREF
  _DWORD v41[8]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v42[8]; // [rsp+108h] [rbp-50h] BYREF
  std::_Ref_count_base *v43; // [rsp+110h] [rbp-48h]
  __int128 v44; // [rsp+128h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  try
  {
    try
    {
      v4 = a3;
      v5 = a2;
      v6 = this;
      v35 = this;
      v37 = a2;
      v36 = a3;
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 5) + 232LL) + 505LL) )
      {
        v7 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameDxBuffer *))(*(_QWORD *)a2 + 152LL))(a2);
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::com_ptr_t<IDXGIResource,wil::err_exception_policy>(
          v34,
          v7);
        v33 = 0;
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::copy_to<ID3D11Texture2D>(v34, &v33);
        *(_OWORD *)v40 = 0;
        memset(v41, 0, 28);
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 80LL))(v33, v40);
        v28 = 0;
        v32 = 0;
        v39 = 0;
        v8 = *((_QWORD *)v6 + 16);
        if ( v8 && v41[0] == *(_DWORD *)(v8 + 32) )
        {
          v9 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameDxBuffer *, _QWORD, _QWORD, __int128 **, unsigned int *))(*(_QWORD *)v5 + 136LL))(
                 v5,
                 0,
                 0,
                 &v32,
                 &v28);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x15B,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
            (const char *)v9,
            (int)"Failed to get moves and dirties",
            v27);
          v10 = v28;
          v11 = v32;
        }
        else
        {
          *(_QWORD *)&v31 = *((_QWORD *)v6 + 15);
          v12 = (__int64 *)std::make_shared<Rdp::Utils::Graphics::CGpuStagingTexture,ID3D11Device *,enum DXGI_FORMAT &,unsigned int &,unsigned int &>(
                             (unsigned int)v42,
                             (unsigned int)&v31,
                             (unsigned int)v41,
                             (unsigned int)v40,
                             (__int64)&v40[1]);
          v13 = *v12;
          v14 = v12[1];
          *v12 = 0;
          v12[1] = 0;
          *((_QWORD *)v6 + 16) = v13;
          v15 = (std::_Ref_count_base *)*((_QWORD *)v6 + 17);
          *((_QWORD *)v6 + 17) = v14;
          if ( v15 )
            std::_Ref_count_base::_Decref(v15);
          if ( v43 )
            std::_Ref_count_base::_Decref(v43);
          *(_QWORD *)&v39 = 0;
          *((_QWORD *)&v39 + 1) = *(_QWORD *)v40;
          v11 = &v39;
          v32 = &v39;
          v10 = 1;
          v28 = 1;
        }
        *(_QWORD *)&v31 = v11;
        *((_QWORD *)&v31 + 1) = v10;
        Rdp::Utils::Graphics::CGpuStagingTexture::Update(*((_QWORD *)v6 + 16), v5, &v31);
        v16 = *((_QWORD *)v6 + 16);
        v30 = 0;
        v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v16 + 24);
        if ( v17 )
        {
          v18 = (**v17)(v17, &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec, &v30);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
              (const char *)(unsigned int)v18,
              v26);
          v19 = v30;
        }
        else
        {
          v19 = 0;
          v30 = 0;
        }
        *(_QWORD *)&v31 = v41[0] | 0x100000000LL;
        *((_QWORD *)&v31 + 1) = 0x42C0000042C00000LL;
        v44 = v31;
        v29 = 0;
        v20 = (__int64 *)*((_QWORD *)v6 + 14);
        v21 = *v20;
        v29 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64, __int128 *, __int64 *))(v21 + 48))(
                v20,
                &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec,
                v19,
                &v44,
                &v29);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
          (const char *)v22,
          (int)"CreateSharedBitmap failed",
          v27);
        *(_QWORD *)&v31 = v38;
        v38[0] = off_180040F40;
        v38[1] = v6;
        v38[2] = &v29;
        v38[7] = v38;
        FileName = CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::GetFileName(v6, v42, v5);
        CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump((__int64)v6, FileName, (__int64)v38);
        std::wstring::_Tidy_deallocate(v42);
        wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v29);
        wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v30);
        wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v33);
        wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(v34);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
        a4);
      v6 = v35;
      v4 = v36;
      v5 = v37;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, struct Rdp::Avenc::IFrameDxBuffer *, bool *))(**((_QWORD **)v6 + 4)
                                                                                            + 64LL))(
               *((_QWORD *)v6 + 4),
               v5,
               v4);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x194,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18002f0b0  push    rbx
0x18002f0b2  push    rsi
0x18002f0b3  push    rdi
0x18002f0b4  sub     rsp, 140h
0x18002f0bb  mov     rax, cs:__security_cookie
0x18002f0c2  xor     rax, rsp
0x18002f0c5  mov     [rsp+158h+var_20], rax
0x18002f0cd  mov     rsi, r8
0x18002f0d0  mov     rdi, rdx
0x18002f0d3  mov     rbx, rcx
0x18002f0d6  mov     [rsp+158h+var_E8], rcx
0x18002f0db  mov     [rsp+158h+var_D8], rdx
0x18002f0e3  mov     [rsp+158h+var_E0], r8
0x18002f0e8  mov     rax, [rcx+28h]
0x18002f0ec  mov     rdx, [rax+0E8h]
0x18002f0f3  mov     al, [rdx+1F9h]
0x18002f0f9  nop
0x18002f0fa  test    al, al
0x18002f0fc  jz      loc_18002F47D
0x18002f102  mov     rax, [rdi]
0x18002f105  mov     rcx, rdi
0x18002f108  mov     rax, [rax+98h]
0x18002f10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f114  mov     rdx, rax
0x18002f117  lea     rcx, [rsp+158h+var_F0]
0x18002f11c  call    ??0?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIDXGIResource@@@Z; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::com_ptr_t<IDXGIResource,wil::err_exception_policy>(IDXGIResource *)
0x18002f121  nop
0x18002f122  mov     [rsp+158h+var_F8], 0
0x18002f12b  lea     rdx, [rsp+158h+var_F8]
0x18002f130  lea     rcx, [rsp+158h+var_F0]
0x18002f135  call    ??$copy_to@UID3D11Texture2D@@@?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUID3D11Texture2D@@@Z; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::copy_to<ID3D11Texture2D>(ID3D11Texture2D * *)
0x18002f13a  xorps   xmm0, xmm0
0x18002f13d  movups  xmmword ptr [rsp+158h+var_80], xmm0
0x18002f145  movups  xmmword ptr [rsp+158h+var_70], xmm0
0x18002f14d  movups  xmmword ptr [rsp+158h+var_70+0Ch], xmm0
0x18002f155  mov     rcx, [rsp+158h+var_F8]
0x18002f15a  mov     rax, [rcx]
0x18002f15d  lea     rdx, [rsp+158h+var_80]
0x18002f165  mov     rax, [rax+50h]
0x18002f169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f16e  mov     [rsp+158h+var_128], 0
0x18002f176  mov     [rsp+158h+var_100], 0
0x18002f17f  xorps   xmm0, xmm0
0x18002f182  movups  [rsp+158h+var_90], xmm0
0x18002f18a  mov     rax, [rbx+80h]
0x18002f191  test    rax, rax
0x18002f194  jz      short loc_18002F1FE
0x18002f196  mov     eax, [rax+20h]
0x18002f199  cmp     [rsp+158h+var_70], eax
0x18002f1a0  jnz     short loc_18002F1FE
0x18002f1a2  mov     rax, [rdi]
0x18002f1a5  lea     rcx, [rsp+158h+var_128]
0x18002f1aa  mov     qword ptr [rsp+158h+var_138], rcx
0x18002f1af  lea     r9, [rsp+158h+var_100]
0x18002f1b4  xor     r8d, r8d
0x18002f1b7  xor     edx, edx
0x18002f1b9  mov     rcx, rdi
0x18002f1bc  mov     rax, [rax+88h]
0x18002f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1c8  mov     rcx, [rsp+158h]; this
0x18002f1d0  lea     rdx, aFailedToGetMov; "Failed to get moves and dirties"
0x18002f1d7  mov     qword ptr [rsp+158h+var_138], rdx; int
0x18002f1dc  mov     r9d, eax; char *
0x18002f1df  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002f1e6  mov     edx, 15Bh; void *
0x18002f1eb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002f1f0  mov     eax, [rsp+158h+var_128]
0x18002f1f4  mov     rcx, [rsp+158h+var_100]
0x18002f1f9  jmp     loc_18002F2BB
0x18002f1fe  mov     rax, [rbx+78h]
0x18002f202  mov     qword ptr [rsp+158h+var_110], rax
0x18002f207  lea     rax, [rsp+158h+var_80+4]
0x18002f20f  mov     qword ptr [rsp+158h+var_138], rax; int
0x18002f214  lea     r9, [rsp+158h+var_80]
0x18002f21c  lea     r8, [rsp+158h+var_70]
0x18002f224  lea     rdx, [rsp+158h+var_110]
0x18002f229  lea     rcx, [rsp+158h+var_50]
0x18002f231  call    ??$make_shared@VCGpuStagingTexture@Graphics@Utils@Rdp@@PEAUID3D11Device@@AEAW4DXGI_FORMAT@@AEAIAEAI@std@@YA?AV?$shared_ptr@VCGpuStagingTexture@Graphics@Utils@Rdp@@@0@$$QEAPEAUID3D11Device@@AEAW4DXGI_FORMAT@@AEAI2@Z; std::make_shared<Rdp::Utils::Graphics::CGpuStagingTexture,ID3D11Device *,DXGI_FORMAT &,uint &,uint &>(ID3D11Device * &&,DXGI_FORMAT &,uint &,uint &)
0x18002f236  mov     rcx, [rax]
0x18002f239  mov     rdx, [rax+8]
0x18002f23d  mov     qword ptr [rax], 0
0x18002f244  mov     qword ptr [rax+8], 0
0x18002f24c  mov     [rbx+80h], rcx
0x18002f253  mov     rcx, [rbx+88h]; this
0x18002f25a  mov     [rbx+88h], rdx
0x18002f261  test    rcx, rcx
0x18002f264  jz      short loc_18002F26B
0x18002f266  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f26b  mov     rcx, [rsp+158h+var_48]; this
0x18002f273  test    rcx, rcx
0x18002f276  jz      short loc_18002F27D
0x18002f278  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f27d  mov     qword ptr [rsp+158h+var_90], 0
0x18002f289  mov     eax, [rsp+158h+var_80]
0x18002f290  mov     dword ptr [rsp+158h+var_90+8], eax
0x18002f297  mov     eax, [rsp+158h+var_80+4]
0x18002f29e  mov     dword ptr [rsp+158h+var_90+0Ch], eax
0x18002f2a5  lea     rcx, [rsp+158h+var_90]
0x18002f2ad  mov     [rsp+158h+var_100], rcx
0x18002f2b2  mov     eax, 1
0x18002f2b7  mov     [rsp+158h+var_128], eax
0x18002f2bb  mov     qword ptr [rsp+158h+var_110], rcx
0x18002f2c0  mov     qword ptr [rsp+158h+var_110+8], rax
0x18002f2c5  lea     r8, [rsp+158h+var_110]
0x18002f2ca  mov     rdx, rdi
0x18002f2cd  mov     rcx, [rbx+80h]
0x18002f2d4  call    ?Update@CGpuStagingTexture@Graphics@Utils@Rdp@@QEAAXAEAUIFrameDxBuffer@Avenc@4@AEBV?$span@$$CBUtagRECT@@$0?0@std@@@Z; Rdp::Utils::Graphics::CGpuStagingTexture::Update(Rdp::Avenc::IFrameDxBuffer &,std::span<tagRECT const,-1> const &)
0x18002f2d9  nop
0x18002f2da  mov     rax, [rbx+80h]
0x18002f2e1  mov     [rsp+158h+var_118], 0
0x18002f2ea  mov     rcx, [rax+18h]
0x18002f2ee  test    rcx, rcx
0x18002f2f1  jz      short loc_18002F321
0x18002f2f3  mov     rax, [rcx]
0x18002f2f6  lea     r8, [rsp+158h+var_118]
0x18002f2fb  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18002f302  mov     rax, [rax]
0x18002f305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f30a  mov     rcx, [rsp+158h]; this
0x18002f312  test    eax, eax
0x18002f314  js      loc_18002F4B5
0x18002f31a  mov     r8, [rsp+158h+var_118]
0x18002f31f  jmp     short loc_18002F329
0x18002f321  xor     r8d, r8d
0x18002f324  mov     [rsp+158h+var_118], r8
0x18002f329  mov     eax, [rsp+158h+var_70]
0x18002f330  mov     dword ptr [rsp+158h+var_120], eax
0x18002f334  mov     dword ptr [rsp+158h+var_120+4], 1
0x18002f33c  mov     rax, [rsp+158h+var_120]
0x18002f341  mov     qword ptr [rsp+158h+var_110], rax
0x18002f346  mov     dword ptr [rsp+158h+var_110+8], 42C00000h
0x18002f34e  mov     dword ptr [rsp+158h+var_110+0Ch], 42C00000h
0x18002f356  movups  xmm1, [rsp+158h+var_110]
0x18002f35b  movups  [rsp+158h+var_30], xmm1
0x18002f363  mov     [rsp+158h+var_120], 0
0x18002f36c  mov     rcx, [rbx+70h]
0x18002f370  mov     rax, [rcx]
0x18002f373  mov     [rsp+158h+var_120], 0
0x18002f37c  lea     rdx, [rsp+158h+var_120]
0x18002f381  mov     qword ptr [rsp+158h+var_138], rdx
0x18002f386  lea     r9, [rsp+158h+var_30]
0x18002f38e  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18002f395  mov     rax, [rax+30h]
0x18002f399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f39e  mov     rcx, [rsp+158h]; this
0x18002f3a6  lea     rdx, aCreatesharedbi; "CreateSharedBitmap failed"
0x18002f3ad  mov     qword ptr [rsp+158h+var_138], rdx; int
0x18002f3b2  mov     r9d, eax; char *
0x18002f3b5  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002f3bc  mov     edx, 177h; void *
0x18002f3c1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002f3c6  lea     rax, [rsp+158h+var_D0]
0x18002f3ce  mov     qword ptr [rsp+158h+var_110], rax
0x18002f3d3  lea     rax, off_180040F40
0x18002f3da  mov     [rsp+158h+var_D0], rax
0x18002f3e2  mov     [rsp+158h+var_C8], rbx
0x18002f3ea  lea     rax, [rsp+158h+var_120]
0x18002f3ef  mov     [rsp+158h+var_C0], rax
0x18002f3f7  lea     rax, [rsp+158h+var_D0]
0x18002f3ff  mov     [rsp+158h+var_98], rax
0x18002f407  mov     r8, rdi
0x18002f40a  lea     rdx, [rsp+158h+var_50]
0x18002f412  mov     rcx, rbx
0x18002f415  call    ?GetFileName@?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUIFrameBuffer@Avenc@Rdp@@@Z; CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::GetFileName(Rdp::Avenc::IFrameBuffer &)
0x18002f41a  nop
0x18002f41b  lea     r8, [rsp+158h+var_D0]
0x18002f423  mov     rdx, rax
0x18002f426  mov     rcx, rbx
0x18002f429  call    ?Dump@?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXPEAUIWICBitmapFrameEncode@@@Z@3@@Z; CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump(std::wstring const &,std::function<void (IWICBitmapFrameEncode *)>)
0x18002f42e  nop
0x18002f42f  lea     rcx, [rsp+158h+var_50]
0x18002f437  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f43c  nop
0x18002f43d  lea     rcx, [rsp+158h+var_120]
0x18002f442  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f447  nop
0x18002f448  lea     rcx, [rsp+158h+var_118]
0x18002f44d  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f452  nop
0x18002f453  lea     rcx, [rsp+158h+var_F8]
0x18002f458  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f45d  nop
0x18002f45e  lea     rcx, [rsp+158h+var_F0]
0x18002f463  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f468  nop
0x18002f469  jmp     short loc_18002F47D
0x18002f46b  mov     rbx, [rsp+158h+var_E8]
0x18002f470  mov     rsi, [rsp+158h+var_E0]
0x18002f475  mov     rdi, [rsp+158h+var_D8]
0x18002f47d  mov     rcx, [rbx+20h]
0x18002f481  mov     rax, [rcx]
0x18002f484  mov     r8, rsi
0x18002f487  mov     rdx, rdi
0x18002f48a  mov     rax, [rax+40h]
0x18002f48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f493  jmp     short loc_18002F499
0x18002f495  mov     eax, [rsp+158h+var_128]
0x18002f499  mov     rcx, [rsp+158h+var_20]
0x18002f4a1  xor     rcx, rsp; StackCookie
0x18002f4a4  call    __security_check_cookie
0x18002f4a9  add     rsp, 140h
0x18002f4b0  pop     rdi
0x18002f4b1  pop     rsi
0x18002f4b2  pop     rbx
0x18002f4b3  retn
0x18002f4b5  mov     r9d, eax; char *
0x18002f4b8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f4bf  mov     edx, 1CBEh; void *
0x18002f4c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
