# MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances

- ea: `0x180081594`
- end: `0x180081a7a`
- name: `MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances`
- size: `1254`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180080e10`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180081594`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800818a2`
- `msvcrt!_wtoi` at `0x1800818e3`
- `msvcrt!_wtoi` at `0x180081924`
- `msvcrt!_wtoi` at `0x180081965`
- `msvcrt!_wtoi` at `0x1800818a2`
- `msvcrt!_wtoi` at `0x1800818e3`
- `msvcrt!_wtoi` at `0x180081924`
- `msvcrt!_wtoi` at `0x180081965`

## string_xrefs

- `0x18008187e`: `ConfigureSystemGuardLaunch`
- `0x1800818bf`: `EnableVirtualizationBasedSecurity`
- `0x180081941`: `RequirePlatformSecurityFeatures`
- `0x1800817e4`: `./Vendor/MSFT/Policy/Config`
- `0x18008160f`: `MDM_Policy_Config01_DeviceGuard02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeviceGuard02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // esi
  WmiRequestHandlerAdd *v8; // r14
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-120h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-118h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_DeviceGuard02_NodeList,
           6u,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeviceGuard02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_58;
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
                      L"DeviceGuard",
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
                        L"ConfigureSystemGuardLaunch",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableVirtualizationBasedSecurity",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LsaCfgFlags",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x180081594  mov     [rsp+arg_8], rbx
