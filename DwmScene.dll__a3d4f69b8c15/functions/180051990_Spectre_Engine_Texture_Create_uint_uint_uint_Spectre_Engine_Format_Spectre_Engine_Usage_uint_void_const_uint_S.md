# Spectre::Engine::Texture::Create(uint,uint,uint,Spectre::Engine::Format,Spectre::Engine::Usage,uint,void const *,uint,Spectre::Engine::RenderDevice *)

- ea: `0x180051990`
- end: `0x180051d67`
- name: `?Create@Texture@Engine@Spectre@@QEAAXIIIW4Format@23@W4Usage@23@IPEBXIPEAVRenderDevice@23@@Z`
- size: `983`
- prototype: ``
- caller_count: `8`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x180027280`
- `0x18004e15c`
- `0x1800518e4`
- `0x180051f98`
- `0x180068d4c`
- `0x18006b9ec`
- `0x1800853ac`
- `0x1800c4c74`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000eb2c`
- `0x18001128c`
- `0x1800117b0`
- `0x180011f64`
- `0x180012df8`
- `0x180014280`
- `0x18001c290`
- `0x1800286b4`
- `0x180034d7c`
- `0x180037560`
- `0x180037594`
- `0x180037614`
- `0x18004d8b0`
- `0x18004e6bc`
- `0x180050b54`
- `0x180050dcc`
- `0x180050e4c`
- `0x180051038`
- `0x180051300`
- `0x180051990`
- `0x180051e54`
- `0x180051ea4`
- `0x180052314`
- `0x180052528`
- `0x1800681a8`
- `0x1800e7010`

## string_xrefs

- `0x180051ce8`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x180051d30`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x180051d1f`: `Texture cannot be created to just target generic devices`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Spectre::Engine::Texture::Create(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        char a5,
        char a6,
        char a7,
        void *Source,
        rsize_t DestinationSize,
        struct Spectre::Engine::RenderDevice *a10)
{
  void *v12; // r13
  rsize_t v13; // r14
  struct Spectre::Engine::RenderDevice *v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rax
  char v17; // bl
  int **v18; // r15
  __int64 v19; // r8
  _DWORD *v20; // rax
  char v21; // r12
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rsi
  struct Spectre::Engine::RenderDevice *v26; // r13
  int *v27; // rbx
  int FormatSlicePitch; // eax
  void *v29; // rbx
  void *v30; // rax
  int *v31; // rax
  int v32; // ecx
  int v33; // edx
  __m128 v34; // xmm1
  __m128 v35; // xmm0
  int v37; // eax
  int v38; // r8d
  int v39; // eax
  int v40; // r8d
  void *Destination; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  void *v44; // [rsp+58h] [rbp-A8h] BYREF
  void *v45; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  _BYTE v49[24]; // [rsp+90h] [rbp-70h] BYREF
  char v50[32]; // [rsp+A8h] [rbp-58h] BYREF
  struct Spectre::Engine::RenderDevice *v51; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v52; // [rsp+D0h] [rbp-30h]
  _BYTE pExceptionObject[56]; // [rsp+E8h] [rbp-18h] BYREF

