# CheckGdiHandlesNearLimit(void)

- ea: `0x1800cbf54`
- end: `0x1800cc06c`
- name: `?CheckGdiHandlesNearLimit@@YAJXZ`
- size: `280`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002015c`

## callees

- `0x1800cbf54`
- `0x18017dbac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cbf78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cbf78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cc01b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cc01b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cc03d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cc03d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cbfda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cbfda`
- `ext-ms-win-ntuser-misc-l1-1-0!GetGuiResources` at `0x1800cbf89`
- `ext-ms-win-ntuser-misc-l1-1-0!GetGuiResources` at `0x1800cbf89`

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
  v4 = dword_180269E30;
  v5 = GuiResources;
  if ( GuiResources >= dword_180269E30 )
  {
    if ( !dword_180269E30 )
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
      dword_180269E30 = v4;
    }
    if ( v5 >= v4 )
      return (unsigned int)-2147024882;
  }
  return v1;
}

```

## disassembly

```asm
0x1800cbf54  push    rbp
0x1800cbf56  push    rbx
0x1800cbf57  push    rsi
0x1800cbf58  push    rdi
0x1800cbf59  mov     rbp, rsp
0x1800cbf5c  sub     rsp, 38h
0x1800cbf60  call    IsGetGuiResourcesPresent
0x1800cbf65  test    al, al
0x1800cbf67  jnz     short loc_1800CBF73
0x1800cbf69  mov     eax, 80004001h
0x1800cbf6e  jmp     loc_1800CC062
0x1800cbf73  mov     edi, 88982F94h
0x1800cbf78  call    cs:__imp_GetCurrentProcess
0x1800cbf7f  nop     dword ptr [rax+rax+00h]
0x1800cbf84  mov     rcx, rax; hProcess
0x1800cbf87  xor     edx, edx; uiFlags
0x1800cbf89  call    cs:__imp_GetGuiResources
0x1800cbf90  nop     dword ptr [rax+rax+00h]
0x1800cbf95  mov     ebx, cs:dword_180269E30
0x1800cbf9b  mov     esi, eax
0x1800cbf9d  cmp     eax, ebx
0x1800cbf9f  jb      loc_1800CC060
0x1800cbfa5  test    ebx, ebx
0x1800cbfa7  jnz     loc_1800CC056
0x1800cbfad  lea     rax, [rbp+hKey]
0x1800cbfb1  mov     [rbp+hKey], 0
0x1800cbfb9  mov     r9d, 1; samDesired
0x1800cbfbf  mov     [rsp+38h+phkResult], rax; phkResult
0x1800cbfc4  xor     r8d, r8d; ulOptions
0x1800cbfc7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800cbfce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cbfd5  mov     ebx, 2710h
0x1800cbfda  call    cs:__imp_RegOpenKeyExW
0x1800cbfe1  nop     dword ptr [rax+rax+00h]
0x1800cbfe6  test    eax, eax
0x1800cbfe8  jnz     short loc_1800CC049
0x1800cbfea  mov     rcx, [rbp+hKey]; hKey
0x1800cbfee  lea     r9, [rbp+Type]; lpType
0x1800cbff2  mov     [rbp+Type], eax
0x1800cbff5  lea     rdx, aGdiprocesshand; "GDIProcessHandleQuota"
0x1800cbffc  mov     [rbp+Data], eax
0x1800cbfff  xor     r8d, r8d; lpReserved
0x1800cc002  lea     rax, [rbp+cbData]
0x1800cc006  mov     [rbp+cbData], 4
0x1800cc00d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800cc012  lea     rax, [rbp+Data]
0x1800cc016  mov     [rsp+38h+phkResult], rax; lpData
0x1800cc01b  call    cs:__imp_RegQueryValueExW
0x1800cc022  nop     dword ptr [rax+rax+00h]
0x1800cc027  test    eax, eax
0x1800cc029  jnz     short loc_1800CC039
0x1800cc02b  cmp     [rbp+Type], 4
0x1800cc02f  jnz     short loc_1800CC039
0x1800cc031  mov     eax, [rbp+Data]
0x1800cc034  test    eax, eax
0x1800cc036  cmovnz  ebx, eax
0x1800cc039  mov     rcx, [rbp+hKey]; hKey
0x1800cc03d  call    cs:__imp_RegCloseKey
0x1800cc044  nop     dword ptr [rax+rax+00h]
0x1800cc049  mov     ecx, ebx
0x1800cc04b  shr     ecx, 3
0x1800cc04e  sub     ebx, ecx
0x1800cc050  mov     cs:dword_180269E30, ebx
0x1800cc056  cmp     esi, ebx
0x1800cc058  mov     eax, 8007000Eh
0x1800cc05d  cmovnb  edi, eax
0x1800cc060  mov     eax, edi
0x1800cc062  add     rsp, 38h
0x1800cc066  pop     rdi
0x1800cc067  pop     rsi
0x1800cc068  pop     rbx
0x1800cc069  pop     rbp
0x1800cc06a  retn
```
