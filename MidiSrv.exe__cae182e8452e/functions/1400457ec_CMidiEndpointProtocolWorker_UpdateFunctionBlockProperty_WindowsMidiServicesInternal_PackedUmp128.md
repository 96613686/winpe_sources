# CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x1400457ec`
- end: `0x140045b14`
- name: `?UpdateFunctionBlockProperty@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400426b4`

## callees

- `0x14000179c`
- `0x140001f28`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x140041138`
- `0x1400418d4`
- `0x1400457ec`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045a10`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045a10`

## string_xrefs

- `0x140045abf`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140045824`: `CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  wchar_t *v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  bool v8; // cc
  const wchar_t *v9; // rax
  unsigned int v10; // ecx
  bool v11; // zf
  unsigned __int8 v12; // al
  int v13; // ecx
  _DWORD *v14; // r10
  const wchar_t *v15; // rax
  __int64 v16; // rcx
  int v17; // ecx
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  int v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v24; // [rsp+58h] [rbp-A8h] BYREF
  bool v25; // [rsp+5Ah] [rbp-A6h]
  unsigned __int8 v26[9]; // [rsp+5Bh] [rbp-A5h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch]
  int v28; // [rsp+68h] [rbp-98h]
  const wchar_t *v29; // [rsp+70h] [rbp-90h] BYREF
  struct _DEVPROPKEY v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v32; // [rsp+98h] [rbp-68h] BYREF
  CMidiEndpointProtocolWorker *v33; // [rsp+A0h] [rbp-60h] BYREF
  struct _DEVPROPKEY v34; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+C4h] [rbp-3Ch]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+D0h] [rbp-30h]
  int v38; // [rsp+D4h] [rbp-2Ch]
  __int16 *v39; // [rsp+D8h] [rbp-28h]
  __int128 v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+F0h] [rbp-10h]
  int v42; // [rsp+F4h] [rbp-Ch]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  int v44; // [rsp+100h] [rbp+0h]
  int v45; // [rsp+104h] [rbp+4h]
  __int64 *v46; // [rsp+108h] [rbp+8h]
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+110h] [rbp+10h] BYREF
  const char *v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  struct _DEVPROPKEY *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  const wchar_t *v52; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h]
  const wchar_t *v54; // [rsp+160h] [rbp+60h]
  int v55; // [rsp+168h] [rbp+68h]
  int v56; // [rsp+16Ch] [rbp+6Ch]
  int *v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]
  char **v59; // [rsp+180h] [rbp+80h]
  __int64 v60; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v4 = (wchar_t *)((char *)this + 56);
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v8 = *((_QWORD *)this + 10) <= 7u;
    v23 = *(_DWORD *)a2;
    if ( v8 )
      v9 = (const wchar_t *)((char *)this + 56);
    else
      v9 = *(const wchar_t **)v4;
    v29 = v9;
    v33 = this;
    v32 = L"Enter";
    *(_QWORD *)&v30.fmtid.Data1 = "CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v5,
      (__int64)&byte_14008BF7F,
      v6,
      v7,
      &v30,
      (__int64)&v33,
      &v32,
      &v29);
  }
  v10 = *(_DWORD *)a2;
  v11 = (*(_DWORD *)a2 & 0x8000) == 0;
  v24 = 0;
  v25 = !v11;
  v26[0] = BYTE1(v10) & 0x7F;
  v26[1] = (v10 >> 6) & 3;
  v26[4] = (v10 >> 4) & 3;
  v12 = *(_BYTE *)a2 & 3;
  v26[3] = (v10 >> 2) & 3;
  v13 = *((_DWORD *)a2 + 1);
  v26[2] = v12;
  v26[5] = HIBYTE(v13);
  v26[6] = BYTE2(v13);
  v26[8] = *((_BYTE *)a2 + 4);
  v27 = *((_DWORD *)a2 + 2);
  v28 = *((_DWORD *)a2 + 3);
  v26[7] = BYTE1(v13);
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    v8 = *((_QWORD *)this + 10) <= 7u;
    LODWORD(v29) = v25;
    LOWORD(v23) = v26[0];
    if ( v8 )
      v15 = (const wchar_t *)((char *)this + 56);
    else
      v15 = *(const wchar_t **)v4;
    *(_QWORD *)&v30.fmtid.Data1 = this;
    v59 = (char **)&v29;
    v57 = (int *)&v23;
    v60 = 4;
    v58 = 2;
    if ( v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v15 = &S2;
      v17 = 2;
    }
    v54 = v15;
    v55 = v17;
    v52 = L"Built function block property";
    v56 = 0;
    v50 = &v30;
    v53 = 60;
    v51 = 8;
    v48 = "CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty";
    v49 = 57;
    tlgWriteTransfer_EventWriteTransfer((__int64)v14, (unsigned __int8 *)byte_14008C441, 0, 0, 8u, &v47);
  }
  v31 = 0;
  GetSystemTimePreciseAsFileTime(&v31);
  CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(this, &v30, v26[0]);
  v8 = *((_QWORD *)this + 10) <= 7u;
  v18 = *((_QWORD *)this + 22);
  v34 = v30;
  v39 = &v24;
  v41 = 183;
  v46 = &v31;
  v40 = PKEY_MIDI_FunctionBlocksLastUpdateTime;
  v35 = 0;
  v36 = 0;
  v37 = 4099;
  v38 = 20;
  v42 = 0;
  v43 = 0;
  v44 = 16;
  v45 = 8;
  if ( !v8 )
    v4 = *(wchar_t **)v4;
  v19 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64, struct _DEVPROPKEY *))(*(_QWORD *)v18 + 48LL))(
          v18,
          v4,
          2,
          &v34);
  v20 = v19;
  if ( v19 >= 0 )
  {
    std::map<unsigned char,MidiFunctionBlockProperty>::insert_or_assign<MidiFunctionBlockProperty &>(
      (char *)this + 296,
      &v30,
      v26,
      &v24);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x698,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)v19,
      v22);
  }
  return v20;
}

```

