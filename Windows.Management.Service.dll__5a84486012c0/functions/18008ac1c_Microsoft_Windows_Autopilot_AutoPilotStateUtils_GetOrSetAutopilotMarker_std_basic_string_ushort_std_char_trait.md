# Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008ac1c`
- end: `0x18008af80`
- name: `?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801ae8e0`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180063dc3`
- `0x180066290`
- `0x180067a34`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x1800814a8`
- `0x180081c44`
- `0x180089f5c`
- `0x180089ff4`
- `0x18008a034`
- `0x18008ac1c`
- `0x18008af88`
- `0x18008c244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acb2`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008adb8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008add4`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008adb8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008add4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008ae7d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008ae7d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008ae46`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008ae46`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18008af06`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18008af06`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18008ac9b`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18008ac9b`
- `DMCmnUtils!UnicodeToMB` at `0x18008aeba`
- `DMCmnUtils!UnicodeToMB` at `0x18008aeba`
- `DMCmnUtils!MBToUnicode` at `0x18008ad4d`
- `DMCmnUtils!MBToUnicode` at `0x18008ad4d`

## string_xrefs

- `0x18008ac5e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008aceb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008ad6b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008aecd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008af14`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  DWORD FirmwareEnvironmentVariableW; // ebx
  signed int LastError; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  char v8; // bl
  HRESULT v9; // edi
  __int64 v10; // rdx
  void *v11; // rdx
  wil::details *v12; // rcx
  bool v13; // zf
  void *v14; // rdx
  wil::details *v15; // rcx
  HRESULT v16; // eax
  int v17; // eax
  const char *v18; // r9
  LPCOLESTR lpsz; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-D8h] BYREF
  DWORD nSize; // [rsp+2Ch] [rbp-D4h] BYREF
  PVOID pValue; // [rsp+30h] [rbp-D0h] BYREF
  PVOID ReturnedState; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+60h] [rbp-A0h] BYREF
  char v27; // [rsp+70h] [rbp-90h]
  GUID iid; // [rsp+78h] [rbp-88h] BYREF
  GUID Buf1; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pBuffer[39]; // [rsp+98h] [rbp-68h] BYREF
  OLECHAR sz[40]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  ReturnedState = 0;
  v2 = ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(&ReturnedState);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v2,
      (int)lpsz);
    goto LABEL_38;
  }
  memset(pBuffer, 0, sizeof(pBuffer));
  FirmwareEnvironmentVariableW = GetFirmwareEnvironmentVariableW(
                                   L"AUTOPILOT_MARKER",
                                   L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}",
                                   pBuffer,
                                   0x27u);
  std::wstring::wstring(v25);
  if ( !FirmwareEnvironmentVariableW )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 203 && LastError != 122 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_12;
      v6 = 514;
      goto LABEL_10;
    }
    goto LABEL_27;
  }
  if ( FirmwareEnvironmentVariableW != 39 )
  {
LABEL_27:
    pguid = 0;
    v16 = CoCreateGuid(&pguid);
    v3 = v16;
    if ( v16 < 0 )
    {
      v7 = (unsigned int)v16;
      v6 = 553;
      goto LABEL_11;
    }
    memset_0(sz, 0, 0x4Eu);
    if ( !StringFromGUID2(&pguid, sz, 39) )
    {
      v3 = -2147418113;
      v6 = 555;
LABEL_10:
      v7 = v3;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
        (const char *)v7,
        (int)lpsz);
LABEL_12:
      std::wstring::_Tidy_deallocate(v25);
      goto LABEL_38;
    }
    nSize = 0;
    pValue = 0;
    v17 = UnicodeToMB(sz, 0xFDE9u, (char **)&pValue, &nSize);
    v3 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
        (const char *)(unsigned int)v17,
        (int)lpsz);
LABEL_33:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pValue);
      goto LABEL_12;
    }
    if ( !SetFirmwareEnvironmentVariableW(L"AUTOPILOT_MARKER", L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}", pValue, nSize) )
    {
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x236,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
             v18);
      goto LABEL_33;
    }
    std::wstring::assign(v25, sz);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pValue);
LABEL_37:
    std::wstring::operator=(a1, v25);
    std::wstring::_Tidy_deallocate(v25);
    v3 = 0;
    goto LABEL_38;
  }
  lpsz = 0;
  v21 = 0;
  *(_QWORD *)&pguid.Data1 = &lpsz;
  *(_QWORD *)pguid.Data4 = 0;
  v8 = 1;
  v27 = 1;
  v9 = MBToUnicode(pBuffer, 0xFDE9u, (unsigned __int16 **)pguid.Data4, &v21);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&pguid);
  if ( v9 >= 0 )
  {
    iid = 0;
    if ( IIDFromString(lpsz, &iid) >= 0 )
    {
      Buf1 = 0;
      v9 = IIDFromString(L"{00000000-0000-0000-0000-000000000000}", &Buf1);
      if ( v9 < 0 )
      {
        v10 = 538;
        goto LABEL_16;
      }
      if ( memcmp_0(&Buf1, &iid, 0x10u) )
      {
        v8 = 0;
        std::wstring::assign(v25, lpsz, v21 - 1);
      }
    }
    v15 = (wil::details *)lpsz;
    lpsz = 0;
    if ( v15 )
      wil::details::FreeProcessHeap(v15, v14);
    if ( !v8 )
      goto LABEL_37;
    goto LABEL_27;
  }
  v10 = 528;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
    (const char *)(unsigned int)v9,
    (int)lpsz);
  v12 = (wil::details *)lpsz;
  v13 = lpsz == 0;
  lpsz = 0;
  if ( !v13 )
    wil::details::FreeProcessHeap(v12, v11);
  std::wstring::_Tidy_deallocate(v25);
  v3 = v9;
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ReturnedState);
  return v3;
}

```

