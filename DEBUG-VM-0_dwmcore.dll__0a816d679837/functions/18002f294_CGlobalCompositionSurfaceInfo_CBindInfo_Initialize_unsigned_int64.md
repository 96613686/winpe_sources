# CGlobalCompositionSurfaceInfo::CBindInfo::Initialize(unsigned __int64)

- ea: `0x18002f294`
- end: `0x18002f630`
- name: `?Initialize@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAJ_K@Z`
- size: `924`
- prototype: `__int64 __fastcall(CGlobalCompositionSurfaceInfo::CBindInfo *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e3d0`
- `0x18002e610`

## callees

- `0x18000a254`
- `0x18000a7f4`
- `0x18002f0e0`
- `0x18002f294`
- `0x18002f690`
- `0x180030350`
- `0x180030848`
- `0x180030af4`
- `0x180030b20`
- `0x180030e88`
- `0x180030f0c`
- `0x180042de0`
- `0x1801cc6a8`
- `0x180228490`
- `0x18022943c`
- `0x18025b328`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5be`
- `win32u!NtQueryCompositionSurfaceBinding` at `0x18002f305`
- `win32u!NtQueryCompositionSurfaceBinding` at `0x18002f305`

## pseudocode

```c
__int64 __fastcall CGlobalCompositionSurfaceInfo::CBindInfo::Initialize(
        CGlobalCompositionSurfaceInfo::CBindInfo *this,
        __int64 a2)
{
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  _DWORD *v7; // r14
  int v8; // edi
  int v9; // r8d
  int v10; // r8d
  char *v11; // rbx
  const struct CCompositionSurfaceInfo *v12; // rcx
  int v13; // eax
  struct CFlipExSwapchainStatistics *v14; // rdx
  int v15; // eax
  unsigned int v17; // r8d
  int v18; // eax
  const struct CGlobalCompositionSurfaceInfo *v19; // rcx
  int v20; // eax
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  struct CFlipExSwapchainStatistics *v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[144]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+F4h] [rbp-Ch]
  HANDLE hObject; // [rsp+4D8h] [rbp+3D8h]
  unsigned __int64 v30; // [rsp+4E0h] [rbp+3E0h]
  unsigned __int16 v31[64]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v23 = a2;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
    McTemplateU0xx_EventWriteTransfer(this, &CompSurfInfo_Binding_Start, *(_QWORD *)(*(_QWORD *)this + 40LL), a2);
  memset_0(v25, 0, 0x520u);
  if ( *((_QWORD *)this + 3) )
    CGlobalCompositionSurfaceInfo::CBindInfo::Reset(this, 0);
  v3 = NtQueryCompositionSurfaceBinding(*(_QWORD *)(*(_QWORD *)this + 32LL), &v23, v25);
  if ( v3 < 0 )
  {
    v8 = v3 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, v3 | 0x10000000, 0x3C2u, 0);
    v7 = (_DWORD *)((char *)this + 32);
    goto LABEL_17;
  }
  v6 = v25[0];
  v7 = (_DWORD *)((char *)this + 32);
  v8 = 0;
  *((_QWORD *)this + 3) = v23;
  *((_DWORD *)this + 8) = v6;
  if ( v6 )
  {
    v9 = v6 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
          v8 = -2147024809;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, -2147024809, 0x406u, 0);
          goto LABEL_26;
        }
        v11 = (char *)hObject;
        v12 = *(const struct CCompositionSurfaceInfo **)this;
        v24[0] = hObject;
        v22 = 0;
        v13 = CCompositionSwapchainStatistics::Create(v12, hObject, v30, &v22);
        v8 = v13;
        if ( v13 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, v13, 0x3F4u, 0);
          if ( v22 )
            (*(void (__fastcall **)(struct CFlipExSwapchainStatistics *))(*(_QWORD *)v22 + 16LL))(v22);
          if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v11);
          goto LABEL_26;
        }
        v14 = v22;
        v22 = 0;
        wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(
          (char *)this + 16,
          v14);
        v15 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
                this,
                (const struct CSM_BUFFER_ATTRIBUTES *)v26,
                v28);
        v8 = v15;
        if ( v15 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, v15, 0x3F8u, 0);
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v22);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v24);
          goto LABEL_26;
        }
        CGlobalCompositionSurfaceInfo::CBindInfo::CheckBufferHomogeneity(this);
        CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(this, v31);
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v11);
        goto LABEL_14;
      }
      v17 = v28;
      if ( v28 > 1 )
      {
        v19 = *(const struct CGlobalCompositionSurfaceInfo **)this;
        v22 = 0;
        v20 = CFlipExSwapchainStatistics::Create(v19, &v22);
        v8 = v20;
        if ( v20 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, v20, 0x3DEu, 0);
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v22);
          goto LABEL_26;
        }
        wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(
          (char *)this + 16,
          v22);
        v17 = v28;
      }
      v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
              this,
              (const struct CSM_BUFFER_ATTRIBUTES *)v26,
              v17);
      v8 = v18;
      if ( v18 >= 0 )
      {
        CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(this, v31);
LABEL_14:
        v6 = v25[0];
        goto LABEL_15;
      }
      v21 = 996;
    }
    else
    {
      v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSingleBuffer(
              this,
              (const struct CSM_BUFFER_ATTRIBUTES *)v26,
              (const struct CSM_SINGLE_BUFFER_INFO *)v27);
      v8 = v18;
      if ( v18 >= 0 )
        goto LABEL_14;
      v21 = 975;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D31B0, 4u, v18, v21, 0);
    goto LABEL_26;
  }
