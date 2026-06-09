# ConnectedStorage::StorageService::RegisterProvider(HSTRING__ *,IStorageUIProvider *)

- ea: `0x180024cc0`
- end: `0x180024e1a`
- name: `?RegisterProvider@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@PEAUIStorageUIProvider@@@Z`
- size: `346`
- prototype: `int(ConnectedStorage::StorageService *__hidden this, HSTRING, struct IStorageUIProvider *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011bd0`
- `0x180013e1c`
- `0x180014a88`
- `0x1800160c8`
- `0x1800170d4`
- `0x180024cc0`
- `0x1800345d8`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024d56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024dcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024d56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024dd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024dd7`
- `ntdll!RtlIsMultiSessionSku` at `0x180024d6a`
- `ntdll!RtlIsMultiSessionSku` at `0x180024d6a`

## string_xrefs

- `0x180024d26`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ConnectedStorage::StorageService::RegisterProvider(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        struct IStorageUIProvider *a3)
{
  char *v6; // r8
  const unsigned __int16 *v7; // r8
  struct ConnectedStorage::Mutex *v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rdx
  char *v11; // r8
  char *v12; // r8
  const unsigned __int16 *v13; // r8
  _BYTE *v14; // rdx
  _BYTE v16[32]; // [rsp+0h] [rbp-C8h] BYREF
  ConnectedStorage *v17; // [rsp+20h] [rbp-A8h]
  HSTRING string; // [rsp+28h] [rbp-A0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-98h] BYREF
  LPCRITICAL_SECTION v20[2]; // [rsp+40h] [rbp-88h] BYREF
  _DWORD v21[16]; // [rsp+50h] [rbp-78h] BYREF

  try
  {
    LODWORD(v17) = 0;
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v6);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v7);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v8 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    v9 = 0;
    if ( (unsigned __int8)RtlIsMultiSessionSku() )
      v9 = *((_DWORD *)ConnectedStorage::CallerInfoWithResult::Get(
                         (ConnectedStorage::StorageService *)((char *)this + 64),
                         v10,
                         v11)
           + 6);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a2);
    ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)v20, (struct _RTL_CRITICAL_SECTION *)v8, v12);
    if ( !a3 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004003LL, (int)L"RegisterUIProvider: provider", v13);
    ConnectedStorage::Contexts::RegisterUIProvider(
      *((ConnectedStorage::Contexts **)v8 + 12),
      v9,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&string,
      a3);
    LeaveCriticalSection(v20[0]);
    WindowsDeleteString(string);
    string = 0;
    ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v21 )
  {
    LODWORD(v17) = v21[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v21);
    return ConnectedStorage::FilterHresult((ConnectedStorage *)(unsigned int)v17, (int)v14);
  }
  catch ( std::bad_alloc )
  {
    v14 = v16;
    LODWORD(v17) = -2147024882;
    return ConnectedStorage::FilterHresult((ConnectedStorage *)(unsigned int)v17, (int)v14);
  }
  catch ( ... )
  {
    v14 = v16;
    LODWORD(v17) = -2147467259;
  }
  return ConnectedStorage::FilterHresult((ConnectedStorage *)(unsigned int)v17, (int)v14);
}

```

## disassembly

```asm
0x180024cc0  push    rbx
0x180024cc2  push    rsi
0x180024cc3  push    rdi
0x180024cc4  push    r14
0x180024cc6  push    r15
0x180024cc8  sub     rsp, 0A0h
0x180024ccf  mov     rax, cs:__security_cookie
0x180024cd6  xor     rax, rsp
0x180024cd9  mov     [rsp+0C8h+var_38], rax
0x180024ce1  mov     rsi, r8
0x180024ce4  mov     r15, rdx
0x180024ce7  mov     r14, rcx
0x180024cea  mov     dword ptr [rsp+0C8h+var_A8], 0
0x180024cf2  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x180024cf9  jnz     short loc_180024D5C
0x180024cfb  or      edx, 0FFFFFFFFh; unsigned int
0x180024cfe  lea     rcx, qword_1800C0998; this
0x180024d05  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180024d0a  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180024d11  lea     rcx, [rsp+0C8h+lpCriticalSection]; this
0x180024d16  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180024d1b  nop
0x180024d1c  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180024d22  test    eax, eax
0x180024d24  jnz     short loc_180024D37
0x180024d26  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180024d2d  mov     ecx, 80004005h; this
0x180024d32  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180024d37  inc     eax
0x180024d39  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180024d3f  mov     edx, 2
0x180024d44  mov     rcx, cs:qword_1800C0858
0x180024d4b  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180024d50  nop
0x180024d51  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x180024d56  call    cs:__imp_LeaveCriticalSection
0x180024d5c  mov     rbx, cs:qword_1800C0858
0x180024d63  mov     [rsp+0C8h+lpCriticalSection], rbx
0x180024d68  xor     edi, edi
0x180024d6a  call    cs:__imp_RtlIsMultiSessionSku
0x180024d70  test    al, al
0x180024d72  jz      short loc_180024D80
0x180024d74  lea     rcx, [r14+40h]; this
0x180024d78  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180024d7d  mov     edi, [rax+18h]
0x180024d80  mov     rdx, r15; string
0x180024d83  lea     rcx, [rsp+0C8h+string]; newString
0x180024d88  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180024d8d  nop
0x180024d8e  mov     rdx, rbx; struct ConnectedStorage::Mutex *
0x180024d91  lea     rcx, [rsp+0C8h+var_88]; this
0x180024d96  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180024d9b  nop
0x180024d9c  test    rsi, rsi
0x180024d9f  jnz     short loc_180024DB2
0x180024da1  lea     rdx, aRegisteruiprov; "RegisterUIProvider: provider"
0x180024da8  mov     ecx, 80004003h; this
0x180024dad  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180024db2  mov     r9, rsi; struct IStorageUIProvider *
0x180024db5  lea     r8, [rsp+0C8h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x180024dba  mov     edx, edi; unsigned int
0x180024dbc  mov     rcx, [rbx+60h]; this
0x180024dc0  call    ?RegisterUIProvider@Contexts@ConnectedStorage@@QEAAXIAEBVSimpleHStringWrapper@2@PEAUIStorageUIProvider@@@Z; ConnectedStorage::Contexts::RegisterUIProvider(uint,ConnectedStorage::SimpleHStringWrapper const &,IStorageUIProvider *)
0x180024dc5  nop
0x180024dc6  mov     rcx, [rsp+0C8h+var_88]; lpCriticalSection
0x180024dcb  call    cs:__imp_LeaveCriticalSection
0x180024dd1  nop
0x180024dd2  mov     rcx, [rsp+0C8h+string]; string
0x180024dd7  call    cs:__imp_WindowsDeleteString
0x180024ddd  mov     [rsp+0C8h+string], 0
0x180024de6  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x180024deb  nop
0x180024dec  jmp     short loc_180024DF2
0x180024dee  jmp     short loc_180024DF2
0x180024df0  jmp     short $+2
0x180024df2  mov     ecx, dword ptr [rsp+0C8h+var_A8]; this
0x180024df6  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x180024dfb  mov     rcx, [rsp+0C8h+var_38]
0x180024e03  xor     rcx, rsp; StackCookie
0x180024e06  call    __security_check_cookie
0x180024e0b  add     rsp, 0A0h
0x180024e12  pop     r15
0x180024e14  pop     r14
0x180024e16  pop     rdi
0x180024e17  pop     rsi
0x180024e18  pop     rbx
0x180024e19  retn
```
