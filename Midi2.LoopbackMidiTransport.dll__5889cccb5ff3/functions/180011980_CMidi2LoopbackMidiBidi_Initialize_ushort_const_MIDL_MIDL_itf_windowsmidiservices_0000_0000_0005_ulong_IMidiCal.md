# CMidi2LoopbackMidiBidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x180011980`
- end: `0x180011fbc`
- name: `?Initialize@CMidi2LoopbackMidiBidi@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `1596`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiBidi *this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800016dc`
- `0x1800018e8`
- `0x180004180`
- `0x18000b740`
- `0x18000bfe4`
- `0x18000ccd8`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x1800104a4`
- `0x180010848`
- `0x180011018`
- `0x180011980`
- `0x180013294`
- `0x18001338c`
- `0x180032010`

## string_xrefs

- `0x180011bb7`: `Initializing Side-A Bidi`
- `0x180011cc1`: `Initializing Side-B Bidi`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiBidi::Initialize(
        CMidi2LoopbackMidiBidi *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        __int64 a6)
{
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // r8
  __int64 v12; // rax
  CMidi2LoopbackMidiBidi *v13; // rsi
  void *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 SwdStringProperty; // rax
  const char *v18; // rdi
  _DWORD *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  const wchar_t *v22; // rax
  CMidi2LoopbackMidiBidi *v23; // rax
  __int64 v24; // rbx
  char v25; // al
  char v26; // bl
  unsigned int *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // eax
  const char *v31; // rax
  CMidi2LoopbackMidiBidi *v32; // rax
  __int64 v33; // rbx
  struct TransportState *v34; // rax
  __int64 v35; // rcx
  _QWORD *v36; // rbx
  volatile signed __int32 *v37; // r15
  void *v38; // rax
  __int64 Device; // r13
  char *v40; // rbx
  __int64 v41; // rdi
  __int64 v42; // rdi
  _DWORD *v43; // rcx
  int v44; // r8d
  int v45; // r9d
  const wchar_t *v47; // [rsp+50h] [rbp-B0h] BYREF
  CMidi2LoopbackMidiBidi *v48; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v49; // [rsp+60h] [rbp-A0h] BYREF
  CMidi2LoopbackMidiBidi *v50; // [rsp+68h] [rbp-98h] BYREF
  const char *v51; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v52[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v53[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v54[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v55; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v56; // [rsp+E8h] [rbp-18h]
  _OWORD v57[2]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v58[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v59[32]; // [rsp+138h] [rbp+38h] BYREF

  v8 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    v47 = a2;
    v48 = this;
    v49 = (const wchar_t *)"CMidi2LoopbackMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v8,
      (unsigned int)word_180057E8A,
      v9,
      v10,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47);
  }
  *((_QWORD *)this + 9) = a6;
  v55 = 0;
  v56 = 0;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  std::wstring::_Construct<1,unsigned short const *>(&v55, a2);
  v12 = std::wstring::wstring(v58, &v55);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v57, v12);
  v13 = (CMidi2LoopbackMidiBidi *)((char *)this + 80);
  std::wstring::operator=((char *)this + 80, v57);
  std::wstring::~wstring(v57);
  std::wstring::~wstring(&v55);
  v14 = (void *)std::wstring::wstring(v53, (char *)this + 80);
  v15 = std::wstring::wstring(v57, v14);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v59, v15);
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v55, &S2);
  memset(v57, 0, sizeof(v57));
  std::wstring::_Construct<1,unsigned short const *>(v57, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 905");
  v16 = std::wstring::wstring(v54, v59);
  SwdStringProperty = WindowsMidiServicesInternal::GetSwdStringProperty(v52, v16, v57, &v55);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v58, SwdStringProperty);
  std::wstring::~wstring(v59);
  std::wstring::~wstring(v14);
  v18 = (char *)this + 32;
  std::wstring::operator=((char *)this + 32, v58);
  std::wstring::~wstring(v58);
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v55, L"MIDIU_LOOP_A_");
  LOBYTE(v14) = WindowsMidiServicesInternal::EndpointInterfaceIdContainsString((char *)this + 80, &v55);
  std::wstring::~wstring(&v55);
  if ( (_BYTE)v14 )
  {
    v19 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v19 > 4u )
    {
      if ( *((_QWORD *)this + 7) <= 7u )
        v22 = (const wchar_t *)((char *)this + 32);
      else
        v22 = *(const wchar_t **)v18;
      v49 = v22;
      if ( *((_QWORD *)this + 13) <= 7u )
        v23 = (CMidi2LoopbackMidiBidi *)((char *)this + 80);
      else
        v23 = *(CMidi2LoopbackMidiBidi **)v13;
      v48 = v23;
      v47 = L"Initializing Side-A Bidi";
      v50 = this;
      v51 = "CMidi2LoopbackMidiBidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v19,
        (unsigned int)&dword_180058064,
        v20,
        v21,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v49);
    }
    v24 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = a5;
    if ( a5 )
      (*(void (__fastcall **)(struct IMidiCallback *))(*(_QWORD *)a5 + 8LL))(a5);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = 1;
LABEL_33:
    *((_BYTE *)this + 24) = v25;
    v34 = TransportState::Current();
    v35 = *((_QWORD *)v34 + 3);
    if ( v35 )
      _InterlockedIncrement((volatile signed __int32 *)(v35 + 8));
    v36 = (_QWORD *)*((_QWORD *)v34 + 2);
    v37 = (volatile signed __int32 *)*((_QWORD *)v34 + 3);
    v38 = (void *)std::wstring::wstring(v52, (char *)this + 32);
    Device = MidiLoopbackDeviceTable::GetDevice(v36, v38);
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    if ( Device )
    {
      v40 = (char *)this + 8;
      if ( *((_BYTE *)this + 24) )
      {
        if ( this != (CMidi2LoopbackMidiBidi *)-8LL )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 8LL))((char *)this + 8);
        v41 = *(_QWORD *)(Device + 464);
        *(_QWORD *)(Device + 464) = v40;
        if ( this != (CMidi2LoopbackMidiBidi *)-8LL )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 8LL))((char *)this + 8);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      else
      {
        if ( this != (CMidi2LoopbackMidiBidi *)-8LL )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 8LL))((char *)this + 8);
        v42 = *(_QWORD *)(Device + 472);
        *(_QWORD *)(Device + 472) = v40;
        if ( this != (CMidi2LoopbackMidiBidi *)-8LL )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 8LL))((char *)this + 8);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      if ( this != (CMidi2LoopbackMidiBidi *)-8LL )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 8);
    }
    else
    {
      v43 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v43 > 4u )
      {
        if ( *((_QWORD *)this + 7) > 7u )
          v18 = *(const char **)v18;
        v51 = v18;
        if ( *((_QWORD *)this + 13) > 7u )
          v13 = *(CMidi2LoopbackMidiBidi **)v13;
        v50 = v13;
        v49 = L"Unable to find matching device in device table";
        v48 = this;
        v47 = (const wchar_t *)"CMidi2LoopbackMidiBidi::Initialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v43,
          (unsigned int)&word_180057F76,
          v44,
          v45,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51);
      }
    }
    return 0;
  }
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v55, L"MIDIU_LOOP_B_");
  v26 = WindowsMidiServicesInternal::EndpointInterfaceIdContainsString((char *)this + 80, &v55);
  std::wstring::~wstring(&v55);
  v27 = (unsigned int *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  v30 = *v27;
  if ( v26 )
  {
    if ( v30 > 4 )
    {
      if ( *((_QWORD *)this + 7) <= 7u )
        v31 = (char *)this + 32;
      else
        v31 = *(const char **)v18;
      v51 = v31;
      if ( *((_QWORD *)this + 13) <= 7u )
        v32 = (CMidi2LoopbackMidiBidi *)((char *)this + 80);
      else
        v32 = *(CMidi2LoopbackMidiBidi **)v13;
      v50 = v32;
      v49 = L"Initializing Side-B Bidi";
      v48 = this;
      v47 = (const wchar_t *)"CMidi2LoopbackMidiBidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v27,
        (unsigned int)byte_180058015,
        v28,
        v29,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v49,
        (__int64)&v50,
        (__int64)&v51);
    }
    v33 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = a5;
    if ( a5 )
      (*(void (__fastcall **)(struct IMidiCallback *))(*(_QWORD *)a5 + 8LL))(a5);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v25 = 0;
    goto LABEL_33;
  }
  if ( v30 > 2 )
  {
    if ( *((_QWORD *)this + 7) > 7u )
      v18 = *(const char **)v18;
    v51 = v18;
    if ( *((_QWORD *)this + 13) > 7u )
      v13 = *(CMidi2LoopbackMidiBidi **)v13;
    v50 = v13;
    v49 = L"We don't understand the endpoint Id";
    v48 = this;
    v47 = (const wchar_t *)"CMidi2LoopbackMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v27,
      (unsigned int)byte_180057FC5,
      v28,
      v29,
      (__int64)&v47,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v50,
      (__int64)&v51);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180011980  mov     [rsp-8+arg_10], rbx
0x180011985  push    rbp
0x180011986  push    rsi
0x180011987  push    rdi
0x180011988  push    r12
0x18001198a  push    r13
0x18001198c  push    r14
0x18001198e  push    r15
0x180011990  lea     rbp, [rsp-60h]
0x180011995  sub     rsp, 160h
0x18001199c  mov     rax, cs:__security_cookie
0x1800119a3  xor     rax, rsp
0x1800119a6  mov     [rbp+90h+var_38], rax
0x1800119aa  mov     rbx, rdx
0x1800119ad  mov     r14, rcx
0x1800119b0  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x1800119b5  mov     rcx, [rax+8]
0x1800119b9  mov     eax, [rcx]
0x1800119bb  lea     r15, aCmidi2loopback_3; "CMidi2LoopbackMidiBidi::Initialize"
0x1800119c2  cmp     eax, 4
0x1800119c5  jbe     short loc_180011A00
0x1800119c7  mov     [rsp+190h+var_140], rbx
0x1800119cc  mov     [rsp+190h+var_138], r14
0x1800119d1  mov     [rsp+190h+var_130], r15
0x1800119d6  lea     rax, [rsp+190h+var_140]
0x1800119db  mov     [rsp+190h+var_160], rax
0x1800119e0  lea     rax, [rsp+190h+var_138]
0x1800119e5  mov     [rsp+190h+var_168], rax
0x1800119ea  lea     rax, [rsp+190h+var_130]
0x1800119ef  mov     [rsp+190h+var_170], rax
0x1800119f4  lea     rdx, word_180057E8A
0x1800119fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180011a00  mov     rax, [rbp+90h+arg_28]
0x180011a07  mov     [r14+48h], rax
0x180011a0b  xorps   xmm0, xmm0
0x180011a0e  movups  [rbp+90h+var_B8], xmm0
0x180011a12  xorps   xmm1, xmm1
0x180011a15  movdqu  [rbp+90h+var_A8], xmm1
0x180011a1a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011a1e  xor     r12d, r12d
0x180011a21  inc     r8
0x180011a24  cmp     [rbx+r8*2], r12w
0x180011a29  jnz     short loc_180011A21
0x180011a2b  mov     rdx, rbx
0x180011a2e  lea     rcx, [rbp+90h+var_B8]
0x180011a32  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011a37  lea     rdx, [rbp+90h+var_B8]
0x180011a3b  lea     rcx, [rbp+90h+var_78]
0x180011a3f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011a44  mov     rdx, rax
0x180011a47  lea     rcx, [rbp+90h+var_98]
0x180011a4b  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x180011a50  lea     rsi, [r14+50h]
0x180011a54  lea     rdx, [rbp+90h+var_98]
0x180011a58  mov     rcx, rsi
0x180011a5b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011a60  lea     rcx, [rbp+90h+var_98]; void *
0x180011a64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011a69  lea     rcx, [rbp+90h+var_B8]; void *
0x180011a6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011a72  mov     rdx, rsi
0x180011a75  lea     rcx, [rbp+90h+var_F8]
0x180011a79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011a7e  mov     rbx, rax
0x180011a81  mov     rdx, rax
0x180011a84  lea     rcx, [rbp+90h+var_98]
0x180011a88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011a8d  mov     rdx, rax
0x180011a90  lea     rcx, [rbp+90h+var_58]
0x180011a94  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x180011a99  xorps   xmm0, xmm0
0x180011a9c  movups  [rbp+90h+var_B8], xmm0
0x180011aa0  xorps   xmm1, xmm1
0x180011aa3  movdqu  [rbp+90h+var_A8], xmm1
0x180011aa8  xor     r8d, r8d
0x180011aab  lea     rdx, S2
0x180011ab2  lea     rcx, [rbp+90h+var_B8]
0x180011ab6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011abb  xorps   xmm0, xmm0
0x180011abe  movups  [rbp+90h+var_98], xmm0
0x180011ac2  xorps   xmm1, xmm1
0x180011ac5  movdqu  [rbp+90h+var_88], xmm1
0x180011aca  mov     r8d, 2Ah ; '*'
0x180011ad0  lea     rdx, a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x180011ad7  lea     rcx, [rbp+90h+var_98]
0x180011adb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011ae0  lea     rdx, [rbp+90h+var_58]
0x180011ae4  lea     rcx, [rbp+90h+var_D8]
0x180011ae8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011aed  lea     r9, [rbp+90h+var_B8]
0x180011af1  lea     r8, [rbp+90h+var_98]
0x180011af5  mov     rdx, rax
0x180011af8  lea     rcx, [rsp+190h+var_118]
0x180011afd  call    ?GetSwdStringProperty@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@00@Z; WindowsMidiServicesInternal::GetSwdStringProperty(std::wstring,std::wstring,std::wstring)
0x180011b02  mov     rdx, rax
0x180011b05  lea     rcx, [rbp+90h+var_78]
0x180011b09  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x180011b0e  lea     rcx, [rbp+90h+var_58]; void *
0x180011b12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b17  mov     rcx, rbx; void *
0x180011b1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b1f  lea     rdi, [r14+20h]
0x180011b23  lea     rdx, [rbp+90h+var_78]
0x180011b27  mov     rcx, rdi
0x180011b2a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011b2f  lea     rcx, [rbp+90h+var_78]; void *
0x180011b33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b38  xorps   xmm0, xmm0
0x180011b3b  movups  [rbp+90h+var_B8], xmm0
0x180011b3f  xorps   xmm1, xmm1
0x180011b42  movdqu  [rbp+90h+var_A8], xmm1
0x180011b47  mov     r13d, 0Dh
0x180011b4d  mov     r8d, r13d
0x180011b50  lea     rdx, aMidiuLoopA; "MIDIU_LOOP_A_"
0x180011b57  lea     rcx, [rbp+90h+var_B8]
0x180011b5b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011b60  lea     rdx, [rbp+90h+var_B8]
0x180011b64  mov     rcx, rsi
0x180011b67  call    ?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::wstring const &,std::wstring const &)
0x180011b6c  mov     bl, al
0x180011b6e  lea     rcx, [rbp+90h+var_B8]; void *
0x180011b72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b77  test    bl, bl
0x180011b79  jz      loc_180011C48
0x180011b7f  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180011b84  mov     rcx, [rax+8]
0x180011b88  mov     eax, [rcx]
0x180011b8a  cmp     eax, 4
0x180011b8d  jbe     short loc_180011C0C
0x180011b8f  cmp     qword ptr [rdi+18h], 7
0x180011b94  jbe     short loc_180011B9B
0x180011b96  mov     rax, [rdi]
0x180011b99  jmp     short loc_180011B9E
0x180011b9b  mov     rax, rdi
0x180011b9e  mov     [rsp+190h+var_130], rax
0x180011ba3  cmp     qword ptr [rsi+18h], 7
0x180011ba8  jbe     short loc_180011BAF
0x180011baa  mov     rax, [rsi]
0x180011bad  jmp     short loc_180011BB2
0x180011baf  mov     rax, rsi
0x180011bb2  mov     [rsp+190h+var_138], rax
0x180011bb7  lea     rax, aInitializingSi; "Initializing Side-A Bidi"
0x180011bbe  mov     [rsp+190h+var_140], rax
0x180011bc3  mov     [rsp+190h+var_128], r14
0x180011bc8  mov     [rsp+190h+var_120], r15
0x180011bcd  lea     rax, [rsp+190h+var_130]
0x180011bd2  mov     [rsp+190h+var_150], rax
0x180011bd7  lea     rax, [rsp+190h+var_138]
0x180011bdc  mov     [rsp+190h+var_158], rax
0x180011be1  lea     rax, [rsp+190h+var_140]
0x180011be6  mov     [rsp+190h+var_160], rax
0x180011beb  lea     rax, [rsp+190h+var_128]
0x180011bf0  mov     [rsp+190h+var_168], rax
0x180011bf5  lea     rax, [rsp+190h+var_120]
0x180011bfa  mov     [rsp+190h+var_170], rax
0x180011bff  lea     rdx, dword_180058064
0x180011c06  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180011c0b  nop
0x180011c0c  mov     rbx, [r14+40h]
0x180011c10  mov     rcx, [rbp+90h+arg_20]
0x180011c17  mov     [r14+40h], rcx
0x180011c1b  test    rcx, rcx
0x180011c1e  jz      short loc_180011C2C
0x180011c20  mov     rax, [rcx]
0x180011c23  mov     rax, [rax+8]
0x180011c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c2c  test    rbx, rbx
0x180011c2f  jz      short loc_180011C41
0x180011c31  mov     rax, [rbx]
0x180011c34  mov     rcx, rbx
0x180011c37  mov     rax, [rax+10h]
0x180011c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c40  nop
0x180011c41  mov     al, 1
0x180011c43  jmp     loc_180011D4E
0x180011c48  xorps   xmm0, xmm0
0x180011c4b  movups  [rbp+90h+var_B8], xmm0
0x180011c4f  xorps   xmm1, xmm1
0x180011c52  movdqu  [rbp+90h+var_A8], xmm1
0x180011c57  mov     r8, r13
0x180011c5a  lea     rdx, aMidiuLoopB; "MIDIU_LOOP_B_"
0x180011c61  lea     rcx, [rbp+90h+var_B8]
0x180011c65  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011c6a  lea     rdx, [rbp+90h+var_B8]
0x180011c6e  mov     rcx, rsi
0x180011c71  call    ?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::wstring const &,std::wstring const &)
0x180011c76  mov     bl, al
0x180011c78  lea     rcx, [rbp+90h+var_B8]; void *
0x180011c7c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c81  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180011c86  mov     rcx, [rax+8]
0x180011c8a  mov     eax, [rcx]
0x180011c8c  test    bl, bl
0x180011c8e  jz      loc_180011F19
0x180011c94  cmp     eax, 4
0x180011c97  jbe     short loc_180011D16
0x180011c99  cmp     qword ptr [rdi+18h], 7
0x180011c9e  jbe     short loc_180011CA5
0x180011ca0  mov     rax, [rdi]
0x180011ca3  jmp     short loc_180011CA8
0x180011ca5  mov     rax, rdi
0x180011ca8  mov     [rsp+190h+var_120], rax
0x180011cad  cmp     qword ptr [rsi+18h], 7
0x180011cb2  jbe     short loc_180011CB9
0x180011cb4  mov     rax, [rsi]
0x180011cb7  jmp     short loc_180011CBC
0x180011cb9  mov     rax, rsi
0x180011cbc  mov     [rsp+190h+var_128], rax
0x180011cc1  lea     rax, aInitializingSi_0; "Initializing Side-B Bidi"
0x180011cc8  mov     [rsp+190h+var_130], rax
0x180011ccd  mov     [rsp+190h+var_138], r14
0x180011cd2  mov     [rsp+190h+var_140], r15
0x180011cd7  lea     rax, [rsp+190h+var_120]
0x180011cdc  mov     [rsp+190h+var_150], rax
0x180011ce1  lea     rax, [rsp+190h+var_128]
0x180011ce6  mov     [rsp+190h+var_158], rax
0x180011ceb  lea     rax, [rsp+190h+var_130]
0x180011cf0  mov     [rsp+190h+var_160], rax
0x180011cf5  lea     rax, [rsp+190h+var_138]
0x180011cfa  mov     [rsp+190h+var_168], rax
0x180011cff  lea     rax, [rsp+190h+var_140]
0x180011d04  mov     [rsp+190h+var_170], rax
0x180011d09  lea     rdx, byte_180058015
0x180011d10  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180011d15  nop
0x180011d16  mov     rbx, [r14+40h]
0x180011d1a  mov     rcx, [rbp+90h+arg_20]
0x180011d21  mov     [r14+40h], rcx
0x180011d25  test    rcx, rcx
0x180011d28  jz      short loc_180011D36
0x180011d2a  mov     rax, [rcx]
0x180011d2d  mov     rax, [rax+8]
0x180011d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d36  test    rbx, rbx
0x180011d39  jz      short loc_180011D4B
0x180011d3b  mov     rax, [rbx]
0x180011d3e  mov     rcx, rbx
0x180011d41  mov     rax, [rax+10h]
0x180011d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d4a  nop
0x180011d4b  mov     al, r12b
0x180011d4e  mov     [r14+18h], al
0x180011d52  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180011d57  mov     rcx, [rax+18h]
0x180011d5b  test    rcx, rcx
0x180011d5e  jz      short loc_180011D64
0x180011d60  lock inc dword ptr [rcx+8]
0x180011d64  mov     rbx, [rax+10h]
0x180011d68  mov     r15, [rax+18h]
0x180011d6c  mov     rdx, rdi
0x180011d6f  lea     rcx, [rsp+190h+var_118]
0x180011d74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011d79  mov     rdx, rax
0x180011d7c  mov     rcx, rbx
0x180011d7f  call    ?GetDevice@MidiLoopbackDeviceTable@@QEAAPEAVMidiLoopbackDevice@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MidiLoopbackDeviceTable::GetDevice(std::wstring)
0x180011d84  mov     r13, rax
0x180011d87  test    r15, r15
0x180011d8a  jz      short loc_180011DC5
0x180011d8c  or      ecx, 0FFFFFFFFh
0x180011d8f  lock xadd [r15+8], ecx
0x180011d95  cmp     ecx, 1
0x180011d98  jnz     short loc_180011DC5
0x180011d9a  mov     rdx, [r15]
0x180011d9d  mov     rcx, r15
0x180011da0  mov     rax, [rdx]
0x180011da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da8  or      eax, 0FFFFFFFFh
0x180011dab  lock xadd [r15+0Ch], eax
0x180011db1  cmp     eax, 1
0x180011db4  jnz     short loc_180011DC5
0x180011db6  mov     rax, [r15]
0x180011db9  mov     rcx, r15
0x180011dbc  mov     rax, [rax+8]
0x180011dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc5  test    r13, r13
0x180011dc8  jz      loc_180011E8C
0x180011dce  lea     rbx, [r14+8]
0x180011dd2  cmp     [r14+18h], r12b
0x180011dd6  jz      short loc_180011E26
0x180011dd8  test    rbx, rbx
0x180011ddb  jz      short loc_180011DED
0x180011ddd  mov     rax, [rbx]
0x180011de0  mov     rcx, rbx
0x180011de3  mov     rax, [rax+8]
0x180011de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dec  nop
0x180011ded  mov     rdi, [r13+1D0h]
0x180011df4  mov     [r13+1D0h], rbx
0x180011dfb  test    rbx, rbx
0x180011dfe  jz      short loc_180011E0F
0x180011e00  mov     rax, [rbx]
0x180011e03  mov     rcx, rbx
0x180011e06  mov     rax, [rax+8]
0x180011e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e0f  test    rdi, rdi
0x180011e12  jz      short loc_180011E24
0x180011e14  mov     rax, [rdi]
0x180011e17  mov     rcx, rdi
0x180011e1a  mov     rax, [rax+10h]
0x180011e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
