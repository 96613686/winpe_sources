# MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances

- ea: `0x180067c48`
- end: `0x180068206`
- name: `MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances`
- size: `1470`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180067420`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005080`
- `0x180005160`
- `0x180005198`
- `0x1800051d0`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180067c48`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180067f5a`
- `msvcrt!_wtoi` at `0x180067fa1`
- `msvcrt!_wtoi` at `0x180067fe8`
- `msvcrt!_wtoi` at `0x18006802f`
- `msvcrt!_wtoi` at `0x1800680e8`
- `msvcrt!_wtoi` at `0x180067f5a`
- `msvcrt!_wtoi` at `0x180067fa1`
- `msvcrt!_wtoi` at `0x180067fe8`
- `msvcrt!_wtoi` at `0x18006802f`
- `msvcrt!_wtoi` at `0x1800680e8`

## string_xrefs

- `0x180067fc4`: `AllowPrepairing`
- `0x18006808b`: `ServicesAllowedList`
- `0x180067e9c`: `./Vendor/MSFT/Policy/Config`
- `0x180067cc3`: `MDM_Policy_Config01_Bluetooth02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-140h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-128h] BYREF
  char v17; // [rsp+80h] [rbp-118h]
  int v18; // [rsp+88h] [rbp-110h] BYREF
  char v19; // [rsp+8Ch] [rbp-10Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-108h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-F8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-E8h] BYREF
  int v23; // [rsp+110h] [rbp-88h]
  char v24; // [rsp+114h] [rbp-84h]
  int v25; // [rsp+118h] [rbp-80h]
  char v26; // [rsp+11Ch] [rbp-7Ch]
  int v27; // [rsp+120h] [rbp-78h]
  char v28; // [rsp+124h] [rbp-74h]
  int v29; // [rsp+128h] [rbp-70h]
  char v30; // [rsp+12Ch] [rbp-6Ch]
  int v31; // [rsp+150h] [rbp-48h]
  char v32; // [rsp+154h] [rbp-44h]

  memset_0(&instance, 0, 0xA8u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_Bluetooth02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180368945,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Bluetooth02_NodeList, 9, 2, &v14);
    if ( v7 == MI_RESULT_OK )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = (wil *)v14;
          if ( v14 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v14;
            if ( v14 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Bluetooth02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_67;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"Bluetooth",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAdvertising",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDiscoverableMode",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPrepairing",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPromptedProximalConnections",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LocalDeviceName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ServicesAllowedList",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SetMinimumEncryptionKeySize",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
            }
            v6 = (wil *)v14;
            if ( v14 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
              v14 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
  }
LABEL_67:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18034C74E,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067c48  mov     [rsp+arg_8], rbx
0x180067c4d  mov     [rsp+arg_10], rsi
0x180067c52  push    rdi
0x180067c53  push    r12
0x180067c55  push    r13
0x180067c57  push    r14
0x180067c59  push    r15
0x180067c5b  sub     rsp, 170h
0x180067c62  mov     rax, cs:__security_cookie
0x180067c69  xor     rax, rsp
0x180067c6c  mov     [rsp+198h+var_38], rax
0x180067c74  mov     r13b, dl
0x180067c77  mov     r12, rcx
0x180067c7a  xor     edx, edx; Val
0x180067c7c  mov     r8d, 0A8h; Size
0x180067c82  lea     rcx, [rsp+198h+instance]; void *
0x180067c8a  call    memset_0
0x180067c8f  xor     edi, edi
0x180067c91  mov     [rsp+198h+var_158], dil
0x180067c96  mov     [rsp+198h+String], rdi
0x180067c9b  mov     [rsp+198h+var_110], edi
0x180067ca2  mov     [rsp+198h+var_10C], dil
0x180067caa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180067cb1  mov     [rsp+198h+var_140], rax
0x180067cb6  lea     rax, [rsp+198h+var_110]
0x180067cbe  mov     [rsp+198h+var_138], rax
0x180067cc3  lea     rax, aMdmPolicyConfi_105; "MDM_Policy_Config01_Bluetooth02"
0x180067cca  mov     [rsp+198h+var_130], rax
0x180067ccf  lea     rcx, [rsp+198h+var_110]
0x180067cd7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180067cdc  mov     eax, cs:dword_180380B68
0x180067ce2  cmp     eax, 5
0x180067ce5  jbe     short loc_180067D57
0x180067ce7  mov     rdx, 200000000000h
0x180067cf1  lea     rcx, dword_180380B68
0x180067cf8  call    _tlgKeywordOn
0x180067cfd  test    al, al
0x180067cff  jz      short loc_180067D57
0x180067d01  cmp     [rsp+198h+var_10C], dil
0x180067d09  jz      short loc_180067D39
0x180067d0b  cmp     [rsp+198h+var_F8], edi
0x180067d12  jnz     short loc_180067D2F
0x180067d14  cmp     [rsp+198h+var_F4], edi
0x180067d1b  jnz     short loc_180067D2F
0x180067d1d  cmp     [rsp+198h+var_F0], edi
0x180067d24  jnz     short loc_180067D2F
0x180067d26  cmp     [rsp+198h+var_EC], edi
0x180067d2d  jz      short loc_180067D39
0x180067d2f  lea     r9, [rsp+198h+var_F8]
0x180067d37  jmp     short loc_180067D3C
0x180067d39  mov     r9, rdi
0x180067d3c  lea     r8, [rsp+198h+var_108]
0x180067d44  lea     rdx, byte_180368945
0x180067d4b  lea     rcx, dword_180380B68
0x180067d52  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180067d57  lea     rcx, [rsp+198h+var_140]; this
0x180067d5c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180067d61  nop
0x180067d62  mov     [rsp+198h+var_148], rdi
0x180067d67  lea     rax, [rsp+198h+var_148]
0x180067d6c  mov     [rsp+198h+var_168], rax
0x180067d71  mov     [rsp+198h+var_170], 2
0x180067d79  mov     [rsp+198h+var_178], 9
0x180067d81  lea     r9, ?MDM_Policy_Config01_Bluetooth02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Bluetooth02_NodeList
0x180067d88  xor     r8d, r8d
0x180067d8b  xor     edx, edx
0x180067d8d  mov     rcx, r12
0x180067d90  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180067d95  mov     r14d, eax
0x180067d98  test    eax, eax
0x180067d9a  jz      short loc_180067DA1
0x180067d9c  jmp     loc_180068165
0x180067da1  lea     rbx, [rsp+198h+var_148]
0x180067da6  mov     [rsp+198h+var_120], rbx
0x180067dab  mov     r15d, 1
0x180067db1  mov     [rsp+198h+var_118], r15b
0x180067db9  mov     rsi, [rsp+198h+var_148]
0x180067dbe  test    rsi, rsi
0x180067dc1  jnz     short loc_180067DCB
0x180067dc3  mov     r14d, r15d
0x180067dc6  jmp     loc_180068165
0x180067dcb  mov     rax, [rsi]
0x180067dce  mov     rcx, rsi
0x180067dd1  mov     rax, [rax+10h]
0x180067dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dda  mov     r14d, eax
0x180067ddd  test    eax, eax
0x180067ddf  jz      short loc_180067DFF
0x180067de1  mov     rcx, [rsp+198h+var_148]
0x180067de6  test    rcx, rcx
0x180067de9  jz      short loc_180067DFA
0x180067deb  mov     rax, [rcx]
0x180067dee  mov     edx, r15d
0x180067df1  mov     rax, [rax]
0x180067df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067df9  nop
0x180067dfa  jmp     loc_180068165
0x180067dff  mov     rax, [rsi]
0x180067e02  mov     rcx, rsi
0x180067e05  mov     rax, [rax+8]
0x180067e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e0e  mov     r14d, eax
0x180067e11  test    eax, eax
0x180067e13  jz      short loc_180067E33
0x180067e15  mov     rcx, [rsp+198h+var_148]
0x180067e1a  test    rcx, rcx
0x180067e1d  jz      short loc_180067E2E
0x180067e1f  mov     rax, [rcx]
0x180067e22  mov     edx, r15d
0x180067e25  mov     rax, [rax]
0x180067e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e2d  nop
0x180067e2e  jmp     loc_180068165
0x180067e33  mov     r15d, edi
0x180067e36  mov     rax, [rsi+108h]
0x180067e3d  sub     rax, [rsi+100h]
0x180067e44  sar     rax, 4
0x180067e48  cmp     r15d, eax
0x180067e4b  jnb     loc_18006812D
0x180067e51  lea     r8, [rsp+198h+instance]; instance
0x180067e59  lea     rdx, MDM_Policy_Config01_Bluetooth02_rtti; classDecl
0x180067e60  mov     rcx, r12; context
0x180067e63  call    MI_Context_ConstructInstance
0x180067e68  mov     r14d, eax
0x180067e6b  test    eax, eax
0x180067e6d  jz      short loc_180067E8F
0x180067e6f  mov     rcx, [rbx]
0x180067e72  test    rcx, rcx
0x180067e75  jz      short loc_180067E8A
0x180067e77  mov     rax, [rcx]
0x180067e7a  mov     edx, 1
0x180067e7f  mov     rax, [rax]
0x180067e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e87  mov     [rbx], rdi
0x180067e8a  jmp     loc_180068165
0x180067e8f  mov     [rsp+198h+var_158], 1
0x180067e94  mov     rax, [rsi]
0x180067e97  lea     r9, [rsp+198h+String]
0x180067e9c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180067ea3  mov     edx, r15d
0x180067ea6  mov     rcx, rsi
0x180067ea9  mov     rax, [rax+18h]
0x180067ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067eb2  test    eax, eax
0x180067eb4  jnz     short loc_180067ECD
0x180067eb6  mov     rdx, [rsp+198h+String]
0x180067ebb  test    rdx, rdx
0x180067ebe  jz      short loc_180067ECD
0x180067ec0  lea     rcx, [rsp+198h+instance]
0x180067ec8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180067ecd  mov     rax, [rsi]
0x180067ed0  lea     r9, [rsp+198h+String]
0x180067ed5  lea     r8, aBluetooth; "Bluetooth"
0x180067edc  mov     edx, r15d
0x180067edf  mov     rcx, rsi
0x180067ee2  mov     rax, [rax+18h]
0x180067ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067eeb  test    eax, eax
0x180067eed  jnz     short loc_180067F06
0x180067eef  mov     rdx, [rsp+198h+String]
0x180067ef4  test    rdx, rdx
0x180067ef7  jz      short loc_180067F06
0x180067ef9  lea     rcx, [rsp+198h+instance]
0x180067f01  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180067f06  cmp     r13b, 1
0x180067f0a  jnz     short loc_180067F2E
0x180067f0c  lea     rdx, [rsp+198h+instance]
0x180067f14  mov     rcx, r12; self
0x180067f17  call    MI_Instance_Destruct
0x180067f1c  lea     rcx, [rsp+198h+instance]; self
0x180067f24  call    MI_Instance_Destruct
0x180067f29  jmp     loc_180068120
0x180067f2e  mov     rax, [rsi]
0x180067f31  lea     r9, [rsp+198h+String]
0x180067f36  lea     r8, aAllowadvertisi; "AllowAdvertising"
0x180067f3d  mov     edx, r15d
0x180067f40  mov     rcx, rsi
0x180067f43  mov     rax, [rax+18h]
0x180067f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f4c  test    eax, eax
0x180067f4e  jnz     short loc_180067F75
0x180067f50  mov     rcx, [rsp+198h+String]; String
0x180067f55  test    rcx, rcx
0x180067f58  jz      short loc_180067F75
0x180067f5a  call    cs:__imp__wtoi
0x180067f61  nop     dword ptr [rax+rax+00h]
0x180067f66  mov     [rsp+198h+var_88], eax
0x180067f6d  mov     [rsp+198h+var_84], 1
0x180067f75  mov     rax, [rsi]
0x180067f78  lea     r9, [rsp+198h+String]
0x180067f7d  lea     r8, aAllowdiscovera; "AllowDiscoverableMode"
0x180067f84  mov     edx, r15d
0x180067f87  mov     rcx, rsi
0x180067f8a  mov     rax, [rax+18h]
0x180067f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f93  test    eax, eax
0x180067f95  jnz     short loc_180067FBC
0x180067f97  mov     rcx, [rsp+198h+String]; String
0x180067f9c  test    rcx, rcx
0x180067f9f  jz      short loc_180067FBC
0x180067fa1  call    cs:__imp__wtoi
0x180067fa8  nop     dword ptr [rax+rax+00h]
0x180067fad  mov     [rsp+198h+var_80], eax
0x180067fb4  mov     [rsp+198h+var_7C], 1
0x180067fbc  mov     rax, [rsi]
0x180067fbf  lea     r9, [rsp+198h+String]
0x180067fc4  lea     r8, aAllowprepairin; "AllowPrepairing"
0x180067fcb  mov     edx, r15d
0x180067fce  mov     rcx, rsi
0x180067fd1  mov     rax, [rax+18h]
0x180067fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fda  test    eax, eax
0x180067fdc  jnz     short loc_180068003
0x180067fde  mov     rcx, [rsp+198h+String]; String
0x180067fe3  test    rcx, rcx
0x180067fe6  jz      short loc_180068003
0x180067fe8  call    cs:__imp__wtoi
0x180067fef  nop     dword ptr [rax+rax+00h]
0x180067ff4  mov     [rsp+198h+var_78], eax
0x180067ffb  mov     [rsp+198h+var_74], 1
0x180068003  mov     rax, [rsi]
0x180068006  lea     r9, [rsp+198h+String]
0x18006800b  lea     r8, aAllowpromptedp; "AllowPromptedProximalConnections"
0x180068012  mov     edx, r15d
0x180068015  mov     rcx, rsi
0x180068018  mov     rax, [rax+18h]
0x18006801c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068021  test    eax, eax
0x180068023  jnz     short loc_18006804A
0x180068025  mov     rcx, [rsp+198h+String]; String
0x18006802a  test    rcx, rcx
0x18006802d  jz      short loc_18006804A
0x18006802f  call    cs:__imp__wtoi
0x180068036  nop     dword ptr [rax+rax+00h]
0x18006803b  mov     [rsp+198h+var_70], eax
0x180068042  mov     [rsp+198h+var_6C], 1
0x18006804a  mov     rax, [rsi]
0x18006804d  lea     r9, [rsp+198h+String]
0x180068052  lea     r8, aLocaldevicenam; "LocalDeviceName"
0x180068059  mov     edx, r15d
0x18006805c  mov     rcx, rsi
0x18006805f  mov     rax, [rax+18h]
0x180068063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068068  test    eax, eax
0x18006806a  jnz     short loc_180068083
0x18006806c  mov     rdx, [rsp+198h+String]
0x180068071  test    rdx, rdx
0x180068074  jz      short loc_180068083
0x180068076  lea     rcx, [rsp+198h+instance]
0x18006807e  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x180068083  mov     rax, [rsi]
0x180068086  lea     r9, [rsp+198h+String]
0x18006808b  lea     r8, aServicesallowe; "ServicesAllowedList"
0x180068092  mov     edx, r15d
0x180068095  mov     rcx, rsi
0x180068098  mov     rax, [rax+18h]
0x18006809c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680a1  test    eax, eax
0x1800680a3  jnz     short loc_1800680BC
0x1800680a5  mov     rdx, [rsp+198h+String]
0x1800680aa  test    rdx, rdx
0x1800680ad  jz      short loc_1800680BC
0x1800680af  lea     rcx, [rsp+198h+instance]
0x1800680b7  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800680bc  mov     rax, [rsi]
0x1800680bf  lea     r9, [rsp+198h+String]
0x1800680c4  lea     r8, aSetminimumencr; "SetMinimumEncryptionKeySize"
0x1800680cb  mov     edx, r15d
0x1800680ce  mov     rcx, rsi
0x1800680d1  mov     rax, [rax+18h]
0x1800680d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680da  test    eax, eax
0x1800680dc  jnz     short loc_180068103
0x1800680de  mov     rcx, [rsp+198h+String]; String
0x1800680e3  test    rcx, rcx
0x1800680e6  jz      short loc_180068103
0x1800680e8  call    cs:__imp__wtoi
0x1800680ef  nop     dword ptr [rax+rax+00h]
0x1800680f4  mov     [rsp+198h+var_48], eax
0x1800680fb  mov     [rsp+198h+var_44], 1
0x180068103  lea     rdx, [rsp+198h+instance]
0x18006810b  mov     rcx, r12; self
0x18006810e  call    MI_Instance_Destruct
0x180068113  lea     rcx, [rsp+198h+instance]; self
0x18006811b  call    MI_Instance_Destruct
0x180068120  mov     [rsp+198h+var_158], dil
0x180068125  inc     r15d
0x180068128  jmp     loc_180067E36
0x18006812d  mov     rcx, [rbx]
0x180068130  test    rcx, rcx
0x180068133  jz      short loc_180068148
0x180068135  mov     rax, [rcx]
0x180068138  mov     edx, 1
0x18006813d  mov     rax, [rax]
0x180068140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068145  mov     [rbx], rdi
0x180068148  jmp     short loc_180068165
0x18006814a  xor     edi, edi
0x18006814c  cmp     [rsp+198h+var_158], dil
0x180068151  jz      short loc_180068160
  ... truncated ...
```
