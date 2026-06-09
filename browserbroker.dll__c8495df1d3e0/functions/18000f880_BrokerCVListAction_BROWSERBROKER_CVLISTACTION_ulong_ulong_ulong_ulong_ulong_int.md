# BrokerCVListAction(_BROWSERBROKER_CVLISTACTION,ulong *,ulong *,ulong *,ulong *,ulong *,int *)

- ea: `0x18000f880`
- end: `0x18000facf`
- name: `?BrokerCVListAction@@YAJW4_BROWSERBROKER_CVLISTACTION@@PEAK1111PEAH@Z`
- size: `591`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x180001010`
- `0x180001358`
- `0x180001680`
- `0x180006cc4`
- `0x18000f880`
- `0x18000fad8`
- `0x18001010c`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000f8d8`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fa39`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000f8d8`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fa39`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000f8c9`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fa2a`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000f8c9`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fa2a`
- `urlmon!__imp_CreateReadOnlyBrowserEmulationFilter` at `0x18000f93f`
- `urlmon!__imp_CreateReadOnlyBrowserEmulationFilter` at `0x18000f93f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BrokerCVListAction(
        __int64 a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        int *a7)
{
  int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ebx
  __int64 (*v14)(void); // rax
  int *v15; // rsi
  unsigned int *v16; // r14
  unsigned int *v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  struct IE_GLOBAL_THREAD_STATE *v23; // [rsp+80h] [rbp-31h] BYREF
  int v24; // [rsp+88h] [rbp-29h] BYREF
  unsigned int v25; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v26; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v27; // [rsp+94h] [rbp-1Dh] BYREF
  unsigned int v28; // [rsp+98h] [rbp-19h] BYREF
  unsigned int v29; // [rsp+9Ch] [rbp-15h] BYREF
  __int64 CLSID; // [rsp+A0h] [rbp-11h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v31; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v32[8]; // [rsp+B0h] [rbp-1h] BYREF
  int v33; // [rsp+100h] [rbp+4Fh] BYREF
  unsigned int *v34; // [rsp+108h] [rbp+57h]

  v34 = a2;
  v9 = a1;
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x10000000) )
  {
    v24 = v9;
    LOBYTE(v33) = 1;
    v23 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)&word_180035206,
      v11,
      v12,
      &CLSID,
      &v23,
      (__int64)&v33,
      (__int64)&v24);
  }
  if ( v9 != 1 )
  {
    v23 = 0;
    v13 = CreateReadOnlyBrowserEmulationFilter(4, &v23);
    if ( v13 < 0 )
    {
LABEL_18:
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&v23);
      goto LABEL_19;
    }
    if ( v9 == 2 )
    {
      v14 = *(__int64 (**)(void))(*(_QWORD *)v23 + 48LL);
      goto LABEL_17;
    }
    if ( v9 == 3 )
    {
      v14 = *(__int64 (**)(void))(*(_QWORD *)v23 + 72LL);
      goto LABEL_17;
    }
    if ( v9 != 4 )
    {
      if ( v9 == 5 )
      {
        v14 = *(__int64 (**)(void))(*(_QWORD *)v23 + 56LL);
LABEL_17:
        v13 = v14();
        goto LABEL_18;
      }
      if ( v9 != 6 )
      {
        v13 = -2147418113;
        goto LABEL_18;
      }
    }
    v14 = *(__int64 (**)(void))(*(_QWORD *)v23 + 64LL);
    goto LABEL_17;
  }
  v33 = 4000000;
  v13 = CCVListUpdateManager::DownloadFile((CCVListUpdateManager *)&v33);
