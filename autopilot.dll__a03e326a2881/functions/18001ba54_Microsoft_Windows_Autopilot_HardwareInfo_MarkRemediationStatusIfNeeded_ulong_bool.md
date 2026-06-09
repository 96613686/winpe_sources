# Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded(ulong &,bool &)

- ea: `0x18001ba54`
- end: `0x18001bcf0`
- name: `?MarkRemediationStatusIfNeeded@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAKAEA_N@Z`
- size: `668`
- prototype: `__int64 __fastcall(unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016420`

## callees

- `0x1800045b0`
- `0x1800105d4`
- `0x1800105f4`
- `0x180013a40`
- `0x180015ed0`
- `0x180017400`
- `0x1800174f0`
- `0x1800193e4`
- `0x1800197f4`
- `0x180019ad4`
- `0x180019c14`
- `0x18001ba28`
- `0x18001ba54`
- `0x18001c234`
- `0x180020810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb14`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001bb26`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001bb26`

## string_xrefs

- `0x18001bad7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded(
        unsigned int *a1,
        bool *a2)
{
  unsigned int v4; // ebx
  int StringFromStorage; // edi
  int v6; // eax
  const char *v7; // r9
  int LastError; // ebx
  unsigned int ValueW; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int v12; // ebx
  __int64 v13; // rdx
  unsigned __int64 v15; // rdx
  signed __int64 v16; // rdx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  bool v19; // di
  int pdwType; // [rsp+20h] [rbp-49h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-49h]
  bool v22; // [rsp+40h] [rbp-29h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-19h] BYREF
  __int128 v25; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h]
  __int64 v27; // [rsp+70h] [rbp+7h]
  SYSTEMTIME SystemTime; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v29; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 7;
  LOWORD(v25) = 0;
  SystemTime = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&SystemTime, L"NextAllowedContactTime", 22);
  StringFromStorage = Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(
                        1,
                        &SystemTime.wYear,
                        (__int64)&v25);
  std::wstring::_Tidy_deallocate(&SystemTime);
  if ( StringFromStorage < 0 )
  {
    if ( (unsigned int)(StringFromStorage + 2147024894) <= 1 )
      goto LABEL_24;
    goto LABEL_22;
  }
  if ( !v26 )
  {
LABEL_22:
    v17 = (unsigned int)StringFromStorage;
    v18 = 847;
    goto LABEL_23;
  }
  SystemTime = 0;
  v6 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(&v25, &SystemTime);
  if ( v6 < 0 )
  {
    v17 = (unsigned int)v6;
    v18 = 842;
LABEL_23:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v17,
      pdwType);
    goto LABEL_24;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x33C,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                  v7);
    std::wstring::_Tidy_deallocate(&v25);
    if ( LastError < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)(unsigned int)LastError,
        pdwType);
    goto LABEL_7;
  }
  v15 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime;
  if ( *(_QWORD *)&SystemTimeAsFileTime < *(unsigned __int64 *)&FileTime )
    v15 = *(_QWORD *)&FileTime - *(_QWORD *)&SystemTimeAsFileTime;
  v16 = v15 / 0x23C34600;
  if ( *(_QWORD *)&SystemTimeAsFileTime > *(unsigned __int64 *)&FileTime )
    v16 = -v16;
  v4 = 0;
  if ( v16 >= 0 )
    v4 = v16;
LABEL_24:
  std::wstring::_Tidy_deallocate(&v25);
  if ( v4 )
  {
    *a2 = 0;
    *a1 = v4;
    return 0;
  }
LABEL_7:
  FileTime.dwLowDateTime = 0;
  SystemTimeAsFileTime.dwLowDateTime = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Provisioning\\HardwareInfo",
             L"HardwareIgnoreFilter",
             0x10u,
             0,
             &FileTime,
             (LPDWORD)&SystemTimeAsFileTime);
  if ( (ValueW & 0xFFFFFFFC) != 0 || ValueW == 1 )
    wil::details::in1diag3::Log_Win32(retaddr, v10, v11, (const char *)ValueW, pdwTypea);
  v22 = 0;
  v12 = Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(FileTime.dwLowDateTime, &v22);
  if ( v12 < 0 )
  {
    v13 = 104;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v12,
      pdwTypea);
    return (unsigned int)v12;
  }
  v19 = v22;
  if ( v22 )
  {
    v12 = Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData();
    if ( v12 < 0 )
    {
      v13 = 108;
      goto LABEL_12;
    }
    v12 = Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache();
    if ( v12 < 0 )
    {
      v13 = 111;
      goto LABEL_12;
    }
    v12 = Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot();
    if ( v12 < 0 )
    {
      v13 = 114;
      goto LABEL_12;
    }
  }
  *a2 = v19;
  return 0;
}

```

