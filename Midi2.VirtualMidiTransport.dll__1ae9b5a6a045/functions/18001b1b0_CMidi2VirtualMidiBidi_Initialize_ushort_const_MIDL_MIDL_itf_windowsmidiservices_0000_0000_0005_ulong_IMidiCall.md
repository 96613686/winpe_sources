# CMidi2VirtualMidiBidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x18001b1b0`
- end: `0x18001b5e1`
- name: `?Initialize@CMidi2VirtualMidiBidi@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiBidi *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callees

- `0x180001878`
- `0x180001990`
- `0x1800038f0`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d1ac`
- `0x18000d7cc`
- `0x1800116e0`
- `0x1800119f4`
- `0x180016740`
- `0x180017014`
- `0x18001adc4`
- `0x18001b094`
- `0x18001b1b0`
- `0x180021010`

## string_xrefs

- `0x18001b35f`: `Initializing device-side Bidi`
- `0x18001b463`: `Initializing client-side Bidi`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiBidi::Initialize(
        CMidi2VirtualMidiBidi *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        __int64 a6,
        struct _GUID *a7)
{
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rax
  const char *v15; // rdi
  char v16; // bl
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  const wchar_t *v20; // rax
  struct TransportState *v21; // rax
  __int64 v22; // rcx
  struct _RTL_CRITICAL_SECTION *v23; // rbx
  volatile signed __int32 *v24; // r14
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rdx
  char v28; // bl
  unsigned int *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  unsigned int v32; // eax
  const char *v33; // rax
  struct TransportState *v34; // rax
  __int64 v35; // rcx
  struct _RTL_CRITICAL_SECTION *v36; // rbx
  int v38; // [rsp+20h] [rbp-B1h]
  int v39[2]; // [rsp+50h] [rbp-81h] BYREF
  const wchar_t *v40; // [rsp+58h] [rbp-79h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-71h] BYREF
  const char *v42; // [rsp+68h] [rbp-69h] BYREF
  const char *v43; // [rsp+70h] [rbp-61h] BYREF
  _BYTE v44[32]; // [rsp+78h] [rbp-59h] BYREF
  __int128 v45; // [rsp+98h] [rbp-39h] BYREF
  __int128 v46; // [rsp+A8h] [rbp-29h]
  _BYTE v47[32]; // [rsp+B8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v9 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    *(_QWORD *)v39 = a2;
    v40 = L"Enter";
    v41 = (const wchar_t *)this;
    v42 = "CMidi2VirtualMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)byte_1800272B3,
      v10,
      v11,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)v39);
  }
  *(struct _GUID *)((char *)this + 88) = *a7;
  *((_QWORD *)this + 6) = a6;
  v12 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = a5;
  if ( a5 )
    (*(void (__fastcall **)(struct IMidiCallback *))(*(_QWORD *)a5 + 8LL))(a5);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v45 = 0;
  v46 = 0;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  std::wstring::_Construct<1,unsigned short const *>(&v45, a2);
  v14 = std::wstring::wstring(v44, &v45);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v47, v14);
  v15 = (char *)this + 56;
  std::wstring::operator=((char *)this + 56, v47);
  std::wstring::~wstring(v47);
  std::wstring::~wstring(&v45);
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v45, L"MIDIU_APPDEV_");
  v16 = WindowsMidiServicesInternal::EndpointInterfaceIdContainsString((char *)this + 56, &v45);
  std::wstring::~wstring(&v45);
  if ( v16 )
  {
    v17 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 5u )
    {
      v42 = (char *)this + 88;
      if ( *((_QWORD *)this + 10) <= 7u )
        v20 = (const wchar_t *)((char *)this + 56);
      else
        v20 = *(const wchar_t **)v15;
      v41 = v20;
      v40 = L"Initializing device-side Bidi";
      *(_QWORD *)v39 = this;
      v43 = "CMidi2VirtualMidiBidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v17,
        (unsigned int)&word_18002724E,
        v18,
        v19,
        (__int64)&v43,
        (__int64)v39,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v42);
    }
    *((_BYTE *)this + 104) = 1;
    v21 = TransportState::Current();
    v22 = *((_QWORD *)v21 + 1);
    if ( v22 )
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    v23 = *(struct _RTL_CRITICAL_SECTION **)v21;
    v24 = (volatile signed __int32 *)*((_QWORD *)v21 + 1);
    std::wstring::wstring(v44, (char *)this + 56);
    v25 = MidiEndpointTable::OnDeviceConnected(v23);
    v26 = v25;
    if ( v25 >= 0 )
      goto LABEL_30;
    v27 = 60;
