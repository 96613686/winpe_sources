# CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140044d70`
- end: `0x1400450d4`
- name: `?UpdateEndpointInfoProperties@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14004225c`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x140044d70`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044e88`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044e88`

## string_xrefs

- `0x140045098`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140044dd9`: `CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  bool v11; // cc
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // [rsp+20h] [rbp-E0h]
  char v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17; // [rsp+41h] [rbp-BFh] BYREF
  char v18; // [rsp+42h] [rbp-BEh] BYREF
  char v19; // [rsp+43h] [rbp-BDh] BYREF
  char v20; // [rsp+44h] [rbp-BCh] BYREF
  char v21; // [rsp+45h] [rbp-BBh] BYREF
  char v22; // [rsp+46h] [rbp-BAh] BYREF
  __int64 v23; // [rsp+47h] [rbp-B9h] BYREF
  char v24; // [rsp+4Fh] [rbp-B1h]
  _QWORD *v25; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v26; // [rsp+58h] [rbp-A8h] BYREF
  CMidiEndpointProtocolWorker *v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  char *v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B4h] [rbp-4Ch]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C4h] [rbp-3Ch]
  char *v42; // [rsp+C8h] [rbp-38h]
  __int128 v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E4h] [rbp-1Ch]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+F0h] [rbp-10h]
  int v48; // [rsp+F4h] [rbp-Ch]
  char *v49; // [rsp+F8h] [rbp-8h]
  __int128 v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+110h] [rbp+10h]
  int v52; // [rsp+114h] [rbp+14h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  int v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+124h] [rbp+24h]
  char *v56; // [rsp+128h] [rbp+28h]
  __int128 v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+140h] [rbp+40h]
  int v59; // [rsp+144h] [rbp+44h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  int v61; // [rsp+150h] [rbp+50h]
  int v62; // [rsp+154h] [rbp+54h]
  char *v63; // [rsp+158h] [rbp+58h]
  __int128 v64; // [rsp+160h] [rbp+60h]
  int v65; // [rsp+170h] [rbp+70h]
  int v66; // [rsp+174h] [rbp+74h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  int v68; // [rsp+180h] [rbp+80h]
  int v69; // [rsp+184h] [rbp+84h]
  char *v70; // [rsp+188h] [rbp+88h]
  __int128 v71; // [rsp+190h] [rbp+90h]
  int v72; // [rsp+1A0h] [rbp+A0h]
  int v73; // [rsp+1A4h] [rbp+A4h]
  __int64 v74; // [rsp+1A8h] [rbp+A8h]
  int v75; // [rsp+1B0h] [rbp+B0h]
  int v76; // [rsp+1B4h] [rbp+B4h]
  char *v77; // [rsp+1B8h] [rbp+B8h]
  __int128 v78; // [rsp+1C0h] [rbp+C0h]
  int v79; // [rsp+1D0h] [rbp+D0h]
  int v80; // [rsp+1D4h] [rbp+D4h]
  __int64 v81; // [rsp+1D8h] [rbp+D8h]
  int v82; // [rsp+1E0h] [rbp+E0h]
  int v83; // [rsp+1E4h] [rbp+E4h]
  __int64 *v84; // [rsp+1E8h] [rbp+E8h]
  __int128 v85; // [rsp+1F0h] [rbp+F0h]
  int v86; // [rsp+200h] [rbp+100h]
  int v87; // [rsp+204h] [rbp+104h]
  __int64 v88; // [rsp+208h] [rbp+108h]
  int v89; // [rsp+210h] [rbp+110h]
  int v90; // [rsp+214h] [rbp+114h]
  char *v91; // [rsp+218h] [rbp+118h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v25 = v7;
    v27 = this;
    v26 = L"Enter";
    *(_QWORD *)v28 = "CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008BB73,
      v5,
      v6,
      v28,
      (__int64)&v27,
      &v26,
      &v25);
  }
  v8 = *((_DWORD *)a2 + 1);
  v20 = BYTE1(*(_DWORD *)a2);
  v21 = *(_BYTE *)a2;
  v24 = 0;
  v22 = HIBYTE(v8) & 0x7F;
  v23 = (unsigned __int8)-(v8 < 0);
  v17 = -((v8 & 0x100) != 0);
  v16 = -((v8 & 0x200) != 0);
  v19 = -((v8 & 1) == 1);
  v18 = -((v8 & 2) != 0);
  GetSystemTimePreciseAsFileTime((char *)&v23 + 1);
  v30 = 150;
  v35 = &v16;
  v37 = 151;
  v29 = PKEY_MIDI_EndpointSupportsMidi2Protocol;
  v42 = &v17;
  v36 = PKEY_MIDI_EndpointSupportsMidi1Protocol;
  v44 = 152;
  v49 = &v18;
  v43 = PKEY_MIDI_EndpointSupportsReceivingJRTimestamps;
  v51 = 153;
  v31 = 0;
  v50 = PKEY_MIDI_EndpointSupportsSendingJRTimestamps;
  v32 = 0;
  v33 = 17;
  v34 = 1;
  v38 = 0;
  v39 = 0;
  v40 = 17;
  v41 = 1;
  v45 = 0;
  v46 = 0;
  v47 = 17;
  v48 = 1;
  v52 = 0;
  v53 = 0;
  v54 = 17;
  v55 = 1;
  v56 = &v19;
  v58 = 154;
  v63 = &v20;
  v65 = 155;
  v70 = &v21;
  v72 = 180;
  v57 = PKEY_MIDI_EndpointUmpVersionMajor;
  v77 = &v22;
  v64 = PKEY_MIDI_EndpointUmpVersionMinor;
  v79 = 182;
  v84 = &v23;
  v71 = PKEY_MIDI_FunctionBlockDeclaredCount;
  v61 = 3;
  v68 = 3;
  v75 = 3;
  v9 = *((_QWORD *)this + 22);
  v78 = PKEY_MIDI_FunctionBlocksAreStatic;
  v86 = 156;
  v82 = 17;
  v10 = (_QWORD *)((char *)this + 56);
  v11 = *((_QWORD *)this + 10) <= 7u;
  v91 = (char *)&v23 + 1;
  v59 = 0;
  v60 = 0;
  v62 = 1;
  v66 = 0;
  v67 = 0;
  v69 = 1;
  v73 = 0;
  v74 = 0;
  v76 = 1;
  v80 = 0;
  v81 = 0;
  v83 = 1;
  v85 = PKEY_MIDI_EndpointInformationLastUpdateTime;
  v87 = 0;
  v88 = 0;
  v89 = 16;
  v90 = 8;
  if ( !v11 )
    v10 = (_QWORD *)*v10;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int128 *))(*(_QWORD *)v9 + 48LL))(v9, v10, 9, &v29);
  v13 = v12;
  if ( v12 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x603,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v12,
    v15);
  return v13;
}

```

