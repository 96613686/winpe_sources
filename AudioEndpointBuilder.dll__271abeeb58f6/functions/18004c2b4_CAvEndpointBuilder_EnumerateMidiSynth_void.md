# CAvEndpointBuilder::EnumerateMidiSynth(void)

- ea: `0x18004c2b4`
- end: `0x18004c58f`
- name: `?EnumerateMidiSynth@CAvEndpointBuilder@@AEAAJXZ`
- size: `731`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e894`

## callees

- `0x180001734`
- `0x180006b0c`
- `0x18000ceb0`
- `0x18001f2b0`
- `0x18001f374`
- `0x1800360d0`
- `0x180037558`
- `0x18003e920`
- `0x18003f7a4`
- `0x18004c2b4`
- `0x18004c598`
- `0x1800527d8`
- `0x180052844`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004c3ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004c3ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c436`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c4f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c436`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c4f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c400`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c4d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c400`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c315`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c4c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c4c2`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18004c333`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18004c333`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004c4aa`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004c4aa`

## pseudocode

```c
__int64 __fastcall CAvEndpointBuilder::EnumerateMidiSynth(CAvEndpointBuilder *this)
{
  char *v1; // rsi
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  char v5; // r15
  void *v6; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  signed int LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  const struct _tlgProvider_t *v19; // rax
  int v20; // r8d
  int v21; // r9d
  void *v23; // [rsp+48h] [rbp-140h] BYREF
  int v24; // [rsp+50h] [rbp-138h] BYREF
  const char *v25; // [rsp+58h] [rbp-130h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-128h] BYREF
  int v27; // [rsp+70h] [rbp-118h] BYREF
  LPVOID pv[4]; // [rsp+78h] [rbp-110h] BYREF
  int v29; // [rsp+98h] [rbp-F0h]
  __int64 v30; // [rsp+A0h] [rbp-E8h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-B0h] BYREF
  WCHAR Buffer[56]; // [rsp+E0h] [rbp-A8h] BYREF

  memset_0(&v27, 0, 0x48u);
  v1 = 0;
  v23 = 0;
  v26[0] = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Midi.MidiSynthesizer", 0x24u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18004C58ELL);
  }
  v5 = 0;
  if ( (int)RoGetActivatableClassRegistration(string, v26) >= 0 )
  {
    v7 = CTCoAllocPolicy::Alloc(v6, 1, 0x40u, &v23);
    v1 = (char *)v23;
    if ( v7 >= 0 )
    {
      *((_DWORD *)v23 + 2) = 1;
      v7 = _AllocString<CTCoAllocPolicy>(v9, v8, L"MicrosoftGSWavetableSynth", v1);
      if ( v7 >= 0 )
      {
        *((_DWORD *)v1 + 14) = 0;
        *((_DWORD *)v1 + 3) = 1;
        *((_QWORD *)v1 + 6) = 0;
        if ( LoadStringW(g_hInstance, 0x12Cu, Buffer, 50) > 0 )
        {
          v25 = v1 + 32;
          v7 = _AllocString<CTCoAllocPolicy>(v11, v10, Buffer, (_QWORD *)v1 + 4);
          if ( v7 >= 0 )
          {
            EnterCriticalSection(&MidiPortsLock);
            *((_DWORD *)v1 + 4) = 1;
            ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(v13, &v23);
            LeaveCriticalSection(&MidiPortsLock);
            v5 = 1;
            v27 = 72;
            v7 = _AllocString<CTCoAllocPolicy>(v15, v14, L"MicrosoftGSWavetableSynth", pv);
            if ( v7 >= 0 )
            {
              v29 = 0;
              v30 = *((_QWORD *)v1 + 4);
              v7 = SwDeviceCreate(L"MMDEVAPI", L"HTREE\\ROOT\\0", &v27, 0);
              if ( v7 >= 0 )
                v1 = 0;
              v23 = v1;
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
    v17 = ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(v16, &v23);
    ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(v18, v17);
    LeaveCriticalSection(&MidiPortsLock);
  }
  MidiPortDeepFree((LPVOID *)v1);
  if ( v7 < 0 )
  {
    v19 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v19 > 2u )
    {
      v24 = v7;
      LODWORD(v23) = 1780;
      v25 = "CAvEndpointBuilder::EnumerateMidiSynth";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v19,
        (unsigned int)&dword_180076DF4,
        v20,
        v21,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v24);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004c2b4  push    rbx
0x18004c2b6  push    rsi
0x18004c2b7  push    rdi
0x18004c2b8  push    r12
0x18004c2ba  push    r15
0x18004c2bc  sub     rsp, 160h
0x18004c2c3  mov     rax, cs:__security_cookie
0x18004c2ca  xor     rax, rsp
0x18004c2cd  mov     [rsp+188h+var_38], rax
0x18004c2d5  xor     edx, edx; Val
0x18004c2d7  lea     r8d, [rdx+48h]; Size
0x18004c2db  lea     rcx, [rsp+188h+var_118]; void *
0x18004c2e0  call    memset_0
0x18004c2e5  xor     edi, edi
0x18004c2e7  mov     esi, edi
0x18004c2e9  mov     [rsp+188h+var_140], rdi
0x18004c2ee  mov     [rsp+188h+var_128], rdi
0x18004c2f3  mov     [rsp+188h+string], rdi
0x18004c2fb  lea     r9, [rsp+188h+string]; string
0x18004c303  lea     r8, [rsp+188h+hstringHeader]; hstringHeader
0x18004c30b  lea     edx, [rdi+24h]; length
0x18004c30e  lea     rcx, sourceString; "Windows.Devices.Midi.MidiSynthesizer"
0x18004c315  call    cs:__imp_WindowsCreateStringReference
0x18004c31b  test    eax, eax
0x18004c31d  js      loc_18004C587
0x18004c323  mov     r15b, dil
0x18004c326  lea     rdx, [rsp+188h+var_128]
0x18004c32b  mov     rcx, [rsp+188h+string]
0x18004c333  call    cs:__imp_RoGetActivatableClassRegistration
0x18004c339  test    eax, eax
0x18004c33b  jns     short loc_18004C344
0x18004c33d  mov     ebx, edi
0x18004c33f  jmp     loc_18004C4BD
0x18004c344  lea     r9, [rsp+188h+var_140]; void **
0x18004c349  mov     edx, 1; unsigned int
0x18004c34e  lea     r8d, [rdx+3Fh]; unsigned __int64
0x18004c352  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004c357  mov     ebx, eax
0x18004c359  mov     rsi, [rsp+188h+var_140]
0x18004c35e  test    eax, eax
0x18004c360  js      loc_18004C4BD
0x18004c366  mov     dword ptr [rsi+8], 1
0x18004c36d  mov     r9, rsi
0x18004c370  lea     r8, aMicrosoftgswav; "MicrosoftGSWavetableSynth"
0x18004c377  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004c37c  mov     ebx, eax
0x18004c37e  test    eax, eax
0x18004c380  js      loc_18004C4BD
0x18004c386  mov     [rsi+38h], edi
0x18004c389  mov     dword ptr [rsi+0Ch], 1
0x18004c390  mov     [rsi+30h], rdi
0x18004c394  mov     r9d, 32h ; '2'; cchBufferMax
0x18004c39a  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x18004c3a2  mov     edx, 12Ch; uID
0x18004c3a7  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18004c3ae  call    cs:__imp_LoadStringW
0x18004c3b4  test    eax, eax
0x18004c3b6  jg      short loc_18004C3D6
0x18004c3b8  call    cs:__imp_GetLastError
0x18004c3be  mov     ebx, eax
0x18004c3c0  test    eax, eax
0x18004c3c2  jle     loc_18004C4BD
0x18004c3c8  movzx   ebx, ax
0x18004c3cb  or      ebx, 80070000h
0x18004c3d1  jmp     loc_18004C4BD
0x18004c3d6  lea     r12, [rsi+20h]
0x18004c3da  mov     [rsp+188h+var_130], r12
0x18004c3df  mov     r9, r12
0x18004c3e2  lea     r8, [rsp+188h+Buffer]
0x18004c3ea  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004c3ef  mov     ebx, eax
0x18004c3f1  test    eax, eax
0x18004c3f3  js      loc_18004C4BD
0x18004c3f9  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x18004c400  call    cs:__imp_EnterCriticalSection
0x18004c406  mov     dword ptr [rsi+10h], 1
0x18004c40d  mov     ebx, edi
0x18004c40f  lea     rdx, [rsp+188h+var_140]
0x18004c414  call    ?AddTail@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBQEAU_MIDIPORT@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(_MIDIPORT * const &)
0x18004c419  nop
0x18004c41a  jmp     short loc_18004C42F
0x18004c41c  xor     edi, edi
0x18004c41e  mov     ebx, [rsp+188h+var_138]
0x18004c422  mov     rsi, [rsp+188h+var_140]
0x18004c427  mov     r15b, dil
0x18004c42a  mov     r12, [rsp+188h+var_130]
0x18004c42f  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x18004c436  call    cs:__imp_LeaveCriticalSection
0x18004c43c  test    ebx, ebx
0x18004c43e  js      short loc_18004C4BD
0x18004c440  mov     r15b, 1
0x18004c443  mov     [rsp+188h+var_118], 48h ; 'H'
0x18004c44b  lea     r9, [rsp+188h+pv]
0x18004c450  lea     r8, aMicrosoftgswav; "MicrosoftGSWavetableSynth"
0x18004c457  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004c45c  mov     ebx, eax
0x18004c45e  test    eax, eax
0x18004c460  js      short loc_18004C4BD
0x18004c462  mov     [rsp+188h+var_F0], edi
0x18004c469  mov     rax, [r12]
0x18004c46d  mov     [rsp+188h+var_E8], rax
0x18004c475  lea     rax, [rsi+18h]
0x18004c479  mov     [rsp+188h+var_150], rax
0x18004c47e  mov     [rsp+188h+var_158], rsi
0x18004c483  lea     rax, ?SwMidiPortCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SwMidiPortCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18004c48a  mov     [rsp+188h+var_160], rax
0x18004c48f  mov     [rsp+188h+var_168], rdi
0x18004c494  xor     r9d, r9d
0x18004c497  lea     r8, [rsp+188h+var_118]
0x18004c49c  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18004c4a3  lea     rcx, aMmdevapi; "MMDEVAPI"
0x18004c4aa  call    cs:__imp_SwDeviceCreate
0x18004c4b0  mov     ebx, eax
0x18004c4b2  test    eax, eax
0x18004c4b4  cmovns  rsi, rdi
0x18004c4b8  mov     [rsp+188h+var_140], rsi
0x18004c4bd  mov     rcx, [rsp+188h+pv]; pv
0x18004c4c2  call    cs:__imp_CoTaskMemFree
0x18004c4c8  test    rsi, rsi
0x18004c4cb  jz      short loc_18004C4FE
0x18004c4cd  test    r15b, r15b
0x18004c4d0  jz      short loc_18004C4FE
0x18004c4d2  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x18004c4d9  call    cs:__imp_EnterCriticalSection
0x18004c4df  lea     rdx, [rsp+188h+var_140]
0x18004c4e4  call    ?Find@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEBAPEAU__POSITION@@AEBQEAU_MIDIPORT@@PEAU3@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(_MIDIPORT * const &,__POSITION *)
0x18004c4e9  mov     rdx, rax
0x18004c4ec  call    ?RemoveAt@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(__POSITION *)
0x18004c4f1  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x18004c4f8  call    cs:__imp_LeaveCriticalSection
0x18004c4fe  mov     rcx, rsi; pv
0x18004c501  call    ?MidiPortDeepFree@@YAXPEAU_MIDIPORT@@@Z; MidiPortDeepFree(_MIDIPORT *)
0x18004c506  test    ebx, ebx
0x18004c508  jns     short loc_18004C55C
0x18004c50a  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18004c50f  mov     ecx, [rax]
0x18004c511  cmp     ecx, 2
0x18004c514  jbe     short loc_18004C55C
0x18004c516  mov     [rsp+188h+var_138], ebx
0x18004c51a  mov     dword ptr [rsp+188h+var_140], 6F4h
0x18004c522  lea     rcx, aCavendpointbui; "CAvEndpointBuilder::EnumerateMidiSynth"
0x18004c529  mov     [rsp+188h+var_130], rcx
0x18004c52e  lea     rcx, [rsp+188h+var_138]
0x18004c533  mov     [rsp+188h+var_158], rcx
0x18004c538  lea     rcx, [rsp+188h+var_140]
0x18004c53d  mov     [rsp+188h+var_160], rcx
0x18004c542  lea     rcx, [rsp+188h+var_130]
0x18004c547  mov     [rsp+188h+var_168], rcx
0x18004c54c  lea     rdx, dword_180076DF4
0x18004c553  mov     rcx, rax
0x18004c556  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004c55b  nop
0x18004c55c  lea     rcx, [rsp+188h+var_128]
0x18004c561  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c566  mov     eax, ebx
0x18004c568  mov     rcx, [rsp+188h+var_38]
0x18004c570  xor     rcx, rsp; StackCookie
0x18004c573  call    __security_check_cookie
0x18004c578  add     rsp, 160h
0x18004c57f  pop     r15
0x18004c581  pop     r12
0x18004c583  pop     rdi
0x18004c584  pop     rsi
0x18004c585  pop     rbx
0x18004c586  retn
0x18004c587  mov     ecx, eax; this
0x18004c589  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
