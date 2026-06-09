# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18003e2d0`
- end: `0x18003e39f`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003de0c`

## callees

- `0x180010fd0`
- `0x18003e2d0`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003e373`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003e373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e2f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e2f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e365`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e365`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003e340`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003e340`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003e31b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003e31b`

## string_xrefs

- `0x18003e339`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18003e2d0  push    rbx
0x18003e2d2  sub     rsp, 470h
0x18003e2d9  mov     rax, cs:__security_cookie
0x18003e2e0  xor     rax, rsp
0x18003e2e3  mov     [rsp+478h+var_18], rax
0x18003e2eb  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18003e2f2  jnz     loc_18003E386
0x18003e2f8  call    cs:__imp_GetCurrentProcess
0x18003e2fe  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18003e303  mov     [rsp+478h+dwSize], 104h
0x18003e30b  mov     rcx, rax; hProcess
0x18003e30e  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18003e316  xor     edx, edx; dwFlags
0x18003e318  mov     rbx, rax
0x18003e31b  call    cs:__imp_QueryFullProcessImageNameW
0x18003e321  test    eax, eax
0x18003e323  jnz     short loc_18003E32E
0x18003e325  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003e32a  test    eax, eax
0x18003e32c  js      short loc_18003E37F
0x18003e32e  mov     r8d, 104h; nSize
0x18003e334  lea     rdx, [rsp+478h+Dst]; lpDst
0x18003e339  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18003e340  call    cs:__imp_ExpandEnvironmentStringsW
0x18003e346  test    eax, eax
0x18003e348  jz      short loc_18003E37F
0x18003e34a  or      edx, 0FFFFFFFFh; cchCount1
0x18003e34d  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18003e355  mov     r9d, edx; cchCount2
0x18003e358  lea     r8, [rsp+478h+Dst]; lpString2
0x18003e35d  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18003e365  call    cs:__imp_CompareStringOrdinal
0x18003e36b  cmp     eax, 2
0x18003e36e  jnz     short loc_18003E37F
0x18003e370  mov     rcx, rbx; Process
0x18003e373  call    cs:__imp_GetProcessId
0x18003e379  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18003e37f  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18003e386  mov     rcx, [rsp+478h+var_18]
0x18003e38e  xor     rcx, rsp; StackCookie
0x18003e391  call    __security_check_cookie
0x18003e396  add     rsp, 470h
0x18003e39d  pop     rbx
0x18003e39e  retn
```
