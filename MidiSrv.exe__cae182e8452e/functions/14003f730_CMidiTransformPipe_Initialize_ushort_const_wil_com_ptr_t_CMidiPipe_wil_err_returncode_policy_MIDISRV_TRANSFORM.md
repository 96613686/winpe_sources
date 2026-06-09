# CMidiTransformPipe::Initialize(ushort const *,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,MIDISRV_TRANSFORMCREATION_PARAMS *,ulong *,IMidiDeviceManager *)

- ea: `0x14003f730`
- end: `0x14003fbe3`
- name: `?Initialize@CMidiTransformPipe@@QEAAJPEBGAEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@PEAUMIDISRV_TRANSFORMCREATION_PARAMS@@PEAKPEAUIMidiDeviceManager@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140019aac`
- `0x14001a084`
- `0x14001a680`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001b8c0`
- `0x14001e990`
- `0x1400252b8`
- `0x14003f730`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003fa0a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003fa0a`

## string_xrefs

- `0x14003f8bc`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003f90d`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003f958`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003f9a6`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003fa1d`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003fa9a`: `avcore\midi2\service\exe\miditransformpipe.cpp`
- `0x14003fb18`: `avcore\midi2\service\exe\miditransformpipe.cpp`

## pseudocode

```c
__int64 __fastcall CMidiTransformPipe::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const wchar_t *a6)
{
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  char v12; // r8
  char v13; // r9
  char v14; // r10
  char v15; // r11
  char v16; // bl
  char v17; // di
  char v18; // si
  char v19; // r14
  __int64 v20; // rdx
  __int16 v21; // cx
  struct _GUID *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  LSTATUS IsComponentPermitted; // eax
  unsigned int v26; // ebx
  __int64 v28; // rsi
  int v29; // eax
  int v30; // eax
  int v31; // eax
  LPVOID v32; // rcx
  HRESULT v33; // eax
  LPVOID v34; // rbx
  __int64 (__fastcall *v35)(LPVOID, GUID *, __int64); // r14
  __int64 v36; // rcx
  int v37; // eax
  int v38; // eax
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  int ppv; // [rsp+20h] [rbp-79h]
  int ppva; // [rsp+20h] [rbp-79h]
  LPVOID v44; // [rsp+40h] [rbp-59h] BYREF
  __int64 v45; // [rsp+48h] [rbp-51h] BYREF
  const wchar_t *v46; // [rsp+50h] [rbp-49h] BYREF
  __int64 v47; // [rsp+58h] [rbp-41h] BYREF
  GUID rguid; // [rsp+60h] [rbp-39h] BYREF
  __int64 v49; // [rsp+70h] [rbp-29h] BYREF
  const wchar_t *v50; // [rsp+78h] [rbp-21h] BYREF
  __int64 v51; // [rsp+80h] [rbp-19h] BYREF
  int v52[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v53; // [rsp+90h] [rbp-9h] BYREF
  int v54; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  *(_QWORD *)&rguid.Data1 = a3;
  v45 = a2;
  v47 = a5;
  v46 = a6;
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v49 = a2;
    v50 = L"Enter";
    v51 = a1;
    *(_QWORD *)v52 = "CMidiTransformPipe::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)byte_14008B49B,
      v10,
      v11,
      (__int64)v52,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49);
  }
  v44 = 0;
  v53 = 0;
  v54 = 0;
  v12 = *(_BYTE *)(a4 + 8);
  v13 = *(_BYTE *)(a4 + 9);
  v14 = *(_BYTE *)(a4 + 10);
  v15 = *(_BYTE *)(a4 + 11);
  v16 = *(_BYTE *)(a4 + 12);
  v17 = *(_BYTE *)(a4 + 13);
  v18 = *(_BYTE *)(a4 + 14);
  v19 = *(_BYTE *)(a4 + 15);
  v20 = *(unsigned __int16 *)(a4 + 6);
  v21 = *(_WORD *)(a4 + 4);
  *(_DWORD *)(a1 + 136) = *(_DWORD *)a4;
  *(_WORD *)(a1 + 140) = v21;
  *(_WORD *)(a1 + 142) = v20;
  *(_BYTE *)(a1 + 144) = v12;
  *(_BYTE *)(a1 + 145) = v13;
  *(_BYTE *)(a1 + 146) = v14;
  *(_BYTE *)(a1 + 147) = v15;
  *(_BYTE *)(a1 + 148) = v16;
  *(_BYTE *)(a1 + 149) = v17;
  *(_BYTE *)(a1 + 150) = v18;
  *(_BYTE *)(a1 + 151) = v19;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                          v20) )
  {
    v23 = **(_QWORD **)&rguid.Data1;
    v24 = *(_QWORD *)(a1 + 120);
    *(_QWORD *)(a1 + 120) = **(_QWORD **)&rguid.Data1;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  rguid = *(GUID *)(a1 + 136);
  IsComponentPermitted = WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v22);
  v26 = IsComponentPermitted;
  if ( IsComponentPermitted < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)IsComponentPermitted,
      ppv);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v28 = v45;
  v29 = CMidiPipe::Initialize(a1, v45, 2);
  v26 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v29,
      ppv);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, *(unsigned int *)(a4 + 16));
  v26 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v30,
      ppv);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 88LL))(a1, *(unsigned int *)(a4 + 20));
  v26 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v31,
      ppv);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v32 = v44;
  v44 = 0;
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  v33 = CoCreateInstance((const IID *const)(a1 + 136), 0, 0x17u, &GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d, &v44);
  v26 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v33,
      ppva);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v34 = v44;
  v35 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64))(*(_QWORD *)v44 + 24LL);
  v36 = *(_QWORD *)(a1 + 128);
  *(_QWORD *)(a1 + 128) = 0;
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  v37 = v35(v34, &GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4, a1 + 128);
  v26 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v37,
      ppva);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v53 = *(_QWORD *)(a1 + 48);
  LOBYTE(v54) = *(_BYTE *)(a4 + 28);
  v38 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(**(_QWORD **)(a1 + 128) + 24LL))(
          *(_QWORD *)(a1 + 128),
          v28,
          &v53,
          v47);
  v26 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"avcore\\midi2\\service\\exe\\miditransformpipe.cpp",
      (const char *)(unsigned int)v38,
      a1);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v26;
  }
  v39 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v39 > 4u )
  {
    v47 = v28;
    v46 = L"Exit success";
    v45 = a1;
    *(_QWORD *)&rguid.Data1 = "CMidiTransformPipe::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v39,
      (unsigned int)byte_14008B445,
      v40,
      v41,
      (__int64)&rguid,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v47);
  }
  if ( v44 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
  return 0;
}

