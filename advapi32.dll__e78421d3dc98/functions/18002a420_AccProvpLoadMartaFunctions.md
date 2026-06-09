# AccProvpLoadMartaFunctions

- ea: `0x18002a420`
- end: `0x18002a579`
- name: `AccProvpLoadMartaFunctions`
- size: `345`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180029900`
- `0x1800299a0`
- `0x180029aa0`
- `0x18002a088`
- `0x180048de0`
- `0x180048f60`
- `0x180049020`
- `0x1800490b0`
- `0x180049140`
- `0x1800491f0`
- `0x1800494a0`

## callees

- `0x18002a2f4`
- `0x18002a420`
- `0x180066010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a46a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a46a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a480`
- `KERNEL32!LocalFree` at `0x18002a48e`
- `KERNEL32!LocalFree` at `0x18002a48e`
- `KERNEL32!EnterCriticalSection` at `0x18002a517`
- `KERNEL32!EnterCriticalSection` at `0x18002a517`
- `KERNEL32!LeaveCriticalSection` at `0x18002a542`
- `KERNEL32!LeaveCriticalSection` at `0x18002a542`
- `KERNEL32!GetLastError` at `0x18002a554`
- `KERNEL32!GetLastError` at `0x18002a554`
- `KERNEL32!GetProcAddress` at `0x18002a4f8`
- `KERNEL32!GetProcAddress` at `0x18002a4f8`
- `KERNEL32!FreeLibrary` at `0x18002a56e`
- `KERNEL32!FreeLibrary` at `0x18002a56e`
- `KERNEL32!LoadLibraryExW` at `0x18002a4e0`
- `KERNEL32!LoadLibraryExW` at `0x18002a4e0`
- `KERNEL32!SetLastError` at `0x18002a49f`
- `KERNEL32!SetLastError` at `0x18002a49f`

## string_xrefs

- `0x18002a45a`: `System\CurrentControlSet\Control\LSA\AccessProviders`
- `0x18002a4ee`: `GetMartaExtensionInterface`
- `0x18002a4be`: `MartaExtension`

## pseudocode

```c
__int64 AccProvpLoadMartaFunctions()
{
  WCHAR *v0; // rdi
  HMODULE v1; // rsi
  unsigned int LastError; // ebx
  unsigned int StringFromRegistry; // eax
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rax
  __int64 v7; // rbp
  signed __int32 v8[18]; // [rsp+0h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  v0 = 0;
  hKey = 0;
  lpLibFileName = 0;
  if ( gNtMartaInfo )
    return 0;
  v1 = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Control\\LSA\\AccessProviders",
                0,
                0x20019u,
                &hKey);
  if ( !LastError )
  {
    StringFromRegistry = AccProvpGetStringFromRegistry(hKey, L"MartaExtension", (HLOCAL *)&lpLibFileName);
    v0 = (WCHAR *)lpLibFileName;
    LastError = StringFromRegistry;
    if ( !StringFromRegistry )
    {
      Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
      v1 = Library;
      if ( Library && (ProcAddress = GetProcAddress(Library, "GetMartaExtensionInterface")) != 0 )
      {
        v7 = ProcAddress();
        if ( v7 )
        {
          EnterCriticalSection(&NtMartaLoadCritical);
          if ( !gNtMartaInfo )
          {
            qword_1800A2048 = v7;
            _InterlockedOr(v8, LastError);
            gNtMartaInfo = v1;
            v1 = 0;
          }
          LeaveCriticalSection(&NtMartaLoadCritical);
        }
        else
        {
          LastError = 50;
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
    LocalFree(v0);
  if ( v1 )
    FreeLibrary(v1);
  SetLastError(LastError);
  return LastError;
}

```

## disassembly

```asm
0x18002a420  mov     r11, rsp
0x18002a423  mov     [r11+18h], rbx
0x18002a427  push    rbp
0x18002a428  push    rsi
0x18002a429  push    rdi
0x18002a42a  sub     rsp, 30h
0x18002a42e  xor     edi, edi
0x18002a430  mov     qword ptr [r11+10h], 0
0x18002a438  cmp     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, rdi; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002a43f  mov     [r11+8], rdi
0x18002a443  jnz     loc_18002A54D
0x18002a449  lea     rax, [r11+10h]
0x18002a44d  mov     r9d, 20019h; samDesired
0x18002a453  xor     r8d, r8d; ulOptions
0x18002a456  mov     [r11-28h], rax
0x18002a45a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\LSA"...
0x18002a461  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a468  xor     esi, esi
0x18002a46a  call    cs:__imp_RegOpenKeyExW
0x18002a470  mov     ebx, eax
0x18002a472  test    eax, eax
0x18002a474  jz      short loc_18002A4B4
0x18002a476  mov     rcx, [rsp+48h+hKey]; hKey
0x18002a47b  test    rcx, rcx
0x18002a47e  jz      short loc_18002A486
0x18002a480  call    cs:__imp_RegCloseKey
0x18002a486  test    rdi, rdi
0x18002a489  jz      short loc_18002A494
0x18002a48b  mov     rcx, rdi; hMem
0x18002a48e  call    cs:__imp_LocalFree
0x18002a494  test    rsi, rsi
0x18002a497  jnz     loc_18002A56B
0x18002a49d  mov     ecx, ebx; dwErrCode
0x18002a49f  call    cs:__imp_SetLastError
0x18002a4a5  mov     eax, ebx
0x18002a4a7  mov     rbx, [rsp+48h+arg_10]
0x18002a4ac  add     rsp, 30h
0x18002a4b0  pop     rdi
0x18002a4b1  pop     rsi
0x18002a4b2  pop     rbp
0x18002a4b3  retn
0x18002a4b4  mov     rcx, [rsp+48h+hKey]; hKey
0x18002a4b9  lea     r8, [rsp+48h+lpLibFileName]
0x18002a4be  lea     rdx, aMartaextension; "MartaExtension"
0x18002a4c5  call    AccProvpGetStringFromRegistry
0x18002a4ca  mov     rdi, [rsp+48h+lpLibFileName]
0x18002a4cf  mov     ebx, eax
0x18002a4d1  test    eax, eax
0x18002a4d3  jnz     short loc_18002A476
0x18002a4d5  xor     edx, edx; hFile
0x18002a4d7  mov     r8d, 800h; dwFlags
0x18002a4dd  mov     rcx, rdi; lpLibFileName
0x18002a4e0  call    cs:__imp_LoadLibraryExW
0x18002a4e6  mov     rsi, rax
0x18002a4e9  test    rax, rax
0x18002a4ec  jz      short loc_18002A554
0x18002a4ee  lea     rdx, aGetmartaextens; "GetMartaExtensionInterface"
0x18002a4f5  mov     rcx, rax; hModule
0x18002a4f8  call    cs:__imp_GetProcAddress
0x18002a4fe  test    rax, rax
0x18002a501  jz      short loc_18002A554
0x18002a503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a508  mov     rbp, rax
0x18002a50b  test    rax, rax
0x18002a50e  jz      short loc_18002A561
0x18002a510  lea     rcx, ?NtMartaLoadCritical@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a517  call    cs:__imp_EnterCriticalSection
0x18002a51d  cmp     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, 0; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002a525  jnz     short loc_18002A53B
0x18002a527  mov     cs:qword_1800A2048, rbp
0x18002a52e  lock or [rsp+48h+var_48], ebx
0x18002a532  mov     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, rsi; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002a539  xor     esi, esi
0x18002a53b  lea     rcx, ?NtMartaLoadCritical@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a542  call    cs:__imp_LeaveCriticalSection
0x18002a548  jmp     loc_18002A476
0x18002a54d  xor     eax, eax
0x18002a54f  jmp     loc_18002A4A7
0x18002a554  call    cs:__imp_GetLastError
0x18002a55a  mov     ebx, eax
0x18002a55c  jmp     loc_18002A476
0x18002a561  mov     ebx, 32h ; '2'
0x18002a566  jmp     loc_18002A476
0x18002a56b  mov     rcx, rsi; hLibModule
0x18002a56e  call    cs:__imp_FreeLibrary
0x18002a574  jmp     loc_18002A49D
```
