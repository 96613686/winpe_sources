# CMidi2VirtualMidiConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x18001d080`
- end: `0x18001d17d`
- name: `?Initialize@CMidi2VirtualMidiConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800017d0`
- `0x180009784`
- `0x18000b5f8`
- `0x18001d080`
- `0x180021010`

## string_xrefs

- `0x18001d0b0`: `CMidi2VirtualMidiConfigurationManager::Initialize`
- `0x18001d0ee`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidiconfigurationmanager.cpp`
- `0x18001d14a`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidiconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2VirtualMidiConfigurationManager::Initialize(
        CMidi2VirtualMidiConfigurationManager *this,
        struct _GUID *a2,
        __int64 (__fastcall ***a3)(struct IMidiDeviceManager *, GUID *, char *),
        struct IMidiServiceConfigurationManager *a4)
{
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 (__fastcall *v11)(struct IMidiDeviceManager *, GUID *, char *); // r14
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-38h]
  int v16[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CMidi2VirtualMidiConfigurationManager *v18; // [rsp+70h] [rbp+18h] BYREF

  v7 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v18 = this;
    *(_QWORD *)v16 = "CMidi2VirtualMidiConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)&byte_1800273E7,
      v8,
      v9,
      (__int64)v16,
      (__int64)&v18);
  }
  if ( a3 )
  {
    v11 = **a3;
    v12 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = v11((struct IMidiDeviceManager *)a3, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 16);
    v14 = v13;
    if ( v13 >= 0 )
    {
      *(struct _GUID *)((char *)this + 24) = *a2;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiconfigurationmanager.cpp",
        (const char *)(unsigned int)v13,
        v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v15);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001d080  mov     [rsp+arg_0], rbx
0x18001d085  mov     [rsp+arg_8], rbp
0x18001d08a  push    rsi
0x18001d08b  push    rdi
0x18001d08c  push    r14
0x18001d08e  sub     rsp, 40h
0x18001d092  mov     rsi, r8
0x18001d095  mov     rbp, rdx
0x18001d098  mov     rbx, rcx
0x18001d09b  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001d0a0  mov     rcx, [rax+8]
0x18001d0a4  mov     eax, [rcx]
0x18001d0a6  cmp     eax, 4
0x18001d0a9  jbe     short loc_18001D0DC
0x18001d0ab  mov     [rsp+58h+arg_10], rbx
0x18001d0b0  lea     rax, aCmidi2virtualm_8; "CMidi2VirtualMidiConfigurationManager::"...
0x18001d0b7  mov     qword ptr [rsp+58h+var_28], rax
0x18001d0bc  lea     rax, [rsp+58h+arg_10]
0x18001d0c1  mov     [rsp+58h+var_30], rax
0x18001d0c6  lea     rax, [rsp+58h+var_28]
0x18001d0cb  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001d0d0  lea     rdx, byte_1800273E7
0x18001d0d7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001d0dc  test    rsi, rsi
0x18001d0df  jnz     short loc_18001D101
0x18001d0e1  mov     rcx, [rsp+58h]; this
0x18001d0e6  mov     ebx, 80070057h
0x18001d0eb  mov     r9d, ebx; char *
0x18001d0ee  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001d0f5  lea     edx, [rsi+1Fh]; void *
0x18001d0f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0fd  mov     eax, ebx
0x18001d0ff  jmp     short loc_18001D16A
0x18001d101  mov     rax, [rsi]
0x18001d104  mov     r14, [rax]
0x18001d107  lea     rdi, [rbx+10h]
0x18001d10b  mov     rcx, [rdi]
0x18001d10e  mov     qword ptr [rdi], 0
0x18001d115  test    rcx, rcx
0x18001d118  jz      short loc_18001D127
0x18001d11a  mov     rdx, [rcx]
0x18001d11d  mov     rax, [rdx+10h]
0x18001d121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d126  nop
0x18001d127  mov     r8, rdi
0x18001d12a  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18001d131  mov     rcx, rsi
0x18001d134  mov     rax, r14
0x18001d137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d13c  mov     edi, eax
0x18001d13e  test    eax, eax
0x18001d140  jns     short loc_18001D15F
0x18001d142  mov     rcx, [rsp+58h]; this
0x18001d147  mov     r9d, eax; char *
0x18001d14a  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001d151  mov     edx, 20h ; ' '; void *
0x18001d156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d15b  mov     eax, edi
0x18001d15d  jmp     short loc_18001D16A
0x18001d15f  movups  xmm0, xmmword ptr [rbp+0]
0x18001d163  movdqu  xmmword ptr [rbx+18h], xmm0
0x18001d168  xor     eax, eax
0x18001d16a  mov     rbx, [rsp+58h+arg_0]
0x18001d16f  mov     rbp, [rsp+58h+arg_8]
0x18001d174  add     rsp, 40h
0x18001d178  pop     r14
0x18001d17a  pop     rdi
0x18001d17b  pop     rsi
0x18001d17c  retn
```
