# CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(MidiLoopbackDeviceDefinition const &)

- ea: `0x18001e50c`
- end: `0x18001e655`
- name: `?DeleteSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJAEBUMidiLoopbackDeviceDefinition@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiEndpointManager *__hidden this, const struct MidiLoopbackDeviceDefinition *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cd54`
- `0x18001e448`

## callees

- `0x180001db8`
- `0x18000a024`
- `0x18000ccd8`
- `0x18001e50c`
- `0x180032010`

## string_xrefs

- `0x18001e5d6`: `CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(
        CMidi2LoopbackMidiEndpointManager *this,
        const struct MidiLoopbackDeviceDefinition *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  bool v14; // cc
  const struct MidiLoopbackDeviceDefinition *v15; // rax
  int v16; // [rsp+20h] [rbp-60h]
  _QWORD *v17; // [rsp+60h] [rbp-20h] BYREF
  const struct MidiLoopbackDeviceDefinition *v18; // [rsp+68h] [rbp-18h] BYREF
  CMidi2LoopbackMidiEndpointManager *v19; // [rsp+70h] [rbp-10h] BYREF
  const char *v20; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  _QWORD *v22; // [rsp+A0h] [rbp+20h] BYREF
  _QWORD *v23; // [rsp+B0h] [rbp+30h] BYREF
  _QWORD *v24; // [rsp+B8h] [rbp+38h] BYREF

  if ( !*((_BYTE *)this + 16) )
  {
    v4 = -2147418113;
    v5 = 199;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)v4,
      v16);
    return v4;
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v4 = -2147467261;
    v5 = 200;
    goto LABEL_3;
  }
  v7 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v10 = (_QWORD *)((char *)a2 + 64);
    if ( *((_QWORD *)a2 + 11) > 7u )
      v10 = (_QWORD *)*v10;
    v22 = v10;
    v11 = (_QWORD *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 7) > 7u )
      v11 = (_QWORD *)*v11;
    v23 = v11;
    v12 = (_QWORD *)((char *)a2 + 128);
    if ( *((_QWORD *)a2 + 19) > 7u )
      v12 = (_QWORD *)*v12;
    v24 = v12;
    v13 = (_QWORD *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v13 = (_QWORD *)*v13;
    v14 = *((_QWORD *)a2 + 3) <= 7u;
    v17 = v13;
    if ( v14 )
      v15 = a2;
    else
      v15 = *(const struct MidiLoopbackDeviceDefinition **)a2;
    v18 = v15;
    v19 = this;
    v20 = "CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)byte_1800586D1,
      v8,
      v9,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22);
  }
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 72LL))(*((_QWORD *)this + 11));
}

```

## disassembly

```asm
0x18001e50c  push    rbp
0x18001e50e  push    rbx
0x18001e50f  push    rdi
0x18001e510  mov     rbp, rsp
0x18001e513  sub     rsp, 80h
0x18001e51a  cmp     byte ptr [rcx+10h], 0
0x18001e51e  mov     rbx, rdx
0x18001e521  mov     rdi, rcx
0x18001e524  jnz     short loc_18001E54A
0x18001e526  mov     ebx, 8000FFFFh
0x18001e52b  mov     edx, 0C7h; void *
0x18001e530  mov     rcx, [rbp+18h]; this
0x18001e534  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001e53b  mov     r9d, ebx; char *
0x18001e53e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e543  mov     eax, ebx
0x18001e545  jmp     loc_18001E64A
0x18001e54a  cmp     qword ptr [rcx+58h], 0
0x18001e54f  jnz     short loc_18001E55D
0x18001e551  mov     ebx, 80004003h
0x18001e556  mov     edx, 0C8h
0x18001e55b  jmp     short loc_18001E530
0x18001e55d  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001e562  mov     rcx, [rax+8]
0x18001e566  mov     eax, [rcx]
0x18001e568  cmp     eax, 4
0x18001e56b  jbe     loc_18001E629
0x18001e571  lea     rax, [rbx+40h]
0x18001e575  cmp     qword ptr [rax+18h], 7
0x18001e57a  jbe     short loc_18001E57F
0x18001e57c  mov     rax, [rax]
0x18001e57f  mov     [rbp+arg_0], rax
0x18001e583  lea     rax, [rbx+20h]
0x18001e587  cmp     qword ptr [rax+18h], 7
0x18001e58c  jbe     short loc_18001E591
0x18001e58e  mov     rax, [rax]
0x18001e591  mov     [rbp+arg_10], rax
0x18001e595  lea     rax, [rbx+80h]
0x18001e59c  cmp     qword ptr [rax+18h], 7
0x18001e5a1  jbe     short loc_18001E5A6
0x18001e5a3  mov     rax, [rax]
0x18001e5a6  mov     [rbp+arg_18], rax
0x18001e5aa  lea     rax, [rbx+60h]
0x18001e5ae  cmp     qword ptr [rax+18h], 7
0x18001e5b3  jbe     short loc_18001E5B8
0x18001e5b5  mov     rax, [rax]
0x18001e5b8  cmp     qword ptr [rbx+18h], 7
0x18001e5bd  mov     [rbp+var_20], rax
0x18001e5c1  jbe     short loc_18001E5C8
0x18001e5c3  mov     rax, [rbx]
0x18001e5c6  jmp     short loc_18001E5CB
0x18001e5c8  mov     rax, rbx
0x18001e5cb  mov     [rbp+var_18], rax
0x18001e5cf  lea     rdx, byte_1800586D1
0x18001e5d6  lea     rax, aCmidi2loopback_8; "CMidi2LoopbackMidiEndpointManager::Dele"...
0x18001e5dd  mov     [rbp+var_10], rdi
0x18001e5e1  mov     [rbp+var_8], rax
0x18001e5e5  lea     rax, [rbp+arg_0]
0x18001e5e9  mov     [rsp+80h+var_30], rax
0x18001e5ee  lea     rax, [rbp+arg_10]
0x18001e5f2  mov     [rsp+80h+var_38], rax
0x18001e5f7  lea     rax, [rbp+arg_18]
0x18001e5fb  mov     [rsp+80h+var_40], rax
0x18001e600  lea     rax, [rbp+var_20]
0x18001e604  mov     [rsp+80h+var_48], rax
0x18001e609  lea     rax, [rbp+var_18]
0x18001e60d  mov     [rsp+80h+var_50], rax
0x18001e612  lea     rax, [rbp+var_10]
0x18001e616  mov     [rsp+80h+var_58], rax
0x18001e61b  lea     rax, [rbp+var_8]
0x18001e61f  mov     [rsp+80h+var_60], rax
0x18001e624  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001e629  mov     rcx, [rdi+58h]
0x18001e62d  lea     rdx, [rbx+0A0h]
0x18001e634  cmp     qword ptr [rdx+18h], 7
0x18001e639  mov     rax, [rcx]
0x18001e63c  jbe     short loc_18001E641
0x18001e63e  mov     rdx, [rdx]
0x18001e641  mov     rax, [rax+48h]
0x18001e645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64a  add     rsp, 80h
0x18001e651  pop     rdi
0x18001e652  pop     rbx
0x18001e653  pop     rbp
0x18001e654  retn
```
