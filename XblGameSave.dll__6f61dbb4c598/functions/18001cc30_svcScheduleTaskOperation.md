# svcScheduleTaskOperation

- ea: `0x18001cc30`
- end: `0x18001cd1c`
- name: `svcScheduleTaskOperation`
- size: `236`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011c0c`
- `0x180013e1c`
- `0x1800160c8`
- `0x180016364`
- `0x1800170d4`
- `0x18001cc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ccc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ccc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ccf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ccf2`

## string_xrefs

- `0x18001cc92`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall svcScheduleTaskOperation(__int64 a1, const WCHAR *a2)
{
  char *v2; // r8
  const unsigned __int16 *v3; // r8
  struct ConnectedStorage::Mutex *v4; // rbx
  unsigned int v6; // [rsp+20h] [rbp-78h]
  HSTRING string; // [rsp+28h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v9[16]; // [rsp+40h] [rbp-58h] BYREF

  v6 = 0;
  try
  {
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a2);
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)&CriticalSection,
        v2);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v3);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v4 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    ConnectedStorage::Service::ScheduledTaskOperation(
      qword_1800C0858,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&string);
    if ( v4 )
      ConnectedStorage::Service::ReturnInstance();
    WindowsDeleteString(string);
  }
  catch ( ConnectedStorage::ComError v9 )
  {
    v6 = v9[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v9);
    return v6;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return v6;
}

```

## disassembly

```asm
0x18001cc30  push    rbx
0x18001cc32  sub     rsp, 90h
0x18001cc39  mov     rax, cs:__security_cookie
0x18001cc40  xor     rax, rsp
0x18001cc43  mov     [rsp+98h+var_18], rax
0x18001cc4b  mov     [rsp+98h+var_78], 0
0x18001cc53  lea     rcx, [rsp+98h+string]; string
0x18001cc58  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18001cc5d  nop
0x18001cc5e  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x18001cc65  jnz     short loc_18001CCC8
0x18001cc67  or      edx, 0FFFFFFFFh; unsigned int
0x18001cc6a  lea     rcx, qword_1800C0998; this
0x18001cc71  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x18001cc76  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x18001cc7d  lea     rcx, [rsp+98h+lpCriticalSection]; this
0x18001cc82  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18001cc87  nop
0x18001cc88  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x18001cc8e  test    eax, eax
0x18001cc90  jnz     short loc_18001CCA3
0x18001cc92  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x18001cc99  mov     ecx, 80004005h; this
0x18001cc9e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001cca3  inc     eax
0x18001cca5  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x18001ccab  mov     edx, 2
0x18001ccb0  mov     rcx, cs:qword_1800C0858
0x18001ccb7  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x18001ccbc  nop
0x18001ccbd  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18001ccc2  call    cs:__imp_LeaveCriticalSection
0x18001ccc8  mov     rbx, cs:qword_1800C0858
0x18001cccf  mov     [rsp+98h+lpCriticalSection], rbx
0x18001ccd4  lea     rdx, [rsp+98h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x18001ccd9  mov     rcx, rbx; this
0x18001ccdc  call    ?ScheduledTaskOperation@Service@ConnectedStorage@@QEAAXAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::Service::ScheduledTaskOperation(ConnectedStorage::SimpleHStringWrapper const &)
0x18001cce1  nop
0x18001cce2  test    rbx, rbx
0x18001cce5  jz      short loc_18001CCED
0x18001cce7  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x18001ccec  nop
0x18001cced  mov     rcx, [rsp+98h+string]; string
0x18001ccf2  call    cs:__imp_WindowsDeleteString
0x18001ccf8  nop
0x18001ccf9  jmp     short loc_18001CCFF
0x18001ccfb  jmp     short loc_18001CCFF
0x18001ccfd  jmp     short $+2
0x18001ccff  mov     eax, [rsp+98h+var_78]
0x18001cd03  mov     rcx, [rsp+98h+var_18]
0x18001cd0b  xor     rcx, rsp; StackCookie
0x18001cd0e  call    __security_check_cookie
0x18001cd13  add     rsp, 90h
0x18001cd1a  pop     rbx
0x18001cd1b  retn
```
