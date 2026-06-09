# CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x14004225c`
- end: `0x140042496`
- name: `?ProcessEndpointInfoNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `570`
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
- `0x14004225c`
- `0x14004334c`
- `0x140044d70`

## string_xrefs

- `0x140042389`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x14004247e`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400423d9`: `Illegal attempt to change function block count after initial discovery`
- `0x140042414`: `Illegal attempt to change the static function block declaration after initial discovery`
- `0x140042274`: `CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  int v8; // eax
  char v9; // r9
  char v10; // cl
  int updated; // eax
  unsigned int v12; // edi
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  _QWORD *v17; // rax
  char *v18; // rdx
  const wchar_t *v19; // rax
  _QWORD *v20; // rax
  bool v21; // zf
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  _QWORD *v26; // [rsp+70h] [rbp+28h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp+30h] BYREF
  CMidiEndpointProtocolWorker *v28; // [rsp+80h] [rbp+38h] BYREF
  const char *v29; // [rsp+88h] [rbp+40h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v26 = v7;
    v28 = this;
    v27 = L"Received Endpoint Info Notification";
    v29 = "CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&byte_14008C0DF,
      v5,
      v6,
      &v29,
      (__int64)&v28,
      &v27,
      &v26);
  }
  v8 = *((_DWORD *)a2 + 1);
  v9 = v8 < 0;
  v10 = HIBYTE(v8) & 0x7F;
  if ( (v8 & 0x100) == 0 && *((_BYTE *)this + 314) == 1 )
    *((_BYTE *)this + 314) = 2;
  if ( (v8 & 0x200) == 0 && *((_BYTE *)this + 314) == 2 )
    *((_BYTE *)this + 314) = 1;
  if ( (v8 & 1) == 0 && *((_BYTE *)this + 313) )
    *((_BYTE *)this + 313) = 0;
  if ( (v8 & 2) == 0 && *((_BYTE *)this + 312) )
    *((_BYTE *)this + 312) = 0;
  if ( *((_BYTE *)this + 136) )
  {
    *((_BYTE *)this + 322) = v9;
    *((_BYTE *)this + 323) = v10;
    goto LABEL_19;
  }
  if ( *((_BYTE *)this + 323) != v10 )
  {
    v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v14 > 3u )
    {
      v17 = (_QWORD *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) > 7u )
        v17 = (_QWORD *)*v17;
      v26 = v17;
      v18 = byte_14008C135;
      v19 = L"Illegal attempt to change function block count after initial discovery";
LABEL_31:
      v27 = v19;
      v29 = "CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage";
      v28 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)v18,
        v15,
        v16,
        &v29,
        (__int64)&v28,
        &v27,
        &v26);
      return 0;
    }
    return 0;
  }
  if ( *((_BYTE *)this + 322) != v9 )
  {
    v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v14 > 3u )
    {
      v20 = (_QWORD *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) > 7u )
        v20 = (_QWORD *)*v20;
      v26 = v20;
      v18 = byte_14008BD21;
      v19 = L"Illegal attempt to change the static function block declaration after initial discovery";
      goto LABEL_31;
    }
    return 0;
  }
LABEL_19:
  updated = CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties(this, a2);
  v12 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)updated,
      v24);
    return v12;
  }
  v21 = *((_BYTE *)this + 136) == 0;
  *((_BYTE *)this + 317) = 1;
  if ( v21 )
    return 0;
  v22 = CMidiEndpointProtocolWorker::RequestAllFunctionBlocks(this);
  v23 = v22;
  if ( v22 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C0,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v22,
    v24);
  return v23;
}

