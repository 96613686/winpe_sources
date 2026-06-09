# WaasMedic::UsoHelper::Initialize(void)

- ea: `0x180055fb8`
- end: `0x1800561b9`
- name: `?Initialize@UsoHelper@WaasMedic@@QEAAJXZ`
- size: `513`
- prototype: `__int64 __fastcall(WaasMedic::UsoHelper *__hidden this)`
- caller_count: `10`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800387e0`
- `0x18003a650`
- `0x18003c3c0`
- `0x18003c8d0`
- `0x180040490`
- `0x18004d5ac`
- `0x18004e150`
- `0x18004e660`
- `0x180051c80`
- `0x180053d7c`

## callees

- `0x1800024a4`
- `0x180016c9c`
- `0x1800178e8`
- `0x18002543c`
- `0x180055fb8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005600b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005600b`

## string_xrefs

- `0x180056017`: `Unable to CoCreateInstance UpdateSessionOrchestrator. hr=0x%08x`
- `0x1800560a0`: `Unable to create update manager from IMoUsoOrchestrator. hr=0x%08x`
- `0x1800560fe`: `Unable to create UX update manager from IMoUsoOrchestrator. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::UsoHelper::Initialize(WaasMedic::UsoHelper *this)
{
  unsigned __int16 *v2; // rbx
  int v3; // edi
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(unsigned __int16 *, const wchar_t *, const OLECHAR *, WaasMedic::UsoHelper *); // rdi
  __int64 v7; // rcx
  int v8; // eax
  __int64 (__fastcall *v9)(unsigned __int16 *, const wchar_t *, char *); // r14
  __int64 v10; // rcx
  int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  int v13; // r9d
  unsigned __int16 *v15; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int16 *v17; // [rsp+80h] [rbp+40h] BYREF
  __int64 v18; // [rsp+88h] [rbp+48h] BYREF

  ppv = 0;
  v2 = 0;
  v17 = 0;
  if ( *((_BYTE *)this + 16) )
  {
    v3 = -2147023649;
LABEL_17:
    v12 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      v5 = *((_QWORD *)v12 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v5 & 0x400000000000LL) == v5 )
      {
        LODWORD(v15) = v3;
        v17 = &gc_pszVersionString;
        v18 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v12,
          (unsigned int)&word_18008A3FE,
          0,
          v13,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v15);
      }
    }
    goto LABEL_21;
  }
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
         &ppv);
  v3 = v4;
  if ( v4 >= 0 )
  {
    v15 = 0;
    (**(void (__fastcall ***)(LPVOID, GUID *, unsigned __int16 **))ppv)(
      ppv,
      &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
      &v15);
    v2 = v15;
    v17 = v15;
    v6 = *(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, const OLECHAR *, WaasMedic::UsoHelper *))(*(_QWORD *)v15 + 24LL);
    v7 = *(_QWORD *)this;
    *(_QWORD *)this = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = v6(v2, L"WaaSMedic", &word_18006939C, this);
    v3 = v8;
    if ( v8 >= 0 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
        goto LABEL_15;
      v9 = *(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, char *))(*(_QWORD *)v2 + 40LL);
      v10 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 1) = 0;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v11 = v9(v2, L"WaaSMedic", (char *)this + 8);
      v3 = v11;
      if ( v11 < 0 )
        LogLevelW(2u, L"Unable to create UX update manager from IMoUsoOrchestrator. hr=0x%08x", (unsigned int)v11);
      else
LABEL_15:
        *((_BYTE *)this + 16) = 1;
    }
    else
    {
      LogLevelW(2u, L"Unable to create update manager from IMoUsoOrchestrator. hr=0x%08x", (unsigned int)v8);
    }
  }
  else
  {
    LogLevelW(2u, L"Unable to CoCreateInstance UpdateSessionOrchestrator. hr=0x%08x", (unsigned int)v4);
  }
  if ( v3 < 0 )
    goto LABEL_17;
