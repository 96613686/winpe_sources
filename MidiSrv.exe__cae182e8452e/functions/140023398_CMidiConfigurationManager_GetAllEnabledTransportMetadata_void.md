# CMidiConfigurationManager::GetAllEnabledTransportMetadata(void)

- ea: `0x140023398`
- end: `0x140023671`
- name: `?GetAllEnabledTransportMetadata@CMidiConfigurationManager@@QEBA?AV?$vector@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@V?$allocator@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@std@@@std@@XZ`
- size: `729`
- prototype: `_QWORD *__fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e0d0`

## callees

- `0x14000183c`
- `0x140002490`
- `0x1400054c0`
- `0x1400060f8`
- `0x14000984c`
- `0x14000c598`
- `0x140021d84`
- `0x140022f94`
- `0x140023398`
- `0x1400238a4`
- `0x1400252b8`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400234a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400234a0`

## string_xrefs

- `0x140023539`: `avcore\midi2\service\exe\midiconfigurationmanager.cpp`
- `0x1400233d5`: `CMidiConfigurationManager::GetAllEnabledTransportMetadata`
- `0x1400235c6`: `CMidiConfigurationManager::GetAllEnabledTransportMetadata`
- `0x1400235bb`: `Unable to activate IMidiServiceTransportPlugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CMidiConfigurationManager::GetAllEnabledTransportMetadata(void *a1, _QWORD *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  struct _GUID *v7; // rdx
  IID *v8; // rdi
  IID *v9; // r12
  LPVOID v10; // rcx
  LPVOID v11; // rsi
  int (__fastcall *v12)(LPVOID, GUID *, const char **); // r15
  const char *v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  _DWORD *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  int ppv; // [rsp+20h] [rbp-A9h]
  const char *v21; // [rsp+40h] [rbp-89h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-81h] BYREF
  void *v23; // [rsp+50h] [rbp-79h] BYREF
  IID *v24; // [rsp+58h] [rbp-71h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp-69h] BYREF
  GUID rguid; // [rsp+70h] [rbp-59h] BYREF
  IID *rclsid[4]; // [rsp+80h] [rbp-49h] BYREF
  _OWORD v28[4]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v29; // [rsp+E0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v22 = a1;
    v21 = "CMidiConfigurationManager::GetAllEnabledTransportMetadata";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (unsigned int)byte_1400886AB,
      v5,
      v6,
      (__int64)&v21,
      (__int64)&v22);
  }
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  CMidiConfigurationManager::GetEnabledTransports((__int64)a1, rclsid);
  v8 = rclsid[0];
  v9 = rclsid[1];
  while ( v8 != v9 )
  {
    v22 = 0;
    v21 = 0;
    rguid = *v8;
    if ( WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v7) >= 0 )
    {
      v10 = v22;
      v22 = 0;
      if ( v10 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
      if ( CoCreateInstance(v8, 0, 0x17u, &GUID_ea264200_3328_49e5_8815_73649a8748be, &v22) >= 0 )
      {
        v11 = v22;
        v12 = *(int (__fastcall **)(LPVOID, GUID *, const char **))(*(_QWORD *)v22 + 24LL);
        v13 = v21;
        v21 = 0;
        if ( v13 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v12(v11, &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4, &v21) < 0 )
        {
          v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v16 > 2u )
          {
            v23 = a1;
            v24 = v8;
            v25 = L"Unable to activate IMidiServiceTransportPlugin";
            *(_QWORD *)&rguid.Data1 = "CMidiConfigurationManager::GetAllEnabledTransportMetadata";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              (_DWORD)v16,
              (unsigned int)byte_1400885A3,
              v17,
              v18,
              (__int64)&rguid,
              (__int64)&v25,
              (__int64)&v24,
              (__int64)&v23);
          }
        }
        else
        {
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v21 + 24LL))(v21);
          memset_0(v28, 0, 0x48u);
          v14 = (*(__int64 (__fastcall **)(const char *, _OWORD *))(*(_QWORD *)v21 + 32LL))(v21, v28);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x155,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiconfigurationmanager.cpp",
              (const char *)(unsigned int)v14,
              ppv);
          v15 = a2[1];
          if ( v15 == a2[2] )
          {
            std::vector<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>::_Emplace_reallocate<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>(
              a2,
              v15,
              v28);
          }
          else
          {
            *(_OWORD *)v15 = v28[0];
            *(_OWORD *)(v15 + 16) = v28[1];
            *(_OWORD *)(v15 + 32) = v28[2];
            *(_OWORD *)(v15 + 48) = v28[3];
            *(_QWORD *)(v15 + 64) = v29;
            a2[1] += 72LL;
          }
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v21 + 40LL))(v21);
        }
      }
    }
    if ( v21 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
    ++v8;
  }
  std::vector<_GUID>::~vector<_GUID>(rclsid);
  return a2;
}

