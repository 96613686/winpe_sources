# IpConfigSignal::Create(__int64,IpConfigSignal::Properties const &,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *)

- ea: `0x180039608`
- end: `0x180039757`
- name: `?Create@IpConfigSignal@@SAJ_JAEBUProperties@1@PEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(__int64, struct Properties *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003a170`

## callees

- `0x1800011c0`
- `0x1800018a4`
- `0x18000459c`
- `0x18000a7f8`
- `0x18000b7b8`
- `0x180012b0c`
- `0x180021980`
- `0x180029568`
- `0x180038fb0`
- `0x180039608`
- `0x18003a7a4`

## import_xrefs

- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180039678`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180039678`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IpConfigSignal::Create(__int64 a1, struct Properties *a2, HANDLE **a3)
{
  HANDLE *v6; // rdi
  unsigned int v7; // eax
  HANDLE *v8; // rbx
  __int64 v9; // rcx
  HANDLE *v10; // rdx
  NaturalAuthTraceLogging *v11; // rcx
  const struct _GUID *ActivityId; // rax
  __int64 v13; // r9
  int v15; // [rsp+30h] [rbp-38h] BYREF
  HANDLE *v16; // [rsp+38h] [rbp-30h] BYREF
  HANDLE *v17; // [rsp+88h] [rbp+20h] BYREF

  v6 = (HANDLE *)operator new(0xC0u);
  v17 = v6;
  GenericPlugin::DefaultSignal::DefaultSignal((GenericPlugin::DefaultSignal *)v6, a1);
  *v6 = &IpConfigSignal::`vftable';
  IpConfigSignal::Properties::Properties((IpConfigSignal::Properties *)(v6 + 6), a2);
  v6[23] = 0;
  v16 = v6;
  v7 = NotifyIpInterfaceChange(0, IpConfigSignal::IpChangeCallback, v6, 0, v6 + 23);
  v8 = (HANDLE *)v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids, v7);
    LODWORD(v8) = (unsigned int)v8 | 0x10000000;
    if ( (unsigned int)dword_18005C570 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005C570, 0x400000000000LL) )
    {
      LODWORD(v17) = (_DWORD)v8;
      v15 = a1;
      ActivityId = NaturalAuthTraceLogging::GetActivityId(v11);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18005C570,
        (__int64)&unk_180050370,
        (__int64)ActivityId,
        v13,
        (__int64)&v15,
        (__int64)&v17);
    }
  }
  else
  {
    IpConfigSignal::UpdateState((IpConfigSignal *)v6);
    v16 = v8;
    v10 = *a3;
    *a3 = v6;
    if ( v10 )
      std::default_delete<NASignal>::operator()(v9, (__int64 (__fastcall ***)(_QWORD, __int64))v10);
  }
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>((__int64 (__fastcall ****)(_QWORD, __int64))&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039608  push    rbx
0x18003960a  push    rbp
0x18003960b  push    rsi
0x18003960c  push    rdi
0x18003960d  sub     rsp, 48h
0x180039611  mov     rsi, r8
0x180039614  mov     rbx, rdx
0x180039617  mov     rbp, rcx
0x18003961a  mov     ecx, 0C0h; Size
0x18003961f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039624  mov     rdi, rax
0x180039627  mov     [rsp+68h+arg_18], rax
0x18003962f  mov     rdx, rbp; __int64
0x180039632  mov     rcx, rax; this
0x180039635  call    ??0DefaultSignal@GenericPlugin@@QEAA@_J@Z; GenericPlugin::DefaultSignal::DefaultSignal(__int64)
0x18003963a  nop
0x18003963b  lea     rax, ??_7IpConfigSignal@@6B@; const IpConfigSignal::`vftable'
0x180039642  mov     [rdi], rax
0x180039645  lea     rcx, [rdi+30h]; this
0x180039649  mov     rdx, rbx; struct Properties *
0x18003964c  call    ??0Properties@IpConfigSignal@@QEAA@AEBU01@@Z; IpConfigSignal::Properties::Properties(IpConfigSignal::Properties const &)
0x180039651  lea     rdx, [rdi+0B8h]
0x180039658  mov     qword ptr [rdx], 0
0x18003965f  mov     [rsp+68h+var_30], rdi
0x180039664  xor     ecx, ecx; Family
0x180039666  mov     [rsp+68h+NotificationHandle], rdx; NotificationHandle
0x18003966b  xor     r9d, r9d; InitialNotification
0x18003966e  mov     r8, rdi; CallerContext
0x180039671  lea     rdx, ?IpChangeCallback@IpConfigSignal@@CAXPEAXPEAU_MIB_IPINTERFACE_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x180039678  call    cs:__imp_NotifyIpInterfaceChange
0x18003967e  mov     ebx, eax
0x180039680  test    eax, eax
0x180039682  jnz     short loc_1800396AA
0x180039684  mov     rcx, rdi; this
0x180039687  call    ?UpdateState@IpConfigSignal@@AEAAXXZ; IpConfigSignal::UpdateState(void)
0x18003968c  mov     [rsp+68h+var_30], rbx
0x180039691  mov     rdx, [rsi]
0x180039694  mov     [rsi], rdi
0x180039697  test    rdx, rdx
0x18003969a  jz      loc_180039742
0x1800396a0  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x1800396a5  jmp     loc_180039742
0x1800396aa  lea     rax, WPP_GLOBAL_Control
0x1800396b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396b8  cmp     rcx, rax
0x1800396bb  jz      short loc_1800396DB
0x1800396bd  test    byte ptr [rcx+1Ch], 1
0x1800396c1  jz      short loc_1800396DB
0x1800396c3  mov     edx, 0Ah
0x1800396c8  mov     r9d, ebx
0x1800396cb  lea     r8, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids
0x1800396d2  mov     rcx, [rcx+10h]
0x1800396d6  call    WPP_SF_d
0x1800396db  bts     ebx, 1Ch
0x1800396df  mov     eax, cs:dword_18005C570
0x1800396e5  cmp     eax, 5
0x1800396e8  jbe     short loc_180039742
0x1800396ea  mov     rdx, 400000000000h
0x1800396f4  lea     rcx, dword_18005C570
0x1800396fb  call    _tlgKeywordOn
0x180039700  test    al, al
0x180039702  jz      short loc_180039742
0x180039704  mov     dword ptr [rsp+68h+arg_18], ebx
0x18003970b  mov     [rsp+68h+var_38], ebp
0x18003970f  call    ?GetActivityId@NaturalAuthTraceLogging@@YAPEBU_GUID@@XZ; NaturalAuthTraceLogging::GetActivityId(void)
0x180039714  mov     r8, rax
0x180039717  lea     rax, [rsp+68h+arg_18]
0x18003971f  mov     [rsp+68h+var_40], rax
0x180039724  lea     rax, [rsp+68h+var_38]
0x180039729  mov     [rsp+68h+NotificationHandle], rax
0x18003972e  lea     rdx, unk_180050370
0x180039735  lea     rcx, dword_18005C570
0x18003973c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180039741  nop
0x180039742  lea     rcx, [rsp+68h+var_30]
0x180039747  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18003974c  mov     eax, ebx
0x18003974e  add     rsp, 48h
0x180039752  pop     rdi
0x180039753  pop     rsi
0x180039754  pop     rbp
0x180039755  pop     rbx
0x180039756  retn
```
