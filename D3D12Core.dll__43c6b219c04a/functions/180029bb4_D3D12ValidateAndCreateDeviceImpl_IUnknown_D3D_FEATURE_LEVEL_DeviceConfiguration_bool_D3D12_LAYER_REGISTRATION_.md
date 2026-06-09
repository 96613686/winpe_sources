# D3D12ValidateAndCreateDeviceImpl(IUnknown *,D3D_FEATURE_LEVEL,DeviceConfiguration *,bool,D3D12_LAYER_REGISTRATION const *,unsigned __int64,_GUID const &,void * *)

- ea: `0x180029bb4`
- end: `0x180029e14`
- name: `?D3D12ValidateAndCreateDeviceImpl@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@PEAVDeviceConfiguration@@_NPEBUD3D12_LAYER_REGISTRATION@@_KAEBU_GUID@@PEAPEAX@Z`
- size: `608`
- prototype: `int(struct IUnknown *, enum D3D_FEATURE_LEVEL, struct DeviceConfiguration *, bool, const struct D3D12_LAYER_REGISTRATION *, unsigned __int64, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029b70`
- `0x1800c9680`

## callees

- `0x180003c84`
- `0x18000ac4c`
- `0x1800299a4`
- `0x180029af8`
- `0x180029b30`
- `0x180029bb4`
- `0x18002a41c`
- `0x18007703c`
- `0x1800c58a4`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180029d63`
- `msvcp_win!_Mtx_unlock` at `0x180029df3`
- `msvcp_win!_Mtx_unlock` at `0x180029d63`
- `msvcp_win!_Mtx_unlock` at `0x180029df3`

## string_xrefs

- `0x180029d38`: `D3D12CreateDevice: Unrecognized D3D_FEATURE_LEVEL (%#x) for MinimumFeatureLevel.`
- `0x180029c57`: `D3D12CreateDevice: MinimumFeatureLevel must be at least D3D_FEATURE_LEVEL_11_0, D3D_FEATURE_LEVEL_*_CORE or D3D_FEATURE_LEVEL_*_GENERIC for a D3D12 device.`
- `0x180029ce1`: `D3D12CreateDevice: pAdapter must support the IDXGIAdapter or IDXCoreAdapter interface.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall D3D12ValidateAndCreateDeviceImpl(
        struct IUnknown *a1,
        enum D3D_FEATURE_LEVEL a2,
        struct DeviceConfiguration *a3,
        char a4,
        const struct D3D12_LAYER_REGISTRATION *a5,
        unsigned __int64 a6,
        const struct _GUID *a7,
        void **a8)
{
  void **v12; // rdi
  std::_Mutex_base *v13; // rsi
  __int64 v14; // rdx
  int Device; // ebx
  _BYTE v17[8]; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v19; // [rsp+B0h] [rbp+40h] BYREF

  v12 = a8;
  if ( a8 )
    *a8 = 0;
  v13 = (std::_Mutex_base *)&g_Module;
  if ( !*((_BYTE *)a3 + 24) )
    v13 = (struct DeviceConfiguration *)((char *)a3 + 72);
  std::_Mutex_base::lock(v13);
  DebugPrintF::DebugPrintF((DebugPrintF *)v17, a3);
  if ( a2 > D3D_FEATURE_LEVEL_10_1 )
  {
    if ( a2 != D3D_FEATURE_LEVEL_11_0
      && a2 != D3D_FEATURE_LEVEL_11_1
      && a2 != D3D_FEATURE_LEVEL_12_0
      && a2 != D3D_FEATURE_LEVEL_12_1
      && a2 != (D3D_FEATURE_LEVEL_12_0|0x200) )
    {
      goto LABEL_24;
    }
  }
  else
  {
    switch ( a2 )
    {
      case 41216:
LABEL_13:
        DebugPrintF::operator()(
          v17,
          0,
          "D3D12CreateDevice: MinimumFeatureLevel must be at least D3D_FEATURE_LEVEL_11_0, D3D_FEATURE_LEVEL_*_CORE or D3"
          "D_FEATURE_LEVEL_*_GENERIC for a D3D12 device.");
        DebugPrintF::~DebugPrintF((DebugPrintF *)v17);
LABEL_25:
        _Mtx_unlock(v13);
        return 2147942487LL;
      case 256:
        LOBYTE(v14) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12GenericFeatureLevel>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_D3D12GenericFeatureLevel>::GetImpl'::`2'::impl,
          v14);
        break;
      case 4096:
        break;
      case 37120:
      case 37376:
      case 37632:
      case 40960:
        goto LABEL_13;
      default:
