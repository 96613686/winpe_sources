# CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18000ec98`
- end: `0x18000ee47`
- name: `?DeleteDeviceEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180017670`

## callees

- `0x1800016dc`
- `0x1800038f0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x18000ec98`
- `0x1800117d8`
- `0x180021010`

## string_xrefs

- `0x18000ecd0`: `CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rax
  unsigned int v8; // edi
  __int64 v9; // rax
  _QWORD *v10; // rdx
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-49h]
  int v19[2]; // [rsp+40h] [rbp-29h] BYREF
  int v20[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v21; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v23; // [rsp+78h] [rbp+Fh]
  _QWORD v24[4]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v23 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    if ( a2[3] <= 7u )
      v7 = a2;
    else
      v7 = (_QWORD *)*a2;
    *(_QWORD *)v19 = v7;
    v21 = a1;
    *(_QWORD *)v20 = "CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)byte_180026831,
      v5,
      v6,
      (__int64)v20,
      (__int64)&v21,
      (__int64)v19);
  }
  if ( *(_QWORD *)(a1 + 64) )
  {
    v9 = std::wstring::wstring(v22, a2);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v24, v9);
    if ( v24[2] )
    {
      v10 = v24;
      if ( v24[3] > 7u )
        v10 = (_QWORD *)v24[0];
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 64) + 72LL))(*(_QWORD *)(a1 + 64), v10);
      v8 = v11;
      if ( v11 >= 0 )
      {
        std::wstring::~wstring(v24);
        std::wstring::~wstring(a2);
        return 0;
      }
      v12 = (unsigned int)v11;
      v13 = 131;
    }
    else
    {
      v15 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v15 > 2u )
      {
        *(_QWORD *)v20 = L"could not find instanceId property for device";
        v21 = a1;
        *(_QWORD *)v19 = "CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v15,
          (unsigned int)&word_1800267FE,
          v16,
          v17,
          (__int64)v19,
          (__int64)&v21,
          (__int64)v20);
      }
      v8 = -2147024809;
      v12 = 2147942487LL;
      v13 = 144;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)v12,
      v18);
    std::wstring::~wstring(v24);
  }
  else
  {
    v8 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)0x80004003LL,
      v18);
  }
  std::wstring::~wstring(a2);
  return v8;
}

```

## disassembly