## disassembly

```asm
0x140044d70  mov     [rsp-8+arg_10], rbx
0x140044d75  push    rbp
0x140044d76  push    rsi
0x140044d77  push    rdi
0x140044d78  lea     rbp, [rsp-130h]
0x140044d80  sub     rsp, 230h
0x140044d87  mov     rax, cs:__security_cookie
0x140044d8e  xor     rax, rsp
0x140044d91  mov     [rbp+140h+var_20], rax
0x140044d98  mov     rdi, rdx
0x140044d9b  mov     rbx, rcx
0x140044d9e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140044da3  mov     rcx, [rax+8]
0x140044da7  mov     eax, [rcx]
0x140044da9  cmp     eax, 4
0x140044dac  jbe     short loc_140044E12
0x140044dae  lea     rax, [rbx+38h]
0x140044db2  cmp     qword ptr [rax+18h], 7
0x140044db7  jbe     short loc_140044DBC
0x140044db9  mov     rax, [rax]
0x140044dbc  mov     [rsp+240h+var_1F0], rax
0x140044dc1  lea     rdx, byte_14008BB73
0x140044dc8  lea     rax, aEnter; "Enter"
0x140044dcf  mov     [rsp+240h+var_1E0], rbx
0x140044dd4  mov     [rsp+240h+var_1E8], rax
0x140044dd9  lea     rax, aCmidiendpointp_15; "CMidiEndpointProtocolWorker::UpdateEndp"...
0x140044de0  mov     qword ptr [rsp+240h+var_1D8], rax
0x140044de5  lea     rax, [rsp+240h+var_1F0]
0x140044dea  mov     [rsp+240h+var_208], rax
0x140044def  lea     rax, [rsp+240h+var_1E8]
0x140044df4  mov     [rsp+240h+var_210], rax
0x140044df9  lea     rax, [rsp+240h+var_1E0]
0x140044dfe  mov     [rsp+240h+var_218], rax
0x140044e03  lea     rax, [rsp+240h+var_1D8]
0x140044e08  mov     qword ptr [rsp+240h+var_220], rax; int
0x140044e0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140044e12  mov     edx, [rdi+4]
0x140044e15  xor     esi, esi
0x140044e17  mov     eax, [rdi]
0x140044e19  mov     ecx, edx
0x140044e1b  shr     eax, 8
0x140044e1e  and     ecx, 80000000h
0x140044e24  mov     [rsp+240h+var_1FC], al
0x140044e28  mov     al, [rdi]
0x140044e2a  lea     edi, [rsi+1]
0x140044e2d  mov     [rsp+240h+var_1FB], al
0x140044e31  mov     eax, edx
0x140044e33  shr     eax, 18h
0x140044e36  and     al, 7Fh
0x140044e38  mov     [rsp+240h+var_1F8], rsi
0x140044e3d  cmp     esi, ecx
0x140044e3f  mov     [rsp+240h+var_1FA], al
0x140044e43  mov     ecx, edx
0x140044e45  sbb     al, al
0x140044e47  and     ecx, 100h
0x140044e4d  cmp     esi, ecx
0x140044e4f  mov     [rsp+240h+var_1F9], al
0x140044e53  mov     ecx, edx
0x140044e55  sbb     al, al
0x140044e57  and     ecx, 200h
0x140044e5d  cmp     esi, ecx
0x140044e5f  mov     [rsp+240h+var_1FF], al
0x140044e63  mov     ecx, edx
0x140044e65  sbb     al, al
0x140044e67  and     cl, dil
0x140044e6a  cmp     sil, cl
0x140044e6d  mov     [rsp+240h+var_200], al
0x140044e71  lea     rcx, [rsp+240h+var_1F8]
0x140044e76  sbb     al, al
0x140044e78  and     dl, 2
0x140044e7b  cmp     sil, dl
0x140044e7e  mov     [rsp+240h+var_1FD], al
0x140044e82  sbb     al, al
0x140044e84  mov     [rsp+240h+var_1FE], al
0x140044e88  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140044e8e  movups  xmm0, cs:PKEY_MIDI_EndpointSupportsMidi2Protocol
0x140044e95  mov     eax, cs:dword_14007A378
0x140044e9b  lea     edx, [rsi+11h]
0x140044e9e  mov     [rbp+140h+var_1C0], eax
0x140044ea1  lea     rax, [rsp+240h+var_200]
0x140044ea6  mov     [rbp+140h+var_1A8], rax
0x140044eaa  mov     eax, cs:dword_14007A948
0x140044eb0  mov     [rbp+140h+var_190], eax
0x140044eb3  lea     rax, [rsp+240h+var_1FF]
0x140044eb8  movaps  [rsp+240h+var_1D0], xmm0
0x140044ebd  movups  xmm0, cs:PKEY_MIDI_EndpointSupportsMidi1Protocol
0x140044ec4  mov     [rbp+140h+var_178], rax
0x140044ec8  mov     eax, cs:dword_14007A570
0x140044ece  movaps  [rbp+140h+var_1A0], xmm0
0x140044ed2  movups  xmm0, cs:PKEY_MIDI_EndpointSupportsReceivingJRTimestamps
0x140044ed9  mov     [rbp+140h+var_160], eax
0x140044edc  lea     rax, [rsp+240h+var_1FE]
0x140044ee1  mov     [rbp+140h+var_148], rax
0x140044ee5  mov     eax, cs:dword_14007A4C8
0x140044eeb  movaps  [rbp+140h+var_170], xmm0
0x140044eef  movups  xmm0, cs:PKEY_MIDI_EndpointSupportsSendingJRTimestamps
0x140044ef6  mov     [rbp+140h+var_130], eax
0x140044ef9  lea     rax, [rsp+240h+var_1FD]
0x140044efe  mov     [rbp+140h+var_1BC], esi
0x140044f01  movaps  [rbp+140h+var_140], xmm0
0x140044f05  movups  xmm0, cs:PKEY_MIDI_EndpointUmpVersionMajor
0x140044f0c  mov     [rbp+140h+var_1B8], rsi
0x140044f10  mov     [rbp+140h+var_1B0], edx
0x140044f13  mov     [rbp+140h+var_1AC], edi
0x140044f16  mov     [rbp+140h+var_18C], esi
0x140044f19  mov     [rbp+140h+var_188], rsi
0x140044f1d  mov     [rbp+140h+var_180], edx
0x140044f20  mov     [rbp+140h+var_17C], edi
0x140044f23  mov     [rbp+140h+var_15C], esi
0x140044f26  mov     [rbp+140h+var_158], rsi
0x140044f2a  mov     [rbp+140h+var_150], edx
0x140044f2d  mov     [rbp+140h+var_14C], edi
0x140044f30  mov     [rbp+140h+var_12C], esi
0x140044f33  mov     [rbp+140h+var_128], rsi
0x140044f37  mov     [rbp+140h+var_120], edx
0x140044f3a  mov     [rbp+140h+var_11C], edi
0x140044f3d  mov     [rbp+140h+var_118], rax
0x140044f41  mov     eax, cs:dword_14007A930
0x140044f47  lea     ecx, [rsi+3]
0x140044f4a  mov     [rbp+140h+var_100], eax
0x140044f4d  lea     rax, [rsp+240h+var_1FC]
0x140044f52  mov     [rbp+140h+var_E8], rax
0x140044f56  mov     eax, cs:dword_14007A348
0x140044f5c  mov     [rbp+140h+var_D0], eax
0x140044f5f  lea     rax, [rsp+240h+var_1FB]
0x140044f64  mov     [rbp+140h+var_B8], rax
0x140044f6b  mov     eax, cs:dword_14007A468
0x140044f71  mov     [rbp+140h+var_A0], eax
0x140044f77  lea     rax, [rsp+240h+var_1FA]
0x140044f7c  movaps  [rbp+140h+var_110], xmm0
0x140044f80  movups  xmm0, cs:PKEY_MIDI_EndpointUmpVersionMinor
0x140044f87  mov     [rbp+140h+var_88], rax
0x140044f8e  mov     eax, cs:dword_14007A828
0x140044f94  movaps  [rbp+140h+var_E0], xmm0
0x140044f98  movups  xmm0, cs:PKEY_MIDI_FunctionBlockDeclaredCount
0x140044f9f  mov     [rbp+140h+var_70], eax
0x140044fa5  lea     rax, [rsp+240h+var_1F9]
0x140044faa  mov     [rbp+140h+var_58], rax
0x140044fb1  mov     eax, cs:dword_14007A4F8
0x140044fb7  movaps  [rbp+140h+var_B0], xmm0
0x140044fbe  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksAreStatic
0x140044fc5  mov     [rbp+140h+var_F0], ecx
0x140044fc8  mov     [rbp+140h+var_C0], ecx
0x140044fce  mov     [rbp+140h+var_90], ecx
0x140044fd4  mov     rcx, [rbx+0B0h]
0x140044fdb  movaps  [rbp+140h+var_80], xmm0
0x140044fe2  movups  xmm0, cs:PKEY_MIDI_EndpointInformationLastUpdateTime
0x140044fe9  mov     [rbp+140h+var_40], eax
0x140044fef  lea     rax, [rsp+240h+var_1F8]
0x140044ff4  mov     [rbp+140h+var_60], edx
0x140044ffa  lea     rdx, [rbx+38h]
0x140044ffe  cmp     qword ptr [rdx+18h], 7
0x140045003  mov     [rbp+140h+var_28], rax
0x14004500a  mov     [rbp+140h+var_FC], esi
0x14004500d  mov     [rbp+140h+var_F8], rsi
0x140045011  mov     [rbp+140h+var_EC], edi
0x140045014  mov     [rbp+140h+var_CC], esi
0x140045017  mov     [rbp+140h+var_C8], rsi
0x14004501b  mov     [rbp+140h+var_BC], edi
0x140045021  mov     [rbp+140h+var_9C], esi
0x140045027  mov     [rbp+140h+var_98], rsi
0x14004502e  mov     [rbp+140h+var_8C], edi
0x140045034  mov     [rbp+140h+var_6C], esi
0x14004503a  mov     [rbp+140h+var_68], rsi
0x140045041  mov     [rbp+140h+var_5C], edi
0x140045047  movaps  [rbp+140h+var_50], xmm0
0x14004504e  mov     [rbp+140h+var_3C], esi
0x140045054  mov     [rbp+140h+var_38], rsi
0x14004505b  mov     [rbp+140h+var_30], 10h
0x140045065  mov     [rbp+140h+var_2C], 8
0x14004506f  mov     rax, [rcx]
0x140045072  jbe     short loc_140045077
0x140045074  mov     rdx, [rdx]
0x140045077  mov     rax, [rax+30h]
0x14004507b  lea     r9, [rsp+240h+var_1D0]
0x140045080  mov     r8d, 9
0x140045086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004508b  mov     ebx, eax
0x14004508d  test    eax, eax
0x14004508f  jns     short loc_1400450B0
0x140045091  mov     rcx, [rbp+148h]; this
0x140045098  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x14004509f  mov     r9d, eax; char *
0x1400450a2  mov     edx, 603h; void *
0x1400450a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400450ac  mov     eax, ebx
0x1400450ae  jmp     short loc_1400450B2
0x1400450b0  xor     eax, eax
0x1400450b2  mov     rcx, [rbp+140h+var_20]
0x1400450b9  xor     rcx, rsp; StackCookie
0x1400450bc  call    __security_check_cookie
0x1400450c1  mov     rbx, [rsp+240h+arg_10]
0x1400450c9  add     rsp, 230h
0x1400450d0  pop     rdi
0x1400450d1  pop     rsi
0x1400450d2  pop     rbp
0x1400450d3  retn
```
