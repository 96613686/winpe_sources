# CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140045b1c`
- end: `0x140045d3e`
- name: `?UpdateStreamConfigurationProperties@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140042f20`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x140045b1c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045bcb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045bcb`

## string_xrefs

- `0x140045d05`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140045b84`: `CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  char *v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rax
  int v9; // ecx
  int v10; // eax
  bool v11; // cc
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  int v16; // [rsp+20h] [rbp-E0h]
  char v17; // [rsp+40h] [rbp-C0h] BYREF
  char v18; // [rsp+41h] [rbp-BFh] BYREF
  char v19; // [rsp+42h] [rbp-BEh] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  char *v21; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v22; // [rsp+58h] [rbp-A8h] BYREF
  CMidiEndpointProtocolWorker *v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+84h] [rbp-7Ch]
  __int64 v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+94h] [rbp-6Ch]
  char *v31; // [rsp+98h] [rbp-68h]
  __int128 v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B4h] [rbp-4Ch]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C4h] [rbp-3Ch]
  char *v38; // [rsp+C8h] [rbp-38h]
  __int128 v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+E4h] [rbp-1Ch]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F4h] [rbp-Ch]
  char *v45; // [rsp+F8h] [rbp-8h]
  __int128 v46; // [rsp+100h] [rbp+0h]
  int v47; // [rsp+110h] [rbp+10h]
  int v48; // [rsp+114h] [rbp+14h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  int v50; // [rsp+120h] [rbp+20h]
  int v51; // [rsp+124h] [rbp+24h]
  __int64 *v52; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = (char *)this + 56;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v8 = (char *)this + 56;
    else
      v8 = *(char **)v4;
    v21 = v8;
    v23 = this;
    v22 = L"Enter";
    *(_QWORD *)v24 = "CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)qword_14008C290,
      v6,
      v7,
      v24,
      (__int64)&v23,
      &v22,
      &v21);
  }
  v20 = 0;
  GetSystemTimePreciseAsFileTime(&v20);
  v9 = *(_DWORD *)a2;
  v10 = *(_DWORD *)a2;
  v27 = 0;
  v19 = BYTE1(v10);
  v25 = PKEY_MIDI_EndpointConfiguredToSendJRTimestamps;
  v28 = 0;
  v30 = 1;
  v17 = ((v9 & 1) == 0) - 1;
  v32 = PKEY_MIDI_EndpointConfiguredToReceiveJRTimestamps;
  v34 = 0;
  v11 = *((_QWORD *)this + 10) <= 7u;
  v18 = -((v9 & 2) != 0);
  v26 = 405;
  v31 = &v17;
  v33 = 406;
  v38 = &v18;
  v40 = 400;
  v45 = &v19;
  v29 = 17;
  v36 = 17;
  v12 = *((_QWORD *)this + 22);
  v39 = PKEY_MIDI_EndpointConfiguredProtocol;
  v47 = 407;
  v52 = &v20;
  v35 = 0;
  v37 = 1;
  v41 = 0;
  v42 = 0;
  v43 = 3;
  v44 = 1;
  v46 = PKEY_MIDI_EndpointConfigurationLastUpdateTime;
  v48 = 0;
  v49 = 0;
  v50 = 16;
  v51 = 8;
  if ( !v11 )
    v4 = *(char **)v4;
  v13 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int128 *))(*(_QWORD *)v12 + 48LL))(v12, v4, 4, &v25);
  v14 = v13;
  if ( v13 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x589,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v13,
    v16);
  return v14;
}

```

## disassembly

