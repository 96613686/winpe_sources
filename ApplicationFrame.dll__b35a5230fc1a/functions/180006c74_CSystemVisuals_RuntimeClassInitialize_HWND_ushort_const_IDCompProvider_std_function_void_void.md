# CSystemVisuals::RuntimeClassInitialize(HWND__ *,ushort const *,IDCompProvider *,std::function<void (void)>)

- ea: `0x180006c74`
- end: `0x180007005`
- name: `?RuntimeClassInitialize@CSystemVisuals@@QEAAJPEAUHWND__@@PEBGPEAUIDCompProvider@@V?$function@$$A6AXXZ@std@@@Z`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004ccac`

## callees

- `0x180004c98`
- `0x180006770`
- `0x180006928`
- `0x180006a5c`
- `0x180006b00`
- `0x180006c3c`
- `0x180006c74`
- `0x180007010`
- `0x180010478`
- `0x1800105f8`
- `0x180010728`
- `0x180010b58`
- `0x18001b644`
- `0x180041dec`
- `0x180043c30`
- `0x18004bb84`
- `0x180072010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x180006d8c`
- `d2d1!__imp_D2D1CreateFactory` at `0x180006d8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CSystemVisuals::RuntimeClassInitialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int ApartmentId; // eax
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  HRESULT v11; // eax
  void *v12; // rdi
  __int64 (__fastcall *v13)(void *, __int64, int *); // rbx
  int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64); // rdi
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, _BYTE *); // rcx
  _BYTE *v21; // rdx
  int v22; // eax
  __int64 v23; // rcx
  void *v24; // rcx
  __int64 v25; // rcx
  const char *v26; // r9
  __int64 result; // rax
  int v28[2]; // [rsp+20h] [rbp-208h] BYREF
  void *ppIFactory; // [rsp+28h] [rbp-200h] BYREF
  __int64 v30; // [rsp+30h] [rbp-1F8h] BYREF
  __int64 v31; // [rsp+38h] [rbp-1F0h]
  __int64 v32; // [rsp+40h] [rbp-1E8h]
  _BYTE v33[56]; // [rsp+50h] [rbp-1D8h] BYREF
  _BYTE *v34; // [rsp+88h] [rbp-1A0h]
  _QWORD v35[42]; // [rsp+90h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v31 = a2;
  v32 = a5;
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v35,
    "SystemVisualCreation");
  v35[0] = &SystemVisualTelemetry::SystemVisualCreation::`vftable';
  SystemVisualTelemetry::SystemVisualCreation::StartActivity((SystemVisualTelemetry::SystemVisualCreation *)v35);
  if ( (unsigned __int8)_ShouldCheckApartments(*(unsigned int *)(a1 + 84)) )
    ApartmentId = SHCoGetApartmentId((unsigned int *)(a1 + 80));
  else
    ApartmentId = 0;
  try
  {
    if ( ApartmentId < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)ApartmentId,
        v28[0]);
    v30 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
    v10 = v9(a4, &v30);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v10,
        v28[0]);
    ppIFactory = 0;
    *(_QWORD *)v28 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppIFactory);
    v11 = D2D1CreateFactory(
            D2D1_FACTORY_TYPE_SINGLE_THREADED,
            &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f,
            0,
            &ppIFactory);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v11,
        v28[0]);
    v12 = ppIFactory;
    v13 = *(__int64 (__fastcall **)(void *, __int64, int *))(*(_QWORD *)ppIFactory + 136LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v28);
    v14 = v13(v12, v30, v28);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v14,
        v28[0]);
    v15 = *(_QWORD *)v28;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(**(_QWORD **)v28 + 32LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 160);
    v17 = v16(v15, 0, a1 + 160);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v17,
        v28[0]);
    *(_QWORD *)(a1 + 88) = v31;
    v18 = std::_WChar_traits<unsigned short>::length(a3);
    std::wstring::_Assign<unsigned short>(a1 + 96, a3, v18);
    if ( *(_QWORD *)(a1 + 152) != a4 )
    {
      if ( a4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
      v19 = *(_QWORD *)(a1 + 152);
      *(_QWORD *)(a1 + 152) = a4;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v34 = 0;
    v20 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a5 + 56);
    if ( v20 )
      v34 = (_BYTE *)(**v20)(v20, v33);
    std::_Func_class<void,>::_Swap(v33, a1 + 216);
    if ( v34 )
    {
      v21 = v33;
      LOBYTE(v21) = v34 != v33;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v34 + 32LL))(v34, v21);
    }
    *(_QWORD *)(a1 + 204) = 0;
    v22 = Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>(a1 + 128);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v22,
        v28[0]);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v35);
    v23 = *(_QWORD *)v28;
    if ( *(_QWORD *)v28 )
    {
      *(_QWORD *)v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v35[0] = &SystemVisualTelemetry::SystemVisualCreation::`vftable';
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v35);
    std::_Func_class<void,>::_Tidy(a5);
    result = 0;
  }
  catch ( ... )
  {
    v28[0] = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0x2D,
               (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
               v26);
    std::_Func_class<void,>::_Tidy(v32);
    return (unsigned int)v28[0];
  }
  return result;
}

