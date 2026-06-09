# VAD_EndpointBuilderServiceStart

- ea: `0x180047854`
- end: `0x180047bf2`
- name: `VAD_EndpointBuilderServiceStart`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045be0`

## callees

- `0x180005358`
- `0x18001f374`
- `0x180024ca0`
- `0x18002658c`
- `0x180029024`
- `0x180033464`
- `0x180034c5c`
- `0x180038b64`
- `0x18003984c`
- `0x18003f7a4`
- `0x180047854`
- `0x180047bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800478bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800478bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047a02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047a02`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180047a41`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180047a41`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180047a7a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180047a9c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180047a7a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180047a9c`

## string_xrefs

- `0x180047a55`: `avcore\audiocore\server\audioendpointbuilder\dll\audioepbservice.cpp`
- `0x1800479c3`: `MidisrvTransferComplete`
- `0x180047a2c`: `MidisrvTransferComplete`

## pseudocode

```c
__int64 VAD_EndpointBuilderServiceStart()
{
  const struct _tlgProvider_t *v0; // rax
  struct _RTL_CRITICAL_SECTION *v1; // rax
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  CMidiBuilder *v3; // rax
  CMidiBuilder *v4; // rcx
  CAvEndpointBuilder *v5; // rcx
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  void *v13; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF

  v0 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v0 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v0,
      (unsigned __int8 *)&byte_180074A0F);
  v1 = (struct _RTL_CRITICAL_SECTION *)operator new(0x70u);
  v2 = v1;
  if ( !v1 )
  {
    AvEndpointBuilder = 0;
    v6 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = 16;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  memset_0(v1, 0, 0x70u);
  InitializeCriticalSectionEx(v2, 0, 0);
  v2[1].DebugInfo = 0;
  *(_QWORD *)&v2[1].LockCount = 0;
  v2[1].OwningThread = 0;
  v2[1].LockSemaphore = 0;
  LODWORD(v2[1].SpinCount) = 20;
  BYTE4(v2[1].SpinCount) = 0;
  v2[2].DebugInfo = 0;
  *(_QWORD *)&v2[2].LockCount = 0;
  LODWORD(v2[2].OwningThread) = 0;
  v2[2].LockSemaphore = 0;
  AvEndpointBuilder = v2;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl) )
  {
    v3 = (CMidiBuilder *)operator new(0x10u);
    if ( !v3 )
    {
      MidiBuilder = 0;
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = 17;
        goto LABEL_44;
      }
LABEL_45:
      VAD_EndpointBuilderServiceStop();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_706bdd9d526432e921f5f2c174ef9912_Traceguids);
      }
      return (unsigned int)v6;
    }
    *(_QWORD *)v3 = 0;
    *((_WORD *)v3 + 4) = 0;
    MidiBuilder = v3;
    v6 = CMidiBuilder::Initialize(v4);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = 18;
LABEL_44:
        WPP_SF_(v7[2], v8, WPP_706bdd9d526432e921f5f2c174ef9912_Traceguids);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
  }
  else
  {
    v9 = operator new(1u);
    if ( !v9 )
    {
      BleMidiEndpointBuilder = 0;
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = 19;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    BleMidiEndpointBuilder = v9;
    Data = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
            L"MidisrvTransferComplete",
            0x18u,
            0,
            &Data,
            &pcbData)
      && Data == 1 )
    {
      Data = 0;
      v10 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
              L"MidisrvTransferComplete",
              4u,
              &Data,
              4u);
      if ( v10 )
      {
        v11 = 1659;
      }
      else
      {
        v10 = RegDeleteKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
                L"midi1");
        if ( v10 )
        {
          v11 = 1660;
        }
        else
        {
          v10 = RegDeleteKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
                  L"midi1");
          if ( !v10 )
            goto LABEL_25;
          v11 = 1662;
        }
      }
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v11,
               (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioepbservice.cpp",
               (const char *)v10,
               pdwType);
    }
  }
LABEL_25:
  v6 = CAvEndpointBuilder::Initialize(v5);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = 20;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  v13 = operator new(1u);
  if ( !v13 )
  {
    AudioEndpointPluginBuilder = 0;
    v6 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = 21;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  AudioEndpointPluginBuilder = v13;
  return 0;
}

```

