# ChatServiceTransaction::_GenerateClientInfoValue(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800a25d0`
- end: `0x1800a28b5`
- name: `?_GenerateClientInfoValue@ChatServiceTransaction@@CAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a3360`

## callees

- `0x180005c50`
- `0x180008870`
- `0x1800242c4`
- `0x18003214c`
- `0x1800a23a8`
- `0x1800a23d4`
- `0x1800a25d0`
- `0x1800c50ec`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800a276b`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800a276b`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800a26f7`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800a26f7`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x1800a2797`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x1800a2797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a27a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a27a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2748`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2748`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a265f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a265f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a2617`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a2617`

## pseudocode

```c
__int64 ChatServiceTransaction::_GenerateClientInfoValue()
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  const wchar_t *v2; // rbx
  signed int v3; // eax
  HRESULT v4; // eax
  int v5; // edi
  GEOID UserGeoID; // eax
  signed int v7; // eax
  int v8; // eax
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v12; // [rsp+68h] [rbp-98h] BYREF
  __int64 v13; // [rsp+6Ah] [rbp-96h]
  int v14; // [rsp+72h] [rbp-8Eh]
  __int16 v15; // [rsp+76h] [rbp-8Ah]
  _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp-88h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR GeoData[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR LocaleName[88]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
    Log_HREvent_78(v1);
    return v1;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  switch ( SystemInfo.wProcessorArchitecture )
  {
    case 9u:
      v2 = L"x64";
      break;
    case 5u:
      v2 = L"arm";
      break;
    case 6u:
      v2 = L"ia64";
      break;
    default:
      if ( SystemInfo.wProcessorArchitecture )
      {
        if ( SystemInfo.wProcessorArchitecture == 12 )
        {
          v2 = L"arm64";
        }
        else
        {
          v2 = L"unknown";
          Log_AssertionEvent_54();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
      else
      {
        v2 = L"x86";
      }
      break;
  }
  memset_0(LocaleName, 0, 0xAAu);
  if ( GetUserDefaultLocaleName(LocaleName, 85) <= 0 )
  {
    v3 = GetLastError();
    v1 = v3;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_4;
  }
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_MessagingOMPhone, 0, 0x17u, &GUID_bbc5f203_d1d3_471c_bed6_e5db4a3502a5, &ppv);
  if ( v4 == -2147221164 )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    if ( v4 >= 0 )
      v5 = 2;
  }
  UserGeoID = GetUserGeoID(0x10u);
  *(_OWORD *)GeoData = 0;
  if ( UserGeoID == -1 || GetGeoInfoW(UserGeoID, 4u, GeoData, 8, 0) > 0 )
  {
    v13 = 0;
    v15 = 0;
    v14 = 0;
    v11[0] = &v12;
    v11[1] = &v12;
    v12 = 0;
    v8 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
           v11,
           L"os=windows; osVer=%lu; proc=%s; lcid=%s; deviceType=%lu; country=%s; clientName=WindowsMessaging; clientVer=%lu.%lu.%lu",
           VersionInformation.dwMajorVersion,
           v2,
           LocaleName,
           v5,
           GeoData,
           VersionInformation.dwMajorVersion,
           VersionInformation.dwMinorVersion,
           VersionInformation.dwBuildNumber);
    v1 = v8;
    if ( v8 >= 0 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        &qword_1800FEAD0,
        v11);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
      v1 = 0;
    }
    else
    {
      Log_HREvent_78(v8);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
    }
  }
  else
  {
    v7 = GetLastError();
    v1 = v7;
    if ( v7 > 0 )
      v1 = (unsigned __int16)v7 | 0x80070000;
    Log_HREvent_78(v1);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v1;
}

