# MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances

- ea: `0x180068464`
- end: `0x180068a03`
- name: `MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances`
- size: `1439`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180067c20`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004eac`
- `0x180004f8c`
- `0x180004fc4`
- `0x180004ffc`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180068464`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180068776`
- `msvcrt!_wtoi` at `0x1800687b7`
- `msvcrt!_wtoi` at `0x1800687f8`
- `msvcrt!_wtoi` at `0x180068839`
- `msvcrt!_wtoi` at `0x1800688ec`
- `msvcrt!_wtoi` at `0x180068776`
- `msvcrt!_wtoi` at `0x1800687b7`
- `msvcrt!_wtoi` at `0x1800687f8`
- `msvcrt!_wtoi` at `0x180068839`
- `msvcrt!_wtoi` at `0x1800688ec`

## string_xrefs

- `0x1800687d4`: `AllowPrepairing`
- `0x18006888f`: `ServicesAllowedList`
- `0x1800686b8`: `./Vendor/MSFT/Policy/Config`
- `0x1800684df`: `MDM_Policy_Config01_Bluetooth02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Bluetooth02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-148h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Bluetooth02_NodeList,
           9u,
           2,
           &v14);
    if ( !v7 )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = v14;
          if ( v14 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v14;
            if ( v14 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Bluetooth02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_67;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAdvertising",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDiscoverableMode",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPrepairing",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPromptedProximalConnections",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LocalDeviceName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ServicesAllowedList",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
            v6 = v14;
            if ( v14 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
              v14 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
      }
    }
  }
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = 1;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = 1;
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
  return v7;
}

```

## disassembly

