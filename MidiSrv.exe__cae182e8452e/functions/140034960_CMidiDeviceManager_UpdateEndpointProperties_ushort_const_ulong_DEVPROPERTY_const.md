# CMidiDeviceManager::UpdateEndpointProperties(ushort const *,ulong,_DEVPROPERTY const *)

- ea: `0x140034960`
- end: `0x140034f3c`
- name: `?UpdateEndpointProperties@CMidiDeviceManager@@UEAAJPEBGKPEBU_DEVPROPERTY@@@Z`
- size: `1500`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, const unsigned __int16 *, unsigned int, const struct _DEVPROPERTY *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140001f28`
- `0x140002184`
- `0x140002f48`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x140013a38`
- `0x14001dccc`
- `0x140028430`
- `0x140032ff4`
- `0x140034960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034e4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034f04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034e4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140034aa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140034aa6`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x140034b99`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x140034b99`

## string_xrefs

- `0x1400349ad`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140034e33`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400349e5`: `CMidiDeviceManager::UpdateEndpointProperties`
- `0x140034bee`: `CMidiDeviceManager::UpdateEndpointProperties`
- `0x140034ea5`: `CMidiDeviceManager::UpdateEndpointProperties`
- `0x140034b15`: `Device not found. If the updates are from the config file, the device may not yet have been enumerated.`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::UpdateEndpointProperties(
        CMidiDeviceManager *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct _DEVPROPERTY *a4)
{
  __int64 v8; // rdx
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  struct _MIDIPORT **v15; // rbx
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  char **v19; // rax
  int v20; // r15d
  __int64 *v21; // rax
  __int64 v22; // rcx
  _DWORD *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  char **v26; // rax
  char v27; // r9
  int v28; // r10d
  unsigned int i; // r8d
  DEVPROPID pid; // eax
  int v31; // eax
  _DWORD *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  char **v35; // rax
  int v36; // [rsp+20h] [rbp-E0h]
  const wchar_t *v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v39; // [rsp+68h] [rbp-98h] BYREF
  const char *v40; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+90h] [rbp-70h]
  _BYTE v44[4]; // [rsp+94h] [rbp-6Ch]
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int128 v46; // [rsp+A0h] [rbp-60h]
  int v47; // [rsp+B0h] [rbp-50h]
  char v48; // [rsp+B4h] [rbp-4Ch]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-30h]
  char v52; // [rsp+D4h] [rbp-2Ch]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int128 v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+F0h] [rbp-10h]
  char v56; // [rsp+F4h] [rbp-Ch]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  int v59; // [rsp+110h] [rbp+10h]
  char v60; // [rsp+114h] [rbp+14h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  __int128 v62; // [rsp+120h] [rbp+20h]
  int v63; // [rsp+130h] [rbp+30h]
  char v64; // [rsp+134h] [rbp+34h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  __int128 v66; // [rsp+140h] [rbp+40h]
  int v67; // [rsp+150h] [rbp+50h]
  char v68; // [rsp+154h] [rbp+54h]
  int v69; // [rsp+158h] [rbp+58h]
  int v70; // [rsp+15Ch] [rbp+5Ch]
  __int128 v71; // [rsp+160h] [rbp+60h]
  int v72; // [rsp+170h] [rbp+70h]
  char v73; // [rsp+174h] [rbp+74h]
  int v74; // [rsp+178h] [rbp+78h]
  int v75; // [rsp+17Ch] [rbp+7Ch]
  __int128 v76; // [rsp+180h] [rbp+80h]
  int v77; // [rsp+190h] [rbp+90h]
  char v78; // [rsp+194h] [rbp+94h]
  __int64 v79; // [rsp+198h] [rbp+98h]
  __int128 v80; // [rsp+1A0h] [rbp+A0h]
  int v81; // [rsp+1B0h] [rbp+B0h]
  char v82; // [rsp+1B4h] [rbp+B4h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]
  __int128 v84; // [rsp+1C0h] [rbp+C0h]
  int v85; // [rsp+1D0h] [rbp+D0h]
  char v86; // [rsp+1D4h] [rbp+D4h]
  __int64 v87; // [rsp+1D8h] [rbp+D8h]
  _BYTE v88[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char *v89[3]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v90; // [rsp+218h] [rbp+118h]
  _OWORD v91[2]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a2 )
  {
    v8 = 1615;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v36);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v8 = 1616;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v8 = 1617;
    goto LABEL_3;
  }
  v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    *(_QWORD *)v38 = a2;
    v39 = (const wchar_t *)this;
    v37 = (const wchar_t *)"CMidiDeviceManager::UpdateEndpointProperties";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (__int64)byte_140088C5B,
      v11,
      v12,
      &v37,
      (__int64)&v39,
      v38);
  }
  memset(v91, 0, sizeof(v91));
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v91, a2, v13);
  v14 = std::wstring::wstring((__int64)v88, (__int64)v91);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v89, v14);
  std::wstring::~wstring((char **)v91);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::unique_ptr__MIDIPORT_std::default_delete__MIDIPORT___________CMidiDeviceManager::UpdateEndpointProperties_::_2_::_lambda_1___(
    &v37,
    *((_QWORD *)this + 17),
    *((_QWORD *)this + 18),
    v89);
  v15 = (struct _MIDIPORT **)v37;
  if ( v37 == *((const wchar_t **)this + 18) )
  {
    v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v16 > 2u )
    {
      v19 = v89;
      if ( v90 > 7 )
        v19 = (char **)v89[0];
      v37 = (const wchar_t *)v19;
      v39 = L"Device not found. If the updates are from the config file, the device may not yet have been enumerated.";
      *(_QWORD *)v38 = this;
      v40 = "CMidiDeviceManager::UpdateEndpointProperties";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v16,
        (__int64)&unk_14008A3A8,
        v17,
        v18,
        &v40,
        (__int64)v38,
        &v39,
        &v37);
    }
    if ( this != (CMidiDeviceManager *)-96LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v20 = -2147023728;
  }
  else
  {
    v21 = *(__int64 **)(*(_QWORD *)v37 + 24LL);
    if ( v21 )
      v22 = *v21;
    else
      v22 = 0;
    v20 = SwDeviceInterfacePropertySet(v22, *(_QWORD *)(*(_QWORD *)v37 + 40LL), a3, a4);
    if ( v20 < 0 )
    {
      v32 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v32 > 2u )
      {
        v35 = v89;
        if ( v90 > 7 )
          v35 = (char **)v89[0];
        v40 = (const char *)v35;
        v37 = L"Error setting properties";
        v41 = "CMidiDeviceManager::UpdateEndpointProperties";
        v38[0] = v20;
        v39 = (const wchar_t *)this;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v32,
          (__int64)byte_14008A50B,
          v33,
          v34,
          &v41,
          (__int64)&v39,
          &v37,
          (__int64)v38,
          &v40);
      }
      if ( this != (CMidiDeviceManager *)-96LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    }
    else
    {
      v23 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v23 > 4u )
      {
        v26 = v89;
        if ( v90 > 7 )
          v26 = (char **)v89[0];
        v40 = (const char *)v26;
        v37 = L"Properties set";
        *(_QWORD *)v38 = "CMidiDeviceManager::UpdateEndpointProperties";
        v39 = (const wchar_t *)this;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v23,
          (__int64)byte_140088BF5,
          v24,
          v25,
          v38,
          (__int64)&v39,
          &v37,
          &v40);
      }
      v27 = 0;
      v43 = 16;
      v28 = 0;
      v47 = 500;
      v51 = 50;
      v55 = 180;
      v59 = 182;
      v63 = 183;
      v67 = 200;
      v72 = 300;
      v77 = 140;
      v81 = 960;
      v44[0] = 0;
      v45 = 0;
      v48 = 0;
      v49 = 0;
      v52 = 0;
      v53 = 0;
      v56 = 0;
      v57 = 0;
      v60 = 0;
      v61 = 0;
      v64 = 0;
      v65 = 0;
      v68 = 1;
      v69 = 200;
      v70 = 231;
      v73 = 1;
      v74 = 300;
      v75 = 331;
      v78 = 0;
      v79 = 0;
      v82 = 0;
      v83 = 0;
      v85 = 955;
      v86 = 0;
      v87 = 0;
      v42 = PKEY_MIDI_CustomPortNumber;
      v46 = PKEY_MIDI_CustomEndpointName;
      v50 = PKEY_MIDI_GroupTerminalBlocks;
      v54 = PKEY_MIDI_FunctionBlockDeclaredCount;
      v58 = PKEY_MIDI_FunctionBlocksAreStatic;
      v62 = PKEY_MIDI_FunctionBlocksLastUpdateTime;
      v66 = PKEY_MIDI_FunctionBlock00;
      v71 = PKEY_MIDI_FunctionBlockName00;
      v76 = PKEY_MIDI_EndpointDiscoveryProcessComplete;
      v80 = PKEY_MIDI_Midi1PortNameTable;
      v84 = PKEY_MIDI_Midi1PortNamingSelection;
      while ( !v27 )
      {
        for ( i = 0; i < 0xB; ++i )
        {
          if ( v27 )
            break;
          if ( *(_OWORD *)&a4[v28].CompKey.Key.fmtid == __PAIR128__(
                                                          *((_QWORD *)&v42 + 4 * i + 1),
                                                          *((_QWORD *)&v42 + 4 * i)) )
          {
            pid = a4[v28].CompKey.Key.pid;
            if ( pid == *(_DWORD *)&v44[32 * i - 4]
              || v44[32 * i] && pid >= *((_DWORD *)&v45 + 8 * i) && pid <= *((_DWORD *)&v45 + 8 * i + 1) )
            {
              v27 = 1;
            }
          }
        }
        if ( ++v28 >= a3 )
        {
          if ( !v27 )
            goto LABEL_43;
          break;
        }
      }
      v31 = CMidiDeviceManager::SyncMidi1Ports(this, *v15);
      if ( v31 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6C3,
          (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
          (const char *)(unsigned int)v31);
LABEL_43:
      if ( this != (CMidiDeviceManager *)-96LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      v20 = 0;
    }
  }
  std::wstring::~wstring(v89);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140034960  push    rbp
