# Spectre::Engine::D3D11::DepthBufferD3D11::Create(uint,uint,Spectre::Engine::Format,uint)

- ea: `0x1800c4f90`
- end: `0x1800c5420`
- name: `?Create@DepthBufferD3D11@D3D11@Engine@Spectre@@UEAAXIIW4Format@34@I@Z`
- size: `1168`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000fe40`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x1800125e8`
- `0x180012ba8`
- `0x180012c58`
- `0x180012df8`
- `0x1800135bc`
- `0x180013664`
- `0x180014a3c`
- `0x180016fe8`
- `0x1800182e8`
- `0x18001c630`
- `0x1800284ec`
- `0x18002866c`
- `0x1800286b4`
- `0x180038ddc`
- `0x18004ff80`
- `0x18005021c`
- `0x1800681a8`
- `0x1800b62f0`
- `0x1800b7e3c`
- `0x1800ba4b0`
- `0x1800bedf4`
- `0x1800c48e0`
- `0x1800c4994`
- `0x1800c4a04`
- `0x1800c4f90`
- `0x1800c56d0`
- `0x1800c5b60`
- `0x1800e7010`

## string_xrefs

- `0x1800c51a2`: `DepthBuffer Readable Sampler`
- `0x1800c509e`: `Readable stencil requested for stencil-buffer format that does not support stencil`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Spectre::Engine::D3D11::DepthBufferD3D11::Create(
        __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5)
{
  __int16 v7; // cx
  __int64 v8; // rax
  int v9; // eax
  int v10; // r8d
  __int64 v11; // r13
  __int64 v12; // rax
  _QWORD *v13; // r15
  __int64 v14; // rbx
  __int64 Name; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  unsigned int v18; // edi
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  _DWORD *v22; // rax
  __int64 v23; // rax
  void (__fastcall *v24)(__int64, __int64); // r8
  __int64 v25; // r9
  __int64 TextureContext; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int128 *, __int64); // rbx
  int v31; // eax
  __int64 v32; // rax
  const char *v33; // rax
  int v34; // eax
  int v35; // r8d
  __int128 v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v45; // [rsp+A0h] [rbp-60h]
  unsigned int v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D4h] [rbp-2Ch]
  bool v48; // [rsp+D5h] [rbp-2Bh]
  bool v49; // [rsp+D6h] [rbp-2Ah]
  _BYTE v50[56]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v51; // [rsp+110h] [rbp+10h]
  _BYTE pExceptionObject[72]; // [rsp+120h] [rbp+20h] BYREF

  v38 = a2;
  v37 = a3;
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(a1 + 72, &v42);
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  if ( a4 - 1 > 1 )
  {
    std::string::string(&v42, "Invalid format for DepthBuffer");
    v34 = std::string::string(
            pExceptionObject,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\depthbufferd3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)&v44, v34, v35, (unsigned int)&v42, 0);
    throw (Spectre::Engine::EngineException *)&v44;
  }
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(a1 + 72, &v36);
  *(_OWORD *)v39 = v36;
  v7 = a5;
  *(_BYTE *)(a1 + 256) = (a5 & 0x40) != 0;
  v51 = 0;
  v46 = a4;
  v47 = HIBYTE(v7) & 1;
  v48 = (v7 & 0x400) != 0;
  v49 = (v7 & 0x200) != 0;
  v8 = lambda_5efd0f16faa6f6439fdb99826dc3e8ab_::_lambda_5efd0f16faa6f6439fdb99826dc3e8ab_(
         (unsigned int)pExceptionObject,
         a1,
         (unsigned int)&v38,
         (unsigned int)&v37,
         (__int64)&a5,
         (__int64)v39);
  std::function_void___cdecl_std::shared_ptr_Spectre::Engine::Texture__enum_Spectre::Engine::Format_unsigned_int__::operator___lambda_5efd0f16faa6f6439fdb99826dc3e8ab__0_(
    v50,
    v8);
  a5 = a5 & 0xFFFFF8BA | 1;
  if ( v48 && a4 != 1 )
  {
    std::string::string(&v44, "Readable stencil requested for stencil-buffer format that does not support stencil");
    v9 = std::string::string(
           &v42,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\depthbufferd3d11.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v9,
      v10,
      (unsigned int)&v44,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v11 = v42;
  v12 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(*(_QWORD *)(v42 + 3984), &v42);
  v13 = (_QWORD *)(a1 + 128);
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a1 + 128, v12);
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  v14 = *v13;
  Name = Spectre::Engine::RendererResource::GetName(a1, &v44);
  v16 = std::operator+<char>(&v42, Name, "Shared Texture");
  Spectre::Engine::RendererResource::SetName(v14, v16);
  std::string::_Tidy_deallocate(&v44);
  Spectre::Engine::RendererResource::SetOption(*v13, 1, 0);
  v18 = v17 + 2;
  Spectre::Engine::RendererResource::SetOption(*v13, (unsigned int)(v17 + 2), v17);
  Spectre::Engine::RendererResource::SetOption(*v13, v18 + 2, v19);
  if ( v47 || v48 || v49 )
  {
    Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceSampler>(v11, &v44);
    v20 = v44;
    v21 = std::string::string(&v42, "DepthBuffer Readable Sampler");
    Spectre::Engine::RendererResource::SetName(v20, v21);
    if ( v47 )
      std::shared_ptr<Spectre::Engine::Light>::operator=(a1 + 208, &v44);
    if ( v48 )
      std::shared_ptr<Spectre::Engine::Light>::operator=(a1 + 240, &v44);
    if ( v49 )
      std::shared_ptr<Spectre::Engine::Light>::operator=(a1 + 224, &v44);
    std::make_shared<Spectre::Engine::SamplerStateDesc,>(&v42);
    v22 = (_DWORD *)v42;
    *(_DWORD *)v42 = 0;
    v22[1] = v18;
    v22[2] = v18;
    v22[3] = v18;
    v23 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v36,
            &v42);
    v24(v25, v23);
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
  }
  v40 = 0;
  v41 = 0;
  if ( a4 - 23 > 1 )
    v18 = (a5 & 8) != 0;
  LODWORD(v40) = Spectre::Engine::D3D11::D3DUtils::GetFormat(a4, v18);
  if ( *(_BYTE *)(a1 + 256) )
  {
    DWORD1(v40) = 5;
    TextureContext = Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext::CreateTextureContext(
                       (Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext *)pExceptionObject,
                       (const struct Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext *)&v46);
    Spectre::Engine::D3D11::DepthBufferD3D11::CreateTexturesMultisampled(a1, TextureContext);
  }
  else
  {
    DWORD1(v40) = 3;
    v27 = Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext::CreateTextureContext(
            (Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext *)pExceptionObject,
            (const struct Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext *)&v46);
    Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextures(a1, v27);
  }
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v39[0], &v36);
  v28 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          &v44,
          a1 + 96);
  Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(
    &v42,
    v28);
  Spectre::Engine::D3D11::TextureD3D11::GetTexture(v42, &v44);
  v29 = v36;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, __int64))(*(_QWORD *)v36 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 112);
  v31 = v30(v29, v44, &v40, a1 + 112);
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v39[0], v31);
  v32 = Spectre::Engine::RendererResource::GetName(a1, pExceptionObject);
  v33 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v32);
  D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(a1 + 112), v33);
  std::string::_Tidy_deallocate(pExceptionObject);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  std::_Func_class<void,>::_Tidy(v50);
  if ( v39[1] )
    std::_Ref_count_base::_Decref(v39[1]);
}