```asm
0x180068464  mov     [rsp+arg_8], rbx
0x180068469  mov     [rsp+arg_10], rsi
0x18006846e  push    rdi
0x18006846f  push    r12
0x180068471  push    r13
0x180068473  push    r14
0x180068475  push    r15
0x180068477  sub     rsp, 170h
0x18006847e  mov     rax, cs:__security_cookie
0x180068485  xor     rax, rsp
0x180068488  mov     [rsp+198h+var_38], rax
0x180068490  mov     r13b, dl
0x180068493  mov     r12, rcx
0x180068496  xor     edx, edx; Val
0x180068498  mov     r8d, 0A8h; Size
0x18006849e  lea     rcx, [rsp+198h+instance]; void *
0x1800684a6  call    memset_0
0x1800684ab  xor     edi, edi
0x1800684ad  mov     [rsp+198h+var_158], dil
0x1800684b2  mov     [rsp+198h+String], rdi
0x1800684b7  mov     [rsp+198h+var_110], edi
0x1800684be  mov     [rsp+198h+var_10C], dil
0x1800684c6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800684cd  mov     [rsp+198h+var_140], rax
0x1800684d2  lea     rax, [rsp+198h+var_110]
0x1800684da  mov     [rsp+198h+var_138], rax
0x1800684df  lea     rax, aMdmPolicyConfi_105; "MDM_Policy_Config01_Bluetooth02"
0x1800684e6  mov     [rsp+198h+var_130], rax
0x1800684eb  lea     rcx, [rsp+198h+var_110]
0x1800684f3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800684f8  mov     eax, cs:dword_180380B68
0x1800684fe  cmp     eax, 5
0x180068501  jbe     short loc_180068573
0x180068503  mov     rdx, 200000000000h
0x18006850d  lea     rcx, dword_180380B68
0x180068514  call    _tlgKeywordOn
0x180068519  test    al, al
0x18006851b  jz      short loc_180068573
0x18006851d  cmp     [rsp+198h+var_10C], dil
0x180068525  jz      short loc_180068555
0x180068527  cmp     [rsp+198h+var_F8], edi
0x18006852e  jnz     short loc_18006854B
0x180068530  cmp     [rsp+198h+var_F4], edi
0x180068537  jnz     short loc_18006854B
0x180068539  cmp     [rsp+198h+var_F0], edi
0x180068540  jnz     short loc_18006854B
0x180068542  cmp     [rsp+198h+var_EC], edi
0x180068549  jz      short loc_180068555
0x18006854b  lea     r9, [rsp+198h+var_F8]
0x180068553  jmp     short loc_180068558
0x180068555  mov     r9, rdi
0x180068558  lea     r8, [rsp+198h+var_108]
0x180068560  lea     rdx, byte_180368945
0x180068567  lea     rcx, dword_180380B68
0x18006856e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180068573  lea     rcx, [rsp+198h+var_140]; this
0x180068578  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18006857d  nop
0x18006857e  mov     [rsp+198h+var_148], rdi
0x180068583  lea     rax, [rsp+198h+var_148]
0x180068588  mov     [rsp+198h+var_168], rax
0x18006858d  mov     [rsp+198h+var_170], 2
0x180068595  mov     [rsp+198h+var_178], 9
0x18006859d  lea     r9, ?MDM_Policy_Config01_Bluetooth02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Bluetooth02_NodeList
0x1800685a4  xor     r8d, r8d
0x1800685a7  xor     edx, edx
0x1800685a9  mov     rcx, r12
0x1800685ac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800685b1  mov     r14d, eax
0x1800685b4  test    eax, eax
0x1800685b6  jz      short loc_1800685BD
0x1800685b8  jmp     loc_180068963
0x1800685bd  lea     rbx, [rsp+198h+var_148]
0x1800685c2  mov     [rsp+198h+var_120], rbx
0x1800685c7  mov     r15d, 1
0x1800685cd  mov     [rsp+198h+var_118], r15b
0x1800685d5  mov     rsi, [rsp+198h+var_148]
0x1800685da  test    rsi, rsi
0x1800685dd  jnz     short loc_1800685E7
0x1800685df  mov     r14d, r15d
0x1800685e2  jmp     loc_180068963
0x1800685e7  mov     rax, [rsi]
0x1800685ea  mov     rcx, rsi
0x1800685ed  mov     rax, [rax+10h]
0x1800685f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685f6  mov     r14d, eax
0x1800685f9  test    eax, eax
0x1800685fb  jz      short loc_18006861B
0x1800685fd  mov     rcx, [rsp+198h+var_148]
0x180068602  test    rcx, rcx
0x180068605  jz      short loc_180068616
0x180068607  mov     rax, [rcx]
0x18006860a  mov     edx, r15d
0x18006860d  mov     rax, [rax]
0x180068610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068615  nop
0x180068616  jmp     loc_180068963
0x18006861b  mov     rax, [rsi]
0x18006861e  mov     rcx, rsi
0x180068621  mov     rax, [rax+8]
0x180068625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006862a  mov     r14d, eax
0x18006862d  test    eax, eax
0x18006862f  jz      short loc_18006864F
0x180068631  mov     rcx, [rsp+198h+var_148]
0x180068636  test    rcx, rcx
0x180068639  jz      short loc_18006864A
0x18006863b  mov     rax, [rcx]
0x18006863e  mov     edx, r15d
0x180068641  mov     rax, [rax]
0x180068644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068649  nop
0x18006864a  jmp     loc_180068963
0x18006864f  mov     r15d, edi
0x180068652  mov     rax, [rsi+108h]
0x180068659  sub     rax, [rsi+100h]
0x180068660  sar     rax, 4
0x180068664  cmp     r15d, eax
0x180068667  jnb     loc_18006892B
0x18006866d  lea     r8, [rsp+198h+instance]; instance
0x180068675  lea     rdx, MDM_Policy_Config01_Bluetooth02_rtti; classDecl
0x18006867c  mov     rcx, r12; context
0x18006867f  call    MI_Context_ConstructInstance
0x180068684  mov     r14d, eax
0x180068687  test    eax, eax
0x180068689  jz      short loc_1800686AB
0x18006868b  mov     rcx, [rbx]
0x18006868e  test    rcx, rcx
0x180068691  jz      short loc_1800686A6
0x180068693  mov     rax, [rcx]
0x180068696  mov     edx, 1
0x18006869b  mov     rax, [rax]
0x18006869e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686a3  mov     [rbx], rdi
0x1800686a6  jmp     loc_180068963
0x1800686ab  mov     [rsp+198h+var_158], 1
0x1800686b0  mov     rax, [rsi]
0x1800686b3  lea     r9, [rsp+198h+String]
0x1800686b8  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800686bf  mov     edx, r15d
0x1800686c2  mov     rcx, rsi
0x1800686c5  mov     rax, [rax+18h]
0x1800686c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686ce  test    eax, eax
0x1800686d0  jnz     short loc_1800686E9
0x1800686d2  mov     rdx, [rsp+198h+String]
0x1800686d7  test    rdx, rdx
0x1800686da  jz      short loc_1800686E9
0x1800686dc  lea     rcx, [rsp+198h+instance]
0x1800686e4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800686e9  mov     rax, [rsi]
0x1800686ec  lea     r9, [rsp+198h+String]
0x1800686f1  lea     r8, aBluetooth; "Bluetooth"
0x1800686f8  mov     edx, r15d
0x1800686fb  mov     rcx, rsi
0x1800686fe  mov     rax, [rax+18h]
0x180068702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068707  test    eax, eax
0x180068709  jnz     short loc_180068722
0x18006870b  mov     rdx, [rsp+198h+String]
0x180068710  test    rdx, rdx
0x180068713  jz      short loc_180068722
0x180068715  lea     rcx, [rsp+198h+instance]
0x18006871d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180068722  cmp     r13b, 1
0x180068726  jnz     short loc_18006874A
0x180068728  lea     rdx, [rsp+198h+instance]
0x180068730  mov     rcx, r12; self
0x180068733  call    MI_Instance_Destruct
0x180068738  lea     rcx, [rsp+198h+instance]; self
0x180068740  call    MI_Instance_Destruct
0x180068745  jmp     loc_18006891E
0x18006874a  mov     rax, [rsi]
0x18006874d  lea     r9, [rsp+198h+String]
0x180068752  lea     r8, aAllowadvertisi; "AllowAdvertising"
0x180068759  mov     edx, r15d
0x18006875c  mov     rcx, rsi
0x18006875f  mov     rax, [rax+18h]
0x180068763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068768  test    eax, eax
0x18006876a  jnz     short loc_18006878B
0x18006876c  mov     rcx, [rsp+198h+String]; String
0x180068771  test    rcx, rcx
0x180068774  jz      short loc_18006878B
0x180068776  call    cs:__imp__wtoi
0x18006877c  mov     [rsp+198h+var_88], eax
0x180068783  mov     [rsp+198h+var_84], 1
0x18006878b  mov     rax, [rsi]
0x18006878e  lea     r9, [rsp+198h+String]
0x180068793  lea     r8, aAllowdiscovera; "AllowDiscoverableMode"
0x18006879a  mov     edx, r15d
0x18006879d  mov     rcx, rsi
0x1800687a0  mov     rax, [rax+18h]
0x1800687a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687a9  test    eax, eax
0x1800687ab  jnz     short loc_1800687CC
0x1800687ad  mov     rcx, [rsp+198h+String]; String
0x1800687b2  test    rcx, rcx
0x1800687b5  jz      short loc_1800687CC
0x1800687b7  call    cs:__imp__wtoi
0x1800687bd  mov     [rsp+198h+var_80], eax
0x1800687c4  mov     [rsp+198h+var_7C], 1
0x1800687cc  mov     rax, [rsi]
0x1800687cf  lea     r9, [rsp+198h+String]
0x1800687d4  lea     r8, aAllowprepairin; "AllowPrepairing"
0x1800687db  mov     edx, r15d
0x1800687de  mov     rcx, rsi
0x1800687e1  mov     rax, [rax+18h]
0x1800687e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687ea  test    eax, eax
0x1800687ec  jnz     short loc_18006880D
0x1800687ee  mov     rcx, [rsp+198h+String]; String
0x1800687f3  test    rcx, rcx
0x1800687f6  jz      short loc_18006880D
0x1800687f8  call    cs:__imp__wtoi
0x1800687fe  mov     [rsp+198h+var_78], eax
0x180068805  mov     [rsp+198h+var_74], 1
0x18006880d  mov     rax, [rsi]
0x180068810  lea     r9, [rsp+198h+String]
0x180068815  lea     r8, aAllowpromptedp; "AllowPromptedProximalConnections"
0x18006881c  mov     edx, r15d
0x18006881f  mov     rcx, rsi
0x180068822  mov     rax, [rax+18h]
0x180068826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006882b  test    eax, eax
0x18006882d  jnz     short loc_18006884E
0x18006882f  mov     rcx, [rsp+198h+String]; String
0x180068834  test    rcx, rcx
0x180068837  jz      short loc_18006884E
0x180068839  call    cs:__imp__wtoi
0x18006883f  mov     [rsp+198h+var_70], eax
0x180068846  mov     [rsp+198h+var_6C], 1
0x18006884e  mov     rax, [rsi]
0x180068851  lea     r9, [rsp+198h+String]
0x180068856  lea     r8, aLocaldevicenam; "LocalDeviceName"
0x18006885d  mov     edx, r15d
0x180068860  mov     rcx, rsi
0x180068863  mov     rax, [rax+18h]
0x180068867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006886c  test    eax, eax
0x18006886e  jnz     short loc_180068887
0x180068870  mov     rdx, [rsp+198h+String]
0x180068875  test    rdx, rdx
0x180068878  jz      short loc_180068887
0x18006887a  lea     rcx, [rsp+198h+instance]
0x180068882  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x180068887  mov     rax, [rsi]
0x18006888a  lea     r9, [rsp+198h+String]
0x18006888f  lea     r8, aServicesallowe; "ServicesAllowedList"
0x180068896  mov     edx, r15d
0x180068899  mov     rcx, rsi
0x18006889c  mov     rax, [rax+18h]
0x1800688a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688a5  test    eax, eax
0x1800688a7  jnz     short loc_1800688C0
0x1800688a9  mov     rdx, [rsp+198h+String]
0x1800688ae  test    rdx, rdx
0x1800688b1  jz      short loc_1800688C0
0x1800688b3  lea     rcx, [rsp+198h+instance]
0x1800688bb  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800688c0  mov     rax, [rsi]
0x1800688c3  lea     r9, [rsp+198h+String]
0x1800688c8  lea     r8, aSetminimumencr; "SetMinimumEncryptionKeySize"
0x1800688cf  mov     edx, r15d
0x1800688d2  mov     rcx, rsi
0x1800688d5  mov     rax, [rax+18h]
0x1800688d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688de  test    eax, eax
0x1800688e0  jnz     short loc_180068901
0x1800688e2  mov     rcx, [rsp+198h+String]; String
0x1800688e7  test    rcx, rcx
0x1800688ea  jz      short loc_180068901
0x1800688ec  call    cs:__imp__wtoi
0x1800688f2  mov     [rsp+198h+var_48], eax
0x1800688f9  mov     [rsp+198h+var_44], 1
0x180068901  lea     rdx, [rsp+198h+instance]
0x180068909  mov     rcx, r12; self
0x18006890c  call    MI_Instance_Destruct
0x180068911  lea     rcx, [rsp+198h+instance]; self
0x180068919  call    MI_Instance_Destruct
0x18006891e  mov     [rsp+198h+var_158], dil
0x180068923  inc     r15d
0x180068926  jmp     loc_180068652
0x18006892b  mov     rcx, [rbx]
0x18006892e  test    rcx, rcx
0x180068931  jz      short loc_180068946
0x180068933  mov     rax, [rcx]
0x180068936  mov     edx, 1
0x18006893b  mov     rax, [rax]
0x18006893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068943  mov     [rbx], rdi
0x180068946  jmp     short loc_180068963
0x180068948  xor     edi, edi
0x18006894a  cmp     [rsp+198h+var_158], dil
0x18006894f  jz      short loc_18006895E
0x180068951  lea     rcx, [rsp+198h+instance]; self
0x180068959  call    MI_Instance_Destruct
0x18006895e  mov     r14d, dword ptr [rsp+198h+var_148]
0x180068963  mov     r8d, r14d; int
0x180068966  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
  ... truncated ...
```
