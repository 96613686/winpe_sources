# Spectre::Engine::D3D11::DepthBufferD3D11::CreateTexturesMultisampled(Spectre::Engine::D3D11::DepthBufferD3D11::CreateTextureContext)

- ea: `0x1800c5b60`
- end: `0x1800c5dca`
- name: `?CreateTexturesMultisampled@DepthBufferD3D11@D3D11@Engine@Spectre@@IEAAXUCreateTextureContext@1234@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800c4f90`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012c58`
- `0x180012df8`
- `0x1800135bc`
- `0x180013664`
- `0x180016fe8`
- `0x180038ddc`
- `0x18005225c`
- `0x1800c4d68`
- `0x1800c5b60`
- `0x1800e7010`

## string_xrefs

- `0x1800c5c99`: `Single sampled readable depth is only supported for Depth32 format`
- `0x1800c5c43`: `Single sampled stencil reads are not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Spectre::Engine::D3D11::DepthBufferD3D11::CreateTexturesMultisampled(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  __int64 v5; // rax
  unsigned int v6; // r14d
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 DeviceTexture; // rax
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // r8d
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-69h] BYREF
  std::_Ref_count_base *v21; // [rsp+38h] [rbp-61h]
  __int64 v22; // [rsp+40h] [rbp-59h]
  _BYTE v23[8]; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v24; // [rsp+50h] [rbp-49h]
  _BYTE v25[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+88h] [rbp-11h] BYREF

  v22 = a2;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v5 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(v4, v20);
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a1 + 128, v5);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  v6 = 69;
  if ( *(_BYTE *)(a2 + 6) )
  {
    v6 = 325;
    std::shared_ptr<Spectre::Engine::Light>::operator=(a1 + 176, a1 + 128);
  }
  v7 = a2 + 8;
  v8 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v20,
         a1 + 128);
  std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,enum Spectre::Engine::Format,unsigned int>::operator()(
    a2 + 8,
    v8,
    v9,
    v6);
  DeviceTexture = Spectre::Engine::Texture::GetDeviceTexture(*(_QWORD *)(a1 + 128), v20, *(unsigned int *)(a1 + 88));
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a1 + 96, DeviceTexture);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( *(_BYTE *)(a2 + 5) )
  {
    std::string::string(v25, "Single sampled stencil reads are not supported");
    v11 = std::string::string(
            v23,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\depthbufferd3d11.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *(_BYTE *)(a2 + 4) )
  {
    if ( *(_DWORD *)a2 != 2 )
    {
      std::string::string(v23, "Single sampled readable depth is only supported for Depth32 format");
      v13 = std::string::string(
              v25,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\depthbufferd3d11.cpp");
      Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
        (unsigned int)pExceptionObject,
        v13,
        v14,
        (unsigned int)v23,
        0);
      throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
    }
    std::weak_ptr<Spectre::Engine::RenderDevice>::lock(a1 + 72, v23);
    v15 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(v4, v20);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a1 + 160, v15);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    v16 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            v20,
            a1 + 160);
    std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,enum Spectre::Engine::Format,unsigned int>::operator()(
      v7,
      v16,
      3,
      64);
    v17 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(v4, v20);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a1 + 144, v17);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    v18 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            v20,
            a1 + 144);
    std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,enum Spectre::Engine::Format,unsigned int>::operator()(
      v7,
      v18,
      3,
      1);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
  }
  return std::_Func_class<void,>::_Tidy(v7);
}