```asm
0x140045b1c  mov     [rsp-8+arg_10], rbx
0x140045b21  push    rbp
0x140045b22  push    rsi
0x140045b23  push    rdi
0x140045b24  lea     rbp, [rsp-40h]
0x140045b29  sub     rsp, 140h
0x140045b30  mov     rax, cs:__security_cookie
0x140045b37  xor     rax, rsp
0x140045b3a  mov     [rbp+50h+var_20], rax
0x140045b3e  mov     rsi, rdx
0x140045b41  mov     rdi, rcx
0x140045b44  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140045b49  lea     rbx, [rdi+38h]
0x140045b4d  mov     rcx, [rax+8]
0x140045b51  mov     eax, [rcx]
0x140045b53  cmp     eax, 4
0x140045b56  jbe     short loc_140045BBD
0x140045b58  cmp     qword ptr [rbx+18h], 7
0x140045b5d  jbe     short loc_140045B64
0x140045b5f  mov     rax, [rbx]
0x140045b62  jmp     short loc_140045B67
0x140045b64  mov     rax, rbx
0x140045b67  mov     [rsp+150h+var_100], rax
0x140045b6c  lea     rdx, qword_14008C290
0x140045b73  lea     rax, aEnter; "Enter"
0x140045b7a  mov     [rsp+150h+var_F0], rdi
0x140045b7f  mov     [rsp+150h+var_F8], rax
0x140045b84  lea     rax, aCmidiendpointp_25; "CMidiEndpointProtocolWorker::UpdateStre"...
0x140045b8b  mov     qword ptr [rsp+150h+var_E8], rax
0x140045b90  lea     rax, [rsp+150h+var_100]
0x140045b95  mov     [rsp+150h+var_118], rax
0x140045b9a  lea     rax, [rsp+150h+var_F8]
0x140045b9f  mov     [rsp+150h+var_120], rax
0x140045ba4  lea     rax, [rsp+150h+var_F0]
0x140045ba9  mov     [rsp+150h+var_128], rax
0x140045bae  lea     rax, [rsp+150h+var_E8]
0x140045bb3  mov     qword ptr [rsp+150h+var_130], rax; int
0x140045bb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140045bbd  lea     rcx, [rsp+150h+var_108]
0x140045bc2  mov     [rsp+150h+var_108], 0
0x140045bcb  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140045bd1  mov     ecx, [rsi]
0x140045bd3  mov     edx, 1
0x140045bd8  movups  xmm0, cs:PKEY_MIDI_EndpointConfiguredToSendJRTimestamps
0x140045bdf  mov     eax, ecx
0x140045be1  mov     [rbp+50h+var_CC], 0
0x140045be8  shr     eax, 8
0x140045beb  mov     [rsp+150h+var_10E], al
0x140045bef  mov     al, cl
0x140045bf1  not     al
0x140045bf3  movaps  [rsp+150h+var_E0], xmm0
0x140045bf8  movups  xmm0, cs:PKEY_MIDI_EndpointConfiguredToReceiveJRTimestamps
0x140045bff  and     al, dl
0x140045c01  mov     [rbp+50h+var_C8], 0
0x140045c09  sub     al, dl
0x140045c0b  mov     [rbp+50h+var_BC], edx
0x140045c0e  mov     [rsp+150h+var_110], al
0x140045c12  and     cl, 2
0x140045c15  neg     cl
0x140045c17  movaps  [rbp+50h+var_B0], xmm0
0x140045c1b  movups  xmm0, cs:PKEY_MIDI_EndpointConfiguredProtocol
0x140045c22  sbb     al, al
0x140045c24  mov     [rbp+50h+var_9C], 0
0x140045c2b  cmp     qword ptr [rbx+18h], 7
0x140045c30  lea     ecx, [rdx+10h]
0x140045c33  mov     [rsp+150h+var_10F], al
0x140045c37  mov     eax, cs:dword_14007A4B0
0x140045c3d  mov     [rbp+50h+var_D0], eax
0x140045c40  lea     rax, [rsp+150h+var_110]
0x140045c45  mov     [rbp+50h+var_B8], rax
0x140045c49  mov     eax, cs:dword_14007A5E8
0x140045c4f  mov     [rbp+50h+var_A0], eax
0x140045c52  lea     rax, [rsp+150h+var_10F]
0x140045c57  mov     [rbp+50h+var_88], rax
0x140045c5b  mov     eax, cs:dword_14007A480
0x140045c61  mov     [rbp+50h+var_70], eax
0x140045c64  lea     rax, [rsp+150h+var_10E]
0x140045c69  mov     [rbp+50h+var_58], rax
0x140045c6d  mov     eax, cs:dword_14007A978
0x140045c73  mov     [rbp+50h+var_C0], ecx
0x140045c76  mov     [rbp+50h+var_90], ecx
0x140045c79  mov     rcx, [rdi+0B0h]
0x140045c80  movaps  [rbp+50h+var_80], xmm0
0x140045c84  movups  xmm0, cs:PKEY_MIDI_EndpointConfigurationLastUpdateTime
0x140045c8b  mov     [rbp+50h+var_40], eax
0x140045c8e  lea     rax, [rsp+150h+var_108]
0x140045c93  mov     [rbp+50h+var_28], rax
0x140045c97  mov     [rbp+50h+var_98], 0
0x140045c9f  mov     [rbp+50h+var_8C], edx
0x140045ca2  mov     [rbp+50h+var_6C], 0
0x140045ca9  mov     [rbp+50h+var_68], 0
0x140045cb1  mov     [rbp+50h+var_60], 3
0x140045cb8  mov     [rbp+50h+var_5C], edx
0x140045cbb  movaps  [rbp+50h+var_50], xmm0
0x140045cbf  mov     [rbp+50h+var_3C], 0
0x140045cc6  mov     [rbp+50h+var_38], 0
0x140045cce  mov     [rbp+50h+var_30], 10h
0x140045cd5  mov     [rbp+50h+var_2C], 8
0x140045cdc  mov     rax, [rcx]
0x140045cdf  jbe     short loc_140045CE4
0x140045ce1  mov     rbx, [rbx]
0x140045ce4  mov     rax, [rax+30h]
0x140045ce8  lea     r9, [rsp+150h+var_E0]
0x140045ced  mov     r8d, 4
0x140045cf3  mov     rdx, rbx
0x140045cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cfb  mov     ebx, eax
0x140045cfd  test    eax, eax
0x140045cff  jns     short loc_140045D1D
0x140045d01  mov     rcx, [rbp+58h]; this
0x140045d05  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140045d0c  mov     r9d, eax; char *
0x140045d0f  mov     edx, 589h; void *
0x140045d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045d19  mov     eax, ebx
0x140045d1b  jmp     short loc_140045D1F
0x140045d1d  xor     eax, eax
0x140045d1f  mov     rcx, [rbp+50h+var_20]
0x140045d23  xor     rcx, rsp; StackCookie
0x140045d26  call    __security_check_cookie
0x140045d2b  mov     rbx, [rsp+150h+arg_10]
0x140045d33  add     rsp, 140h
0x140045d3a  pop     rdi
0x140045d3b  pop     rsi
0x140045d3c  pop     rbp
0x140045d3d  retn
```
