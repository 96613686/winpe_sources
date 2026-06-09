# RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)

- ea: `0x180091fa0`
- end: `0x180092131`
- name: `?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z`
- size: `401`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008cfc4`
- `0x1800972ec`
- `0x1800a318c`
- `0x1800a32a8`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008b744`
- `0x180091c18`
- `0x180091fa0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18009203c`
- `ntdll!RtlGetPersistedStateLocation` at `0x18009203c`

## string_xrefs

- `0x180092053`: `LocationTypeRegistry`
- `0x18009207d`: `Logger::WriteGetPersistedStateLocationFailureEvent`
- `0x180092076`: `EventWriteGetPersistedStateLocationFailureEvent`
- `0x180091fdd`: `RegistryPath::InitializePersistedStatePath`
- `0x18009209d`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`
- `0x1800920de`: `RegistryPath::InitializeLocalMachinePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryPath::InitializePersistedStatePath(
        RegistryPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int PersistedStateLocation; // esi
  int v8; // edi
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // eax
  const wchar_t *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  unsigned __int16 v16[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(v16, 0, 0x208u);
  if ( a2 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(a2, 0, a3, 0, v16);
    if ( PersistedStateLocation >= 0 )
    {
      v13 = RegistryPath::Initialize(this, HKEY_LOCAL_MACHINE, L"HKEY_LOCAL_MACHINE", v16);
      v8 = v13;
      if ( v13 < 0 )
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistryPath::InitializePersistedStatePath",
          L"RegistryPath::InitializeLocalMachinePath",
          (unsigned int)v13);
    }
    else
    {
      v8 = 0;
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v11 = McTemplateU0dzzdz_EventWriteTransfer(
                v10,
                v9,
                PersistedStateLocation,
                (_DWORD)a2,
                (__int64)a3,
                520,
                (__int64)L"LocationTypeRegistry");
        if ( v11 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteGetPersistedStateLocationFailureEvent",
            L"EventWriteGetPersistedStateLocationFailureEvent",
            v11);
      }
      v12 = L"<NULL>";
      if ( a3 )
        v12 = a3;
      Logger::TraceError(
        L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
        L"RegistryPath::InitializePersistedStatePath",
        (unsigned int)PersistedStateLocation,
        a2,
        v12);
    }
  }
  else
  {
    PersistedStateLocation = 0;
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::InitializePersistedStatePath", L"sourceId");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistryPath::InitializePersistedStatePath", L"sourceId");
  }
  v14 = PersistedStateLocation | 0x10000000;
  if ( PersistedStateLocation >= 0 )
    v14 = v8;
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::InitializePersistedStatePath", v14);
  return v14;
}

```

## disassembly

```asm
0x180091fa0  push    rbx
0x180091fa2  push    rbp
0x180091fa3  push    rsi
0x180091fa4  push    rdi
0x180091fa5  push    r14
0x180091fa7  sub     rsp, 260h
0x180091fae  mov     rax, cs:__security_cookie
0x180091fb5  xor     rax, rsp
0x180091fb8  mov     [rsp+288h+var_38], rax
0x180091fc0  mov     rbx, r8
0x180091fc3  mov     rbp, rdx
0x180091fc6  mov     rdi, rcx
0x180091fc9  mov     esi, 208h
0x180091fce  mov     r8d, esi; Size
0x180091fd1  lea     rcx, [rsp+288h+var_248]; void *
0x180091fd6  xor     edx, edx; Val
0x180091fd8  call    memset_0
0x180091fdd  lea     r14, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180091fe4  test    rbp, rbp
0x180091fe7  jnz     short loc_18009201A
0x180091fe9  lea     r8, aSourceid; "sourceId"
0x180091ff0  mov     rdx, r14
0x180091ff3  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180091ffa  xor     esi, esi
0x180091ffc  mov     edi, 80070057h
0x180092001  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092006  lea     rdx, aSourceid; "sourceId"
0x18009200d  mov     rcx, r14; unsigned __int16 *
0x180092010  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180092015  jmp     loc_1800920F4
0x18009201a  mov     [rsp+288h+var_258], 0
0x180092023  lea     rax, [rsp+288h+var_248]
0x180092028  mov     [rsp+288h+var_260], esi
0x18009202c  xor     r9d, r9d
0x18009202f  mov     r8, rbx
0x180092032  mov     [rsp+288h+var_268], rax
0x180092037  xor     edx, edx
0x180092039  mov     rcx, rbp
0x18009203c  call    cs:__imp_RtlGetPersistedStateLocation
0x180092042  mov     esi, eax
0x180092044  test    eax, eax
0x180092046  jns     short loc_1800920BA
0x180092048  xor     edi, edi
0x18009204a  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180092051  jz      short loc_180092090
0x180092053  lea     rax, aLocationtypere; "LocationTypeRegistry"
0x18009205a  mov     r9, rbp
0x18009205d  mov     [rsp+288h+var_258], rax
0x180092062  mov     r8d, esi
0x180092065  mov     [rsp+288h+var_268], rbx
0x18009206a  call    McTemplateU0dzzdz_EventWriteTransfer
0x18009206f  test    eax, eax
0x180092071  jz      short loc_180092090
0x180092073  mov     r9d, eax
0x180092076  lea     r8, aEventwritegetp; "EventWriteGetPersistedStateLocationFail"...
0x18009207d  lea     rdx, aLoggerWriteget_0; "Logger::WriteGetPersistedStateLocationF"...
0x180092084  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009208b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092090  test    rbx, rbx
0x180092093  lea     rax, aNull_2; "<NULL>"
0x18009209a  mov     r9, rbp
0x18009209d  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x1800920a4  cmovnz  rax, rbx
0x1800920a8  mov     r8d, esi
0x1800920ab  mov     rdx, r14
0x1800920ae  mov     [rsp+288h+var_268], rax
0x1800920b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800920b8  jmp     short loc_1800920F4
0x1800920ba  lea     r9, [rsp+288h+var_248]; unsigned __int16 *
0x1800920bf  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800920c6  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x1800920cd  mov     rcx, rdi; this
0x1800920d0  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800920d5  mov     edi, eax
0x1800920d7  test    eax, eax
0x1800920d9  jns     short loc_1800920F4
0x1800920db  mov     r9d, eax
0x1800920de  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x1800920e5  mov     rdx, r14
0x1800920e8  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800920ef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800920f4  mov     ebx, esi
0x1800920f6  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800920fd  bts     ebx, 1Ch
0x180092101  mov     rdx, r14
0x180092104  test    esi, esi
0x180092106  cmovns  ebx, edi
0x180092109  mov     r8d, ebx
0x18009210c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092111  mov     eax, ebx
0x180092113  mov     rcx, [rsp+288h+var_38]
0x18009211b  xor     rcx, rsp; StackCookie
0x18009211e  call    __security_check_cookie
0x180092123  add     rsp, 260h
0x18009212a  pop     r14
0x18009212c  pop     rdi
0x18009212d  pop     rsi
0x18009212e  pop     rbp
0x18009212f  pop     rbx
0x180092130  retn
```
