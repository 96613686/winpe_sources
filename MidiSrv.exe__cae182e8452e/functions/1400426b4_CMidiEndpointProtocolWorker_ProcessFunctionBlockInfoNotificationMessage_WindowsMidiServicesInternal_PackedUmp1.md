# CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x1400426b4`
- end: `0x1400428be`
- name: `?ProcessFunctionBlockInfoNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14000a6b4`
- `0x140041138`
- `0x1400426b4`
- `0x1400457ec`

## string_xrefs

- `0x140042838`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400426d1`: `CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  char *v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rax
  unsigned int v9; // ecx
  char v10; // r8
  unsigned __int8 v11; // dl
  _DWORD *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  const wchar_t *v15; // rax
  int *v16; // rdx
  unsigned __int8 v17; // al
  char v18; // al
  int v19; // ecx
  int v20; // eax
  int updated; // eax
  unsigned int v22; // ebx
  int v24; // [rsp+20h] [rbp-50h]
  _BYTE v25[16]; // [rsp+40h] [rbp-30h] BYREF
  __int16 v26; // [rsp+50h] [rbp-20h] BYREF
  bool v27; // [rsp+52h] [rbp-1Eh]
  _BYTE v28[9]; // [rsp+53h] [rbp-1Dh] BYREF
  int v29; // [rsp+5Ch] [rbp-14h]
  int v30; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char *v32; // [rsp+A0h] [rbp+30h] BYREF
  const wchar_t *v33; // [rsp+A8h] [rbp+38h] BYREF
  CMidiEndpointProtocolWorker *v34; // [rsp+B0h] [rbp+40h] BYREF
  const char *v35; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (char *)this + 56;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v8 = (char *)this + 56;
    else
      v8 = *(char **)v4;
    v32 = v8;
    v34 = this;
    v33 = L"Received Function Block Info Notification";
    v35 = "CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_14008BBC9,
      v6,
      v7,
      &v35,
      (__int64)&v34,
      &v33,
      &v32);
  }
  v9 = *(_DWORD *)a2;
  v10 = *((_BYTE *)this + 136);
  v11 = BYTE1(*(_DWORD *)a2) & 0x7F;
  if ( v10 || !*((_BYTE *)this + 322) )
  {
    v17 = *((_BYTE *)this + 323);
    if ( v10 )
    {
      if ( v11 < v17 )
      {
        v28[0] = BYTE1(*(_DWORD *)a2) & 0x7F;
        v26 = 0;
        v27 = (v9 & 0x8000) != 0;
        v28[1] = (v9 >> 6) & 3;
        v28[4] = (v9 >> 4) & 3;
        v18 = *(_BYTE *)a2 & 3;
        v28[3] = (v9 >> 2) & 3;
        v19 = *((_DWORD *)a2 + 1);
        v28[2] = v18;
        v28[5] = HIBYTE(v19);
        v28[6] = BYTE2(v19);
        v28[8] = *((_BYTE *)a2 + 4);
        v29 = *((_DWORD *)a2 + 2);
        v20 = *((_DWORD *)a2 + 3);
        v28[7] = BYTE1(v19);
        v30 = v20;
        std::map<unsigned char,MidiFunctionBlockProperty>::insert_or_assign<MidiFunctionBlockProperty &>(
          (char *)this + 296,
          v25,
          v28,
          &v26);
      }
      return 0;
    }
    if ( v11 >= v17 )
    {
      v12 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v12 > 3u )
      {
        if ( *((_QWORD *)this + 10) > 7u )
          v4 = *(char **)v4;
        v15 = L"Endpoint illegally tried to add more function blocks after initial discovery";
        v16 = &dword_14008C33C;
        goto LABEL_22;
      }
    }
    else
    {
      updated = CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty(this, a2);
      v22 = updated;
      if ( updated < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x306,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
          (const char *)(unsigned int)updated,
          v24);
        return v22;
      }
    }
  }
  else
  {
    v12 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v12 > 3u )
    {
      if ( *((_QWORD *)this + 10) > 7u )
        v4 = *(char **)v4;
      v15 = L"Endpoint illegally tried change static function blocks";
      v16 = &dword_14008B96C;
LABEL_22:
      v33 = v15;
      v32 = v4;
      v34 = this;
      v35 = "CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v12,
        (__int64)v16,
        v13,
        v14,
        &v35,
        (__int64)&v34,
        &v33,
        &v32);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400426b4  push    rbp
