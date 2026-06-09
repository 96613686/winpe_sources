# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180043d2c`
- end: `0x180043dfb`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004359c`

## callees

- `0x180002d40`
- `0x180043ae8`
- `0x180043d2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043d54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043d54`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180043dcf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180043dcf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043dc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043dc1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043d9c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043d9c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180043d77`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180043d77`

## string_xrefs

- `0x180043d95`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x180043d2c  push    rbx
0x180043d2e  sub     rsp, 470h
0x180043d35  mov     rax, cs:__security_cookie
0x180043d3c  xor     rax, rsp
0x180043d3f  mov     [rsp+478h+var_18], rax
0x180043d47  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180043d4e  jnz     loc_180043DE2
0x180043d54  call    cs:__imp_GetCurrentProcess
0x180043d5a  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x180043d5f  mov     [rsp+478h+dwSize], 104h
0x180043d67  mov     rcx, rax; hProcess
0x180043d6a  lea     r8, [rsp+478h+ExeName]; lpExeName
0x180043d72  xor     edx, edx; dwFlags
0x180043d74  mov     rbx, rax
0x180043d77  call    cs:__imp_QueryFullProcessImageNameW
0x180043d7d  test    eax, eax
0x180043d7f  jnz     short loc_180043D8A
0x180043d81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180043d86  test    eax, eax
0x180043d88  js      short loc_180043DDB
0x180043d8a  mov     r8d, 104h; nSize
0x180043d90  lea     rdx, [rsp+478h+Dst]; lpDst
0x180043d95  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180043d9c  call    cs:__imp_ExpandEnvironmentStringsW
0x180043da2  test    eax, eax
0x180043da4  jz      short loc_180043DDB
0x180043da6  or      edx, 0FFFFFFFFh; cchCount1
0x180043da9  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180043db1  mov     r9d, edx; cchCount2
0x180043db4  lea     r8, [rsp+478h+Dst]; lpString2
0x180043db9  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180043dc1  call    cs:__imp_CompareStringOrdinal
0x180043dc7  cmp     eax, 2
0x180043dca  jnz     short loc_180043DDB
0x180043dcc  mov     rcx, rbx; Process
0x180043dcf  call    cs:__imp_GetProcessId
0x180043dd5  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180043ddb  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180043de2  mov     rcx, [rsp+478h+var_18]
0x180043dea  xor     rcx, rsp; StackCookie
0x180043ded  call    __security_check_cookie
0x180043df2  add     rsp, 470h
0x180043df9  pop     rbx
0x180043dfa  retn
```
