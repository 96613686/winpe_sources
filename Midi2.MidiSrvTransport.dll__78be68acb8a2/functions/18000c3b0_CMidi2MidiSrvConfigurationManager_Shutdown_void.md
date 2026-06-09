# CMidi2MidiSrvConfigurationManager::Shutdown(void)

- ea: `0x18000c3b0`
- end: `0x18000c478`
- name: `?Shutdown@CMidi2MidiSrvConfigurationManager@@UEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(CMidi2MidiSrvConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c3b0`
- `0x18000d190`
- `0x1800138f8`

## string_xrefs

- `0x18000c417`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`
- `0x18000c3cd`: `CMidi2MidiSrvConfigurationManager::Shutdown`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvConfigurationManager::Shutdown(CMidi2MidiSrv **this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  CMidi2MidiSrv *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  CMidiXProc **v9; // rbx
  CMidiXProc *v10; // rdi
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CMidi2MidiSrvConfigurationManager *v13; // [rsp+40h] [rbp+8h] BYREF
  const char *v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v13 = (CMidi2MidiSrvConfigurationManager *)this;
    v14 = "CMidi2MidiSrvConfigurationManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)&byte_18001A03F,
      v3,
      v4,
      (__int64)&v14,
      (__int64)&v13);
  }
  v5 = this[3];
  if ( v5 )
  {
    v6 = CMidi2MidiSrv::Shutdown(v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
        (const char *)(unsigned int)v6,
        v11);
      return v7;
    }
    v9 = (CMidiXProc **)this[3];
    this[3] = 0;
    if ( v9 )
    {
      v10 = v9[2];
      if ( v10 )
      {
        CMidiXProc::~CMidiXProc(v9[2]);
        operator delete(v10);
      }
      operator delete(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c3b0  mov     [rsp+arg_10], rbx
0x18000c3b5  push    rdi
0x18000c3b6  sub     rsp, 30h
0x18000c3ba  mov     rdi, rcx
0x18000c3bd  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c3c2  mov     rcx, [rax+8]
0x18000c3c6  mov     eax, [rcx]
0x18000c3c8  cmp     eax, 4
0x18000c3cb  jbe     short loc_18000C3FE
0x18000c3cd  lea     rax, aCmidi2midisrvc_3; "CMidi2MidiSrvConfigurationManager::Shut"...
0x18000c3d4  mov     [rsp+38h+arg_0], rdi
0x18000c3d9  mov     [rsp+38h+arg_8], rax
0x18000c3de  lea     rdx, byte_18001A03F
0x18000c3e5  lea     rax, [rsp+38h+arg_0]
0x18000c3ea  mov     [rsp+38h+var_10], rax
0x18000c3ef  lea     rax, [rsp+38h+arg_8]
0x18000c3f4  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000c3f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c3fe  mov     rcx, [rdi+18h]; this
0x18000c402  test    rcx, rcx
0x18000c405  jz      short loc_18000C46B
0x18000c407  call    ?Shutdown@CMidi2MidiSrv@@QEAAJXZ; CMidi2MidiSrv::Shutdown(void)
0x18000c40c  mov     ebx, eax
0x18000c40e  test    eax, eax
0x18000c410  jns     short loc_18000C42F
0x18000c412  mov     rcx, [rsp+38h]; this
0x18000c417  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c41e  mov     r9d, eax; char *
0x18000c421  mov     edx, 7Bh ; '{'; void *
0x18000c426  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c42b  mov     eax, ebx
0x18000c42d  jmp     short loc_18000C46D
0x18000c42f  mov     rbx, [rdi+18h]
0x18000c433  mov     qword ptr [rdi+18h], 0
0x18000c43b  test    rbx, rbx
0x18000c43e  jz      short loc_18000C46B
0x18000c440  mov     rdi, [rbx+10h]
0x18000c444  test    rdi, rdi
0x18000c447  jz      short loc_18000C45E
0x18000c449  mov     rcx, rdi; this
0x18000c44c  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000c451  mov     edx, 90h
0x18000c456  mov     rcx, rdi; Block
0x18000c459  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c45e  mov     edx, 20h ; ' '
0x18000c463  mov     rcx, rbx; Block
0x18000c466  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c46b  xor     eax, eax
0x18000c46d  mov     rbx, [rsp+38h+arg_10]
0x18000c472  add     rsp, 30h
0x18000c476  pop     rdi
0x18000c477  retn
```