LABEL_15:
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
    McTemplateU0qqt_EventWriteTransfer(
      v5,
      v4,
      v6,
      (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 3,
      *((_BYTE *)this + 190));
LABEL_17:
  if ( v8 < 0 )
  {
LABEL_26:
    *((_QWORD *)this + 3) = 0;
    *v7 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002f294  mov     [rsp-8+arg_10], rbx
0x18002f299  push    rbp
0x18002f29a  push    rsi
0x18002f29b  push    rdi
0x18002f29c  push    r14
0x18002f29e  push    r15
0x18002f2a0  lea     rbp, [rsp-480h]
0x18002f2a8  sub     rsp, 580h
0x18002f2af  mov     rax, cs:__security_cookie
0x18002f2b6  xor     rax, rsp
0x18002f2b9  mov     [rbp+4A0h+var_30], rax
0x18002f2c0  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x18002f2c7  mov     rsi, rcx
0x18002f2ca  mov     [rsp+5A0h+var_568], rdx
0x18002f2cf  jnz     loc_18002F46E
0x18002f2d5  xor     edx, edx; Val
0x18002f2d7  lea     rcx, [rsp+5A0h+var_550]; void *
0x18002f2dc  mov     r8d, 520h; Size
0x18002f2e2  call    memset_0
0x18002f2e7  xor     r15d, r15d
0x18002f2ea  cmp     [rsi+18h], r15
0x18002f2ee  jnz     loc_18002F512
0x18002f2f4  mov     rcx, [rsi]
0x18002f2f7  lea     r8, [rsp+5A0h+var_550]
0x18002f2fc  lea     rdx, [rsp+5A0h+var_568]
0x18002f301  mov     rcx, [rcx+20h]
0x18002f305  call    cs:__imp_NtQueryCompositionSurfaceBinding
0x18002f30b  mov     edi, eax
0x18002f30d  test    eax, eax
0x18002f30f  js      loc_18002F521
0x18002f315  mov     r8d, [rsp+5A0h+var_550]
0x18002f31a  lea     r14, [rsi+20h]
0x18002f31e  mov     rax, [rsp+5A0h+var_568]
0x18002f323  mov     edi, r15d
0x18002f326  mov     [rsi+18h], rax
0x18002f32a  mov     [r14], r8d
0x18002f32d  test    r8d, r8d
0x18002f330  jz      loc_18002F3DE
0x18002f336  sub     r8d, 1
0x18002f33a  jz      loc_18002F610
0x18002f340  sub     r8d, 1
0x18002f344  jz      loc_18002F417
0x18002f34a  cmp     r8d, 1
0x18002f34e  jnz     loc_18002F554
0x18002f354  mov     rbx, [rbp+4A0h+hObject]
0x18002f35b  lea     r9, [rsp+5A0h+var_570]; struct CCompositionSwapchainStatistics **
0x18002f360  mov     r8, [rbp+4A0h+var_C0]; unsigned __int64
0x18002f367  mov     rdx, rbx; void *
0x18002f36a  mov     rcx, [rsi]; struct CCompositionSurfaceInfo *
0x18002f36d  mov     [rsp+5A0h+var_560], rbx
0x18002f372  mov     [rsp+5A0h+var_570], r15
0x18002f377  call    ?Create@CCompositionSwapchainStatistics@@SAJPEBVCCompositionSurfaceInfo@@PEAX_KPEAPEAV1@@Z; CCompositionSwapchainStatistics::Create(CCompositionSurfaceInfo const *,void *,unsigned __int64,CCompositionSwapchainStatistics * *)
0x18002f37c  mov     edi, eax
0x18002f37e  test    eax, eax
0x18002f380  js      loc_18002F489
0x18002f386  mov     rdx, [rsp+5A0h+var_570]
0x18002f38b  lea     rcx, [rsi+10h]
0x18002f38f  mov     [rsp+5A0h+var_570], r15
0x18002f394  call    ?attach@?$com_ptr_t@UIDisplayTarget@Core@Display@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXPEAUIDisplayTarget@Core@Display@Devices@Windows@@@Z; wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(Windows::Devices::Display::Core::IDisplayTarget *)
0x18002f399  mov     r8d, [rbp+4A0h+var_4AC]; unsigned int
0x18002f39d  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x18002f3a2  mov     rcx, rsi; this
0x18002f3a5  call    ?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)
0x18002f3aa  mov     edi, eax
0x18002f3ac  test    eax, eax
0x18002f3ae  js      loc_18002F57C
0x18002f3b4  mov     rcx, rsi; this
0x18002f3b7  call    ?CheckBufferHomogeneity@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXXZ; CGlobalCompositionSurfaceInfo::CBindInfo::CheckBufferHomogeneity(void)
0x18002f3bc  lea     rdx, [rbp+4A0h+var_B0]; unsigned __int16 *
0x18002f3c3  mov     rcx, rsi; this
0x18002f3c6  call    ?EnsureSwapChainTelemetryInitialized@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEBG@Z; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(ushort const *)
0x18002f3cb  lea     rax, [rbx-1]
0x18002f3cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f3d3  jbe     loc_18002F56E
0x18002f3d9  mov     r8d, [rsp+5A0h+var_550]
0x18002f3de  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x18002f3e5  jnz     short loc_18002F44D
0x18002f3e7  test    edi, edi
0x18002f3e9  js      loc_18002F4D3
0x18002f3ef  mov     eax, edi
0x18002f3f1  mov     rcx, [rbp+4A0h+var_30]
0x18002f3f8  xor     rcx, rsp; StackCookie
0x18002f3fb  call    __security_check_cookie
0x18002f400  mov     rbx, [rsp+5A0h+arg_10]
0x18002f408  add     rsp, 580h
0x18002f40f  pop     r15
0x18002f411  pop     r14
0x18002f413  pop     rdi
0x18002f414  pop     rsi
0x18002f415  pop     rbp
0x18002f416  retn
0x18002f417  mov     r8d, [rbp+4A0h+var_4AC]; unsigned int
0x18002f41b  cmp     r8d, 1
0x18002f41f  ja      loc_18002F4DF
0x18002f425  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x18002f42a  mov     rcx, rsi; this
0x18002f42d  call    ?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)
0x18002f432  mov     edi, eax
0x18002f434  test    eax, eax
0x18002f436  js      loc_18002F5FE
0x18002f43c  lea     rdx, [rbp+4A0h+var_B0]; unsigned __int16 *
0x18002f443  mov     rcx, rsi; this
0x18002f446  call    ?EnsureSwapChainTelemetryInitialized@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEBG@Z; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(ushort const *)
0x18002f44b  jmp     short loc_18002F3D9
0x18002f44d  mov     r9, [rsi+50h]
0x18002f451  sub     r9, [rsi+48h]
0x18002f455  movzx   eax, byte ptr [rsi+0BEh]
0x18002f45c  sar     r9, 3
0x18002f460  mov     [rsp+5A0h+var_580], eax
0x18002f464  call    McTemplateU0qqt_EventWriteTransfer
0x18002f469  jmp     loc_18002F3E7
0x18002f46e  mov     r8, [rcx]
0x18002f471  mov     r9, rdx
0x18002f474  lea     rdx, CompSurfInfo_Binding_Start
0x18002f47b  mov     r8, [r8+28h]
0x18002f47f  call    McTemplateU0xx_EventWriteTransfer
0x18002f484  jmp     loc_18002F2D5
0x18002f489  mov     r8d, 4; unsigned int
0x18002f48f  mov     [rsp+5A0h+var_578], r15; void *
0x18002f494  mov     r9d, eax; int
0x18002f497  mov     [rsp+5A0h+var_580], 3F4h; unsigned int
0x18002f49f  lea     rdx, dword_1802D31B0; int *
0x18002f4a6  lea     ecx, [r8+10h]; unsigned int
0x18002f4aa  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f4af  mov     rcx, [rsp+5A0h+var_570]
0x18002f4b4  test    rcx, rcx
0x18002f4b7  jz      short loc_18002F4C5
0x18002f4b9  mov     rax, [rcx]
0x18002f4bc  mov     rax, [rax+10h]
0x18002f4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4c5  lea     rax, [rbx-1]
0x18002f4c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f4cd  jbe     loc_18002F5BB
0x18002f4d3  mov     [rsi+18h], r15
0x18002f4d7  mov     [r14], r15d
0x18002f4da  jmp     loc_18002F3EF
0x18002f4df  mov     rcx, [rsi]; struct CGlobalCompositionSurfaceInfo *
0x18002f4e2  lea     rdx, [rsp+5A0h+var_570]; struct CFlipExSwapchainStatistics **
0x18002f4e7  mov     [rsp+5A0h+var_570], r15
0x18002f4ec  call    ?Create@CFlipExSwapchainStatistics@@SAJPEBVCGlobalCompositionSurfaceInfo@@PEAPEAV1@@Z; CFlipExSwapchainStatistics::Create(CGlobalCompositionSurfaceInfo const *,CFlipExSwapchainStatistics * *)
0x18002f4f1  mov     edi, eax
0x18002f4f3  test    eax, eax
0x18002f4f5  js      loc_18002F5C9
0x18002f4fb  mov     rdx, [rsp+5A0h+var_570]
0x18002f500  lea     rcx, [rsi+10h]
0x18002f504  call    ?attach@?$com_ptr_t@UIDisplayTarget@Core@Display@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXPEAUIDisplayTarget@Core@Display@Devices@Windows@@@Z; wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(Windows::Devices::Display::Core::IDisplayTarget *)
0x18002f509  mov     r8d, [rbp+4A0h+var_4AC]
0x18002f50d  jmp     loc_18002F425
0x18002f512  xor     edx, edx; bool
0x18002f514  mov     rcx, rsi; this
0x18002f517  call    ?Reset@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAX_N@Z; CGlobalCompositionSurfaceInfo::CBindInfo::Reset(bool)
0x18002f51c  jmp     loc_18002F2F4
0x18002f521  mov     r8d, 4; unsigned int
0x18002f527  mov     [rsp+5A0h+var_578], r15; void *
0x18002f52c  bts     edi, 1Ch
0x18002f530  mov     [rsp+5A0h+var_580], 3C2h; unsigned int
0x18002f538  mov     r9d, edi; int
0x18002f53b  lea     rdx, dword_1802D31B0; int *
0x18002f542  lea     ecx, [r8+10h]; unsigned int
0x18002f546  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f54b  lea     r14, [rsi+20h]
0x18002f54f  jmp     loc_18002F3E7
0x18002f554  mov     edi, 80070057h
0x18002f559  mov     [rsp+5A0h+var_578], r15
0x18002f55e  mov     r9d, edi
0x18002f561  mov     [rsp+5A0h+var_580], 406h
0x18002f569  jmp     loc_18029CEF2
0x18002f56e  mov     rcx, rbx; hObject
0x18002f571  call    cs:__imp_CloseHandle
0x18002f577  jmp     loc_18002F3D9
0x18002f57c  mov     r8d, 4; unsigned int
0x18002f582  mov     [rsp+5A0h+var_578], r15; void *
0x18002f587  mov     r9d, eax; int
0x18002f58a  mov     [rsp+5A0h+var_580], 3F8h; unsigned int
0x18002f592  lea     rdx, dword_1802D31B0; int *
0x18002f599  lea     ecx, [r8+10h]; unsigned int
0x18002f59d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f5a2  lea     rcx, [rsp+5A0h+var_570]
0x18002f5a7  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18002f5ac  lea     rcx, [rsp+5A0h+var_560]
0x18002f5b1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f5b6  jmp     loc_18002F4D3
0x18002f5bb  mov     rcx, rbx; hObject
0x18002f5be  call    cs:__imp_CloseHandle
0x18002f5c4  jmp     loc_18002F4D3
0x18002f5c9  mov     r8d, 4; unsigned int
0x18002f5cf  mov     [rsp+5A0h+var_578], r15; void *
0x18002f5d4  mov     r9d, eax; int
0x18002f5d7  mov     [rsp+5A0h+var_580], 3DEh; unsigned int
0x18002f5df  lea     rdx, dword_1802D31B0; int *
0x18002f5e6  lea     ecx, [r8+10h]; unsigned int
0x18002f5ea  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f5ef  lea     rcx, [rsp+5A0h+var_570]
0x18002f5f4  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18002f5f9  jmp     loc_18002F4D3
0x18002f5fe  mov     [rsp+5A0h+var_578], r15
0x18002f603  mov     [rsp+5A0h+var_580], 3E4h
0x18002f60b  jmp     loc_18029CEEF
0x18002f610  lea     r8, [rbp+4A0h+var_4B0]; struct CSM_SINGLE_BUFFER_INFO *
0x18002f614  mov     rcx, rsi; this
0x18002f617  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x18002f61c  call    ?CreateAndAddSingleBuffer@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@AEBUCSM_SINGLE_BUFFER_INFO@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSingleBuffer(CSM_BUFFER_ATTRIBUTES const &,CSM_SINGLE_BUFFER_INFO const &)
0x18002f621  mov     edi, eax
0x18002f623  test    eax, eax
0x18002f625  jns     loc_18002F3D9
0x18002f62b  jmp     loc_18029CEE2
0x18029cee2  mov     [rsp+5A0h+var_578], r15; void *
0x18029cee7  mov     [rsp+5A0h+var_580], 3CFh; unsigned int
0x18029ceef  mov     r9d, eax; int
0x18029cef2  mov     r8d, 4; unsigned int
0x18029cef8  lea     rdx, dword_1802D31B0; int *
0x18029ceff  lea     ecx, [r8+10h]; unsigned int
0x18029cf03  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18029cf08  nop
0x18029cf09  jmp     loc_18002F4D3
```