LABEL_29:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidibidi.cpp",
      (const char *)(unsigned int)v25,
      v38);
LABEL_30:
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    return v26;
  }
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v45, L"MIDIU_APPPUB_");
  v28 = WindowsMidiServicesInternal::EndpointInterfaceIdContainsString((char *)this + 56, &v45);
  std::wstring::~wstring(&v45);
  v29 = (unsigned int *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  v32 = *v29;
  if ( v28 )
  {
    if ( v32 > 5 )
    {
      v43 = (char *)this + 88;
      if ( *((_QWORD *)this + 10) <= 7u )
        v33 = (char *)this + 56;
      else
        v33 = *(const char **)v15;
      v42 = v33;
      v41 = L"Initializing client-side Bidi";
      v40 = (const wchar_t *)this;
      *(_QWORD *)v39 = "CMidi2VirtualMidiBidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v29,
        (unsigned int)byte_1800271E9,
        v30,
        v31,
        (__int64)v39,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v43);
    }
    *((_BYTE *)this + 104) = 0;
    v34 = TransportState::Current();
    v35 = *((_QWORD *)v34 + 1);
    if ( v35 )
      _InterlockedIncrement((volatile signed __int32 *)(v35 + 8));
    v36 = *(struct _RTL_CRITICAL_SECTION **)v34;
    v24 = (volatile signed __int32 *)*((_QWORD *)v34 + 1);
    std::wstring::wstring(v44, (char *)this + 56);
    v25 = MidiEndpointTable::OnClientConnected(v36);
    v26 = v25;
    if ( v25 >= 0 )
      goto LABEL_30;
    v27 = 77;
    goto LABEL_29;
  }
  if ( v32 > 2 )
  {
    v43 = (char *)this + 88;
    if ( *((_QWORD *)this + 10) > 7u )
      v15 = *(const char **)v15;
    v42 = v15;
    v41 = L"We don't understand the endpoint Id";
    v40 = (const wchar_t *)this;
    *(_QWORD *)v39 = "CMidi2VirtualMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
      (_DWORD)v29,
      (unsigned int)&word_180027186,
      v30,
      v31,
      (__int64)v39,
      (__int64)&v40,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v43);
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18001b1b0  mov     [rsp-8+arg_10], rbx
0x18001b1b5  push    rbp
0x18001b1b6  push    rsi
0x18001b1b7  push    rdi
0x18001b1b8  push    r12
0x18001b1ba  push    r13
0x18001b1bc  push    r14
0x18001b1be  push    r15
0x18001b1c0  lea     rbp, [rsp-0Fh]
0x18001b1c5  sub     rsp, 0E0h
0x18001b1cc  mov     rax, cs:__security_cookie
0x18001b1d3  xor     rax, rsp
0x18001b1d6  mov     [rbp+3Fh+var_38], rax
0x18001b1da  mov     rdi, rdx
0x18001b1dd  mov     rsi, rcx
0x18001b1e0  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001b1e5  mov     rcx, [rax+8]
0x18001b1e9  mov     eax, [rcx]
0x18001b1eb  lea     r13, aCmidi2virtualm_5; "CMidi2VirtualMidiBidi::Initialize"
0x18001b1f2  cmp     eax, 4
0x18001b1f5  jbe     short loc_18001B240
0x18001b1f7  mov     qword ptr [rsp+110h+var_C0], rdi
0x18001b1fc  lea     rax, aEnter; "Enter"
0x18001b203  mov     [rbp+3Fh+var_B8], rax
0x18001b207  mov     [rbp+3Fh+var_B0], rsi
0x18001b20b  mov     [rbp+3Fh+var_A8], r13
0x18001b20f  lea     rax, [rsp+110h+var_C0]
0x18001b214  mov     [rsp+110h+var_D8], rax
0x18001b219  lea     rax, [rbp+3Fh+var_B8]
0x18001b21d  mov     [rsp+110h+var_E0], rax
0x18001b222  lea     rax, [rbp+3Fh+var_B0]
0x18001b226  mov     [rsp+110h+var_E8], rax
0x18001b22b  lea     rax, [rbp+3Fh+var_A8]
0x18001b22f  mov     qword ptr [rsp+110h+var_F0], rax
0x18001b234  lea     rdx, byte_1800272B3
0x18001b23b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001b240  lea     r14, [rsi+58h]
0x18001b244  mov     rax, [rbp+3Fh+arg_30]
0x18001b248  movups  xmm0, xmmword ptr [rax]
0x18001b24b  movdqu  xmmword ptr [r14], xmm0
0x18001b250  mov     rax, [rbp+3Fh+arg_28]
0x18001b254  mov     [rsi+30h], rax
0x18001b258  mov     rbx, [rsi+28h]
0x18001b25c  mov     rcx, [rbp+3Fh+arg_20]
0x18001b260  mov     [rsi+28h], rcx
0x18001b264  xor     r15d, r15d
0x18001b267  test    rcx, rcx
0x18001b26a  jz      short loc_18001B278
0x18001b26c  mov     rax, [rcx]
0x18001b26f  mov     rax, [rax+8]
0x18001b273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b278  test    rbx, rbx
0x18001b27b  jz      short loc_18001B28D
0x18001b27d  mov     rax, [rbx]
0x18001b280  mov     rcx, rbx
0x18001b283  mov     rax, [rax+10h]
0x18001b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28c  nop
0x18001b28d  xorps   xmm0, xmm0
0x18001b290  movups  [rbp+3Fh+var_78], xmm0
0x18001b294  xorps   xmm1, xmm1
0x18001b297  movdqu  [rbp+3Fh+var_68], xmm1
0x18001b29c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001b2a0  mov     r8, r12
0x18001b2a3  inc     r8
0x18001b2a6  cmp     [rdi+r8*2], r15w
0x18001b2ab  jnz     short loc_18001B2A3
0x18001b2ad  mov     rdx, rdi
0x18001b2b0  lea     rcx, [rbp+3Fh+var_78]
0x18001b2b4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b2b9  lea     rdx, [rbp+3Fh+var_78]
0x18001b2bd  lea     rcx, [rbp+3Fh+var_98]
0x18001b2c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b2c6  mov     rdx, rax
0x18001b2c9  lea     rcx, [rbp+3Fh+var_58]
0x18001b2cd  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18001b2d2  lea     rdi, [rsi+38h]
0x18001b2d6  lea     rdx, [rbp+3Fh+var_58]
0x18001b2da  mov     rcx, rdi
0x18001b2dd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001b2e2  lea     rcx, [rbp+3Fh+var_58]
0x18001b2e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b2eb  lea     rcx, [rbp+3Fh+var_78]
0x18001b2ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b2f4  xorps   xmm0, xmm0
0x18001b2f7  movups  [rbp+3Fh+var_78], xmm0
0x18001b2fb  xorps   xmm1, xmm1
0x18001b2fe  movdqu  [rbp+3Fh+var_68], xmm1
0x18001b303  mov     r8d, 0Dh
0x18001b309  lea     rdx, aMidiuAppdev; "MIDIU_APPDEV_"
0x18001b310  lea     rcx, [rbp+3Fh+var_78]
0x18001b314  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b319  lea     rdx, [rbp+3Fh+var_78]
0x18001b31d  mov     rcx, rdi
0x18001b320  call    ?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::wstring const &,std::wstring const &)
0x18001b325  mov     bl, al
0x18001b327  lea     rcx, [rbp+3Fh+var_78]
0x18001b32b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b330  test    bl, bl
0x18001b332  jz      loc_18001B3F8
0x18001b338  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001b33d  mov     rcx, [rax+8]
0x18001b341  mov     eax, [rcx]
0x18001b343  cmp     eax, 5
0x18001b346  jbe     short loc_18001B3AD
0x18001b348  mov     [rbp+3Fh+var_A8], r14
0x18001b34c  cmp     qword ptr [rdi+18h], 7
0x18001b351  jbe     short loc_18001B358
0x18001b353  mov     rax, [rdi]
0x18001b356  jmp     short loc_18001B35B
0x18001b358  mov     rax, rdi
0x18001b35b  mov     [rbp+3Fh+var_B0], rax
0x18001b35f  lea     rax, aInitializingDe; "Initializing device-side Bidi"
0x18001b366  mov     [rbp+3Fh+var_B8], rax
0x18001b36a  mov     qword ptr [rsp+110h+var_C0], rsi
0x18001b36f  mov     [rbp+3Fh+var_A0], r13
0x18001b373  lea     rax, [rbp+3Fh+var_A8]
0x18001b377  mov     [rsp+110h+var_D0], rax
0x18001b37c  lea     rax, [rbp+3Fh+var_B0]
0x18001b380  mov     [rsp+110h+var_D8], rax
0x18001b385  lea     rax, [rbp+3Fh+var_B8]
0x18001b389  mov     [rsp+110h+var_E0], rax
0x18001b38e  lea     rax, [rsp+110h+var_C0]
0x18001b393  mov     [rsp+110h+var_E8], rax
0x18001b398  lea     rax, [rbp+3Fh+var_A0]
0x18001b39c  mov     qword ptr [rsp+110h+var_F0], rax
0x18001b3a1  lea     rdx, word_18002724E
0x18001b3a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x18001b3ad  mov     byte ptr [rsi+68h], 1
0x18001b3b1  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001b3b6  mov     rcx, [rax+8]
0x18001b3ba  test    rcx, rcx
0x18001b3bd  jz      short loc_18001B3C3
0x18001b3bf  lock inc dword ptr [rcx+8]
0x18001b3c3  mov     rbx, [rax]
0x18001b3c6  mov     r14, [rax+8]
0x18001b3ca  mov     rdx, rdi
0x18001b3cd  lea     rcx, [rbp+3Fh+var_98]
0x18001b3d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b3d6  mov     r8, rsi
0x18001b3d9  mov     rdx, rax
0x18001b3dc  mov     rcx, rbx; lpCriticalSection
0x18001b3df  call    ?OnDeviceConnected@MidiEndpointTable@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCMidi2VirtualMidiBidi@@@Z; MidiEndpointTable::OnDeviceConnected(std::wstring,CMidi2VirtualMidiBidi *)
0x18001b3e4  mov     ebx, eax
0x18001b3e6  test    eax, eax
0x18001b3e8  jns     loc_18001B506
0x18001b3ee  mov     edx, 3Ch ; '<'
0x18001b3f3  jmp     loc_18001B4F3
0x18001b3f8  xorps   xmm0, xmm0
0x18001b3fb  movups  [rbp+3Fh+var_78], xmm0
0x18001b3ff  xorps   xmm1, xmm1
0x18001b402  movdqu  [rbp+3Fh+var_68], xmm1
0x18001b407  mov     r8d, 0Dh
0x18001b40d  lea     rdx, aMidiuApppub; "MIDIU_APPPUB_"
0x18001b414  lea     rcx, [rbp+3Fh+var_78]
0x18001b418  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b41d  lea     rdx, [rbp+3Fh+var_78]
0x18001b421  mov     rcx, rdi
0x18001b424  call    ?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::wstring const &,std::wstring const &)
0x18001b429  mov     bl, al
0x18001b42b  lea     rcx, [rbp+3Fh+var_78]
0x18001b42f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b434  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001b439  mov     rcx, [rax+8]
0x18001b43d  mov     eax, [rcx]
0x18001b43f  test    bl, bl
0x18001b441  jz      loc_18001B54E
0x18001b447  cmp     eax, 5
0x18001b44a  jbe     short loc_18001B4B1
0x18001b44c  mov     [rbp+3Fh+var_A0], r14
0x18001b450  cmp     qword ptr [rdi+18h], 7
0x18001b455  jbe     short loc_18001B45C
0x18001b457  mov     rax, [rdi]
0x18001b45a  jmp     short loc_18001B45F
0x18001b45c  mov     rax, rdi
0x18001b45f  mov     [rbp+3Fh+var_A8], rax
0x18001b463  lea     rax, aInitializingCl; "Initializing client-side Bidi"
0x18001b46a  mov     [rbp+3Fh+var_B0], rax
0x18001b46e  mov     [rbp+3Fh+var_B8], rsi
0x18001b472  mov     qword ptr [rsp+110h+var_C0], r13
0x18001b477  lea     rax, [rbp+3Fh+var_A0]
0x18001b47b  mov     [rsp+110h+var_D0], rax
0x18001b480  lea     rax, [rbp+3Fh+var_A8]
0x18001b484  mov     [rsp+110h+var_D8], rax
0x18001b489  lea     rax, [rbp+3Fh+var_B0]
0x18001b48d  mov     [rsp+110h+var_E0], rax
0x18001b492  lea     rax, [rbp+3Fh+var_B8]
0x18001b496  mov     [rsp+110h+var_E8], rax
0x18001b49b  lea     rax, [rsp+110h+var_C0]
0x18001b4a0  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18001b4a5  lea     rdx, byte_1800271E9
0x18001b4ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x18001b4b1  mov     [rsi+68h], r15b
0x18001b4b5  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001b4ba  mov     rcx, [rax+8]
0x18001b4be  test    rcx, rcx
0x18001b4c1  jz      short loc_18001B4C7
0x18001b4c3  lock inc dword ptr [rcx+8]
0x18001b4c7  mov     rbx, [rax]
0x18001b4ca  mov     r14, [rax+8]
0x18001b4ce  mov     rdx, rdi
0x18001b4d1  lea     rcx, [rbp+3Fh+var_98]
0x18001b4d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b4da  mov     r8, rsi
0x18001b4dd  mov     rdx, rax
0x18001b4e0  mov     rcx, rbx; lpCriticalSection
0x18001b4e3  call    ?OnClientConnected@MidiEndpointTable@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCMidi2VirtualMidiBidi@@@Z; MidiEndpointTable::OnClientConnected(std::wstring,CMidi2VirtualMidiBidi *)
0x18001b4e8  mov     ebx, eax
0x18001b4ea  test    eax, eax
0x18001b4ec  jns     short loc_18001B506
0x18001b4ee  mov     edx, 4Dh ; 'M'; void *
0x18001b4f3  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001b4fa  mov     r9d, eax; char *
0x18001b4fd  mov     rcx, [rbp+47h]; this
0x18001b501  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b506  test    r14, r14
0x18001b509  jz      loc_18001B5B8
0x18001b50f  mov     eax, r12d
0x18001b512  lock xadd [r14+8], eax
0x18001b518  add     eax, r12d
0x18001b51b  jnz     loc_18001B5B8
0x18001b521  mov     rax, [r14]
0x18001b524  mov     rcx, r14
0x18001b527  mov     rax, [rax]
0x18001b52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b52f  mov     eax, r12d
0x18001b532  lock xadd [r14+0Ch], eax
0x18001b538  add     eax, r12d
0x18001b53b  jnz     short loc_18001B5B8
0x18001b53d  mov     rax, [r14]
0x18001b540  mov     rcx, r14
0x18001b543  mov     rax, [rax+8]
0x18001b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54c  jmp     short loc_18001B5B8
0x18001b54e  cmp     eax, 2
0x18001b551  jbe     short loc_18001B5B3
0x18001b553  mov     [rbp+3Fh+var_A0], r14
0x18001b557  cmp     qword ptr [rdi+18h], 7
0x18001b55c  jbe     short loc_18001B561
0x18001b55e  mov     rdi, [rdi]
0x18001b561  mov     [rbp+3Fh+var_A8], rdi
0x18001b565  lea     rax, aWeDonTUndersta; "We don't understand the endpoint Id"
0x18001b56c  mov     [rbp+3Fh+var_B0], rax
0x18001b570  mov     [rbp+3Fh+var_B8], rsi
0x18001b574  mov     qword ptr [rsp+110h+var_C0], r13
0x18001b579  lea     rax, [rbp+3Fh+var_A0]
0x18001b57d  mov     [rsp+110h+var_D0], rax
0x18001b582  lea     rax, [rbp+3Fh+var_A8]
0x18001b586  mov     [rsp+110h+var_D8], rax
0x18001b58b  lea     rax, [rbp+3Fh+var_B0]
0x18001b58f  mov     [rsp+110h+var_E0], rax
0x18001b594  lea     rax, [rbp+3Fh+var_B8]
0x18001b598  mov     [rsp+110h+var_E8], rax
0x18001b59d  lea     rax, [rsp+110h+var_C0]
0x18001b5a2  mov     qword ptr [rsp+110h+var_F0], rax
0x18001b5a7  lea     rdx, word_180027186
0x18001b5ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x18001b5b3  mov     ebx, 80070057h
0x18001b5b8  mov     eax, ebx
0x18001b5ba  mov     rcx, [rbp+3Fh+var_38]
0x18001b5be  xor     rcx, rsp; StackCookie
0x18001b5c1  call    __security_check_cookie
0x18001b5c6  mov     rbx, [rsp+110h+arg_10]
0x18001b5ce  add     rsp, 0E0h
0x18001b5d5  pop     r15
0x18001b5d7  pop     r14
0x18001b5d9  pop     r13
0x18001b5db  pop     r12
0x18001b5dd  pop     rdi
0x18001b5de  pop     rsi
0x18001b5df  pop     rbp
0x18001b5e0  retn
```
