# ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory(void)

- ea: `0x1801546cc`
- end: `0x180154840`
- name: `?SetAttestationDllDirectory@MaaRequestor@Core@Autopilot@ModernDeployment@@KAJXZ`
- size: `372`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180152ccc`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x180067f70`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800839bc`
- `0x18008982c`
- `0x18008dc94`
- `0x1801546cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154796`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015473d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015473d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015478c`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015478c`

## string_xrefs

- `0x180154707`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x1801547f4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015471f`: `MaaRequestor::SetAttestationDllDirectory `
- `0x1801547ab`: `SetDllDirectoryW`
- `0x180154751`: `GetSystemDirectoryW`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory(void)
{
  const char *v0; // r9
  __int64 result; // rax
  signed int v2; // ebx
  const wchar_t *v3; // rdx
  signed int LastError; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-258h]
  _BYTE v8[40]; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)0x80004001LL,
        v7);
      return 2147500033LL;
    }
    std::wstring::wstring(v8, L"MaaRequestor::SetAttestationDllDirectory ");
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
    {
      v2 = StringCchCatW(Buffer, 0x104u, L"\\HealthAttestationClient");
      if ( v2 >= 0 )
      {
        if ( SetDllDirectoryW(Buffer) )
          goto LABEL_18;
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        std::wstring::append(v8, L"SetDllDirectoryW");
        if ( v2 >= 0 )
        {
LABEL_18:
          std::wstring::_Tidy_deallocate(v8);
          return 0;
        }
        goto LABEL_13;
      }
      v3 = L"StringCchCatW";
    }
    else
    {
      v2 = -2147024809;
      v3 = L"GetSystemDirectoryW";
    }
    std::wstring::append(v8, v3);
LABEL_13:
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
      McTemplateU0dz_EventWriteTransfer(v6, AutopilotMaaAttestationPhaseFailure, (unsigned int)v2, v5);
    }
    if ( v2 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)(unsigned int)v2,
        v7);
    std::wstring::_Tidy_deallocate(v8);
    result = (unsigned int)v2;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF1,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                           v0);
  }
  return result;
}

```

## disassembly

```asm
0x1801546cc  push    rbx
0x1801546ce  sub     rsp, 270h
0x1801546d5  mov     rax, cs:__security_cookie
0x1801546dc  xor     rax, rsp
0x1801546df  mov     [rsp+278h+var_18], rax
0x1801546e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801546ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801546f3  test    al, al
0x1801546f5  jnz     short loc_18015471F
0x1801546f7  mov     rcx, [rsp+278h]; this
0x1801546ff  mov     ebx, 80004001h
0x180154704  mov     r9d, ebx; char *
0x180154707  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015470e  mov     edx, 0C7h; void *
0x180154713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154718  mov     eax, ebx
0x18015471a  jmp     loc_180154826
0x18015471f  lea     rdx, aMaarequestorSe; "MaaRequestor::SetAttestationDllDirector"...
0x180154726  lea     rcx, [rsp+278h+var_250]
0x18015472b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180154730  nop
0x180154731  mov     ebx, 104h
0x180154736  mov     edx, ebx; uSize
0x180154738  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18015473d  call    cs:__imp_GetSystemDirectoryW
0x180154743  dec     eax
0x180154745  cmp     eax, 102h
0x18015474a  jbe     short loc_18015475A
0x18015474c  mov     ebx, 80070057h
0x180154751  lea     rdx, aGetsystemdirec; "GetSystemDirectoryW"
0x180154758  jmp     short loc_18015477B
0x18015475a  lea     r8, aHealthattestat; "\\HealthAttestationClient"
0x180154761  mov     rdx, rbx; unsigned __int64
0x180154764  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x180154769  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18015476e  mov     ebx, eax
0x180154770  test    eax, eax
0x180154772  jns     short loc_180154787
0x180154774  lea     rdx, aStringcchcatw; "StringCchCatW"
0x18015477b  lea     rcx, [rsp+278h+var_250]
0x180154780  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180154785  jmp     short loc_1801547C0
0x180154787  lea     rcx, [rsp+278h+Buffer]; lpPathName
0x18015478c  call    cs:__imp_SetDllDirectoryW
0x180154792  test    eax, eax
0x180154794  jnz     short loc_180154814
0x180154796  call    cs:__imp_GetLastError
0x18015479c  mov     ebx, eax
0x18015479e  test    eax, eax
0x1801547a0  jle     short loc_1801547AB
0x1801547a2  movzx   ebx, ax
0x1801547a5  or      ebx, 80070000h
0x1801547ab  lea     rdx, aSetdlldirector; "SetDllDirectoryW"
0x1801547b2  lea     rcx, [rsp+278h+var_250]
0x1801547b7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801547bc  test    ebx, ebx
0x1801547be  jns     short loc_180154814
0x1801547c0  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801547c7  jz      short loc_1801547E5
0x1801547c9  lea     rcx, [rsp+278h+var_250]
0x1801547ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801547d3  mov     r9, rax
0x1801547d6  mov     r8d, ebx
0x1801547d9  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x1801547e0  call    McTemplateU0dz_EventWriteTransfer
0x1801547e5  test    ebx, ebx
0x1801547e7  jns     short loc_180154806
0x1801547e9  mov     rcx, [rsp+278h]; this
0x1801547f1  mov     r9d, ebx; char *
0x1801547f4  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801547fb  mov     edx, 0ECh; void *
0x180154800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154805  nop
0x180154806  lea     rcx, [rsp+278h+var_250]
0x18015480b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180154810  mov     eax, ebx
0x180154812  jmp     short loc_180154826
0x180154814  lea     rcx, [rsp+278h+var_250]
0x180154819  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015481e  xor     eax, eax
0x180154820  jmp     short loc_180154826
0x180154822  mov     eax, [rsp+278h+var_258]
0x180154826  mov     rcx, [rsp+278h+var_18]
0x18015482e  xor     rcx, rsp; StackCookie
0x180154831  call    __security_check_cookie
0x180154836  add     rsp, 270h
0x18015483d  pop     rbx
0x18015483e  retn
```
