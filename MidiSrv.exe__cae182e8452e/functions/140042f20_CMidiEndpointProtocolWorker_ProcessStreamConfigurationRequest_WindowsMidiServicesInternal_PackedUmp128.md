# CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140042f20`
- end: `0x1400431c3`
- name: `?ProcessStreamConfigurationRequest@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x140042f20`
- `0x140045b1c`
- `0x14005a010`

## string_xrefs

- `0x140042fbd`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x14004305b`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x14004316c`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140042f6d`: `CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  __int64 v8; // r10
  int v9; // ebx
  __int64 v10; // rdx
  int v12; // r8d
  char v13; // r9
  char v14; // al
  unsigned __int8 v15; // dl
  unsigned __int8 v16; // cl
  int updated; // eax
  char v18; // r9
  char v19; // r11
  unsigned __int8 v20; // cl
  unsigned __int8 v21; // cl
  int v22; // eax
  int v23; // [rsp+20h] [rbp-30h]
  _BYTE v24[12]; // [rsp+40h] [rbp-10h] BYREF
  int v25; // [rsp+4Ch] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  _QWORD *v27; // [rsp+70h] [rbp+20h] BYREF
  const wchar_t *v28; // [rsp+80h] [rbp+30h] BYREF
  CMidiEndpointProtocolWorker *v29; // [rsp+88h] [rbp+38h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v27 = v7;
    v29 = this;
    v28 = L"Enter";
    *(_QWORD *)v24 = "CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&word_14008C506,
      v5,
      v6,
      v24,
      (__int64)&v29,
      &v28,
      &v27);
  }
  v8 = *((_QWORD *)this + 26);
  if ( !v8 )
  {
    v9 = -2147467261;
    v10 = 1100;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)v9,
      v23);
    return (unsigned int)v9;
  }
  v12 = *((unsigned __int8 *)this + 314);
  if ( BYTE1(*(_DWORD *)a2) == (_BYTE)v12
    && (v13 = *((_BYTE *)this + 312), ((*(_DWORD *)a2 & 2) != 0) == v13)
    && (v14 = *((_BYTE *)this + 313), (*(_DWORD *)a2 & 1) == v14) )
  {
    *(_QWORD *)&v24[4] = 0;
    v25 = 0;
    v15 = v14 != 0 ? 2 : 0;
    v16 = v15 | 1;
    if ( !v13 )
      v16 = v15;
    *(_DWORD *)v24 = ((v12 | 0xFFF00600) << 8) | v16;
    updated = CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(
                this,
                (struct WindowsMidiServicesInternal::PackedUmp128 *)v24);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x492,
        (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
        (const char *)(unsigned int)updated);
    v23 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, __int64))(**((_QWORD **)this + 26) + 40LL))(
           *((_QWORD *)this + 26),
           0,
           v24,
           16);
    if ( v9 < 0 )
    {
      v10 = 1176;
      goto LABEL_7;
    }
  }
  else
  {
    v18 = *((_BYTE *)this + 313);
    v19 = *((_BYTE *)this + 312);
    *(_QWORD *)&v24[4] = 0;
    v25 = 0;
    if ( *((_BYTE *)this + 315) )
    {
      v21 = (v18 != 0 ? 2 : 0) | 1;
      if ( !v19 )
        v21 = v18 != 0 ? 2 : 0;
      *(_DWORD *)v24 = ((v12 | 0xFFF00600) << 8) | v21;
      v22 = CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(
              this,
              (struct WindowsMidiServicesInternal::PackedUmp128 *)v24);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x47D,
          (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
          (const char *)(unsigned int)v22);
      v23 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, __int64))(**((_QWORD **)this + 26) + 40LL))(
             *((_QWORD *)this + 26),
             0,
             v24,
             16);
      if ( v9 < 0 )
      {
        v10 = 1155;
        goto LABEL_7;
      }
    }
    else
    {
      *((_BYTE *)this + 315) = 1;
      v23 = 0;
      v20 = (v19 != 0 ? 2 : 0) | 1;
      if ( !v18 )
        v20 = v19 != 0 ? 2 : 0;
      *(_DWORD *)v24 = ((v12 | 0xFFF00500) << 8) | v20;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 0, v24, 16);
      if ( v9 < 0 )
      {
        v10 = 1132;
        goto LABEL_7;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140042f20  mov     [rsp-18h+arg_8], rbx
0x140042f25  push    rbp
0x140042f26  push    rsi
0x140042f27  push    rdi
0x140042f28  mov     rbp, rsp
0x140042f2b  sub     rsp, 50h
0x140042f2f  mov     rdi, rdx
0x140042f32  mov     rbx, rcx
0x140042f35  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140042f3a  mov     rcx, [rax+8]
0x140042f3e  mov     eax, [rcx]
0x140042f40  cmp     eax, 4
0x140042f43  jbe     short loc_140042FA1
0x140042f45  lea     rax, [rbx+38h]
0x140042f49  cmp     qword ptr [rax+18h], 7
0x140042f4e  jbe     short loc_140042F53
0x140042f50  mov     rax, [rax]
0x140042f53  mov     [rbp+arg_0], rax
0x140042f57  lea     rdx, word_14008C506
0x140042f5e  lea     rax, aEnter; "Enter"
0x140042f65  mov     [rbp+arg_18], rbx
0x140042f69  mov     [rbp+arg_10], rax
0x140042f6d  lea     rax, aCmidiendpointp_26; "CMidiEndpointProtocolWorker::ProcessStr"...
0x140042f74  mov     qword ptr [rbp+var_10], rax
0x140042f78  lea     rax, [rbp+arg_0]
0x140042f7c  mov     [rsp+50h+var_18], rax
0x140042f81  lea     rax, [rbp+arg_10]
0x140042f85  mov     [rsp+50h+var_20], rax
0x140042f8a  lea     rax, [rbp+arg_18]
0x140042f8e  mov     [rsp+50h+var_28], rax
0x140042f93  lea     rax, [rbp+var_10]
0x140042f97  mov     qword ptr [rsp+50h+var_30], rax; int
0x140042f9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042fa1  mov     r10, [rbx+0D0h]
0x140042fa8  xor     esi, esi
0x140042faa  test    r10, r10
0x140042fad  jnz     short loc_140042FD3
0x140042faf  mov     ebx, 80004003h
0x140042fb4  mov     edx, 44Ch; void *
0x140042fb9  mov     rcx, [rbp+18h]; this
0x140042fbd  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042fc4  mov     r9d, ebx; char *
0x140042fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042fcc  mov     eax, ebx
0x140042fce  jmp     loc_1400431B6
0x140042fd3  mov     ecx, [rdi]
0x140042fd5  mov     edx, ecx
0x140042fd7  movzx   r8d, byte ptr [rbx+13Ah]
0x140042fdf  mov     dil, 1
0x140042fe2  shr     edx, 1
0x140042fe4  mov     eax, ecx
0x140042fe6  and     dl, dil
0x140042fe9  shr     eax, 8
0x140042fec  cmp     al, r8b
0x140042fef  jnz     loc_1400430A7
0x140042ff5  mov     r9b, [rbx+138h]
0x140042ffc  cmp     dl, r9b
0x140042fff  jnz     loc_1400430A7
0x140043005  mov     al, [rbx+139h]
0x14004300b  and     cl, dil
0x14004300e  cmp     cl, al
0x140043010  jnz     loc_1400430A7
0x140043016  neg     al
0x140043018  mov     qword ptr [rbp+var_10+4], rsi
0x14004301c  mov     [rbp+var_4], esi
0x14004301f  sbb     al, al
0x140043021  and     al, 2
0x140043023  movzx   edx, al
0x140043026  mov     al, dl
0x140043028  or      al, dil
0x14004302b  movzx   ecx, al
0x14004302e  test    r9b, r9b
0x140043031  mov     eax, r8d
0x140043034  cmovz   ecx, edx
0x140043037  or      eax, 0FFF00600h
0x14004303c  movzx   edx, cl
0x14004303f  mov     rcx, rbx; this
0x140043042  shl     eax, 8
0x140043045  or      edx, eax
0x140043047  mov     dword ptr [rbp+var_10], edx
0x14004304a  lea     rdx, [rbp+var_10]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x14004304e  call    ?UpdateStreamConfigurationProperties@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(WindowsMidiServicesInternal::PackedUmp128 &)
0x140043053  test    eax, eax
0x140043055  jns     short loc_14004306F
0x140043057  mov     rcx, [rbp+18h]; this
0x14004305b  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140043062  mov     r9d, eax; char *
0x140043065  mov     edx, 492h; void *
0x14004306a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004306f  mov     rcx, [rbx+0D0h]
0x140043076  lea     r8, [rbp+var_10]
0x14004307a  mov     r9d, 10h
0x140043080  mov     qword ptr [rsp+50h+var_30], rsi
0x140043085  xor     edx, edx
0x140043087  mov     rax, [rcx]
0x14004308a  mov     rax, [rax+28h]
0x14004308e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043093  mov     ebx, eax
0x140043095  test    eax, eax
0x140043097  jns     loc_1400431B4
0x14004309d  mov     edx, 498h
0x1400430a2  jmp     loc_140042FB9
0x1400430a7  mov     r9b, [rbx+139h]
0x1400430ae  mov     r11b, [rbx+138h]
0x1400430b5  mov     qword ptr [rbp+var_10+4], rsi
0x1400430b9  mov     [rbp+var_4], esi
0x1400430bc  cmp     [rbx+13Bh], sil
0x1400430c3  jnz     short loc_14004312C
0x1400430c5  neg     r11b
0x1400430c8  mov     [rbx+13Bh], dil
0x1400430cf  mov     qword ptr [rsp+50h+var_30], rsi
0x1400430d4  sbb     al, al
0x1400430d6  and     al, 2
0x1400430d8  movzx   edx, al
0x1400430db  mov     al, dl
0x1400430dd  or      al, dil
0x1400430e0  movzx   ecx, al
0x1400430e3  test    r9b, r9b
0x1400430e6  mov     r9d, 10h
0x1400430ec  cmovz   ecx, edx
0x1400430ef  or      r8d, 0FFF00500h
0x1400430f6  movzx   eax, cl
0x1400430f9  xor     edx, edx
0x1400430fb  shl     r8d, 8
0x1400430ff  mov     rcx, r10
0x140043102  or      eax, r8d
0x140043105  lea     r8, [rbp+var_10]
0x140043109  mov     dword ptr [rbp+var_10], eax
0x14004310c  mov     rax, [r10]
0x14004310f  mov     rax, [rax+28h]
0x140043113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043118  mov     ebx, eax
0x14004311a  test    eax, eax
0x14004311c  jns     loc_1400431B4
0x140043122  mov     edx, 46Ch
0x140043127  jmp     loc_140042FB9
0x14004312c  neg     r9b
0x14004312f  sbb     al, al
0x140043131  and     al, 2
0x140043133  movzx   edx, al
0x140043136  mov     al, dl
0x140043138  or      al, dil
0x14004313b  movzx   ecx, al
0x14004313e  test    r11b, r11b
0x140043141  cmovz   ecx, edx
0x140043144  or      r8d, 0FFF00600h
0x14004314b  movzx   eax, cl
0x14004314e  lea     rdx, [rbp+var_10]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x140043152  shl     r8d, 8
0x140043156  mov     rcx, rbx; this
0x140043159  or      eax, r8d
0x14004315c  mov     dword ptr [rbp+var_10], eax
0x14004315f  call    ?UpdateStreamConfigurationProperties@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::UpdateStreamConfigurationProperties(WindowsMidiServicesInternal::PackedUmp128 &)
0x140043164  test    eax, eax
0x140043166  jns     short loc_140043180
0x140043168  mov     rcx, [rbp+18h]; this
0x14004316c  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140043173  mov     r9d, eax; char *
0x140043176  mov     edx, 47Dh; void *
0x14004317b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140043180  mov     rcx, [rbx+0D0h]
0x140043187  lea     r8, [rbp+var_10]
0x14004318b  mov     r9d, 10h
0x140043191  mov     qword ptr [rsp+50h+var_30], rsi
0x140043196  xor     edx, edx
0x140043198  mov     rax, [rcx]
0x14004319b  mov     rax, [rax+28h]
0x14004319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400431a4  mov     ebx, eax
0x1400431a6  test    eax, eax
0x1400431a8  jns     short loc_1400431B4
0x1400431aa  mov     edx, 483h
0x1400431af  jmp     loc_140042FB9
0x1400431b4  xor     eax, eax
0x1400431b6  mov     rbx, [rsp+50h+arg_8]
0x1400431bb  add     rsp, 50h
0x1400431bf  pop     rdi
0x1400431c0  pop     rsi
0x1400431c1  pop     rbp
0x1400431c2  retn
```
