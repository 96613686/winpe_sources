# Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(IDXGIAdapter3 *)

- ea: `0x180023578`
- end: `0x18002391c`
- name: `??0CRenderDevice@Graphics@Utils@Rdp@@QEAA@PEAUIDXGIAdapter3@@@Z`
- size: `932`
- prototype: `_QWORD(Rdp::Utils::Graphics::CRenderDevice *__hidden this, struct IDXGIAdapter3 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024a28`

## callees

- `0x180001cec`
- `0x180002590`
- `0x180006f60`
- `0x180007b38`
- `0x18000d614`
- `0x18000ead8`
- `0x18001ddf4`
- `0x18002142c`
- `0x180021570`
- `0x180023578`
- `0x18003f010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x1800236c2`
- `d3d11!D3D11CreateDevice` at `0x1800236c2`

## string_xrefs

- `0x1800235e0`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RenderAdapter.h`
- `0x1800236d5`: `D3D11CreateDevice failed`
- `0x1800237bb`: `Render device created`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Rdp::Utils::Graphics::CRenderDevice *__fastcall Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(
        Rdp::Utils::Graphics::CRenderDevice *this,
        IDXGIAdapter *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  ID3D11DeviceContext *v7; // rcx
  ID3D11Device *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  _DWORD *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  ID3D11Device *v14; // rax
  __int64 v15; // rcx
  ID3D11DeviceContext *v16; // rax
  __int64 v17; // rcx
  const char *FeatureLevelsa; // [rsp+28h] [rbp-F8h]
  const char *FeatureLevelsb; // [rsp+28h] [rbp-F8h]
  UINT FeatureLevels[2]; // [rsp+28h] [rbp-F8h]
  int v22; // [rsp+A0h] [rbp-80h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+A8h] [rbp-78h] BYREF
  ID3D11Device *ppDevice; // [rsp+B0h] [rbp-70h] BYREF
  int v25; // [rsp+B8h] [rbp-68h] BYREF
  int v26; // [rsp+BCh] [rbp-64h] BYREF
  int v27; // [rsp+C0h] [rbp-60h] BYREF
  int v28; // [rsp+C4h] [rbp-5Ch] BYREF
  int v29; // [rsp+C8h] [rbp-58h] BYREF
  int v30; // [rsp+CCh] [rbp-54h] BYREF
  const char *v31; // [rsp+D0h] [rbp-50h] BYREF
  const char *v32; // [rsp+D8h] [rbp-48h] BYREF
  const char *v33; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+E8h] [rbp-38h] BYREF
  _BYTE *v35; // [rsp+F0h] [rbp-30h] BYREF
  const char *v36; // [rsp+F8h] [rbp-28h] BYREF
  const char *v37; // [rsp+100h] [rbp-20h] BYREF
  _QWORD v38[3]; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v39[256]; // [rsp+120h] [rbp+0h] BYREF
  int v40; // [rsp+220h] [rbp+100h]
  int v41; // [rsp+224h] [rbp+104h]
  int v42; // [rsp+228h] [rbp+108h]
  int v43; // [rsp+22Ch] [rbp+10Ch]
  int v44; // [rsp+230h] [rbp+110h]
  int v45; // [rsp+238h] [rbp+118h]
  int v46; // [rsp+240h] [rbp+120h]
  __int64 v47; // [rsp+248h] [rbp+128h]
  int v48; // [rsp+250h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+178h]

  v38[1] = this;
  *(_QWORD *)this = &Rdp::Utils::Graphics::CRenderDevice::`vftable';
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  ppDevice = 0;
  ppImmediateContext = 0;
  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u )
  {
    v33 = "Creating render device";
    v32 = "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice";
    v22 = 104;
    v31 = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)v4,
      (unsigned int)byte_18004EA65,
      v5,
      v6,
      (__int64)&v31,
      (__int64)&v22,
      (__int64)&v32,
      (__int64)&v33);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"Creating render device",
    "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x69u);
  v7 = ppImmediateContext;
  ppImmediateContext = 0;
  if ( v7 )
    ((void (__fastcall *)(ID3D11DeviceContext *))v7->lpVtbl->Release)(v7);
  v8 = ppDevice;
  ppDevice = 0;
  if ( v8 )
    ((void (__fastcall *)(ID3D11Device *))v8->lpVtbl->Release)(v8);
  v9 = D3D11CreateDevice(a2, D3D_DRIVER_TYPE_UNKNOWN, 0, 0x20u, 0, 0, 7u, &ppDevice, 0, &ppImmediateContext);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x77,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v9,
    (int)"D3D11CreateDevice failed",
    FeatureLevelsa);
  memset_0(v39, 0, 0x140u);
  v10 = ((__int64 (__fastcall *)(IDXGIAdapter *, _BYTE *))a2->lpVtbl[1].AddRef)(a2, v39);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v10,
    (int)"Failed to get DXGI adapter description",
    FeatureLevelsb);
  *((_BYTE *)this + 8) = (v48 & 2) != 0;
  v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v11 > 4u )
  {
    v22 = *((unsigned __int8 *)this + 8);
    v34 = v47;
    v25 = v48;
    v26 = v46;
    v27 = v45;
    v28 = v44;
    v29 = v43;
    v30 = v42;
    LODWORD(v31) = v41;
    LODWORD(v32) = v40;
    v35 = v39;
    v36 = "Render device created";
    v37 = "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice";
    LODWORD(v33) = 142;
    v38[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v11,
      (unsigned int)&dword_18004EA9C,
      v12,
      v13,
      (__int64)v38,
      (__int64)&v33,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v34,
      (__int64)&v22);
  }
  FeatureLevels[0] = *((unsigned __int8 *)this + 8);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RenderDevice: IsWarp: %d",
    "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x8Fu,
    *(_QWORD *)FeatureLevels);
  v14 = ppDevice;
  ppDevice = 0;
  v15 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v14;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = ppImmediateContext;
  ppImmediateContext = 0;
  v17 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v16;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&ppImmediateContext);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&ppDevice);
  return this;
}

