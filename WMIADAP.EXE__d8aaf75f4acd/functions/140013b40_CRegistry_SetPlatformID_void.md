# CRegistry::SetPlatformID(void)

- ea: `0x140013b40`
- end: `0x140013ba0`
- name: `?SetPlatformID@CRegistry@@CAHXZ`
- size: `96`
- prototype: `BOOL(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011be0`

## callees

- `0x140001a6f`
- `0x140014ad0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x140013b78`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x140013b78`

## pseudocode

```c
BOOL CRegistry::SetPlatformID(void)
{
  BOOL result; // eax
  _OSVERSIONINFOA VersionInformation; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  VersionInformation.dwOSVersionInfoSize = 148;
  result = GetVersionExA(&VersionInformation);
  CRegistry::s_dwPlatform = VersionInformation.dwPlatformId;
  return result;
}

```

## disassembly

```asm
0x140013b40  sub     rsp, 0D8h
0x140013b47  mov     rax, cs:__security_cookie
0x140013b4e  xor     rax, rsp
0x140013b51  mov     [rsp+0D8h+var_18], rax
0x140013b59  xor     edx, edx; Val
0x140013b5b  lea     rcx, [rsp+0D8h+VersionInformation.dwMajorVersion]; void *
0x140013b60  mov     r8d, 90h; Size
0x140013b66  call    memset_0
0x140013b6b  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x140013b70  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], 94h
0x140013b78  call    cs:__imp_GetVersionExA
0x140013b7e  mov     ecx, [rsp+0D8h+VersionInformation.dwPlatformId]
0x140013b82  mov     cs:?s_dwPlatform@CRegistry@@0KA, ecx; ulong CRegistry::s_dwPlatform
0x140013b88  mov     rcx, [rsp+0D8h+var_18]
0x140013b90  xor     rcx, rsp; StackCookie
0x140013b93  call    __security_check_cookie
0x140013b98  add     rsp, 0D8h
0x140013b9f  retn
```