  v43 = a2;
  v42 = a3;
  v46 = a4;
  v12 = Source;
  v44 = Source;
  v13 = (unsigned int)DestinationSize;
  LODWORD(v45) = DestinationSize;
  v14 = a10;
  LODWORD(Destination) = 0;
  v15 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  if ( v15 )
    std::default_delete<Spectre::Utils::Tweening::ITweenable>::operator()();
  if ( a4 )
  {
    v16 = std::make_unique<Spectre::Engine::TextureDesc,unsigned int &,unsigned int &,unsigned int &,enum Spectre::Engine::Format &,unsigned int &,enum Spectre::Engine::Usage &,0>(
            (unsigned int)&Destination,
            (unsigned int)&v43,
            (unsigned int)&v42,
            (unsigned int)&v46,
            (__int64)&a5,
            (__int64)&a7,
            (__int64)&a6);
    v17 = 2;
  }
  else
  {
    v16 = std::make_unique<Spectre::Engine::TextureDesc,unsigned int &,unsigned int &,enum Spectre::Engine::Format &,unsigned int &,enum Spectre::Engine::Usage &,0>(
            (unsigned int)&v51,
            (unsigned int)&v43,
            (unsigned int)&v42,
            (unsigned int)&a5,
            (__int64)&a7,
            (__int64)&a6);
    v17 = 1;
  }
  v18 = (int **)(a1 + 128);
  std::unique_ptr<Spectre::Engine::TextureDesc>::operator=<std::default_delete<Spectre::Engine::TextureDesc>,0>(
    a1 + 128,
    v16);
  if ( (v17 & 2) != 0 )
  {
    v17 &= ~2u;
    std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(&Destination);
  }
  if ( (v17 & 1) != 0 )
    std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(&v51);
  Spectre::Engine::CreateDefaultImageSetView(v49, *v18, v12, v13);
  if ( v14 )
  {
    LOBYTE(v19) = 1;
    Spectre::Engine::RendererResource::SetOption(a1, 1, v19);
  }
  v20 = *(_DWORD **)(a1 + 72);
  Destination = v20;
  v21 = 0;
  if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
  {
    if ( v14 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(struct Spectre::Engine::RenderDevice *))(*(_QWORD *)v14 + 32LL))(v14) )
      {
        std::string::string(&v51, "Texture cannot be created to just target generic devices");
        v39 = std::string::string(
                &v47,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
        Spectre::Engine::EngineException::EngineException(
          (unsigned int)pExceptionObject,
          v39,
          v40,
          (unsigned int)&v51,
          0);
        throw (Spectre::Engine::EngineException *)pExceptionObject;
      }
      Spectre::Engine::Texture::CreateDeviceTextureHelper(
        (Spectre::Engine::Texture *)a1,
        (const struct Spectre::Engine::TextureImageSetView *)v49,
        v14);
      Spectre::Engine::RendererResource::SetOption(a1, 2, 0);
      Spectre::Engine::RendererResource::SetOption(v23, (unsigned int)(v22 + 4), v22);
      v21 = 1;
    }
    else
    {
      Spectre::Engine::Engine::SafeGetDeviceList(v20, &v47);
      v24 = v47;
      v25 = v48;
      if ( v47 != v48 )
      {
        do
        {
          std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v51,
            v24);
          v26 = v51;
          if ( !(*(unsigned __int8 (__fastcall **)(struct Spectre::Engine::RenderDevice *))(*(_QWORD *)v51 + 32LL))(v51) )
          {
            Spectre::Engine::Texture::CreateDeviceTextureHelper(
              (Spectre::Engine::Texture *)a1,
              (const struct Spectre::Engine::TextureImageSetView *)v49,
              v26);
            v21 = 1;
          }
          if ( v52 )
            std::_Ref_count_base::_Decref(v52);
          v24 += 16;
        }
        while ( v24 != v25 );
        v12 = v44;
      }
      std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(&v47);
    }
    v20 = Destination;
  }
  if ( v12 && (v20[138] == 1 || !v21) )
  {
    v27 = *v18;
    FormatSlicePitch = Spectre::Engine::GetFormatSlicePitch(
                         (unsigned int)(*v18)[4],
                         (unsigned int)**v18,
                         (unsigned int)(*v18)[1]);
    if ( (v27[5] & 0x10) != 0 )
      FormatSlicePitch *= 6;
    if ( v27[2] * FormatSlicePitch != (_DWORD)v45 )
    {
      std::string::string(&v51, "Wrong buffer size");
      v37 = std::string::string(
              &v47,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v37, v38, (unsigned int)&v51, 1);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    std::make_unique<unsigned char [0],0>(&Destination, v13);
    v29 = Destination;
    memcpy_s(Destination, v13, v12, v13);
    v30 = operator new(0x40u);
    if ( v30 )
    {
      Destination = 0;
      v44 = v29;
      v30 = (void *)Spectre::Engine::TextureImageSet::TextureImageSet(v30, v49, &v44, v13);
    }
    v45 = v30;
    std::unique_ptr<Spectre::Utils::Tweening::ITweenable>::operator=<Spectre::Utils::Tweening::TweenProperty<float,Spectre::Utils::Tweening::TransformationDefault<float>>,std::default_delete<Spectre::Utils::Tweening::TweenProperty<float,Spectre::Utils::Tweening::TransformationDefault<float>>>,0>(
      a1 + 136,
      &v45);
    std::unique_ptr<Spectre::Engine::TextureImageSet>::~unique_ptr<Spectre::Engine::TextureImageSet>(&v45);
    Microsoft::WRL::Details::MakeAllocator<SpectreTexture>::~MakeAllocator<SpectreTexture>(&Destination);
  }
  v31 = *v18;
  if ( *v18 )
  {
    v32 = v31[1];
    v33 = *v31;
  }
  else
  {
    v32 = 0;
    v33 = 0;
  }
  v34 = 0;
  v34.m128_f32[0] = (float)v33;
  v35 = 0;
  v35.m128_f32[0] = (float)v32;
  Spectre::Engine::Texture::SetActiveSize(a1, _mm_unpacklo_ps(v34, v35).m128_u64[0]);
  return std::vector<Spectre::Engine::TextureImageDesc>::_Tidy(v50);
}

