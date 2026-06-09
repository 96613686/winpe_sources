# Spectre::Engine::D3D11::CommandListD3D11::Create(Spectre::Engine::State const &)

- ea: `0x1800bf6e0`
- end: `0x1800bf8df`
- name: `?Create@CommandListD3D11@D3D11@Engine@Spectre@@UEAA_NAEBVState@34@@Z`
- size: `511`
- prototype: `bool __fastcall(Spectre::Engine::D3D11::CommandListD3D11 *__hidden this, const struct Spectre::Engine::State *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000fe40`
- `0x18001128c`
- `0x1800125e8`
- `0x180012ba8`
- `0x180012c58`
- `0x180012df8`
- `0x180014a3c`
- `0x18001daf4`
- `0x1800284ec`
- `0x1800376f0`
- `0x1800b62f0`
- `0x1800b7e3c`
- `0x1800bba28`
- `0x1800bf6e0`
- `0x1800e7010`

## string_xrefs

- `0x1800bf7e3`: `Failed to create DeferredContext with HRESULT error 0x%.8x`
- `0x1800bf712`: `Failed to create CommandList object`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall Spectre::Engine::D3D11::CommandListD3D11::Create(
        Spectre::Engine::D3D11::CommandListD3D11 *this,
        const struct Spectre::Engine::State *a2)
{
  struct ID3D11DeviceChild **v4; // rdi
  __int64 v5; // rax
  __int64 *v6; // rsi
  char v7; // al
  __int64 v8; // r14
  char *v9; // rcx
  int v10; // esi
  __int64 Name; // rax
  const char *v12; // rax
  char *v13; // rsi
  struct ID3D11DeviceChild *v14; // rdi
  HRESULT (__stdcall *QueryInterface)(ID3D11DeviceChild *, const IID *const, void **); // rbx
  _QWORD v16[2]; // [rsp+20h] [rbp-60h] BYREF
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v17; // [rsp+30h] [rbp-50h] BYREF
  std::_Ref_count_base *v18; // [rsp+38h] [rbp-48h]
  _BYTE v19[8]; // [rsp+48h] [rbp-38h] BYREF
  std::_Ref_count_base *v20; // [rsp+50h] [rbp-30h]
  _BYTE v21[32]; // [rsp+58h] [rbp-28h] BYREF

  if ( !Spectre::Engine::CommandList::Create(this, a2) )
  {
    Trace::LevelSettingsWrapper::Output(&gTraceLevelsCommandListD3D11, 3, "Failed to create CommandList object");
    return 0;
  }
  v4 = (struct ID3D11DeviceChild **)((char *)this + 144);
  if ( !*((_QWORD *)this + 18) )
  {
    std::weak_ptr<Spectre::Engine::RenderDevice>::lock((char *)this + 72, v19);
    v5 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
           v16,
           v19);
    Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(
      &v17,
      v5);
    Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v17, v16);
    v6 = (__int64 *)v16[0];
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v16[0] + 304LL))(v16[0]);
    v8 = *v6;
    v9 = (char *)this + 144;
    if ( (v7 & 1) != 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
      (*(void (__fastcall **)(__int64 *, char *))(v8 + 344))(v6, (char *)this + 144);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *))(v8 + 352))(v6, 0, (char *)this + 144);
      Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v17, v10);
      if ( v10 < 0 )
      {
        Trace::LevelSettingsWrapper::Output(
          &gTraceLevelsCommandListD3D11,
          3,
          "Failed to create DeferredContext with HRESULT error 0x%.8x",
          v10);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
        if ( v18 )
          std::_Ref_count_base::_Decref(v18);
        if ( v20 )
          std::_Ref_count_base::_Decref(v20);
        return 0;
      }
      Name = Spectre::Engine::RendererResource::GetName(this, v21);
      v12 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(Name);
      D3D11_SetDebugName(*v4, v12);
      std::string::_Tidy_deallocate(v21);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
  }
  v13 = (char *)this + 152;
  if ( *((_QWORD *)this + 19) )
    return 1;
  v14 = *v4;
  QueryInterface = v14->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
  return ((int (__fastcall *)(struct ID3D11DeviceChild *, GUID *, char *))QueryInterface)(
           v14,
           &GUID_b2daad8b_03d4_4dbf_95eb_32ab4b63d0ab,
           v13) >= 0;
}

