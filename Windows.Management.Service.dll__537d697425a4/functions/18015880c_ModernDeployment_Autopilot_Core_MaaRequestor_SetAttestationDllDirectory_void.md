# ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory(void)

- ea: `0x18015880c`
- end: `0x180158996`
- name: `?SetAttestationDllDirectory@MaaRequestor@Core@Autopilot@ModernDeployment@@KAJXZ`
- size: `394`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180156de0`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180068390`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180084574`
- `0x18008a67c`
- `0x18008ed78`
- `0x18015880c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801588e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801588e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015887d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015887d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801588d2`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801588d2`

## string_xrefs

- `0x180158847`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015894a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180158897`: `GetSystemDirectoryW`
- `0x18015885f`: `MaaRequestor::SetAttestationDllDirectory `
- `0x180158901`: `SetDllDirectoryW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18015880c  push    rbx
0x18015880e  sub     rsp, 270h
0x180158815  mov     rax, cs:__security_cookie
0x18015881c  xor     rax, rsp
0x18015881f  mov     [rsp+278h+var_18], rax
0x180158827  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18015882e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180158833  test    al, al
0x180158835  jnz     short loc_18015885F
0x180158837  mov     rcx, [rsp+278h]; this
0x18015883f  mov     ebx, 80004001h
0x180158844  mov     r9d, ebx; char *
0x180158847  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015884e  mov     edx, 0C7h; void *
0x180158853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158858  mov     eax, ebx
0x18015885a  jmp     loc_18015897C
0x18015885f  lea     rdx, aMaarequestorSe; "MaaRequestor::SetAttestationDllDirector"...
0x180158866  lea     rcx, [rsp+278h+var_250]
0x18015886b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180158870  nop
0x180158871  mov     ebx, 104h
0x180158876  mov     edx, ebx; uSize
0x180158878  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18015887d  call    cs:__imp_GetSystemDirectoryW
0x180158884  nop     dword ptr [rax+rax+00h]
0x180158889  dec     eax
0x18015888b  cmp     eax, 102h
0x180158890  jbe     short loc_1801588A0
0x180158892  mov     ebx, 80070057h
0x180158897  lea     rdx, aGetsystemdirec; "GetSystemDirectoryW"
0x18015889e  jmp     short loc_1801588C1
0x1801588a0  lea     r8, aHealthattestat; "\\HealthAttestationClient"
0x1801588a7  mov     rdx, rbx; unsigned __int64
0x1801588aa  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x1801588af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801588b4  mov     ebx, eax
0x1801588b6  test    eax, eax
0x1801588b8  jns     short loc_1801588CD
0x1801588ba  lea     rdx, aStringcchcatw; "StringCchCatW"
0x1801588c1  lea     rcx, [rsp+278h+var_250]
0x1801588c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801588cb  jmp     short loc_180158916
0x1801588cd  lea     rcx, [rsp+278h+Buffer]; lpPathName
0x1801588d2  call    cs:__imp_SetDllDirectoryW
0x1801588d9  nop     dword ptr [rax+rax+00h]
0x1801588de  test    eax, eax
0x1801588e0  jnz     loc_18015896A
0x1801588e6  call    cs:__imp_GetLastError
0x1801588ed  nop     dword ptr [rax+rax+00h]
0x1801588f2  mov     ebx, eax
0x1801588f4  test    eax, eax
0x1801588f6  jle     short loc_180158901
0x1801588f8  movzx   ebx, ax
0x1801588fb  or      ebx, 80070000h
0x180158901  lea     rdx, aSetdlldirector; "SetDllDirectoryW"
0x180158908  lea     rcx, [rsp+278h+var_250]
0x18015890d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180158912  test    ebx, ebx
0x180158914  jns     short loc_18015896A
0x180158916  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18015891d  jz      short loc_18015893B
0x18015891f  lea     rcx, [rsp+278h+var_250]
0x180158924  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180158929  mov     r9, rax
0x18015892c  mov     r8d, ebx
0x18015892f  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180158936  call    McTemplateU0dz_EventWriteTransfer
0x18015893b  test    ebx, ebx
0x18015893d  jns     short loc_18015895C
0x18015893f  mov     rcx, [rsp+278h]; this
0x180158947  mov     r9d, ebx; char *
0x18015894a  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180158951  mov     edx, 0ECh; void *
0x180158956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015895b  nop
0x18015895c  lea     rcx, [rsp+278h+var_250]
0x180158961  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180158966  mov     eax, ebx
0x180158968  jmp     short loc_18015897C
0x18015896a  lea     rcx, [rsp+278h+var_250]
0x18015896f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180158974  xor     eax, eax
0x180158976  jmp     short loc_18015897C
0x180158978  mov     eax, [rsp+278h+var_258]
0x18015897c  mov     rcx, [rsp+278h+var_18]
0x180158984  xor     rcx, rsp; StackCookie
0x180158987  call    __security_check_cookie
0x18015898c  add     rsp, 270h
0x180158993  pop     rbx
0x180158994  retn
```
