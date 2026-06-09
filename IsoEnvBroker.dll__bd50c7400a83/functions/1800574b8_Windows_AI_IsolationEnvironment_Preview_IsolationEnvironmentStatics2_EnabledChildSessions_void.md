# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(void)

- ea: `0x1800574b8`
- end: `0x18005752d`
- name: `?EnabledChildSessions@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@AEAA_NXZ`
- size: `117`
- prototype: `bool __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800564f0`
- `0x180056d90`

## callees

- `0x1800574b8`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800574ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800574ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800574fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057519`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800574fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057519`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800574ce`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800574ce`

## string_xrefs

- `0x1800574c7`: `wtsapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *this)
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  bool v5; // di

  LibraryW = LoadLibraryW(L"wtsapi32.dll");
  v2 = LibraryW;
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "WTSEnableChildSessions");
  if ( !ProcAddress )
  {
    FreeLibrary(v2);
    return 0;
  }
  v5 = ((unsigned int (__fastcall *)(__int64))ProcAddress)(1) != 0;
  FreeLibrary(v2);
  return v5;
}

```

## disassembly

```asm
0x1800574b8  mov     [rsp+arg_8], rbx
0x1800574bd  mov     [rsp+arg_0], rcx
0x1800574c2  push    rdi
0x1800574c3  sub     rsp, 20h
0x1800574c7  lea     rcx, LibFileName; "wtsapi32.dll"
0x1800574ce  call    cs:__imp_LoadLibraryW
0x1800574d4  mov     rbx, rax
0x1800574d7  mov     [rsp+28h+arg_0], rax
0x1800574dc  test    rax, rax
0x1800574df  jnz     short loc_1800574E5
0x1800574e1  xor     al, al
0x1800574e3  jmp     short loc_180057522
0x1800574e5  lea     rdx, aWtsenablechild; "WTSEnableChildSessions"
0x1800574ec  mov     rcx, rbx; hModule
0x1800574ef  call    cs:__imp_GetProcAddress
0x1800574f5  test    rax, rax
0x1800574f8  jnz     short loc_180057505
0x1800574fa  mov     rcx, rbx; hLibModule
0x1800574fd  call    cs:__imp_FreeLibrary
0x180057503  jmp     short loc_1800574E1
0x180057505  mov     ecx, 1
0x18005750a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005750f  nop
0x180057510  test    eax, eax
0x180057512  setnz   dil
0x180057516  mov     rcx, rbx; hLibModule
0x180057519  call    cs:__imp_FreeLibrary
0x18005751f  mov     al, dil
0x180057522  mov     rbx, [rsp+28h+arg_8]
0x180057527  add     rsp, 20h
0x18005752b  pop     rdi
0x18005752c  retn
```
