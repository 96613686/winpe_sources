# winreGetPrereleaseVersion

- ea: `0x180031e88`
- end: `0x180031f9d`
- name: `winreGetPrereleaseVersion`
- size: `277`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800298cc`
- `0x18002da38`

## callees

- `0x1800059fc`
- `0x180031e88`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180031f2d`
- `ADVAPI32!RegQueryValueExW` at `0x180031f2d`
- `ADVAPI32!RegOpenKeyExW` at `0x180031edd`
- `ADVAPI32!RegOpenKeyExW` at `0x180031edd`
- `ADVAPI32!RegCloseKey` at `0x180031f7d`
- `ADVAPI32!RegCloseKey` at `0x180031f7d`

## string_xrefs

- `0x180031eec`: `RegOpenKeyEx(CurrentVersion) failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetPrereleaseVersion(LPBYTE lpData)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 1u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    UnattendLogW(1, L"RegOpenKeyEx(CurrentVersion) failed: 0x%x", v2);
  }
  else
  {
    cbData = 604;
    v4 = RegQueryValueExW(hKey, L"BuildLabEx", 0, &Type, lpData, &cbData);
    v3 = v4;
    if ( v4 )
    {
      UnattendLogW(1, L"RegQueryValueEx failed: 0x%x", v4);
    }
    else if ( Type != 1 || !cbData )
    {
      UnattendLogW(1, L"Inavlid Reg value type");
      v3 = 1010;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180031e88  mov     r11, rsp
0x180031e8b  mov     [r11+10h], rbx
0x180031e8f  push    rdi
0x180031e90  sub     rsp, 50h
0x180031e94  mov     rax, cs:__security_cookie
0x180031e9b  xor     rax, rsp
0x180031e9e  mov     [rsp+58h+var_18], rax
0x180031ea3  mov     rdi, rcx
0x180031ea6  mov     qword ptr [r11-28h], 0
0x180031eae  lea     rax, [r11-28h]
0x180031eb2  mov     [rsp+58h+Type], 0
0x180031eba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031ec1  mov     [r11-38h], rax
0x180031ec5  mov     r9d, 1; samDesired
0x180031ecb  mov     [rsp+58h+cbData], 0
0x180031ed3  xor     r8d, r8d; ulOptions
0x180031ed6  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x180031edd  call    cs:__imp_RegOpenKeyExW
0x180031ee3  mov     ebx, eax
0x180031ee5  test    eax, eax
0x180031ee7  jz      short loc_180031F02
0x180031ee9  mov     r8d, eax
0x180031eec  lea     rdx, aRegopenkeyexCu; "RegOpenKeyEx(CurrentVersion) failed: 0x"...
0x180031ef3  mov     ecx, 1
0x180031ef8  call    UnattendLogW
0x180031efd  jmp     loc_180031F83
0x180031f02  mov     rcx, [rsp+58h+hKey]; hKey
0x180031f07  lea     rax, [rsp+58h+cbData]
0x180031f0c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180031f11  lea     r9, [rsp+58h+Type]; lpType
0x180031f16  xor     r8d, r8d; lpReserved
0x180031f19  mov     [rsp+58h+lpData], rdi; lpData
0x180031f1e  lea     rdx, aBuildlabex; "BuildLabEx"
0x180031f25  mov     [rsp+58h+cbData], 25Ch
0x180031f2d  call    cs:__imp_RegQueryValueExW
0x180031f33  mov     ebx, eax
0x180031f35  test    eax, eax
0x180031f37  jz      short loc_180031F4F
0x180031f39  mov     r8d, eax
0x180031f3c  lea     rdx, aRegqueryvaluee_0; "RegQueryValueEx failed: 0x%x"
0x180031f43  mov     ecx, 1
0x180031f48  call    UnattendLogW
0x180031f4d  jmp     short loc_180031F73
0x180031f4f  cmp     [rsp+58h+Type], 1
0x180031f54  jnz     short loc_180031F5D
0x180031f56  cmp     [rsp+58h+cbData], 1
0x180031f5b  jnb     short loc_180031F73
0x180031f5d  lea     rdx, aInavlidRegValu; "Inavlid Reg value type"
0x180031f64  mov     ecx, 1
0x180031f69  call    UnattendLogW
0x180031f6e  mov     ebx, 3F2h
0x180031f73  mov     rcx, [rsp+58h+hKey]; hKey
0x180031f78  test    rcx, rcx
0x180031f7b  jz      short loc_180031F83
0x180031f7d  call    cs:__imp_RegCloseKey
0x180031f83  mov     eax, ebx
0x180031f85  mov     rcx, [rsp+58h+var_18]
0x180031f8a  xor     rcx, rsp; StackCookie
0x180031f8d  call    __security_check_cookie
0x180031f92  mov     rbx, [rsp+58h+arg_8]
0x180031f97  add     rsp, 50h
0x180031f9b  pop     rdi
0x180031f9c  retn
```
