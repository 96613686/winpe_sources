# wWinMain

- ea: `0x140001c40`
- end: `0x140001cf5`
- name: `wWinMain`
- size: `181`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001ac0`

## callees

- `0x140001540`
- `0x140001c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400023e4`
- `KERNEL32!GetProcAddress` at `0x1400023f5`
- `KERNEL32!GetProcAddress` at `0x1400023f5`
- `KERNEL32!LoadLibraryExW` at `0x1400023d4`
- `KERNEL32!LoadLibraryExW` at `0x1400023d4`
- `ADVAPI32!RegCloseKey` at `0x140001cca`
- `ADVAPI32!RegCloseKey` at `0x140001cca`
- `ADVAPI32!RegOpenKeyExW` at `0x140001c81`
- `ADVAPI32!RegOpenKeyExW` at `0x140001c81`
- `ADVAPI32!RegQueryValueExW` at `0x140001cbd`
- `ADVAPI32!RegQueryValueExW` at `0x140001cbd`
- `ppcore!PPMain` at `0x140001ce7`
- `ppcore!PPMain` at `0x140001ce7`

## string_xrefs

- `0x140001cb1`: `PPCoreTDLL`
- `0x1400023c7`: `ppcoret.dll`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LSTATUS v5; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF

  cbData = 4;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Office\\16.0\\PowerPoint", 0, 1u, &hKey)
    || !hKey
    || (v5 = RegQueryValueExW(hKey, L"PPCoreTDLL", 0, &Type, Data, &cbData), RegCloseKey(hKey), v5)
    || Type != 4
    || *(_DWORD *)Data != 1 )
  {
    PPMain(lpCmdLine, ProcessStartTimeNanosecondsSinceEpoch);
    return 0;
  }
  Library = LoadLibraryExW(L"ppcoret.dll", 0, 0x1000u);
  if ( !Library )
    return GetLastError();
  ProcAddress = GetProcAddress(Library, "PPMain");
  if ( ProcAddress )
  {
    ((void (__fastcall *)(LPWSTR, __int64))ProcAddress)(lpCmdLine, ProcessStartTimeNanosecondsSinceEpoch);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140001c40  push    rbx
0x140001c42  sub     rsp, 50h
0x140001c46  xor     eax, eax
0x140001c48  mov     [rsp+58h+cbData], 4
0x140001c50  mov     [rsp+58h+hKey], rax
0x140001c55  lea     rdx, SubKey; "Software\\Microsoft\\Office\\16.0\\Powe"...
0x140001c5c  mov     [rsp+58h+Type], eax
0x140001c60  mov     rbx, r8
0x140001c63  mov     dword ptr [rsp+58h+Data], eax
0x140001c67  mov     r9d, 1; samDesired
0x140001c6d  lea     rax, [rsp+58h+hKey]
0x140001c72  xor     r8d, r8d; ulOptions
0x140001c75  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140001c7c  mov     [rsp+58h+phkResult], rax; phkResult
0x140001c81  call    cs:__imp_RegOpenKeyExW
0x140001c87  test    eax, eax
0x140001c89  jnz     short loc_140001CDD
0x140001c8b  mov     rcx, [rsp+58h+hKey]; hKey
0x140001c90  test    rcx, rcx
0x140001c93  jz      short loc_140001CDD
0x140001c95  lea     rax, [rsp+58h+cbData]
0x140001c9a  mov     [rsp+58h+arg_0], rdi
0x140001c9f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140001ca4  lea     r9, [rsp+58h+Type]; lpType
0x140001ca9  lea     rax, [rsp+58h+Data]
0x140001cae  xor     r8d, r8d; lpReserved
0x140001cb1  lea     rdx, ValueName; "PPCoreTDLL"
0x140001cb8  mov     [rsp+58h+phkResult], rax; lpData
0x140001cbd  call    cs:__imp_RegQueryValueExW
0x140001cc3  mov     rcx, [rsp+58h+hKey]; hKey
0x140001cc8  mov     edi, eax
0x140001cca  call    cs:__imp_RegCloseKey
0x140001cd0  test    edi, edi
0x140001cd2  mov     rdi, [rsp+58h+arg_0]
0x140001cd7  jz      loc_1400023AF
0x140001cdd  mov     rdx, cs:?ProcessStartTimeNanosecondsSinceEpoch@@3_JA; __int64 ProcessStartTimeNanosecondsSinceEpoch
0x140001ce4  mov     rcx, rbx
0x140001ce7  call    cs:__imp_PPMain
0x140001ced  xor     eax, eax
0x140001cef  jmp     loc_140002405
0x1400023af  cmp     [rsp+58h+Type], 4
0x1400023b4  jnz     loc_140001CDD
0x1400023ba  cmp     dword ptr [rsp+58h+Data], 1
0x1400023bf  jnz     loc_140001CDD
0x1400023c5  xor     edx, edx; hFile
0x1400023c7  lea     rcx, LibFileName; "ppcoret.dll"
0x1400023ce  mov     r8d, 1000h; dwFlags
0x1400023d4  call    cs:__imp_LoadLibraryExW
0x1400023da  test    rax, rax
0x1400023dd  jnz     short loc_1400023EB
0x1400023df  add     rsp, 50h
0x1400023e3  pop     rbx
0x1400023e4  jmp     cs:__imp_GetLastError
0x1400023eb  lea     rdx, aPpmain_0; "PPMain"
0x1400023f2  mov     rcx, rax; hModule
0x1400023f5  call    cs:__imp_GetProcAddress
0x1400023fb  test    rax, rax
0x1400023fe  jnz     short loc_14000240B
0x140002400  mov     eax, 1
0x140002405  add     rsp, 50h
0x140002409  pop     rbx
0x14000240a  retn
0x14000240b  mov     rdx, cs:?ProcessStartTimeNanosecondsSinceEpoch@@3_JA; __int64 ProcessStartTimeNanosecondsSinceEpoch
0x140002412  mov     rcx, rbx
0x140002415  call    cs:__guard_dispatch_icall_fptr
0x14000241b  jmp     loc_140001CED
```