## disassembly

```asm
0x18008ac1c  push    rbp
0x18008ac1e  push    rbx
0x18008ac1f  push    rsi
0x18008ac20  push    rdi
0x18008ac21  lea     rbp, [rsp-28h]
0x18008ac26  sub     rsp, 128h
0x18008ac2d  mov     rax, cs:__security_cookie
0x18008ac34  xor     rax, rsp
0x18008ac37  mov     [rbp+40h+var_30], rax
0x18008ac3b  mov     rsi, rcx
0x18008ac3e  mov     [rsp+140h+ReturnedState], 0
0x18008ac47  lea     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x18008ac4c  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x18008ac51  mov     ebx, eax
0x18008ac53  test    eax, eax
0x18008ac55  jns     short loc_18008AC74
0x18008ac57  mov     rcx, [rbp+48h]; this
0x18008ac5b  mov     r9d, eax; char *
0x18008ac5e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ac65  mov     edx, 1F2h; void *
0x18008ac6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ac6f  jmp     loc_18008AF5C
0x18008ac74  xorps   xmm0, xmm0
0x18008ac77  xor     eax, eax
0x18008ac79  movups  [rbp+40h+pBuffer], xmm0
0x18008ac7d  movups  xmmword ptr [rbp+40h+var_98], xmm0
0x18008ac81  mov     qword ptr [rbp+40h+var_98+0Fh], rax
0x18008ac85  lea     r9d, [rax+27h]; nSize
0x18008ac89  lea     r8, [rbp+40h+pBuffer]; pBuffer
0x18008ac8d  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18008ac94  lea     rcx, Name; "AUTOPILOT_MARKER"
0x18008ac9b  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x18008aca1  mov     ebx, eax
0x18008aca3  lea     rcx, [rsp+140h+var_100]
0x18008aca8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008acad  nop
0x18008acae  test    ebx, ebx
0x18008acb0  jnz     short loc_18008AD07
0x18008acb2  call    cs:__imp_GetLastError
0x18008acb8  mov     ebx, eax
0x18008acba  cmp     eax, 0CBh
0x18008acbf  jz      loc_18008AE39
0x18008acc5  cmp     eax, 7Ah ; 'z'
0x18008acc8  jz      loc_18008AE39
0x18008acce  test    eax, eax
0x18008acd0  jle     short loc_18008ACDB
0x18008acd2  movzx   ebx, ax
0x18008acd5  or      ebx, 80070000h
0x18008acdb  test    ebx, ebx
0x18008acdd  jns     short loc_18008ACF8
0x18008acdf  mov     edx, 202h; void *
0x18008ace4  mov     r9d, ebx; char *
0x18008ace7  mov     rcx, [rbp+48h]; this
0x18008aceb  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008acf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008acf7  nop
0x18008acf8  lea     rcx, [rsp+140h+var_100]
0x18008acfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008ad02  jmp     loc_18008AF5C
0x18008ad07  cmp     ebx, 27h ; '''
0x18008ad0a  jnz     loc_18008AE39
0x18008ad10  mov     [rsp+140h+lpsz], 0; int
0x18008ad19  mov     [rsp+140h+var_118], 0
0x18008ad21  lea     rax, [rsp+140h+lpsz]
0x18008ad26  mov     qword ptr [rsp+140h+pguid.Data1], rax
0x18008ad2b  mov     qword ptr [rsp+140h+pguid.Data4], 0
0x18008ad34  mov     bl, 1
0x18008ad36  mov     [rsp+140h+var_D0], bl
0x18008ad3a  lea     r9, [rsp+140h+var_118]
0x18008ad3f  lea     r8, [rsp+140h+pguid.Data4]
0x18008ad44  mov     edx, 0FDE9h
0x18008ad49  lea     rcx, [rbp+40h+pBuffer]
0x18008ad4d  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x18008ad53  mov     edi, eax
0x18008ad55  lea     rcx, [rsp+140h+pguid]
0x18008ad5a  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18008ad5f  test    edi, edi
0x18008ad61  jns     short loc_18008ADA6
0x18008ad63  mov     edx, 210h; void *
0x18008ad68  mov     r9d, edi; char *
0x18008ad6b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ad72  mov     rcx, [rbp+48h]; this
0x18008ad76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ad7b  nop
0x18008ad7c  mov     rcx, [rsp+140h+lpsz]; this
0x18008ad81  test    rcx, rcx
0x18008ad84  mov     [rsp+140h+lpsz], 0
0x18008ad8d  jz      short loc_18008AD95
0x18008ad8f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18008ad94  nop
0x18008ad95  lea     rcx, [rsp+140h+var_100]
0x18008ad9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008ad9f  mov     ebx, edi
0x18008ada1  jmp     loc_18008AF5C
0x18008ada6  xorps   xmm0, xmm0
0x18008ada9  movups  xmmword ptr [rsp+140h+iid.Data1], xmm0
0x18008adae  lea     rdx, [rsp+140h+iid]; lpiid
0x18008adb3  mov     rcx, [rsp+140h+lpsz]; lpsz
0x18008adb8  call    cs:__imp_IIDFromString
0x18008adbe  test    eax, eax
0x18008adc0  js      short loc_18008AE19
0x18008adc2  xorps   xmm0, xmm0
0x18008adc5  movups  xmmword ptr [rbp+40h+Buf1.Data1], xmm0
0x18008adc9  lea     rdx, [rbp+40h+Buf1]; lpiid
0x18008adcd  lea     rcx, sz; "{00000000-0000-0000-0000-000000000000}"
0x18008add4  call    cs:__imp_IIDFromString
0x18008adda  mov     edi, eax
0x18008addc  test    eax, eax
0x18008adde  jns     short loc_18008ADE7
0x18008ade0  mov     edx, 21Ah
0x18008ade5  jmp     short loc_18008AD68
0x18008ade7  mov     r8d, 10h; Size
0x18008aded  lea     rdx, [rsp+140h+iid]; Buf2
0x18008adf2  lea     rcx, [rbp+40h+Buf1]; Buf1
0x18008adf6  call    memcmp_0
0x18008adfb  test    eax, eax
0x18008adfd  jz      short loc_18008AE19
0x18008adff  xor     bl, bl
0x18008ae01  mov     r8d, [rsp+140h+var_118]
0x18008ae06  dec     r8d
0x18008ae09  mov     rdx, [rsp+140h+lpsz]
0x18008ae0e  lea     rcx, [rsp+140h+var_100]
0x18008ae13  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18008ae18  nop
0x18008ae19  mov     rcx, [rsp+140h+lpsz]; this
0x18008ae1e  mov     [rsp+140h+lpsz], 0; int
0x18008ae27  test    rcx, rcx
0x18008ae2a  jz      short loc_18008AE31
0x18008ae2c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18008ae31  test    bl, bl
0x18008ae33  jz      loc_18008AF42
0x18008ae39  xorps   xmm0, xmm0
0x18008ae3c  movups  xmmword ptr [rsp+140h+pguid.Data1], xmm0
0x18008ae41  lea     rcx, [rsp+140h+pguid]; pguid
0x18008ae46  call    cs:__imp_CoCreateGuid
0x18008ae4c  mov     ebx, eax
0x18008ae4e  test    eax, eax
0x18008ae50  jns     short loc_18008AE5F
0x18008ae52  mov     r9d, eax
0x18008ae55  mov     edx, 229h
0x18008ae5a  jmp     loc_18008ACE7
0x18008ae5f  xor     edx, edx; Val
0x18008ae61  lea     r8d, [rdx+4Eh]; Size
0x18008ae65  lea     rcx, [rbp+40h+sz]; void *
0x18008ae69  call    memset_0
0x18008ae6e  mov     r8d, 27h ; '''; cchMax
0x18008ae74  lea     rdx, [rbp+40h+sz]; lpsz
0x18008ae78  lea     rcx, [rsp+140h+pguid]; rguid
0x18008ae7d  call    cs:__imp_StringFromGUID2
0x18008ae83  test    eax, eax
0x18008ae85  jnz     short loc_18008AE96
0x18008ae87  mov     ebx, 8000FFFFh
0x18008ae8c  mov     edx, 22Bh
0x18008ae91  jmp     loc_18008ACE4
0x18008ae96  mov     [rsp+140h+nSize], 0
0x18008ae9e  mov     [rsp+140h+pValue], 0
0x18008aea7  lea     r9, [rsp+140h+nSize]
0x18008aeac  lea     r8, [rsp+140h+pValue]
0x18008aeb1  mov     edx, 0FDE9h
0x18008aeb6  lea     rcx, [rbp+40h+sz]
0x18008aeba  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18008aec0  mov     ebx, eax
0x18008aec2  test    eax, eax
0x18008aec4  jns     short loc_18008AEEE
0x18008aec6  mov     rcx, [rbp+48h]; this
0x18008aeca  mov     r9d, eax; char *
0x18008aecd  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008aed4  mov     edx, 22Fh; void *
0x18008aed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008aede  nop
0x18008aedf  lea     rcx, [rsp+140h+pValue]
0x18008aee4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008aee9  jmp     loc_18008ACF8
0x18008aeee  mov     r9d, [rsp+140h+nSize]; nSize
0x18008aef3  mov     r8, [rsp+140h+pValue]; pValue
0x18008aef8  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18008aeff  lea     rcx, Name; "AUTOPILOT_MARKER"
0x18008af06  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x18008af0c  test    eax, eax
0x18008af0e  jnz     short loc_18008AF29
0x18008af10  mov     rcx, [rbp+48h]; this
0x18008af14  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008af1b  mov     edx, 236h; void *
0x18008af20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008af25  mov     ebx, eax
0x18008af27  jmp     short loc_18008AEDF
0x18008af29  lea     rdx, [rbp+40h+sz]
0x18008af2d  lea     rcx, [rsp+140h+var_100]
0x18008af32  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008af37  nop
0x18008af38  lea     rcx, [rsp+140h+pValue]
0x18008af3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008af42  lea     rdx, [rsp+140h+var_100]
0x18008af47  mov     rcx, rsi
0x18008af4a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008af4f  nop
0x18008af50  lea     rcx, [rsp+140h+var_100]
0x18008af55  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008af5a  xor     ebx, ebx
0x18008af5c  lea     rcx, [rsp+140h+ReturnedState]
0x18008af61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008af66  mov     eax, ebx
0x18008af68  mov     rcx, [rbp+40h+var_30]
0x18008af6c  xor     rcx, rsp; StackCookie
0x18008af6f  call    __security_check_cookie
0x18008af74  add     rsp, 128h
0x18008af7b  pop     rdi
0x18008af7c  pop     rsi
0x18008af7d  pop     rbx
0x18008af7e  pop     rbp
0x18008af7f  retn
```
