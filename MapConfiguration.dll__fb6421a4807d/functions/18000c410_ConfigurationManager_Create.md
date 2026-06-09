# ConfigurationManager_Create

- ea: `0x18000c410`
- end: `0x18000c612`
- name: `ConfigurationManager_Create`
- size: `514`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c620`

## callees

- `0x180009988`
- `0x18000b4b8`
- `0x18000b4e4`
- `0x18000b6e8`
- `0x18000c410`
- `0x18000c894`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c453`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c4d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c453`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c4d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c515`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c55f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c5e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c515`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c55f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c5e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c606`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c549`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c549`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c430`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c4b1`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c430`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c4b1`

## string_xrefs

- `0x18000c424`: `ConfigurationManager_Create`
- `0x18000c4aa`: `ConfigurationManager_Create`
- `0x18000c540`: `ConfigurationManager_Create`

## pseudocode

```c
__int64 __fastcall ConfigurationManager_Create(_QWORD *a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64; // rax
  unsigned int v11; // [rsp+40h] [rbp+8h]
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp+10h] BYREF
  _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+18h]
  MapControl::Configuration::LocalSettingsInitializer *v14; // [rsp+58h] [rbp+20h]

  if ( !a1 )
  {
    v2 = ZTraceReportOriginationNoThis(-2147467261, "ConfigurationManager_Create", 57);
    goto LABEL_24;
  }
  *a1 = 0;
  EnterCriticalSection(&stru_18007B7A0);
  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v3 = 0;
  v12 = 0;
  v4 = qword_18007B7C8;
  if ( qword_18007B7C8 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)qword_18007B7C8 + 24LL))(
           qword_18007B7C8,
           &GUID_7891c740_e2e2_4dd1_9ef8_fe0e9d4a6747,
           &v12);
    v3 = v12;
  }
  if ( v4 < 0 )
  {
    v5 = 64;
LABEL_7:
    v2 = ZTraceReportOriginationNoThis(v4, "ConfigurationManager_Create", v5);
LABEL_23:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    LeaveCriticalSection(&stru_18007B7A0);
    goto LABEL_24;
  }
  if ( !v3 )
  {
    v13 = &Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex;
    EnterCriticalSection(&Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v6 = Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount;
      if ( !Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount )
      {
        v14 = (MapControl::Configuration::LocalSettingsInitializer *)operator new(1u);
        _InterlockedExchange64(
          &Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstance,
          (__int64)MapControl::Configuration::LocalSettingsInitializer::LocalSettingsInitializer(v14));
        v6 = Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount;
      }
      Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount = v6 + 1;
      LeaveCriticalSection(&Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      v7 = Microsoft::WRL::Details::MakeAndInitialize<ConfigurationManagerAdapter,IConfigurationManager,std::wstring &>(
             &v12,
             (__int64)qword_18007B7D0);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::runtime_error `RTTI Type Descriptor', 0) )
      {
        v11 = ZTraceReportOriginationNoThis(-2147418113, "ConfigurationManager_Create", 81);
        __eh34_try_continuation(0, &std::runtime_error `RTTI Type Descriptor', &loc_18000C5F4);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
        LeaveCriticalSection(&stru_18007B7A0);
        v2 = v11;
LABEL_24:
         = v2;
      }
    }
    if ( v7 < 0 )
    {
      v2 = ZTraceReportPropagationNoThis(v7, "ConfigurationManager_Create", 72);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      LeaveCriticalSection(&stru_18007B7A0);
      goto LABEL_24;
    }
    v8 = qword_18007B7C8;
    qword_18007B7C8 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v9 = Microsoft::WRL::AsWeak<IConfigurationManager>(v12, &qword_18007B7C8);
    if ( v9 < 0 )
    {
      v5 = 84;
      v4 = v9;
      goto LABEL_7;
    }
    v3 = v12;
  }
  v2 = 0;
  if ( v3 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v3)[1])(v3);
    v3 = v12;
  }
  *a1 = v3;
  goto LABEL_23;
}

```

## disassembly

```asm
0x18000c410  push    rbx
0x18000c412  push    rsi
0x18000c413  push    rdi
0x18000c414  sub     rsp, 20h
0x18000c418  mov     rsi, rcx
0x18000c41b  test    rcx, rcx
0x18000c41e  jnz     short loc_18000C43D
0x18000c420  lea     r8d, [rcx+39h]
0x18000c424  lea     rdx, aConfigurationm_5; "ConfigurationManager_Create"
0x18000c42b  mov     ecx, 80004003h
0x18000c430  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c436  mov     edi, eax
0x18000c438  jmp     loc_18000C5EA
0x18000c43d  mov     qword ptr [rcx], 0
0x18000c444  lea     rbx, stru_18007B7A0
0x18000c44b  mov     [rsp+38h+arg_0], rbx
0x18000c450  mov     rcx, rbx; lpCriticalSection
0x18000c453  call    cs:__imp_EnterCriticalSection
0x18000c459  nop
0x18000c45a  mov     [rsp+38h+arg_8], 0
0x18000c463  lea     rcx, [rsp+38h+arg_8]
0x18000c468  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c46d  nop
0x18000c46e  xor     eax, eax
0x18000c470  mov     [rsp+38h+arg_8], rax
0x18000c475  mov     rcx, cs:qword_18007B7C8
0x18000c47c  test    rcx, rcx
0x18000c47f  jz      short loc_18000C4A0
0x18000c481  mov     rax, [rcx]
0x18000c484  lea     r8, [rsp+38h+arg_8]
0x18000c489  lea     rdx, _GUID_7891c740_e2e2_4dd1_9ef8_fe0e9d4a6747
0x18000c490  mov     rax, [rax+18h]
0x18000c494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c499  mov     ecx, eax
0x18000c49b  mov     rax, [rsp+38h+arg_8]
0x18000c4a0  test    ecx, ecx
0x18000c4a2  jns     short loc_18000C4BE
0x18000c4a4  mov     r8d, 40h ; '@'
0x18000c4aa  lea     rdx, aConfigurationm_5; "ConfigurationManager_Create"
0x18000c4b1  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c4b7  mov     edi, eax
0x18000c4b9  jmp     loc_18000C5D6
0x18000c4be  test    rax, rax
0x18000c4c1  jnz     loc_18000C5B5
0x18000c4c7  lea     rdi, ?sInstanceMutex@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex
0x18000c4ce  mov     [rsp+38h+arg_10], rdi
0x18000c4d3  mov     rcx, rdi; lpCriticalSection
0x18000c4d6  call    cs:__imp_EnterCriticalSection
0x18000c4dc  nop
0x18000c4dd  mov     eax, cs:?sInstanceCount@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0HA; int Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount
0x18000c4e3  test    eax, eax
0x18000c4e5  jnz     short loc_18000C50A
0x18000c4e7  lea     ecx, [rax+1]; Size
0x18000c4ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4ef  mov     [rsp+38h+arg_18], rax
0x18000c4f4  mov     rcx, rax; this
0x18000c4f7  call    ??0LocalSettingsInitializer@Configuration@MapControl@@QEAA@XZ; MapControl::Configuration::LocalSettingsInitializer::LocalSettingsInitializer(void)
0x18000c4fc  nop
0x18000c4fd  xchg    rax, cs:?sInstance@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0U?$atomic@PEAVLocalSettingsInitializer@Configuration@MapControl@@@std@@A; std::atomic<MapControl::Configuration::LocalSettingsInitializer *> Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstance
0x18000c504  mov     eax, cs:?sInstanceCount@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0HA; int Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount
0x18000c50a  inc     eax
0x18000c50c  mov     cs:?sInstanceCount@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0HA, eax; int Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceCount
0x18000c512  mov     rcx, rdi; lpCriticalSection
0x18000c515  call    cs:__imp_LeaveCriticalSection
0x18000c51b  lea     rcx, [rsp+38h+arg_8]
0x18000c520  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c525  lea     rdx, qword_18007B7D0
0x18000c52c  lea     rcx, [rsp+38h+arg_8]
0x18000c531  call    ??$MakeAndInitialize@VConfigurationManagerAdapter@@UIConfigurationManager@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIConfigurationManager@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ConfigurationManagerAdapter,IConfigurationManager,std::wstring &>(IConfigurationManager * *,std::wstring &)
0x18000c536  test    eax, eax
0x18000c538  jns     short loc_18000C56A
0x18000c53a  mov     r8d, 48h ; 'H'
0x18000c540  lea     rdx, aConfigurationm_5; "ConfigurationManager_Create"
0x18000c547  mov     ecx, eax
0x18000c549  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c54f  mov     edi, eax
0x18000c551  lea     rcx, [rsp+38h+arg_8]
0x18000c556  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c55b  nop
0x18000c55c  mov     rcx, rbx; lpCriticalSection
0x18000c55f  call    cs:__imp_LeaveCriticalSection
0x18000c565  jmp     loc_18000C5EA
0x18000c56a  mov     rcx, cs:qword_18007B7C8
0x18000c571  mov     cs:qword_18007B7C8, 0
0x18000c57c  test    rcx, rcx
0x18000c57f  jz      short loc_18000C58E
0x18000c581  mov     rax, [rcx]
0x18000c584  mov     rax, [rax+10h]
0x18000c588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c58d  nop
0x18000c58e  lea     rdx, qword_18007B7C8
0x18000c595  mov     rcx, [rsp+38h+arg_8]
0x18000c59a  call    ??$AsWeak@UIConfigurationManager@@@WRL@Microsoft@@YAJPEAUIConfigurationManager@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IConfigurationManager>(IConfigurationManager *,Microsoft::WRL::WeakRef *)
0x18000c59f  test    eax, eax
0x18000c5a1  jns     short loc_18000C5B0
0x18000c5a3  mov     r8d, 54h ; 'T'
0x18000c5a9  mov     ecx, eax
0x18000c5ab  jmp     loc_18000C4AA
0x18000c5b0  mov     rax, [rsp+38h+arg_8]
0x18000c5b5  xor     edi, edi
0x18000c5b7  test    rax, rax
0x18000c5ba  jz      short loc_18000C5D3
0x18000c5bc  mov     rcx, [rax]
0x18000c5bf  mov     rdx, [rcx+8]
0x18000c5c3  mov     rcx, rax
0x18000c5c6  mov     rax, rdx
0x18000c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ce  mov     rax, [rsp+38h+arg_8]
0x18000c5d3  mov     [rsi], rax
0x18000c5d6  lea     rcx, [rsp+38h+arg_8]
0x18000c5db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c5e0  nop
0x18000c5e1  mov     rcx, rbx; lpCriticalSection
0x18000c5e4  call    cs:__imp_LeaveCriticalSection
0x18000c5ea  mov     eax, edi
0x18000c5ec  add     rsp, 20h
0x18000c5f0  pop     rdi
0x18000c5f1  pop     rsi
0x18000c5f2  pop     rbx
0x18000c5f3  retn
0x18000c5f4  lea     rcx, [rsp+38h+arg_8]
0x18000c5f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c5fe  nop
0x18000c5ff  lea     rcx, stru_18007B7A0; lpCriticalSection
0x18000c606  call    cs:__imp_LeaveCriticalSection
0x18000c60c  mov     edi, dword ptr [rsp+38h+arg_0]
0x18000c610  jmp     short loc_18000C5EA
```
