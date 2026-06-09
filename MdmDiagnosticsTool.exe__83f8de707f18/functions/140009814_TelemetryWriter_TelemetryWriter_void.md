# TelemetryWriter::TelemetryWriter(void)

- ea: `0x140009814`
- end: `0x1400098f9`
- name: `??0TelemetryWriter@@QEAA@XZ`
- size: `229`
- prototype: `TelemetryWriter *__fastcall(TelemetryWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008694`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001258`
- `0x140009814`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140009862`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140009862`

## pseudocode

```c
TelemetryWriter *__fastcall TelemetryWriter::TelemetryWriter(TelemetryWriter *this)
{
  __int64 v2; // r8
  __int64 v3; // r9
  char *v4; // rdi

  *((_DWORD *)this + 1) = 0;
  *((_BYTE *)this + 8) = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  if ( (unsigned int)dword_140012000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140012000, 0x200000000000LL, v2, v3) )
  {
    v4 = (char *)this + 12;
    EventActivityIdControl(3u, (LPGUID)((char *)this + 12));
  }
  else
  {
    v4 = (char *)this + 12;
    *(_OWORD *)((char *)this + 12) = 0;
  }
  *((_DWORD *)this + 1) = 1;
  if ( (unsigned int)dword_140012000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140012000, 0x200000000000LL, v2, v3) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_140012000,
      byte_14000F97B,
      v4);
  *(_DWORD *)this = 0;
  return this;
}

```

## disassembly

```asm
0x140009814  mov     [rsp+arg_0], rbx
0x140009819  push    rdi
0x14000981a  sub     rsp, 20h
0x14000981e  mov     rbx, rcx
0x140009821  mov     dword ptr [rcx+4], 0
0x140009828  mov     byte ptr [rcx+8], 0
0x14000982c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140009831  mov     eax, cs:dword_140012000
0x140009837  cmp     eax, 5
0x14000983a  jbe     short loc_140009870
0x14000983c  mov     rdx, 200000000000h
0x140009846  lea     rcx, dword_140012000
0x14000984d  call    _tlgKeywordOn
0x140009852  test    al, al
0x140009854  jz      short loc_140009870
0x140009856  lea     rdi, [rbx+0Ch]
0x14000985a  mov     ecx, 3; ControlCode
0x14000985f  mov     rdx, rdi; ActivityId
0x140009862  call    cs:__imp_EventActivityIdControl
0x140009869  nop     dword ptr [rax+rax+00h]
0x14000986e  jmp     short loc_14000987A
0x140009870  lea     rdi, [rbx+0Ch]
0x140009874  xorps   xmm0, xmm0
0x140009877  movups  xmmword ptr [rdi], xmm0
0x14000987a  mov     dword ptr [rbx+4], 1
0x140009881  mov     eax, cs:dword_140012000
0x140009887  cmp     eax, 5
0x14000988a  jbe     short loc_1400098E4
0x14000988c  mov     rdx, 200000000000h
0x140009896  lea     rcx, dword_140012000
0x14000989d  call    _tlgKeywordOn
0x1400098a2  test    al, al
0x1400098a4  jz      short loc_1400098E4
0x1400098a6  cmp     byte ptr [rbx+8], 0
0x1400098aa  jz      short loc_1400098CB
0x1400098ac  lea     r9, [rbx+1Ch]
0x1400098b0  cmp     dword ptr [r9], 0
0x1400098b4  jnz     short loc_1400098CE
0x1400098b6  cmp     dword ptr [r9+4], 0
0x1400098bb  jnz     short loc_1400098CE
0x1400098bd  cmp     dword ptr [r9+8], 0
0x1400098c2  jnz     short loc_1400098CE
0x1400098c4  cmp     dword ptr [r9+0Ch], 0
0x1400098c9  jnz     short loc_1400098CE
0x1400098cb  xor     r9d, r9d
0x1400098ce  mov     r8, rdi
0x1400098d1  lea     rdx, byte_14000F97B
0x1400098d8  lea     rcx, dword_140012000
0x1400098df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1400098e4  mov     dword ptr [rbx], 0
0x1400098ea  mov     rax, rbx
0x1400098ed  mov     rbx, [rsp+28h+arg_0]
0x1400098f2  add     rsp, 20h
0x1400098f6  pop     rdi
0x1400098f7  retn
```
