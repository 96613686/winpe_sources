# HNS::Service::Core::StorageManager::InitializeDatabase(void)

- ea: `0x1800b368c`
- end: `0x1800b3871`
- name: `?InitializeDatabase@StorageManager@Core@Service@HNS@@AEAAXXZ`
- size: `485`
- prototype: `void __fastcall(HNS::Service::Core::StorageManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b3950`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800666b4`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x18007dc48`
- `0x18007df4c`
- `0x18008c6c0`
- `0x1800b368c`
- `0x1801a1080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b383f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b383f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b374f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b374f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b36e6`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b3719`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b36e6`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b3719`

## string_xrefs

- `0x1800b37fb`: `onecore\vm\dv\net\hns\service\core\storagemanager.cpp`
- `0x1800b382d`: `onecore\vm\dv\net\hns\service\core\storagemanager.cpp`
- `0x1800b385f`: `onecore\vm\dv\net\hns\service\core\storagemanager.cpp`
- `0x1800b36df`: `ProgramData`
- `0x1800b3712`: `ProgramData`
- `0x1800b36b4`: `HNS::Service::Core::StorageManager::InitializeDatabase`
- `0x1800b37b6`: `HNS::Service::Core::StorageManager::InitializeDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HNS::Service::Core::StorageManager::InitializeDatabase(HNS::Service::Core::StorageManager *this)
{
  DWORD EnvironmentVariableW; // ebx
  WCHAR *v3; // rdx
  DWORD v4; // eax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rdx
  int v7; // eax
  unsigned int v8; // eax
  signed int LastError; // eax
  unsigned int v10; // eax
  signed int v11; // eax
  unsigned int v12; // eax
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-40h] BYREF
  __m128i si128; // [rsp+30h] [rbp-30h]
  _DWORD v15[6]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  HNSTraceProvider::TraceEnter("HNS::Service::Core::StorageManager::InitializeDatabase", 0x46u);
  *(_OWORD *)lpBuffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpBuffer[0]) = 0;
  EnvironmentVariableW = GetEnvironmentVariableW(L"ProgramData", 0, 0);
  if ( !EnvironmentVariableW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = wil::verify_hresult<long>((unsigned int)LastError);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\storagemanager.cpp",
      (const char *)v10,
      (int)lpBuffer[0]);
  }
  std::wstring::resize(lpBuffer);
  v3 = (WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v3 = lpBuffer[0];
  v4 = GetEnvironmentVariableW(L"ProgramData", v3, EnvironmentVariableW);
  if ( !v4 )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v12 = wil::verify_hresult<long>((unsigned int)v11);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\storagemanager.cpp",
      (const char *)v12,
      (int)lpBuffer[0]);
  }
  if ( v4 >= EnvironmentVariableW )
  {
    v8 = wil::verify_hresult<long>(2147500037LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\storagemanager.cpp",
      (const char *)v8,
      (int)lpBuffer[0]);
  }
  std::wstring::append(lpBuffer, L"\\Microsoft\\Windows\\HNS");
  v5 = (const WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = lpBuffer[0];
  CreateDirectoryW(v5, 0);
  std::wstring::append(lpBuffer, L"\\");
  std::wstring::append(lpBuffer, L"HNS.data");
  v6 = (const WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = lpBuffer[0];
  v7 = HNSObjectStorage::Initialize((HNS::Service::Core::StorageManager *)((char *)this + 104), v6);
  if ( v7 < 0 )
  {
    v15[0] = v7;
    v15[4] = 4;
    v15[5] = 4;
    EventWrite(&HNS_DATA_LOAD_FAILED_EVENT, (struct HNSEventType *)v15, 0);
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Core::StorageManager::InitializeDatabase", 0x5Fu);
  std::wstring::~wstring(lpBuffer);
}

```

## disassembly

```asm
0x1800b368c  mov     [rsp-8+arg_8], rbx
0x1800b3691  mov     [rsp-8+arg_10], rdi
0x1800b3696  push    rbp
0x1800b3697  mov     rbp, rsp
0x1800b369a  sub     rsp, 60h
0x1800b369e  mov     rax, cs:__security_cookie
0x1800b36a5  xor     rax, rsp
0x1800b36a8  mov     [rbp+var_8], rax
0x1800b36ac  mov     rdi, rcx
0x1800b36af  mov     edx, 46h ; 'F'; unsigned int
0x1800b36b4  lea     rcx, aHnsServiceCore_61; "HNS::Service::Core::StorageManager::Ini"...
0x1800b36bb  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800b36c0  xorps   xmm0, xmm0
0x1800b36c3  movups  xmmword ptr [rbp+lpBuffer], xmm0
0x1800b36c7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800b36cf  movdqu  [rbp+var_30], xmm1
0x1800b36d4  xor     eax, eax
0x1800b36d6  mov     word ptr [rbp+lpBuffer], ax
0x1800b36da  xor     r8d, r8d; nSize
0x1800b36dd  xor     edx, edx; lpBuffer
0x1800b36df  lea     rcx, Name; "ProgramData"
0x1800b36e6  call    cs:__imp_GetEnvironmentVariableW
0x1800b36ec  mov     ebx, eax
0x1800b36ee  test    eax, eax
0x1800b36f0  jz      loc_1800B380D
0x1800b36f6  mov     edx, ebx
0x1800b36f8  lea     rcx, [rbp+lpBuffer]; Src
0x1800b36fc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b3701  lea     rdx, [rbp+lpBuffer]
0x1800b3705  cmp     qword ptr [rbp+var_30+8], 7
0x1800b370a  cmova   rdx, [rbp+lpBuffer]; lpBuffer
0x1800b370f  mov     r8d, ebx; nSize
0x1800b3712  lea     rcx, Name; "ProgramData"
0x1800b3719  call    cs:__imp_GetEnvironmentVariableW
0x1800b371f  test    eax, eax
0x1800b3721  jz      loc_1800B383F
0x1800b3727  cmp     eax, ebx
0x1800b3729  jnb     loc_1800B37EA
0x1800b372f  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\HNS"
0x1800b3736  lea     rcx, [rbp+lpBuffer]; Src
0x1800b373a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b373f  lea     rcx, [rbp+lpBuffer]
0x1800b3743  cmp     qword ptr [rbp+var_30+8], 7
0x1800b3748  cmova   rcx, [rbp+lpBuffer]; lpPathName
0x1800b374d  xor     edx, edx; lpSecurityAttributes
0x1800b374f  call    cs:__imp_CreateDirectoryW
0x1800b3755  lea     rdx, asc_1802E2688; "\\"
0x1800b375c  lea     rcx, [rbp+lpBuffer]; Src
0x1800b3760  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b3765  lea     rdx, aHnsData; "HNS.data"
0x1800b376c  lea     rcx, [rbp+lpBuffer]; Src
0x1800b3770  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b3775  lea     rdx, [rbp+lpBuffer]
0x1800b3779  cmp     qword ptr [rbp+var_30+8], 7
0x1800b377e  cmova   rdx, [rbp+lpBuffer]; lpFileName
0x1800b3783  lea     rcx, [rdi+68h]; this
0x1800b3787  call    ?Initialize@HNSObjectStorage@@QEAAJPEBG@Z; HNSObjectStorage::Initialize(ushort const *)
0x1800b378c  test    eax, eax
0x1800b378e  jns     short loc_1800B37B1
0x1800b3790  mov     [rbp+var_20], eax
0x1800b3793  mov     eax, 4
0x1800b3798  mov     [rbp+var_10], eax
0x1800b379b  mov     [rbp+var_C], eax
0x1800b379e  xor     r8d, r8d
0x1800b37a1  lea     rdx, [rbp+var_20]; this
0x1800b37a5  lea     rcx, HNS_DATA_LOAD_FAILED_EVENT; EventDescriptor
0x1800b37ac  call    ?EventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVHNSEventType@@ZZ; EventWrite(_EVENT_DESCRIPTOR const *,HNSEventType *,...)
0x1800b37b1  mov     edx, 5Fh ; '_'; unsigned int
0x1800b37b6  lea     rcx, aHnsServiceCore_61; "HNS::Service::Core::StorageManager::Ini"...
0x1800b37bd  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800b37c2  nop
0x1800b37c3  lea     rcx, [rbp+lpBuffer]; void *
0x1800b37c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b37cc  mov     rcx, [rbp+var_8]
0x1800b37d0  xor     rcx, rsp; StackCookie
0x1800b37d3  call    __security_check_cookie
0x1800b37d8  lea     r11, [rsp+60h+var_s0]
0x1800b37dd  mov     rbx, [r11+18h]
0x1800b37e1  mov     rdi, [r11+20h]
0x1800b37e5  mov     rsp, r11
0x1800b37e8  pop     rbp
0x1800b37e9  retn
0x1800b37ea  mov     ecx, 80004005h
0x1800b37ef  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800b37f4  mov     r9d, eax; char *
0x1800b37f7  mov     rcx, [rbp+8]; this
0x1800b37fb  lea     r8, aOnecoreVmDvNet_66; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800b3802  mov     edx, 2Fh ; '/'; void *
0x1800b3807  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b380d  call    cs:__imp_GetLastError
0x1800b3813  test    eax, eax
0x1800b3815  jle     short loc_1800B381F
0x1800b3817  movzx   eax, ax
0x1800b381a  or      eax, 80070000h
0x1800b381f  mov     ecx, eax
0x1800b3821  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800b3826  mov     r9d, eax; char *
0x1800b3829  mov     rcx, [rbp+8]; this
0x1800b382d  lea     r8, aOnecoreVmDvNet_66; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800b3834  mov     edx, 23h ; '#'; void *
0x1800b3839  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b383f  call    cs:__imp_GetLastError
0x1800b3845  test    eax, eax
0x1800b3847  jle     short loc_1800B3851
0x1800b3849  movzx   eax, ax
0x1800b384c  or      eax, 80070000h
0x1800b3851  mov     ecx, eax
0x1800b3853  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800b3858  mov     r9d, eax; char *
0x1800b385b  mov     rcx, [rbp+8]; this
0x1800b385f  lea     r8, aOnecoreVmDvNet_66; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800b3866  mov     edx, 2Ah ; '*'; void *
0x1800b386b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
