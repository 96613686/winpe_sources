# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800c35a4`
- end: `0x1800c3673`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800230b0`
- `0x18003d760`

## callees

- `0x18006c6bc`
- `0x180071dc0`
- `0x1800c35a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c3639`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c3639`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c3647`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c3647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c35cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c35cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c3614`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c3614`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800c35ef`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800c35ef`

## string_xrefs

- `0x1800c360d`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c
void __fastcall CallerIdentity::_EnsureRuntimeBrokerPID(CallerIdentity *this)
{
  HANDLE CurrentProcess; // rbx
  DWORD dwSize[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR ExeName[264]; // [rsp+250h] [rbp-228h] BYREF

  if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
  {
    dwSize[0] = 260;
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize) || (int)ResultFromKnownLastError() >= 0 )
    {
      if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u) )
      {
        if ( CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
          CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
    }
    CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
  }
}

```

## disassembly

```asm
0x1800c35a4  push    rbx
0x1800c35a6  sub     rsp, 470h
0x1800c35ad  mov     rax, cs:__security_cookie
0x1800c35b4  xor     rax, rsp
0x1800c35b7  mov     [rsp+478h+var_18], rax
0x1800c35bf  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800c35c6  jnz     loc_1800C365A
0x1800c35cc  call    cs:__imp_GetCurrentProcess
0x1800c35d2  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800c35d7  mov     [rsp+478h+dwSize], 104h
0x1800c35df  mov     rcx, rax; hProcess
0x1800c35e2  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800c35ea  xor     edx, edx; dwFlags
0x1800c35ec  mov     rbx, rax
0x1800c35ef  call    cs:__imp_QueryFullProcessImageNameW
0x1800c35f5  test    eax, eax
0x1800c35f7  jnz     short loc_1800C3602
0x1800c35f9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c35fe  test    eax, eax
0x1800c3600  js      short loc_1800C3653
0x1800c3602  mov     r8d, 104h; nSize
0x1800c3608  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800c360d  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800c3614  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c361a  test    eax, eax
0x1800c361c  jz      short loc_1800C3653
0x1800c361e  or      edx, 0FFFFFFFFh; cchCount1
0x1800c3621  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800c3629  mov     r9d, edx; cchCount2
0x1800c362c  lea     r8, [rsp+478h+Dst]; lpString2
0x1800c3631  lea     rcx, [rsp+478h+ExeName]; lpString1
0x1800c3639  call    cs:__imp_CompareStringOrdinal
0x1800c363f  cmp     eax, 2
0x1800c3642  jnz     short loc_1800C3653
0x1800c3644  mov     rcx, rbx; Process
0x1800c3647  call    cs:__imp_GetProcessId
0x1800c364d  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800c3653  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800c365a  mov     rcx, [rsp+478h+var_18]
0x1800c3662  xor     rcx, rsp; StackCookie
0x1800c3665  call    __security_check_cookie
0x1800c366a  add     rsp, 470h
0x1800c3671  pop     rbx
0x1800c3672  retn
```
