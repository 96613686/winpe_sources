# CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18000eae0`
- end: `0x18000ec8f`
- name: `?DeleteClientEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x18000eae0`
- `0x1800117d8`
- `0x180021010`

## string_xrefs

- `0x18000eb18`: `CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint(__int64 a1, _QWORD *a2)
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
    *(_QWORD *)v20 = "CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)&dword_1800268A4,
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
      v13 = 83;
    }
    else
    {
      v15 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v15 > 2u )
      {
        *(_QWORD *)v20 = L"could not find instanceId property for client";
        v21 = a1;
        *(_QWORD *)v19 = "CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v15,
          (unsigned int)byte_180026871,
          v16,
          v17,
          (__int64)v19,
          (__int64)&v21,
          (__int64)v20);
      }
      v8 = -2147024809;
      v12 = 2147942487LL;
      v13 = 96;
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
      (void *)0x66,
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
0x18000eae0  mov     [rsp-8+arg_10], rbx
0x18000eae5  push    rbp
0x18000eae6  push    rdi
0x18000eae7  push    r14
0x18000eae9  lea     rbp, [rsp-47h]
0x18000eaee  sub     rsp, 0B0h
0x18000eaf5  mov     rax, cs:__security_cookie
0x18000eafc  xor     rax, rsp
0x18000eaff  mov     [rbp+57h+var_20], rax
0x18000eb03  mov     rbx, rdx
0x18000eb06  mov     rdi, rcx
0x18000eb09  mov     [rbp+57h+var_48], rdx
0x18000eb0d  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000eb12  mov     rcx, [rax+8]
0x18000eb16  mov     eax, [rcx]
0x18000eb18  lea     r14, aCmidi2virtualm; "CMidi2VirtualMidiEndpointManager::Delet"...
0x18000eb1f  cmp     eax, 4
0x18000eb22  jbe     short loc_18000EB66
0x18000eb24  cmp     qword ptr [rbx+18h], 7
0x18000eb29  jbe     short loc_18000EB30
0x18000eb2b  mov     rax, [rbx]
0x18000eb2e  jmp     short loc_18000EB33
0x18000eb30  mov     rax, rbx
0x18000eb33  mov     qword ptr [rbp+57h+var_80], rax
0x18000eb37  mov     [rbp+57h+var_70], rdi
0x18000eb3b  mov     qword ptr [rbp+57h+var_78], r14
0x18000eb3f  lea     rax, [rbp+57h+var_80]
0x18000eb43  mov     [rsp+0C0h+var_90], rax
0x18000eb48  lea     rax, [rbp+57h+var_70]
0x18000eb4c  mov     [rsp+0C0h+var_98], rax
0x18000eb51  lea     rax, [rbp+57h+var_78]
0x18000eb55  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000eb5a  lea     rdx, dword_1800268A4
0x18000eb61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000eb66  cmp     qword ptr [rdi+40h], 0
0x18000eb6b  jnz     short loc_18000EB8F
0x18000eb6d  mov     rcx, [rbp+5Fh]; this
0x18000eb71  mov     edi, 80004003h
0x18000eb76  mov     r9d, edi; char *
0x18000eb79  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000eb80  mov     edx, 66h ; 'f'; void *
0x18000eb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb8a  jmp     loc_18000EC65
0x18000eb8f  mov     rdx, rbx
0x18000eb92  lea     rcx, [rbp+57h+var_68]
0x18000eb96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000eb9b  mov     rdx, rax
0x18000eb9e  lea     rcx, [rbp+57h+var_40]
0x18000eba2  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000eba7  nop
0x18000eba8  cmp     [rbp+57h+var_30], 0
0x18000ebad  jz      short loc_18000EBF3
0x18000ebaf  mov     rcx, [rdi+40h]
0x18000ebb3  mov     rax, [rcx]
0x18000ebb6  lea     rdx, [rbp+57h+var_40]
0x18000ebba  cmp     [rbp+57h+var_28], 7
0x18000ebbf  cmova   rdx, [rbp+57h+var_40]
0x18000ebc4  mov     rax, [rax+48h]
0x18000ebc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebcd  mov     edi, eax
0x18000ebcf  test    eax, eax
0x18000ebd1  jns     short loc_18000EBDD
0x18000ebd3  mov     r9d, eax
0x18000ebd6  mov     edx, 53h ; 'S'
0x18000ebdb  jmp     short loc_18000EC4A
0x18000ebdd  lea     rcx, [rbp+57h+var_40]
0x18000ebe1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ebe6  nop
0x18000ebe7  mov     rcx, rbx
0x18000ebea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ebef  xor     eax, eax
0x18000ebf1  jmp     short loc_18000EC6F
0x18000ebf3  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000ebf8  mov     rcx, [rax+8]
0x18000ebfc  mov     eax, [rcx]
0x18000ebfe  cmp     eax, 2
0x18000ec01  jbe     short loc_18000EC3D
0x18000ec03  lea     rax, aCouldNotFindIn; "could not find instanceId property for "...
0x18000ec0a  mov     qword ptr [rbp+57h+var_78], rax
0x18000ec0e  mov     [rbp+57h+var_70], rdi
0x18000ec12  mov     qword ptr [rbp+57h+var_80], r14
0x18000ec16  lea     rax, [rbp+57h+var_78]
0x18000ec1a  mov     [rsp+0C0h+var_90], rax
0x18000ec1f  lea     rax, [rbp+57h+var_70]
0x18000ec23  mov     [rsp+0C0h+var_98], rax
0x18000ec28  lea     rax, [rbp+57h+var_80]
0x18000ec2c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000ec31  lea     rdx, byte_180026871
0x18000ec38  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ec3d  mov     edi, 80070057h
0x18000ec42  mov     r9d, edi; char *
0x18000ec45  mov     edx, 60h ; '`'; void *
0x18000ec4a  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000ec51  mov     rcx, [rbp+5Fh]; this
0x18000ec55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec5a  nop
0x18000ec5b  lea     rcx, [rbp+57h+var_40]
0x18000ec5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ec64  nop
0x18000ec65  mov     rcx, rbx
0x18000ec68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ec6d  mov     eax, edi
0x18000ec6f  mov     rcx, [rbp+57h+var_20]
0x18000ec73  xor     rcx, rsp; StackCookie
0x18000ec76  call    __security_check_cookie
0x18000ec7b  mov     rbx, [rsp+0C0h+arg_10]
0x18000ec83  add     rsp, 0B0h
0x18000ec8a  pop     r14
0x18000ec8c  pop     rdi
0x18000ec8d  pop     rbp
0x18000ec8e  retn
```
