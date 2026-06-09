# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800cbd10`
- end: `0x1800cbddf`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001541c`

## callees

- `0x18001a540`
- `0x1800cbce4`
- `0x1800cbd10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800cbdb3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800cbdb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cbd38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cbd38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cbda5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cbda5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cbd80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cbd80`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800cbd5b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800cbd5b`

## string_xrefs

- `0x1800cbd79`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x1800cbd10  push    rbx
0x1800cbd12  sub     rsp, 470h
0x1800cbd19  mov     rax, cs:__security_cookie
0x1800cbd20  xor     rax, rsp
0x1800cbd23  mov     [rsp+478h+var_18], rax
0x1800cbd2b  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800cbd32  jnz     loc_1800CBDC6
0x1800cbd38  call    cs:__imp_GetCurrentProcess
0x1800cbd3e  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800cbd43  mov     [rsp+478h+dwSize], 104h
0x1800cbd4b  mov     rcx, rax; hProcess
0x1800cbd4e  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800cbd56  xor     edx, edx; dwFlags
0x1800cbd58  mov     rbx, rax
0x1800cbd5b  call    cs:__imp_QueryFullProcessImageNameW
0x1800cbd61  test    eax, eax
0x1800cbd63  jnz     short loc_1800CBD6E
0x1800cbd65  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cbd6a  test    eax, eax
0x1800cbd6c  js      short loc_1800CBDBF
0x1800cbd6e  mov     r8d, 104h; nSize
0x1800cbd74  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800cbd79  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800cbd80  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cbd86  test    eax, eax
0x1800cbd88  jz      short loc_1800CBDBF
0x1800cbd8a  or      edx, 0FFFFFFFFh; cchCount1
0x1800cbd8d  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800cbd95  mov     r9d, edx; cchCount2
0x1800cbd98  lea     r8, [rsp+478h+Dst]; lpString2
0x1800cbd9d  lea     rcx, [rsp+478h+ExeName]; lpString1
0x1800cbda5  call    cs:__imp_CompareStringOrdinal
0x1800cbdab  cmp     eax, 2
0x1800cbdae  jnz     short loc_1800CBDBF
0x1800cbdb0  mov     rcx, rbx; Process
0x1800cbdb3  call    cs:__imp_GetProcessId
0x1800cbdb9  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800cbdbf  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800cbdc6  mov     rcx, [rsp+478h+var_18]
0x1800cbdce  xor     rcx, rsp; StackCookie
0x1800cbdd1  call    __security_check_cookie
0x1800cbdd6  add     rsp, 470h
0x1800cbddd  pop     rbx
0x1800cbdde  retn
```
