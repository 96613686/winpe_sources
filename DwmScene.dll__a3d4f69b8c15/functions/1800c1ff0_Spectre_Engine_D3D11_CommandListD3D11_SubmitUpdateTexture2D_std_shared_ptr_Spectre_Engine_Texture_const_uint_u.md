# Spectre::Engine::D3D11::CommandListD3D11::SubmitUpdateTexture2D(std::shared_ptr<Spectre::Engine::Texture> const &,uint,uint,uint,uint,void const *,uint,uint,uint,uint)

- ea: `0x1800c1ff0`
- end: `0x1800c250a`
- name: `?SubmitUpdateTexture2D@CommandListD3D11@D3D11@Engine@Spectre@@MEAA_NAEBV?$shared_ptr@VTexture@Engine@Spectre@@@std@@IIIIPEBXIIII@Z`
- size: `1306`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000fe40`
- `0x18001128c`
- `0x1800117b0`
- `0x180011f64`
- `0x180012c58`
- `0x18001daf4`
- `0x18004574c`
- `0x18005225c`
- `0x1800522b8`
- `0x180052420`
- `0x1800681a8`
- `0x1800b7e3c`
- `0x1800bea74`
- `0x1800bedf4`
- `0x1800bf1d4`
- `0x1800bf248`
- `0x1800c1ff0`
- `0x1800e7010`

## string_xrefs

- `0x1800c210d`: `UpdateTexture2D can only be used with 2D textures`
- `0x1800c211e`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c217f`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c21dd`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c2246`: `onecoreuap\windows\dwm\spectre\engine\shared\nativerendererd3d11\cpp\source\commandlistd3d11.cpp`
- `0x1800c2235`: `UpdateTexture2D: Src rectangle exceeds the size of the data buffer`
- `0x1800c2499`: `Failed to update Texture2D with HRESULT error 0x%.8x`
- `0x1800c216e`: `UpdateTexture2D can only be used with a valid ID3D11Texture2D interface pointer`
- `0x1800c21cc`: `UpdateTexture2D: Src X/Y offset exceeds the size of the data buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Spectre::Engine::D3D11::CommandListD3D11::SubmitUpdateTexture2D(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        int a11)
{
  __int64 *DeviceTexture; // rax
  char v12; // bl
  __int64 v13; // rcx
  std::_Ref_count_base *v14; // r14
  __int64 v15; // r13
  unsigned int Format; // eax
  int FormatPitch; // edi
  __int64 v18; // rcx
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rbx
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // r15d
  unsigned int v25; // r12d
  int v26; // eax
  int v27; // r8d
  int v28; // eax
  int v29; // r8d
  __int64 v30; // rdi
  __int64 v31; // rbx
  int v32; // esi
  char *v33; // rdi
  char *v34; // rsi
  unsigned int v35; // r15d
  rsize_t v36; // r12
  __int64 v37; // r13
  __int64 v38; // rdi
  __int64 v39; // rsi
  void (__fastcall *v40)(__int64, _QWORD, _QWORD, _QWORD, int, _DWORD, __int64, _DWORD, __int128 *); // rdi
  _QWORD *Texture; // rax
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A8h]
  unsigned int v45; // [rsp+5Ch] [rbp-A4h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v47; // [rsp+68h] [rbp-98h]
  int v48; // [rsp+6Ch] [rbp-94h]
  int v49; // [rsp+70h] [rbp-90h]
  int v50; // [rsp+74h] [rbp-8Ch]
  unsigned int v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v53; // [rsp+88h] [rbp-78h]
  void *Destination[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  _QWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v57; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v58; // [rsp+C0h] [rbp-40h]
  std::_Ref_count_base *v59[2]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v60[28]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v61; // [rsp+108h] [rbp+8h] BYREF
  __int64 v62; // [rsp+118h] [rbp+18h]
  _BYTE pExceptionObject[56]; // [rsp+120h] [rbp+20h] BYREF

  v50 = a4;
  v51 = a3;
  v55 = a1;
  v45 = a6;
  v44 = a5;
  v43 = a7;
  v47 = a9;
  LODWORD(v46) = a10;
  v49 = a11;
  v48 = 0;
  if ( *a2 )
  {
    DeviceTexture = (__int64 *)Spectre::Engine::Texture::GetDeviceTexture(*a2, v59, *(unsigned int *)(a1 + 88));
    v12 = 1;
    v13 = *DeviceTexture;
  }
  else
  {
    v53 = 0;
    DeviceTexture = &v52;
    v12 = 2;
    v13 = 0;
  }
  v56[0] = v13;
  v14 = (std::_Ref_count_base *)DeviceTexture[1];
  v56[1] = v14;
  *DeviceTexture = 0;
  DeviceTexture[1] = 0;
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
  }
  if ( (v12 & 1) != 0 && v59[1] )
    std::_Ref_count_base::_Decref(v59[1]);
  std::dynamic_pointer_cast<Spectre::Engine::D3D11::TextureD3D11,Spectre::Engine::DeviceTexture>(&v52, v56);
  v15 = v52;
  Format = Spectre::Engine::DeviceTexture::GetFormat(v52);
  FormatPitch = Spectre::Engine::GetFormatPitch(Format);
  v48 = FormatPitch;
  if ( (unsigned int)Spectre::Engine::DeviceTexture::GetTextureType(v15) != 1 )
  {
    std::string::string(&v57, "UpdateTexture2D can only be used with 2D textures");
    v19 = std::string::string(
            v59,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v19, v20, (unsigned int)&v57, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v21 = *(_QWORD *)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v18, &v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  if ( !v21 )
  {
    std::string::string(&v57, "UpdateTexture2D can only be used with a valid ID3D11Texture2D interface pointer");
    v22 = std::string::string(
            v59,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v22, v23, (unsigned int)&v57, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v24 = FormatPitch * a10;
  v25 = v47 * a11;
  if ( v47 * a11 + FormatPitch * a10 >= a8 )
  {
    std::string::string(&v57, "UpdateTexture2D: Src X/Y offset exceeds the size of the data buffer");
    v26 = std::string::string(
            v59,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v26, v27, (unsigned int)&v57, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( FormatPitch * (v44 + (_DWORD)v46) + v47 * (a6 + v49 - 1) > a8 )
  {
    std::string::string(&v57, "UpdateTexture2D: Src rectangle exceeds the size of the data buffer");
    v28 = std::string::string(
            v59,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\commandlistd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v28, v29, (unsigned int)&v57, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  Spectre::Engine::D3D11::TextureD3D11::GetOrCreateCPUStagingTexture(v15, &v46, v44, a6);
  *(_OWORD *)Destination = 0;
  v30 = v55;
  v31 = v46;
  v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, void **))(**(_QWORD **)(v55 + 144) + 112LL))(
          *(_QWORD *)(v55 + 144),
          v46,
          0,
          4,
          0,
          Destination);
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v30 + 72, v59);
  std::dynamic_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(&v57, v59);
  if ( v59[1] )
    std::_Ref_count_base::_Decref(v59[1]);
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v57, v32);
  if ( v32 >= 0 && (v33 = (char *)Destination[0]) != 0 )
  {
    if ( !LODWORD(Destination[1]) )
    {
      *(_OWORD *)v59 = 0;
      memset(v60, 0, sizeof(v60));
      (*(void (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)v31 + 80LL))(v31, v59);
      LODWORD(Destination[1]) = 4 * LODWORD(v59[0]);
      v33 = (char *)Destination[0];
    }
    v34 = (char *)(v43 + v25 + v24);
    v61 = 0;
    v62 = 0;
    v35 = 0;
    if ( v45 )
    {
      v36 = v48 * v44;
      v37 = v47;
      do
      {
        memcpy_s(v33, v36, v34, v36);
        v33 += LODWORD(Destination[1]);
        v34 += v37;
        ++v35;
      }
      while ( v35 < v45 );
      v31 = v46;
      v15 = v52;
    }
    v38 = v55;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v55 + 144) + 120LL))(*(_QWORD *)(v55 + 144), v31, 0);
    *(_QWORD *)&v61 = 0;
    HIDWORD(v61) = v44;
    v62 = v45 | 0x100000000LL;
    DWORD2(v61) = 0;
    v39 = *(_QWORD *)(v38 + 144);
    v40 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, _DWORD, __int64, _DWORD, __int128 *))(*(_QWORD *)v39 + 368LL);
    Texture = (_QWORD *)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v15, &v43);
    v40(v39, *Texture, 0, v51, v50, 0, v31, 0, &v61);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    if ( v58 )
      std::_Ref_count_base::_Decref(v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    return 1;
  }
  else
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsCommandListD3D11,
      3,
      "Failed to update Texture2D with HRESULT error 0x%.8x",
      v32);
    if ( v58 )
      std::_Ref_count_base::_Decref(v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    return 0;
  }
}

```