```

## disassembly

```asm
0x1800bf6e0  mov     [rsp-18h+arg_10], rbx
0x1800bf6e5  mov     [rsp-18h+arg_18], rsi
0x1800bf6ea  push    rbp
0x1800bf6eb  push    rdi
0x1800bf6ec  push    r14
0x1800bf6ee  mov     rbp, rsp
0x1800bf6f1  sub     rsp, 80h
0x1800bf6f8  mov     rax, cs:__security_cookie
0x1800bf6ff  xor     rax, rsp
0x1800bf702  mov     [rbp+var_8], rax
0x1800bf706  mov     rbx, rcx
0x1800bf709  call    ?Create@CommandList@Engine@Spectre@@UEAA_NAEBVState@23@@Z; Spectre::Engine::CommandList::Create(Spectre::Engine::State const &)
0x1800bf70e  test    al, al
0x1800bf710  jnz     short loc_1800BF731
0x1800bf712  lea     r8, aFailedToCreate_0; "Failed to create CommandList object"
0x1800bf719  mov     edx, 3
0x1800bf71e  lea     rcx, ?gTraceLevelsCommandListD3D11@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsCommandListD3D11
0x1800bf725  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800bf72a  xor     al, al
0x1800bf72c  jmp     loc_1800BF8BB
0x1800bf731  lea     rdi, [rbx+90h]
0x1800bf738  cmp     qword ptr [rdi], 0
0x1800bf73c  jnz     loc_1800BF87E
0x1800bf742  lea     rcx, [rbx+48h]
0x1800bf746  lea     rdx, [rbp+var_38]
0x1800bf74a  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800bf74f  nop
0x1800bf750  lea     rdx, [rbp+var_38]
0x1800bf754  lea     rcx, [rbp+var_60]
0x1800bf758  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800bf75d  mov     rdx, rax
0x1800bf760  lea     rcx, [rbp+var_50]
0x1800bf764  call    ??$spectre_safe_pointer_cast@VRenderDeviceD3D11@D3D11@Engine@Spectre@@VRenderDevice@34@@Utils@Spectre@@YA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::RenderDeviceD3D11,Spectre::Engine::RenderDevice>(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x1800bf769  nop
0x1800bf76a  lea     rdx, [rbp+var_60]
0x1800bf76e  mov     rcx, [rbp+var_50]
0x1800bf772  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x1800bf777  nop
0x1800bf778  mov     rsi, [rbp+var_60]
0x1800bf77c  mov     rax, [rsi]
0x1800bf77f  mov     rcx, rsi
0x1800bf782  mov     rax, [rax+130h]
0x1800bf789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf78e  bt      eax, 0
0x1800bf792  mov     r14, [rsi]
0x1800bf795  mov     rcx, rdi
0x1800bf798  jnb     short loc_1800BF7B6
0x1800bf79a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bf79f  mov     rdx, rdi
0x1800bf7a2  mov     rcx, rsi
0x1800bf7a5  mov     rax, [r14+158h]
0x1800bf7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf7b1  jmp     loc_1800BF857
0x1800bf7b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bf7bb  mov     r8, rdi
0x1800bf7be  xor     edx, edx
0x1800bf7c0  mov     rcx, rsi
0x1800bf7c3  mov     rax, [r14+160h]
0x1800bf7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf7cf  mov     esi, eax
0x1800bf7d1  mov     edx, eax; int
0x1800bf7d3  mov     rcx, [rbp+var_50]; this
0x1800bf7d7  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800bf7dc  test    esi, esi
0x1800bf7de  jns     short loc_1800BF82C
0x1800bf7e0  mov     r9d, esi
0x1800bf7e3  lea     r8, aFailedToCreate; "Failed to create DeferredContext with H"...
0x1800bf7ea  mov     edx, 3
0x1800bf7ef  lea     rcx, ?gTraceLevelsCommandListD3D11@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsCommandListD3D11
0x1800bf7f6  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800bf7fb  nop
0x1800bf7fc  lea     rcx, [rbp+var_60]
0x1800bf800  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bf805  nop
0x1800bf806  mov     rcx, [rbp+var_48]; this
0x1800bf80a  test    rcx, rcx
0x1800bf80d  jz      short loc_1800BF815
0x1800bf80f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf814  nop
0x1800bf815  mov     rcx, [rbp+var_30]; this
0x1800bf819  test    rcx, rcx
0x1800bf81c  jz      loc_1800BF72A
0x1800bf822  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf827  jmp     loc_1800BF72A
0x1800bf82c  lea     rdx, [rbp+var_28]
0x1800bf830  mov     rcx, rbx
0x1800bf833  call    ?GetName@RendererResource@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::RendererResource::GetName(void)
0x1800bf838  nop
0x1800bf839  mov     rcx, rax
0x1800bf83c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800bf841  mov     rdx, rax; char *
0x1800bf844  mov     rcx, [rdi]; struct ID3D11DeviceChild *
0x1800bf847  call    ?D3D11_SetDebugName@@YAXPEAUID3D11DeviceChild@@PEBD@Z; D3D11_SetDebugName(ID3D11DeviceChild *,char const *)
0x1800bf84c  nop
0x1800bf84d  lea     rcx, [rbp+var_28]
0x1800bf851  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800bf856  nop
0x1800bf857  lea     rcx, [rbp+var_60]
0x1800bf85b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bf860  nop
0x1800bf861  mov     rcx, [rbp+var_48]; this
0x1800bf865  test    rcx, rcx
0x1800bf868  jz      short loc_1800BF870
0x1800bf86a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf86f  nop
0x1800bf870  mov     rcx, [rbp+var_30]; this
0x1800bf874  test    rcx, rcx
0x1800bf877  jz      short loc_1800BF87E
0x1800bf879  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf87e  lea     rsi, [rbx+98h]
0x1800bf885  cmp     qword ptr [rsi], 0
0x1800bf889  jnz     short loc_1800BF8B9
0x1800bf88b  mov     rdi, [rdi]
0x1800bf88e  mov     rax, [rdi]
0x1800bf891  mov     rbx, [rax]
0x1800bf894  mov     rcx, rsi
0x1800bf897  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bf89c  mov     r8, rsi
0x1800bf89f  lea     rdx, _GUID_b2daad8b_03d4_4dbf_95eb_32ab4b63d0ab
0x1800bf8a6  mov     rcx, rdi
0x1800bf8a9  mov     rax, rbx
0x1800bf8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf8b1  nop
0x1800bf8b2  test    eax, eax
0x1800bf8b4  setns   al
0x1800bf8b7  jmp     short loc_1800BF8BB
0x1800bf8b9  mov     al, 1
0x1800bf8bb  mov     rcx, [rbp+var_8]
0x1800bf8bf  xor     rcx, rsp; StackCookie
0x1800bf8c2  call    __security_check_cookie
0x1800bf8c7  lea     r11, [rsp+80h+var_s0]
0x1800bf8cf  mov     rbx, [r11+30h]
0x1800bf8d3  mov     rsi, [r11+38h]
0x1800bf8d7  mov     rsp, r11
0x1800bf8da  pop     r14
0x1800bf8dc  pop     rdi
0x1800bf8dd  pop     rbp
0x1800bf8de  retn
```
