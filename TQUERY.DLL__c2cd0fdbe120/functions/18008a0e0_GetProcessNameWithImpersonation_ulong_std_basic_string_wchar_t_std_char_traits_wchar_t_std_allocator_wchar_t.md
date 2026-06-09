# GetProcessNameWithImpersonation(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18008a0e0`
- end: `0x18008a27b`
- name: `?GetProcessNameWithImpersonation@@YAXKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800728f4`

## callees

- `0x18008a0e0`
- `0x18008a284`
- `0x18008a2b0`
- `0x18008b084`
- `0x1800f4820`
- `0x18013effc`
- `0x180147238`
- `0x180188d90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008a189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008a189`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008a19e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008a19e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a1f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a1f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a26b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18008a1c4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18008a1c4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a255`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a255`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008a116`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008a240`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008a116`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008a240`

## string_xrefs

- `0x18008a213`: `onecoreuap\base\appmodel\search\common\telemetry\telemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall GetProcessNameWithImpersonation(DWORD dwProcessId)
{
  int Error; // ebx
  int result; // eax
  HANDLE CurrentThread; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rbx
  HANDLE v7; // rax
  HANDLE hObject; // [rsp+20h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hObject = OpenProcess(0x1000u, 0, dwProcessId);
  if ( hObject )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024891 )
    {
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error == -2147023888 )
        {
          std::wstring::wstring(v11, v5);
          if ( CoImpersonateClient() )
          {
            Error = -2147023550;
          }
          else
          {
            v6 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hObject);
            v7 = OpenProcess(0x1000u, 0, dwProcessId);
            *v6 = v7;
            if ( v7 )
              Error = 0;
            else
              Error = ResultFromKnownLastError();
            CoRevertToSelf();
          }
          std::wstring::_Tidy_deallocate(v11);
        }
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
    }
  }
  if ( Error < 0 )
  {
    if ( Error != -2147023550 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\telemetry\\telemetry.cpp",
        (const char *)(unsigned int)Error,
        (int)hObject);
  }
  else
  {
    try
    {
      GetProcessNameFromHANDLE(hObject);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        63,
        "onecoreuap\\base\\appmodel\\search\\common\\telemetry\\telemetry.cpp");
    }
  }
  result = (_DWORD)hObject - 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hObject);
  return result;
}

```

## disassembly

```asm
0x18008a0e0  mov     [rsp+arg_10], rbx
0x18008a0e5  mov     [rsp+arg_18], rsi
0x18008a0ea  push    rdi
0x18008a0eb  sub     rsp, 60h
0x18008a0ef  mov     rax, cs:__security_cookie
0x18008a0f6  xor     rax, rsp
0x18008a0f9  mov     [rsp+68h+var_10], rax
0x18008a0fe  mov     rsi, rdx
0x18008a101  mov     edi, ecx
0x18008a103  mov     [rsp+68h+hObject], 0
0x18008a10c  mov     r8d, ecx; dwProcessId
0x18008a10f  xor     edx, edx; bInheritHandle
0x18008a111  mov     ecx, 1000h; dwDesiredAccess
0x18008a116  call    cs:__imp_OpenProcess
0x18008a11c  mov     [rsp+68h+hObject], rax; int
0x18008a121  test    rax, rax
0x18008a124  jz      short loc_18008A12A
0x18008a126  xor     ebx, ebx
0x18008a128  jmp     short loc_18008A138
0x18008a12a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008a12f  mov     ebx, eax
0x18008a131  cmp     eax, 80070005h
0x18008a136  jz      short loc_18008A180
0x18008a138  test    ebx, ebx
0x18008a13a  js      loc_18008A1FF
0x18008a140  mov     rdx, rsi
0x18008a143  mov     rcx, [rsp+68h+hObject]; hProcess
0x18008a148  call    ?GetProcessNameFromHANDLE@@YAXPEAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetProcessNameFromHANDLE(void *,std::wstring &)
0x18008a14d  nop
0x18008a14e  mov     rcx, [rsp+68h+hObject]; hObject
0x18008a153  lea     rax, [rcx-1]
0x18008a157  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008a15b  jbe     loc_18008A26B
0x18008a161  mov     rcx, [rsp+68h+var_10]
0x18008a166  xor     rcx, rsp; StackCookie
0x18008a169  call    __security_check_cookie
0x18008a16e  lea     r11, [rsp+68h+var_8]
0x18008a173  mov     rbx, [r11+20h]
0x18008a177  mov     rsi, [r11+28h]
0x18008a17b  mov     rsp, r11
0x18008a17e  pop     rdi
0x18008a17f  retn
0x18008a180  mov     [rsp+68h+TokenHandle], 0
0x18008a189  call    cs:__imp_GetCurrentThread
0x18008a18f  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18008a194  xor     r8d, r8d; OpenAsSelf
0x18008a197  lea     edx, [r8+8]; DesiredAccess
0x18008a19b  mov     rcx, rax; ThreadHandle
0x18008a19e  call    cs:__imp_OpenThreadToken
0x18008a1a4  test    eax, eax
0x18008a1a6  jnz     loc_18008A264
0x18008a1ac  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008a1b1  mov     ebx, eax
0x18008a1b3  cmp     eax, 800703F0h
0x18008a1b8  jnz     short loc_18008A1E1
0x18008a1ba  lea     rcx, [rsp+68h+var_30]
0x18008a1bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008a1c4  call    cs:__imp_CoImpersonateClient
0x18008a1ca  mov     [rsp+68h+var_38], eax
0x18008a1ce  test    eax, eax
0x18008a1d0  jz      short loc_18008A229
0x18008a1d2  mov     ebx, 80070542h
0x18008a1d7  lea     rcx, [rsp+68h+var_30]
0x18008a1dc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008a1e1  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18008a1e6  lea     rax, [rcx-1]
0x18008a1ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008a1ee  ja      loc_18008A138
0x18008a1f4  call    cs:__imp_CloseHandle
0x18008a1fa  jmp     loc_18008A138
0x18008a1ff  cmp     ebx, 80070542h
0x18008a205  jz      loc_18008A14E
0x18008a20b  mov     rcx, [rsp+68h]; this
0x18008a210  mov     r9d, ebx; char *
0x18008a213  lea     r8, aOnecoreuapBase_148; "onecoreuap\\base\\appmodel\\search\\com"...
0x18008a21a  mov     edx, 38h ; '8'; void *
0x18008a21f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008a224  jmp     loc_18008A14E
0x18008a229  lea     rcx, [rsp+68h+hObject]
0x18008a22e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18008a233  mov     rbx, rax
0x18008a236  mov     r8d, edi; dwProcessId
0x18008a239  xor     edx, edx; bInheritHandle
0x18008a23b  mov     ecx, 1000h; dwDesiredAccess
0x18008a240  call    cs:__imp_OpenProcess
0x18008a246  mov     [rbx], rax
0x18008a249  test    rax, rax
0x18008a24c  jnz     short loc_18008A260
0x18008a24e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008a253  mov     ebx, eax
0x18008a255  call    cs:__imp_CoRevertToSelf
0x18008a25b  jmp     loc_18008A1D7
0x18008a260  xor     ebx, ebx
0x18008a262  jmp     short loc_18008A255
0x18008a264  xor     ebx, ebx
0x18008a266  jmp     loc_18008A1E1
0x18008a26b  call    cs:__imp_CloseHandle
0x18008a271  jmp     loc_18008A161
0x18008a276  jmp     loc_18008A161
```
