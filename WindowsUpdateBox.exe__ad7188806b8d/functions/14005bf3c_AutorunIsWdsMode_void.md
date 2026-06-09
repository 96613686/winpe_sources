# AutorunIsWdsMode(void)

- ea: `0x14005bf3c`
- end: `0x14005c0cc`
- name: `?AutorunIsWdsMode@@YAHXZ`
- size: `400`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013894`

## callees

- `0x140002116`
- `0x14005bf3c`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14005bfdf`
- `ADVAPI32!RegQueryValueExW` at `0x14005bfdf`
- `ADVAPI32!RegOpenKeyExW` at `0x14005bfa6`
- `ADVAPI32!RegOpenKeyExW` at `0x14005bfa6`
- `ADVAPI32!RegCloseKey` at `0x14005bff2`
- `ADVAPI32!RegCloseKey` at `0x14005bff2`
- `KERNEL32!GetWindowsDirectoryW` at `0x14005c020`
- `KERNEL32!GetWindowsDirectoryW` at `0x14005c020`
- `KERNEL32!GetModuleFileNameW` at `0x14005c044`
- `KERNEL32!GetModuleFileNameW` at `0x14005c044`
- `KERNEL32!SetLastError` at `0x14005c000`
- `KERNEL32!SetLastError` at `0x14005c08a`
- `KERNEL32!SetLastError` at `0x14005c000`
- `KERNEL32!SetLastError` at `0x14005c08a`
- `msvcrt!towupper` at `0x14005c059`
- `msvcrt!towupper` at `0x14005c06b`
- `msvcrt!towupper` at `0x14005c059`
- `msvcrt!towupper` at `0x14005c06b`

## pseudocode

```c
__int64 AutorunIsWdsMode(void)
{
  LSTATUS Value; // ebx
  wint_t v1; // di
  wint_t v2; // bx
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !dword_1400A5E0C )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\PXE", 0, 0x20019u, &hKey) || !hKey )
    {
      SetLastError(0);
    }
    else
    {
      Value = RegQueryValueExW(hKey, L"BootServerReply", 0, 0, 0, 0);
      RegCloseKey(hKey);
      SetLastError(0);
      if ( !Value )
      {
        if ( GetWindowsDirectoryW(Buffer, 0x104u) )
        {
          v1 = Buffer[0];
          if ( Buffer[0] )
          {
            if ( GetModuleFileNameW(0, Buffer, 0x104u) )
            {
              v2 = towupper(Buffer[0]);
              if ( v2 == towupper(v1) )
                dword_1400A5E08 = 1;
            }
          }
        }
      }
    }
    dword_1400A5E0C = 1;
  }
  return (unsigned int)dword_1400A5E08;
}

```

## disassembly

