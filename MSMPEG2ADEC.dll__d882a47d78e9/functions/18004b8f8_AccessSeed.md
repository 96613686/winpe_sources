# AccessSeed

- ea: `0x18004b8f8`
- end: `0x18004b9ee`
- name: `AccessSeed`
- size: `246`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a97c`
- `0x18004b490`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18004b8f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b9b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b9b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004b965`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004b965`

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
0x18004b8f8  mov     [rsp+arg_10], rbx
0x18004b8fd  push    rdi
0x18004b8fe  sub     rsp, 280h
0x18004b905  mov     rax, cs:__security_cookie
0x18004b90c  xor     rax, rsp
0x18004b90f  mov     [rsp+288h+var_18], rax
0x18004b917  mov     rdi, rdx
0x18004b91a  mov     ebx, ecx
0x18004b91c  xor     edx, edx; Val
0x18004b91e  lea     rcx, [rsp+288h+SubKey]; void *
0x18004b923  mov     r8d, 208h; Size
0x18004b929  call    memset_0
0x18004b92e  lea     rax, [rsp+288h+var_238]
0x18004b933  mov     [rsp+288h+var_238], 0
0x18004b93b  mov     [rsp+288h+lpSecurityAttributes], rax
0x18004b940  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\DRM_"...
0x18004b947  lea     rax, [rsp+288h+SubKey]
0x18004b94c  mov     [rsp+288h+samDesired], 208h
0x18004b954  xor     r9d, r9d
0x18004b957  mov     qword ptr [rsp+288h+dwOptions], rax
0x18004b95c  xor     edx, edx
0x18004b95e  lea     rcx, aDrmRng; "DRM_RNG"
0x18004b965  call    cs:__imp_RtlGetPersistedStateLocation
0x18004b96c  nop     dword ptr [rax+rax+00h]
0x18004b971  test    eax, eax
0x18004b973  js      short loc_18004B9CA
0x18004b975  lea     rax, [rsp+288h+dwDisposition]
0x18004b97a  mov     [rsp+288h+dwDisposition], 0
0x18004b982  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x18004b987  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18004b98c  mov     [rsp+288h+phkResult], rdi; phkResult
0x18004b991  xor     r9d, r9d; lpClass
0x18004b994  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004b99d  xor     r8d, r8d; Reserved
0x18004b9a0  mov     [rsp+288h+samDesired], ebx; samDesired
0x18004b9a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b9ab  mov     [rsp+288h+dwOptions], 0; dwOptions
0x18004b9b3  call    cs:__imp_RegCreateKeyExW
0x18004b9ba  nop     dword ptr [rax+rax+00h]
0x18004b9bf  xor     ecx, ecx
0x18004b9c1  test    eax, eax
0x18004b9c3  setz    cl
0x18004b9c6  mov     eax, ecx
0x18004b9c8  jmp     short loc_18004B9CC
0x18004b9ca  xor     eax, eax
0x18004b9cc  mov     rcx, [rsp+288h+var_18]
0x18004b9d4  xor     rcx, rsp; StackCookie
0x18004b9d7  call    __security_check_cookie
0x18004b9dc  mov     rbx, [rsp+288h+arg_10]
0x18004b9e4  add     rsp, 280h
0x18004b9eb  pop     rdi
0x18004b9ec  retn
```
