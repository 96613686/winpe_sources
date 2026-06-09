# Spectre::Engine::D3D11::CommandListD3D11::SubmitUpdateTexture2D(std::shared_ptr<Spectre::Engine::Texture> const &,uint,uint,uint,uint,void const *,uint,uint,uint,uint)

- ea: `0x18032bac0`
- end: `0x18032c2c5`
- name: `?SubmitUpdateTexture2D@CommandListD3D11@D3D11@Engine@Spectre@@MEAA_NAEBV?$shared_ptr@VTexture@Engine@Spectre@@@std@@IIIIPEBXIIII@Z`
- size: `2053`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180015770`
- `0x1801cd2a0`
- `0x1801fd490`
- `0x180277d80`
- `0x180283480`
- `0x180283510`
- `0x1802836c0`
- `0x180323750`
- `0x180326ca0`
- `0x18032bac0`
- `0x18033c1b0`
- `0x18033c5f0`
- `0x18039e5b0`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x18039f910`
- `0x18039f970`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032be9a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032be9a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18032bea6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18032bea6`

## string_xrefs

- `0x18032c1de`: `UpdateTexture2D can only be used with 2D textures`
- `0x18032c1a2`: `..\Source\CommandListD3D11.cpp`
- `0x18032c1ef`: `..\Source\CommandListD3D11.cpp`
- `0x18032c23c`: `..\Source\CommandListD3D11.cpp`
- `0x18032c289`: `..\Source\CommandListD3D11.cpp`
- `0x18032c22b`: `UpdateTexture2D can only be used with a valid ID3D11Texture2D interface pointer`
- `0x18032c278`: `UpdateTexture2D: Src X/Y offset exceeds the size of the data buffer`
- `0x18032c191`: `UpdateTexture2D: Src rectangle exceeds the size of the data buffer`
- `0x18032c062`: `Failed to update Texture2D with HRESULT error 0x%.8x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall Spectre::Engine::D3D11::CommandListD3D11::SubmitUpdateTexture2D(
        unsigned int *a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        int a9,
        int a10,
        int a11)
{
  __int64 *DeviceTexture; // rcx
  char v12; // si
  __int64 v13; // r14
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rax
  int Format; // eax
  int v18; // r12d
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rsi
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v22; // r13
  int v23; // r15d
  __int64 v24; // rdx
  signed __int32 v25; // eax
  signed __int32 v26; // ett
  __int64 v27; // rbx
  char *v28; // rbx
  char *v29; // rsi
  size_t v30; // r14
  __int64 v31; // r12
  __int64 i; // r15
  __int64 v33; // rbx
  _QWORD *Texture; // rax
  __int64 v35; // rcx
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rbx
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v40; // rbx
  __int64 v41; // rcx
  __int64 v42; // rbx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  __int128 v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h]
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v50[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v51; // [rsp+88h] [rbp-78h]
  int v52; // [rsp+98h] [rbp-68h]
  unsigned int v53; // [rsp+9Ch] [rbp-64h]
  __int128 v54; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v55[8]; // [rsp+B0h] [rbp-50h] BYREF
  volatile signed __int32 *v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v58[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v59[8]; // [rsp+F8h] [rbp-8h] BYREF
  volatile signed __int32 *v60; // [rsp+100h] [rbp+0h]
  _BYTE pExceptionObject[64]; // [rsp+110h] [rbp+10h] BYREF
  void *v62; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v63; // [rsp+158h] [rbp+58h]
  __int64 v64; // [rsp+160h] [rbp+60h] BYREF
  __int64 v65; // [rsp+168h] [rbp+68h] BYREF
  int v66; // [rsp+170h] [rbp+70h]
  int v67; // [rsp+174h] [rbp+74h]
  unsigned int v68; // [rsp+178h] [rbp+78h]
  int v69; // [rsp+17Ch] [rbp+7Ch]
  _DWORD v70[12]; // [rsp+180h] [rbp+80h] BYREF

  v52 = a4;
  v53 = a3;
  v50[0] = (Spectre::Engine::D3D11::RenderDeviceD3D11 *)a1;
  v49 = a7;
  LODWORD(v48) = a9;
  LODWORD(v64) = 0;
  v51 = 0;
  if ( *a2 )
  {
    DeviceTexture = (__int64 *)Spectre::Engine::Texture::GetDeviceTexture(*a2, v59, a1[20]);
    v12 = 1;
    v13 = *DeviceTexture;
  }
  else
  {
    v56 = 0;
    DeviceTexture = (__int64 *)v55;
    v12 = 2;
    v13 = 0;
  }
  *(_QWORD *)&v51 = v13;
  *((_QWORD *)&v51 + 1) = DeviceTexture[1];
  *DeviceTexture = 0;
  DeviceTexture[1] = 0;
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    if ( v56 )
    {
      if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
      {
        v14 = v56;
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
  }
  if ( (v12 & 1) != 0 )
  {
    v15 = v60;
    if ( v60 )
    {
      if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
  }
  v16 = _RTDynamicCast_0(
          v13,
          0,
          &Spectre::Engine::DeviceTexture `RTTI Type Descriptor',
          &Spectre::Engine::D3D11::TextureD3D11 `RTTI Type Descriptor',
          0);
  if ( v16 )
  {
    if ( *((_QWORD *)&v51 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v51 + 1) + 8LL));
    *(_QWORD *)&v47 = v16;
    *((_QWORD *)&v47 + 1) = *((_QWORD *)&v51 + 1);
    Format = Spectre::Engine::DeviceTexture::GetFormat(v16);
  }
  else
  {
    v47 = 0;
    Format = Spectre::Engine::DeviceTexture::GetFormat(0);
  }
  v18 = sub_1801FD490(Format);
  if ( (unsigned int)Spectre::Engine::DeviceTexture::GetTextureType(v47) != 1 )
  {
    std::string::string(v58, "UpdateTexture2D can only be used with 2D textures");
    v44 = std::string::string(v55, "..\\Source\\CommandListD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v44, 772, (unsigned int)v58, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v19 = *(_QWORD *)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v47, &v57);
  v20 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( !v19 )
  {
    std::string::string(v55, "UpdateTexture2D can only be used with a valid ID3D11Texture2D interface pointer");
    v45 = std::string::string(v58, "..\\Source\\CommandListD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v45, 777, (unsigned int)v55, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v21 = (unsigned int)(v18 * a10);
  if ( (int)v48 * a11 + (int)v21 >= a8 )
  {
    std::string::string(v55, "UpdateTexture2D: Src X/Y offset exceeds the size of the data buffer");
    v46 = std::string::string(v58, "..\\Source\\CommandListD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v46, 784, (unsigned int)v55, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( v18 * (a10 + a5) + (unsigned int)v48 * (a11 + a6 - 1) > a8 )
  {
    std::string::string(v55, "UpdateTexture2D: Src rectangle exceeds the size of the data buffer");
    v43 = std::string::string(v58, "..\\Source\\CommandListD3D11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v43, 789, (unsigned int)v55, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v64 = 0;
  Spectre::Engine::D3D11::TextureD3D11::GetOrCreateCPUStagingTexture(v47, &v64);
  v22 = v50[0];
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, void **))(**((_QWORD **)v50[0] + 17) + 112LL))(
          *((_QWORD *)v50[0] + 17),
          v64,
          0,
          4,
          0,
          &v62);
  *(_OWORD *)v50 = 0;
  v54 = 0;
  v24 = *((_QWORD *)v22 + 9);
  if ( v24 )
  {
    v25 = *(_DWORD *)(v24 + 8);
    if ( v25 )
    {
      while ( 1 )
      {
        v26 = v25;
        v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v24 + 8), v25 + 1, v25);
        if ( v26 == v25 )
          break;
        if ( !v25 )
          goto LABEL_31;
      }
      v54 = *((_OWORD *)v22 + 4);
    }
  }
LABEL_31:
  std::dynamic_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(v50, &v54);
  if ( *((_QWORD *)&v54 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      v27 = *((_QWORD *)&v54 + 1);
      (***((void (__fastcall ****)(_QWORD))&v54 + 1))(*((_QWORD *)&v54 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 12), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 8LL))(*((_QWORD *)&v54 + 1));
    }
  }
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v50[0], v23);
  if ( v23 >= 0 && (v28 = (char *)v62) != 0 )
  {
    if ( !v63 )
    {
      (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v64 + 80LL))(v64, v70);
      v63 = 4 * v70[0];
      v28 = (char *)v62;
    }
    v29 = (char *)(v49 + (unsigned int)(v48 * a11) + v21);
    if ( a6 )
    {
      v30 = (unsigned int)(v18 * a5);
      v31 = (unsigned int)v48;
      for ( i = a6; i; --i )
      {
        if ( v30 )
        {
          if ( !v28 )
            goto LABEL_46;
          if ( !v29 )
          {
            memset_0(v28, 0, v30);
LABEL_46:
            *_errno() = 22;
            _invalid_parameter_noinfo();
            goto LABEL_47;
          }
          memcpy_0(v28, v29, v30);
        }
LABEL_47:
        v28 += v63;
        v29 += v31;
      }
    }
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v22 + 17) + 120LL))(*((_QWORD *)v22 + 17), v64, 0);
    v65 = 0;
    v67 = a5;
    v68 = a6;
    v66 = 0;
    v69 = 1;
    v33 = *((_QWORD *)v22 + 17);
    Texture = (_QWORD *)Spectre::Engine::D3D11::TextureD3D11::GetTexture(v47, &v48);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, _DWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v33 + 368LL))(
      v33,
      *Texture,
      0,
      v53,
      v52,
      0,
      v64,
      0,
      &v65);
    v35 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    if ( v50[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v50[1] + 2, 0xFFFFFFFF) == 1 )
      {
        v36 = v50[1];
        (**(void (__fastcall ***)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))v50[1])(v50[1]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))(*(_QWORD *)v50[1] + 8LL))(v50[1]);
      }
    }
    v37 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v47 + 1))(*((_QWORD *)&v47 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v47 + 1) + 8LL))(*((_QWORD *)&v47 + 1));
      }
    }
    if ( *((_QWORD *)&v51 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      v38 = *((_QWORD *)&v51 + 1);
      (***((void (__fastcall ****)(_QWORD))&v51 + 1))(*((_QWORD *)&v51 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 12), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v51 + 1) + 8LL))(*((_QWORD *)&v51 + 1));
    }
    return 1;
  }
  else
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsCommandListD3D11,
      3,
      "Failed to update Texture2D with HRESULT error 0x%.8x",
      v23);
    if ( v50[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v50[1] + 2, 0xFFFFFFFF) == 1 )
      {
        v40 = v50[1];
        (**(void (__fastcall ***)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))v50[1])(v50[1]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderDeviceD3D11 *))(*(_QWORD *)v50[1] + 8LL))(v50[1]);
      }
    }
    v41 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v47 + 1))(*((_QWORD *)&v47 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v47 + 1) + 8LL))(*((_QWORD *)&v47 + 1));
      }
    }
    if ( *((_QWORD *)&v51 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        v42 = *((_QWORD *)&v51 + 1);
        (***((void (__fastcall ****)(_QWORD))&v51 + 1))(*((_QWORD *)&v51 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 12), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v51 + 1) + 8LL))(*((_QWORD *)&v51 + 1));
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18032bac0  push    rbp
0x18032bac2  push    rbx
0x18032bac3  push    rsi
0x18032bac4  push    rdi
0x18032bac5  push    r12
0x18032bac7  push    r13
0x18032bac9  push    r14
0x18032bacb  push    r15
0x18032bacd  lea     rbp, [rsp-0C8h]
0x18032bad5  sub     rsp, 1C8h
0x18032badc  mov     rax, cs:__security_cookie
0x18032bae3  xor     rax, rsp
0x18032bae6  mov     [rbp+100h+var_50], rax
0x18032baed  mov     [rbp+100h+var_168], r9d
0x18032baf1  mov     [rbp+100h+var_164], r8d
0x18032baf5  mov     r8, rcx
0x18032baf8  mov     [rsp+200h+var_188], rcx
0x18032bafd  mov     eax, [rbp+100h+arg_28]
0x18032bb03  mov     [rsp+200h+var_1AC], eax
0x18032bb07  mov     eax, [rbp+100h+arg_20]
0x18032bb0d  mov     [rsp+200h+var_1B0], eax
0x18032bb11  mov     rax, [rbp+100h+arg_30]
0x18032bb18  mov     [rsp+200h+var_190], rax
0x18032bb1d  mov     eax, [rbp+100h+arg_40]
0x18032bb23  mov     dword ptr [rsp+200h+var_198], eax
0x18032bb27  mov     r15d, [rbp+100h+arg_48]
0x18032bb2e  mov     r13d, [rbp+100h+arg_50]
0x18032bb35  xor     r12d, r12d
0x18032bb38  mov     dword ptr [rbp+100h+var_A0], r12d
0x18032bb3c  xorps   xmm0, xmm0
0x18032bb3f  movups  [rbp+100h+var_178], xmm0
0x18032bb43  mov     rcx, [rdx]
0x18032bb46  test    rcx, rcx
0x18032bb49  jz      short loc_18032BB65
0x18032bb4b  mov     r8d, [r8+50h]
0x18032bb4f  lea     rdx, [rbp+100h+var_108]
0x18032bb53  call    ?GetDeviceTexture@Texture@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@W4RenderDeviceID@23@@Z; Spectre::Engine::Texture::GetDeviceTexture(Spectre::Engine::RenderDeviceID)
0x18032bb58  mov     rcx, rax
0x18032bb5b  lea     esi, [r12+1]
0x18032bb60  mov     r14, [rax]
0x18032bb63  jmp     short loc_18032BB75
0x18032bb65  mov     [rbp+100h+var_148], r12
0x18032bb69  lea     rcx, [rbp+100h+var_150]
0x18032bb6d  mov     esi, 2
0x18032bb72  mov     r14, r12
0x18032bb75  mov     qword ptr [rbp+100h+var_178], r14
0x18032bb79  mov     rax, [rcx+8]
0x18032bb7d  mov     qword ptr [rbp+100h+var_178+8], rax
0x18032bb81  mov     [rcx], r12
0x18032bb84  mov     [rcx+8], r12
0x18032bb88  mov     edi, 0FFFFFFFFh
0x18032bb8d  test    sil, 2
0x18032bb91  jz      short loc_18032BBDB
0x18032bb93  and     esi, 0FFFFFFFDh
0x18032bb96  mov     rcx, [rbp+100h+var_148]
0x18032bb9a  test    rcx, rcx
0x18032bb9d  jz      short loc_18032BBDB
0x18032bb9f  mov     eax, edi
0x18032bba1  lock xadd [rcx+8], eax
0x18032bba6  cmp     eax, 1
0x18032bba9  jnz     short loc_18032BBDB
0x18032bbab  mov     rbx, [rbp+100h+var_148]
0x18032bbaf  mov     rax, [rbx]
0x18032bbb2  mov     rcx, rbx
0x18032bbb5  mov     rax, [rax]
0x18032bbb8  call    cs:__guard_dispatch_icall_fptr
0x18032bbbe  mov     eax, edi
0x18032bbc0  lock xadd [rbx+0Ch], eax
0x18032bbc5  cmp     eax, 1
0x18032bbc8  jnz     short loc_18032BBDB
0x18032bbca  mov     rcx, [rbp+100h+var_148]
0x18032bbce  mov     rax, [rcx]
0x18032bbd1  mov     rax, [rax+8]
0x18032bbd5  call    cs:__guard_dispatch_icall_fptr
0x18032bbdb  test    sil, 1
0x18032bbdf  jz      short loc_18032BC21
0x18032bbe1  mov     rbx, [rbp+100h+var_100]
0x18032bbe5  test    rbx, rbx
0x18032bbe8  jz      short loc_18032BC21
0x18032bbea  mov     eax, edi
0x18032bbec  lock xadd [rbx+8], eax
0x18032bbf1  cmp     eax, 1
0x18032bbf4  jnz     short loc_18032BC21
0x18032bbf6  mov     rax, [rbx]
0x18032bbf9  mov     rcx, rbx
0x18032bbfc  mov     rax, [rax]
0x18032bbff  call    cs:__guard_dispatch_icall_fptr
0x18032bc05  mov     eax, edi
0x18032bc07  lock xadd [rbx+0Ch], eax
0x18032bc0c  cmp     eax, 1
0x18032bc0f  jnz     short loc_18032BC21
0x18032bc11  mov     rax, [rbx]
0x18032bc14  mov     rcx, rbx
0x18032bc17  mov     rax, [rax+8]
0x18032bc1b  call    cs:__guard_dispatch_icall_fptr
0x18032bc21  xorps   xmm0, xmm0
0x18032bc24  movups  [rsp+200h+var_1A8], xmm0
0x18032bc29  mov     [rsp+200h+var_1E0], r12d
0x18032bc2e  lea     r9, ??_R0?AVTextureD3D11@D3D11@Engine@Spectre@@@8; Spectre::Engine::D3D11::TextureD3D11 `RTTI Type Descriptor'
0x18032bc35  lea     r8, ??_R0?AVDeviceTexture@Engine@Spectre@@@8; Spectre::Engine::DeviceTexture `RTTI Type Descriptor'
0x18032bc3c  xor     edx, edx
0x18032bc3e  mov     rcx, r14
0x18032bc41  call    __RTDynamicCast_0
0x18032bc46  test    rax, rax
0x18032bc49  jz      short loc_18032BC68
0x18032bc4b  mov     rcx, qword ptr [rbp+100h+var_178+8]
0x18032bc4f  test    rcx, rcx
0x18032bc52  jz      short loc_18032BC58
0x18032bc54  lock inc dword ptr [rcx+8]
0x18032bc58  mov     qword ptr [rsp+200h+var_1A8], rax
0x18032bc5d  mov     rax, qword ptr [rbp+100h+var_178+8]
0x18032bc61  mov     qword ptr [rsp+200h+var_1A8+8], rax
0x18032bc66  jmp     short loc_18032BC71
0x18032bc68  xorps   xmm0, xmm0
0x18032bc6b  movdqu  [rsp+200h+var_1A8], xmm0
0x18032bc71  mov     rcx, qword ptr [rsp+200h+var_1A8]
0x18032bc76  call    ?GetFormat@DeviceTexture@Engine@Spectre@@QEBA?AW4Format@23@XZ; Spectre::Engine::DeviceTexture::GetFormat(void)
0x18032bc7b  mov     ecx, eax
0x18032bc7d  call    sub_1801FD490
0x18032bc82  mov     r12d, eax
0x18032bc85  mov     rcx, qword ptr [rsp+200h+var_1A8]
0x18032bc8a  call    ?GetTextureType@DeviceTexture@Engine@Spectre@@QEBA?AW4TextureType@23@XZ; Spectre::Engine::DeviceTexture::GetTextureType(void)
0x18032bc8f  cmp     eax, 1
0x18032bc92  jnz     loc_18032C1DE
0x18032bc98  lea     rdx, [rbp+100h+var_130]
0x18032bc9c  mov     rcx, qword ptr [rsp+200h+var_1A8]
0x18032bca1  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x18032bca6  mov     rbx, [rax]
0x18032bca9  mov     rcx, [rbp+100h+var_130]
0x18032bcad  test    rcx, rcx
0x18032bcb0  jz      short loc_18032BCC7
0x18032bcb2  mov     [rbp+100h+var_130], 0
0x18032bcba  mov     rax, [rcx]
0x18032bcbd  mov     rax, [rax+10h]
0x18032bcc1  call    cs:__guard_dispatch_icall_fptr
0x18032bcc7  test    rbx, rbx
0x18032bcca  jz      loc_18032C22B
0x18032bcd0  mov     esi, r15d
0x18032bcd3  imul    esi, r12d
0x18032bcd7  mov     r14d, r13d
0x18032bcda  mov     r8d, dword ptr [rsp+200h+var_198]
0x18032bcdf  imul    r14d, r8d
0x18032bce3  lea     eax, [r14+rsi]
0x18032bce7  mov     edx, [rbp+100h+arg_38]
0x18032bced  cmp     eax, edx
0x18032bcef  jnb     loc_18032C278
0x18032bcf5  mov     r9d, [rsp+200h+var_1AC]
0x18032bcfa  lea     ecx, [r9-1]
0x18032bcfe  add     ecx, r13d
0x18032bd01  imul    ecx, r8d
0x18032bd05  mov     r8d, [rsp+200h+var_1B0]
0x18032bd0a  lea     eax, [r15+r8]
0x18032bd0e  imul    eax, r12d
0x18032bd12  add     ecx, eax
0x18032bd14  cmp     ecx, edx
0x18032bd16  ja      loc_18032C191
0x18032bd1c  xor     ebx, ebx
0x18032bd1e  mov     [rbp+100h+var_A0], rbx
0x18032bd22  lea     rdx, [rbp+100h+var_A0]
0x18032bd26  mov     rcx, qword ptr [rsp+200h+var_1A8]
0x18032bd2b  call    ?GetOrCreateCPUStagingTexture@TextureD3D11@D3D11@Engine@Spectre@@QEAA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@II@Z; Spectre::Engine::D3D11::TextureD3D11::GetOrCreateCPUStagingTexture(uint,uint)
0x18032bd30  nop
0x18032bd31  mov     r13, [rsp+200h+var_188]
0x18032bd36  mov     rcx, [r13+88h]
0x18032bd3d  mov     rax, [rcx]
0x18032bd40  lea     rdx, [rbp+100h+var_B0]
0x18032bd44  mov     [rsp+200h+var_1D8], rdx
0x18032bd49  mov     [rsp+200h+var_1E0], ebx
0x18032bd4d  lea     r9d, [rbx+4]
0x18032bd51  xor     r8d, r8d
0x18032bd54  mov     rdx, [rbp+100h+var_A0]
0x18032bd58  mov     rax, [rax+70h]
0x18032bd5c  call    cs:__guard_dispatch_icall_fptr
0x18032bd62  mov     r15d, eax
0x18032bd65  xorps   xmm0, xmm0
0x18032bd68  movups  xmmword ptr [rsp+200h+var_188], xmm0
0x18032bd6d  xorps   xmm1, xmm1
0x18032bd70  movdqu  [rbp+100h+var_160], xmm1
0x18032bd75  mov     rdx, [r13+48h]
0x18032bd79  test    rdx, rdx
0x18032bd7c  jz      short loc_18032BDA5
0x18032bd7e  mov     eax, [rdx+8]
0x18032bd81  test    eax, eax
0x18032bd83  jz      short loc_18032BDA5
0x18032bd85  lea     ecx, [rax+1]
0x18032bd88  lock cmpxchg [rdx+8], ecx
0x18032bd8d  jz      short loc_18032BD95
0x18032bd8f  test    eax, eax
0x18032bd91  jnz     short loc_18032BD85
0x18032bd93  jmp     short loc_18032BDA5
0x18032bd95  mov     rax, [r13+40h]
0x18032bd99  mov     qword ptr [rbp+100h+var_160], rax
0x18032bd9d  mov     rax, [r13+48h]
0x18032bda1  mov     qword ptr [rbp+100h+var_160+8], rax
0x18032bda5  lea     rdx, [rbp+100h+var_160]
0x18032bda9  lea     rcx, [rsp+200h+var_188]
0x18032bdae  call    ??$dynamic_pointer_cast@VRenderDeviceD3D11@D3D11@Engine@Spectre@@VRenderDevice@34@@std@@YA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@0@$$QEAV?$shared_ptr@VRenderDevice@Engine@Spectre@@@0@@Z; std::dynamic_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(std::shared_ptr<Spectre::Engine::RenderDevice> &&)
0x18032bdb3  nop
0x18032bdb4  mov     rcx, qword ptr [rbp+100h+var_160+8]
0x18032bdb8  test    rcx, rcx
0x18032bdbb  jz      short loc_18032BDF9
0x18032bdbd  mov     eax, edi
0x18032bdbf  lock xadd [rcx+8], eax
0x18032bdc4  cmp     eax, 1
0x18032bdc7  jnz     short loc_18032BDF9
0x18032bdc9  mov     rbx, qword ptr [rbp+100h+var_160+8]
0x18032bdcd  mov     rax, [rbx]
0x18032bdd0  mov     rcx, rbx
0x18032bdd3  mov     rax, [rax]
0x18032bdd6  call    cs:__guard_dispatch_icall_fptr
0x18032bddc  mov     eax, edi
0x18032bdde  lock xadd [rbx+0Ch], eax
0x18032bde3  cmp     eax, 1
0x18032bde6  jnz     short loc_18032BDF9
0x18032bde8  mov     rcx, qword ptr [rbp+100h+var_160+8]
0x18032bdec  mov     rax, [rcx]
0x18032bdef  mov     rax, [rax+8]
0x18032bdf3  call    cs:__guard_dispatch_icall_fptr
0x18032bdf9  mov     edx, r15d; int
0x18032bdfc  mov     rcx, [rsp+200h+var_188]; this
0x18032be01  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x18032be06  test    r15d, r15d
0x18032be09  js      loc_18032C05F
0x18032be0f  mov     rbx, [rbp+100h+var_B0]
0x18032be13  test    rbx, rbx
0x18032be16  jz      loc_18032C05F
0x18032be1c  cmp     [rbp+100h+var_A8], 0
0x18032be20  jnz     short loc_18032BE4E
0x18032be22  mov     rcx, [rbp+100h+var_A0]
0x18032be26  mov     rax, [rcx]
0x18032be29  lea     rdx, [rbp+100h+var_80]
0x18032be30  mov     rax, [rax+50h]
0x18032be34  call    cs:__guard_dispatch_icall_fptr
0x18032be3a  mov     eax, [rbp+100h+var_80]
0x18032be40  lea     eax, ds:0[rax*4]
0x18032be47  mov     [rbp+100h+var_A8], eax
0x18032be4a  mov     rbx, [rbp+100h+var_B0]
0x18032be4e  mov     eax, r14d
0x18032be51  add     rax, [rsp+200h+var_190]
0x18032be56  add     rsi, rax
0x18032be59  mov     eax, [rsp+200h+var_1B0]
0x18032be5d  imul    eax, r12d
0x18032be61  mov     ecx, [rsp+200h+var_1AC]
0x18032be65  test    ecx, ecx
0x18032be67  jz      short loc_18032BEBB
0x18032be69  mov     r14d, eax
0x18032be6c  mov     r12d, dword ptr [rsp+200h+var_198]
0x18032be71  mov     r15d, ecx
0x18032be74  test    r14, r14
0x18032be77  jz      short loc_18032BEAC
0x18032be79  test    rbx, rbx
0x18032be7c  jz      short loc_18032BE9A
0x18032be7e  mov     r8, r14; Size
0x18032be81  mov     rcx, rbx; void *
0x18032be84  test    rsi, rsi
0x18032be87  jz      short loc_18032BE93
0x18032be89  mov     rdx, rsi; Src
0x18032be8c  call    memcpy_0
0x18032be91  jmp     short loc_18032BEAC
0x18032be93  xor     edx, edx; Val
0x18032be95  call    memset_0
0x18032be9a  call    cs:__imp__errno
0x18032bea0  mov     dword ptr [rax], 16h
0x18032bea6  call    cs:__imp__invalid_parameter_noinfo
0x18032beac  mov     eax, [rbp+100h+var_A8]
0x18032beaf  add     rbx, rax
0x18032beb2  add     rsi, r12
0x18032beb5  sub     r15, 1
0x18032beb9  jnz     short loc_18032BE74
0x18032bebb  mov     rcx, [r13+88h]
0x18032bec2  mov     rax, [rcx]
0x18032bec5  xor     r8d, r8d
0x18032bec8  mov     rdx, [rbp+100h+var_A0]
0x18032becc  mov     rax, [rax+78h]
0x18032bed0  call    cs:__guard_dispatch_icall_fptr
0x18032bed6  xor     esi, esi
0x18032bed8  mov     [rbp+100h+var_98], rsi
0x18032bedc  mov     eax, [rsp+200h+var_1B0]
0x18032bee0  mov     [rbp+100h+var_8C], eax
0x18032bee3  mov     r9d, [rsp+200h+var_1AC]
0x18032bee8  mov     [rbp+100h+var_88], r9d
0x18032beec  mov     [rbp+100h+var_90], esi
0x18032beef  mov     [rbp+100h+var_84], 1
0x18032bef6  mov     rbx, [r13+88h]
0x18032befd  lea     rdx, [rsp+200h+var_198]
0x18032bf02  mov     rcx, qword ptr [rsp+200h+var_1A8]
0x18032bf07  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x18032bf0c  mov     r10, rax
0x18032bf0f  mov     rdx, [rbx]
0x18032bf12  mov     rax, [rdx+170h]
0x18032bf19  lea     rcx, [rbp+100h+var_98]
0x18032bf1d  mov     [rsp+200h+var_1C0], rcx
0x18032bf22  mov     [rsp+200h+var_1C8], esi
0x18032bf26  mov     rdx, [rbp+100h+var_A0]
0x18032bf2a  mov     [rsp+200h+var_1D0], rdx
0x18032bf2f  mov     dword ptr [rsp+200h+var_1D8], esi
0x18032bf33  mov     ecx, [rbp+100h+var_168]
0x18032bf36  mov     [rsp+200h+var_1E0], ecx
0x18032bf3a  mov     r9d, [rbp+100h+var_164]
0x18032bf3e  xor     r8d, r8d
  ... truncated ...
```
