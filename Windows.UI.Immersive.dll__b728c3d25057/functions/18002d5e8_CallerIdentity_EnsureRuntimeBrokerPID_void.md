# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18002d5e8`
- end: `0x18002d6b7`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d8268`

## callees

- `0x18002d5e8`
- `0x18003aa84`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002d633`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002d633`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d67d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d67d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002d68b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002d68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d610`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d658`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d658`

## string_xrefs

- `0x18002d651`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18002d5e8  push    rbx
0x18002d5ea  sub     rsp, 470h
0x18002d5f1  mov     rax, cs:__security_cookie
0x18002d5f8  xor     rax, rsp
0x18002d5fb  mov     [rsp+478h+var_18], rax
0x18002d603  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18002d60a  jnz     loc_18002D69E
0x18002d610  call    cs:__imp_GetCurrentProcess
0x18002d616  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18002d61b  mov     [rsp+478h+dwSize], 104h
0x18002d623  mov     rcx, rax; hProcess
0x18002d626  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18002d62e  xor     edx, edx; dwFlags
0x18002d630  mov     rbx, rax
0x18002d633  call    cs:__imp_QueryFullProcessImageNameW
0x18002d639  test    eax, eax
0x18002d63b  jnz     short loc_18002D646
0x18002d63d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d642  test    eax, eax
0x18002d644  js      short loc_18002D697
0x18002d646  mov     r8d, 104h; nSize
0x18002d64c  lea     rdx, [rsp+478h+Dst]; lpDst
0x18002d651  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18002d658  call    cs:__imp_ExpandEnvironmentStringsW
0x18002d65e  test    eax, eax
0x18002d660  jz      short loc_18002D697
0x18002d662  or      edx, 0FFFFFFFFh; cchCount1
0x18002d665  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18002d66d  mov     r9d, edx; cchCount2
0x18002d670  lea     r8, [rsp+478h+Dst]; lpString2
0x18002d675  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18002d67d  call    cs:__imp_CompareStringOrdinal
0x18002d683  cmp     eax, 2
0x18002d686  jnz     short loc_18002D697
0x18002d688  mov     rcx, rbx; Process
0x18002d68b  call    cs:__imp_GetProcessId
0x18002d691  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18002d697  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18002d69e  mov     rcx, [rsp+478h+var_18]
0x18002d6a6  xor     rcx, rsp; StackCookie
0x18002d6a9  call    __security_check_cookie
0x18002d6ae  add     rsp, 470h
0x18002d6b5  pop     rbx
0x18002d6b6  retn
```