```

## disassembly

```asm
0x1800c5b60  mov     [rsp-8+arg_10], rbx
0x1800c5b65  mov     [rsp-8+arg_18], rsi
0x1800c5b6a  push    rbp
0x1800c5b6b  push    rdi
0x1800c5b6c  push    r12
0x1800c5b6e  push    r14
0x1800c5b70  push    r15
0x1800c5b72  lea     rbp, [rsp-37h]
0x1800c5b77  sub     rsp, 0D0h
0x1800c5b7e  mov     rax, cs:__security_cookie
0x1800c5b85  xor     rax, rsp
0x1800c5b88  mov     [rbp+57h+var_30], rax
0x1800c5b8c  mov     rbx, rdx
0x1800c5b8f  mov     rdi, rcx
0x1800c5b92  mov     [rbp+57h+var_B0], rdx
0x1800c5b96  mov     rax, [rcx]
0x1800c5b99  mov     rax, [rax+20h]
0x1800c5b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5ba2  mov     r12, rax
0x1800c5ba5  lea     rdx, [rbp+57h+var_C0]
0x1800c5ba9  mov     rcx, rax
0x1800c5bac  call    ??$CreateResource@VTexture@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(void)
0x1800c5bb1  lea     r15, [rdi+80h]
0x1800c5bb8  mov     rdx, rax
0x1800c5bbb  mov     rcx, r15
0x1800c5bbe  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800c5bc3  mov     rcx, [rbp+57h+var_B8]; this
0x1800c5bc7  test    rcx, rcx
0x1800c5bca  jz      short loc_1800C5BD1
0x1800c5bcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5bd1  mov     r14d, 45h ; 'E'
0x1800c5bd7  cmp     byte ptr [rbx+6], 0
0x1800c5bdb  jz      short loc_1800C5BF2
0x1800c5bdd  mov     r14d, 145h
0x1800c5be3  lea     rcx, [rdi+0B0h]
0x1800c5bea  mov     rdx, r15
0x1800c5bed  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x1800c5bf2  lea     rsi, [rbx+8]
0x1800c5bf6  mov     r8d, [rbx]
0x1800c5bf9  mov     rdx, r15
0x1800c5bfc  lea     rcx, [rbp+57h+var_C0]
0x1800c5c00  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c5c05  mov     r9d, r14d
0x1800c5c08  mov     rdx, rax
0x1800c5c0b  mov     rcx, rsi
0x1800c5c0e  call    ??R?$_Func_class@XV?$shared_ptr@VTexture@Engine@Spectre@@@std@@W4Format@Engine@Spectre@@I@std@@QEBAXV?$shared_ptr@VTexture@Engine@Spectre@@@1@W4Format@Engine@Spectre@@I@Z; std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint>::operator()(std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint)
0x1800c5c13  mov     r8d, [rdi+58h]
0x1800c5c17  lea     rdx, [rbp+57h+var_C0]
0x1800c5c1b  mov     rcx, [r15]
0x1800c5c1e  call    ?GetDeviceTexture@Texture@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@W4RenderDeviceID@23@@Z; Spectre::Engine::Texture::GetDeviceTexture(Spectre::Engine::RenderDeviceID)
0x1800c5c23  lea     rcx, [rdi+60h]
0x1800c5c27  mov     rdx, rax
0x1800c5c2a  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800c5c2f  mov     rcx, [rbp+57h+var_B8]; this
0x1800c5c33  test    rcx, rcx
0x1800c5c36  jz      short loc_1800C5C3D
0x1800c5c38  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5c3d  cmp     byte ptr [rbx+5], 0
0x1800c5c41  jz      short loc_1800C5C8A
0x1800c5c43  lea     rdx, aSingleSampledS; "Single sampled stencil reads are not su"...
0x1800c5c4a  lea     rcx, [rbp+57h+var_88]
0x1800c5c4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c5c53  nop
0x1800c5c54  lea     rdx, aOnecoreuapWind_11; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c5c5b  lea     rcx, [rbp+57h+var_A8]
0x1800c5c5f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c5c64  mov     [rsp+0F0h+var_D0], 0
0x1800c5c69  lea     r9, [rbp+57h+var_88]
0x1800c5c6d  mov     rdx, rax
0x1800c5c70  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c5c74  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800c5c79  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800c5c80  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c5c84  call    _CxxThrowException_0
0x1800c5c8a  cmp     byte ptr [rbx+4], 0
0x1800c5c8e  jz      loc_1800C5D9A
0x1800c5c94  cmp     dword ptr [rbx], 2
0x1800c5c97  jz      short loc_1800C5CE0
0x1800c5c99  lea     rdx, aSingleSampledR; "Single sampled readable depth is only s"...
0x1800c5ca0  lea     rcx, [rbp+57h+var_A8]
0x1800c5ca4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c5ca9  nop
0x1800c5caa  lea     rdx, aOnecoreuapWind_11; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800c5cb1  lea     rcx, [rbp+57h+var_88]
0x1800c5cb5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800c5cba  mov     [rsp+0F0h+var_D0], 0
0x1800c5cbf  lea     r9, [rbp+57h+var_A8]
0x1800c5cc3  mov     rdx, rax
0x1800c5cc6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c5cca  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800c5ccf  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800c5cd6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c5cda  call    _CxxThrowException_0
0x1800c5ce0  lea     rcx, [rdi+48h]
0x1800c5ce4  lea     rdx, [rbp+57h+var_A8]
0x1800c5ce8  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800c5ced  nop
0x1800c5cee  lea     rdx, [rbp+57h+var_C0]
0x1800c5cf2  mov     rcx, r12
0x1800c5cf5  call    ??$CreateResource@VTexture@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(void)
0x1800c5cfa  lea     rbx, [rdi+0A0h]
0x1800c5d01  mov     rdx, rax
0x1800c5d04  mov     rcx, rbx
0x1800c5d07  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800c5d0c  mov     rcx, [rbp+57h+var_B8]; this
0x1800c5d10  test    rcx, rcx
0x1800c5d13  jz      short loc_1800C5D1A
0x1800c5d15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5d1a  mov     rdx, rbx
0x1800c5d1d  lea     rcx, [rbp+57h+var_C0]
0x1800c5d21  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c5d26  mov     ebx, 3
0x1800c5d2b  lea     r9d, [rbx+3Dh]
0x1800c5d2f  mov     r8d, ebx
0x1800c5d32  mov     rdx, rax
0x1800c5d35  mov     rcx, rsi
0x1800c5d38  call    ??R?$_Func_class@XV?$shared_ptr@VTexture@Engine@Spectre@@@std@@W4Format@Engine@Spectre@@I@std@@QEBAXV?$shared_ptr@VTexture@Engine@Spectre@@@1@W4Format@Engine@Spectre@@I@Z; std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint>::operator()(std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint)
0x1800c5d3d  lea     rdx, [rbp+57h+var_C0]
0x1800c5d41  mov     rcx, r12
0x1800c5d44  call    ??$CreateResource@VTexture@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(void)
0x1800c5d49  mov     rdx, rax
0x1800c5d4c  lea     rcx, [rdi+90h]
0x1800c5d53  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800c5d58  mov     rcx, [rbp+57h+var_B8]; this
0x1800c5d5c  test    rcx, rcx
0x1800c5d5f  jz      short loc_1800C5D66
0x1800c5d61  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5d66  lea     rdx, [rdi+90h]
0x1800c5d6d  lea     rcx, [rbp+57h+var_C0]
0x1800c5d71  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800c5d76  mov     r9d, 1
0x1800c5d7c  mov     r8d, ebx
0x1800c5d7f  mov     rdx, rax
0x1800c5d82  mov     rcx, rsi
0x1800c5d85  call    ??R?$_Func_class@XV?$shared_ptr@VTexture@Engine@Spectre@@@std@@W4Format@Engine@Spectre@@I@std@@QEBAXV?$shared_ptr@VTexture@Engine@Spectre@@@1@W4Format@Engine@Spectre@@I@Z; std::_Func_class<void,std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint>::operator()(std::shared_ptr<Spectre::Engine::Texture>,Spectre::Engine::Format,uint)
0x1800c5d8a  nop
0x1800c5d8b  mov     rcx, [rbp+57h+var_A0]; this
0x1800c5d8f  test    rcx, rcx
0x1800c5d92  jz      short loc_1800C5D9A
0x1800c5d94  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c5d99  nop
0x1800c5d9a  mov     rcx, rsi
0x1800c5d9d  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800c5da2  mov     rcx, [rbp+57h+var_30]
0x1800c5da6  xor     rcx, rsp; StackCookie
0x1800c5da9  call    __security_check_cookie
0x1800c5dae  lea     r11, [rsp+0F0h+var_20]
0x1800c5db6  mov     rbx, [r11+40h]
0x1800c5dba  mov     rsi, [r11+48h]
0x1800c5dbe  mov     rsp, r11
0x1800c5dc1  pop     r15
0x1800c5dc3  pop     r14
0x1800c5dc5  pop     r12
0x1800c5dc7  pop     rdi
0x1800c5dc8  pop     rbp
0x1800c5dc9  retn
```
