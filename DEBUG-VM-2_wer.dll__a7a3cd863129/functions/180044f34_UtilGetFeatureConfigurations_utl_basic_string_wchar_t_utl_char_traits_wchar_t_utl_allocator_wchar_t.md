# UtilGetFeatureConfigurations(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180044f34`
- end: `0x180045120`
- name: `?UtilGetFeatureConfigurations@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017a18`

## callees

- `0x18000c390`
- `0x18001fe24`
- `0x18003bf14`
- `0x180043d04`
- `0x180044f34`
- `0x18004a8e0`
- `0x18004cb10`
- `0x180050db0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180044f60`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180044f60`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180045103`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180045103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800450e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800450e9`

## string_xrefs

- `0x180044fc9`: `Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetFeatureConfigurations(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  wchar_t *v8; // rax
  __int64 v9; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+29h] [rbp-3Fh]
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-18h]

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3);
  v4 = RoInitialize(1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v14 = 1;
    v15 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager",
      0x4Du,
      0x4Cu);
    v5 = Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(
           v17,
           &v15);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)v5);
      goto LABEL_23;
    }
    string = 0;
    v6 = v15;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v7(v6, &string);
    if ( v5 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              a1,
                              StringRawBuffer) )
      {
        WindowsDeleteString(string);
        string = 0;
        v5 = 0;
        goto LABEL_23;
      }
      v5 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_17:
        WindowsDeleteString(string);
        string = 0;
LABEL_23:
        utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v15);
        RoUninitialize(v11);
        return (unsigned int)v5;
      }
      v9 = 144;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_17;
      v9 = 143;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v5);
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044f34  push    rbp
0x180044f36  push    rbx
0x180044f37  push    rsi
0x180044f38  push    rdi
0x180044f39  mov     rbp, rsp
0x180044f3c  sub     rsp, 68h
0x180044f40  mov     rax, cs:__security_cookie
0x180044f47  xor     rax, rsp
0x180044f4a  mov     [rbp+var_10], rax
0x180044f4e  mov     rsi, rcx
0x180044f51  test    rcx, rcx
0x180044f54  jnz     short loc_180044F5B
0x180044f56  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044f5b  mov     ecx, 1
0x180044f60  call    cs:__imp_RoInitialize
0x180044f66  mov     ebx, eax
0x180044f68  test    eax, eax
0x180044f6a  jns     short loc_180044FAB
0x180044f6c  lea     rcx, WPP_GLOBAL_Control
0x180044f73  mov     r10, cs:WPP_GLOBAL_Control
0x180044f7a  cmp     r10, rcx
0x180044f7d  jz      loc_180045109
0x180044f83  test    byte ptr [r10+1Ch], 1
0x180044f88  jz      loc_180045109
0x180044f8e  mov     edx, 8Dh
0x180044f93  mov     r9d, eax
0x180044f96  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180044f9d  mov     rcx, [r10+10h]
0x180044fa1  call    WPP_SF_d
0x180044fa6  jmp     loc_180045109
0x180044fab  mov     [rbp+var_3F], 1
0x180044faf  mov     [rbp+var_38], 0
0x180044fb7  mov     [rbp+var_18], 0
0x180044fbf  mov     r9d, 4Ch ; 'L'; unsigned int
0x180044fc5  lea     r8d, [r9+1]; unsigned int
0x180044fc9  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_FeatureConfiguration_FeatureConfigurationsManager@@3QB_WB; "Windows.Internal.Flighting.FeatureConfi"...
0x180044fd0  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180044fd4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180044fd9  nop
0x180044fda  lea     rdx, [rbp+var_38]
0x180044fde  mov     rcx, [rbp+var_18]
0x180044fe2  call    ??$ActivateInstance@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(HSTRING__ *,Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager * *)
0x180044fe7  mov     ebx, eax
0x180044fe9  test    eax, eax
0x180044feb  jns     short loc_180045024
0x180044fed  lea     rcx, WPP_GLOBAL_Control
0x180044ff4  mov     rax, cs:WPP_GLOBAL_Control
0x180044ffb  cmp     rax, rcx
0x180044ffe  jz      short loc_18004501F
0x180045000  test    byte ptr [rax+1Ch], 1
0x180045004  jz      short loc_18004501F
0x180045006  mov     edx, 8Eh
0x18004500b  mov     r9d, ebx
0x18004500e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180045015  mov     rcx, [rax+10h]
0x180045019  call    WPP_SF_d
0x18004501e  nop
0x18004501f  jmp     loc_1800450F9
0x180045024  mov     [rbp+string], 0
0x18004502c  mov     rdi, [rbp+var_38]
0x180045030  mov     rax, [rdi]
0x180045033  mov     rbx, [rax+40h]
0x180045037  xor     ecx, ecx; string
0x180045039  call    cs:__imp_WindowsDeleteString
0x18004503f  mov     [rbp+string], 0
0x180045047  lea     rdx, [rbp+string]
0x18004504b  mov     rcx, rdi
0x18004504e  mov     rax, rbx
0x180045051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045056  mov     ebx, eax
0x180045058  test    eax, eax
0x18004505a  jns     short loc_1800450A5
0x18004505c  lea     rcx, WPP_GLOBAL_Control
0x180045063  mov     rax, cs:WPP_GLOBAL_Control
0x18004506a  cmp     rax, rcx
0x18004506d  jz      short loc_18004508E
0x18004506f  test    byte ptr [rax+1Ch], 1
0x180045073  jz      short loc_18004508E
0x180045075  mov     edx, 8Fh
0x18004507a  mov     r9d, ebx
0x18004507d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180045084  mov     rcx, [rax+10h]
0x180045088  call    WPP_SF_d
0x18004508d  nop
0x18004508e  mov     rcx, [rbp+string]; string
0x180045092  call    cs:__imp_WindowsDeleteString
0x180045098  mov     [rbp+string], 0
0x1800450a0  jmp     loc_18004501F
0x1800450a5  xor     edx, edx; length
0x1800450a7  mov     rcx, [rbp+string]; string
0x1800450ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800450b1  mov     rdx, rax
0x1800450b4  mov     rcx, rsi
0x1800450b7  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800450bc  test    al, al
0x1800450be  jnz     short loc_1800450E5
0x1800450c0  mov     ebx, 8007000Eh
0x1800450c5  lea     rcx, WPP_GLOBAL_Control
0x1800450cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800450d3  cmp     rax, rcx
0x1800450d6  jz      short loc_18004508E
0x1800450d8  test    byte ptr [rax+1Ch], 1
0x1800450dc  jz      short loc_18004508E
0x1800450de  mov     edx, 90h
0x1800450e3  jmp     short loc_18004507A
0x1800450e5  mov     rcx, [rbp+string]; string
0x1800450e9  call    cs:__imp_WindowsDeleteString
0x1800450ef  mov     [rbp+string], 0
0x1800450f7  xor     ebx, ebx
0x1800450f9  lea     rcx, [rbp+var_38]
0x1800450fd  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x180045102  nop
0x180045103  call    cs:__imp_RoUninitialize
0x180045109  mov     eax, ebx
0x18004510b  mov     rcx, [rbp+var_10]
0x18004510f  xor     rcx, rsp; StackCookie
0x180045112  call    __security_check_cookie
0x180045117  add     rsp, 68h
0x18004511b  pop     rdi
0x18004511c  pop     rsi
0x18004511d  pop     rbx
0x18004511e  pop     rbp
0x18004511f  retn
```
