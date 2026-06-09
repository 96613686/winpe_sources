# CMidi2VirtualMidiEndpointManager::CreateParentDevice(void)

- ea: `0x18000e840`
- end: `0x18000eada`
- name: `?CreateParentDevice@CMidi2VirtualMidiEndpointManager@@AEAAJXZ`
- size: `666`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiEndpointManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010b50`

## callees

- `0x1800016dc`
- `0x1800017d0`
- `0x1800038f0`
- `0x1800046a0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d1ac`
- `0x18000d7cc`
- `0x18000e840`
- `0x1800117d8`
- `0x180011a7c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea99`

## string_xrefs

- `0x18000e878`: `CMidi2VirtualMidiEndpointManager::CreateParentDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMidi2VirtualMidiEndpointManager::CreateParentDevice(CMidi2VirtualMidiEndpointManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int128 *v7; // rax
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // rax
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  CMidi2VirtualMidiEndpointManager *v19; // [rsp+48h] [rbp-B8h] BYREF
  const char *v20; // [rsp+50h] [rbp-B0h] BYREF
  const char *v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v23; // [rsp+68h] [rbp-98h]
  char *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  __int128 *v26; // [rsp+90h] [rbp-70h]
  _BYTE v27[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v28; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-20h]
  __int128 v30; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v31; // [rsp+100h] [rbp+0h]
  _QWORD v32[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v19 = this;
    v20 = "CMidi2VirtualMidiEndpointManager::CreateParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)byte_1800267D5,
      v3,
      v4,
      (__int64)&v20,
      (__int64)&v19);
  }
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"MIDI 2.0 Virtual Devices");
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v28, L"MIDIU_APP_TRANSPORT");
  v5 = std::wstring::wstring(v33, &v28);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v32, v5);
  std::wstring::~wstring(&v28);
  memset_0(&v22, 0, 0x48u);
  v22 = 72;
  v6 = v32;
  if ( v32[3] > 7u )
    v6 = (_QWORD *)v32[0];
  v23 = v6;
  v25 = 0;
  v7 = &v30;
  if ( *((_QWORD *)&v31 + 1) > 7u )
    v7 = (__int128 *)v30;
  v26 = v7;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
    v24 = (char *)this + 16;
  pv = 0;
  v8 = (__int64 *)*((_QWORD *)this + 8);
  v9 = *v8;
  pv = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, int *))(v9 + 24))(v8, 0, 0, &v22);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v28 = 0;
    v29 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)pv + v12) );
    std::wstring::_Construct<1,unsigned short const *>(&v28, pv);
    v13 = std::wstring::wstring(v27, &v28);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v33, v13);
    std::wstring::operator=((char *)this + 32, v33);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(&v28);
    v14 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v14 > 4u )
    {
      v20 = (const char *)pv;
      v19 = this;
      v21 = "CMidi2VirtualMidiEndpointManager::CreateParentDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)byte_18002678D,
        v15,
        v16,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&v20);
    }
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v10,
      (int)&pv);
    if ( pv )
      CoTaskMemFree(pv);
  }
  std::wstring::~wstring(v32);
  std::wstring::~wstring(&v30);
  return v11;
}

