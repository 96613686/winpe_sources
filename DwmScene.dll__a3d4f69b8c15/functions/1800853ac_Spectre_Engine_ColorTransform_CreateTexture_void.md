# Spectre::Engine::ColorTransform::CreateTexture(void)

- ea: `0x1800853ac`
- end: `0x180085551`
- name: `?CreateTexture@ColorTransform@Engine@Spectre@@AEAAXXZ`
- size: `421`
- prototype: `void __fastcall(Spectre::Engine::ColorTransform *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800857ac`
- `0x1800859ac`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012df8`
- `0x180014280`
- `0x180016fe8`
- `0x18002866c`
- `0x180034d7c`
- `0x180047a48`
- `0x180051990`
- `0x180078050`
- `0x1800853ac`
- `0x1800e7010`

## string_xrefs

- `0x18008544f`: `ColorTransform::CreateResources() -- volume texture must be power of two below feature level 10.0`
- `0x180085460`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\colortransform.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Spectre::Engine::ColorTransform::CreateTexture(Spectre::Engine::ColorTransform *this)
{
  struct Spectre::Engine::Engine *Engine; // rax
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r8
  struct Spectre::Engine::Engine *v8; // rax
  __int64 v9; // rax
  __int64 *v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rax
  rsize_t v13; // [rsp+40h] [rbp-C0h]
  _DWORD *v14; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-A8h]
  _QWORD v16[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+C0h] [rbp-40h] BYREF

  Engine = Spectre::Engine::Component::GetEngine(this);
  Spectre::Engine::Engine::SafeGetDeviceList(Engine, v16);
  v3 = v16[0];
  v4 = v16[1];
  while ( v3 != v4 )
  {
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v14, v3);
    if ( v14[61] )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v14 + 96LL))(v14, 1) )
      {
        v5 = *((_QWORD *)this + 18);
        if ( !v5 || ((v5 - 1) & v5) != 0 )
        {
          std::string::string(
            v18,
            "ColorTransform::CreateResources() -- volume texture must be power of two below feature level 10.0");
          v6 = std::string::string(
                 v17,
                 "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\c"
                 "olortransform.cpp");
          Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v6, v7, v18);
          throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
        }
      }
    }
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    v3 += 16;
  }
  v8 = Spectre::Engine::Component::GetEngine(this);
  v9 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(v8, &v14);
  v10 = (__int64 *)((char *)this + 96);
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=((char *)this + 96, v9);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v11 = *v10;
  v12 = std::string::string(v18, "ColorTransform");
  Spectre::Engine::RendererResource::SetName(v11, v12);
  LODWORD(v13) = (*((_QWORD *)this + 15) - *((_QWORD *)this + 14)) & 0xFFFFFFFC;
  Spectre::Engine::Texture::Create(
    *v10,
    *((_DWORD *)this + 36),
    *((_DWORD *)this + 36),
    *((_DWORD *)this + 36),
    16,
    0,
    1,
    *((void **)this + 14),
    v13,
    0);
  std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(v16);
}

```

## disassembly

