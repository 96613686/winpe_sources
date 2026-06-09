# mutex::CreateUserBoundaryDescriptor(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180038750`
- end: `0x18003890d`
- name: `?CreateUserBoundaryDescriptor@mutex@@YAJPEAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteBoundaryDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(PSID RequiredSid, void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180038914`

## callees

- `0x180002214`
- `0x1800110fc`
- `0x18001c75c`
- `0x180038750`
- `0x18003916c`
- `0x18003923c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800388bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800388bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003878f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003878f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003882c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800388d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003882c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800388d8`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18003883e`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18003883e`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800387f1`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800387f1`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18003884c`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800388b4`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18003884c`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800388b4`

## string_xrefs

- `0x18003879d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038803`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038870`: `AddSIDToBoundaryDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall mutex::CreateUserBoundaryDescriptor(PSID RequiredSid, void *Src, void **a3)
{
  const char *v6; // r9
  unsigned int LastError; // ebx
  LPWSTR v8; // rbx
  __int64 v9; // rax
  const WCHAR *v10; // rcx
  const char *v11; // r9
  __int64 v12; // rdx
  signed int v13; // eax
  signed int v14; // ecx
  HANDLE v15; // r15
  void *v16; // rsi
  DWORD v17; // ebx
  __int64 v19; // [rsp+20h] [rbp-39h]
  _BYTE v21[32]; // [rsp+38h] [rbp-21h] BYREF
  HANDLE BoundaryDescriptor; // [rsp+58h] [rbp-1h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+7h] BYREF
  LPCWSTR Name[4]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  StringSid = 0;
  if ( !ConvertSidToStringSidW(RequiredSid, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x70,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
                  v6);
    goto LABEL_8;
  }
  v8 = StringSid;
  v9 = std::operator+<wchar_t>(v21, Src, L"_");
  std::operator+<wchar_t>(Name, v9, v8);
  std::wstring::~wstring(v21);
  v10 = (const WCHAR *)Name;
  if ( Name[3] > (LPCWSTR)7 )
    v10 = Name[0];
  BoundaryDescriptor = CreateBoundaryDescriptorW(v10, 0);
  if ( !BoundaryDescriptor )
  {
    v12 = 117;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
                  v11);
    std::wstring::~wstring(Name);
LABEL_8:
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_21;
  }
  if ( !AddSIDToBoundaryDescriptor(&BoundaryDescriptor, RequiredSid) )
  {
    DeleteBoundaryDescriptor(BoundaryDescriptor);
    v13 = GetLastError();
    v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      v14 = v13;
    if ( v14 >= 0 )
      v14 = -2147418113;
    LODWORD(v19) = v14;
    WUTrace(0, 0, 0x1000000, 3, v19, L"AddSIDToBoundaryDescriptor", Src);
    v12 = 123;
    goto LABEL_7;
  }
  v15 = BoundaryDescriptor;
  v16 = *a3;
  if ( *a3 )
  {
    v17 = GetLastError();
    DeleteBoundaryDescriptor(v16);
    SetLastError(v17);
  }
  *a3 = v15;
  std::wstring::~wstring(Name);
  if ( StringSid )
    LocalFree(StringSid);
  LastError = 0;
LABEL_21:
  std::wstring::~wstring(Src);
  return LastError;
}