```

## disassembly

```asm
0x180023578  mov     [rsp-8+arg_10], rbx
0x18002357d  push    rbp
0x18002357e  push    rsi
0x18002357f  push    rdi
0x180023580  push    r14
0x180023582  push    r15
0x180023584  lea     rbp, [rsp-150h]
0x18002358c  sub     rsp, 270h
0x180023593  mov     rax, cs:__security_cookie
0x18002359a  xor     rax, rsp
0x18002359d  mov     [rbp+170h+var_30], rax
0x1800235a4  mov     rdi, rdx
0x1800235a7  mov     rbx, rcx
0x1800235aa  mov     [rbp+170h+var_180], rcx
0x1800235ae  lea     rax, ??_7CRenderDevice@Graphics@Utils@Rdp@@6B@; const Rdp::Utils::Graphics::CRenderDevice::`vftable'
0x1800235b5  mov     [rcx], rax
0x1800235b8  xor     esi, esi
0x1800235ba  mov     [rcx+8], sil
0x1800235be  mov     [rcx+10h], rsi
0x1800235c2  mov     [rcx+18h], rsi
0x1800235c6  mov     [rbp+170h+var_1E0], rsi
0x1800235ca  mov     [rbp+170h+var_1E8], rsi
0x1800235ce  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800235d3  mov     rcx, [rax+8]
0x1800235d7  mov     eax, [rcx]
0x1800235d9  lea     r15, aRdpUtilsGraphi_0; "Rdp::Utils::Graphics::CRenderDevice::CR"...
0x1800235e0  lea     r14, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800235e7  cmp     eax, 4
0x1800235ea  jbe     short loc_180023636
0x1800235ec  lea     rax, aCreatingRender; "Creating render device"
0x1800235f3  mov     [rbp+170h+var_1B0], rax
0x1800235f7  mov     [rbp+170h+var_1B8], r15
0x1800235fb  mov     [rbp+170h+var_1F0], 68h ; 'h'
0x180023602  mov     [rbp+170h+var_1C0], r14
0x180023606  lea     rax, [rbp+170h+var_1B0]
0x18002360a  mov     [rsp+290h+ppDevice], rax
0x18002360f  lea     rax, [rbp+170h+var_1B8]
0x180023613  mov     qword ptr [rsp+290h+SDKVersion], rax
0x180023618  lea     rax, [rbp+170h+var_1F0]
0x18002361c  mov     qword ptr [rsp+290h+FeatureLevels], rax
0x180023621  lea     rax, [rbp+170h+var_1C0]
0x180023625  mov     [rsp+290h+pFeatureLevels], rax
0x18002362a  lea     rdx, byte_18004EA65
0x180023631  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180023636  mov     dword ptr [rsp+290h+pFeatureLevels], 69h ; 'i'; unsigned int
0x18002363e  mov     r9, r14; char *
0x180023641  mov     r8, r15; char *
0x180023644  lea     rdx, aCreatingRender_1; "Creating render device"
0x18002364b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180023652  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180023657  nop
0x180023658  mov     rcx, [rbp+170h+var_1E8]
0x18002365c  mov     [rbp+170h+var_1E8], rsi
0x180023660  test    rcx, rcx
0x180023663  jz      short loc_180023672
0x180023665  mov     rax, [rcx]
0x180023668  mov     rax, [rax+10h]
0x18002366c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023671  nop
0x180023672  mov     rcx, [rbp+170h+var_1E0]
0x180023676  mov     [rbp+170h+var_1E0], rsi
0x18002367a  test    rcx, rcx
0x18002367d  jz      short loc_18002368C
0x18002367f  mov     rax, [rcx]
0x180023682  mov     rax, [rax+10h]
0x180023686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002368b  nop
0x18002368c  lea     rax, [rbp+170h+var_1E8]
0x180023690  mov     [rsp+290h+ppImmediateContext], rax; ppImmediateContext
0x180023695  mov     [rsp+290h+pFeatureLevel], rsi; pFeatureLevel
0x18002369a  lea     rax, [rbp+170h+var_1E0]
0x18002369e  mov     [rsp+290h+ppDevice], rax; ppDevice
0x1800236a3  mov     [rsp+290h+SDKVersion], 7; SDKVersion
0x1800236ab  mov     [rsp+290h+FeatureLevels], esi; char *
0x1800236af  mov     [rsp+290h+pFeatureLevels], rsi; pFeatureLevels
0x1800236b4  mov     r9d, 20h ; ' '; Flags
0x1800236ba  xor     r8d, r8d; Software
0x1800236bd  xor     edx, edx; DriverType
0x1800236bf  mov     rcx, rdi; pAdapter
0x1800236c2  call    cs:__imp_D3D11CreateDevice
0x1800236c9  nop     dword ptr [rax+rax+00h]
0x1800236ce  mov     rcx, [rbp+178h]; this
0x1800236d5  lea     rdx, aD3d11createdev; "D3D11CreateDevice failed"
0x1800236dc  mov     [rsp+290h+pFeatureLevels], rdx; int
0x1800236e1  mov     r9d, eax; char *
0x1800236e4  mov     r8, r14; unsigned int
0x1800236e7  mov     edx, 77h ; 'w'; void *
0x1800236ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800236f1  xor     edx, edx; Val
0x1800236f3  mov     r8d, 140h; Size
0x1800236f9  lea     rcx, [rbp+170h+var_170]; void *
0x1800236fd  call    memset_0
0x180023702  mov     rax, [rdi]
0x180023705  lea     rdx, [rbp+170h+var_170]
0x180023709  mov     rcx, rdi
0x18002370c  mov     rax, [rax+58h]
0x180023710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023715  mov     rcx, [rbp+178h]; this
0x18002371c  lea     rdx, aFailedToGetDxg; "Failed to get DXGI adapter description"
0x180023723  mov     [rsp+290h+pFeatureLevels], rdx; int
0x180023728  mov     r9d, eax; char *
0x18002372b  mov     r8, r14; unsigned int
0x18002372e  mov     edx, 7Eh ; '~'; void *
0x180023733  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023738  mov     eax, [rbp+170h+var_40]
0x18002373e  shr     eax, 1
0x180023740  and     al, 1
0x180023742  mov     [rbx+8], al
0x180023745  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002374a  mov     rcx, [rax+8]
0x18002374e  mov     eax, [rcx]
0x180023750  cmp     eax, 4
0x180023753  jbe     loc_180023871
0x180023759  movzx   eax, byte ptr [rbx+8]
0x18002375d  mov     [rbp+170h+var_1F0], eax
0x180023760  mov     rax, [rbp+170h+var_48]
0x180023767  mov     [rbp+170h+var_1A8], rax
0x18002376b  mov     eax, [rbp+170h+var_40]
0x180023771  mov     [rbp+170h+var_1D8], eax
0x180023774  mov     eax, [rbp+170h+var_50]
0x18002377a  mov     [rbp+170h+var_1D4], eax
0x18002377d  mov     eax, [rbp+170h+var_58]
0x180023783  mov     [rbp+170h+var_1D0], eax
0x180023786  mov     eax, [rbp+170h+var_60]
0x18002378c  mov     [rbp+170h+var_1CC], eax
0x18002378f  mov     eax, [rbp+170h+var_64]
0x180023795  mov     [rbp+170h+var_1C8], eax
0x180023798  mov     eax, [rbp+170h+var_68]
0x18002379e  mov     [rbp+170h+var_1C4], eax
0x1800237a1  mov     eax, [rbp+170h+var_6C]
0x1800237a7  mov     dword ptr [rbp+170h+var_1C0], eax
0x1800237aa  mov     eax, [rbp+170h+var_70]
0x1800237b0  mov     dword ptr [rbp+170h+var_1B8], eax
0x1800237b3  lea     rax, [rbp+170h+var_170]
0x1800237b7  mov     [rbp+170h+var_1A0], rax
0x1800237bb  lea     rax, aRenderDeviceCr; "Render device created"
0x1800237c2  mov     [rbp+170h+var_198], rax
0x1800237c6  mov     [rbp+170h+var_190], r15
0x1800237ca  mov     dword ptr [rbp+170h+var_1B0], 8Eh
0x1800237d1  mov     [rbp+170h+var_188], r14
0x1800237d5  lea     rax, [rbp+170h+var_1F0]
0x1800237d9  mov     [rsp+290h+var_200], rax
0x1800237e1  lea     rax, [rbp+170h+var_1A8]
0x1800237e5  mov     [rsp+290h+var_208], rax
0x1800237ed  lea     rax, [rbp+170h+var_1D8]
0x1800237f1  mov     [rsp+290h+var_210], rax
0x1800237f9  lea     rax, [rbp+170h+var_1D4]
0x1800237fd  mov     [rsp+290h+var_218], rax
0x180023802  lea     rax, [rbp+170h+var_1D0]
0x180023806  mov     [rsp+290h+var_220], rax
0x18002380b  lea     rax, [rbp+170h+var_1CC]
0x18002380f  mov     [rsp+290h+var_228], rax
0x180023814  lea     rax, [rbp+170h+var_1C8]
0x180023818  mov     [rsp+290h+var_230], rax
0x18002381d  lea     rax, [rbp+170h+var_1C4]
0x180023821  mov     [rsp+290h+var_238], rax
0x180023826  lea     rax, [rbp+170h+var_1C0]
0x18002382a  mov     [rsp+290h+var_240], rax
0x18002382f  lea     rax, [rbp+170h+var_1B8]
0x180023833  mov     [rsp+290h+ppImmediateContext], rax
0x180023838  lea     rax, [rbp+170h+var_1A0]
0x18002383c  mov     [rsp+290h+pFeatureLevel], rax
0x180023841  lea     rax, [rbp+170h+var_198]
0x180023845  mov     [rsp+290h+ppDevice], rax
0x18002384a  lea     rax, [rbp+170h+var_190]
0x18002384e  mov     qword ptr [rsp+290h+SDKVersion], rax
0x180023853  lea     rax, [rbp+170h+var_1B0]
0x180023857  mov     qword ptr [rsp+290h+FeatureLevels], rax
0x18002385c  lea     rax, [rbp+170h+var_188]
0x180023860  mov     [rsp+290h+pFeatureLevels], rax
0x180023865  lea     rdx, dword_18004EA9C
0x18002386c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@44444444AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180023871  movzx   eax, byte ptr [rbx+8]
0x180023875  mov     [rsp+290h+FeatureLevels], eax
0x180023879  mov     dword ptr [rsp+290h+pFeatureLevels], 8Fh; unsigned int
0x180023881  mov     r9, r14; char *
0x180023884  mov     r8, r15; char *
0x180023887  lea     rdx, aRenderdeviceIs; "RenderDevice: IsWarp: %d"
0x18002388e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180023895  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002389a  mov     rax, [rbp+170h+var_1E0]
0x18002389e  mov     [rbp+170h+var_1E0], rsi
0x1800238a2  mov     rcx, [rbx+10h]
0x1800238a6  mov     [rbx+10h], rax
0x1800238aa  test    rcx, rcx
0x1800238ad  jz      short loc_1800238BC
0x1800238af  mov     rax, [rcx]
0x1800238b2  mov     rax, [rax+10h]
0x1800238b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238bb  nop
0x1800238bc  mov     rax, [rbp+170h+var_1E8]
0x1800238c0  mov     [rbp+170h+var_1E8], rsi
0x1800238c4  mov     rcx, [rbx+18h]
0x1800238c8  mov     [rbx+18h], rax
0x1800238cc  test    rcx, rcx
0x1800238cf  jz      short loc_1800238DE
0x1800238d1  mov     rax, [rcx]
0x1800238d4  mov     rax, [rax+10h]
0x1800238d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238dd  nop
0x1800238de  lea     rcx, [rbp+170h+var_1E8]
0x1800238e2  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800238e7  nop
0x1800238e8  lea     rcx, [rbp+170h+var_1E0]
0x1800238ec  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800238f1  nop
0x1800238f2  mov     rax, rbx
0x1800238f5  mov     rcx, [rbp+170h+var_30]
0x1800238fc  xor     rcx, rsp; StackCookie
0x1800238ff  call    __security_check_cookie
0x180023904  mov     rbx, [rsp+290h+arg_10]
0x18002390c  add     rsp, 270h
0x180023913  pop     r15
0x180023915  pop     r14
0x180023917  pop     rdi
0x180023918  pop     rsi
0x180023919  pop     rbp
0x18002391a  retn
```
