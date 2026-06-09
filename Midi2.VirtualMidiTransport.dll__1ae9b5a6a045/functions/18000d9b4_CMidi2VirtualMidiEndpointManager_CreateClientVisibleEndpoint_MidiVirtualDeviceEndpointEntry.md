# CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint(MidiVirtualDeviceEndpointEntry &)

- ea: `0x18000d9b4`
- end: `0x18000e09e`
- name: `?CreateClientVisibleEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJAEAUMidiVirtualDeviceEndpointEntry@@@Z`
- size: `1770`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiEndpointManager *__hidden this, struct MidiVirtualDeviceEndpointEntry *)`
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017014`

## callees

- `0x1800016dc`
- `0x1800038f0`
- `0x1800046a0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000cbfc`
- `0x18000d1ac`
- `0x18000d27c`
- `0x18000d354`
- `0x18000d4f0`
- `0x18000d748`
- `0x18000d7cc`
- `0x18000d86c`
- `0x18000d8e8`
- `0x18000d9b4`
- `0x180010cd4`
- `0x1800116e0`
- `0x1800117d8`
- `0x1800119f4`
- `0x180011a4c`
- `0x18001f40c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e015`

## string_xrefs

- `0x18000d9f4`: `CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint(
        CMidi2VirtualMidiEndpointManager *this,
        struct MidiVirtualDeviceEndpointEntry *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  struct MidiVirtualDeviceEndpointEntry *v7; // rax
  __int64 v8; // rdx
  int v9; // eax
  _QWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int128 *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // rbx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  _DWORD *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  int v30; // [rsp+20h] [rbp-E0h]
  int v31[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  CMidi2VirtualMidiEndpointManager *v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+98h] [rbp-68h] BYREF
  __int128 v37; // [rsp+A8h] [rbp-58h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  _OWORD v39[3]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int v41; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+128h] [rbp+28h]
  _QWORD *v44; // [rsp+130h] [rbp+30h]
  int v45[4]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v46; // [rsp+160h] [rbp+60h]
  _QWORD *v47; // [rsp+168h] [rbp+68h]
  __int128 *v48; // [rsp+170h] [rbp+70h]
  _QWORD *v49; // [rsp+178h] [rbp+78h]
  _QWORD *v50; // [rsp+180h] [rbp+80h]
  __int64 v51; // [rsp+188h] [rbp+88h]
  __int64 v52; // [rsp+190h] [rbp+90h]
  _QWORD *v53; // [rsp+198h] [rbp+98h]
  __int64 v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1A8h] [rbp+A8h]
  int v56; // [rsp+1ACh] [rbp+ACh]
  int v57; // [rsp+1B0h] [rbp+B0h]
  int v58; // [rsp+1B4h] [rbp+B4h]
  __int128 v59; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v60; // [rsp+1D0h] [rbp+D0h]
  __int128 v61; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v62; // [rsp+1F0h] [rbp+F0h]
  _QWORD v63[3]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v64; // [rsp+218h] [rbp+118h]
  __int128 v65; // [rsp+220h] [rbp+120h] BYREF
  __int128 v66; // [rsp+230h] [rbp+130h]
  _QWORD v67[4]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD Src[4]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v69[4]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v32 = (const char *)L"Enter";
    v33 = this;
    *(_QWORD *)v31 = "CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)byte_180026725,
      v5,
      v6,
      (__int64)v31,
      (__int64)&v33,
      (__int64)&v32);
  }
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v65, L"APP");
  std::wstring::wstring(v63, (char *)a2 + 32);
  std::wstring::wstring(v69, (char *)a2 + 64);
  v34 = 0;
  v35 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v61, &S2);
  v59 = 0;
  v60 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v59, &S2);
  WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(Src);
  std::wstring::~wstring(&v59);
  std::wstring::~wstring(&v61);
  v36 = PKEY_MIDI_VirtualMidiEndpointAssociator;
  v37 = 0x389u;
  LODWORD(v38) = 18;
  DWORD1(v38) = 2 * *((_DWORD *)a2 + 4) + 2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v7 = a2;
  else
    v7 = *(struct MidiVirtualDeviceEndpointEntry **)a2;
  *((_QWORD *)&v38 + 1) = v7;
  v8 = *((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) == v35 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v34, *((_QWORD *)&v34 + 1), &v36);
  }
  else
  {
    **((_OWORD **)&v34 + 1) = PKEY_MIDI_VirtualMidiEndpointAssociator;
    *(_OWORD *)(v8 + 16) = v37;
    *(_OWORD *)(v8 + 32) = v38;
    *((_QWORD *)&v34 + 1) += 48LL;
  }
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v39);
  v9 = WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(v39, &v34);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v9,
      v30);
  memset_0(&v41, 0, 0x48u);
  v41 = 72;
  v10 = (_QWORD *)((char *)a2 + 96);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)a2 + 14)) < 0xD )
    std::_Xlen_string();
  std::wstring::wstring(&v61);
  v11 = std::wstring::wstring(&v59, &v61);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v67, v11);
  std::wstring::~wstring(&v61);
  v12 = v67;
  if ( v67[3] > 7u )
    v12 = (_QWORD *)v67[0];
  v42 = v12;
  v43 = 0;
  v13 = v63;
  if ( v64 > 7 )
    v13 = (_QWORD *)v63[0];
  v44 = v13;
  v46 = 0;
  v58 = 0;
  *(GUID *)v45 = GUID_8feaad91_70e1_4a19_997a_377720a719c1;
  v14 = Src;
  if ( Src[3] > 7u )
    v14 = (_QWORD *)Src[0];
  v47 = v14;
  v15 = &v65;
  if ( *((_QWORD *)&v66 + 1) > 7u )
    v15 = (__int128 *)v65;
  v48 = v15;
  v16 = v63;
  if ( v64 > 7 )
    v16 = (_QWORD *)v63[0];
  v49 = v16;
  v17 = v69;
  if ( v69[3] > 7u )
    v17 = (_QWORD *)v69[0];
  v50 = v17;
  v51 = 0;
  v52 = 0;
  if ( *((_QWORD *)a2 + 15) > 7u )
    v10 = (_QWORD *)*v10;
  v53 = v10;
  v54 = 0;
  v55 = 2;
  v56 = 2;
  v57 = 15;
  v18 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v18 = (_QWORD *)*v18;
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          v18,
          *((unsigned __int8 *)a2 + 288));
  v20 = v19;
  if ( v19 >= 0 )
  {
    std::wstring::operator=((char *)a2 + 256, v67);
    v61 = 0;
    v62 = 0;
    v22 = -1;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(2 * v23) );
    std::wstring::_Construct<1,unsigned short const *>(&v61, 0);
    v24 = std::wstring::wstring(&v36, &v61);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(&v59, v24);
    std::wstring::operator=((char *)a2 + 224, &v59);
    std::wstring::~wstring(&v59);
    std::wstring::~wstring(&v61);
    v25 = *((_QWORD *)a2 + 38);
    *((_QWORD *)a2 + 38) = 0;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v59 = 0;
    v60 = 0u;
    do
      ++v22;
    while ( *(_WORD *)(2 * v22) );
    std::wstring::_Construct<1,unsigned short const *>(&v59, 0);
    v26 = CMidi2VirtualMidiEndpointManager::NegotiateAndRequestMetadata(this, &v59);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
        (const char *)(unsigned int)v26,
        (int)v45);
    v27 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v27 > 4u )
    {
      *(_QWORD *)v31 = L"Exit";
      v33 = this;
      v32 = "CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v27,
        (unsigned int)byte_1800266F3,
        v28,
        v29,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)v31);
    }
    std::wstring::~wstring(v67);
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v39);
    std::wstring::~wstring(Src);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v34);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v63);
    std::wstring::~wstring(&v65);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v19,
      (int)v45);
    std::wstring::~wstring(v67);
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v39);
    std::wstring::~wstring(Src);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v34);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v63);
    std::wstring::~wstring(&v65);
    return v20;
  }
}

```