```

## disassembly

```asm
0x1800a25d0  mov     [rsp-8+arg_0], rbx
0x1800a25d5  mov     [rsp-8+arg_8], rdi
0x1800a25da  push    rbp
0x1800a25db  lea     rbp, [rsp-1A0h]
0x1800a25e3  sub     rsp, 2A0h
0x1800a25ea  mov     rax, cs:__security_cookie
0x1800a25f1  xor     rax, rsp
0x1800a25f4  mov     [rbp+1A0h+var_10], rax
0x1800a25fb  xor     edx, edx; Val
0x1800a25fd  lea     rcx, [rbp+1A0h+VersionInformation.dwMajorVersion]; void *
0x1800a2601  mov     r8d, 110h; Size
0x1800a2607  call    memset_0
0x1800a260c  lea     rcx, [rbp+1A0h+VersionInformation]; lpVersionInformation
0x1800a2610  mov     [rbp+1A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x1800a2617  call    cs:__imp_GetVersionExW
0x1800a261d  test    eax, eax
0x1800a261f  jnz     short loc_1800A264A
0x1800a2621  call    cs:__imp_GetLastError
0x1800a2627  mov     ebx, eax
0x1800a2629  test    eax, eax
0x1800a262b  jle     short loc_1800A2636
0x1800a262d  movzx   ebx, ax
0x1800a2630  or      ebx, 80070000h
0x1800a2636  mov     r9d, 0E8h
0x1800a263c  xor     edx, edx
0x1800a263e  mov     ecx, ebx; int
0x1800a2640  call    Log_HREvent_78
0x1800a2645  jmp     loc_1800A288F
0x1800a264a  xorps   xmm0, xmm0
0x1800a264d  lea     rcx, [rsp+2A0h+SystemInfo]; lpSystemInfo
0x1800a2652  movups  xmmword ptr [rsp+2A0h+SystemInfo], xmm0
0x1800a2657  movups  xmmword ptr [rbp+1A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800a265b  movups  xmmword ptr [rbp+1A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800a265f  call    cs:__imp_GetSystemInfo
0x1800a2665  movzx   ecx, word ptr [rsp+2A0h+SystemInfo]
0x1800a266a  mov     eax, 9
0x1800a266f  cmp     ax, cx
0x1800a2672  jnz     short loc_1800A267D
0x1800a2674  lea     rbx, aX64; "x64"
0x1800a267b  jmp     short loc_1800A26D7
0x1800a267d  mov     eax, 5
0x1800a2682  cmp     ax, cx
0x1800a2685  jnz     short loc_1800A2690
0x1800a2687  lea     rbx, aArm; "arm"
0x1800a268e  jmp     short loc_1800A26D7
0x1800a2690  mov     eax, 6
0x1800a2695  cmp     ax, cx
0x1800a2698  jnz     short loc_1800A26A3
0x1800a269a  lea     rbx, aIa64; "ia64"
0x1800a26a1  jmp     short loc_1800A26D7
0x1800a26a3  xor     eax, eax
0x1800a26a5  cmp     ax, cx
0x1800a26a8  jnz     short loc_1800A26B3
0x1800a26aa  lea     rbx, aX86; "x86"
0x1800a26b1  jmp     short loc_1800A26D7
0x1800a26b3  mov     eax, 0Ch
0x1800a26b8  cmp     ax, cx
0x1800a26bb  jnz     short loc_1800A26C6
0x1800a26bd  lea     rbx, aArm64; "arm64"
0x1800a26c4  jmp     short loc_1800A26D7
0x1800a26c6  lea     rbx, aUnknown; "unknown"
0x1800a26cd  call    Log_AssertionEvent_54
0x1800a26d2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a26d7  xor     edx, edx; Val
0x1800a26d9  lea     rcx, [rbp+1A0h+LocaleName]; void *
0x1800a26e0  mov     r8d, 0AAh; Size
0x1800a26e6  call    memset_0
0x1800a26eb  mov     edx, 55h ; 'U'; cchLocaleName
0x1800a26f0  lea     rcx, [rbp+1A0h+LocaleName]; lpLocaleName
0x1800a26f7  call    cs:__imp_GetUserDefaultLocaleName
0x1800a26fd  test    eax, eax
0x1800a26ff  jg      short loc_1800A2721
0x1800a2701  call    cs:__imp_GetLastError
0x1800a2707  mov     ebx, eax
0x1800a2709  test    eax, eax
0x1800a270b  jle     short loc_1800A2716
0x1800a270d  movzx   ebx, ax
0x1800a2710  or      ebx, 80070000h
0x1800a2716  mov     r9d, 109h
0x1800a271c  jmp     loc_1800A263C
0x1800a2721  xor     edx, edx; pUnkOuter
0x1800a2723  mov     [rsp+2A0h+var_250], 0
0x1800a272c  lea     rax, [rsp+2A0h+var_250]
0x1800a2731  lea     r9, _GUID_bbc5f203_d1d3_471c_bed6_e5db4a3502a5; riid
0x1800a2738  mov     [rsp+2A0h+ppv], rax; ppv
0x1800a273d  lea     rcx, ?CLSID_MessagingOMPhone@@3U_GUID@@B; rclsid
0x1800a2744  lea     r8d, [rdx+17h]; dwClsContext
0x1800a2748  call    cs:__imp_CoCreateInstance
0x1800a274e  cmp     eax, 80040154h
0x1800a2753  jnz     short loc_1800A275C
0x1800a2755  mov     edi, 1
0x1800a275a  jmp     short loc_1800A2766
0x1800a275c  xor     edi, edi
0x1800a275e  test    eax, eax
0x1800a2760  lea     ecx, [rdi+2]
0x1800a2763  cmovns  edi, ecx
0x1800a2766  mov     ecx, 10h; GeoClass
0x1800a276b  call    cs:__imp_GetUserGeoID
0x1800a2771  xorps   xmm0, xmm0
0x1800a2774  movups  xmmword ptr [rbp+1A0h+GeoData], xmm0
0x1800a277b  cmp     eax, 0FFFFFFFFh
0x1800a277e  jz      short loc_1800A27CA
0x1800a2780  xor     ecx, ecx
0x1800a2782  lea     r8, [rbp+1A0h+GeoData]; lpGeoData
0x1800a2789  mov     word ptr [rsp+2A0h+ppv], cx; LangId
0x1800a278e  lea     r9d, [rcx+8]; cchData
0x1800a2792  lea     edx, [rcx+4]; GeoType
0x1800a2795  mov     ecx, eax; Location
0x1800a2797  call    cs:__imp_GetGeoInfoW
0x1800a279d  test    eax, eax
0x1800a279f  jg      short loc_1800A27CA
0x1800a27a1  call    cs:__imp_GetLastError
0x1800a27a7  mov     ebx, eax
0x1800a27a9  test    eax, eax
0x1800a27ab  jle     short loc_1800A27B6
0x1800a27ad  movzx   ebx, ax
0x1800a27b0  or      ebx, 80070000h
0x1800a27b6  xor     edx, edx
0x1800a27b8  mov     r9d, 11Ch
0x1800a27be  mov     ecx, ebx; int
0x1800a27c0  call    Log_HREvent_78
0x1800a27c5  jmp     loc_1800A2885
0x1800a27ca  mov     r8d, [rbp+1A0h+VersionInformation.dwMajorVersion]
0x1800a27ce  lea     rdx, aOsWindowsOsver; "os=windows; osVer=%lu; proc=%s; lcid=%s"...
0x1800a27d5  xor     eax, eax
0x1800a27d7  mov     [rsp+2A0h+var_236], 0
0x1800a27e0  mov     [rsp+2A0h+var_22A], ax
0x1800a27e5  lea     rcx, [rsp+2A0h+var_248]
0x1800a27ea  lea     rax, [rsp+2A0h+var_238]
0x1800a27ef  mov     [rsp+2A0h+var_22E], 0
0x1800a27f7  mov     [rsp+2A0h+var_248], rax
0x1800a27fc  mov     r9, rbx
0x1800a27ff  lea     rax, [rsp+2A0h+var_238]
0x1800a2804  mov     [rsp+2A0h+var_240], rax
0x1800a2809  xor     eax, eax
0x1800a280b  mov     [rsp+2A0h+var_238], ax
0x1800a2810  mov     eax, [rbp+1A0h+VersionInformation.dwBuildNumber]
0x1800a2813  mov     [rsp+2A0h+var_258], eax
0x1800a2817  mov     eax, [rbp+1A0h+VersionInformation.dwMinorVersion]
0x1800a281a  mov     [rsp+2A0h+var_260], eax
0x1800a281e  lea     rax, [rbp+1A0h+GeoData]
0x1800a2825  mov     [rsp+2A0h+var_268], r8d
0x1800a282a  mov     [rsp+2A0h+var_270], rax
0x1800a282f  lea     rax, [rbp+1A0h+LocaleName]
0x1800a2836  mov     [rsp+2A0h+var_278], edi
0x1800a283a  mov     [rsp+2A0h+ppv], rax
0x1800a283f  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800a2844  mov     ebx, eax
0x1800a2846  test    eax, eax
0x1800a2848  jns     short loc_1800A2868
0x1800a284a  mov     edx, 1
0x1800a284f  mov     r9d, 12Ch
0x1800a2855  mov     ecx, eax; int
0x1800a2857  call    Log_HREvent_78
0x1800a285c  lea     rcx, [rsp+2A0h+var_248]
0x1800a2861  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a2866  jmp     short loc_1800A2885
0x1800a2868  lea     rdx, [rsp+2A0h+var_248]
0x1800a286d  lea     rcx, qword_1800FEAD0
0x1800a2874  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800a2879  lea     rcx, [rsp+2A0h+var_248]
0x1800a287e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a2883  xor     ebx, ebx
0x1800a2885  lea     rcx, [rsp+2A0h+var_250]
0x1800a288a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a288f  mov     eax, ebx
0x1800a2891  mov     rcx, [rbp+1A0h+var_10]
0x1800a2898  xor     rcx, rsp; StackCookie
0x1800a289b  call    __security_check_cookie
0x1800a28a0  lea     r11, [rsp+2A0h+var_s0]
0x1800a28a8  mov     rbx, [r11+10h]
0x1800a28ac  mov     rdi, [r11+18h]
0x1800a28b0  mov     rsp, r11
0x1800a28b3  pop     rbp
0x1800a28b4  retn
```
