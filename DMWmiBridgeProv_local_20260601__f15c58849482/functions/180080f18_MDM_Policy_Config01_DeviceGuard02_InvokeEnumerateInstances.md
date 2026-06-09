# MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances

- ea: `0x180080f18`
- end: `0x180081417`
- name: `MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances`
- size: `1279`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800807b0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180080f18`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180081226`
- `msvcrt!_wtoi` at `0x18008126d`
- `msvcrt!_wtoi` at `0x1800812b4`
- `msvcrt!_wtoi` at `0x1800812fb`
- `msvcrt!_wtoi` at `0x180081226`
- `msvcrt!_wtoi` at `0x18008126d`
- `msvcrt!_wtoi` at `0x1800812b4`
- `msvcrt!_wtoi` at `0x1800812fb`

## string_xrefs

- `0x180081202`: `ConfigureSystemGuardLaunch`
- `0x180081249`: `EnableVirtualizationBasedSecurity`
- `0x1800812d7`: `RequirePlatformSecurityFeatures`
- `0x180081168`: `./Vendor/MSFT/Policy/Config`
- `0x180080f93`: `MDM_Policy_Config01_DeviceGuard02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // esi
  _QWORD *v8; // r14
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-120h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-118h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-110h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-F8h] BYREF
  char v17; // [rsp+80h] [rbp-E8h]
  int v18; // [rsp+88h] [rbp-E0h] BYREF
  char v19; // [rsp+8Ch] [rbp-DCh]
  _BYTE v20[16]; // [rsp+90h] [rbp-D8h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-C8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-B8h] BYREF
  int v23; // [rsp+110h] [rbp-58h]
  char v24; // [rsp+114h] [rbp-54h]
  int v25; // [rsp+118h] [rbp-50h]
  char v26; // [rsp+11Ch] [rbp-4Ch]
  int v27; // [rsp+120h] [rbp-48h]
  char v28; // [rsp+124h] [rbp-44h]
  int v29; // [rsp+128h] [rbp-40h]
  char v30; // [rsp+12Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0x80u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_DeviceGuard02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180343199,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_DeviceGuard02_NodeList, 6, 2, &v14);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeviceGuard02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_58;
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
                      L"DeviceGuard",
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
                        L"ConfigureSystemGuardLaunch",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableVirtualizationBasedSecurity",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LsaCfgFlags",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePlatformSecurityFeatures",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
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
LABEL_58:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180333C57,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180080f18  mov     [rsp+arg_8], rbx
0x180080f1d  mov     [rsp+arg_10], rsi
0x180080f22  push    rdi
0x180080f23  push    r12
0x180080f25  push    r13
0x180080f27  push    r14
0x180080f29  push    r15
0x180080f2b  sub     rsp, 140h
0x180080f32  mov     rax, cs:__security_cookie
0x180080f39  xor     rax, rsp
0x180080f3c  mov     [rsp+168h+var_38], rax
0x180080f44  mov     r13b, dl
0x180080f47  mov     r12, rcx
0x180080f4a  xor     edx, edx; Val
0x180080f4c  mov     r8d, 80h; Size
0x180080f52  lea     rcx, [rsp+168h+instance]; void *
0x180080f5a  call    memset_0
0x180080f5f  xor     edi, edi
0x180080f61  mov     [rsp+168h+var_128], dil
0x180080f66  mov     [rsp+168h+String], rdi
0x180080f6b  mov     [rsp+168h+var_E0], edi
0x180080f72  mov     [rsp+168h+var_DC], dil
0x180080f7a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180080f81  mov     [rsp+168h+var_110], rax
0x180080f86  lea     rax, [rsp+168h+var_E0]
0x180080f8e  mov     [rsp+168h+var_108], rax
0x180080f93  lea     rax, aMdmPolicyConfi_159; "MDM_Policy_Config01_DeviceGuard02"
0x180080f9a  mov     [rsp+168h+var_100], rax
0x180080f9f  lea     rcx, [rsp+168h+var_E0]
0x180080fa7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180080fac  mov     eax, cs:dword_180380B68
0x180080fb2  cmp     eax, 5
0x180080fb5  jbe     short loc_180081027
0x180080fb7  mov     rdx, 200000000000h
0x180080fc1  lea     rcx, dword_180380B68
0x180080fc8  call    _tlgKeywordOn
0x180080fcd  test    al, al
0x180080fcf  jz      short loc_180081027
0x180080fd1  cmp     [rsp+168h+var_DC], dil
0x180080fd9  jz      short loc_180081009
0x180080fdb  cmp     [rsp+168h+var_C8], edi
0x180080fe2  jnz     short loc_180080FFF
0x180080fe4  cmp     [rsp+168h+var_C4], edi
0x180080feb  jnz     short loc_180080FFF
0x180080fed  cmp     [rsp+168h+var_C0], edi
0x180080ff4  jnz     short loc_180080FFF
0x180080ff6  cmp     [rsp+168h+var_BC], edi
0x180080ffd  jz      short loc_180081009
0x180080fff  lea     r9, [rsp+168h+var_C8]
0x180081007  jmp     short loc_18008100C
0x180081009  mov     r9, rdi
0x18008100c  lea     r8, [rsp+168h+var_D8]
0x180081014  lea     rdx, byte_180343199
0x18008101b  lea     rcx, dword_180380B68
0x180081022  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180081027  lea     rcx, [rsp+168h+var_110]; this
0x18008102c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180081031  nop
0x180081032  mov     [rsp+168h+var_118], rdi
0x180081037  lea     rax, [rsp+168h+var_118]
0x18008103c  mov     [rsp+168h+var_138], rax
0x180081041  mov     [rsp+168h+var_140], 2
0x180081049  mov     [rsp+168h+var_148], 6
0x180081051  lea     r9, ?MDM_Policy_Config01_DeviceGuard02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceGuard02_NodeList
0x180081058  xor     r8d, r8d
0x18008105b  xor     edx, edx
0x18008105d  mov     rcx, r12
0x180081060  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180081065  mov     esi, eax
0x180081067  test    eax, eax
0x180081069  jz      short loc_180081070
0x18008106b  jmp     loc_180081377
0x180081070  lea     rbx, [rsp+168h+var_118]
0x180081075  mov     [rsp+168h+var_F0], rbx
0x18008107a  mov     r15d, 1
0x180081080  mov     [rsp+168h+var_E8], r15b
0x180081088  mov     r14, [rsp+168h+var_118]
0x18008108d  test    r14, r14
0x180081090  jnz     short loc_18008109A
0x180081092  mov     esi, r15d
0x180081095  jmp     loc_180081377
0x18008109a  mov     rax, [r14]
0x18008109d  mov     rcx, r14
0x1800810a0  mov     rax, [rax+10h]
0x1800810a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810a9  mov     esi, eax
0x1800810ab  test    eax, eax
0x1800810ad  jz      short loc_1800810CD
0x1800810af  mov     rcx, [rsp+168h+var_118]
0x1800810b4  test    rcx, rcx
0x1800810b7  jz      short loc_1800810C8
0x1800810b9  mov     rax, [rcx]
0x1800810bc  mov     edx, r15d
0x1800810bf  mov     rax, [rax]
0x1800810c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810c7  nop
0x1800810c8  jmp     loc_180081377
0x1800810cd  mov     rax, [r14]
0x1800810d0  mov     rcx, r14
0x1800810d3  mov     rax, [rax+8]
0x1800810d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810dc  mov     esi, eax
0x1800810de  test    eax, eax
0x1800810e0  jz      short loc_180081100
0x1800810e2  mov     rcx, [rsp+168h+var_118]
0x1800810e7  test    rcx, rcx
0x1800810ea  jz      short loc_1800810FB
0x1800810ec  mov     rax, [rcx]
0x1800810ef  mov     edx, r15d
0x1800810f2  mov     rax, [rax]
0x1800810f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810fa  nop
0x1800810fb  jmp     loc_180081377
0x180081100  mov     r15d, edi
0x180081103  mov     rax, [r14+108h]
0x18008110a  sub     rax, [r14+100h]
0x180081111  sar     rax, 4
0x180081115  cmp     r15d, eax
0x180081118  jnb     loc_180081340
0x18008111e  lea     r8, [rsp+168h+instance]; instance
0x180081126  lea     rdx, MDM_Policy_Config01_DeviceGuard02_rtti; classDecl
0x18008112d  mov     rcx, r12; context
0x180081130  call    MI_Context_ConstructInstance
0x180081135  mov     esi, eax
0x180081137  test    eax, eax
0x180081139  jz      short loc_18008115B
0x18008113b  mov     rcx, [rbx]
0x18008113e  test    rcx, rcx
0x180081141  jz      short loc_180081156
0x180081143  mov     rax, [rcx]
0x180081146  mov     edx, 1
0x18008114b  mov     rax, [rax]
0x18008114e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081153  mov     [rbx], rdi
0x180081156  jmp     loc_180081377
0x18008115b  mov     [rsp+168h+var_128], 1
0x180081160  mov     rax, [r14]
0x180081163  lea     r9, [rsp+168h+String]
0x180081168  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18008116f  mov     edx, r15d
0x180081172  mov     rcx, r14
0x180081175  mov     rax, [rax+18h]
0x180081179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008117e  test    eax, eax
0x180081180  jnz     short loc_180081199
0x180081182  mov     rdx, [rsp+168h+String]
0x180081187  test    rdx, rdx
0x18008118a  jz      short loc_180081199
0x18008118c  lea     rcx, [rsp+168h+instance]
0x180081194  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180081199  mov     rax, [r14]
0x18008119c  lea     r9, [rsp+168h+String]
0x1800811a1  lea     r8, aDeviceguard; "DeviceGuard"
0x1800811a8  mov     edx, r15d
0x1800811ab  mov     rcx, r14
0x1800811ae  mov     rax, [rax+18h]
0x1800811b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800811b7  test    eax, eax
0x1800811b9  jnz     short loc_1800811D2
0x1800811bb  mov     rdx, [rsp+168h+String]
0x1800811c0  test    rdx, rdx
0x1800811c3  jz      short loc_1800811D2
0x1800811c5  lea     rcx, [rsp+168h+instance]
0x1800811cd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800811d2  cmp     r13b, 1
0x1800811d6  jnz     short loc_1800811FA
0x1800811d8  lea     rdx, [rsp+168h+instance]
0x1800811e0  mov     rcx, r12; self
0x1800811e3  call    MI_Instance_Destruct
0x1800811e8  lea     rcx, [rsp+168h+instance]; self
0x1800811f0  call    MI_Instance_Destruct
0x1800811f5  jmp     loc_180081333
0x1800811fa  mov     rax, [r14]
0x1800811fd  lea     r9, [rsp+168h+String]
0x180081202  lea     r8, aConfiguresyste; "ConfigureSystemGuardLaunch"
0x180081209  mov     edx, r15d
0x18008120c  mov     rcx, r14
0x18008120f  mov     rax, [rax+18h]
0x180081213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081218  test    eax, eax
0x18008121a  jnz     short loc_180081241
0x18008121c  mov     rcx, [rsp+168h+String]; String
0x180081221  test    rcx, rcx
0x180081224  jz      short loc_180081241
0x180081226  call    cs:__imp__wtoi
0x18008122d  nop     dword ptr [rax+rax+00h]
0x180081232  mov     [rsp+168h+var_58], eax
0x180081239  mov     [rsp+168h+var_54], 1
0x180081241  mov     rax, [r14]
0x180081244  lea     r9, [rsp+168h+String]
0x180081249  lea     r8, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x180081250  mov     edx, r15d
0x180081253  mov     rcx, r14
0x180081256  mov     rax, [rax+18h]
0x18008125a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008125f  test    eax, eax
0x180081261  jnz     short loc_180081288
0x180081263  mov     rcx, [rsp+168h+String]; String
0x180081268  test    rcx, rcx
0x18008126b  jz      short loc_180081288
0x18008126d  call    cs:__imp__wtoi
0x180081274  nop     dword ptr [rax+rax+00h]
0x180081279  mov     [rsp+168h+var_50], eax
0x180081280  mov     [rsp+168h+var_4C], 1
0x180081288  mov     rax, [r14]
0x18008128b  lea     r9, [rsp+168h+String]
0x180081290  lea     r8, aLsacfgflags; "LsaCfgFlags"
0x180081297  mov     edx, r15d
0x18008129a  mov     rcx, r14
0x18008129d  mov     rax, [rax+18h]
0x1800812a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812a6  test    eax, eax
0x1800812a8  jnz     short loc_1800812CF
0x1800812aa  mov     rcx, [rsp+168h+String]; String
0x1800812af  test    rcx, rcx
0x1800812b2  jz      short loc_1800812CF
0x1800812b4  call    cs:__imp__wtoi
0x1800812bb  nop     dword ptr [rax+rax+00h]
0x1800812c0  mov     [rsp+168h+var_48], eax
0x1800812c7  mov     [rsp+168h+var_44], 1
0x1800812cf  mov     rax, [r14]
0x1800812d2  lea     r9, [rsp+168h+String]
0x1800812d7  lea     r8, aRequireplatfor; "RequirePlatformSecurityFeatures"
0x1800812de  mov     edx, r15d
0x1800812e1  mov     rcx, r14
0x1800812e4  mov     rax, [rax+18h]
0x1800812e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812ed  test    eax, eax
0x1800812ef  jnz     short loc_180081316
0x1800812f1  mov     rcx, [rsp+168h+String]; String
0x1800812f6  test    rcx, rcx
0x1800812f9  jz      short loc_180081316
0x1800812fb  call    cs:__imp__wtoi
0x180081302  nop     dword ptr [rax+rax+00h]
0x180081307  mov     [rsp+168h+var_40], eax
0x18008130e  mov     [rsp+168h+var_3C], 1
0x180081316  lea     rdx, [rsp+168h+instance]
0x18008131e  mov     rcx, r12; self
0x180081321  call    MI_Instance_Destruct
0x180081326  lea     rcx, [rsp+168h+instance]; self
0x18008132e  call    MI_Instance_Destruct
0x180081333  mov     [rsp+168h+var_128], dil
0x180081338  inc     r15d
0x18008133b  jmp     loc_180081103
0x180081340  mov     rcx, [rbx]
0x180081343  test    rcx, rcx
0x180081346  jz      short loc_18008135B
0x180081348  mov     rax, [rcx]
0x18008134b  mov     edx, 1
0x180081350  mov     rax, [rax]
0x180081353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081358  mov     [rbx], rdi
0x18008135b  jmp     short loc_180081377
0x18008135d  xor     edi, edi
0x18008135f  cmp     [rsp+168h+var_128], dil
0x180081364  jz      short loc_180081373
0x180081366  lea     rcx, [rsp+168h+instance]; self
0x18008136e  call    MI_Instance_Destruct
0x180081373  mov     esi, dword ptr [rsp+168h+var_118]
0x180081377  mov     r8d, esi; int
0x18008137a  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x180081381  lea     rcx, [rsp+168h+var_110]; this
0x180081386  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x18008138b  mov     [rsp+168h+var_E0], 2
0x180081396  mov     eax, cs:dword_180380B68
0x18008139c  cmp     eax, 5
0x18008139f  jbe     short loc_1800813DA
0x1800813a1  mov     rdx, 200000000000h
0x1800813ab  lea     rcx, dword_180380B68
0x1800813b2  call    _tlgKeywordOn
0x1800813b7  test    al, al
0x1800813b9  jz      short loc_1800813DA
0x1800813bb  xor     r9d, r9d
0x1800813be  lea     r8, [rsp+168h+var_D8]
0x1800813c6  lea     rdx, byte_180333C57
0x1800813cd  lea     rcx, dword_180380B68
0x1800813d4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800813d9  nop
0x1800813da  lea     rcx, [rsp+168h+var_E0]
0x1800813e2  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800813e7  mov     eax, esi
0x1800813e9  mov     rcx, [rsp+168h+var_38]
0x1800813f1  xor     rcx, rsp; StackCookie
0x1800813f4  call    __security_check_cookie
0x1800813f9  lea     r11, [rsp+168h+var_28]
0x180081401  mov     rbx, [r11+38h]
0x180081405  mov     rsi, [r11+40h]
0x180081409  mov     rsp, r11
0x18008140c  pop     r15
0x18008140e  pop     r14
0x180081410  pop     r13
0x180081412  pop     r12
0x180081414  pop     rdi
0x180081415  retn
```
