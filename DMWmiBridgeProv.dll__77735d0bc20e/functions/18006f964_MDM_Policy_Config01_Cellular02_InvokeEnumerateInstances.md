# MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances

- ea: `0x18006f964`
- end: `0x18006fe6b`
- name: `MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances`
- size: `1287`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x18006f1a0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004ee4`
- `0x180004f1c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18006f964`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18006fc72`
- `msvcrt!_wtoi` at `0x18006fc72`

## string_xrefs

- `0x18006fc4e`: `LetAppsAccessCellularData`
- `0x18006fc8f`: `LetAppsAccessCellularData_ForceAllowTheseApps`
- `0x18006fcc8`: `LetAppsAccessCellularData_ForceDenyTheseApps`
- `0x18006fd01`: `LetAppsAccessCellularData_UserInControlOfTheseApps`
- `0x18006fd3a`: `ShowAppCellularAccessUI`
- `0x18006fbb4`: `./Vendor/MSFT/Policy/Config`
- `0x18006f9df`: `MDM_Policy_Config01_Cellular02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // esi
  WmiRequestHandlerAdd *v7; // r14
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  WmiRequestHandlerAdd *v11; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-140h] BYREF
  char v13; // [rsp+80h] [rbp-118h]
  int v14; // [rsp+88h] [rbp-110h] BYREF
  char v15; // [rsp+8Ch] [rbp-10Ch]
  _BYTE v16[16]; // [rsp+90h] [rbp-108h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-F8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-E8h] BYREF
  int v19; // [rsp+110h] [rbp-88h]
  char v20; // [rsp+114h] [rbp-84h]

  memset_0(&instance, 0, 0xA8u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Config01_Cellular02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180333E35,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Cellular02_NodeList,
         7u,
         2,
         &v11);
  if ( !v6 )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Cellular02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_53;
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Config",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"Cellular",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_ForceAllowTheseApps",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_ForceDenyTheseApps",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_UserInControlOfTheseApps",
                      &String)
                && String )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ShowAppCellularAccessUI",
                      &String)
                && String )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
              }
            }
            MI_Instance_Destruct((MI_Instance *)self);
            MI_Instance_Destruct(&instance);
          }
          if ( v11 )
          {
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
    }
  }
LABEL_53:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033CA5C,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return v6;
}

```

## disassembly

