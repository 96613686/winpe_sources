# Spectre::Engine::D3D11::CommandListD3D11::SubmitCopyTexture2D(std::shared_ptr<Spectre::Engine::Texture> const &,uint,uint,uint,uint,std::shared_ptr<Spectre::Engine::Texture> const &,uint,uint)

- ea: `0x1800bff10`
- end: `0x1800c02e2`
- name: `?SubmitCopyTexture2D@CommandListD3D11@D3D11@Engine@Spectre@@MEAAXAEBV?$shared_ptr@VTexture@Engine@Spectre@@@std@@IIII0II@Z`
- size: `978`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000fe40`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x1800182e8`
- `0x18005225c`
- `0x1800523f8`
- `0x18005240c`
- `0x1800681a8`
- `0x1800bcae0`
- `0x1800bedf4`
- `0x1800bff10`
- `0x1800e7010`

## string_xrefs

- `0x1800c0265`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c02ac`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c0254`: `CopyTexture2D does not support mipmapped or MSAA textures`
- `0x1800c029b`: `CopyTexture2D does not support mipmapped or MSAA textures`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Spectre::Engine::D3D11::CommandListD3D11::SubmitCopyTexture2D(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        _QWORD *a7,
        int a8,
        int a9)
{
  Spectre::Engine::DeviceTexture **DeviceTexture; // rax
  char v14; // bl
  Spectre::Engine::DeviceTexture *v15; // rcx
  std::_Ref_count_base *v16; // rsi
  __int64 v17; // rax
  Spectre::Engine::DeviceTexture *v18; // rcx
  __int64 v19; // rcx
  __int64 *Texture; // rax
  char v21; // di
  char v22; // di
  Spectre::Engine::DeviceTexture **v23; // rax
  char v24; // bl
  Spectre::Engine::DeviceTexture *v25; // rcx
  char v26; // bl
  std::_Ref_count_base *v27; // rsi
  __int64 v28; // rax
  Spectre::Engine::DeviceTexture *v29; // rcx
  __int64 v30; // rcx
  Spectre::Engine::DeviceTexture **v31; // rax
  char v32; // di
  char v33; // di
  int v35; // eax
  int v36; // r8d
  int v37; // eax
  int v38; // r8d
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  char v40[8]; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v41; // [rsp+60h] [rbp-A0h]
  Spectre::Engine::DeviceTexture *v42; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v43; // [rsp+70h] [rbp-90h]
  Spectre::Engine::DeviceTexture *v44; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v47[6]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v48[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v49[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+E8h] [rbp-18h] BYREF

  LODWORD(v39) = 0;
  v46 = 0;
  if ( *a7 )
  {
    DeviceTexture = (Spectre::Engine::DeviceTexture **)Spectre::Engine::Texture::GetDeviceTexture(
                                                         *a7,
                                                         &v44,
                                                         *(unsigned int *)(a1 + 88));
    v14 = 1;
    v15 = *DeviceTexture;
  }
  else
  {
    v41 = 0;
    DeviceTexture = (Spectre::Engine::DeviceTexture **)v40;
    v14 = 2;
    v15 = 0;
  }
  v42 = v15;
  v16 = DeviceTexture[1];
  v43 = v16;
  *DeviceTexture = 0;
  DeviceTexture[1] = 0;
  if ( (v14 & 2) != 0 )
  {
    v14 &= ~2u;
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
  }
  if ( (v14 & 1) != 0 )
  {
    v14 &= ~1u;
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
  }
  v17 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v40,
          &v42);
  Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(
    &v44,
    v17);
  if ( Spectre::Engine::DeviceTexture::GetMipLevels(v44) > 1 || Spectre::Engine::DeviceTexture::GetSampleCount(v18) > 1 )
  {
    std::string::string(v48, "CopyTexture2D does not support mipmapped or MSAA textures");
    v37 = std::string::string(
            v49,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v37, v38, (unsigned int)v48, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( v19 )
  {
    Texture = (__int64 *)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v19, &v42);
    v21 = 4;
  }
  else
  {
    v39 = 0;
    Texture = &v39;
    v21 = 8;
  }
  v22 = v14 | v21;
  Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(&v46, Texture);
  if ( (v22 & 8) != 0 )
  {
    v22 &= ~8u;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  }
  if ( (v22 & 4) != 0 )
  {
    v22 &= ~4u;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  }
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v39 = 0;
  if ( *a2 )
  {
    v23 = (Spectre::Engine::DeviceTexture **)Spectre::Engine::Texture::GetDeviceTexture(
                                               *a2,
                                               v40,
                                               *(unsigned int *)(a1 + 88));
    v24 = 16;
    v25 = *v23;
  }
  else
  {
    v45 = 0;
    v23 = &v44;
    v24 = 32;
    v25 = 0;
  }
  v26 = v22 | v24;
  v42 = v25;
  v27 = v23[1];
  v43 = v27;
  *v23 = 0;
  v23[1] = 0;
  if ( (v26 & 0x20) != 0 )
  {
    v26 &= ~0x20u;
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
  }
  if ( (v26 & 0x10) != 0 )
  {
    v26 &= ~0x10u;
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
  }
  v28 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v40,
          &v42);
  Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(
    &v44,
    v28);
  if ( Spectre::Engine::DeviceTexture::GetMipLevels(v44) > 1 || Spectre::Engine::DeviceTexture::GetSampleCount(v29) > 1 )
  {
    std::string::string(v49, "CopyTexture2D does not support mipmapped or MSAA textures");
    v35 = std::string::string(
            v48,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v35, v36, (unsigned int)v49, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( v30 )
  {
    v31 = (Spectre::Engine::DeviceTexture **)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v30, v40);
    v32 = 64;
  }
  else
  {
    v42 = 0;
    v31 = &v42;
    v32 = 0x80;
  }
  v33 = v26 | v32;
  Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(&v39, v31);
  if ( v33 < 0 )
  {
    v33 &= ~0x80u;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  }
  if ( (v33 & 0x40) != 0 )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  v47[2] = 0;
  v47[0] = a8;
  v47[1] = a9;
  v47[3] = a5 + a8;
  v47[4] = a9 + a6;
  v47[5] = 1;
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, _DWORD, __int64, _DWORD, _DWORD *))(**(_QWORD **)(a1 + 144)
                                                                                                  + 368LL))(
    *(_QWORD *)(a1 + 144),
    v39,
    0,
    a3,
    a4,
    0,
    v46,
    0,
    v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
}

