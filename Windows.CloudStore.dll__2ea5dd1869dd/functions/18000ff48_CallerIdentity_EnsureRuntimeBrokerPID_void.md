# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18000ff48`
- end: `0x180010017`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ff24`
- `0x180055580`

## callees

- `0x18000ff48`
- `0x1801201a0`
- `0x1801afa28`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000ff93`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000ff93`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ffb8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ffb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ff70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ff70`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ffeb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ffeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ffdd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ffdd`

## string_xrefs

- `0x18000ffb1`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18000ff48  push    rbx
0x18000ff4a  sub     rsp, 470h
0x18000ff51  mov     rax, cs:__security_cookie
0x18000ff58  xor     rax, rsp
0x18000ff5b  mov     [rsp+478h+var_18], rax
0x18000ff63  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18000ff6a  jnz     loc_18000FFFE
0x18000ff70  call    cs:__imp_GetCurrentProcess
0x18000ff76  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18000ff7b  mov     [rsp+478h+dwSize], 104h
0x18000ff83  mov     rcx, rax; hProcess
0x18000ff86  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18000ff8e  xor     edx, edx; dwFlags
0x18000ff90  mov     rbx, rax
0x18000ff93  call    cs:__imp_QueryFullProcessImageNameW
0x18000ff99  test    eax, eax
0x18000ff9b  jnz     short loc_18000FFA6
0x18000ff9d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000ffa2  test    eax, eax
0x18000ffa4  js      short loc_18000FFF7
0x18000ffa6  mov     r8d, 104h; nSize
0x18000ffac  lea     rdx, [rsp+478h+Dst]; lpDst
0x18000ffb1  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18000ffb8  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ffbe  test    eax, eax
0x18000ffc0  jz      short loc_18000FFF7
0x18000ffc2  or      edx, 0FFFFFFFFh; cchCount1
0x18000ffc5  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18000ffcd  mov     r9d, edx; cchCount2
0x18000ffd0  lea     r8, [rsp+478h+Dst]; lpString2
0x18000ffd5  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18000ffdd  call    cs:__imp_CompareStringOrdinal
0x18000ffe3  cmp     eax, 2
0x18000ffe6  jnz     short loc_18000FFF7
0x18000ffe8  mov     rcx, rbx; Process
0x18000ffeb  call    cs:__imp_GetProcessId
0x18000fff1  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18000fff7  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18000fffe  mov     rcx, [rsp+478h+var_18]
0x180010006  xor     rcx, rsp; StackCookie
0x180010009  call    __security_check_cookie
0x18001000e  add     rsp, 470h
0x180010015  pop     rbx
0x180010016  retn
```