```asm
0x18006f964  mov     [rsp+arg_8], rbx
0x18006f969  mov     [rsp+arg_10], rsi
0x18006f96e  push    rdi
0x18006f96f  push    r12
0x18006f971  push    r13
0x18006f973  push    r14
0x18006f975  push    r15
0x18006f977  sub     rsp, 170h
0x18006f97e  mov     rax, cs:__security_cookie
0x18006f985  xor     rax, rsp
0x18006f988  mov     [rsp+198h+var_38], rax
0x18006f990  mov     r13b, dl
0x18006f993  mov     r12, rcx
0x18006f996  xor     edx, edx; Val
0x18006f998  mov     r8d, 0A8h; Size
0x18006f99e  lea     rcx, [rsp+198h+instance]; void *
0x18006f9a6  call    memset_0
0x18006f9ab  xor     edi, edi
0x18006f9ad  mov     [rsp+198h+var_158], dil
0x18006f9b2  mov     [rsp+198h+String], rdi
0x18006f9b7  mov     [rsp+198h+var_110], edi
0x18006f9be  mov     [rsp+198h+var_10C], dil
0x18006f9c6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006f9cd  mov     [rsp+198h+var_140], rax
0x18006f9d2  lea     rax, [rsp+198h+var_110]
0x18006f9da  mov     [rsp+198h+var_138], rax
0x18006f9df  lea     rax, aMdmPolicyConfi_157; "MDM_Policy_Config01_Cellular02"
0x18006f9e6  mov     [rsp+198h+var_130], rax
0x18006f9eb  lea     rcx, [rsp+198h+var_110]
0x18006f9f3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18006f9f8  mov     eax, cs:dword_180380B68
0x18006f9fe  cmp     eax, 5
0x18006fa01  jbe     short loc_18006FA73
0x18006fa03  mov     rdx, 200000000000h
0x18006fa0d  lea     rcx, dword_180380B68
0x18006fa14  call    _tlgKeywordOn
0x18006fa19  test    al, al
0x18006fa1b  jz      short loc_18006FA73
0x18006fa1d  cmp     [rsp+198h+var_10C], dil
0x18006fa25  jz      short loc_18006FA55
0x18006fa27  cmp     [rsp+198h+var_F8], edi
0x18006fa2e  jnz     short loc_18006FA4B
0x18006fa30  cmp     [rsp+198h+var_F4], edi
0x18006fa37  jnz     short loc_18006FA4B
0x18006fa39  cmp     [rsp+198h+var_F0], edi
0x18006fa40  jnz     short loc_18006FA4B
0x18006fa42  cmp     [rsp+198h+var_EC], edi
0x18006fa49  jz      short loc_18006FA55
0x18006fa4b  lea     r9, [rsp+198h+var_F8]
0x18006fa53  jmp     short loc_18006FA58
0x18006fa55  mov     r9, rdi
0x18006fa58  lea     r8, [rsp+198h+var_108]
0x18006fa60  lea     rdx, byte_180333E35
0x18006fa67  lea     rcx, dword_180380B68
0x18006fa6e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006fa73  lea     rcx, [rsp+198h+var_140]; this
0x18006fa78  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18006fa7d  nop
0x18006fa7e  mov     [rsp+198h+var_148], rdi
0x18006fa83  lea     rax, [rsp+198h+var_148]
0x18006fa88  mov     [rsp+198h+var_168], rax
0x18006fa8d  mov     [rsp+198h+var_170], 2
0x18006fa95  mov     [rsp+198h+var_178], 7
0x18006fa9d  lea     r9, ?MDM_Policy_Config01_Cellular02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Cellular02_NodeList
0x18006faa4  xor     r8d, r8d
0x18006faa7  xor     edx, edx
0x18006faa9  mov     rcx, r12
0x18006faac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18006fab1  mov     esi, eax
0x18006fab3  test    eax, eax
0x18006fab5  jz      short loc_18006FABC
0x18006fab7  jmp     loc_18006FDCC
0x18006fabc  lea     rbx, [rsp+198h+var_148]
0x18006fac1  mov     [rsp+198h+var_120], rbx
0x18006fac6  mov     r15d, 1
0x18006facc  mov     [rsp+198h+var_118], r15b
0x18006fad4  mov     r14, [rsp+198h+var_148]
0x18006fad9  test    r14, r14
0x18006fadc  jnz     short loc_18006FAE6
0x18006fade  mov     esi, r15d
0x18006fae1  jmp     loc_18006FDCC
0x18006fae6  mov     rax, [r14]
0x18006fae9  mov     rcx, r14
0x18006faec  mov     rax, [rax+10h]
0x18006faf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006faf5  mov     esi, eax
0x18006faf7  test    eax, eax
0x18006faf9  jz      short loc_18006FB19
0x18006fafb  mov     rcx, [rsp+198h+var_148]
0x18006fb00  test    rcx, rcx
0x18006fb03  jz      short loc_18006FB14
0x18006fb05  mov     rax, [rcx]
0x18006fb08  mov     edx, r15d
0x18006fb0b  mov     rax, [rax]
0x18006fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb13  nop
0x18006fb14  jmp     loc_18006FDCC
0x18006fb19  mov     rax, [r14]
0x18006fb1c  mov     rcx, r14
0x18006fb1f  mov     rax, [rax+8]
0x18006fb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb28  mov     esi, eax
0x18006fb2a  test    eax, eax
0x18006fb2c  jz      short loc_18006FB4C
0x18006fb2e  mov     rcx, [rsp+198h+var_148]
0x18006fb33  test    rcx, rcx
0x18006fb36  jz      short loc_18006FB47
0x18006fb38  mov     rax, [rcx]
0x18006fb3b  mov     edx, r15d
0x18006fb3e  mov     rax, [rax]
0x18006fb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb46  nop
0x18006fb47  jmp     loc_18006FDCC
0x18006fb4c  mov     r15d, edi
0x18006fb4f  mov     rax, [r14+108h]
0x18006fb56  sub     rax, [r14+100h]
0x18006fb5d  sar     rax, 4
0x18006fb61  cmp     r15d, eax
0x18006fb64  jnb     loc_18006FD95
0x18006fb6a  lea     r8, [rsp+198h+instance]; instance
0x18006fb72  lea     rdx, MDM_Policy_Config01_Cellular02_rtti; classDecl
0x18006fb79  mov     rcx, r12; context
0x18006fb7c  call    MI_Context_ConstructInstance
0x18006fb81  mov     esi, eax
0x18006fb83  test    eax, eax
0x18006fb85  jz      short loc_18006FBA7
0x18006fb87  mov     rcx, [rbx]
0x18006fb8a  test    rcx, rcx
0x18006fb8d  jz      short loc_18006FBA2
0x18006fb8f  mov     rax, [rcx]
0x18006fb92  mov     edx, 1
0x18006fb97  mov     rax, [rax]
0x18006fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb9f  mov     [rbx], rdi
0x18006fba2  jmp     loc_18006FDCC
0x18006fba7  mov     [rsp+198h+var_158], 1
0x18006fbac  mov     rax, [r14]
0x18006fbaf  lea     r9, [rsp+198h+String]
0x18006fbb4  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18006fbbb  mov     edx, r15d
0x18006fbbe  mov     rcx, r14
0x18006fbc1  mov     rax, [rax+18h]
0x18006fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fbca  test    eax, eax
0x18006fbcc  jnz     short loc_18006FBE5
0x18006fbce  mov     rdx, [rsp+198h+String]
0x18006fbd3  test    rdx, rdx
0x18006fbd6  jz      short loc_18006FBE5
0x18006fbd8  lea     rcx, [rsp+198h+instance]
0x18006fbe0  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18006fbe5  mov     rax, [r14]
0x18006fbe8  lea     r9, [rsp+198h+String]
0x18006fbed  lea     r8, aCellular; "Cellular"
0x18006fbf4  mov     edx, r15d
0x18006fbf7  mov     rcx, r14
0x18006fbfa  mov     rax, [rax+18h]
0x18006fbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc03  test    eax, eax
0x18006fc05  jnz     short loc_18006FC1E
0x18006fc07  mov     rdx, [rsp+198h+String]
0x18006fc0c  test    rdx, rdx
0x18006fc0f  jz      short loc_18006FC1E
0x18006fc11  lea     rcx, [rsp+198h+instance]
0x18006fc19  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18006fc1e  cmp     r13b, 1
0x18006fc22  jnz     short loc_18006FC46
0x18006fc24  lea     rdx, [rsp+198h+instance]
0x18006fc2c  mov     rcx, r12; self
0x18006fc2f  call    MI_Instance_Destruct
0x18006fc34  lea     rcx, [rsp+198h+instance]; self
0x18006fc3c  call    MI_Instance_Destruct
0x18006fc41  jmp     loc_18006FD88
0x18006fc46  mov     rax, [r14]
0x18006fc49  lea     r9, [rsp+198h+String]
0x18006fc4e  lea     r8, aLetappsaccessc_0; "LetAppsAccessCellularData"
0x18006fc55  mov     edx, r15d
0x18006fc58  mov     rcx, r14
0x18006fc5b  mov     rax, [rax+18h]
0x18006fc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc64  test    eax, eax
0x18006fc66  jnz     short loc_18006FC87
0x18006fc68  mov     rcx, [rsp+198h+String]; String
0x18006fc6d  test    rcx, rcx
0x18006fc70  jz      short loc_18006FC87
0x18006fc72  call    cs:__imp__wtoi
0x18006fc78  mov     [rsp+198h+var_88], eax
0x18006fc7f  mov     [rsp+198h+var_84], 1
0x18006fc87  mov     rax, [r14]
0x18006fc8a  lea     r9, [rsp+198h+String]
0x18006fc8f  lea     r8, aLetappsaccessc_18; "LetAppsAccessCellularData_ForceAllowThe"...
0x18006fc96  mov     edx, r15d
0x18006fc99  mov     rcx, r14
0x18006fc9c  mov     rax, [rax+18h]
0x18006fca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fca5  test    eax, eax
0x18006fca7  jnz     short loc_18006FCC0
0x18006fca9  mov     rdx, [rsp+198h+String]
0x18006fcae  test    rdx, rdx
0x18006fcb1  jz      short loc_18006FCC0
0x18006fcb3  lea     rcx, [rsp+198h+instance]
0x18006fcbb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x18006fcc0  mov     rax, [r14]
0x18006fcc3  lea     r9, [rsp+198h+String]
0x18006fcc8  lea     r8, aLetappsaccessc_10; "LetAppsAccessCellularData_ForceDenyThes"...
0x18006fccf  mov     edx, r15d
0x18006fcd2  mov     rcx, r14
0x18006fcd5  mov     rax, [rax+18h]
0x18006fcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcde  test    eax, eax
0x18006fce0  jnz     short loc_18006FCF9
0x18006fce2  mov     rdx, [rsp+198h+String]
0x18006fce7  test    rdx, rdx
0x18006fcea  jz      short loc_18006FCF9
0x18006fcec  lea     rcx, [rsp+198h+instance]
0x18006fcf4  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18006fcf9  mov     rax, [r14]
0x18006fcfc  lea     r9, [rsp+198h+String]
0x18006fd01  lea     r8, aLetappsaccessc_11; "LetAppsAccessCellularData_UserInControl"...
0x18006fd08  mov     edx, r15d
0x18006fd0b  mov     rcx, r14
0x18006fd0e  mov     rax, [rax+18h]
0x18006fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd17  test    eax, eax
0x18006fd19  jnz     short loc_18006FD32
0x18006fd1b  mov     rdx, [rsp+198h+String]
0x18006fd20  test    rdx, rdx
0x18006fd23  jz      short loc_18006FD32
0x18006fd25  lea     rcx, [rsp+198h+instance]
0x18006fd2d  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x18006fd32  mov     rax, [r14]
0x18006fd35  lea     r9, [rsp+198h+String]
0x18006fd3a  lea     r8, aShowappcellula; "ShowAppCellularAccessUI"
0x18006fd41  mov     edx, r15d
0x18006fd44  mov     rcx, r14
0x18006fd47  mov     rax, [rax+18h]
0x18006fd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd50  test    eax, eax
0x18006fd52  jnz     short loc_18006FD6B
0x18006fd54  mov     rdx, [rsp+198h+String]
0x18006fd59  test    rdx, rdx
0x18006fd5c  jz      short loc_18006FD6B
0x18006fd5e  lea     rcx, [rsp+198h+instance]
0x18006fd66  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18006fd6b  lea     rdx, [rsp+198h+instance]
0x18006fd73  mov     rcx, r12; self
0x18006fd76  call    MI_Instance_Destruct
0x18006fd7b  lea     rcx, [rsp+198h+instance]; self
0x18006fd83  call    MI_Instance_Destruct
0x18006fd88  mov     [rsp+198h+var_158], dil
0x18006fd8d  inc     r15d
0x18006fd90  jmp     loc_18006FB4F
0x18006fd95  mov     rcx, [rbx]
0x18006fd98  test    rcx, rcx
0x18006fd9b  jz      short loc_18006FDB0
0x18006fd9d  mov     rax, [rcx]
0x18006fda0  mov     edx, 1
0x18006fda5  mov     rax, [rax]
0x18006fda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fdad  mov     [rbx], rdi
0x18006fdb0  jmp     short loc_18006FDCC
0x18006fdb2  xor     edi, edi
0x18006fdb4  cmp     [rsp+198h+var_158], dil
0x18006fdb9  jz      short loc_18006FDC8
0x18006fdbb  lea     rcx, [rsp+198h+instance]; self
0x18006fdc3  call    MI_Instance_Destruct
0x18006fdc8  mov     esi, dword ptr [rsp+198h+var_148]
0x18006fdcc  mov     r8d, esi; int
0x18006fdcf  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x18006fdd6  lea     rcx, [rsp+198h+var_140]; this
0x18006fddb  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x18006fde0  mov     [rsp+198h+var_110], 2
0x18006fdeb  mov     eax, cs:dword_180380B68
0x18006fdf1  cmp     eax, 5
0x18006fdf4  jbe     short loc_18006FE2F
0x18006fdf6  mov     rdx, 200000000000h
0x18006fe00  lea     rcx, dword_180380B68
0x18006fe07  call    _tlgKeywordOn
0x18006fe0c  test    al, al
0x18006fe0e  jz      short loc_18006FE2F
0x18006fe10  xor     r9d, r9d
0x18006fe13  lea     r8, [rsp+198h+var_108]
0x18006fe1b  lea     rdx, dword_18033CA5C
0x18006fe22  lea     rcx, dword_180380B68
0x18006fe29  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006fe2e  nop
0x18006fe2f  lea     rcx, [rsp+198h+var_110]
0x18006fe37  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x18006fe3c  mov     eax, esi
0x18006fe3e  mov     rcx, [rsp+198h+var_38]
0x18006fe46  xor     rcx, rsp; StackCookie
0x18006fe49  call    __security_check_cookie
0x18006fe4e  lea     r11, [rsp+198h+var_28]
0x18006fe56  mov     rbx, [r11+38h]
0x18006fe5a  mov     rsi, [r11+40h]
0x18006fe5e  mov     rsp, r11
0x18006fe61  pop     r15
0x18006fe63  pop     r14
0x18006fe65  pop     r13
0x18006fe67  pop     r12
0x18006fe69  pop     rdi
  ... truncated ...
```
