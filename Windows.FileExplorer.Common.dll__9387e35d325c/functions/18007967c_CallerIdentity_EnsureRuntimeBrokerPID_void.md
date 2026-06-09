# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18007967c`
- end: `0x18007974b`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800791dc`

## callees

- `0x18000c668`
- `0x180037780`
- `0x18007967c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007971f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007971f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800796a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800796a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079711`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079711`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800796ec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800796ec`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800796c7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800796c7`

## string_xrefs

- `0x1800796e5`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18007967c  push    rbx
0x18007967e  sub     rsp, 470h
0x180079685  mov     rax, cs:__security_cookie
0x18007968c  xor     rax, rsp
0x18007968f  mov     [rsp+478h+var_18], rax
0x180079697  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18007969e  jnz     loc_180079732
0x1800796a4  call    cs:__imp_GetCurrentProcess
0x1800796aa  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800796af  mov     [rsp+478h+dwSize], 104h
0x1800796b7  mov     rcx, rax; hProcess
0x1800796ba  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800796c2  xor     edx, edx; dwFlags
0x1800796c4  mov     rbx, rax
0x1800796c7  call    cs:__imp_QueryFullProcessImageNameW
0x1800796cd  test    eax, eax
0x1800796cf  jnz     short loc_1800796DA
0x1800796d1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800796d6  test    eax, eax
0x1800796d8  js      short loc_18007972B
0x1800796da  mov     r8d, 104h; nSize
0x1800796e0  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800796e5  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800796ec  call    cs:__imp_ExpandEnvironmentStringsW
0x1800796f2  test    eax, eax
0x1800796f4  jz      short loc_18007972B
0x1800796f6  or      edx, 0FFFFFFFFh; cchCount1
0x1800796f9  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180079701  mov     r9d, edx; cchCount2
0x180079704  lea     r8, [rsp+478h+Dst]; lpString2
0x180079709  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180079711  call    cs:__imp_CompareStringOrdinal
0x180079717  cmp     eax, 2
0x18007971a  jnz     short loc_18007972B
0x18007971c  mov     rcx, rbx; Process
0x18007971f  call    cs:__imp_GetProcessId
0x180079725  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18007972b  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180079732  mov     rcx, [rsp+478h+var_18]
0x18007973a  xor     rcx, rsp; StackCookie
0x18007973d  call    __security_check_cookie
0x180079742  add     rsp, 470h
0x180079749  pop     rbx
0x18007974a  retn
```