## disassembly

```asm
0x180047854  mov     [rsp+arg_10], rbx
0x180047859  mov     [rsp+arg_18], rbp
0x18004785e  push    rsi
0x18004785f  push    rdi
0x180047860  push    r14
0x180047862  sub     rsp, 40h
0x180047866  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18004786b  mov     esi, 4
0x180047870  mov     ecx, [rax]
0x180047872  cmp     ecx, esi
0x180047874  jbe     short loc_180047885
0x180047876  lea     rdx, byte_180074A0F
0x18004787d  mov     rcx, rax
0x180047880  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180047885  mov     r14d, 70h ; 'p'
0x18004788b  mov     ecx, r14d; unsigned __int64
0x18004788e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047893  xor     edi, edi
0x180047895  lea     rbp, WPP_706bdd9d526432e921f5f2c174ef9912_Traceguids
0x18004789c  mov     rbx, rax
0x18004789f  test    rax, rax
0x1800478a2  jz      loc_180047B70
0x1800478a8  mov     r8d, r14d; Size
0x1800478ab  xor     edx, edx; Val
0x1800478ad  mov     rcx, rax; void *
0x1800478b0  call    memset_0
0x1800478b5  xor     r8d, r8d; Flags
0x1800478b8  xor     edx, edx; dwSpinCount
0x1800478ba  mov     rcx, rbx; lpCriticalSection
0x1800478bd  call    cs:__imp_InitializeCriticalSectionEx
0x1800478c3  mov     [rbx+28h], rdi
0x1800478c7  mov     [rbx+30h], rdi
0x1800478cb  mov     [rbx+38h], rdi
0x1800478cf  mov     [rbx+40h], rdi
0x1800478d3  mov     dword ptr [rbx+48h], 14h
0x1800478da  mov     [rbx+4Ch], dil
0x1800478de  mov     [rbx+50h], rdi
0x1800478e2  mov     [rbx+58h], rdi
0x1800478e6  mov     [rbx+60h], edi
0x1800478e9  mov     [rbx+68h], rdi
0x1800478ed  mov     cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA, rbx; CAvEndpointBuilder * AvEndpointBuilder
0x1800478f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MIDI2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2> `wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl(void)'::`2'::impl
0x1800478fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(void)
0x180047900  lea     r14d, [rdi+1]
0x180047904  test    al, al
0x180047906  jz      loc_1800479AB
0x18004790c  lea     ecx, [rdi+10h]; unsigned __int64
0x18004790f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047914  test    rax, rax
0x180047917  jz      short loc_18004796A
0x180047919  mov     [rax], rdi
0x18004791c  mov     [rax+8], di
0x180047920  mov     cs:?MidiBuilder@@3PEAVCMidiBuilder@@EA, rax; CMidiBuilder * MidiBuilder
0x180047927  call    ?Initialize@CMidiBuilder@@QEAAJXZ; CMidiBuilder::Initialize(void)
0x18004792c  mov     ebx, eax
0x18004792e  test    eax, eax
0x180047930  jns     loc_180047AAD
0x180047936  mov     rcx, cs:WPP_GLOBAL_Control
0x18004793d  lea     rdi, WPP_GLOBAL_Control
0x180047944  cmp     rcx, rdi
0x180047947  jz      loc_180047BAC
0x18004794d  test    [rcx+1Ch], sil
0x180047951  jz      loc_180047BAC
0x180047957  cmp     [rcx+19h], sil
0x18004795b  jb      loc_180047BAC
0x180047961  lea     edx, [r14+11h]
0x180047965  jmp     loc_180047BA0
0x18004796a  mov     cs:?MidiBuilder@@3PEAVCMidiBuilder@@EA, rdi; CMidiBuilder * MidiBuilder
0x180047971  mov     ebx, 8007000Eh
0x180047976  mov     rcx, cs:WPP_GLOBAL_Control
0x18004797d  lea     rdi, WPP_GLOBAL_Control
0x180047984  cmp     rcx, rdi
0x180047987  jz      loc_180047BAC
0x18004798d  test    [rcx+1Ch], sil
0x180047991  jz      loc_180047BAC
0x180047997  cmp     [rcx+19h], sil
0x18004799b  jb      loc_180047BAC
0x1800479a1  mov     edx, 11h
0x1800479a6  jmp     loc_180047BA0
0x1800479ab  mov     rcx, r14; unsigned __int64
0x1800479ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800479b3  test    rax, rax
0x1800479b6  jz      loc_180047B3E
0x1800479bc  mov     cs:?BleMidiEndpointBuilder@@3PEAVCBleMidiEndpointBuilder@@EA, rax; CBleMidiEndpointBuilder * BleMidiEndpointBuilder
0x1800479c3  lea     r8, ?midisrvTransferComplete@@3QBGB; "MidisrvTransferComplete"
0x1800479ca  lea     rax, [rsp+58h+arg_8]
0x1800479cf  mov     [rsp+58h+Data], edi
0x1800479d3  mov     [rsp+58h+pcbData], rax; pcbData
0x1800479d8  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800479df  lea     rax, [rsp+58h+Data]
0x1800479e4  mov     [rsp+58h+arg_8], esi
0x1800479e8  mov     [rsp+58h+pvData], rax; pvData
0x1800479ed  mov     rbx, 0FFFFFFFF80000002h
0x1800479f4  mov     r9d, 18h; dwFlags
0x1800479fa  mov     [rsp+58h+pdwType], rdi; pdwType
0x1800479ff  mov     rcx, rbx; hkey
0x180047a02  call    cs:__imp_RegGetValueW
0x180047a08  test    eax, eax
0x180047a0a  jnz     loc_180047AAD
0x180047a10  cmp     [rsp+58h+Data], r14d
0x180047a15  jnz     loc_180047AAD
0x180047a1b  lea     rax, [rsp+58h+Data]
0x180047a20  mov     dword ptr [rsp+58h+pvData], esi; cbData
0x180047a24  mov     r9d, esi; dwType
0x180047a27  mov     [rsp+58h+pdwType], rax; unsigned int
0x180047a2c  lea     r8, ?midisrvTransferComplete@@3QBGB; "MidisrvTransferComplete"
0x180047a33  mov     [rsp+58h+Data], edi
0x180047a37  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180047a3e  mov     rcx, rbx; hKey
0x180047a41  call    cs:__imp_RegSetKeyValueW
0x180047a47  test    eax, eax
0x180047a49  jz      short loc_180047A69
0x180047a4b  mov     edx, 67Bh; void *
0x180047a50  mov     rcx, [rsp+58h]; this
0x180047a55  lea     r8, aAvcoreAudiocor_12; "avcore\\audiocore\\server\\audioendpoin"...
0x180047a5c  mov     r9d, eax; char *
0x180047a5f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047a64  jmp     loc_180047BDF
0x180047a69  lea     r8, ?midi2Alias@@3QBGB; "midi1"
0x180047a70  mov     rcx, rbx; hKey
0x180047a73  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180047a7a  call    cs:__imp_RegDeleteKeyValueW
0x180047a80  test    eax, eax
0x180047a82  jz      short loc_180047A8B
0x180047a84  mov     edx, 67Ch
0x180047a89  jmp     short loc_180047A50
0x180047a8b  lea     r8, ?midi2Alias@@3QBGB; "midi1"
0x180047a92  mov     rcx, rbx; hKey
0x180047a95  lea     rdx, ?driver32WowPath@@3QBGB; "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x180047a9c  call    cs:__imp_RegDeleteKeyValueW
0x180047aa2  test    eax, eax
0x180047aa4  jz      short loc_180047AAD
0x180047aa6  mov     edx, 67Eh
0x180047aab  jmp     short loc_180047A50
0x180047aad  call    ?Initialize@CAvEndpointBuilder@@QEAAJXZ; CAvEndpointBuilder::Initialize(void)
0x180047ab2  mov     ebx, eax
0x180047ab4  test    eax, eax
0x180047ab6  jns     short loc_180047AED
0x180047ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180047abf  lea     rdi, WPP_GLOBAL_Control
0x180047ac6  cmp     rcx, rdi
0x180047ac9  jz      loc_180047BAC
0x180047acf  test    [rcx+1Ch], sil
0x180047ad3  jz      loc_180047BAC
0x180047ad9  cmp     [rcx+19h], sil
0x180047add  jb      loc_180047BAC
0x180047ae3  mov     edx, 14h
0x180047ae8  jmp     loc_180047BA0
0x180047aed  mov     rcx, r14; unsigned __int64
0x180047af0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047af5  test    rax, rax
0x180047af8  jz      short loc_180047B08
0x180047afa  mov     cs:?AudioEndpointPluginBuilder@@3PEAVCAudioEndpointPluginBuilder@@EA, rax; CAudioEndpointPluginBuilder * AudioEndpointPluginBuilder
0x180047b01  mov     ebx, edi
0x180047b03  jmp     loc_180047BDD
0x180047b08  mov     cs:?AudioEndpointPluginBuilder@@3PEAVCAudioEndpointPluginBuilder@@EA, rdi; CAudioEndpointPluginBuilder * AudioEndpointPluginBuilder
0x180047b0f  mov     ebx, 8007000Eh
0x180047b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b1b  lea     rdi, WPP_GLOBAL_Control
0x180047b22  cmp     rcx, rdi
0x180047b25  jz      loc_180047BAC
0x180047b2b  test    [rcx+1Ch], sil
0x180047b2f  jz      short loc_180047BAC
0x180047b31  cmp     [rcx+19h], sil
0x180047b35  jb      short loc_180047BAC
0x180047b37  mov     edx, 15h
0x180047b3c  jmp     short loc_180047BA0
0x180047b3e  mov     cs:?BleMidiEndpointBuilder@@3PEAVCBleMidiEndpointBuilder@@EA, rdi; CBleMidiEndpointBuilder * BleMidiEndpointBuilder
0x180047b45  mov     ebx, 8007000Eh
0x180047b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b51  lea     rdi, WPP_GLOBAL_Control
0x180047b58  cmp     rcx, rdi
0x180047b5b  jz      short loc_180047BAC
0x180047b5d  test    [rcx+1Ch], sil
0x180047b61  jz      short loc_180047BAC
0x180047b63  cmp     [rcx+19h], sil
0x180047b67  jb      short loc_180047BAC
0x180047b69  mov     edx, 13h
0x180047b6e  jmp     short loc_180047BA0
0x180047b70  mov     cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA, rdi; CAvEndpointBuilder * AvEndpointBuilder
0x180047b77  mov     ebx, 8007000Eh
0x180047b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b83  lea     rdi, WPP_GLOBAL_Control
0x180047b8a  cmp     rcx, rdi
0x180047b8d  jz      short loc_180047BAC
0x180047b8f  test    [rcx+1Ch], sil
0x180047b93  jz      short loc_180047BAC
0x180047b95  cmp     [rcx+19h], sil
0x180047b99  jb      short loc_180047BAC
0x180047b9b  mov     edx, 10h
0x180047ba0  mov     rcx, [rcx+10h]
0x180047ba4  mov     r8, rbp
0x180047ba7  call    WPP_SF_
0x180047bac  call    VAD_EndpointBuilderServiceStop
0x180047bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bb8  cmp     rcx, rdi
0x180047bbb  jz      short loc_180047BDD
0x180047bbd  test    byte ptr [rcx+1Ch], 40h
0x180047bc1  jz      short loc_180047BDD
0x180047bc3  cmp     byte ptr [rcx+19h], 2
0x180047bc7  jb      short loc_180047BDD
0x180047bc9  mov     rcx, [rcx+10h]
0x180047bcd  mov     edx, 17h
0x180047bd2  mov     r9d, ebx
0x180047bd5  mov     r8, rbp
0x180047bd8  call    WPP_SF_d
0x180047bdd  mov     eax, ebx
0x180047bdf  mov     rbx, [rsp+58h+arg_10]
0x180047be4  mov     rbp, [rsp+58h+arg_18]
0x180047be9  add     rsp, 40h
0x180047bed  pop     r14
0x180047bef  pop     rdi
0x180047bf0  pop     rsi
0x180047bf1  retn
```
