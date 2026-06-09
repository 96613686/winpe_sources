# CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint(MidiVirtualDeviceEndpointEntry &)

- ea: `0x18000e0a4`
- end: `0x18000e838`
- name: `?CreateDeviceSideEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJAEAUMidiVirtualDeviceEndpointEntry@@@Z`
- size: `1940`
- prototype: `int(CMidi2VirtualMidiEndpointManager *__hidden this, struct MidiVirtualDeviceEndpointEntry *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x1800016dc`
- `0x1800017d0`
- `0x1800038f0`
- `0x1800046a0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000cbfc`
- `0x18000d1ac`
- `0x18000d27c`
- `0x18000d4f0`
- `0x18000d7cc`
- `0x18000d86c`
- `0x18000d8e8`
- `0x18000e0a4`
- `0x1800116e0`
- `0x1800117d8`
- `0x180011918`
- `0x180011a4c`
- `0x180014ab0`
- `0x18001adc4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7a8`

## string_xrefs

- `0x18000e0ea`: `CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint`
- `0x18000e75d`: `Created device-side endpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint(
        CMidi2VirtualMidiEndpointManager *this,
        struct MidiVirtualDeviceEndpointEntry *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  struct MidiVirtualDeviceEndpointEntry *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int128 *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // r8
  __int64 v21; // rax
  _WORD *v22; // rcx
  _WORD *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  struct TransportState *v26; // rax
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rdi
  int v29; // ebx
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  const char *v34; // [rsp+68h] [rbp-98h] BYREF
  CMidi2VirtualMidiEndpointManager *v35; // [rsp+70h] [rbp-90h] BYREF
  const char *v36; // [rsp+78h] [rbp-88h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+98h] [rbp-68h] BYREF
  __int128 v40; // [rsp+A8h] [rbp-58h]
  __int128 v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v43; // [rsp+D8h] [rbp-28h]
  int v44; // [rsp+F8h] [rbp-8h]
  _QWORD *v45; // [rsp+100h] [rbp+0h]
  int v46[4]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v47; // [rsp+130h] [rbp+30h]
  _QWORD *v48; // [rsp+138h] [rbp+38h]
  __int128 *v49; // [rsp+140h] [rbp+40h]
  _QWORD *v50; // [rsp+148h] [rbp+48h]
  _QWORD *v51; // [rsp+150h] [rbp+50h]
  __int64 v52; // [rsp+158h] [rbp+58h]
  __int64 v53; // [rsp+160h] [rbp+60h]
  _QWORD *v54; // [rsp+168h] [rbp+68h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  int v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+17Ch] [rbp+7Ch]
  int v58; // [rsp+180h] [rbp+80h]
  int v59; // [rsp+184h] [rbp+84h]
  __int128 v60; // [rsp+190h] [rbp+90h] BYREF
  __int128 v61; // [rsp+1A0h] [rbp+A0h]
  _OWORD v62[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD Src[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v64; // [rsp+1E8h] [rbp+E8h]
  __int128 v65; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v66; // [rsp+200h] [rbp+100h]
  _QWORD v67[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v68[4]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v69[4]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v35 = this;
    v36 = "CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (unsigned int)word_1800266CA,
      v5,
      v6,
      (__int64)&v36,
      (__int64)&v35);
  }
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v65, L"APP");
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)a2 + 6)) < 0x16 )
    std::_Xlen_string();
  std::wstring::wstring(&v60);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)a2 + 10)) < 0x3D )
    std::_Xlen_string();
  std::wstring::wstring(v62);
  WindowsMidiServicesInternal::TrimmedWStringCopy(v69);
  v37 = 0;
  v38 = 0;
  v60 = 0;
  v61 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v60, &S2);
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,unsigned short const *>(v62, &S2);
  WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(v68);
  std::wstring::~wstring(v62);
  std::wstring::~wstring(&v60);
  v39 = PKEY_MIDI_VirtualMidiEndpointAssociator;
  v40 = 0x389u;
  LODWORD(v41) = 18;
  DWORD1(v41) = 2 * *((_DWORD *)a2 + 4) + 2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v7 = a2;
  else
    v7 = *(struct MidiVirtualDeviceEndpointEntry **)a2;
  *((_QWORD *)&v41 + 1) = v7;
  v8 = *((_QWORD *)&v37 + 1);
  if ( *((_QWORD *)&v37 + 1) == v38 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v37, *((_QWORD *)&v37 + 1), &v39);
  }
  else
  {
    **((_OWORD **)&v37 + 1) = PKEY_MIDI_VirtualMidiEndpointAssociator;
    *(_OWORD *)(v8 + 16) = v40;
    *(_OWORD *)(v8 + 32) = v41;
    *((_QWORD *)&v37 + 1) += 48LL;
  }
  memset_0(&v42, 0, 0x48u);
  v42 = 72;
  v9 = (_QWORD *)((char *)a2 + 96);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)a2 + 14)) < 0xD )
    std::_Xlen_string();
  std::wstring::wstring(&v60);
  v10 = std::wstring::wstring(v62, &v60);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v67, v10);
  std::wstring::~wstring(&v60);
  v11 = v67;
  if ( v67[3] > 7u )
    v11 = (_QWORD *)v67[0];
  v43 = v11;
  v44 = 0;
  v12 = Src;
  if ( v64 > 7 )
    v12 = (_QWORD *)Src[0];
  v45 = v12;
  v47 = 100;
  v55 = 0;
  v59 = 0;
  *(GUID *)v46 = GUID_8feaad91_70e1_4a19_997a_377720a719c1;
  v13 = v68;
  if ( v68[3] > 7u )
    v13 = (_QWORD *)v68[0];
  v48 = v13;
  v14 = &v65;
  if ( *((_QWORD *)&v66 + 1) > 7u )
    v14 = (__int128 *)v65;
  v49 = v14;
  v15 = Src;
  if ( v64 > 7 )
    v15 = (_QWORD *)Src[0];
  v50 = v15;
  v16 = v69;
  if ( v69[3] > 7u )
    v16 = (_QWORD *)v69[0];
  v51 = v16;
  v52 = 0;
  v53 = 0;
  if ( *((_QWORD *)a2 + 15) > 7u )
    v9 = (_QWORD *)*v9;
  v54 = v9;
  v56 = 2;
  v57 = 2;
  v58 = 11;
  v17 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v17 = (_QWORD *)*v17;
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          v17,
          1);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v18,
      (int)v46);
LABEL_50:
    std::wstring::~wstring(v67);
    std::wstring::~wstring(v68);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v37);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v65);
    return v19;
  }
  std::wstring::operator=((char *)a2 + 192, v67);
  v60 = 0;
  v61 = 0;
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(2 * v20) );
  std::wstring::_Construct<1,unsigned short const *>(&v60, 0);
  v21 = std::wstring::wstring(&v39, &v60);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v62, v21);
  std::wstring::operator=((char *)a2 + 160, v62);
  std::wstring::~wstring(v62);
  std::wstring::~wstring(&v60);
  if ( *((_QWORD *)a2 + 31) <= 7u )
    v22 = (_WORD *)((char *)a2 + 224);
  else
    v22 = (_WORD *)*((_QWORD *)a2 + 28);
  *((_QWORD *)a2 + 30) = 0;
  *v22 = 0;
  if ( *((_QWORD *)a2 + 35) <= 7u )
    v23 = (_WORD *)((char *)a2 + 256);
  else
    v23 = (_WORD *)*((_QWORD *)a2 + 32);
  *((_QWORD *)a2 + 34) = 0;
  *v23 = 0;
  v24 = *((_QWORD *)a2 + 37);
  *((_QWORD *)a2 + 37) = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = *((_QWORD *)a2 + 38);
  *((_QWORD *)a2 + 38) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = TransportState::Current();
  v27 = *((_QWORD *)v26 + 1);
  if ( v27 )
    _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
  v28 = (volatile signed __int32 *)*((_QWORD *)v26 + 1);
  v29 = MidiEndpointTable::AddCreatedEndpointDevice(*(MidiEndpointTable **)v26, a2);
  if ( v28 )
  {
    if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v19 = v29;
    goto LABEL_50;
  }
  v31 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v31 > 4u )
  {
    v36 = (const char *)L"Created device-side endpoint";
    v35 = this;
    v34 = "CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v31,
      (unsigned int)qword_180026698,
      v32,
      v33,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&v36);
  }
  std::wstring::~wstring(v67);
  std::wstring::~wstring(v68);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v37);
  std::wstring::~wstring(v69);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v65);
  return 0;
}

```

