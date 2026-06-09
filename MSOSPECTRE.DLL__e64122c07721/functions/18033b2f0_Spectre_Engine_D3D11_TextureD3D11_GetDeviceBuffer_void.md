# Spectre::Engine::D3D11::TextureD3D11::GetDeviceBuffer(void)

- ea: `0x18033b2f0`
- end: `0x18033be23`
- name: `?GetDeviceBuffer@TextureD3D11@D3D11@Engine@Spectre@@UEBA?AUTextureImageSet@34@XZ`
- size: `2867`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180014b80`
- `0x180015730`
- `0x180015740`
- `0x180015770`
- `0x18002a178`
- `0x1801872c0`
- `0x1801cf670`
- `0x1801fd490`
- `0x18021e120`
- `0x180277d80`
- `0x180277e30`
- `0x180280a80`
- `0x180283510`
- `0x180283530`
- `0x180283680`
- `0x180283700`
- `0x180320740`
- `0x180320770`
- `0x180323750`
- `0x18033b2f0`
- `0x18033c620`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039ebc0`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18033b884`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18033b884`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18033b745`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18033b745`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18033b751`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18033b751`

## string_xrefs

- `0x18033baa2`: `TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for cubemaps`
- `0x18033bb45`: `TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for MSAA textures`
- `0x18033bc03`: `"TextureD3D11::GetDeviceBuffer(): unable to create texture (2D)"`
- `0x18033bd7e`: `"TextureD3D11::GetDeviceBuffer(): unable to create texture (3D)"`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
_QWORD *__fastcall Spectre::Engine::D3D11::TextureD3D11::GetDeviceBuffer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  _DWORD *v5; // rax
  __int64 v6; // rdx
  signed __int32 v7; // eax
  signed __int32 v8; // ett
  volatile signed __int32 *v9; // r15
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rcx
  int v16; // edi
  int v17; // esi
  int Format; // eax
  unsigned int v19; // r13d
  int Height; // r14d
  unsigned int Width; // esi
  unsigned int v22; // eax
  unsigned __int64 v23; // r14
  _DWORD *v24; // rax
  _DWORD *v25; // rsi
  _OWORD *v26; // rax
  _QWORD *v27; // rsi
  __int64 v28; // rax
  void *v29; // rax
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v33; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rax
  const char *v40; // rax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  const char *v53; // rax
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rax
  const char *v60; // rax
  int v61; // eax
  __int64 v62[2]; // [rsp+40h] [rbp-C0h] BYREF
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v63[2]; // [rsp+50h] [rbp-B0h]
  _DWORD *v64; // [rsp+60h] [rbp-A0h]
  _QWORD *v65; // [rsp+68h] [rbp-98h]
  int v66; // [rsp+70h] [rbp-90h] BYREF
  void **v67; // [rsp+78h] [rbp-88h]
  __int64 v68; // [rsp+80h] [rbp-80h]
  void *Block[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+98h] [rbp-68h]
  __int64 v71; // [rsp+A0h] [rbp-60h]
  __int128 v72; // [rsp+B0h] [rbp-50h]
  __int128 v73; // [rsp+C0h] [rbp-40h]
  _BYTE v74[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v75[32]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v76[3]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v77[40]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v78[64]; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v79; // [rsp+190h] [rbp+90h]
  __int128 v80; // [rsp+1A0h] [rbp+A0h]
  __int128 v81; // [rsp+1B0h] [rbp+B0h]
  __int128 v82; // [rsp+1C0h] [rbp+C0h]
  _BYTE pExceptionObject[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v84; // [rsp+210h] [rbp+110h]
  _BYTE v85[32]; // [rsp+220h] [rbp+120h] BYREF
  void *Src[2]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v87; // [rsp+250h] [rbp+150h] BYREF
  __int64 v88; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v89[32]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v90; // [rsp+280h] [rbp+180h] BYREF
  __int64 v91; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v92[12]; // [rsp+290h] [rbp+190h] BYREF
  int v93; // [rsp+29Ch] [rbp+19Ch]
  __int64 v94; // [rsp+2ACh] [rbp+1ACh]
  __int64 v95; // [rsp+2B4h] [rbp+1B4h]
  _BYTE v96[20]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v97; // [rsp+2D4h] [rbp+1D4h]
  __int64 v98; // [rsp+2DCh] [rbp+1DCh]

  v65 = (_QWORD *)a2;
  v64 = (_DWORD *)a2;
  v4 = *(_QWORD *)(a1 + 104);
  if ( v4 )
  {
    v5 = *(_DWORD **)v4;
    v64 = v5;
    if ( v5 && (v5[5] & 0x10) != 0 )
    {
      std::string::string(
        v75,
        "TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for cubemaps");
      v42 = std::string::string(v89, "..\\Source\\TextureD3D11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)v78, v42, 350, (unsigned int)v75, 0);
      throw (Spectre::Engine::EngineException *)v78;
    }
  }
  else
  {
    v64 = 0;
  }
  if ( *(_DWORD *)(v4 + 12) > 1u )
  {
    std::string::string(
      v75,
      "TextureD3D11::GetDeviceBuffer() -- reading of texture data is not supported for MSAA textures");
    v44 = std::string::string(v89, "..\\Source\\TextureD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)v78, v44, 355, (unsigned int)v75, 0);
    throw (Spectre::Engine::EngineException *)v78;
  }
  v80 = 0;
  *(_OWORD *)v63 = 0;
  v6 = *(_QWORD *)(a1 + 72);
  if ( !v6 )
    goto LABEL_14;
  v7 = *(_DWORD *)(v6 + 8);
  if ( !v7 )
    goto LABEL_14;
  while ( 1 )
  {
    v8 = v7;
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 8), v7 + 1, v7);
    if ( v8 == v7 )
      break;
    if ( !v7 )
      goto LABEL_14;
  }
  v63[0] = *(Spectre::Engine::D3D11::RenderDeviceD3D11 **)(a1 + 64);
  v9 = *(volatile signed __int32 **)(a1 + 72);
  v63[1] = (Spectre::Engine::D3D11::RenderDeviceD3D11 *)v9;
  if ( v9 )
  {
    _InterlockedIncrement(v9 + 2);
LABEL_14:
    v9 = (volatile signed __int32 *)v63[1];
  }
  v80 = *(_OWORD *)v63;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1
      && ((**(void (__fastcall ***)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))v63[1])(v63[1]),
          _InterlockedExchangeAdd((volatile signed __int32 *)v63[1] + 3, 0xFFFFFFFF) == 1) )
    {
      v9 = (volatile signed __int32 *)v63[1];
      (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))(*(_QWORD *)v63[1] + 8LL))(v63[1]);
    }
    else
    {
      v9 = (volatile signed __int32 *)v63[1];
    }
  }
  v88 = 0;
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v63[0], &v88, a3);
  v87 = 0;
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDeviceContext(v63[0], &v87);
  v71 = 0;
  v68 = 0;
  v10 = *(_QWORD *)(a1 + 160);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 80LL))(v10, v92);
    v94 = 3;
    v95 = 0x20000;
    v93 = 1;
    v90 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int64 *))(*(_QWORD *)v88 + 40LL))(v88, v92, 0, &v90);
    Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v63[0], v11);
    if ( v11 < 0 )
    {
      std::string::string(v89, "THROW_IF_FAILED_DETAILED. ");
      v45 = std::string::append(v89, " File=");
      std::string::append(v45, "..\\Source\\TextureD3D11.cpp");
      v46 = std::string::append(v89, " Line=");
      std::string::append(v46, "384");
      v47 = std::string::append(v89, " Message=");
      std::string::append(v47, "\"TextureD3D11::GetDeviceBuffer(): unable to create texture (2D)\"");
      DirectX::Filters::TriangleRow::TriangleRow((DirectX::Filters::TriangleRow *)v75);
      v48 = ExceptionDetails::ToString(v85, v92, v75);
      v49 = std::string::append(v89, " Details=\"");
      v50 = std::string::append(v49, v48);
      std::string::append(v50, "\"");
      std::string::~string(v85);
      std::vector<Spectre::Engine::ShaderOptionFilter>::~vector<Spectre::Engine::ShaderOptionFilter>(v75);
      v51 = std::to_string(v77);
      v52 = std::string::append(v89, " HRESULT=");
      std::string::append(v52, v51);
      std::string::~string(v77);
      v53 = (const char *)std::string::c_str(v89);
      std::string::string(v78, v53);
      v54 = std::string::string(v74, "..\\Source\\TextureD3D11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v54, 384, v11, (__int64)v78, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v12 = *(_QWORD *)(a1 + 160);
    if ( v12 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(a1 + 160));
    v71 = v12;
    v13 = v90;
    v14 = v90;
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 8LL))(v90);
      v13 = v90;
    }
    v68 = v14;
    if ( v13 )
    {
      v90 = 0;
LABEL_36:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  else
  {
    v15 = *(_QWORD *)(a1 + 168);
    if ( !v15 )
    {
      std::string::string(v74, "TextureD3D11::GetDeviceBuffer - No valid D3D11 texture interface pointer");
      v43 = std::string::string(v78, "..\\Source\\TextureD3D11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v43, 415, (unsigned int)v74, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 80LL))(v15, v96);
    v97 = 3;
    v98 = 0x20000;
    v91 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int64 *))(*(_QWORD *)v88 + 48LL))(v88, v96, 0, &v91);
    Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v63[0], v16);
    if ( v16 < 0 )
    {
      std::string::string(v89, "THROW_IF_FAILED. ");
      v55 = std::string::append(v89, " File=");
      std::string::append(v55, "..\\Source\\TextureD3D11.cpp");
      v56 = std::string::append(v89, " Line=");
      std::string::append(v56, "408");
      v57 = std::string::append(v89, " Message=");
      std::string::append(v57, "\"TextureD3D11::GetDeviceBuffer(): unable to create texture (3D)\"");
      v58 = std::to_string(v78);
      v59 = std::string::append(v89, " HRESULT=");
      std::string::append(v59, v58);
      std::string::~string(v78);
      v60 = (const char *)std::string::c_str(v89);
      std::string::string(v77, v60);
      v61 = std::string::string(v74, "..\\Source\\TextureD3D11.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v61, 408, v16, (__int64)v77, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v12 = *(_QWORD *)(a1 + 168);
    if ( v12 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(a1 + 168));
    v71 = v12;
    v13 = v91;
    v14 = v91;
    if ( v91 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 8LL))(v91);
      v13 = v91;
    }
    v68 = v14;
    if ( v13 )
    {
      v91 = 0;
      goto LABEL_36;
    }
  }
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v87 + 376LL))(v87, v14, v12);
  v84 = 0;
  *(_OWORD *)Src = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, void **))(*(_QWORD *)v87 + 112LL))(
          v87,
          v14,
          0,
          1,
          0,
          Src);
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v63[0], v17);
  if ( v17 < 0 )
  {
    std::string::string(v89, "THROW_IF_FAILED. ");
    v35 = std::string::append(v89, " File=");
    std::string::append(v35, "..\\Source\\TextureD3D11.cpp");
    v36 = std::string::append(v89, " Line=");
    std::string::append(v36, "429");
    v37 = std::string::append(v89, " Message=");
    std::string::append(v37, "\"TextureD3D11::GetDeviceBuffer(): unable to map resource\"");
    v38 = std::to_string(v78);
    v39 = std::string::append(v89, " HRESULT=");
    std::string::append(v39, v38);
    std::string::~string(v78);
    v40 = (const char *)std::string::c_str(v89);
    std::string::string(v77, v40);
    v41 = std::string::string(v74, "..\\Source\\TextureD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v41, 429, v17, (__int64)v77, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  Format = Spectre::Engine::DeviceTexture::GetFormat(a1);
  LODWORD(v67) = sub_1801FD490(Format);
  LODWORD(v62[0]) = Src[1];
  v66 = (int)Src[1];
  if ( *(_QWORD *)(a1 + 168) )
  {
    v19 = HIDWORD(Src[1]);
  }
  else
  {
    Height = Spectre::Engine::DeviceTexture::GetHeight((Spectre::Engine::DeviceTexture *)a1);
    Width = Spectre::Engine::DeviceTexture::GetWidth((Spectre::Engine::DeviceTexture *)a1);
    v22 = Spectre::Engine::DeviceTexture::GetFormat(a1);
    v19 = sub_180283530(v22, Width, Height, &v66);
  }
  v23 = v64[2] * v19;
  v24 = operator new[](v23);
  v25 = v24;
  if ( v24 )
    memset_0(v24, 0, (unsigned int)v23);
  else
    v25 = 0;
  v64 = v25;
  if ( v23 )
  {
    if ( v25 )
    {
      if ( Src[0] )
      {
        memcpy_0(v25, Src[0], v23);
        goto LABEL_50;
      }
      memset_0(v25, 0, v23);
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
LABEL_50:
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v87 + 120LL))(v87, v14, 0);
  *(_QWORD *)&v72 = 0;
  *((_QWORD *)&v72 + 1) = v23;
  *(_QWORD *)&v73 = __PAIR64__(v62[0], (unsigned int)v67);
  *((_QWORD *)&v73 + 1) = v19;
  v67 = (void **)v62;
  v81 = v72;
  v82 = v73;
  v64 = 0;
  v62[0] = (__int64)v25;
  v79 = v62;
  *(_OWORD *)Block = 0;
  v70 = 0;
  v26 = operator new(0x20u);
  *v26 = v81;
  v26[1] = v82;
  v67 = Block;
  v70 = 0;
  Block[1] = 0;
  Block[0] = 0;
  v76[0] = v26;
  v76[1] = v26 + 2;
  v76[2] = v26 + 2;
  v27 = v65;
  Spectre::Engine::TextureImageSetView::TextureImageSetView((__int64)v65, v76, v62[0], v23);
  *v27 = &Spectre::Engine::TextureImageSet::`vftable';
  v28 = v62[0];
  v62[0] = 0;
  v27[7] = v28;
  v29 = 0;
  v30 = Block[0];
  if ( Block[0] )
  {
    if ( ((v70 - (unsigned __int64)Block[0]) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
    {
      v30 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v30 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v30);
    *(_OWORD *)Block = 0;
    v70 = 0;
    v29 = (void *)v62[0];
  }
  if ( v29 )
    operator delete(v29);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v31 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      v33 = v63[1];
      (**(void (__fastcall ***)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))v63[1])(v63[1]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))(*(_QWORD *)v63[1] + 8LL))(v63[1]);
    }
  }
  return v27;
}

```

## disassembly

```asm
0x18033b2f0  mov     [rsp-8+arg_10], rbx
0x18033b2f5  push    rbp
0x18033b2f6  push    rsi
0x18033b2f7  push    rdi
0x18033b2f8  push    r12
0x18033b2fa  push    r13
0x18033b2fc  push    r14
0x18033b2fe  push    r15
0x18033b300  lea     rbp, [rsp-1F0h]
0x18033b308  sub     rsp, 2F0h
0x18033b30f  mov     rax, cs:__security_cookie
0x18033b316  xor     rax, rsp
0x18033b319  mov     [rbp+220h+var_38], rax
0x18033b320  mov     [rsp+320h+var_2B8], rdx
0x18033b325  mov     r13, rcx
0x18033b328  mov     [rsp+320h+var_2C0], rdx
0x18033b32d  mov     rcx, [rcx+68h]
0x18033b331  xor     esi, esi
0x18033b333  test    rcx, rcx
0x18033b336  jz      short loc_18033B355
0x18033b338  mov     rax, [rcx]
0x18033b33b  mov     [rsp+320h+var_2C0], rax
0x18033b340  test    rax, rax
0x18033b343  jz      short loc_18033B35A
0x18033b345  mov     eax, [rax+14h]
0x18033b348  shr     eax, 4
0x18033b34b  test    al, 1
0x18033b34d  jnz     loc_18033BAA2
0x18033b353  jmp     short loc_18033B35A
0x18033b355  mov     [rsp+320h+var_2C0], rsi
0x18033b35a  cmp     dword ptr [rcx+0Ch], 1
0x18033b35e  ja      loc_18033BB45
0x18033b364  xorps   xmm0, xmm0
0x18033b367  movups  [rbp+220h+var_180], xmm0
0x18033b36e  movdqa  xmmword ptr [rsp+320h+var_2D0], xmm0
0x18033b374  mov     rdx, [r13+48h]
0x18033b378  test    rdx, rdx
0x18033b37b  jz      short loc_18033B3B0
0x18033b37d  mov     eax, [rdx+8]
0x18033b380  test    eax, eax
0x18033b382  jz      short loc_18033B3B0
0x18033b384  lea     ecx, [rax+1]
0x18033b387  lock cmpxchg [rdx+8], ecx
0x18033b38c  jz      short loc_18033B394
0x18033b38e  test    eax, eax
0x18033b390  jnz     short loc_18033B384
0x18033b392  jmp     short loc_18033B3B0
0x18033b394  mov     rax, [r13+40h]
0x18033b398  mov     [rsp+320h+var_2D0], rax
0x18033b39d  mov     r15, [r13+48h]
0x18033b3a1  mov     [rsp+320h+var_2D0+8], r15
0x18033b3a6  test    r15, r15
0x18033b3a9  jz      short loc_18033B3B5
0x18033b3ab  lock inc dword ptr [r15+8]
0x18033b3b0  mov     r15, [rsp+320h+var_2D0+8]
0x18033b3b5  movaps  xmm0, xmmword ptr [rsp+320h+var_2D0]
0x18033b3ba  movdqa  [rbp+220h+var_180], xmm0
0x18033b3c2  mov     r12d, 0FFFFFFFFh
0x18033b3c8  test    r15, r15
0x18033b3cb  jz      short loc_18033B418
0x18033b3cd  mov     eax, r12d
0x18033b3d0  lock xadd [r15+8], eax
0x18033b3d6  cmp     eax, 1
0x18033b3d9  jnz     short loc_18033B413
0x18033b3db  mov     rbx, [rsp+320h+var_2D0+8]
0x18033b3e0  mov     rax, [rbx]
0x18033b3e3  mov     rcx, rbx
0x18033b3e6  mov     rax, [rax]
0x18033b3e9  call    cs:__guard_dispatch_icall_fptr
0x18033b3ef  mov     eax, r12d
0x18033b3f2  lock xadd [rbx+0Ch], eax
0x18033b3f7  cmp     eax, 1
0x18033b3fa  jnz     short loc_18033B413
0x18033b3fc  mov     r15, [rsp+320h+var_2D0+8]
0x18033b401  mov     rax, [r15]
0x18033b404  mov     rcx, r15
0x18033b407  mov     rax, [rax+8]
0x18033b40b  call    cs:__guard_dispatch_icall_fptr
0x18033b411  jmp     short loc_18033B418
0x18033b413  mov     r15, [rsp+320h+var_2D0+8]
0x18033b418  mov     [rbp+220h+var_C8], rsi
0x18033b41f  lea     rdx, [rbp+220h+var_C8]
0x18033b426  mov     rbx, [rsp+320h+var_2D0]
0x18033b42b  mov     rcx, rbx
0x18033b42e  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x18033b433  nop
0x18033b434  mov     [rbp+220h+var_D0], rsi
0x18033b43b  lea     rdx, [rbp+220h+var_D0]
0x18033b442  mov     rcx, rbx
0x18033b445  call    ?GetDeviceContext@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11DeviceContext1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDeviceContext(void)
0x18033b44a  nop
0x18033b44b  mov     [rbp+220h+var_280], rsi
0x18033b44f  mov     [rbp+220h+var_2A0], rsi
0x18033b453  mov     rcx, [r13+0A0h]
0x18033b45a  test    rcx, rcx
0x18033b45d  jz      loc_18033B533
0x18033b463  mov     rax, [rcx]
0x18033b466  lea     rdx, [rbp+220h+var_90]
0x18033b46d  mov     rax, [rax+50h]
0x18033b471  call    cs:__guard_dispatch_icall_fptr
0x18033b477  mov     [rbp+220h+var_74], 3
0x18033b482  mov     [rbp+220h+var_6C], 20000h
0x18033b48d  mov     [rbp+220h+var_84], 1
0x18033b497  mov     [rbp+220h+var_A0], rsi
0x18033b49e  mov     rcx, [rbp+220h+var_C8]
0x18033b4a5  mov     rax, [rcx]
0x18033b4a8  lea     r9, [rbp+220h+var_A0]
0x18033b4af  xor     r8d, r8d
0x18033b4b2  lea     rdx, [rbp+220h+var_90]
0x18033b4b9  mov     rax, [rax+28h]
0x18033b4bd  call    cs:__guard_dispatch_icall_fptr
0x18033b4c3  mov     edi, eax
0x18033b4c5  mov     edx, eax; int
0x18033b4c7  mov     rcx, rbx; this
0x18033b4ca  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x18033b4cf  test    edi, edi
0x18033b4d1  js      loc_18033BB95
0x18033b4d7  mov     rbx, [r13+0A0h]
0x18033b4de  test    rbx, rbx
0x18033b4e1  jz      short loc_18033B4F3
0x18033b4e3  mov     rax, [rbx]
0x18033b4e6  mov     rcx, rbx
0x18033b4e9  mov     rax, [rax+8]
0x18033b4ed  call    cs:__guard_dispatch_icall_fptr
0x18033b4f3  mov     [rbp+220h+var_280], rbx
0x18033b4f7  mov     rcx, [rbp+220h+var_A0]
0x18033b4fe  mov     rdi, rcx
0x18033b501  test    rcx, rcx
0x18033b504  jz      short loc_18033B51A
0x18033b506  mov     rax, [rcx]
0x18033b509  mov     rax, [rax+8]
0x18033b50d  call    cs:__guard_dispatch_icall_fptr
0x18033b513  mov     rcx, [rbp+220h+var_A0]
0x18033b51a  mov     [rbp+220h+var_2A0], rdi
0x18033b51e  test    rcx, rcx
0x18033b521  jz      loc_18033B60F
0x18033b527  mov     [rbp+220h+var_A0], rsi
0x18033b52e  jmp     loc_18033B602
0x18033b533  mov     rcx, [r13+0A8h]
0x18033b53a  test    rcx, rcx
0x18033b53d  jz      loc_18033BAF2
0x18033b543  mov     rax, [rcx]
0x18033b546  lea     rdx, [rbp+220h+var_60]
0x18033b54d  mov     rax, [rax+50h]
0x18033b551  call    cs:__guard_dispatch_icall_fptr
0x18033b557  mov     [rbp+220h+var_4C], 3
0x18033b562  mov     [rbp+220h+var_44], 20000h
0x18033b56d  mov     [rbp+220h+var_98], rsi
0x18033b574  mov     rcx, [rbp+220h+var_C8]
0x18033b57b  mov     rax, [rcx]
0x18033b57e  lea     r9, [rbp+220h+var_98]
0x18033b585  xor     r8d, r8d
0x18033b588  lea     rdx, [rbp+220h+var_60]
0x18033b58f  mov     rax, [rax+30h]
0x18033b593  call    cs:__guard_dispatch_icall_fptr
0x18033b599  mov     edi, eax
0x18033b59b  mov     edx, eax; int
0x18033b59d  mov     rcx, [rsp+320h+var_2D0]; this
0x18033b5a2  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x18033b5a7  test    edi, edi
0x18033b5a9  js      loc_18033BD10
0x18033b5af  mov     rbx, [r13+0A8h]
0x18033b5b6  test    rbx, rbx
0x18033b5b9  jz      short loc_18033B5CB
0x18033b5bb  mov     rax, [rbx]
0x18033b5be  mov     rcx, rbx
0x18033b5c1  mov     rax, [rax+8]
0x18033b5c5  call    cs:__guard_dispatch_icall_fptr
0x18033b5cb  mov     [rbp+220h+var_280], rbx
0x18033b5cf  mov     rcx, [rbp+220h+var_98]
0x18033b5d6  mov     rdi, rcx
0x18033b5d9  test    rcx, rcx
0x18033b5dc  jz      short loc_18033B5F2
0x18033b5de  mov     rax, [rcx]
0x18033b5e1  mov     rax, [rax+8]
0x18033b5e5  call    cs:__guard_dispatch_icall_fptr
0x18033b5eb  mov     rcx, [rbp+220h+var_98]
0x18033b5f2  mov     [rbp+220h+var_2A0], rdi
0x18033b5f6  test    rcx, rcx
0x18033b5f9  jz      short loc_18033B60F
0x18033b5fb  mov     [rbp+220h+var_98], rsi
0x18033b602  mov     rax, [rcx]
0x18033b605  mov     rax, [rax+10h]
0x18033b609  call    cs:__guard_dispatch_icall_fptr
0x18033b60f  mov     rcx, [rbp+220h+var_D0]
0x18033b616  mov     rax, [rcx]
0x18033b619  mov     r8, rbx
0x18033b61c  mov     rdx, rdi
0x18033b61f  mov     rax, [rax+178h]
0x18033b626  call    cs:__guard_dispatch_icall_fptr
0x18033b62c  xorps   xmm0, xmm0
0x18033b62f  movaps  [rbp+220h+var_110], xmm0
0x18033b636  movdqa  xmmword ptr [rbp+220h+Src], xmm0
0x18033b63e  mov     rcx, [rbp+220h+var_D0]
0x18033b645  mov     rax, [rcx]
0x18033b648  lea     rdx, [rbp+220h+Src]
0x18033b64f  mov     [rsp+320h+var_2F8], rdx
0x18033b654  mov     dword ptr [rsp+320h+var_300], esi
0x18033b658  mov     r9d, 1
0x18033b65e  xor     r8d, r8d
0x18033b661  mov     rdx, rdi
0x18033b664  mov     rax, [rax+70h]
0x18033b668  call    cs:__guard_dispatch_icall_fptr
0x18033b66e  mov     esi, eax
0x18033b670  mov     edx, eax; int
0x18033b672  mov     rcx, [rsp+320h+var_2D0]; this
0x18033b677  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x18033b67c  test    esi, esi
0x18033b67e  js      loc_18033B98F
0x18033b684  mov     rcx, r13
0x18033b687  call    ?GetFormat@DeviceTexture@Engine@Spectre@@QEBA?AW4Format@23@XZ; Spectre::Engine::DeviceTexture::GetFormat(void)
0x18033b68c  mov     ecx, eax
0x18033b68e  call    sub_1801FD490
0x18033b693  mov     dword ptr [rsp+320h+var_2A8], eax
0x18033b697  mov     eax, dword ptr [rbp+220h+Src+8]
0x18033b69d  mov     dword ptr [rsp+320h+var_2E0], eax
0x18033b6a1  mov     [rsp+320h+var_2B0], eax
0x18033b6a5  cmp     qword ptr [r13+0A8h], 0
0x18033b6ad  jz      short loc_18033B6B8
0x18033b6af  mov     r13d, dword ptr [rbp+220h+Src+0Ch]
0x18033b6b6  jmp     short loc_18033B6E9
0x18033b6b8  mov     rcx, r13; this
0x18033b6bb  call    ?GetHeight@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetHeight(void)
0x18033b6c0  mov     r14d, eax
0x18033b6c3  mov     rcx, r13; this
0x18033b6c6  call    ?GetWidth@DeviceTexture@Engine@Spectre@@QEBAIXZ; Spectre::Engine::DeviceTexture::GetWidth(void)
0x18033b6cb  mov     esi, eax
0x18033b6cd  mov     rcx, r13
0x18033b6d0  call    ?GetFormat@DeviceTexture@Engine@Spectre@@QEBA?AW4Format@23@XZ; Spectre::Engine::DeviceTexture::GetFormat(void)
0x18033b6d5  mov     ecx, eax
0x18033b6d7  lea     r9, [rsp+320h+var_2B0]
0x18033b6dc  mov     r8d, r14d
0x18033b6df  mov     edx, esi
0x18033b6e1  call    sub_180283530
0x18033b6e6  mov     r13d, eax
0x18033b6e9  mov     eax, r13d
0x18033b6ec  mov     rcx, [rsp+320h+var_2C0]
0x18033b6f1  imul    eax, [rcx+8]
0x18033b6f5  mov     r14d, eax
0x18033b6f8  mov     ecx, eax; unsigned __int64
0x18033b6fa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18033b6ff  mov     rsi, rax
0x18033b702  test    rax, rax
0x18033b705  jz      short loc_18033B716
0x18033b707  mov     r8d, r14d; Size
0x18033b70a  xor     edx, edx; Val
0x18033b70c  mov     rcx, rax; void *
0x18033b70f  call    memset_0
0x18033b714  jmp     short loc_18033B718
0x18033b716  xor     esi, esi
0x18033b718  mov     [rsp+320h+var_2C0], rsi
0x18033b71d  test    r14, r14
0x18033b720  jz      short loc_18033B757
0x18033b722  test    rsi, rsi
0x18033b725  jz      short loc_18033B745
0x18033b727  mov     rdx, [rbp+220h+Src]; Val
0x18033b72e  mov     r8, r14; Size
0x18033b731  mov     rcx, rsi; void *
0x18033b734  test    rdx, rdx
0x18033b737  jz      short loc_18033B740
0x18033b739  call    memcpy_0
0x18033b73e  jmp     short loc_18033B757
0x18033b740  call    memset_0
0x18033b745  call    cs:__imp__errno
0x18033b74b  mov     dword ptr [rax], 16h
0x18033b751  call    cs:__imp__invalid_parameter_noinfo
0x18033b757  mov     rcx, [rbp+220h+var_D0]
0x18033b75e  mov     rax, [rcx]
0x18033b761  xor     r8d, r8d
0x18033b764  mov     rdx, rdi
0x18033b767  mov     rax, [rax+78h]
0x18033b76b  call    cs:__guard_dispatch_icall_fptr
0x18033b771  mov     qword ptr [rbp+220h+var_270], 0
0x18033b779  mov     qword ptr [rbp+220h+var_270+8], r14
0x18033b77d  mov     eax, dword ptr [rsp+320h+var_2A8]
0x18033b781  mov     dword ptr [rbp+220h+var_260], eax
0x18033b784  mov     eax, dword ptr [rsp+320h+var_2E0]
0x18033b788  mov     dword ptr [rbp+220h+var_260+4], eax
0x18033b78b  mov     dword ptr [rbp+220h+var_260+8], r13d
0x18033b78f  xor     r13d, r13d
0x18033b792  mov     dword ptr [rbp+220h+var_260+0Ch], r13d
0x18033b796  lea     rax, [rsp+320h+var_2E0]
0x18033b79b  mov     [rsp+320h+var_2A8], rax
0x18033b7a0  movups  xmm0, [rbp+220h+var_270]
0x18033b7a4  movups  [rbp+220h+var_170], xmm0
0x18033b7ab  movups  xmm1, [rbp+220h+var_260]
0x18033b7af  movups  [rbp+220h+var_160], xmm1
0x18033b7b6  mov     [rsp+320h+var_2C0], r13
0x18033b7bb  mov     [rsp+320h+var_2E0], rsi
0x18033b7c0  lea     rax, [rsp+320h+var_2E0]
0x18033b7c5  mov     [rbp+220h+var_190], rax
0x18033b7cc  xorps   xmm0, xmm0
0x18033b7cf  movdqu  xmmword ptr [rbp+220h+Block], xmm0
0x18033b7d4  mov     [rbp+220h+var_288], r13
0x18033b7d8  lea     ecx, [r13+20h]; Size
0x18033b7dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18033b7e1  lea     rcx, [rax+20h]
0x18033b7e5  movups  xmm0, [rbp+220h+var_170]
0x18033b7ec  movups  xmmword ptr [rax], xmm0
0x18033b7ef  movups  xmm1, [rbp+220h+var_160]
  ... truncated ...
```