```

## disassembly

```asm
0x180051990  push    rbp
0x180051992  push    rbx
0x180051993  push    rsi
0x180051994  push    rdi
0x180051995  push    r12
0x180051997  push    r13
0x180051999  push    r14
0x18005199b  push    r15
0x18005199d  lea     rbp, [rsp-38h]
0x1800519a2  sub     rsp, 138h
0x1800519a9  mov     rax, cs:__security_cookie
0x1800519b0  xor     rax, rsp
0x1800519b3  mov     [rbp+70h+var_50], rax
0x1800519b7  mov     ebx, r9d
0x1800519ba  mov     rdi, rcx
0x1800519bd  mov     [rsp+170h+var_120], edx
0x1800519c1  mov     [rsp+170h+var_128], r8d
0x1800519c6  mov     [rsp+170h+var_108], ebx
0x1800519ca  mov     r13, [rbp+70h+Source]
0x1800519d1  mov     [rsp+170h+var_118], r13
0x1800519d6  mov     r14d, dword ptr [rbp+70h+DestinationSize]
0x1800519dd  mov     dword ptr [rsp+170h+var_110], r14d
0x1800519e2  mov     rsi, [rbp+70h+arg_48]
0x1800519e9  mov     dword ptr [rsp+170h+Destination], 0
0x1800519f1  lea     rax, [rcx+88h]
0x1800519f8  mov     rdx, [rax]
0x1800519fb  mov     qword ptr [rax], 0
0x180051a02  test    rdx, rdx
0x180051a05  jz      short loc_180051A0C
0x180051a07  call    ??R?$default_delete@VITweenable@Tweening@Utils@Spectre@@@std@@QEBAXPEAVITweenable@Tweening@Utils@Spectre@@@Z; std::default_delete<Spectre::Utils::Tweening::ITweenable>::operator()(Spectre::Utils::Tweening::ITweenable *)
0x180051a0c  mov     r12d, 1
0x180051a12  lea     rax, [rbp+70h+arg_28]
0x180051a19  lea     r8, [rsp+170h+var_128]
0x180051a1e  lea     rdx, [rsp+170h+var_120]
0x180051a23  test    ebx, ebx
0x180051a25  jnz     short loc_180051A4D
0x180051a27  mov     [rsp+170h+var_148], rax
0x180051a2c  lea     rax, [rbp+70h+arg_30]
0x180051a33  mov     [rsp+170h+var_150], rax
0x180051a38  lea     r9, [rbp+70h+arg_20]
0x180051a3f  lea     rcx, [rbp+70h+var_A8]
0x180051a43  call    ??$make_unique@UTextureDesc@Engine@Spectre@@AEAIAEAIAEAW4Format@23@AEAIAEAW4Usage@23@$0A@@std@@YA?AV?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@0@AEAI0AEAW4Format@Engine@Spectre@@0AEAW4Usage@34@@Z; std::make_unique<Spectre::Engine::TextureDesc,uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &,0>(uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &)
0x180051a48  mov     ebx, r12d
0x180051a4b  jmp     short loc_180051A7E
0x180051a4d  mov     [rsp+170h+var_140], rax
0x180051a52  lea     rax, [rbp+70h+arg_30]
0x180051a59  mov     [rsp+170h+var_148], rax
0x180051a5e  lea     rax, [rbp+70h+arg_20]
0x180051a65  mov     [rsp+170h+var_150], rax
0x180051a6a  lea     r9, [rsp+170h+var_108]
0x180051a6f  lea     rcx, [rsp+170h+Destination]
0x180051a74  call    ??$make_unique@UTextureDesc@Engine@Spectre@@AEAIAEAIAEAIAEAW4Format@23@AEAIAEAW4Usage@23@$0A@@std@@YA?AV?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@0@AEAI00AEAW4Format@Engine@Spectre@@0AEAW4Usage@34@@Z; std::make_unique<Spectre::Engine::TextureDesc,uint &,uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &,0>(uint &,uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &)
0x180051a79  mov     ebx, 2
0x180051a7e  lea     r15, [rdi+80h]
0x180051a85  mov     rdx, rax
0x180051a88  mov     rcx, r15
0x180051a8b  call    ??$?4U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@$0A@@?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Spectre::Engine::TextureDesc>::operator=<std::default_delete<Spectre::Engine::TextureDesc>,0>(std::unique_ptr<Spectre::Engine::TextureDesc> &&)
0x180051a90  test    bl, 2
0x180051a93  jz      short loc_180051AA2
0x180051a95  and     ebx, 0FFFFFFFDh
0x180051a98  lea     rcx, [rsp+170h+Destination]
0x180051a9d  call    ??1?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(void)
0x180051aa2  test    r12b, bl
0x180051aa5  jz      short loc_180051AB0
0x180051aa7  lea     rcx, [rbp+70h+var_A8]
0x180051aab  call    ??1?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(void)
0x180051ab0  mov     r9, r14
0x180051ab3  mov     r8, r13
0x180051ab6  mov     rdx, [r15]
0x180051ab9  lea     rcx, [rbp+70h+var_E0]
0x180051abd  call    ?CreateDefaultImageSetView@Engine@Spectre@@YA?AUTextureImageSetView@12@AEBUTextureDesc@12@PEBX_K@Z; Spectre::Engine::CreateDefaultImageSetView(Spectre::Engine::TextureDesc const &,void const *,unsigned __int64)
0x180051ac2  nop
0x180051ac3  test    rsi, rsi
0x180051ac6  jz      short loc_180051AD6
0x180051ac8  mov     r8b, r12b
0x180051acb  mov     edx, r12d
0x180051ace  mov     rcx, rdi
0x180051ad1  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x180051ad6  mov     rax, [rdi+48h]
0x180051ada  mov     [rsp+170h+Destination], rax
0x180051adf  xor     r12b, r12b
0x180051ae2  test    byte ptr [rdi+28h], 1
0x180051ae6  jz      loc_180051BB3
0x180051aec  test    rsi, rsi
0x180051aef  jz      short loc_180051B34
0x180051af1  mov     rax, [rsi]
0x180051af4  mov     rcx, rsi
0x180051af7  mov     rax, [rax+20h]
0x180051afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b00  test    al, al
0x180051b02  jnz     loc_180051D1F
0x180051b08  mov     r8, rsi; struct Spectre::Engine::RenderDevice *
0x180051b0b  lea     rdx, [rbp+70h+var_E0]; struct Spectre::Engine::TextureImageSetView *
0x180051b0f  mov     rcx, rdi; this
0x180051b12  call    ?CreateDeviceTextureHelper@Texture@Engine@Spectre@@AEAAXAEBUTextureImageSetView@23@PEAVRenderDevice@23@@Z; Spectre::Engine::Texture::CreateDeviceTextureHelper(Spectre::Engine::TextureImageSetView const &,Spectre::Engine::RenderDevice *)
0x180051b17  xor     r8d, r8d
0x180051b1a  lea     edx, [r8+2]
0x180051b1e  mov     rcx, rdi
0x180051b21  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x180051b26  lea     edx, [r8+4]
0x180051b2a  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x180051b2f  mov     r12b, 1
0x180051b32  jmp     short loc_180051BAE
0x180051b34  lea     rdx, [rsp+170h+var_100]
0x180051b39  mov     rcx, rax
0x180051b3c  call    ?SafeGetDeviceList@Engine@1Spectre@@QEAA?AV?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@XZ; Spectre::Engine::Engine::SafeGetDeviceList(void)
0x180051b41  nop
0x180051b42  mov     rbx, [rsp+170h+var_100]
0x180051b47  mov     rsi, [rsp+170h+var_F8]
0x180051b4c  cmp     rbx, rsi
0x180051b4f  jz      short loc_180051BA4
0x180051b51  mov     rdx, rbx
0x180051b54  lea     rcx, [rbp+70h+var_A8]
0x180051b58  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180051b5d  nop
0x180051b5e  mov     r13, [rbp+70h+var_A8]
0x180051b62  mov     rax, [r13+0]
0x180051b66  mov     rcx, r13
0x180051b69  mov     rax, [rax+20h]
0x180051b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b72  test    al, al
0x180051b74  jnz     short loc_180051B88
0x180051b76  mov     r8, r13; struct Spectre::Engine::RenderDevice *
0x180051b79  lea     rdx, [rbp+70h+var_E0]; struct Spectre::Engine::TextureImageSetView *
0x180051b7d  mov     rcx, rdi; this
0x180051b80  call    ?CreateDeviceTextureHelper@Texture@Engine@Spectre@@AEAAXAEBUTextureImageSetView@23@PEAVRenderDevice@23@@Z; Spectre::Engine::Texture::CreateDeviceTextureHelper(Spectre::Engine::TextureImageSetView const &,Spectre::Engine::RenderDevice *)
0x180051b85  mov     r12b, 1
0x180051b88  mov     rcx, [rbp+70h+var_A0]; this
0x180051b8c  test    rcx, rcx
0x180051b8f  jz      short loc_180051B96
0x180051b91  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180051b96  add     rbx, 10h
0x180051b9a  cmp     rbx, rsi
0x180051b9d  jnz     short loc_180051B51
0x180051b9f  mov     r13, [rsp+170h+var_118]
0x180051ba4  lea     rcx, [rsp+170h+var_100]
0x180051ba9  call    ?_Tidy@?$vector@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(void)
0x180051bae  mov     rax, [rsp+170h+Destination]
0x180051bb3  test    r13, r13
0x180051bb6  jz      loc_180051C76
0x180051bbc  cmp     dword ptr [rax+228h], 1
0x180051bc3  jz      short loc_180051BCE
0x180051bc5  test    r12b, r12b
0x180051bc8  jnz     loc_180051C76
0x180051bce  mov     rbx, [r15]
0x180051bd1  mov     r8d, [rbx+4]
0x180051bd5  mov     edx, [rbx]
0x180051bd7  mov     ecx, [rbx+10h]
0x180051bda  call    Spectre__Engine__GetFormatSlicePitch
0x180051bdf  test    byte ptr [rbx+14h], 10h
0x180051be3  jz      short loc_180051BEA
0x180051be5  lea     eax, [rax+rax*2]
0x180051be8  add     eax, eax
0x180051bea  imul    eax, [rbx+8]
0x180051bee  cmp     eax, dword ptr [rsp+170h+var_110]
0x180051bf2  jnz     loc_180051CD7
0x180051bf8  mov     rdx, r14
0x180051bfb  lea     rcx, [rsp+170h+Destination]
0x180051c00  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180051c05  mov     r9, r14; SourceSize
0x180051c08  mov     r8, r13; Source
0x180051c0b  mov     rdx, r14; DestinationSize
0x180051c0e  mov     rbx, [rsp+170h+Destination]
0x180051c13  mov     rcx, rbx; Destination
0x180051c16  call    memcpy_s
0x180051c1b  mov     ecx, 40h ; '@'; unsigned __int64
0x180051c20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051c25  test    rax, rax
0x180051c28  jz      short loc_180051C4C
0x180051c2a  mov     [rsp+170h+Destination], 0
0x180051c33  mov     [rsp+170h+var_118], rbx
0x180051c38  mov     r9, r14
0x180051c3b  lea     r8, [rsp+170h+var_118]
0x180051c40  lea     rdx, [rbp+70h+var_E0]
0x180051c44  mov     rcx, rax
0x180051c47  call    ??0TextureImageSet@Engine@Spectre@@QEAA@$$QEAUTextureImageSetView@12@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@_K@Z; Spectre::Engine::TextureImageSet::TextureImageSet(Spectre::Engine::TextureImageSetView &&,std::unique_ptr<uchar [0]>,unsigned __int64)
0x180051c4c  mov     [rsp+170h+var_110], rax
0x180051c51  lea     rdx, [rsp+170h+var_110]
0x180051c56  lea     rcx, [rdi+88h]
0x180051c5d  call    ??$?4V?$TweenProperty@MV?$TransformationDefault@M@Tweening@Utils@Spectre@@@Tweening@Utils@Spectre@@U?$default_delete@V?$TweenProperty@MV?$TransformationDefault@M@Tweening@Utils@Spectre@@@Tweening@Utils@Spectre@@@std@@$0A@@?$unique_ptr@VITweenable@Tweening@Utils@Spectre@@U?$default_delete@VITweenable@Tweening@Utils@Spectre@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@V?$TweenProperty@MV?$TransformationDefault@M@Tweening@Utils@Spectre@@@Tweening@Utils@Spectre@@U?$default_delete@V?$TweenProperty@MV?$TransformationDefault@M@Tweening@Utils@Spectre@@@Tweening@Utils@Spectre@@@std@@@1@@Z; std::unique_ptr<Spectre::Utils::Tweening::ITweenable>::operator=<Spectre::Utils::Tweening::TweenProperty<float,Spectre::Utils::Tweening::TransformationDefault<float>>,std::default_delete<Spectre::Utils::Tweening::TweenProperty<float,Spectre::Utils::Tweening::TransformationDefault<float>>>,0>(std::unique_ptr<Spectre::Utils::Tweening::TweenProperty<float,Spectre::Utils::Tweening::TransformationDefault<float>>> &&)
0x180051c62  lea     rcx, [rsp+170h+var_110]
0x180051c67  call    ??1?$unique_ptr@UTextureImageSet@Engine@Spectre@@U?$default_delete@UTextureImageSet@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::TextureImageSet>::~unique_ptr<Spectre::Engine::TextureImageSet>(void)
0x180051c6c  lea     rcx, [rsp+170h+Destination]
0x180051c71  call    ??1?$MakeAllocator@VSpectreTexture@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SpectreTexture>::~MakeAllocator<SpectreTexture>(void)
0x180051c76  mov     rax, [r15]
0x180051c79  test    rax, rax
0x180051c7c  jz      short loc_180051C85
0x180051c7e  mov     ecx, [rax+4]
0x180051c81  mov     edx, [rax]
0x180051c83  jmp     short loc_180051C89
0x180051c85  xor     ecx, ecx
0x180051c87  xor     edx, edx
0x180051c89  mov     eax, edx
0x180051c8b  xorps   xmm1, xmm1
0x180051c8e  cvtsi2ss xmm1, rax
0x180051c93  mov     eax, ecx
0x180051c95  xorps   xmm0, xmm0
0x180051c98  cvtsi2ss xmm0, rax
0x180051c9d  unpcklps xmm1, xmm0
0x180051ca0  movq    rdx, xmm1
0x180051ca5  mov     rcx, rdi
0x180051ca8  call    ?SetActiveSize@Texture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z; Spectre::Engine::Texture::SetActiveSize(Spectre::Utils::Math::Vector2)
0x180051cad  nop
0x180051cae  lea     rcx, [rbp+70h+var_C8]
0x180051cb2  call    ?_Tidy@?$vector@UTextureImageDesc@Engine@Spectre@@V?$allocator@UTextureImageDesc@Engine@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Engine::TextureImageDesc>::_Tidy(void)
0x180051cb7  mov     rcx, [rbp+70h+var_50]
0x180051cbb  xor     rcx, rsp; StackCookie
0x180051cbe  call    __security_check_cookie
0x180051cc3  add     rsp, 138h
0x180051cca  pop     r15
0x180051ccc  pop     r14
0x180051cce  pop     r13
0x180051cd0  pop     r12
0x180051cd2  pop     rdi
0x180051cd3  pop     rsi
0x180051cd4  pop     rbx
0x180051cd5  pop     rbp
0x180051cd6  retn
0x180051cd7  lea     rdx, aWrongBufferSiz; "Wrong buffer size"
0x180051cde  lea     rcx, [rbp+70h+var_A8]
0x180051ce2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051ce7  nop
0x180051ce8  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180051cef  lea     rcx, [rsp+170h+var_100]
0x180051cf4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051cf9  mov     byte ptr [rsp+170h+var_150], 1
0x180051cfe  lea     r9, [rbp+70h+var_A8]
0x180051d02  mov     rdx, rax
0x180051d05  lea     rcx, [rbp+70h+pExceptionObject]
0x180051d09  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180051d0e  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180051d15  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180051d19  call    _CxxThrowException_0
0x180051d1f  lea     rdx, aTextureCannotB; "Texture cannot be created to just targe"...
0x180051d26  lea     rcx, [rbp+70h+var_A8]
0x180051d2a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051d2f  nop
0x180051d30  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180051d37  lea     rcx, [rsp+170h+var_100]
0x180051d3c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051d41  mov     byte ptr [rsp+170h+var_150], 0
0x180051d46  lea     r9, [rbp+70h+var_A8]
0x180051d4a  mov     rdx, rax
0x180051d4d  lea     rcx, [rbp+70h+pExceptionObject]
0x180051d51  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180051d56  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180051d5d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180051d61  call    _CxxThrowException_0
```
