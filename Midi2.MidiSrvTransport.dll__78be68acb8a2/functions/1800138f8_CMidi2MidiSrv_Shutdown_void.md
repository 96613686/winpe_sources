# CMidi2MidiSrv::Shutdown(void)

- ea: `0x1800138f8`
- end: `0x180013a36`
- name: `?Shutdown@CMidi2MidiSrv@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CMidi2MidiSrv *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000b7f0`
- `0x18000bbb0`
- `0x18000bfc0`
- `0x18000c3b0`
- `0x18000c8d0`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x180007e24`
- `0x180009bf8`
- `0x18000d190`
- `0x180010b10`
- `0x180012124`
- `0x180012610`
- `0x1800138f8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800139dc`
- `RPCRT4!RpcBindingFree` at `0x180013a26`
- `RPCRT4!RpcBindingFree` at `0x1800139dc`
- `RPCRT4!RpcBindingFree` at `0x180013a26`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::Shutdown(CMidiXProc **this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  CMidiXProc *v5; // rcx
  int v6; // eax
  int MidiSrvBindingHandle; // edi
  CMidiXProc *v9; // rdi
  __int64 v10; // rdx
  _QWORD v11[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  RPC_BINDING_HANDLE v13; // [rsp+60h] [rbp+20h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp+28h] BYREF
  const char *v15; // [rsp+70h] [rbp+30h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    Binding = this;
    v15 = "CMidi2MidiSrv::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v2,
      (unsigned __int8 *)qword_18001ABB0,
      v3,
      v4,
      (const unsigned __int16 **)&v15,
      (__int64)&Binding);
  }
  v5 = this[2];
  if ( v5 )
  {
    v6 = CMidiXProc::Shutdown(v5);
    MidiSrvBindingHandle = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
        (const char *)(unsigned int)v6);
      return (unsigned int)MidiSrvBindingHandle;
    }
    v9 = this[2];
    this[2] = 0;
    if ( v9 )
    {
      CMidiXProc::~CMidiXProc(v9);
      operator delete(v9);
    }
  }
  v13 = 0;
  MidiSrvBindingHandle = GetMidiSrvBindingHandle(&v13);
  if ( MidiSrvBindingHandle < 0 )
  {
    v10 = 239;
    goto LABEL_11;
  }
  if ( this[1] )
  {
    v11[1] = this;
    v11[0] = &v13;
    MidiSrvBindingHandle = CMidi2MidiSrv::Shutdown_::_29_::_lambda_1_::operator()(v11);
    if ( MidiSrvBindingHandle < 0 )
    {
      v10 = 251;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
        (const char *)(unsigned int)MidiSrvBindingHandle);
      if ( v13 )
      {
        Binding = v13;
        RpcBindingFree(&Binding);
      }
      return (unsigned int)MidiSrvBindingHandle;
    }
    this[1] = 0;
  }
  if ( v13 )
  {
    Binding = v13;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x1800138f8  push    rbp
0x1800138fa  push    rbx
0x1800138fb  push    rdi
0x1800138fc  mov     rbp, rsp
0x1800138ff  sub     rsp, 40h
0x180013903  mov     rbx, rcx
0x180013906  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18001390b  mov     rcx, [rax+8]
0x18001390f  mov     eax, [rcx]
0x180013911  cmp     eax, 4
0x180013914  jbe     short loc_180013943
0x180013916  lea     rax, aCmidi2midisrvS; "CMidi2MidiSrv::Shutdown"
0x18001391d  mov     [rbp+Binding], rbx
0x180013921  mov     [rbp+arg_10], rax
0x180013925  lea     rdx, qword_18001ABB0
0x18001392c  lea     rax, [rbp+Binding]
0x180013930  mov     [rsp+40h+var_18], rax
0x180013935  lea     rax, [rbp+arg_10]
0x180013939  mov     qword ptr [rsp+40h+var_20], rax; int
0x18001393e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180013943  mov     rcx, [rbx+10h]; this
0x180013947  test    rcx, rcx
0x18001394a  jz      short loc_18001399C
0x18001394c  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180013951  mov     edi, eax
0x180013953  test    eax, eax
0x180013955  jns     short loc_180013976
0x180013957  mov     rcx, [rbp+18h]; this
0x18001395b  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180013962  mov     r9d, eax; char *
0x180013965  mov     edx, 0E9h; void *
0x18001396a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001396f  mov     eax, edi
0x180013971  jmp     loc_180013A2E
0x180013976  mov     rdi, [rbx+10h]
0x18001397a  mov     qword ptr [rbx+10h], 0
0x180013982  test    rdi, rdi
0x180013985  jz      short loc_18001399C
0x180013987  mov     rcx, rdi; this
0x18001398a  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18001398f  mov     edx, 90h
0x180013994  mov     rcx, rdi; Block
0x180013997  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001399c  lea     rcx, [rbp+arg_0]; Binding
0x1800139a0  mov     [rbp+arg_0], 0
0x1800139a8  call    ?GetMidiSrvBindingHandle@@YAJPEAPEAX@Z; GetMidiSrvBindingHandle(void * *)
0x1800139ad  mov     edi, eax
0x1800139af  test    eax, eax
0x1800139b1  jns     short loc_1800139E4
0x1800139b3  mov     edx, 0EFh; void *
0x1800139b8  mov     rcx, [rbp+18h]; this
0x1800139bc  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x1800139c3  mov     r9d, edi; char *
0x1800139c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800139cb  mov     rcx, [rbp+arg_0]
0x1800139cf  test    rcx, rcx
0x1800139d2  jz      short loc_18001396F
0x1800139d4  mov     [rbp+Binding], rcx
0x1800139d8  lea     rcx, [rbp+Binding]; Binding
0x1800139dc  call    cs:__imp_RpcBindingFree
0x1800139e2  jmp     short loc_18001396F
0x1800139e4  cmp     qword ptr [rbx+8], 0
0x1800139e9  jz      short loc_180013A15
0x1800139eb  lea     rax, [rbp+arg_0]
0x1800139ef  mov     [rbp+var_8], rbx
0x1800139f3  lea     rcx, [rbp+var_10]
0x1800139f7  mov     [rbp+var_10], rax
0x1800139fb  call    _CMidi2MidiSrv__Shutdown____29____lambda_1___operator__
0x180013a00  mov     edi, eax
0x180013a02  test    eax, eax
0x180013a04  jns     short loc_180013A0D
0x180013a06  mov     edx, 0FBh
0x180013a0b  jmp     short loc_1800139B8
0x180013a0d  mov     qword ptr [rbx+8], 0
0x180013a15  mov     rax, [rbp+arg_0]
0x180013a19  test    rax, rax
0x180013a1c  jz      short loc_180013A2C
0x180013a1e  lea     rcx, [rbp+Binding]; Binding
0x180013a22  mov     [rbp+Binding], rax
0x180013a26  call    cs:__imp_RpcBindingFree
0x180013a2c  xor     eax, eax
0x180013a2e  add     rsp, 40h
0x180013a32  pop     rdi
0x180013a33  pop     rbx
0x180013a34  pop     rbp
0x180013a35  retn
```
