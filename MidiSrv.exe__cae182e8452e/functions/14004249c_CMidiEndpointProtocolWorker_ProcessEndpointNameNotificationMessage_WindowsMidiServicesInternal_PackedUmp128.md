# CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x14004249c`
- end: `0x1400426ae`
- name: `?ProcessEndpointNameNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001440c`
- `0x14001ddc4`
- `0x14002698c`
- `0x140029568`
- `0x140041c98`
- `0x14004249c`
- `0x1400450dc`

## string_xrefs

- `0x14004266f`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400424f5`: `CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  __int64 v8; // rax
  void *v9; // rax
  __int64 v10; // rax
  int updated; // edi
  __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rax
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-69h]
  int v18[2]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v19; // [rsp+48h] [rbp-41h] BYREF
  const wchar_t *v20; // [rsp+50h] [rbp-39h] BYREF
  CMidiEndpointProtocolWorker *v21; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-29h] BYREF
  char *v23[4]; // [rsp+80h] [rbp-9h] BYREF
  char *Src[4]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v19 = v7;
    v20 = L"Received Endpoint Name Notification";
    v21 = this;
    *(_QWORD *)v18 = "CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008C033,
      v5,
      v6,
      v18,
      (__int64)&v21,
      &v20,
      &v19);
  }
  if ( ((*(_DWORD *)a2 >> 26) & 3) == 0 )
  {
    v14 = (void *)CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    v15 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v14);
    std::wstring::operator=((char **)this + 27, v15);
    std::wstring::~wstring(Src);
    updated = CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(this);
    if ( updated < 0 )
    {
      v12 = 962;
      goto LABEL_18;
    }