0x140034962  push    rbx
0x140034963  push    rsi
0x140034964  push    rdi
0x140034965  push    r12
0x140034967  push    r13
0x140034969  push    r14
0x14003496b  push    r15
0x14003496d  lea     rbp, [rsp-158h]
0x140034975  sub     rsp, 258h
0x14003497c  mov     rax, cs:__security_cookie
0x140034983  xor     rax, rsp
0x140034986  mov     [rbp+190h+var_50], rax
0x14003498d  xor     r13d, r13d
0x140034990  mov     r12, r9
0x140034993  mov     r14d, r8d
0x140034996  mov     rbx, rdx
0x140034999  mov     rsi, rcx
0x14003499c  test    rdx, rdx
0x14003499f  jnz     short loc_1400349C8
0x1400349a1  mov     edx, 64Fh; void *
0x1400349a6  mov     rcx, [rbp+198h]; this
0x1400349ad  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x1400349b4  mov     ebx, 80070057h
0x1400349b9  mov     r9d, ebx; char *
0x1400349bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400349c1  mov     eax, ebx
0x1400349c3  jmp     loc_140034F19
0x1400349c8  test    r12, r12
0x1400349cb  jnz     short loc_1400349D4
0x1400349cd  mov     edx, 650h
0x1400349d2  jmp     short loc_1400349A6
0x1400349d4  test    r14d, r14d
0x1400349d7  jnz     short loc_1400349E0
0x1400349d9  mov     edx, 651h
0x1400349de  jmp     short loc_1400349A6
0x1400349e0  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400349e5  lea     r15, aCmidideviceman_18; "CMidiDeviceManager::UpdateEndpointPrope"...
0x1400349ec  mov     rcx, [rax+8]
0x1400349f0  mov     eax, [rcx]
0x1400349f2  cmp     eax, 4
0x1400349f5  jbe     short loc_140034A3F
0x1400349f7  lea     rax, [rsp+290h+var_240]
0x1400349fc  mov     [rsp+290h+var_240], r14d
0x140034a01  mov     [rsp+290h+var_258], rax
0x140034a06  lea     rdx, byte_140088C5B
0x140034a0d  lea     rax, [rsp+290h+var_230]
0x140034a12  mov     qword ptr [rsp+290h+var_230], rbx
0x140034a17  mov     [rsp+290h+var_260], rax
0x140034a1c  lea     rax, [rsp+290h+var_228]
0x140034a21  mov     [rsp+290h+var_268], rax
0x140034a26  lea     rax, [rsp+290h+var_238]
0x140034a2b  mov     qword ptr [rsp+290h+var_270], rax
0x140034a30  mov     [rsp+290h+var_228], rsi
0x140034a35  mov     [rsp+290h+var_238], r15
0x140034a3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140034a3f  xorps   xmm0, xmm0
0x140034a42  xorps   xmm1, xmm1
0x140034a45  movups  [rbp+190h+var_70], xmm0
0x140034a4c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034a50  movdqu  [rbp+190h+var_60], xmm1
0x140034a58  inc     r8
0x140034a5b  cmp     [rbx+r8*2], r13w
0x140034a60  jnz     short loc_140034A58
0x140034a62  mov     rdx, rbx
0x140034a65  lea     rcx, [rbp+190h+var_70]
0x140034a6c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140034a71  lea     rdx, [rbp+190h+var_70]
0x140034a78  lea     rcx, [rbp+190h+var_B0]
0x140034a7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140034a84  mov     rdx, rax
0x140034a87  lea     rcx, [rbp+190h+var_90]
0x140034a8e  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140034a93  lea     rcx, [rbp+190h+var_70]; void *
0x140034a9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140034a9f  lea     rdi, [rsi+60h]
0x140034aa3  mov     rcx, rdi; lpCriticalSection
0x140034aa6  call    cs:__imp_EnterCriticalSection
0x140034aac  mov     r8, [rsi+90h]
0x140034ab3  lea     r9, [rbp+190h+var_90]
0x140034aba  mov     rdx, [rsi+88h]
0x140034ac1  lea     rcx, [rsp+290h+var_238]
0x140034ac6  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__unique_ptr__MIDIPORT_std__default_delete__MIDIPORT___________CMidiDeviceManager__UpdateEndpointProperties____2____lambda_1___
0x140034acb  mov     rbx, [rsp+290h+var_238]
0x140034ad0  cmp     rbx, [rsi+90h]
0x140034ad7  jnz     loc_140034B7B
0x140034add  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140034ae2  mov     rcx, [rax+8]
0x140034ae6  mov     eax, [rcx]
0x140034ae8  cmp     eax, 2
0x140034aeb  jbe     short loc_140034B62
0x140034aed  cmp     [rbp+190h+var_78], 7
0x140034af5  lea     rax, [rbp+190h+var_90]
0x140034afc  lea     rdx, unk_14008A3A8
0x140034b03  mov     [rsp+290h+var_240], r14d
0x140034b08  cmova   rax, [rbp+190h+var_90]
0x140034b10  mov     [rsp+290h+var_238], rax
0x140034b15  lea     rax, aDeviceNotFound; "Device not found. If the updates are fr"...
0x140034b1c  mov     [rsp+290h+var_228], rax
0x140034b21  lea     rax, [rsp+290h+var_240]
0x140034b26  mov     [rsp+290h+var_250], rax
0x140034b2b  lea     rax, [rsp+290h+var_238]
0x140034b30  mov     [rsp+290h+var_258], rax
0x140034b35  lea     rax, [rsp+290h+var_228]
0x140034b3a  mov     [rsp+290h+var_260], rax
0x140034b3f  lea     rax, [rsp+290h+var_230]
0x140034b44  mov     [rsp+290h+var_268], rax
0x140034b49  lea     rax, [rsp+290h+var_220]
0x140034b4e  mov     qword ptr [rsp+290h+var_270], rax
0x140034b53  mov     qword ptr [rsp+290h+var_230], rsi
0x140034b58  mov     [rsp+290h+var_220], r15
0x140034b5d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140034b62  test    rdi, rdi
0x140034b65  jz      short loc_140034B70
0x140034b67  mov     rcx, rdi; lpCriticalSection
0x140034b6a  call    cs:__imp_LeaveCriticalSection
0x140034b70  mov     r15d, 80070490h
0x140034b76  jmp     loc_140034F0A
0x140034b7b  mov     rdx, [rbx]
0x140034b7e  mov     rax, [rdx+18h]
0x140034b82  test    rax, rax
0x140034b85  jz      short loc_140034B8C
0x140034b87  mov     rcx, [rax]
0x140034b8a  jmp     short loc_140034B8F
0x140034b8c  mov     rcx, r13
0x140034b8f  mov     rdx, [rdx+28h]
0x140034b93  mov     r9, r12
0x140034b96  mov     r8d, r14d
0x140034b99  call    cs:__imp_SwDeviceInterfacePropertySet
0x140034b9f  mov     r15d, eax
0x140034ba2  test    eax, eax
0x140034ba4  js      loc_140034E5D
0x140034baa  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140034baf  mov     rcx, [rax+8]
0x140034bb3  mov     eax, [rcx]
0x140034bb5  cmp     eax, 4
0x140034bb8  jbe     short loc_140034C36
0x140034bba  cmp     [rbp+190h+var_78], 7
0x140034bc2  lea     rax, [rbp+190h+var_90]
0x140034bc9  lea     rdx, byte_140088BF5
0x140034bd0  mov     [rsp+290h+var_240], r14d
0x140034bd5  cmova   rax, [rbp+190h+var_90]
0x140034bdd  mov     [rsp+290h+var_220], rax
0x140034be2  lea     rax, aPropertiesSet; "Properties set"
0x140034be9  mov     [rsp+290h+var_238], rax
0x140034bee  lea     rax, aCmidideviceman_18; "CMidiDeviceManager::UpdateEndpointPrope"...
0x140034bf5  mov     qword ptr [rsp+290h+var_230], rax
0x140034bfa  lea     rax, [rsp+290h+var_240]
0x140034bff  mov     [rsp+290h+var_250], rax
0x140034c04  lea     rax, [rsp+290h+var_220]
0x140034c09  mov     [rsp+290h+var_258], rax
0x140034c0e  lea     rax, [rsp+290h+var_238]
0x140034c13  mov     [rsp+290h+var_260], rax
0x140034c18  lea     rax, [rsp+290h+var_228]
0x140034c1d  mov     [rsp+290h+var_268], rax
0x140034c22  lea     rax, [rsp+290h+var_230]
0x140034c27  mov     qword ptr [rsp+290h+var_270], rax; int
0x140034c2c  mov     [rsp+290h+var_228], rsi
0x140034c31  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140034c36  mov     eax, cs:dword_14007A810
0x140034c3c  mov     r9b, r13b
0x140034c3f  mov     [rbp+190h+var_200], eax
0x140034c42  mov     r10d, r13d
0x140034c45  mov     eax, cs:dword_14007A8D0
0x140034c4b  mov     [rbp+190h+var_1E0], eax
0x140034c4e  mov     eax, cs:dword_14007A8B8
0x140034c54  mov     [rbp+190h+var_1C0], eax
0x140034c57  mov     eax, cs:dword_14007A468
0x140034c5d  mov     [rbp+190h+var_1A0], eax
0x140034c60  mov     eax, cs:dword_14007A828
0x140034c66  mov     [rbp+190h+var_180], eax
0x140034c69  mov     eax, cs:dword_14007A8E8
0x140034c6f  mov     [rbp+190h+var_160], eax
0x140034c72  mov     eax, cs:dword_14007A510
0x140034c78  mov     [rbp+190h+var_140], eax
0x140034c7b  mov     eax, cs:dword_14007A408
0x140034c81  mov     [rbp+190h+var_120], eax
0x140034c84  mov     eax, cs:dword_14007A3F0
0x140034c8a  mov     [rbp+190h+var_100], eax
0x140034c90  mov     eax, cs:dword_14007A900
0x140034c96  mov     [rbp+190h+var_E0], eax
0x140034c9c  mov     eax, cs:dword_14007A840
0x140034ca2  mov     [rbp+190h+var_1FC], r13b
0x140034ca6  mov     [rbp+190h+var_1F8], r13
0x140034caa  mov     [rbp+190h+var_1DC], r13b
0x140034cae  mov     [rbp+190h+var_1D8], r13
0x140034cb2  mov     [rbp+190h+var_1BC], r13b
0x140034cb6  mov     [rbp+190h+var_1B8], r13
0x140034cba  mov     [rbp+190h+var_19C], r13b
0x140034cbe  mov     [rbp+190h+var_198], r13
0x140034cc2  mov     [rbp+190h+var_17C], r13b
0x140034cc6  mov     [rbp+190h+var_178], r13
0x140034cca  mov     [rbp+190h+var_15C], r13b
0x140034cce  mov     [rbp+190h+var_158], r13
0x140034cd2  mov     [rbp+190h+var_13C], 1
0x140034cd6  mov     [rbp+190h+var_138], 0C8h
0x140034cdd  mov     [rbp+190h+var_134], 0E7h
0x140034ce4  mov     [rbp+190h+var_11C], 1
0x140034ce8  mov     [rbp+190h+var_118], 12Ch
0x140034cef  mov     [rbp+190h+var_114], 14Bh
0x140034cf6  mov     [rbp+190h+var_FC], r13b
0x140034cfd  mov     [rbp+190h+var_F8], r13
0x140034d04  mov     [rbp+190h+var_DC], r13b
0x140034d0b  mov     [rbp+190h+var_D8], r13
0x140034d12  mov     [rbp+190h+var_C0], eax
0x140034d18  mov     [rbp+190h+var_BC], r13b
0x140034d1f  mov     [rbp+190h+var_B8], r13
0x140034d26  movups  xmm0, cs:PKEY_MIDI_CustomPortNumber
0x140034d2d  movaps  [rbp+190h+var_210], xmm0
0x140034d31  movups  xmm0, cs:PKEY_MIDI_CustomEndpointName
0x140034d38  movaps  [rbp+190h+var_1F0], xmm0
0x140034d3c  movups  xmm0, cs:PKEY_MIDI_GroupTerminalBlocks
0x140034d43  movaps  [rbp+190h+var_1D0], xmm0
0x140034d47  movups  xmm0, cs:PKEY_MIDI_FunctionBlockDeclaredCount
0x140034d4e  movaps  [rbp+190h+var_1B0], xmm0
0x140034d52  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksAreStatic
0x140034d59  movaps  [rbp+190h+var_190], xmm0
0x140034d5d  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksLastUpdateTime
0x140034d64  movaps  [rbp+190h+var_170], xmm0
0x140034d68  movups  xmm0, cs:PKEY_MIDI_FunctionBlock00
0x140034d6f  movaps  [rbp+190h+var_150], xmm0
0x140034d73  movups  xmm0, cs:PKEY_MIDI_FunctionBlockName00
0x140034d7a  movaps  [rbp+190h+var_130], xmm0
0x140034d7e  movups  xmm0, cs:PKEY_MIDI_EndpointDiscoveryProcessComplete
0x140034d85  movaps  [rbp+190h+var_110], xmm0
0x140034d8c  movups  xmm0, cs:PKEY_MIDI_Midi1PortNameTable
0x140034d93  movaps  [rbp+190h+var_F0], xmm0
0x140034d9a  movups  xmm0, cs:PKEY_MIDI_Midi1PortNamingSelection
0x140034da1  movaps  [rbp+190h+var_D0], xmm0
0x140034da8  test    r14d, r14d
0x140034dab  jz      loc_140034E47
0x140034db1  test    r9b, r9b
0x140034db4  jnz     short loc_140034E1D
0x140034db6  mov     eax, r10d
0x140034db9  mov     r8d, r13d
0x140034dbc  lea     rdx, [rax+rax*2]
0x140034dc0  add     rdx, rdx
0x140034dc3  test    r9b, r9b
0x140034dc6  jnz     short loc_140034E10
0x140034dc8  mov     rax, [r12+rdx*8]
0x140034dcc  mov     ecx, r8d
0x140034dcf  shl     rcx, 5
0x140034dd3  cmp     rax, qword ptr [rbp+rcx+190h+var_210]
0x140034dd8  jnz     short loc_140034E07
0x140034dda  mov     rax, [r12+rdx*8+8]
0x140034ddf  cmp     rax, qword ptr [rbp+rcx+190h+var_210+8]
0x140034de4  jnz     short loc_140034E07
0x140034de6  mov     eax, [r12+rdx*8+10h]
0x140034deb  cmp     eax, [rbp+rcx+190h+var_200]
0x140034def  jz      short loc_140034E04
0x140034df1  cmp     [rbp+rcx+190h+var_1FC], r13b
0x140034df6  jz      short loc_140034E07
0x140034df8  cmp     eax, dword ptr [rbp+rcx+190h+var_1F8]
0x140034dfc  jb      short loc_140034E07
0x140034dfe  cmp     eax, dword ptr [rbp+rcx+190h+var_1F8+4]
0x140034e02  ja      short loc_140034E07
0x140034e04  mov     r9b, 1
0x140034e07  inc     r8d
0x140034e0a  cmp     r8d, 0Bh
0x140034e0e  jb      short loc_140034DC3
0x140034e10  inc     r10d
0x140034e13  cmp     r10d, r14d
0x140034e16  jb      short loc_140034DB1
0x140034e18  test    r9b, r9b
0x140034e1b  jz      short loc_140034E47
0x140034e1d  mov     rdx, [rbx]; struct _MIDIPORT *
0x140034e20  mov     rcx, rsi; this
0x140034e23  call    ?SyncMidi1Ports@CMidiDeviceManager@@AEAAJPEAU_MIDIPORT@@@Z; CMidiDeviceManager::SyncMidi1Ports(_MIDIPORT *)
0x140034e28  test    eax, eax
0x140034e2a  jns     short loc_140034E47
0x140034e2c  mov     rcx, [rbp+198h]; this
0x140034e33  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140034e3a  mov     r9d, eax; char *
0x140034e3d  mov     edx, 6C3h; void *
0x140034e42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140034e47  test    rdi, rdi
0x140034e4a  jz      short loc_140034E55
0x140034e4c  mov     rcx, rdi; lpCriticalSection
0x140034e4f  call    cs:__imp_LeaveCriticalSection
0x140034e55  mov     r15d, r13d
0x140034e58  jmp     loc_140034F0A
0x140034e5d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140034e62  mov     rcx, [rax+8]
0x140034e66  mov     eax, [rcx]
0x140034e68  cmp     eax, 2
0x140034e6b  jbe     loc_140034EFC
0x140034e71  cmp     [rbp+190h+var_78], 7
0x140034e79  lea     rax, [rbp+190h+var_90]
0x140034e80  lea     rdx, byte_14008A50B
0x140034e87  mov     [rsp+290h+var_240], r14d
0x140034e8c  cmova   rax, [rbp+190h+var_90]
0x140034e94  mov     [rsp+290h+var_220], rax
0x140034e99  lea     rax, aErrorSettingPr; "Error setting properties"
0x140034ea0  mov     [rsp+290h+var_238], rax
0x140034ea5  lea     rax, aCmidideviceman_18; "CMidiDeviceManager::UpdateEndpointPrope"...
0x140034eac  mov     [rsp+290h+var_218], rax
0x140034eb1  lea     rax, [rsp+290h+var_240]
0x140034eb6  mov     [rsp+290h+var_248], rax
0x140034ebb  lea     rax, [rsp+290h+var_220]
0x140034ec0  mov     [rsp+290h+var_250], rax
  ... truncated ...
```
