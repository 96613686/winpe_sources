# Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded(ulong &,bool &)

- ea: `0x18001c190`
- end: `0x18001c43f`
- name: `?MarkRemediationStatusIfNeeded@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAKAEA_N@Z`
- size: `687`
- prototype: `__int64 __fastcall(unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800168c0`

## callees

- `0x1800045d0`
- `0x180010744`
- `0x180010764`
- `0x180013de4`
- `0x180016350`
- `0x18001792c`
- `0x180017a20`
- `0x1800199e4`
- `0x180019e18`
- `0x18001a0f8`
- `0x18001a238`
- `0x18001c164`
- `0x18001c190`
- `0x18001c958`
- `0x1800211e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c2f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c2f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c250`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c250`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c268`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c268`

## string_xrefs

- `0x18001c213`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
  std::wstring::_Construct<1,unsigned short const *>(&SystemTime, L"NextAllowedContactTime");
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
0x18001c190  mov     [rsp-8+arg_10], rbx
0x18001c195  push    rbp
0x18001c196  push    rsi
0x18001c197  push    rdi
0x18001c198  push    r12
0x18001c19a  push    r14
0x18001c19c  lea     rbp, [rsp-37h]
0x18001c1a1  sub     rsp, 0A0h
0x18001c1a8  mov     rax, cs:__security_cookie
0x18001c1af  xor     rax, rsp
0x18001c1b2  mov     [rbp+57h+var_28], rax
0x18001c1b6  mov     rsi, rdx
0x18001c1b9  mov     r14, rcx
0x18001c1bc  xor     ebx, ebx
0x18001c1be  xorps   xmm0, xmm0
0x18001c1c1  movups  [rbp+57h+var_68], xmm0
0x18001c1c5  mov     [rbp+57h+var_58], rbx
0x18001c1c9  mov     [rbp+57h+var_50], 7
0x18001c1d1  xor     eax, eax
0x18001c1d3  mov     word ptr [rbp+57h+var_68], ax
0x18001c1d7  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c1db  xorps   xmm1, xmm1
0x18001c1de  movdqu  [rbp+57h+var_38], xmm1
0x18001c1e3  lea     r8d, [rbx+16h]
0x18001c1e7  lea     rdx, aNextallowedcon; "NextAllowedContactTime"
0x18001c1ee  lea     rcx, [rbp+57h+SystemTime]
0x18001c1f2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c1f7  nop
0x18001c1f8  lea     r8, [rbp+57h+var_68]
0x18001c1fc  lea     rdx, [rbp+57h+SystemTime]
0x18001c200  lea     ecx, [rbx+1]
0x18001c203  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x18001c208  mov     edi, eax
0x18001c20a  lea     rcx, [rbp+57h+SystemTime]
0x18001c20e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c213  lea     r12, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c21a  test    edi, edi
0x18001c21c  js      loc_18001C395
0x18001c222  cmp     [rbp+57h+var_58], rbx
0x18001c226  jz      loc_18001C3A0
0x18001c22c  xorps   xmm0, xmm0
0x18001c22f  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c233  lea     rdx, [rbp+57h+SystemTime]
0x18001c237  lea     rcx, [rbp+57h+var_68]
0x18001c23b  call    ?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::wstring const &,_SYSTEMTIME &)
0x18001c240  test    eax, eax
0x18001c242  js      loc_18001C38B
0x18001c248  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001c24c  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c250  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c257  nop     dword ptr [rax+rax+00h]
0x18001c25c  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x18001c260  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001c264  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c268  call    cs:__imp_SystemTimeToFileTime
0x18001c26f  nop     dword ptr [rax+rax+00h]
0x18001c274  test    eax, eax
0x18001c276  jnz     loc_18001C34D
0x18001c27c  mov     rcx, [rbp+5Fh]; this
0x18001c280  mov     r8, r12; unsigned int
0x18001c283  mov     edx, 33Ch; void *
0x18001c288  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c28d  mov     ebx, eax
0x18001c28f  lea     rcx, [rbp+57h+var_68]
0x18001c293  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c298  test    ebx, ebx
0x18001c29a  jns     short loc_18001C2B0
0x18001c29c  mov     rcx, [rbp+5Fh]; this
0x18001c2a0  mov     r9d, ebx; char *
0x18001c2a3  mov     r8, r12; unsigned int
0x18001c2a6  mov     edx, 5Ah ; 'Z'; void *
0x18001c2ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c2b0  mov     [rbp+57h+FileTime.dwLowDateTime], 0
0x18001c2b7  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 4
0x18001c2be  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x18001c2c2  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001c2c7  lea     rax, [rbp+57h+FileTime]
0x18001c2cb  mov     [rsp+0C0h+pvData], rax; pvData
0x18001c2d0  mov     [rsp+0C0h+pdwType], 0; int
0x18001c2d9  mov     r9d, 10h; dwFlags
0x18001c2df  lea     r8, aHardwareignore; "HardwareIgnoreFilter"
0x18001c2e6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001c2ed  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c2f4  call    cs:__imp_RegGetValueW
0x18001c2fb  nop     dword ptr [rax+rax+00h]
0x18001c300  test    eax, 0FFFFFFFCh
0x18001c305  jnz     short loc_18001C30C
0x18001c307  cmp     eax, 1
0x18001c30a  jnz     short loc_18001C318
0x18001c30c  mov     rcx, [rbp+5Fh]; this
0x18001c310  mov     r9d, eax; char *
0x18001c313  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001c318  mov     [rbp+57h+var_80], 0
0x18001c31c  lea     rdx, [rbp+57h+var_80]; bool *
0x18001c320  mov     ecx, [rbp+57h+FileTime.dwLowDateTime]; unsigned int
0x18001c323  call    ?CheckIfHardwareChanged@HardwareInfo@Autopilot@Windows@Microsoft@@SAJKAEA_N@Z; Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(ulong,bool &)
0x18001c328  mov     ebx, eax
0x18001c32a  test    eax, eax
0x18001c32c  jns     loc_18001C3CE
0x18001c332  mov     edx, 68h ; 'h'; void *
0x18001c337  mov     r8, r12; unsigned int
0x18001c33a  mov     r9d, ebx; char *
0x18001c33d  mov     rcx, [rbp+5Fh]; this
0x18001c341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c346  mov     eax, ebx
0x18001c348  jmp     loc_18001C41B
0x18001c34d  mov     r8, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c351  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18001c355  mov     rax, rcx
0x18001c358  sub     rax, r8
0x18001c35b  mov     rdx, r8
0x18001c35e  sub     rdx, rcx
0x18001c361  cmp     r8, rcx
0x18001c364  cmovb   rdx, rax
0x18001c368  mov     rax, 0E5109EC205D7BEA7h
0x18001c372  mul     rdx
0x18001c375  shr     rdx, 1Dh
0x18001c379  cmp     r8, rcx
0x18001c37c  jbe     short loc_18001C381
0x18001c37e  neg     rdx
0x18001c381  xor     ebx, ebx
0x18001c383  test    rdx, rdx
0x18001c386  cmovns  ebx, edx
0x18001c389  jmp     short loc_18001C3B5
0x18001c38b  mov     r9d, eax
0x18001c38e  mov     edx, 34Ah
0x18001c393  jmp     short loc_18001C3A8
0x18001c395  lea     eax, [rdi+7FF8FFFEh]
0x18001c39b  cmp     eax, 1
0x18001c39e  jbe     short loc_18001C3B5
0x18001c3a0  mov     r9d, edi; char *
0x18001c3a3  mov     edx, 34Fh; void *
0x18001c3a8  mov     r8, r12; unsigned int
0x18001c3ab  mov     rcx, [rbp+5Fh]; this
0x18001c3af  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c3b4  nop
0x18001c3b5  lea     rcx, [rbp+57h+var_68]
0x18001c3b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c3be  test    ebx, ebx
0x18001c3c0  jz      loc_18001C2B0
0x18001c3c6  mov     byte ptr [rsi], 0
0x18001c3c9  mov     [r14], ebx
0x18001c3cc  jmp     short loc_18001C419
0x18001c3ce  mov     dil, [rbp+57h+var_80]
0x18001c3d2  test    dil, dil
0x18001c3d5  jz      short loc_18001C416
0x18001c3d7  call    ?CallApsWithRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData(void)
0x18001c3dc  mov     ebx, eax
0x18001c3de  test    eax, eax
0x18001c3e0  jns     short loc_18001C3EC
0x18001c3e2  mov     edx, 6Ch ; 'l'
0x18001c3e7  jmp     loc_18001C337
0x18001c3ec  call    ?CopyHardwareComponentsCache@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@0@Z; Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x18001c3f1  mov     ebx, eax
0x18001c3f3  test    eax, eax
0x18001c3f5  jns     short loc_18001C401
0x18001c3f7  mov     edx, 6Fh ; 'o'
0x18001c3fc  jmp     loc_18001C337
0x18001c401  call    ?CollectHardwareSnapshot@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)
0x18001c406  mov     ebx, eax
0x18001c408  test    eax, eax
0x18001c40a  jns     short loc_18001C416
0x18001c40c  mov     edx, 72h ; 'r'
0x18001c411  jmp     loc_18001C337
0x18001c416  mov     [rsi], dil
0x18001c419  xor     eax, eax
0x18001c41b  mov     rcx, [rbp+57h+var_28]
0x18001c41f  xor     rcx, rsp; StackCookie
0x18001c422  call    __security_check_cookie
0x18001c427  mov     rbx, [rsp+0C0h+arg_10]
0x18001c42f  add     rsp, 0A0h
0x18001c436  pop     r14
0x18001c438  pop     r12
0x18001c43a  pop     rdi
0x18001c43b  pop     rsi
0x18001c43c  pop     rbp
0x18001c43d  retn
```