```

## disassembly

```asm
0x1800c4f90  push    rbp
0x1800c4f92  push    rbx
0x1800c4f93  push    rsi
0x1800c4f94  push    rdi
0x1800c4f95  push    r12
0x1800c4f97  push    r13
0x1800c4f99  push    r14
0x1800c4f9b  push    r15
0x1800c4f9d  lea     rbp, [rsp-78h]
0x1800c4fa2  sub     rsp, 178h
0x1800c4fa9  mov     rax, cs:__security_cookie
0x1800c4fb0  xor     rax, rsp
0x1800c4fb3  mov     [rbp+0B0h+var_48], rax
0x1800c4fb7  mov     esi, r9d
0x1800c4fba  mov     r14, rcx
0x1800c4fbd  mov     [rsp+1B0h+var_168], edx
0x1800c4fc1  mov     [rsp+1B0h+var_170], r8d
0x1800c4fc6  lea     rdx, [rsp+1B0h+var_138]
0x1800c4fcb  add     rcx, 48h ; 'H'
0x1800c4fcf  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800c4fd4  mov     rcx, [rbp+0B0h+var_130]; this
0x1800c4fd8  xor     r12d, r12d
0x1800c4fdb  test    rcx, rcx
0x1800c4fde  jz      short loc_1800C4FE5
0x1800c4fe0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c4fe5  lea     eax, [rsi-1]
0x1800c4fe8  mov     edi, 1
0x1800c4fed  cmp     eax, edi
0x1800c4fef  ja      loc_1800C53D7
0x1800c4ff5  lea     rdx, [rsp+1B0h+var_180]
0x1800c4ffa  lea     rcx, [r14+48h]
0x1800c4ffe  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800c5003  movaps  xmm0, [rsp+1B0h+var_180]
0x1800c5008  movdqa  xmmword ptr [rsp+1B0h+var_160], xmm0
0x1800c500e  mov     ecx, [rbp+0B0h+arg_20]
0x1800c5014  mov     eax, ecx
0x1800c5016  shr     eax, 6
0x1800c5019  and     al, dil
0x1800c501c  mov     [r14+100h], al
0x1800c5023  mov     [rbp+0B0h+var_A0], r12
0x1800c5027  mov     [rbp+0B0h+var_E0], esi
0x1800c502a  mov     eax, ecx
0x1800c502c  shr     eax, 8
0x1800c502f  and     al, dil
0x1800c5032  mov     [rbp+0B0h+var_DC], al
0x1800c5035  mov     eax, ecx
0x1800c5037  shr     eax, 0Ah
0x1800c503a  and     al, dil
0x1800c503d  mov     [rbp+0B0h+var_DB], al
0x1800c5040  shr     ecx, 9
0x1800c5043  and     cl, dil
0x1800c5046  mov     [rbp+0B0h+var_DA], cl
0x1800c5049  lea     rax, [rsp+1B0h+var_160]
0x1800c504e  mov     [rsp+1B0h+var_188], rax
0x1800c5053  lea     rax, [rbp+0B0h+arg_20]
0x1800c505a  mov     [rsp+1B0h+var_190], rax
0x1800c505f  lea     r9, [rsp+1B0h+var_170]
0x1800c5064  lea     r8, [rsp+1B0h+var_168]
0x1800c5069  mov     rdx, r14
0x1800c506c  lea     rcx, [rbp+0B0h+pExceptionObject]
0x1800c5070  call    _lambda_5efd0f16faa6f6439fdb99826dc3e8ab____lambda_5efd0f16faa6f6439fdb99826dc3e8ab_
0x1800c5075  mov     rdx, rax
0x1800c5078  lea     rcx, [rbp+0B0h+var_D8]
0x1800c507c  call    std__function_void___cdecl_std__shared_ptr_Spectre__Engine__Texture__enum_Spectre__Engine__Format_unsigned_int____operator___lambda_5efd0f16faa6f6439fdb99826dc3e8ab__0_
0x1800c5081  mov     eax, [rbp+0B0h+arg_20]
0x1800c5087  and     eax, 0FFFFF8BBh
0x1800c508c  or      eax, edi
0x1800c508e  mov     [rbp+0B0h+arg_20], eax
0x1800c5094  cmp     [rbp+0B0h+var_DB], r12b
0x1800c5098  jz      short loc_1800C50E6
0x1800c509a  cmp     esi, edi
0x1800c509c  jz      short loc_1800C50E6
0x1800c509e  lea     rdx, aReadableStenci; "Readable stencil requested for stencil-"...
0x1800c50a5  lea     rcx, [rbp+0B0h+var_118]
0x1800c50a9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c50ae  nop
0x1800c50af  lea     rdx, aOnecoreuapWind_11; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c50b6  lea     rcx, [rsp+1B0h+var_138]
0x1800c50bb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c50c0  mov     byte ptr [rsp+1B0h+var_190], r12b
0x1800c50c5  lea     r9, [rbp+0B0h+var_118]
0x1800c50c9  mov     rdx, rax
0x1800c50cc  lea     rcx, [rbp+0B0h+pExceptionObject]
0x1800c50d0  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800c50d5  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800c50dc  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800c50e0  call    _CxxThrowException_0
0x1800c50e6  mov     r13, [rsp+1B0h+var_138]
0x1800c50eb  lea     rdx, [rsp+1B0h+var_138]
0x1800c50f0  mov     rcx, [r13+0F90h]
0x1800c50f7  call    ??$CreateResource@VTexture@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(void)
0x1800c50fc  lea     r15, [r14+80h]
0x1800c5103  mov     rdx, rax
0x1800c5106  mov     rcx, r15
0x1800c5109  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800c510e  mov     rcx, [rbp+0B0h+var_130]; this
0x1800c5112  test    rcx, rcx
0x1800c5115  jz      short loc_1800C511C
0x1800c5117  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c511c  mov     rbx, [r15]
0x1800c511f  lea     rdx, [rbp+0B0h+var_118]
0x1800c5123  mov     rcx, r14
0x1800c5126  call    ?GetName@RendererResource@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::RendererResource::GetName(void)
0x1800c512b  nop
0x1800c512c  lea     r8, aSharedTexture; "Shared Texture"
0x1800c5133  mov     rdx, rax
0x1800c5136  lea     rcx, [rsp+1B0h+var_138]
0x1800c513b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800c5140  mov     rdx, rax
0x1800c5143  mov     rcx, rbx
0x1800c5146  call    ?SetName@RendererResource@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::RendererResource::SetName(std::string)
0x1800c514b  nop
0x1800c514c  lea     rcx, [rbp+0B0h+var_118]
0x1800c5150  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c5155  xor     r8d, r8d
0x1800c5158  mov     edx, edi
0x1800c515a  mov     rcx, [r15]
0x1800c515d  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x1800c5162  lea     edi, [r8+2]
0x1800c5166  mov     edx, edi
0x1800c5168  mov     rcx, [r15]
0x1800c516b  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x1800c5170  lea     edx, [rdi+2]
0x1800c5173  mov     rcx, [r15]
0x1800c5176  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x1800c517b  cmp     [rbp+0B0h+var_DC], r12b
0x1800c517f  jnz     short loc_1800C5191
0x1800c5181  cmp     [rbp+0B0h+var_DB], r12b
0x1800c5185  jnz     short loc_1800C5191
0x1800c5187  cmp     [rbp+0B0h+var_DA], r12b
0x1800c518b  jz      loc_1800C5262
0x1800c5191  lea     rdx, [rbp+0B0h+var_118]
0x1800c5195  mov     rcx, r13
0x1800c5198  call    ??$CreateResource@VDeviceSampler@Engine@Spectre@@@RenderDevice@Engine@Spectre@@QEAA?AV?$shared_ptr@VDeviceSampler@Engine@Spectre@@@std@@XZ; Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceSampler>(void)
0x1800c519d  nop
0x1800c519e  mov     rbx, [rbp+0B0h+var_118]
0x1800c51a2  lea     rdx, aDepthbufferRea; "DepthBuffer Readable Sampler"
0x1800c51a9  lea     rcx, [rsp+1B0h+var_138]
0x1800c51ae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c51b3  mov     rdx, rax
0x1800c51b6  mov     rcx, rbx
0x1800c51b9  call    ?SetName@RendererResource@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::RendererResource::SetName(std::string)
0x1800c51be  cmp     [rbp+0B0h+var_DC], r12b
0x1800c51c2  jz      short loc_1800C51D4
0x1800c51c4  lea     rcx, [r14+0D0h]
0x1800c51cb  lea     rdx, [rbp+0B0h+var_118]
0x1800c51cf  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x1800c51d4  cmp     [rbp+0B0h+var_DB], r12b
0x1800c51d8  jz      short loc_1800C51EA
0x1800c51da  lea     rcx, [r14+0F0h]
0x1800c51e1  lea     rdx, [rbp+0B0h+var_118]
0x1800c51e5  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x1800c51ea  cmp     [rbp+0B0h+var_DA], r12b
0x1800c51ee  jz      short loc_1800C5200
0x1800c51f0  lea     rcx, [r14+0E0h]
0x1800c51f7  lea     rdx, [rbp+0B0h+var_118]
0x1800c51fb  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x1800c5200  lea     rcx, [rsp+1B0h+var_138]
0x1800c5205  call    ??$make_shared@USamplerStateDesc@Engine@Spectre@@$$V@std@@YA?AV?$shared_ptr@USamplerStateDesc@Engine@Spectre@@@0@XZ; std::make_shared<Spectre::Engine::SamplerStateDesc,>(void)
0x1800c520a  nop
0x1800c520b  mov     rax, [rsp+1B0h+var_138]
0x1800c5210  mov     [rax], r12d
0x1800c5213  mov     [rax+4], edi
0x1800c5216  mov     [rax+8], edi
0x1800c5219  mov     [rax+0Ch], edi
0x1800c521c  mov     r9, [rbp+0B0h+var_118]
0x1800c5220  mov     rax, [r9]
0x1800c5223  mov     r8, [rax+30h]
0x1800c5227  lea     rdx, [rsp+1B0h+var_138]
0x1800c522c  lea     rcx, [rsp+1B0h+var_180]
0x1800c5231  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c5236  mov     rdx, rax
0x1800c5239  mov     rcx, r9
0x1800c523c  mov     rax, r8
0x1800c523f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5244  nop
0x1800c5245  mov     rcx, [rbp+0B0h+var_130]; this
0x1800c5249  test    rcx, rcx
0x1800c524c  jz      short loc_1800C5254
0x1800c524e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5253  nop
0x1800c5254  mov     rcx, [rbp+0B0h+var_110]; this
0x1800c5258  test    rcx, rcx
0x1800c525b  jz      short loc_1800C5262
0x1800c525d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5262  xorps   xmm0, xmm0
0x1800c5265  xor     eax, eax
0x1800c5267  movups  [rsp+1B0h+var_150], xmm0
0x1800c526c  mov     [rsp+1B0h+var_140], rax
0x1800c5271  lea     eax, [rsi-17h]
0x1800c5274  cmp     eax, 1
0x1800c5277  jbe     short loc_1800C528A
0x1800c5279  mov     edi, r12d
0x1800c527c  test    byte ptr [rbp+0B0h+arg_20], 8
0x1800c5283  jz      short loc_1800C528A
0x1800c5285  mov     edi, 1
0x1800c528a  mov     edx, edi
0x1800c528c  mov     ecx, esi
0x1800c528e  call    ?GetFormat@D3DUtils@D3D11@Engine@Spectre@@SA?AW4DXGI_FORMAT@@W4Format@34@W4ColorSpace@234@@Z; Spectre::Engine::D3D11::D3DUtils::GetFormat(Spectre::Engine::Format,Spectre::Engine::D3D11::ColorSpace)
0x1800c5293  mov     dword ptr [rsp+1B0h+var_150], eax
0x1800c5297  lea     rdx, [rbp+0B0h+var_E0]; struct Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext *
0x1800c529b  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1800c529f  cmp     [r14+100h], r12b
0x1800c52a6  jz      short loc_1800C52C2
0x1800c52a8  mov     dword ptr [rsp+1B0h+var_150+4], 5
0x1800c52b0  call    ??0CreateTextureContext@DepthBufferD3D11@D3D11@Engine@Spectre@@QEAA@AEBU01234@@Z; Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext::CreateTextureContext(Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext const &)
0x1800c52b5  mov     rdx, rax
0x1800c52b8  mov     rcx, r14
0x1800c52bb  call    ?CreateTexturesMultisampled@DepthBufferD3D11@D3D11@Engine@Spectre@@IEAAXUCreateTextureContext@1234@@Z; Spectre::Engine::D3D11::DepthBufferD3D11::CreateTexturesMultisampled(Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext)
0x1800c52c0  jmp     short loc_1800C52DA
0x1800c52c2  mov     dword ptr [rsp+1B0h+var_150+4], 3
0x1800c52ca  call    ??0CreateTextureContext@DepthBufferD3D11@D3D11@Engine@Spectre@@QEAA@AEBU01234@@Z; Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext::CreateTextureContext(Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext const &)
0x1800c52cf  mov     rdx, rax
0x1800c52d2  mov     rcx, r14
0x1800c52d5  call    ?CreateTextures@DepthBufferD3D11@D3D11@Engine@Spectre@@IEAAXUCreateTextureContext@1234@@Z; Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextures(Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext)
0x1800c52da  lea     rdx, [rsp+1B0h+var_180]
0x1800c52df  mov     rcx, [rsp+1B0h+var_160]
0x1800c52e4  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x1800c52e9  nop
0x1800c52ea  lea     rdx, [r14+60h]
0x1800c52ee  lea     rcx, [rbp+0B0h+var_118]
0x1800c52f2  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c52f7  mov     rdx, rax
0x1800c52fa  lea     rcx, [rsp+1B0h+var_138]
0x1800c52ff  call    ??$spectre_safe_pointer_cast@VCommandListD3D11@D3D11@Engine@Spectre@@VCommandList@34@@Utils@Spectre@@YA?AV?$shared_ptr@VCommandListD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VCommandList@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(std::shared_ptr<Spectre::Engine::CommandList>)
0x1800c5304  nop
0x1800c5305  lea     rdx, [rbp+0B0h+var_118]
0x1800c5309  mov     rcx, [rsp+1B0h+var_138]
0x1800c530e  call    ?GetTexture@TextureD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::TextureD3D11::GetTexture(void)
0x1800c5313  nop
0x1800c5314  mov     rdi, qword ptr [rsp+1B0h+var_180]
0x1800c5319  mov     rax, [rdi]
0x1800c531c  mov     rbx, [rax+50h]
0x1800c5320  lea     rsi, [r14+70h]
0x1800c5324  mov     rcx, rsi
0x1800c5327  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c532c  mov     r9, rsi
0x1800c532f  lea     r8, [rsp+1B0h+var_150]
0x1800c5334  mov     rdx, [rbp+0B0h+var_118]
0x1800c5338  mov     rcx, rdi
0x1800c533b  mov     rax, rbx
0x1800c533e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5343  mov     edx, eax; int
0x1800c5345  mov     rcx, [rsp+1B0h+var_160]; this
0x1800c534a  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800c534f  lea     rdx, [rbp+0B0h+pExceptionObject]
0x1800c5353  mov     rcx, r14
0x1800c5356  call    ?GetName@RendererResource@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::RendererResource::GetName(void)
0x1800c535b  nop
0x1800c535c  mov     rcx, rax
0x1800c535f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800c5364  mov     rdx, rax; char *
0x1800c5367  mov     rcx, [rsi]; struct ID3D11DeviceChild *
0x1800c536a  call    ?D3D11_SetDebugName@@YAXPEAUID3D11DeviceChild@@PEBD@Z; D3D11_SetDebugName(ID3D11DeviceChild *,char const *)
0x1800c536f  nop
0x1800c5370  lea     rcx, [rbp+0B0h+pExceptionObject]
0x1800c5374  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c5379  nop
0x1800c537a  lea     rcx, [rbp+0B0h+var_118]
0x1800c537e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5383  nop
0x1800c5384  mov     rcx, [rbp+0B0h+var_130]; this
0x1800c5388  test    rcx, rcx
0x1800c538b  jz      short loc_1800C5393
0x1800c538d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5392  nop
0x1800c5393  lea     rcx, [rsp+1B0h+var_180]
0x1800c5398  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c539d  nop
0x1800c539e  lea     rcx, [rbp+0B0h+var_D8]
0x1800c53a2  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800c53a7  nop
0x1800c53a8  mov     rcx, [rsp+1B0h+var_160+8]; this
0x1800c53ad  test    rcx, rcx
0x1800c53b0  jz      short loc_1800C53B7
0x1800c53b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c53b7  mov     rcx, [rbp+0B0h+var_48]
0x1800c53bb  xor     rcx, rsp; StackCookie
0x1800c53be  call    __security_check_cookie
0x1800c53c3  add     rsp, 178h
0x1800c53ca  pop     r15
0x1800c53cc  pop     r14
0x1800c53ce  pop     r13
0x1800c53d0  pop     r12
0x1800c53d2  pop     rdi
0x1800c53d3  pop     rsi
0x1800c53d4  pop     rbx
0x1800c53d5  pop     rbp
0x1800c53d6  retn
0x1800c53d7  lea     rdx, aInvalidFormatF; "Invalid format for DepthBuffer"
0x1800c53de  lea     rcx, [rsp+1B0h+var_138]
0x1800c53e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c53e8  nop
0x1800c53e9  lea     rdx, aOnecoreuapWind_11; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c53f0  lea     rcx, [rbp+0B0h+pExceptionObject]
0x1800c53f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c53f9  mov     byte ptr [rsp+1B0h+var_190], r12b
0x1800c53fe  lea     r9, [rsp+1B0h+var_138]
0x1800c5403  mov     rdx, rax
0x1800c5406  lea     rcx, [rbp+0B0h+var_118]
  ... truncated ...
```
