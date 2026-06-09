# CMidiEndpointProtocolWorker::RequestAllEndpointDiscoveryInformation(void)

- ea: `0x1400431cc`
- end: `0x140043345`
- name: `?RequestAllEndpointDiscoveryInformation@CMidiEndpointProtocolWorker@@AEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140043720`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400431cc`
- `0x14005a010`

## string_xrefs

- `0x14004325e`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400432bf`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400431e6`: `CMidiEndpointProtocolWorker::RequestAllEndpointDiscoveryInformation`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::RequestAllEndpointDiscoveryInformation(
        CMidiEndpointProtocolWorker *this)
{
  char *v2; // rbx
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  char *v6; // rax
  __int64 v7; // rcx
  int v9; // eax
  unsigned int v10; // esi
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+20h] [rbp-30h]
  _DWORD v15[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char *v18; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v19; // [rsp+88h] [rbp+38h] BYREF
  CMidiEndpointProtocolWorker *v20; // [rsp+90h] [rbp+40h] BYREF
  const char *v21; // [rsp+98h] [rbp+48h] BYREF

  v2 = (char *)this + 56;
  v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v3 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v6 = (char *)this + 56;
    else
      v6 = *(char **)v2;
    v18 = v6;
    v20 = this;
    v19 = L"Enter";
    v21 = "CMidiEndpointProtocolWorker::RequestAllEndpointDiscoveryInformation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)qword_14008B8C0,
      v4,
      v5,
      &v21,
      (__int64)&v20,
      &v19,
      &v18);
  }
  v7 = *((_QWORD *)this + 26);
  if ( v7 )
  {
    v16 = 0;
    v15[0] = -268435199;
    v15[1] = 31;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64))(*(_QWORD *)v7 + 40LL))(v7, 0, v15, 16);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v11 > 4u )
      {
        if ( *((_QWORD *)this + 10) > 7u )
          v2 = *(char **)v2;
        v18 = v2;
        v19 = L"Exit success";
        v20 = this;
        v21 = "CMidiEndpointProtocolWorker::RequestAllEndpointDiscoveryInformation";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v11,
          (__int64)&word_14008C2E6,
          v12,
          v13,
          &v21,
          (__int64)&v20,
          &v19,
          &v18);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
        (const char *)(unsigned int)v9,
        0);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x423,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)0x80004003LL,
      v14);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1400431cc  push    rbp
0x1400431ce  push    rbx
0x1400431cf  push    rsi
0x1400431d0  push    rdi
0x1400431d1  push    r15
0x1400431d3  mov     rbp, rsp
0x1400431d6  sub     rsp, 50h
0x1400431da  mov     rdi, rcx
0x1400431dd  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400431e2  lea     rbx, [rdi+38h]
0x1400431e6  lea     r15, aCmidiendpointp_7; "CMidiEndpointProtocolWorker::RequestAll"...
0x1400431ed  mov     rcx, [rax+8]
0x1400431f1  mov     eax, [rcx]
0x1400431f3  cmp     eax, 4
0x1400431f6  jbe     short loc_14004324E
0x1400431f8  cmp     qword ptr [rbx+18h], 7
0x1400431fd  jbe     short loc_140043204
0x1400431ff  mov     rax, [rbx]
0x140043202  jmp     short loc_140043207
0x140043204  mov     rax, rbx
0x140043207  mov     [rbp+arg_0], rax
0x14004320b  lea     rdx, qword_14008B8C0
0x140043212  lea     rax, aEnter; "Enter"
0x140043219  mov     [rbp+arg_10], rdi
0x14004321d  mov     [rbp+arg_8], rax
0x140043221  lea     rax, [rbp+arg_0]
0x140043225  mov     [rsp+50h+var_18], rax
0x14004322a  lea     rax, [rbp+arg_8]
0x14004322e  mov     [rsp+50h+var_20], rax
0x140043233  lea     rax, [rbp+arg_10]
0x140043237  mov     [rsp+50h+var_28], rax
0x14004323c  lea     rax, [rbp+arg_18]
0x140043240  mov     qword ptr [rsp+50h+var_30], rax; int
0x140043245  mov     [rbp+arg_18], r15
0x140043249  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14004324e  mov     rcx, [rdi+0D0h]
0x140043255  test    rcx, rcx
0x140043258  jnz     short loc_14004327E
0x14004325a  mov     rcx, [rbp+28h]; this
0x14004325e  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140043265  mov     ebx, 80004003h
0x14004326a  mov     edx, 423h; void *
0x14004326f  mov     r9d, ebx; char *
0x140043272  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140043277  mov     eax, ebx
0x140043279  jmp     loc_14004333A
0x14004327e  mov     [rbp+var_8], 0
0x140043286  lea     r8, [rbp+var_10]
0x14004328a  mov     [rbp+var_10], 0F0000101h
0x140043291  mov     r9d, 10h
0x140043297  mov     [rbp+var_C], 1Fh
0x14004329e  xor     edx, edx
0x1400432a0  mov     rax, [rcx]
0x1400432a3  mov     qword ptr [rsp+50h+var_30], 0; int
0x1400432ac  mov     rax, [rax+28h]
0x1400432b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400432b5  mov     esi, eax
0x1400432b7  test    eax, eax
0x1400432b9  jns     short loc_1400432D7
0x1400432bb  mov     rcx, [rbp+28h]; this
0x1400432bf  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x1400432c6  mov     r9d, eax; char *
0x1400432c9  mov     edx, 42Fh; void *
0x1400432ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400432d3  mov     eax, esi
0x1400432d5  jmp     short loc_14004333A
0x1400432d7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400432dc  mov     rcx, [rax+8]
0x1400432e0  mov     eax, [rcx]
0x1400432e2  cmp     eax, 4
0x1400432e5  jbe     short loc_140043338
0x1400432e7  cmp     qword ptr [rbx+18h], 7
0x1400432ec  jbe     short loc_1400432F1
0x1400432ee  mov     rbx, [rbx]
0x1400432f1  lea     rax, aExitSuccess_0; "Exit success"
0x1400432f8  mov     [rbp+arg_0], rbx
0x1400432fc  mov     [rbp+arg_8], rax
0x140043300  lea     rdx, word_14008C2E6
0x140043307  lea     rax, [rbp+arg_0]
0x14004330b  mov     [rbp+arg_10], rdi
0x14004330f  mov     [rsp+50h+var_18], rax
0x140043314  lea     rax, [rbp+arg_8]
0x140043318  mov     [rsp+50h+var_20], rax
0x14004331d  lea     rax, [rbp+arg_10]
0x140043321  mov     [rsp+50h+var_28], rax
0x140043326  lea     rax, [rbp+arg_18]
0x14004332a  mov     qword ptr [rsp+50h+var_30], rax
0x14004332f  mov     [rbp+arg_18], r15
0x140043333  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140043338  xor     eax, eax
0x14004333a  add     rsp, 50h
0x14004333e  pop     r15
0x140043340  pop     rdi
0x140043341  pop     rsi
0x140043342  pop     rbx
0x140043343  pop     rbp
0x140043344  retn
```
