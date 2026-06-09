# MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances

- ea: `0x18006f2dc`
- end: `0x18006f7ea`
- name: `MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances`
- size: `1294`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x18006eb30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050b8`
- `0x1800050f0`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18006f2dc`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18006f5ea`
- `msvcrt!_wtoi` at `0x18006f5ea`

## string_xrefs

- `0x18006f5c6`: `LetAppsAccessCellularData`
- `0x18006f60d`: `LetAppsAccessCellularData_ForceAllowTheseApps`
- `0x18006f646`: `LetAppsAccessCellularData_ForceDenyTheseApps`
- `0x18006f67f`: `LetAppsAccessCellularData_UserInControlOfTheseApps`
- `0x18006f6b8`: `ShowAppCellularAccessUI`
- `0x18006f52c`: `./Vendor/MSFT/Policy/Config`
- `0x18006f357`: `MDM_Policy_Config01_Cellular02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_Cellular02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // esi
  _QWORD *v7; // r14
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-148h] BYREF
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
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Cellular02_NodeList, 7, 2, &v11);
  if ( v6 == MI_RESULT_OK )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Cellular02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_53;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Config",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_ForceAllowTheseApps",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_ForceDenyTheseApps",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LetAppsAccessCellularData_UserInControlOfTheseApps",
                      &String)
                && String )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
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
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006f2dc  mov     [rsp+arg_8], rbx
0x18006f2e1  mov     [rsp+arg_10], rsi
0x18006f2e6  push    rdi
0x18006f2e7  push    r12
0x18006f2e9  push    r13
0x18006f2eb  push    r14
0x18006f2ed  push    r15
0x18006f2ef  sub     rsp, 170h
0x18006f2f6  mov     rax, cs:__security_cookie
0x18006f2fd  xor     rax, rsp
0x18006f300  mov     [rsp+198h+var_38], rax
0x18006f308  mov     r13b, dl
0x18006f30b  mov     r12, rcx
0x18006f30e  xor     edx, edx; Val
0x18006f310  mov     r8d, 0A8h; Size
0x18006f316  lea     rcx, [rsp+198h+instance]; void *
0x18006f31e  call    memset_0
0x18006f323  xor     edi, edi
0x18006f325  mov     [rsp+198h+var_158], dil
0x18006f32a  mov     [rsp+198h+String], rdi
0x18006f32f  mov     [rsp+198h+var_110], edi
0x18006f336  mov     [rsp+198h+var_10C], dil
0x18006f33e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006f345  mov     [rsp+198h+var_140], rax
0x18006f34a  lea     rax, [rsp+198h+var_110]
0x18006f352  mov     [rsp+198h+var_138], rax
0x18006f357  lea     rax, aMdmPolicyConfi_157; "MDM_Policy_Config01_Cellular02"
0x18006f35e  mov     [rsp+198h+var_130], rax
0x18006f363  lea     rcx, [rsp+198h+var_110]
0x18006f36b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18006f370  mov     eax, cs:dword_180380B68
0x18006f376  cmp     eax, 5
0x18006f379  jbe     short loc_18006F3EB
0x18006f37b  mov     rdx, 200000000000h
0x18006f385  lea     rcx, dword_180380B68
0x18006f38c  call    _tlgKeywordOn
0x18006f391  test    al, al
0x18006f393  jz      short loc_18006F3EB
0x18006f395  cmp     [rsp+198h+var_10C], dil
0x18006f39d  jz      short loc_18006F3CD
0x18006f39f  cmp     [rsp+198h+var_F8], edi
0x18006f3a6  jnz     short loc_18006F3C3
0x18006f3a8  cmp     [rsp+198h+var_F4], edi
0x18006f3af  jnz     short loc_18006F3C3
0x18006f3b1  cmp     [rsp+198h+var_F0], edi
0x18006f3b8  jnz     short loc_18006F3C3
0x18006f3ba  cmp     [rsp+198h+var_EC], edi
0x18006f3c1  jz      short loc_18006F3CD
0x18006f3c3  lea     r9, [rsp+198h+var_F8]
0x18006f3cb  jmp     short loc_18006F3D0
0x18006f3cd  mov     r9, rdi
0x18006f3d0  lea     r8, [rsp+198h+var_108]
0x18006f3d8  lea     rdx, byte_180333E35
0x18006f3df  lea     rcx, dword_180380B68
0x18006f3e6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006f3eb  lea     rcx, [rsp+198h+var_140]; this
0x18006f3f0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18006f3f5  nop
0x18006f3f6  mov     [rsp+198h+var_148], rdi
0x18006f3fb  lea     rax, [rsp+198h+var_148]
0x18006f400  mov     [rsp+198h+var_168], rax
0x18006f405  mov     [rsp+198h+var_170], 2
0x18006f40d  mov     [rsp+198h+var_178], 7
0x18006f415  lea     r9, ?MDM_Policy_Config01_Cellular02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Cellular02_NodeList
0x18006f41c  xor     r8d, r8d
0x18006f41f  xor     edx, edx
0x18006f421  mov     rcx, r12
0x18006f424  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18006f429  mov     esi, eax
0x18006f42b  test    eax, eax
0x18006f42d  jz      short loc_18006F434
0x18006f42f  jmp     loc_18006F74A
0x18006f434  lea     rbx, [rsp+198h+var_148]
0x18006f439  mov     [rsp+198h+var_120], rbx
0x18006f43e  mov     r15d, 1
0x18006f444  mov     [rsp+198h+var_118], r15b
0x18006f44c  mov     r14, [rsp+198h+var_148]
0x18006f451  test    r14, r14
0x18006f454  jnz     short loc_18006F45E
0x18006f456  mov     esi, r15d
0x18006f459  jmp     loc_18006F74A
0x18006f45e  mov     rax, [r14]
0x18006f461  mov     rcx, r14
0x18006f464  mov     rax, [rax+10h]
0x18006f468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f46d  mov     esi, eax
0x18006f46f  test    eax, eax
0x18006f471  jz      short loc_18006F491
0x18006f473  mov     rcx, [rsp+198h+var_148]
0x18006f478  test    rcx, rcx
0x18006f47b  jz      short loc_18006F48C
0x18006f47d  mov     rax, [rcx]
0x18006f480  mov     edx, r15d
0x18006f483  mov     rax, [rax]
0x18006f486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f48b  nop
0x18006f48c  jmp     loc_18006F74A
0x18006f491  mov     rax, [r14]
0x18006f494  mov     rcx, r14
0x18006f497  mov     rax, [rax+8]
0x18006f49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4a0  mov     esi, eax
0x18006f4a2  test    eax, eax
0x18006f4a4  jz      short loc_18006F4C4
0x18006f4a6  mov     rcx, [rsp+198h+var_148]
0x18006f4ab  test    rcx, rcx
0x18006f4ae  jz      short loc_18006F4BF
0x18006f4b0  mov     rax, [rcx]
0x18006f4b3  mov     edx, r15d
0x18006f4b6  mov     rax, [rax]
0x18006f4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4be  nop
0x18006f4bf  jmp     loc_18006F74A
0x18006f4c4  mov     r15d, edi
0x18006f4c7  mov     rax, [r14+108h]
0x18006f4ce  sub     rax, [r14+100h]
0x18006f4d5  sar     rax, 4
0x18006f4d9  cmp     r15d, eax
0x18006f4dc  jnb     loc_18006F713
0x18006f4e2  lea     r8, [rsp+198h+instance]; instance
0x18006f4ea  lea     rdx, MDM_Policy_Config01_Cellular02_rtti; classDecl
0x18006f4f1  mov     rcx, r12; context
0x18006f4f4  call    MI_Context_ConstructInstance
0x18006f4f9  mov     esi, eax
0x18006f4fb  test    eax, eax
0x18006f4fd  jz      short loc_18006F51F
0x18006f4ff  mov     rcx, [rbx]
0x18006f502  test    rcx, rcx
0x18006f505  jz      short loc_18006F51A
0x18006f507  mov     rax, [rcx]
0x18006f50a  mov     edx, 1
0x18006f50f  mov     rax, [rax]
0x18006f512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f517  mov     [rbx], rdi
0x18006f51a  jmp     loc_18006F74A
0x18006f51f  mov     [rsp+198h+var_158], 1
0x18006f524  mov     rax, [r14]
0x18006f527  lea     r9, [rsp+198h+String]
0x18006f52c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18006f533  mov     edx, r15d
0x18006f536  mov     rcx, r14
0x18006f539  mov     rax, [rax+18h]
0x18006f53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f542  test    eax, eax
0x18006f544  jnz     short loc_18006F55D
0x18006f546  mov     rdx, [rsp+198h+String]
0x18006f54b  test    rdx, rdx
0x18006f54e  jz      short loc_18006F55D
0x18006f550  lea     rcx, [rsp+198h+instance]
0x18006f558  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18006f55d  mov     rax, [r14]
0x18006f560  lea     r9, [rsp+198h+String]
0x18006f565  lea     r8, aCellular; "Cellular"
0x18006f56c  mov     edx, r15d
0x18006f56f  mov     rcx, r14
0x18006f572  mov     rax, [rax+18h]
0x18006f576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f57b  test    eax, eax
0x18006f57d  jnz     short loc_18006F596
0x18006f57f  mov     rdx, [rsp+198h+String]
0x18006f584  test    rdx, rdx
0x18006f587  jz      short loc_18006F596
0x18006f589  lea     rcx, [rsp+198h+instance]
0x18006f591  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18006f596  cmp     r13b, 1
0x18006f59a  jnz     short loc_18006F5BE
0x18006f59c  lea     rdx, [rsp+198h+instance]
0x18006f5a4  mov     rcx, r12; self
0x18006f5a7  call    MI_Instance_Destruct
0x18006f5ac  lea     rcx, [rsp+198h+instance]; self
0x18006f5b4  call    MI_Instance_Destruct
0x18006f5b9  jmp     loc_18006F706
0x18006f5be  mov     rax, [r14]
0x18006f5c1  lea     r9, [rsp+198h+String]
0x18006f5c6  lea     r8, aLetappsaccessc_0; "LetAppsAccessCellularData"
0x18006f5cd  mov     edx, r15d
0x18006f5d0  mov     rcx, r14
0x18006f5d3  mov     rax, [rax+18h]
0x18006f5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f5dc  test    eax, eax
0x18006f5de  jnz     short loc_18006F605
0x18006f5e0  mov     rcx, [rsp+198h+String]; String
0x18006f5e5  test    rcx, rcx
0x18006f5e8  jz      short loc_18006F605
0x18006f5ea  call    cs:__imp__wtoi
0x18006f5f1  nop     dword ptr [rax+rax+00h]
0x18006f5f6  mov     [rsp+198h+var_88], eax
0x18006f5fd  mov     [rsp+198h+var_84], 1
0x18006f605  mov     rax, [r14]
0x18006f608  lea     r9, [rsp+198h+String]
0x18006f60d  lea     r8, aLetappsaccessc_18; "LetAppsAccessCellularData_ForceAllowThe"...
0x18006f614  mov     edx, r15d
0x18006f617  mov     rcx, r14
0x18006f61a  mov     rax, [rax+18h]
0x18006f61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f623  test    eax, eax
0x18006f625  jnz     short loc_18006F63E
0x18006f627  mov     rdx, [rsp+198h+String]
0x18006f62c  test    rdx, rdx
0x18006f62f  jz      short loc_18006F63E
0x18006f631  lea     rcx, [rsp+198h+instance]
0x18006f639  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x18006f63e  mov     rax, [r14]
0x18006f641  lea     r9, [rsp+198h+String]
0x18006f646  lea     r8, aLetappsaccessc_10; "LetAppsAccessCellularData_ForceDenyThes"...
0x18006f64d  mov     edx, r15d
0x18006f650  mov     rcx, r14
0x18006f653  mov     rax, [rax+18h]
0x18006f657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f65c  test    eax, eax
0x18006f65e  jnz     short loc_18006F677
0x18006f660  mov     rdx, [rsp+198h+String]
0x18006f665  test    rdx, rdx
0x18006f668  jz      short loc_18006F677
0x18006f66a  lea     rcx, [rsp+198h+instance]
0x18006f672  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18006f677  mov     rax, [r14]
0x18006f67a  lea     r9, [rsp+198h+String]
0x18006f67f  lea     r8, aLetappsaccessc_11; "LetAppsAccessCellularData_UserInControl"...
0x18006f686  mov     edx, r15d
0x18006f689  mov     rcx, r14
0x18006f68c  mov     rax, [rax+18h]
0x18006f690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f695  test    eax, eax
0x18006f697  jnz     short loc_18006F6B0
0x18006f699  mov     rdx, [rsp+198h+String]
0x18006f69e  test    rdx, rdx
0x18006f6a1  jz      short loc_18006F6B0
0x18006f6a3  lea     rcx, [rsp+198h+instance]
0x18006f6ab  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x18006f6b0  mov     rax, [r14]
0x18006f6b3  lea     r9, [rsp+198h+String]
0x18006f6b8  lea     r8, aShowappcellula; "ShowAppCellularAccessUI"
0x18006f6bf  mov     edx, r15d
0x18006f6c2  mov     rcx, r14
0x18006f6c5  mov     rax, [rax+18h]
0x18006f6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6ce  test    eax, eax
0x18006f6d0  jnz     short loc_18006F6E9
0x18006f6d2  mov     rdx, [rsp+198h+String]
0x18006f6d7  test    rdx, rdx
0x18006f6da  jz      short loc_18006F6E9
0x18006f6dc  lea     rcx, [rsp+198h+instance]
0x18006f6e4  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18006f6e9  lea     rdx, [rsp+198h+instance]
0x18006f6f1  mov     rcx, r12; self
0x18006f6f4  call    MI_Instance_Destruct
0x18006f6f9  lea     rcx, [rsp+198h+instance]; self
0x18006f701  call    MI_Instance_Destruct
0x18006f706  mov     [rsp+198h+var_158], dil
0x18006f70b  inc     r15d
0x18006f70e  jmp     loc_18006F4C7
0x18006f713  mov     rcx, [rbx]
0x18006f716  test    rcx, rcx
0x18006f719  jz      short loc_18006F72E
0x18006f71b  mov     rax, [rcx]
0x18006f71e  mov     edx, 1
0x18006f723  mov     rax, [rax]
0x18006f726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f72b  mov     [rbx], rdi
0x18006f72e  jmp     short loc_18006F74A
0x18006f730  xor     edi, edi
0x18006f732  cmp     [rsp+198h+var_158], dil
0x18006f737  jz      short loc_18006F746
0x18006f739  lea     rcx, [rsp+198h+instance]; self
0x18006f741  call    MI_Instance_Destruct
0x18006f746  mov     esi, dword ptr [rsp+198h+var_148]
0x18006f74a  mov     r8d, esi; int
0x18006f74d  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x18006f754  lea     rcx, [rsp+198h+var_140]; this
0x18006f759  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x18006f75e  mov     [rsp+198h+var_110], 2
0x18006f769  mov     eax, cs:dword_180380B68
0x18006f76f  cmp     eax, 5
0x18006f772  jbe     short loc_18006F7AD
0x18006f774  mov     rdx, 200000000000h
0x18006f77e  lea     rcx, dword_180380B68
0x18006f785  call    _tlgKeywordOn
0x18006f78a  test    al, al
0x18006f78c  jz      short loc_18006F7AD
0x18006f78e  xor     r9d, r9d
0x18006f791  lea     r8, [rsp+198h+var_108]
0x18006f799  lea     rdx, dword_18033CA5C
0x18006f7a0  lea     rcx, dword_180380B68
0x18006f7a7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006f7ac  nop
0x18006f7ad  lea     rcx, [rsp+198h+var_110]
0x18006f7b5  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x18006f7ba  mov     eax, esi
0x18006f7bc  mov     rcx, [rsp+198h+var_38]
0x18006f7c4  xor     rcx, rsp; StackCookie
0x18006f7c7  call    __security_check_cookie
0x18006f7cc  lea     r11, [rsp+198h+var_28]
0x18006f7d4  mov     rbx, [r11+38h]
0x18006f7d8  mov     rsi, [r11+40h]
0x18006f7dc  mov     rsp, r11
0x18006f7df  pop     r15
0x18006f7e1  pop     r14
0x18006f7e3  pop     r13
0x18006f7e5  pop     r12
  ... truncated ...
```
