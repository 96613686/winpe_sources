# UtilGetFeatureConfigurations(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800e5728`
- end: `0x1800e5988`
- name: `?UtilGetFeatureConfigurations@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18019c878`

## callees

- `0x1800e4454`
- `0x1800e5728`
- `0x1800e5990`
- `0x1801c1134`
- `0x1801e19ac`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e58cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e58cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e57e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e57e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e5782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e5782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5924`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800e582c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800e582c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800e574a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800e574a`

## string_xrefs

- `0x1800e577b`: `Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UtilGetFeatureConfigurations(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  HRESULT v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  __int64 v7; // rcx
  HSTRING v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  char v11; // [rsp+31h] [rbp-37h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h] BYREF

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v11 = 1;
    v10 = 0;
    string = 0;
    v4 = WindowsCreateStringReference(
           L"Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager",
           0x4Cu,
           &hstringHeader,
           &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
      __debugbreak();
    }
    v3 = Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(
           string,
           &v10);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)v3);
    }
    else
    {
      v9 = 0;
      v5 = v10;
      v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 64LL);
      WindowsDeleteString(0);
      v9 = 0;
      v3 = v6(v5, &v9);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            143,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (unsigned int)v3);
        WindowsDeleteString(v9);
        v9 = 0;
        v7 = v10;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_9;
      }
      WindowsGetStringRawBuffer(v9, 0);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1) )
      {
        WindowsDeleteString(v9);
        v9 = 0;
        v7 = v10;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v3 = 0;
        goto LABEL_9;
      }
      v3 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          2147942414LL);
      WindowsDeleteString(v9);
      v9 = 0;
    }
    utl::unique_ptr<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,tlx::release_delete>::~unique_ptr<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,tlx::release_delete>(&v10);
LABEL_9:
    RoUninitialize(v7);
    return (unsigned int)v3;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800e5728  push    rbp
0x1800e572a  push    rbx
0x1800e572b  push    rsi
0x1800e572c  push    rdi
0x1800e572d  mov     rbp, rsp
0x1800e5730  sub     rsp, 68h
0x1800e5734  mov     rax, cs:__security_cookie
0x1800e573b  xor     rax, rsp
0x1800e573e  mov     [rbp+var_10], rax
0x1800e5742  mov     rsi, rcx
0x1800e5745  mov     ecx, 1
0x1800e574a  call    cs:__imp_RoInitialize
0x1800e5750  mov     ebx, eax
0x1800e5752  test    eax, eax
0x1800e5754  js      loc_1800E5849
0x1800e575a  mov     [rbp+var_37], 1
0x1800e575e  mov     [rbp+var_40], 0
0x1800e5766  mov     [rbp+string], 0
0x1800e576e  lea     r9, [rbp+string]; string
0x1800e5772  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e5776  mov     edx, 4Ch ; 'L'; length
0x1800e577b  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_FeatureConfiguration_FeatureConfigurationsManager@@3QB_WB; "Windows.Internal.Flighting.FeatureConfi"...
0x1800e5782  call    cs:__imp_WindowsCreateStringReference
0x1800e5788  test    eax, eax
0x1800e578a  js      loc_1800E58C1
0x1800e5790  lea     rdx, [rbp+var_40]
0x1800e5794  mov     rcx, [rbp+string]
0x1800e5798  call    ??$ActivateInstance@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(HSTRING__ *,Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager * *)
0x1800e579d  mov     ebx, eax
0x1800e579f  test    eax, eax
0x1800e57a1  js      loc_1800E58D4
0x1800e57a7  mov     [rbp+var_48], 0
0x1800e57af  mov     rdi, [rbp+var_40]
0x1800e57b3  mov     rax, [rdi]
0x1800e57b6  mov     rbx, [rax+40h]
0x1800e57ba  xor     ecx, ecx; string
0x1800e57bc  call    cs:__imp_WindowsDeleteString
0x1800e57c2  mov     [rbp+var_48], 0
0x1800e57ca  lea     rdx, [rbp+var_48]
0x1800e57ce  mov     rcx, rdi
0x1800e57d1  mov     rax, rbx
0x1800e57d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e57d9  mov     ebx, eax
0x1800e57db  test    eax, eax
0x1800e57dd  js      loc_1800E587D
0x1800e57e3  xor     edx, edx; length
0x1800e57e5  mov     rcx, [rbp+var_48]; string
0x1800e57e9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e57ef  mov     rdx, rax
0x1800e57f2  mov     rcx, rsi
0x1800e57f5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e57fa  test    al, al
0x1800e57fc  jz      loc_1800E5967
0x1800e5802  mov     rcx, [rbp+var_48]; string
0x1800e5806  call    cs:__imp_WindowsDeleteString
0x1800e580c  mov     [rbp+var_48], 0
0x1800e5814  mov     rcx, [rbp+var_40]
0x1800e5818  test    rcx, rcx
0x1800e581b  jz      short loc_1800E582A
0x1800e581d  mov     rax, [rcx]
0x1800e5820  mov     rax, [rax+10h]
0x1800e5824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5829  nop
0x1800e582a  xor     ebx, ebx
0x1800e582c  call    cs:__imp_RoUninitialize
0x1800e5832  mov     eax, ebx
0x1800e5834  mov     rcx, [rbp+var_10]
0x1800e5838  xor     rcx, rsp; StackCookie
0x1800e583b  call    __security_check_cookie
0x1800e5840  add     rsp, 68h
0x1800e5844  pop     rdi
0x1800e5845  pop     rsi
0x1800e5846  pop     rbx
0x1800e5847  pop     rbp
0x1800e5848  retn
0x1800e5849  lea     rcx, WPP_GLOBAL_Control
0x1800e5850  mov     r10, cs:WPP_GLOBAL_Control
0x1800e5857  cmp     r10, rcx
0x1800e585a  jz      short loc_1800E5832
0x1800e585c  test    byte ptr [r10+1Ch], 1
0x1800e5861  jz      short loc_1800E5832
0x1800e5863  mov     edx, 8Dh
0x1800e5868  mov     r9d, ebx
0x1800e586b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e5872  mov     rcx, [r10+10h]
0x1800e5876  call    WPP_SF_d
0x1800e587b  jmp     short loc_1800E5832
0x1800e587d  lea     rcx, WPP_GLOBAL_Control
0x1800e5884  mov     rax, cs:WPP_GLOBAL_Control
0x1800e588b  cmp     rax, rcx
0x1800e588e  jnz     loc_1800E5940
0x1800e5894  mov     rcx, [rbp+var_48]; string
0x1800e5898  call    cs:__imp_WindowsDeleteString
0x1800e589e  mov     [rbp+var_48], 0
0x1800e58a6  mov     rcx, [rbp+var_40]
0x1800e58aa  test    rcx, rcx
0x1800e58ad  jz      short loc_1800E58BC
0x1800e58af  mov     rax, [rcx]
0x1800e58b2  mov     rax, [rax+10h]
0x1800e58b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e58bb  nop
0x1800e58bc  jmp     loc_1800E582C
0x1800e58c1  xor     r9d, r9d; lpArguments
0x1800e58c4  xor     r8d, r8d; nNumberOfArguments
0x1800e58c7  lea     edx, [r9+1]; dwExceptionFlags
0x1800e58cb  mov     ecx, eax; dwExceptionCode
0x1800e58cd  call    cs:__imp_RaiseException
0x1800e58d3  int     3; Trap to Debugger
0x1800e58d4  lea     rcx, WPP_GLOBAL_Control
0x1800e58db  mov     rax, cs:WPP_GLOBAL_Control
0x1800e58e2  cmp     rax, rcx
0x1800e58e5  jz      short loc_1800E5932
0x1800e58e7  test    byte ptr [rax+1Ch], 1
0x1800e58eb  jz      short loc_1800E5932
0x1800e58ed  mov     edx, 8Eh
0x1800e58f2  mov     r9d, ebx
0x1800e58f5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e58fc  mov     rcx, [rax+10h]
0x1800e5900  call    WPP_SF_d
0x1800e5905  jmp     short loc_1800E5932
0x1800e5907  mov     edx, 90h
0x1800e590c  mov     r9d, ebx
0x1800e590f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e5916  mov     rcx, [rax+10h]
0x1800e591a  call    WPP_SF_d
0x1800e591f  nop
0x1800e5920  mov     rcx, [rbp+var_48]; string
0x1800e5924  call    cs:__imp_WindowsDeleteString
0x1800e592a  mov     [rbp+var_48], 0
0x1800e5932  lea     rcx, [rbp+var_40]
0x1800e5936  call    ??1?$unique_ptr@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,tlx::release_delete>::~unique_ptr<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,tlx::release_delete>(void)
0x1800e593b  jmp     loc_1800E582C
0x1800e5940  test    byte ptr [rax+1Ch], 1
0x1800e5944  jz      loc_1800E5894
0x1800e594a  mov     edx, 8Fh
0x1800e594f  mov     r9d, ebx
0x1800e5952  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e5959  mov     rcx, [rax+10h]
0x1800e595d  call    WPP_SF_d
0x1800e5962  jmp     loc_1800E5894
0x1800e5967  mov     ebx, 8007000Eh
0x1800e596c  lea     rcx, WPP_GLOBAL_Control
0x1800e5973  mov     rax, cs:WPP_GLOBAL_Control
0x1800e597a  cmp     rax, rcx
0x1800e597d  jz      short loc_1800E5920
0x1800e597f  test    byte ptr [rax+1Ch], 1
0x1800e5983  jz      short loc_1800E5920
0x1800e5985  jmp     short loc_1800E5907
```
