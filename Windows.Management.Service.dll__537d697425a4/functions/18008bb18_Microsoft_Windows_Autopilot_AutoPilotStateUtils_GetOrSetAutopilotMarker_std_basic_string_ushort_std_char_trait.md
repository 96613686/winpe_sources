# Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008bb18`
- end: `0x18008beb6`
- name: `?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801b4164`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180063fa3`
- `0x180066580`
- `0x180067e34`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180081f38`
- `0x180082700`
- `0x18008ae10`
- `0x18008aea8`
- `0x18008aef0`
- `0x18008bb18`
- `0x18008bebc`
- `0x18008d290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbb4`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008bcc6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008bce8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008bcc6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008bce8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008bda0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008bda0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008bd63`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008bd63`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18008be35`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18008be35`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18008bb97`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18008bb97`
- `DMCmnUtils!UnicodeToMB` at `0x18008bde3`
- `DMCmnUtils!UnicodeToMB` at `0x18008bde3`
- `DMCmnUtils!MBToUnicode` at `0x18008bc55`
- `DMCmnUtils!MBToUnicode` at `0x18008bc55`

## string_xrefs

- `0x18008bb5a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bbf3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bc79`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bdfc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008be49`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18008bb18  push    rbp
0x18008bb1a  push    rbx
0x18008bb1b  push    rsi
0x18008bb1c  push    rdi
0x18008bb1d  lea     rbp, [rsp-28h]
0x18008bb22  sub     rsp, 128h
0x18008bb29  mov     rax, cs:__security_cookie
0x18008bb30  xor     rax, rsp
0x18008bb33  mov     [rbp+40h+var_30], rax
0x18008bb37  mov     rsi, rcx
0x18008bb3a  mov     [rsp+140h+ReturnedState], 0
0x18008bb43  lea     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x18008bb48  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x18008bb4d  mov     ebx, eax
0x18008bb4f  test    eax, eax
0x18008bb51  jns     short loc_18008BB70
0x18008bb53  mov     rcx, [rbp+48h]; this
0x18008bb57  mov     r9d, eax; char *
0x18008bb5a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bb61  mov     edx, 1F2h; void *
0x18008bb66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bb6b  jmp     loc_18008BE91
0x18008bb70  xorps   xmm0, xmm0
0x18008bb73  xor     eax, eax
0x18008bb75  movups  [rbp+40h+pBuffer], xmm0
0x18008bb79  movups  xmmword ptr [rbp+40h+var_98], xmm0
0x18008bb7d  mov     qword ptr [rbp+40h+var_98+0Fh], rax
0x18008bb81  lea     r9d, [rax+27h]; nSize
0x18008bb85  lea     r8, [rbp+40h+pBuffer]; pBuffer
0x18008bb89  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18008bb90  lea     rcx, Name; "AUTOPILOT_MARKER"
0x18008bb97  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x18008bb9e  nop     dword ptr [rax+rax+00h]
0x18008bba3  mov     ebx, eax
0x18008bba5  lea     rcx, [rsp+140h+var_100]
0x18008bbaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008bbaf  nop
0x18008bbb0  test    ebx, ebx
0x18008bbb2  jnz     short loc_18008BC0F
0x18008bbb4  call    cs:__imp_GetLastError
0x18008bbbb  nop     dword ptr [rax+rax+00h]
0x18008bbc0  mov     ebx, eax
0x18008bbc2  cmp     eax, 0CBh
0x18008bbc7  jz      loc_18008BD56
0x18008bbcd  cmp     eax, 7Ah ; 'z'
0x18008bbd0  jz      loc_18008BD56
0x18008bbd6  test    eax, eax
0x18008bbd8  jle     short loc_18008BBE3
0x18008bbda  movzx   ebx, ax
0x18008bbdd  or      ebx, 80070000h
0x18008bbe3  test    ebx, ebx
0x18008bbe5  jns     short loc_18008BC00
0x18008bbe7  mov     edx, 202h; void *
0x18008bbec  mov     r9d, ebx; char *
0x18008bbef  mov     rcx, [rbp+48h]; this
0x18008bbf3  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bbfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bbff  nop
0x18008bc00  lea     rcx, [rsp+140h+var_100]
0x18008bc05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008bc0a  jmp     loc_18008BE91
0x18008bc0f  cmp     ebx, 27h ; '''
0x18008bc12  jnz     loc_18008BD56
0x18008bc18  mov     [rsp+140h+lpsz], 0; int
0x18008bc21  mov     [rsp+140h+var_118], 0
0x18008bc29  lea     rax, [rsp+140h+lpsz]
0x18008bc2e  mov     qword ptr [rsp+140h+pguid.Data1], rax
0x18008bc33  mov     qword ptr [rsp+140h+pguid.Data4], 0
0x18008bc3c  mov     bl, 1
0x18008bc3e  mov     [rsp+140h+var_D0], bl
0x18008bc42  lea     r9, [rsp+140h+var_118]
0x18008bc47  lea     r8, [rsp+140h+pguid.Data4]
0x18008bc4c  mov     edx, 0FDE9h
0x18008bc51  lea     rcx, [rbp+40h+pBuffer]
0x18008bc55  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x18008bc5c  nop     dword ptr [rax+rax+00h]
0x18008bc61  mov     edi, eax
0x18008bc63  lea     rcx, [rsp+140h+pguid]
0x18008bc68  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18008bc6d  test    edi, edi
0x18008bc6f  jns     short loc_18008BCB4
0x18008bc71  mov     edx, 210h; void *
0x18008bc76  mov     r9d, edi; char *
0x18008bc79  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bc80  mov     rcx, [rbp+48h]; this
0x18008bc84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bc89  nop
0x18008bc8a  mov     rcx, [rsp+140h+lpsz]; this
0x18008bc8f  test    rcx, rcx
0x18008bc92  mov     [rsp+140h+lpsz], 0
0x18008bc9b  jz      short loc_18008BCA3
0x18008bc9d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18008bca2  nop
0x18008bca3  lea     rcx, [rsp+140h+var_100]
0x18008bca8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008bcad  mov     ebx, edi
0x18008bcaf  jmp     loc_18008BE91
0x18008bcb4  xorps   xmm0, xmm0
0x18008bcb7  movups  xmmword ptr [rsp+140h+iid.Data1], xmm0
0x18008bcbc  lea     rdx, [rsp+140h+iid]; lpiid
0x18008bcc1  mov     rcx, [rsp+140h+lpsz]; lpsz
0x18008bcc6  call    cs:__imp_IIDFromString
0x18008bccd  nop     dword ptr [rax+rax+00h]
0x18008bcd2  test    eax, eax
0x18008bcd4  js      short loc_18008BD36
0x18008bcd6  xorps   xmm0, xmm0
0x18008bcd9  movups  xmmword ptr [rbp+40h+Buf1.Data1], xmm0
0x18008bcdd  lea     rdx, [rbp+40h+Buf1]; lpiid
0x18008bce1  lea     rcx, sz; "{00000000-0000-0000-0000-000000000000}"
0x18008bce8  call    cs:__imp_IIDFromString
0x18008bcef  nop     dword ptr [rax+rax+00h]
0x18008bcf4  mov     edi, eax
0x18008bcf6  test    eax, eax
0x18008bcf8  jns     short loc_18008BD04
0x18008bcfa  mov     edx, 21Ah
0x18008bcff  jmp     loc_18008BC76
0x18008bd04  mov     r8d, 10h; Size
0x18008bd0a  lea     rdx, [rsp+140h+iid]; Buf2
0x18008bd0f  lea     rcx, [rbp+40h+Buf1]; Buf1
0x18008bd13  call    memcmp_0
0x18008bd18  test    eax, eax
0x18008bd1a  jz      short loc_18008BD36
0x18008bd1c  xor     bl, bl
0x18008bd1e  mov     r8d, [rsp+140h+var_118]
0x18008bd23  dec     r8d
0x18008bd26  mov     rdx, [rsp+140h+lpsz]
0x18008bd2b  lea     rcx, [rsp+140h+var_100]
0x18008bd30  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18008bd35  nop
0x18008bd36  mov     rcx, [rsp+140h+lpsz]; this
0x18008bd3b  mov     [rsp+140h+lpsz], 0; int
0x18008bd44  test    rcx, rcx
0x18008bd47  jz      short loc_18008BD4E
0x18008bd49  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18008bd4e  test    bl, bl
0x18008bd50  jz      loc_18008BE77
0x18008bd56  xorps   xmm0, xmm0
0x18008bd59  movups  xmmword ptr [rsp+140h+pguid.Data1], xmm0
0x18008bd5e  lea     rcx, [rsp+140h+pguid]; pguid
0x18008bd63  call    cs:__imp_CoCreateGuid
0x18008bd6a  nop     dword ptr [rax+rax+00h]
0x18008bd6f  mov     ebx, eax
0x18008bd71  test    eax, eax
0x18008bd73  jns     short loc_18008BD82
0x18008bd75  mov     r9d, eax
0x18008bd78  mov     edx, 229h
0x18008bd7d  jmp     loc_18008BBEF
0x18008bd82  xor     edx, edx; Val
0x18008bd84  lea     r8d, [rdx+4Eh]; Size
0x18008bd88  lea     rcx, [rbp+40h+sz]; void *
0x18008bd8c  call    memset_0
0x18008bd91  mov     r8d, 27h ; '''; cchMax
0x18008bd97  lea     rdx, [rbp+40h+sz]; lpsz
0x18008bd9b  lea     rcx, [rsp+140h+pguid]; rguid
0x18008bda0  call    cs:__imp_StringFromGUID2
0x18008bda7  nop     dword ptr [rax+rax+00h]
0x18008bdac  test    eax, eax
0x18008bdae  jnz     short loc_18008BDBF
0x18008bdb0  mov     ebx, 8000FFFFh
0x18008bdb5  mov     edx, 22Bh
0x18008bdba  jmp     loc_18008BBEC
0x18008bdbf  mov     [rsp+140h+nSize], 0
0x18008bdc7  mov     [rsp+140h+pValue], 0
0x18008bdd0  lea     r9, [rsp+140h+nSize]
0x18008bdd5  lea     r8, [rsp+140h+pValue]
0x18008bdda  mov     edx, 0FDE9h
0x18008bddf  lea     rcx, [rbp+40h+sz]
0x18008bde3  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18008bdea  nop     dword ptr [rax+rax+00h]
0x18008bdef  mov     ebx, eax
0x18008bdf1  test    eax, eax
0x18008bdf3  jns     short loc_18008BE1D
0x18008bdf5  mov     rcx, [rbp+48h]; this
0x18008bdf9  mov     r9d, eax; char *
0x18008bdfc  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008be03  mov     edx, 22Fh; void *
0x18008be08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008be0d  nop
0x18008be0e  lea     rcx, [rsp+140h+pValue]
0x18008be13  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008be18  jmp     loc_18008BC00
0x18008be1d  mov     r9d, [rsp+140h+nSize]; nSize
0x18008be22  mov     r8, [rsp+140h+pValue]; pValue
0x18008be27  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18008be2e  lea     rcx, Name; "AUTOPILOT_MARKER"
0x18008be35  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x18008be3c  nop     dword ptr [rax+rax+00h]
0x18008be41  test    eax, eax
0x18008be43  jnz     short loc_18008BE5E
0x18008be45  mov     rcx, [rbp+48h]; this
0x18008be49  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008be50  mov     edx, 236h; void *
0x18008be55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008be5a  mov     ebx, eax
0x18008be5c  jmp     short loc_18008BE0E
0x18008be5e  lea     rdx, [rbp+40h+sz]
0x18008be62  lea     rcx, [rsp+140h+var_100]
0x18008be67  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008be6c  nop
0x18008be6d  lea     rcx, [rsp+140h+pValue]
0x18008be72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008be77  lea     rdx, [rsp+140h+var_100]
0x18008be7c  mov     rcx, rsi
0x18008be7f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008be84  nop
0x18008be85  lea     rcx, [rsp+140h+var_100]
0x18008be8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008be8f  xor     ebx, ebx
0x18008be91  lea     rcx, [rsp+140h+ReturnedState]
0x18008be96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008be9b  mov     eax, ebx
0x18008be9d  mov     rcx, [rbp+40h+var_30]
0x18008bea1  xor     rcx, rsp; StackCookie
0x18008bea4  call    __security_check_cookie
0x18008bea9  add     rsp, 128h
0x18008beb0  pop     rdi
0x18008beb1  pop     rsi
0x18008beb2  pop     rbx
0x18008beb3  pop     rbp
0x18008beb4  retn
```