LABEL_24:
        DebugPrintF::operator()(
          v17,
          0,
          "D3D12CreateDevice: Unrecognized D3D_FEATURE_LEVEL (%#x) for MinimumFeatureLevel.",
          a2);
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v18);
        D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)v17, 0);
        goto LABEL_25;
    }
  }
  v19 = 0;
  a8 = 0;
  if ( a1
    && a1->QueryInterface(a1, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, (void **)&v19) < 0
    && a1->QueryInterface(a1, &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e, (void **)&a8) < 0 )
  {
    DebugPrintF::operator()(
      v17,
      0,
      "D3D12CreateDevice: pAdapter must support the IDXGIAdapter or IDXCoreAdapter interface.");
    Device = -2147024809;
  }
  else
  {
    Device = D3D12CoreCreateDevice(a1, a2, (int **)a3, a4, (struct DebugPrintF *)v17, a5, a6, a7, v12);
    if ( Device < 0 && v12 && *v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)*v12 + 16LL))(*v12);
      *v12 = 0;
    }
  }
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&a8);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v19);
  DebugPrintF::~DebugPrintF((DebugPrintF *)v17);
  _Mtx_unlock(v13);
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x180029bb4  mov     [rsp-28h+arg_0], rbx
0x180029bb9  mov     [rsp-28h+arg_8], rsi
0x180029bbe  push    rbp
0x180029bbf  push    rdi
0x180029bc0  push    r12
0x180029bc2  push    r14
0x180029bc4  push    r15
0x180029bc6  mov     rbp, rsp
0x180029bc9  sub     rsp, 70h
0x180029bcd  mov     r12b, r9b
0x180029bd0  mov     r14, r8
0x180029bd3  mov     ebx, edx
0x180029bd5  mov     r15, rcx
0x180029bd8  mov     rdi, [rbp+arg_38]
0x180029bdc  test    rdi, rdi
0x180029bdf  jz      short loc_180029BE8
0x180029be1  mov     qword ptr [rdi], 0
0x180029be8  cmp     byte ptr [r8+18h], 0
0x180029bed  lea     rsi, ?g_Module@@3VCModule@@A; CModule g_Module
0x180029bf4  jnz     short loc_180029BFA
0x180029bf6  lea     rsi, [r8+48h]
0x180029bfa  mov     [rbp+var_20], rsi
0x180029bfe  mov     rcx, rsi; this
0x180029c01  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180029c06  nop
0x180029c07  mov     rdx, r14; struct DeviceConfiguration *
0x180029c0a  lea     rcx, [rbp+var_18]; this
0x180029c0e  call    ??0DebugPrintF@@QEAA@PEAVDeviceConfiguration@@@Z; DebugPrintF::DebugPrintF(DeviceConfiguration *)
0x180029c13  nop
0x180029c14  mov     eax, 0A100h
0x180029c19  cmp     ebx, eax
0x180029c1b  jg      loc_180029CFD
0x180029c21  jz      short loc_180029C57
0x180029c23  cmp     ebx, 100h
0x180029c29  jz      short loc_180029C78
0x180029c2b  cmp     ebx, 1000h
0x180029c31  jz      short loc_180029C86
0x180029c33  cmp     ebx, 9100h
0x180029c39  jz      short loc_180029C57
0x180029c3b  cmp     ebx, 9200h
0x180029c41  jz      short loc_180029C57
0x180029c43  cmp     ebx, 9300h
0x180029c49  jz      short loc_180029C57
0x180029c4b  cmp     ebx, 0A000h
0x180029c51  jnz     loc_180029D35
0x180029c57  lea     r8, aD3d12createdev; "D3D12CreateDevice: MinimumFeatureLevel "...
0x180029c5e  xor     edx, edx
0x180029c60  lea     rcx, [rbp+var_18]
0x180029c64  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x180029c69  nop
0x180029c6a  lea     rcx, [rbp+var_18]; this
0x180029c6e  call    ??1DebugPrintF@@QEAA@XZ; DebugPrintF::~DebugPrintF(void)
0x180029c73  jmp     loc_180029D60
0x180029c78  mov     dl, 1
0x180029c7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12GenericFeatureLevel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12GenericFeatureLevel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12GenericFeatureLevel> `wil::Feature<__WilFeatureTraits_Feature_D3D12GenericFeatureLevel>::GetImpl(void)'::`2'::impl
0x180029c81  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12GenericFeatureLevel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12GenericFeatureLevel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029c86  mov     [rbp+arg_10], 0
0x180029c8e  mov     [rbp+arg_38], 0
0x180029c96  test    r15, r15
0x180029c99  jz      loc_180029D73
0x180029c9f  mov     rax, [r15]
0x180029ca2  lea     r8, [rbp+arg_10]
0x180029ca6  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180029cad  mov     rcx, r15
0x180029cb0  mov     rax, [rax]
0x180029cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cb8  test    eax, eax
0x180029cba  jns     loc_180029D73
0x180029cc0  mov     rax, [r15]
0x180029cc3  lea     r8, [rbp+arg_38]
0x180029cc7  lea     rdx, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x180029cce  mov     rcx, r15
0x180029cd1  mov     rax, [rax]
0x180029cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cd9  test    eax, eax
0x180029cdb  jns     loc_180029D73
0x180029ce1  lea     r8, aD3d12createdev_0; "D3D12CreateDevice: pAdapter must suppor"...
0x180029ce8  xor     edx, edx
0x180029cea  lea     rcx, [rbp+var_18]
0x180029cee  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x180029cf3  mov     ebx, 80070057h
0x180029cf8  jmp     loc_180029DD2
0x180029cfd  cmp     ebx, 0B000h
0x180029d03  jz      short loc_180029C86
0x180029d05  cmp     ebx, 0B100h
0x180029d0b  jz      loc_180029C86
0x180029d11  cmp     ebx, 0C000h
0x180029d17  jz      loc_180029C86
0x180029d1d  cmp     ebx, 0C100h
0x180029d23  jz      loc_180029C86
0x180029d29  cmp     ebx, 0C200h
0x180029d2f  jz      loc_180029C86
0x180029d35  mov     r9d, ebx
0x180029d38  lea     r8, aD3d12createdev_1; "D3D12CreateDevice: Unrecognized D3D_FEA"...
0x180029d3f  xor     edx, edx
0x180029d41  lea     rcx, [rbp+var_18]
0x180029d45  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x180029d4a  nop
0x180029d4b  lea     rcx, [rbp+var_10]
0x180029d4f  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180029d54  xor     edx, edx; HINSTANCE
0x180029d56  lea     rcx, [rbp+var_18]; this
0x180029d5a  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x180029d5f  nop
0x180029d60  mov     rcx, rsi; _Mtx_t
0x180029d63  call    cs:__imp__Mtx_unlock
0x180029d69  mov     eax, 80070057h
0x180029d6e  jmp     loc_180029DFB
0x180029d73  mov     [rsp+70h+var_30], rdi; void **
0x180029d78  mov     rax, [rbp+arg_30]
0x180029d7c  mov     [rsp+70h+var_38], rax; struct _GUID *
0x180029d81  mov     rax, [rbp+arg_28]
0x180029d85  mov     [rsp+70h+var_40], rax; unsigned __int64
0x180029d8a  mov     rax, [rbp+arg_20]
0x180029d8e  mov     [rsp+70h+var_48], rax; struct D3D12_LAYER_REGISTRATION *
0x180029d93  lea     rax, [rbp+var_18]
0x180029d97  mov     [rsp+70h+var_50], rax; struct DebugPrintF *
0x180029d9c  mov     r9b, r12b; bool
0x180029d9f  mov     r8, r14; struct DeviceConfiguration *
0x180029da2  mov     edx, ebx; enum D3D_FEATURE_LEVEL
0x180029da4  mov     rcx, r15; struct IUnknown *
0x180029da7  call    ?D3D12CoreCreateDevice@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@PEAVDeviceConfiguration@@_NAEAVDebugPrintF@@PEBUD3D12_LAYER_REGISTRATION@@_KAEBU_GUID@@PEAPEAX@Z; D3D12CoreCreateDevice(IUnknown *,D3D_FEATURE_LEVEL,DeviceConfiguration *,bool,DebugPrintF &,D3D12_LAYER_REGISTRATION const *,unsigned __int64,_GUID const &,void * *)
0x180029dac  mov     ebx, eax
0x180029dae  test    eax, eax
0x180029db0  jns     short loc_180029DD2
0x180029db2  test    rdi, rdi
0x180029db5  jz      short loc_180029DD2
0x180029db7  mov     rcx, [rdi]
0x180029dba  test    rcx, rcx
0x180029dbd  jz      short loc_180029DD2
0x180029dbf  mov     rdx, [rcx]
0x180029dc2  mov     rax, [rdx+10h]
0x180029dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dcb  mov     qword ptr [rdi], 0
0x180029dd2  lea     rcx, [rbp+arg_38]
0x180029dd6  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180029ddb  nop
0x180029ddc  lea     rcx, [rbp+arg_10]
0x180029de0  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180029de5  nop
0x180029de6  lea     rcx, [rbp+var_18]; this
0x180029dea  call    ??1DebugPrintF@@QEAA@XZ; DebugPrintF::~DebugPrintF(void)
0x180029def  nop
0x180029df0  mov     rcx, rsi; _Mtx_t
0x180029df3  call    cs:__imp__Mtx_unlock
0x180029df9  mov     eax, ebx
0x180029dfb  lea     r11, [rsp+70h+var_s0]
0x180029e00  mov     rbx, [r11+30h]
0x180029e04  mov     rsi, [r11+38h]
0x180029e08  mov     rsp, r11
0x180029e0b  pop     r15
0x180029e0d  pop     r14
0x180029e0f  pop     r12
0x180029e11  pop     rdi
0x180029e12  pop     rbp
0x180029e13  retn
```
