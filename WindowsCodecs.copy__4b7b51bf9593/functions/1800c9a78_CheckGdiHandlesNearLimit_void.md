# CheckGdiHandlesNearLimit(void)

- ea: `0x1800c9a78`
- end: `0x1800c9b71`
- name: `?CheckGdiHandlesNearLimit@@YAJXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800802d4`

## callees

- `0x1800c9a78`
- `0x18017ac9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c9a9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c9a9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c9b2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c9b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9b49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9b49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c9af2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c9af2`
- `ext-ms-win-ntuser-misc-l1-1-0!GetGuiResources` at `0x1800c9aa7`
- `ext-ms-win-ntuser-misc-l1-1-0!GetGuiResources` at `0x1800c9aa7`

## pseudocode

```c
__int64 CheckGdiHandlesNearLimit(void)
{
  unsigned int v1; // edi
  HANDLE CurrentProcess; // rax
  DWORD GuiResources; // eax
  unsigned int v4; // ebx
  DWORD v5; // esi
  unsigned int v6; // ebx
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  if ( !(unsigned __int8)IsGetGuiResourcesPresent() )
    return 2147500033LL;
  v1 = -2003292268;
  CurrentProcess = GetCurrentProcess();
  GuiResources = GetGuiResources(CurrentProcess, 0);
  v4 = dword_180265D00;
  v5 = GuiResources;
  if ( GuiResources >= dword_180265D00 )
  {
    if ( !dword_180265D00 )
    {
      hKey = 0;
      v6 = 10000;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows", 0, 1u, &hKey) )
      {
        Type = 0;
        Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"GDIProcessHandleQuota", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
          v6 = Data;
        RegCloseKey(hKey);
      }
      v4 = v6 - (v6 >> 3);
      dword_180265D00 = v4;
    }
    if ( v5 >= v4 )
      return (unsigned int)-2147024882;
  }
  return v1;
}

```

## disassembly

```asm
0x1800c9a78  push    rbp
0x1800c9a7a  push    rbx
0x1800c9a7b  push    rsi
0x1800c9a7c  push    rdi
0x1800c9a7d  mov     rbp, rsp
0x1800c9a80  sub     rsp, 38h
0x1800c9a84  call    IsGetGuiResourcesPresent
0x1800c9a89  test    al, al
0x1800c9a8b  jnz     short loc_1800C9A97
0x1800c9a8d  mov     eax, 80004001h
0x1800c9a92  jmp     loc_1800C9B68
0x1800c9a97  mov     edi, 88982F94h
0x1800c9a9c  call    cs:__imp_GetCurrentProcess
0x1800c9aa2  mov     rcx, rax; hProcess
0x1800c9aa5  xor     edx, edx; uiFlags
0x1800c9aa7  call    cs:__imp_GetGuiResources
0x1800c9aad  mov     ebx, cs:dword_180265D00
0x1800c9ab3  mov     esi, eax
0x1800c9ab5  cmp     eax, ebx
0x1800c9ab7  jb      loc_1800C9B66
0x1800c9abd  test    ebx, ebx
0x1800c9abf  jnz     loc_1800C9B5C
0x1800c9ac5  lea     rax, [rbp+hKey]
0x1800c9ac9  mov     [rbp+hKey], 0
0x1800c9ad1  mov     r9d, 1; samDesired
0x1800c9ad7  mov     [rsp+38h+phkResult], rax; phkResult
0x1800c9adc  xor     r8d, r8d; ulOptions
0x1800c9adf  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800c9ae6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c9aed  mov     ebx, 2710h
0x1800c9af2  call    cs:__imp_RegOpenKeyExW
0x1800c9af8  test    eax, eax
0x1800c9afa  jnz     short loc_1800C9B4F
0x1800c9afc  mov     rcx, [rbp+hKey]; hKey
0x1800c9b00  lea     r9, [rbp+Type]; lpType
0x1800c9b04  mov     [rbp+Type], eax
0x1800c9b07  lea     rdx, aGdiprocesshand; "GDIProcessHandleQuota"
0x1800c9b0e  mov     [rbp+Data], eax
0x1800c9b11  xor     r8d, r8d; lpReserved
0x1800c9b14  lea     rax, [rbp+cbData]
0x1800c9b18  mov     [rbp+cbData], 4
0x1800c9b1f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800c9b24  lea     rax, [rbp+Data]
0x1800c9b28  mov     [rsp+38h+phkResult], rax; lpData
0x1800c9b2d  call    cs:__imp_RegQueryValueExW
0x1800c9b33  test    eax, eax
0x1800c9b35  jnz     short loc_1800C9B45
0x1800c9b37  cmp     [rbp+Type], 4
0x1800c9b3b  jnz     short loc_1800C9B45
0x1800c9b3d  mov     eax, [rbp+Data]
0x1800c9b40  test    eax, eax
0x1800c9b42  cmovnz  ebx, eax
0x1800c9b45  mov     rcx, [rbp+hKey]; hKey
0x1800c9b49  call    cs:__imp_RegCloseKey
0x1800c9b4f  mov     ecx, ebx
0x1800c9b51  shr     ecx, 3
0x1800c9b54  sub     ebx, ecx
0x1800c9b56  mov     cs:dword_180265D00, ebx
0x1800c9b5c  cmp     esi, ebx
0x1800c9b5e  mov     eax, 8007000Eh
0x1800c9b63  cmovnb  edi, eax
0x1800c9b66  mov     eax, edi
0x1800c9b68  add     rsp, 38h
0x1800c9b6c  pop     rdi
0x1800c9b6d  pop     rsi
0x1800c9b6e  pop     rbx
0x1800c9b6f  pop     rbp
0x1800c9b70  retn
```
