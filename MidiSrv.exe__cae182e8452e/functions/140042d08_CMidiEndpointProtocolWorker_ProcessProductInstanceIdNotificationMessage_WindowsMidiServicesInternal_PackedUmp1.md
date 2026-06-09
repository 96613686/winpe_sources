# CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140042d08`
- end: `0x140042f1a`
- name: `?ProcessProductInstanceIdNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
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
- `0x140042d08`
- `0x1400452d8`

## string_xrefs

- `0x140042edb`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140042d61`: `CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage(
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
    v20 = L"Received Product Instance Id Notification";
    v21 = this;
    *(_QWORD *)v18 = "CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008BA1B,
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
    std::wstring::operator=((char **)this + 31, v15);
    std::wstring::~wstring(Src);
    updated = CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(this);
    if ( updated < 0 )
    {
      v12 = 899;
      goto LABEL_18;
    }
LABEL_19:
    *((_BYTE *)this + 320) = 1;
    return 0;
  }
  if ( ((*(_DWORD *)a2 >> 26) & 3) == 1 )
  {
    v13 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    std::wstring::operator=((char **)this + 31, v13);
    goto LABEL_15;
  }
  if ( ((*(_DWORD *)a2 >> 26) & 3) != 2 )
  {
    if ( ((*(_DWORD *)a2 >> 26) & 3) != 3 || !*((_QWORD *)this + 33) )
      return 0;
    v8 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    v9 = (void *)std::operator+<unsigned short>(v22, (char *)this + 248, v8);
    v10 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v9);
    std::wstring::operator=((char **)this + 31, v10);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v23);
    updated = CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(this);
    if ( updated < 0 )
    {
      v12 = 925;
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
  if ( *((_QWORD *)this + 33) )
  {
    CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v23, a2);
    std::wstring::operator+=((char *)this + 248);
LABEL_15:
    std::wstring::~wstring(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x140042d08  mov     [rsp-8+arg_10], rbx
0x140042d0d  push    rbp
0x140042d0e  push    rsi
0x140042d0f  push    rdi
0x140042d10  lea     rbp, [rsp-47h]
0x140042d15  sub     rsp, 0D0h
0x140042d1c  mov     rax, cs:__security_cookie
0x140042d23  xor     rax, rsp
0x140042d26  mov     [rbp+57h+var_20], rax
0x140042d2a  mov     rdi, rdx
0x140042d2d  mov     rbx, rcx
0x140042d30  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140042d35  mov     rcx, [rax+8]
0x140042d39  mov     eax, [rcx]
0x140042d3b  cmp     eax, 4
0x140042d3e  jbe     short loc_140042D9C
0x140042d40  lea     rax, [rbx+38h]
0x140042d44  cmp     qword ptr [rax+18h], 7
0x140042d49  jbe     short loc_140042D4E
0x140042d4b  mov     rax, [rax]
0x140042d4e  mov     [rbp+57h+var_98], rax
0x140042d52  lea     rax, aReceivedProduc; "Received Product Instance Id Notificati"...
0x140042d59  mov     [rbp+57h+var_90], rax
0x140042d5d  mov     [rbp+57h+var_88], rbx
0x140042d61  lea     rax, aCmidiendpointp_4; "CMidiEndpointProtocolWorker::ProcessPro"...
0x140042d68  mov     qword ptr [rbp+57h+var_A0], rax
0x140042d6c  lea     rax, [rbp+57h+var_98]
0x140042d70  mov     [rsp+0E0h+var_A8], rax
0x140042d75  lea     rax, [rbp+57h+var_90]
0x140042d79  mov     [rsp+0E0h+var_B0], rax
0x140042d7e  lea     rax, [rbp+57h+var_88]
0x140042d82  mov     [rsp+0E0h+var_B8], rax
0x140042d87  lea     rax, [rbp+57h+var_A0]
0x140042d8b  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140042d90  lea     rdx, byte_14008BA1B
0x140042d97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042d9c  mov     ecx, [rdi]
0x140042d9e  shr     ecx, 1Ah
0x140042da1  and     ecx, 3
0x140042da4  jz      loc_140042E95
0x140042daa  sub     ecx, 1
0x140042dad  jz      loc_140042E6C
0x140042db3  sub     ecx, 1
0x140042db6  jz      loc_140042E3C
0x140042dbc  cmp     ecx, 1
0x140042dbf  jnz     loc_140042EF9
0x140042dc5  lea     rsi, [rbx+0F8h]
0x140042dcc  cmp     qword ptr [rsi+10h], 0
0x140042dd1  jz      loc_140042EF9
0x140042dd7  mov     r8, rdi
0x140042dda  lea     rdx, [rbp+57h+var_60]
0x140042dde  mov     rcx, rbx
0x140042de1  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042de6  nop
0x140042de7  mov     r8, rax
0x140042dea  mov     rdx, rsi
0x140042ded  lea     rcx, [rbp+57h+var_80]
0x140042df1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140042df6  mov     rdx, rax; void *
0x140042df9  lea     rcx, [rbp+57h+Src]; Src
0x140042dfd  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042e02  mov     rdx, rax
0x140042e05  mov     rcx, rsi
0x140042e08  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042e0d  lea     rcx, [rbp+57h+Src]; void *
0x140042e11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042e16  nop
0x140042e17  lea     rcx, [rbp+57h+var_60]; void *
0x140042e1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042e20  mov     rcx, rbx; this
0x140042e23  call    ?UpdateEndpointProductInstanceIdProperty@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(void)
0x140042e28  mov     edi, eax
0x140042e2a  test    eax, eax
0x140042e2c  jns     loc_140042EF2
0x140042e32  mov     edx, 39Dh
0x140042e37  jmp     loc_140042EDB
0x140042e3c  lea     rsi, [rbx+0F8h]
0x140042e43  cmp     qword ptr [rsi+10h], 0
0x140042e48  jz      loc_140042EF9
0x140042e4e  mov     r8, rdi
0x140042e51  lea     rdx, [rbp+57h+var_60]
0x140042e55  mov     rcx, rbx
0x140042e58  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042e5d  nop
0x140042e5e  mov     rdx, rax
0x140042e61  mov     rcx, rsi; Src
0x140042e64  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x140042e69  nop
0x140042e6a  jmp     short loc_140042E8A
0x140042e6c  mov     r8, rdi
0x140042e6f  lea     rdx, [rbp+57h+var_60]
0x140042e73  mov     rcx, rbx
0x140042e76  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042e7b  lea     rcx, [rbx+0F8h]
0x140042e82  mov     rdx, rax
0x140042e85  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042e8a  lea     rcx, [rbp+57h+var_60]; void *
0x140042e8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042e93  jmp     short loc_140042EF9
0x140042e95  mov     r8, rdi
0x140042e98  lea     rdx, [rbp+57h+var_60]
0x140042e9c  mov     rcx, rbx
0x140042e9f  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042ea4  mov     rdx, rax; void *
0x140042ea7  lea     rcx, [rbp+57h+Src]; Src
0x140042eab  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042eb0  lea     rcx, [rbx+0F8h]
0x140042eb7  mov     rdx, rax
0x140042eba  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042ebf  lea     rcx, [rbp+57h+Src]; void *
0x140042ec3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042ec8  mov     rcx, rbx; this
0x140042ecb  call    ?UpdateEndpointProductInstanceIdProperty@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(void)
0x140042ed0  mov     edi, eax
0x140042ed2  test    eax, eax
0x140042ed4  jns     short loc_140042EF2
0x140042ed6  mov     edx, 383h; void *
0x140042edb  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042ee2  mov     r9d, edi; char *
0x140042ee5  mov     rcx, [rbp+5Fh]; this
0x140042ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042eee  mov     eax, edi
0x140042ef0  jmp     short loc_140042EFB
0x140042ef2  mov     byte ptr [rbx+140h], 1
0x140042ef9  xor     eax, eax
0x140042efb  mov     rcx, [rbp+57h+var_20]
0x140042eff  xor     rcx, rsp; StackCookie
0x140042f02  call    __security_check_cookie
0x140042f07  mov     rbx, [rsp+0E0h+arg_10]
0x140042f0f  add     rsp, 0D0h
0x140042f16  pop     rdi
0x140042f17  pop     rsi
0x140042f18  pop     rbp
0x140042f19  retn
```
