# InitializeUserCalendars(void)

- ea: `0x180041ef8`
- end: `0x180042014`
- name: `?InitializeUserCalendars@@YAXXZ`
- size: `284`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002adc8`

## callees

- `0x180041ef8`
- `0x18004d900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180041f7f`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180041f7f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180041fd9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180041fd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041fe7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041fe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180041f4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180041f4b`

## pseudocode

```c
void InitializeUserCalendars(void)
{
  int v0; // ebx
  DWORD v1; // edx
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-30h] BYREF
  char String[32]; // [rsp+58h] [rbp-28h] BYREF

  hKey = 0;
  if ( !dword_1800C3608 )
  {
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\OLEAUT\\UserEra", 0, 9u, &hKey) )
    {
      v0 = 0;
      v1 = 0;
      ftLastWriteTime = 0;
      while ( 1 )
      {
        cchName = 32;
        if ( RegEnumKeyExA(hKey, v1, String, &cchName, 0, 0, 0, &ftLastWriteTime) )
          break;
        if ( (unsigned __int16)atoi(String) == 1028 )
          dword_1800C360C |= 1u;
        ftLastWriteTime = 0;
        v1 = ++v0;
      }
      RegCloseKey(hKey);
    }
    dword_1800C3608 = 1;
  }
}

```

## disassembly

```asm
0x180041ef8  mov     [rsp-8+arg_0], rbx
0x180041efd  push    rbp
0x180041efe  mov     rbp, rsp
0x180041f01  sub     rsp, 80h
0x180041f08  mov     rax, cs:__security_cookie
0x180041f0f  xor     rax, rsp
0x180041f12  mov     [rbp+var_8], rax
0x180041f16  cmp     cs:dword_1800C3608, 0
0x180041f1d  mov     [rbp+hKey], 0
0x180041f25  jnz     loc_180041FF7
0x180041f2b  lea     rax, [rbp+hKey]
0x180041f2f  mov     r9d, 9; samDesired
0x180041f35  xor     r8d, r8d; ulOptions
0x180041f38  mov     [rsp+80h+phkResult], rax; phkResult
0x180041f3d  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\OLEAUT\\UserEra"
0x180041f44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041f4b  call    cs:__imp_RegOpenKeyExA
0x180041f51  test    eax, eax
0x180041f53  jnz     loc_180041FED
0x180041f59  xor     ebx, ebx
0x180041f5b  lea     rax, [rbp+ftLastWriteTime]
0x180041f5f  mov     [rsp+80h+lpftLastWriteTime], rax
0x180041f64  xor     edx, edx
0x180041f66  mov     [rsp+80h+lpcchClass], rbx
0x180041f6b  mov     [rsp+80h+lpClass], rbx
0x180041f70  mov     [rsp+80h+phkResult], rbx
0x180041f75  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], rbx
0x180041f79  jmp     short loc_180041FC6
0x180041f7b  lea     rcx, [rbp+String]; String
0x180041f7f  call    cs:__imp_atoi
0x180041f85  mov     ecx, 404h
0x180041f8a  cmp     ax, cx
0x180041f8d  jnz     short loc_180041F96
0x180041f8f  or      cs:dword_1800C360C, 1
0x180041f96  lea     rax, [rbp+ftLastWriteTime]
0x180041f9a  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], 0
0x180041fa2  mov     [rsp+80h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180041fa7  inc     ebx
0x180041fa9  mov     [rsp+80h+lpcchClass], 0; lpcchClass
0x180041fb2  mov     edx, ebx; dwIndex
0x180041fb4  mov     [rsp+80h+lpClass], 0; lpClass
0x180041fbd  mov     [rsp+80h+phkResult], 0; lpReserved
0x180041fc6  mov     rcx, [rbp+hKey]; hKey
0x180041fca  lea     r9, [rbp+cchName]; lpcchName
0x180041fce  lea     r8, [rbp+String]; lpName
0x180041fd2  mov     [rbp+cchName], 20h ; ' '
0x180041fd9  call    cs:__imp_RegEnumKeyExA
0x180041fdf  test    eax, eax
0x180041fe1  jz      short loc_180041F7B
0x180041fe3  mov     rcx, [rbp+hKey]; hKey
0x180041fe7  call    cs:__imp_RegCloseKey
0x180041fed  mov     cs:dword_1800C3608, 1
0x180041ff7  mov     rcx, [rbp+var_8]
0x180041ffb  xor     rcx, rsp; StackCookie
0x180041ffe  call    __security_check_cookie
0x180042003  mov     rbx, [rsp+80h+arg_0]
0x18004200b  add     rsp, 80h
0x180042012  pop     rbp
0x180042013  retn
```