```

## disassembly

```asm
0x18000e840  mov     [rsp-8+arg_8], rbx
0x18000e845  mov     [rsp-8+arg_10], rsi
0x18000e84a  push    rbp
0x18000e84b  push    rdi
0x18000e84c  push    r14
0x18000e84e  lea     rbp, [rsp-60h]
0x18000e853  sub     rsp, 160h
0x18000e85a  mov     rax, cs:__security_cookie
0x18000e861  xor     rax, rsp
0x18000e864  mov     [rbp+70h+var_20], rax
0x18000e868  mov     rbx, rcx
0x18000e86b  xor     esi, esi
0x18000e86d  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000e872  mov     rcx, [rax+8]
0x18000e876  mov     eax, [rcx]
0x18000e878  lea     r14, aCmidi2virtualm_4; "CMidi2VirtualMidiEndpointManager::Creat"...
0x18000e87f  cmp     eax, 4
0x18000e882  jbe     short loc_18000E8AE
0x18000e884  mov     [rsp+170h+var_128], rbx
0x18000e889  mov     [rsp+170h+var_120], r14
0x18000e88e  lea     rax, [rsp+170h+var_128]
0x18000e893  mov     [rsp+170h+var_148], rax
0x18000e898  lea     rax, [rsp+170h+var_120]
0x18000e89d  mov     qword ptr [rsp+170h+var_150], rax
0x18000e8a2  lea     rdx, byte_1800267D5
0x18000e8a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e8ae  xorps   xmm0, xmm0
0x18000e8b1  movups  [rbp+70h+var_80], xmm0
0x18000e8b5  xorps   xmm1, xmm1
0x18000e8b8  movdqu  [rbp+70h+var_70], xmm1
0x18000e8bd  mov     r8d, 18h
0x18000e8c3  lea     rdx, aMidi20VirtualD; "MIDI 2.0 Virtual Devices"
0x18000e8ca  lea     rcx, [rbp+70h+var_80]
0x18000e8ce  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e8d3  nop
0x18000e8d4  xorps   xmm0, xmm0
0x18000e8d7  movups  [rbp+70h+var_A0], xmm0
0x18000e8db  xorps   xmm1, xmm1
0x18000e8de  movdqu  [rbp+70h+var_90], xmm1
0x18000e8e3  mov     r8d, 13h
0x18000e8e9  lea     rdx, aMidiuAppTransp; "MIDIU_APP_TRANSPORT"
0x18000e8f0  lea     rcx, [rbp+70h+var_A0]
0x18000e8f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e8f9  nop
0x18000e8fa  lea     rdx, [rbp+70h+var_A0]
0x18000e8fe  lea     rcx, [rbp+70h+var_40]
0x18000e902  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e907  mov     rdx, rax
0x18000e90a  lea     rcx, [rbp+70h+var_60]
0x18000e90e  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000e913  nop
0x18000e914  lea     rcx, [rbp+70h+var_A0]
0x18000e918  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e91d  mov     edi, 48h ; 'H'
0x18000e922  mov     r8d, edi; Size
0x18000e925  xor     edx, edx; Val
0x18000e927  lea     rcx, [rsp+170h+var_110]; void *
0x18000e92c  call    memset_0
0x18000e931  mov     [rsp+170h+var_110], edi
0x18000e935  lea     rax, [rbp+70h+var_60]
0x18000e939  cmp     [rbp+70h+var_48], 7
0x18000e93e  cmova   rax, [rbp+70h+var_60]
0x18000e943  mov     [rsp+170h+var_108], rax
0x18000e948  mov     [rbp+70h+var_E8], esi
0x18000e94b  lea     rax, [rbp+70h+var_80]
0x18000e94f  cmp     qword ptr [rbp+70h+var_70+8], 7
0x18000e954  cmova   rax, qword ptr [rbp+70h+var_80]
0x18000e959  mov     [rbp+70h+var_E0], rax
0x18000e95d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x18000e964  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x18000e969  test    al, al
0x18000e96b  jnz     short loc_18000E975
0x18000e96d  lea     rax, [rbx+10h]
0x18000e971  mov     [rbp+70h+var_F0], rax
0x18000e975  mov     [rsp+170h+pv], rsi
0x18000e97a  mov     rcx, [rbx+40h]
0x18000e97e  mov     rax, [rcx]
0x18000e981  mov     [rsp+170h+pv], rsi
0x18000e986  lea     rdx, [rsp+170h+pv]
0x18000e98b  mov     qword ptr [rsp+170h+var_150], rdx; int
0x18000e990  lea     r9, [rsp+170h+var_110]
0x18000e995  xor     r8d, r8d
0x18000e998  xor     edx, edx
0x18000e99a  mov     rax, [rax+18h]
0x18000e99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a3  mov     edi, eax
0x18000e9a5  test    eax, eax
0x18000e9a7  jns     short loc_18000E9DB
0x18000e9a9  mov     rcx, [rbp+78h]; this
0x18000e9ad  mov     r9d, eax; char *
0x18000e9b0  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000e9b7  mov     edx, 0C0h; void *
0x18000e9bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9c1  nop
0x18000e9c2  mov     rcx, [rsp+170h+pv]; pv
0x18000e9c7  test    rcx, rcx
0x18000e9ca  jz      loc_18000EAA1
0x18000e9d0  call    cs:__imp_CoTaskMemFree
0x18000e9d6  jmp     loc_18000EAA1
0x18000e9db  mov     rdx, [rsp+170h+pv]
0x18000e9e0  xorps   xmm0, xmm0
0x18000e9e3  movups  [rbp+70h+var_A0], xmm0
0x18000e9e7  xorps   xmm1, xmm1
0x18000e9ea  movdqu  [rbp+70h+var_90], xmm1
0x18000e9ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e9f3  inc     r8
0x18000e9f6  cmp     [rdx+r8*2], si
0x18000e9fb  jnz     short loc_18000E9F3
0x18000e9fd  lea     rcx, [rbp+70h+var_A0]
0x18000ea01  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ea06  nop
0x18000ea07  lea     rdx, [rbp+70h+var_A0]
0x18000ea0b  lea     rcx, [rbp+70h+var_C0]
0x18000ea0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea14  mov     rdx, rax
0x18000ea17  lea     rcx, [rbp+70h+var_40]
0x18000ea1b  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18000ea20  lea     rcx, [rbx+20h]
0x18000ea24  lea     rdx, [rbp+70h+var_40]
0x18000ea28  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ea2d  lea     rcx, [rbp+70h+var_40]
0x18000ea31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ea36  nop
0x18000ea37  lea     rcx, [rbp+70h+var_A0]
0x18000ea3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ea40  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000ea45  mov     rcx, [rax+8]
0x18000ea49  mov     eax, [rcx]
0x18000ea4b  cmp     eax, 4
0x18000ea4e  jbe     short loc_18000EA8F
0x18000ea50  mov     rax, [rsp+170h+pv]
0x18000ea55  mov     [rsp+170h+var_120], rax
0x18000ea5a  mov     [rsp+170h+var_128], rbx
0x18000ea5f  mov     [rsp+170h+var_118], r14
0x18000ea64  lea     rax, [rsp+170h+var_120]
0x18000ea69  mov     [rsp+170h+var_140], rax
0x18000ea6e  lea     rax, [rsp+170h+var_128]
0x18000ea73  mov     [rsp+170h+var_148], rax
0x18000ea78  lea     rax, [rsp+170h+var_118]
0x18000ea7d  mov     qword ptr [rsp+170h+var_150], rax
0x18000ea82  lea     rdx, byte_18002678D
0x18000ea89  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ea8e  nop
0x18000ea8f  mov     rcx, [rsp+170h+pv]; pv
0x18000ea94  test    rcx, rcx
0x18000ea97  jz      short loc_18000EA9F
0x18000ea99  call    cs:__imp_CoTaskMemFree
0x18000ea9f  mov     edi, esi
0x18000eaa1  lea     rcx, [rbp+70h+var_60]
0x18000eaa5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaaa  nop
0x18000eaab  lea     rcx, [rbp+70h+var_80]
0x18000eaaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eab4  mov     eax, edi
0x18000eab6  mov     rcx, [rbp+70h+var_20]
0x18000eaba  xor     rcx, rsp; StackCookie
0x18000eabd  call    __security_check_cookie
0x18000eac2  lea     r11, [rsp+170h+var_10]
0x18000eaca  mov     rbx, [r11+28h]
0x18000eace  mov     rsi, [r11+30h]
0x18000ead2  mov     rsp, r11
0x18000ead5  pop     r14
0x18000ead7  pop     rdi
0x18000ead8  pop     rbp
0x18000ead9  retn
```