0x1400426b6  push    rbx
0x1400426b7  push    rsi
0x1400426b8  push    rdi
0x1400426b9  push    r14
0x1400426bb  mov     rbp, rsp
0x1400426be  sub     rsp, 70h
0x1400426c2  mov     rsi, rdx
0x1400426c5  mov     rdi, rcx
0x1400426c8  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400426cd  lea     rbx, [rdi+38h]
0x1400426d1  lea     r14, aCmidiendpointp_5; "CMidiEndpointProtocolWorker::ProcessFun"...
0x1400426d8  mov     rcx, [rax+8]
0x1400426dc  mov     eax, [rcx]
0x1400426de  cmp     eax, 4
0x1400426e1  jbe     short loc_140042739
0x1400426e3  cmp     qword ptr [rbx+18h], 7
0x1400426e8  jbe     short loc_1400426EF
0x1400426ea  mov     rax, [rbx]
0x1400426ed  jmp     short loc_1400426F2
0x1400426ef  mov     rax, rbx
0x1400426f2  mov     [rbp+arg_0], rax
0x1400426f6  lea     rdx, byte_14008BBC9
0x1400426fd  lea     rax, aReceivedFuncti_0; "Received Function Block Info Notificati"...
0x140042704  mov     [rbp+arg_10], rdi
0x140042708  mov     [rbp+arg_8], rax
0x14004270c  lea     rax, [rbp+arg_0]
0x140042710  mov     [rsp+70h+var_38], rax
0x140042715  lea     rax, [rbp+arg_8]
0x140042719  mov     [rsp+70h+var_40], rax
0x14004271e  lea     rax, [rbp+arg_10]
0x140042722  mov     [rsp+70h+var_48], rax
0x140042727  lea     rax, [rbp+arg_18]
0x14004272b  mov     qword ptr [rsp+70h+var_50], rax; int
0x140042730  mov     [rbp+arg_18], r14
0x140042734  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042739  mov     ecx, [rsi]
0x14004273b  mov     edx, ecx
0x14004273d  mov     r8b, [rdi+88h]
0x140042744  shr     edx, 8
0x140042747  and     dl, 7Fh
0x14004274a  test    r8b, r8b
0x14004274d  jnz     short loc_140042789
0x14004274f  cmp     [rdi+142h], r8b
0x140042756  jz      short loc_140042789
0x140042758  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14004275d  mov     rcx, [rax+8]
0x140042761  mov     eax, [rcx]
0x140042763  cmp     eax, 3
0x140042766  jbe     loc_1400428B1
0x14004276c  cmp     qword ptr [rbx+18h], 7
0x140042771  jbe     short loc_140042776
0x140042773  mov     rbx, [rbx]
0x140042776  lea     rax, aEndpointIllega; "Endpoint illegally tried change static "...
0x14004277d  lea     rdx, dword_14008B96C
0x140042784  jmp     loc_140042878
0x140042789  mov     al, [rdi+143h]
0x14004278f  test    r8b, r8b
0x140042792  jz      loc_14004281F
0x140042798  cmp     dl, al
0x14004279a  jnb     loc_1400428B1
0x1400427a0  xor     eax, eax
0x1400427a2  mov     [rbp+var_1D], dl
0x1400427a5  mov     [rbp+var_20], ax
0x1400427a9  lea     r9, [rbp+var_20]
0x1400427ad  test    ecx, 8000h
0x1400427b3  lea     r8, [rbp+var_1D]
0x1400427b7  mov     eax, ecx
0x1400427b9  lea     rdx, [rbp+var_30]
0x1400427bd  setnbe  [rbp+var_1E]
0x1400427c1  shr     eax, 6
0x1400427c4  and     al, 3
0x1400427c6  mov     [rbp+var_1C], al
0x1400427c9  mov     eax, ecx
0x1400427cb  shr     eax, 4
0x1400427ce  and     al, 3
0x1400427d0  shr     ecx, 2
0x1400427d3  mov     [rbp+var_19], al
0x1400427d6  and     cl, 3
0x1400427d9  mov     al, [rsi]
0x1400427db  and     al, 3
0x1400427dd  mov     [rbp+var_1A], cl
0x1400427e0  mov     ecx, [rsi+4]
0x1400427e3  mov     [rbp+var_1B], al
0x1400427e6  mov     eax, ecx
0x1400427e8  shr     eax, 18h
0x1400427eb  mov     [rbp+var_18], al
0x1400427ee  mov     eax, ecx
0x1400427f0  shr     eax, 10h
0x1400427f3  mov     [rbp+var_17], al
0x1400427f6  mov     al, [rsi+4]
0x1400427f9  mov     [rbp+var_15], al
0x1400427fc  mov     eax, [rsi+8]
0x1400427ff  shr     ecx, 8
0x140042802  mov     [rbp+var_14], eax
0x140042805  mov     eax, [rsi+0Ch]
0x140042808  mov     [rbp+var_16], cl
0x14004280b  lea     rcx, [rdi+128h]
0x140042812  mov     [rbp+var_10], eax
0x140042815  call    ??$insert_or_assign@AEAUMidiFunctionBlockProperty@@@?$map@EUMidiFunctionBlockProperty@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@@std@@@std@@@std@@_N@1@AEBEAEAUMidiFunctionBlockProperty@@@Z; std::map<uchar,MidiFunctionBlockProperty>::insert_or_assign<MidiFunctionBlockProperty &>(uchar const &,MidiFunctionBlockProperty &)
0x14004281a  jmp     loc_1400428B1
0x14004281f  cmp     dl, al
0x140042821  jnb     short loc_140042850
0x140042823  mov     rdx, rsi; struct WindowsMidiServicesInternal::PackedUmp128 *
0x140042826  mov     rcx, rdi; this
0x140042829  call    ?UpdateFunctionBlockProperty@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::UpdateFunctionBlockProperty(WindowsMidiServicesInternal::PackedUmp128 &)
0x14004282e  mov     ebx, eax
0x140042830  test    eax, eax
0x140042832  jns     short loc_1400428B1
0x140042834  mov     rcx, [rbp+28h]; this
0x140042838  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x14004283f  mov     r9d, eax; char *
0x140042842  mov     edx, 306h; void *
0x140042847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004284c  mov     eax, ebx
0x14004284e  jmp     short loc_1400428B3
0x140042850  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140042855  mov     rcx, [rax+8]
0x140042859  mov     eax, [rcx]
0x14004285b  cmp     eax, 3
0x14004285e  jbe     short loc_1400428B1
0x140042860  cmp     qword ptr [rbx+18h], 7
0x140042865  jbe     short loc_14004286A
0x140042867  mov     rbx, [rbx]
0x14004286a  lea     rax, aEndpointIllega_0; "Endpoint illegally tried to add more fu"...
0x140042871  lea     rdx, dword_14008C33C
0x140042878  mov     [rbp+arg_8], rax
0x14004287c  lea     rax, [rbp+arg_0]
0x140042880  mov     [rsp+70h+var_38], rax
0x140042885  lea     rax, [rbp+arg_8]
0x140042889  mov     [rsp+70h+var_40], rax
0x14004288e  lea     rax, [rbp+arg_10]
0x140042892  mov     [rsp+70h+var_48], rax
0x140042897  lea     rax, [rbp+arg_18]
0x14004289b  mov     qword ptr [rsp+70h+var_50], rax
0x1400428a0  mov     [rbp+arg_0], rbx
0x1400428a4  mov     [rbp+arg_10], rdi
0x1400428a8  mov     [rbp+arg_18], r14
0x1400428ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400428b1  xor     eax, eax
0x1400428b3  add     rsp, 70h
0x1400428b7  pop     r14
0x1400428b9  pop     rdi
0x1400428ba  pop     rsi
0x1400428bb  pop     rbx
0x1400428bc  pop     rbp
0x1400428bd  retn
```
