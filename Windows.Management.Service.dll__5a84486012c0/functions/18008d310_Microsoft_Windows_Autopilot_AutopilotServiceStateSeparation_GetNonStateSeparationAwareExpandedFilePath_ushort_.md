# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008d310`
- end: `0x18008d47b`
- name: `?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007e5cc`
- `0x18008d578`
- `0x180091e88`
- `0x1801ae2c0`
- `0x1801b9fcc`
- `0x1801bb598`
- `0x1801c65f8`
- `0x1801c7ae4`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a34`
- `0x180067a54`
- `0x18007755c`
- `0x1800839bc`
- `0x18008a0a8`
- `0x18008cfa4`
- `0x18008d310`
- `0x18008dddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008d35d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008d35d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d34a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d34a`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18008d3b8`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18008d3b8`

## string_xrefs

- `0x18008d36f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d3ca`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d402`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(
        LPCWSTR lpSrc,
        __int64 a2)
{
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  unsigned int v8; // eax
  const char *v9; // r9
  unsigned int LastError; // ebx
  __int64 v11; // rax
  void *TokenHandle; // [rsp+20h] [rbp-258h] BYREF
  _BYTE v13[40]; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Dest[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    memset_0(Dest, 0, 0x208u);
    v8 = ExpandEnvironmentStringsForUserW(TokenHandle, lpSrc, Dest, 0x104u);
    if ( v8 )
    {
      if ( v8 <= 0x104 )
      {
        v11 = std::wstring::wstring(v13, Dest);
        std::wstring::operator=(a2, v11);
        std::wstring::_Tidy_deallocate(v13);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)0x8007007ALL,
          (int)TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 2147942522LL;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBF,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                    v9);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return LastError;
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xBB,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
           v5);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
}

```

## disassembly

```asm
0x18008d310  mov     [rsp+arg_10], rbx
0x18008d315  push    rdi
0x18008d316  sub     rsp, 270h
0x18008d31d  mov     rax, cs:__security_cookie
0x18008d324  xor     rax, rsp
0x18008d327  mov     [rsp+278h+var_18], rax
0x18008d32f  mov     rbx, rdx
0x18008d332  mov     rdi, rcx
0x18008d335  mov     [rsp+278h+TokenHandle], 0; int
0x18008d33e  xor     edx, edx
0x18008d340  lea     rcx, [rsp+278h+TokenHandle]
0x18008d345  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008d34a  call    cs:__imp_GetCurrentProcess
0x18008d350  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x18008d355  mov     edx, 0Eh; DesiredAccess
0x18008d35a  mov     rcx, rax; ProcessHandle
0x18008d35d  call    cs:__imp_OpenProcessToken
0x18008d363  test    eax, eax
0x18008d365  jnz     short loc_18008D393
0x18008d367  mov     rcx, [rsp+278h]; this
0x18008d36f  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d376  mov     edx, 0BBh; void *
0x18008d37b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d380  mov     ebx, eax
0x18008d382  lea     rcx, [rsp+278h+TokenHandle]
0x18008d387  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d38c  mov     eax, ebx
0x18008d38e  jmp     loc_18008D459
0x18008d393  xor     edx, edx; Val
0x18008d395  mov     r8d, 208h; Size
0x18008d39b  lea     rcx, [rsp+278h+Dest]; void *
0x18008d3a0  call    memset_0
0x18008d3a5  mov     r9d, 104h; dwSize
0x18008d3ab  lea     r8, [rsp+278h+Dest]; lpDest
0x18008d3b0  mov     rdx, rdi; lpSrc
0x18008d3b3  mov     rcx, [rsp+278h+TokenHandle]; hToken
0x18008d3b8  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18008d3be  test    eax, eax
0x18008d3c0  jnz     short loc_18008D3EB
0x18008d3c2  mov     rcx, [rsp+278h]; this
0x18008d3ca  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d3d1  mov     edx, 0BFh; void *
0x18008d3d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d3db  mov     ebx, eax
0x18008d3dd  lea     rcx, [rsp+278h+TokenHandle]
0x18008d3e2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d3e7  mov     eax, ebx
0x18008d3e9  jmp     short loc_18008D459
0x18008d3eb  cmp     eax, 104h
0x18008d3f0  jbe     short loc_18008D422
0x18008d3f2  mov     rcx, [rsp+278h]; this
0x18008d3fa  mov     ebx, 8007007Ah
0x18008d3ff  mov     r9d, ebx; char *
0x18008d402  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d409  mov     edx, 0C0h; void *
0x18008d40e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d413  nop
0x18008d414  lea     rcx, [rsp+278h+TokenHandle]
0x18008d419  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d41e  mov     eax, ebx
0x18008d420  jmp     short loc_18008D459
0x18008d422  lea     rdx, [rsp+278h+Dest]
0x18008d427  lea     rcx, [rsp+278h+var_250]
0x18008d42c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d431  mov     rdx, rax
0x18008d434  mov     rcx, rbx
0x18008d437  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008d43c  lea     rcx, [rsp+278h+var_250]
0x18008d441  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d446  nop
0x18008d447  lea     rcx, [rsp+278h+TokenHandle]
0x18008d44c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d451  xor     eax, eax
0x18008d453  jmp     short loc_18008D459
0x18008d455  mov     eax, dword ptr [rsp+278h+TokenHandle]
0x18008d459  mov     rcx, [rsp+278h+var_18]
0x18008d461  xor     rcx, rsp; StackCookie
0x18008d464  call    __security_check_cookie
0x18008d469  mov     rbx, [rsp+278h+arg_10]
0x18008d471  add     rsp, 270h
0x18008d478  pop     rdi
0x18008d479  retn
```
