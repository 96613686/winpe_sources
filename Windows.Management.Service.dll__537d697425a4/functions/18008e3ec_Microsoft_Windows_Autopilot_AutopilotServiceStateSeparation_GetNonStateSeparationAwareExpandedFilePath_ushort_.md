# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008e3ec`
- end: `0x18008e569`
- name: `?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007ef6c`
- `0x18008e664`
- `0x1800930a0`
- `0x1801b3b00`
- `0x1801bfaf4`
- `0x1801c1174`
- `0x1801cc330`
- `0x1801cd870`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e34`
- `0x180067e54`
- `0x180077de0`
- `0x180084574`
- `0x18008af70`
- `0x18008e088`
- `0x18008e3ec`
- `0x18008eef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e43f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e43f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008e426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008e426`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18008e4a0`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18008e4a0`

## string_xrefs

- `0x18008e457`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e4b8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e4f0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

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
0x18008e3ec  mov     [rsp+arg_10], rbx
0x18008e3f1  push    rdi
0x18008e3f2  sub     rsp, 270h
0x18008e3f9  mov     rax, cs:__security_cookie
0x18008e400  xor     rax, rsp
0x18008e403  mov     [rsp+278h+var_18], rax
0x18008e40b  mov     rbx, rdx
0x18008e40e  mov     rdi, rcx
0x18008e411  mov     [rsp+278h+TokenHandle], 0; int
0x18008e41a  xor     edx, edx
0x18008e41c  lea     rcx, [rsp+278h+TokenHandle]
0x18008e421  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008e426  call    cs:__imp_GetCurrentProcess
0x18008e42d  nop     dword ptr [rax+rax+00h]
0x18008e432  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x18008e437  mov     edx, 0Eh; DesiredAccess
0x18008e43c  mov     rcx, rax; ProcessHandle
0x18008e43f  call    cs:__imp_OpenProcessToken
0x18008e446  nop     dword ptr [rax+rax+00h]
0x18008e44b  test    eax, eax
0x18008e44d  jnz     short loc_18008E47B
0x18008e44f  mov     rcx, [rsp+278h]; this
0x18008e457  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e45e  mov     edx, 0BBh; void *
0x18008e463  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008e468  mov     ebx, eax
0x18008e46a  lea     rcx, [rsp+278h+TokenHandle]
0x18008e46f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e474  mov     eax, ebx
0x18008e476  jmp     loc_18008E547
0x18008e47b  xor     edx, edx; Val
0x18008e47d  mov     r8d, 208h; Size
0x18008e483  lea     rcx, [rsp+278h+Dest]; void *
0x18008e488  call    memset_0
0x18008e48d  mov     r9d, 104h; dwSize
0x18008e493  lea     r8, [rsp+278h+Dest]; lpDest
0x18008e498  mov     rdx, rdi; lpSrc
0x18008e49b  mov     rcx, [rsp+278h+TokenHandle]; hToken
0x18008e4a0  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18008e4a7  nop     dword ptr [rax+rax+00h]
0x18008e4ac  test    eax, eax
0x18008e4ae  jnz     short loc_18008E4D9
0x18008e4b0  mov     rcx, [rsp+278h]; this
0x18008e4b8  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e4bf  mov     edx, 0BFh; void *
0x18008e4c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008e4c9  mov     ebx, eax
0x18008e4cb  lea     rcx, [rsp+278h+TokenHandle]
0x18008e4d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e4d5  mov     eax, ebx
0x18008e4d7  jmp     short loc_18008E547
0x18008e4d9  cmp     eax, 104h
0x18008e4de  jbe     short loc_18008E510
0x18008e4e0  mov     rcx, [rsp+278h]; this
0x18008e4e8  mov     ebx, 8007007Ah
0x18008e4ed  mov     r9d, ebx; char *
0x18008e4f0  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e4f7  mov     edx, 0C0h; void *
0x18008e4fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e501  nop
0x18008e502  lea     rcx, [rsp+278h+TokenHandle]
0x18008e507  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e50c  mov     eax, ebx
0x18008e50e  jmp     short loc_18008E547
0x18008e510  lea     rdx, [rsp+278h+Dest]
0x18008e515  lea     rcx, [rsp+278h+var_250]
0x18008e51a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008e51f  mov     rdx, rax
0x18008e522  mov     rcx, rbx
0x18008e525  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008e52a  lea     rcx, [rsp+278h+var_250]
0x18008e52f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e534  nop
0x18008e535  lea     rcx, [rsp+278h+TokenHandle]
0x18008e53a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e53f  xor     eax, eax
0x18008e541  jmp     short loc_18008E547
0x18008e543  mov     eax, dword ptr [rsp+278h+TokenHandle]
0x18008e547  mov     rcx, [rsp+278h+var_18]
0x18008e54f  xor     rcx, rsp; StackCookie
0x18008e552  call    __security_check_cookie
0x18008e557  mov     rbx, [rsp+278h+arg_10]
0x18008e55f  add     rsp, 270h
0x18008e566  pop     rdi
0x18008e567  retn
```
