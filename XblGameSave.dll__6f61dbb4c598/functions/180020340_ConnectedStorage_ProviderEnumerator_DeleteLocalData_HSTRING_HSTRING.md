# ConnectedStorage::ProviderEnumerator::DeleteLocalData(HSTRING__ *,HSTRING__ *)

- ea: `0x180020340`
- end: `0x1800204a0`
- name: `?DeleteLocalData@ProviderEnumerator@ConnectedStorage@@MEAAJPEAUHSTRING__@@0@Z`
- size: `352`
- prototype: `int(ConnectedStorage::ProviderEnumerator *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011bd0`
- `0x180013e1c`
- `0x180014720`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001ff8c`
- `0x180020340`
- `0x1800235c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002041c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002041c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020457`

## string_xrefs

- `0x1800203ab`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ConnectedStorage::ProviderEnumerator::DeleteLocalData(
        ConnectedStorage::ProviderEnumerator *this,
        HSTRING a2,
        HSTRING a3)
{
  char *v5; // r8
  const unsigned __int16 *v6; // r8
  ConnectedStorage::Service *v7; // rbx
  __int64 v8; // rdx
  unsigned int v10; // [rsp+20h] [rbp-88h]
  HSTRING v11; // [rsp+28h] [rbp-80h] BYREF
  HSTRING newString; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string; // [rsp+38h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+40h] [rbp-68h] BYREF
  _DWORD v15[16]; // [rsp+50h] [rbp-58h] BYREF

  v10 = 0;
  try
  {
    ConnectedStorage::ProviderEnumerator::CheckCaller(this);
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v5);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v6);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v7 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a2);
    v8 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a3);
    ConnectedStorage::NormalizeScid(&v11, v8);
    WindowsDeleteString(string);
    string = 0;
    ConnectedStorage::Service::DeleteLocalStorageForContext(
      v7,
      (struct ConnectedStorage::SimpleHStringWrapper *)&newString,
      (struct ConnectedStorage::SimpleHStringWrapper *)&v11);
    WindowsDeleteString(v11);
    v11 = 0;
    WindowsDeleteString(newString);
    newString = 0;
    if ( v7 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v15 )
  {
    v10 = v15[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v15);
    return v10;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return v10;
}

```

## disassembly

```asm
0x180020340  mov     [rsp+arg_0], rbx
0x180020345  mov     [rsp+arg_18], rsi
0x18002034a  push    rdi
0x18002034b  sub     rsp, 0A0h
0x180020352  mov     rax, cs:__security_cookie
0x180020359  xor     rax, rsp
0x18002035c  mov     [rsp+0A8h+var_18], rax
0x180020364  mov     rsi, r8
0x180020367  mov     rdi, rdx
0x18002036a  mov     [rsp+0A8h+var_88], 0
0x180020372  call    ?CheckCaller@ProviderEnumerator@ConnectedStorage@@AEAAXXZ; ConnectedStorage::ProviderEnumerator::CheckCaller(void)
0x180020377  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x18002037e  jnz     short loc_1800203E1
0x180020380  or      edx, 0FFFFFFFFh; unsigned int
0x180020383  lea     rcx, qword_1800C0998; this
0x18002038a  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x18002038f  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180020396  lea     rcx, [rsp+0A8h+lpCriticalSection]; this
0x18002039b  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800203a0  nop
0x1800203a1  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x1800203a7  test    eax, eax
0x1800203a9  jnz     short loc_1800203BC
0x1800203ab  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x1800203b2  mov     ecx, 80004005h; this
0x1800203b7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800203bc  inc     eax
0x1800203be  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x1800203c4  mov     edx, 2
0x1800203c9  mov     rcx, cs:qword_1800C0858
0x1800203d0  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x1800203d5  nop
0x1800203d6  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x1800203db  call    cs:__imp_LeaveCriticalSection
0x1800203e1  mov     rbx, cs:qword_1800C0858
0x1800203e8  mov     [rsp+0A8h+lpCriticalSection], rbx
0x1800203ed  mov     rdx, rdi; string
0x1800203f0  lea     rcx, [rsp+0A8h+newString]; newString
0x1800203f5  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x1800203fa  nop
0x1800203fb  mov     rdx, rsi; string
0x1800203fe  lea     rcx, [rsp+0A8h+string]; newString
0x180020403  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180020408  nop
0x180020409  mov     rdx, rax
0x18002040c  lea     rcx, [rsp+0A8h+var_80]
0x180020411  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x180020416  nop
0x180020417  mov     rcx, [rsp+0A8h+string]; string
0x18002041c  call    cs:__imp_WindowsDeleteString
0x180020422  mov     [rsp+0A8h+string], 0
0x18002042b  lea     r8, [rsp+0A8h+var_80]; struct ConnectedStorage::SimpleHStringWrapper *
0x180020430  lea     rdx, [rsp+0A8h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x180020435  mov     rcx, rbx; this
0x180020438  call    ?DeleteLocalStorageForContext@Service@ConnectedStorage@@QEAAXAEAVSimpleHStringWrapper@2@0@Z; ConnectedStorage::Service::DeleteLocalStorageForContext(ConnectedStorage::SimpleHStringWrapper &,ConnectedStorage::SimpleHStringWrapper &)
0x18002043d  nop
0x18002043e  mov     rcx, [rsp+0A8h+var_80]; string
0x180020443  call    cs:__imp_WindowsDeleteString
0x180020449  mov     [rsp+0A8h+var_80], 0
0x180020452  mov     rcx, [rsp+0A8h+newString]; string
0x180020457  call    cs:__imp_WindowsDeleteString
0x18002045d  mov     [rsp+0A8h+newString], 0
0x180020466  test    rbx, rbx
0x180020469  jz      short loc_180020471
0x18002046b  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x180020470  nop
0x180020471  jmp     short loc_180020477
0x180020473  jmp     short loc_180020477
0x180020475  jmp     short $+2
0x180020477  mov     eax, [rsp+0A8h+var_88]
0x18002047b  mov     rcx, [rsp+0A8h+var_18]
0x180020483  xor     rcx, rsp; StackCookie
0x180020486  call    __security_check_cookie
0x18002048b  lea     r11, [rsp+0A8h+var_8]
0x180020493  mov     rbx, [r11+10h]
0x180020497  mov     rsi, [r11+28h]
0x18002049b  mov     rsp, r11
0x18002049e  pop     rdi
0x18002049f  retn
```
