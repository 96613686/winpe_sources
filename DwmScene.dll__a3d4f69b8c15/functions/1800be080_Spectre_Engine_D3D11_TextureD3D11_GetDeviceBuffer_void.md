# Spectre::Engine::D3D11::TextureD3D11::GetDeviceBuffer(void)

- ea: `0x1800be080`
- end: `0x1800be7de`
- name: `?GetDeviceBuffer@TextureD3D11@D3D11@Engine@Spectre@@UEBA?AUTextureImageSet@34@XZ`
- size: `1886`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000d54a`
- `0x18000d660`
- `0x18000d678`
- `0x18000dfa2`
- `0x18000e87c`
- `0x18000e8d0`
- `0x18000eb2c`
- `0x18000fe40`
- `0x18001128c`
- `0x180011f64`
- `0x180012ba8`
- `0x180012c58`
- `0x180014a3c`
- `0x18001c790`
- `0x18001dda8`
- `0x180027ea4`
- `0x18004574c`
- `0x18004d8b0`
- `0x1800510a8`
- `0x1800522b8`
- `0x180052398`
- `0x180052460`
- `0x1800681a8`
- `0x180068214`
- `0x1800b62f0`
- `0x1800b6324`
- `0x1800b7e3c`
- `0x1800bba28`
- `0x1800bc4e8`
- `0x1800bc7c8`
- `0x1800be080`
- `0x1800be9e4`
- `0x1800bee20`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be6ab`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be6ab`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800be2de`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800be613`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800be2de`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800be613`

## string_xrefs

- `0x1800be12e`: `TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for MSAA textures`
- `0x1800be0d8`: `TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for cubemaps`
- `0x1800be420`: `"TextureD3D11::GetDeviceBuffer(): unable to create texture (2D)"`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_BYTE *__fastcall Spectre::Engine::D3D11::TextureD3D11::GetDeviceBuffer(_QWORD *a1, _BYTE *a2)
{
  __int64 *v3; // rax
  __int64 v4; // r14
  int v5; // eax
  int v6; // r8d
  int v7; // eax
  int v8; // r8d
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v9; // r13
  __int64 v10; // rcx
  _QWORD *v11; // r15
  __int64 v12; // rcx
  int v13; // eax
  int v14; // r8d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _BYTE *, _QWORD, _BYTE **); // rbx
  int v17; // eax
  ULONG_PTR v18; // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _OWORD *, _QWORD, _BYTE **); // rbx
  int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // eax
  int v32; // r8d
  __int64 v33; // rbx
  __int64 v34; // r12
  int v35; // eax
  ULONG_PTR v36; // rdi
  unsigned int Format; // eax
  unsigned int v38; // r13d
  unsigned int FormatSlicePitch_0; // r15d
  Spectre::Engine::DeviceTexture *v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdi
  void *v46; // rsi
  _BYTE *v47; // rbx
  _BYTE *v49; // [rsp+40h] [rbp-C0h] BYREF
  void *v50; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v51; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  void *v56; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-78h] BYREF
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v59; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v60; // [rsp+A8h] [rbp-58h]
  EXCEPTION_RECORD pExceptionRecord; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v62[36]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v63; // [rsp+178h] [rbp+78h] BYREF
  __int64 v64; // [rsp+188h] [rbp+88h]
  _OWORD pExceptionObject[3]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v66[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v67[56]; // [rsp+1F0h] [rbp+F0h] BYREF
  void *retaddr; // [rsp+268h] [rbp+168h]

  v51 = a2;
  v53 = a2;
  v3 = (__int64 *)a1[14];
  if ( v3 )
  {
    v4 = *v3;
    if ( *v3 && (*(_BYTE *)(v4 + 20) & 0x10) != 0 )
    {
      std::string::string(
        &v63,
        "TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for cubemaps");
      v5 = std::string::string(
             v62,
             "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v5, v6, (unsigned int)&v63, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
  }
  else
  {
    v4 = 0;
  }
  if ( *((_DWORD *)v3 + 3) > 1u )
  {
    std::string::string(
      &v63,
      "TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for MSAA textures");
    v7 = std::string::string(
           v62,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v7, v8, (unsigned int)&v63, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(a1 + 9, v66);
  Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(
    &v59,
    v66);
  v9 = v59;
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v59, &v55);
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDeviceContext(v9, &v57);
  v52 = 0;
  v54 = 0;
  v10 = a1[21];
  if ( v10 )
  {
    memset(pExceptionObject, 0, 44);
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v10 + 80LL))(v10, pExceptionObject);
    *(_QWORD *)((char *)&pExceptionObject[1] + 12) = 3;
    *(_QWORD *)((char *)&pExceptionObject[2] + 4) = 0x20000;
    HIDWORD(pExceptionObject[0]) = 1;
    v49 = 0;
    v19 = v55;
    v20 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, _BYTE **))(*(_QWORD *)v55 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v21 = v20(v19, pExceptionObject, 0, &v49);
    Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v9, v21);
    if ( v21 < 0 )
    {
      std::string::string(v62, "THROW_IF_FAILED_DETAILED. ");
      v22 = std::string::_Append<char>(v62, " File=", 6);
      std::string::_Append<char>(
        v22,
        "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp",
        92);
      v23 = std::string::_Append<char>(v62, " Line=", 6);
      std::string::_Append<char>(v23, "387", 3);
      v24 = std::string::_Append<char>(v62, " Message=", 9);
      std::string::_Append<char>(v24, "\"TextureD3D11::GetDeviceBuffer(): unable to create texture (2D)\"", 64);
      v25 = std::string::_Append<char>(v62, " Details=\"", 10);
      std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(&v63);
      v26 = ExceptionDetails::ToString(v66, pExceptionObject, &v63);
      v27 = std::string::append(v25, v26);
      std::string::_Append<char>(v27, "\"", 1);
      std::string::_Tidy_deallocate(v66);
      if ( (_QWORD)v63 )
        std::_Deallocate<16>(v63, (v64 - v63) & 0xFFFFFFFFFFFFFFF0uLL);
      v28 = std::string::_Append<char>(v62, " HRESULT=", 9);
      v29 = std::to_string(&v63, (unsigned int)v21);
      std::string::append(v28, v29);
      std::string::_Tidy_deallocate(&v63);
      v30 = std::_String_val<std::_Simple_types<char>>::_Myptr(v62);
      std::string::string(v66, v30);
      v31 = std::string::string(
              &v63,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)v67, v31, v32, v21, (__int64)v66, 0);
      throw (Spectre::Engine::EngineException *)v67;
    }
    Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(&v52, a1 + 21);
    Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(&v54, &v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v11 = a1 + 22;
  }
  else
  {
    v11 = a1 + 22;
    v12 = a1[22];
    if ( !v12 )
    {
      std::string::string(&v63, "TextureD3D11::GetDeviceBuffer - No valid D3D11 texture interface pointer");
      v13 = std::string::string(
              v62,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v13, v14, (unsigned int)&v63, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    memset(v62, 0, sizeof(v62));
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 80LL))(v12, v62);
    *(_QWORD *)&v62[20] = 3;
    *(_QWORD *)&v62[28] = 0x20000;
    v49 = 0;
    v15 = v55;
    v16 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _BYTE **))(*(_QWORD *)v55 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v17 = v16(v15, v62, 0, &v49);
    v18 = v17;
    Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v9, v17);
    if ( (v18 & 0x80000000) != 0LL )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v18;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(&v52, a1 + 22);
    Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(&v54, &v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  }
  v33 = v57;
  v34 = v54;
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 376LL))(v57, v54, v52);
  *(_OWORD *)Src = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, void **))(*(_QWORD *)v33 + 112LL))(
          v33,
          v34,
          0,
          1,
          0,
          Src);
  v36 = v35;
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v9, v35);
  if ( (v36 & 0x80000000) != 0LL )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v36;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  Format = Spectre::Engine::DeviceTexture::GetFormat(a1);
  LODWORD(v49) = Spectre::Engine::GetFormatPitch(Format);
  v38 = (unsigned int)Src[1];
  LODWORD(v50) = Src[1];
  if ( *v11 )
  {
    FormatSlicePitch_0 = HIDWORD(Src[1]);
  }
  else
  {
    Spectre::Engine::DeviceTexture::GetHeight((Spectre::Engine::DeviceTexture *)a1);
    Spectre::Engine::DeviceTexture::GetWidth(v40);
    v42 = Spectre::Engine::DeviceTexture::GetFormat(v41);
    FormatSlicePitch_0 = Spectre::Engine::GetFormatSlicePitch_0(v42, v43, v44, &v50);
  }
  v45 = *(_DWORD *)(v4 + 8) * FormatSlicePitch_0;
  std::make_unique<unsigned char [0],0>(&v50, v45);
  v46 = v50;
  if ( v45 )
  {
    if ( v50 )
    {
      if ( Src[0] )
      {
        memcpy_0(v50, Src[0], (unsigned int)v45);
        goto LABEL_30;
      }
      memset_0(v50, 0, (unsigned int)v45);
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_30:
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 120LL))(v33, v34, 0);
  v66[0] = &v56;
  v50 = 0;
  v56 = v46;
  *(_QWORD *)v62 = 0;
  *(_QWORD *)&v62[8] = v45;
  *(_QWORD *)&v62[16] = __PAIR64__(v38, (unsigned int)v49);
  *(_QWORD *)&v62[24] = FormatSlicePitch_0;
  v63 = 0;
  v64 = 0;
  v49 = &v62[32];
  v53 = v62;
  std::vector<Spectre::Engine::TextureImageDesc>::_Construct_n<Spectre::Engine::TextureImageDesc const *,Spectre::Engine::TextureImageDesc const *>(
    &v63,
    1,
    &v53,
    &v49);
  v47 = v51;
  Spectre::Engine::TextureImageSet::TextureImageSet(v51, &v63, &v56, v45);
  Microsoft::WRL::Details::MakeAllocator<SpectreTexture>::~MakeAllocator<SpectreTexture>(&v50);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  if ( v60 )
    std::_Ref_count_base::_Decref(v60);
  return v47;
}

```

