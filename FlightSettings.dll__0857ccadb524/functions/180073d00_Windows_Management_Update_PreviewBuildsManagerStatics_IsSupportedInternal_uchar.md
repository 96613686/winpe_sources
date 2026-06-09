# Windows::Management::Update::PreviewBuildsManagerStatics::IsSupportedInternal(uchar *)

- ea: `0x180073d00`
- end: `0x180073ecc`
- name: `?IsSupportedInternal@PreviewBuildsManagerStatics@Update@Management@Windows@@CAJPEAE@Z`
- size: `460`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180073b80`
- `0x180073cf0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180017870`
- `0x1800466b0`
- `0x180073d00`
- `0x1800888f8`
- `0x180088a48`
- `0x1800944d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073de2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073e39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073e23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073e23`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180073d7c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180073d7c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180073e41`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180073e41`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180073def`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180073def`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180073e81`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180073e81`

## string_xrefs

- `0x180073d20`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerstatics.cpp`
- `0x180073e02`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerstatics.cpp`
- `0x180073e4f`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerstatics.cpp`
- `0x180073e92`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Management::Update::PreviewBuildsManagerStatics::IsSupportedInternal(bool *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  bool v4; // bl
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HRESULT v8; // eax
  HANDLE v9; // rax
  BOOL v10; // ebx
  const char *v11; // r9
  int v12; // eax
  bool v13; // al
  int v14[40]; // [rsp+20h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  char v16; // [rsp+D0h] [rbp+67h] BYREF
  int v17; // [rsp+D8h] [rbp+6Fh] BYREF
  void *TokenHandle; // [rsp+E0h] [rbp+77h] BYREF

  if ( a1 )
  {
    *a1 = 0;
    OneSettingsQuery::OneSettingsQuery((OneSettingsQuery *)v14);
    v4 = (int)OneSettingsQuery::Initialize((OneSettingsQuery *)v14, 1) >= 0 && v14[10] != 0;
    OneSettingsQuery::~OneSettingsQuery((OneSettingsQuery *)v14);
    if ( !v4 )
    {
      v17 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v17, 0);
      if ( v17 >= 32 )
      {
        v2 = -2147418113;
        v3 = 51;
        goto LABEL_3;
      }
      if ( (unsigned int)(v17 - 7) > 1 )
      {
        *a1 = 0;
        return 1;
      }
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError != 1008 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_22;
      }
      v8 = CoImpersonateClient();
      v2 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerstatics.cpp",
          (const char *)(unsigned int)v8,
          v14[0]);
LABEL_24:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return v2;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      v9 = GetCurrentThread();
      v10 = OpenThreadToken(v9, 8u, 1, &TokenHandle);
      CoRevertToSelf();
      if ( !v10 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x5B,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previe"
                                    "wbuildsmanagerstatics.cpp",
                      v11);
LABEL_22:
        v2 = LastError;
        goto LABEL_24;
      }
    }
    v16 = 0;
    v12 = CapabilityCheck(TokenHandle, L"systemManagement", &v16);
    if ( v12 >= 0 )
    {
      v13 = v16 == 1;
      *a1 = v16 == 1;
      v2 = !v13;
      goto LABEL_24;
    }
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x67,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbui"
                                "ldsmanagerstatics.cpp",
                  (const char *)(unsigned int)v12,
                  v14[0]);
    goto LABEL_22;
  }
  v2 = -2147024809;
  v3 = 40;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerstatics.cpp",
    (const char *)v2,
    v14[0]);
  return v2;
}

