# MDM_Policy_Result01_Storage02_InvokeEnumerateInstances

- ea: `0x180198278`
- end: `0x180198944`
- name: `MDM_Policy_Result01_Storage02_InvokeEnumerateInstances`
- size: `1740`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180197950`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x180005358`
- `0x180005438`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180198278`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019858a`
- `msvcrt!_wtoi` at `0x1801985d1`
- `msvcrt!_wtoi` at `0x180198618`
- `msvcrt!_wtoi` at `0x18019865f`
- `msvcrt!_wtoi` at `0x1801986a6`
- `msvcrt!_wtoi` at `0x1801986ed`
- `msvcrt!_wtoi` at `0x180198734`
- `msvcrt!_wtoi` at `0x1801987b4`
- `msvcrt!_wtoi` at `0x18019858a`
- `msvcrt!_wtoi` at `0x1801985d1`
- `msvcrt!_wtoi` at `0x180198618`
- `msvcrt!_wtoi` at `0x18019865f`
- `msvcrt!_wtoi` at `0x1801986a6`
- `msvcrt!_wtoi` at `0x1801986ed`
- `msvcrt!_wtoi` at `0x180198734`
- `msvcrt!_wtoi` at `0x1801987b4`

## string_xrefs

- `0x180198566`: `AllowDiskHealthModelUpdates`
- `0x1801985f4`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x18019863b`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x180198682`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1801986c9`: `ConfigStorageSenseGlobalCadence`
- `0x180198710`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x180198790`: `RemovableDiskDenyWriteAccess`
- `0x1801987d7`: `WPDDevicesDenyReadAccessPerDevice`
- `0x180198810`: `WPDDevicesDenyWriteAccessPerDevice`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Storage02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r14d
  _QWORD *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-170h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-168h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-160h] BYREF
  char v13; // [rsp+80h] [rbp-138h]
  int v14; // [rsp+88h] [rbp-130h] BYREF
  char v15; // [rsp+8Ch] [rbp-12Ch]
  _BYTE v16[16]; // [rsp+90h] [rbp-128h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-118h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-108h] BYREF
  int v19; // [rsp+110h] [rbp-A8h]
  char v20; // [rsp+114h] [rbp-A4h]
  int v21; // [rsp+118h] [rbp-A0h]
  char v22; // [rsp+11Ch] [rbp-9Ch]
  int v23; // [rsp+120h] [rbp-98h]
  char v24; // [rsp+124h] [rbp-94h]
  int v25; // [rsp+128h] [rbp-90h]
  char v26; // [rsp+12Ch] [rbp-8Ch]
  int v27; // [rsp+130h] [rbp-88h]
  char v28; // [rsp+134h] [rbp-84h]
  int v29; // [rsp+138h] [rbp-80h]
  char v30; // [rsp+13Ch] [rbp-7Ch]
  int v31; // [rsp+140h] [rbp-78h]
  char v32; // [rsp+144h] [rbp-74h]
  int v33; // [rsp+158h] [rbp-60h]
  char v34; // [rsp+15Ch] [rbp-5Ch]

  memset_0(&instance, 0, 0xD0u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Result01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033628C,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_Storage02_NodeList, 13, 2, &v11);
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Storage02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_71;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"Storage",
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
                      L"AllowDiskHealthModelUpdates",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageSenseGlobal",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageSenseTemporaryFilesCleanup",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseCloudContentDehydrationThreshold",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseDownloadsCleanupThreshold",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseGlobalCadence",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseRecycleBinCleanupThreshold",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnhancedStorageDevices",
                      &String)
                && String )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RemovableDiskDenyWriteAccess",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"WPDDevicesDenyReadAccessPerDevice",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"WPDDevicesDenyWriteAccessPerDevice",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
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
LABEL_71:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180342C0B,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180198278  mov     [rsp+arg_8], rbx
0x18019827d  mov     [rsp+arg_10], rsi
0x180198282  push    rdi
0x180198283  push    r12
0x180198285  push    r13
0x180198287  push    r14
0x180198289  push    r15
0x18019828b  sub     rsp, 190h
0x180198292  mov     rax, cs:__security_cookie
0x180198299  xor     rax, rsp
0x18019829c  mov     [rsp+1B8h+var_38], rax
0x1801982a4  mov     r13b, dl
0x1801982a7  mov     r12, rcx
0x1801982aa  xor     edx, edx; Val
0x1801982ac  mov     r8d, 0D0h; Size
0x1801982b2  lea     rcx, [rsp+1B8h+instance]; void *
0x1801982ba  call    memset_0
0x1801982bf  xor     edi, edi
0x1801982c1  mov     [rsp+1B8h+var_178], dil
0x1801982c6  mov     [rsp+1B8h+String], rdi
0x1801982cb  mov     [rsp+1B8h+var_130], edi
0x1801982d2  mov     [rsp+1B8h+var_12C], dil
0x1801982da  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801982e1  mov     [rsp+1B8h+var_160], rax
0x1801982e6  lea     rax, [rsp+1B8h+var_130]
0x1801982ee  mov     [rsp+1B8h+var_158], rax
0x1801982f3  lea     rax, aMdmPolicyResul_127; "MDM_Policy_Result01_Storage02"
0x1801982fa  mov     [rsp+1B8h+var_150], rax
0x1801982ff  lea     rcx, [rsp+1B8h+var_130]
0x180198307  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019830c  mov     eax, cs:dword_180380B68
0x180198312  cmp     eax, 5
0x180198315  jbe     short loc_180198387
0x180198317  mov     rdx, 200000000000h
0x180198321  lea     rcx, dword_180380B68
0x180198328  call    _tlgKeywordOn
0x18019832d  test    al, al
0x18019832f  jz      short loc_180198387
0x180198331  cmp     [rsp+1B8h+var_12C], dil
0x180198339  jz      short loc_180198369
0x18019833b  cmp     [rsp+1B8h+var_118], edi
0x180198342  jnz     short loc_18019835F
0x180198344  cmp     [rsp+1B8h+var_114], edi
0x18019834b  jnz     short loc_18019835F
0x18019834d  cmp     [rsp+1B8h+var_110], edi
0x180198354  jnz     short loc_18019835F
0x180198356  cmp     [rsp+1B8h+var_10C], edi
0x18019835d  jz      short loc_180198369
0x18019835f  lea     r9, [rsp+1B8h+var_118]
0x180198367  jmp     short loc_18019836C
0x180198369  mov     r9, rdi
0x18019836c  lea     r8, [rsp+1B8h+var_128]
0x180198374  lea     rdx, dword_18033628C
0x18019837b  lea     rcx, dword_180380B68
0x180198382  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180198387  lea     rcx, [rsp+1B8h+var_160]; this
0x18019838c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180198391  nop
0x180198392  mov     [rsp+1B8h+var_168], rdi
0x180198397  lea     rax, [rsp+1B8h+var_168]
0x18019839c  mov     [rsp+1B8h+var_188], rax
0x1801983a1  mov     [rsp+1B8h+var_190], 2
0x1801983a9  mov     [rsp+1B8h+var_198], 0Dh
0x1801983b1  lea     r9, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Storage02_NodeList
0x1801983b8  xor     r8d, r8d
0x1801983bb  xor     edx, edx
0x1801983bd  mov     rcx, r12
0x1801983c0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801983c5  mov     r14d, eax
0x1801983c8  test    eax, eax
0x1801983ca  jz      short loc_1801983D1
0x1801983cc  jmp     loc_1801988A3
0x1801983d1  lea     rbx, [rsp+1B8h+var_168]
0x1801983d6  mov     [rsp+1B8h+var_140], rbx
0x1801983db  mov     r15d, 1
0x1801983e1  mov     [rsp+1B8h+var_138], r15b
0x1801983e9  mov     rsi, [rsp+1B8h+var_168]
0x1801983ee  test    rsi, rsi
0x1801983f1  jnz     short loc_1801983FB
0x1801983f3  mov     r14d, r15d
0x1801983f6  jmp     loc_1801988A3
0x1801983fb  mov     rax, [rsi]
0x1801983fe  mov     rcx, rsi
0x180198401  mov     rax, [rax+10h]
0x180198405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019840a  mov     r14d, eax
0x18019840d  test    eax, eax
0x18019840f  jz      short loc_18019842F
0x180198411  mov     rcx, [rsp+1B8h+var_168]
0x180198416  test    rcx, rcx
0x180198419  jz      short loc_18019842A
0x18019841b  mov     rax, [rcx]
0x18019841e  mov     edx, r15d
0x180198421  mov     rax, [rax]
0x180198424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198429  nop
0x18019842a  jmp     loc_1801988A3
0x18019842f  mov     rax, [rsi]
0x180198432  mov     rcx, rsi
0x180198435  mov     rax, [rax+8]
0x180198439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019843e  mov     r14d, eax
0x180198441  test    eax, eax
0x180198443  jz      short loc_180198463
0x180198445  mov     rcx, [rsp+1B8h+var_168]
0x18019844a  test    rcx, rcx
0x18019844d  jz      short loc_18019845E
0x18019844f  mov     rax, [rcx]
0x180198452  mov     edx, r15d
0x180198455  mov     rax, [rax]
0x180198458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019845d  nop
0x18019845e  jmp     loc_1801988A3
0x180198463  mov     r15d, edi
0x180198466  mov     rax, [rsi+108h]
0x18019846d  sub     rax, [rsi+100h]
0x180198474  sar     rax, 4
0x180198478  cmp     r15d, eax
0x18019847b  jnb     loc_18019886B
0x180198481  lea     r8, [rsp+1B8h+instance]; instance
0x180198489  lea     rdx, MDM_Policy_Result01_Storage02_rtti; classDecl
0x180198490  mov     rcx, r12; context
0x180198493  call    MI_Context_ConstructInstance
0x180198498  mov     r14d, eax
0x18019849b  test    eax, eax
0x18019849d  jz      short loc_1801984BF
0x18019849f  mov     rcx, [rbx]
0x1801984a2  test    rcx, rcx
0x1801984a5  jz      short loc_1801984BA
0x1801984a7  mov     rax, [rcx]
0x1801984aa  mov     edx, 1
0x1801984af  mov     rax, [rax]
0x1801984b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801984b7  mov     [rbx], rdi
0x1801984ba  jmp     loc_1801988A3
0x1801984bf  mov     [rsp+1B8h+var_178], 1
0x1801984c4  mov     rax, [rsi]
0x1801984c7  lea     r9, [rsp+1B8h+String]
0x1801984cc  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801984d3  mov     edx, r15d
0x1801984d6  mov     rcx, rsi
0x1801984d9  mov     rax, [rax+18h]
0x1801984dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801984e2  test    eax, eax
0x1801984e4  jnz     short loc_1801984FD
0x1801984e6  mov     rdx, [rsp+1B8h+String]
0x1801984eb  test    rdx, rdx
0x1801984ee  jz      short loc_1801984FD
0x1801984f0  lea     rcx, [rsp+1B8h+instance]
0x1801984f8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801984fd  mov     rax, [rsi]
0x180198500  lea     r9, [rsp+1B8h+String]
0x180198505  lea     r8, aStorage; "Storage"
0x18019850c  mov     edx, r15d
0x18019850f  mov     rcx, rsi
0x180198512  mov     rax, [rax+18h]
0x180198516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019851b  test    eax, eax
0x18019851d  jnz     short loc_180198536
0x18019851f  mov     rdx, [rsp+1B8h+String]
0x180198524  test    rdx, rdx
0x180198527  jz      short loc_180198536
0x180198529  lea     rcx, [rsp+1B8h+instance]
0x180198531  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180198536  cmp     r13b, 1
0x18019853a  jnz     short loc_18019855E
0x18019853c  lea     rdx, [rsp+1B8h+instance]
0x180198544  mov     rcx, r12; self
0x180198547  call    MI_Instance_Destruct
0x18019854c  lea     rcx, [rsp+1B8h+instance]; self
0x180198554  call    MI_Instance_Destruct
0x180198559  jmp     loc_18019885E
0x18019855e  mov     rax, [rsi]
0x180198561  lea     r9, [rsp+1B8h+String]
0x180198566  lea     r8, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x18019856d  mov     edx, r15d
0x180198570  mov     rcx, rsi
0x180198573  mov     rax, [rax+18h]
0x180198577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019857c  test    eax, eax
0x18019857e  jnz     short loc_1801985A5
0x180198580  mov     rcx, [rsp+1B8h+String]; String
0x180198585  test    rcx, rcx
0x180198588  jz      short loc_1801985A5
0x18019858a  call    cs:__imp__wtoi
0x180198591  nop     dword ptr [rax+rax+00h]
0x180198596  mov     [rsp+1B8h+var_A8], eax
0x18019859d  mov     [rsp+1B8h+var_A4], 1
0x1801985a5  mov     rax, [rsi]
0x1801985a8  lea     r9, [rsp+1B8h+String]
0x1801985ad  lea     r8, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1801985b4  mov     edx, r15d
0x1801985b7  mov     rcx, rsi
0x1801985ba  mov     rax, [rax+18h]
0x1801985be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801985c3  test    eax, eax
0x1801985c5  jnz     short loc_1801985EC
0x1801985c7  mov     rcx, [rsp+1B8h+String]; String
0x1801985cc  test    rcx, rcx
0x1801985cf  jz      short loc_1801985EC
0x1801985d1  call    cs:__imp__wtoi
0x1801985d8  nop     dword ptr [rax+rax+00h]
0x1801985dd  mov     [rsp+1B8h+var_A0], eax
0x1801985e4  mov     [rsp+1B8h+var_9C], 1
0x1801985ec  mov     rax, [rsi]
0x1801985ef  lea     r9, [rsp+1B8h+String]
0x1801985f4  lea     r8, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1801985fb  mov     edx, r15d
0x1801985fe  mov     rcx, rsi
0x180198601  mov     rax, [rax+18h]
0x180198605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019860a  test    eax, eax
0x18019860c  jnz     short loc_180198633
0x18019860e  mov     rcx, [rsp+1B8h+String]; String
0x180198613  test    rcx, rcx
0x180198616  jz      short loc_180198633
0x180198618  call    cs:__imp__wtoi
0x18019861f  nop     dword ptr [rax+rax+00h]
0x180198624  mov     [rsp+1B8h+var_98], eax
0x18019862b  mov     [rsp+1B8h+var_94], 1
0x180198633  mov     rax, [rsi]
0x180198636  lea     r9, [rsp+1B8h+String]
0x18019863b  lea     r8, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x180198642  mov     edx, r15d
0x180198645  mov     rcx, rsi
0x180198648  mov     rax, [rax+18h]
0x18019864c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198651  test    eax, eax
0x180198653  jnz     short loc_18019867A
0x180198655  mov     rcx, [rsp+1B8h+String]; String
0x18019865a  test    rcx, rcx
0x18019865d  jz      short loc_18019867A
0x18019865f  call    cs:__imp__wtoi
0x180198666  nop     dword ptr [rax+rax+00h]
0x18019866b  mov     [rsp+1B8h+var_90], eax
0x180198672  mov     [rsp+1B8h+var_8C], 1
0x18019867a  mov     rax, [rsi]
0x18019867d  lea     r9, [rsp+1B8h+String]
0x180198682  lea     r8, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x180198689  mov     edx, r15d
0x18019868c  mov     rcx, rsi
0x18019868f  mov     rax, [rax+18h]
0x180198693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198698  test    eax, eax
0x18019869a  jnz     short loc_1801986C1
0x18019869c  mov     rcx, [rsp+1B8h+String]; String
0x1801986a1  test    rcx, rcx
0x1801986a4  jz      short loc_1801986C1
0x1801986a6  call    cs:__imp__wtoi
0x1801986ad  nop     dword ptr [rax+rax+00h]
0x1801986b2  mov     [rsp+1B8h+var_88], eax
0x1801986b9  mov     [rsp+1B8h+var_84], 1
0x1801986c1  mov     rax, [rsi]
0x1801986c4  lea     r9, [rsp+1B8h+String]
0x1801986c9  lea     r8, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1801986d0  mov     edx, r15d
0x1801986d3  mov     rcx, rsi
0x1801986d6  mov     rax, [rax+18h]
0x1801986da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986df  test    eax, eax
0x1801986e1  jnz     short loc_180198708
0x1801986e3  mov     rcx, [rsp+1B8h+String]; String
0x1801986e8  test    rcx, rcx
0x1801986eb  jz      short loc_180198708
0x1801986ed  call    cs:__imp__wtoi
0x1801986f4  nop     dword ptr [rax+rax+00h]
0x1801986f9  mov     [rsp+1B8h+var_80], eax
0x180198700  mov     [rsp+1B8h+var_7C], 1
0x180198708  mov     rax, [rsi]
0x18019870b  lea     r9, [rsp+1B8h+String]
0x180198710  lea     r8, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x180198717  mov     edx, r15d
0x18019871a  mov     rcx, rsi
0x18019871d  mov     rax, [rax+18h]
0x180198721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198726  test    eax, eax
0x180198728  jnz     short loc_18019874F
0x18019872a  mov     rcx, [rsp+1B8h+String]; String
0x18019872f  test    rcx, rcx
0x180198732  jz      short loc_18019874F
0x180198734  call    cs:__imp__wtoi
0x18019873b  nop     dword ptr [rax+rax+00h]
0x180198740  mov     [rsp+1B8h+var_78], eax
0x180198747  mov     [rsp+1B8h+var_74], 1
0x18019874f  mov     rax, [rsi]
0x180198752  lea     r9, [rsp+1B8h+String]
0x180198757  lea     r8, aEnhancedstorag; "EnhancedStorageDevices"
0x18019875e  mov     edx, r15d
0x180198761  mov     rcx, rsi
0x180198764  mov     rax, [rax+18h]
0x180198768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019876d  test    eax, eax
0x18019876f  jnz     short loc_180198788
0x180198771  mov     rdx, [rsp+1B8h+String]
0x180198776  test    rdx, rdx
0x180198779  jz      short loc_180198788
0x18019877b  lea     rcx, [rsp+1B8h+instance]
0x180198783  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180198788  mov     rax, [rsi]
0x18019878b  lea     r9, [rsp+1B8h+String]
  ... truncated ...
```
