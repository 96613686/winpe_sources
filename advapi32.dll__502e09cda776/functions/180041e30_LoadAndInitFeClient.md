# LoadAndInitFeClient

- ea: `0x180041e30`
- end: `0x180041f4e`
- name: `LoadAndInitFeClient`
- size: `286`
- prototype: `__int64()`
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180037ab0`
- `0x18003b130`
- `0x180041820`
- `0x180041890`
- `0x180041a00`
- `0x180041a90`
- `0x180041be0`
- `0x180041c60`
- `0x180041d80`
- `0x180042030`
- `0x1800420a0`
- `0x180042110`
- `0x1800421a0`
- `0x180042210`
- `0x180042270`
- `0x1800422f0`

## callees

- `0x180041e30`
- `0x180074010`

## import_xrefs

- `ntdll!DbgPrint` at `0x180041edc`
- `ntdll!DbgPrint` at `0x180041edc`
- `KERNEL32!EnterCriticalSection` at `0x180041e3d`
- `KERNEL32!EnterCriticalSection` at `0x180041e3d`
- `KERNEL32!LeaveCriticalSection` at `0x180041ef1`
- `KERNEL32!LeaveCriticalSection` at `0x180041f1b`
- `KERNEL32!LeaveCriticalSection` at `0x180041ef1`
- `KERNEL32!LeaveCriticalSection` at `0x180041f1b`
- `KERNEL32!GetLastError` at `0x180041e84`
- `KERNEL32!GetLastError` at `0x180041ec7`
- `KERNEL32!GetLastError` at `0x180041e84`
- `KERNEL32!GetLastError` at `0x180041ec7`
- `KERNEL32!GetProcAddress` at `0x180041ea3`
- `KERNEL32!GetProcAddress` at `0x180041ea3`
- `KERNEL32!FreeLibrary` at `0x180041ebb`
- `KERNEL32!FreeLibrary` at `0x180041f32`
- `KERNEL32!FreeLibrary` at `0x180041ebb`
- `KERNEL32!FreeLibrary` at `0x180041f32`
- `KERNEL32!LoadLibraryExW` at `0x180041e6c`
- `KERNEL32!LoadLibraryExW` at `0x180041e6c`

## string_xrefs

- `0x180041e5f`: `feclient.dll`
- `0x180041e90`: `Unable to load client dll, error = %d\n`

## pseudocode

```c
__int64 LoadAndInitFeClient()
{
  unsigned int v0; // ebx
  HMODULE Library; // rax
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  DWORD v4; // eax
  int v6; // ebx

  EnterCriticalSection(&FeClientLoadCritical);
  if ( FeClientInfo )
  {
    v0 = 1;
LABEL_8:
    LeaveCriticalSection(&FeClientLoadCritical);
    return v0;
  }
  Library = LoadLibraryExW(L"feclient.dll", 0, 0x800u);
  FeClientModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    DbgPrint("Unable to load client dll, error = %d\n", LastError);
LABEL_7:
    v0 = 0;
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(Library, "FeClientInitialize");
  if ( !ProcAddress )
  {
    FreeLibrary(FeClientModule);
    v4 = GetLastError();
    DbgPrint("Unable to locate init routine, error = %d\n", v4);
    goto LABEL_7;
  }
  v6 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(0x10000, &FeClientInfo);
  LeaveCriticalSection(&FeClientLoadCritical);
  if ( v6 )
    return 1;
  FreeLibrary(FeClientModule);
  return 0;
}

```

## disassembly

```asm
0x180041e30  push    rbx
0x180041e32  sub     rsp, 20h
0x180041e36  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x180041e3d  call    cs:__imp_EnterCriticalSection
0x180041e44  nop     dword ptr [rax+rax+00h]
0x180041e49  cmp     cs:FeClientInfo, 0
0x180041e51  jz      short loc_180041E5D
0x180041e53  mov     ebx, 1
0x180041e58  jmp     loc_180041EEA
0x180041e5d  xor     edx, edx; hFile
0x180041e5f  lea     rcx, aFeclientDll; "feclient.dll"
0x180041e66  mov     r8d, 800h; dwFlags
0x180041e6c  call    cs:__imp_LoadLibraryExW
0x180041e73  nop     dword ptr [rax+rax+00h]
0x180041e78  mov     cs:FeClientModule, rax
0x180041e7f  test    rax, rax
0x180041e82  jnz     short loc_180041E99
0x180041e84  call    cs:__imp_GetLastError
0x180041e8b  nop     dword ptr [rax+rax+00h]
0x180041e90  lea     rcx, aUnableToLoadCl; "Unable to load client dll, error = %d\n"
0x180041e97  jmp     short loc_180041EDA
0x180041e99  lea     rdx, aFeclientinitia; "FeClientInitialize"
0x180041ea0  mov     rcx, rax; hModule
0x180041ea3  call    cs:__imp_GetProcAddress
0x180041eaa  nop     dword ptr [rax+rax+00h]
0x180041eaf  test    rax, rax
0x180041eb2  jnz     short loc_180041F01
0x180041eb4  mov     rcx, cs:FeClientModule; hLibModule
0x180041ebb  call    cs:__imp_FreeLibrary
0x180041ec2  nop     dword ptr [rax+rax+00h]
0x180041ec7  call    cs:__imp_GetLastError
0x180041ece  nop     dword ptr [rax+rax+00h]
0x180041ed3  lea     rcx, aUnableToLocate; "Unable to locate init routine, error = "...
0x180041eda  mov     edx, eax
0x180041edc  call    cs:__imp_DbgPrint
0x180041ee3  nop     dword ptr [rax+rax+00h]
0x180041ee8  xor     ebx, ebx
0x180041eea  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x180041ef1  call    cs:__imp_LeaveCriticalSection
0x180041ef8  nop     dword ptr [rax+rax+00h]
0x180041efd  mov     eax, ebx
0x180041eff  jmp     short loc_180041F47
0x180041f01  lea     rdx, FeClientInfo
0x180041f08  mov     ecx, 10000h
0x180041f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f12  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x180041f19  mov     ebx, eax
0x180041f1b  call    cs:__imp_LeaveCriticalSection
0x180041f22  nop     dword ptr [rax+rax+00h]
0x180041f27  test    ebx, ebx
0x180041f29  jnz     short loc_180041F42
0x180041f2b  mov     rcx, cs:FeClientModule; hLibModule
0x180041f32  call    cs:__imp_FreeLibrary
0x180041f39  nop     dword ptr [rax+rax+00h]
0x180041f3e  xor     eax, eax
0x180041f40  jmp     short loc_180041F47
0x180041f42  mov     eax, 1
0x180041f47  add     rsp, 20h
0x180041f4b  pop     rbx
0x180041f4c  retn
```