```asm
0x14005bf3c  mov     [rsp+arg_0], rbx
0x14005bf41  mov     [rsp+arg_8], rsi
0x14005bf46  push    rdi
0x14005bf47  sub     rsp, 260h
0x14005bf4e  mov     rax, cs:__security_cookie
0x14005bf55  xor     rax, rsp
0x14005bf58  mov     [rsp+268h+var_18], rax
0x14005bf60  xor     edx, edx; Val
0x14005bf62  lea     rcx, [rsp+268h+Buffer]; void *
0x14005bf67  mov     r8d, 208h; Size
0x14005bf6d  call    memset_0
0x14005bf72  xor     esi, esi
0x14005bf74  cmp     cs:dword_1400A5E0C, esi
0x14005bf7a  jnz     loc_14005C0A0
0x14005bf80  lea     rax, [rsp+268h+hKey]
0x14005bf85  mov     [rsp+268h+hKey], rsi
0x14005bf8a  mov     r9d, 20019h; samDesired
0x14005bf90  mov     [rsp+268h+phkResult], rax; phkResult
0x14005bf95  xor     r8d, r8d; ulOptions
0x14005bf98  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\PXE"
0x14005bf9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005bfa6  call    cs:__imp_RegOpenKeyExW
0x14005bfad  nop     dword ptr [rax+rax+00h]
0x14005bfb2  test    eax, eax
0x14005bfb4  jnz     loc_14005C088
0x14005bfba  mov     rcx, [rsp+268h+hKey]; hKey
0x14005bfbf  test    rcx, rcx
0x14005bfc2  jz      loc_14005C088
0x14005bfc8  mov     [rsp+268h+lpcbData], rsi; lpcbData
0x14005bfcd  lea     rdx, aBootserverrepl; "BootServerReply"
0x14005bfd4  xor     r9d, r9d; lpType
0x14005bfd7  mov     [rsp+268h+phkResult], rsi; lpData
0x14005bfdc  xor     r8d, r8d; lpReserved
0x14005bfdf  call    cs:__imp_RegQueryValueExW
0x14005bfe6  nop     dword ptr [rax+rax+00h]
0x14005bfeb  mov     rcx, [rsp+268h+hKey]; hKey
0x14005bff0  mov     ebx, eax
0x14005bff2  call    cs:__imp_RegCloseKey
0x14005bff9  nop     dword ptr [rax+rax+00h]
0x14005bffe  xor     ecx, ecx; dwErrCode
0x14005c000  call    cs:__imp_SetLastError
0x14005c007  nop     dword ptr [rax+rax+00h]
0x14005c00c  test    ebx, ebx
0x14005c00e  jnz     loc_14005C096
0x14005c014  mov     ebx, 104h
0x14005c019  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x14005c01e  mov     edx, ebx; uSize
0x14005c020  call    cs:__imp_GetWindowsDirectoryW
0x14005c027  nop     dword ptr [rax+rax+00h]
0x14005c02c  test    eax, eax
0x14005c02e  jz      short loc_14005C096
0x14005c030  movzx   edi, [rsp+268h+Buffer]
0x14005c035  test    di, di
0x14005c038  jz      short loc_14005C096
0x14005c03a  mov     r8d, ebx; nSize
0x14005c03d  lea     rdx, [rsp+268h+Buffer]; lpFilename
0x14005c042  xor     ecx, ecx; hModule
0x14005c044  call    cs:__imp_GetModuleFileNameW
0x14005c04b  nop     dword ptr [rax+rax+00h]
0x14005c050  test    eax, eax
0x14005c052  jz      short loc_14005C096
0x14005c054  movzx   ecx, [rsp+268h+Buffer]; C
0x14005c059  call    cs:__imp_towupper
0x14005c060  nop     dword ptr [rax+rax+00h]
0x14005c065  movzx   ecx, di; C
0x14005c068  movzx   ebx, ax
0x14005c06b  call    cs:__imp_towupper
0x14005c072  nop     dword ptr [rax+rax+00h]
0x14005c077  cmp     bx, ax
0x14005c07a  jnz     short loc_14005C096
0x14005c07c  mov     cs:dword_1400A5E08, 1
0x14005c086  jmp     short loc_14005C096
0x14005c088  xor     ecx, ecx; dwErrCode
0x14005c08a  call    cs:__imp_SetLastError
0x14005c091  nop     dword ptr [rax+rax+00h]
0x14005c096  mov     cs:dword_1400A5E0C, 1
0x14005c0a0  mov     eax, cs:dword_1400A5E08
0x14005c0a6  mov     rcx, [rsp+268h+var_18]
0x14005c0ae  xor     rcx, rsp; StackCookie
0x14005c0b1  call    __security_check_cookie
0x14005c0b6  lea     r11, [rsp+268h+var_8]
0x14005c0be  mov     rbx, [r11+10h]
0x14005c0c2  mov     rsi, [r11+18h]
0x14005c0c6  mov     rsp, r11
0x14005c0c9  pop     rdi
0x14005c0ca  retn
```
