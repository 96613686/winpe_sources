# LoadAndInitFeClient

- ea: `0x18003d76c`
- end: `0x18003d84a`
- name: `LoadAndInitFeClient`
- size: `222`
- prototype: `__int64()`
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034160`
- `0x180037120`
- `0x18003d1e0`
- `0x18003d250`
- `0x18003d3a0`
- `0x18003d420`
- `0x18003d550`
- `0x18003d5c0`
- `0x18003d6c0`
- `0x18003d910`
- `0x18003d980`
- `0x18003d9f0`
- `0x18003da80`
- `0x18003daf0`
- `0x18003db50`
- `0x18003dbd0`

## callees

- `0x18003d76c`
- `0x180066010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18003d7f1`
- `ntdll!DbgPrint` at `0x18003d7f1`
- `KERNEL32!EnterCriticalSection` at `0x18003d779`
- `KERNEL32!EnterCriticalSection` at `0x18003d779`
- `KERNEL32!LeaveCriticalSection` at `0x18003d800`
- `KERNEL32!LeaveCriticalSection` at `0x18003d824`
- `KERNEL32!LeaveCriticalSection` at `0x18003d800`
- `KERNEL32!LeaveCriticalSection` at `0x18003d824`
- `KERNEL32!GetLastError` at `0x18003d7b1`
- `KERNEL32!GetLastError` at `0x18003d7e2`
- `KERNEL32!GetLastError` at `0x18003d7b1`
- `KERNEL32!GetLastError` at `0x18003d7e2`
- `KERNEL32!GetProcAddress` at `0x18003d7ca`
- `KERNEL32!GetProcAddress` at `0x18003d7ca`
- `KERNEL32!FreeLibrary` at `0x18003d7dc`
- `KERNEL32!FreeLibrary` at `0x18003d835`
- `KERNEL32!FreeLibrary` at `0x18003d7dc`
- `KERNEL32!FreeLibrary` at `0x18003d835`
- `KERNEL32!LoadLibraryExW` at `0x18003d79f`
- `KERNEL32!LoadLibraryExW` at `0x18003d79f`

## string_xrefs

- `0x18003d792`: `feclient.dll`
- `0x18003d7b7`: `Unable to load client dll, error = %d\n`

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
0x18003d76c  push    rbx
0x18003d76e  sub     rsp, 20h
0x18003d772  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x18003d779  call    cs:__imp_EnterCriticalSection
0x18003d77f  cmp     cs:FeClientInfo, 0
0x18003d787  jz      short loc_18003D790
0x18003d789  mov     ebx, 1
0x18003d78e  jmp     short loc_18003D7F9
0x18003d790  xor     edx, edx; hFile
0x18003d792  lea     rcx, aFeclientDll; "feclient.dll"
0x18003d799  mov     r8d, 800h; dwFlags
0x18003d79f  call    cs:__imp_LoadLibraryExW
0x18003d7a5  mov     cs:FeClientModule, rax
0x18003d7ac  test    rax, rax
0x18003d7af  jnz     short loc_18003D7C0
0x18003d7b1  call    cs:__imp_GetLastError
0x18003d7b7  lea     rcx, aUnableToLoadCl; "Unable to load client dll, error = %d\n"
0x18003d7be  jmp     short loc_18003D7EF
0x18003d7c0  lea     rdx, aFeclientinitia; "FeClientInitialize"
0x18003d7c7  mov     rcx, rax; hModule
0x18003d7ca  call    cs:__imp_GetProcAddress
0x18003d7d0  test    rax, rax
0x18003d7d3  jnz     short loc_18003D80A
0x18003d7d5  mov     rcx, cs:FeClientModule; hLibModule
0x18003d7dc  call    cs:__imp_FreeLibrary
0x18003d7e2  call    cs:__imp_GetLastError
0x18003d7e8  lea     rcx, aUnableToLocate; "Unable to locate init routine, error = "...
0x18003d7ef  mov     edx, eax
0x18003d7f1  call    cs:__imp_DbgPrint
0x18003d7f7  xor     ebx, ebx
0x18003d7f9  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x18003d800  call    cs:__imp_LeaveCriticalSection
0x18003d806  mov     eax, ebx
0x18003d808  jmp     short loc_18003D844
0x18003d80a  lea     rdx, FeClientInfo
0x18003d811  mov     ecx, 10000h
0x18003d816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d81b  lea     rcx, FeClientLoadCritical; lpCriticalSection
0x18003d822  mov     ebx, eax
0x18003d824  call    cs:__imp_LeaveCriticalSection
0x18003d82a  test    ebx, ebx
0x18003d82c  jnz     short loc_18003D83F
0x18003d82e  mov     rcx, cs:FeClientModule; hLibModule
0x18003d835  call    cs:__imp_FreeLibrary
0x18003d83b  xor     eax, eax
0x18003d83d  jmp     short loc_18003D844
0x18003d83f  mov     eax, 1
0x18003d844  add     rsp, 20h
0x18003d848  pop     rbx
0x18003d849  retn
```
