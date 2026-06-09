# RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)

- ea: `0x180081a14`
- end: `0x180081b65`
- name: `?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z`
- size: `337`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007dfa4`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d4ac`
- `0x18008168c`
- `0x180081a14`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180081a77`
- `ntdll!RtlGetPersistedStateLocation` at `0x180081a77`

## string_xrefs

- `0x180081a8e`: `LocationTypeRegistry`
- `0x180081ab0`: `Logger::WriteGetPersistedStateLocationFailureEvent`
- `0x180081aa9`: `EventWriteGetPersistedStateLocationFailureEvent`
- `0x180081ad2`: `RegistryPath::InitializePersistedStatePath`
- `0x180081b12`: `RegistryPath::InitializePersistedStatePath`
- `0x180081b27`: `RegistryPath::InitializePersistedStatePath`
- `0x180081b0b`: `RegistryPath::InitializeLocalMachinePath`
- `0x180081ad9`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`

## pseudocode

```c
__int64 __fastcall RegistryPath::InitializePersistedStatePath(
        RegistryPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v5; // edx
  int v6; // ecx
  int PersistedStateLocation; // esi
  int v8; // r9d
  unsigned int v9; // edi
  unsigned int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned __int16 v14[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(v14, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CloudDomainJoinRoot",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
                             0);
  if ( PersistedStateLocation >= 0 )
  {
    v11 = RegistryPath::Initialize(this, HKEY_LOCAL_MACHINE, L"HKEY_LOCAL_MACHINE", v14);
    v9 = v11;
    if ( v11 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistryPath::InitializePersistedStatePath",
        L"RegistryPath::InitializeLocalMachinePath",
        (unsigned int)v11);
  }
  else
  {
    v9 = 0;
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v10 = McTemplateU0dzzdz_EventWriteTransfer(
              v6,
              v5,
              PersistedStateLocation,
              v8,
              (unsigned int)v14,
              520,
              (__int64)L"LocationTypeRegistry");
      if ( v10 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteGetPersistedStateLocationFailureEvent",
          L"EventWriteGetPersistedStateLocationFailureEvent",
          v10);
    }
    Logger::TraceError(
      L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
      L"RegistryPath::InitializePersistedStatePath",
      (unsigned int)PersistedStateLocation,
      L"CloudDomainJoinRoot",
      L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin");
  }
  v12 = PersistedStateLocation | 0x10000000;
  if ( PersistedStateLocation >= 0 )
    v12 = v9;
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::InitializePersistedStatePath", v12);
  return v12;
}

```

## disassembly

```asm
0x180081a14  push    rbx
0x180081a16  push    rsi
0x180081a17  push    rdi
0x180081a18  push    r14
0x180081a1a  sub     rsp, 268h
0x180081a21  mov     rax, cs:__security_cookie
0x180081a28  xor     rax, rsp
0x180081a2b  mov     [rsp+288h+var_38], rax
0x180081a33  mov     rbx, rcx
0x180081a36  mov     edi, 208h
0x180081a3b  mov     r8d, edi; Size
0x180081a3e  lea     rcx, [rsp+288h+var_248]; void *
0x180081a43  xor     edx, edx; Val
0x180081a45  call    memset_0
0x180081a4a  lea     rax, [rsp+288h+var_248]
0x180081a4f  mov     [rsp+288h+var_258], 0
0x180081a58  lea     r14, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x180081a5f  mov     [rsp+288h+var_260], edi
0x180081a63  mov     r8, r14
0x180081a66  mov     [rsp+288h+var_268], rax
0x180081a6b  xor     r9d, r9d
0x180081a6e  lea     rcx, aClouddomainjoi; "CloudDomainJoinRoot"
0x180081a75  xor     edx, edx
0x180081a77  call    cs:__imp_RtlGetPersistedStateLocation
0x180081a7d  mov     esi, eax
0x180081a7f  test    eax, eax
0x180081a81  jns     short loc_180081AE7
0x180081a83  xor     edi, edi
0x180081a85  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180081a8c  jz      short loc_180081AC3
0x180081a8e  lea     rax, aLocationtypere; "LocationTypeRegistry"
0x180081a95  mov     r8d, esi
0x180081a98  mov     [rsp+288h+var_258], rax
0x180081a9d  call    McTemplateU0dzzdz_EventWriteTransfer
0x180081aa2  test    eax, eax
0x180081aa4  jz      short loc_180081AC3
0x180081aa6  mov     r9d, eax
0x180081aa9  lea     r8, aEventwritegetp; "EventWriteGetPersistedStateLocationFail"...
0x180081ab0  lea     rdx, aLoggerWriteget; "Logger::WriteGetPersistedStateLocationF"...
0x180081ab7  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180081abe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081ac3  lea     r9, aClouddomainjoi; "CloudDomainJoinRoot"
0x180081aca  mov     [rsp+288h+var_268], r14
0x180081acf  mov     r8d, esi
0x180081ad2  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180081ad9  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x180081ae0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081ae5  jmp     short loc_180081B25
0x180081ae7  lea     r9, [rsp+288h+var_248]; unsigned __int16 *
0x180081aec  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180081af3  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180081afa  mov     rcx, rbx; this
0x180081afd  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180081b02  mov     edi, eax
0x180081b04  test    eax, eax
0x180081b06  jns     short loc_180081B25
0x180081b08  mov     r9d, eax
0x180081b0b  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x180081b12  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180081b19  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180081b20  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081b25  mov     ebx, esi
0x180081b27  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180081b2e  bts     ebx, 1Ch
0x180081b32  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180081b39  test    esi, esi
0x180081b3b  cmovns  ebx, edi
0x180081b3e  mov     r8d, ebx
0x180081b41  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180081b46  mov     eax, ebx
0x180081b48  mov     rcx, [rsp+288h+var_38]
0x180081b50  xor     rcx, rsp; StackCookie
0x180081b53  call    __security_check_cookie
0x180081b58  add     rsp, 268h
0x180081b5f  pop     r14
0x180081b61  pop     rdi
0x180081b62  pop     rsi
0x180081b63  pop     rbx
0x180081b64  retn
```