```

## disassembly

```asm
0x14003f730  mov     [rsp-8+arg_10], rbx
0x14003f735  push    rbp
0x14003f736  push    rsi
0x14003f737  push    rdi
0x14003f738  push    r12
0x14003f73a  push    r13
0x14003f73c  push    r14
0x14003f73e  push    r15
0x14003f740  lea     rbp, [rsp-17h]
0x14003f745  sub     rsp, 0B0h
0x14003f74c  mov     rax, cs:__security_cookie
0x14003f753  xor     rax, rsp
0x14003f756  mov     [rbp+47h+var_40], rax
0x14003f75a  mov     r12, r9
0x14003f75d  mov     qword ptr [rbp+47h+rguid.Data1], r8
0x14003f761  mov     rbx, rdx
0x14003f764  mov     [rbp+47h+var_98], rdx
0x14003f768  mov     r15, rcx
0x14003f76b  mov     rax, [rbp+47h+arg_20]
0x14003f76f  mov     [rbp+47h+var_88], rax
0x14003f773  mov     rax, [rbp+47h+arg_28]
0x14003f777  mov     [rbp+47h+var_90], rax
0x14003f77b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f780  mov     rcx, [rax+8]
0x14003f784  mov     eax, [rcx]
0x14003f786  lea     rdx, aCmiditransform; "CMidiTransformPipe::Initialize"
0x14003f78d  cmp     eax, 4
0x14003f790  jbe     short loc_14003F7D9
0x14003f792  mov     [rbp+47h+var_70], rbx
0x14003f796  lea     rax, aEnter; "Enter"
0x14003f79d  mov     [rbp+47h+var_68], rax
0x14003f7a1  mov     [rbp+47h+var_60], r15
0x14003f7a5  mov     qword ptr [rbp+47h+var_58], rdx
0x14003f7a9  lea     rax, [rbp+47h+var_70]
0x14003f7ad  mov     [rsp+0E0h+var_A8], rax
0x14003f7b2  lea     rax, [rbp+47h+var_68]
0x14003f7b6  mov     [rsp+0E0h+var_B0], rax
0x14003f7bb  lea     rax, [rbp+47h+var_60]
0x14003f7bf  mov     [rsp+0E0h+var_B8], rax
0x14003f7c4  lea     rax, [rbp+47h+var_58]
0x14003f7c8  mov     [rsp+0E0h+ppv], rax; int
0x14003f7cd  lea     rdx, byte_14008B49B
0x14003f7d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003f7d9  mov     [rbp+47h+var_A0], 0
0x14003f7e1  xor     eax, eax
0x14003f7e3  mov     [rbp+47h+var_50], rax
0x14003f7e7  mov     [rbp+47h+var_48], eax
0x14003f7ea  mov     r8b, [r12+8]
0x14003f7ef  mov     r9b, [r12+9]
0x14003f7f4  mov     r10b, [r12+0Ah]
0x14003f7f9  mov     r11b, [r12+0Bh]
0x14003f7fe  mov     bl, [r12+0Ch]
0x14003f803  mov     dil, [r12+0Dh]
0x14003f808  mov     sil, [r12+0Eh]
0x14003f80d  mov     r14b, [r12+0Fh]
0x14003f812  movzx   edx, word ptr [r12+6]
0x14003f818  movzx   ecx, word ptr [r12+4]
0x14003f81e  lea     r13, [r15+88h]
0x14003f825  mov     eax, [r12]
0x14003f829  mov     [r13+0], eax
0x14003f82d  mov     [r13+4], cx
0x14003f832  mov     [r13+6], dx
0x14003f837  mov     [r13+8], r8b
0x14003f83b  mov     [r13+9], r9b
0x14003f83f  mov     [r13+0Ah], r10b
0x14003f843  mov     [r13+0Bh], r11b
0x14003f847  mov     [r13+0Ch], bl
0x14003f84b  mov     [r13+0Dh], dil
0x14003f84f  mov     [r13+0Eh], sil
0x14003f853  mov     [r13+0Fh], r14b
0x14003f857  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14003f85e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14003f863  test    al, al
0x14003f865  jz      short loc_14003F89C
0x14003f867  mov     rcx, qword ptr [rbp+47h+rguid.Data1]
0x14003f86b  mov     rcx, [rcx]
0x14003f86e  mov     rbx, [r15+78h]
0x14003f872  mov     [r15+78h], rcx
0x14003f876  test    rcx, rcx
0x14003f879  jz      short loc_14003F887
0x14003f87b  mov     rax, [rcx]
0x14003f87e  mov     rax, [rax+8]
0x14003f882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f887  test    rbx, rbx
0x14003f88a  jz      short loc_14003F89C
0x14003f88c  mov     rax, [rbx]
0x14003f88f  mov     rcx, rbx
0x14003f892  mov     rax, [rax+10h]
0x14003f896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f89b  nop
0x14003f89c  movups  xmm0, xmmword ptr [r13+0]
0x14003f8a1  movdqu  xmmword ptr [rbp+47h+rguid.Data1], xmm0
0x14003f8a6  lea     rcx, [rbp+47h+rguid]; rguid
0x14003f8aa  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x14003f8af  mov     ebx, eax
0x14003f8b1  test    eax, eax
0x14003f8b3  jns     short loc_14003F8EB
0x14003f8b5  mov     rcx, [rbp+4Fh]; this
0x14003f8b9  mov     r9d, eax; char *
0x14003f8bc  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003f8c3  mov     edx, 2Ch ; ','; void *
0x14003f8c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f8cd  nop
0x14003f8ce  mov     rcx, [rbp+47h+var_A0]
0x14003f8d2  test    rcx, rcx
0x14003f8d5  jz      short loc_14003F8E4
0x14003f8d7  mov     rax, [rcx]
0x14003f8da  mov     rax, [rax+10h]
0x14003f8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f8e3  nop
0x14003f8e4  mov     eax, ebx
0x14003f8e6  jmp     loc_14003FBBC
0x14003f8eb  mov     r8d, 2
0x14003f8f1  mov     rsi, [rbp+47h+var_98]
0x14003f8f5  mov     rdx, rsi
0x14003f8f8  mov     rcx, r15
0x14003f8fb  call    ?Initialize@CMidiPipe@@UEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidiPipe::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x14003f900  mov     ebx, eax
0x14003f902  test    eax, eax
0x14003f904  jns     short loc_14003F937
0x14003f906  mov     rcx, [rbp+4Fh]; this
0x14003f90a  mov     r9d, eax; char *
0x14003f90d  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003f914  mov     edx, 30h ; '0'; void *
0x14003f919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f91e  nop
0x14003f91f  mov     rcx, [rbp+47h+var_A0]
0x14003f923  test    rcx, rcx
0x14003f926  jz      short loc_14003F935
0x14003f928  mov     rax, [rcx]
0x14003f92b  mov     rax, [rax+10h]
0x14003f92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f934  nop
0x14003f935  jmp     short loc_14003F8E4
0x14003f937  mov     rax, [r15]
0x14003f93a  mov     edx, [r12+10h]
0x14003f93f  mov     rcx, r15
0x14003f942  mov     rax, [rax+50h]
0x14003f946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f94b  mov     ebx, eax
0x14003f94d  test    eax, eax
0x14003f94f  jns     short loc_14003F985
0x14003f951  mov     rcx, [rbp+4Fh]; this
0x14003f955  mov     r9d, eax; char *
0x14003f958  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003f95f  mov     edx, 32h ; '2'; void *
0x14003f964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f969  nop
0x14003f96a  mov     rcx, [rbp+47h+var_A0]
0x14003f96e  test    rcx, rcx
0x14003f971  jz      short loc_14003F980
0x14003f973  mov     rax, [rcx]
0x14003f976  mov     rax, [rax+10h]
0x14003f97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f97f  nop
0x14003f980  jmp     loc_14003F8E4
0x14003f985  mov     rax, [r15]
0x14003f988  mov     edx, [r12+14h]
0x14003f98d  mov     rcx, r15
0x14003f990  mov     rax, [rax+58h]
0x14003f994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f999  mov     ebx, eax
0x14003f99b  test    eax, eax
0x14003f99d  jns     short loc_14003F9D3
0x14003f99f  mov     rcx, [rbp+4Fh]; this
0x14003f9a3  mov     r9d, eax; char *
0x14003f9a6  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003f9ad  mov     edx, 33h ; '3'; void *
0x14003f9b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f9b7  nop
0x14003f9b8  mov     rcx, [rbp+47h+var_A0]
0x14003f9bc  test    rcx, rcx
0x14003f9bf  jz      short loc_14003F9CE
0x14003f9c1  mov     rax, [rcx]
0x14003f9c4  mov     rax, [rax+10h]
0x14003f9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f9cd  nop
0x14003f9ce  jmp     loc_14003F8E4
0x14003f9d3  mov     rcx, [rbp+47h+var_A0]
0x14003f9d7  mov     [rbp+47h+var_A0], 0
0x14003f9df  test    rcx, rcx
0x14003f9e2  jz      short loc_14003F9F1
0x14003f9e4  mov     rax, [rcx]
0x14003f9e7  mov     rax, [rax+10h]
0x14003f9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f9f0  nop
0x14003f9f1  lea     rax, [rbp+47h+var_A0]
0x14003f9f5  mov     [rsp+0E0h+ppv], rax; int
0x14003f9fa  lea     r9, _GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d; riid
0x14003fa01  xor     edx, edx; pUnkOuter
0x14003fa03  lea     r8d, [rdx+17h]; dwClsContext
0x14003fa07  mov     rcx, r13; rclsid
0x14003fa0a  call    cs:__imp_CoCreateInstance
0x14003fa10  mov     ebx, eax
0x14003fa12  test    eax, eax
0x14003fa14  jns     short loc_14003FA4A
0x14003fa16  mov     rcx, [rbp+4Fh]; this
0x14003fa1a  mov     r9d, eax; char *
0x14003fa1d  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003fa24  mov     edx, 35h ; '5'; void *
0x14003fa29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fa2e  nop
0x14003fa2f  mov     rcx, [rbp+47h+var_A0]
0x14003fa33  test    rcx, rcx
0x14003fa36  jz      short loc_14003FA45
0x14003fa38  mov     rax, [rcx]
0x14003fa3b  mov     rax, [rax+10h]
0x14003fa3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fa44  nop
0x14003fa45  jmp     loc_14003F8E4
0x14003fa4a  mov     rbx, [rbp+47h+var_A0]
0x14003fa4e  mov     rax, [rbx]
0x14003fa51  mov     r14, [rax+18h]
0x14003fa55  lea     rdi, [r15+80h]
0x14003fa5c  mov     rcx, [rdi]
0x14003fa5f  mov     qword ptr [rdi], 0
0x14003fa66  test    rcx, rcx
0x14003fa69  jz      short loc_14003FA78
0x14003fa6b  mov     rdx, [rcx]
0x14003fa6e  mov     rax, [rdx+10h]
0x14003fa72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fa77  nop
0x14003fa78  mov     r8, rdi
0x14003fa7b  lea     rdx, _GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4
0x14003fa82  mov     rcx, rbx
0x14003fa85  mov     rax, r14
0x14003fa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fa8d  mov     ebx, eax
0x14003fa8f  test    eax, eax
0x14003fa91  jns     short loc_14003FAC7
0x14003fa93  mov     rcx, [rbp+4Fh]; this
0x14003fa97  mov     r9d, eax; char *
0x14003fa9a  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003faa1  mov     edx, 36h ; '6'; void *
0x14003faa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003faab  nop
0x14003faac  mov     rcx, [rbp+47h+var_A0]
0x14003fab0  test    rcx, rcx
0x14003fab3  jz      short loc_14003FAC2
0x14003fab5  mov     rax, [rcx]
0x14003fab8  mov     rax, [rax+10h]
0x14003fabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fac1  nop
0x14003fac2  jmp     loc_14003F8E4
0x14003fac7  mov     eax, [r15+30h]
0x14003facb  mov     dword ptr [rbp+47h+var_50], eax
0x14003face  mov     eax, [r15+34h]
0x14003fad2  mov     dword ptr [rbp+47h+var_50+4], eax
0x14003fad5  movzx   edx, byte ptr [r12+1Ch]
0x14003fadb  mov     byte ptr [rbp+47h+var_48], dl
0x14003fade  mov     rcx, [rdi]
0x14003fae1  mov     rax, [rcx]
0x14003fae4  mov     r8, [rbp+47h+var_90]
0x14003fae8  mov     [rsp+0E0h+var_B0], r8
0x14003faed  mov     [rsp+0E0h+var_B8], rdx
0x14003faf2  mov     [rsp+0E0h+ppv], r15; int
0x14003faf7  mov     r9, [rbp+47h+var_88]
0x14003fafb  lea     r8, [rbp+47h+var_50]
0x14003faff  mov     rdx, rsi
0x14003fb02  mov     rax, [rax+18h]
0x14003fb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb0b  mov     ebx, eax
0x14003fb0d  test    eax, eax
0x14003fb0f  jns     short loc_14003FB45
0x14003fb11  mov     rcx, [rbp+4Fh]; this
0x14003fb15  mov     r9d, eax; char *
0x14003fb18  lea     r8, aAvcoreMidi2Ser_8; "avcore\\midi2\\service\\exe\\miditransf"...
0x14003fb1f  mov     edx, 3Dh ; '='; void *
0x14003fb24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fb29  nop
0x14003fb2a  mov     rcx, [rbp+47h+var_A0]
0x14003fb2e  test    rcx, rcx
0x14003fb31  jz      short loc_14003FB40
0x14003fb33  mov     rax, [rcx]
0x14003fb36  mov     rax, [rax+10h]
0x14003fb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb3f  nop
0x14003fb40  jmp     loc_14003F8E4
0x14003fb45  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003fb4a  mov     rcx, [rax+8]
0x14003fb4e  mov     eax, [rcx]
0x14003fb50  cmp     eax, 4
0x14003fb53  jbe     short loc_14003FBA4
0x14003fb55  mov     [rbp+47h+var_88], rsi
0x14003fb59  lea     rax, aExitSuccess_0; "Exit success"
0x14003fb60  mov     [rbp+47h+var_90], rax
0x14003fb64  mov     [rbp+47h+var_98], r15
0x14003fb68  lea     rax, aCmiditransform; "CMidiTransformPipe::Initialize"
0x14003fb6f  mov     qword ptr [rbp+47h+rguid.Data1], rax
0x14003fb73  lea     rax, [rbp+47h+var_88]
0x14003fb77  mov     [rsp+0E0h+var_A8], rax
0x14003fb7c  lea     rax, [rbp+47h+var_90]
0x14003fb80  mov     [rsp+0E0h+var_B0], rax
0x14003fb85  lea     rax, [rbp+47h+var_98]
0x14003fb89  mov     [rsp+0E0h+var_B8], rax
0x14003fb8e  lea     rax, [rbp+47h+rguid]
0x14003fb92  mov     [rsp+0E0h+ppv], rax
0x14003fb97  lea     rdx, byte_14008B445
0x14003fb9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003fba3  nop
  ... truncated ...
```
