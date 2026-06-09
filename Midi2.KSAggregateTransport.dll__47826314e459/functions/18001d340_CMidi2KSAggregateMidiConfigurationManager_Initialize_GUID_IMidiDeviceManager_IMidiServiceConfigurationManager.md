# CMidi2KSAggregateMidiConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x18001d340`
- end: `0x18001d46c`
- name: `?Initialize@CMidi2KSAggregateMidiConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x18000206c`
- `0x18000b394`
- `0x1800117d8`
- `0x18001d340`
- `0x18005e010`

## string_xrefs

- `0x18001d370`: `CMidi2KSAggregateMidiConfigurationManager::Initialize`
- `0x18001d3e5`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001d442`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSAggregateMidiConfigurationManager::Initialize(
        CMidi2KSAggregateMidiConfigurationManager *this,
        struct _GUID *a2,
        __int64 (__fastcall ***a3)(struct IMidiDeviceManager *, GUID *, char *),
        __int64 (__fastcall ***a4)(struct IMidiServiceConfigurationManager *, GUID *, char *))
{
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 (__fastcall *v10)(struct IMidiDeviceManager *, GUID *, char *); // rbp
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  __int64 (__fastcall *v15)(struct IMidiServiceConfigurationManager *, GUID *, char *); // rdi
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2KSAggregateMidiConfigurationManager *v21; // [rsp+50h] [rbp+8h] BYREF
  const char *v22; // [rsp+60h] [rbp+18h] BYREF

  v7 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v21 = this;
    v22 = "CMidi2KSAggregateMidiConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)&byte_1800890D7,
      v8,
      v9,
      (__int64)&v22,
      (__int64)&v21);
  }
  v10 = **a3;
  v11 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = v10((struct IMidiDeviceManager *)a3, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 40);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v15 = **a4;
    v16 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v17 = v15(
            (struct IMidiServiceConfigurationManager *)a4,
            &GUID_6c21fcda_051b_4f06_8d40_f5bced5957c0,
            (char *)this + 32);
    v18 = v17;
    if ( v17 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
        (const char *)(unsigned int)v17,
        v19);
      return v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
      (const char *)(unsigned int)v12,
      v19);
    return v13;
  }
}

```

## disassembly

```asm
0x18001d340  mov     [rsp+arg_8], rbx
0x18001d345  mov     [rsp+arg_18], rbp
0x18001d34a  push    rsi
0x18001d34b  push    rdi
0x18001d34c  push    r14
0x18001d34e  sub     rsp, 30h
0x18001d352  mov     r14, r9
0x18001d355  mov     rsi, r8
0x18001d358  mov     rbx, rcx
0x18001d35b  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001d360  mov     rcx, [rax+8]
0x18001d364  mov     eax, [rcx]
0x18001d366  cmp     eax, 4
0x18001d369  jbe     short loc_18001D39C
0x18001d36b  mov     [rsp+48h+arg_0], rbx
0x18001d370  lea     rax, aCmidi2ksaggreg_37; "CMidi2KSAggregateMidiConfigurationManag"...
0x18001d377  mov     [rsp+48h+arg_10], rax
0x18001d37c  lea     rax, [rsp+48h+arg_0]
0x18001d381  mov     [rsp+48h+var_20], rax
0x18001d386  lea     rax, [rsp+48h+arg_10]
0x18001d38b  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001d390  lea     rdx, byte_1800890D7
0x18001d397  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001d39c  mov     rax, [rsi]
0x18001d39f  mov     rbp, [rax]
0x18001d3a2  lea     rdi, [rbx+28h]
0x18001d3a6  mov     rcx, [rdi]
0x18001d3a9  mov     qword ptr [rdi], 0
0x18001d3b0  test    rcx, rcx
0x18001d3b3  jz      short loc_18001D3C2
0x18001d3b5  mov     rdx, [rcx]
0x18001d3b8  mov     rax, [rdx+10h]
0x18001d3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c1  nop
0x18001d3c2  mov     r8, rdi
0x18001d3c5  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18001d3cc  mov     rcx, rsi
0x18001d3cf  mov     rax, rbp
0x18001d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d7  mov     edi, eax
0x18001d3d9  test    eax, eax
0x18001d3db  jns     short loc_18001D3FA
0x18001d3dd  mov     rcx, [rsp+48h]; this
0x18001d3e2  mov     r9d, eax; char *
0x18001d3e5  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001d3ec  mov     edx, 22h ; '"'; void *
0x18001d3f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3f6  mov     eax, edi
0x18001d3f8  jmp     short loc_18001D459
0x18001d3fa  mov     rax, [r14]
0x18001d3fd  mov     rdi, [rax]
0x18001d400  mov     rcx, [rbx+20h]
0x18001d404  mov     qword ptr [rbx+20h], 0
0x18001d40c  test    rcx, rcx
0x18001d40f  jz      short loc_18001D41E
0x18001d411  mov     rdx, [rcx]
0x18001d414  mov     rax, [rdx+10h]
0x18001d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d41d  nop
0x18001d41e  lea     r8, [rbx+20h]
0x18001d422  lea     rdx, _GUID_6c21fcda_051b_4f06_8d40_f5bced5957c0
0x18001d429  mov     rcx, r14
0x18001d42c  mov     rax, rdi
0x18001d42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d434  mov     ebx, eax
0x18001d436  test    eax, eax
0x18001d438  jns     short loc_18001D457
0x18001d43a  mov     rcx, [rsp+48h]; this
0x18001d43f  mov     r9d, eax; char *
0x18001d442  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001d449  mov     edx, 24h ; '$'; void *
0x18001d44e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d453  mov     eax, ebx
0x18001d455  jmp     short loc_18001D459
0x18001d457  xor     eax, eax
0x18001d459  mov     rbx, [rsp+48h+arg_8]
0x18001d45e  mov     rbp, [rsp+48h+arg_18]
0x18001d463  add     rsp, 30h
0x18001d467  pop     r14
0x18001d469  pop     rdi
0x18001d46a  pop     rsi
0x18001d46b  retn
```
