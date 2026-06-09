# CMidi2MidiSrvConfigurationManager::GetTransformList(ushort * *)

- ea: `0x18000c090`
- end: `0x18000c161`
- name: `?GetTransformList@CMidi2MidiSrvConfigurationManager@@UEAAJPEAPEAG@Z`
- size: `209`
- prototype: `int(CMidi2MidiSrvConfigurationManager *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800017d0`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c090`
- `0x180012830`
- `0x180015010`

## string_xrefs

- `0x18000c123`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`
- `0x18000c0b9`: `CMidi2MidiSrvConfigurationManager::GetTransformList`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvConfigurationManager::GetTransformList(
        CMidi2MidiSrvConfigurationManager *this,
        unsigned __int16 **a2)
{
  char *v4; // rbx
  _DWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  CMidi2MidiSrv *v12; // rcx
  int v13; // [rsp+20h] [rbp-28h]
  __int128 v14; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char *v16; // [rsp+50h] [rbp+8h] BYREF
  const char *v17; // [rsp+60h] [rbp+18h] BYREF

  v4 = (char *)this - 8;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v16 = (char *)this - 8;
    v17 = "CMidi2MidiSrvConfigurationManager::GetTransformList";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v5,
      (unsigned int)qword_18001A068,
      v6,
      v7,
      (__int64)&v17,
      (__int64)&v16);
  }
  if ( !v4[48] )
  {
    v8 = *(_QWORD *)v4;
    v14 = 0;
    v9 = (*(__int64 (__fastcall **)(char *, __int128 *, _QWORD, _QWORD))(v8 + 24))((char *)this - 8, &v14, 0, 0);
    if ( v9 < 0 )
    {
      v10 = 103;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
        (const char *)(unsigned int)v9,
        v13);
      return (unsigned int)v9;
    }
  }
  v12 = (CMidi2MidiSrv *)*((_QWORD *)this + 2);
  if ( !v12 )
  {
    v9 = -2147221008;
    v10 = 106;
    goto LABEL_6;
  }
  return CMidi2MidiSrv::GetTransformList(v12, a2);
}

```

## disassembly

```asm
0x18000c090  mov     [rsp+arg_8], rbx
0x18000c095  mov     [rsp+arg_18], rsi
0x18000c09a  push    rdi
0x18000c09b  sub     rsp, 40h
0x18000c09f  mov     rsi, rdx
0x18000c0a2  mov     rdi, rcx
0x18000c0a5  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c0aa  lea     rbx, [rdi-8]
0x18000c0ae  mov     rcx, [rax+8]
0x18000c0b2  mov     eax, [rcx]
0x18000c0b4  cmp     eax, 4
0x18000c0b7  jbe     short loc_18000C0EA
0x18000c0b9  lea     rax, aCmidi2midisrvc_2; "CMidi2MidiSrvConfigurationManager::GetT"...
0x18000c0c0  mov     [rsp+48h+arg_0], rbx
0x18000c0c5  mov     [rsp+48h+arg_10], rax
0x18000c0ca  lea     rdx, qword_18001A068
0x18000c0d1  lea     rax, [rsp+48h+arg_0]
0x18000c0d6  mov     [rsp+48h+var_20], rax
0x18000c0db  lea     rax, [rsp+48h+arg_10]
0x18000c0e0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c0e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c0ea  cmp     byte ptr [rbx+30h], 0
0x18000c0ee  jnz     short loc_18000C136
0x18000c0f0  mov     rax, [rbx]
0x18000c0f3  lea     rdx, [rsp+48h+var_18]
0x18000c0f8  xorps   xmm0, xmm0
0x18000c0fb  xor     r9d, r9d
0x18000c0fe  xor     r8d, r8d
0x18000c101  movdqa  [rsp+48h+var_18], xmm0
0x18000c107  mov     rcx, rbx
0x18000c10a  mov     rax, [rax+18h]
0x18000c10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c113  mov     ebx, eax
0x18000c115  test    eax, eax
0x18000c117  jns     short loc_18000C136
0x18000c119  mov     edx, 67h ; 'g'; void *
0x18000c11e  mov     rcx, [rsp+48h]; this
0x18000c123  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c12a  mov     r9d, ebx; char *
0x18000c12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c132  mov     eax, ebx
0x18000c134  jmp     short loc_18000C151
0x18000c136  mov     rcx, [rdi+10h]; this
0x18000c13a  test    rcx, rcx
0x18000c13d  jnz     short loc_18000C149
0x18000c13f  mov     ebx, 800401F0h
0x18000c144  lea     edx, [rcx+6Ah]
0x18000c147  jmp     short loc_18000C11E
0x18000c149  mov     rdx, rsi; unsigned __int16 **
0x18000c14c  call    ?GetTransformList@CMidi2MidiSrv@@QEAAJPEAPEAG@Z; CMidi2MidiSrv::GetTransformList(ushort * *)
0x18000c151  mov     rbx, [rsp+48h+arg_8]
0x18000c156  mov     rsi, [rsp+48h+arg_18]
0x18000c15b  add     rsp, 40h
0x18000c15f  pop     rdi
0x18000c160  retn
```
