# GetPhoneOSVersion(BuildVersion *)

- ea: `0x18001791c`
- end: `0x1800179c1`
- name: `?GetPhoneOSVersion@@YAJPEAUBuildVersion@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct BuildVersion *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180017a34`
- `0x1800183b4`

## callees

- `0x180002da8`
- `0x18001791c`
- `0x18002120a`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017963`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017959`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017959`

## string_xrefs

- `0x18001797e`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\PhoneOsVersion.h`

## pseudocode

```c
__int64 __fastcall GetPhoneOSVersion(struct BuildVersion *a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  DWORD dwMinorVersion; // ecx
  DWORD dwBuildNumber; // edx
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    dwMinorVersion = VersionInformation.dwMinorVersion;
    dwBuildNumber = VersionInformation.dwBuildNumber;
    *(_DWORD *)a1 = VersionInformation.dwMajorVersion;
    result = 0;
    *((_DWORD *)a1 + 1) = dwMinorVersion;
    *((_DWORD *)a1 + 2) = dwBuildNumber;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(v3, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\PhoneOsVersion.h", 31);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18001791c  push    rbx
0x18001791e  sub     rsp, 160h
0x180017925  mov     rax, cs:__security_cookie
0x18001792c  xor     rax, rsp
0x18001792f  mov     [rsp+168h+var_18], rax
0x180017937  mov     rbx, rcx
0x18001793a  xor     edx, edx; Val
0x18001793c  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x180017941  mov     r8d, 118h; Size
0x180017947  call    memset_0
0x18001794c  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x180017951  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180017959  call    cs:__imp_GetVersionExW
0x18001795f  test    eax, eax
0x180017961  jnz     short loc_180017992
0x180017963  call    cs:__imp_GetLastError
0x180017969  mov     ebx, eax
0x18001796b  test    eax, eax
0x18001796d  jle     short loc_180017978
0x18001796f  movzx   ebx, ax
0x180017972  or      ebx, 80070000h
0x180017978  mov     r9d, 1Fh
0x18001797e  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180017985  xor     edx, edx
0x180017987  mov     ecx, ebx
0x180017989  call    Log_HREvent
0x18001798e  mov     eax, ebx
0x180017990  jmp     short loc_1800179A8
0x180017992  mov     eax, [rsp+168h+VersionInformation.dwMajorVersion]
0x180017996  mov     ecx, [rsp+168h+VersionInformation.dwMinorVersion]
0x18001799a  mov     edx, [rsp+168h+VersionInformation.dwBuildNumber]
0x18001799e  mov     [rbx], eax
0x1800179a0  xor     eax, eax
0x1800179a2  mov     [rbx+4], ecx
0x1800179a5  mov     [rbx+8], edx
0x1800179a8  mov     rcx, [rsp+168h+var_18]
0x1800179b0  xor     rcx, rsp; StackCookie
0x1800179b3  call    __security_check_cookie
0x1800179b8  add     rsp, 160h
0x1800179bf  pop     rbx
0x1800179c0  retn
```
