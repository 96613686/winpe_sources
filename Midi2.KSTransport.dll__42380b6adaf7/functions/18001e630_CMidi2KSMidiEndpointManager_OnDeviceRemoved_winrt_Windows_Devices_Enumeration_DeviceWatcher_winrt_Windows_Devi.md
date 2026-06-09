# CMidi2KSMidiEndpointManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x18001e630`
- end: `0x18001e82e`
- name: `?OnDeviceRemoved@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001c20`
- `0x180004434`
- `0x1800052fc`
- `0x180005374`
- `0x18000c948`
- `0x18000d1c0`
- `0x18000db18`
- `0x180018884`
- `0x18001acd0`
- `0x18001e630`
- `0x18001fdb0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e71f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e71f`

## string_xrefs

- `0x18001e693`: `Device removed`
- `0x18001e6a2`: `CMidi2KSMidiEndpointManager::OnDeviceRemoved`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidi2KSMidiEndpointManager::OnDeviceRemoved(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _DWORD *v6; // rbx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  const wchar_t *v10; // rax
  void *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  _MIDI_PIN_INFO **v14; // rbx
  _MIDI_PIN_INFO **v15; // rsi
  int v16; // eax
  _MIDI_PIN_INFO **v17; // r13
  _MIDI_PIN_INFO **i; // rsi
  _MIDI_PIN_INFO *v19; // rax
  _MIDI_PIN_INFO *v20; // r15
  __int64 v21; // rax
  void *v22; // rbx
  int v24; // [rsp+20h] [rbp-50h]
  const wchar_t *v25; // [rsp+40h] [rbp-30h] BYREF
  __int64 v26; // [rsp+48h] [rbp-28h] BYREF
  const char *v27; // [rsp+50h] [rbp-20h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  const wchar_t *v30; // [rsp+C8h] [rbp+58h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v7 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
           a3,
           lpMem);
    v10 = *(_QWORD *)v7 ? *(const wchar_t **)(*(_QWORD *)v7 + 16LL) : &S1;
    v30 = v10;
    v25 = L"Device removed";
    v26 = a1;
    v27 = "CMidi2KSMidiEndpointManager::OnDeviceRemoved";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)&word_180068876,
      v8,
      v9,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v30);
    v11 = lpMem[0];
    if ( lpMem[0] )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
      }
    }
  }
  while ( 1 )
  {
    v14 = *(_MIDI_PIN_INFO ***)(a1 + 32);
    lpMem[0] = a3;
    lpMem[1] = (LPVOID)a1;
    v15 = *(_MIDI_PIN_INFO ***)(a1 + 40);
    while ( v14 != v15
         && !(unsigned __int8)CMidi2KSMidiEndpointManager::OnDeviceRemoved_::_9_::_lambda_1_::operator()(lpMem, v14) )
      ++v14;
    if ( v14 == *(_MIDI_PIN_INFO ***)(a1 + 40) )
      break;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 72LL))(*(_QWORD *)(a1 + 16));
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x373,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiendpointmanager.cpp",
        (const char *)(unsigned int)v16,
        v24);
    v17 = *(_MIDI_PIN_INFO ***)(a1 + 40);
    for ( i = v14 + 1; i != v17; ++i )
    {
      v19 = *i;
      *i = 0;
      v20 = *v14;
      *v14 = v19;
      if ( v20 )
      {
        _MIDI_PIN_INFO::~_MIDI_PIN_INFO(v20);
        operator delete(v20);
      }
      ++v14;
    }
    v21 = *(_QWORD *)(a1 + 40);
    v22 = *(void **)(v21 - 8);
    if ( v22 )
    {
      _MIDI_PIN_INFO::~_MIDI_PIN_INFO(*(_MIDI_PIN_INFO **)(v21 - 8));
      operator delete(v22);
    }
    *(_QWORD *)(a1 + 40) -= 8LL;
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x18001e630  mov     [rsp-38h+arg_0], rbx
0x18001e635  mov     [rsp-38h+arg_10], r8
0x18001e63a  mov     [rsp-38h+arg_8], rdx
0x18001e63f  push    rbp
0x18001e640  push    rsi
0x18001e641  push    rdi
0x18001e642  push    r12
0x18001e644  push    r13
0x18001e646  push    r14
0x18001e648  push    r15
0x18001e64a  mov     rbp, rsp
0x18001e64d  sub     rsp, 70h
0x18001e651  mov     r14, r8
0x18001e654  mov     r12, rdx
0x18001e657  mov     rdi, rcx
0x18001e65a  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18001e65f  mov     rbx, [rax+8]
0x18001e663  mov     eax, [rbx]
0x18001e665  cmp     eax, 4
0x18001e668  jbe     loc_18001E709
0x18001e66e  lea     rdx, [rbp+lpMem]
0x18001e672  mov     rcx, r14
0x18001e675  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x18001e67a  mov     rcx, [rax]
0x18001e67d  test    rcx, rcx
0x18001e680  jz      short loc_18001E688
0x18001e682  mov     rax, [rcx+10h]
0x18001e686  jmp     short loc_18001E68F
0x18001e688  lea     rax, S1
0x18001e68f  mov     [rbp+arg_18], rax
0x18001e693  lea     rax, aDeviceRemoved; "Device removed"
0x18001e69a  mov     [rbp+var_30], rax
0x18001e69e  mov     [rbp+var_28], rdi
0x18001e6a2  lea     rax, aCmidi2ksmidien_2; "CMidi2KSMidiEndpointManager::OnDeviceRe"...
0x18001e6a9  mov     [rbp+var_20], rax
0x18001e6ad  lea     rax, [rbp+arg_18]
0x18001e6b1  mov     [rsp+70h+var_38], rax
0x18001e6b6  lea     rax, [rbp+var_30]
0x18001e6ba  mov     [rsp+70h+var_40], rax
0x18001e6bf  lea     rax, [rbp+var_28]
0x18001e6c3  mov     [rsp+70h+var_48], rax
0x18001e6c8  lea     rax, [rbp+var_20]
0x18001e6cc  mov     [rsp+70h+var_50], rax
0x18001e6d1  lea     rdx, word_180068876
0x18001e6d8  mov     rcx, rbx
0x18001e6db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001e6e0  mov     rbx, [rbp+lpMem]
0x18001e6e4  test    rbx, rbx
0x18001e6e7  jz      short loc_18001E709
0x18001e6e9  or      eax, 0FFFFFFFFh
0x18001e6ec  lock xadd [rbx+18h], eax
0x18001e6f1  sub     eax, 1
0x18001e6f4  jnz     short loc_18001E71B
0x18001e6f6  nop
0x18001e6f7  call    WINRT_IMPL_GetProcessHeap
0x18001e6fc  mov     rcx, rax; hHeap
0x18001e6ff  mov     r8, rbx; lpMem
0x18001e702  xor     edx, edx; dwFlags
0x18001e704  call    WINRT_IMPL_HeapFree
0x18001e709  mov     rbx, [rdi+20h]
0x18001e70d  mov     [rbp+lpMem], r14
0x18001e711  mov     [rbp+var_8], rdi
0x18001e715  mov     rsi, [rdi+28h]
0x18001e719  jmp     short loc_18001E73A
0x18001e71b  test    eax, eax
0x18001e71d  jns     short loc_18001E709
0x18001e71f  call    cs:__imp_abort
0x18001e726  mov     rdx, rbx
0x18001e729  lea     rcx, [rbp+lpMem]
0x18001e72d  call    _CMidi2KSMidiEndpointManager__OnDeviceRemoved____9____lambda_1___operator__
0x18001e732  test    al, al
0x18001e734  jnz     short loc_18001E73F
0x18001e736  add     rbx, 8
0x18001e73a  cmp     rbx, rsi
0x18001e73d  jnz     short loc_18001E726
0x18001e73f  cmp     rbx, [rdi+28h]
0x18001e743  jz      loc_18001E7F6
0x18001e749  mov     rcx, [rdi+10h]
0x18001e74d  mov     rax, [rcx]
0x18001e750  mov     r8, [rax+48h]
0x18001e754  mov     rdx, [rbx]
0x18001e757  add     rdx, 20h ; ' '
0x18001e75b  cmp     qword ptr [rdx+18h], 7
0x18001e760  jbe     short loc_18001E765
0x18001e762  mov     rdx, [rdx]
0x18001e765  mov     rax, r8
0x18001e768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e76d  test    eax, eax
0x18001e76f  jns     short loc_18001E789
0x18001e771  mov     rcx, [rbp+38h]; this
0x18001e775  mov     r9d, eax; char *
0x18001e778  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\kstransport\\"...
0x18001e77f  mov     edx, 373h; void *
0x18001e784  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e789  mov     r13, [rdi+28h]
0x18001e78d  lea     rsi, [rbx+8]
0x18001e791  jmp     short loc_18001E7C5
0x18001e793  mov     rax, [rsi]
0x18001e796  mov     qword ptr [rsi], 0
0x18001e79d  mov     r15, [rbx]
0x18001e7a0  mov     [rbx], rax
0x18001e7a3  test    r15, r15
0x18001e7a6  jz      short loc_18001E7BD
0x18001e7a8  mov     rcx, r15; this
0x18001e7ab  call    ??1_MIDI_PIN_INFO@@QEAA@XZ; _MIDI_PIN_INFO::~_MIDI_PIN_INFO(void)
0x18001e7b0  mov     edx, 148h
0x18001e7b5  mov     rcx, r15; Block
0x18001e7b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e7bd  add     rbx, 8
0x18001e7c1  add     rsi, 8
0x18001e7c5  cmp     rsi, r13
0x18001e7c8  jnz     short loc_18001E793
0x18001e7ca  mov     rax, [rdi+28h]
0x18001e7ce  mov     rbx, [rax-8]
0x18001e7d2  test    rbx, rbx
0x18001e7d5  jz      short loc_18001E7EC
0x18001e7d7  mov     rcx, rbx; this
0x18001e7da  call    ??1_MIDI_PIN_INFO@@QEAA@XZ; _MIDI_PIN_INFO::~_MIDI_PIN_INFO(void)
0x18001e7df  mov     edx, 148h
0x18001e7e4  mov     rcx, rbx; Block
0x18001e7e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e7ec  add     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFF8h
0x18001e7f1  jmp     loc_18001E709
0x18001e7f6  cmp     qword ptr [r12], 0
0x18001e7fb  jz      short loc_18001E806
0x18001e7fd  mov     rcx, r12
0x18001e800  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e805  nop
0x18001e806  cmp     qword ptr [r14], 0
0x18001e80a  jz      short loc_18001E814
0x18001e80c  mov     rcx, r14
0x18001e80f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e814  xor     eax, eax
0x18001e816  mov     rbx, [rsp+70h+arg_0]
0x18001e81e  add     rsp, 70h
0x18001e822  pop     r15
0x18001e824  pop     r14
0x18001e826  pop     r13
0x18001e828  pop     r12
0x18001e82a  pop     rdi
0x18001e82b  pop     rsi
0x18001e82c  pop     rbp
0x18001e82d  retn
```
