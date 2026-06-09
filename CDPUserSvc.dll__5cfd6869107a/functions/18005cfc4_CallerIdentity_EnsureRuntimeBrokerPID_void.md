# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18005cfc4`
- end: `0x18005d093`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005cc80`

## callees

- `0x18002c570`
- `0x180056c68`
- `0x18005cfc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cfec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cfec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005d067`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005d067`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d059`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d059`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d034`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d034`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005d00f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005d00f`

## string_xrefs

- `0x18005d02d`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18005cfc4  push    rbx
0x18005cfc6  sub     rsp, 470h
0x18005cfcd  mov     rax, cs:__security_cookie
0x18005cfd4  xor     rax, rsp
0x18005cfd7  mov     [rsp+478h+var_18], rax
0x18005cfdf  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18005cfe6  jnz     loc_18005D07A
0x18005cfec  call    cs:__imp_GetCurrentProcess
0x18005cff2  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18005cff7  mov     [rsp+478h+dwSize], 104h
0x18005cfff  mov     rcx, rax; hProcess
0x18005d002  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18005d00a  xor     edx, edx; dwFlags
0x18005d00c  mov     rbx, rax
0x18005d00f  call    cs:__imp_QueryFullProcessImageNameW
0x18005d015  test    eax, eax
0x18005d017  jnz     short loc_18005D022
0x18005d019  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005d01e  test    eax, eax
0x18005d020  js      short loc_18005D073
0x18005d022  mov     r8d, 104h; nSize
0x18005d028  lea     rdx, [rsp+478h+Dst]; lpDst
0x18005d02d  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18005d034  call    cs:__imp_ExpandEnvironmentStringsW
0x18005d03a  test    eax, eax
0x18005d03c  jz      short loc_18005D073
0x18005d03e  or      edx, 0FFFFFFFFh; cchCount1
0x18005d041  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18005d049  mov     r9d, edx; cchCount2
0x18005d04c  lea     r8, [rsp+478h+Dst]; lpString2
0x18005d051  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18005d059  call    cs:__imp_CompareStringOrdinal
0x18005d05f  cmp     eax, 2
0x18005d062  jnz     short loc_18005D073
0x18005d064  mov     rcx, rbx; Process
0x18005d067  call    cs:__imp_GetProcessId
0x18005d06d  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18005d073  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18005d07a  mov     rcx, [rsp+478h+var_18]
0x18005d082  xor     rcx, rsp; StackCookie
0x18005d085  call    __security_check_cookie
0x18005d08a  add     rsp, 470h
0x18005d091  pop     rbx
0x18005d092  retn
```