```asm
0x18000ec98  mov     [rsp-8+arg_10], rbx
0x18000ec9d  push    rbp
0x18000ec9e  push    rdi
0x18000ec9f  push    r14
0x18000eca1  lea     rbp, [rsp-47h]
0x18000eca6  sub     rsp, 0B0h
0x18000ecad  mov     rax, cs:__security_cookie
0x18000ecb4  xor     rax, rsp
0x18000ecb7  mov     [rbp+57h+var_20], rax
0x18000ecbb  mov     rbx, rdx
0x18000ecbe  mov     rdi, rcx
0x18000ecc1  mov     [rbp+57h+var_48], rdx
0x18000ecc5  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000ecca  mov     rcx, [rax+8]
0x18000ecce  mov     eax, [rcx]
0x18000ecd0  lea     r14, aCmidi2virtualm_13; "CMidi2VirtualMidiEndpointManager::Delet"...
0x18000ecd7  cmp     eax, 4
0x18000ecda  jbe     short loc_18000ED1E
0x18000ecdc  cmp     qword ptr [rbx+18h], 7
0x18000ece1  jbe     short loc_18000ECE8
0x18000ece3  mov     rax, [rbx]
0x18000ece6  jmp     short loc_18000ECEB
0x18000ece8  mov     rax, rbx
0x18000eceb  mov     qword ptr [rbp+57h+var_80], rax
0x18000ecef  mov     [rbp+57h+var_70], rdi
0x18000ecf3  mov     qword ptr [rbp+57h+var_78], r14
0x18000ecf7  lea     rax, [rbp+57h+var_80]
0x18000ecfb  mov     [rsp+0C0h+var_90], rax
0x18000ed00  lea     rax, [rbp+57h+var_70]
0x18000ed04  mov     [rsp+0C0h+var_98], rax
0x18000ed09  lea     rax, [rbp+57h+var_78]
0x18000ed0d  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000ed12  lea     rdx, byte_180026831
0x18000ed19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ed1e  cmp     qword ptr [rdi+40h], 0
0x18000ed23  jnz     short loc_18000ED47
0x18000ed25  mov     rcx, [rbp+5Fh]; this
0x18000ed29  mov     edi, 80004003h
0x18000ed2e  mov     r9d, edi; char *
0x18000ed31  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000ed38  mov     edx, 96h; void *
0x18000ed3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed42  jmp     loc_18000EE1D
0x18000ed47  mov     rdx, rbx
0x18000ed4a  lea     rcx, [rbp+57h+var_68]
0x18000ed4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ed53  mov     rdx, rax
0x18000ed56  lea     rcx, [rbp+57h+var_40]
0x18000ed5a  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000ed5f  nop
0x18000ed60  cmp     [rbp+57h+var_30], 0
0x18000ed65  jz      short loc_18000EDAB
0x18000ed67  mov     rcx, [rdi+40h]
0x18000ed6b  mov     rax, [rcx]
0x18000ed6e  lea     rdx, [rbp+57h+var_40]
0x18000ed72  cmp     [rbp+57h+var_28], 7
0x18000ed77  cmova   rdx, [rbp+57h+var_40]
0x18000ed7c  mov     rax, [rax+48h]
0x18000ed80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed85  mov     edi, eax
0x18000ed87  test    eax, eax
0x18000ed89  jns     short loc_18000ED95
0x18000ed8b  mov     r9d, eax
0x18000ed8e  mov     edx, 83h
0x18000ed93  jmp     short loc_18000EE02
0x18000ed95  lea     rcx, [rbp+57h+var_40]
0x18000ed99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed9e  nop
0x18000ed9f  mov     rcx, rbx
0x18000eda2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eda7  xor     eax, eax
0x18000eda9  jmp     short loc_18000EE27
0x18000edab  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000edb0  mov     rcx, [rax+8]
0x18000edb4  mov     eax, [rcx]
0x18000edb6  cmp     eax, 2
0x18000edb9  jbe     short loc_18000EDF5
0x18000edbb  lea     rax, aCouldNotFindIn_0; "could not find instanceId property for "...
0x18000edc2  mov     qword ptr [rbp+57h+var_78], rax
0x18000edc6  mov     [rbp+57h+var_70], rdi
0x18000edca  mov     qword ptr [rbp+57h+var_80], r14
0x18000edce  lea     rax, [rbp+57h+var_78]
0x18000edd2  mov     [rsp+0C0h+var_90], rax
0x18000edd7  lea     rax, [rbp+57h+var_70]
0x18000eddb  mov     [rsp+0C0h+var_98], rax
0x18000ede0  lea     rax, [rbp+57h+var_80]
0x18000ede4  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000ede9  lea     rdx, word_1800267FE
0x18000edf0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000edf5  mov     edi, 80070057h
0x18000edfa  mov     r9d, edi; char *
0x18000edfd  mov     edx, 90h; void *
0x18000ee02  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000ee09  mov     rcx, [rbp+5Fh]; this
0x18000ee0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee12  nop
0x18000ee13  lea     rcx, [rbp+57h+var_40]
0x18000ee17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ee1c  nop
0x18000ee1d  mov     rcx, rbx
0x18000ee20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ee25  mov     eax, edi
0x18000ee27  mov     rcx, [rbp+57h+var_20]
0x18000ee2b  xor     rcx, rsp; StackCookie
0x18000ee2e  call    __security_check_cookie
0x18000ee33  mov     rbx, [rsp+0C0h+arg_10]
0x18000ee3b  add     rsp, 0B0h
0x18000ee42  pop     r14
0x18000ee44  pop     rdi
0x18000ee45  pop     rbp
0x18000ee46  retn
```
