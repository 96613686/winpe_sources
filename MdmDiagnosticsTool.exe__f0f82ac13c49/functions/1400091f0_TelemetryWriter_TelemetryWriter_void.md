# TelemetryWriter::TelemetryWriter(void)

- ea: `0x1400091f0`
- end: `0x1400092ce`
- name: `??0TelemetryWriter@@QEAA@XZ`
- size: `222`
- prototype: `TelemetryWriter *__fastcall(TelemetryWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008130`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001248`
- `0x1400091f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000923e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000923e`

## pseudocode

```c
TelemetryWriter *__fastcall TelemetryWriter::TelemetryWriter(TelemetryWriter *this)
{
  *((_DWORD *)this + 1) = 0;
  *((_BYTE *)this + 8) = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  if ( (unsigned int)dword_140011000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140011000, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)((char *)this + 12));
  else
    *(_OWORD *)((char *)this + 12) = 0;
  *((_DWORD *)this + 1) = 1;
  if ( (unsigned int)dword_140011000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140011000, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_140011000,
      (__int64)byte_14000E97B);
  *(_DWORD *)this = 0;
  return this;
}

```

## disassembly

```asm
0x1400091f0  mov     [rsp+arg_0], rbx
0x1400091f5  push    rdi
0x1400091f6  sub     rsp, 20h
0x1400091fa  mov     rbx, rcx
0x1400091fd  mov     dword ptr [rcx+4], 0
0x140009204  mov     byte ptr [rcx+8], 0
0x140009208  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000920d  mov     eax, cs:dword_140011000
0x140009213  cmp     eax, 5
0x140009216  jbe     short loc_140009246
0x140009218  mov     rdx, 200000000000h
0x140009222  lea     rcx, dword_140011000
0x140009229  call    _tlgKeywordOn
0x14000922e  test    al, al
0x140009230  jz      short loc_140009246
0x140009232  lea     rdi, [rbx+0Ch]
0x140009236  mov     ecx, 3; ControlCode
0x14000923b  mov     rdx, rdi; ActivityId
0x14000923e  call    cs:__imp_EventActivityIdControl
0x140009244  jmp     short loc_140009250
0x140009246  lea     rdi, [rbx+0Ch]
0x14000924a  xorps   xmm0, xmm0
0x14000924d  movups  xmmword ptr [rdi], xmm0
0x140009250  mov     dword ptr [rbx+4], 1
0x140009257  mov     eax, cs:dword_140011000
0x14000925d  cmp     eax, 5
0x140009260  jbe     short loc_1400092BA
0x140009262  mov     rdx, 200000000000h
0x14000926c  lea     rcx, dword_140011000
0x140009273  call    _tlgKeywordOn
0x140009278  test    al, al
0x14000927a  jz      short loc_1400092BA
0x14000927c  cmp     byte ptr [rbx+8], 0
0x140009280  jz      short loc_1400092A1
0x140009282  lea     r9, [rbx+1Ch]
0x140009286  cmp     dword ptr [r9], 0
0x14000928a  jnz     short loc_1400092A4
0x14000928c  cmp     dword ptr [r9+4], 0
0x140009291  jnz     short loc_1400092A4
0x140009293  cmp     dword ptr [r9+8], 0
0x140009298  jnz     short loc_1400092A4
0x14000929a  cmp     dword ptr [r9+0Ch], 0
0x14000929f  jnz     short loc_1400092A4
0x1400092a1  xor     r9d, r9d
0x1400092a4  mov     r8, rdi
0x1400092a7  lea     rdx, byte_14000E97B
0x1400092ae  lea     rcx, dword_140011000
0x1400092b5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1400092ba  mov     dword ptr [rbx], 0
0x1400092c0  mov     rax, rbx
0x1400092c3  mov     rbx, [rsp+28h+arg_0]
0x1400092c8  add     rsp, 20h
0x1400092cc  pop     rdi
0x1400092cd  retn
```
