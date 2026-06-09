# GetProcessNameWithImpersonation(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180220c1c`
- end: `0x180220d8f`
- name: `?GetProcessNameWithImpersonation@@YAXKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800efe78`

## callees

- `0x18004b638`
- `0x18005e788`
- `0x1800723ac`
- `0x180079c44`
- `0x18010ff58`
- `0x1801244c0`
- `0x180220afc`
- `0x180220b24`
- `0x180220c1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180220c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180220c98`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180220cab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180220cab`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180220c5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180220cfd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180220c5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180220cfd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180220cd1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180220cd1`

## string_xrefs

- `0x180220d42`: `onecoreuap\base\appmodel\search\common\telemetry\telemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProcessNameWithImpersonation(DWORD dwProcessId)
{
  _QWORD *v2; // rbx
  HANDLE v3; // rax
  int Error; // ebx
  void **v5; // rbx
  HANDLE CurrentThread; // rax
  _QWORD *v7; // rbx
  HANDLE v8; // rax
  HANDLE hProcess; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h] BYREF
  HRESULT v12; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hProcess = 0;
  v2 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hProcess);
  v3 = OpenProcess(0x1000u, 0, dwProcessId);
  *v2 = v3;
  if ( v3 )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024891 )
    {
      v11 = 0;
      v5 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v11);
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 0, v5) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error == -2147023888 )
        {
          std::wstring::wstring(v13);
          v12 = CoImpersonateClient();
          if ( v12 )
          {
            Error = -2147023550;
          }
          else
          {
            v7 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hProcess);
            v8 = OpenProcess(0x1000u, 0, dwProcessId);
            *v7 = v8;
            if ( v8 )
              Error = 0;
            else
              Error = ResultFromKnownLastError();
          }
          ImpersonateCOMClient::~ImpersonateCOMClient((ImpersonateCOMClient *)&v12);
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    }
  }
  if ( Error >= 0 )
  {
    try
    {
      GetProcessNameFromHANDLE(hProcess);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        63,
        "onecoreuap\\base\\appmodel\\search\\common\\telemetry\\telemetry.cpp");
    }
  }
  else if ( Error != -2147023550 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\telemetry\\telemetry.cpp",
      (const char *)(unsigned int)Error,
      (int)hProcess);
  }
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
}

```

## disassembly

```asm
0x180220c1c  mov     r11, rsp
0x180220c1f  mov     [r11+18h], rbx
0x180220c23  mov     [r11+20h], rsi
0x180220c27  push    rdi
0x180220c28  sub     rsp, 60h
0x180220c2c  mov     rax, cs:__security_cookie
0x180220c33  xor     rax, rsp
0x180220c36  mov     [rsp+68h+var_10], rax
0x180220c3b  mov     rsi, rdx
0x180220c3e  mov     edi, ecx
0x180220c40  mov     qword ptr [r11-48h], 0
0x180220c48  lea     rcx, [r11-48h]
0x180220c4c  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x180220c51  mov     rbx, rax
0x180220c54  mov     r8d, edi; dwProcessId
0x180220c57  xor     edx, edx; bInheritHandle
0x180220c59  mov     ecx, 1000h; dwDesiredAccess
0x180220c5e  call    cs:__imp_OpenProcess
0x180220c64  mov     [rbx], rax
0x180220c67  test    rax, rax
0x180220c6a  jnz     loc_180220D2C
0x180220c70  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180220c75  mov     ebx, eax
0x180220c77  cmp     eax, 80070005h
0x180220c7c  jnz     loc_180220D2E
0x180220c82  mov     [rsp+68h+var_40], 0
0x180220c8b  lea     rcx, [rsp+68h+var_40]
0x180220c90  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x180220c95  mov     rbx, rax
0x180220c98  call    cs:__imp_GetCurrentThread
0x180220c9e  mov     r9, rbx; TokenHandle
0x180220ca1  xor     r8d, r8d; OpenAsSelf
0x180220ca4  lea     edx, [r8+8]; DesiredAccess
0x180220ca8  mov     rcx, rax; ThreadHandle
0x180220cab  call    cs:__imp_OpenThreadToken
0x180220cb1  test    eax, eax
0x180220cb3  jz      short loc_180220CB9
0x180220cb5  xor     ebx, ebx
0x180220cb7  jmp     short loc_180220D20
0x180220cb9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180220cbe  mov     ebx, eax
0x180220cc0  cmp     eax, 800703F0h
0x180220cc5  jnz     short loc_180220D20
0x180220cc7  lea     rcx, [rsp+68h+var_30]
0x180220ccc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180220cd1  call    cs:__imp_CoImpersonateClient
0x180220cd7  mov     [rsp+68h+var_38], eax
0x180220cdb  test    eax, eax
0x180220cdd  jz      short loc_180220CE6
0x180220cdf  mov     ebx, 80070542h
0x180220ce4  jmp     short loc_180220D16
0x180220ce6  lea     rcx, [rsp+68h+hProcess]
0x180220ceb  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x180220cf0  mov     rbx, rax
0x180220cf3  mov     r8d, edi; dwProcessId
0x180220cf6  xor     edx, edx; bInheritHandle
0x180220cf8  mov     ecx, 1000h; dwDesiredAccess
0x180220cfd  call    cs:__imp_OpenProcess
0x180220d03  mov     [rbx], rax
0x180220d06  test    rax, rax
0x180220d09  jnz     short loc_180220D14
0x180220d0b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180220d10  mov     ebx, eax
0x180220d12  jmp     short loc_180220D16
0x180220d14  xor     ebx, ebx
0x180220d16  lea     rcx, [rsp+68h+var_38]; this
0x180220d1b  call    ??1ImpersonateCOMClient@@QEAA@XZ; ImpersonateCOMClient::~ImpersonateCOMClient(void)
0x180220d20  lea     rcx, [rsp+68h+var_40]
0x180220d25  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180220d2a  jmp     short loc_180220D2E
0x180220d2c  xor     ebx, ebx
0x180220d2e  test    ebx, ebx
0x180220d30  jns     short loc_180220D55
0x180220d32  cmp     ebx, 80070542h
0x180220d38  jz      short loc_180220D63
0x180220d3a  mov     rcx, [rsp+68h]; this
0x180220d3f  mov     r9d, ebx; char *
0x180220d42  lea     r8, aOnecoreuapBase_106; "onecoreuap\\base\\appmodel\\search\\com"...
0x180220d49  mov     edx, 38h ; '8'; void *
0x180220d4e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180220d53  jmp     short loc_180220D63
0x180220d55  mov     rdx, rsi
0x180220d58  mov     rcx, [rsp+68h+hProcess]; hProcess
0x180220d5d  call    ?GetProcessNameFromHANDLE@@YAXPEAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetProcessNameFromHANDLE(void *,std::wstring &)
0x180220d62  nop
0x180220d63  lea     rcx, [rsp+68h+hProcess]
0x180220d68  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180220d6d  nop
0x180220d6e  jmp     short $+2
0x180220d70  mov     rcx, [rsp+68h+var_10]
0x180220d75  xor     rcx, rsp; StackCookie
0x180220d78  call    __security_check_cookie
0x180220d7d  lea     r11, [rsp+68h+var_8]
0x180220d82  mov     rbx, [r11+20h]
0x180220d86  mov     rsi, [r11+28h]
0x180220d8a  mov     rsp, r11
0x180220d8d  pop     rdi
0x180220d8e  retn
```