```

## disassembly

```asm
0x180006c74  push    rbx
0x180006c76  push    rsi
0x180006c77  push    rdi
0x180006c78  push    r12
0x180006c7a  push    r13
0x180006c7c  push    r14
0x180006c7e  push    r15
0x180006c80  sub     rsp, 1F0h
0x180006c87  mov     rax, cs:__security_cookie
0x180006c8e  xor     rax, rsp
0x180006c91  mov     [rsp+228h+var_48], rax
0x180006c99  mov     r15, r9
0x180006c9c  mov     r12, r8
0x180006c9f  mov     [rsp+228h+var_1F0], rdx
0x180006ca4  mov     r14, rcx
0x180006ca7  mov     r13, [rsp+228h+arg_20]
0x180006caf  mov     [rsp+228h+var_1E8], r13
0x180006cb4  lea     rdx, aSystemvisualcr; "SystemVisualCreation"
0x180006cbb  lea     rcx, [rsp+228h+var_198]
0x180006cc3  call    ??0?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180006cc8  lea     rax, ??_7SystemVisualCreation@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::SystemVisualCreation::`vftable'
0x180006ccf  mov     [rsp+228h+var_198], rax
0x180006cd7  lea     rcx, [rsp+228h+var_198]; this
0x180006cdf  call    ?StartActivity@SystemVisualCreation@SystemVisualTelemetry@@QEAAXXZ; SystemVisualTelemetry::SystemVisualCreation::StartActivity(void)
0x180006ce4  nop
0x180006ce5  mov     ecx, [r14+54h]
0x180006ce9  call    ?_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z; _ShouldCheckApartments(ApartmentCheckEnum)
0x180006cee  xor     esi, esi
0x180006cf0  test    al, al
0x180006cf2  jz      short loc_180006CFF
0x180006cf4  lea     rcx, [r14+50h]; unsigned int *
0x180006cf8  call    ?SHCoGetApartmentId@@YAJPEAK@Z; SHCoGetApartmentId(ulong *)
0x180006cfd  jmp     short loc_180006D01
0x180006cff  mov     eax, esi
0x180006d01  mov     rcx, [rsp+228h]; this
0x180006d09  test    eax, eax
0x180006d0b  jns     short loc_180006D21
0x180006d0d  mov     r9d, eax; char *
0x180006d10  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006d17  mov     edx, 15h; void *
0x180006d1c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006d21  mov     [rsp+228h+var_1F8], rsi
0x180006d26  mov     rax, [r15]
0x180006d29  mov     rbx, [rax+18h]
0x180006d2d  lea     rcx, [rsp+228h+var_1F8]
0x180006d32  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006d37  lea     rdx, [rsp+228h+var_1F8]
0x180006d3c  mov     rcx, r15
0x180006d3f  mov     rax, rbx
0x180006d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d47  mov     rcx, [rsp+228h]; this
0x180006d4f  test    eax, eax
0x180006d51  jns     short loc_180006D67
0x180006d53  mov     r9d, eax; char *
0x180006d56  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006d5d  mov     edx, 18h; void *
0x180006d62  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006d67  mov     [rsp+228h+ppIFactory], rsi
0x180006d6c  mov     qword ptr [rsp+228h+var_208], rsi; int
0x180006d71  lea     rcx, [rsp+228h+ppIFactory]
0x180006d76  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006d7b  lea     r9, [rsp+228h+ppIFactory]; ppIFactory
0x180006d80  xor     r8d, r8d; pFactoryOptions
0x180006d83  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x180006d8a  xor     ecx, ecx; factoryType
0x180006d8c  call    cs:__imp_D2D1CreateFactory
0x180006d92  mov     rcx, [rsp+228h]; this
0x180006d9a  test    eax, eax
0x180006d9c  jns     short loc_180006DB2
0x180006d9e  mov     r9d, eax; char *
0x180006da1  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006da8  mov     edx, 1Dh; void *
0x180006dad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006db2  mov     rdi, [rsp+228h+ppIFactory]
0x180006db7  mov     rax, [rdi]
0x180006dba  mov     rbx, [rax+88h]
0x180006dc1  lea     rcx, [rsp+228h+var_208]
0x180006dc6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006dcb  lea     r8, [rsp+228h+var_208]
0x180006dd0  mov     rdx, [rsp+228h+var_1F8]
0x180006dd5  mov     rcx, rdi
0x180006dd8  mov     rax, rbx
0x180006ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de0  mov     rcx, [rsp+228h]; this
0x180006de8  test    eax, eax
0x180006dea  jns     short loc_180006E00
0x180006dec  mov     r9d, eax; char *
0x180006def  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006df6  mov     edx, 1Eh; void *
0x180006dfb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006e00  mov     rsi, qword ptr [rsp+228h+var_208]
0x180006e05  mov     rax, [rsi]
0x180006e08  mov     rdi, [rax+20h]
0x180006e0c  lea     rbx, [r14+0A0h]
0x180006e13  mov     rcx, rbx
0x180006e16  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006e1b  mov     r8, rbx
0x180006e1e  xor     edx, edx
0x180006e20  mov     rcx, rsi
0x180006e23  mov     rax, rdi
0x180006e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2b  mov     rcx, [rsp+228h]; this
0x180006e33  xor     ebx, ebx
0x180006e35  test    eax, eax
0x180006e37  jns     short loc_180006E4B
0x180006e39  mov     r9d, eax; char *
0x180006e3c  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006e43  lea     edx, [rbx+1Fh]; void *
0x180006e46  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006e4b  mov     rax, [rsp+228h+var_1F0]
0x180006e50  mov     [r14+58h], rax
0x180006e54  mov     rcx, r12
0x180006e57  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006e5c  lea     rcx, [r14+60h]
0x180006e60  mov     r8, rax
0x180006e63  mov     rdx, r12
0x180006e66  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180006e6b  cmp     [r14+98h], r15
0x180006e72  jz      short loc_180006EA9
0x180006e74  test    r15, r15
0x180006e77  jz      short loc_180006E89
0x180006e79  mov     rax, [r15]
0x180006e7c  mov     rcx, r15
0x180006e7f  mov     rax, [rax+8]
0x180006e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e88  nop
0x180006e89  mov     rcx, [r14+98h]
0x180006e90  mov     [r14+98h], r15
0x180006e97  test    rcx, rcx
0x180006e9a  jz      short loc_180006EA9
0x180006e9c  mov     rax, [rcx]
0x180006e9f  mov     rax, [rax+10h]
0x180006ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea8  nop
0x180006ea9  mov     [rsp+228h+var_1A0], rbx
0x180006eb1  mov     rcx, [r13+38h]
0x180006eb5  test    rcx, rcx
0x180006eb8  jz      short loc_180006ED2
0x180006eba  mov     rax, [rcx]
0x180006ebd  lea     rdx, [rsp+228h+var_1D8]
0x180006ec2  mov     rax, [rax]
0x180006ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eca  mov     [rsp+228h+var_1A0], rax
0x180006ed2  lea     rdx, [r14+0D8h]
0x180006ed9  lea     rcx, [rsp+228h+var_1D8]
0x180006ede  call    ?_Swap@?$_Func_class@X$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<void,>::_Swap(std::_Func_class<void,> &)
0x180006ee3  mov     rcx, [rsp+228h+var_1A0]
0x180006eeb  test    rcx, rcx
0x180006eee  jz      short loc_180006F07
0x180006ef0  mov     rax, [rcx]
0x180006ef3  lea     rdx, [rsp+228h+var_1D8]
0x180006ef8  cmp     rcx, rdx
0x180006efb  setnz   dl
0x180006efe  mov     rax, [rax+20h]
0x180006f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f07  xor     eax, eax
0x180006f09  mov     [r14+0CCh], rax
0x180006f10  lea     rcx, [r14+80h]
0x180006f17  call    ??$MakeAndInitialize@VCreationThreadDispatcher@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCreationThreadDispatcher@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CreationThreadDispatcher>>)
0x180006f1c  mov     rcx, [rsp+228h]; this
0x180006f24  test    eax, eax
0x180006f26  jns     short loc_180006F3C
0x180006f28  mov     r9d, eax; char *
0x180006f2b  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x180006f32  mov     edx, 29h ; ')'; void *
0x180006f37  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006f3c  lea     rcx, [rsp+228h+var_198]
0x180006f44  call    ?Stop@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180006f49  nop
0x180006f4a  mov     rcx, qword ptr [rsp+228h+var_208]
0x180006f4f  test    rcx, rcx
0x180006f52  jz      short loc_180006F66
0x180006f54  mov     qword ptr [rsp+228h+var_208], rbx
0x180006f59  mov     rax, [rcx]
0x180006f5c  mov     rax, [rax+10h]
0x180006f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f65  nop
0x180006f66  mov     rcx, [rsp+228h+ppIFactory]
0x180006f6b  test    rcx, rcx
0x180006f6e  jz      short loc_180006F82
0x180006f70  mov     [rsp+228h+ppIFactory], rbx
0x180006f75  mov     rax, [rcx]
0x180006f78  mov     rax, [rax+10h]
0x180006f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f81  nop
0x180006f82  mov     rcx, [rsp+228h+var_1F8]
0x180006f87  test    rcx, rcx
0x180006f8a  jz      short loc_180006F9E
0x180006f8c  mov     [rsp+228h+var_1F8], rbx
0x180006f91  mov     rax, [rcx]
0x180006f94  mov     rax, [rax+10h]
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  nop
0x180006f9e  lea     rax, ??_7SystemVisualCreation@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::SystemVisualCreation::`vftable'
0x180006fa5  mov     [rsp+228h+var_198], rax
0x180006fad  lea     rcx, [rsp+228h+var_198]
0x180006fb5  call    ?Destroy@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180006fba  lea     rcx, [rsp+228h+var_198]
0x180006fc2  call    ??1?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180006fc7  nop
0x180006fc8  mov     rcx, r13
0x180006fcb  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180006fd0  xor     eax, eax
0x180006fd2  jmp     short loc_180006FE2
0x180006fd4  mov     rcx, [rsp+228h+var_1E8]
0x180006fd9  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180006fde  mov     eax, [rsp+228h+var_208]
0x180006fe2  mov     rcx, [rsp+228h+var_48]
0x180006fea  xor     rcx, rsp; StackCookie
0x180006fed  call    __security_check_cookie
0x180006ff2  add     rsp, 1F0h
0x180006ff9  pop     r15
0x180006ffb  pop     r14
0x180006ffd  pop     r13
0x180006fff  pop     r12
0x180007001  pop     rdi
0x180007002  pop     rsi
0x180007003  pop     rbx
0x180007004  retn
```
