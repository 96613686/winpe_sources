# CMidiBuilder::EnumerateMidiSynth(void)

- ea: `0x180037790`
- end: `0x180037a6b`
- name: `?EnumerateMidiSynth@CMidiBuilder@@AEAAJXZ`
- size: `731`
- prototype: `__int64 __fastcall(CMidiBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003772c`

## callees

- `0x180001734`
- `0x180006b0c`
- `0x18000ceb0`
- `0x18001f2b0`
- `0x18001f374`
- `0x1800360d0`
- `0x180037558`
- `0x180037790`
- `0x18003e920`
- `0x18003f7a4`
- `0x18004c598`
- `0x1800527d8`
- `0x180052844`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003788a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003788a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037912`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037912`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800379b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800379b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800377f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800377f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003799e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003799e`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18003780f`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18003780f`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180037986`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180037986`

## pseudocode

```c
__int64 __fastcall CMidiBuilder::EnumerateMidiSynth(CMidiBuilder *this)
{
  char *v1; // rsi
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  char v5; // r15
  void *v6; // rcx
  signed int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  signed int LastError; // eax
  const char *v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  const struct _tlgProvider_t *v20; // rax
  int v21; // r8d
  int v22; // r9d
  ATL::CAtlException *v24; // rbx
  void *v25; // [rsp+48h] [rbp-140h] BYREF
  signed int v26; // [rsp+50h] [rbp-138h] BYREF
  const char *v27; // [rsp+58h] [rbp-130h] BYREF
  __int64 v28; // [rsp+60h] [rbp-128h] BYREF
  ATL::CAtlException *v29; // [rsp+68h] [rbp-120h] BYREF
  int v30; // [rsp+70h] [rbp-118h] BYREF
  LPVOID pv[4]; // [rsp+78h] [rbp-110h] BYREF
  int v32; // [rsp+98h] [rbp-F0h]
  __int64 v33; // [rsp+A0h] [rbp-E8h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-B0h] BYREF
  WCHAR Buffer[56]; // [rsp+E0h] [rbp-A8h] BYREF

  memset_0(&v30, 0, 0x48u);
  v1 = 0;
  v25 = 0;
  v28 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Midi.MidiSynthesizer", 0x24u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180037A6ALL);
  }
  v5 = 0;
  if ( (int)RoGetActivatableClassRegistration(string, &v28) >= 0 )
  {
    v7 = ((int (__stdcall *)(void *, unsigned int, unsigned __int64, void **))CTCoAllocPolicy::Alloc)(
           v6,
           1u,
           0x40u,
           &v25);
    v1 = (char *)v25;
    if ( v7 >= 0 )
    {
      *((_DWORD *)v25 + 2) = 1;
      v7 = _AllocString<CTCoAllocPolicy>(v9, v8, L"MicrosoftGSWavetableSynth", v1);
      if ( v7 >= 0 )
      {
        *((_DWORD *)v1 + 14) = 0;
        *((_DWORD *)v1 + 3) = 1;
        *((_QWORD *)v1 + 6) = 0;
        if ( LoadStringW(g_hInstance, 0x12Cu, Buffer, 50) > 0 )
        {
          v13 = v1 + 32;
          v27 = v1 + 32;
          v7 = _AllocString<CTCoAllocPolicy>(v11, v10, Buffer, (_QWORD *)v1 + 4);
          if ( v7 >= 0 )
          {
            EnterCriticalSection(&MidiPortsLock);
            *((_DWORD *)v1 + 4) = 1;
            v7 = 0;
            if ( __eh34_try(-1, 0) )
            {
              __eh34_scope_strut(0);
              ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(v14, &v25);
            }
            if ( __eh34_catch(0) )
            {
              if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v29) )
              {
                v24 = v29;
                if ( *(_DWORD *)v29 == -1073741571 )
                  _o__resetstkoflw();
                v26 = *(_DWORD *)v24;
                v7 = v26;
                v1 = (char *)v25;
                v5 = 0;
                v13 = v27;
                __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800378F8);
              }
            }
            LeaveCriticalSection(&MidiPortsLock);
            if ( v7 >= 0 )
            {
              v5 = 1;
              v30 = 72;
              v7 = _AllocString<CTCoAllocPolicy>(v16, v15, L"MicrosoftGSWavetableSynth", pv);
              if ( v7 >= 0 )
              {
                v32 = 0;
                v33 = *(_QWORD *)v13;
                v7 = SwDeviceCreate(L"MMDEVAPI", L"HTREE\\ROOT\\0", &v30, 0);
                if ( v7 >= 0 )
                  v1 = 0;
                v25 = v1;
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
  CoTaskMemFree(pv[0]);
  if ( v1 && v5 )
  {
    EnterCriticalSection(&MidiPortsLock);
    v18 = ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(v17, &v25);
    ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(v19, v18);
    LeaveCriticalSection(&MidiPortsLock);
  }
  MidiPortDeepFree((LPVOID *)v1);
  if ( v7 < 0 )
  {
    v20 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v20 > 2u )
    {
      v26 = v7;
      LODWORD(v25) = 452;
      v27 = "CMidiBuilder::EnumerateMidiSynth";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)v20,
        (int)byte_180077343,
        v21,
        v22,
        (const unsigned __int16 **)&v27,
        (__int64)&v25,
        (__int64)&v26);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180037790  push    rbx
0x180037792  push    rsi
0x180037793  push    rdi
0x180037794  push    r12
0x180037796  push    r15
0x180037798  sub     rsp, 160h
0x18003779f  mov     rax, cs:__security_cookie
0x1800377a6  xor     rax, rsp
0x1800377a9  mov     [rsp+188h+var_38], rax
0x1800377b1  xor     edx, edx; Val
0x1800377b3  lea     r8d, [rdx+48h]; Size
0x1800377b7  lea     rcx, [rsp+188h+var_118]; void *
0x1800377bc  call    memset_0
0x1800377c1  xor     edi, edi
0x1800377c3  mov     esi, edi
0x1800377c5  mov     [rsp+188h+var_140], rdi
0x1800377ca  mov     [rsp+188h+var_128], rdi
0x1800377cf  mov     [rsp+188h+string], rdi
0x1800377d7  lea     r9, [rsp+188h+string]; string
0x1800377df  lea     r8, [rsp+188h+hstringHeader]; hstringHeader
0x1800377e7  lea     edx, [rdi+24h]; length
0x1800377ea  lea     rcx, sourceString; "Windows.Devices.Midi.MidiSynthesizer"
0x1800377f1  call    cs:__imp_WindowsCreateStringReference
0x1800377f7  test    eax, eax
0x1800377f9  js      loc_180037A63
0x1800377ff  mov     r15b, dil
0x180037802  lea     rdx, [rsp+188h+var_128]
0x180037807  mov     rcx, [rsp+188h+string]
0x18003780f  call    cs:__imp_RoGetActivatableClassRegistration
0x180037815  test    eax, eax
0x180037817  jns     short loc_180037820
0x180037819  mov     ebx, edi
0x18003781b  jmp     loc_180037999
0x180037820  lea     r9, [rsp+188h+var_140]; void **
0x180037825  mov     edx, 1; unsigned int
0x18003782a  lea     r8d, [rdx+3Fh]; unsigned __int64
0x18003782e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180037833  mov     ebx, eax
0x180037835  mov     rsi, [rsp+188h+var_140]
0x18003783a  test    eax, eax
0x18003783c  js      loc_180037999
0x180037842  mov     dword ptr [rsi+8], 1
0x180037849  mov     r9, rsi
0x18003784c  lea     r8, aMicrosoftgswav; "MicrosoftGSWavetableSynth"
0x180037853  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180037858  mov     ebx, eax
0x18003785a  test    eax, eax
0x18003785c  js      loc_180037999
0x180037862  mov     [rsi+38h], edi
0x180037865  mov     dword ptr [rsi+0Ch], 1
0x18003786c  mov     [rsi+30h], rdi
0x180037870  mov     r9d, 32h ; '2'; cchBufferMax
0x180037876  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x18003787e  mov     edx, 12Ch; uID
0x180037883  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18003788a  call    cs:__imp_LoadStringW
0x180037890  test    eax, eax
0x180037892  jg      short loc_1800378B2
0x180037894  call    cs:__imp_GetLastError
0x18003789a  mov     ebx, eax
0x18003789c  test    eax, eax
0x18003789e  jle     loc_180037999
0x1800378a4  movzx   ebx, ax
0x1800378a7  or      ebx, 80070000h
0x1800378ad  jmp     loc_180037999
0x1800378b2  lea     r12, [rsi+20h]
0x1800378b6  mov     [rsp+188h+var_130], r12
0x1800378bb  mov     r9, r12
0x1800378be  lea     r8, [rsp+188h+Buffer]
0x1800378c6  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800378cb  mov     ebx, eax
0x1800378cd  test    eax, eax
0x1800378cf  js      loc_180037999
0x1800378d5  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x1800378dc  call    cs:__imp_EnterCriticalSection
0x1800378e2  mov     dword ptr [rsi+10h], 1
0x1800378e9  mov     ebx, edi
0x1800378eb  lea     rdx, [rsp+188h+var_140]
0x1800378f0  call    ?AddTail@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBQEAU_MIDIPORT@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(_MIDIPORT * const &)
0x1800378f5  nop
0x1800378f6  jmp     short loc_18003790B
0x1800378f8  xor     edi, edi
0x1800378fa  mov     ebx, [rsp+188h+var_138]
0x1800378fe  mov     rsi, [rsp+188h+var_140]
0x180037903  mov     r15b, dil
0x180037906  mov     r12, [rsp+188h+var_130]
0x18003790b  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x180037912  call    cs:__imp_LeaveCriticalSection
0x180037918  test    ebx, ebx
0x18003791a  js      short loc_180037999
0x18003791c  mov     r15b, 1
0x18003791f  mov     [rsp+188h+var_118], 48h ; 'H'
0x180037927  lea     r9, [rsp+188h+pv]
0x18003792c  lea     r8, aMicrosoftgswav; "MicrosoftGSWavetableSynth"
0x180037933  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180037938  mov     ebx, eax
0x18003793a  test    eax, eax
0x18003793c  js      short loc_180037999
0x18003793e  mov     [rsp+188h+var_F0], edi
0x180037945  mov     rax, [r12]
0x180037949  mov     [rsp+188h+var_E8], rax
0x180037951  lea     rax, [rsi+18h]
0x180037955  mov     [rsp+188h+var_150], rax
0x18003795a  mov     [rsp+188h+var_158], rsi
0x18003795f  lea     rax, ?SwMidiPortCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SwMidiPortCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180037966  mov     [rsp+188h+var_160], rax
0x18003796b  mov     [rsp+188h+var_168], rdi
0x180037970  xor     r9d, r9d
0x180037973  lea     r8, [rsp+188h+var_118]
0x180037978  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18003797f  lea     rcx, aMmdevapi; "MMDEVAPI"
0x180037986  call    cs:__imp_SwDeviceCreate
0x18003798c  mov     ebx, eax
0x18003798e  test    eax, eax
0x180037990  cmovns  rsi, rdi
0x180037994  mov     [rsp+188h+var_140], rsi
0x180037999  mov     rcx, [rsp+188h+pv]; pv
0x18003799e  call    cs:__imp_CoTaskMemFree
0x1800379a4  test    rsi, rsi
0x1800379a7  jz      short loc_1800379DA
0x1800379a9  test    r15b, r15b
0x1800379ac  jz      short loc_1800379DA
0x1800379ae  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x1800379b5  call    cs:__imp_EnterCriticalSection
0x1800379bb  lea     rdx, [rsp+188h+var_140]
0x1800379c0  call    ?Find@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEBAPEAU__POSITION@@AEBQEAU_MIDIPORT@@PEAU3@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(_MIDIPORT * const &,__POSITION *)
0x1800379c5  mov     rdx, rax
0x1800379c8  call    ?RemoveAt@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(__POSITION *)
0x1800379cd  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x1800379d4  call    cs:__imp_LeaveCriticalSection
0x1800379da  mov     rcx, rsi; pv
0x1800379dd  call    ?MidiPortDeepFree@@YAXPEAU_MIDIPORT@@@Z; MidiPortDeepFree(_MIDIPORT *)
0x1800379e2  test    ebx, ebx
0x1800379e4  jns     short loc_180037A38
0x1800379e6  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800379eb  mov     ecx, [rax]
0x1800379ed  cmp     ecx, 2
0x1800379f0  jbe     short loc_180037A38
0x1800379f2  mov     [rsp+188h+var_138], ebx
0x1800379f6  mov     dword ptr [rsp+188h+var_140], 1C4h
0x1800379fe  lea     rcx, aCmidibuilderEn_0; "CMidiBuilder::EnumerateMidiSynth"
0x180037a05  mov     [rsp+188h+var_130], rcx
0x180037a0a  lea     rcx, [rsp+188h+var_138]
0x180037a0f  mov     [rsp+188h+var_158], rcx
0x180037a14  lea     rcx, [rsp+188h+var_140]
0x180037a19  mov     [rsp+188h+var_160], rcx
0x180037a1e  lea     rcx, [rsp+188h+var_130]
0x180037a23  mov     [rsp+188h+var_168], rcx
0x180037a28  lea     rdx, byte_180077343
0x180037a2f  mov     rcx, rax
0x180037a32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037a37  nop
0x180037a38  lea     rcx, [rsp+188h+var_128]
0x180037a3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037a42  mov     eax, ebx
0x180037a44  mov     rcx, [rsp+188h+var_38]
0x180037a4c  xor     rcx, rsp; StackCookie
0x180037a4f  call    __security_check_cookie
0x180037a54  add     rsp, 160h
0x180037a5b  pop     r15
0x180037a5d  pop     r12
0x180037a5f  pop     rdi
0x180037a60  pop     rsi
0x180037a61  pop     rbx
0x180037a62  retn
0x180037a63  mov     ecx, eax; this
0x180037a65  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
