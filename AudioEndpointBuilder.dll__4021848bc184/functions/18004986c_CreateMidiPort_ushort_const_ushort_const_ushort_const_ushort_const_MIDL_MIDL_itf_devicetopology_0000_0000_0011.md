# CreateMidiPort(ushort const *,ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_devicetopology_0000_0000_0011,uint,unsigned __int64)

- ea: `0x18004986c`
- end: `0x180049b27`
- name: `?CreateMidiPort@@YAJPEBG000W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@I_K@Z`
- size: `699`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011, unsigned int, unsigned __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003868c`
- `0x18003d314`
- `0x180056ad4`

## callees

- `0x180001734`
- `0x18000ceb0`
- `0x18001f2b0`
- `0x18001f374`
- `0x1800360d0`
- `0x180037558`
- `0x18003e920`
- `0x18003f7a4`
- `0x18004986c`
- `0x18004c598`
- `0x180052844`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049aa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049aa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004994c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004994c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a82`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180049a5e`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180049a5e`

## string_xrefs

- `0x180049acb`: `CreateMidiPort`

## pseudocode

```c
__int64 __fastcall CreateMidiPort(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 a5,
        unsigned int a6,
        unsigned __int64 a7)
{
  const unsigned __int16 *v8; // r13
  char v9; // r12
  void *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // edi
  struct _MIDIPORT *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  const char *v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  ATL::CAtlException *v26; // rbx
  char v27; // [rsp+41h] [rbp-107h] BYREF
  struct _MIDIPORT *pv; // [rsp+48h] [rbp-100h] BYREF
  const unsigned __int16 *v29; // [rsp+50h] [rbp-F8h] BYREF
  const char *v30; // [rsp+58h] [rbp-F0h] BYREF
  const WCHAR *v31; // [rsp+60h] [rbp-E8h]
  const unsigned __int16 *v32; // [rsp+68h] [rbp-E0h]
  const unsigned __int16 *v33; // [rsp+70h] [rbp-D8h]
  ATL::CAtlException *v34; // [rsp+78h] [rbp-D0h] BYREF
  int v35; // [rsp+80h] [rbp-C8h] BYREF
  const unsigned __int16 *v36; // [rsp+88h] [rbp-C0h]
  int v37; // [rsp+A8h] [rbp-A0h]
  __int64 v38; // [rsp+B0h] [rbp-98h]
  DEVPROPKEY v39; // [rsp+D0h] [rbp-78h]
  int v40; // [rsp+E4h] [rbp-64h]
  __int64 v41; // [rsp+E8h] [rbp-60h]
  int v42; // [rsp+F0h] [rbp-58h]
  int v43; // [rsp+F4h] [rbp-54h]
  char *v44; // [rsp+F8h] [rbp-50h]

  v31 = a4;
  v29 = a3;
  v8 = a1;
  v32 = a1;
  v33 = a3;
  memset_0(&v35, 0, 0x48u);
  pv = 0;
  v9 = 0;
  v13 = CTCoAllocPolicy::Alloc(v10, 1, 0x40u, (void **)&pv);
  v14 = pv;
  if ( v13 >= 0 )
  {
    v13 = _AllocString<CTCoAllocPolicy>(v12, v11, a2, pv);
    if ( v13 >= 0 )
    {
      v17 = (char *)v14 + 32;
      v30 = (char *)v14 + 32;
      v13 = _AllocString<CTCoAllocPolicy>(v16, v15, v31, (_QWORD *)v14 + 4);
      if ( v13 >= 0 )
      {
        *((_DWORD *)v14 + 2) = 1;
        *((_DWORD *)v14 + 3) = a5;
        *((_DWORD *)v14 + 14) = a6;
        *((_QWORD *)v14 + 6) = a7;
        EnterCriticalSection(&MidiPortsLock);
        *((_DWORD *)v14 + 4) = 1;
        v13 = 0;
        try
        {
          ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(v18, &pv);
        }
        catch ( ATL::CAtlException *v34 )
        {
          v26 = v34;
          if ( *(_DWORD *)v34 == -1073741571 )
            _o__resetstkoflw();
          v13 = *(_DWORD *)v26;
          v14 = pv;
          v9 = 0;
          v8 = v32;
          v29 = v33;
          v17 = v30;
        }
        LeaveCriticalSection(&MidiPortsLock);
        if ( v13 >= 0 )
        {
          v9 = 1;
          v35 = 72;
          v36 = v29;
          v37 = 0;
          v38 = *(_QWORD *)v17;
          v27 = -1;
          v39 = DEVPKEY_Device_PresenceNotForDevice;
          v40 = 0;
          v41 = 0;
          v42 = 17;
          v43 = 1;
          v44 = &v27;
          v13 = SwDeviceCreate(L"MMDEVAPI", v8, &v35, 1);
          if ( v13 >= 0 )
            v14 = 0;
          pv = v14;
        }
      }
    }
  }
  if ( v14 && v9 )
  {
    EnterCriticalSection(&MidiPortsLock);
    v20 = ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(v19, &pv);
    ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(v21, v20);
    LeaveCriticalSection(&MidiPortsLock);
  }
  MidiPortDeepFree((LPVOID *)v14);
  if ( v13 < 0 )
  {
    v22 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v22 > 2u )
    {
      LODWORD(v29) = v13;
      LODWORD(pv) = 1122;
      v30 = "CreateMidiPort";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)v22,
        (int)byte_180076EC9,
        v23,
        v24,
        (const unsigned __int16 **)&v30,
        (__int64)&pv,
        (__int64)&v29);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004986c  push    rbx
0x18004986e  push    rsi
0x18004986f  push    rdi
0x180049870  push    r12
0x180049872  push    r13
0x180049874  push    r15
0x180049876  sub     rsp, 118h
0x18004987d  mov     rax, cs:__security_cookie
0x180049884  xor     rax, rsp
0x180049887  mov     [rsp+148h+var_48], rax
0x18004988f  mov     [rsp+148h+var_E8], r9
0x180049894  mov     rax, r8
0x180049897  mov     [rsp+148h+var_F8], rax
0x18004989c  mov     r15, rdx
0x18004989f  mov     r13, rcx
0x1800498a2  mov     [rsp+148h+var_E0], rcx
0x1800498a7  mov     [rsp+148h+var_D8], rax
0x1800498ac  xor     edx, edx; Val
0x1800498ae  lea     r8d, [rdx+48h]; Size
0x1800498b2  lea     rcx, [rsp+148h+var_C8]; void *
0x1800498ba  call    memset_0
0x1800498bf  xor     esi, esi
0x1800498c1  mov     [rsp+148h+pv], rsi
0x1800498c6  mov     r12b, sil
0x1800498c9  lea     r9, [rsp+148h+pv]; void **
0x1800498ce  lea     edx, [rsi+1]; unsigned int
0x1800498d1  lea     r8d, [rsi+40h]; unsigned __int64
0x1800498d5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800498da  mov     edi, eax
0x1800498dc  mov     rbx, [rsp+148h+pv]
0x1800498e1  test    eax, eax
0x1800498e3  js      loc_180049A71
0x1800498e9  mov     r9, rbx
0x1800498ec  mov     r8, r15
0x1800498ef  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800498f4  mov     edi, eax
0x1800498f6  test    eax, eax
0x1800498f8  js      loc_180049A71
0x1800498fe  lea     r15, [rbx+20h]
0x180049902  mov     [rsp+148h+var_F0], r15
0x180049907  mov     r9, r15
0x18004990a  mov     r8, [rsp+148h+var_E8]
0x18004990f  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180049914  mov     edi, eax
0x180049916  test    eax, eax
0x180049918  js      loc_180049A71
0x18004991e  mov     dword ptr [rbx+8], 1
0x180049925  mov     eax, [rsp+148h+arg_20]
0x18004992c  mov     [rbx+0Ch], eax
0x18004992f  mov     eax, [rsp+148h+arg_28]
0x180049936  mov     [rbx+38h], eax
0x180049939  mov     rax, [rsp+148h+arg_30]
0x180049941  mov     [rbx+30h], rax
0x180049945  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x18004994c  call    cs:__imp_EnterCriticalSection
0x180049952  mov     dword ptr [rbx+10h], 1
0x180049959  mov     edi, esi
0x18004995b  lea     rdx, [rsp+148h+pv]
0x180049960  call    ?AddTail@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBQEAU_MIDIPORT@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::AddTail(_MIDIPORT * const &)
0x180049965  nop
0x180049966  jmp     short loc_18004998A
0x180049968  xor     esi, esi
0x18004996a  mov     edi, dword ptr [rsp+148h+var_F8]
0x18004996e  mov     rbx, [rsp+148h+pv]
0x180049973  mov     r12b, sil
0x180049976  mov     r13, [rsp+148h+var_E0]
0x18004997b  mov     rax, [rsp+148h+var_D8]
0x180049980  mov     [rsp+148h+var_F8], rax
0x180049985  mov     r15, [rsp+148h+var_F0]
0x18004998a  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x180049991  call    cs:__imp_LeaveCriticalSection
0x180049997  test    edi, edi
0x180049999  js      loc_180049A71
0x18004999f  mov     r12b, 1
0x1800499a2  mov     [rsp+148h+var_C8], 48h ; 'H'
0x1800499ad  mov     rax, [rsp+148h+var_F8]
0x1800499b2  mov     [rsp+148h+var_C0], rax
0x1800499ba  mov     [rsp+148h+var_A0], esi
0x1800499c1  mov     rax, [r15]
0x1800499c4  mov     [rsp+148h+var_98], rax
0x1800499cc  mov     [rsp+148h+var_107], 0FFh
0x1800499d1  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_PresenceNotForDevice.fmtid.Data1
0x1800499d8  movups  [rsp+148h+var_78], xmm0
0x1800499e0  mov     eax, cs:DEVPKEY_Device_PresenceNotForDevice.pid
0x1800499e6  mov     [rsp+148h+var_68], eax
0x1800499ed  mov     [rsp+148h+var_64], esi
0x1800499f4  mov     [rsp+148h+var_60], rsi
0x1800499fc  mov     [rsp+148h+var_58], 11h
0x180049a07  mov     [rsp+148h+var_54], 1
0x180049a12  lea     rax, [rsp+148h+var_107]
0x180049a17  mov     [rsp+148h+var_50], rax
0x180049a1f  lea     rax, [rbx+18h]
0x180049a23  mov     [rsp+148h+var_110], rax
0x180049a28  mov     [rsp+148h+var_118], rbx
0x180049a2d  lea     rax, ?SwMidiPortCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SwMidiPortCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180049a34  mov     [rsp+148h+var_120], rax
0x180049a39  lea     rax, [rsp+148h+var_78]
0x180049a41  mov     [rsp+148h+var_128], rax
0x180049a46  mov     r9d, 1
0x180049a4c  lea     r8, [rsp+148h+var_C8]
0x180049a54  mov     rdx, r13
0x180049a57  lea     rcx, aMmdevapi; "MMDEVAPI"
0x180049a5e  call    cs:__imp_SwDeviceCreate
0x180049a64  mov     edi, eax
0x180049a66  test    eax, eax
0x180049a68  cmovns  rbx, rsi
0x180049a6c  mov     [rsp+148h+pv], rbx
0x180049a71  test    rbx, rbx
0x180049a74  jz      short loc_180049AA7
0x180049a76  test    r12b, r12b
0x180049a79  jz      short loc_180049AA7
0x180049a7b  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x180049a82  call    cs:__imp_EnterCriticalSection
0x180049a88  lea     rdx, [rsp+148h+pv]
0x180049a8d  call    ?Find@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEBAPEAU__POSITION@@AEBQEAU_MIDIPORT@@PEAU3@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::Find(_MIDIPORT * const &,__POSITION *)
0x180049a92  mov     rdx, rax
0x180049a95  call    ?RemoveAt@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(__POSITION *)
0x180049a9a  lea     rcx, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; lpCriticalSection
0x180049aa1  call    cs:__imp_LeaveCriticalSection
0x180049aa7  mov     rcx, rbx; pv
0x180049aaa  call    ?MidiPortDeepFree@@YAXPEAU_MIDIPORT@@@Z; MidiPortDeepFree(_MIDIPORT *)
0x180049aaf  test    edi, edi
0x180049ab1  jns     short loc_180049B04
0x180049ab3  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180049ab8  mov     ecx, [rax]
0x180049aba  cmp     ecx, 2
0x180049abd  jbe     short loc_180049B04
0x180049abf  mov     dword ptr [rsp+148h+var_F8], edi
0x180049ac3  mov     dword ptr [rsp+148h+pv], 462h
0x180049acb  lea     rcx, aCreatemidiport_0; "CreateMidiPort"
0x180049ad2  mov     [rsp+148h+var_F0], rcx
0x180049ad7  lea     rcx, [rsp+148h+var_F8]
0x180049adc  mov     [rsp+148h+var_118], rcx
0x180049ae1  lea     rcx, [rsp+148h+pv]
0x180049ae6  mov     [rsp+148h+var_120], rcx
0x180049aeb  lea     rcx, [rsp+148h+var_F0]
0x180049af0  mov     [rsp+148h+var_128], rcx
0x180049af5  lea     rdx, byte_180076EC9
0x180049afc  mov     rcx, rax
0x180049aff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180049b04  mov     eax, edi
0x180049b06  mov     rcx, [rsp+148h+var_48]
0x180049b0e  xor     rcx, rsp; StackCookie
0x180049b11  call    __security_check_cookie
0x180049b16  add     rsp, 118h
0x180049b1d  pop     r15
0x180049b1f  pop     r13
0x180049b21  pop     r12
0x180049b23  pop     rdi
0x180049b24  pop     rsi
0x180049b25  pop     rbx
0x180049b26  retn
```
