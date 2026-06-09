# AccProvpLoadMartaFunctions

- ea: `0x18002dcc8`
- end: `0x18002de5e`
- name: `AccProvpLoadMartaFunctions`
- size: `406`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d060`
- `0x18002d100`
- `0x18002d200`
- `0x18002d8a0`
- `0x18004e9d0`
- `0x18004eb60`
- `0x18004ec30`
- `0x18004ecc0`
- `0x18004ed50`
- `0x18004ee00`
- `0x18004f110`

## callees

- `0x18002db08`
- `0x18002dcc8`
- `0x180074010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dd12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dd12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd2e`
- `KERNEL32!LocalFree` at `0x18002dd42`
- `KERNEL32!LocalFree` at `0x18002dd42`
- `KERNEL32!EnterCriticalSection` at `0x18002dde4`
- `KERNEL32!EnterCriticalSection` at `0x18002dde4`
- `KERNEL32!LeaveCriticalSection` at `0x18002de15`
- `KERNEL32!LeaveCriticalSection` at `0x18002de15`
- `KERNEL32!GetLastError` at `0x18002de2d`
- `KERNEL32!GetLastError` at `0x18002de2d`
- `KERNEL32!GetProcAddress` at `0x18002ddbf`
- `KERNEL32!GetProcAddress` at `0x18002ddbf`
- `KERNEL32!FreeLibrary` at `0x18002de4d`
- `KERNEL32!FreeLibrary` at `0x18002de4d`
- `KERNEL32!LoadLibraryExW` at `0x18002dda1`
- `KERNEL32!LoadLibraryExW` at `0x18002dda1`
- `KERNEL32!SetLastError` at `0x18002dd59`
- `KERNEL32!SetLastError` at `0x18002dd59`

## string_xrefs

- `0x18002dd02`: `System\CurrentControlSet\Control\LSA\AccessProviders`
- `0x18002ddb5`: `GetMartaExtensionInterface`
- `0x18002dd7f`: `MartaExtension`

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
            qword_1800B1048 = v7;
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
0x18002dcc8  mov     r11, rsp
0x18002dccb  mov     [r11+18h], rbx
0x18002dccf  push    rbp
0x18002dcd0  push    rsi
0x18002dcd1  push    rdi
0x18002dcd2  sub     rsp, 30h
0x18002dcd6  xor     edi, edi
0x18002dcd8  mov     qword ptr [r11+10h], 0
0x18002dce0  cmp     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, rdi; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002dce7  mov     [r11+8], rdi
0x18002dceb  jnz     loc_18002DE26
0x18002dcf1  lea     rax, [r11+10h]
0x18002dcf5  mov     r9d, 20019h; samDesired
0x18002dcfb  xor     r8d, r8d; ulOptions
0x18002dcfe  mov     [r11-28h], rax
0x18002dd02  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\LSA"...
0x18002dd09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dd10  xor     esi, esi
0x18002dd12  call    cs:__imp_RegOpenKeyExW
0x18002dd19  nop     dword ptr [rax+rax+00h]
0x18002dd1e  mov     ebx, eax
0x18002dd20  test    eax, eax
0x18002dd22  jz      short loc_18002DD75
0x18002dd24  mov     rcx, [rsp+48h+hKey]; hKey
0x18002dd29  test    rcx, rcx
0x18002dd2c  jz      short loc_18002DD3A
0x18002dd2e  call    cs:__imp_RegCloseKey
0x18002dd35  nop     dword ptr [rax+rax+00h]
0x18002dd3a  test    rdi, rdi
0x18002dd3d  jz      short loc_18002DD4E
0x18002dd3f  mov     rcx, rdi; hMem
0x18002dd42  call    cs:__imp_LocalFree
0x18002dd49  nop     dword ptr [rax+rax+00h]
0x18002dd4e  test    rsi, rsi
0x18002dd51  jnz     loc_18002DE4A
0x18002dd57  mov     ecx, ebx; dwErrCode
0x18002dd59  call    cs:__imp_SetLastError
0x18002dd60  nop     dword ptr [rax+rax+00h]
0x18002dd65  mov     eax, ebx
0x18002dd67  mov     rbx, [rsp+48h+arg_10]
0x18002dd6c  add     rsp, 30h
0x18002dd70  pop     rdi
0x18002dd71  pop     rsi
0x18002dd72  pop     rbp
0x18002dd73  retn
0x18002dd75  mov     rcx, [rsp+48h+hKey]; hKey
0x18002dd7a  lea     r8, [rsp+48h+lpLibFileName]
0x18002dd7f  lea     rdx, aMartaextension; "MartaExtension"
0x18002dd86  call    AccProvpGetStringFromRegistry
0x18002dd8b  mov     rdi, [rsp+48h+lpLibFileName]
0x18002dd90  mov     ebx, eax
0x18002dd92  test    eax, eax
0x18002dd94  jnz     short loc_18002DD24
0x18002dd96  xor     edx, edx; hFile
0x18002dd98  mov     r8d, 800h; dwFlags
0x18002dd9e  mov     rcx, rdi; lpLibFileName
0x18002dda1  call    cs:__imp_LoadLibraryExW
0x18002dda8  nop     dword ptr [rax+rax+00h]
0x18002ddad  mov     rsi, rax
0x18002ddb0  test    rax, rax
0x18002ddb3  jz      short loc_18002DE2D
0x18002ddb5  lea     rdx, aGetmartaextens; "GetMartaExtensionInterface"
0x18002ddbc  mov     rcx, rax; hModule
0x18002ddbf  call    cs:__imp_GetProcAddress
0x18002ddc6  nop     dword ptr [rax+rax+00h]
0x18002ddcb  test    rax, rax
0x18002ddce  jz      short loc_18002DE2D
0x18002ddd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddd5  mov     rbp, rax
0x18002ddd8  test    rax, rax
0x18002dddb  jz      short loc_18002DE40
0x18002dddd  lea     rcx, ?NtMartaLoadCritical@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002dde4  call    cs:__imp_EnterCriticalSection
0x18002ddeb  nop     dword ptr [rax+rax+00h]
0x18002ddf0  cmp     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, 0; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002ddf8  jnz     short loc_18002DE0E
0x18002ddfa  mov     cs:qword_1800B1048, rbp
0x18002de01  lock or [rsp+48h+var_48], ebx
0x18002de05  mov     cs:?gNtMartaInfo@@3U_MARTA_NTMARTA_INFO@@A, rsi; _MARTA_NTMARTA_INFO gNtMartaInfo
0x18002de0c  xor     esi, esi
0x18002de0e  lea     rcx, ?NtMartaLoadCritical@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002de15  call    cs:__imp_LeaveCriticalSection
0x18002de1c  nop     dword ptr [rax+rax+00h]
0x18002de21  jmp     loc_18002DD24
0x18002de26  xor     eax, eax
0x18002de28  jmp     loc_18002DD67
0x18002de2d  call    cs:__imp_GetLastError
0x18002de34  nop     dword ptr [rax+rax+00h]
0x18002de39  mov     ebx, eax
0x18002de3b  jmp     loc_18002DD24
0x18002de40  mov     ebx, 32h ; '2'
0x18002de45  jmp     loc_18002DD24
0x18002de4a  mov     rcx, rsi; hLibModule
0x18002de4d  call    cs:__imp_FreeLibrary
0x18002de54  nop     dword ptr [rax+rax+00h]
0x18002de59  jmp     loc_18002DD57
```