```

## disassembly

```asm
0x1800bff10  push    rbp
0x1800bff12  push    rbx
0x1800bff13  push    rsi
0x1800bff14  push    rdi
0x1800bff15  push    r12
0x1800bff17  push    r13
0x1800bff19  push    r14
0x1800bff1b  push    r15
0x1800bff1d  lea     rbp, [rsp-38h]
0x1800bff22  sub     rsp, 138h
0x1800bff29  mov     rax, cs:__security_cookie
0x1800bff30  xor     rax, rsp
0x1800bff33  mov     [rbp+70h+var_50], rax
0x1800bff37  mov     r13d, r9d
0x1800bff3a  mov     r12d, r8d
0x1800bff3d  mov     r14, rdx
0x1800bff40  mov     r15, rcx
0x1800bff43  mov     rax, [rbp+70h+arg_30]
0x1800bff4a  xor     edi, edi
0x1800bff4c  mov     dword ptr [rsp+170h+var_120], edi
0x1800bff50  mov     [rbp+70h+var_E8], rdi
0x1800bff54  mov     rcx, [rax]
0x1800bff57  test    rcx, rcx
0x1800bff5a  jz      short loc_1800BFF72
0x1800bff5c  mov     r8d, [r15+58h]
0x1800bff60  lea     rdx, [rsp+170h+var_F8]
0x1800bff65  call    ?GetDeviceTexture@Texture@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@W4RenderDeviceID@23@@Z; Spectre::Engine::Texture::GetDeviceTexture(Spectre::Engine::RenderDeviceID)
0x1800bff6a  lea     ebx, [rdi+1]
0x1800bff6d  mov     rcx, [rax]
0x1800bff70  jmp     short loc_1800BFF84
0x1800bff72  mov     [rsp+170h+var_110], rdi
0x1800bff77  lea     rax, [rsp+170h+var_118]
0x1800bff7c  mov     ebx, 2
0x1800bff81  mov     rcx, rdi
0x1800bff84  mov     [rsp+170h+var_108], rcx
0x1800bff89  mov     rsi, [rax+8]
0x1800bff8d  mov     [rsp+170h+var_100], rsi
0x1800bff92  mov     [rax], rdi
0x1800bff95  mov     [rax+8], rdi
0x1800bff99  test    bl, 2
0x1800bff9c  jz      short loc_1800BFFB0
0x1800bff9e  and     ebx, 0FFFFFFFDh
0x1800bffa1  mov     rcx, [rsp+170h+var_110]; this
0x1800bffa6  test    rcx, rcx
0x1800bffa9  jz      short loc_1800BFFB0
0x1800bffab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bffb0  test    bl, 1
0x1800bffb3  jz      short loc_1800BFFC6
0x1800bffb5  and     ebx, 0FFFFFFFEh
0x1800bffb8  mov     rcx, [rbp+70h+var_F0]; this
0x1800bffbc  test    rcx, rcx
0x1800bffbf  jz      short loc_1800BFFC6
0x1800bffc1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bffc6  lea     rdx, [rsp+170h+var_108]
0x1800bffcb  lea     rcx, [rsp+170h+var_118]
0x1800bffd0  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800bffd5  mov     rdx, rax
0x1800bffd8  lea     rcx, [rsp+170h+var_F8]
0x1800bffdd  call    ??$spectre_safe_pointer_cast@VCommandListD3D11@D3D11@Engine@Spectre@@VCommandList@34@@Utils@Spectre@@YA?AV?$shared_ptr@VCommandListD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VCommandList@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(std::shared_ptr<Spectre::Engine::CommandList>)
0x1800bffe2  nop
0x1800bffe3  mov     rcx, [rsp+170h+var_F8]; this
0x1800bffe8  call    ?GetMipLevels@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetMipLevels(void)
0x1800bffed  cmp     eax, 1
0x1800bfff0  ja      loc_1800C029B
0x1800bfff6  call    ?GetSampleCount@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetSampleCount(void)
0x1800bfffb  cmp     eax, 1
0x1800bfffe  ja      loc_1800C029B
0x1800c0004  test    rcx, rcx
0x1800c0007  jz      short loc_1800C001A
0x1800c0009  lea     rdx, [rsp+170h+var_108]
0x1800c000e  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x1800c0013  mov     edi, 4
0x1800c0018  jmp     short loc_1800C0029
0x1800c001a  mov     [rsp+170h+var_120], rdi
0x1800c001f  lea     rax, [rsp+170h+var_120]
0x1800c0024  mov     edi, 8
0x1800c0029  or      edi, ebx
0x1800c002b  mov     rdx, rax
0x1800c002e  lea     rcx, [rbp+70h+var_E8]
0x1800c0032  call    ??4?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(Microsoft::WRL::ComPtr<ID3D11Texture2D> &&)
0x1800c0037  test    dil, 8
0x1800c003b  jz      short loc_1800C004A
0x1800c003d  and     edi, 0FFFFFFF7h
0x1800c0040  lea     rcx, [rsp+170h+var_120]
0x1800c0045  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c004a  test    dil, 4
0x1800c004e  jz      short loc_1800C005E
0x1800c0050  and     edi, 0FFFFFFFBh
0x1800c0053  lea     rcx, [rsp+170h+var_108]
0x1800c0058  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c005d  nop
0x1800c005e  mov     rcx, [rbp+70h+var_F0]; this
0x1800c0062  test    rcx, rcx
0x1800c0065  jz      short loc_1800C006D
0x1800c0067  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c006c  nop
0x1800c006d  test    rsi, rsi
0x1800c0070  jz      short loc_1800C007A
0x1800c0072  mov     rcx, rsi; this
0x1800c0075  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c007a  mov     [rsp+170h+var_120], 0
0x1800c0083  mov     rcx, [r14]
0x1800c0086  xor     r14d, r14d
0x1800c0089  test    rcx, rcx
0x1800c008c  jz      short loc_1800C00A5
0x1800c008e  mov     r8d, [r15+58h]
0x1800c0092  lea     rdx, [rsp+170h+var_118]
0x1800c0097  call    ?GetDeviceTexture@Texture@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@W4RenderDeviceID@23@@Z; Spectre::Engine::Texture::GetDeviceTexture(Spectre::Engine::RenderDeviceID)
0x1800c009c  lea     ebx, [r14+10h]
0x1800c00a0  mov     rcx, [rax]
0x1800c00a3  jmp     short loc_1800C00B6
0x1800c00a5  mov     [rbp+70h+var_F0], r14
0x1800c00a9  lea     rax, [rsp+170h+var_F8]
0x1800c00ae  mov     ebx, 20h ; ' '
0x1800c00b3  mov     rcx, r14
0x1800c00b6  or      ebx, edi
0x1800c00b8  mov     [rsp+170h+var_108], rcx
0x1800c00bd  mov     rsi, [rax+8]
0x1800c00c1  mov     [rsp+170h+var_100], rsi
0x1800c00c6  mov     [rax], r14
0x1800c00c9  mov     [rax+8], r14
0x1800c00cd  test    bl, 20h
0x1800c00d0  jz      short loc_1800C00E3
0x1800c00d2  and     ebx, 0FFFFFFDFh
0x1800c00d5  mov     rcx, [rbp+70h+var_F0]; this
0x1800c00d9  test    rcx, rcx
0x1800c00dc  jz      short loc_1800C00E3
0x1800c00de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c00e3  test    bl, 10h
0x1800c00e6  jz      short loc_1800C00FA
0x1800c00e8  and     ebx, 0FFFFFFEFh
0x1800c00eb  mov     rcx, [rsp+170h+var_110]; this
0x1800c00f0  test    rcx, rcx
0x1800c00f3  jz      short loc_1800C00FA
0x1800c00f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c00fa  lea     rdx, [rsp+170h+var_108]
0x1800c00ff  lea     rcx, [rsp+170h+var_118]
0x1800c0104  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c0109  mov     rdx, rax
0x1800c010c  lea     rcx, [rsp+170h+var_F8]
0x1800c0111  call    ??$spectre_safe_pointer_cast@VCommandListD3D11@D3D11@Engine@Spectre@@VCommandList@34@@Utils@Spectre@@YA?AV?$shared_ptr@VCommandListD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VCommandList@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(std::shared_ptr<Spectre::Engine::CommandList>)
0x1800c0116  nop
0x1800c0117  mov     rcx, [rsp+170h+var_F8]; this
0x1800c011c  call    ?GetMipLevels@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetMipLevels(void)
0x1800c0121  cmp     eax, 1
0x1800c0124  ja      loc_1800C0254
0x1800c012a  call    ?GetSampleCount@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetSampleCount(void)
0x1800c012f  cmp     eax, 1
0x1800c0132  ja      loc_1800C0254
0x1800c0138  test    rcx, rcx
0x1800c013b  jz      short loc_1800C014E
0x1800c013d  lea     rdx, [rsp+170h+var_118]
0x1800c0142  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x1800c0147  mov     edi, 40h ; '@'
0x1800c014c  jmp     short loc_1800C015D
0x1800c014e  mov     [rsp+170h+var_108], r14
0x1800c0153  lea     rax, [rsp+170h+var_108]
0x1800c0158  mov     edi, 80h
0x1800c015d  or      edi, ebx
0x1800c015f  mov     rdx, rax
0x1800c0162  lea     rcx, [rsp+170h+var_120]
0x1800c0167  call    ??4?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(Microsoft::WRL::ComPtr<ID3D11Texture2D> &&)
0x1800c016c  test    dil, dil
0x1800c016f  jns     short loc_1800C017F
0x1800c0171  btr     edi, 7
0x1800c0175  lea     rcx, [rsp+170h+var_108]
0x1800c017a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c017f  test    dil, 40h
0x1800c0183  jz      short loc_1800C0190
0x1800c0185  lea     rcx, [rsp+170h+var_118]
0x1800c018a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c018f  nop
0x1800c0190  mov     rcx, [rbp+70h+var_F0]; this
0x1800c0194  test    rcx, rcx
0x1800c0197  jz      short loc_1800C019F
0x1800c0199  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c019e  nop
0x1800c019f  test    rsi, rsi
0x1800c01a2  jz      short loc_1800C01AC
0x1800c01a4  mov     rcx, rsi; this
0x1800c01a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c01ac  mov     [rbp+70h+var_D8], r14d
0x1800c01b0  mov     ecx, [rbp+70h+arg_38]
0x1800c01b6  mov     [rbp+70h+var_E0], ecx
0x1800c01b9  mov     edx, [rbp+70h+arg_40]
0x1800c01bf  mov     [rbp+70h+var_DC], edx
0x1800c01c2  add     ecx, [rbp+70h+arg_20]
0x1800c01c8  mov     [rbp+70h+var_D4], ecx
0x1800c01cb  mov     ecx, [rbp+70h+arg_28]
0x1800c01d1  add     ecx, edx
0x1800c01d3  mov     [rbp+70h+var_D0], ecx
0x1800c01d6  mov     [rbp+70h+var_CC], 1
0x1800c01dd  mov     rcx, [r15+90h]
0x1800c01e4  mov     rax, [rcx]
0x1800c01e7  lea     rdx, [rbp+70h+var_E0]
0x1800c01eb  mov     [rsp+170h+var_130], rdx
0x1800c01f0  mov     [rsp+170h+var_138], r14d
0x1800c01f5  mov     rdx, [rbp+70h+var_E8]
0x1800c01f9  mov     [rsp+170h+var_140], rdx
0x1800c01fe  mov     [rsp+170h+var_148], r14d
0x1800c0203  mov     [rsp+170h+var_150], r13d
0x1800c0208  mov     r9d, r12d
0x1800c020b  xor     r8d, r8d
0x1800c020e  mov     rdx, [rsp+170h+var_120]
0x1800c0213  mov     rax, [rax+170h]
0x1800c021a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c021f  nop
0x1800c0220  lea     rcx, [rsp+170h+var_120]
0x1800c0225  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c022a  nop
0x1800c022b  lea     rcx, [rbp+70h+var_E8]
0x1800c022f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c0234  mov     rcx, [rbp+70h+var_50]
0x1800c0238  xor     rcx, rsp; StackCookie
0x1800c023b  call    __security_check_cookie
0x1800c0240  add     rsp, 138h
0x1800c0247  pop     r15
0x1800c0249  pop     r14
0x1800c024b  pop     r13
0x1800c024d  pop     r12
0x1800c024f  pop     rdi
0x1800c0250  pop     rsi
0x1800c0251  pop     rbx
0x1800c0252  pop     rbp
0x1800c0253  retn
0x1800c0254  lea     rdx, aCopytexture2dD; "CopyTexture2D does not support mipmappe"...
0x1800c025b  lea     rcx, [rbp+70h+var_A8]
0x1800c025f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c0264  nop
0x1800c0265  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c026c  lea     rcx, [rbp+70h+var_C8]
0x1800c0270  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c0275  mov     byte ptr [rsp+170h+var_150], r14b
0x1800c027a  lea     r9, [rbp+70h+var_A8]
0x1800c027e  mov     rdx, rax
0x1800c0281  lea     rcx, [rbp+70h+pExceptionObject]
0x1800c0285  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c028a  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c0291  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800c0295  call    _CxxThrowException_0
0x1800c029b  lea     rdx, aCopytexture2dD; "CopyTexture2D does not support mipmappe"...
0x1800c02a2  lea     rcx, [rbp+70h+var_C8]
0x1800c02a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c02ab  nop
0x1800c02ac  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c02b3  lea     rcx, [rbp+70h+var_A8]
0x1800c02b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c02bc  mov     byte ptr [rsp+170h+var_150], dil
0x1800c02c1  lea     r9, [rbp+70h+var_C8]
0x1800c02c5  mov     rdx, rax
0x1800c02c8  lea     rcx, [rbp+70h+pExceptionObject]
0x1800c02cc  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c02d1  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c02d8  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800c02dc  call    _CxxThrowException_0
```
