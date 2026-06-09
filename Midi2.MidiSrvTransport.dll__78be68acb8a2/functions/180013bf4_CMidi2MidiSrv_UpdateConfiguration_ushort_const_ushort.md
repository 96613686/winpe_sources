# CMidi2MidiSrv::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x180013bf4`
- end: `0x180013d8f`
- name: `?UpdateConfiguration@CMidi2MidiSrv@@QEAAJPEBGPEAPEAG@Z`
- size: `411`
- prototype: `int(CMidi2MidiSrv *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000c480`

## callees

- `0x180001998`
- `0x180007e24`
- `0x180009bf8`
- `0x18000bc80`
- `0x1800121c4`
- `0x180012574`
- `0x180012610`
- `0x180013bf4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180013cf9`
- `RPCRT4!RpcBindingFree` at `0x180013d74`
- `RPCRT4!RpcBindingFree` at `0x180013cf9`
- `RPCRT4!RpcBindingFree` at `0x180013d74`

## string_xrefs

- `0x180013c32`: `Entering UpdateConfiguration`
- `0x180013c3d`: `CMidi2MidiSrv::UpdateConfiguration`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::UpdateConfiguration(
        CMidi2MidiSrv *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  _DWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rdx
  int MidiSrvBindingHandle; // ebx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // [rsp+20h] [rbp-39h]
  unsigned __int16 **v14; // [rsp+50h] [rbp-9h] BYREF
  const unsigned __int16 *v15; // [rsp+58h] [rbp-1h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp+7h] BYREF
  CMidi2MidiSrv *v17; // [rsp+68h] [rbp+Fh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+17h] BYREF
  _QWORD v19[7]; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+6Fh] BYREF
  RPC_BINDING_HANDLE v22; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int16 *Block; // [rsp+D8h] [rbp+7Fh] BYREF

  v21 = a2;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v15 = v21;
    v16 = L"Entering UpdateConfiguration";
    Binding = "CMidi2MidiSrv::UpdateConfiguration";
    v14 = a3;
    v17 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (_DWORD)v5,
      (unsigned int)&dword_18001A9FC,
      v6,
      v7,
      (__int64)&Binding,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  if ( !a3 )
  {
    v8 = 523;
LABEL_5:
    MidiSrvBindingHandle = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)0x80070057LL,
      v13);
    return (unsigned int)MidiSrvBindingHandle;
  }
  if ( !v21 )
  {
    v8 = 525;
    goto LABEL_5;
  }
  v22 = 0;
  MidiSrvBindingHandle = GetMidiSrvBindingHandle(&v22);
  if ( MidiSrvBindingHandle < 0 )
  {
    v11 = 528;
    goto LABEL_11;
  }
  Block = 0;
  v19[0] = &v22;
  v19[3] = this;
  v19[1] = &v21;
  v19[2] = &Block;
  MidiSrvBindingHandle = CMidi2MidiSrv::UpdateConfiguration_::_36_::_lambda_1_::operator()(v19);
  if ( MidiSrvBindingHandle < 0 )
  {
    v11 = 553;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)(unsigned int)MidiSrvBindingHandle,
      v13);
    if ( v22 )
    {
      Binding = v22;
      RpcBindingFree(&Binding);
    }
    return (unsigned int)MidiSrvBindingHandle;
  }
  v12 = CopyStringToOutputParameter(Block, a3);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)(unsigned int)v12,
      v13);
  if ( v22 )
  {
    Binding = v22;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x180013bf4  mov     [rsp-8+arg_0], rbx
0x180013bf9  mov     [rsp-8+arg_8], rdx
0x180013bfe  push    rbp
0x180013bff  push    rsi
0x180013c00  push    rdi
0x180013c01  lea     rbp, [rsp-47h]
0x180013c06  sub     rsp, 0A0h
0x180013c0d  mov     rdi, r8
0x180013c10  mov     rsi, rcx
0x180013c13  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x180013c18  mov     rcx, [rax+8]
0x180013c1c  mov     eax, [rcx]
0x180013c1e  cmp     eax, 4
0x180013c21  jbe     short loc_180013C82
0x180013c23  mov     rax, [rbp+57h+arg_8]
0x180013c27  lea     rdx, dword_18001A9FC
0x180013c2e  mov     [rbp+57h+var_58], rax
0x180013c32  lea     rax, aEnteringUpdate; "Entering UpdateConfiguration"
0x180013c39  mov     [rbp+57h+var_50], rax
0x180013c3d  lea     rax, aCmidi2midisrvU; "CMidi2MidiSrv::UpdateConfiguration"
0x180013c44  mov     [rbp+57h+Binding], rax
0x180013c48  lea     rax, [rbp+57h+var_60]
0x180013c4c  mov     [rsp+0B0h+var_70], rax
0x180013c51  lea     rax, [rbp+57h+var_58]
0x180013c55  mov     [rsp+0B0h+var_78], rax
0x180013c5a  lea     rax, [rbp+57h+var_50]
0x180013c5e  mov     [rsp+0B0h+var_80], rax
0x180013c63  lea     rax, [rbp+57h+var_48]
0x180013c67  mov     [rsp+0B0h+var_88], rax
0x180013c6c  lea     rax, [rbp+57h+Binding]
0x180013c70  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180013c75  mov     [rbp+57h+var_60], rdi
0x180013c79  mov     [rbp+57h+var_48], rsi
0x180013c7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180013c82  test    rdi, rdi
0x180013c85  jnz     short loc_180013CAB
0x180013c87  mov     edx, 20Bh; void *
0x180013c8c  mov     rcx, [rbp+5Fh]; this
0x180013c90  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180013c97  mov     ebx, 80070057h
0x180013c9c  mov     r9d, ebx; char *
0x180013c9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ca4  mov     eax, ebx
0x180013ca6  jmp     loc_180013D7C
0x180013cab  cmp     [rbp+57h+arg_8], 0
0x180013cb0  jnz     short loc_180013CB9
0x180013cb2  mov     edx, 20Dh
0x180013cb7  jmp     short loc_180013C8C
0x180013cb9  lea     rcx, [rbp+57h+arg_10]; Binding
0x180013cbd  mov     [rbp+57h+arg_10], 0
0x180013cc5  call    ?GetMidiSrvBindingHandle@@YAJPEAPEAX@Z; GetMidiSrvBindingHandle(void * *)
0x180013cca  mov     ebx, eax
0x180013ccc  test    eax, eax
0x180013cce  jns     short loc_180013D01
0x180013cd0  mov     edx, 210h; void *
0x180013cd5  mov     rcx, [rbp+5Fh]; this
0x180013cd9  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180013ce0  mov     r9d, ebx; char *
0x180013ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ce8  mov     rcx, [rbp+57h+arg_10]
0x180013cec  test    rcx, rcx
0x180013cef  jz      short loc_180013CA4
0x180013cf1  mov     [rbp+57h+Binding], rcx
0x180013cf5  lea     rcx, [rbp+57h+Binding]; Binding
0x180013cf9  call    cs:__imp_RpcBindingFree
0x180013cff  jmp     short loc_180013CA4
0x180013d01  lea     rax, [rbp+57h+arg_10]
0x180013d05  mov     [rbp+57h+Block], 0
0x180013d0d  mov     [rbp+57h+var_38], rax
0x180013d11  lea     rcx, [rbp+57h+var_38]
0x180013d15  lea     rax, [rbp+57h+arg_8]
0x180013d19  mov     [rbp+57h+var_20], rsi
0x180013d1d  mov     [rbp+57h+var_30], rax
0x180013d21  lea     rax, [rbp+57h+Block]
0x180013d25  mov     [rbp+57h+var_28], rax
0x180013d29  call    _CMidi2MidiSrv__UpdateConfiguration____36____lambda_1___operator__
0x180013d2e  mov     ebx, eax
0x180013d30  test    eax, eax
0x180013d32  jns     short loc_180013D3B
0x180013d34  mov     edx, 229h
0x180013d39  jmp     short loc_180013CD5
0x180013d3b  mov     rcx, [rbp+57h+Block]; Block
0x180013d3f  mov     rdx, rdi; unsigned __int16 **
0x180013d42  call    ?CopyStringToOutputParameter@@YAJPEBGPEAPEAG@Z; CopyStringToOutputParameter(ushort const *,ushort * *)
0x180013d47  test    eax, eax
0x180013d49  jns     short loc_180013D63
0x180013d4b  mov     rcx, [rbp+5Fh]; this
0x180013d4f  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180013d56  mov     r9d, eax; char *
0x180013d59  mov     edx, 22Ah; void *
0x180013d5e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013d63  mov     rax, [rbp+57h+arg_10]
0x180013d67  test    rax, rax
0x180013d6a  jz      short loc_180013D7A
0x180013d6c  lea     rcx, [rbp+57h+Binding]; Binding
0x180013d70  mov     [rbp+57h+Binding], rax
0x180013d74  call    cs:__imp_RpcBindingFree
0x180013d7a  xor     eax, eax
0x180013d7c  mov     rbx, [rsp+0B0h+arg_0]
0x180013d84  add     rsp, 0A0h
0x180013d8b  pop     rdi
0x180013d8c  pop     rsi
0x180013d8d  pop     rbp
0x180013d8e  retn
```