```

## disassembly

```asm
0x180073d00  push    rbp
0x180073d02  push    rbx
0x180073d03  push    rdi
0x180073d04  lea     rbp, [rsp-47h]
0x180073d09  sub     rsp, 0B0h
0x180073d10  mov     rdi, rcx
0x180073d13  test    rcx, rcx
0x180073d16  jnz     short loc_180073D38
0x180073d18  mov     ebx, 80070057h
0x180073d1d  lea     edx, [rcx+28h]; void *
0x180073d20  lea     r8, aOnecoreBaseFli_58; "onecore\\base\\flighting\\flightsetting"...
0x180073d27  mov     r9d, ebx; char *
0x180073d2a  mov     rcx, [rbp+5Fh]; this
0x180073d2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073d33  jmp     loc_180073EBF
0x180073d38  mov     byte ptr [rcx], 0
0x180073d3b  lea     rcx, [rbp+57h+var_A0]; this
0x180073d3f  call    ??0OneSettingsQuery@@QEAA@XZ; OneSettingsQuery::OneSettingsQuery(void)
0x180073d44  nop
0x180073d45  mov     dl, 1; bool
0x180073d47  lea     rcx, [rbp+57h+var_A0]; this
0x180073d4b  call    ?Initialize@OneSettingsQuery@@QEAAJ_N@Z; OneSettingsQuery::Initialize(bool)
0x180073d50  test    eax, eax
0x180073d52  jns     short loc_180073D58
0x180073d54  xor     bl, bl
0x180073d56  jmp     short loc_180073D5F
0x180073d58  cmp     [rbp+57h+var_78], 0
0x180073d5c  setnbe  bl
0x180073d5f  lea     rcx, [rbp+57h+var_A0]; this
0x180073d63  call    ??1OneSettingsQuery@@QEAA@XZ; OneSettingsQuery::~OneSettingsQuery(void)
0x180073d68  test    bl, bl
0x180073d6a  jnz     short loc_180073DAB
0x180073d6c  mov     [rbp+57h+arg_8], 0
0x180073d73  xor     r8d, r8d
0x180073d76  lea     rdx, [rbp+57h+arg_8]
0x180073d7a  xor     ecx, ecx
0x180073d7c  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180073d82  mov     ecx, [rbp+57h+arg_8]
0x180073d85  cmp     ecx, 20h ; ' '
0x180073d88  jl      short loc_180073D96
0x180073d8a  mov     ebx, 8000FFFFh
0x180073d8f  mov     edx, 33h ; '3'
0x180073d94  jmp     short loc_180073D20
0x180073d96  add     ecx, 0FFFFFFF9h
0x180073d99  cmp     ecx, 1
0x180073d9c  jbe     short loc_180073DAB
0x180073d9e  mov     byte ptr [rdi], 0
0x180073da1  mov     eax, 1
0x180073da6  jmp     loc_180073EC1
0x180073dab  mov     [rbp+57h+TokenHandle], 0
0x180073db3  xor     edx, edx
0x180073db5  lea     rcx, [rbp+57h+TokenHandle]
0x180073db9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180073dbe  call    cs:__imp_GetCurrentThread
0x180073dc4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180073dc8  mov     edx, 8; DesiredAccess
0x180073dcd  lea     r8d, [rdx-7]; OpenAsSelf
0x180073dd1  mov     rcx, rax; ThreadHandle
0x180073dd4  call    cs:__imp_OpenThreadToken
0x180073dda  test    eax, eax
0x180073ddc  jnz     loc_180073E6E
0x180073de2  call    cs:__imp_GetLastError
0x180073de8  cmp     eax, 3F0h
0x180073ded  jnz     short loc_180073E60
0x180073def  call    cs:__imp_CoImpersonateClient
0x180073df5  mov     ebx, eax
0x180073df7  test    eax, eax
0x180073df9  jns     short loc_180073E18
0x180073dfb  mov     rcx, [rbp+5Fh]; this
0x180073dff  mov     r9d, eax; char *
0x180073e02  lea     r8, aOnecoreBaseFli_58; "onecore\\base\\flighting\\flightsetting"...
0x180073e09  mov     edx, 4Eh ; 'N'; void *
0x180073e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073e13  jmp     loc_180073EB6
0x180073e18  xor     edx, edx
0x180073e1a  lea     rcx, [rbp+57h+TokenHandle]
0x180073e1e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180073e23  call    cs:__imp_GetCurrentThread
0x180073e29  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180073e2d  mov     edx, 8; DesiredAccess
0x180073e32  lea     r8d, [rdx-7]; OpenAsSelf
0x180073e36  mov     rcx, rax; ThreadHandle
0x180073e39  call    cs:__imp_OpenThreadToken
0x180073e3f  mov     ebx, eax
0x180073e41  call    cs:__imp_CoRevertToSelf
0x180073e47  test    ebx, ebx
0x180073e49  jnz     short loc_180073E6E
0x180073e4b  mov     rcx, [rbp+5Fh]; this
0x180073e4f  lea     r8, aOnecoreBaseFli_58; "onecore\\base\\flighting\\flightsetting"...
0x180073e56  lea     edx, [rbx+5Bh]; void *
0x180073e59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073e5e  jmp     short loc_180073EA3
0x180073e60  test    eax, eax
0x180073e62  jle     short loc_180073EA3
0x180073e64  movzx   eax, ax
0x180073e67  or      eax, 80070000h
0x180073e6c  jmp     short loc_180073EA3
0x180073e6e  mov     [rbp+57h+arg_0], 0
0x180073e72  lea     r8, [rbp+57h+arg_0]
0x180073e76  lea     rdx, aSystemmanageme; "systemManagement"
0x180073e7d  mov     rcx, [rbp+57h+TokenHandle]
0x180073e81  call    cs:__imp_CapabilityCheck
0x180073e87  test    eax, eax
0x180073e89  jns     short loc_180073EA7
0x180073e8b  mov     rcx, [rbp+5Fh]; this
0x180073e8f  mov     r9d, eax; char *
0x180073e92  lea     r8, aOnecoreBaseFli_58; "onecore\\base\\flighting\\flightsetting"...
0x180073e99  mov     edx, 67h ; 'g'; void *
0x180073e9e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180073ea3  mov     ebx, eax
0x180073ea5  jmp     short loc_180073EB6
0x180073ea7  cmp     [rbp+57h+arg_0], 1
0x180073eab  setz    al
0x180073eae  mov     [rdi], al
0x180073eb0  movzx   ebx, al
0x180073eb3  xor     ebx, 1
0x180073eb6  lea     rcx, [rbp+57h+TokenHandle]
0x180073eba  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180073ebf  mov     eax, ebx
0x180073ec1  add     rsp, 0B0h
0x180073ec8  pop     rdi
0x180073ec9  pop     rbx
0x180073eca  pop     rbp
0x180073ecb  retn
```
