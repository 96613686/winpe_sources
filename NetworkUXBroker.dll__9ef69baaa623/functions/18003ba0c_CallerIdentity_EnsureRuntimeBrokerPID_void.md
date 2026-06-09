# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18003ba0c`
- end: `0x18003badb`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b36c`

## callees

- `0x180002520`
- `0x18003b8f4`
- `0x18003ba0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ba34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ba34`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003baaf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003baaf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003baa1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003baa1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003ba7c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003ba7c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003ba57`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003ba57`

## string_xrefs

- `0x18003ba75`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
0x18003ba0c  push    rbx
0x18003ba0e  sub     rsp, 470h
0x18003ba15  mov     rax, cs:__security_cookie
0x18003ba1c  xor     rax, rsp
0x18003ba1f  mov     [rsp+478h+var_18], rax
0x18003ba27  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18003ba2e  jnz     loc_18003BAC2
0x18003ba34  call    cs:__imp_GetCurrentProcess
0x18003ba3a  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18003ba3f  mov     [rsp+478h+dwSize], 104h
0x18003ba47  mov     rcx, rax; hProcess
0x18003ba4a  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18003ba52  xor     edx, edx; dwFlags
0x18003ba54  mov     rbx, rax
0x18003ba57  call    cs:__imp_QueryFullProcessImageNameW
0x18003ba5d  test    eax, eax
0x18003ba5f  jnz     short loc_18003BA6A
0x18003ba61  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003ba66  test    eax, eax
0x18003ba68  js      short loc_18003BABB
0x18003ba6a  mov     r8d, 104h; nSize
0x18003ba70  lea     rdx, [rsp+478h+Dst]; lpDst
0x18003ba75  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18003ba7c  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ba82  test    eax, eax
0x18003ba84  jz      short loc_18003BABB
0x18003ba86  or      edx, 0FFFFFFFFh; cchCount1
0x18003ba89  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18003ba91  mov     r9d, edx; cchCount2
0x18003ba94  lea     r8, [rsp+478h+Dst]; lpString2
0x18003ba99  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18003baa1  call    cs:__imp_CompareStringOrdinal
0x18003baa7  cmp     eax, 2
0x18003baaa  jnz     short loc_18003BABB
0x18003baac  mov     rcx, rbx; Process
0x18003baaf  call    cs:__imp_GetProcessId
0x18003bab5  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18003babb  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18003bac2  mov     rcx, [rsp+478h+var_18]
0x18003baca  xor     rcx, rsp; StackCookie
0x18003bacd  call    __security_check_cookie
0x18003bad2  add     rsp, 470h
0x18003bad9  pop     rbx
0x18003bada  retn
```
