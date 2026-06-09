# OSIntegration::DEH::Internal::GetVirtualizationManagerDllFilename(ushort const * *)

- ea: `0x18015acd0`
- end: `0x18015ae04`
- name: `?GetVirtualizationManagerDllFilename@Internal@DEH@OSIntegration@@YAJPEAPEBG@Z`
- size: `308`
- prototype: `int(OSIntegration::DEH::Internal *__hidden this, const unsigned __int16 **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180152b98`
- `0x180152d8c`
- `0x180152fec`
- `0x1801533c0`

## callees

- `0x18006a4c8`
- `0x180075e2c`
- `0x1800762a8`
- `0x1800762cc`
- `0x18007c244`
- `0x180157ea0`
- `0x18015acd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18015ad20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18015ad20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18015ace7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18015ace7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015adc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015adc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015ad5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015ad5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18015add4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18015add4`

## string_xrefs

- `0x18015ad9d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18015ad92`: `OSIntegration::DEH::Internal::GetVirtualizationManagerDllFilename`
- `0x18015ada4`: `GetInprocServer32Properties(WhichHive::LocalMachine, __uuidof(PackagedInprocClassVirtualizationManager), &g_virtualizationManagerDllPath)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::GetVirtualizationManagerDllFilename(
        OSIntegration::DEH::Internal *this,
        const unsigned __int16 **a2)
{
  HKEY v4; // rdx
  __int64 v5; // rcx
  LPWSTR FileNameW; // rax
  HSTRING v7; // rbx
  int InprocServer32Properties; // eax
  unsigned int v9; // ebx
  const WCHAR *StringRawBuffer; // rax
  char *v11; // [rsp+28h] [rbp-10h]
  int v12; // [rsp+30h] [rbp-8h]
  wil::details::in1diag5 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v14; // [rsp+48h] [rbp+10h] BYREF
  RTL_SRWLOCK *v15; // [rsp+50h] [rbp+18h] BYREF

  AcquireSRWLockShared(&stru_180245BE8);
  v14 = &stru_180245BE8;
  if ( qword_180245BF0 )
  {
    *(_QWORD *)this = qword_180245BF0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
    return 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  AcquireSRWLockExclusive(&stru_180245BE8);
  FileNameW = (LPWSTR)qword_180245BF0;
  v15 = &stru_180245BE8;
  if ( qword_180245BF0 )
    goto LABEL_9;
  v7 = string;
  if ( string )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    WindowsDeleteString(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  string = 0;
  InprocServer32Properties = Com::Catalog::Win32Registry::GetInprocServer32Properties(v5, v4, &string);
  v9 = InprocServer32Properties;
  if ( InprocServer32Properties >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FileNameW = PathFindFileNameW(StringRawBuffer);
    qword_180245BF0 = (__int64)FileNameW;
LABEL_9:
    *(_QWORD *)this = FileNameW;
    v9 = 0;
    goto LABEL_10;
  }
  LODWORD(v11) = InprocServer32Properties;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x235,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
    "OSIntegration::DEH::Internal::GetVirtualizationManagerDllFilename",
    "GetInprocServer32Properties(WhichHive::LocalMachine, __uuidof(PackagedInprocClassVirtualizationManager), &g_virtuali"
    "zationManagerDllPath)",
    v11,
    v12);
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  return v9;
}

```

## disassembly

```asm
0x18015acd0  mov     [rsp+arg_0], rbx
0x18015acd5  push    rdi; int
0x18015acd6  sub     rsp, 30h
0x18015acda  mov     rdi, rcx
0x18015acdd  lea     rbx, stru_180245BE8
0x18015ace4  mov     rcx, rbx; SRWLock
0x18015ace7  call    cs:__imp_AcquireSRWLockShared
0x18015acee  nop     dword ptr [rax+rax+00h]
0x18015acf3  mov     rax, cs:qword_180245BF0
0x18015acfa  lea     rcx, [rsp+38h+arg_8]
0x18015acff  mov     [rsp+38h+arg_8], rbx
0x18015ad04  test    rax, rax
0x18015ad07  jz      short loc_18015AD18
0x18015ad09  mov     [rdi], rax
0x18015ad0c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18015ad11  xor     eax, eax
0x18015ad13  jmp     loc_18015ADF8
0x18015ad18  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18015ad1d  mov     rcx, rbx; SRWLock
0x18015ad20  call    cs:__imp_AcquireSRWLockExclusive
0x18015ad27  nop     dword ptr [rax+rax+00h]
0x18015ad2c  mov     rax, cs:qword_180245BF0
0x18015ad33  mov     [rsp+38h+arg_10], rbx
0x18015ad38  test    rax, rax
0x18015ad3b  jnz     loc_18015ADE7
0x18015ad41  mov     rbx, cs:string
0x18015ad48  test    rbx, rbx
0x18015ad4b  jz      short loc_18015AD70
0x18015ad4d  lea     rcx, [rsp+38h+arg_8]; this
0x18015ad52  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18015ad57  mov     rcx, rbx; string
0x18015ad5a  call    cs:__imp_WindowsDeleteString
0x18015ad61  nop     dword ptr [rax+rax+00h]
0x18015ad66  lea     rcx, [rsp+38h+arg_8]; this
0x18015ad6b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18015ad70  lea     r8, string
0x18015ad77  mov     cs:string, 0
0x18015ad82  call    ?GetInprocServer32Properties@Win32Registry@Catalog@Com@@YAJW4WhichHive@123@AEBU_GUID@@PEAPEAUHSTRING__@@PEAW4ThreadingModel@@@Z; Com::Catalog::Win32Registry::GetInprocServer32Properties(Com::Catalog::Win32Registry::WhichHive,_GUID const &,HSTRING__ * *,ThreadingModel *)
0x18015ad87  mov     ebx, eax
0x18015ad89  test    eax, eax
0x18015ad8b  jns     short loc_18015ADBC
0x18015ad8d  mov     rcx, [rsp+38h]; this
0x18015ad92  lea     r9, aOsintegrationD_175; "OSIntegration::DEH::Internal::GetVirtua"...
0x18015ad99  mov     dword ptr [rsp+38h+var_10], eax; char *
0x18015ad9d  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015ada4  lea     rax, aGetinprocserve; "GetInprocServer32Properties(WhichHive::"...
0x18015adab  mov     edx, 235h; void *
0x18015adb0  mov     [rsp+38h+var_18], rax; char *
0x18015adb5  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18015adba  jmp     short loc_18015ADEC
0x18015adbc  mov     rcx, cs:string; string
0x18015adc3  xor     edx, edx; length
0x18015adc5  call    cs:__imp_WindowsGetStringRawBuffer
0x18015adcc  nop     dword ptr [rax+rax+00h]
0x18015add1  mov     rcx, rax; pszPath
0x18015add4  call    cs:__imp_PathFindFileNameW
0x18015addb  nop     dword ptr [rax+rax+00h]
0x18015ade0  mov     cs:qword_180245BF0, rax
0x18015ade7  mov     [rdi], rax
0x18015adea  xor     ebx, ebx
0x18015adec  lea     rcx, [rsp+38h+arg_10]
0x18015adf1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18015adf6  mov     eax, ebx
0x18015adf8  mov     rbx, [rsp+38h+arg_0]
0x18015adfd  add     rsp, 30h
0x18015ae01  pop     rdi
0x18015ae02  retn
```
