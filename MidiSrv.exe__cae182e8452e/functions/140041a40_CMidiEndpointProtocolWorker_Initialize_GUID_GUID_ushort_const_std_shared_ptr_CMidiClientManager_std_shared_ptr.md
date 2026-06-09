# CMidiEndpointProtocolWorker::Initialize(_GUID,_GUID,ushort const *,std::shared_ptr<CMidiClientManager> &,std::shared_ptr<CMidiDeviceManager> &,std::shared_ptr<CMidiSessionTracker> &)

- ea: `0x140041a40`
- end: `0x140041c92`
- name: `?Initialize@CMidiEndpointProtocolWorker@@UEAAJU_GUID@@0PEBGAEAV?$shared_ptr@VCMidiClientManager@@@std@@AEAV?$shared_ptr@VCMidiDeviceManager@@@4@AEAV?$shared_ptr@VCMidiSessionTracker@@@4@@Z`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001440c`
- `0x1400144ac`
- `0x14001dccc`
- `0x14002156c`
- `0x140036378`
- `0x140041a40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140041bd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140041bd4`

## string_xrefs

- `0x140041bf3`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140041c1b`: `Initialize complete`
- `0x140041a87`: `CMidiEndpointProtocolWorker::Initialize`
- `0x140041c31`: `CMidiEndpointProtocolWorker::Initialize`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::Initialize(
        __int64 a1,
        __int128 *a2,
        _OWORD *a3,
        const char *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct MidiSrvTelemetryProvider *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // rdx
  _DWORD *v15; // rcx
  unsigned int v16; // eax
  unsigned __int64 v17; // r8
  __int128 v18; // xmm1
  __int64 v19; // rax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v21; // esi
  _DWORD *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // [rsp+20h] [rbp-A1h]
  unsigned int v27; // [rsp+40h] [rbp-81h] BYREF
  const char *v28; // [rsp+48h] [rbp-79h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-71h] BYREF
  const wchar_t *v30; // [rsp+58h] [rbp-69h] BYREF
  int v31[2]; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v32[32]; // [rsp+68h] [rbp-59h] BYREF
  _OWORD v33[2]; // [rsp+88h] [rbp-39h] BYREF
  char *v34[4]; // [rsp+A8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v11 = MidiSrvTelemetryProvider::Instance();
  v14 = "CMidiEndpointProtocolWorker::Initialize";
  v15 = (_DWORD *)*((_QWORD *)v11 + 1);
  if ( *v15 > 4u )
  {
    *(_QWORD *)v31 = "CMidiEndpointProtocolWorker::Initialize";
    v29 = L"Enter";
    v28 = a4;
    v30 = (const wchar_t *)a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v15,
      (__int64)&word_14008C18E,
      v12,
      v13,
      v31,
      (__int64)&v30,
      &v29,
      &v28);
  }
  v27 = 5000;
  if ( wil::reg::get_value_dword_nothrow<unsigned long,0>((__int64)v15, (__int64)v14, L"Midi2DiscoveryTimeoutMS", &v27) < 0 )
  {
    *(_DWORD *)(a1 + 140) = 5000;
  }
  else
  {
    v16 = v27;
    if ( v27 <= 0x1F4 )
    {
      v16 = 500;
      v27 = 500;
    }
    if ( v16 >= 0xC350 )
    {
      v16 = 50000;
      v27 = 50000;
    }
    *(_DWORD *)(a1 + 140) = v16;
  }
  v17 = -1;
  v18 = *a2;
  *(_OWORD *)(a1 + 108) = *a3;
  *(_OWORD *)(a1 + 88) = v18;
  memset(v33, 0, sizeof(v33));
  do
    ++v17;
  while ( *(_WORD *)&a4[2 * v17] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v33, a4, v17);
  v19 = std::wstring::wstring((__int64)v32, (__int64)v33);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v34, v19);
  std::wstring::operator=((char **)(a1 + 56), (__int64)v34);
  std::wstring::~wstring(v34);
  std::wstring::~wstring((char **)v33);
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 160, a5);
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 176, a6);
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 192, a7);
  *(_DWORD *)(a1 + 104) = GetCurrentProcessId();
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 144);
  v21 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v23 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v23 > 4u )
    {
      *(_QWORD *)v31 = a4;
      v30 = L"Initialize complete";
      v29 = (const wchar_t *)a1;
      v28 = "CMidiEndpointProtocolWorker::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v23,
        (__int64)&word_14008B916,
        v24,
        v25,
        &v28,
        (__int64)&v29,
        &v30,
        v31);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v26);
    return v21;
  }
}