```

## disassembly

```asm
0x14004225c  push    rbp
0x14004225e  push    rbx
0x14004225f  push    rdi
0x140042260  push    r14
0x140042262  mov     rbp, rsp
0x140042265  sub     rsp, 48h
0x140042269  mov     rdi, rdx
0x14004226c  mov     rbx, rcx
0x14004226f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140042274  lea     r14, aCmidiendpointp_17; "CMidiEndpointProtocolWorker::ProcessEnd"...
0x14004227b  mov     rcx, [rax+8]
0x14004227f  mov     eax, [rcx]
0x140042281  cmp     eax, 4
0x140042284  jbe     short loc_1400422DB
0x140042286  lea     rax, [rbx+38h]
0x14004228a  cmp     qword ptr [rax+18h], 7
0x14004228f  jbe     short loc_140042294
0x140042291  mov     rax, [rax]
0x140042294  mov     [rbp+arg_0], rax
0x140042298  lea     rdx, byte_14008C0DF
0x14004229f  lea     rax, aReceivedEndpoi; "Received Endpoint Info Notification"
0x1400422a6  mov     [rbp+arg_10], rbx
0x1400422aa  mov     [rbp+arg_8], rax
0x1400422ae  lea     rax, [rbp+arg_0]
0x1400422b2  mov     [rsp+48h+var_10], rax
0x1400422b7  lea     rax, [rbp+arg_8]
0x1400422bb  mov     [rsp+48h+var_18], rax
0x1400422c0  lea     rax, [rbp+arg_10]
0x1400422c4  mov     [rsp+48h+var_20], rax
0x1400422c9  lea     rax, [rbp+arg_18]
0x1400422cd  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400422d2  mov     [rbp+arg_18], r14
0x1400422d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400422db  mov     eax, [rdi+4]
0x1400422de  mov     edx, eax
0x1400422e0  and     edx, 200h
0x1400422e6  mov     r8d, eax
0x1400422e9  and     r8d, 1
0x1400422ed  mov     r10d, eax
0x1400422f0  and     r10d, 2
0x1400422f4  mov     ecx, eax
0x1400422f6  test    eax, 80000000h
0x1400422fb  setnbe  r9b
0x1400422ff  shr     ecx, 18h
0x140042302  and     cl, 7Fh
0x140042305  test    eax, 100h
0x14004230a  ja      short loc_14004231C
0x14004230c  cmp     byte ptr [rbx+13Ah], 1
0x140042313  jnz     short loc_14004231C
0x140042315  mov     byte ptr [rbx+13Ah], 2
0x14004231c  test    edx, edx
0x14004231e  jnz     short loc_140042330
0x140042320  cmp     byte ptr [rbx+13Ah], 2
0x140042327  jnz     short loc_140042330
0x140042329  mov     byte ptr [rbx+13Ah], 1
0x140042330  test    r8d, r8d
0x140042333  jnz     short loc_140042345
0x140042335  cmp     [rbx+139h], r8b
0x14004233c  jz      short loc_140042345
0x14004233e  mov     [rbx+139h], r8b
0x140042345  test    r10d, r10d
0x140042348  jnz     short loc_14004235A
0x14004234a  cmp     [rbx+138h], r10b
0x140042351  jz      short loc_14004235A
0x140042353  mov     [rbx+138h], r10b
0x14004235a  cmp     byte ptr [rbx+88h], 0
0x140042361  jz      short loc_1400423A4
0x140042363  mov     [rbx+142h], r9b
0x14004236a  mov     [rbx+143h], cl
0x140042370  mov     rdx, rdi; struct WindowsMidiServicesInternal::PackedUmp128 *
0x140042373  mov     rcx, rbx; this
0x140042376  call    ?UpdateEndpointInfoProperties@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::UpdateEndpointInfoProperties(WindowsMidiServicesInternal::PackedUmp128 &)
0x14004237b  mov     edi, eax
0x14004237d  test    eax, eax
0x14004237f  jns     loc_14004245C
0x140042385  mov     rcx, [rbp+20h]; this
0x140042389  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042390  mov     r9d, eax; char *
0x140042393  mov     edx, 2B9h; void *
0x140042398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004239d  mov     eax, edi
0x14004239f  jmp     loc_140042452
0x1400423a4  cmp     [rbx+143h], cl
0x1400423aa  jz      short loc_1400423E2
0x1400423ac  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400423b1  mov     rcx, [rax+8]
0x1400423b5  mov     eax, [rcx]
0x1400423b7  cmp     eax, 3
0x1400423ba  jbe     loc_140042450
0x1400423c0  lea     rax, [rbx+38h]
0x1400423c4  cmp     qword ptr [rax+18h], 7
0x1400423c9  jbe     short loc_1400423CE
0x1400423cb  mov     rax, [rax]
0x1400423ce  mov     [rbp+arg_0], rax
0x1400423d2  lea     rdx, byte_14008C135
0x1400423d9  lea     rax, aIllegalAttempt_0; "Illegal attempt to change function bloc"...
0x1400423e0  jmp     short loc_14004241B
0x1400423e2  cmp     [rbx+142h], r9b
0x1400423e9  jz      short loc_140042370
0x1400423eb  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400423f0  mov     rcx, [rax+8]
0x1400423f4  mov     eax, [rcx]
0x1400423f6  cmp     eax, 3
0x1400423f9  jbe     short loc_140042450
0x1400423fb  lea     rax, [rbx+38h]
0x1400423ff  cmp     qword ptr [rax+18h], 7
0x140042404  jbe     short loc_140042409
0x140042406  mov     rax, [rax]
0x140042409  mov     [rbp+arg_0], rax
0x14004240d  lea     rdx, byte_14008BD21
0x140042414  lea     rax, aIllegalAttempt; "Illegal attempt to change the static fu"...
0x14004241b  mov     [rbp+arg_8], rax
0x14004241f  lea     rax, [rbp+arg_0]
0x140042423  mov     [rsp+48h+var_10], rax
0x140042428  lea     rax, [rbp+arg_8]
0x14004242c  mov     [rsp+48h+var_18], rax
0x140042431  lea     rax, [rbp+arg_10]
0x140042435  mov     [rsp+48h+var_20], rax
0x14004243a  lea     rax, [rbp+arg_18]
0x14004243e  mov     qword ptr [rsp+48h+var_28], rax
0x140042443  mov     [rbp+arg_18], r14
0x140042447  mov     [rbp+arg_10], rbx
0x14004244b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042450  xor     eax, eax
0x140042452  add     rsp, 48h
0x140042456  pop     r14
0x140042458  pop     rdi
0x140042459  pop     rbx
0x14004245a  pop     rbp
0x14004245b  retn
0x14004245c  cmp     byte ptr [rbx+88h], 0
0x140042463  mov     byte ptr [rbx+13Dh], 1
0x14004246a  jz      short loc_140042450
0x14004246c  mov     rcx, rbx; this
0x14004246f  call    ?RequestAllFunctionBlocks@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::RequestAllFunctionBlocks(void)
0x140042474  mov     ebx, eax
0x140042476  test    eax, eax
0x140042478  jns     short loc_140042450
0x14004247a  mov     rcx, [rbp+20h]; this
0x14004247e  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042485  mov     r9d, eax; char *
0x140042488  mov     edx, 2C0h; void *
0x14004248d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042492  mov     eax, ebx
0x140042494  jmp     short loc_140042452
```