```

## disassembly

```asm
0x140023398  mov     [rsp-8+arg_10], rbx
0x14002339d  mov     [rsp-8+arg_18], rsi
0x1400233a2  push    rbp
0x1400233a3  push    rdi
0x1400233a4  push    r12
0x1400233a6  push    r14
0x1400233a8  push    r15
0x1400233aa  lea     rbp, [rsp-37h]
0x1400233af  sub     rsp, 100h
0x1400233b6  mov     rax, cs:__security_cookie
0x1400233bd  xor     rax, rsp
0x1400233c0  mov     [rbp+57h+var_30], rax
0x1400233c4  mov     rbx, rdx
0x1400233c7  mov     r14, rcx
0x1400233ca  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400233cf  mov     rcx, [rax+8]
0x1400233d3  mov     eax, [rcx]
0x1400233d5  lea     rdx, aCmidiconfigura_3; "CMidiConfigurationManager::GetAllEnable"...
0x1400233dc  cmp     eax, 4
0x1400233df  jbe     short loc_14002340B
0x1400233e1  mov     [rsp+120h+var_D8], r14
0x1400233e6  mov     [rsp+120h+var_E0], rdx
0x1400233eb  lea     rax, [rsp+120h+var_D8]
0x1400233f0  mov     [rsp+120h+var_F8], rax
0x1400233f5  lea     rax, [rsp+120h+var_E0]
0x1400233fa  mov     [rsp+120h+ppv], rax
0x1400233ff  lea     rdx, byte_1400886AB
0x140023406  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x14002340b  mov     qword ptr [rbx], 0
0x140023412  mov     qword ptr [rbx+8], 0
0x14002341a  mov     qword ptr [rbx+10h], 0
0x140023422  lea     rdx, [rbp+57h+rclsid]
0x140023426  mov     rcx, r14
0x140023429  call    ?GetEnabledTransports@CMidiConfigurationManager@@QEBA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ; CMidiConfigurationManager::GetEnabledTransports(void)
0x14002342e  mov     rdi, [rbp+57h+rclsid]
0x140023432  mov     r12, [rbp+57h+var_98]
0x140023436  jmp     loc_140023634
0x14002343b  mov     [rsp+120h+var_D8], 0
0x140023444  mov     [rsp+120h+var_E0], 0
0x14002344d  movups  xmm0, xmmword ptr [rdi]
0x140023450  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x140023455  lea     rcx, [rbp+57h+rguid]; rguid
0x140023459  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x14002345e  test    eax, eax
0x140023460  js      loc_140023602
0x140023466  mov     rcx, [rsp+120h+var_D8]
0x14002346b  mov     [rsp+120h+var_D8], 0
0x140023474  test    rcx, rcx
0x140023477  jz      short loc_140023486
0x140023479  mov     rax, [rcx]
0x14002347c  mov     rax, [rax+10h]
0x140023480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023485  nop
0x140023486  lea     rax, [rsp+120h+var_D8]
0x14002348b  mov     [rsp+120h+ppv], rax; int
0x140023490  lea     r9, _GUID_ea264200_3328_49e5_8815_73649a8748be; riid
0x140023497  xor     edx, edx; pUnkOuter
0x140023499  lea     r8d, [rdx+17h]; dwClsContext
0x14002349d  mov     rcx, rdi; rclsid
0x1400234a0  call    cs:__imp_CoCreateInstance
0x1400234a6  test    eax, eax
0x1400234a8  js      loc_140023602
0x1400234ae  mov     rsi, [rsp+120h+var_D8]
0x1400234b3  mov     rax, [rsi]
0x1400234b6  mov     r15, [rax+18h]
0x1400234ba  mov     rcx, [rsp+120h+var_E0]
0x1400234bf  mov     [rsp+120h+var_E0], 0
0x1400234c8  test    rcx, rcx
0x1400234cb  jz      short loc_1400234DA
0x1400234cd  mov     rdx, [rcx]
0x1400234d0  mov     rax, [rdx+10h]
0x1400234d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400234d9  nop
0x1400234da  lea     r8, [rsp+120h+var_E0]
0x1400234df  lea     rdx, _GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4
0x1400234e6  mov     rcx, rsi
0x1400234e9  mov     rax, r15
0x1400234ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400234f1  test    eax, eax
0x1400234f3  js      loc_1400235A3
0x1400234f9  mov     rcx, [rsp+120h+var_E0]
0x1400234fe  mov     rax, [rcx]
0x140023501  mov     rax, [rax+18h]
0x140023505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002350a  xor     edx, edx; Val
0x14002350c  lea     r8d, [rdx+48h]; Size
0x140023510  lea     rcx, [rbp+57h+var_80]; void *
0x140023514  call    memset_0
0x140023519  mov     rcx, [rsp+120h+var_E0]
0x14002351e  mov     rax, [rcx]
0x140023521  lea     rdx, [rbp+57h+var_80]
0x140023525  mov     rax, [rax+20h]
0x140023529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002352e  mov     rcx, [rbp+5Fh]; this
0x140023532  test    eax, eax
0x140023534  jns     short loc_14002354A
0x140023536  mov     r9d, eax; char *
0x140023539  lea     r8, aAvcoreMidi2Ser_7; "avcore\\midi2\\service\\exe\\midiconfig"...
0x140023540  mov     edx, 155h; void *
0x140023545  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002354a  mov     rdx, [rbx+8]
0x14002354e  cmp     rdx, [rbx+10h]
0x140023552  jz      short loc_140023584
0x140023554  movaps  xmm0, [rbp+57h+var_80]
0x140023558  movups  xmmword ptr [rdx], xmm0
0x14002355b  movaps  xmm1, [rbp+57h+var_70]
0x14002355f  movups  xmmword ptr [rdx+10h], xmm1
0x140023563  movaps  xmm0, [rbp+57h+var_60]
0x140023567  movups  xmmword ptr [rdx+20h], xmm0
0x14002356b  movaps  xmm1, [rbp+57h+var_50]
0x14002356f  movups  xmmword ptr [rdx+30h], xmm1
0x140023573  movsd   xmm0, [rbp+57h+var_40]
0x140023578  movsd   qword ptr [rdx+40h], xmm0
0x14002357d  add     qword ptr [rbx+8], 48h ; 'H'
0x140023582  jmp     short loc_140023590
0x140023584  lea     r8, [rbp+57h+var_80]
0x140023588  mov     rcx, rbx
0x14002358b  call    ??$_Emplace_reallocate@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@?$vector@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@V?$allocator@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@std@@@std@@AEAAPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@QEAU2@$$QEAU2@@Z; std::vector<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>::_Emplace_reallocate<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 * const,__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 &&)
0x140023590  mov     rcx, [rsp+120h+var_E0]
0x140023595  mov     rax, [rcx]
0x140023598  mov     rax, [rax+28h]
0x14002359c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400235a1  jmp     short loc_140023602
0x1400235a3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400235a8  mov     rcx, [rax+8]
0x1400235ac  mov     eax, [rcx]
0x1400235ae  cmp     eax, 2
0x1400235b1  jbe     short loc_140023602
0x1400235b3  mov     [rbp+57h+var_D0], r14
0x1400235b7  mov     [rbp+57h+var_C8], rdi
0x1400235bb  lea     rax, aUnableToActiva; "Unable to activate IMidiServiceTranspor"...
0x1400235c2  mov     [rbp+57h+var_C0], rax
0x1400235c6  lea     rax, aCmidiconfigura_3; "CMidiConfigurationManager::GetAllEnable"...
0x1400235cd  mov     qword ptr [rbp+57h+rguid.Data1], rax
0x1400235d1  lea     rax, [rbp+57h+var_D0]
0x1400235d5  mov     [rsp+120h+var_E8], rax
0x1400235da  lea     rax, [rbp+57h+var_C8]
0x1400235de  mov     [rsp+120h+var_F0], rax
0x1400235e3  lea     rax, [rbp+57h+var_C0]
0x1400235e7  mov     [rsp+120h+var_F8], rax
0x1400235ec  lea     rax, [rbp+57h+rguid]
0x1400235f0  mov     [rsp+120h+ppv], rax
0x1400235f5  lea     rdx, byte_1400885A3
0x1400235fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x140023601  nop
0x140023602  mov     rcx, [rsp+120h+var_E0]
0x140023607  test    rcx, rcx
0x14002360a  jz      short loc_140023619
0x14002360c  mov     rax, [rcx]
0x14002360f  mov     rax, [rax+10h]
0x140023613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023618  nop
0x140023619  mov     rcx, [rsp+120h+var_D8]
0x14002361e  test    rcx, rcx
0x140023621  jz      short loc_140023630
0x140023623  mov     rax, [rcx]
0x140023626  mov     rax, [rax+10h]
0x14002362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002362f  nop
0x140023630  add     rdi, 10h
0x140023634  cmp     rdi, r12
0x140023637  jnz     loc_14002343B
0x14002363d  lea     rcx, [rbp+57h+rclsid]
0x140023641  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x140023646  mov     rax, rbx
0x140023649  mov     rcx, [rbp+57h+var_30]
0x14002364d  xor     rcx, rsp; StackCookie
0x140023650  call    __security_check_cookie
0x140023655  lea     r11, [rsp+120h+var_20]
0x14002365d  mov     rbx, [r11+40h]
0x140023661  mov     rsi, [r11+48h]
0x140023665  mov     rsp, r11
0x140023668  pop     r15
0x14002366a  pop     r14
0x14002366c  pop     r12
0x14002366e  pop     rdi
0x14002366f  pop     rbp
0x140023670  retn
```