```

## disassembly

```asm
0x140041a40  mov     [rsp-8+arg_8], rbx
0x140041a45  push    rbp
0x140041a46  push    rsi
0x140041a47  push    rdi
0x140041a48  push    r12
0x140041a4a  push    r13
0x140041a4c  push    r14
0x140041a4e  push    r15
0x140041a50  lea     rbp, [rsp-0Fh]
0x140041a55  sub     rsp, 0D0h
0x140041a5c  mov     rax, cs:__security_cookie
0x140041a63  xor     rax, rsp
0x140041a66  mov     [rbp+3Fh+var_38], rax
0x140041a6a  mov     r15, [rbp+3Fh+arg_20]
0x140041a6e  mov     rdi, r9
0x140041a71  mov     r12, [rbp+3Fh+arg_28]
0x140041a75  mov     rsi, r8
0x140041a78  mov     r13, [rbp+3Fh+arg_30]
0x140041a7c  mov     r14, rdx
0x140041a7f  mov     rbx, rcx
0x140041a82  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140041a87  lea     rdx, aCmidiendpointp_20; "CMidiEndpointProtocolWorker::Initialize"
0x140041a8e  mov     rcx, [rax+8]
0x140041a92  mov     eax, [rcx]
0x140041a94  cmp     eax, 4
0x140041a97  jbe     short loc_140041AE0
0x140041a99  lea     rax, aEnter; "Enter"
0x140041aa0  mov     qword ptr [rbp+3Fh+var_A0], rdx
0x140041aa4  mov     [rbp+3Fh+var_B0], rax
0x140041aa8  lea     rdx, word_14008C18E
0x140041aaf  lea     rax, [rbp+3Fh+var_B8]
0x140041ab3  mov     [rbp+3Fh+var_B8], rdi
0x140041ab7  mov     [rsp+100h+var_C8], rax
0x140041abc  lea     rax, [rbp+3Fh+var_B0]
0x140041ac0  mov     [rsp+100h+var_D0], rax
0x140041ac5  lea     rax, [rbp+3Fh+var_A8]
0x140041ac9  mov     [rsp+100h+var_D8], rax
0x140041ace  lea     rax, [rbp+3Fh+var_A0]
0x140041ad2  mov     qword ptr [rsp+100h+var_E0], rax; int
0x140041ad7  mov     [rbp+3Fh+var_A8], rbx
0x140041adb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140041ae0  lea     r9, [rsp+100h+var_C0]
0x140041ae5  mov     [rsp+100h+var_C0], 1388h
0x140041aed  lea     r8, aMidi2discovery_0; "Midi2DiscoveryTimeoutMS"
0x140041af4  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140041af9  xor     ecx, ecx
0x140041afb  test    eax, eax
0x140041afd  js      short loc_140041B2B
0x140041aff  mov     eax, [rsp+100h+var_C0]
0x140041b03  mov     ecx, 1F4h
0x140041b08  cmp     eax, ecx
0x140041b0a  ja      short loc_140041B12
0x140041b0c  mov     eax, ecx
0x140041b0e  mov     [rsp+100h+var_C0], ecx
0x140041b12  mov     ecx, 0C350h
0x140041b17  cmp     eax, ecx
0x140041b19  jb      short loc_140041B21
0x140041b1b  mov     eax, ecx
0x140041b1d  mov     [rsp+100h+var_C0], ecx
0x140041b21  mov     [rbx+8Ch], eax
0x140041b27  xor     ecx, ecx
0x140041b29  jmp     short loc_140041B35
0x140041b2b  mov     dword ptr [rbx+8Ch], 1388h
0x140041b35  movups  xmm0, xmmword ptr [rsi]
0x140041b38  or      r8, 0FFFFFFFFFFFFFFFFh
0x140041b3c  movups  xmm1, xmmword ptr [r14]
0x140041b40  movdqu  xmmword ptr [rbx+6Ch], xmm0
0x140041b45  movdqu  xmmword ptr [rbx+58h], xmm1
0x140041b4a  xorps   xmm0, xmm0
0x140041b4d  xorps   xmm1, xmm1
0x140041b50  movups  [rbp+3Fh+var_78], xmm0
0x140041b54  movdqu  [rbp+3Fh+var_68], xmm1
0x140041b59  inc     r8
0x140041b5c  cmp     [rdi+r8*2], cx
0x140041b61  jnz     short loc_140041B59
0x140041b63  mov     rdx, rdi
0x140041b66  lea     rcx, [rbp+3Fh+var_78]
0x140041b6a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140041b6f  lea     rdx, [rbp+3Fh+var_78]
0x140041b73  lea     rcx, [rbp+3Fh+var_98]
0x140041b77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140041b7c  mov     rdx, rax
0x140041b7f  lea     rcx, [rbp+3Fh+var_58]
0x140041b83  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140041b88  lea     rcx, [rbx+38h]
0x140041b8c  lea     rdx, [rbp+3Fh+var_58]
0x140041b90  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140041b95  lea     rcx, [rbp+3Fh+var_58]; void *
0x140041b99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140041b9e  lea     rcx, [rbp+3Fh+var_78]; void *
0x140041ba2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140041ba7  lea     rcx, [rbx+0A0h]
0x140041bae  mov     rdx, r15
0x140041bb1  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x140041bb6  lea     rcx, [rbx+0B0h]
0x140041bbd  mov     rdx, r12
0x140041bc0  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x140041bc5  lea     rcx, [rbx+0C0h]
0x140041bcc  mov     rdx, r13
0x140041bcf  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x140041bd4  call    cs:__imp_GetCurrentProcessId
0x140041bda  lea     rcx, [rbx+90h]
0x140041be1  mov     [rbx+68h], eax
0x140041be4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140041be9  mov     esi, eax
0x140041beb  test    eax, eax
0x140041bed  jns     short loc_140041C0B
0x140041bef  mov     rcx, [rbp+47h]; this
0x140041bf3  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140041bfa  mov     r9d, eax; char *
0x140041bfd  mov     edx, 3Ch ; '<'; void *
0x140041c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140041c07  mov     eax, esi
0x140041c09  jmp     short loc_140041C6B
0x140041c0b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140041c10  mov     rcx, [rax+8]
0x140041c14  mov     eax, [rcx]
0x140041c16  cmp     eax, 4
0x140041c19  jbe     short loc_140041C69
0x140041c1b  lea     rax, aInitializeComp; "Initialize complete"
0x140041c22  mov     qword ptr [rbp+3Fh+var_A0], rdi
0x140041c26  mov     [rbp+3Fh+var_A8], rax
0x140041c2a  lea     rdx, word_14008B916
0x140041c31  lea     rax, aCmidiendpointp_20; "CMidiEndpointProtocolWorker::Initialize"
0x140041c38  mov     [rbp+3Fh+var_B0], rbx
0x140041c3c  mov     [rbp+3Fh+var_B8], rax
0x140041c40  lea     rax, [rbp+3Fh+var_A0]
0x140041c44  mov     [rsp+100h+var_C8], rax
0x140041c49  lea     rax, [rbp+3Fh+var_A8]
0x140041c4d  mov     [rsp+100h+var_D0], rax
0x140041c52  lea     rax, [rbp+3Fh+var_B0]
0x140041c56  mov     [rsp+100h+var_D8], rax
0x140041c5b  lea     rax, [rbp+3Fh+var_B8]
0x140041c5f  mov     qword ptr [rsp+100h+var_E0], rax
0x140041c64  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140041c69  xor     eax, eax
0x140041c6b  mov     rcx, [rbp+3Fh+var_38]
0x140041c6f  xor     rcx, rsp; StackCookie
0x140041c72  call    __security_check_cookie
0x140041c77  mov     rbx, [rsp+100h+arg_8]
0x140041c7f  add     rsp, 0D0h
0x140041c86  pop     r15
0x140041c88  pop     r14
0x140041c8a  pop     r13
0x140041c8c  pop     r12
0x140041c8e  pop     rdi
0x140041c8f  pop     rsi
0x140041c90  pop     rbp
0x140041c91  retn
```