LABEL_21:
  if ( v2 )
    (*(void (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v2 + 16LL))(v2, v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 16LL))(ppv, v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180055fb8  push    rbp
0x180055fba  push    rbx
0x180055fbb  push    rsi
0x180055fbc  push    rdi
0x180055fbd  push    r14
0x180055fbf  mov     rbp, rsp
0x180055fc2  sub     rsp, 40h
0x180055fc6  mov     rsi, rcx
0x180055fc9  mov     [rbp+arg_8], 0
0x180055fd1  xor     ebx, ebx
0x180055fd3  mov     [rbp+arg_10], rbx
0x180055fd7  cmp     [rcx+10h], bl
0x180055fda  jz      short loc_180055FE6
0x180055fdc  mov     edi, 800704DFh
0x180055fe1  jmp     loc_180056112
0x180055fe6  mov     [rbp+arg_8], 0
0x180055fee  lea     rax, [rbp+arg_8]
0x180055ff2  mov     [rsp+40h+ppv], rax; ppv
0x180055ff7  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x180055ffe  xor     edx, edx; pUnkOuter
0x180056000  lea     r8d, [rdx+4]; dwClsContext
0x180056004  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x18005600b  call    cs:__imp_CoCreateInstance
0x180056011  mov     edi, eax
0x180056013  test    eax, eax
0x180056015  jns     short loc_180056030
0x180056017  lea     rdx, aUnableToCocrea_0; "Unable to CoCreateInstance UpdateSessio"...
0x18005601e  mov     r8d, eax
0x180056021  mov     ecx, 2; unsigned __int8
0x180056026  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005602b  jmp     loc_18005610E
0x180056030  mov     rcx, [rbp+arg_8]
0x180056034  mov     [rbp+arg_0], 0
0x18005603c  mov     rax, [rcx]
0x18005603f  lea     r8, [rbp+arg_0]
0x180056043  lea     rdx, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a
0x18005604a  mov     rax, [rax]
0x18005604d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056052  nop
0x180056053  mov     rbx, [rbp+arg_0]
0x180056057  mov     [rbp+arg_10], rbx
0x18005605b  mov     rax, [rbx]
0x18005605e  mov     rdi, [rax+18h]
0x180056062  mov     rcx, [rsi]
0x180056065  mov     qword ptr [rsi], 0
0x18005606c  test    rcx, rcx
0x18005606f  jz      short loc_18005607E
0x180056071  mov     rax, [rcx]
0x180056074  mov     rax, [rax+10h]
0x180056078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005607d  nop
0x18005607e  mov     r9, rsi
0x180056081  lea     r8, word_18006939C
0x180056088  lea     rdx, aWaasmedic_1; "WaaSMedic"
0x18005608f  mov     rcx, rbx
0x180056092  mov     rax, rdi
0x180056095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005609a  mov     edi, eax
0x18005609c  test    eax, eax
0x18005609e  jns     short loc_1800560AC
0x1800560a0  lea     rdx, aUnableToCreate_0; "Unable to create update manager from IM"...
0x1800560a7  jmp     loc_18005601E
0x1800560ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCPPluginSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport> `wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl(void)'::`2'::impl
0x1800560b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(void)
0x1800560b8  test    al, al
0x1800560ba  jz      short loc_18005610A
0x1800560bc  mov     rax, [rbx]
0x1800560bf  mov     r14, [rax+28h]
0x1800560c3  lea     rdi, [rsi+8]
0x1800560c7  mov     rcx, [rdi]
0x1800560ca  mov     qword ptr [rdi], 0
0x1800560d1  test    rcx, rcx
0x1800560d4  jz      short loc_1800560E3
0x1800560d6  mov     r9, [rcx]
0x1800560d9  mov     rax, [r9+10h]
0x1800560dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560e2  nop
0x1800560e3  mov     r8, rdi
0x1800560e6  lea     rdx, aWaasmedic_1; "WaaSMedic"
0x1800560ed  mov     rcx, rbx
0x1800560f0  mov     rax, r14
0x1800560f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560f8  mov     edi, eax
0x1800560fa  test    eax, eax
0x1800560fc  jns     short loc_18005610A
0x1800560fe  lea     rdx, aUnableToCreate; "Unable to create UX update manager from"...
0x180056105  jmp     loc_18005601E
0x18005610a  mov     byte ptr [rsi+10h], 1
0x18005610e  test    edi, edi
0x180056110  jns     short loc_180056181
0x180056112  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180056117  mov     ecx, [rax]
0x180056119  cmp     ecx, 5
0x18005611c  jbe     short loc_180056181
0x18005611e  mov     rdx, [rax+18h]
0x180056122  mov     rcx, [rax+10h]
0x180056126  mov     r8, 400000000000h
0x180056130  test    r8, rcx
0x180056133  jz      short loc_180056181
0x180056135  mov     rcx, rdx
0x180056138  and     rcx, r8
0x18005613b  cmp     rcx, rdx
0x18005613e  jnz     short loc_180056181
0x180056140  mov     dword ptr [rbp+arg_0], edi
0x180056143  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18005614a  mov     [rbp+arg_10], rcx
0x18005614e  mov     [rbp+arg_18], 1000000h
0x180056156  lea     rcx, [rbp+arg_0]
0x18005615a  mov     [rsp+40h+var_10], rcx
0x18005615f  lea     rcx, [rbp+arg_10]
0x180056163  mov     [rsp+40h+var_18], rcx
0x180056168  lea     rcx, [rbp+arg_18]
0x18005616c  mov     [rsp+40h+ppv], rcx
0x180056171  lea     rdx, word_18008A3FE
0x180056178  mov     rcx, rax
0x18005617b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180056180  nop
0x180056181  test    rbx, rbx
0x180056184  jz      short loc_180056196
0x180056186  mov     rax, [rbx]
0x180056189  mov     rcx, rbx
0x18005618c  mov     rax, [rax+10h]
0x180056190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056195  nop
0x180056196  mov     rcx, [rbp+arg_8]
0x18005619a  test    rcx, rcx
0x18005619d  jz      short loc_1800561AC
0x18005619f  mov     rax, [rcx]
0x1800561a2  mov     rax, [rax+10h]
0x1800561a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561ab  nop
0x1800561ac  mov     eax, edi
0x1800561ae  add     rsp, 40h
0x1800561b2  pop     r14
0x1800561b4  pop     rdi
0x1800561b5  pop     rsi
0x1800561b6  pop     rbx
0x1800561b7  pop     rbp
0x1800561b8  retn
```
