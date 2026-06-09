# CMidi2KSMidiConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x180022690`
- end: `0x1800227bc`
- name: `?Initialize@CMidi2KSMidiConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CMidi2KSMidiConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180001918`
- `0x18000a814`
- `0x18000db18`
- `0x180022690`
- `0x180041010`

## string_xrefs

- `0x1800226c0`: `CMidi2KSMidiConfigurationManager::Initialize`
- `0x180022735`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`
- `0x180022792`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSMidiConfigurationManager::Initialize(
        CMidi2KSMidiConfigurationManager *this,
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
  CMidi2KSMidiConfigurationManager *v21; // [rsp+50h] [rbp+8h] BYREF
  const char *v22; // [rsp+60h] [rbp+18h] BYREF

  v7 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v21 = this;
    v22 = "CMidi2KSMidiConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)&word_180068E8E,
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
        (void *)0x22,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
        (const char *)(unsigned int)v17,
        v19);
      return v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
      (const char *)(unsigned int)v12,
      v19);
    return v13;
  }
}

```

## disassembly

```asm
0x180022690  mov     [rsp+arg_8], rbx
0x180022695  mov     [rsp+arg_18], rbp
0x18002269a  push    rsi
0x18002269b  push    rdi
0x18002269c  push    r14
0x18002269e  sub     rsp, 30h
0x1800226a2  mov     r14, r9
0x1800226a5  mov     rsi, r8
0x1800226a8  mov     rbx, rcx
0x1800226ab  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x1800226b0  mov     rcx, [rax+8]
0x1800226b4  mov     eax, [rcx]
0x1800226b6  cmp     eax, 4
0x1800226b9  jbe     short loc_1800226EC
0x1800226bb  mov     [rsp+48h+arg_0], rbx
0x1800226c0  lea     rax, aCmidi2ksmidico; "CMidi2KSMidiConfigurationManager::Initi"...
0x1800226c7  mov     [rsp+48h+arg_10], rax
0x1800226cc  lea     rax, [rsp+48h+arg_0]
0x1800226d1  mov     [rsp+48h+var_20], rax
0x1800226d6  lea     rax, [rsp+48h+arg_10]
0x1800226db  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800226e0  lea     rdx, word_180068E8E
0x1800226e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800226ec  mov     rax, [rsi]
0x1800226ef  mov     rbp, [rax]
0x1800226f2  lea     rdi, [rbx+28h]
0x1800226f6  mov     rcx, [rdi]
0x1800226f9  mov     qword ptr [rdi], 0
0x180022700  test    rcx, rcx
0x180022703  jz      short loc_180022712
0x180022705  mov     rdx, [rcx]
0x180022708  mov     rax, [rdx+10h]
0x18002270c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022711  nop
0x180022712  mov     r8, rdi
0x180022715  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18002271c  mov     rcx, rsi
0x18002271f  mov     rax, rbp
0x180022722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022727  mov     edi, eax
0x180022729  test    eax, eax
0x18002272b  jns     short loc_18002274A
0x18002272d  mov     rcx, [rsp+48h]; this
0x180022732  mov     r9d, eax; char *
0x180022735  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\kstransport\\"...
0x18002273c  mov     edx, 20h ; ' '; void *
0x180022741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022746  mov     eax, edi
0x180022748  jmp     short loc_1800227A9
0x18002274a  mov     rax, [r14]
0x18002274d  mov     rdi, [rax]
0x180022750  mov     rcx, [rbx+20h]
0x180022754  mov     qword ptr [rbx+20h], 0
0x18002275c  test    rcx, rcx
0x18002275f  jz      short loc_18002276E
0x180022761  mov     rdx, [rcx]
0x180022764  mov     rax, [rdx+10h]
0x180022768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002276d  nop
0x18002276e  lea     r8, [rbx+20h]
0x180022772  lea     rdx, _GUID_6c21fcda_051b_4f06_8d40_f5bced5957c0
0x180022779  mov     rcx, r14
0x18002277c  mov     rax, rdi
0x18002277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022784  mov     ebx, eax
0x180022786  test    eax, eax
0x180022788  jns     short loc_1800227A7
0x18002278a  mov     rcx, [rsp+48h]; this
0x18002278f  mov     r9d, eax; char *
0x180022792  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\kstransport\\"...
0x180022799  mov     edx, 22h ; '"'; void *
0x18002279e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227a3  mov     eax, ebx
0x1800227a5  jmp     short loc_1800227A9
0x1800227a7  xor     eax, eax
0x1800227a9  mov     rbx, [rsp+48h+arg_8]
0x1800227ae  mov     rbp, [rsp+48h+arg_18]
0x1800227b3  add     rsp, 30h
0x1800227b7  pop     r14
0x1800227b9  pop     rdi
0x1800227ba  pop     rsi
0x1800227bb  retn
```