## disassembly

```asm
0x1400457ec  push    rbp
0x1400457ee  push    rbx
0x1400457ef  push    rsi
0x1400457f0  push    rdi
0x1400457f1  push    r13
0x1400457f3  push    r14
0x1400457f5  lea     rbp, [rsp-0A8h]
0x1400457fd  sub     rsp, 1A8h
0x140045804  mov     rax, cs:__security_cookie
0x14004580b  xor     rax, rsp
0x14004580e  mov     [rbp+0D0h+var_40], rax
0x140045815  mov     rsi, rdx
0x140045818  mov     rdi, rcx
0x14004581b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140045820  lea     rbx, [rdi+38h]
0x140045824  lea     r13, aCmidiendpointp_23; "CMidiEndpointProtocolWorker::UpdateFunc"...
0x14004582b  mov     rcx, [rax+8]
0x14004582f  mov     eax, [rcx]
0x140045831  cmp     eax, 4
0x140045834  jbe     short loc_1400458A0
0x140045836  cmp     qword ptr [rbx+18h], 7
0x14004583b  mov     eax, [rsi]
0x14004583d  mov     [rsp+1D0h+var_180], eax
0x140045841  jbe     short loc_140045848
0x140045843  mov     rax, [rbx]
0x140045846  jmp     short loc_14004584B
0x140045848  mov     rax, rbx
0x14004584b  mov     [rsp+1D0h+var_160], rax
0x140045850  lea     rdx, byte_14008BF7F
0x140045857  lea     rax, aEnter; "Enter"
0x14004585e  mov     [rbp+0D0h+var_130], rdi
0x140045862  mov     [rbp+0D0h+var_138], rax
0x140045866  lea     rax, [rsp+1D0h+var_180]
0x14004586b  mov     [rsp+1D0h+var_190], rax
0x140045870  lea     rax, [rsp+1D0h+var_160]
0x140045875  mov     [rsp+1D0h+var_198], rax
0x14004587a  lea     rax, [rbp+0D0h+var_138]
0x14004587e  mov     [rsp+1D0h+var_1A0], rax
0x140045883  lea     rax, [rbp+0D0h+var_130]
0x140045887  mov     [rsp+1D0h+var_1A8], rax
0x14004588c  lea     rax, [rsp+1D0h+var_158]
0x140045891  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x140045896  mov     qword ptr [rsp+1D0h+var_158.fmtid.Data1], r13
0x14004589b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400458a0  mov     ecx, [rsi]
0x1400458a2  mov     dl, 3
0x1400458a4  mov     eax, ecx
0x1400458a6  xor     r14d, r14d
0x1400458a9  test    ecx, 8000h
0x1400458af  mov     [rsp+1D0h+var_178], r14w
0x1400458b5  setnbe  [rsp+1D0h+var_176]
0x1400458ba  shr     eax, 8
0x1400458bd  and     al, 7Fh
0x1400458bf  mov     [rsp+1D0h+var_175], al
0x1400458c3  mov     eax, ecx
0x1400458c5  shr     eax, 6
0x1400458c8  and     al, dl
0x1400458ca  mov     [rsp+1D0h+var_174], al
0x1400458ce  mov     eax, ecx
0x1400458d0  shr     eax, 4
0x1400458d3  and     al, dl
0x1400458d5  shr     ecx, 2
0x1400458d8  mov     [rsp+1D0h+var_171], al
0x1400458dc  and     cl, dl
0x1400458de  mov     al, [rsi]
0x1400458e0  and     al, dl
0x1400458e2  mov     [rsp+1D0h+var_172], cl
0x1400458e6  mov     ecx, [rsi+4]
0x1400458e9  mov     [rsp+1D0h+var_173], al
0x1400458ed  mov     eax, ecx
0x1400458ef  shr     eax, 18h
0x1400458f2  mov     [rsp+1D0h+var_170], al
0x1400458f6  mov     eax, ecx
0x1400458f8  shr     eax, 10h
0x1400458fb  mov     [rsp+1D0h+var_16F], al
0x1400458ff  mov     al, [rsi+4]
0x140045902  mov     [rsp+1D0h+var_16D], al
0x140045906  mov     eax, [rsi+8]
0x140045909  mov     [rsp+1D0h+var_16C], eax
0x14004590d  mov     eax, [rsi+0Ch]
0x140045910  shr     ecx, 8
0x140045913  mov     [rsp+1D0h+var_168], eax
0x140045917  mov     [rsp+1D0h+var_16E], cl
0x14004591b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140045920  mov     r10, [rax+8]
0x140045924  mov     eax, [r10]
0x140045927  cmp     eax, 4
0x14004592a  jbe     loc_140045A08
0x140045930  cmp     qword ptr [rbx+18h], 7
0x140045935  movzx   eax, [rsp+1D0h+var_176]
0x14004593a  mov     dword ptr [rsp+1D0h+var_160], eax
0x14004593e  movzx   eax, [rsp+1D0h+var_175]
0x140045943  mov     word ptr [rsp+1D0h+var_180], ax
0x140045948  jbe     short loc_14004594F
0x14004594a  mov     rax, [rbx]
0x14004594d  jmp     short loc_140045952
0x14004594f  mov     rax, rbx
0x140045952  mov     qword ptr [rsp+1D0h+var_158.fmtid.Data1], rdi
0x140045957  lea     rcx, [rsp+1D0h+var_160]
0x14004595c  mov     [rbp+0D0h+var_50], rcx
0x140045963  lea     rcx, [rsp+1D0h+var_180]
0x140045968  mov     [rbp+0D0h+var_60], rcx
0x14004596c  mov     [rbp+0D0h+var_48], 4
0x140045977  mov     [rbp+0D0h+var_58], 2
0x14004597f  test    rax, rax
0x140045982  jz      short loc_14004599B
0x140045984  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140045988  inc     rcx
0x14004598b  cmp     [rax+rcx*2], r14w
0x140045990  jnz     short loc_140045988
0x140045992  lea     ecx, ds:2[rcx*2]
0x140045999  jmp     short loc_1400459A7
0x14004599b  lea     rax, S2
0x1400459a2  mov     ecx, 2
0x1400459a7  mov     [rbp+0D0h+var_70], rax
0x1400459ab  lea     rdx, byte_14008C441
0x1400459b2  lea     rax, aBuiltFunctionB; "Built function block property"
0x1400459b9  mov     [rbp+0D0h+var_68], ecx
0x1400459bc  mov     [rbp+0D0h+var_80], rax
0x1400459c0  xor     r9d, r9d
0x1400459c3  lea     rax, [rsp+1D0h+var_158]
0x1400459c8  mov     [rbp+0D0h+var_64], r14d
0x1400459cc  mov     [rbp+0D0h+var_90], rax
0x1400459d0  xor     r8d, r8d
0x1400459d3  lea     rax, [rbp+0D0h+var_C0]
0x1400459d7  mov     [rbp+0D0h+var_78], 3Ch ; '<'
0x1400459df  mov     [rsp+1D0h+var_1A8], rax
0x1400459e4  mov     rcx, r10
0x1400459e7  mov     [rsp+1D0h+var_1B0], 8; int
0x1400459ef  mov     [rbp+0D0h+var_88], 8
0x1400459f7  mov     [rbp+0D0h+var_A0], r13
0x1400459fb  mov     [rbp+0D0h+var_98], 39h ; '9'
0x140045a03  call    _tlgWriteTransfer_EventWriteTransfer
0x140045a08  lea     rcx, [rbp+0D0h+var_140]
0x140045a0c  mov     [rbp+0D0h+var_140], r14
0x140045a10  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140045a16  mov     r8b, [rsp+1D0h+var_175]; unsigned __int8
0x140045a1b  lea     rdx, [rsp+1D0h+var_158]; retstr
0x140045a20  mov     rcx, rdi; this
0x140045a23  call    ?FunctionBlockPropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(uchar)
0x140045a28  cmp     qword ptr [rbx+18h], 7
0x140045a2d  movups  xmm0, xmmword ptr [rsp+1D0h+var_158.fmtid.Data1]
0x140045a32  mov     eax, [rbp+0D0h+var_158.pid]
0x140045a35  mov     rcx, [rdi+0B0h]
0x140045a3c  mov     [rbp+0D0h+var_110], eax
0x140045a3f  lea     rax, [rsp+1D0h+var_178]
0x140045a44  mov     [rbp+0D0h+var_F8], rax
0x140045a48  mov     eax, cs:dword_14007A8E8
0x140045a4e  movaps  [rbp+0D0h+var_120], xmm0
0x140045a52  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksLastUpdateTime
0x140045a59  mov     [rbp+0D0h+var_E0], eax
0x140045a5c  lea     rax, [rbp+0D0h+var_140]
0x140045a60  mov     [rbp+0D0h+var_C8], rax
0x140045a64  movaps  [rbp+0D0h+var_F0], xmm0
0x140045a68  mov     [rbp+0D0h+var_10C], r14d
0x140045a6c  mov     [rbp+0D0h+var_108], r14
0x140045a70  mov     [rbp+0D0h+var_100], 1003h
0x140045a77  mov     [rbp+0D0h+var_FC], 14h
0x140045a7e  mov     [rbp+0D0h+var_DC], r14d
0x140045a82  mov     [rbp+0D0h+var_D8], r14
0x140045a86  mov     [rbp+0D0h+var_D0], 10h
0x140045a8d  mov     [rbp+0D0h+var_CC], 8
0x140045a94  mov     rax, [rcx]
0x140045a97  jbe     short loc_140045A9C
0x140045a99  mov     rbx, [rbx]
0x140045a9c  mov     rax, [rax+30h]
0x140045aa0  lea     r9, [rbp+0D0h+var_120]
0x140045aa4  mov     r8d, 2
0x140045aaa  mov     rdx, rbx
0x140045aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ab2  mov     ebx, eax
0x140045ab4  test    eax, eax
0x140045ab6  jns     short loc_140045AD5
0x140045ab8  mov     rcx, [rbp+0D8h]; this
0x140045abf  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140045ac6  mov     r9d, eax; char *
0x140045ac9  mov     edx, 698h; void *
0x140045ace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045ad3  jmp     short loc_140045AF3
0x140045ad5  lea     rcx, [rdi+128h]
0x140045adc  lea     r9, [rsp+1D0h+var_178]
0x140045ae1  lea     r8, [rsp+1D0h+var_175]
0x140045ae6  lea     rdx, [rsp+1D0h+var_158]
0x140045aeb  call    ??$insert_or_assign@AEAUMidiFunctionBlockProperty@@@?$map@EUMidiFunctionBlockProperty@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@@std@@@std@@@std@@_N@1@AEBEAEAUMidiFunctionBlockProperty@@@Z; std::map<uchar,MidiFunctionBlockProperty>::insert_or_assign<MidiFunctionBlockProperty &>(uchar const &,MidiFunctionBlockProperty &)
0x140045af0  mov     ebx, r14d
0x140045af3  mov     eax, ebx
0x140045af5  mov     rcx, [rbp+0D0h+var_40]
0x140045afc  xor     rcx, rsp; StackCookie
0x140045aff  call    __security_check_cookie
0x140045b04  add     rsp, 1A8h
0x140045b0b  pop     r14
0x140045b0d  pop     r13
0x140045b0f  pop     rdi
0x140045b10  pop     rsi
0x140045b11  pop     rbx
0x140045b12  pop     rbp
0x140045b13  retn
```