## disassembly

```asm
0x1800be080  mov     [rsp-8+arg_10], rbx
0x1800be085  push    rbp
0x1800be086  push    rsi
0x1800be087  push    rdi
0x1800be088  push    r12
0x1800be08a  push    r13
0x1800be08c  push    r14
0x1800be08e  push    r15
0x1800be090  lea     rbp, [rsp-130h]
0x1800be098  sub     rsp, 230h
0x1800be09f  mov     rax, cs:__security_cookie
0x1800be0a6  xor     rax, rsp
0x1800be0a9  mov     [rbp+160h+var_38], rax
0x1800be0b0  mov     [rsp+260h+var_210], rdx
0x1800be0b5  mov     rsi, rcx
0x1800be0b8  mov     [rsp+260h+var_200], rdx
0x1800be0bd  xor     r12d, r12d
0x1800be0c0  mov     rax, [rcx+70h]
0x1800be0c4  test    rax, rax
0x1800be0c7  jz      short loc_1800BE125
0x1800be0c9  mov     r14, [rax]
0x1800be0cc  test    r14, r14
0x1800be0cf  jz      short loc_1800BE128
0x1800be0d1  test    byte ptr [r14+14h], 10h
0x1800be0d6  jz      short loc_1800BE128
0x1800be0d8  lea     rdx, aTextured3d11Ge_1; "TextureD3D11::GetDeviceBuffer() -- read"...
0x1800be0df  lea     rcx, [rbp+160h+var_E8]
0x1800be0e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be0e8  nop
0x1800be0e9  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800be0f0  lea     rcx, [rbp+160h+var_110]
0x1800be0f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be0f9  mov     byte ptr [rsp+260h+var_240], r12b
0x1800be0fe  lea     r9, [rbp+160h+var_E8]
0x1800be102  mov     rdx, rax
0x1800be105  lea     rcx, [rbp+160h+pExceptionObject]
0x1800be10c  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800be111  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800be118  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x1800be11f  call    _CxxThrowException_0
0x1800be125  mov     r14, r12
0x1800be128  cmp     dword ptr [rax+0Ch], 1
0x1800be12c  jbe     short loc_1800BE17B
0x1800be12e  lea     rdx, aTextured3d11Ge_2; "TextureD3D11::GetDeviceBuffer() -- read"...
0x1800be135  lea     rcx, [rbp+160h+var_E8]
0x1800be139  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be13e  nop
0x1800be13f  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800be146  lea     rcx, [rbp+160h+var_110]
0x1800be14a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be14f  mov     byte ptr [rsp+260h+var_240], r12b
0x1800be154  lea     r9, [rbp+160h+var_E8]
0x1800be158  mov     rdx, rax
0x1800be15b  lea     rcx, [rbp+160h+pExceptionObject]
0x1800be162  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800be167  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800be16e  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x1800be175  call    _CxxThrowException_0
0x1800be17b  add     rcx, 48h ; 'H'
0x1800be17f  lea     rdx, [rbp+160h+var_90]
0x1800be186  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800be18b  lea     rdx, [rbp+160h+var_90]
0x1800be192  lea     rcx, [rbp+160h+var_1C0]
0x1800be196  call    ??$spectre_safe_pointer_cast@VRenderDeviceD3D11@D3D11@Engine@Spectre@@VRenderDevice@34@@Utils@Spectre@@YA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x1800be19b  nop
0x1800be19c  lea     rdx, [rsp+260h+var_1F0]
0x1800be1a1  mov     r13, [rbp+160h+var_1C0]
0x1800be1a5  mov     rcx, r13
0x1800be1a8  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x1800be1ad  nop
0x1800be1ae  lea     rdx, [rbp+160h+var_1E0]
0x1800be1b2  mov     rcx, r13
0x1800be1b5  call    ?GetDeviceContext@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11DeviceContext1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDeviceContext(void)
0x1800be1ba  nop
0x1800be1bb  mov     [rsp+260h+var_208], r12
0x1800be1c0  mov     [rsp+260h+var_1F8], r12
0x1800be1c5  lea     r15, [rsi+0A8h]
0x1800be1cc  mov     rcx, [r15]
0x1800be1cf  test    rcx, rcx
0x1800be1d2  jnz     loc_1800BE310
0x1800be1d8  lea     r15, [rsi+0B0h]
0x1800be1df  mov     rcx, [r15]
0x1800be1e2  test    rcx, rcx
0x1800be1e5  jnz     short loc_1800BE234
0x1800be1e7  lea     rdx, aTextured3d11Ge_3; "TextureD3D11::GetDeviceBuffer - No vali"...
0x1800be1ee  lea     rcx, [rbp+160h+var_E8]
0x1800be1f2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be1f7  nop
0x1800be1f8  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800be1ff  lea     rcx, [rbp+160h+var_110]
0x1800be203  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be208  mov     byte ptr [rsp+260h+var_240], r12b
0x1800be20d  lea     r9, [rbp+160h+var_E8]
0x1800be211  mov     rdx, rax
0x1800be214  lea     rcx, [rbp+160h+pExceptionObject]
0x1800be21b  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800be220  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800be227  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x1800be22e  call    _CxxThrowException_0
0x1800be234  xorps   xmm0, xmm0
0x1800be237  xor     eax, eax
0x1800be239  movups  [rbp+160h+var_110], xmm0
0x1800be23d  movups  [rbp+160h+var_100], xmm0
0x1800be241  mov     [rbp+160h+var_F0], eax
0x1800be244  mov     rax, [rcx]
0x1800be247  lea     rdx, [rbp+160h+var_110]
0x1800be24b  mov     rax, [rax+50h]
0x1800be24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be254  mov     qword ptr [rbp+160h+var_100+4], 3
0x1800be25c  mov     qword ptr [rbp+160h+var_100+0Ch], 20000h
0x1800be264  mov     [rsp+260h+var_220], r12
0x1800be269  mov     rdi, [rsp+260h+var_1F0]
0x1800be26e  mov     rax, [rdi]
0x1800be271  mov     rbx, [rax+30h]
0x1800be275  lea     rcx, [rsp+260h+var_220]
0x1800be27a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800be27f  lea     r9, [rsp+260h+var_220]
0x1800be284  xor     r8d, r8d
0x1800be287  lea     rdx, [rbp+160h+var_110]
0x1800be28b  mov     rcx, rdi
0x1800be28e  mov     rax, rbx
0x1800be291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be296  movsxd  rbx, eax
0x1800be299  mov     edx, ebx; int
0x1800be29b  mov     rcx, r13; this
0x1800be29e  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800be2a3  test    ebx, ebx
0x1800be2a5  jns     short loc_1800BE2E4
0x1800be2a7  xor     edx, edx; Val
0x1800be2a9  mov     r8d, 98h; Size
0x1800be2af  lea     rcx, [rbp+160h+pExceptionRecord]; void *
0x1800be2b3  call    memset_0
0x1800be2b8  mov     [rbp+160h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800be2bf  mov     rax, [rbp+168h]
0x1800be2c6  mov     [rbp+160h+pExceptionRecord.ExceptionAddress], rax
0x1800be2ca  mov     [rbp+160h+pExceptionRecord.NumberParameters], 1
0x1800be2d1  mov     [rbp+160h+pExceptionRecord.ExceptionInformation], rbx
0x1800be2d5  xor     r8d, r8d; dwFlags
0x1800be2d8  xor     edx, edx; pContextRecord
0x1800be2da  lea     rcx, [rbp+160h+pExceptionRecord]; pExceptionRecord
0x1800be2de  call    cs:__imp_RaiseFailFastException
0x1800be2e4  mov     rdx, r15
0x1800be2e7  lea     rcx, [rsp+260h+var_208]
0x1800be2ec  call    ??$?4UID3D11Texture3D@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UID3D11Texture3D@@@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(Microsoft::WRL::ComPtr<ID3D11Texture3D> const &)
0x1800be2f1  lea     rdx, [rsp+260h+var_220]
0x1800be2f6  lea     rcx, [rsp+260h+var_1F8]
0x1800be2fb  call    ??$?4UID3D11Texture3D@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UID3D11Texture3D@@@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(Microsoft::WRL::ComPtr<ID3D11Texture3D> const &)
0x1800be300  nop
0x1800be301  lea     rcx, [rsp+260h+var_220]
0x1800be306  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800be30b  jmp     loc_1800BE575
0x1800be310  xorps   xmm0, xmm0
0x1800be313  movups  [rbp+160h+pExceptionObject], xmm0
0x1800be31a  movups  [rbp+160h+var_B8], xmm0
0x1800be321  movups  [rbp+160h+var_B8+0Ch], xmm0
0x1800be328  mov     rax, [rcx]
0x1800be32b  lea     rdx, [rbp+160h+pExceptionObject]
0x1800be332  mov     rax, [rax+50h]
0x1800be336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be33b  mov     qword ptr [rbp+160h+var_B8+0Ch], 3
0x1800be346  mov     [rbp+160h+var_A4], 20000h
0x1800be351  mov     dword ptr [rbp+160h+pExceptionObject+0Ch], 1
0x1800be35b  mov     [rsp+260h+var_220], r12
0x1800be360  mov     rdi, [rsp+260h+var_1F0]
0x1800be365  mov     rax, [rdi]
0x1800be368  mov     rbx, [rax+28h]
0x1800be36c  lea     rcx, [rsp+260h+var_220]
0x1800be371  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800be376  lea     r9, [rsp+260h+var_220]
0x1800be37b  xor     r8d, r8d
0x1800be37e  lea     rdx, [rbp+160h+pExceptionObject]
0x1800be385  mov     rcx, rdi
0x1800be388  mov     rax, rbx
0x1800be38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be390  mov     edi, eax
0x1800be392  mov     edx, eax; int
0x1800be394  mov     rcx, r13; this
0x1800be397  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800be39c  test    edi, edi
0x1800be39e  jns     loc_1800BE547
0x1800be3a4  lea     rdx, aThrowIfFailedD; "THROW_IF_FAILED_DETAILED. "
0x1800be3ab  lea     rcx, [rbp+160h+var_110]
0x1800be3af  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be3b4  nop
0x1800be3b5  mov     ebx, 6
0x1800be3ba  mov     r8d, ebx
0x1800be3bd  lea     rdx, aFile_0; " File="
0x1800be3c4  lea     rcx, [rbp+160h+var_110]
0x1800be3c8  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be3cd  lea     r8d, [rbx+56h]
0x1800be3d1  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800be3d8  mov     rcx, rax
0x1800be3db  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be3e0  mov     r8d, ebx
0x1800be3e3  lea     rdx, aLine; " Line="
0x1800be3ea  lea     rcx, [rbp+160h+var_110]
0x1800be3ee  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be3f3  lea     r8d, [rbx-3]
0x1800be3f7  lea     rdx, a387; "387"
0x1800be3fe  mov     rcx, rax
0x1800be401  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be406  lea     esi, [rbx+3]
0x1800be409  mov     r8d, esi
0x1800be40c  lea     rdx, aMessage; " Message="
0x1800be413  lea     rcx, [rbp+160h+var_110]
0x1800be417  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be41c  lea     r8d, [rbx+3Ah]
0x1800be420  lea     rdx, aTextured3d11Ge_0; "\"TextureD3D11::GetDeviceBuffer(): unab"...
0x1800be427  mov     rcx, rax
0x1800be42a  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be42f  lea     r8d, [rbx+4]
0x1800be433  lea     rdx, aDetails; " Details=\""
0x1800be43a  lea     rcx, [rbp+160h+var_110]
0x1800be43e  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be443  mov     rbx, rax
0x1800be446  lea     rcx, [rbp+160h+var_E8]; void *
0x1800be44a  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x1800be44f  nop
0x1800be450  lea     r8, [rbp+160h+var_E8]
0x1800be454  lea     rdx, [rbp+160h+pExceptionObject]
0x1800be45b  lea     rcx, [rbp+160h+var_90]
0x1800be462  call    ?ToString@ExceptionDetails@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUD3D11_TEXTURE2D_DESC@@AEBV?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@3@@Z; ExceptionDetails::ToString(D3D11_TEXTURE2D_DESC const &,std::vector<D3D11_SUBRESOURCE_DATA> const &)
0x1800be467  nop
0x1800be468  mov     rdx, rax
0x1800be46b  mov     rcx, rbx
0x1800be46e  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@@Z; std::string::append(std::string const &)
0x1800be473  lea     r8d, [rsi-8]
0x1800be477  lea     rdx, asc_180176544; "\""
0x1800be47e  mov     rcx, rax
0x1800be481  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be486  nop
0x1800be487  lea     rcx, [rbp+160h+var_90]
0x1800be48e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800be493  nop
0x1800be494  mov     rcx, qword ptr [rbp+160h+var_E8]
0x1800be498  test    rcx, rcx
0x1800be49b  jz      short loc_1800BE4B0
0x1800be49d  mov     rdx, [rbp+160h+var_D8]
0x1800be4a4  sub     rdx, rcx
0x1800be4a7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800be4ab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800be4b0  mov     r8, rsi
0x1800be4b3  lea     rdx, aHresult; " HRESULT="
0x1800be4ba  lea     rcx, [rbp+160h+var_110]
0x1800be4be  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800be4c3  mov     rbx, rax
0x1800be4c6  mov     edx, edi
0x1800be4c8  lea     rcx, [rbp+160h+var_E8]
0x1800be4cc  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@J@Z; std::to_string(long)
0x1800be4d1  nop
0x1800be4d2  mov     rdx, rax
0x1800be4d5  mov     rcx, rbx
0x1800be4d8  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@@Z; std::string::append(std::string const &)
0x1800be4dd  nop
0x1800be4de  lea     rcx, [rbp+160h+var_E8]
0x1800be4e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800be4e7  lea     rcx, [rbp+160h+var_110]
0x1800be4eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800be4f0  mov     rdx, rax
0x1800be4f3  lea     rcx, [rbp+160h+var_90]
0x1800be4fa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be4ff  nop
0x1800be500  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800be507  lea     rcx, [rbp+160h+var_E8]
0x1800be50b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800be510  mov     byte ptr [rsp+260h+var_238], r12b
0x1800be515  lea     rcx, [rbp+160h+var_90]
0x1800be51c  mov     [rsp+260h+var_240], rcx
0x1800be521  mov     r9d, edi
0x1800be524  mov     rdx, rax
0x1800be527  lea     rcx, [rbp+160h+var_70]
0x1800be52e  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HJAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,long,std::string const &,bool)
0x1800be533  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800be53a  lea     rcx, [rbp+160h+var_70]; pExceptionObject
0x1800be541  call    _CxxThrowException_0
0x1800be547  mov     rdx, r15
0x1800be54a  lea     rcx, [rsp+260h+var_208]
0x1800be54f  call    ??$?4UID3D11Texture3D@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UID3D11Texture3D@@@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(Microsoft::WRL::ComPtr<ID3D11Texture3D> const &)
0x1800be554  lea     rdx, [rsp+260h+var_220]
0x1800be559  lea     rcx, [rsp+260h+var_1F8]
0x1800be55e  call    ??$?4UID3D11Texture3D@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UID3D11Texture3D@@@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::operator=<ID3D11Texture3D>(Microsoft::WRL::ComPtr<ID3D11Texture3D> const &)
0x1800be563  nop
0x1800be564  lea     rcx, [rsp+260h+var_220]
0x1800be569  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800be56e  lea     r15, [rsi+0B0h]
0x1800be575  mov     rbx, [rbp+160h+var_1E0]
0x1800be579  mov     rax, [rbx]
0x1800be57c  mov     r8, [rsp+260h+var_208]
0x1800be581  mov     r12, [rsp+260h+var_1F8]
0x1800be586  mov     rdx, r12
0x1800be589  mov     rcx, rbx
0x1800be58c  mov     rax, [rax+178h]
0x1800be593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be598  xorps   xmm0, xmm0
0x1800be59b  movups  xmmword ptr [rbp+160h+Src], xmm0
0x1800be59f  mov     rax, [rbx]
0x1800be5a2  lea     rcx, [rbp+160h+Src]
0x1800be5a6  mov     [rsp+260h+var_238], rcx
0x1800be5ab  mov     dword ptr [rsp+260h+var_240], 0
0x1800be5b3  mov     r9d, 1
  ... truncated ...
```
