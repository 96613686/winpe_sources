# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180055f6c`
- end: `0x18005603b`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055a34`

## callees

- `0x180003ca0`
- `0x1800545a0`
- `0x180055f6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f94`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005600f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005600f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056001`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056001`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180055fb7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180055fb7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180055fdc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180055fdc`

## string_xrefs

- `0x180055fd5`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x180055f6c  push    rbx
0x180055f6e  sub     rsp, 470h
0x180055f75  mov     rax, cs:__security_cookie
0x180055f7c  xor     rax, rsp
0x180055f7f  mov     [rsp+478h+var_18], rax
0x180055f87  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180055f8e  jnz     loc_180056022
0x180055f94  call    cs:__imp_GetCurrentProcess
0x180055f9a  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x180055f9f  mov     [rsp+478h+dwSize], 104h
0x180055fa7  mov     rcx, rax; hProcess
0x180055faa  lea     r8, [rsp+478h+ExeName]; lpExeName
0x180055fb2  xor     edx, edx; dwFlags
0x180055fb4  mov     rbx, rax
0x180055fb7  call    cs:__imp_QueryFullProcessImageNameW
0x180055fbd  test    eax, eax
0x180055fbf  jnz     short loc_180055FCA
0x180055fc1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055fc6  test    eax, eax
0x180055fc8  js      short loc_18005601B
0x180055fca  mov     r8d, 104h; nSize
0x180055fd0  lea     rdx, [rsp+478h+Dst]; lpDst
0x180055fd5  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180055fdc  call    cs:__imp_ExpandEnvironmentStringsW
0x180055fe2  test    eax, eax
0x180055fe4  jz      short loc_18005601B
0x180055fe6  or      edx, 0FFFFFFFFh; cchCount1
0x180055fe9  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180055ff1  mov     r9d, edx; cchCount2
0x180055ff4  lea     r8, [rsp+478h+Dst]; lpString2
0x180055ff9  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180056001  call    cs:__imp_CompareStringOrdinal
0x180056007  cmp     eax, 2
0x18005600a  jnz     short loc_18005601B
0x18005600c  mov     rcx, rbx; Process
0x18005600f  call    cs:__imp_GetProcessId
0x180056015  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18005601b  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180056022  mov     rcx, [rsp+478h+var_18]
0x18005602a  xor     rcx, rsp; StackCookie
0x18005602d  call    __security_check_cookie
0x180056032  add     rsp, 470h
0x180056039  pop     rbx
0x18005603a  retn
```