LABEL_19:
  v15 = a7;
  v16 = a6;
  v17 = a5;
  CCVListUpdateManager::GetVersions(v34, a3, a4, a5, a6, a7);
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v18, 0x10000000) )
  {
    v24 = *v15;
    v25 = *v16;
    v26 = *v17;
    v27 = *a4;
    v28 = *a3;
    v29 = *v34;
    LODWORD(CLSID) = v13;
    LODWORD(v23) = v9;
    LOBYTE(v33) = 1;
    v31 = GlobalThreadState();
    v32[0] = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (__int64)word_18003511A,
      v20,
      v21,
      v32,
      (__int64 *)&v31,
      (__int64)&v33,
      (__int64)&v23,
      (__int64)&CLSID,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000f880  mov     [rsp-8+arg_10], rbx
0x18000f885  mov     [rsp-8+arg_8], rdx
0x18000f88a  push    rbp
0x18000f88b  push    rsi
0x18000f88c  push    rdi
0x18000f88d  push    r12
0x18000f88f  push    r13
0x18000f891  push    r14
0x18000f893  push    r15
0x18000f895  lea     rbp, [rsp-0Fh]
0x18000f89a  sub     rsp, 0C0h
0x18000f8a1  mov     r12, r9
0x18000f8a4  mov     r13, r8
0x18000f8a7  mov     edi, ecx
0x18000f8a9  mov     eax, cs:dword_18003F000
0x18000f8af  cmp     eax, 5
0x18000f8b2  jbe     short loc_18000F912
0x18000f8b4  mov     edx, 10000000h
0x18000f8b9  call    _tlgKeywordOn
0x18000f8be  test    al, al
0x18000f8c0  jz      short loc_18000F912
0x18000f8c2  mov     [rbp+3Fh+var_68], edi
0x18000f8c5  mov     byte ptr [rbp+3Fh+arg_0], 1
0x18000f8c9  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000f8cf  mov     [rbp+3Fh+var_70], rax
0x18000f8d3  mov     ecx, 10000003h
0x18000f8d8  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000f8de  mov     [rbp+3Fh+var_50], rax
0x18000f8e2  lea     rax, [rbp+3Fh+var_68]
0x18000f8e6  mov     [rsp+0F0h+var_B8], rax
0x18000f8eb  lea     rax, [rbp+3Fh+arg_0]
0x18000f8ef  mov     [rsp+0F0h+var_C0], rax
0x18000f8f4  lea     rax, [rbp+3Fh+var_70]
0x18000f8f8  mov     [rsp+0F0h+var_C8], rax
0x18000f8fd  lea     rax, [rbp+3Fh+var_50]
0x18000f901  mov     [rsp+0F0h+var_D0], rax
0x18000f906  lea     rdx, word_180035206
0x18000f90d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18000f912  cmp     edi, 1
0x18000f915  jnz     short loc_18000F92E
0x18000f917  mov     [rbp+3Fh+arg_0], 3D0900h
0x18000f91e  lea     rcx, [rbp+3Fh+arg_0]; this
0x18000f922  call    ?DownloadFile@CCVListUpdateManager@@QEAAJXZ; CCVListUpdateManager::DownloadFile(void)
0x18000f927  mov     ebx, eax
0x18000f929  jmp     loc_18000F9AF
0x18000f92e  mov     [rbp+3Fh+var_70], 0
0x18000f936  lea     rdx, [rbp+3Fh+var_70]
0x18000f93a  mov     ecx, 4
0x18000f93f  call    cs:__imp_CreateReadOnlyBrowserEmulationFilter
0x18000f945  mov     ebx, eax
0x18000f947  test    eax, eax
0x18000f949  js      short loc_18000F9A6
0x18000f94b  mov     ecx, edi
0x18000f94d  sub     ecx, 2
0x18000f950  jz      short loc_18000F994
0x18000f952  sub     ecx, 1
0x18000f955  jz      short loc_18000F987
0x18000f957  sub     ecx, 1
0x18000f95a  jz      short loc_18000F97A
0x18000f95c  sub     ecx, 1
0x18000f95f  jz      short loc_18000F96D
0x18000f961  cmp     ecx, 1
0x18000f964  jz      short loc_18000F97A
0x18000f966  mov     ebx, 8000FFFFh
0x18000f96b  jmp     short loc_18000F9A6
0x18000f96d  mov     rcx, [rbp+3Fh+var_70]
0x18000f971  mov     rax, [rcx]
0x18000f974  mov     rax, [rax+38h]
0x18000f978  jmp     short loc_18000F99F
0x18000f97a  mov     rcx, [rbp+3Fh+var_70]
0x18000f97e  mov     rax, [rcx]
0x18000f981  mov     rax, [rax+40h]
0x18000f985  jmp     short loc_18000F99F
0x18000f987  mov     rcx, [rbp+3Fh+var_70]
0x18000f98b  mov     rax, [rcx]
0x18000f98e  mov     rax, [rax+48h]
0x18000f992  jmp     short loc_18000F99F
0x18000f994  mov     rcx, [rbp+3Fh+var_70]
0x18000f998  mov     rax, [rcx]
0x18000f99b  mov     rax, [rax+30h]
0x18000f99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9a4  mov     ebx, eax
0x18000f9a6  lea     rcx, [rbp+3Fh+var_70]
0x18000f9aa  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18000f9af  mov     rsi, [rbp+3Fh+arg_30]
0x18000f9b3  mov     [rsp+0F0h+var_C8], rsi; int *
0x18000f9b8  mov     r14, [rbp+3Fh+arg_28]
0x18000f9bc  mov     [rsp+0F0h+var_D0], r14; unsigned int *
0x18000f9c1  mov     r15, [rbp+3Fh+arg_20]
0x18000f9c5  mov     r9, r15; unsigned int *
0x18000f9c8  mov     r8, r12; unsigned int *
0x18000f9cb  mov     rdx, r13; unsigned int *
0x18000f9ce  mov     rcx, [rbp+3Fh+arg_8]; unsigned int *
0x18000f9d2  call    ?GetVersions@CCVListUpdateManager@@SAXPEAK0000PEAH@Z; CCVListUpdateManager::GetVersions(ulong *,ulong *,ulong *,ulong *,ulong *,int *)
0x18000f9d7  mov     eax, cs:dword_18003F000
0x18000f9dd  cmp     eax, 5
0x18000f9e0  jbe     loc_18000FAB2
0x18000f9e6  mov     edx, 10000000h
0x18000f9eb  call    _tlgKeywordOn
0x18000f9f0  test    al, al
0x18000f9f2  jz      loc_18000FAB2
0x18000f9f8  mov     eax, [rsi]
0x18000f9fa  mov     [rbp+3Fh+var_68], eax
0x18000f9fd  mov     eax, [r14]
0x18000fa00  mov     [rbp+3Fh+var_64], eax
0x18000fa03  mov     eax, [r15]
0x18000fa06  mov     [rbp+3Fh+var_60], eax
0x18000fa09  mov     eax, [r12]
0x18000fa0d  mov     [rbp+3Fh+var_5C], eax
0x18000fa10  mov     eax, [r13+0]
0x18000fa14  mov     [rbp+3Fh+var_58], eax
0x18000fa17  mov     rax, [rbp+3Fh+arg_8]
0x18000fa1b  mov     eax, [rax]
0x18000fa1d  mov     [rbp+3Fh+var_54], eax
0x18000fa20  mov     dword ptr [rbp+3Fh+var_50], ebx
0x18000fa23  mov     dword ptr [rbp+3Fh+var_70], edi
0x18000fa26  mov     byte ptr [rbp+3Fh+arg_0], 1
0x18000fa2a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000fa30  mov     [rbp+3Fh+var_48], rax
0x18000fa34  mov     ecx, 10000003h
0x18000fa39  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000fa3f  mov     [rbp+3Fh+var_40], rax
0x18000fa43  lea     rax, [rbp+3Fh+var_68]
0x18000fa47  mov     [rsp+0F0h+var_80], rax
0x18000fa4c  lea     rax, [rbp+3Fh+var_64]
0x18000fa50  mov     [rsp+0F0h+var_88], rax
0x18000fa55  lea     rax, [rbp+3Fh+var_60]
0x18000fa59  mov     [rsp+0F0h+var_90], rax
0x18000fa5e  lea     rax, [rbp+3Fh+var_5C]
0x18000fa62  mov     [rsp+0F0h+var_98], rax
0x18000fa67  lea     rax, [rbp+3Fh+var_58]
0x18000fa6b  mov     [rsp+0F0h+var_A0], rax
0x18000fa70  lea     rax, [rbp+3Fh+var_54]
0x18000fa74  mov     [rsp+0F0h+var_A8], rax
0x18000fa79  lea     rax, [rbp+3Fh+var_50]
0x18000fa7d  mov     [rsp+0F0h+var_B0], rax
0x18000fa82  lea     rax, [rbp+3Fh+var_70]
0x18000fa86  mov     [rsp+0F0h+var_B8], rax
0x18000fa8b  lea     rax, [rbp+3Fh+arg_0]
0x18000fa8f  mov     [rsp+0F0h+var_C0], rax
0x18000fa94  lea     rax, [rbp+3Fh+var_48]
0x18000fa98  mov     [rsp+0F0h+var_C8], rax
0x18000fa9d  lea     rax, [rbp+3Fh+var_40]
0x18000faa1  mov     [rsp+0F0h+var_D0], rax
0x18000faa6  lea     rdx, word_18003511A
0x18000faad  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5555555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000fab2  mov     eax, ebx
0x18000fab4  mov     rbx, [rsp+0F0h+arg_10]
0x18000fabc  add     rsp, 0C0h
0x18000fac3  pop     r15
0x18000fac5  pop     r14
0x18000fac7  pop     r13
0x18000fac9  pop     r12
0x18000facb  pop     rdi
0x18000facc  pop     rsi
0x18000facd  pop     rbp
0x18000face  retn
```