```asm
0x1800853ac  push    rbp
0x1800853ae  push    rbx
0x1800853af  push    rsi
0x1800853b0  push    rdi
0x1800853b1  lea     rbp, [rsp-8]
0x1800853b6  sub     rsp, 108h
0x1800853bd  mov     rax, cs:__security_cookie
0x1800853c4  xor     rax, rsp
0x1800853c7  mov     [rbp+20h+var_28], rax
0x1800853cb  mov     rdi, rcx
0x1800853ce  call    ?GetEngine@Component@Engine@Spectre@@QEBAPEAV223@XZ; Spectre::Engine::Component::GetEngine(void)
0x1800853d3  lea     rdx, [rsp+120h+var_B8]
0x1800853d8  mov     rcx, rax
0x1800853db  call    ?SafeGetDeviceList@Engine@1Spectre@@QEAA?AV?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@XZ; Spectre::Engine::Engine::SafeGetDeviceList(void)
0x1800853e0  nop
0x1800853e1  mov     rbx, [rsp+120h+var_B8]
0x1800853e6  mov     rsi, [rsp+120h+var_B0]
0x1800853eb  cmp     rbx, rsi
0x1800853ee  jz      loc_180085491
0x1800853f4  mov     rdx, rbx
0x1800853f7  lea     rcx, [rsp+120h+var_D0]
0x1800853fc  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180085401  nop
0x180085402  mov     rcx, [rsp+120h+var_D0]
0x180085407  cmp     dword ptr [rcx+0F4h], 0
0x18008540e  jz      short loc_18008543A
0x180085410  mov     rax, [rcx]
0x180085413  mov     edx, 1
0x180085418  mov     rax, [rax+60h]
0x18008541c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085421  test    al, al
0x180085423  jnz     short loc_18008543A
0x180085425  mov     rcx, [rdi+90h]
0x18008542c  test    rcx, rcx
0x18008542f  jz      short loc_18008544F
0x180085431  lea     rax, [rcx-1]
0x180085435  test    rcx, rax
0x180085438  jnz     short loc_18008544F
0x18008543a  mov     rcx, [rsp+120h+var_C8]; this
0x18008543f  test    rcx, rcx
0x180085442  jz      short loc_180085449
0x180085444  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180085449  add     rbx, 10h
0x18008544d  jmp     short loc_1800853EB
0x18008544f  lea     rdx, aColortransform_2; "ColorTransform::CreateResources() -- vo"...
0x180085456  lea     rcx, [rbp+20h+var_80]
0x18008545a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18008545f  nop
0x180085460  lea     rdx, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180085467  lea     rcx, [rbp+20h+var_A0]
0x18008546b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085470  lea     r9, [rbp+20h+var_80]
0x180085474  mov     rdx, rax
0x180085477  lea     rcx, [rbp+20h+pExceptionObject]
0x18008547b  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x180085480  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x180085487  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18008548b  call    _CxxThrowException_0
0x180085491  mov     rcx, rdi; this
0x180085494  call    ?GetEngine@Component@Engine@Spectre@@QEBAPEAV223@XZ; Spectre::Engine::Component::GetEngine(void)
0x180085499  lea     rdx, [rsp+120h+var_D0]
0x18008549e  mov     rcx, rax
0x1800854a1  call    ??$CreateResource@VTexture@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Texture,>(void)
0x1800854a6  lea     rsi, [rdi+60h]
0x1800854aa  mov     rdx, rax
0x1800854ad  mov     rcx, rsi
0x1800854b0  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800854b5  mov     rcx, [rsp+120h+var_C8]; this
0x1800854ba  test    rcx, rcx
0x1800854bd  jz      short loc_1800854C4
0x1800854bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800854c4  mov     rbx, [rsi]
0x1800854c7  lea     rdx, aColortransform_0; "ColorTransform"
0x1800854ce  lea     rcx, [rbp+20h+var_80]
0x1800854d2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800854d7  mov     rdx, rax
0x1800854da  mov     rcx, rbx
0x1800854dd  call    ?SetName@RendererResource@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::RendererResource::SetName(std::string)
0x1800854e2  mov     edx, [rdi+90h]
0x1800854e8  mov     r8, [rdi+70h]
0x1800854ec  mov     rax, [rdi+78h]
0x1800854f0  sub     rax, r8
0x1800854f3  and     eax, 0FFFFFFFCh
0x1800854f6  mov     [rsp+120h+var_D8], 0
0x1800854ff  mov     dword ptr [rsp+120h+var_E0], eax
0x180085503  mov     [rsp+120h+var_E8], r8
0x180085508  mov     [rsp+120h+var_F0], 1
0x180085510  mov     [rsp+120h+var_F8], 0
0x180085518  mov     [rsp+120h+var_100], 10h
0x180085520  mov     r9d, edx
0x180085523  mov     r8d, edx
0x180085526  mov     rcx, [rsi]
0x180085529  call    ?Create@Texture@Engine@Spectre@@QEAAXIIIW4Format@23@W4Usage@23@IPEBXIPEAVRenderDevice@23@@Z; Spectre::Engine::Texture::Create(uint,uint,uint,Spectre::Engine::Format,Spectre::Engine::Usage,uint,void const *,uint,Spectre::Engine::RenderDevice *)
0x18008552e  nop
0x18008552f  lea     rcx, [rsp+120h+var_B8]
0x180085534  call    ?_Tidy@?$vector@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(void)
0x180085539  mov     rcx, [rbp+20h+var_28]
0x18008553d  xor     rcx, rsp; StackCookie
0x180085540  call    __security_check_cookie
0x180085545  add     rsp, 108h
0x18008554c  pop     rdi
0x18008554d  pop     rsi
0x18008554e  pop     rbx
0x18008554f  pop     rbp
0x180085550  retn
```