```

## disassembly

```asm
0x180038750  mov     [rsp-8+arg_18], rbx
0x180038755  push    rbp
0x180038756  push    rsi
0x180038757  push    rdi
0x180038758  push    r14
0x18003875a  push    r15
0x18003875c  lea     rbp, [rsp-37h]
0x180038761  sub     rsp, 90h
0x180038768  mov     rax, cs:__security_cookie
0x18003876f  xor     rax, rsp
0x180038772  mov     [rbp+57h+var_28], rax
0x180038776  mov     r14, r8
0x180038779  mov     rdi, rdx
0x18003877c  mov     rsi, rcx
0x18003877f  mov     [rbp+57h+var_80], rdx
0x180038783  mov     [rbp+57h+StringSid], 0
0x18003878b  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18003878f  call    cs:__imp_ConvertSidToStringSidW
0x180038795  test    eax, eax
0x180038797  jnz     short loc_1800387B0
0x180038799  mov     rcx, [rbp+5Fh]; this
0x18003879d  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800387a4  lea     edx, [rax+70h]; void *
0x1800387a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800387ac  mov     ebx, eax
0x1800387ae  jmp     short loc_18003881F
0x1800387b0  mov     rbx, [rbp+57h+StringSid]
0x1800387b4  lea     r8, asc_18007B970; "_"
0x1800387bb  mov     rdx, rdi; Src
0x1800387be  lea     rcx, [rbp+57h+var_78]; void *
0x1800387c2  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x1800387c7  nop
0x1800387c8  mov     r8, rbx
0x1800387cb  mov     rdx, rax
0x1800387ce  lea     rcx, [rbp+57h+Name]
0x1800387d2  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800387d7  nop
0x1800387d8  lea     rcx, [rbp+57h+var_78]
0x1800387dc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800387e1  lea     rcx, [rbp+57h+Name]
0x1800387e5  cmp     [rbp+57h+var_30], 7
0x1800387ea  cmova   rcx, [rbp+57h+Name]; Name
0x1800387ef  xor     edx, edx; Flags
0x1800387f1  call    cs:__imp_CreateBoundaryDescriptorW
0x1800387f7  mov     [rbp+57h+BoundaryDescriptor], rax
0x1800387fb  test    rax, rax
0x1800387fe  jnz     short loc_180038837
0x180038800  lea     edx, [rax+75h]; void *
0x180038803  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003880a  mov     rcx, [rbp+5Fh]; this
0x18003880e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038813  mov     ebx, eax
0x180038815  lea     rcx, [rbp+57h+Name]
0x180038819  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003881e  nop
0x18003881f  mov     rcx, [rbp+57h+StringSid]; hMem
0x180038823  test    rcx, rcx
0x180038826  jz      loc_1800388E0
0x18003882c  call    cs:__imp_LocalFree
0x180038832  jmp     loc_1800388E0
0x180038837  mov     rdx, rsi; RequiredSid
0x18003883a  lea     rcx, [rbp+57h+BoundaryDescriptor]; BoundaryDescriptor
0x18003883e  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180038844  test    eax, eax
0x180038846  jnz     short loc_18003889D
0x180038848  mov     rcx, [rbp+57h+BoundaryDescriptor]; BoundaryDescriptor
0x18003884c  call    cs:__imp_DeleteBoundaryDescriptor
0x180038852  call    cs:__imp_GetLastError
0x180038858  movzx   ecx, ax
0x18003885b  or      ecx, 80070000h
0x180038861  test    eax, eax
0x180038863  cmovle  ecx, eax
0x180038866  mov     eax, 8000FFFFh
0x18003886b  test    ecx, ecx
0x18003886d  cmovns  ecx, eax
0x180038870  lea     rax, aAddsidtobounda_0; "AddSIDToBoundaryDescriptor"
0x180038877  mov     [rsp+0B0h+var_88], rax
0x18003887c  mov     dword ptr [rsp+0B0h+var_90], ecx
0x180038880  xor     edx, edx
0x180038882  xor     ecx, ecx
0x180038884  lea     r9d, [rdx+3]
0x180038888  mov     r8d, 1000000h
0x18003888e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180038893  mov     edx, 7Bh ; '{'
0x180038898  jmp     loc_180038803
0x18003889d  mov     r15, [rbp+57h+BoundaryDescriptor]
0x1800388a1  mov     rsi, [r14]
0x1800388a4  test    rsi, rsi
0x1800388a7  jz      short loc_1800388C2
0x1800388a9  call    cs:__imp_GetLastError
0x1800388af  mov     ebx, eax
0x1800388b1  mov     rcx, rsi; BoundaryDescriptor
0x1800388b4  call    cs:__imp_DeleteBoundaryDescriptor
0x1800388ba  mov     ecx, ebx; dwErrCode
0x1800388bc  call    cs:__imp_SetLastError
0x1800388c2  mov     [r14], r15
0x1800388c5  lea     rcx, [rbp+57h+Name]
0x1800388c9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800388ce  nop
0x1800388cf  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800388d3  test    rcx, rcx
0x1800388d6  jz      short loc_1800388DE
0x1800388d8  call    cs:__imp_LocalFree
0x1800388de  xor     ebx, ebx
0x1800388e0  mov     rcx, rdi
0x1800388e3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800388e8  mov     eax, ebx
0x1800388ea  mov     rcx, [rbp+57h+var_28]
0x1800388ee  xor     rcx, rsp; StackCookie
0x1800388f1  call    __security_check_cookie
0x1800388f6  mov     rbx, [rsp+0B0h+arg_18]
0x1800388fe  add     rsp, 90h
0x180038905  pop     r15
0x180038907  pop     r14
0x180038909  pop     rdi
0x18003890a  pop     rsi
0x18003890b  pop     rbp
0x18003890c  retn
```
