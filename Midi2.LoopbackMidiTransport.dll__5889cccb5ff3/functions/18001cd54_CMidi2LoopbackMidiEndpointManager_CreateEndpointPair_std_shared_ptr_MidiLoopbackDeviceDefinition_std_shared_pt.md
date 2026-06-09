# CMidi2LoopbackMidiEndpointManager::CreateEndpointPair(std::shared_ptr<MidiLoopbackDeviceDefinition>,std::shared_ptr<MidiLoopbackDeviceDefinition>)

- ea: `0x18001cd54`
- end: `0x18001d181`
- name: `?CreateEndpointPair@CMidi2LoopbackMidiEndpointManager@@QEAAJV?$shared_ptr@UMidiLoopbackDeviceDefinition@@@std@@0@Z`
- size: `1069`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiEndpointManager *this)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x180018710`
- `0x1800203c8`

## callees

- `0x1800016dc`
- `0x180001a38`
- `0x180004180`
- `0x18000500c`
- `0x18000b740`
- `0x18000b910`
- `0x18000bfe4`
- `0x18000ccd8`
- `0x18000f0a4`
- `0x18000f174`
- `0x18001c74c`
- `0x18001ccbc`
- `0x18001cd54`
- `0x18001d454`
- `0x18001e50c`
- `0x180020dc4`
- `0x180032010`

## string_xrefs

- `0x18001cd99`: `CMidi2LoopbackMidiEndpointManager::CreateEndpointPair`
- `0x18001d045`: `Failed to create loopback endpoint B. Removing A now.`
- `0x18001d0a2`: `Failed to create loopback endpoint A`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::CreateEndpointPair(
        CMidi2LoopbackMidiEndpointManager *this,
        _QWORD *a2,
        _QWORD *a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rax
  struct TransportState *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  volatile signed __int32 *v14; // rdi
  void *v15; // rax
  volatile signed __int32 *v16; // rdi
  volatile signed __int32 *v17; // rdi
  _DWORD *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  volatile signed __int32 *v25; // rdi
  volatile signed __int32 *v26; // rdi
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  const char *v28; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[232]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v32[232]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v33; // [rsp+268h] [rbp+168h]
  __int64 v34; // [rsp+270h] [rbp+170h]
  _BYTE v35[40]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v36[232]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v37[232]; // [rsp+388h] [rbp+288h] BYREF
  __int128 v38; // [rsp+470h] [rbp+370h]

  v29[2] = a2;
  v29[3] = a3;
  v6 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v29[0] = this;
    v28 = "CMidi2LoopbackMidiEndpointManager::CreateEndpointPair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)byte_18005847D,
      v7,
      v8,
      (__int64)&v28,
      (__int64)v29);
  }
  v27 = 0;
  v9 = a2[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v27 = *(_OWORD *)a2;
  if ( (int)CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint((__int64)this, &v27) < 0 )
  {
    v22 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v22 > 2u )
    {
      *(_QWORD *)&v27 = L"Failed to create loopback endpoint A";
      v28 = (const char *)this;
      v29[0] = "CMidi2LoopbackMidiEndpointManager::CreateEndpointPair";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v22,
        (unsigned int)&byte_180058417,
        v23,
        v24,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  else
  {
    v27 = 0;
    v10 = a3[1];
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v27 = *(_OWORD *)a3;
    if ( (int)CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint((__int64)this, &v27) >= 0 )
    {
      std::wstring::wstring(v35, *a2);
      memset_0(v36, 0, 0x1E0u);
      MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition((MidiLoopbackDeviceDefinition *)v36);
      MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition((MidiLoopbackDeviceDefinition *)v37);
      v38 = 0;
      MidiLoopbackDeviceDefinition::operator=(v36, *a2);
      MidiLoopbackDeviceDefinition::operator=(v37, *a3);
      v11 = TransportState::Current();
      v12 = *((_QWORD *)v11 + 3);
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      v13 = *((_QWORD *)v11 + 2);
      v29[0] = v13;
      v14 = (volatile signed __int32 *)*((_QWORD *)v11 + 3);
      v29[1] = v14;
      *(_QWORD *)&v27 = v31;
      MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(
        (MidiLoopbackDeviceDefinition *)v31,
        (const struct MidiLoopbackDeviceDefinition *)v36);
      MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(
        (MidiLoopbackDeviceDefinition *)v32,
        (const struct MidiLoopbackDeviceDefinition *)v37);
      v33 = v38;
      if ( (_QWORD)v38 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 8LL))(v38);
      v34 = *((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v38 + 1) + 8LL))(*((_QWORD *)&v38 + 1));
      v15 = (void *)std::wstring::wstring(v30, v35);
      MidiLoopbackDeviceTable::SetDevice(v13, v15, (MidiLoopbackDevice *)v31);
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      MidiLoopbackDevice::~MidiLoopbackDevice((MidiLoopbackDevice *)v36);
      std::wstring::~wstring(v35);
      v16 = (volatile signed __int32 *)a2[1];
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      v17 = (volatile signed __int32 *)a3[1];
      if ( v17 && _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
      return 0;
    }
    v19 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v19 > 2u )
    {
      v28 = (const char *)L"Failed to create loopback endpoint B. Removing A now.";
      v29[0] = this;
      *(_QWORD *)&v27 = "CMidi2LoopbackMidiEndpointManager::CreateEndpointPair";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v19,
        (unsigned int)word_18005844A,
        v20,
        v21,
        (__int64)&v27,
        (__int64)v29,
        (__int64)&v28);
    }
    CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(this, (const struct MidiLoopbackDeviceDefinition *)*a2);
  }
  v25 = (volatile signed __int32 *)a2[1];
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = (volatile signed __int32 *)a3[1];
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001cd54  push    rbp
0x18001cd56  push    rbx
0x18001cd57  push    rsi
0x18001cd58  push    rdi
0x18001cd59  push    r14
0x18001cd5b  lea     rbp, [rsp-390h]
0x18001cd63  sub     rsp, 490h
0x18001cd6a  mov     rax, cs:__security_cookie
0x18001cd71  xor     rax, rsp
0x18001cd74  mov     [rbp+3B0h+var_30], rax
0x18001cd7b  mov     r14, r8
0x18001cd7e  mov     rsi, rdx
0x18001cd81  mov     rbx, rcx
0x18001cd84  mov     [rsp+4B0h+var_448], rdx
0x18001cd89  mov     [rsp+4B0h+var_440], r8
0x18001cd8e  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001cd93  mov     rcx, [rax+8]
0x18001cd97  mov     eax, [rcx]
0x18001cd99  lea     rdi, aCmidi2loopback_13; "CMidi2LoopbackMidiEndpointManager::Crea"...
0x18001cda0  cmp     eax, 4
0x18001cda3  jbe     short loc_18001CDCF
0x18001cda5  mov     [rsp+4B0h+var_458], rbx
0x18001cdaa  mov     [rsp+4B0h+var_460], rdi
0x18001cdaf  lea     rax, [rsp+4B0h+var_458]
0x18001cdb4  mov     [rsp+4B0h+var_488], rax
0x18001cdb9  lea     rax, [rsp+4B0h+var_460]
0x18001cdbe  mov     [rsp+4B0h+var_490], rax
0x18001cdc3  lea     rdx, byte_18005847D
0x18001cdca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001cdcf  xorps   xmm0, xmm0
0x18001cdd2  movdqu  [rsp+4B0h+var_470], xmm0
0x18001cdd8  mov     rax, [rsi+8]
0x18001cddc  test    rax, rax
0x18001cddf  jz      short loc_18001CDE5
0x18001cde1  lock inc dword ptr [rax+8]
0x18001cde5  mov     rax, [rsi]
0x18001cde8  mov     qword ptr [rsp+4B0h+var_470], rax
0x18001cded  mov     rax, [rsi+8]
0x18001cdf1  mov     qword ptr [rsp+4B0h+var_470+8], rax
0x18001cdf6  lea     rdx, [rsp+4B0h+var_470]
0x18001cdfb  mov     rcx, rbx
0x18001cdfe  call    ?CreateSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJV?$shared_ptr@UMidiLoopbackDeviceDefinition@@@std@@@Z; CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint(std::shared_ptr<MidiLoopbackDeviceDefinition>)
0x18001ce03  test    eax, eax
0x18001ce05  js      loc_18001D092
0x18001ce0b  xorps   xmm0, xmm0
0x18001ce0e  movdqu  [rsp+4B0h+var_470], xmm0
0x18001ce14  mov     rax, [r14+8]
0x18001ce18  test    rax, rax
0x18001ce1b  jz      short loc_18001CE21
0x18001ce1d  lock inc dword ptr [rax+8]
0x18001ce21  mov     rax, [r14]
0x18001ce24  mov     qword ptr [rsp+4B0h+var_470], rax
0x18001ce29  mov     rax, [r14+8]
0x18001ce2d  mov     qword ptr [rsp+4B0h+var_470+8], rax
0x18001ce32  lea     rdx, [rsp+4B0h+var_470]
0x18001ce37  mov     rcx, rbx
0x18001ce3a  call    ?CreateSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJV?$shared_ptr@UMidiLoopbackDeviceDefinition@@@std@@@Z; CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint(std::shared_ptr<MidiLoopbackDeviceDefinition>)
0x18001ce3f  test    eax, eax
0x18001ce41  js      loc_18001D035
0x18001ce47  mov     rdx, [rsi]
0x18001ce4a  lea     rcx, [rbp+3B0h+var_238]
0x18001ce51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ce56  nop
0x18001ce57  xor     edx, edx; Val
0x18001ce59  mov     r8d, 1E0h; Size
0x18001ce5f  lea     rcx, [rbp+3B0h+var_210]; void *
0x18001ce66  call    memset_0
0x18001ce6b  lea     rcx, [rbp+3B0h+var_210]; this
0x18001ce72  call    ??0MidiLoopbackDeviceDefinition@@QEAA@XZ; MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(void)
0x18001ce77  lea     rcx, [rbp+3B0h+var_128]; this
0x18001ce7e  call    ??0MidiLoopbackDeviceDefinition@@QEAA@XZ; MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(void)
0x18001ce83  xorps   xmm1, xmm1
0x18001ce86  movdqa  [rbp+3B0h+var_40], xmm1
0x18001ce8e  mov     rdx, [rsi]
0x18001ce91  lea     rcx, [rbp+3B0h+var_210]
0x18001ce98  call    ??4MidiLoopbackDeviceDefinition@@QEAAAEAU0@AEBU0@@Z; MidiLoopbackDeviceDefinition::operator=(MidiLoopbackDeviceDefinition const &)
0x18001ce9d  mov     rdx, [r14]
0x18001cea0  lea     rcx, [rbp+3B0h+var_128]
0x18001cea7  call    ??4MidiLoopbackDeviceDefinition@@QEAAAEAU0@AEBU0@@Z; MidiLoopbackDeviceDefinition::operator=(MidiLoopbackDeviceDefinition const &)
0x18001ceac  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001ceb1  mov     rcx, [rax+18h]
0x18001ceb5  test    rcx, rcx
0x18001ceb8  jz      short loc_18001CEBE
0x18001ceba  lock inc dword ptr [rcx+8]
0x18001cebe  mov     rbx, [rax+10h]
0x18001cec2  mov     [rsp+4B0h+var_458], rbx
0x18001cec7  mov     rdi, [rax+18h]
0x18001cecb  mov     [rsp+4B0h+var_450], rdi
0x18001ced0  lea     rax, [rbp+3B0h+var_418]
0x18001ced4  mov     qword ptr [rsp+4B0h+var_470], rax
0x18001ced9  lea     rdx, [rbp+3B0h+var_210]; struct MidiLoopbackDeviceDefinition *
0x18001cee0  lea     rcx, [rbp+3B0h+var_418]; this
0x18001cee4  call    ??0MidiLoopbackDeviceDefinition@@QEAA@AEBU0@@Z; MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(MidiLoopbackDeviceDefinition const &)
0x18001cee9  nop
0x18001ceea  lea     rdx, [rbp+3B0h+var_128]; struct MidiLoopbackDeviceDefinition *
0x18001cef1  lea     rcx, [rbp+3B0h+var_330]; this
0x18001cef8  call    ??0MidiLoopbackDeviceDefinition@@QEAA@AEBU0@@Z; MidiLoopbackDeviceDefinition::MidiLoopbackDeviceDefinition(MidiLoopbackDeviceDefinition const &)
0x18001cefd  mov     rcx, qword ptr [rbp+3B0h+var_40]
0x18001cf04  mov     [rbp+3B0h+var_248], rcx
0x18001cf0b  test    rcx, rcx
0x18001cf0e  jz      short loc_18001CF1D
0x18001cf10  mov     rax, [rcx]
0x18001cf13  mov     rax, [rax+8]
0x18001cf17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf1c  nop
0x18001cf1d  mov     rcx, qword ptr [rbp+3B0h+var_40+8]
0x18001cf24  mov     [rbp+3B0h+var_240], rcx
0x18001cf2b  test    rcx, rcx
0x18001cf2e  jz      short loc_18001CF3D
0x18001cf30  mov     rax, [rcx]
0x18001cf33  mov     rax, [rax+8]
0x18001cf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf3c  nop
0x18001cf3d  lea     rdx, [rbp+3B0h+var_238]
0x18001cf44  lea     rcx, [rsp+4B0h+var_438]
0x18001cf49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cf4e  nop
0x18001cf4f  lea     r8, [rbp+3B0h+var_418]
0x18001cf53  mov     rdx, rax
0x18001cf56  mov     rcx, rbx
0x18001cf59  call    ?SetDevice@MidiLoopbackDeviceTable@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VMidiLoopbackDevice@@@Z; MidiLoopbackDeviceTable::SetDevice(std::wstring,MidiLoopbackDevice)
0x18001cf5e  nop
0x18001cf5f  or      ebx, 0FFFFFFFFh
0x18001cf62  test    rdi, rdi
0x18001cf65  jz      short loc_18001CF9B
0x18001cf67  mov     eax, ebx
0x18001cf69  lock xadd [rdi+8], eax
0x18001cf6e  add     eax, ebx
0x18001cf70  jnz     short loc_18001CF9B
0x18001cf72  mov     rax, [rdi]
0x18001cf75  mov     rcx, rdi
0x18001cf78  mov     rax, [rax]
0x18001cf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf80  mov     eax, ebx
0x18001cf82  lock xadd [rdi+0Ch], eax
0x18001cf87  add     eax, ebx
0x18001cf89  jnz     short loc_18001CF9B
0x18001cf8b  mov     rax, [rdi]
0x18001cf8e  mov     rcx, rdi
0x18001cf91  mov     rax, [rax+8]
0x18001cf95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9a  nop
0x18001cf9b  lea     rcx, [rbp+3B0h+var_210]; this
0x18001cfa2  call    ??1MidiLoopbackDevice@@QEAA@XZ; MidiLoopbackDevice::~MidiLoopbackDevice(void)
0x18001cfa7  nop
0x18001cfa8  lea     rcx, [rbp+3B0h+var_238]; void *
0x18001cfaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cfb4  nop
0x18001cfb5  mov     rdi, [rsi+8]
0x18001cfb9  test    rdi, rdi
0x18001cfbc  jz      short loc_18001CFF2
0x18001cfbe  mov     eax, ebx
0x18001cfc0  lock xadd [rdi+8], eax
0x18001cfc5  add     eax, ebx
0x18001cfc7  jnz     short loc_18001CFF2
0x18001cfc9  mov     rax, [rdi]
0x18001cfcc  mov     rcx, rdi
0x18001cfcf  mov     rax, [rax]
0x18001cfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd7  mov     eax, ebx
0x18001cfd9  lock xadd [rdi+0Ch], eax
0x18001cfde  add     eax, ebx
0x18001cfe0  jnz     short loc_18001CFF2
0x18001cfe2  mov     rax, [rdi]
0x18001cfe5  mov     rcx, rdi
0x18001cfe8  mov     rax, [rax+8]
0x18001cfec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cff1  nop
0x18001cff2  mov     rdi, [r14+8]
0x18001cff6  test    rdi, rdi
0x18001cff9  jz      short loc_18001D02E
0x18001cffb  mov     eax, ebx
0x18001cffd  lock xadd [rdi+8], eax
0x18001d002  add     eax, ebx
0x18001d004  jnz     short loc_18001D02E
0x18001d006  mov     rax, [rdi]
0x18001d009  mov     rcx, rdi
0x18001d00c  mov     rax, [rax]
0x18001d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d014  mov     eax, ebx
0x18001d016  lock xadd [rdi+0Ch], eax
0x18001d01b  add     eax, ebx
0x18001d01d  jnz     short loc_18001D02E
0x18001d01f  mov     rax, [rdi]
0x18001d022  mov     rcx, rdi
0x18001d025  mov     rax, [rax+8]
0x18001d029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d02e  xor     eax, eax
0x18001d030  jmp     loc_18001D164
0x18001d035  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d03a  mov     rcx, [rax+8]
0x18001d03e  mov     eax, [rcx]
0x18001d040  cmp     eax, 2
0x18001d043  jbe     short loc_18001D085
0x18001d045  lea     rax, aFailedToCreate_0; "Failed to create loopback endpoint B. R"...
0x18001d04c  mov     [rsp+4B0h+var_460], rax
0x18001d051  mov     [rsp+4B0h+var_458], rbx
0x18001d056  mov     qword ptr [rsp+4B0h+var_470], rdi
0x18001d05b  lea     rax, [rsp+4B0h+var_460]
0x18001d060  mov     [rsp+4B0h+var_480], rax
0x18001d065  lea     rax, [rsp+4B0h+var_458]
0x18001d06a  mov     [rsp+4B0h+var_488], rax
0x18001d06f  lea     rax, [rsp+4B0h+var_470]
0x18001d074  mov     [rsp+4B0h+var_490], rax
0x18001d079  lea     rdx, word_18005844A
0x18001d080  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d085  mov     rdx, [rsi]; struct MidiLoopbackDeviceDefinition *
0x18001d088  mov     rcx, rbx; this
0x18001d08b  call    ?DeleteSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJAEBUMidiLoopbackDeviceDefinition@@@Z; CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(MidiLoopbackDeviceDefinition const &)
0x18001d090  jmp     short loc_18001D0E3
0x18001d092  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d097  mov     rcx, [rax+8]
0x18001d09b  mov     eax, [rcx]
0x18001d09d  cmp     eax, 2
0x18001d0a0  jbe     short loc_18001D0E3
0x18001d0a2  lea     rax, aFailedToCreate; "Failed to create loopback endpoint A"
0x18001d0a9  mov     qword ptr [rsp+4B0h+var_470], rax
0x18001d0ae  mov     [rsp+4B0h+var_460], rbx
0x18001d0b3  mov     [rsp+4B0h+var_458], rdi
0x18001d0b8  lea     rax, [rsp+4B0h+var_470]
0x18001d0bd  mov     [rsp+4B0h+var_480], rax
0x18001d0c2  lea     rax, [rsp+4B0h+var_460]
0x18001d0c7  mov     [rsp+4B0h+var_488], rax
0x18001d0cc  lea     rax, [rsp+4B0h+var_458]
0x18001d0d1  mov     [rsp+4B0h+var_490], rax
0x18001d0d6  lea     rdx, byte_180058417
0x18001d0dd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d0e2  nop
0x18001d0e3  or      ebx, 0FFFFFFFFh
0x18001d0e6  mov     rdi, [rsi+8]
0x18001d0ea  test    rdi, rdi
0x18001d0ed  jz      short loc_18001D123
0x18001d0ef  mov     eax, ebx
0x18001d0f1  lock xadd [rdi+8], eax
0x18001d0f6  add     eax, ebx
0x18001d0f8  jnz     short loc_18001D123
0x18001d0fa  mov     rax, [rdi]
0x18001d0fd  mov     rcx, rdi
0x18001d100  mov     rax, [rax]
0x18001d103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d108  mov     eax, ebx
0x18001d10a  lock xadd [rdi+0Ch], eax
0x18001d10f  add     eax, ebx
0x18001d111  jnz     short loc_18001D123
0x18001d113  mov     rax, [rdi]
0x18001d116  mov     rcx, rdi
0x18001d119  mov     rax, [rax+8]
0x18001d11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d122  nop
0x18001d123  mov     rdi, [r14+8]
0x18001d127  test    rdi, rdi
0x18001d12a  jz      short loc_18001D15F
0x18001d12c  mov     eax, ebx
0x18001d12e  lock xadd [rdi+8], eax
0x18001d133  add     eax, ebx
0x18001d135  jnz     short loc_18001D15F
0x18001d137  mov     rax, [rdi]
0x18001d13a  mov     rcx, rdi
0x18001d13d  mov     rax, [rax]
0x18001d140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d145  mov     eax, ebx
0x18001d147  lock xadd [rdi+0Ch], eax
0x18001d14c  add     eax, ebx
0x18001d14e  jnz     short loc_18001D15F
0x18001d150  mov     rax, [rdi]
0x18001d153  mov     rcx, rdi
0x18001d156  mov     rax, [rax+8]
0x18001d15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d15f  mov     eax, 80004005h
0x18001d164  mov     rcx, [rbp+3B0h+var_30]
0x18001d16b  xor     rcx, rsp; StackCookie
0x18001d16e  call    __security_check_cookie
0x18001d173  add     rsp, 490h
0x18001d17a  pop     r14
0x18001d17c  pop     rdi
0x18001d17d  pop     rsi
0x18001d17e  pop     rbx
0x18001d17f  pop     rbp
0x18001d180  retn
```