## disassembly

```asm
0x18000d9b4  mov     [rsp-8+arg_10], rbx
0x18000d9b9  push    rbp
0x18000d9ba  push    rsi
0x18000d9bb  push    rdi
0x18000d9bc  push    r13
0x18000d9be  push    r14
0x18000d9c0  lea     rbp, [rsp-1B0h]
0x18000d9c8  sub     rsp, 2B0h
0x18000d9cf  mov     rax, cs:__security_cookie
0x18000d9d6  xor     rax, rsp
0x18000d9d9  mov     [rbp+1D0h+var_30], rax
0x18000d9e0  mov     rdi, rdx
0x18000d9e3  mov     rsi, rcx
0x18000d9e6  xor     r14d, r14d
0x18000d9e9  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000d9ee  mov     rcx, [rax+8]
0x18000d9f2  mov     eax, [rcx]
0x18000d9f4  lea     r13, aCmidi2virtualm_7; "CMidi2VirtualMidiEndpointManager::Creat"...
0x18000d9fb  cmp     eax, 4
0x18000d9fe  jbe     short loc_18000DA40
0x18000da00  lea     rax, aEnter; "Enter"
0x18000da07  mov     [rsp+2D0h+var_260], rax
0x18000da0c  mov     [rsp+2D0h+var_258], rsi
0x18000da11  mov     qword ptr [rsp+2D0h+var_268], r13
0x18000da16  lea     rax, [rsp+2D0h+var_260]
0x18000da1b  mov     [rsp+2D0h+var_2A0], rax
0x18000da20  lea     rax, [rsp+2D0h+var_258]
0x18000da25  mov     [rsp+2D0h+var_2A8], rax
0x18000da2a  lea     rax, [rsp+2D0h+var_268]
0x18000da2f  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18000da34  lea     rdx, byte_180026725
0x18000da3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000da40  xorps   xmm0, xmm0
0x18000da43  movups  [rbp+1D0h+var_B0], xmm0
0x18000da4a  xorps   xmm1, xmm1
0x18000da4d  movdqu  [rbp+1D0h+var_A0], xmm1
0x18000da55  mov     r8d, 3
0x18000da5b  lea     rdx, aApp; "APP"
0x18000da62  lea     rcx, [rbp+1D0h+var_B0]
0x18000da69  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000da6e  nop
0x18000da6f  lea     rdx, [rdi+20h]
0x18000da73  lea     rcx, [rbp+1D0h+var_D0]
0x18000da7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000da7f  nop
0x18000da80  lea     rdx, [rdi+40h]
0x18000da84  lea     rcx, [rbp+1D0h+var_50]
0x18000da8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000da90  nop
0x18000da91  xorps   xmm0, xmm0
0x18000da94  movdqu  [rbp+1D0h+var_250], xmm0
0x18000da99  mov     [rbp+1D0h+var_240], r14
0x18000da9d  movups  [rbp+1D0h+var_F0], xmm0
0x18000daa4  xorps   xmm1, xmm1
0x18000daa7  movdqu  [rbp+1D0h+var_E0], xmm1
0x18000daaf  xor     r8d, r8d
0x18000dab2  lea     rdx, S2
0x18000dab9  lea     rcx, [rbp+1D0h+var_F0]
0x18000dac0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000dac5  nop
0x18000dac6  xorps   xmm0, xmm0
0x18000dac9  movups  [rbp+1D0h+var_110], xmm0
0x18000dad0  xorps   xmm1, xmm1
0x18000dad3  movdqu  [rbp+1D0h+var_100], xmm1
0x18000dadb  xor     r8d, r8d
0x18000dade  lea     rdx, S2
0x18000dae5  lea     rcx, [rbp+1D0h+var_110]
0x18000daec  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000daf1  nop
0x18000daf2  lea     r9, [rbp+1D0h+var_F0]
0x18000daf9  lea     r8, [rbp+1D0h+var_110]
0x18000db00  lea     rdx, [rbp+1D0h+var_D0]
0x18000db07  lea     rcx, [rbp+1D0h+Src]; Src
0x18000db0e  call    ?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18000db13  nop
0x18000db14  lea     rcx, [rbp+1D0h+var_110]
0x18000db1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000db20  nop
0x18000db21  lea     rcx, [rbp+1D0h+var_F0]
0x18000db28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000db2d  movups  xmm0, cs:PKEY_MIDI_VirtualMidiEndpointAssociator
0x18000db34  movups  [rbp+1D0h+var_238], xmm0
0x18000db38  mov     eax, cs:dword_180023E10
0x18000db3e  mov     dword ptr [rbp+1D0h+var_228], eax
0x18000db41  mov     dword ptr [rbp+1D0h+var_228+4], r14d
0x18000db45  mov     qword ptr [rbp+1D0h+var_228+8], r14
0x18000db49  mov     dword ptr [rbp+1D0h+var_218], 12h
0x18000db50  mov     eax, [rdi+10h]
0x18000db53  lea     eax, ds:2[rax*2]
0x18000db5a  mov     dword ptr [rbp+1D0h+var_218+4], eax
0x18000db5d  cmp     qword ptr [rdi+18h], 7
0x18000db62  jbe     short loc_18000DB69
0x18000db64  mov     rax, [rdi]
0x18000db67  jmp     short loc_18000DB6C
0x18000db69  mov     rax, rdi
0x18000db6c  mov     qword ptr [rbp+1D0h+var_218+8], rax
0x18000db70  mov     rdx, qword ptr [rbp+1D0h+var_250+8]
0x18000db74  cmp     rdx, [rbp+1D0h+var_240]
0x18000db78  jz      short loc_18000DB94
0x18000db7a  movups  xmmword ptr [rdx], xmm0
0x18000db7d  movups  xmm0, [rbp+1D0h+var_228]
0x18000db81  movups  xmmword ptr [rdx+10h], xmm0
0x18000db85  movups  xmm1, [rbp+1D0h+var_218]
0x18000db89  movups  xmmword ptr [rdx+20h], xmm1
0x18000db8d  add     qword ptr [rbp+1D0h+var_250+8], 30h ; '0'
0x18000db92  jmp     short loc_18000DBA1
0x18000db94  lea     r8, [rbp+1D0h+var_238]
0x18000db98  lea     rcx, [rbp+1D0h+var_250]
0x18000db9c  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18000dba1  xorps   xmm0, xmm0
0x18000dba4  xor     eax, eax
0x18000dba6  movups  [rbp+1D0h+var_208], xmm0
0x18000dbaa  movups  [rbp+1D0h+var_1F8], xmm0
0x18000dbae  movups  [rbp+1D0h+var_1E8], xmm0
0x18000dbb2  mov     [rbp+1D0h+var_1D8], rax
0x18000dbb6  lea     rcx, [rbp+1D0h+var_208]; this
0x18000dbba  call    ??0MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ; WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(void)
0x18000dbbf  nop
0x18000dbc0  lea     rdx, [rbp+1D0h+var_250]
0x18000dbc4  lea     rcx, [rbp+1D0h+var_208]
0x18000dbc8  call    ?WriteProperties@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(std::vector<_DEVPROPERTY> &)
0x18000dbcd  mov     rcx, [rbp+1D8h]; this
0x18000dbd4  test    eax, eax
0x18000dbd6  jns     short loc_18000DBEC
0x18000dbd8  mov     r9d, eax; char *
0x18000dbdb  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000dbe2  mov     edx, 117h; void *
0x18000dbe7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dbec  mov     ebx, 48h ; 'H'
0x18000dbf1  mov     r8d, ebx; Size
0x18000dbf4  xor     edx, edx; Val
0x18000dbf6  lea     rcx, [rbp+1D0h+var_1D0]; void *
0x18000dbfa  call    memset_0
0x18000dbff  mov     [rbp+1D0h+var_1D0], ebx
0x18000dc02  lea     rbx, [rdi+60h]
0x18000dc06  mov     rcx, [rbx+10h]
0x18000dc0a  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000dc14  sub     rax, rcx
0x18000dc17  cmp     rax, 0Dh
0x18000dc1b  jb      loc_18000E098
0x18000dc21  cmp     qword ptr [rbx+18h], 7
0x18000dc26  jbe     short loc_18000DC2D
0x18000dc28  mov     rax, [rbx]
0x18000dc2b  jmp     short loc_18000DC30
0x18000dc2d  mov     rax, rbx
0x18000dc30  mov     [rsp+2D0h+var_2A0], rcx
0x18000dc35  mov     [rsp+2D0h+var_2A8], rax
0x18000dc3a  mov     qword ptr [rsp+2D0h+var_2B0], 0Dh
0x18000dc43  lea     r9, aMidiuApppub; "MIDIU_APPPUB_"
0x18000dc4a  lea     rcx, [rbp+1D0h+var_F0]
0x18000dc51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000dc56  nop
0x18000dc57  lea     rdx, [rbp+1D0h+var_F0]
0x18000dc5e  lea     rcx, [rbp+1D0h+var_110]
0x18000dc65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dc6a  mov     rdx, rax
0x18000dc6d  lea     rcx, [rbp+1D0h+var_90]
0x18000dc74  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000dc79  nop
0x18000dc7a  lea     rcx, [rbp+1D0h+var_F0]
0x18000dc81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dc86  lea     rax, [rbp+1D0h+var_90]
0x18000dc8d  cmp     [rbp+1D0h+var_78], 7
0x18000dc95  cmova   rax, [rbp+1D0h+var_90]
0x18000dc9d  mov     [rbp+1D0h+var_1C8], rax
0x18000dca1  mov     [rbp+1D0h+var_1A8], r14d
0x18000dca5  lea     rax, [rbp+1D0h+var_D0]
0x18000dcac  cmp     [rbp+1D0h+var_B8], 7
0x18000dcb4  cmova   rax, [rbp+1D0h+var_D0]
0x18000dcbc  mov     [rbp+1D0h+var_1A0], rax
0x18000dcc0  mov     [rsp+2D0h+pv], r14
0x18000dcc5  xor     eax, eax
0x18000dcc7  mov     [rbp+1D0h+var_170], rax
0x18000dccb  mov     [rbp+1D0h+var_11C], eax
0x18000dcd1  movups  xmm0, xmmword ptr cs:_GUID_8feaad91_70e1_4a19_997a_377720a719c1.Data1
0x18000dcd8  movdqu  xmmword ptr [rbp+1D0h+var_180], xmm0
0x18000dcdd  lea     rax, [rbp+1D0h+Src]
0x18000dce4  cmp     [rbp+1D0h+var_58], 7
0x18000dcec  cmova   rax, [rbp+1D0h+Src]
0x18000dcf4  mov     [rbp+1D0h+var_168], rax
0x18000dcf8  lea     rax, [rbp+1D0h+var_B0]
0x18000dcff  cmp     qword ptr [rbp+1D0h+var_A0+8], 7
0x18000dd07  cmova   rax, qword ptr [rbp+1D0h+var_B0]
0x18000dd0f  mov     [rbp+1D0h+var_160], rax
0x18000dd13  lea     rax, [rbp+1D0h+var_D0]
0x18000dd1a  cmp     [rbp+1D0h+var_B8], 7
0x18000dd22  cmova   rax, [rbp+1D0h+var_D0]
0x18000dd2a  mov     [rbp+1D0h+var_158], rax
0x18000dd2e  lea     rax, [rbp+1D0h+var_50]
0x18000dd35  cmp     [rbp+1D0h+var_38], 7
0x18000dd3d  cmova   rax, [rbp+1D0h+var_50]
0x18000dd45  mov     [rbp+1D0h+var_150], rax
0x18000dd4c  mov     [rbp+1D0h+var_148], r14
0x18000dd53  mov     [rbp+1D0h+var_140], r14
0x18000dd5a  cmp     qword ptr [rbx+18h], 7
0x18000dd5f  jbe     short loc_18000DD64
0x18000dd61  mov     rbx, [rbx]
0x18000dd64  mov     [rbp+1D0h+var_138], rbx
0x18000dd6b  mov     [rbp+1D0h+var_130], r14
0x18000dd72  mov     r9d, 2
0x18000dd78  mov     [rbp+1D0h+var_128], r9d
0x18000dd7f  mov     [rbp+1D0h+var_124], r9d
0x18000dd86  mov     [rbp+1D0h+var_120], 0Fh
0x18000dd90  mov     rcx, [rsi+40h]
0x18000dd94  mov     rax, [rcx]
0x18000dd97  mov     r11, [rax+28h]
0x18000dd9b  mov     [rsp+2D0h+pv], r14
0x18000dda0  mov     r8, qword ptr [rbp+1D0h+var_250]
0x18000dda4  mov     rax, qword ptr [rbp+1D0h+var_250+8]
0x18000dda8  sub     rax, r8
0x18000ddab  sar     rax, 4
0x18000ddaf  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000ddb9  imul    rax, rdx
0x18000ddbd  movzx   r10d, byte ptr [rdi+120h]
0x18000ddc5  lea     rdx, [rsi+20h]
0x18000ddc9  cmp     qword ptr [rdx+18h], 7
0x18000ddce  jbe     short loc_18000DDD3
0x18000ddd0  mov     rdx, [rdx]
0x18000ddd3  lea     rbx, [rsp+2D0h+pv]
0x18000ddd8  mov     [rsp+2D0h+var_280], rbx
0x18000dddd  lea     rbx, [rbp+1D0h+var_1D0]
0x18000dde1  mov     [rsp+2D0h+var_288], rbx
0x18000dde6  mov     [rsp+2D0h+var_290], r14
0x18000ddeb  mov     [rsp+2D0h+var_298], r8
0x18000ddf0  mov     dword ptr [rsp+2D0h+var_2A0], r14d
0x18000ddf5  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x18000ddf9  lea     rax, [rbp+1D0h+var_180]
0x18000ddfd  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18000de02  mov     r8d, r10d
0x18000de05  mov     rax, r11
0x18000de08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0d  mov     ebx, eax
0x18000de0f  test    eax, eax
0x18000de11  jns     loc_18000DE9F
0x18000de17  mov     rcx, [rbp+1D8h]; this
0x18000de1e  mov     r9d, eax; char *
0x18000de21  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000de28  mov     edx, 144h; void *
0x18000de2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de32  nop
0x18000de33  mov     rcx, [rsp+2D0h+pv]; pv
0x18000de38  test    rcx, rcx
0x18000de3b  jz      short loc_18000DE44
0x18000de3d  call    cs:__imp_CoTaskMemFree
0x18000de43  nop
0x18000de44  lea     rcx, [rbp+1D0h+var_90]
0x18000de4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000de50  nop
0x18000de51  lea     rcx, [rbp+1D0h+var_208]; this
0x18000de55  call    ??1MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ; WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable(void)
0x18000de5a  nop
0x18000de5b  lea     rcx, [rbp+1D0h+Src]
0x18000de62  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000de67  nop
0x18000de68  lea     rcx, [rbp+1D0h+var_250]
0x18000de6c  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x18000de71  nop
0x18000de72  lea     rcx, [rbp+1D0h+var_50]
0x18000de79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000de7e  nop
0x18000de7f  lea     rcx, [rbp+1D0h+var_D0]
0x18000de86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000de8b  nop
0x18000de8c  lea     rcx, [rbp+1D0h+var_B0]
0x18000de93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000de98  mov     eax, ebx
0x18000de9a  jmp     loc_18000E072
0x18000de9f  lea     rcx, [rdi+100h]
0x18000dea6  lea     rdx, [rbp+1D0h+var_90]
0x18000dead  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000deb2  mov     rdx, [rsp+2D0h+pv]
0x18000deb7  xorps   xmm0, xmm0
0x18000deba  movups  [rbp+1D0h+var_F0], xmm0
0x18000dec1  xorps   xmm1, xmm1
0x18000dec4  movdqu  [rbp+1D0h+var_E0], xmm1
0x18000decc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ded0  mov     r8, rbx
0x18000ded3  inc     r8
0x18000ded6  cmp     [rdx+r8*2], r14w
0x18000dedb  jnz     short loc_18000DED3
0x18000dedd  lea     rcx, [rbp+1D0h+var_F0]
0x18000dee4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000dee9  nop
0x18000deea  lea     rdx, [rbp+1D0h+var_F0]
0x18000def1  lea     rcx, [rbp+1D0h+var_238]
0x18000def5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000defa  mov     rdx, rax
0x18000defd  lea     rcx, [rbp+1D0h+var_110]
0x18000df04  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18000df09  lea     rcx, [rdi+0E0h]
0x18000df10  lea     rdx, [rbp+1D0h+var_110]
0x18000df17  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000df1c  lea     rcx, [rbp+1D0h+var_110]
0x18000df23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df28  nop
0x18000df29  lea     rcx, [rbp+1D0h+var_F0]
0x18000df30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df35  nop
0x18000df36  mov     rcx, [rdi+130h]
0x18000df3d  mov     [rdi+130h], r14
  ... truncated ...
```
