# Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetAvailableXmlPath(HSTRING__ * *)

- ea: `0x1800613c0`
- end: `0x180061589`
- name: `?GetAvailableXmlPath@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *__hidden this, HSTRING *newString)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006245c`

## callees

- `0x1800181ec`
- `0x1800605bc`
- `0x180060e54`
- `0x1800613c0`
- `0x180061bc0`
- `0x180061e90`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006146e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800614f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006146e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800614f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800613f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006142c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800613f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006142c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006153c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006153c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180061556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180061556`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetAvailableXmlPath(
        Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *this,
        HSTRING *newString)
{
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v4; // rcx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v7; // rcx
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v8; // rcx
  bool v10; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v13; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  *newString = 0;
  WindowsDeleteString(0);
  string = 0;
  v10 = 0;
  if ( Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetVariantXmlFilePath(this, &string) >= 0 )
  {
    Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(v4, string, &v10);
    if ( v10 )
      goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  length[0] = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( aCProgramsComms[v6] );
  if ( (int)ULongLongToUInt(v6, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(L"C:\\Programs\\CommsApplications\\", length[0], &hstringHeader, &v13);
  if ( Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlFilePath(this, v13, &string) >= 0 )
  {
    Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(v7, string, &v10);
    if ( v10 )
      goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  length[0] = 0;
  do
    ++v5;
  while ( aCWindowsSystem[v5] );
  if ( (int)ULongLongToUInt(v5, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(L"C:\\Windows\\System32\\", length[0], &hstringHeader, &v13);
  if ( Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlFilePath(this, v13, &string) >= 0 )
  {
    Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(v8, string, &v10);
    if ( v10 )
    {
LABEL_15:
      *(_QWORD *)length = WindowsGetStringRawBuffer(string, 0);
      SyncPartnershipApiTelemetry::OemFileIsBeingUsed<unsigned short const * &>(length);
      WindowsDuplicateString(string, newString);
    }
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800613c0  mov     [rsp-28h+arg_10], rbx
0x1800613c5  push    rbp
0x1800613c6  push    rsi
0x1800613c7  push    rdi
0x1800613c8  push    r14
0x1800613ca  push    r15
0x1800613cc  mov     rbp, rsp
0x1800613cf  sub     rsp, 60h
0x1800613d3  mov     rax, cs:__security_cookie
0x1800613da  xor     rax, rsp
0x1800613dd  mov     [rbp+var_8], rax
0x1800613e1  mov     r14, rdx
0x1800613e4  mov     rsi, rcx
0x1800613e7  xor     r15d, r15d
0x1800613ea  mov     [rdx], r15
0x1800613ed  mov     [rbp+string], r15
0x1800613f1  xor     ecx, ecx; string
0x1800613f3  call    cs:__imp_WindowsDeleteString
0x1800613f9  mov     [rbp+string], r15
0x1800613fd  lea     rdx, [rbp+string]; HSTRING *
0x180061401  mov     rcx, rsi; this
0x180061404  call    ?GetVariantXmlFilePath@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetVariantXmlFilePath(HSTRING__ * *)
0x180061409  mov     [rbp+var_40], r15b
0x18006140d  test    eax, eax
0x18006140f  js      short loc_180061428
0x180061411  lea     r8, [rbp+var_40]; bool *
0x180061415  mov     rdx, [rbp+string]; HSTRING
0x180061419  call    ?DoesFileExist@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEA_N@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(HSTRING__ *,bool *)
0x18006141e  cmp     [rbp+var_40], r15b
0x180061422  jnz     loc_180061536
0x180061428  mov     rcx, [rbp+string]; string
0x18006142c  call    cs:__imp_WindowsDeleteString
0x180061432  mov     [rbp+string], r15
0x180061436  mov     rdi, cs:off_1800890A0; "C:\\Programs\\CommsApplications\\"
0x18006143d  mov     [rbp+length], r15d
0x180061441  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180061445  mov     rcx, rbx
0x180061448  inc     rcx; unsigned __int64
0x18006144b  cmp     [rdi+rcx*2], r15w
0x180061450  jnz     short loc_180061448
0x180061452  lea     rdx, [rbp+length]; unsigned int *
0x180061456  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18006145b  test    eax, eax
0x18006145d  jns     short loc_180061474
0x18006145f  xor     r9d, r9d; lpArguments
0x180061462  xor     r8d, r8d; nNumberOfArguments
0x180061465  lea     edx, [r9+1]; dwExceptionFlags
0x180061469  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006146e  call    cs:__imp_RaiseException
0x180061474  lea     r9, [rbp+var_28]; string
0x180061478  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006147c  mov     edx, [rbp+length]; length
0x18006147f  mov     rcx, rdi; sourceString
0x180061482  call    cs:__imp_WindowsCreateStringReference
0x180061488  lea     r8, [rbp+string]; HSTRING *
0x18006148c  mov     rdx, [rbp+var_28]; HSTRING
0x180061490  mov     rcx, rsi; this
0x180061493  call    ?GetXmlFilePath@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlFilePath(HSTRING__ *,HSTRING__ * *)
0x180061498  test    eax, eax
0x18006149a  js      short loc_1800614B3
0x18006149c  lea     r8, [rbp+var_40]; bool *
0x1800614a0  mov     rdx, [rbp+string]; HSTRING
0x1800614a4  call    ?DoesFileExist@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEA_N@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(HSTRING__ *,bool *)
0x1800614a9  cmp     [rbp+var_40], r15b
0x1800614ad  jnz     loc_180061536
0x1800614b3  mov     rcx, [rbp+string]; string
0x1800614b7  call    cs:__imp_WindowsDeleteString
0x1800614bd  mov     [rbp+string], r15
0x1800614c1  mov     rdi, cs:off_1800890A8; "C:\\Windows\\System32\\"
0x1800614c8  mov     [rbp+length], r15d
0x1800614cc  inc     rbx
0x1800614cf  cmp     [rdi+rbx*2], r15w
0x1800614d4  jnz     short loc_1800614CC
0x1800614d6  lea     rdx, [rbp+length]; unsigned int *
0x1800614da  mov     rcx, rbx; unsigned __int64
0x1800614dd  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800614e2  test    eax, eax
0x1800614e4  jns     short loc_1800614FB
0x1800614e6  xor     r9d, r9d; lpArguments
0x1800614e9  xor     r8d, r8d; nNumberOfArguments
0x1800614ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800614f0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800614f5  call    cs:__imp_RaiseException
0x1800614fb  lea     r9, [rbp+var_28]; string
0x1800614ff  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180061503  mov     edx, [rbp+length]; length
0x180061506  mov     rcx, rdi; sourceString
0x180061509  call    cs:__imp_WindowsCreateStringReference
0x18006150f  lea     r8, [rbp+string]; HSTRING *
0x180061513  mov     rdx, [rbp+var_28]; HSTRING
0x180061517  mov     rcx, rsi; this
0x18006151a  call    ?GetXmlFilePath@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlFilePath(HSTRING__ *,HSTRING__ * *)
0x18006151f  test    eax, eax
0x180061521  js      short loc_18006155D
0x180061523  lea     r8, [rbp+var_40]; bool *
0x180061527  mov     rdx, [rbp+string]; HSTRING
0x18006152b  call    ?DoesFileExist@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEA_N@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::DoesFileExist(HSTRING__ *,bool *)
0x180061530  cmp     [rbp+var_40], r15b
0x180061534  jz      short loc_18006155D
0x180061536  xor     edx, edx; length
0x180061538  mov     rcx, [rbp+string]; string
0x18006153c  call    cs:__imp_WindowsGetStringRawBuffer
0x180061542  mov     qword ptr [rbp+length], rax
0x180061546  lea     rcx, [rbp+length]
0x18006154a  call    ??$OemFileIsBeingUsed@AEAPEBG@SyncPartnershipApiTelemetry@@SAXAEAPEBG@Z; SyncPartnershipApiTelemetry::OemFileIsBeingUsed<ushort const * &>(ushort const * &)
0x18006154f  mov     rdx, r14; newString
0x180061552  mov     rcx, [rbp+string]; string
0x180061556  call    cs:__imp_WindowsDuplicateString
0x18006155c  nop
0x18006155d  mov     rcx, [rbp+string]; string
0x180061561  call    cs:__imp_WindowsDeleteString
0x180061567  xor     eax, eax
0x180061569  mov     rcx, [rbp+var_8]
0x18006156d  xor     rcx, rsp; StackCookie
0x180061570  call    __security_check_cookie
0x180061575  mov     rbx, [rsp+60h+arg_10]
0x18006157d  add     rsp, 60h
0x180061581  pop     r15
0x180061583  pop     r14
0x180061585  pop     rdi
0x180061586  pop     rsi
0x180061587  pop     rbp
0x180061588  retn
```