LABEL_19:
    *((_BYTE *)this + 319) = 1;
    return 0;
  }
  if ( ((*(_DWORD *)a2 >> 26) & 3) == 1 )
  {
    v13 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    std::wstring::operator=((char **)this + 27, v13);
    goto LABEL_15;
  }
  if ( ((*(_DWORD *)a2 >> 26) & 3) != 2 )
  {
    if ( ((*(_DWORD *)a2 >> 26) & 3) != 3 || !*((_QWORD *)this + 29) )
      return 0;
    v8 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    v9 = (void *)std::operator+<unsigned short>(v22, (char *)this + 216, v8);
    v10 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v9);
    std::wstring::operator=((char **)this + 27, v10);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v23);
    updated = CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(this);
    if ( updated < 0 )
    {
      v12 = 988;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
        (const char *)(unsigned int)updated,
        v17);
      return (unsigned int)updated;
    }
    goto LABEL_19;
  }
  if ( *((_QWORD *)this + 29) )
  {
    CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    std::wstring::operator+=((char *)this + 216);
LABEL_15:
    std::wstring::~wstring(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x14004249c  mov     [rsp-8+arg_10], rbx
0x1400424a1  push    rbp
0x1400424a2  push    rsi
0x1400424a3  push    rdi
0x1400424a4  lea     rbp, [rsp-47h]
0x1400424a9  sub     rsp, 0D0h
0x1400424b0  mov     rax, cs:__security_cookie
0x1400424b7  xor     rax, rsp
0x1400424ba  mov     [rbp+57h+var_20], rax
0x1400424be  mov     rdi, rdx
0x1400424c1  mov     rbx, rcx
0x1400424c4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400424c9  mov     rcx, [rax+8]
0x1400424cd  mov     eax, [rcx]
0x1400424cf  cmp     eax, 4
0x1400424d2  jbe     short loc_140042530
0x1400424d4  lea     rax, [rbx+38h]
0x1400424d8  cmp     qword ptr [rax+18h], 7
0x1400424dd  jbe     short loc_1400424E2
0x1400424df  mov     rax, [rax]
0x1400424e2  mov     [rbp+57h+var_98], rax
0x1400424e6  lea     rax, aReceivedEndpoi_0; "Received Endpoint Name Notification"
0x1400424ed  mov     [rbp+57h+var_90], rax
0x1400424f1  mov     [rbp+57h+var_88], rbx
0x1400424f5  lea     rax, aCmidiendpointp; "CMidiEndpointProtocolWorker::ProcessEnd"...
0x1400424fc  mov     qword ptr [rbp+57h+var_A0], rax
0x140042500  lea     rax, [rbp+57h+var_98]
0x140042504  mov     [rsp+0E0h+var_A8], rax
0x140042509  lea     rax, [rbp+57h+var_90]
0x14004250d  mov     [rsp+0E0h+var_B0], rax
0x140042512  lea     rax, [rbp+57h+var_88]
0x140042516  mov     [rsp+0E0h+var_B8], rax
0x14004251b  lea     rax, [rbp+57h+var_A0]
0x14004251f  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140042524  lea     rdx, byte_14008C033
0x14004252b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042530  mov     ecx, [rdi]
0x140042532  shr     ecx, 1Ah
0x140042535  and     ecx, 3
0x140042538  jz      loc_140042629
0x14004253e  sub     ecx, 1
0x140042541  jz      loc_140042600
0x140042547  sub     ecx, 1
0x14004254a  jz      loc_1400425D0
0x140042550  cmp     ecx, 1
0x140042553  jnz     loc_14004268D
0x140042559  lea     rsi, [rbx+0D8h]
0x140042560  cmp     qword ptr [rsi+10h], 0
0x140042565  jz      loc_14004268D
0x14004256b  mov     r8, rdi
0x14004256e  lea     rdx, [rbp+57h+var_60]
0x140042572  mov     rcx, rbx
0x140042575  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x14004257a  nop
0x14004257b  mov     r8, rax
0x14004257e  mov     rdx, rsi
0x140042581  lea     rcx, [rbp+57h+var_80]
0x140042585  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x14004258a  mov     rdx, rax; void *
0x14004258d  lea     rcx, [rbp+57h+Src]; Src
0x140042591  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042596  mov     rdx, rax
0x140042599  mov     rcx, rsi
0x14004259c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400425a1  lea     rcx, [rbp+57h+Src]; void *
0x1400425a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400425aa  nop
0x1400425ab  lea     rcx, [rbp+57h+var_60]; void *
0x1400425af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400425b4  mov     rcx, rbx; this
0x1400425b7  call    ?UpdateEndpointNameProperty@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(void)
0x1400425bc  mov     edi, eax
0x1400425be  test    eax, eax
0x1400425c0  jns     loc_140042686
0x1400425c6  mov     edx, 3DCh
0x1400425cb  jmp     loc_14004266F
0x1400425d0  lea     rsi, [rbx+0D8h]
0x1400425d7  cmp     qword ptr [rsi+10h], 0
0x1400425dc  jz      loc_14004268D
0x1400425e2  mov     r8, rdi
0x1400425e5  lea     rdx, [rbp+57h+var_60]
0x1400425e9  mov     rcx, rbx
0x1400425ec  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x1400425f1  nop
0x1400425f2  mov     rdx, rax
0x1400425f5  mov     rcx, rsi; Src
0x1400425f8  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x1400425fd  nop
0x1400425fe  jmp     short loc_14004261E
0x140042600  mov     r8, rdi
0x140042603  lea     rdx, [rbp+57h+var_60]
0x140042607  mov     rcx, rbx
0x14004260a  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x14004260f  lea     rcx, [rbx+0D8h]
0x140042616  mov     rdx, rax
0x140042619  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14004261e  lea     rcx, [rbp+57h+var_60]; void *
0x140042622  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042627  jmp     short loc_14004268D
0x140042629  mov     r8, rdi
0x14004262c  lea     rdx, [rbp+57h+var_60]
0x140042630  mov     rcx, rbx
0x140042633  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042638  mov     rdx, rax; void *
0x14004263b  lea     rcx, [rbp+57h+Src]; Src
0x14004263f  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042644  lea     rcx, [rbx+0D8h]
0x14004264b  mov     rdx, rax
0x14004264e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042653  lea     rcx, [rbp+57h+Src]; void *
0x140042657  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004265c  mov     rcx, rbx; this
0x14004265f  call    ?UpdateEndpointNameProperty@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(void)
0x140042664  mov     edi, eax
0x140042666  test    eax, eax
0x140042668  jns     short loc_140042686
0x14004266a  mov     edx, 3C2h; void *
0x14004266f  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042676  mov     r9d, edi; char *
0x140042679  mov     rcx, [rbp+5Fh]; this
0x14004267d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042682  mov     eax, edi
0x140042684  jmp     short loc_14004268F
0x140042686  mov     byte ptr [rbx+13Fh], 1
0x14004268d  xor     eax, eax
0x14004268f  mov     rcx, [rbp+57h+var_20]
0x140042693  xor     rcx, rsp; StackCookie
0x140042696  call    __security_check_cookie
0x14004269b  mov     rbx, [rsp+0E0h+arg_10]
0x1400426a3  add     rsp, 0D0h
0x1400426aa  pop     rdi
0x1400426ab  pop     rsi
0x1400426ac  pop     rbp
0x1400426ad  retn
```
