# AccessSeed

- ea: `0x180064d70`
- end: `0x180064e66`
- name: `AccessSeed`
- size: `246`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006400c`
- `0x180064e6c`

## callees

- `0x18004d320`
- `0x18004dd14`
- `0x180064d70`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180064ddd`
- `ntdll!RtlGetPersistedStateLocation` at `0x180064ddd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180064e2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180064e2b`

## pseudocode

```c
_BOOL8 __fastcall AccessSeed(REGSAM samDesired, PHKEY phkResult)
{
  int v5; // [rsp+50h] [rbp-238h] BYREF
  DWORD dwDisposition[3]; // [rsp+54h] [rbp-234h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v5 = 0;
  if ( (int)RtlGetPersistedStateLocation(
              L"DRM_RNG",
              0,
              L"SOFTWARE\\Microsoft\\Cryptography\\DRM_RNG",
              0,
              SubKey,
              520,
              &v5) < 0 )
    return 0;
  dwDisposition[0] = 0;
  return RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, samDesired, 0, phkResult, dwDisposition) == 0;
}

```

## disassembly

```asm
0x180064d70  mov     [rsp+arg_10], rbx
0x180064d75  push    rdi
0x180064d76  sub     rsp, 280h
0x180064d7d  mov     rax, cs:__security_cookie
0x180064d84  xor     rax, rsp
0x180064d87  mov     [rsp+288h+var_18], rax
0x180064d8f  mov     rdi, rdx
0x180064d92  mov     ebx, ecx
0x180064d94  xor     edx, edx; Val
0x180064d96  lea     rcx, [rsp+288h+SubKey]; void *
0x180064d9b  mov     r8d, 208h; Size
0x180064da1  call    memset_0
0x180064da6  lea     rax, [rsp+288h+var_238]
0x180064dab  mov     [rsp+288h+var_238], 0
0x180064db3  mov     [rsp+288h+lpSecurityAttributes], rax
0x180064db8  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography\\DRM_"...
0x180064dbf  lea     rax, [rsp+288h+SubKey]
0x180064dc4  mov     [rsp+288h+samDesired], 208h
0x180064dcc  xor     r9d, r9d
0x180064dcf  mov     qword ptr [rsp+288h+dwOptions], rax
0x180064dd4  xor     edx, edx
0x180064dd6  lea     rcx, aDrmRng; "DRM_RNG"
0x180064ddd  call    cs:__imp_RtlGetPersistedStateLocation
0x180064de4  nop     dword ptr [rax+rax+00h]
0x180064de9  test    eax, eax
0x180064deb  js      short loc_180064E42
0x180064ded  lea     rax, [rsp+288h+dwDisposition]
0x180064df2  mov     [rsp+288h+dwDisposition], 0
0x180064dfa  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x180064dff  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180064e04  mov     [rsp+288h+phkResult], rdi; phkResult
0x180064e09  xor     r9d, r9d; lpClass
0x180064e0c  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180064e15  xor     r8d, r8d; Reserved
0x180064e18  mov     [rsp+288h+samDesired], ebx; samDesired
0x180064e1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064e23  mov     [rsp+288h+dwOptions], 0; dwOptions
0x180064e2b  call    cs:__imp_RegCreateKeyExW
0x180064e32  nop     dword ptr [rax+rax+00h]
0x180064e37  xor     ecx, ecx
0x180064e39  test    eax, eax
0x180064e3b  setz    cl
0x180064e3e  mov     eax, ecx
0x180064e40  jmp     short loc_180064E44
0x180064e42  xor     eax, eax
0x180064e44  mov     rcx, [rsp+288h+var_18]
0x180064e4c  xor     rcx, rsp; StackCookie
0x180064e4f  call    __security_check_cookie
0x180064e54  mov     rbx, [rsp+288h+arg_10]
0x180064e5c  add     rsp, 280h
0x180064e63  pop     rdi
0x180064e64  retn
```