## disassembly

```asm
0x18000e0a4  mov     [rsp-8+arg_10], rbx
0x18000e0a9  mov     [rsp-8+arg_18], rsi
0x18000e0ae  push    rbp
0x18000e0af  push    rdi
0x18000e0b0  push    r13
0x18000e0b2  push    r14
0x18000e0b4  push    r15
0x18000e0b6  lea     rbp, [rsp-180h]
0x18000e0be  sub     rsp, 280h
0x18000e0c5  mov     rax, cs:__security_cookie
0x18000e0cc  xor     rax, rsp
0x18000e0cf  mov     [rbp+1A0h+var_30], rax
0x18000e0d6  mov     rbx, rdx
0x18000e0d9  mov     r14, rcx
0x18000e0dc  xor     r15d, r15d
0x18000e0df  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000e0e4  mov     rcx, [rax+8]
0x18000e0e8  mov     eax, [rcx]
0x18000e0ea  lea     r13, aCmidi2virtualm_3; "CMidi2VirtualMidiEndpointManager::Creat"...
0x18000e0f1  cmp     eax, 4
0x18000e0f4  jbe     short loc_18000E120
0x18000e0f6  mov     [rsp+2A0h+var_230], r14
0x18000e0fb  mov     [rsp+2A0h+var_228], r13
0x18000e100  lea     rax, [rsp+2A0h+var_230]
0x18000e105  mov     [rsp+2A0h+var_278], rax
0x18000e10a  lea     rax, [rsp+2A0h+var_228]
0x18000e10f  mov     qword ptr [rsp+2A0h+var_280], rax
0x18000e114  lea     rdx, word_1800266CA
0x18000e11b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e120  xorps   xmm0, xmm0
0x18000e123  movups  [rbp+1A0h+var_B0], xmm0
0x18000e12a  xorps   xmm1, xmm1
0x18000e12d  movdqu  [rbp+1A0h+var_A0], xmm1
0x18000e135  mov     r8d, 3
0x18000e13b  lea     rdx, aApp; "APP"
0x18000e142  lea     rcx, [rbp+1A0h+var_B0]
0x18000e149  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e14e  nop
0x18000e14f  lea     r9, [rbx+20h]
0x18000e153  mov     rcx, [r9+10h]
0x18000e157  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18000e161  mov     rax, rsi
0x18000e164  sub     rax, rcx
0x18000e167  cmp     rax, 16h
0x18000e16b  jb      loc_18000E82C
0x18000e171  cmp     qword ptr [r9+18h], 7
0x18000e176  jbe     short loc_18000E17B
0x18000e178  mov     r9, [r9]
0x18000e17b  mov     [rsp+2A0h+var_270], 16h
0x18000e184  lea     rax, aVirtualMidiDev; " (Virtual MIDI Device)"
0x18000e18b  mov     [rsp+2A0h+var_278], rax
0x18000e190  mov     qword ptr [rsp+2A0h+var_280], rcx
0x18000e195  lea     rcx, [rbp+1A0h+var_110]
0x18000e19c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000e1a1  lea     rdx, [rbp+1A0h+var_110]
0x18000e1a8  lea     rcx, [rbp+1A0h+Src]; Src
0x18000e1af  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18000e1b4  nop
0x18000e1b5  lea     r9, [rbx+40h]
0x18000e1b9  mov     rcx, [r9+10h]
0x18000e1bd  mov     rax, rsi
0x18000e1c0  sub     rax, rcx
0x18000e1c3  cmp     rax, 3Dh ; '='
0x18000e1c7  jb      loc_18000E832
0x18000e1cd  cmp     qword ptr [r9+18h], 7
0x18000e1d2  jbe     short loc_18000E1D7
0x18000e1d4  mov     r9, [r9]
0x18000e1d7  mov     [rsp+2A0h+var_270], 3Dh ; '='
0x18000e1e0  lea     rax, aThisEndpointFo; " (This endpoint for use only by the dev"...
0x18000e1e7  mov     [rsp+2A0h+var_278], rax
0x18000e1ec  mov     qword ptr [rsp+2A0h+var_280], rcx
0x18000e1f1  lea     rcx, [rbp+1A0h+var_F0]
0x18000e1f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000e1fd  lea     rdx, [rbp+1A0h+var_F0]
0x18000e204  lea     rcx, [rbp+1A0h+var_50]; Src
0x18000e20b  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18000e210  nop
0x18000e211  xorps   xmm0, xmm0
0x18000e214  movdqu  [rbp+1A0h+var_220], xmm0
0x18000e219  mov     [rbp+1A0h+var_210], r15
0x18000e21d  movups  [rbp+1A0h+var_110], xmm0
0x18000e224  xorps   xmm1, xmm1
0x18000e227  movdqu  [rbp+1A0h+var_100], xmm1
0x18000e22f  xor     r8d, r8d
0x18000e232  lea     rdx, S2
0x18000e239  lea     rcx, [rbp+1A0h+var_110]
0x18000e240  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e245  nop
0x18000e246  xorps   xmm0, xmm0
0x18000e249  movups  [rbp+1A0h+var_F0], xmm0
0x18000e250  xorps   xmm1, xmm1
0x18000e253  movdqu  [rbp+1A0h+var_E0], xmm1
0x18000e25b  xor     r8d, r8d
0x18000e25e  lea     rdx, S2
0x18000e265  lea     rcx, [rbp+1A0h+var_F0]
0x18000e26c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e271  nop
0x18000e272  lea     r9, [rbp+1A0h+var_110]
0x18000e279  lea     r8, [rbp+1A0h+var_F0]
0x18000e280  lea     rdx, [rbp+1A0h+Src]
0x18000e287  lea     rcx, [rbp+1A0h+var_70]; Src
0x18000e28e  call    ?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18000e293  nop
0x18000e294  lea     rcx, [rbp+1A0h+var_F0]
0x18000e29b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2a0  nop
0x18000e2a1  lea     rcx, [rbp+1A0h+var_110]
0x18000e2a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2ad  movups  xmm0, cs:PKEY_MIDI_VirtualMidiEndpointAssociator
0x18000e2b4  movups  [rbp+1A0h+var_208], xmm0
0x18000e2b8  mov     eax, cs:dword_180023E10
0x18000e2be  mov     dword ptr [rbp+1A0h+var_1F8], eax
0x18000e2c1  mov     dword ptr [rbp+1A0h+var_1F8+4], r15d
0x18000e2c5  mov     qword ptr [rbp+1A0h+var_1F8+8], r15
0x18000e2c9  mov     dword ptr [rbp+1A0h+var_1E8], 12h
0x18000e2d0  mov     eax, [rbx+10h]
0x18000e2d3  lea     eax, ds:2[rax*2]
0x18000e2da  mov     dword ptr [rbp+1A0h+var_1E8+4], eax
0x18000e2dd  cmp     qword ptr [rbx+18h], 7
0x18000e2e2  jbe     short loc_18000E2E9
0x18000e2e4  mov     rax, [rbx]
0x18000e2e7  jmp     short loc_18000E2EC
0x18000e2e9  mov     rax, rbx
0x18000e2ec  mov     qword ptr [rbp+1A0h+var_1E8+8], rax
0x18000e2f0  mov     rdx, qword ptr [rbp+1A0h+var_220+8]
0x18000e2f4  cmp     rdx, [rbp+1A0h+var_210]
0x18000e2f8  jz      short loc_18000E314
0x18000e2fa  movups  xmmword ptr [rdx], xmm0
0x18000e2fd  movups  xmm0, [rbp+1A0h+var_1F8]
0x18000e301  movups  xmmword ptr [rdx+10h], xmm0
0x18000e305  movups  xmm1, [rbp+1A0h+var_1E8]
0x18000e309  movups  xmmword ptr [rdx+20h], xmm1
0x18000e30d  add     qword ptr [rbp+1A0h+var_220+8], 30h ; '0'
0x18000e312  jmp     short loc_18000E321
0x18000e314  lea     r8, [rbp+1A0h+var_208]
0x18000e318  lea     rcx, [rbp+1A0h+var_220]
0x18000e31c  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18000e321  mov     edi, 48h ; 'H'
0x18000e326  mov     r8d, edi; Size
0x18000e329  xor     edx, edx; Val
0x18000e32b  lea     rcx, [rbp+1A0h+var_1D0]; void *
0x18000e32f  call    memset_0
0x18000e334  mov     [rbp+1A0h+var_1D0], edi
0x18000e337  lea     rdi, [rbx+60h]
0x18000e33b  mov     rcx, [rdi+10h]
0x18000e33f  sub     rsi, rcx
0x18000e342  cmp     rsi, 0Dh
0x18000e346  jb      loc_18000E826
0x18000e34c  cmp     qword ptr [rdi+18h], 7
0x18000e351  jbe     short loc_18000E358
0x18000e353  mov     rax, [rdi]
0x18000e356  jmp     short loc_18000E35B
0x18000e358  mov     rax, rdi
0x18000e35b  mov     [rsp+2A0h+var_270], rcx
0x18000e360  mov     [rsp+2A0h+var_278], rax
0x18000e365  mov     qword ptr [rsp+2A0h+var_280], 0Dh
0x18000e36e  lea     r9, aMidiuAppdev; "MIDIU_APPDEV_"
0x18000e375  lea     rcx, [rbp+1A0h+var_110]
0x18000e37c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000e381  nop
0x18000e382  lea     rdx, [rbp+1A0h+var_110]
0x18000e389  lea     rcx, [rbp+1A0h+var_F0]
0x18000e390  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e395  mov     rdx, rax
0x18000e398  lea     rcx, [rbp+1A0h+var_90]
0x18000e39f  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000e3a4  nop
0x18000e3a5  lea     rcx, [rbp+1A0h+var_110]
0x18000e3ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e3b1  lea     rax, [rbp+1A0h+var_90]
0x18000e3b8  cmp     [rbp+1A0h+var_78], 7
0x18000e3c0  cmova   rax, [rbp+1A0h+var_90]
0x18000e3c8  mov     [rbp+1A0h+var_1C8], rax
0x18000e3cc  mov     [rbp+1A0h+var_1A8], r15d
0x18000e3d0  lea     rax, [rbp+1A0h+Src]
0x18000e3d7  cmp     [rbp+1A0h+var_B8], 7
0x18000e3df  cmova   rax, [rbp+1A0h+Src]
0x18000e3e7  mov     [rbp+1A0h+var_1A0], rax
0x18000e3eb  mov     [rsp+2A0h+pv], r15
0x18000e3f0  mov     [rbp+1A0h+var_170], 64h ; 'd'
0x18000e3f8  xor     eax, eax
0x18000e3fa  mov     [rbp+1A0h+var_130], rax
0x18000e3fe  mov     [rbp+1A0h+var_11C], eax
0x18000e404  movups  xmm0, xmmword ptr cs:_GUID_8feaad91_70e1_4a19_997a_377720a719c1.Data1
0x18000e40b  movdqu  xmmword ptr [rbp+1A0h+var_180], xmm0
0x18000e410  lea     rax, [rbp+1A0h+var_70]
0x18000e417  cmp     [rbp+1A0h+var_58], 7
0x18000e41f  cmova   rax, [rbp+1A0h+var_70]
0x18000e427  mov     [rbp+1A0h+var_168], rax
0x18000e42b  lea     rax, [rbp+1A0h+var_B0]
0x18000e432  cmp     qword ptr [rbp+1A0h+var_A0+8], 7
0x18000e43a  cmova   rax, qword ptr [rbp+1A0h+var_B0]
0x18000e442  mov     [rbp+1A0h+var_160], rax
0x18000e446  lea     rax, [rbp+1A0h+Src]
0x18000e44d  cmp     [rbp+1A0h+var_B8], 7
0x18000e455  cmova   rax, [rbp+1A0h+Src]
0x18000e45d  mov     [rbp+1A0h+var_158], rax
0x18000e461  lea     rax, [rbp+1A0h+var_50]
0x18000e468  cmp     [rbp+1A0h+var_38], 7
0x18000e470  cmova   rax, [rbp+1A0h+var_50]
0x18000e478  mov     [rbp+1A0h+var_150], rax
0x18000e47c  mov     [rbp+1A0h+var_148], r15
0x18000e480  mov     [rbp+1A0h+var_140], r15
0x18000e484  cmp     qword ptr [rdi+18h], 7
0x18000e489  jbe     short loc_18000E48E
0x18000e48b  mov     rdi, [rdi]
0x18000e48e  mov     [rbp+1A0h+var_138], rdi
0x18000e492  mov     r9d, 2
0x18000e498  mov     [rbp+1A0h+var_128], r9d
0x18000e49c  mov     [rbp+1A0h+var_124], r9d
0x18000e4a0  mov     [rbp+1A0h+var_120], 0Bh
0x18000e4aa  mov     rcx, [r14+40h]
0x18000e4ae  mov     rax, [rcx]
0x18000e4b1  mov     r10, [rax+28h]
0x18000e4b5  mov     [rsp+2A0h+pv], r15
0x18000e4ba  mov     r8, qword ptr [rbp+1A0h+var_220]
0x18000e4be  mov     rax, qword ptr [rbp+1A0h+var_220+8]
0x18000e4c2  sub     rax, r8
0x18000e4c5  sar     rax, 4
0x18000e4c9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000e4d3  imul    rax, rdx
0x18000e4d7  lea     rdx, [r14+20h]
0x18000e4db  cmp     qword ptr [rdx+18h], 7
0x18000e4e0  jbe     short loc_18000E4E5
0x18000e4e2  mov     rdx, [rdx]
0x18000e4e5  lea     r11, [rsp+2A0h+pv]
0x18000e4ea  mov     [rsp+2A0h+var_250], r11
0x18000e4ef  lea     r11, [rbp+1A0h+var_1D0]
0x18000e4f3  mov     [rsp+2A0h+var_258], r11
0x18000e4f8  mov     [rsp+2A0h+var_260], r15
0x18000e4fd  mov     [rsp+2A0h+var_268], r8
0x18000e502  mov     dword ptr [rsp+2A0h+var_270], r15d
0x18000e507  mov     dword ptr [rsp+2A0h+var_278], eax
0x18000e50b  lea     rax, [rbp+1A0h+var_180]
0x18000e50f  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18000e514  mov     r8d, 1
0x18000e51a  mov     rax, r10
0x18000e51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e522  mov     edi, eax
0x18000e524  test    eax, eax
0x18000e526  jns     short loc_18000E55D
0x18000e528  mov     rcx, [rbp+1A8h]; this
0x18000e52f  mov     r9d, eax; char *
0x18000e532  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000e539  mov     edx, 1AAh; void *
0x18000e53e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e543  nop
0x18000e544  mov     rcx, [rsp+2A0h+pv]; pv
0x18000e549  test    rcx, rcx
0x18000e54c  jz      loc_18000E6FC
0x18000e552  call    cs:__imp_CoTaskMemFree
0x18000e558  jmp     loc_18000E6FC
0x18000e55d  lea     rcx, [rbx+0C0h]
0x18000e564  lea     rdx, [rbp+1A0h+var_90]
0x18000e56b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000e570  mov     rdx, [rsp+2A0h+pv]
0x18000e575  xorps   xmm0, xmm0
0x18000e578  movups  [rbp+1A0h+var_110], xmm0
0x18000e57f  xorps   xmm1, xmm1
0x18000e582  movdqu  [rbp+1A0h+var_100], xmm1
0x18000e58a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e58e  mov     r8, rsi
0x18000e591  inc     r8
0x18000e594  cmp     [rdx+r8*2], r15w
0x18000e599  jnz     short loc_18000E591
0x18000e59b  lea     rcx, [rbp+1A0h+var_110]
0x18000e5a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e5a7  nop
0x18000e5a8  lea     rdx, [rbp+1A0h+var_110]
0x18000e5af  lea     rcx, [rbp+1A0h+var_208]
0x18000e5b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e5b8  mov     rdx, rax
0x18000e5bb  lea     rcx, [rbp+1A0h+var_F0]
0x18000e5c2  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18000e5c7  lea     rcx, [rbx+0A0h]
0x18000e5ce  lea     rdx, [rbp+1A0h+var_F0]
0x18000e5d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e5da  lea     rcx, [rbp+1A0h+var_F0]
0x18000e5e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e5e6  nop
0x18000e5e7  lea     rcx, [rbp+1A0h+var_110]
0x18000e5ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e5f3  lea     rax, [rbx+0E0h]
0x18000e5fa  cmp     qword ptr [rax+18h], 7
0x18000e5ff  jbe     short loc_18000E606
0x18000e601  mov     rcx, [rax]
0x18000e604  jmp     short loc_18000E609
0x18000e606  mov     rcx, rax
0x18000e609  mov     [rax+10h], r15
0x18000e60d  mov     [rcx], r15w
0x18000e611  lea     rax, [rbx+100h]
0x18000e618  cmp     qword ptr [rax+18h], 7
0x18000e61d  jbe     short loc_18000E624
0x18000e61f  mov     rcx, [rax]
0x18000e622  jmp     short loc_18000E627
0x18000e624  mov     rcx, rax
0x18000e627  mov     [rax+10h], r15
0x18000e62b  mov     [rcx], r15w
0x18000e62f  mov     rcx, [rbx+128h]
0x18000e636  mov     [rbx+128h], r15
  ... truncated ...
```
