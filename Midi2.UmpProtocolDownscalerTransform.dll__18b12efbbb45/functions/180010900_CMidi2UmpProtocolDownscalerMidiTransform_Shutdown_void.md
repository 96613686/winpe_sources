# CMidi2UmpProtocolDownscalerMidiTransform::Shutdown(void)

- ea: `0x180010900`
- end: `0x180010985`
- name: `?Shutdown@CMidi2UmpProtocolDownscalerMidiTransform@@UEAAJXZ`
- size: `133`
- prototype: `__int64 __fastcall(CMidi2UmpProtocolDownscalerMidiTransform *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800016dc`
- `0x18000a798`
- `0x180010900`

## string_xrefs

- `0x180010944`: `CMidi2UmpProtocolDownscalerMidiTransform::Shutdown`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::Shutdown(CMidi2UmpProtocolDownscalerMidiTransform *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  _QWORD *v5; // rax
  const char *v7; // [rsp+40h] [rbp-18h] BYREF
  _QWORD *v8; // [rsp+68h] [rbp+10h] BYREF
  const wchar_t *v9; // [rsp+70h] [rbp+18h] BYREF
  CMidi2UmpProtocolDownscalerMidiTransform *v10; // [rsp+78h] [rbp+20h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v5 = (_QWORD *)((char *)this + 104);
    if ( *((_QWORD *)this + 16) > 7u )
      v5 = (_QWORD *)*v5;
    v8 = v5;
    v10 = this;
    v9 = L"Enter";
    v7 = "CMidi2UmpProtocolDownscalerMidiTransform::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v2,
      (unsigned int)&word_1800171EE,
      v3,
      v4,
      (__int64)&v7,
      (__int64)&v10,
      (__int64)&v9,
      (__int64)&v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180010900  push    rbx
0x180010902  sub     rsp, 50h
0x180010906  mov     rbx, rcx
0x180010909  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18001090e  mov     rcx, [rax+8]
0x180010912  mov     eax, [rcx]
0x180010914  cmp     eax, 4
0x180010917  jbe     short loc_18001097D
0x180010919  lea     rax, [rbx+68h]
0x18001091d  cmp     qword ptr [rax+18h], 7
0x180010922  jbe     short loc_180010927
0x180010924  mov     rax, [rax]
0x180010927  mov     [rsp+58h+arg_8], rax
0x18001092c  lea     rdx, word_1800171EE
0x180010933  lea     rax, aEnter; "Enter"
0x18001093a  mov     [rsp+58h+arg_18], rbx
0x18001093f  mov     [rsp+58h+arg_10], rax
0x180010944  lea     rax, aCmidi2umpproto; "CMidi2UmpProtocolDownscalerMidiTransfor"...
0x18001094b  mov     [rsp+58h+var_18], rax
0x180010950  lea     rax, [rsp+58h+arg_8]
0x180010955  mov     [rsp+58h+var_20], rax
0x18001095a  lea     rax, [rsp+58h+arg_10]
0x18001095f  mov     [rsp+58h+var_28], rax
0x180010964  lea     rax, [rsp+58h+arg_18]
0x180010969  mov     [rsp+58h+var_30], rax
0x18001096e  lea     rax, [rsp+58h+var_18]
0x180010973  mov     [rsp+58h+var_38], rax
0x180010978  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001097d  xor     eax, eax
0x18001097f  add     rsp, 50h
0x180010983  pop     rbx
0x180010984  retn
```