0x180081599  mov     [rsp+arg_10], rsi
0x18008159e  push    rdi
0x18008159f  push    r12
0x1800815a1  push    r13
0x1800815a3  push    r14
0x1800815a5  push    r15
0x1800815a7  sub     rsp, 140h
0x1800815ae  mov     rax, cs:__security_cookie
0x1800815b5  xor     rax, rsp
0x1800815b8  mov     [rsp+168h+var_38], rax
0x1800815c0  mov     r13b, dl
0x1800815c3  mov     r12, rcx
0x1800815c6  xor     edx, edx; Val
0x1800815c8  mov     r8d, 80h; Size
0x1800815ce  lea     rcx, [rsp+168h+instance]; void *
0x1800815d6  call    memset_0
0x1800815db  xor     edi, edi
0x1800815dd  mov     [rsp+168h+var_128], dil
0x1800815e2  mov     [rsp+168h+String], rdi
0x1800815e7  mov     [rsp+168h+var_E0], edi
0x1800815ee  mov     [rsp+168h+var_DC], dil
0x1800815f6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800815fd  mov     [rsp+168h+var_110], rax
0x180081602  lea     rax, [rsp+168h+var_E0]
0x18008160a  mov     [rsp+168h+var_108], rax
0x18008160f  lea     rax, aMdmPolicyConfi_159; "MDM_Policy_Config01_DeviceGuard02"
0x180081616  mov     [rsp+168h+var_100], rax
0x18008161b  lea     rcx, [rsp+168h+var_E0]
0x180081623  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180081628  mov     eax, cs:dword_180380B68
0x18008162e  cmp     eax, 5
0x180081631  jbe     short loc_1800816A3
0x180081633  mov     rdx, 200000000000h
0x18008163d  lea     rcx, dword_180380B68
0x180081644  call    _tlgKeywordOn
0x180081649  test    al, al
0x18008164b  jz      short loc_1800816A3
0x18008164d  cmp     [rsp+168h+var_DC], dil
0x180081655  jz      short loc_180081685
0x180081657  cmp     [rsp+168h+var_C8], edi
0x18008165e  jnz     short loc_18008167B
0x180081660  cmp     [rsp+168h+var_C4], edi
0x180081667  jnz     short loc_18008167B
0x180081669  cmp     [rsp+168h+var_C0], edi
0x180081670  jnz     short loc_18008167B
0x180081672  cmp     [rsp+168h+var_BC], edi
0x180081679  jz      short loc_180081685
0x18008167b  lea     r9, [rsp+168h+var_C8]
0x180081683  jmp     short loc_180081688
0x180081685  mov     r9, rdi
0x180081688  lea     r8, [rsp+168h+var_D8]
0x180081690  lea     rdx, byte_180343199
0x180081697  lea     rcx, dword_180380B68
0x18008169e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800816a3  lea     rcx, [rsp+168h+var_110]; this
0x1800816a8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800816ad  nop
0x1800816ae  mov     [rsp+168h+var_118], rdi
0x1800816b3  lea     rax, [rsp+168h+var_118]
0x1800816b8  mov     [rsp+168h+var_138], rax
0x1800816bd  mov     [rsp+168h+var_140], 2
0x1800816c5  mov     [rsp+168h+var_148], 6
0x1800816cd  lea     r9, ?MDM_Policy_Config01_DeviceGuard02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceGuard02_NodeList
0x1800816d4  xor     r8d, r8d
0x1800816d7  xor     edx, edx
0x1800816d9  mov     rcx, r12
0x1800816dc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800816e1  mov     esi, eax
0x1800816e3  test    eax, eax
0x1800816e5  jz      short loc_1800816EC
0x1800816e7  jmp     loc_1800819DB
0x1800816ec  lea     rbx, [rsp+168h+var_118]
0x1800816f1  mov     [rsp+168h+var_F0], rbx
0x1800816f6  mov     r15d, 1
0x1800816fc  mov     [rsp+168h+var_E8], r15b
0x180081704  mov     r14, [rsp+168h+var_118]
0x180081709  test    r14, r14
0x18008170c  jnz     short loc_180081716
0x18008170e  mov     esi, r15d
0x180081711  jmp     loc_1800819DB
0x180081716  mov     rax, [r14]
0x180081719  mov     rcx, r14
0x18008171c  mov     rax, [rax+10h]
0x180081720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081725  mov     esi, eax
0x180081727  test    eax, eax
0x180081729  jz      short loc_180081749
0x18008172b  mov     rcx, [rsp+168h+var_118]
0x180081730  test    rcx, rcx
0x180081733  jz      short loc_180081744
0x180081735  mov     rax, [rcx]
0x180081738  mov     edx, r15d
0x18008173b  mov     rax, [rax]
0x18008173e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081743  nop
0x180081744  jmp     loc_1800819DB
0x180081749  mov     rax, [r14]
0x18008174c  mov     rcx, r14
0x18008174f  mov     rax, [rax+8]
0x180081753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081758  mov     esi, eax
0x18008175a  test    eax, eax
0x18008175c  jz      short loc_18008177C
0x18008175e  mov     rcx, [rsp+168h+var_118]
0x180081763  test    rcx, rcx
0x180081766  jz      short loc_180081777
0x180081768  mov     rax, [rcx]
0x18008176b  mov     edx, r15d
0x18008176e  mov     rax, [rax]
0x180081771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081776  nop
0x180081777  jmp     loc_1800819DB
0x18008177c  mov     r15d, edi
0x18008177f  mov     rax, [r14+108h]
0x180081786  sub     rax, [r14+100h]
0x18008178d  sar     rax, 4
0x180081791  cmp     r15d, eax
0x180081794  jnb     loc_1800819A4
0x18008179a  lea     r8, [rsp+168h+instance]; instance
0x1800817a2  lea     rdx, MDM_Policy_Config01_DeviceGuard02_rtti; classDecl
0x1800817a9  mov     rcx, r12; context
0x1800817ac  call    MI_Context_ConstructInstance
0x1800817b1  mov     esi, eax
0x1800817b3  test    eax, eax
0x1800817b5  jz      short loc_1800817D7
0x1800817b7  mov     rcx, [rbx]
0x1800817ba  test    rcx, rcx
0x1800817bd  jz      short loc_1800817D2
0x1800817bf  mov     rax, [rcx]
0x1800817c2  mov     edx, 1
0x1800817c7  mov     rax, [rax]
0x1800817ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817cf  mov     [rbx], rdi
0x1800817d2  jmp     loc_1800819DB
0x1800817d7  mov     [rsp+168h+var_128], 1
0x1800817dc  mov     rax, [r14]
0x1800817df  lea     r9, [rsp+168h+String]
0x1800817e4  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800817eb  mov     edx, r15d
0x1800817ee  mov     rcx, r14
0x1800817f1  mov     rax, [rax+18h]
0x1800817f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817fa  test    eax, eax
0x1800817fc  jnz     short loc_180081815
0x1800817fe  mov     rdx, [rsp+168h+String]
0x180081803  test    rdx, rdx
0x180081806  jz      short loc_180081815
0x180081808  lea     rcx, [rsp+168h+instance]
0x180081810  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180081815  mov     rax, [r14]
0x180081818  lea     r9, [rsp+168h+String]
0x18008181d  lea     r8, aDeviceguard; "DeviceGuard"
0x180081824  mov     edx, r15d
0x180081827  mov     rcx, r14
0x18008182a  mov     rax, [rax+18h]
0x18008182e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081833  test    eax, eax
0x180081835  jnz     short loc_18008184E
0x180081837  mov     rdx, [rsp+168h+String]
0x18008183c  test    rdx, rdx
0x18008183f  jz      short loc_18008184E
0x180081841  lea     rcx, [rsp+168h+instance]
0x180081849  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18008184e  cmp     r13b, 1
0x180081852  jnz     short loc_180081876
0x180081854  lea     rdx, [rsp+168h+instance]
0x18008185c  mov     rcx, r12; self
0x18008185f  call    MI_Instance_Destruct
0x180081864  lea     rcx, [rsp+168h+instance]; self
0x18008186c  call    MI_Instance_Destruct
0x180081871  jmp     loc_180081997
0x180081876  mov     rax, [r14]
0x180081879  lea     r9, [rsp+168h+String]
0x18008187e  lea     r8, aConfiguresyste; "ConfigureSystemGuardLaunch"
0x180081885  mov     edx, r15d
0x180081888  mov     rcx, r14
0x18008188b  mov     rax, [rax+18h]
0x18008188f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081894  test    eax, eax
0x180081896  jnz     short loc_1800818B7
0x180081898  mov     rcx, [rsp+168h+String]; String
0x18008189d  test    rcx, rcx
0x1800818a0  jz      short loc_1800818B7
0x1800818a2  call    cs:__imp__wtoi
0x1800818a8  mov     [rsp+168h+var_58], eax
0x1800818af  mov     [rsp+168h+var_54], 1
0x1800818b7  mov     rax, [r14]
0x1800818ba  lea     r9, [rsp+168h+String]
0x1800818bf  lea     r8, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x1800818c6  mov     edx, r15d
0x1800818c9  mov     rcx, r14
0x1800818cc  mov     rax, [rax+18h]
0x1800818d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818d5  test    eax, eax
0x1800818d7  jnz     short loc_1800818F8
0x1800818d9  mov     rcx, [rsp+168h+String]; String
0x1800818de  test    rcx, rcx
0x1800818e1  jz      short loc_1800818F8
0x1800818e3  call    cs:__imp__wtoi
0x1800818e9  mov     [rsp+168h+var_50], eax
0x1800818f0  mov     [rsp+168h+var_4C], 1
0x1800818f8  mov     rax, [r14]
0x1800818fb  lea     r9, [rsp+168h+String]
0x180081900  lea     r8, aLsacfgflags; "LsaCfgFlags"
0x180081907  mov     edx, r15d
0x18008190a  mov     rcx, r14
0x18008190d  mov     rax, [rax+18h]
0x180081911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081916  test    eax, eax
0x180081918  jnz     short loc_180081939
0x18008191a  mov     rcx, [rsp+168h+String]; String
0x18008191f  test    rcx, rcx
0x180081922  jz      short loc_180081939
0x180081924  call    cs:__imp__wtoi
0x18008192a  mov     [rsp+168h+var_48], eax
0x180081931  mov     [rsp+168h+var_44], 1
0x180081939  mov     rax, [r14]
0x18008193c  lea     r9, [rsp+168h+String]
0x180081941  lea     r8, aRequireplatfor; "RequirePlatformSecurityFeatures"
0x180081948  mov     edx, r15d
0x18008194b  mov     rcx, r14
0x18008194e  mov     rax, [rax+18h]
0x180081952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081957  test    eax, eax
0x180081959  jnz     short loc_18008197A
0x18008195b  mov     rcx, [rsp+168h+String]; String
0x180081960  test    rcx, rcx
0x180081963  jz      short loc_18008197A
0x180081965  call    cs:__imp__wtoi
0x18008196b  mov     [rsp+168h+var_40], eax
0x180081972  mov     [rsp+168h+var_3C], 1
0x18008197a  lea     rdx, [rsp+168h+instance]
0x180081982  mov     rcx, r12; self
0x180081985  call    MI_Instance_Destruct
0x18008198a  lea     rcx, [rsp+168h+instance]; self
0x180081992  call    MI_Instance_Destruct
0x180081997  mov     [rsp+168h+var_128], dil
0x18008199c  inc     r15d
0x18008199f  jmp     loc_18008177F
0x1800819a4  mov     rcx, [rbx]
0x1800819a7  test    rcx, rcx
0x1800819aa  jz      short loc_1800819BF
0x1800819ac  mov     rax, [rcx]
0x1800819af  mov     edx, 1
0x1800819b4  mov     rax, [rax]
0x1800819b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800819bc  mov     [rbx], rdi
0x1800819bf  jmp     short loc_1800819DB
0x1800819c1  xor     edi, edi
0x1800819c3  cmp     [rsp+168h+var_128], dil
0x1800819c8  jz      short loc_1800819D7
0x1800819ca  lea     rcx, [rsp+168h+instance]; self
0x1800819d2  call    MI_Instance_Destruct
0x1800819d7  mov     esi, dword ptr [rsp+168h+var_118]
0x1800819db  mov     r8d, esi; int
0x1800819de  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x1800819e5  lea     rcx, [rsp+168h+var_110]; this
0x1800819ea  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800819ef  mov     [rsp+168h+var_E0], 2
0x1800819fa  mov     eax, cs:dword_180380B68
0x180081a00  cmp     eax, 5
0x180081a03  jbe     short loc_180081A3E
0x180081a05  mov     rdx, 200000000000h
0x180081a0f  lea     rcx, dword_180380B68
0x180081a16  call    _tlgKeywordOn
0x180081a1b  test    al, al
0x180081a1d  jz      short loc_180081A3E
0x180081a1f  xor     r9d, r9d
0x180081a22  lea     r8, [rsp+168h+var_D8]
0x180081a2a  lea     rdx, byte_180333C57
0x180081a31  lea     rcx, dword_180380B68
0x180081a38  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180081a3d  nop
0x180081a3e  lea     rcx, [rsp+168h+var_E0]
0x180081a46  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x180081a4b  mov     eax, esi
0x180081a4d  mov     rcx, [rsp+168h+var_38]
0x180081a55  xor     rcx, rsp; StackCookie
0x180081a58  call    __security_check_cookie
0x180081a5d  lea     r11, [rsp+168h+var_28]
0x180081a65  mov     rbx, [r11+38h]
0x180081a69  mov     rsi, [r11+40h]
0x180081a6d  mov     rsp, r11
0x180081a70  pop     r15
0x180081a72  pop     r14
0x180081a74  pop     r13
0x180081a76  pop     r12
0x180081a78  pop     rdi
0x180081a79  retn
```
