# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800998c0`
- end: `0x18009998f`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800234f8`

## callees

- `0x18004b914`
- `0x18005ae90`
- `0x1800998c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800998e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800998e8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180099963`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180099963`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099955`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099955`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18009990b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18009990b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180099930`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180099930`

## string_xrefs

- `0x180099929`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x1800998c0  push    rbx
0x1800998c2  sub     rsp, 470h
0x1800998c9  mov     rax, cs:__security_cookie
0x1800998d0  xor     rax, rsp
0x1800998d3  mov     [rsp+478h+var_18], rax
0x1800998db  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800998e2  jnz     loc_180099976
0x1800998e8  call    cs:__imp_GetCurrentProcess
0x1800998ee  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800998f3  mov     [rsp+478h+dwSize], 104h
0x1800998fb  mov     rcx, rax; hProcess
0x1800998fe  lea     r8, [rsp+478h+ExeName]; lpExeName
0x180099906  xor     edx, edx; dwFlags
0x180099908  mov     rbx, rax
0x18009990b  call    cs:__imp_QueryFullProcessImageNameW
0x180099911  test    eax, eax
0x180099913  jnz     short loc_18009991E
0x180099915  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009991a  test    eax, eax
0x18009991c  js      short loc_18009996F
0x18009991e  mov     r8d, 104h; nSize
0x180099924  lea     rdx, [rsp+478h+Dst]; lpDst
0x180099929  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180099930  call    cs:__imp_ExpandEnvironmentStringsW
0x180099936  test    eax, eax
0x180099938  jz      short loc_18009996F
0x18009993a  or      edx, 0FFFFFFFFh; cchCount1
0x18009993d  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180099945  mov     r9d, edx; cchCount2
0x180099948  lea     r8, [rsp+478h+Dst]; lpString2
0x18009994d  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180099955  call    cs:__imp_CompareStringOrdinal
0x18009995b  cmp     eax, 2
0x18009995e  jnz     short loc_18009996F
0x180099960  mov     rcx, rbx; Process
0x180099963  call    cs:__imp_GetProcessId
0x180099969  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18009996f  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180099976  mov     rcx, [rsp+478h+var_18]
0x18009997e  xor     rcx, rsp; StackCookie
0x180099981  call    __security_check_cookie
0x180099986  add     rsp, 470h
0x18009998d  pop     rbx
0x18009998e  retn
```
