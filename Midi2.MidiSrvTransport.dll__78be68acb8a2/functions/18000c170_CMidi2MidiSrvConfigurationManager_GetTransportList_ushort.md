# CMidi2MidiSrvConfigurationManager::GetTransportList(ushort * *)

- ea: `0x18000c170`
- end: `0x18000c241`
- name: `?GetTransportList@CMidi2MidiSrvConfigurationManager@@UEAAJPEAPEAG@Z`
- size: `209`
- prototype: `__int64 __fastcall(CMidi2MidiSrvConfigurationManager *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800017d0`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c170`
- `0x180012964`
- `0x180015010`

## string_xrefs

- `0x18000c203`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`
- `0x18000c199`: `CMidi2MidiSrvConfigurationManager::GetTransportList`

## pseudocode

```c
int __fastcall CMidi2MidiSrvConfigurationManager::GetTransportList(
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
    v17 = "CMidi2MidiSrvConfigurationManager::GetTransportList";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v5,
      (unsigned int)byte_18001A091,
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
      v10 = 80;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
        (const char *)(unsigned int)v9,
        v13);
      return v9;
    }
  }
  v12 = (CMidi2MidiSrv *)*((_QWORD *)this + 2);
  if ( !v12 )
  {
    v9 = -2147221008;
    v10 = 83;
    goto LABEL_6;
  }
  return CMidi2MidiSrv::GetTransportList(v12, a2);
}

```

## disassembly

```asm
0x18000c170  mov     [rsp+arg_8], rbx
0x18000c175  mov     [rsp+arg_18], rsi
0x18000c17a  push    rdi
0x18000c17b  sub     rsp, 40h
0x18000c17f  mov     rsi, rdx
0x18000c182  mov     rdi, rcx
0x18000c185  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c18a  lea     rbx, [rdi-8]
0x18000c18e  mov     rcx, [rax+8]
0x18000c192  mov     eax, [rcx]
0x18000c194  cmp     eax, 4
0x18000c197  jbe     short loc_18000C1CA
0x18000c199  lea     rax, aCmidi2midisrvc_1; "CMidi2MidiSrvConfigurationManager::GetT"...
0x18000c1a0  mov     [rsp+48h+arg_0], rbx
0x18000c1a5  mov     [rsp+48h+arg_10], rax
0x18000c1aa  lea     rdx, byte_18001A091
0x18000c1b1  lea     rax, [rsp+48h+arg_0]
0x18000c1b6  mov     [rsp+48h+var_20], rax
0x18000c1bb  lea     rax, [rsp+48h+arg_10]
0x18000c1c0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c1c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c1ca  cmp     byte ptr [rbx+30h], 0
0x18000c1ce  jnz     short loc_18000C216
0x18000c1d0  mov     rax, [rbx]
0x18000c1d3  lea     rdx, [rsp+48h+var_18]
0x18000c1d8  xorps   xmm0, xmm0
0x18000c1db  xor     r9d, r9d
0x18000c1de  xor     r8d, r8d
0x18000c1e1  movdqa  [rsp+48h+var_18], xmm0
0x18000c1e7  mov     rcx, rbx
0x18000c1ea  mov     rax, [rax+18h]
0x18000c1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f3  mov     ebx, eax
0x18000c1f5  test    eax, eax
0x18000c1f7  jns     short loc_18000C216
0x18000c1f9  mov     edx, 50h ; 'P'; void *
0x18000c1fe  mov     rcx, [rsp+48h]; this
0x18000c203  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c20a  mov     r9d, ebx; char *
0x18000c20d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c212  mov     eax, ebx
0x18000c214  jmp     short loc_18000C231
0x18000c216  mov     rcx, [rdi+10h]; this
0x18000c21a  test    rcx, rcx
0x18000c21d  jnz     short loc_18000C229
0x18000c21f  mov     ebx, 800401F0h
0x18000c224  lea     edx, [rcx+53h]
0x18000c227  jmp     short loc_18000C1FE
0x18000c229  mov     rdx, rsi; unsigned __int16 **
0x18000c22c  call    ?GetTransportList@CMidi2MidiSrv@@QEAAJPEAPEAG@Z; CMidi2MidiSrv::GetTransportList(ushort * *)
0x18000c231  mov     rbx, [rsp+48h+arg_8]
0x18000c236  mov     rsi, [rsp+48h+arg_18]
0x18000c23b  add     rsp, 40h
0x18000c23f  pop     rdi
0x18000c240  retn
```