## disassembly

```asm
0x18001ba54  mov     [rsp-8+arg_10], rbx
0x18001ba59  push    rbp
0x18001ba5a  push    rsi
0x18001ba5b  push    rdi
0x18001ba5c  push    r12
0x18001ba5e  push    r14
0x18001ba60  lea     rbp, [rsp-37h]
0x18001ba65  sub     rsp, 0A0h
0x18001ba6c  mov     rax, cs:__security_cookie
0x18001ba73  xor     rax, rsp
0x18001ba76  mov     [rbp+57h+var_28], rax
0x18001ba7a  mov     rsi, rdx
0x18001ba7d  mov     r14, rcx
0x18001ba80  xor     ebx, ebx
0x18001ba82  xorps   xmm0, xmm0
0x18001ba85  movups  [rbp+57h+var_68], xmm0
0x18001ba89  mov     [rbp+57h+var_58], rbx
0x18001ba8d  mov     [rbp+57h+var_50], 7
0x18001ba95  xor     eax, eax
0x18001ba97  mov     word ptr [rbp+57h+var_68], ax
0x18001ba9b  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001ba9f  xorps   xmm1, xmm1
0x18001baa2  movdqu  [rbp+57h+var_38], xmm1
0x18001baa7  lea     r8d, [rbx+16h]
0x18001baab  lea     rdx, aNextallowedcon; "NextAllowedContactTime"
0x18001bab2  lea     rcx, [rbp+57h+SystemTime]
0x18001bab6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001babb  nop
0x18001babc  lea     r8, [rbp+57h+var_68]
0x18001bac0  lea     rdx, [rbp+57h+SystemTime]
0x18001bac4  lea     ecx, [rbx+1]
0x18001bac7  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x18001bacc  mov     edi, eax
0x18001bace  lea     rcx, [rbp+57h+SystemTime]
0x18001bad2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bad7  lea     r12, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bade  test    edi, edi
0x18001bae0  js      loc_18001BC47
0x18001bae6  cmp     [rbp+57h+var_58], rbx
0x18001baea  jz      loc_18001BC52
0x18001baf0  xorps   xmm0, xmm0
0x18001baf3  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001baf7  lea     rdx, [rbp+57h+SystemTime]
0x18001bafb  lea     rcx, [rbp+57h+var_68]
0x18001baff  call    ?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::wstring const &,_SYSTEMTIME &)
0x18001bb04  test    eax, eax
0x18001bb06  js      loc_18001BC3D
0x18001bb0c  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001bb10  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bb14  call    cs:__imp_GetSystemTimeAsFileTime
0x18001bb1a  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x18001bb1e  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001bb22  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001bb26  call    cs:__imp_SystemTimeToFileTime
0x18001bb2c  test    eax, eax
0x18001bb2e  jnz     loc_18001BBFF
0x18001bb34  mov     rcx, [rbp+5Fh]; this
0x18001bb38  mov     r8, r12; unsigned int
0x18001bb3b  mov     edx, 33Ch; void *
0x18001bb40  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bb45  mov     ebx, eax
0x18001bb47  lea     rcx, [rbp+57h+var_68]
0x18001bb4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bb50  test    ebx, ebx
0x18001bb52  jns     short loc_18001BB68
0x18001bb54  mov     rcx, [rbp+5Fh]; this
0x18001bb58  mov     r9d, ebx; char *
0x18001bb5b  mov     r8, r12; unsigned int
0x18001bb5e  mov     edx, 5Ah ; 'Z'; void *
0x18001bb63  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bb68  mov     [rbp+57h+FileTime.dwLowDateTime], 0
0x18001bb6f  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 4
0x18001bb76  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x18001bb7a  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001bb7f  lea     rax, [rbp+57h+FileTime]
0x18001bb83  mov     [rsp+0C0h+pvData], rax; pvData
0x18001bb88  mov     [rsp+0C0h+pdwType], 0; int
0x18001bb91  mov     r9d, 10h; dwFlags
0x18001bb97  lea     r8, aHardwareignore; "HardwareIgnoreFilter"
0x18001bb9e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001bba5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001bbac  call    cs:__imp_RegGetValueW
0x18001bbb2  test    eax, 0FFFFFFFCh
0x18001bbb7  jnz     short loc_18001BBBE
0x18001bbb9  cmp     eax, 1
0x18001bbbc  jnz     short loc_18001BBCA
0x18001bbbe  mov     rcx, [rbp+5Fh]; this
0x18001bbc2  mov     r9d, eax; char *
0x18001bbc5  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001bbca  mov     [rbp+57h+var_80], 0
0x18001bbce  lea     rdx, [rbp+57h+var_80]; bool *
0x18001bbd2  mov     ecx, [rbp+57h+FileTime.dwLowDateTime]; unsigned int
0x18001bbd5  call    ?CheckIfHardwareChanged@HardwareInfo@Autopilot@Windows@Microsoft@@SAJKAEA_N@Z; Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(ulong,bool &)
0x18001bbda  mov     ebx, eax
0x18001bbdc  test    eax, eax
0x18001bbde  jns     loc_18001BC80
0x18001bbe4  mov     edx, 68h ; 'h'; void *
0x18001bbe9  mov     r8, r12; unsigned int
0x18001bbec  mov     r9d, ebx; char *
0x18001bbef  mov     rcx, [rbp+5Fh]; this
0x18001bbf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbf8  mov     eax, ebx
0x18001bbfa  jmp     loc_18001BCCD
0x18001bbff  mov     r8, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001bc03  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18001bc07  mov     rax, rcx
0x18001bc0a  sub     rax, r8
0x18001bc0d  mov     rdx, r8
0x18001bc10  sub     rdx, rcx
0x18001bc13  cmp     r8, rcx
0x18001bc16  cmovb   rdx, rax
0x18001bc1a  mov     rax, 0E5109EC205D7BEA7h
0x18001bc24  mul     rdx
0x18001bc27  shr     rdx, 1Dh
0x18001bc2b  cmp     r8, rcx
0x18001bc2e  jbe     short loc_18001BC33
0x18001bc30  neg     rdx
0x18001bc33  xor     ebx, ebx
0x18001bc35  test    rdx, rdx
0x18001bc38  cmovns  ebx, edx
0x18001bc3b  jmp     short loc_18001BC67
0x18001bc3d  mov     r9d, eax
0x18001bc40  mov     edx, 34Ah
0x18001bc45  jmp     short loc_18001BC5A
0x18001bc47  lea     eax, [rdi+7FF8FFFEh]
0x18001bc4d  cmp     eax, 1
0x18001bc50  jbe     short loc_18001BC67
0x18001bc52  mov     r9d, edi; char *
0x18001bc55  mov     edx, 34Fh; void *
0x18001bc5a  mov     r8, r12; unsigned int
0x18001bc5d  mov     rcx, [rbp+5Fh]; this
0x18001bc61  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001bc66  nop
0x18001bc67  lea     rcx, [rbp+57h+var_68]
0x18001bc6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bc70  test    ebx, ebx
0x18001bc72  jz      loc_18001BB68
0x18001bc78  mov     byte ptr [rsi], 0
0x18001bc7b  mov     [r14], ebx
0x18001bc7e  jmp     short loc_18001BCCB
0x18001bc80  mov     dil, [rbp+57h+var_80]
0x18001bc84  test    dil, dil
0x18001bc87  jz      short loc_18001BCC8
0x18001bc89  call    ?CallApsWithRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData(void)
0x18001bc8e  mov     ebx, eax
0x18001bc90  test    eax, eax
0x18001bc92  jns     short loc_18001BC9E
0x18001bc94  mov     edx, 6Ch ; 'l'
0x18001bc99  jmp     loc_18001BBE9
0x18001bc9e  call    ?CopyHardwareComponentsCache@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@0@Z; Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x18001bca3  mov     ebx, eax
0x18001bca5  test    eax, eax
0x18001bca7  jns     short loc_18001BCB3
0x18001bca9  mov     edx, 6Fh ; 'o'
0x18001bcae  jmp     loc_18001BBE9
0x18001bcb3  call    ?CollectHardwareSnapshot@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)
0x18001bcb8  mov     ebx, eax
0x18001bcba  test    eax, eax
0x18001bcbc  jns     short loc_18001BCC8
0x18001bcbe  mov     edx, 72h ; 'r'
0x18001bcc3  jmp     loc_18001BBE9
0x18001bcc8  mov     [rsi], dil
0x18001bccb  xor     eax, eax
0x18001bccd  mov     rcx, [rbp+57h+var_28]
0x18001bcd1  xor     rcx, rsp; StackCookie
0x18001bcd4  call    __security_check_cookie
0x18001bcd9  mov     rbx, [rsp+0C0h+arg_10]
0x18001bce1  add     rsp, 0A0h
0x18001bce8  pop     r14
0x18001bcea  pop     r12
0x18001bcec  pop     rdi
0x18001bced  pop     rsi
0x18001bcee  pop     rbp
0x18001bcef  retn
```