## disassembly

```asm
0x1800c1ff0  push    rbp
0x1800c1ff2  push    rbx
0x1800c1ff3  push    rsi
0x1800c1ff4  push    rdi
0x1800c1ff5  push    r12
0x1800c1ff7  push    r13
0x1800c1ff9  push    r14
0x1800c1ffb  push    r15
0x1800c1ffd  lea     rbp, [rsp-68h]
0x1800c2002  sub     rsp, 168h
0x1800c2009  mov     rax, cs:__security_cookie
0x1800c2010  xor     rax, rsp
0x1800c2013  mov     [rbp+0A0h+var_48], rax
0x1800c2017  mov     [rsp+1A0h+var_12C], r9d
0x1800c201c  mov     [rsp+1A0h+var_128], r8d
0x1800c2021  mov     r8, rcx
0x1800c2024  mov     [rbp+0A0h+var_100], rcx
0x1800c2028  mov     esi, [rbp+0A0h+arg_28]
0x1800c202e  mov     [rsp+1A0h+var_144], esi
0x1800c2032  mov     eax, [rbp+0A0h+arg_20]
0x1800c2038  mov     [rsp+1A0h+var_148], eax
0x1800c203c  mov     rax, [rbp+0A0h+arg_30]
0x1800c2043  mov     [rsp+1A0h+var_150], rax
0x1800c2048  mov     eax, [rbp+0A0h+arg_40]
0x1800c204e  mov     [rsp+1A0h+var_138], eax
0x1800c2052  mov     r15d, [rbp+0A0h+arg_48]
0x1800c2059  mov     dword ptr [rsp+1A0h+var_140], r15d
0x1800c205e  mov     r12d, [rbp+0A0h+arg_50]
0x1800c2065  mov     [rsp+1A0h+var_130], r12d
0x1800c206a  xor     edi, edi
0x1800c206c  mov     [rsp+1A0h+var_134], edi
0x1800c2070  mov     rcx, [rdx]
0x1800c2073  test    rcx, rcx
0x1800c2076  jz      short loc_1800C208D
0x1800c2078  mov     r8d, [r8+58h]
0x1800c207c  lea     rdx, [rbp+0A0h+var_C8]
0x1800c2080  call    ?GetDeviceTexture@Texture@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@W4RenderDeviceID@23@@Z; Spectre::Engine::Texture::GetDeviceTexture(Spectre::Engine::RenderDeviceID)
0x1800c2085  lea     ebx, [rdi+1]
0x1800c2088  mov     rcx, [rax]
0x1800c208b  jmp     short loc_1800C209D
0x1800c208d  mov     [rbp+0A0h+var_118], rdi
0x1800c2091  lea     rax, [rbp+0A0h+var_120]
0x1800c2095  mov     ebx, 2
0x1800c209a  mov     rcx, rdi
0x1800c209d  mov     [rbp+0A0h+var_F8], rcx
0x1800c20a1  mov     r14, [rax+8]
0x1800c20a5  mov     [rbp+0A0h+var_F0], r14
0x1800c20a9  mov     [rax], rdi
0x1800c20ac  mov     [rax+8], rdi
0x1800c20b0  test    bl, 2
0x1800c20b3  jz      short loc_1800C20C6
0x1800c20b5  and     ebx, 0FFFFFFFDh
0x1800c20b8  mov     rcx, [rbp+0A0h+var_118]; this
0x1800c20bc  test    rcx, rcx
0x1800c20bf  jz      short loc_1800C20C6
0x1800c20c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c20c6  test    bl, 1
0x1800c20c9  jz      short loc_1800C20D9
0x1800c20cb  mov     rcx, [rbp+0A0h+var_C8+8]; this
0x1800c20cf  test    rcx, rcx
0x1800c20d2  jz      short loc_1800C20D9
0x1800c20d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c20d9  lea     rdx, [rbp+0A0h+var_F8]
0x1800c20dd  lea     rcx, [rbp+0A0h+var_120]
0x1800c20e1  call    ??$dynamic_pointer_cast@VTextureD3D11@D3D11@Engine@Spectre@@VDeviceTexture@34@@std@@YA?AV?$shared_ptr@VTextureD3D11@D3D11@Engine@Spectre@@@0@AEBV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@0@@Z; std::dynamic_pointer_cast<Spectre::Engine::D3D11::TextureD3D11,Spectre::Engine::DeviceTexture>(std::shared_ptr<Spectre::Engine::DeviceTexture> const &)
0x1800c20e6  nop
0x1800c20e7  mov     r13, [rbp+0A0h+var_120]
0x1800c20eb  mov     rcx, r13
0x1800c20ee  call    ?GetFormat@DeviceTexture@Engine@Spectre@@QEBA?AW4Format@23@XZ; Spectre::Engine::DeviceTexture::GetFormat(void)
0x1800c20f3  mov     ecx, eax
0x1800c20f5  call    Spectre__Engine__GetFormatPitch
0x1800c20fa  mov     edi, eax
0x1800c20fc  mov     [rsp+1A0h+var_134], eax
0x1800c2100  mov     rcx, r13
0x1800c2103  call    ?GetTextureType@DeviceTexture@Engine@Spectre@@QEBA?AW4TextureType@23@XZ; Spectre::Engine::DeviceTexture::GetTextureType(void)
0x1800c2108  cmp     eax, 1
0x1800c210b  jz      short loc_1800C2154
0x1800c210d  lea     rdx, aUpdatetexture2; "UpdateTexture2D can only be used with 2"...
0x1800c2114  lea     rcx, [rbp+0A0h+var_E8]
0x1800c2118  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c211d  nop
0x1800c211e  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c2125  lea     rcx, [rbp+0A0h+var_C8]
0x1800c2129  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c212e  mov     byte ptr [rsp+1A0h+var_180], 0
0x1800c2133  lea     r9, [rbp+0A0h+var_E8]
0x1800c2137  mov     rdx, rax
0x1800c213a  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800c213e  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c2143  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c214a  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800c214e  call    _CxxThrowException_0
0x1800c2154  lea     rdx, [rbp+0A0h+var_E8]
0x1800c2158  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x1800c215d  mov     rbx, [rax]
0x1800c2160  lea     rcx, [rbp+0A0h+var_E8]
0x1800c2164  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2169  test    rbx, rbx
0x1800c216c  jnz     short loc_1800C21B4
0x1800c216e  lea     rdx, aUpdatetexture2_1; "UpdateTexture2D can only be used with a"...
0x1800c2175  lea     rcx, [rbp+0A0h+var_E8]
0x1800c2179  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c217e  nop
0x1800c217f  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c2186  lea     rcx, [rbp+0A0h+var_C8]
0x1800c218a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c218f  mov     byte ptr [rsp+1A0h+var_180], bl
0x1800c2193  lea     r9, [rbp+0A0h+var_E8]
0x1800c2197  mov     rdx, rax
0x1800c219a  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800c219e  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c21a3  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c21aa  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800c21ae  call    _CxxThrowException_0
0x1800c21b4  imul    r15d, edi
0x1800c21b8  mov     edx, [rsp+1A0h+var_138]
0x1800c21bc  imul    r12d, edx
0x1800c21c0  lea     eax, [r12+r15]
0x1800c21c4  cmp     eax, [rbp+0A0h+arg_38]
0x1800c21ca  jb      short loc_1800C2213
0x1800c21cc  lea     rdx, aUpdatetexture2_0; "UpdateTexture2D: Src X/Y offset exceeds"...
0x1800c21d3  lea     rcx, [rbp+0A0h+var_E8]
0x1800c21d7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c21dc  nop
0x1800c21dd  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c21e4  lea     rcx, [rbp+0A0h+var_C8]
0x1800c21e8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c21ed  mov     byte ptr [rsp+1A0h+var_180], 0
0x1800c21f2  lea     r9, [rbp+0A0h+var_E8]
0x1800c21f6  mov     rdx, rax
0x1800c21f9  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800c21fd  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c2202  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c2209  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800c220d  call    _CxxThrowException_0
0x1800c2213  mov     ecx, [rsp+1A0h+var_130]
0x1800c2217  dec     ecx
0x1800c2219  add     ecx, esi
0x1800c221b  imul    ecx, edx
0x1800c221e  mov     eax, dword ptr [rsp+1A0h+var_140]
0x1800c2222  mov     edx, [rsp+1A0h+var_148]
0x1800c2226  add     eax, edx
0x1800c2228  imul    eax, edi
0x1800c222b  add     ecx, eax
0x1800c222d  cmp     ecx, [rbp+0A0h+arg_38]
0x1800c2233  jbe     short loc_1800C227C
0x1800c2235  lea     rdx, aUpdatetexture2_2; "UpdateTexture2D: Src rectangle exceeds "...
0x1800c223c  lea     rcx, [rbp+0A0h+var_E8]
0x1800c2240  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c2245  nop
0x1800c2246  lea     rdx, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c224d  lea     rcx, [rbp+0A0h+var_C8]
0x1800c2251  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c2256  mov     byte ptr [rsp+1A0h+var_180], 0
0x1800c225b  lea     r9, [rbp+0A0h+var_E8]
0x1800c225f  mov     rdx, rax
0x1800c2262  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800c2266  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800c226b  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800c2272  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800c2276  call    _CxxThrowException_0
0x1800c227c  mov     r9d, esi
0x1800c227f  mov     r8d, edx
0x1800c2282  lea     rdx, [rsp+1A0h+var_140]
0x1800c2287  mov     rcx, r13
0x1800c228a  call    ?GetOrCreateCPUStagingTexture@TextureD3D11@D3D11@Engine@Spectre@@QEAA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@II@Z; Spectre::Engine::D3D11::TextureD3D11::GetOrCreateCPUStagingTexture(uint,uint)
0x1800c228f  nop
0x1800c2290  xorps   xmm0, xmm0
0x1800c2293  movups  xmmword ptr [rbp+0A0h+Destination], xmm0
0x1800c2297  mov     rdi, [rbp+0A0h+var_100]
0x1800c229b  mov     rcx, [rdi+90h]
0x1800c22a2  mov     rax, [rcx]
0x1800c22a5  lea     rdx, [rbp+0A0h+Destination]
0x1800c22a9  mov     [rsp+1A0h+var_178], rdx
0x1800c22ae  mov     [rsp+1A0h+var_180], 0
0x1800c22b6  mov     r9d, 4
0x1800c22bc  xor     r8d, r8d
0x1800c22bf  mov     rbx, [rsp+1A0h+var_140]
0x1800c22c4  mov     rdx, rbx
0x1800c22c7  mov     rax, [rax+70h]
0x1800c22cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c22d0  mov     esi, eax
0x1800c22d2  lea     rcx, [rdi+48h]
0x1800c22d6  lea     rdx, [rbp+0A0h+var_C8]
0x1800c22da  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800c22df  lea     rdx, [rbp+0A0h+var_C8]
0x1800c22e3  lea     rcx, [rbp+0A0h+var_E8]
0x1800c22e7  call    ??$dynamic_pointer_cast@VRenderDeviceD3D11@D3D11@Engine@Spectre@@VRenderDevice@34@@std@@YA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@0@$$QEAV?$shared_ptr@VRenderDevice@Engine@Spectre@@@0@@Z; std::dynamic_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(std::shared_ptr<Spectre::Engine::RenderDevice> &&)
0x1800c22ec  nop
0x1800c22ed  mov     rcx, [rbp+0A0h+var_C8+8]; this
0x1800c22f1  test    rcx, rcx
0x1800c22f4  jz      short loc_1800C22FB
0x1800c22f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c22fb  mov     edx, esi; int
0x1800c22fd  mov     rcx, [rbp+0A0h+var_E8]; this
0x1800c2301  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800c2306  test    esi, esi
0x1800c2308  js      loc_1800C2496
0x1800c230e  mov     rdi, [rbp+0A0h+Destination]
0x1800c2312  test    rdi, rdi
0x1800c2315  jz      loc_1800C2496
0x1800c231b  cmp     dword ptr [rbp+0A0h+Destination+8], 0
0x1800c231f  jnz     short loc_1800C2350
0x1800c2321  xorps   xmm0, xmm0
0x1800c2324  movups  xmmword ptr [rbp+0A0h+var_C8], xmm0
0x1800c2328  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x1800c232c  movups  xmmword ptr [rbp+0A0h+var_B8+0Ch], xmm0
0x1800c2330  mov     rax, [rbx]
0x1800c2333  lea     rdx, [rbp+0A0h+var_C8]
0x1800c2337  mov     rcx, rbx
0x1800c233a  mov     rax, [rax+50h]
0x1800c233e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2343  mov     eax, dword ptr [rbp+0A0h+var_C8]
0x1800c2346  shl     eax, 2
0x1800c2349  mov     dword ptr [rbp+0A0h+Destination+8], eax
0x1800c234c  mov     rdi, [rbp+0A0h+Destination]
0x1800c2350  mov     eax, r12d
0x1800c2353  mov     esi, r15d
0x1800c2356  add     rax, [rsp+1A0h+var_150]
0x1800c235b  add     rsi, rax
0x1800c235e  mov     eax, [rsp+1A0h+var_148]
0x1800c2362  imul    eax, [rsp+1A0h+var_134]
0x1800c2367  xorps   xmm0, xmm0
0x1800c236a  xor     ecx, ecx
0x1800c236c  movups  [rbp+0A0h+var_98], xmm0
0x1800c2370  mov     [rbp+0A0h+var_88], rcx
0x1800c2374  xor     r12d, r12d
0x1800c2377  mov     r15d, r12d
0x1800c237a  cmp     [rsp+1A0h+var_144], r12d
0x1800c237f  jbe     short loc_1800C23BD
0x1800c2381  mov     r12d, eax
0x1800c2384  mov     eax, [rsp+1A0h+var_138]
0x1800c2388  mov     r13d, eax
0x1800c238b  mov     ebx, [rsp+1A0h+var_144]
0x1800c238f  mov     r9, r12; SourceSize
0x1800c2392  mov     r8, rsi; Source
0x1800c2395  mov     rdx, r12; DestinationSize
0x1800c2398  mov     rcx, rdi; Destination
0x1800c239b  call    memcpy_s
0x1800c23a0  mov     eax, dword ptr [rbp+0A0h+Destination+8]
0x1800c23a3  add     rdi, rax
0x1800c23a6  add     rsi, r13
0x1800c23a9  inc     r15d
0x1800c23ac  cmp     r15d, ebx
0x1800c23af  jb      short loc_1800C238F
0x1800c23b1  mov     rbx, [rsp+1A0h+var_140]
0x1800c23b6  mov     r13, [rbp+0A0h+var_120]
0x1800c23ba  xor     r12d, r12d
0x1800c23bd  mov     rdi, [rbp+0A0h+var_100]
0x1800c23c1  mov     rcx, [rdi+90h]
0x1800c23c8  mov     rax, [rcx]
0x1800c23cb  xor     r8d, r8d
0x1800c23ce  mov     rdx, rbx
0x1800c23d1  mov     rax, [rax+78h]
0x1800c23d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c23da  mov     qword ptr [rbp+0A0h+var_98], 0
0x1800c23e2  mov     eax, [rsp+1A0h+var_148]
0x1800c23e6  mov     dword ptr [rbp+0A0h+var_98+0Ch], eax
0x1800c23e9  mov     eax, [rsp+1A0h+var_144]
0x1800c23ed  mov     dword ptr [rbp+0A0h+var_88], eax
0x1800c23f0  mov     dword ptr [rbp+0A0h+var_98+8], r12d
0x1800c23f4  mov     dword ptr [rbp+0A0h+var_88+4], 1
0x1800c23fb  mov     rsi, [rdi+90h]
0x1800c2402  mov     rax, [rsi]
0x1800c2405  mov     rdi, [rax+170h]
0x1800c240c  lea     rdx, [rsp+1A0h+var_150]
0x1800c2411  mov     rcx, r13
0x1800c2414  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x1800c2419  nop
0x1800c241a  lea     rcx, [rbp+0A0h+var_98]
0x1800c241e  mov     [rsp+1A0h+var_160], rcx
0x1800c2423  mov     [rsp+1A0h+var_168], r12d
0x1800c2428  mov     [rsp+1A0h+var_170], rbx
0x1800c242d  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800c2432  mov     ecx, [rsp+1A0h+var_12C]
0x1800c2436  mov     [rsp+1A0h+var_180], ecx
0x1800c243a  mov     r9d, [rsp+1A0h+var_128]
0x1800c243f  xor     r8d, r8d
0x1800c2442  mov     rdx, [rax]
0x1800c2445  mov     rcx, rsi
0x1800c2448  mov     rax, rdi
0x1800c244b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2450  nop
0x1800c2451  lea     rcx, [rsp+1A0h+var_150]
0x1800c2456  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c245b  nop
0x1800c245c  mov     rcx, [rbp+0A0h+var_E0]; this
0x1800c2460  test    rcx, rcx
0x1800c2463  jz      short loc_1800C246B
0x1800c2465  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c246a  nop
0x1800c246b  lea     rcx, [rsp+1A0h+var_140]
0x1800c2470  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2475  nop
0x1800c2476  mov     rcx, [rbp+0A0h+var_118]; this
0x1800c247a  test    rcx, rcx
0x1800c247d  jz      short loc_1800C2485
0x1800c247f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2484  nop
0x1800c2485  test    r14, r14
  ... truncated ...
```
